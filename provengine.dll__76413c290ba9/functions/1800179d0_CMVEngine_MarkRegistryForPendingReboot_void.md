# CMVEngine::MarkRegistryForPendingReboot(void)

- ea: `0x1800179d0`
- end: `0x180017aa2`
- name: `?MarkRegistryForPendingReboot@CMVEngine@@UEAAJXZ`
- size: `210`
- prototype: `__int64 __fastcall(CMVEngine *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180009900`
- `0x1800179d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017a79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017a79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a94`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017a1d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017a1d`

## pseudocode

```c
__int64 __fastcall CMVEngine::MarkRegistryForPendingReboot(CMVEngine *this)
{
  unsigned int v1; // eax
  __int64 v2; // rdx
  unsigned int v3; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v1 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 1u, 2u, 0, &hKey, 0);
  if ( v1 )
  {
    v2 = 3292;
LABEL_3:
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v2,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
           (const char *)v1,
           dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  Data = 1;
  v1 = RegSetValueExW(hKey, 0, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v1 )
  {
    v2 = 3296;
    goto LABEL_3;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800179d0  mov     r11, rsp
0x1800179d3  push    rbx
0x1800179d4  sub     rsp, 50h
0x1800179d8  mov     rdx, cs:lpSubKey; lpSubKey
0x1800179df  lea     rax, [r11+18h]
0x1800179e3  mov     qword ptr [r11-18h], 0
0x1800179eb  mov     ebx, 1
0x1800179f0  mov     [r11-20h], rax
0x1800179f4  xor     r9d, r9d; lpClass
0x1800179f7  mov     qword ptr [r11-28h], 0
0x1800179ff  xor     r8d, r8d; Reserved
0x180017a02  mov     [rsp+58h+samDesired], 2; samDesired
0x180017a0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017a11  mov     [rsp+58h+dwOptions], ebx; unsigned int
0x180017a15  mov     qword ptr [r11+18h], 0
0x180017a1d  call    cs:__imp_RegCreateKeyExW
0x180017a23  test    eax, eax
0x180017a25  jz      short loc_180017A56
0x180017a27  mov     edx, 0CDCh; void *
0x180017a2c  mov     rcx, [rsp+58h]; this
0x180017a31  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180017a38  mov     r9d, eax; char *
0x180017a3b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017a40  mov     rcx, [rsp+58h+hKey]; hKey
0x180017a45  mov     ebx, eax
0x180017a47  test    rcx, rcx
0x180017a4a  jz      short loc_180017A52
0x180017a4c  call    cs:__imp_RegCloseKey
0x180017a52  mov     eax, ebx
0x180017a54  jmp     short loc_180017A9C
0x180017a56  mov     rcx, [rsp+58h+hKey]; hKey
0x180017a5b  lea     rax, [rsp+58h+Data]
0x180017a60  mov     r9d, 4; dwType
0x180017a66  mov     [rsp+58h+Data], ebx
0x180017a6a  mov     [rsp+58h+samDesired], r9d; cbData
0x180017a6f  xor     r8d, r8d; Reserved
0x180017a72  xor     edx, edx; lpValueName
0x180017a74  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180017a79  call    cs:__imp_RegSetValueExW
0x180017a7f  test    eax, eax
0x180017a81  jz      short loc_180017A8A
0x180017a83  mov     edx, 0CE0h
0x180017a88  jmp     short loc_180017A2C
0x180017a8a  mov     rcx, [rsp+58h+hKey]; hKey
0x180017a8f  test    rcx, rcx
0x180017a92  jz      short loc_180017A9A
0x180017a94  call    cs:__imp_RegCloseKey
0x180017a9a  xor     eax, eax
0x180017a9c  add     rsp, 50h
0x180017aa0  pop     rbx
0x180017aa1  retn
```
