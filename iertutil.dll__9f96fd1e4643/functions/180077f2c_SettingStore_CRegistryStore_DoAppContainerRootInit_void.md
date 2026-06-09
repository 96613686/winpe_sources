# SettingStore::CRegistryStore::_DoAppContainerRootInit(void)

- ea: `0x180077f2c`
- end: `0x18007801e`
- name: `?_DoAppContainerRootInit@CRegistryStore@SettingStore@@AEAAJXZ`
- size: `242`
- prototype: `__int64 __fastcall(SettingStore::CRegistryStore *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020014`

## callees

- `0x180031f00`
- `0x180077f2c`
- `0x180083be6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077f45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077f45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180077fcf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180077fcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180077fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180077fbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077fa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077fa0`

## pseudocode

```c
__int64 __fastcall SettingStore::CRegistryStore::_DoAppContainerRootInit(SettingStore::CRegistryStore *this)
{
  const wchar_t *String; // rdi
  unsigned int v3; // ebx
  size_t v4; // rsi
  LSTATUS v5; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rax
  HKEY v8; // rcx
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  String = (const wchar_t *)IEConfiguration_GetString(285212719);
  if ( GetLastError() == 87 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v4 = MaxCount;
    if ( !wcsncmp_0(String, L"HKCU\\", (unsigned int)MaxCount) )
    {
      v3 = 0;
      phkResult = 0;
      v5 = RegOpenKeyExW(HKEY_CURRENT_USER, &String[v4], 0, 0x20019u, &phkResult);
      if ( v5 )
      {
        if ( v5 > 0 )
          return (unsigned __int16)v5 | 0x80070000;
        else
          return (unsigned int)v5;
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        v7 = HeapAlloc(ProcessHeap, 8u, 0x18u);
        if ( v7 )
        {
          v8 = phkResult;
          *v7 = &SettingStore::CRegistryKey::`vftable';
          v7[2] = v8;
          *((_DWORD *)v7 + 3) = 3;
          *((_DWORD *)v7 + 2) = 1;
        }
        *((_QWORD *)this + 826) = v7;
        if ( !v7 )
          return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180077f2c  push    rbx
0x180077f2e  push    rbp
0x180077f2f  push    rsi
0x180077f30  push    rdi
0x180077f31  sub     rsp, 38h
0x180077f35  mov     rbp, rcx
0x180077f38  mov     ecx, 1100002Fh
0x180077f3d  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180077f42  mov     rdi, rax
0x180077f45  call    cs:__imp_GetLastError
0x180077f4b  cmp     eax, 57h ; 'W'
0x180077f4e  jnz     short loc_180077F5A
0x180077f50  mov     ebx, 80004005h
0x180077f55  jmp     loc_180078013
0x180077f5a  mov     rsi, cs:MaxCount
0x180077f61  lea     rdx, aHkcu; "HKCU\\"
0x180077f68  mov     r8d, esi; MaxCount
0x180077f6b  mov     rcx, rdi; String1
0x180077f6e  call    wcsncmp_0
0x180077f73  test    eax, eax
0x180077f75  jnz     loc_18007800E
0x180077f7b  lea     rax, [rsp+58h+arg_8]
0x180077f80  xor     ebx, ebx
0x180077f82  lea     rdx, [rdi+rsi*2]; lpSubKey
0x180077f86  mov     [rsp+58h+arg_8], rbx
0x180077f8b  mov     r9d, 20019h; samDesired
0x180077f91  mov     [rsp+58h+phkResult], rax; phkResult
0x180077f96  xor     r8d, r8d; ulOptions
0x180077f99  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180077fa0  call    cs:__imp_RegOpenKeyExW
0x180077fa6  test    eax, eax
0x180077fa8  jz      short loc_180077FBD
0x180077faa  jg      short loc_180077FB0
0x180077fac  mov     ebx, eax
0x180077fae  jmp     short loc_180077FB9
0x180077fb0  movzx   ebx, ax
0x180077fb3  or      ebx, 80070000h
0x180077fb9  test    ebx, ebx
0x180077fbb  js      short loc_180078013
0x180077fbd  call    cs:__imp_GetProcessHeap
0x180077fc3  mov     edx, 8; dwFlags
0x180077fc8  mov     rcx, rax; hHeap
0x180077fcb  lea     r8d, [rdx+10h]; dwBytes
0x180077fcf  call    cs:__imp_HeapAlloc
0x180077fd5  test    rax, rax
0x180077fd8  jz      short loc_180077FFB
0x180077fda  mov     rcx, [rsp+58h+arg_8]
0x180077fdf  lea     rdx, ??_7CRegistryKey@SettingStore@@6B@; const SettingStore::CRegistryKey::`vftable'
0x180077fe6  mov     [rax], rdx
0x180077fe9  mov     [rax+10h], rcx
0x180077fed  mov     dword ptr [rax+0Ch], 3
0x180077ff4  mov     dword ptr [rax+8], 1
0x180077ffb  mov     [rbp+19D0h], rax
0x180078002  test    rax, rax
0x180078005  jnz     short loc_180078013
0x180078007  mov     ebx, 8007000Eh
0x18007800c  jmp     short loc_180078013
0x18007800e  mov     ebx, 8000FFFFh
0x180078013  mov     eax, ebx
0x180078015  add     rsp, 38h
0x180078019  pop     rdi
0x18007801a  pop     rsi
0x18007801b  pop     rbp
0x18007801c  pop     rbx
0x18007801d  retn
```
