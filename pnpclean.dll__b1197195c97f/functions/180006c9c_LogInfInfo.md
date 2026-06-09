# LogInfInfo

- ea: `0x180006c9c`
- end: `0x180006dbc`
- name: `LogInfInfo`
- size: `288`
- prototype: `__int64 __fastcall(__int64, __int64, const FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180007680`

## callees

- `0x180006c9c`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `KERNEL32!FileTimeToLocalFileTime` at `0x180006ce7`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180006ce7`
- `KERNEL32!FileTimeToSystemTime` at `0x180006cf9`
- `KERNEL32!FileTimeToSystemTime` at `0x180006cf9`
- `SETUPAPI!pSetupStringFromGuid` at `0x180006d6f`
- `SETUPAPI!pSetupStringFromGuid` at `0x180006d6f`

## pseudocode

```c
__int64 __fastcall LogInfInfo(__int64 a1, __int64 a2, const FILETIME *a3)
{
  bool v3; // zf
  const FILETIME *v6; // rcx
  __int64 result; // rax
  int wYear; // [rsp+20h] [rbp-79h]
  int wMonth; // [rsp+28h] [rbp-71h]
  int wDay; // [rsp+30h] [rbp-69h]
  int wHour; // [rsp+38h] [rbp-61h]
  int wMinute; // [rsp+40h] [rbp-59h]
  int wSecond; // [rsp+48h] [rbp-51h]
  int wMilliseconds; // [rsp+50h] [rbp-49h]
  struct _FILETIME LocalFileTime; // [rsp+60h] [rbp-39h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v17[80]; // [rsp+80h] [rbp-19h] BYREF

  v3 = a3[14].dwHighDateTime == 0;
  LocalFileTime = 0;
  SystemTime = 0;
  v6 = a3 + 14;
  if ( (!v3 || v6->dwLowDateTime)
    && FileTimeToLocalFileTime(v6, &LocalFileTime)
    && FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
  {
    wMilliseconds = SystemTime.wMilliseconds;
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wDay = SystemTime.wDay;
    wMonth = SystemTime.wMonth;
    wYear = SystemTime.wYear;
    (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 40))(
      *(_QWORD *)(a1 + 48),
      3,
      0,
      "     Import Date: %04d/%02d/%02d %02d:%02d:%02d:%03d.",
      wYear,
      wMonth,
      wDay,
      wHour,
      wMinute,
      wSecond,
      wMilliseconds);
  }
  result = pSetupStringFromGuid(&a3[18], v17, 39);
  if ( !(_DWORD)result )
    return (*(__int64 (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 40))(
             *(_QWORD *)(a1 + 48),
             3,
             0,
             "     Class GUID:  %ws",
             v17);
  return result;
}

```

## disassembly

```asm
0x180006c9c  mov     [rsp-8+arg_8], rbx
0x180006ca1  push    rbp
0x180006ca2  push    rsi
0x180006ca3  push    rdi
0x180006ca4  lea     rbp, [rsp-47h]
0x180006ca9  sub     rsp, 0E0h
0x180006cb0  mov     rax, cs:__security_cookie
0x180006cb7  xor     rax, rsp
0x180006cba  mov     [rbp+57h+var_20], rax
0x180006cbe  cmp     dword ptr [r8+74h], 0
0x180006cc3  xorps   xmm0, xmm0
0x180006cc6  mov     rsi, rcx
0x180006cc9  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], 0
0x180006cd1  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180006cd5  mov     rdi, r8
0x180006cd8  lea     rcx, [r8+70h]; lpFileTime
0x180006cdc  jnz     short loc_180006CE3
0x180006cde  cmp     dword ptr [rcx], 0
0x180006ce1  jz      short loc_180006D5E
0x180006ce3  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x180006ce7  call    cs:__imp_FileTimeToLocalFileTime
0x180006ced  test    eax, eax
0x180006cef  jz      short loc_180006D5E
0x180006cf1  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180006cf5  lea     rcx, [rbp+57h+LocalFileTime]; lpFileTime
0x180006cf9  call    cs:__imp_FileTimeToSystemTime
0x180006cff  test    eax, eax
0x180006d01  jz      short loc_180006D5E
0x180006d03  movzx   ecx, [rbp+57h+SystemTime.wMilliseconds]
0x180006d07  movzx   edx, [rbp+57h+SystemTime.wSecond]
0x180006d0b  movzx   r8d, [rbp+57h+SystemTime.wMinute]
0x180006d10  movzx   r9d, [rbp+57h+SystemTime.wHour]
0x180006d15  movzx   r10d, [rbp+57h+SystemTime.wDay]
0x180006d1a  movzx   r11d, [rbp+57h+SystemTime.wMonth]
0x180006d1f  movzx   ebx, [rbp+57h+SystemTime.wYear]
0x180006d23  mov     rax, [rsi+28h]
0x180006d27  mov     [rsp+0F0h+var_A0], ecx
0x180006d2b  mov     rcx, [rsi+30h]
0x180006d2f  mov     [rsp+0F0h+var_A8], edx
0x180006d33  mov     [rsp+0F0h+var_B0], r8d
0x180006d38  xor     r8d, r8d
0x180006d3b  mov     [rsp+0F0h+var_B8], r9d
0x180006d40  lea     r9, aImportDate04d0; "     Import Date: %04d/%02d/%02d %02d:%"...
0x180006d47  mov     [rsp+0F0h+var_C0], r10d
0x180006d4c  mov     [rsp+0F0h+var_C8], r11d
0x180006d51  lea     edx, [r8+3]
0x180006d55  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180006d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d5e  lea     rcx, [rdi+90h]
0x180006d65  mov     r8d, 27h ; '''
0x180006d6b  lea     rdx, [rbp+57h+var_70]
0x180006d6f  call    cs:__imp_pSetupStringFromGuid
0x180006d75  test    eax, eax
0x180006d77  jnz     short loc_180006D9D
0x180006d79  mov     rcx, [rsi+30h]
0x180006d7d  lea     rax, [rbp+57h+var_70]
0x180006d81  xor     r8d, r8d
0x180006d84  mov     [rsp+0F0h+var_D0], rax
0x180006d89  mov     rax, [rsi+28h]
0x180006d8d  lea     r9, aClassGuidWs; "     Class GUID:  %ws"
0x180006d94  lea     edx, [r8+3]
0x180006d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d9d  mov     rcx, [rbp+57h+var_20]
0x180006da1  xor     rcx, rsp; StackCookie
0x180006da4  call    __security_check_cookie
0x180006da9  mov     rbx, [rsp+0F0h+arg_8]
0x180006db1  add     rsp, 0E0h
0x180006db8  pop     rdi
0x180006db9  pop     rsi
0x180006dba  pop     rbp
0x180006dbb  retn
```
