# DhcpCreateListFromStringAndFree

- ea: `0x1800044cc`
- end: `0x1800046a9`
- name: `DhcpCreateListFromStringAndFree`
- size: `477`
- prototype: `__int64 __fastcall(PCWSTR SourceString, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800042b8`

## callees

- `0x180003cdc`
- `0x1800044cc`
- `0x1800057f0`
- `0x180006440`
- `0x18001cef0`
- `0x18004d200`

## import_xrefs

- `ntdll!RtlxUnicodeStringToOemSize` at `0x1800045be`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x1800045be`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800045e0`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800045e0`
- `ntdll!RtlInitUnicodeString` at `0x1800045b3`
- `ntdll!RtlInitUnicodeString` at `0x1800045b3`
- `WS2_32!__imp_inet_addr` at `0x1800045f7`
- `WS2_32!__imp_inet_addr` at `0x180004604`
- `WS2_32!__imp_inet_addr` at `0x1800045f7`
- `WS2_32!__imp_inet_addr` at `0x180004604`

## pseudocode

```c
__int64 __fastcall DhcpCreateListFromStringAndFree(PCWSTR SourceString, __int64 a2, unsigned int *a3)
{
  const WCHAR *v4; // rdi
  __int64 result; // rax
  __int64 v6; // rax
  PCWSTR v7; // rbx
  unsigned int v8; // esi
  _WORD *v9; // rax
  __int64 v10; // rbx
  unsigned int v11; // r14d
  unsigned int i; // r12d
  const char *Buffer; // r15
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  PCWSTR v17; // [rsp+20h] [rbp-E0h] BYREF
  _STRING v18; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID v19; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  char v21; // [rsp+50h] [rbp-B0h] BYREF

  v17 = SourceString;
  *a3 = 0;
  v4 = SourceString;
  if ( !SourceString )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( SourceString[v6] );
  v7 = SourceString;
  v8 = v6 != 0;
  while ( x_wcschr(v7) )
  {
    v9 = (_WORD *)x_wcschr(v7);
    if ( !v9 )
      goto LABEL_12;
    v7 = v9 + 1;
    *v9 = 0;
    ++v8;
  }
  if ( !v8 )
  {
    DhcpPunycodeFree(&v17);
    return 0;
  }
  v19 = DhcpAlloc(4LL * v8);
  v10 = (__int64)v19;
  if ( !v19 )
  {
LABEL_12:
    v11 = 0;
LABEL_25:
    v10 = 0;
    goto LABEL_26;
  }
  v11 = 0;
  for ( i = 0; i < v8; ++i )
  {
    v18 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v4);
    v18.MaximumLength = RtlxUnicodeStringToOemSize(&DestinationString);
    v18.Buffer = &v21;
    if ( RtlUnicodeStringToOemString(&v18, &DestinationString, 0) >= 0 && (Buffer = v18.Buffer) != 0 )
    {
      if ( inet_addr(v18.Buffer) )
      {
        v14 = inet_addr(Buffer);
        v15 = v11++;
        *(_DWORD *)(v10 + 4 * v15) = v14;
      }
    }
    else if ( (xmmword_1800616A0 & 2) != 0 )
    {
      WPP_SF_S(1025, 20, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, v4);
    }
    v16 = -1;
    do
      ++v16;
    while ( v4[v16] );
    v4 += v16 + 1;
  }
  if ( !v11 )
  {
    DhcpPunycodeFree(&v19);
    goto LABEL_25;
  }
LABEL_26:
  DhcpPunycodeFree(&v17);
  result = v10;
  *a3 = v11;
  return result;
}

```

## disassembly

```asm
0x1800044cc  mov     [rsp-8+arg_8], rbx
0x1800044d1  push    rbp
0x1800044d2  push    rsi
0x1800044d3  push    rdi
0x1800044d4  push    r12
0x1800044d6  push    r13
0x1800044d8  push    r14
0x1800044da  push    r15
0x1800044dc  lea     rbp, [rsp-350h]
0x1800044e4  sub     rsp, 450h
0x1800044eb  mov     rax, cs:__security_cookie
0x1800044f2  xor     rax, rsp
0x1800044f5  mov     [rbp+380h+var_40], rax
0x1800044fc  xor     r15d, r15d
0x1800044ff  mov     [rsp+480h+var_460], rcx
0x180004504  mov     [r8], r15d
0x180004507  mov     r13, r8
0x18000450a  mov     rdi, rcx
0x18000450d  test    rcx, rcx
0x180004510  jnz     short loc_180004519
0x180004512  xor     eax, eax
0x180004514  jmp     loc_18000467F
0x180004519  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000451d  inc     rax
0x180004520  cmp     [rcx+rax*2], r15w
0x180004525  jnz     short loc_18000451D
0x180004527  test    rax, rax
0x18000452a  mov     esi, r15d
0x18000452d  mov     rbx, rcx
0x180004530  setnz   sil
0x180004534  mov     rcx, rbx
0x180004537  call    x_wcschr
0x18000453c  test    rax, rax
0x18000453f  jz      short loc_18000455D
0x180004541  mov     rcx, rbx
0x180004544  call    x_wcschr
0x180004549  mov     rbx, rax
0x18000454c  test    rax, rax
0x18000454f  jz      short loc_180004585
0x180004551  add     rbx, 2
0x180004555  mov     [rax], r15w
0x180004559  inc     esi
0x18000455b  jmp     short loc_180004534
0x18000455d  test    esi, esi
0x18000455f  jnz     short loc_18000456D
0x180004561  lea     rcx, [rsp+480h+var_460]
0x180004566  call    DhcpPunycodeFree
0x18000456b  jmp     short loc_180004512
0x18000456d  mov     ecx, esi
0x18000456f  shl     rcx, 2
0x180004573  call    DhcpAlloc
0x180004578  mov     [rsp+480h+var_448], rax
0x18000457d  mov     rbx, rax
0x180004580  test    rax, rax
0x180004583  jnz     short loc_18000458D
0x180004585  mov     r14d, r15d
0x180004588  jmp     loc_18000466B
0x18000458d  mov     r14d, r15d
0x180004590  mov     r12d, r15d
0x180004593  test    esi, esi
0x180004595  jz      loc_180004661
0x18000459b  xorps   xmm0, xmm0
0x18000459e  lea     rcx, [rsp+480h+DestinationString]; DestinationString
0x1800045a3  xorps   xmm1, xmm1
0x1800045a6  mov     rdx, rdi; SourceString
0x1800045a9  movups  xmmword ptr [rsp+480h+var_458.Length], xmm0
0x1800045ae  movups  xmmword ptr [rsp+480h+DestinationString.Length], xmm1
0x1800045b3  call    cs:__imp_RtlInitUnicodeString
0x1800045b9  lea     rcx, [rsp+480h+DestinationString]; UnicodeString
0x1800045be  call    cs:__imp_RtlxUnicodeStringToOemSize
0x1800045c4  mov     [rsp+480h+var_458.MaximumLength], ax
0x1800045c9  xor     r8d, r8d; AllocateDestinationString
0x1800045cc  lea     rdx, [rsp+480h+DestinationString]; SourceString
0x1800045d1  lea     rax, [rsp+480h+var_430]
0x1800045d6  lea     rcx, [rsp+480h+var_458]; DestinationString
0x1800045db  mov     [rsp+480h+var_458.Buffer], rax
0x1800045e0  call    cs:__imp_RtlUnicodeStringToOemString
0x1800045e6  test    eax, eax
0x1800045e8  js      short loc_180004615
0x1800045ea  mov     r15, [rsp+480h+var_458.Buffer]
0x1800045ef  test    r15, r15
0x1800045f2  jz      short loc_180004615
0x1800045f4  mov     rcx, r15; cp
0x1800045f7  call    cs:__imp_inet_addr
0x1800045fd  test    eax, eax
0x1800045ff  jz      short loc_180004637
0x180004601  mov     rcx, r15; cp
0x180004604  call    cs:__imp_inet_addr
0x18000460a  mov     ecx, r14d
0x18000460d  inc     r14d
0x180004610  mov     [rbx+rcx*4], eax
0x180004613  jmp     short loc_180004637
0x180004615  test    byte ptr cs:xmmword_1800616A0, 2
0x18000461c  jz      short loc_180004637
0x18000461e  mov     edx, 14h
0x180004623  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x18000462a  mov     ecx, 401h
0x18000462f  mov     r9, rdi
0x180004632  call    WPP_SF_S
0x180004637  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000463b  xor     r15d, r15d
0x18000463e  inc     rax
0x180004641  cmp     [rdi+rax*2], r15w
0x180004646  jnz     short loc_18000463E
0x180004648  lea     rdi, [rdi+rax*2]
0x18000464c  inc     r12d
0x18000464f  add     rdi, 2
0x180004653  cmp     r12d, esi
0x180004656  jb      loc_18000459B
0x18000465c  test    r14d, r14d
0x18000465f  jnz     short loc_18000466E
0x180004661  lea     rcx, [rsp+480h+var_448]
0x180004666  call    DhcpPunycodeFree
0x18000466b  mov     rbx, r15
0x18000466e  lea     rcx, [rsp+480h+var_460]
0x180004673  call    DhcpPunycodeFree
0x180004678  mov     rax, rbx
0x18000467b  mov     [r13+0], r14d
0x18000467f  mov     rcx, [rbp+380h+var_40]
0x180004686  xor     rcx, rsp; StackCookie
0x180004689  call    __security_check_cookie
0x18000468e  mov     rbx, [rsp+480h+arg_8]
0x180004696  add     rsp, 450h
0x18000469d  pop     r15
0x18000469f  pop     r14
0x1800046a1  pop     r13
0x1800046a3  pop     r12
0x1800046a5  pop     rdi
0x1800046a6  pop     rsi
0x1800046a7  pop     rbp
0x1800046a8  retn
```
