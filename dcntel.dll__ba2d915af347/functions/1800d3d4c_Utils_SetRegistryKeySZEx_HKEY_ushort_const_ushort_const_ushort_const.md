# Utils::SetRegistryKeySZEx(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800d3d4c`
- end: `0x1800d3e98`
- name: `?SetRegistryKeySZEx@Utils@@SAJPEAUHKEY__@@PEBG11@Z`
- size: `332`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a58c8`
- `0x1800a5a14`
- `0x1800a5b9c`

## callees

- `0x18001dcc8`
- `0x1800d3620`
- `0x1800d3d4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3e7e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d3dff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d3dff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d3dbb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d3dbb`

## pseudocode

```c
__int64 __fastcall Utils::SetRegistryKeySZEx(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4)
{
  DWORD v6; // ebx
  __int64 v7; // rax
  LSTATUS v8; // esi
  LSTATUS v10; // ebx
  signed int LastError; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  void **v20; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF

  v20 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
  hKey = 0;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&a4[2 * v7] );
    v6 = 2 * v7 + 2;
  }
  else
  {
    v6 = 0;
  }
  v8 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v8 >= 0 )
  {
    v20 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
    v10 = RegSetValueExW(hKey, a3, 0, 1u, a4, v6);
    if ( v10 >= 0 )
    {
      if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v20) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v12, v13);
        __debugbreak();
      }
      return 0;
    }
    else
    {
      if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v20) )
      {
        v17 = GetLastError();
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
        JUMPOUT(0x1800D3E97LL);
      }
      return (unsigned int)v10;
    }
  }
  else
  {
    v20 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
    if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v20) )
    {
      v14 = GetLastError();
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
      __debugbreak();
    }
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1800d3d4c  push    rbp
0x1800d3d4e  push    rbx
0x1800d3d4f  push    rsi
0x1800d3d50  push    rdi
0x1800d3d51  push    r12
0x1800d3d53  push    r14
0x1800d3d55  push    r15
0x1800d3d57  mov     rbp, rsp
0x1800d3d5a  sub     rsp, 60h
0x1800d3d5e  xor     r15d, r15d
0x1800d3d61  lea     r12, ??_7?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable'
0x1800d3d68  mov     [rbp+var_10], r12
0x1800d3d6c  mov     rdi, r9
0x1800d3d6f  mov     [rbp+hKey], r15
0x1800d3d73  mov     r14, r8
0x1800d3d76  test    r9, r9
0x1800d3d79  jnz     short loc_1800D3D80
0x1800d3d7b  mov     ebx, r15d
0x1800d3d7e  jmp     short loc_1800D3D95
0x1800d3d80  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d3d84  inc     rax
0x1800d3d87  cmp     [r9+rax*2], r15w
0x1800d3d8c  jnz     short loc_1800D3D84
0x1800d3d8e  lea     ebx, ds:2[rax*2]
0x1800d3d95  mov     [rsp+60h+lpdwDisposition], r15; lpdwDisposition
0x1800d3d9a  lea     rax, [rbp+hKey]
0x1800d3d9e  mov     [rsp+60h+phkResult], rax; phkResult
0x1800d3da3  xor     r9d, r9d; lpClass
0x1800d3da6  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800d3dab  xor     r8d, r8d; Reserved
0x1800d3dae  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x1800d3db6  mov     [rsp+60h+dwOptions], r15d; dwOptions
0x1800d3dbb  call    cs:__imp_RegCreateKeyExW
0x1800d3dc1  mov     esi, eax
0x1800d3dc3  test    eax, eax
0x1800d3dc5  jns     short loc_1800D3DE6
0x1800d3dc7  mov     [rbp+var_10], r12
0x1800d3dcb  cmp     [rbp+hKey], r15
0x1800d3dcf  jz      short loc_1800D3DE2
0x1800d3dd1  lea     rcx, [rbp+var_10]
0x1800d3dd5  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3dda  test    al, al
0x1800d3ddc  jz      loc_1800D3E64
0x1800d3de2  mov     eax, esi
0x1800d3de4  jmp     short loc_1800D3E3B
0x1800d3de6  mov     rcx, [rbp+hKey]; hKey
0x1800d3dea  mov     r9d, 1; dwType
0x1800d3df0  mov     [rsp+60h+samDesired], ebx; cbData
0x1800d3df4  xor     r8d, r8d; Reserved
0x1800d3df7  mov     rdx, r14; lpValueName
0x1800d3dfa  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x1800d3dff  call    cs:__imp_RegSetValueExW
0x1800d3e05  mov     [rbp+var_10], r12
0x1800d3e09  mov     ebx, eax
0x1800d3e0b  test    eax, eax
0x1800d3e0d  jns     short loc_1800D3E26
0x1800d3e0f  cmp     [rbp+hKey], r15
0x1800d3e13  jz      short loc_1800D3E22
0x1800d3e15  lea     rcx, [rbp+var_10]
0x1800d3e19  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3e1e  test    al, al
0x1800d3e20  jz      short loc_1800D3E7E
0x1800d3e22  mov     eax, ebx
0x1800d3e24  jmp     short loc_1800D3E3B
0x1800d3e26  cmp     [rbp+hKey], r15
0x1800d3e2a  jz      short loc_1800D3E39
0x1800d3e2c  lea     rcx, [rbp+var_10]
0x1800d3e30  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3e35  test    al, al
0x1800d3e37  jz      short loc_1800D3E4A
0x1800d3e39  xor     eax, eax
0x1800d3e3b  add     rsp, 60h
0x1800d3e3f  pop     r15
0x1800d3e41  pop     r14
0x1800d3e43  pop     r12
0x1800d3e45  pop     rdi
0x1800d3e46  pop     rsi
0x1800d3e47  pop     rbx
0x1800d3e48  pop     rbp
0x1800d3e49  retn
0x1800d3e4a  call    cs:__imp_GetLastError
0x1800d3e50  test    eax, eax
0x1800d3e52  jle     short loc_1800D3E5C
0x1800d3e54  movzx   eax, ax
0x1800d3e57  or      eax, 80070000h
0x1800d3e5c  mov     ecx, eax; this
0x1800d3e5e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d3e63  int     3; Trap to Debugger
0x1800d3e64  call    cs:__imp_GetLastError
0x1800d3e6a  test    eax, eax
0x1800d3e6c  jle     short loc_1800D3E76
0x1800d3e6e  movzx   eax, ax
0x1800d3e71  or      eax, 80070000h
0x1800d3e76  mov     ecx, eax; this
0x1800d3e78  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d3e7d  int     3; Trap to Debugger
0x1800d3e7e  call    cs:__imp_GetLastError
0x1800d3e84  test    eax, eax
0x1800d3e86  jle     short loc_1800D3E90
0x1800d3e88  movzx   eax, ax
0x1800d3e8b  or      eax, 80070000h
0x1800d3e90  mov     ecx, eax; this
0x1800d3e92  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
