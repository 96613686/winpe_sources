# DownSampling(uchar const *,uchar const *,uchar *,uchar *,long,long,long,long,long,long,long,long)

- ea: `0x180002da4`
- end: `0x180002ecf`
- name: `?DownSampling@@YAXPEBE0PEAE1JJJJJJJJ@Z`
- size: `299`
- prototype: `void __fastcall(const unsigned __int8 *, const unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int, int, int, int, int, int, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a10`
- `0x18001de30`
- `0x18001f120`

## callees

- `0x180002da4`

## pseudocode

```c
void __fastcall DownSampling(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  __int64 v10; // rbx
  int v11; // r15d
  unsigned __int8 *v12; // r11
  int v13; // ebp
  unsigned __int8 *v14; // r10
  const unsigned __int8 *v15; // rsi
  const unsigned __int8 *v16; // r14
  __int64 v17; // r12
  const unsigned __int8 *v18; // r13
  int v19; // r15d
  const unsigned __int8 *v20; // rbx
  unsigned __int8 *v21; // r12
  unsigned __int8 *v22; // rbp
  int v23; // ecx
  int v24; // edx
  int v25; // edx
  int v26; // ecx
  int i; // ecx
  int v28; // [rsp+68h] [rbp+38h]

  v10 = a5;
  v11 = 0;
  v12 = a2;
  v13 = a10 >> 1;
  v14 = a1;
  v28 = 0;
  v15 = &a1[a5];
  v16 = &a2[a5];
  if ( a10 >> 1 > 0 )
  {
    v17 = a6;
    do
    {
      v18 = v15;
      if ( a9 > 0 )
      {
        v19 = 0;
        v20 = v16;
        v21 = a3;
        v22 = a4;
        do
        {
          v23 = *v18;
          ++v19;
          v24 = *v14;
          v18 += 4;
          v14 += 4;
          *v21++ = (unsigned int)(v23 + 1 + v24) >> 1;
          v25 = *v12;
          v12 += 4;
          v26 = *v20;
          v20 += 4;
          *v22++ = (unsigned int)(v26 + v25 + 1) >> 1;
        }
        while ( v19 < a9 );
        v10 = a5;
        v13 = a10 >> 1;
        v11 = v28;
        v17 = a6;
      }
      ++v11;
      v14 = (unsigned __int8 *)&v15[v10];
      a3 += v17;
      v28 = v11;
      a4 += v17;
      v12 = (unsigned __int8 *)&v16[v10];
      v15 += 2 * v10;
      v16 += 2 * v10;
    }
    while ( v11 < v13 );
  }
  if ( (a10 & 1) != 0 )
  {
    for ( i = 0; i < a9; ++a4 )
    {
      ++i;
      *a3 = *v14;
      v14 += 4;
      ++a3;
      *a4 = *v12;
      v12 += 4;
    }
  }
}

```

## disassembly

```asm
0x180002da4  mov     [rsp+arg_18], rbx
0x180002da9  push    rbp
0x180002daa  push    rsi
0x180002dab  push    r12
0x180002dad  push    r13
0x180002daf  push    r14
0x180002db1  push    r15
0x180002db3  movsxd  rbx, [rsp+30h+arg_20]
0x180002db8  xor     r15d, r15d
0x180002dbb  mov     ebp, [rsp+30h+arg_48]
0x180002dc2  mov     r11, rdx
0x180002dc5  sar     ebp, 1
0x180002dc7  mov     r10, rcx
0x180002dca  mov     [rsp+30h+arg_50], ebp
0x180002dd1  mov     [rsp+30h+arg_30], r15d
0x180002dd6  lea     rsi, [rbx+rcx]
0x180002dda  lea     r14, [rbx+rdx]
0x180002dde  test    ebp, ebp
0x180002de0  jle     loc_180002E8B
0x180002de6  movsxd  r12, [rsp+30h+arg_28]
0x180002deb  cmp     [rsp+30h+arg_40], 0
0x180002df0  mov     r13, rsi
0x180002df3  mov     [rsp+30h+arg_38], 0
0x180002dfb  jle     short loc_180002E64
0x180002dfd  mov     r15d, [rsp+30h+arg_38]
0x180002e02  mov     rbx, r14
0x180002e05  mov     r12, r8
0x180002e08  mov     rbp, r9
0x180002e0b  movzx   ecx, byte ptr [r13+0]
0x180002e10  inc     r15d
0x180002e13  movzx   edx, byte ptr [r10]
0x180002e17  lea     r13, [r13+4]
0x180002e1b  inc     ecx
0x180002e1d  lea     r10, [r10+4]
0x180002e21  add     edx, ecx
0x180002e23  shr     edx, 1
0x180002e25  mov     [r12], dl
0x180002e29  inc     r12
0x180002e2c  movzx   edx, byte ptr [r11]
0x180002e30  lea     r11, [r11+4]
0x180002e34  movzx   ecx, byte ptr [rbx]
0x180002e37  inc     edx
0x180002e39  add     edx, ecx
0x180002e3b  lea     rbx, [rbx+4]
0x180002e3f  shr     edx, 1
0x180002e41  mov     [rbp+0], dl
0x180002e44  inc     rbp
0x180002e47  cmp     r15d, [rsp+30h+arg_40]
0x180002e4c  jl      short loc_180002E0B
0x180002e4e  movsxd  rbx, [rsp+30h+arg_20]
0x180002e53  mov     ebp, [rsp+30h+arg_50]
0x180002e5a  mov     r15d, [rsp+30h+arg_30]
0x180002e5f  movsxd  r12, [rsp+30h+arg_28]
0x180002e64  inc     r15d
0x180002e67  lea     r10, [rbx+rsi]
0x180002e6b  add     r8, r12
0x180002e6e  mov     [rsp+30h+arg_30], r15d
0x180002e73  add     r9, r12
0x180002e76  lea     r11, [rbx+r14]
0x180002e7a  lea     rsi, [rsi+rbx*2]
0x180002e7e  lea     r14, [r14+rbx*2]
0x180002e82  cmp     r15d, ebp
0x180002e85  jl      loc_180002DEB
0x180002e8b  test    byte ptr [rsp+30h+arg_48], 1
0x180002e93  jz      short loc_180002EBF
0x180002e95  xor     ecx, ecx
0x180002e97  cmp     [rsp+30h+arg_40], ecx
0x180002e9b  jle     short loc_180002EBF
0x180002e9d  mov     al, [r10]
0x180002ea0  inc     ecx
0x180002ea2  mov     [r8], al
0x180002ea5  lea     r10, [r10+4]
0x180002ea9  mov     al, [r11]
0x180002eac  inc     r8
0x180002eaf  mov     [r9], al
0x180002eb2  lea     r11, [r11+4]
0x180002eb6  inc     r9
0x180002eb9  cmp     ecx, [rsp+30h+arg_40]
0x180002ebd  jl      short loc_180002E9D
0x180002ebf  mov     rbx, [rsp+30h+arg_18]
0x180002ec4  pop     r15
0x180002ec6  pop     r14
0x180002ec8  pop     r13
0x180002eca  pop     r12
0x180002ecc  pop     rsi
0x180002ecd  pop     rbp
0x180002ece  retn
```
