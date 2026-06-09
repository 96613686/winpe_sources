# StdEncoderFindMatch

- ea: `0x180002580`
- end: `0x1800026d5`
- name: `StdEncoderFindMatch`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, unsigned int *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c40`

## callees

- `0x180002580`

## pseudocode

```c
__int64 __fastcall StdEncoderFindMatch(__int64 a1, __int64 a2, int a3, int a4, unsigned int *a5, int a6, int a7)
{
  int v7; // edi
  int v10; // r15d
  int v11; // esi
  __int64 i; // r10
  unsigned int v14; // eax
  __int64 v16; // r8
  _BYTE *v17; // rdx

  v7 = 0;
  v10 = 0;
  v11 = a3 - 0x8000;
  for ( i = a1 + a3; a4 > v11; a4 = *(unsigned __int16 *)(a2 + 2LL * (a4 & 0x7FFF)) )
  {
    if ( *(_BYTE *)(v7 + i) == *(_BYTE *)(v7 + a4 + a1) )
    {
      v16 = 0;
      do
      {
        v17 = (_BYTE *)(a1 + (int)v16 + a4);
        if ( *(_BYTE *)(v16 + i) != *v17 )
          break;
        if ( *(_BYTE *)(v16 + i + 1) != v17[1] )
        {
          LODWORD(v16) = v16 + 1;
          break;
        }
        if ( *(_BYTE *)(v16 + i + 2) != v17[2] )
        {
          LODWORD(v16) = v16 + 2;
          break;
        }
        if ( *(_BYTE *)(v16 + i + 3) != v17[3] )
        {
          LODWORD(v16) = v16 + 3;
          break;
        }
        if ( *(_BYTE *)(v16 + i + 4) != v17[4] )
        {
          LODWORD(v16) = v16 + 4;
          break;
        }
        if ( *(_BYTE *)(v16 + i + 5) != v17[5] )
        {
          LODWORD(v16) = v16 + 5;
          break;
        }
        v16 = (unsigned int)(v16 + 6);
      }
      while ( (int)v16 < 258 );
      if ( (int)v16 > v7 )
      {
        v7 = v16;
        v10 = a4;
        if ( (int)v16 > a7 )
          break;
      }
    }
    if ( !--a6 )
      break;
  }
  v14 = a3 - v10 - 1;
  if ( v7 == 3 && v14 >= 0x1000 )
    return 0;
  *a5 = v14;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002580  push    rdi
0x180002582  sub     rsp, 10h
0x180002586  mov     [rsp+18h+arg_8], rbp
0x18000258b  xor     edi, edi
0x18000258d  mov     [rsp+18h+arg_10], rsi
0x180002592  mov     rbp, rdx
0x180002595  mov     [rsp+18h+var_10], r14
0x18000259a  mov     r11, rcx
0x18000259d  movsxd  r14, r8d
0x1800025a0  mov     [rsp+18h+var_18], r15
0x1800025a4  xor     r15d, r15d
0x1800025a7  lea     esi, [r14-8000h]
0x1800025ae  lea     r10, [rcx+r14]
0x1800025b2  cmp     r9d, esi
0x1800025b5  jle     short loc_1800025F1
0x1800025b7  mov     [rsp+18h+arg_0], rbx
0x1800025bc  mov     ebx, [rsp+18h+arg_28]
0x1800025c0  lea     eax, [rdi+r9]
0x1800025c4  movsxd  rcx, edi
0x1800025c7  cdqe
0x1800025c9  movzx   eax, byte ptr [rax+r11]
0x1800025ce  cmp     [rcx+r10], al
0x1800025d2  jz      short loc_180002623
0x1800025d4  sub     ebx, 1
0x1800025d7  jz      short loc_1800025EC
0x1800025d9  mov     eax, r9d
0x1800025dc  and     eax, 7FFFh
0x1800025e1  movzx   r9d, word ptr [rbp+rax*2+0]
0x1800025e7  cmp     r9d, esi
0x1800025ea  jg      short loc_1800025C0
0x1800025ec  mov     rbx, [rsp+18h+arg_0]
0x1800025f1  mov     rsi, [rsp+18h+arg_10]
0x1800025f6  sub     r14d, r15d
0x1800025f9  mov     r15, [rsp+18h+var_18]
0x1800025fd  mov     rbp, [rsp+18h+arg_8]
0x180002602  lea     eax, [r14-1]
0x180002606  mov     r14, [rsp+18h+var_10]
0x18000260b  cmp     edi, 3
0x18000260e  jz      loc_1800026C3
0x180002614  mov     rcx, [rsp+18h+arg_20]
0x180002619  mov     [rcx], eax
0x18000261b  mov     eax, edi
0x18000261d  add     rsp, 10h
0x180002621  pop     rdi
0x180002622  retn
0x180002623  xor     r8d, r8d
0x180002626  nop     word ptr [rax+rax+00000000h]
0x180002630  lea     eax, [r8+r9]
0x180002634  movsxd  rdx, eax
0x180002637  add     rdx, r11
0x18000263a  movzx   ecx, byte ptr [rdx]
0x18000263d  cmp     [r8+r10], cl
0x180002641  jnz     short loc_180002687
0x180002643  movzx   ecx, byte ptr [rdx+1]
0x180002647  cmp     [r8+r10+1], cl
0x18000264c  jnz     short loc_1800026B2
0x18000264e  movzx   ecx, byte ptr [rdx+2]
0x180002652  cmp     [r8+r10+2], cl
0x180002657  jnz     short loc_1800026AC
0x180002659  movzx   ecx, byte ptr [rdx+3]
0x18000265d  cmp     [r8+r10+3], cl
0x180002662  jnz     short loc_1800026A6
0x180002664  movzx   ecx, byte ptr [rdx+4]
0x180002668  cmp     [r8+r10+4], cl
0x18000266d  jnz     short loc_1800026BD
0x18000266f  movzx   ecx, byte ptr [rdx+5]
0x180002673  cmp     [r8+r10+5], cl
0x180002678  jnz     short loc_1800026B7
0x18000267a  add     r8d, 6
0x18000267e  cmp     r8d, 102h
0x180002685  jl      short loc_180002630
0x180002687  cmp     r8d, edi
0x18000268a  jle     loc_1800025D4
0x180002690  mov     edi, r8d
0x180002693  mov     r15d, r9d
0x180002696  cmp     r8d, [rsp+18h+arg_30]
0x18000269b  jg      loc_1800025EC
0x1800026a1  jmp     loc_1800025D4
0x1800026a6  add     r8d, 3
0x1800026aa  jmp     short loc_180002687
0x1800026ac  add     r8d, 2
0x1800026b0  jmp     short loc_180002687
0x1800026b2  inc     r8d
0x1800026b5  jmp     short loc_180002687
0x1800026b7  add     r8d, 5
0x1800026bb  jmp     short loc_180002687
0x1800026bd  add     r8d, 4
0x1800026c1  jmp     short loc_180002687
0x1800026c3  cmp     eax, 1000h
0x1800026c8  jb      loc_180002614
0x1800026ce  xor     eax, eax
0x1800026d0  jmp     loc_18000261D
```
