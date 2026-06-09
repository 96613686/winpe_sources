# CTempRegKey::~CTempRegKey(void)

- ea: `0x18005c3ac`
- end: `0x18005c41c`
- name: `??1CTempRegKey@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(CTempRegKey *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180027370`
- `0x18005c480`
- `0x18005c844`
- `0x18005fdce`
- `0x18006051a`

## callees

- `0x18005c3ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c3e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c3fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c3e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c3fb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005c3d1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005c3d1`
- `fwbase!FwBaseFree` at `0x18005c410`

## pseudocode

```c
void __fastcall CTempRegKey::~CTempRegKey(CTempRegKey *this)
{
  HKEY v2; // rcx
  const WCHAR *v3; // rdx
  HKEY v4; // rcx
  HKEY v5; // rcx

  *(_QWORD *)this = &CTempRegKey::`vftable';
  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = (const WCHAR *)*((_QWORD *)this + 3);
    if ( v3 )
      RegDeleteTreeW(v2, v3);
  }
  v4 = (HKEY)*((_QWORD *)this + 2);
  if ( v4 )
    RegCloseKey(v4);
  v5 = (HKEY)*((_QWORD *)this + 1);
  if ( v5 )
    RegCloseKey(v5);
  FwBaseFree(*((_QWORD *)this + 3));
}

```

## disassembly

```asm
0x18005c3ac  push    rbx
0x18005c3ae  sub     rsp, 20h
0x18005c3b2  lea     rax, ??_7CTempRegKey@@6B@; const CTempRegKey::`vftable'
0x18005c3b9  mov     rbx, rcx
0x18005c3bc  mov     [rcx], rax
0x18005c3bf  mov     rcx, [rcx+10h]; hKey
0x18005c3c3  test    rcx, rcx
0x18005c3c6  jz      short loc_18005C3DD
0x18005c3c8  mov     rdx, [rbx+18h]; lpSubKey
0x18005c3cc  test    rdx, rdx
0x18005c3cf  jz      short loc_18005C3DD
0x18005c3d1  call    cs:__imp_RegDeleteTreeW
0x18005c3d8  nop     dword ptr [rax+rax+00h]
0x18005c3dd  mov     rcx, [rbx+10h]; hKey
0x18005c3e1  test    rcx, rcx
0x18005c3e4  jz      short loc_18005C3F2
0x18005c3e6  call    cs:__imp_RegCloseKey
0x18005c3ed  nop     dword ptr [rax+rax+00h]
0x18005c3f2  mov     rcx, [rbx+8]; hKey
0x18005c3f6  test    rcx, rcx
0x18005c3f9  jz      short loc_18005C407
0x18005c3fb  call    cs:__imp_RegCloseKey
0x18005c402  nop     dword ptr [rax+rax+00h]
0x18005c407  mov     rcx, [rbx+18h]
0x18005c40b  add     rsp, 20h
0x18005c40f  pop     rbx
0x18005c410  jmp     cs:__imp_FwBaseFree
```
