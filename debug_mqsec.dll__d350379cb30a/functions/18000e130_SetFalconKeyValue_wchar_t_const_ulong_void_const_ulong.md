# SetFalconKeyValue(wchar_t const *,ulong *,void const *,ulong *)

- ea: `0x18000e130`
- end: `0x18000e198`
- name: `?SetFalconKeyValue@@YAJPEB_WPEAKPEBX1@Z`
- size: `104`
- prototype: `int(const wchar_t *, unsigned int *, const void *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000da54`
- `0x18000e130`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000e182`
- `ADVAPI32!RegSetValueExW` at `0x18000e182`

## pseudocode

```c
LSTATUS __fastcall SetFalconKeyValue(const wchar_t *a1, unsigned int *a2, const BYTE *a3, unsigned int *a4)
{
  DWORD v4; // edi
  DWORD cbData; // esi
  LSTATUS result; // eax
  LPCWSTR lpValueName; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v4 = *a2;
  cbData = *a4;
  hKey = 0;
  lpValueName = 0;
  result = GetValueKey(a1, &lpValueName, &hKey);
  if ( !result )
    return RegSetValueExW(hKey, lpValueName, 0, v4, a3, cbData);
  return result;
}

```

## disassembly

```asm
0x18000e130  mov     rax, rsp
0x18000e133  mov     [rax+8], rbx
0x18000e137  mov     [rax+18h], rsi
0x18000e13b  push    rdi
0x18000e13c  sub     rsp, 30h
0x18000e140  mov     edi, [rdx]
0x18000e142  mov     rbx, r8
0x18000e145  mov     esi, [r9]
0x18000e148  lea     r8, [rax+20h]; HKEY *
0x18000e14c  lea     rdx, [rax+10h]; wchar_t **
0x18000e150  mov     qword ptr [rax+20h], 0
0x18000e158  mov     qword ptr [rax+10h], 0
0x18000e160  call    ?GetValueKey@@YAJPEB_WPEAPEB_WPEAPEAUHKEY__@@@Z; GetValueKey(wchar_t const *,wchar_t const * *,HKEY__ * *)
0x18000e165  test    eax, eax
0x18000e167  jnz     short loc_18000E188
0x18000e169  mov     rdx, [rsp+38h+lpValueName]; lpValueName
0x18000e16e  mov     r9d, edi; dwType
0x18000e171  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e176  xor     r8d, r8d; Reserved
0x18000e179  mov     [rsp+38h+cbData], esi; cbData
0x18000e17d  mov     [rsp+38h+lpData], rbx; lpData
0x18000e182  call    cs:__imp_RegSetValueExW
0x18000e188  mov     rbx, [rsp+38h+arg_0]
0x18000e18d  mov     rsi, [rsp+38h+arg_10]
0x18000e192  add     rsp, 30h
0x18000e196  pop     rdi
0x18000e197  retn
```
