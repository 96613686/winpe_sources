# AccountInfo::persist(void)

- ea: `0x180011b58`
- end: `0x180011c50`
- name: `?persist@AccountInfo@@IEAAXXZ`
- size: `248`
- prototype: `void __fastcall(AccountInfo *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001193c`
- `0x18001195c`
- `0x180011a8c`

## callees

- `0x180011b58`
- `0x180011df8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180011c15`
- `ADVAPI32!RegCloseKey` at `0x180011c15`
- `ADVAPI32!RegSetValueExW` at `0x180011c08`
- `ADVAPI32!RegSetValueExW` at `0x180011c08`
- `ADVAPI32!RegCreateKeyExW` at `0x180011bbe`
- `ADVAPI32!RegCreateKeyExW` at `0x180011bbe`
- `ADVAPI32!RegDeleteKeyW` at `0x180011c36`
- `ADVAPI32!RegDeleteKeyW` at `0x180011c36`

## pseudocode

```c
void __fastcall AccountInfo::persist(AccountInfo *this)
{
  const BYTE *v1; // rdi
  bool v3; // zf
  HKEY v4; // rcx
  _WORD *v5; // rax
  _WORD *v6; // rcx
  _WORD *v7; // rax
  DWORD v8; // [rsp+60h] [rbp+8h] BYREF
  HKEY v9; // [rsp+68h] [rbp+10h] BYREF

  v1 = (const BYTE *)this + 8;
  v3 = *((_DWORD *)this + 2) == 0;
  v4 = *(HKEY *)this;
  if ( v3 )
  {
    if ( v4 )
    {
      RegCloseKey(v4);
      v7 = (_WORD *)*((_QWORD *)this + 2);
      *(_QWORD *)this = 0;
      *v7 = 58;
      RegDeleteKeyW(hKey, (LPCWSTR)this + 12);
      **((_WORD **)this + 2) = 0;
    }
  }
  else
  {
    if ( !v4 )
    {
      v5 = (_WORD *)*((_QWORD *)this + 2);
      v9 = 0;
      v8 = 0;
      *v5 = 58;
      RegCreateKeyExW(hKey, (LPCWSTR)this + 12, 0, 0, 0, 0x2001Fu, 0, &v9, &v8);
      if ( qword_18003FAF0 )
        LockoutKey::collectGarbage((LockoutKey *)&AccountInfo::root);
      v6 = (_WORD *)*((_QWORD *)this + 2);
      *(_QWORD *)this = v9;
      *v6 = 0;
    }
    RegSetValueExW(*(HKEY *)this, L"Denials", 0, 4u, v1, 4u);
  }
}

```

## disassembly

```asm
0x180011b58  mov     r11, rsp
0x180011b5b  mov     [r11+18h], rbx
0x180011b5f  push    rdi
0x180011b60  sub     rsp, 50h
0x180011b64  lea     rdi, [rcx+8]
0x180011b68  mov     rbx, rcx
0x180011b6b  cmp     dword ptr [rdi], 0
0x180011b6e  mov     rcx, [rcx]; hKey
0x180011b71  jbe     loc_180011C10
0x180011b77  test    rcx, rcx
0x180011b7a  jnz     short loc_180011BEB
0x180011b7c  mov     rax, [rbx+10h]
0x180011b80  lea     rdx, [rbx+18h]; lpSubKey
0x180011b84  mov     [r11+10h], rcx
0x180011b88  xor     r9d, r9d; lpClass
0x180011b8b  mov     [rsp+58h+arg_0], ecx
0x180011b8f  xor     r8d, r8d; Reserved
0x180011b92  mov     word ptr [rax], 3Ah ; ':'
0x180011b97  lea     rax, [r11+8]
0x180011b9b  mov     [r11-18h], rax
0x180011b9f  lea     rax, [r11+10h]
0x180011ba3  mov     [r11-20h], rax
0x180011ba7  mov     [r11-28h], rcx
0x180011bab  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180011bb3  mov     [rsp+58h+dwOptions], ecx; dwOptions
0x180011bb7  mov     rcx, cs:hKey; hKey
0x180011bbe  call    cs:__imp_RegCreateKeyExW
0x180011bc4  cmp     cs:qword_18003FAF0, 0
0x180011bcc  jz      short loc_180011BDA
0x180011bce  lea     rcx, ?root@AccountInfo@@0VLockoutKey@@A; this
0x180011bd5  call    ?collectGarbage@LockoutKey@@IEAAXXZ; LockoutKey::collectGarbage(void)
0x180011bda  mov     rax, [rsp+58h+arg_8]
0x180011bdf  mov     rcx, [rbx+10h]
0x180011be3  mov     [rbx], rax
0x180011be6  xor     eax, eax
0x180011be8  mov     [rcx], ax
0x180011beb  mov     rcx, [rbx]; hKey
0x180011bee  lea     rdx, ValueName; "Denials"
0x180011bf5  mov     r9d, 4; dwType
0x180011bfb  xor     r8d, r8d; Reserved
0x180011bfe  mov     [rsp+58h+samDesired], r9d; cbData
0x180011c03  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x180011c08  call    cs:__imp_RegSetValueExW
0x180011c0e  jmp     short loc_180011C45
0x180011c10  test    rcx, rcx
0x180011c13  jz      short loc_180011C45
0x180011c15  call    cs:__imp_RegCloseKey
0x180011c1b  mov     rax, [rbx+10h]
0x180011c1f  lea     rdx, [rbx+18h]; lpSubKey
0x180011c23  mov     qword ptr [rbx], 0
0x180011c2a  mov     word ptr [rax], 3Ah ; ':'
0x180011c2f  mov     rcx, cs:hKey; hKey
0x180011c36  call    cs:__imp_RegDeleteKeyW
0x180011c3c  mov     rcx, [rbx+10h]
0x180011c40  xor     eax, eax
0x180011c42  mov     [rcx], ax
0x180011c45  mov     rbx, [rsp+58h+arg_10]
0x180011c4a  add     rsp, 50h
0x180011c4e  pop     rdi
0x180011c4f  retn
```
