# DereferenceRefCount

- ea: `0x1400035f0`
- end: `0x140003613`
- name: `DereferenceRefCount`
- size: `35`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140001be0`
- `0x140002e40`
- `0x140003190`
- `0x140003550`
- `0x140007364`
- `0x140008e5c`
- `0x140011540`
- `0x140013b68`
- `0x1400254c8`
- `0x140025830`
- `0x140027a50`
- `0x14002f620`
- `0x140030014`

## callees

- `0x1400035f0`
- `0x140016230`

## pseudocode

```c
__int64 __fastcall DereferenceRefCount(__int64 a1)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return (*(__int64 (**)(void))(a1 + 8))();
  return result;
}

```

## disassembly

```asm
0x1400035f0  sub     rsp, 28h
0x1400035f4  mov     eax, 0FFFFFFFFh
0x1400035f9  lock xadd [rcx], eax
0x1400035fd  cmp     eax, 1
0x140003600  jz      short loc_140003608
0x140003602  add     rsp, 28h
0x140003606  retn
0x140003608  mov     rax, [rcx+8]
0x14000360c  call    _guard_dispatch_icall
0x140003611  jmp     short loc_140003602
```
