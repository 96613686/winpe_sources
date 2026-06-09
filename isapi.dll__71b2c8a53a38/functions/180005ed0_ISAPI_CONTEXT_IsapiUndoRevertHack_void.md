# ISAPI_CONTEXT::IsapiUndoRevertHack(void * *)

- ea: `0x180005ed0`
- end: `0x180005eff`
- name: `?IsapiUndoRevertHack@ISAPI_CONTEXT@@QEAAXPEAPEAX@Z`
- size: `47`
- prototype: `void __fastcall(ISAPI_CONTEXT *__hidden this, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034c0`
- `0x180003bc0`
- `0x180003ef0`
- `0x180004b70`

## callees

- `0x180005ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005ee3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005eec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005eec`

## pseudocode

```c
void __fastcall ISAPI_CONTEXT::IsapiUndoRevertHack(ISAPI_CONTEXT *this, void **a2)
{
  HANDLE v3; // rdx

  v3 = *a2;
  if ( v3 )
  {
    SetThreadToken(0, v3);
    CloseHandle(*a2);
  }
  *a2 = 0;
}

```

## disassembly

```asm
0x180005ed0  push    rbx
0x180005ed2  sub     rsp, 20h
0x180005ed6  mov     rbx, rdx
0x180005ed9  mov     rdx, [rdx]; Token
0x180005edc  test    rdx, rdx
0x180005edf  jz      short loc_180005EF2
0x180005ee1  xor     ecx, ecx; Thread
0x180005ee3  call    cs:__imp_SetThreadToken
0x180005ee9  mov     rcx, [rbx]; hObject
0x180005eec  call    cs:__imp_CloseHandle
0x180005ef2  mov     qword ptr [rbx], 0
0x180005ef9  add     rsp, 20h
0x180005efd  pop     rbx
0x180005efe  retn
```
