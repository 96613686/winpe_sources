# WEBSOCKET_CONTEXT::OnPostedCompletion(ulong,ulong,_OVERLAPPED *)

- ea: `0x180005ed0`
- end: `0x180005f3f`
- name: `?OnPostedCompletion@WEBSOCKET_CONTEXT@@CAXKKPEAU_OVERLAPPED@@@Z`
- size: `111`
- prototype: `void __fastcall(int, int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005ae8`
- `0x180005cb8`
- `0x180005ed0`
- `0x180009010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180005f03`
- `iisutil!WriteRefTraceLog` at `0x180005f03`

## pseudocode

```c
void __fastcall WEBSOCKET_CONTEXT::OnPostedCompletion(int a1, int a2, struct _OVERLAPPED *a3)
{
  PVOID Pointer; // rcx

  if ( a2 )
    WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest((WEBSOCKET_CONTEXT *)a3, a1);
  else
    WEBSOCKET_CONTEXT::CompleteApplicationReadRequest((WEBSOCKET_CONTEXT *)a3, a1);
  Pointer = a3[13].Pointer;
  if ( Pointer )
    WriteRefTraceLog(Pointer, HIDWORD(a3[11].hEvent), a3);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&a3[11].hEvent + 1, 0xFFFFFFFF) == 1
    && LODWORD(a3[11].Internal) == 3 )
  {
    (*(void (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)a3[10].hEvent + 64LL))(a3[10].hEvent, 0);
  }
}

```

## disassembly

```asm
0x180005ed0  push    rbx
0x180005ed2  sub     rsp, 20h
0x180005ed6  mov     rbx, r8
0x180005ed9  test    edx, edx
0x180005edb  mov     edx, ecx; int
0x180005edd  mov     rcx, rbx; this
0x180005ee0  jnz     short loc_180005EE9
0x180005ee2  call    ?CompleteApplicationReadRequest@WEBSOCKET_CONTEXT@@AEAAJJ@Z; WEBSOCKET_CONTEXT::CompleteApplicationReadRequest(long)
0x180005ee7  jmp     short loc_180005EEE
0x180005ee9  call    ?CompleteApplicationWriteRequest@WEBSOCKET_CONTEXT@@AEAAJJ@Z; WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest(long)
0x180005eee  mov     rcx, [rbx+1B0h]
0x180005ef5  test    rcx, rcx
0x180005ef8  jz      short loc_180005F09
0x180005efa  mov     edx, [rbx+17Ch]
0x180005f00  mov     r8, rbx
0x180005f03  call    cs:__imp_WriteRefTraceLog
0x180005f09  or      eax, 0FFFFFFFFh
0x180005f0c  lock xadd [rbx+17Ch], eax
0x180005f14  cmp     eax, 1
0x180005f17  jnz     short loc_180005F39
0x180005f19  mov     eax, [rbx+160h]
0x180005f1f  cmp     eax, 3
0x180005f22  jnz     short loc_180005F39
0x180005f24  mov     rcx, [rbx+158h]
0x180005f2b  xor     edx, edx
0x180005f2d  mov     rax, [rcx]
0x180005f30  mov     rax, [rax+40h]
0x180005f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f39  add     rsp, 20h
0x180005f3d  pop     rbx
0x180005f3e  retn
```
