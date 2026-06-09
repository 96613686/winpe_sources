# COConnectionPoint::ListenersPresent(void)

- ea: `0x18000d180`
- end: `0x18000d1db`
- name: `?ListenersPresent@COConnectionPoint@@QEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a50`
- `0x180007c20`

## callees

- `0x18000d180`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d1c3`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d1c3`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d196`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d196`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::ListenersPresent(COConnectionPoint *this)
{
  unsigned int v2; // ebx

  CReaderWriterLock3::ReadLock((COConnectionPoint *)((char *)this + 8));
  if ( *((_DWORD *)this + 10) )
  {
    v2 = -2147418113;
  }
  else
  {
    v2 = 1;
    if ( *((_DWORD *)this + 11) )
      v2 = *((_DWORD *)this + 6) == 0;
  }
  CReaderWriterLock3::ReadUnlock((COConnectionPoint *)((char *)this + 8));
  return v2;
}

```

## disassembly

```asm
0x18000d180  mov     [rsp+arg_0], rbx
0x18000d185  mov     [rsp+arg_8], rsi
0x18000d18a  push    rdi
0x18000d18b  sub     rsp, 20h
0x18000d18f  mov     rdi, rcx
0x18000d192  add     rcx, 8
0x18000d196  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000d19c  mov     eax, [rdi+28h]
0x18000d19f  test    eax, eax
0x18000d1a1  jz      short loc_18000D1AA
0x18000d1a3  mov     ebx, 8000FFFFh
0x18000d1a8  jmp     short loc_18000D1BF
0x18000d1aa  cmp     dword ptr [rdi+2Ch], 0
0x18000d1ae  mov     ebx, 1
0x18000d1b3  jz      short loc_18000D1BF
0x18000d1b5  xor     edx, edx
0x18000d1b7  cmp     [rdi+18h], edx
0x18000d1ba  cmovz   edx, ebx
0x18000d1bd  mov     ebx, edx
0x18000d1bf  lea     rcx, [rdi+8]
0x18000d1c3  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000d1c9  mov     rsi, [rsp+28h+arg_8]
0x18000d1ce  mov     eax, ebx
0x18000d1d0  mov     rbx, [rsp+28h+arg_0]
0x18000d1d5  add     rsp, 20h
0x18000d1d9  pop     rdi
0x18000d1da  retn
```
