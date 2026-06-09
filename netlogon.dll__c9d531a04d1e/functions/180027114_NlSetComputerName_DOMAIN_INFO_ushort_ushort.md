# NlSetComputerName(_DOMAIN_INFO *,ushort *,ushort *)

- ea: `0x180027114`
- end: `0x1800273fe`
- name: `?NlSetComputerName@@YAKPEAU_DOMAIN_INFO@@PEAG1@Z`
- size: `746`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, LPCWCH lpWideCharStr, LPCWSTR lpSrcStr)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024f08`
- `0x18005360c`

## callees

- `0x18000ba1c`
- `0x18000bd98`
- `0x18000d710`
- `0x180026238`
- `0x180027114`
- `0x18003f648`
- `0x180082cc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002716c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002716c`
- `ntdll!RtlCreateUnicodeString` at `0x1800272d3`
- `ntdll!RtlCreateUnicodeString` at `0x1800272d3`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x1800271f1`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x1800271f1`
- `ntdll!RtlInitUnicodeString` at `0x1800271c7`
- `ntdll!RtlInitUnicodeString` at `0x1800273bc`
- `ntdll!RtlInitUnicodeString` at `0x1800271c7`
- `ntdll!RtlInitUnicodeString` at `0x1800273bc`
- `netutils!NetpwNameCanonicalize` at `0x180027191`
- `netutils!NetpwNameCanonicalize` at `0x180027191`

## string_xrefs

- `0x180027370`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`
- `0x180027148`: `Setting our computer name to %ws %ws\n`
- `0x1800271a1`: `ComputerName %ws is invalid\n`
- `0x180027210`: `Overflow error converting computer name to OEM %ws %lx\n`
- `0x180027290`: `Unable to convert computer name to OEM %ws %lx\n`
- `0x180027270`: `Unable to convert computer name to UTF8 %ws\n`
- `0x1800272e0`: `Unable to RtlCreateUnicodeString for host name %ws\n`

## pseudocode

```c
__int64 __fastcall NlSetComputerName(struct _DOMAIN_INFO *a1, LPCWCH lpWideCharStr, LPCWSTR lpSrcStr)
{
  NTSTATUS v6; // r14d
  char *Utf8StrFromWStr; // rax
  char *v8; // rcx
  __int64 v9; // rax
  struct _UNICODE_STRING *v10; // rcx
  char *v11; // rax
  LPCWCH *v12; // r14
  char *v13; // rax
  char *v14; // r9
  ULONG UnicodeSize[2]; // [rsp+20h] [rbp-20h]
  unsigned int v17; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v18; // [rsp+88h] [rbp+48h] BYREF

  v17 = 0;
  NlPrintDomRoutine(0x400u, a1, L"Setting our computer name to %ws %ws\n", lpWideCharStr, lpSrcStr);
  _o_wcscpy_s((char *)a1 + 216, 18);
  v17 = NetpwNameCanonicalize(lpWideCharStr, (char *)a1 + 220, 32);
  if ( v17 )
  {
    NlPrintDomRoutine(0x100u, a1, L"ComputerName %ws is invalid\n", lpWideCharStr);
    goto LABEL_25;
  }
  RtlInitUnicodeString((PUNICODE_STRING)a1 + 16, (PCWSTR)a1 + 110);
  v6 = RtlUpcaseUnicodeToOemN(
         (PCHAR)a1 + 312,
         0xFu,
         (PULONG)a1 + 82,
         *((PCWCH *)a1 + 33),
         *((unsigned __int16 *)a1 + 128));
  if ( v6 == -2147483643 )
  {
    UnicodeSize[0] = -2147483643;
    NlPrintDomRoutine(
      0x100u,
      a1,
      L"Overflow error converting computer name to OEM %ws %lx\n",
      lpWideCharStr,
      *(_QWORD *)UnicodeSize);
    if ( NlGlobalChangeLogRole == 2 )
    {
      NlPrintDomRoutine(0x800u, a1, L"Overriding STATUS_BUFFER_OVERFLOW error for workstation\n");
      *((_BYTE *)a1 + 327) = 0;
      goto LABEL_6;
    }
LABEL_10:
    UnicodeSize[0] = v6;
    NlPrintDomRoutine(
      0x100u,
      a1,
      L"Unable to convert computer name to OEM %ws %lx\n",
      lpWideCharStr,
      *(_QWORD *)UnicodeSize);
LABEL_11:
    v17 = 8;
LABEL_26:
    NlFreeComputerName(a1);
    return v17;
  }
  if ( v6 < 0 )
    goto LABEL_10;
LABEL_6:
  *((_BYTE *)a1 + *((unsigned int *)a1 + 82) + 312) = 0;
  Utf8StrFromWStr = NetpCreateUtf8StrFromWStr(lpWideCharStr, 0, 0);
  *((_QWORD *)a1 + 42) = Utf8StrFromWStr;
  v8 = Utf8StrFromWStr;
  if ( !Utf8StrFromWStr )
  {
    NlPrintDomRoutine(0x100u, a1, L"Unable to convert computer name to UTF8 %ws\n", lpWideCharStr);
    goto LABEL_11;
  }
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  *((_DWORD *)a1 + 86) = v9;
  v10 = (struct _UNICODE_STRING *)((char *)a1 + 272);
  if ( lpSrcStr )
  {
    if ( !RtlCreateUnicodeString(v10, lpSrcStr) )
    {
      NlPrintDomRoutine(0x100u, a1, L"Unable to RtlCreateUnicodeString for host name %ws\n", lpSrcStr);
      goto LABEL_11;
    }
    v11 = NetpCreateUtf8StrFromWStr(lpSrcStr, 0, 0);
    *((_QWORD *)a1 + 36) = v11;
    if ( !v11 )
    {
      NlPrintDomRoutine(0x100u, a1, L"Unable to convert host name to UTF8 %ws\n", lpSrcStr);
      goto LABEL_11;
    }
    v12 = (LPCWCH *)((char *)a1 + 296);
    v17 = NetpAllocLowerCaseWStrFromWStr(lpSrcStr, (unsigned __int16 **)a1 + 37);
    if ( v17 )
    {
      NlPrintDomRoutine(0x100u, a1, L"Unable to convert host name to lowercase %ws\n", lpSrcStr);
      NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\domain.cxx", 1727, v14);
      v18 = (unsigned __int16 *)v17;
      NlpWriteEventlog(0x16C1u, 1u, 0x40000000u, &v18, 1u, (unsigned __int8 *)&v17, 4u);
      goto LABEL_25;
    }
    v13 = NetpCreateUtf8StrFromWStr(*v12, 0, 0);
    *((_QWORD *)a1 + 38) = v13;
    if ( !v13 )
    {
      NlPrintDomRoutine(0x100u, a1, L"Unable to convert lowercase host name to UTF8 %ws\n", *v12);
      goto LABEL_11;
    }
  }
  else
  {
    RtlInitUnicodeString(v10, 0);
    *((_QWORD *)a1 + 36) = 0;
  }
  v17 = 0;
LABEL_25:
  if ( v17 )
    goto LABEL_26;
  return v17;
}

```

## disassembly

```asm
0x180027114  mov     [rsp-28h+arg_8], rbx
0x180027119  mov     [rsp-28h+arg_10], rsi
0x18002711e  push    rbp
0x18002711f  push    rdi
0x180027120  push    r12
0x180027122  push    r14
0x180027124  push    r15
0x180027126  mov     rbp, rsp
0x180027129  sub     rsp, 40h
0x18002712d  mov     r15, rdx
0x180027130  mov     qword ptr [rsp+40h+UnicodeSize], r8
0x180027135  mov     r9, rdx
0x180027138  mov     [rbp+arg_0], 0
0x18002713f  mov     rdx, rcx; struct _DOMAIN_INFO *
0x180027142  mov     rsi, r8
0x180027145  mov     rdi, rcx
0x180027148  lea     r8, aSettingOurComp; "Setting our computer name to %ws %ws\n"
0x18002714f  mov     ecx, 400h; unsigned int
0x180027154  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027159  lea     rcx, [rdi+0D8h]
0x180027160  mov     edx, 12h
0x180027165  lea     r8, String2; "\\\\"
0x18002716c  call    cs:__imp__o_wcscpy_s
0x180027172  mov     r9d, 4
0x180027178  mov     [rsp+40h+UnicodeSize], 0
0x180027180  lea     r14, [rdi+0DCh]
0x180027187  mov     rcx, r15
0x18002718a  mov     rdx, r14
0x18002718d  lea     r8d, [r9+1Ch]
0x180027191  call    cs:__imp_NetpwNameCanonicalize
0x180027197  mov     [rbp+arg_0], eax
0x18002719a  test    eax, eax
0x18002719c  jz      short loc_1800271BA
0x18002719e  mov     r9, r15
0x1800271a1  lea     r8, aComputernameWs; "ComputerName %ws is invalid\n"
0x1800271a8  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800271ab  mov     ecx, 100h; unsigned int
0x1800271b0  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800271b5  jmp     loc_1800273D4
0x1800271ba  lea     rbx, [rdi+100h]
0x1800271c1  mov     rdx, r14; SourceString
0x1800271c4  mov     rcx, rbx; DestinationString
0x1800271c7  call    cs:__imp_RtlInitUnicodeString
0x1800271cd  movzx   eax, word ptr [rbx]
0x1800271d0  lea     r12, [rdi+148h]
0x1800271d7  mov     r9, [rdi+108h]; UnicodeString
0x1800271de  lea     rcx, [rdi+138h]; OemString
0x1800271e5  mov     r8, r12; ResultSize
0x1800271e8  mov     [rsp+40h+UnicodeSize], eax; UnicodeSize
0x1800271ec  mov     edx, 0Fh; OemSize
0x1800271f1  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x1800271f7  mov     r14d, eax
0x1800271fa  mov     ebx, 100h
0x1800271ff  mov     eax, 80000005h
0x180027204  cmp     r14d, eax
0x180027207  jnz     short loc_180027283
0x180027209  mov     r9, r15
0x18002720c  mov     [rsp+40h+UnicodeSize], eax
0x180027210  lea     r8, aOverflowErrorC; "Overflow error converting computer name"...
0x180027217  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002721a  mov     ecx, ebx; unsigned int
0x18002721c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027221  cmp     cs:?NlGlobalChangeLogRole@@3W4_CHANGELOG_ROLE@@A, 2; _CHANGELOG_ROLE NlGlobalChangeLogRole
0x180027228  jnz     short loc_180027288
0x18002722a  lea     r8, aOverridingStat; "Overriding STATUS_BUFFER_OVERFLOW error"...
0x180027231  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180027234  mov     ecx, 800h; unsigned int
0x180027239  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002723e  mov     byte ptr [rdi+147h], 0
0x180027245  mov     eax, [r12]
0x180027249  xor     r8d, r8d; int
0x18002724c  xor     edx, edx; lpMultiByteStr
0x18002724e  mov     rcx, r15; lpWideCharStr
0x180027251  mov     byte ptr [rax+rdi+138h], 0
0x180027259  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x18002725e  mov     [rdi+150h], rax
0x180027265  mov     rcx, rax
0x180027268  test    rax, rax
0x18002726b  jnz     short loc_1800272AD
0x18002726d  mov     r9, r15
0x180027270  lea     r8, aUnableToConver_3; "Unable to convert computer name to UTF8"...
0x180027277  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002727a  mov     ecx, ebx; unsigned int
0x18002727c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027281  jmp     short loc_1800272A1
0x180027283  test    r14d, r14d
0x180027286  jns     short loc_180027245
0x180027288  mov     r9, r15
0x18002728b  mov     [rsp+40h+UnicodeSize], r14d
0x180027290  lea     r8, aUnableToConver; "Unable to convert computer name to OEM "...
0x180027297  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002729a  mov     ecx, ebx; unsigned int
0x18002729c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800272a1  mov     [rbp+arg_0], 8
0x1800272a8  jmp     loc_1800273DA
0x1800272ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800272b1  inc     rax
0x1800272b4  cmp     byte ptr [rcx+rax], 0
0x1800272b8  jnz     short loc_1800272B1
0x1800272ba  mov     [rdi+158h], eax
0x1800272c0  lea     rcx, [rdi+110h]; DestinationString
0x1800272c7  test    rsi, rsi
0x1800272ca  jz      loc_1800273BA
0x1800272d0  mov     rdx, rsi; SourceString
0x1800272d3  call    cs:__imp_RtlCreateUnicodeString
0x1800272d9  test    al, al
0x1800272db  jnz     short loc_1800272E9
0x1800272dd  mov     r9, rsi
0x1800272e0  lea     r8, aUnableToRtlcre; "Unable to RtlCreateUnicodeString for ho"...
0x1800272e7  jmp     short loc_180027277
0x1800272e9  xor     r8d, r8d; int
0x1800272ec  xor     edx, edx; lpMultiByteStr
0x1800272ee  mov     rcx, rsi; lpWideCharStr
0x1800272f1  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x1800272f6  mov     [rdi+120h], rax
0x1800272fd  test    rax, rax
0x180027300  jnz     short loc_180027311
0x180027302  mov     r9, rsi
0x180027305  lea     r8, aUnableToConver_0; "Unable to convert host name to UTF8 %ws"...
0x18002730c  jmp     loc_180027277
0x180027311  lea     r14, [rdi+128h]
0x180027318  mov     rcx, rsi; lpSrcStr
0x18002731b  mov     rdx, r14; unsigned __int16 **
0x18002731e  call    ?NetpAllocLowerCaseWStrFromWStr@@YAKPEBGPEAPEAG@Z; NetpAllocLowerCaseWStrFromWStr(ushort const *,ushort * *)
0x180027323  mov     [rbp+arg_0], eax
0x180027326  test    eax, eax
0x180027328  jnz     short loc_180027356
0x18002732a  mov     rcx, [r14]; lpWideCharStr
0x18002732d  xor     r8d, r8d; int
0x180027330  xor     edx, edx; lpMultiByteStr
0x180027332  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180027337  mov     [rdi+130h], rax
0x18002733e  test    rax, rax
0x180027341  jnz     loc_1800273CD
0x180027347  mov     r9, [r14]
0x18002734a  lea     r8, aUnableToConver_2; "Unable to convert lowercase host name t"...
0x180027351  jmp     loc_180027277
0x180027356  mov     r9, rsi
0x180027359  lea     r8, aUnableToConver_1; "Unable to convert host name to lowercas"...
0x180027360  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180027363  mov     ecx, ebx; unsigned int
0x180027365  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002736a  mov     r8d, 6BFh; unsigned int
0x180027370  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180027377  lea     rcx, aFalse; "FALSE"
0x18002737e  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180027383  mov     eax, [rbp+arg_0]
0x180027386  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x18002738a  mov     [rbp+arg_18], rax
0x18002738e  mov     edx, 1; unsigned int
0x180027393  lea     rax, [rbp+arg_0]
0x180027397  mov     [rsp+40h+var_10], 4; unsigned int
0x18002739f  mov     [rsp+40h+var_18], rax; unsigned __int8 *
0x1800273a4  mov     ecx, 16C1h; unsigned int
0x1800273a9  mov     r8d, 40000000h; unsigned int
0x1800273af  mov     [rsp+40h+UnicodeSize], edx; unsigned int
0x1800273b3  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x1800273b8  jmp     short loc_1800273D4
0x1800273ba  xor     edx, edx; SourceString
0x1800273bc  call    cs:__imp_RtlInitUnicodeString
0x1800273c2  mov     qword ptr [rdi+120h], 0
0x1800273cd  mov     [rbp+arg_0], 0
0x1800273d4  cmp     [rbp+arg_0], 0
0x1800273d8  jz      short loc_1800273E2
0x1800273da  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800273dd  call    ?NlFreeComputerName@@YAXPEAU_DOMAIN_INFO@@@Z; NlFreeComputerName(_DOMAIN_INFO *)
0x1800273e2  mov     eax, [rbp+arg_0]
0x1800273e5  lea     r11, [rsp+40h+var_s0]
0x1800273ea  mov     rbx, [r11+38h]
0x1800273ee  mov     rsi, [r11+40h]
0x1800273f2  mov     rsp, r11
0x1800273f5  pop     r15
0x1800273f7  pop     r14
0x1800273f9  pop     r12
0x1800273fb  pop     rdi
0x1800273fc  pop     rbp
0x1800273fd  retn
```
