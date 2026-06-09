# Utils::SetRegistryKeyDWORD64Ex(HKEY__ *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x1800d3ac4`
- end: `0x1800d3c07`
- name: `?SetRegistryKeyDWORD64Ex@Utils@@SAJPEAUHKEY__@@PEBG1_K@Z`
- size: `323`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a5b9c`

## callees

- `0x18001dcc8`
- `0x1800d3620`
- `0x1800d3ac4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3bd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3bd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3bed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d3b6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d3b6d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d3b1c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d3b1c`

## pseudocode

```c
__int64 __fastcall Utils::SetRegistryKeyDWORD64Ex(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  LSTATUS v4; // ebx
  signed int v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  signed int v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  signed int LastError; // eax
  int v13; // edx
  unsigned int v14; // r8d
  void **v15; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  __int64 Data; // [rsp+88h] [rbp+28h] BYREF

  Data = a4;
  v15 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
  hKey = 0;
  v4 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v4 < 0 )
  {
    v15 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
    if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v15) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v13, v14);
      JUMPOUT(0x1800D3C06LL);
    }
    return (unsigned int)v4;
  }
  v15 = &Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable';
  v4 = RegSetValueExW(hKey, L"StartTimeBin", 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( v4 < 0 )
  {
    if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v15) )
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
      __debugbreak();
    }
    return (unsigned int)v4;
  }
  if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(&v15) )
  {
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800d3ac4  mov     r11, rsp
0x1800d3ac7  mov     [r11+8], rbx
0x1800d3acb  mov     [r11+10h], rsi
0x1800d3acf  mov     [r11+20h], r9
0x1800d3ad3  push    rbp
0x1800d3ad4  mov     rbp, rsp
0x1800d3ad7  sub     rsp, 60h
0x1800d3adb  mov     qword ptr [r11-28h], 0
0x1800d3ae3  lea     rax, [rbp+hKey]
0x1800d3ae7  mov     [r11-30h], rax
0x1800d3aeb  lea     rsi, ??_7?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::`vftable'
0x1800d3af2  mov     qword ptr [r11-38h], 0
0x1800d3afa  xor     r9d, r9d; lpClass
0x1800d3afd  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x1800d3b05  xor     r8d, r8d; Reserved
0x1800d3b08  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800d3b10  mov     [rbp+var_10], rsi
0x1800d3b14  mov     [rbp+hKey], 0
0x1800d3b1c  call    cs:__imp_RegCreateKeyExW
0x1800d3b22  mov     ebx, eax
0x1800d3b24  test    eax, eax
0x1800d3b26  jns     short loc_1800D3B48
0x1800d3b28  cmp     [rbp+hKey], 0
0x1800d3b2d  mov     [rbp+var_10], rsi
0x1800d3b31  jz      short loc_1800D3B44
0x1800d3b33  lea     rcx, [rbp+var_10]
0x1800d3b37  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3b3c  test    al, al
0x1800d3b3e  jz      loc_1800D3BED
0x1800d3b44  mov     eax, ebx
0x1800d3b46  jmp     short loc_1800D3BA9
0x1800d3b48  mov     rcx, [rbp+hKey]; hKey
0x1800d3b4c  lea     rax, [rbp+Data]
0x1800d3b50  mov     [rsp+60h+samDesired], 8; cbData
0x1800d3b58  lea     rdx, aStarttimebin; "StartTimeBin"
0x1800d3b5f  mov     r9d, 0Bh; dwType
0x1800d3b65  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800d3b6a  xor     r8d, r8d; Reserved
0x1800d3b6d  call    cs:__imp_RegSetValueExW
0x1800d3b73  mov     [rbp+var_10], rsi
0x1800d3b77  mov     ebx, eax
0x1800d3b79  test    eax, eax
0x1800d3b7b  jns     short loc_1800D3B93
0x1800d3b7d  cmp     [rbp+hKey], 0
0x1800d3b82  jz      short loc_1800D3B44
0x1800d3b84  lea     rcx, [rbp+var_10]
0x1800d3b88  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3b8d  test    al, al
0x1800d3b8f  jz      short loc_1800D3BD3
0x1800d3b91  jmp     short loc_1800D3B44
0x1800d3b93  cmp     [rbp+hKey], 0
0x1800d3b98  jz      short loc_1800D3BA7
0x1800d3b9a  lea     rcx, [rbp+var_10]
0x1800d3b9e  call    ?InternalClose@?$HandleT@URegistryKeyTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegistryKeyTraits>::InternalClose(void)
0x1800d3ba3  test    al, al
0x1800d3ba5  jz      short loc_1800D3BB9
0x1800d3ba7  xor     eax, eax
0x1800d3ba9  mov     rbx, [rsp+60h+arg_0]
0x1800d3bae  mov     rsi, [rsp+60h+arg_8]
0x1800d3bb3  add     rsp, 60h
0x1800d3bb7  pop     rbp
0x1800d3bb8  retn
0x1800d3bb9  call    cs:__imp_GetLastError
0x1800d3bbf  test    eax, eax
0x1800d3bc1  jle     short loc_1800D3BCB
0x1800d3bc3  movzx   eax, ax
0x1800d3bc6  or      eax, 80070000h
0x1800d3bcb  mov     ecx, eax; this
0x1800d3bcd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d3bd2  int     3; Trap to Debugger
0x1800d3bd3  call    cs:__imp_GetLastError
0x1800d3bd9  test    eax, eax
0x1800d3bdb  jle     short loc_1800D3BE5
0x1800d3bdd  movzx   eax, ax
0x1800d3be0  or      eax, 80070000h
0x1800d3be5  mov     ecx, eax; this
0x1800d3be7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800d3bec  int     3; Trap to Debugger
0x1800d3bed  call    cs:__imp_GetLastError
0x1800d3bf3  test    eax, eax
0x1800d3bf5  jle     short loc_1800D3BFF
0x1800d3bf7  movzx   eax, ax
0x1800d3bfa  or      eax, 80070000h
0x1800d3bff  mov     ecx, eax; this
0x1800d3c01  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
