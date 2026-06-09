# SkipBytes

- ea: `0x180004fa4`
- end: `0x180004ff2`
- name: `SkipBytes`
- size: `78`
- prototype: `char __fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003fdc`
- `0x180004588`
- `0x180005a1c`

## callees

- `0x180004fa4`
- `0x1800058bc`

## pseudocode

```c
char __fastcall SkipBytes(__int64 a1, int a2)
{
  int i; // esi
  char result; // al

  for ( i = 0; i < a2; ++i )
  {
    result = LookByte(a1);
    if ( *(_DWORD *)a1 )
    {
      if ( !*(_DWORD *)(a1 + 56) )
        break;
    }
    else
    {
      ++*(_QWORD *)(a1 + 24);
    }
  }
  *(_DWORD *)(a1 + 80) = a2 - i;
  return result;
}

```

## disassembly

```asm
0x180004fa4  mov     [rsp+arg_0], rbx
0x180004fa9  mov     [rsp+arg_8], rsi
0x180004fae  push    rdi
0x180004faf  sub     rsp, 20h
0x180004fb3  xor     esi, esi
0x180004fb5  mov     edi, edx
0x180004fb7  mov     rbx, rcx
0x180004fba  test    edx, edx
0x180004fbc  jle     short loc_180004FDD
0x180004fbe  mov     rcx, rbx
0x180004fc1  call    LookByte
0x180004fc6  cmp     dword ptr [rbx], 0
0x180004fc9  jnz     short loc_180004FD1
0x180004fcb  inc     qword ptr [rbx+18h]
0x180004fcf  jmp     short loc_180004FD7
0x180004fd1  cmp     dword ptr [rbx+38h], 0
0x180004fd5  jz      short loc_180004FDD
0x180004fd7  inc     esi
0x180004fd9  cmp     esi, edi
0x180004fdb  jl      short loc_180004FBE
0x180004fdd  sub     edi, esi
0x180004fdf  mov     rsi, [rsp+28h+arg_8]
0x180004fe4  mov     [rbx+50h], edi
0x180004fe7  mov     rbx, [rsp+28h+arg_0]
0x180004fec  add     rsp, 20h
0x180004ff0  pop     rdi
0x180004ff1  retn
```
