# HrCleanRouterInterfacesEntries(void)

- ea: `0x180035c70`
- end: `0x180035e26`
- name: `?HrCleanRouterInterfacesEntries@@YAJXZ`
- size: `438`
- prototype: `LSTATUS(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800356d0`

## callees

- `0x180035c70`
- `0x1800372a0`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035d46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035ded`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035d46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035ded`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180035d2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180035d2a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180035dce`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180035dce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035cc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035cc3`

## string_xrefs

- `0x180035cb5`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`

## pseudocode

```c
LSTATUS HrCleanRouterInterfacesEntries(void)
{
  LSTATUS result; // eax
  LSTATUS v1; // eax
  signed int v2; // ebx
  WCHAR *v3; // rax
  __int64 v4; // rcx
  LSTATUS v5; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces",
             0,
             0x2000000u,
             &hKey);
  if ( result == 2 )
    return 0;
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    cSubKeys = 0;
    v1 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v2 = v1;
    if ( v1 )
    {
      if ( v1 > 0 )
        v2 = (unsigned __int16)v1 | 0x80070000;
      RegCloseKey(hKey);
    }
    else
    {
      memset_0(Name, 0, sizeof(Name));
      cchName = 256;
      while ( 1 )
      {
        v5 = RegEnumKeyExW(hKey, --cSubKeys, Name, &cchName, 0, 0, 0, 0);
        v2 = v5;
        if ( v5 )
          break;
        v2 = RecurseDeleteKey(hKey, Name);
        if ( v2 > 2 )
          goto LABEL_18;
        cchName = 256;
        v3 = Name;
        v4 = 512;
        do
        {
          *(_BYTE *)v3 = 0;
          v3 = (WCHAR *)((char *)v3 + 1);
          --v4;
        }
        while ( v4 );
      }
      if ( v5 == 2 || v5 == 259 )
        v2 = 0;
LABEL_18:
      RegCloseKey(hKey);
      if ( v2 > 0 )
        return (unsigned __int16)v2 | 0x80070000;
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180035c70  mov     [rsp-8+arg_0], rbx
0x180035c75  mov     [rsp-8+arg_8], rdi
0x180035c7a  push    rbp
0x180035c7b  lea     rbp, [rsp-180h]
0x180035c83  sub     rsp, 280h
0x180035c8a  mov     rax, cs:__security_cookie
0x180035c91  xor     rax, rsp
0x180035c94  mov     [rbp+180h+var_10], rax
0x180035c9b  lea     rax, [rsp+280h+hKey]
0x180035ca0  xor     edi, edi
0x180035ca2  mov     r9d, 2000000h; samDesired
0x180035ca8  mov     [rsp+280h+hKey], rdi
0x180035cad  xor     r8d, r8d; ulOptions
0x180035cb0  mov     [rsp+280h+phkResult], rax; phkResult
0x180035cb5  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Re"...
0x180035cbc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035cc3  call    cs:__imp_RegOpenKeyExW
0x180035cc9  cmp     eax, 2
0x180035ccc  jnz     short loc_180035CD5
0x180035cce  xor     eax, eax
0x180035cd0  jmp     loc_180035E02
0x180035cd5  test    eax, eax
0x180035cd7  jz      short loc_180035CEC
0x180035cd9  jle     loc_180035E02
0x180035cdf  movzx   eax, ax
0x180035ce2  or      eax, 80070000h
0x180035ce7  jmp     loc_180035E02
0x180035cec  mov     rcx, [rsp+280h+hKey]; hKey
0x180035cf1  lea     rax, [rsp+280h+cSubKeys]
0x180035cf6  mov     [rsp+280h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180035cfb  xor     r9d, r9d; lpReserved
0x180035cfe  mov     [rsp+280h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180035d03  xor     r8d, r8d; lpcchClass
0x180035d06  mov     [rsp+280h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180035d0b  xor     edx, edx; lpClass
0x180035d0d  mov     [rsp+280h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180035d12  mov     [rsp+280h+lpcValues], rdi; lpcValues
0x180035d17  mov     [rsp+280h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180035d1c  mov     [rsp+280h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180035d21  mov     [rsp+280h+phkResult], rax; lpcSubKeys
0x180035d26  mov     [rsp+280h+cSubKeys], edi
0x180035d2a  call    cs:__imp_RegQueryInfoKeyW
0x180035d30  mov     ebx, eax
0x180035d32  test    eax, eax
0x180035d34  jz      short loc_180035D51
0x180035d36  jle     short loc_180035D41
0x180035d38  movzx   ebx, ax
0x180035d3b  or      ebx, 80070000h
0x180035d41  mov     rcx, [rsp+280h+hKey]; hKey
0x180035d46  call    cs:__imp_RegCloseKey
0x180035d4c  jmp     loc_180035E00
0x180035d51  xor     edx, edx; Val
0x180035d53  lea     rcx, [rsp+280h+Name]; void *
0x180035d58  mov     r8d, 200h; Size
0x180035d5e  call    memset_0
0x180035d63  mov     [rsp+280h+cchName], 100h
0x180035d6b  jmp     short loc_180035DA1
0x180035d6d  mov     rcx, [rsp+280h+hKey]; HKEY
0x180035d72  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180035d77  call    ?RecurseDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; RecurseDeleteKey(HKEY__ *,ushort const *)
0x180035d7c  mov     ebx, eax
0x180035d7e  cmp     eax, 2
0x180035d81  jg      short loc_180035DE8
0x180035d83  mov     [rsp+280h+cchName], 100h
0x180035d8b  lea     rax, [rsp+280h+Name]
0x180035d90  mov     ecx, 200h
0x180035d95  mov     [rax], dil
0x180035d98  inc     rax
0x180035d9b  sub     rcx, 1
0x180035d9f  jnz     short loc_180035D95
0x180035da1  mov     edx, [rsp+280h+cSubKeys]
0x180035da5  lea     r9, [rsp+280h+cchName]; lpcchName
0x180035daa  mov     rcx, [rsp+280h+hKey]; hKey
0x180035daf  lea     r8, [rsp+280h+Name]; lpName
0x180035db4  mov     [rsp+280h+lpcValues], rdi; lpftLastWriteTime
0x180035db9  dec     edx; dwIndex
0x180035dbb  mov     [rsp+280h+lpcbMaxClassLen], rdi; lpcchClass
0x180035dc0  mov     [rsp+280h+lpcbMaxSubKeyLen], rdi; lpClass
0x180035dc5  mov     [rsp+280h+cSubKeys], edx
0x180035dc9  mov     [rsp+280h+phkResult], rdi; lpReserved
0x180035dce  call    cs:__imp_RegEnumKeyExW
0x180035dd4  mov     ebx, eax
0x180035dd6  test    eax, eax
0x180035dd8  jz      short loc_180035D6D
0x180035dda  cmp     eax, 2
0x180035ddd  jz      short loc_180035DE6
0x180035ddf  cmp     eax, 103h
0x180035de4  jnz     short loc_180035DE8
0x180035de6  mov     ebx, edi
0x180035de8  mov     rcx, [rsp+280h+hKey]; hKey
0x180035ded  call    cs:__imp_RegCloseKey
0x180035df3  test    ebx, ebx
0x180035df5  jle     short loc_180035E00
0x180035df7  movzx   ebx, bx
0x180035dfa  or      ebx, 80070000h
0x180035e00  mov     eax, ebx
0x180035e02  mov     rcx, [rbp+180h+var_10]
0x180035e09  xor     rcx, rsp; StackCookie
0x180035e0c  call    __security_check_cookie
0x180035e11  lea     r11, [rsp+280h+var_s0]
0x180035e19  mov     rbx, [r11+10h]
0x180035e1d  mov     rdi, [r11+18h]
0x180035e21  mov     rsp, r11
0x180035e24  pop     rbp
0x180035e25  retn
```
