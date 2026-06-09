# DereferenceRefCount

- ea: `0x140002030`
- end: `0x140002053`
- name: `DereferenceRefCount`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `37`
- callee_count: `2`
- tags: ``

## callers

- `0x1400018b0`
- `0x140002700`
- `0x140003b58`
- `0x140003fc0`
- `0x140005110`
- `0x140010720`
- `0x140010820`
- `0x140010900`
- `0x140010988`
- `0x140010c58`
- `0x140010fd4`
- `0x140011500`
- `0x140011b00`
- `0x1400121b0`
- `0x140012290`
- `0x140012de0`
- `0x140013150`
- `0x1400133f0`
- `0x140013ad0`
- `0x140013eb0`
- `0x140014150`
- `0x140014220`
- `0x1400142f0`
- `0x1400148f0`
- `0x1400149c0`
- `0x140014a90`
- `0x140014b60`
- `0x140014c30`
- `0x140014d00`
- `0x1400150e0`
- `0x1400155b0`
- `0x140015e70`
- `0x1400168d0`
- `0x140016cf0`
- `0x1400174f0`
- `0x140017550`
- `0x140019ae0`

## callees

- `0x140002030`
- `0x140005ef0`

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
0x140002030  sub     rsp, 28h
0x140002034  mov     eax, 0FFFFFFFFh
0x140002039  lock xadd [rcx], eax
0x14000203d  cmp     eax, 1
0x140002040  jz      short loc_140002048
0x140002042  add     rsp, 28h
0x140002046  retn
0x140002048  mov     rax, [rcx+8]
0x14000204c  call    _guard_dispatch_icall
0x140002051  jmp     short loc_140002042
```
