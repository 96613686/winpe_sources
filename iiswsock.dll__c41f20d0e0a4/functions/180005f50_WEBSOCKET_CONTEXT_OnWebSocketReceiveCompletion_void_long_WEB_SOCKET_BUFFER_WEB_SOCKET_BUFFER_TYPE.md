# WEBSOCKET_CONTEXT::OnWebSocketReceiveCompletion(void *,long,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE)

- ea: `0x180005f50`
- end: `0x180005fc3`
- name: `?OnWebSocketReceiveCompletion@WEBSOCKET_CONTEXT@@CAXPEAXJPEAT_WEB_SOCKET_BUFFER@@W4_WEB_SOCKET_BUFFER_TYPE@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005d88`
- `0x180005f50`
- `0x180009010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180005f87`
- `iisutil!WriteRefTraceLog` at `0x180005f87`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::OnWebSocketReceiveCompletion(__int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 352) == 3 )
  {
    v2 = *(_QWORD *)(a1 + 432);
  }
  else
  {
    WEBSOCKET_CONTEXT::DoReceiveComplete();
    v2 = *(_QWORD *)(a1 + 432);
  }
  if ( v2 )
    WriteRefTraceLog(v2, *(unsigned int *)(a1 + 380), a1);
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 380), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    result = *(unsigned int *)(a1 + 352);
    if ( (_DWORD)result == 3 )
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 344) + 64LL))(*(_QWORD *)(a1 + 344), 0);
  }
  return result;
}

```

## disassembly

```asm
0x180005f50  push    rbx
0x180005f52  sub     rsp, 20h
0x180005f56  mov     eax, [rcx+160h]
0x180005f5c  mov     rbx, rcx
0x180005f5f  cmp     eax, 3
0x180005f62  jnz     short loc_180005F6D
0x180005f64  mov     rcx, [rcx+1B0h]
0x180005f6b  jmp     short loc_180005F79
0x180005f6d  call    ?DoReceiveComplete@WEBSOCKET_CONTEXT@@AEAAXJPEAT_WEB_SOCKET_BUFFER@@W4_WEB_SOCKET_BUFFER_TYPE@@@Z; WEBSOCKET_CONTEXT::DoReceiveComplete(long,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE)
0x180005f72  mov     rcx, [rbx+1B0h]
0x180005f79  test    rcx, rcx
0x180005f7c  jz      short loc_180005F8D
0x180005f7e  mov     edx, [rbx+17Ch]
0x180005f84  mov     r8, rbx
0x180005f87  call    cs:__imp_WriteRefTraceLog
0x180005f8d  or      eax, 0FFFFFFFFh
0x180005f90  lock xadd [rbx+17Ch], eax
0x180005f98  cmp     eax, 1
0x180005f9b  jnz     short loc_180005FBD
0x180005f9d  mov     eax, [rbx+160h]
0x180005fa3  cmp     eax, 3
0x180005fa6  jnz     short loc_180005FBD
0x180005fa8  mov     rcx, [rbx+158h]
0x180005faf  xor     edx, edx
0x180005fb1  mov     rax, [rcx]
0x180005fb4  mov     rax, [rax+40h]
0x180005fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fbd  add     rsp, 20h
0x180005fc1  pop     rbx
0x180005fc2  retn
```
