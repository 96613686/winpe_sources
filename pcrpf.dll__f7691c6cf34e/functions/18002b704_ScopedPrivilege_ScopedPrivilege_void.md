# ScopedPrivilege::~ScopedPrivilege(void)

- ea: `0x18002b704`
- end: `0x18002b74a`
- name: `??1ScopedPrivilege@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180032844`
- `0x180057d7a`

## callees

- `0x18002b704`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002b718`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002b718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b730`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b730`

## pseudocode

```c
void __fastcall ScopedPrivilege::~ScopedPrivilege(HANDLE *this)
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
0x18002b704  push    rbx
0x18002b706  sub     rsp, 20h
0x18002b70a  cmp     byte ptr [rcx+8], 0
0x18002b70e  mov     rbx, rcx
0x18002b711  jz      short loc_18002B728
0x18002b713  mov     rdx, [rcx]; Token
0x18002b716  xor     ecx, ecx; Thread
0x18002b718  call    cs:__imp_SetThreadToken
0x18002b71f  nop     dword ptr [rax+rax+00h]
0x18002b724  mov     byte ptr [rbx+8], 0
0x18002b728  mov     rcx, [rbx]; hObject
0x18002b72b  test    rcx, rcx
0x18002b72e  jz      short loc_18002B743
0x18002b730  call    cs:__imp_CloseHandle
0x18002b737  nop     dword ptr [rax+rax+00h]
0x18002b73c  mov     qword ptr [rbx], 0
0x18002b743  add     rsp, 20h
0x18002b747  pop     rbx
0x18002b748  retn
```
