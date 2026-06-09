# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180013af4`
- end: `0x180013b79`
- name: `?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `133`
- prototype: `__int64 __fastcall(BYTE **, __int64, const WCHAR *, const WCHAR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013938`
- `0x180016ff8`
- `0x180019f14`

## callees

- `0x180013af4`
- `0x180016864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013b31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013b31`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
        BYTE **a1,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4)
{
  LSTATUS v6; // eax
  int v7; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey);
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
0x180013af4  mov     rax, rsp
0x180013af7  mov     [rax+8], rbx
0x180013afb  mov     [rax+18h], rsi
0x180013aff  mov     [rax+10h], rdx
0x180013b03  push    rdi
0x180013b04  sub     rsp, 30h
0x180013b08  mov     rsi, rcx
0x180013b0b  mov     qword ptr [rax+10h], 0
0x180013b13  lea     rcx, [rax+10h]
0x180013b17  mov     rdi, r9
0x180013b1a  mov     [rax-18h], rcx
0x180013b1e  mov     rdx, r8; lpSubKey
0x180013b21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013b28  mov     r9d, 20019h; samDesired
0x180013b2e  xor     r8d, r8d; ulOptions
0x180013b31  call    cs:__imp_RegOpenKeyExW
0x180013b37  mov     ebx, eax
0x180013b39  test    eax, eax
0x180013b3b  jle     short loc_180013B46
0x180013b3d  movzx   ebx, ax
0x180013b40  or      ebx, 80070000h
0x180013b46  test    ebx, ebx
0x180013b48  js      short loc_180013B67
0x180013b4a  mov     rdx, [rsp+38h+hKey]
0x180013b4f  mov     r8, rdi
0x180013b52  mov     rcx, rsi
0x180013b55  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180013b5a  mov     rcx, [rsp+38h+hKey]; hKey
0x180013b5f  mov     ebx, eax
0x180013b61  call    cs:__imp_RegCloseKey
0x180013b67  mov     rsi, [rsp+38h+arg_10]
0x180013b6c  mov     eax, ebx
0x180013b6e  mov     rbx, [rsp+38h+arg_0]
0x180013b73  add     rsp, 30h
0x180013b77  pop     rdi
0x180013b78  retn
```
