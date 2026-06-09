# PMSIHANDLE::~PMSIHANDLE(void)

- ea: `0x140003c20`
- end: `0x140003c35`
- name: `??1PMSIHANDLE@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(PMSIHANDLE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400042b4`

## callees

- `0x140003c20`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x140003c2a`
- `msi!__imp_MsiCloseHandle` at `0x140003c2a`

## pseudocode

```c
void __fastcall PMSIHANDLE::~PMSIHANDLE(MSIHANDLE *this)
{
  MSIHANDLE v1; // ecx

  v1 = *this;
  if ( v1 )
    MsiCloseHandle(v1);
}

```

## disassembly

```asm
0x140003c20  sub     rsp, 28h
0x140003c24  mov     ecx, [rcx]; hAny
0x140003c26  test    ecx, ecx
0x140003c28  jz      short loc_140003C30
0x140003c2a  call    cs:__imp_MsiCloseHandle
0x140003c30  add     rsp, 28h
0x140003c34  retn
```
