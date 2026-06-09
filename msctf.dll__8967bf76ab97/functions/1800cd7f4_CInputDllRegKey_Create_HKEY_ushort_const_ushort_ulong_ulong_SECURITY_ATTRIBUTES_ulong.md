# CInputDllRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1800cd7f4`
- end: `0x1800cd910`
- name: `?Create@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `284`
- prototype: `__int64 __usercall@<rax>(CInputDllRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cf5a8`
- `0x1800d0718`
- `0x1800d0b9c`

## callees

- `0x1800539d8`
- `0x1800cd7f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd884`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd8cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd884`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd8cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd8f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd8f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800cd840`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800cd840`

## pseudocode

```c
__int64 __fastcall CInputDllRegKey::Create(
        CInputDllRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        DWORD dwDisposition)
{
  HKEY v6; // rsi
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  HKEY phkResult; // [rsp+78h] [rbp+28h] BYREF
  HKEY v12; // [rsp+88h] [rbp+38h] BYREF

  dwDisposition = 0;
  v12 = 0;
  v6 = hKey;
  phkResult = 0;
  if ( hKey == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x2001Fu, &phkResult) )
    v6 = phkResult;
  v8 = RegCreateKeyExW(v6, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v12, &dwDisposition);
  v9 = v8;
  if ( !v8 || v8 == 5 && (v9 = RegCreateKeyExW(v6, lpSubKey, 0, 0, 4u, 0x2001Fu, 0, &v12, &dwDisposition)) == 0 )
  {
    v9 = CInputDllRegKey::Close(this);
    *((_QWORD *)this + 1) = v12;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v9;
}

```

## disassembly

```asm
0x1800cd7f4  mov     [rsp-18h+arg_0], rbx
0x1800cd7f9  mov     [rsp-18h+arg_10], rsi
0x1800cd7fe  mov     [rsp-18h+arg_18], r9
0x1800cd803  push    rbp
0x1800cd804  push    rdi
0x1800cd805  push    r14
0x1800cd807  mov     rbp, rsp
0x1800cd80a  sub     rsp, 50h
0x1800cd80e  mov     [rbp+dwDisposition], 0
0x1800cd815  mov     r14, r8
0x1800cd818  mov     [rbp+arg_18], 0
0x1800cd820  mov     rsi, rdx
0x1800cd823  mov     [rbp+phkResult], 0
0x1800cd82b  mov     rdi, rcx
0x1800cd82e  cmp     rdx, 0FFFFFFFF80000001h
0x1800cd835  jnz     short loc_1800CD84D
0x1800cd837  lea     rdx, [rbp+phkResult]; phkResult
0x1800cd83b  mov     ecx, 2001Fh; samDesired
0x1800cd840  call    cs:__imp_RegOpenCurrentUser
0x1800cd846  test    eax, eax
0x1800cd848  cmovz   rsi, [rbp+phkResult]
0x1800cd84d  lea     rax, [rbp+dwDisposition]
0x1800cd851  xor     r9d, r9d; lpClass
0x1800cd854  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x1800cd859  xor     r8d, r8d; Reserved
0x1800cd85c  lea     rax, [rbp+arg_18]
0x1800cd860  mov     rdx, r14; lpSubKey
0x1800cd863  mov     [rsp+50h+var_18], rax; phkResult
0x1800cd868  mov     rcx, rsi; hKey
0x1800cd86b  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cd874  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x1800cd87c  mov     [rsp+50h+dwOptions], 0; dwOptions
0x1800cd884  call    cs:__imp_RegCreateKeyExW
0x1800cd88a  mov     ebx, eax
0x1800cd88c  test    eax, eax
0x1800cd88e  jz      short loc_1800CD8D8
0x1800cd890  cmp     eax, 5
0x1800cd893  jnz     short loc_1800CD8EA
0x1800cd895  lea     rax, [rbp+dwDisposition]
0x1800cd899  xor     r9d, r9d; lpClass
0x1800cd89c  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x1800cd8a1  xor     r8d, r8d; Reserved
0x1800cd8a4  lea     rax, [rbp+arg_18]
0x1800cd8a8  mov     rdx, r14; lpSubKey
0x1800cd8ab  mov     [rsp+50h+var_18], rax; phkResult
0x1800cd8b0  mov     rcx, rsi; hKey
0x1800cd8b3  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cd8bc  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x1800cd8c4  mov     [rsp+50h+dwOptions], 4; dwOptions
0x1800cd8cc  call    cs:__imp_RegCreateKeyExW
0x1800cd8d2  mov     ebx, eax
0x1800cd8d4  test    eax, eax
0x1800cd8d6  jnz     short loc_1800CD8EA
0x1800cd8d8  mov     rcx, rdi; this
0x1800cd8db  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800cd8e0  mov     ebx, eax
0x1800cd8e2  mov     rax, [rbp+arg_18]
0x1800cd8e6  mov     [rdi+8], rax
0x1800cd8ea  mov     rcx, [rbp+phkResult]; hKey
0x1800cd8ee  test    rcx, rcx
0x1800cd8f1  jz      short loc_1800CD8F9
0x1800cd8f3  call    cs:__imp_RegCloseKey
0x1800cd8f9  lea     r11, [rsp+50h+var_s0]
0x1800cd8fe  mov     eax, ebx
0x1800cd900  mov     rbx, [r11+20h]
0x1800cd904  mov     rsi, [r11+30h]
0x1800cd908  mov     rsp, r11
0x1800cd90b  pop     r14
0x1800cd90d  pop     rdi
0x1800cd90e  pop     rbp
0x1800cd90f  retn
```
