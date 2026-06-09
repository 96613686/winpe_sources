# CTSSession::WriteLastRemoteLogonTime(void)

- ea: `0x18006f140`
- end: `0x18006f27e`
- name: `?WriteLastRemoteLogonTime@CTSSession@@AEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800332b0`
- `0x18006afe0`

## callees

- `0x180018200`
- `0x18004b460`
- `0x18006f140`
- `0x18006f968`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f213`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f213`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f243`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f243`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006f181`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006f181`

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
0x18006f140  mov     [rsp-8+arg_0], rbx
0x18006f145  mov     [rsp-8+arg_8], rdi
0x18006f14a  push    rbp
0x18006f14b  lea     rbp, [rsp-190h]
0x18006f153  sub     rsp, 290h
0x18006f15a  mov     rax, cs:__security_cookie
0x18006f161  xor     rax, rsp
0x18006f164  mov     [rbp+190h+var_10], rax
0x18006f16b  xorps   xmm0, xmm0
0x18006f16e  mov     [rsp+290h+hKey], 0
0x18006f177  lea     rcx, [rsp+290h+SystemTime]; lpSystemTime
0x18006f17c  movups  xmmword ptr [rsp+290h+SystemTime.wYear], xmm0
0x18006f181  call    cs:__imp_GetSystemTime
0x18006f187  movzx   ecx, [rsp+290h+SystemTime.wSecond]
0x18006f18c  movzx   edx, [rsp+290h+SystemTime.wMinute]
0x18006f191  movzx   r8d, [rsp+290h+SystemTime.wHour]
0x18006f197  movzx   eax, [rsp+290h+SystemTime.wMilliseconds]
0x18006f19c  movzx   r10d, [rsp+290h+SystemTime.wDay]
0x18006f1a2  movzx   r11d, [rsp+290h+SystemTime.wMonth]
0x18006f1a8  movzx   r9d, [rsp+290h+SystemTime.wYear]
0x18006f1ae  mov     [rsp+290h+var_248], eax
0x18006f1b2  mov     [rsp+290h+var_250], ecx
0x18006f1b6  lea     rcx, [rsp+290h+Source]; unsigned __int16 *
0x18006f1bb  mov     [rsp+290h+var_258], edx
0x18006f1bf  mov     edx, 104h; unsigned __int64
0x18006f1c4  mov     [rsp+290h+var_260], r8d
0x18006f1c9  lea     r8, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02u.%03uZ"
0x18006f1d0  mov     [rsp+290h+cbData], r10d
0x18006f1d5  mov     dword ptr [rsp+290h+phkResult], r11d
0x18006f1da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006f1df  lea     rcx, [rsp+290h+Source]; Source
0x18006f1e4  mov     ebx, eax
0x18006f1e6  call    wcsnlen_s
0x18006f1eb  mov     rdi, rax
0x18006f1ee  test    ebx, ebx
0x18006f1f0  js      short loc_18006F258
0x18006f1f2  lea     rax, [rsp+290h+hKey]
0x18006f1f7  mov     r9d, 2; samDesired
0x18006f1fd  xor     r8d, r8d; ulOptions
0x18006f200  mov     [rsp+290h+phkResult], rax; phkResult
0x18006f205  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18006f20c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006f213  call    cs:__imp_RegOpenKeyExW
0x18006f219  mov     ebx, eax
0x18006f21b  test    eax, eax
0x18006f21d  jnz     short loc_18006F24B
0x18006f21f  mov     rcx, [rsp+290h+hKey]; hKey
0x18006f224  lea     eax, [rdi+rdi]
0x18006f227  mov     [rsp+290h+cbData], eax; cbData
0x18006f22b  lea     r9d, [rbx+1]; dwType
0x18006f22f  lea     rax, [rsp+290h+Source]
0x18006f234  xor     r8d, r8d; Reserved
0x18006f237  lea     rdx, aLastremotelogo; "LastRemoteLogonTime"
0x18006f23e  mov     [rsp+290h+phkResult], rax; lpData
0x18006f243  call    cs:__imp_RegSetValueExW
0x18006f249  mov     ebx, eax
0x18006f24b  test    ebx, ebx
0x18006f24d  jle     short loc_18006F258
0x18006f24f  movzx   ebx, bx
0x18006f252  or      ebx, 80070000h
0x18006f258  mov     eax, ebx
0x18006f25a  mov     rcx, [rbp+190h+var_10]
0x18006f261  xor     rcx, rsp; StackCookie
0x18006f264  call    __security_check_cookie
0x18006f269  lea     r11, [rsp+290h+var_s0]
0x18006f271  mov     rbx, [r11+10h]
0x18006f275  mov     rdi, [r11+18h]
0x18006f279  mov     rsp, r11
0x18006f27c  pop     rbp
0x18006f27d  retn
```
