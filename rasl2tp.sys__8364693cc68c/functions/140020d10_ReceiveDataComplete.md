# ReceiveDataComplete

- ea: `0x140020d10`
- end: `0x140020d3f`
- name: `ReceiveDataComplete`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140019a80`

## callees

- `0x140004830`
- `0x140020d10`

## pseudocode

```c
__int64 __fastcall ReceiveDataComplete(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 512), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      return (*(__int64 (**)(void))(a1 + 520))();
  }
  return result;
}

```

## disassembly

```asm
0x140020d10  sub     rsp, 28h
0x140020d14  test    rcx, rcx
0x140020d17  jz      short loc_140020D2B
0x140020d19  mov     eax, 0FFFFFFFFh
0x140020d1e  lock xadd [rcx+200h], eax
0x140020d26  cmp     eax, 1
0x140020d29  jz      short loc_140020D31
0x140020d2b  add     rsp, 28h
0x140020d2f  retn
0x140020d31  mov     rax, [rcx+208h]
0x140020d38  call    _guard_dispatch_icall
0x140020d3d  jmp     short loc_140020D2B
```
