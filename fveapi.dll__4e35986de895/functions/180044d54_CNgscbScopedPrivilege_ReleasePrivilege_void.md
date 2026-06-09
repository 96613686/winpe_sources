# CNgscbScopedPrivilege::ReleasePrivilege(void)

- ea: `0x180044d54`
- end: `0x180044d9c`
- name: `?ReleasePrivilege@CNgscbScopedPrivilege@@QEAAXXZ`
- size: `72`
- prototype: `void __fastcall(CNgscbScopedPrivilege *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180086534`
- `0x18008686c`
- `0x18008fcb0`
- `0x1800d49ec`
- `0x1800d67e8`

## callees

- `0x180044d54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180044d68`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180044d68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044d87`

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
0x180044d54  push    rbx
0x180044d56  sub     rsp, 20h
0x180044d5a  cmp     byte ptr [rcx+8], 0
0x180044d5e  mov     rbx, rcx
0x180044d61  jz      short loc_180044D78
0x180044d63  mov     rdx, [rcx]; Token
0x180044d66  xor     ecx, ecx; Thread
0x180044d68  call    cs:__imp_SetThreadToken
0x180044d6f  nop     dword ptr [rax+rax+00h]
0x180044d74  mov     byte ptr [rbx+8], 0
0x180044d78  mov     rcx, [rbx]; hObject
0x180044d7b  test    rcx, rcx
0x180044d7e  jnz     short loc_180044D87
0x180044d80  add     rsp, 20h
0x180044d84  pop     rbx
0x180044d85  retn
0x180044d87  call    cs:__imp_CloseHandle
0x180044d8e  nop     dword ptr [rax+rax+00h]
0x180044d93  mov     qword ptr [rbx], 0
0x180044d9a  jmp     short loc_180044D80
```
