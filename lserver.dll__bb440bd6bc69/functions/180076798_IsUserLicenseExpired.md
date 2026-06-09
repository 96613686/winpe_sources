# IsUserLicenseExpired

- ea: `0x180076798`
- end: `0x18007682b`
- name: `IsUserLicenseExpired`
- size: `147`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180057958`

## callees

- `0x180076798`
- `0x1800a0fb0`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800767cd`
- `KERNEL32!GetSystemTime` at `0x1800767cd`
- `KERNEL32!CompareFileTime` at `0x1800767f8`
- `KERNEL32!CompareFileTime` at `0x1800767f8`
- `KERNEL32!SystemTimeToFileTime` at `0x1800767e3`
- `KERNEL32!SystemTimeToFileTime` at `0x1800767e3`

## pseudocode

```c
__int64 __fastcall IsUserLicenseExpired(__int64 a1)
{
  unsigned int v1; // ebx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-20h] BYREF

  v1 = 0;
  FileTime = 0;
  SystemTime = 0;
  if ( !a1 )
    return 1;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  LOBYTE(v1) = CompareFileTime((const FILETIME *)(a1 + 4), &FileTime) < 0;
  return v1;
}

```

## disassembly

```asm
0x180076798  mov     [rsp+arg_8], rbx
0x18007679d  push    rdi
0x18007679e  sub     rsp, 40h
0x1800767a2  mov     rax, cs:__security_cookie
0x1800767a9  xor     rax, rsp
0x1800767ac  mov     [rsp+48h+var_10], rax
0x1800767b1  xor     ebx, ebx
0x1800767b3  xorps   xmm0, xmm0
0x1800767b6  mov     qword ptr [rsp+48h+FileTime.dwLowDateTime], rbx
0x1800767bb  mov     rdi, rcx
0x1800767be  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x1800767c3  test    rcx, rcx
0x1800767c6  jz      short loc_18007680D
0x1800767c8  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x1800767cd  call    cs:__imp_GetSystemTime
0x1800767d4  nop     dword ptr [rax+rax+00h]
0x1800767d9  lea     rdx, [rsp+48h+FileTime]; lpFileTime
0x1800767de  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x1800767e3  call    cs:__imp_SystemTimeToFileTime
0x1800767ea  nop     dword ptr [rax+rax+00h]
0x1800767ef  lea     rcx, [rdi+4]; lpFileTime1
0x1800767f3  lea     rdx, [rsp+48h+FileTime]; lpFileTime2
0x1800767f8  call    cs:__imp_CompareFileTime
0x1800767ff  nop     dword ptr [rax+rax+00h]
0x180076804  test    eax, eax
0x180076806  sets    bl
0x180076809  mov     eax, ebx
0x18007680b  jmp     short loc_180076812
0x18007680d  mov     eax, 1
0x180076812  mov     rcx, [rsp+48h+var_10]
0x180076817  xor     rcx, rsp; StackCookie
0x18007681a  call    __security_check_cookie
0x18007681f  mov     rbx, [rsp+48h+arg_8]
0x180076824  add     rsp, 40h
0x180076828  pop     rdi
0x180076829  retn
```
