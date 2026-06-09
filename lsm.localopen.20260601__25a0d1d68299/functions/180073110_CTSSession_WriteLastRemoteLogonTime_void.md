# CTSSession::WriteLastRemoteLogonTime(void)

- ea: `0x180073110`
- end: `0x180073261`
- name: `?WriteLastRemoteLogonTime@CTSSession@@AEAAJXZ`
- size: `337`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800353d0`
- `0x18006ee30`

## callees

- `0x18000c17c`
- `0x18004e850`
- `0x180073110`
- `0x18007397c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800731e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800731e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007321f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007321f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180073151`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180073151`

## pseudocode

```c
__int64 __fastcall CTSSession::WriteLastRemoteLogonTime(CTSSession *this)
{
  LSTATUS v1; // ebx
  size_t v2; // rdx
  int v3; // edi
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  int wHour; // [rsp+30h] [rbp-D0h]
  int wMinute; // [rsp+38h] [rbp-C8h]
  int wSecond; // [rsp+40h] [rbp-C0h]
  int wMilliseconds; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Source[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  wMilliseconds = SystemTime.wMilliseconds;
  wSecond = SystemTime.wSecond;
  wMinute = SystemTime.wMinute;
  wHour = SystemTime.wHour;
  cbData = SystemTime.wDay;
  phkResult = SystemTime.wMonth;
  v1 = StringCchPrintfW(
         Source,
         0x104u,
         L"%04u-%02u-%02uT%02u:%02u:%02u.%03uZ",
         SystemTime.wYear,
         phkResult,
         cbData,
         wHour,
         wMinute,
         wSecond,
         wMilliseconds);
  v3 = wcsnlen_s(Source, v2);
  if ( v1 >= 0 )
  {
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 2u, &hKey);
    if ( !v1 )
      v1 = RegSetValueExW(hKey, L"LastRemoteLogonTime", 0, 1u, (const BYTE *)Source, 2 * v3);
    if ( v1 > 0 )
      return (unsigned __int16)v1 | 0x80070000;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180073110  mov     [rsp-8+arg_0], rbx
0x180073115  mov     [rsp-8+arg_8], rdi
0x18007311a  push    rbp
0x18007311b  lea     rbp, [rsp-190h]
0x180073123  sub     rsp, 290h
0x18007312a  mov     rax, cs:__security_cookie
0x180073131  xor     rax, rsp
0x180073134  mov     [rbp+190h+var_10], rax
0x18007313b  xorps   xmm0, xmm0
0x18007313e  mov     [rsp+290h+hKey], 0
0x180073147  lea     rcx, [rsp+290h+SystemTime]; lpSystemTime
0x18007314c  movups  xmmword ptr [rsp+290h+SystemTime.wYear], xmm0
0x180073151  call    cs:__imp_GetSystemTime
0x180073158  nop     dword ptr [rax+rax+00h]
0x18007315d  movzx   ecx, [rsp+290h+SystemTime.wSecond]
0x180073162  movzx   edx, [rsp+290h+SystemTime.wMinute]
0x180073167  movzx   r8d, [rsp+290h+SystemTime.wHour]
0x18007316d  movzx   eax, [rsp+290h+SystemTime.wMilliseconds]
0x180073172  movzx   r10d, [rsp+290h+SystemTime.wDay]
0x180073178  movzx   r11d, [rsp+290h+SystemTime.wMonth]
0x18007317e  movzx   r9d, [rsp+290h+SystemTime.wYear]
0x180073184  mov     [rsp+290h+var_248], eax
0x180073188  mov     [rsp+290h+var_250], ecx
0x18007318c  lea     rcx, [rsp+290h+Source]; unsigned __int16 *
0x180073191  mov     [rsp+290h+var_258], edx
0x180073195  mov     edx, 104h; unsigned __int64
0x18007319a  mov     [rsp+290h+var_260], r8d
0x18007319f  lea     r8, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02u.%03uZ"
0x1800731a6  mov     [rsp+290h+cbData], r10d
0x1800731ab  mov     dword ptr [rsp+290h+phkResult], r11d
0x1800731b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800731b5  lea     rcx, [rsp+290h+Source]; Source
0x1800731ba  mov     ebx, eax
0x1800731bc  call    wcsnlen_s
0x1800731c1  mov     rdi, rax
0x1800731c4  test    ebx, ebx
0x1800731c6  js      short loc_18007323A
0x1800731c8  lea     rax, [rsp+290h+hKey]
0x1800731cd  mov     r9d, 2; samDesired
0x1800731d3  xor     r8d, r8d; ulOptions
0x1800731d6  mov     [rsp+290h+phkResult], rax; phkResult
0x1800731db  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x1800731e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800731e9  call    cs:__imp_RegOpenKeyExW
0x1800731f0  nop     dword ptr [rax+rax+00h]
0x1800731f5  mov     ebx, eax
0x1800731f7  test    eax, eax
0x1800731f9  jnz     short loc_18007322D
0x1800731fb  mov     rcx, [rsp+290h+hKey]; hKey
0x180073200  lea     eax, [rdi+rdi]
0x180073203  mov     [rsp+290h+cbData], eax; cbData
0x180073207  lea     r9d, [rbx+1]; dwType
0x18007320b  lea     rax, [rsp+290h+Source]
0x180073210  xor     r8d, r8d; Reserved
0x180073213  lea     rdx, aLastremotelogo; "LastRemoteLogonTime"
0x18007321a  mov     [rsp+290h+phkResult], rax; lpData
0x18007321f  call    cs:__imp_RegSetValueExW
0x180073226  nop     dword ptr [rax+rax+00h]
0x18007322b  mov     ebx, eax
0x18007322d  test    ebx, ebx
0x18007322f  jle     short loc_18007323A
0x180073231  movzx   ebx, bx
0x180073234  or      ebx, 80070000h
0x18007323a  mov     eax, ebx
0x18007323c  mov     rcx, [rbp+190h+var_10]
0x180073243  xor     rcx, rsp; StackCookie
0x180073246  call    __security_check_cookie
0x18007324b  lea     r11, [rsp+290h+var_s0]
0x180073253  mov     rbx, [r11+10h]
0x180073257  mov     rdi, [r11+18h]
0x18007325b  mov     rsp, r11
0x18007325e  pop     rbp
0x18007325f  retn
```
