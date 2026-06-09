# GetVarLen

- ea: `0x180003f68`
- end: `0x180003fd5`
- name: `GetVarLen`
- size: `109`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003dc0`
- `0x180003fdc`
- `0x180004588`

## callees

- `0x180003f68`
- `0x1800058bc`

## pseudocode

```c
__int64 __fastcall GetVarLen(__int64 a1)
{
  char v2; // al
  unsigned int v3; // ebx
  int v4; // esi
  char v5; // al

  v2 = LookByte(a1);
  if ( !*(_DWORD *)a1 )
    ++*(_QWORD *)(a1 + 24);
  v3 = (unsigned __int8)v2;
  if ( v2 < 0 )
  {
    v4 = 1;
    v3 = v2 & 0x7F;
    do
    {
      v5 = LookByte(a1);
      if ( !*(_DWORD *)a1 )
        ++*(_QWORD *)(a1 + 24);
      ++v4;
      v3 = (v5 & 0x7F) + (v3 << 7);
    }
    while ( v5 < 0 );
    if ( v4 > 4 )
      return 0x7FFFFFFF;
  }
  return v3;
}

```

## disassembly

```asm
0x180003f68  mov     [rsp+arg_0], rbx
0x180003f6d  mov     [rsp+arg_8], rsi
0x180003f72  push    rdi
0x180003f73  sub     rsp, 20h
0x180003f77  mov     rdi, rcx
0x180003f7a  call    LookByte
0x180003f7f  cmp     dword ptr [rdi], 0
0x180003f82  jnz     short loc_180003F88
0x180003f84  inc     qword ptr [rdi+18h]
0x180003f88  movzx   ebx, al
0x180003f8b  test    al, al
0x180003f8d  jns     short loc_180003FC3
0x180003f8f  mov     esi, 1
0x180003f94  and     ebx, 7Fh
0x180003f97  mov     rcx, rdi
0x180003f9a  call    LookByte
0x180003f9f  cmp     dword ptr [rdi], 0
0x180003fa2  jnz     short loc_180003FA8
0x180003fa4  inc     qword ptr [rdi+18h]
0x180003fa8  shl     ebx, 7
0x180003fab  inc     esi
0x180003fad  movzx   edx, al
0x180003fb0  and     edx, 7Fh
0x180003fb3  add     ebx, edx
0x180003fb5  test    al, al
0x180003fb7  js      short loc_180003F97
0x180003fb9  cmp     esi, 4
0x180003fbc  jle     short loc_180003FC3
0x180003fbe  mov     ebx, 7FFFFFFFh
0x180003fc3  mov     rsi, [rsp+28h+arg_8]
0x180003fc8  mov     eax, ebx
0x180003fca  mov     rbx, [rsp+28h+arg_0]
0x180003fcf  add     rsp, 20h
0x180003fd3  pop     rdi
0x180003fd4  retn
```
