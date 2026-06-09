# GetAppPoolSid(ushort const *,void * *)

- ea: `0x180008e54`
- end: `0x180008ea8`
- name: `?GetAppPoolSid@@YAJPEBGPEAPEAX@Z`
- size: `84`
- prototype: `int(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180004180`

## callees

- `0x1800054a0`
- `0x180008c90`
- `0x180008e54`
- `0x180008eb0`

## pseudocode

```c
__int64 __fastcall GetAppPoolSid(const unsigned __int16 *a1, void **a2)
{
  int SIDFromHash; // ebx
  void *Block; // [rsp+40h] [rbp+18h] BYREF

  Block = 0;
  SIDFromHash = CalculateAppPoolHash(a1, (struct APP_POOL_HASH **)&Block);
  if ( SIDFromHash >= 0 )
    SIDFromHash = MakeSIDFromHash((ULONG *)Block, a2);
  if ( Block )
    operator delete(Block);
  return (unsigned int)SIDFromHash;
}

```

## disassembly

```asm
0x180008e54  mov     [rsp+arg_0], rbx
0x180008e59  push    rsi
0x180008e5a  sub     rsp, 20h
0x180008e5e  mov     rsi, rdx
0x180008e61  mov     [rsp+28h+Block], 0
0x180008e6a  lea     rdx, [rsp+28h+Block]; struct APP_POOL_HASH **
0x180008e6f  call    ?CalculateAppPoolHash@@YAJPEBGPEAPEAUAPP_POOL_HASH@@@Z; CalculateAppPoolHash(ushort const *,APP_POOL_HASH * *)
0x180008e74  mov     ebx, eax
0x180008e76  test    eax, eax
0x180008e78  js      short loc_180008E89
0x180008e7a  mov     rcx, [rsp+28h+Block]; struct APP_POOL_HASH *
0x180008e7f  mov     rdx, rsi; void **
0x180008e82  call    ?MakeSIDFromHash@@YAJPEAUAPP_POOL_HASH@@PEAPEAX@Z; MakeSIDFromHash(APP_POOL_HASH *,void * *)
0x180008e87  mov     ebx, eax
0x180008e89  cmp     [rsp+28h+Block], 0
0x180008e8f  jz      short loc_180008E9B
0x180008e91  mov     rcx, [rsp+28h+Block]; Block
0x180008e96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008e9b  mov     eax, ebx
0x180008e9d  mov     rbx, [rsp+28h+arg_0]
0x180008ea2  add     rsp, 20h
0x180008ea6  pop     rsi
0x180008ea7  retn
```
