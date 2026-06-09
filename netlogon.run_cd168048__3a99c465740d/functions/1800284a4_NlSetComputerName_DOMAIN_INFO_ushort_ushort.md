# NlSetComputerName(_DOMAIN_INFO *,ushort *,ushort *)

- ea: `0x1800284a4`
- end: `0x1800287b3`
- name: `?NlSetComputerName@@YAKPEAU_DOMAIN_INFO@@PEAG1@Z`
- size: `783`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, LPCWCH lpWideCharStr, LPCWSTR lpSrcStr)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025f54`
- `0x180056fd4`

## callees

- `0x18000c130`
- `0x18000c440`
- `0x18000dd00`
- `0x180027424`
- `0x1800284a4`
- `0x180041f80`
- `0x180088e04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800284fc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800284fc`
- `ntdll!RtlCreateUnicodeString` at `0x18002867b`
- `ntdll!RtlCreateUnicodeString` at `0x18002867b`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x180028593`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x180028593`
- `ntdll!RtlInitUnicodeString` at `0x180028563`
- `ntdll!RtlInitUnicodeString` at `0x18002876a`
- `ntdll!RtlInitUnicodeString` at `0x180028563`
- `ntdll!RtlInitUnicodeString` at `0x18002876a`
- `netutils!NetpwNameCanonicalize` at `0x180028527`
- `netutils!NetpwNameCanonicalize` at `0x180028527`

## string_xrefs

- `0x18002871e`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`
- `0x1800284d8`: `Setting our computer name to %ws %ws\n`
- `0x18002853d`: `ComputerName %ws is invalid\n`
- `0x1800285b8`: `Overflow error converting computer name to OEM %ws %lx\n`
- `0x180028638`: `Unable to convert computer name to OEM %ws %lx\n`
- `0x180028618`: `Unable to convert computer name to UTF8 %ws\n`
- `0x18002868e`: `Unable to RtlCreateUnicodeString for host name %ws\n`

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
  _o_wcscpy_s((char *)a1 + 216, 18, L"\\\\");
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
      NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\domain.cxx", 0x6BFu, v14);
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
0x1800284a4  mov     [rsp-28h+arg_8], rbx
0x1800284a9  mov     [rsp-28h+arg_10], rsi
0x1800284ae  push    rbp
0x1800284af  push    rdi
0x1800284b0  push    r12
0x1800284b2  push    r14
0x1800284b4  push    r15
0x1800284b6  mov     rbp, rsp
0x1800284b9  sub     rsp, 40h
0x1800284bd  mov     r15, rdx
0x1800284c0  mov     qword ptr [rsp+40h+UnicodeSize], r8
0x1800284c5  mov     r9, rdx
0x1800284c8  mov     [rbp+arg_0], 0
0x1800284cf  mov     rdx, rcx; struct _DOMAIN_INFO *
0x1800284d2  mov     rsi, r8
0x1800284d5  mov     rdi, rcx
0x1800284d8  lea     r8, aSettingOurComp; "Setting our computer name to %ws %ws\n"
0x1800284df  mov     ecx, 400h; unsigned int
0x1800284e4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800284e9  lea     rcx, [rdi+0D8h]
0x1800284f0  mov     edx, 12h
0x1800284f5  lea     r8, String2; "\\\\"
0x1800284fc  call    cs:__imp__o_wcscpy_s
0x180028503  nop     dword ptr [rax+rax+00h]
0x180028508  mov     r9d, 4
0x18002850e  mov     [rsp+40h+UnicodeSize], 0
0x180028516  lea     r14, [rdi+0DCh]
0x18002851d  mov     rcx, r15
0x180028520  mov     rdx, r14
0x180028523  lea     r8d, [r9+1Ch]
0x180028527  call    cs:__imp_NetpwNameCanonicalize
0x18002852e  nop     dword ptr [rax+rax+00h]
0x180028533  mov     [rbp+arg_0], eax
0x180028536  test    eax, eax
0x180028538  jz      short loc_180028556
0x18002853a  mov     r9, r15
0x18002853d  lea     r8, aComputernameWs; "ComputerName %ws is invalid\n"
0x180028544  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180028547  mov     ecx, 100h; unsigned int
0x18002854c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180028551  jmp     loc_180028788
0x180028556  lea     rbx, [rdi+100h]
0x18002855d  mov     rdx, r14; SourceString
0x180028560  mov     rcx, rbx; DestinationString
0x180028563  call    cs:__imp_RtlInitUnicodeString
0x18002856a  nop     dword ptr [rax+rax+00h]
0x18002856f  movzx   eax, word ptr [rbx]
0x180028572  lea     r12, [rdi+148h]
0x180028579  mov     r9, [rdi+108h]; UnicodeString
0x180028580  lea     rcx, [rdi+138h]; OemString
0x180028587  mov     r8, r12; ResultSize
0x18002858a  mov     [rsp+40h+UnicodeSize], eax; UnicodeSize
0x18002858e  mov     edx, 0Fh; OemSize
0x180028593  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x18002859a  nop     dword ptr [rax+rax+00h]
0x18002859f  mov     r14d, eax
0x1800285a2  mov     ebx, 100h
0x1800285a7  mov     eax, 80000005h
0x1800285ac  cmp     r14d, eax
0x1800285af  jnz     short loc_18002862B
0x1800285b1  mov     r9, r15
0x1800285b4  mov     [rsp+40h+UnicodeSize], eax
0x1800285b8  lea     r8, aOverflowErrorC; "Overflow error converting computer name"...
0x1800285bf  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800285c2  mov     ecx, ebx; unsigned int
0x1800285c4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800285c9  cmp     cs:?NlGlobalChangeLogRole@@3W4_CHANGELOG_ROLE@@A, 2; _CHANGELOG_ROLE NlGlobalChangeLogRole
0x1800285d0  jnz     short loc_180028630
0x1800285d2  lea     r8, aOverridingStat; "Overriding STATUS_BUFFER_OVERFLOW error"...
0x1800285d9  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800285dc  mov     ecx, 800h; unsigned int
0x1800285e1  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800285e6  mov     byte ptr [rdi+147h], 0
0x1800285ed  mov     eax, [r12]
0x1800285f1  xor     r8d, r8d; int
0x1800285f4  xor     edx, edx; lpMultiByteStr
0x1800285f6  mov     rcx, r15; lpWideCharStr
0x1800285f9  mov     byte ptr [rax+rdi+138h], 0
0x180028601  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180028606  mov     [rdi+150h], rax
0x18002860d  mov     rcx, rax
0x180028610  test    rax, rax
0x180028613  jnz     short loc_180028655
0x180028615  mov     r9, r15
0x180028618  lea     r8, aUnableToConver_3; "Unable to convert computer name to UTF8"...
0x18002861f  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180028622  mov     ecx, ebx; unsigned int
0x180028624  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180028629  jmp     short loc_180028649
0x18002862b  test    r14d, r14d
0x18002862e  jns     short loc_1800285ED
0x180028630  mov     r9, r15
0x180028633  mov     [rsp+40h+UnicodeSize], r14d
0x180028638  lea     r8, aUnableToConver; "Unable to convert computer name to OEM "...
0x18002863f  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180028642  mov     ecx, ebx; unsigned int
0x180028644  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180028649  mov     [rbp+arg_0], 8
0x180028650  jmp     loc_18002878E
0x180028655  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028659  inc     rax
0x18002865c  cmp     byte ptr [rcx+rax], 0
0x180028660  jnz     short loc_180028659
0x180028662  mov     [rdi+158h], eax
0x180028668  lea     rcx, [rdi+110h]; DestinationString
0x18002866f  test    rsi, rsi
0x180028672  jz      loc_180028768
0x180028678  mov     rdx, rsi; SourceString
0x18002867b  call    cs:__imp_RtlCreateUnicodeString
0x180028682  nop     dword ptr [rax+rax+00h]
0x180028687  test    al, al
0x180028689  jnz     short loc_180028697
0x18002868b  mov     r9, rsi
0x18002868e  lea     r8, aUnableToRtlcre; "Unable to RtlCreateUnicodeString for ho"...
0x180028695  jmp     short loc_18002861F
0x180028697  xor     r8d, r8d; int
0x18002869a  xor     edx, edx; lpMultiByteStr
0x18002869c  mov     rcx, rsi; lpWideCharStr
0x18002869f  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x1800286a4  mov     [rdi+120h], rax
0x1800286ab  test    rax, rax
0x1800286ae  jnz     short loc_1800286BF
0x1800286b0  mov     r9, rsi
0x1800286b3  lea     r8, aUnableToConver_0; "Unable to convert host name to UTF8 %ws"...
0x1800286ba  jmp     loc_18002861F
0x1800286bf  lea     r14, [rdi+128h]
0x1800286c6  mov     rcx, rsi; lpSrcStr
0x1800286c9  mov     rdx, r14; unsigned __int16 **
0x1800286cc  call    ?NetpAllocLowerCaseWStrFromWStr@@YAKPEBGPEAPEAG@Z; NetpAllocLowerCaseWStrFromWStr(ushort const *,ushort * *)
0x1800286d1  mov     [rbp+arg_0], eax
0x1800286d4  test    eax, eax
0x1800286d6  jnz     short loc_180028704
0x1800286d8  mov     rcx, [r14]; lpWideCharStr
0x1800286db  xor     r8d, r8d; int
0x1800286de  xor     edx, edx; lpMultiByteStr
0x1800286e0  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x1800286e5  mov     [rdi+130h], rax
0x1800286ec  test    rax, rax
0x1800286ef  jnz     loc_180028781
0x1800286f5  mov     r9, [r14]
0x1800286f8  lea     r8, aUnableToConver_2; "Unable to convert lowercase host name t"...
0x1800286ff  jmp     loc_18002861F
0x180028704  mov     r9, rsi
0x180028707  lea     r8, aUnableToConver_1; "Unable to convert host name to lowercas"...
0x18002870e  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180028711  mov     ecx, ebx; unsigned int
0x180028713  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180028718  mov     r8d, 6BFh; unsigned int
0x18002871e  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180028725  lea     rcx, aFalse; "FALSE"
0x18002872c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180028731  mov     eax, [rbp+arg_0]
0x180028734  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x180028738  mov     [rbp+arg_18], rax
0x18002873c  mov     edx, 1; unsigned int
0x180028741  lea     rax, [rbp+arg_0]
0x180028745  mov     [rsp+40h+var_10], 4; unsigned int
0x18002874d  mov     [rsp+40h+var_18], rax; unsigned __int8 *
0x180028752  mov     ecx, 16C1h; unsigned int
0x180028757  mov     r8d, 40000000h; unsigned int
0x18002875d  mov     [rsp+40h+UnicodeSize], edx; unsigned int
0x180028761  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180028766  jmp     short loc_180028788
0x180028768  xor     edx, edx; SourceString
0x18002876a  call    cs:__imp_RtlInitUnicodeString
0x180028771  nop     dword ptr [rax+rax+00h]
0x180028776  mov     qword ptr [rdi+120h], 0
0x180028781  mov     [rbp+arg_0], 0
0x180028788  cmp     [rbp+arg_0], 0
0x18002878c  jz      short loc_180028796
0x18002878e  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180028791  call    ?NlFreeComputerName@@YAXPEAU_DOMAIN_INFO@@@Z; NlFreeComputerName(_DOMAIN_INFO *)
0x180028796  mov     eax, [rbp+arg_0]
0x180028799  lea     r11, [rsp+40h+var_s0]
0x18002879e  mov     rbx, [r11+38h]
0x1800287a2  mov     rsi, [r11+40h]
0x1800287a6  mov     rsp, r11
0x1800287a9  pop     r15
0x1800287ab  pop     r14
0x1800287ad  pop     r12
0x1800287af  pop     rdi
0x1800287b0  pop     rbp
0x1800287b1  retn
```
