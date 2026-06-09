# CInputDllRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800cf4a4`
- end: `0x1800cf5a1`
- name: `?Open@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `253`
- prototype: `__int64 __fastcall(CInputDllRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800cd114`
- `0x1800cdcec`
- `0x1800ce6c4`
- `0x1800cf108`
- `0x1800cf5a8`
- `0x1800cfc04`
- `0x1800cffc0`

## callees

- `0x1800539d8`
- `0x1800cf4a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf507`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf507`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cf55b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cf55b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf584`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800cf4e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800cf4e3`

## pseudocode

```c
__int64 __fastcall CInputDllRegKey::Open(CInputDllRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)
{
  HKEY v6; // rsi
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  HKEY phkResult; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp+10h] BYREF

  phkResult = 0;
  hKeya = 0;
  v6 = hKey;
  if ( hKey == HKEY_CURRENT_USER && !RegOpenCurrentUser(samDesired, &hKeya) )
    v6 = hKeya;
  v8 = RegOpenKeyExW(v6, lpSubKey, 0, samDesired, &phkResult);
  v9 = v8;
  if ( !v8
    || v8 == 5
    && (dwDisposition = 0, (v9 = RegCreateKeyExW(v6, lpSubKey, 0, 0, 4u, samDesired, 0, &phkResult, &dwDisposition)) == 0) )
  {
    v9 = CInputDllRegKey::Close(this);
    *((_QWORD *)this + 1) = phkResult;
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return v9;
}

```

## disassembly

```asm
0x1800cf4a4  mov     rax, rsp
0x1800cf4a7  mov     [rax+8], rbx
0x1800cf4ab  mov     [rax+18h], rbp
0x1800cf4af  push    rsi
0x1800cf4b0  push    rdi
0x1800cf4b1  push    r14
0x1800cf4b3  sub     rsp, 60h
0x1800cf4b7  mov     qword ptr [rax-28h], 0
0x1800cf4bf  mov     ebp, r9d
0x1800cf4c2  mov     qword ptr [rax-20h], 0
0x1800cf4ca  mov     r14, r8
0x1800cf4cd  mov     rsi, rdx
0x1800cf4d0  mov     rdi, rcx
0x1800cf4d3  cmp     rdx, 0FFFFFFFF80000001h
0x1800cf4da  jnz     short loc_1800CF4F1
0x1800cf4dc  lea     rdx, [rax-20h]; phkResult
0x1800cf4e0  mov     ecx, r9d; samDesired
0x1800cf4e3  call    cs:__imp_RegOpenCurrentUser
0x1800cf4e9  test    eax, eax
0x1800cf4eb  cmovz   rsi, [rsp+78h+hKey]
0x1800cf4f1  lea     rax, [rsp+78h+var_28]
0x1800cf4f6  mov     r9d, ebp; samDesired
0x1800cf4f9  xor     r8d, r8d; ulOptions
0x1800cf4fc  mov     [rsp+78h+phkResult], rax; phkResult
0x1800cf501  mov     rdx, r14; lpSubKey
0x1800cf504  mov     rcx, rsi; hKey
0x1800cf507  call    cs:__imp_RegOpenKeyExW
0x1800cf50d  mov     ebx, eax
0x1800cf50f  test    eax, eax
0x1800cf511  jz      short loc_1800CF567
0x1800cf513  cmp     eax, 5
0x1800cf516  jnz     short loc_1800CF57A
0x1800cf518  lea     rax, [rsp+78h+dwDisposition]
0x1800cf520  mov     [rsp+78h+dwDisposition], 0
0x1800cf52b  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x1800cf530  xor     r9d, r9d; lpClass
0x1800cf533  lea     rax, [rsp+78h+var_28]
0x1800cf538  xor     r8d, r8d; Reserved
0x1800cf53b  mov     [rsp+78h+var_40], rax; phkResult
0x1800cf540  mov     rdx, r14; lpSubKey
0x1800cf543  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cf54c  mov     rcx, rsi; hKey
0x1800cf54f  mov     [rsp+78h+samDesired], ebp; samDesired
0x1800cf553  mov     dword ptr [rsp+78h+phkResult], 4; dwOptions
0x1800cf55b  call    cs:__imp_RegCreateKeyExW
0x1800cf561  mov     ebx, eax
0x1800cf563  test    eax, eax
0x1800cf565  jnz     short loc_1800CF57A
0x1800cf567  mov     rcx, rdi; this
0x1800cf56a  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800cf56f  mov     ebx, eax
0x1800cf571  mov     rax, [rsp+78h+var_28]
0x1800cf576  mov     [rdi+8], rax
0x1800cf57a  mov     rcx, [rsp+78h+hKey]; hKey
0x1800cf57f  test    rcx, rcx
0x1800cf582  jz      short loc_1800CF58A
0x1800cf584  call    cs:__imp_RegCloseKey
0x1800cf58a  lea     r11, [rsp+78h+var_18]
0x1800cf58f  mov     eax, ebx
0x1800cf591  mov     rbx, [r11+20h]
0x1800cf595  mov     rbp, [r11+30h]
0x1800cf599  mov     rsp, r11
0x1800cf59c  pop     r14
0x1800cf59e  pop     rdi
0x1800cf59f  pop     rsi
0x1800cf5a0  retn
```
