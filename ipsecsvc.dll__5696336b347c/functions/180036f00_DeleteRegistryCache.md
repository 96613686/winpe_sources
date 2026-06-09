# DeleteRegistryCache

- ea: `0x180036f00`
- end: `0x18003708f`
- name: `DeleteRegistryCache`
- size: `399`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002b688`
- `0x18002cf74`
- `0x18002d64c`
- `0x180035714`

## callees

- `0x18000e510`
- `0x180036f00`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036f57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036f57`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003704f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003704f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037063`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037063`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180037000`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180037000`

## string_xrefs

- `0x180036f44`: `SYSTEM\CurrentControlSet\Services\PolicyAgent\Parameters\Cache`

## pseudocode

```c
__int64 DeleteRegistryCache()
{
  unsigned int v0; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  HKEY v3; // rcx
  __int64 v4; // rdx
  WCHAR *v5; // rax
  __int64 v6; // rcx
  WCHAR *v7; // rax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  cchName = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\PolicyAgent\\Parameters\\Cache",
         0,
         0xF003Fu,
         &hKey);
  if ( !v0 )
  {
    v3 = hKey;
    if ( hKey )
    {
      v4 = 520;
      v5 = SubKey;
      do
      {
        *(_BYTE *)v5 = 0;
        v5 = (WCHAR *)((char *)v5 + 1);
        --v4;
      }
      while ( v4 );
      while ( 1 )
      {
        cchName = 260;
        if ( RegEnumKeyExW(v3, 0, SubKey, &cchName, 0, 0, 0, 0) )
          break;
        v0 = RegDeleteKeyExW(hKey, SubKey, 0, 0);
        if ( v0 )
          break;
        v6 = 520;
        v7 = SubKey;
        do
        {
          *(_BYTE *)v7 = 0;
          v7 = (WCHAR *)((char *)v7 + 1);
          --v6;
        }
        while ( v6 );
        v3 = hKey;
      }
      goto LABEL_18;
    }
    v0 = 1359;
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return v0;
    v2 = 150;
    goto LABEL_5;
  }
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v2 = 149;
LABEL_5:
    WPP_SF_d(v1[2], v2, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v0);
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180036f00  mov     [rsp-8+arg_0], rbx
0x180036f05  mov     [rsp-8+arg_8], rdi
0x180036f0a  push    rbp
0x180036f0b  lea     rbp, [rsp-170h]
0x180036f13  sub     rsp, 270h
0x180036f1a  mov     rax, cs:__security_cookie
0x180036f21  xor     rax, rsp
0x180036f24  mov     [rbp+170h+var_10], rax
0x180036f2b  xor     edi, edi
0x180036f2d  lea     rax, [rsp+270h+hKey]
0x180036f32  mov     r9d, 0F003Fh; samDesired
0x180036f38  mov     [rsp+270h+hKey], rdi
0x180036f3d  xor     r8d, r8d; ulOptions
0x180036f40  mov     [rsp+270h+cchName], edi
0x180036f44  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x180036f4b  mov     [rsp+270h+phkResult], rax; phkResult
0x180036f50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036f57  call    cs:__imp_RegOpenKeyExW
0x180036f5d  mov     ebx, eax
0x180036f5f  test    eax, eax
0x180036f61  jz      short loc_180036FA1
0x180036f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f6a  lea     rax, WPP_GLOBAL_Control
0x180036f71  cmp     rcx, rax
0x180036f74  jz      loc_180037059
0x180036f7a  test    byte ptr [rcx+1Ch], 10h
0x180036f7e  jz      loc_180037059
0x180036f84  mov     edx, 95h
0x180036f89  mov     rcx, [rcx+10h]
0x180036f8d  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036f94  mov     r9d, ebx
0x180036f97  call    WPP_SF_d
0x180036f9c  jmp     loc_180037059
0x180036fa1  mov     rcx, [rsp+270h+hKey]
0x180036fa6  test    rcx, rcx
0x180036fa9  jnz     short loc_180036FD8
0x180036fab  mov     ebx, 54Fh
0x180036fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180036fb7  lea     rax, WPP_GLOBAL_Control
0x180036fbe  cmp     rcx, rax
0x180036fc1  jz      loc_180037069
0x180036fc7  test    byte ptr [rcx+1Ch], 10h
0x180036fcb  jz      loc_180037069
0x180036fd1  mov     edx, 96h
0x180036fd6  jmp     short loc_180036F89
0x180036fd8  mov     edx, 208h
0x180036fdd  lea     rax, [rsp+270h+SubKey]
0x180036fe2  mov     [rax], dil
0x180036fe5  inc     rax
0x180036fe8  sub     rdx, 1
0x180036fec  jnz     short loc_180036FE2
0x180036fee  jmp     short loc_180037027
0x180036ff0  mov     rcx, [rsp+270h+hKey]; hKey
0x180036ff5  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x180036ffa  xor     r9d, r9d; Reserved
0x180036ffd  xor     r8d, r8d; samDesired
0x180037000  call    cs:__imp_RegDeleteKeyExW
0x180037006  mov     ebx, eax
0x180037008  test    eax, eax
0x18003700a  jnz     short loc_180037059
0x18003700c  mov     ecx, 208h
0x180037011  lea     rax, [rsp+270h+SubKey]
0x180037016  mov     [rax], dil
0x180037019  inc     rax
0x18003701c  sub     rcx, 1
0x180037020  jnz     short loc_180037016
0x180037022  mov     rcx, [rsp+270h+hKey]; hKey
0x180037027  mov     [rsp+270h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18003702c  lea     r9, [rsp+270h+cchName]; lpcchName
0x180037031  mov     [rsp+270h+lpcchClass], rdi; lpcchClass
0x180037036  lea     r8, [rsp+270h+SubKey]; lpName
0x18003703b  mov     [rsp+270h+lpClass], rdi; lpClass
0x180037040  xor     edx, edx; dwIndex
0x180037042  mov     [rsp+270h+phkResult], rdi; lpReserved
0x180037047  mov     [rsp+270h+cchName], 104h
0x18003704f  call    cs:__imp_RegEnumKeyExW
0x180037055  test    eax, eax
0x180037057  jz      short loc_180036FF0
0x180037059  mov     rcx, [rsp+270h+hKey]; hKey
0x18003705e  test    rcx, rcx
0x180037061  jz      short loc_180037069
0x180037063  call    cs:__imp_RegCloseKey
0x180037069  mov     eax, ebx
0x18003706b  mov     rcx, [rbp+170h+var_10]
0x180037072  xor     rcx, rsp; StackCookie
0x180037075  call    __security_check_cookie
0x18003707a  lea     r11, [rsp+270h+var_s0]
0x180037082  mov     rbx, [r11+10h]
0x180037086  mov     rdi, [r11+18h]
0x18003708a  mov     rsp, r11
0x18003708d  pop     rbp
0x18003708e  retn
```
