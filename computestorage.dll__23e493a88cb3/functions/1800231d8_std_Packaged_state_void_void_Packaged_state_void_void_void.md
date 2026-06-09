# std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(void)

- ea: `0x1800231d8`
- end: `0x180023255`
- name: `??1?$_Packaged_state@$$A6AXXZ@std@@UEAA@XZ`
- size: `125`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800232b4`
- `0x180024050`
- `0x180044487`

## callees

- `0x1800231d8`
- `0x180049010`

## import_xrefs

- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18002322f`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x18002322f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023249`

## pseudocode

```c
void __fastcall std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rcx
  bool v5; // zf

  v2 = a1 + 208;
  v4 = *(_QWORD *)(a1 + 264);
  if ( v4 )
  {
    LOBYTE(a2) = v4 != v2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *(_QWORD *)(v2 + 56) = 0;
  }
  v5 = *(_BYTE *)(a1 + 193) == 0;
  *(_QWORD *)a1 = &std::_Associated_state<int>::`vftable';
  if ( !v5 && !*(_DWORD *)(a1 + 188) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 32));
  __ExceptionPtrDestroy((void *)(a1 + 16));
}

```

## disassembly

```asm
0x1800231d8  mov     [rsp+arg_0], rbx
0x1800231dd  push    rdi
0x1800231de  sub     rsp, 20h
0x1800231e2  lea     rdi, [rcx+0D0h]
0x1800231e9  mov     rbx, rcx
0x1800231ec  mov     rcx, [rdi+38h]
0x1800231f0  test    rcx, rcx
0x1800231f3  jz      short loc_18002320F
0x1800231f5  mov     rax, [rcx]
0x1800231f8  cmp     rcx, rdi
0x1800231fb  setnz   dl
0x1800231fe  mov     rax, [rax+20h]
0x180023202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023207  mov     qword ptr [rdi+38h], 0
0x18002320f  cmp     byte ptr [rbx+0C1h], 0
0x180023216  lea     rax, ??_7?$_Associated_state@H@std@@6B@; const std::_Associated_state<int>::`vftable'
0x18002321d  mov     [rbx], rax
0x180023220  jz      short loc_18002323B
0x180023222  cmp     dword ptr [rbx+0BCh], 0
0x180023229  jnz     short loc_18002323B
0x18002322b  lea     rcx, [rbx+20h]; _Mtx_t
0x18002322f  call    cs:__imp__Cnd_unregister_at_thread_exit
0x180023236  nop     dword ptr [rax+rax+00h]
0x18002323b  lea     rcx, [rbx+10h]
0x18002323f  mov     rbx, [rsp+28h+arg_0]
0x180023244  add     rsp, 20h
0x180023248  pop     rdi
0x180023249  jmp     cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
```
