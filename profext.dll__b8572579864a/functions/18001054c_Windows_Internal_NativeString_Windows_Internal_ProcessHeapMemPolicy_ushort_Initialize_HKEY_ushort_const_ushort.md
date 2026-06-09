# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18001054c`
- end: `0x1800105e2`
- name: `?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000feb0`

## callees

- `0x18001054c`
- `0x18001d414`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001058d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001058d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800105c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800105c3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion", 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
           a1,
           hKey,
           a4);
    RegCloseKey(hKey);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001054c  mov     r11, rsp
0x18001054f  mov     [r11+8], rbx
0x180010553  mov     [r11+10h], rsi
0x180010557  mov     [r11+18h], r8
0x18001055b  push    rdi
0x18001055c  sub     rsp, 30h
0x180010560  mov     rdi, r9
0x180010563  mov     qword ptr [r11+18h], 0
0x18001056b  mov     rsi, rcx
0x18001056e  lea     rax, [r11+18h]
0x180010572  mov     r9d, 20019h; samDesired
0x180010578  mov     [r11-18h], rax
0x18001057c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010583  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001058a  xor     r8d, r8d; ulOptions
0x18001058d  call    cs:__imp_RegOpenKeyExW
0x180010594  nop     dword ptr [rax+rax+00h]
0x180010599  mov     ebx, eax
0x18001059b  test    eax, eax
0x18001059d  jle     short loc_1800105A8
0x18001059f  movzx   ebx, ax
0x1800105a2  or      ebx, 80070000h
0x1800105a8  test    ebx, ebx
0x1800105aa  js      short loc_1800105CF
0x1800105ac  mov     rdx, [rsp+38h+hKey]
0x1800105b1  mov     r8, rdi
0x1800105b4  mov     rcx, rsi
0x1800105b7  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x1800105bc  mov     rcx, [rsp+38h+hKey]; hKey
0x1800105c1  mov     ebx, eax
0x1800105c3  call    cs:__imp_RegCloseKey
0x1800105ca  nop     dword ptr [rax+rax+00h]
0x1800105cf  mov     rsi, [rsp+38h+arg_8]
0x1800105d4  mov     eax, ebx
0x1800105d6  mov     rbx, [rsp+38h+arg_0]
0x1800105db  add     rsp, 30h
0x1800105df  pop     rdi
0x1800105e0  retn
```
