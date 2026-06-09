# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800432fc`
- end: `0x18004337d`
- name: `?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `129`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003f1a0`

## callees

- `0x1800432fc`
- `0x18004bcb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004336a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004336a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043336`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043336`

## string_xrefs

- `0x180043354`: `PreviewConfigs`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        __int64 a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsSelfHost\\FIDs", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
           a1,
           hKey,
           L"PreviewConfigs");
    RegCloseKey(hKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800432fc  mov     r11, rsp
0x1800432ff  mov     [r11+8], rbx
0x180043303  mov     [r11+20h], r9
0x180043307  push    rdi
0x180043308  sub     rsp, 30h
0x18004330c  mov     rdi, rcx
0x18004330f  mov     qword ptr [r11+20h], 0
0x180043317  lea     rax, [r11+20h]
0x18004331b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043322  mov     r9d, 20019h; samDesired
0x180043328  mov     [r11-18h], rax
0x18004332c  xor     r8d, r8d; ulOptions
0x18004332f  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\WindowsSelfHost\\F"...
0x180043336  call    cs:__imp_RegOpenKeyExW
0x18004333c  mov     ebx, eax
0x18004333e  test    eax, eax
0x180043340  jle     short loc_18004334B
0x180043342  movzx   ebx, ax
0x180043345  or      ebx, 80070000h
0x18004334b  test    ebx, ebx
0x18004334d  js      short loc_180043370
0x18004334f  mov     rdx, [rsp+38h+hKey]
0x180043354  lea     r8, aPreviewconfigs; "PreviewConfigs"
0x18004335b  mov     rcx, rdi
0x18004335e  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180043363  mov     rcx, [rsp+38h+hKey]; hKey
0x180043368  mov     ebx, eax
0x18004336a  call    cs:__imp_RegCloseKey
0x180043370  mov     eax, ebx
0x180043372  mov     rbx, [rsp+38h+arg_0]
0x180043377  add     rsp, 30h
0x18004337b  pop     rdi
0x18004337c  retn
```
