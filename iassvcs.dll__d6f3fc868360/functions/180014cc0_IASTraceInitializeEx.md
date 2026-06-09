# IASTraceInitializeEx

- ea: `0x180014cc0`
- end: `0x180014e6a`
- name: `IASTraceInitializeEx`
- size: `426`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000f538`
- `0x18000f6c0`

## callees

- `0x180014cc0`
- `0x180014ebc`
- `0x1800181a2`
- `0x1800181e0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180014d8a`
- `msvcrt!wcsrchr` at `0x180014dad`
- `msvcrt!wcsrchr` at `0x180014d8a`
- `msvcrt!wcsrchr` at `0x180014dad`
- `msvcrt!wcscat_s` at `0x180014de5`
- `msvcrt!wcscat_s` at `0x180014df5`
- `msvcrt!wcscat_s` at `0x180014e20`
- `msvcrt!wcscat_s` at `0x180014de5`
- `msvcrt!wcscat_s` at `0x180014df5`
- `msvcrt!wcscat_s` at `0x180014e20`
- `msvcrt!wcscpy_s` at `0x180014dd1`
- `msvcrt!wcscpy_s` at `0x180014e07`
- `msvcrt!wcscpy_s` at `0x180014dd1`
- `msvcrt!wcscpy_s` at `0x180014e07`
- `msvcrt!_wcsupr_s` at `0x180014e2e`
- `msvcrt!_wcsupr_s` at `0x180014e2e`
- `KERNEL32!Sleep` at `0x180014d18`
- `KERNEL32!Sleep` at `0x180014d18`
- `KERNEL32!VirtualQuery` at `0x180014d59`
- `KERNEL32!VirtualQuery` at `0x180014d59`
- `KERNEL32!GetModuleFileNameW` at `0x180014d76`
- `KERNEL32!GetModuleFileNameW` at `0x180014d76`
- `rtutils!TraceRegisterExW` at `0x180014e3b`
- `rtutils!TraceRegisterExW` at `0x180014e3b`

## pseudocode

```c
__int64 __fastcall IASTraceInitializeEx(wchar_t *Source)
{
  __int64 v2; // rcx
  const wchar_t *v3; // rbx
  int v4; // esi
  wchar_t *v5; // rax
  wchar_t *v6; // rax
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t Destination[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp+160h] BYREF

  memset(&Buffer, 0, sizeof(Buffer));
  memset_0(Destination, 0, 0x20Au);
  while ( _InterlockedExchange(&lLocked, 1) )
    Sleep(5u);
  if ( ++lRefCount == 1 )
  {
    v3 = 0;
    v4 = IsRunningInIASService(v2);
    if ( VirtualQuery(IASTraceInitializeEx, &Buffer, 0x30u)
      && GetModuleFileNameW((HMODULE)Buffer.AllocationBase, Filename, 0x104u) )
    {
      v5 = wcsrchr(Filename, 0x5Cu);
      v3 = v5 ? v5 + 1 : Filename;
      v6 = wcsrchr(v3, 0x2Eu);
      if ( v6 )
        *v6 = 0;
    }
    if ( Source )
    {
      wcscpy_s(Destination, 0x105u, Source);
      wcscat_s(Destination, 0x105u, L"_");
      wcscat_s(Destination, 0x105u, v3);
    }
    else
    {
      wcscpy_s(Destination, 0x105u, v3);
    }
    if ( !v4 )
      wcscat_s(Destination, 0x105u, L"_AUX");
    _wcsupr_s(Destination, 0x105u);
    dwTraceID = TraceRegisterExW(Destination, 0);
  }
  return (unsigned int)_InterlockedExchange(&lLocked, 0);
}

```

## disassembly

```asm
0x180014cc0  push    rbp
0x180014cc2  push    rbx
0x180014cc3  push    rsi
0x180014cc4  push    rdi
0x180014cc5  lea     rbp, [rsp-388h]
0x180014ccd  sub     rsp, 488h
0x180014cd4  mov     rax, cs:__security_cookie
0x180014cdb  xor     rax, rsp
0x180014cde  mov     [rbp+3A0h+var_30], rax
0x180014ce5  xorps   xmm0, xmm0
0x180014ce8  mov     rdi, rcx
0x180014ceb  lea     rcx, [rsp+4A0h+Destination]; void *
0x180014cf0  xor     edx, edx; Val
0x180014cf2  mov     r8d, 20Ah; Size
0x180014cf8  movups  xmmword ptr [rsp+4A0h+Buffer.BaseAddress], xmm0
0x180014cfd  movups  xmmword ptr [rsp+4A0h+Buffer.AllocationProtect], xmm0
0x180014d02  movups  xmmword ptr [rsp+4A0h+Buffer.State], xmm0
0x180014d07  call    memset_0
0x180014d0c  mov     ebx, 1
0x180014d11  jmp     short loc_180014D1E
0x180014d13  mov     ecx, 5; dwMilliseconds
0x180014d18  call    cs:__imp_Sleep
0x180014d1e  mov     eax, ebx
0x180014d20  xchg    eax, cs:lLocked
0x180014d26  test    eax, eax
0x180014d28  jnz     short loc_180014D13
0x180014d2a  mov     eax, cs:lRefCount
0x180014d30  add     eax, ebx
0x180014d32  mov     cs:lRefCount, eax
0x180014d38  cmp     eax, ebx
0x180014d3a  jnz     loc_180014E47
0x180014d40  xor     ebx, ebx
0x180014d42  call    IsRunningInIASService
0x180014d47  lea     r8d, [rbx+30h]; dwLength
0x180014d4b  mov     esi, eax
0x180014d4d  lea     rdx, [rsp+4A0h+Buffer]; lpBuffer
0x180014d52  lea     rcx, IASTraceInitializeEx; lpAddress
0x180014d59  call    cs:__imp_VirtualQuery
0x180014d5f  test    rax, rax
0x180014d62  jz      short loc_180014DBD
0x180014d64  mov     rcx, [rsp+4A0h+Buffer.AllocationBase]; hModule
0x180014d69  lea     rdx, [rbp+3A0h+Filename]; lpFilename
0x180014d70  mov     r8d, 104h; nSize
0x180014d76  call    cs:__imp_GetModuleFileNameW
0x180014d7c  test    eax, eax
0x180014d7e  jz      short loc_180014DBD
0x180014d80  lea     edx, [rbx+5Ch]; Ch
0x180014d83  lea     rcx, [rbp+3A0h+Filename]; Str
0x180014d8a  call    cs:__imp_wcsrchr
0x180014d90  mov     rbx, rax
0x180014d93  test    rax, rax
0x180014d96  jnz     short loc_180014DA1
0x180014d98  lea     rbx, [rbp+3A0h+Filename]
0x180014d9f  jmp     short loc_180014DA5
0x180014da1  add     rbx, 2
0x180014da5  mov     edx, 2Eh ; '.'; Ch
0x180014daa  mov     rcx, rbx; Str
0x180014dad  call    cs:__imp_wcsrchr
0x180014db3  test    rax, rax
0x180014db6  jz      short loc_180014DBD
0x180014db8  xor     ecx, ecx
0x180014dba  mov     [rax], cx
0x180014dbd  lea     rcx, [rsp+4A0h+Destination]; Destination
0x180014dc2  test    rdi, rdi
0x180014dc5  jz      short loc_180014DFD
0x180014dc7  mov     r8, rdi; Source
0x180014dca  mov     edi, 105h
0x180014dcf  mov     edx, edi; SizeInWords
0x180014dd1  call    cs:__imp_wcscpy_s
0x180014dd7  lea     r8, asc_18001D490; "_"
0x180014dde  mov     edx, edi; SizeInWords
0x180014de0  lea     rcx, [rsp+4A0h+Destination]; Destination
0x180014de5  call    cs:__imp_wcscat_s
0x180014deb  mov     r8, rbx; Source
0x180014dee  lea     rcx, [rsp+4A0h+Destination]; Destination
0x180014df3  mov     edx, edi; SizeInWords
0x180014df5  call    cs:__imp_wcscat_s
0x180014dfb  jmp     short loc_180014E0D
0x180014dfd  mov     edi, 105h
0x180014e02  mov     r8, rbx; Source
0x180014e05  mov     edx, edi; SizeInWords
0x180014e07  call    cs:__imp_wcscpy_s
0x180014e0d  test    esi, esi
0x180014e0f  jnz     short loc_180014E26
0x180014e11  lea     r8, aAux; "_AUX"
0x180014e18  mov     rdx, rdi; SizeInWords
0x180014e1b  lea     rcx, [rsp+4A0h+Destination]; Destination
0x180014e20  call    cs:__imp_wcscat_s
0x180014e26  mov     rdx, rdi; Size
0x180014e29  lea     rcx, [rsp+4A0h+Destination]; String
0x180014e2e  call    cs:__imp__wcsupr_s
0x180014e34  xor     edx, edx; dwFlags
0x180014e36  lea     rcx, [rsp+4A0h+Destination]; lpszCallerName
0x180014e3b  call    cs:__imp_TraceRegisterExW
0x180014e41  mov     cs:dwTraceID, eax
0x180014e47  xor     eax, eax
0x180014e49  xchg    eax, cs:lLocked
0x180014e4f  mov     rcx, [rbp+3A0h+var_30]
0x180014e56  xor     rcx, rsp; StackCookie
0x180014e59  call    __security_check_cookie
0x180014e5e  add     rsp, 488h
0x180014e65  pop     rdi
0x180014e66  pop     rsi
0x180014e67  pop     rbx
0x180014e68  pop     rbp
0x180014e69  retn
```
