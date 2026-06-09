# CThreadContext::RevertToPreviousToken(void)

- ea: `0x18000a804`
- end: `0x18000a841`
- name: `?RevertToPreviousToken@CThreadContext@@QEAAXXZ`
- size: `61`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a7c4`

## callees

- `0x18000a804`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a818`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a827`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a827`

## pseudocode

```c
void __fastcall CThreadContext::RevertToPreviousToken(HANDLE *this)
{
  HANDLE v2; // rcx

  if ( *(_DWORD *)this )
  {
    SetThreadToken(0, this[1]);
    v2 = this[1];
    if ( v2 )
    {
      CloseHandle(v2);
      this[1] = 0;
    }
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000a804  push    rbx
0x18000a806  sub     rsp, 20h
0x18000a80a  cmp     dword ptr [rcx], 0
0x18000a80d  mov     rbx, rcx
0x18000a810  jz      short loc_18000A83B
0x18000a812  mov     rdx, [rcx+8]; Token
0x18000a816  xor     ecx, ecx; Thread
0x18000a818  call    cs:__imp_SetThreadToken
0x18000a81e  mov     rcx, [rbx+8]; hObject
0x18000a822  test    rcx, rcx
0x18000a825  jz      short loc_18000A835
0x18000a827  call    cs:__imp_CloseHandle
0x18000a82d  mov     qword ptr [rbx+8], 0
0x18000a835  mov     dword ptr [rbx], 0
0x18000a83b  add     rsp, 20h
0x18000a83f  pop     rbx
0x18000a840  retn
```
