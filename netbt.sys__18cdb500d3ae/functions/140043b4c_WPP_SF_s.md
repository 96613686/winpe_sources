# WPP_SF_s

- ea: `0x140043b4c`
- end: `0x140043b9a`
- name: `WPP_SF_s`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dd3c`
- `0x140017a3c`
- `0x14001ba80`
- `0x14002571c`
- `0x14002c018`
- `0x1400447ac`
- `0x14004b48c`
- `0x14004da30`
- `0x14004dc90`

## callees

- `0x140030bc8`
- `0x140043b4c`

## pseudocode

```c
void __fastcall WPP_SF_s(__int16 a1, USHORT a2, ULONGLONG a3, const char *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  FastWppTraceMessage(a1, a2, a3, a4, v5, 0);
}

```

## disassembly

```asm
0x140043b4c  sub     rsp, 38h
0x140043b50  test    r9, r9
0x140043b53  jz      short loc_140043B68
0x140043b55  or      rax, 0FFFFFFFFFFFFFFFFh
0x140043b59  inc     rax
0x140043b5c  cmp     byte ptr [r9+rax], 0
0x140043b61  jnz     short loc_140043B59
0x140043b63  inc     rax
0x140043b66  jmp     short loc_140043B6D
0x140043b68  mov     eax, 5
0x140043b6d  test    r9, r9
0x140043b70  mov     [rsp+38h+var_10], 0
0x140043b79  lea     r10, aNull; "NULL"
0x140043b80  movzx   edx, dx
0x140043b83  cmovz   r9, r10
0x140043b87  movzx   ecx, cx
0x140043b8a  mov     [rsp+38h+var_18], rax
0x140043b8f  call    FastWppTraceMessage
0x140043b94  add     rsp, 38h
0x140043b98  retn
```
