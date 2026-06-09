# CDisplayRegKey::CDisplayRegKey(ushort const *)

- ea: `0x1800f68ec`
- end: `0x1800f697b`
- name: `??0CDisplayRegKey@@QEAA@PEBG@Z`
- size: `143`
- prototype: `CDisplayRegKey *__fastcall(CDisplayRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f6860`

## callees

- `0x1800f68ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6929`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f695f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f6929`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f695f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f696c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f696c`

## pseudocode

```c
CDisplayRegKey *__fastcall CDisplayRegKey::CDisplayRegKey(CDisplayRegKey *this, const unsigned __int16 *a2)
{
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *(_BYTE *)this = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Direct2D", 0, 1u, &hKey) )
  {
    v4 = RegOpenKeyExW(hKey, &cchOriginalDestLength, 0, 1u, (PHKEY)this + 1);
    RegCloseKey(hKey);
    if ( !v4 )
      *(_BYTE *)this = 1;
  }
  return this;
}

```

## disassembly

```asm
0x1800f68ec  mov     r11, rsp
0x1800f68ef  mov     [r11+8], rbx
0x1800f68f3  mov     [r11+10h], rdx
0x1800f68f7  push    rdi
0x1800f68f8  sub     rsp, 30h
0x1800f68fc  mov     rdi, rcx
0x1800f68ff  mov     byte ptr [rcx], 0
0x1800f6902  lea     rax, [r11+10h]
0x1800f6906  mov     qword ptr [r11+10h], 0
0x1800f690e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f6915  mov     [r11-18h], rax
0x1800f6919  mov     r9d, 1; samDesired
0x1800f691f  lea     rdx, SubKey; "Software\\Microsoft\\Direct2D"
0x1800f6926  xor     r8d, r8d; ulOptions
0x1800f6929  call    cs:__imp_RegOpenKeyExW
0x1800f692f  test    eax, eax
0x1800f6931  jz      short loc_1800F6941
0x1800f6933  mov     rbx, [rsp+38h+arg_0]
0x1800f6938  mov     rax, rdi
0x1800f693b  add     rsp, 30h
0x1800f693f  pop     rdi
0x1800f6940  retn
0x1800f6941  mov     rcx, [rsp+38h+hKey]; hKey
0x1800f6946  lea     rax, [rdi+8]
0x1800f694a  mov     r9d, 1; samDesired
0x1800f6950  mov     [rsp+38h+phkResult], rax; phkResult
0x1800f6955  xor     r8d, r8d; ulOptions
0x1800f6958  lea     rdx, cchOriginalDestLength; lpSubKey
0x1800f695f  call    cs:__imp_RegOpenKeyExW
0x1800f6965  mov     rcx, [rsp+38h+hKey]; hKey
0x1800f696a  mov     ebx, eax
0x1800f696c  call    cs:__imp_RegCloseKey
0x1800f6972  test    ebx, ebx
0x1800f6974  jnz     short loc_1800F6933
0x1800f6976  mov     byte ptr [rdi], 1
0x1800f6979  jmp     short loc_1800F6933
```
