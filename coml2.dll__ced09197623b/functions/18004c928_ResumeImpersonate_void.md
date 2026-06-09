# ResumeImpersonate(void *)

- ea: `0x18004c928`
- end: `0x18004c94f`
- name: `?ResumeImpersonate@@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800369a0`

## callees

- `0x18004c928`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c943`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004c93a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004c93a`

## pseudocode

```c
void __fastcall ResumeImpersonate(HANDLE hObject)
{
  if ( hObject )
  {
    SetThreadToken(0, hObject);
    CloseHandle(hObject);
  }
}

```

## disassembly

```asm
0x18004c928  test    rcx, rcx
0x18004c92b  jz      short locret_18004C94E
0x18004c92d  push    rbx
0x18004c92e  sub     rsp, 20h
0x18004c932  mov     rbx, rcx
0x18004c935  mov     rdx, rcx; Token
0x18004c938  xor     ecx, ecx; Thread
0x18004c93a  call    cs:__imp_SetThreadToken
0x18004c940  mov     rcx, rbx; hObject
0x18004c943  call    cs:__imp_CloseHandle
0x18004c949  add     rsp, 20h
0x18004c94d  pop     rbx
0x18004c94e  retn
```
