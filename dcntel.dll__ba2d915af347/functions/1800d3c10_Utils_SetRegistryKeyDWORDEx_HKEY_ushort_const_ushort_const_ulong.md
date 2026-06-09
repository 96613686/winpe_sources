# Utils::SetRegistryKeyDWORDEx(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x1800d3c10`
- end: `0x1800d3d45`
- name: `?SetRegistryKeyDWORDEx@Utils@@SAJPEAUHKEY__@@PEBG1K@Z`
- size: `309`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2cd0`
- `0x1800a47e0`
- `0x1800a5ac4`

## callees

- `0x18001dcc8`
- `0x1800d3620`
- `0x1800d3c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3cf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3d2b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d3cb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d3cb1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d3c67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d3c67`

## pseudocode

```c
__int64 __fastcall Utils::SetRegistryKeyDWORDEx(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  LSTATUS v5; // ebx
  signed int v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  signed int v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  signed int LastError; // eax
  int v14; // edx
  unsigned int v15; // r8d
  void **v16; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-10h] BYREF
  int Data; // [rsp+A8h] [rbp+40h] BYREF

  Data = a4;
  v16 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
  hKey = 0;
  v5 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v5 < 0 )
  {
    v16 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
    if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v16) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v14, v15);
      JUMPOUT(0x1800D3D44LL);
    }
    return (unsigned int)v5;
  }
  v16 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
  v5 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v5 < 0 )
  {
    if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v16) )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      __debugbreak();
    }
    return (unsigned int)v5;
  }
  if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v16) )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800d3c10  mov     r11, rsp
0x1800d3c13  mov     [r11+20h], r9d
0x1800d3c17  push    rbp
0x1800d3c18  push    rbx
0x1800d3c19  push    rdi
0x1800d3c1a  push    r14
0x1800d3c1c  mov     rbp, rsp
0x1800d3c1f  sub     rsp, 68h
0x1800d3c23  mov     qword ptr [r11-48h], 0
0x1800d3c2b  lea     rax, [rbp+hKey]
0x1800d3c2f  mov     [r11-50h], rax
0x1800d3c33  lea     r14, ??_7?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable'
0x1800d3c3a  mov     qword ptr [r11-58h], 0
0x1800d3c42  mov     rdi, r8
0x1800d3c45  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x1800d3c4d  xor     r9d, r9d; lpClass
0x1800d3c50  xor     r8d, r8d; Reserved
0x1800d3c53  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800d3c5b  mov     [rbp+var_18], r14
0x1800d3c5f  mov     [rbp+hKey], 0
0x1800d3c67  call    cs:__imp_RegCreateKeyExW
0x1800d3c6d  mov     ebx, eax
0x1800d3c6f  test    eax, eax
0x1800d3c71  jns     short loc_1800D3C93
0x1800d3c73  cmp     [rbp+hKey], 0
0x1800d3c78  mov     [rbp+var_18], r14
0x1800d3c7c  jz      short loc_1800D3C8F
0x1800d3c7e  lea     rcx, [rbp+var_18]
0x1800d3c82  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3c87  test    al, al
0x1800d3c89  jz      loc_1800D3D2B
0x1800d3c8f  mov     eax, ebx
0x1800d3c91  jmp     short loc_1800D3CED
0x1800d3c93  mov     rcx, [rbp+hKey]; hKey
0x1800d3c97  lea     rax, [rbp+Data]
0x1800d3c9b  mov     r9d, 4; dwType
0x1800d3ca1  xor     r8d, r8d; Reserved
0x1800d3ca4  mov     [rsp+68h+samDesired], r9d; cbData
0x1800d3ca9  mov     rdx, rdi; lpValueName
0x1800d3cac  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800d3cb1  call    cs:__imp_RegSetValueExW
0x1800d3cb7  mov     [rbp+var_18], r14
0x1800d3cbb  mov     ebx, eax
0x1800d3cbd  test    eax, eax
0x1800d3cbf  jns     short loc_1800D3CD7
0x1800d3cc1  cmp     [rbp+hKey], 0
0x1800d3cc6  jz      short loc_1800D3C8F
0x1800d3cc8  lea     rcx, [rbp+var_18]
0x1800d3ccc  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3cd1  test    al, al
0x1800d3cd3  jz      short loc_1800D3D11
0x1800d3cd5  jmp     short loc_1800D3C8F
0x1800d3cd7  cmp     [rbp+hKey], 0
0x1800d3cdc  jz      short loc_1800D3CEB
0x1800d3cde  lea     rcx, [rbp+var_18]
0x1800d3ce2  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3ce7  test    al, al
0x1800d3ce9  jz      short loc_1800D3CF7
0x1800d3ceb  xor     eax, eax
0x1800d3ced  add     rsp, 68h
0x1800d3cf1  pop     r14
0x1800d3cf3  pop     rdi
0x1800d3cf4  pop     rbx
0x1800d3cf5  pop     rbp
0x1800d3cf6  retn
0x1800d3cf7  call    cs:__imp_GetLastError
0x1800d3cfd  test    eax, eax
0x1800d3cff  jle     short loc_1800D3D09
0x1800d3d01  movzx   eax, ax
0x1800d3d04  or      eax, 80070000h
0x1800d3d09  mov     ecx, eax; this
0x1800d3d0b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d3d10  int     3; Trap to Debugger
0x1800d3d11  call    cs:__imp_GetLastError
0x1800d3d17  test    eax, eax
0x1800d3d19  jle     short loc_1800D3D23
0x1800d3d1b  movzx   eax, ax
0x1800d3d1e  or      eax, 80070000h
0x1800d3d23  mov     ecx, eax; this
0x1800d3d25  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d3d2a  int     3; Trap to Debugger
0x1800d3d2b  call    cs:__imp_GetLastError
0x1800d3d31  test    eax, eax
0x1800d3d33  jle     short loc_1800D3D3D
0x1800d3d35  movzx   eax, ax
0x1800d3d38  or      eax, 80070000h
0x1800d3d3d  mov     ecx, eax; this
0x1800d3d3f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
