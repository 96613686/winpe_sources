# DecompressFrame16To555C

- ea: `0x1800054f0`
- end: `0x1800055db`
- name: `DecompressFrame16To555C`
- size: `235`
- prototype: `__int64 __fastcall(_DWORD *, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800037e0`
- `0x1800054f0`
- `0x180005d98`

## pseudocode

```c
__int64 __fastcall DecompressFrame16To555C(_DWORD *a1, int a2, int a3, int a4, int a5, int a6)
{
  unsigned int v6; // r15d
  unsigned int v7; // r12d
  signed int v9; // r15d
  signed int v10; // r12d
  int v11; // ebp
  int v12; // ebx
  int v13; // r14d
  int v14; // esi
  int v15; // edi
  int v16; // eax
  int v18; // [rsp+30h] [rbp-48h] BYREF
  int v19; // [rsp+80h] [rbp+8h] BYREF
  int v20; // [rsp+88h] [rbp+10h] BYREF

  v6 = a1[1];
  v7 = a1[2];
  v18 = a1[5];
  v20 = 0;
  v19 = 0;
  v9 = v6 >> 2;
  v10 = v7 >> 2;
  v11 = 0;
  v12 = DibXY(a3, a4, a5, a6, (__int64)&v19);
  if ( v10 )
  {
    v13 = v19;
    do
    {
      v14 = 0;
      v15 = v12;
      if ( v9 )
      {
        do
        {
          v16 = DecompressCBlock16To555(v15, a2, (unsigned int)&v18, v13, (__int64)&v20);
          ++v14;
          v15 += 8;
          a2 = v16;
        }
        while ( v14 < v9 );
      }
      ++v11;
      v12 += 4 * v13;
    }
    while ( v11 < v10 );
  }
  return 0;
}

```

## disassembly

```asm
0x1800054f0  mov     [rsp+arg_10], rbx
0x1800054f5  push    rbp
0x1800054f6  push    rsi
0x1800054f7  push    rdi
0x1800054f8  push    r12
0x1800054fa  push    r13
0x1800054fc  push    r14
0x1800054fe  push    r15
0x180005500  sub     rsp, 40h
0x180005504  mov     eax, [rcx+14h]
0x180005507  mov     r11, r8
0x18000550a  mov     r15d, [rcx+4]
0x18000550e  mov     r10, r9
0x180005511  mov     r12d, [rcx+8]
0x180005515  mov     r13, rdx
0x180005518  mov     r8d, [rsp+78h+arg_20]
0x180005520  mov     rdx, r10
0x180005523  mov     r9d, [rsp+78h+arg_28]
0x18000552b  mov     rcx, r11
0x18000552e  mov     [rsp+78h+var_48], eax
0x180005532  lea     rax, [rsp+78h+arg_0]
0x18000553a  mov     [rsp+78h+var_58], rax
0x18000553f  mov     [rsp+78h+arg_8], 0
0x18000554a  mov     [rsp+78h+arg_0], 0
0x180005555  shr     r15d, 2
0x180005559  shr     r12d, 2
0x18000555d  call    DibXY
0x180005562  xor     ebp, ebp
0x180005564  mov     rbx, rax
0x180005567  test    r12d, r12d
0x18000556a  jz      short loc_1800055C1
0x18000556c  mov     r14d, [rsp+78h+arg_0]
0x180005574  xor     esi, esi
0x180005576  mov     rdi, rbx
0x180005579  test    r15d, r15d
0x18000557c  jz      short loc_1800055AC
0x18000557e  lea     rax, [rsp+78h+arg_8]
0x180005586  mov     r9d, r14d
0x180005589  lea     r8, [rsp+78h+var_48]
0x18000558e  mov     [rsp+78h+var_58], rax
0x180005593  mov     rdx, r13
0x180005596  mov     rcx, rdi
0x180005599  call    DecompressCBlock16To555
0x18000559e  inc     esi
0x1800055a0  add     rdi, 8
0x1800055a4  mov     r13, rax
0x1800055a7  cmp     esi, r15d
0x1800055aa  jl      short loc_18000557E
0x1800055ac  lea     eax, ds:0[r14*4]
0x1800055b4  inc     ebp
0x1800055b6  movsxd  rcx, eax
0x1800055b9  add     rbx, rcx
0x1800055bc  cmp     ebp, r12d
0x1800055bf  jl      short loc_180005574
0x1800055c1  mov     rbx, [rsp+78h+arg_10]
0x1800055c9  xor     eax, eax
0x1800055cb  add     rsp, 40h
0x1800055cf  pop     r15
0x1800055d1  pop     r14
0x1800055d3  pop     r13
0x1800055d5  pop     r12
0x1800055d7  pop     rdi
0x1800055d8  pop     rsi
0x1800055d9  pop     rbp
0x1800055da  retn
```
