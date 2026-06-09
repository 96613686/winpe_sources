# FwIcfAuthorizedAppCompare

- ea: `0x18002a71c`
- end: `0x18002a75c`
- name: `FwIcfAuthorizedAppCompare`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002b334`
- `0x18002bde0`

## callees

- `0x180013440`
- `0x18002a71c`

## pseudocode

```c
__int64 __fastcall FwIcfAuthorizedAppCompare(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = FwWcsICmp(*(_QWORD *)(a1 + 16), *(_QWORD *)(a2 + 16));
  if ( !(_DWORD)result && !*(_QWORD *)(a1 + 16) )
    return FwWcsICmp(*(_QWORD *)(a1 + 8), *(_QWORD *)(a2 + 8));
  return result;
}

```

## disassembly

```asm
0x18002a71c  mov     [rsp+arg_0], rbx
0x18002a721  push    rdi
0x18002a722  sub     rsp, 20h
0x18002a726  mov     rdi, rdx
0x18002a729  mov     rbx, rcx
0x18002a72c  mov     rdx, [rdx+10h]
0x18002a730  mov     rcx, [rcx+10h]
0x18002a734  call    FwWcsICmp
0x18002a739  test    eax, eax
0x18002a73b  jnz     short loc_18002A751
0x18002a73d  cmp     qword ptr [rbx+10h], 0
0x18002a742  jnz     short loc_18002A751
0x18002a744  mov     rdx, [rdi+8]
0x18002a748  mov     rcx, [rbx+8]
0x18002a74c  call    FwWcsICmp
0x18002a751  mov     rbx, [rsp+28h+arg_0]
0x18002a756  add     rsp, 20h
0x18002a75a  pop     rdi
0x18002a75b  retn
```
