# FwGetComputerName(_COMPUTER_NAME_FORMAT,ushort * *)

- ea: `0x18001f88c`
- end: `0x18001f989`
- name: `?FwGetComputerName@@YAJW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z`
- size: `253`
- prototype: `__int64 __fastcall(COMPUTER_NAME_FORMAT NameType, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800038e0`

## callees

- `0x180004750`
- `0x180004840`
- `0x180004870`
- `0x18001e1d0`
- `0x18001f88c`
- `0x18002f43c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f8cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f8cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f941`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f8be`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f929`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f8be`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18001f929`

## string_xrefs

- `0x18001f8e7`: `GetComputerNameEx`
- `0x18001f913`: `GetComputerNameEx`
- `0x18001f93a`: `GetComputerNameEx`
- `0x18001f8e0`: `FwGetComputerName`
- `0x18001f90c`: `FwGetComputerName`
- `0x18001f933`: `FwGetComputerName`

## pseudocode

```c
__int64 __fastcall FwGetComputerName(COMPUTER_NAME_FORMAT NameType, unsigned __int16 **a2)
{
  DWORD LastError; // eax
  __int64 v5; // rdx
  unsigned __int16 *v6; // rsi
  __int64 v7; // rcx
  WCHAR *v8; // rax
  int v9; // ebx
  DWORD nSize; // [rsp+20h] [rbp-18h] BYREF

  nSize = 0;
  if ( GetComputerNameExW(NameType, 0, &nSize) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LastError = GetLastError();
  if ( LastError == 234 || !LastError )
  {
    v7 = 2LL * ++nSize;
    v8 = (WCHAR *)FwAlloc(v7, v5);
    v6 = v8;
    if ( v8 )
    {
      if ( GetComputerNameExW(NameType, v8, &nSize) )
      {
        v9 = 0;
        *a2 = v6;
        return (unsigned int)v9;
      }
      LastError = GetLastError();
    }
    else
    {
      LastError = 14;
    }
  }
  else
  {
    v6 = 0;
  }
  v9 = FwReportErrorAsWinError("FwGetComputerName", "GetComputerNameEx", LastError);
  if ( v9 < 0 )
    FwFree(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001f88c  mov     [rsp+arg_10], rbx
0x18001f891  mov     [rsp+arg_18], rsi
0x18001f896  push    rdi
0x18001f897  sub     rsp, 30h
0x18001f89b  mov     rax, cs:__security_cookie
0x18001f8a2  xor     rax, rsp
0x18001f8a5  mov     [rsp+38h+var_10], rax
0x18001f8aa  mov     rdi, rdx
0x18001f8ad  mov     [rsp+38h+nSize], 0
0x18001f8b5  xor     edx, edx; lpBuffer
0x18001f8b7  lea     r8, [rsp+38h+nSize]; nSize
0x18001f8bc  mov     ebx, ecx
0x18001f8be  call    cs:__imp_GetComputerNameExW
0x18001f8c4  test    eax, eax
0x18001f8c6  jz      short loc_18001F8CD
0x18001f8c8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!retVal")
0x18001f8cd  call    cs:__imp_GetLastError
0x18001f8d3  cmp     eax, 0EAh
0x18001f8d8  jz      short loc_18001F8F0
0x18001f8da  test    eax, eax
0x18001f8dc  jz      short loc_18001F8F0
0x18001f8de  xor     esi, esi
0x18001f8e0  lea     rbx, aFwgetcomputern; "FwGetComputerName"
0x18001f8e7  lea     rdi, aGetcomputernam; "GetComputerNameEx"
0x18001f8ee  jmp     short loc_18001F947
0x18001f8f0  mov     eax, [rsp+38h+nSize]
0x18001f8f4  inc     eax
0x18001f8f6  mov     ecx, eax
0x18001f8f8  add     rcx, rcx
0x18001f8fb  mov     [rsp+38h+nSize], eax
0x18001f8ff  call    FwAlloc
0x18001f904  mov     rsi, rax
0x18001f907  test    rax, rax
0x18001f90a  jnz     short loc_18001F91F
0x18001f90c  lea     rbx, aFwgetcomputern; "FwGetComputerName"
0x18001f913  lea     rdi, aGetcomputernam; "GetComputerNameEx"
0x18001f91a  lea     eax, [rsi+0Eh]
0x18001f91d  jmp     short loc_18001F947
0x18001f91f  lea     r8, [rsp+38h+nSize]; nSize
0x18001f924  mov     rdx, rsi; lpBuffer
0x18001f927  mov     ecx, ebx; NameType
0x18001f929  call    cs:__imp_GetComputerNameExW
0x18001f92f  test    eax, eax
0x18001f931  jnz     short loc_18001F965
0x18001f933  lea     rbx, aFwgetcomputern; "FwGetComputerName"
0x18001f93a  lea     rdi, aGetcomputernam; "GetComputerNameEx"
0x18001f941  call    cs:__imp_GetLastError
0x18001f947  mov     r8d, eax
0x18001f94a  mov     rdx, rdi
0x18001f94d  mov     rcx, rbx
0x18001f950  call    FwReportErrorAsWinError
0x18001f955  mov     ebx, eax
0x18001f957  test    eax, eax
0x18001f959  jns     short loc_18001F96A
0x18001f95b  mov     rcx, rsi
0x18001f95e  call    FwFree
0x18001f963  jmp     short loc_18001F96A
0x18001f965  xor     ebx, ebx
0x18001f967  mov     [rdi], rsi
0x18001f96a  mov     eax, ebx
0x18001f96c  mov     rcx, [rsp+38h+var_10]
0x18001f971  xor     rcx, rsp; StackCookie
0x18001f974  call    __security_check_cookie
0x18001f979  mov     rbx, [rsp+38h+arg_10]
0x18001f97e  mov     rsi, [rsp+38h+arg_18]
0x18001f983  add     rsp, 30h
0x18001f987  pop     rdi
0x18001f988  retn
```
