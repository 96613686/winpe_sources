# DereferenceRefCount

- ea: `0x140001a70`
- end: `0x140001a93`
- name: `DereferenceRefCount`
- size: `35`
- prototype: ``
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x140002e78`
- `0x140003aa8`
- `0x140005730`
- `0x1400059b0`
- `0x140005bf0`
- `0x140005ee0`
- `0x14000f344`
- `0x14000f588`
- `0x14000fbac`
- `0x1400102fc`
- `0x140010974`
- `0x140010aa4`
- `0x140010e00`
- `0x140010ef0`
- `0x140010f80`
- `0x140011050`
- `0x140011790`
- `0x140011838`
- `0x1400122b0`
- `0x1400133d0`
- `0x140013954`
- `0x140015a40`
- `0x140016180`
- `0x1400162f0`
- `0x140016980`
- `0x140017650`
- `0x140018550`
- `0x140018890`

## callees

- `0x140001a70`
- `0x140007710`

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
0x140001a70  sub     rsp, 28h
0x140001a74  mov     eax, 0FFFFFFFFh
0x140001a79  lock xadd [rcx], eax
0x140001a7d  cmp     eax, 1
0x140001a80  jz      short loc_140001A88
0x140001a82  add     rsp, 28h
0x140001a86  retn
0x140001a88  mov     rax, [rcx+8]
0x140001a8c  call    _guard_dispatch_icall
0x140001a91  jmp     short loc_140001A82
```
