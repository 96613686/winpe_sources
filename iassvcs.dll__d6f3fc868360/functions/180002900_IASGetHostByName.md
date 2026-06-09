# IASGetHostByName

- ea: `0x180002900`
- end: `0x180002b8f`
- name: `IASGetHostByName`
- size: `655`
- prototype: `__int64 __fastcall(const WCHAR *, PADDRINFOW *ppResult)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002900`
- `0x18000d2d8`
- `0x180017754`
- `0x180017a84`
- `0x1800181e0`
- `0x1800182a0`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x180002956`
- `KERNEL32!GetComputerNameExW` at `0x180002a12`
- `KERNEL32!GetComputerNameExW` at `0x180002956`
- `KERNEL32!GetComputerNameExW` at `0x180002a12`
- `KERNEL32!FormatMessageW` at `0x180002acd`
- `KERNEL32!FormatMessageW` at `0x180002b09`
- `KERNEL32!FormatMessageW` at `0x180002acd`
- `KERNEL32!FormatMessageW` at `0x180002b09`
- `KERNEL32!GetLastError` at `0x180002a1c`
- `KERNEL32!GetLastError` at `0x180002a1c`
- `WS2_32!FreeAddrInfoW` at `0x180002b50`
- `WS2_32!FreeAddrInfoW` at `0x180002b50`
- `WS2_32!GetAddrInfoW` at `0x180002a6a`
- `WS2_32!GetAddrInfoW` at `0x180002a6a`

## pseudocode

```c
__int64 __fastcall IASGetHostByName(const WCHAR *a1, PADDRINFOW *ppResult)
{
  const WCHAR *v3; // r14
  __int64 v4; // rax
  unsigned __int64 v5; // rdi
  DWORD *p_nSize; // rbx
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  _DWORD *v11; // rax
  signed int LastError; // eax
  unsigned int v14; // edi
  INT AddrInfoW; // esi
  __int64 v16; // [rsp+0h] [rbp-40h] BYREF
  DWORD nSize; // [rsp+40h] [rbp+0h] BYREF
  __int64 v18; // [rsp+48h] [rbp+8h] BYREF
  ADDRINFOW pHints; // [rsp+50h] [rbp+10h] BYREF

  v3 = a1;
  memset(&pHints, 0, sizeof(pHints));
  *ppResult = 0;
  v4 = 0;
  nSize = 0;
  if ( !a1 )
  {
    GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, 0, &nSize);
    v4 = nSize;
  }
  v5 = 2 * v4;
  p_nSize = 0;
  if ( !(2 * v4)
    || v5 > g_ulMaxStackAllocSize
    || v5 + g_ulAdditionalProbeSize + 8 < v5
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_11;
  }
  v7 = v5 + 23;
  if ( v5 + 23 <= v5 + 8 )
    v7 = 0xFFFFFFFFFFFFFF0LL;
  v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
  v9 = alloca(v8);
  v10 = alloca(v8);
  p_nSize = &nSize;
  if ( &v16 == (__int64 *)-64LL || (nSize = 1801679955, (p_nSize = (DWORD *)&v18) == 0) )
  {
LABEL_11:
    if ( v5 + 8 >= v5 )
    {
      v11 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v11 )
        return 2147942414LL;
      *v11 = 1885431112;
      p_nSize = v11 + 2;
    }
    if ( !p_nSize )
      return 2147942414LL;
  }
  if ( v3 )
    goto LABEL_25;
  if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, (LPWSTR)p_nSize, &nSize) )
  {
    v3 = (const WCHAR *)p_nSize;
LABEL_25:
    v14 = 0;
    *(_QWORD *)&pHints.ai_flags = 1024;
    AddrInfoW = GetAddrInfoW(v3, 0, &pHints, ppResult);
    if ( AddrInfoW )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        FormatMessageW(0x12FFu, 0, AddrInfoW, 0x400u, &`gai_strerrorW'::`2'::buff, 0x400u, 0);
        WppDbgPrint("GetAddrInfo (name resolution) failed for %S; error = %lu (%S)");
        FormatMessageW(0x12FFu, 0, AddrInfoW, 0x400u, &`gai_strerrorW'::`2'::buff, 0x400u, 0);
        WPP_SF_sSLS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v3, AddrInfoW, (__int64)&`gai_strerrorW'::`2'::buff);
      }
      if ( AddrInfoW > 0 )
        v14 = (unsigned __int16)AddrInfoW | 0x80070000;
      else
        v14 = AddrInfoW;
      if ( *ppResult )
        FreeAddrInfoW(*ppResult);
    }
    if ( p_nSize && *(p_nSize - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    return v14;
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( LastError > 0 )
    v14 = (unsigned __int16)LastError | 0x80070000;
  if ( p_nSize )
  {
    if ( *(p_nSize - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v14;
}

```

## disassembly

```asm
0x180002900  push    rbp
0x180002902  push    rbx
0x180002903  push    rsi
0x180002904  push    rdi
0x180002905  push    r12
0x180002907  push    r14
0x180002909  push    r15
0x18000290b  sub     rsp, 90h
0x180002912  lea     rbp, [rsp+40h]
0x180002917  mov     rax, cs:__security_cookie
0x18000291e  xor     rax, rbp
0x180002921  mov     [rbp+80h+var_40], rax
0x180002925  mov     r15, rdx
0x180002928  mov     r14, rcx
0x18000292b  xorps   xmm0, xmm0
0x18000292e  movups  xmmword ptr [rbp+80h+pHints.ai_flags], xmm0
0x180002932  movups  xmmword ptr [rbp+80h+pHints.ai_addrlen], xmm0
0x180002936  movups  xmmword ptr [rbp+80h+pHints.ai_addr], xmm0
0x18000293a  mov     qword ptr [rdx], 0
0x180002941  xor     eax, eax
0x180002943  mov     [rbp+80h+nSize], eax
0x180002946  lea     esi, [rax+7]
0x180002949  test    rcx, rcx
0x18000294c  jnz     short loc_18000295F
0x18000294e  lea     r8, [rbp+80h+nSize]; nSize
0x180002952  xor     edx, edx; lpBuffer
0x180002954  mov     ecx, esi; NameType
0x180002956  call    cs:__imp_GetComputerNameExW
0x18000295c  mov     eax, [rbp+80h+nSize]
0x18000295f  lea     rdi, [rax+rax]
0x180002963  xor     ebx, ebx
0x180002965  mov     r12d, 70616548h
0x18000296b  test    rdi, rdi
0x18000296e  jz      short loc_1800029D1
0x180002970  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180002977  ja      short loc_1800029D1
0x180002979  mov     rcx, cs:g_ulAdditionalProbeSize
0x180002980  add     rcx, 8
0x180002984  add     rcx, rdi
0x180002987  cmp     rcx, rdi
0x18000298a  jb      short loc_1800029D1
0x18000298c  call    VerifyStackAvailable
0x180002991  test    eax, eax
0x180002993  jz      short loc_1800029D1
0x180002995  lea     rax, [rdi+8]
0x180002999  lea     rcx, [rax+0Fh]
0x18000299d  cmp     rcx, rax
0x1800029a0  ja      short loc_1800029AC
0x1800029a2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800029ac  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800029b0  mov     rax, rcx
0x1800029b3  call    _alloca_probe
0x1800029b8  sub     rsp, rcx
0x1800029bb  lea     rbx, [rsp+0C0h+nSize]
0x1800029c0  test    rbx, rbx
0x1800029c3  jz      short loc_1800029D1
0x1800029c5  mov     dword ptr [rbx], 6B637453h
0x1800029cb  add     rbx, 8
0x1800029cf  jnz     short loc_180002A04
0x1800029d1  lea     rcx, [rdi+8]
0x1800029d5  cmp     rcx, rdi
0x1800029d8  jb      short loc_1800029F5
0x1800029da  mov     rax, cs:g_pfnAllocate
0x1800029e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e6  mov     rbx, rax
0x1800029e9  test    rax, rax
0x1800029ec  jz      short loc_1800029FA
0x1800029ee  mov     [rax], r12d
0x1800029f1  add     rbx, 8
0x1800029f5  test    rbx, rbx
0x1800029f8  jnz     short loc_180002A04
0x1800029fa  mov     eax, 8007000Eh
0x1800029ff  jmp     loc_180002B74
0x180002a04  test    r14, r14
0x180002a07  jnz     short loc_180002A54
0x180002a09  lea     r8, [rbp+80h+nSize]; nSize
0x180002a0d  mov     rdx, rbx; lpBuffer
0x180002a10  mov     ecx, esi; NameType
0x180002a12  call    cs:__imp_GetComputerNameExW
0x180002a18  test    eax, eax
0x180002a1a  jnz     short loc_180002A51
0x180002a1c  call    cs:__imp_GetLastError
0x180002a22  mov     edi, eax
0x180002a24  test    eax, eax
0x180002a26  jle     short loc_180002A31
0x180002a28  movzx   edi, ax
0x180002a2b  or      edi, 80070000h
0x180002a31  test    rbx, rbx
0x180002a34  jz      short loc_180002A4C
0x180002a36  lea     rcx, [rbx-8]
0x180002a3a  cmp     [rcx], r12d
0x180002a3d  jnz     short loc_180002A4C
0x180002a3f  mov     rax, cs:g_pfnFree
0x180002a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4b  nop
0x180002a4c  jmp     loc_180002B72
0x180002a51  mov     r14, rbx
0x180002a54  xor     edi, edi
0x180002a56  mov     qword ptr [rbp+80h+pHints.ai_flags], 400h
0x180002a5e  mov     r9, r15; ppResult
0x180002a61  lea     r8, [rbp+80h+pHints]; pHints
0x180002a65  xor     edx, edx; pServiceName
0x180002a67  mov     rcx, r14; pNodeName
0x180002a6a  call    cs:__imp_GetAddrInfoW
0x180002a70  mov     esi, eax
0x180002a72  test    eax, eax
0x180002a74  jz      loc_180002B57
0x180002a7a  lea     rcx, WPP_GLOBAL_Control
0x180002a81  mov     rax, cs:WPP_GLOBAL_Control
0x180002a88  cmp     rax, rcx
0x180002a8b  jz      loc_180002B33
0x180002a91  cmp     byte ptr [rax+19h], 2
0x180002a95  jb      loc_180002B33
0x180002a9b  test    byte ptr [rax+1Ch], 4
0x180002a9f  jz      loc_180002B33
0x180002aa5  mov     [rsp+0C0h+Arguments], rdi; Arguments
0x180002aaa  mov     r9d, 400h; dwLanguageId
0x180002ab0  mov     [rsp+0C0h+var_98], r9d; nSize
0x180002ab5  lea     r12, ?buff@?1??gai_strerrorW@@9@4PAGA; ushort near * `gai_strerrorW'::`2'::buff
0x180002abc  mov     [rsp+0C0h+lpBuffer], r12; lpBuffer
0x180002ac1  mov     r8d, esi; dwMessageId
0x180002ac4  xor     edx, edx; lpSource
0x180002ac6  mov     edi, 12FFh
0x180002acb  mov     ecx, edi; dwFlags
0x180002acd  call    cs:__imp_FormatMessageW
0x180002ad3  mov     r9, r12
0x180002ad6  mov     r8d, esi
0x180002ad9  mov     rdx, r14
0x180002adc  lea     rcx, String1; "GetAddrInfo (name resolution) failed fo"...
0x180002ae3  call    WppDbgPrint
0x180002ae8  mov     [rsp+0C0h+Arguments], 0; Arguments
0x180002af1  mov     eax, 400h
0x180002af6  mov     [rsp+0C0h+var_98], eax; nSize
0x180002afa  mov     [rsp+0C0h+lpBuffer], r12; lpBuffer
0x180002aff  mov     r9d, eax; dwLanguageId
0x180002b02  mov     r8d, esi; dwMessageId
0x180002b05  xor     edx, edx; lpSource
0x180002b07  mov     ecx, edi; dwFlags
0x180002b09  call    cs:__imp_FormatMessageW
0x180002b0f  mov     [rsp+0C0h+Arguments], r12; __int64
0x180002b14  mov     [rsp+0C0h+var_98], esi; char
0x180002b18  mov     [rsp+0C0h+lpBuffer], r14; __int64
0x180002b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b24  mov     rcx, [rcx+10h]; LoggerHandle
0x180002b28  call    WPP_SF_sSLS
0x180002b2d  mov     r12d, 70616548h
0x180002b33  test    esi, esi
0x180002b35  jg      short loc_180002B3B
0x180002b37  mov     edi, esi
0x180002b39  jmp     short loc_180002B44
0x180002b3b  movzx   edi, si
0x180002b3e  or      edi, 80070000h
0x180002b44  test    edi, edi
0x180002b46  jns     short loc_180002B57
0x180002b48  mov     rcx, [r15]; pAddrInfo
0x180002b4b  test    rcx, rcx
0x180002b4e  jz      short loc_180002B57
0x180002b50  call    cs:__imp_FreeAddrInfoW
0x180002b56  nop
0x180002b57  test    rbx, rbx
0x180002b5a  jz      short loc_180002B72
0x180002b5c  lea     rcx, [rbx-8]
0x180002b60  cmp     [rcx], r12d
0x180002b63  jnz     short loc_180002B72
0x180002b65  mov     rax, cs:g_pfnFree
0x180002b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b71  nop
0x180002b72  mov     eax, edi
0x180002b74  mov     rcx, [rbp+80h+var_40]
0x180002b78  xor     rcx, rbp; StackCookie
0x180002b7b  call    __security_check_cookie
0x180002b80  lea     rsp, [rbp+50h]
0x180002b84  pop     r15
0x180002b86  pop     r14
0x180002b88  pop     r12
0x180002b8a  pop     rdi
0x180002b8b  pop     rsi
0x180002b8c  pop     rbx
0x180002b8d  pop     rbp
0x180002b8e  retn
```
