# FindConverter

- ea: `0x18000250c`
- end: `0x18000257d`
- name: `FindConverter`
- size: `113`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e90`
- `0x1800031d0`
- `0x1800035d0`
- `0x180003850`
- `0x180003960`

## callees

- `0x18000250c`

## pseudocode

```c
__int64 *__fastcall FindConverter(int a1, int a2)
{
  int i; // r9d
  __int64 *v3; // r10

  for ( i = 0; ; ++i )
  {
    if ( i > giMaxConverters )
      return 0;
    v3 = &(*paicConverters)[6 * i];
    if ( *((_DWORD *)v3 + 4) == a1 && *((_DWORD *)v3 + 5) == a2 && !v3[4] )
      break;
  }
  if ( !(a1 + a2) && i < g_max_converters - 1 && i == giMaxConverters )
    ++giMaxConverters;
  return &(*paicConverters)[6 * i];
}

```

## disassembly

```asm
0x18000250c  mov     [rsp+arg_0], rbx
0x180002511  mov     r8d, cs:giMaxConverters
0x180002518  xor     r9d, r9d
0x18000251b  mov     rbx, cs:paicConverters
0x180002522  cmp     r9d, r8d
0x180002525  jg      short loc_180002575
0x180002527  movsxd  rax, r9d
0x18000252a  lea     r10, [rax+rax*2]
0x18000252e  shl     r10, 4
0x180002532  add     r10, rbx
0x180002535  cmp     [r10+10h], ecx
0x180002539  jnz     short loc_180002548
0x18000253b  cmp     [r10+14h], edx
0x18000253f  jnz     short loc_180002548
0x180002541  cmp     qword ptr [r10+20h], 0
0x180002546  jz      short loc_18000254D
0x180002548  inc     r9d
0x18000254b  jmp     short loc_180002522
0x18000254d  lea     eax, [rcx+rdx]
0x180002550  test    eax, eax
0x180002552  jnz     short loc_180002570
0x180002554  mov     ecx, cs:g_max_converters
0x18000255a  dec     ecx
0x18000255c  cmp     r9d, ecx
0x18000255f  jge     short loc_180002570
0x180002561  cmp     r9d, r8d
0x180002564  jnz     short loc_180002570
0x180002566  inc     r8d
0x180002569  mov     cs:giMaxConverters, r8d
0x180002570  mov     rax, r10
0x180002573  jmp     short loc_180002577
0x180002575  xor     eax, eax
0x180002577  mov     rbx, [rsp+arg_0]
0x18000257c  retn
```
