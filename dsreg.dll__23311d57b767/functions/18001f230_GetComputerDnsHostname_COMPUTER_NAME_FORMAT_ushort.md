# GetComputerDnsHostname(_COMPUTER_NAME_FORMAT,ushort * *)

- ea: `0x18001f230`
- end: `0x18001f36b`
- name: `?GetComputerDnsHostname@@YAJW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z`
- size: `315`
- prototype: `__int64 __fastcall(enum _COMPUTER_NAME_FORMAT, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001f1b4`
- `0x180058074`
- `0x1800a21e4`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x180012cf0`
- `0x18001f230`
- `0x1800307c4`
- `0x18003334c`
- `0x18003a138`
- `0x18008a78c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f28d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f314`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f28d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f31e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f31e`

## string_xrefs

- `0x18001f256`: `GetComputerDnsHostname`
- `0x18001f270`: `GetComputerDnsHostname`
- `0x18001f2bc`: `GetComputerDnsHostname`
- `0x18001f2f5`: `GetComputerDnsHostname`
- `0x18001f2ee`: `GetComputerNameExW`

## pseudocode

```c
__int64 __fastcall GetComputerDnsHostname(COMPUTER_NAME_FORMAT a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rsi
  unsigned int v5; // edi
  signed int LastError; // ebx
  WCHAR *v7; // rax
  const unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // rax
  DWORD nSize; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  nSize = 0;
  if ( a2 )
  {
    *a2 = 0;
    if ( GetComputerNameExW(a1, 0, &nSize)
      || (LastError = GetLastError(), LastError == 234)
      || (v8 = ComputerNameFormatToString(a1), Logger::WriteGetComputerNameFailureEvent(v8, LastError), !LastError) )
    {
      v7 = (WCHAR *)SafeAlloc(2LL * nSize);
      v2 = v7;
      if ( !v7 )
      {
        v5 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"GetComputerDnsHostname");
        goto LABEL_15;
      }
      if ( GetComputerNameExW(a1, v7, &nSize)
        || (LastError = GetLastError(),
            v9 = ComputerNameFormatToString(a1),
            Logger::WriteGetComputerNameFailureEvent(v9, LastError),
            !LastError) )
      {
        v5 = 0;
        *a2 = v2;
        v2 = 0;
        goto LABEL_15;
      }
    }
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"GetComputerDnsHostname",
      L"GetComputerNameExW",
      (unsigned int)LastError);
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    else
      v5 = LastError;
  }
  else
  {
    v5 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetComputerDnsHostname", L"pName");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetComputerDnsHostname", L"pName");
  }
LABEL_15:
  SafeFree(v2);
  return v5;
}

```

## disassembly

```asm
0x18001f230  push    rbx
0x18001f232  push    rsi
0x18001f233  push    rdi
0x18001f234  push    r14
0x18001f236  sub     rsp, 28h
0x18001f23a  xor     esi, esi
0x18001f23c  mov     r14, rdx
0x18001f23f  mov     [rsp+48h+nSize], esi
0x18001f243  mov     edi, ecx
0x18001f245  test    rdx, rdx
0x18001f248  jnz     short loc_18001F281
0x18001f24a  lea     r8, aPname; "pName"
0x18001f251  mov     edi, 80070057h
0x18001f256  lea     rdx, aGetcomputerdns; "GetComputerDnsHostname"
0x18001f25d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18001f264  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f269  lea     rdx, aPname; "pName"
0x18001f270  lea     rcx, aGetcomputerdns; "GetComputerDnsHostname"
0x18001f277  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001f27c  jmp     loc_18001F357
0x18001f281  xor     ebx, ebx
0x18001f283  lea     r8, [rsp+48h+nSize]; nSize
0x18001f288  mov     [rdx], rbx
0x18001f28b  xor     edx, edx; lpBuffer
0x18001f28d  call    cs:__imp_GetComputerNameExW
0x18001f293  test    eax, eax
0x18001f295  jnz     short loc_18001F2A8
0x18001f297  call    cs:__imp_GetLastError
0x18001f29d  mov     ebx, eax
0x18001f29f  cmp     eax, 0EAh
0x18001f2a4  jnz     short loc_18001F2D6
0x18001f2a6  xor     ebx, ebx
0x18001f2a8  mov     ecx, [rsp+48h+nSize]
0x18001f2ac  add     rcx, rcx; unsigned __int64
0x18001f2af  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18001f2b4  mov     rsi, rax
0x18001f2b7  test    rax, rax
0x18001f2ba  jnz     short loc_18001F30A
0x18001f2bc  lea     rdx, aGetcomputerdns; "GetComputerDnsHostname"
0x18001f2c3  mov     edi, 8007000Eh
0x18001f2c8  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18001f2cf  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18001f2d4  jmp     short loc_18001F342
0x18001f2d6  mov     ecx, edi; enum _COMPUTER_NAME_FORMAT
0x18001f2d8  call    ?ComputerNameFormatToString@@YAPEBGW4_COMPUTER_NAME_FORMAT@@@Z; ComputerNameFormatToString(_COMPUTER_NAME_FORMAT)
0x18001f2dd  mov     rcx, rax; unsigned __int16 *
0x18001f2e0  mov     edx, ebx; unsigned int
0x18001f2e2  call    ?WriteGetComputerNameFailureEvent@Logger@@SAJPEBGK@Z; Logger::WriteGetComputerNameFailureEvent(ushort const *,ulong)
0x18001f2e7  test    ebx, ebx
0x18001f2e9  jz      short loc_18001F2A8
0x18001f2eb  mov     r9d, ebx
0x18001f2ee  lea     r8, aGetcomputernam; "GetComputerNameExW"
0x18001f2f5  lea     rdx, aGetcomputerdns; "GetComputerDnsHostname"
0x18001f2fc  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001f303  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001f308  jmp     short loc_18001F346
0x18001f30a  lea     r8, [rsp+48h+nSize]; nSize
0x18001f30f  mov     rdx, rsi; lpBuffer
0x18001f312  mov     ecx, edi; NameType
0x18001f314  call    cs:__imp_GetComputerNameExW
0x18001f31a  test    eax, eax
0x18001f31c  jnz     short loc_18001F33B
0x18001f31e  call    cs:__imp_GetLastError
0x18001f324  mov     ecx, edi; enum _COMPUTER_NAME_FORMAT
0x18001f326  mov     ebx, eax
0x18001f328  call    ?ComputerNameFormatToString@@YAPEBGW4_COMPUTER_NAME_FORMAT@@@Z; ComputerNameFormatToString(_COMPUTER_NAME_FORMAT)
0x18001f32d  mov     rcx, rax; unsigned __int16 *
0x18001f330  mov     edx, ebx; unsigned int
0x18001f332  call    ?WriteGetComputerNameFailureEvent@Logger@@SAJPEBGK@Z; Logger::WriteGetComputerNameFailureEvent(ushort const *,ulong)
0x18001f337  test    ebx, ebx
0x18001f339  jnz     short loc_18001F2EB
0x18001f33b  xor     edi, edi
0x18001f33d  mov     [r14], rsi
0x18001f340  xor     esi, esi
0x18001f342  test    ebx, ebx
0x18001f344  jz      short loc_18001F357
0x18001f346  test    ebx, ebx
0x18001f348  jg      short loc_18001F34E
0x18001f34a  mov     edi, ebx
0x18001f34c  jmp     short loc_18001F357
0x18001f34e  movzx   edi, bx
0x18001f351  or      edi, 80070000h
0x18001f357  mov     rcx, rsi; lpMem
0x18001f35a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18001f35f  mov     eax, edi
0x18001f361  add     rsp, 28h
0x18001f365  pop     r14
0x18001f367  pop     rdi
0x18001f368  pop     rsi
0x18001f369  pop     rbx
0x18001f36a  retn
```
