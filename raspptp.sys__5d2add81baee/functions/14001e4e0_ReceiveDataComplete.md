# ReceiveDataComplete

- ea: `0x14001e4e0`
- end: `0x14001e52e`
- name: `ReceiveDataComplete`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010974`
- `0x140012f60`
- `0x140016db0`
- `0x140018190`

## callees

- `0x140007710`
- `0x14001e4e0`

## import_xrefs

- `NDIS!NdisFreeNetBufferList` at `0x14001e50f`
- `NDIS!NdisFreeNetBufferList` at `0x14001e50f`

## pseudocode

```c
void __fastcall ReceiveDataComplete(__int64 a1, struct _NET_BUFFER_LIST *a2)
{
  if ( a2 )
    NdisFreeNetBufferList(a2);
  if ( a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 512), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a1 + 520))(a1);
  }
}

```

## disassembly

```asm
0x14001e4e0  push    rbx
0x14001e4e2  sub     rsp, 20h
0x14001e4e6  mov     rbx, rcx
0x14001e4e9  test    rdx, rdx
0x14001e4ec  jnz     short loc_14001E50C
0x14001e4ee  test    rbx, rbx
0x14001e4f1  jz      short loc_14001E505
0x14001e4f3  mov     eax, 0FFFFFFFFh
0x14001e4f8  lock xadd [rbx+200h], eax
0x14001e500  cmp     eax, 1
0x14001e503  jz      short loc_14001E51D
0x14001e505  add     rsp, 20h
0x14001e509  pop     rbx
0x14001e50a  retn
0x14001e50c  mov     rcx, rdx; NetBufferList
0x14001e50f  call    cs:__imp_NdisFreeNetBufferList
0x14001e516  nop     dword ptr [rax+rax+00h]
0x14001e51b  jmp     short loc_14001E4EE
0x14001e51d  mov     rax, [rbx+208h]
0x14001e524  mov     rcx, rbx
0x14001e527  call    _guard_dispatch_icall
0x14001e52c  jmp     short loc_14001E505
```
