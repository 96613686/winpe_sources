# CNgscbScopedPrivilege::ReleasePrivilege(void)

- ea: `0x180010e54`
- end: `0x180010e8d`
- name: `?ReleasePrivilege@CNgscbScopedPrivilege@@QEAAXXZ`
- size: `57`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800106ec`

## callees

- `0x180010e54`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180010e7a`
- `KERNEL32!CloseHandle` at `0x180010e7a`
- `ADVAPI32!SetThreadToken` at `0x180010e68`
- `ADVAPI32!SetThreadToken` at `0x180010e68`

## pseudocode

```c
void __fastcall CNgscbScopedPrivilege::ReleasePrivilege(HANDLE *this)
{
  if ( *((_BYTE *)this + 8) )
  {
    SetThreadToken(0, *this);
    *((_BYTE *)this + 8) = 0;
  }
  if ( *this )
  {
    CloseHandle(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180010e54  push    rbx
0x180010e56  sub     rsp, 20h
0x180010e5a  cmp     byte ptr [rcx+8], 0
0x180010e5e  mov     rbx, rcx
0x180010e61  jz      short loc_180010E72
0x180010e63  mov     rdx, [rcx]; Token
0x180010e66  xor     ecx, ecx; Thread
0x180010e68  call    cs:__imp_SetThreadToken
0x180010e6e  mov     byte ptr [rbx+8], 0
0x180010e72  mov     rcx, [rbx]; hObject
0x180010e75  test    rcx, rcx
0x180010e78  jz      short loc_180010E87
0x180010e7a  call    cs:__imp_CloseHandle
0x180010e80  mov     qword ptr [rbx], 0
0x180010e87  add     rsp, 20h
0x180010e8b  pop     rbx
0x180010e8c  retn
```
