# CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18007a4d8`
- end: `0x18007a607`
- name: `?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a878`
- `0x18007ac3c`
- `0x18007b444`
- `0x18007bdec`
- `0x18007c678`

## callees

- `0x180071344`
- `0x18007a4d8`
- `0x180081154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a5f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a5f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a52b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a52b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a576`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a5d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a576`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a5d4`

## pseudocode

```c
__int64 __fastcall CommonUtil::GetStringFromRegistry(LPCWSTR lpSubKey, LPCWSTR lpValueName, __int64 a3)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  BYTE *v9; // rax
  LSTATUS v10; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  *(_QWORD *)(a3 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    cbData = 0;
    Type = 0;
    v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 )
    {
      if ( Type == 1 )
      {
        std::wstring::resize(a3, ((unsigned __int64)cbData >> 1) - 1, 0);
        v9 = (BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
        v10 = RegQueryValueExW(hKey, lpValueName, 0, &Type, v9, &cbData);
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
      }
      else
      {
        v7 = -2147418113;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007a4d8  mov     [rsp-18h+arg_0], rbx
0x18007a4dd  push    rbp
0x18007a4de  push    rsi
0x18007a4df  push    rdi
0x18007a4e0  mov     rbp, rsp
0x18007a4e3  sub     rsp, 40h
0x18007a4e7  mov     rbx, rcx
0x18007a4ea  mov     [rbp+hKey], 0
0x18007a4f2  mov     rcx, r8
0x18007a4f5  mov     qword ptr [r8+10h], 0
0x18007a4fd  mov     rdi, r8
0x18007a500  mov     rsi, rdx
0x18007a503  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a508  xor     r9d, r9d
0x18007a50b  xor     r8d, r8d; ulOptions
0x18007a50e  mov     rdx, rbx; lpSubKey
0x18007a511  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007a518  mov     [rax], r9w
0x18007a51c  lea     rax, [rbp+hKey]
0x18007a520  mov     r9d, 20019h; samDesired
0x18007a526  mov     [rsp+40h+phkResult], rax; phkResult
0x18007a52b  call    cs:__imp_RegOpenKeyExW
0x18007a531  mov     ebx, eax
0x18007a533  test    eax, eax
0x18007a535  jle     short loc_18007A540
0x18007a537  movzx   ebx, ax
0x18007a53a  or      ebx, 80070000h
0x18007a540  test    ebx, ebx
0x18007a542  js      loc_18007A5E9
0x18007a548  mov     rcx, [rbp+hKey]; hKey
0x18007a54c  lea     rax, [rbp+cbData]
0x18007a550  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18007a555  lea     r9, [rbp+Type]; lpType
0x18007a559  xor     r8d, r8d; lpReserved
0x18007a55c  mov     [rsp+40h+phkResult], 0; lpData
0x18007a565  mov     rdx, rsi; lpValueName
0x18007a568  mov     [rbp+cbData], 0
0x18007a56f  mov     [rbp+Type], 0
0x18007a576  call    cs:__imp_RegQueryValueExW
0x18007a57c  mov     ebx, eax
0x18007a57e  test    eax, eax
0x18007a580  jle     short loc_18007A58B
0x18007a582  movzx   ebx, ax
0x18007a585  or      ebx, 80070000h
0x18007a58b  test    ebx, ebx
0x18007a58d  js      short loc_18007A5E9
0x18007a58f  cmp     [rbp+Type], 1
0x18007a593  jz      short loc_18007A59C
0x18007a595  mov     ebx, 8000FFFFh
0x18007a59a  jmp     short loc_18007A5E9
0x18007a59c  mov     edx, [rbp+cbData]
0x18007a59f  xor     r8d, r8d
0x18007a5a2  shr     rdx, 1
0x18007a5a5  mov     rcx, rdi
0x18007a5a8  dec     rdx
0x18007a5ab  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18007a5b0  mov     rcx, rdi
0x18007a5b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a5b8  lea     rcx, [rbp+cbData]
0x18007a5bc  xor     r8d, r8d; lpReserved
0x18007a5bf  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18007a5c4  lea     r9, [rbp+Type]; lpType
0x18007a5c8  mov     rcx, [rbp+hKey]; hKey
0x18007a5cc  mov     rdx, rsi; lpValueName
0x18007a5cf  mov     [rsp+40h+phkResult], rax; lpData
0x18007a5d4  call    cs:__imp_RegQueryValueExW
0x18007a5da  mov     ebx, eax
0x18007a5dc  test    eax, eax
0x18007a5de  jle     short loc_18007A5E9
0x18007a5e0  movzx   ebx, ax
0x18007a5e3  or      ebx, 80070000h
0x18007a5e9  mov     rcx, [rbp+hKey]; hKey
0x18007a5ed  test    rcx, rcx
0x18007a5f0  jz      short loc_18007A5F8
0x18007a5f2  call    cs:__imp_RegCloseKey
0x18007a5f8  mov     eax, ebx
0x18007a5fa  mov     rbx, [rsp+40h+arg_0]
0x18007a5ff  add     rsp, 40h
0x18007a603  pop     rdi
0x18007a604  pop     rsi
0x18007a605  pop     rbp
0x18007a606  retn
```
