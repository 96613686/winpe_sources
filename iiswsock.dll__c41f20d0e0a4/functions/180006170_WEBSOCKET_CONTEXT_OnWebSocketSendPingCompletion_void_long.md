# WEBSOCKET_CONTEXT::OnWebSocketSendPingCompletion(void *,long)

- ea: `0x180006170`
- end: `0x1800061d7`
- name: `?OnWebSocketSendPingCompletion@WEBSOCKET_CONTEXT@@CAXPEAXJ@Z`
- size: `103`
- prototype: `void __fastcall(void *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006170`
- `0x180009010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18000619b`
- `iisutil!WriteRefTraceLog` at `0x18000619b`

## pseudocode

```c
void __fastcall WEBSOCKET_CONTEXT::OnWebSocketSendPingCompletion(volatile signed __int32 *a1)
{
  __int64 v2; // rcx

  _InterlockedCompareExchange(a1 + 94, 0, 1);
  v2 = *((_QWORD *)a1 + 54);
  if ( v2 )
    WriteRefTraceLog(v2, *((unsigned int *)a1 + 95), a1);
  if ( _InterlockedExchangeAdd(a1 + 95, 0xFFFFFFFF) == 1 && *((_DWORD *)a1 + 88) == 3 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 43) + 64LL))(*((_QWORD *)a1 + 43), 0);
}

```

## disassembly

```asm
0x180006170  push    rbx
0x180006172  sub     rsp, 20h
0x180006176  xor     edx, edx
0x180006178  mov     rbx, rcx
0x18000617b  lea     eax, [rdx+1]
0x18000617e  lock cmpxchg [rcx+178h], edx
0x180006186  mov     rcx, [rcx+1B0h]
0x18000618d  test    rcx, rcx
0x180006190  jz      short loc_1800061A1
0x180006192  mov     edx, [rbx+17Ch]
0x180006198  mov     r8, rbx
0x18000619b  call    cs:__imp_WriteRefTraceLog
0x1800061a1  or      eax, 0FFFFFFFFh
0x1800061a4  lock xadd [rbx+17Ch], eax
0x1800061ac  cmp     eax, 1
0x1800061af  jnz     short loc_1800061D1
0x1800061b1  mov     eax, [rbx+160h]
0x1800061b7  cmp     eax, 3
0x1800061ba  jnz     short loc_1800061D1
0x1800061bc  mov     rcx, [rbx+158h]
0x1800061c3  xor     edx, edx
0x1800061c5  mov     rax, [rcx]
0x1800061c8  mov     rax, [rax+40h]
0x1800061cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d1  add     rsp, 20h
0x1800061d5  pop     rbx
0x1800061d6  retn
```
