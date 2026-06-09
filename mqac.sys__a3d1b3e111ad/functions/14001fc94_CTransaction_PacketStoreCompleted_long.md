# CTransaction::PacketStoreCompleted(long)

- ea: `0x14001fc94`
- end: `0x14001fcc0`
- name: `?PacketStoreCompleted@CTransaction@@QEAAXJ@Z`
- size: `44`
- prototype: `void __fastcall(CTransaction *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400177c4`

## callees

- `0x140019cfc`
- `0x14001fc94`

## pseudocode

```c
void __fastcall CTransaction::PacketStoreCompleted(CTransaction *this, int a2)
{
  int *v3; // rdx

  v3 = (int *)((char *)this + 132);
  if ( a2 < 0 )
    *v3 = a2;
  if ( (*((_DWORD *)this + 32))-- == 1 )
    CQueueBase::CancelTaggedRequest(this, *v3, 0);
}

```

## disassembly

```asm
0x14001fc94  sub     rsp, 28h
0x14001fc98  mov     eax, edx
0x14001fc9a  lea     rdx, [rcx+84h]
0x14001fca1  test    eax, eax
0x14001fca3  jns     short loc_14001FCA7
0x14001fca5  mov     [rdx], eax
0x14001fca7  add     dword ptr [rcx+80h], 0FFFFFFFFh
0x14001fcae  jnz     short loc_14001FCBA
0x14001fcb0  mov     edx, [rdx]; int
0x14001fcb2  xor     r8d, r8d; unsigned int
0x14001fcb5  call    ?CancelTaggedRequest@CQueueBase@@QEAAJJK@Z; CQueueBase::CancelTaggedRequest(long,ulong)
0x14001fcba  add     rsp, 28h
0x14001fcbe  retn
```
