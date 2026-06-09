# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180009ef8`
- end: `0x180009fea`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `242`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c30`
- `0x18000e1a8`

## callees

- `0x180009ef8`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  unsigned __int16 *v7; // r11
  unsigned int v8; // r8d
  __int64 v9; // rax
  unsigned __int64 v10; // r9
  unsigned __int16 *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r10

  v7 = a1;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( a2 > 0x7FFFFFFF )
  {
    v8 = -2147024809;
    *a1 = 0;
    return v8;
  }
  v9 = 2147483646;
  v10 = a2;
  v11 = a1;
  v12 = 0;
  do
  {
    if ( !v9 )
      break;
    if ( !*a3 )
      break;
    *v11++ = *a3++;
    --v9;
    ++v12;
    --v10;
  }
  while ( v10 );
  v13 = v12 - 1;
  if ( v10 )
    v13 = v12;
  v14 = v11 - 1;
  v8 = v10 != 0 ? 0 : 0x8007007A;
  if ( v10 )
    v14 = v11;
  v15 = a2 - v13;
  *v14 = 0;
  if ( v10 )
  {
    v7 += v13;
    v16 = a2 - v13;
  }
  else
  {
    v16 = a2 & 0x7FFFFFFFFFFFFFFFLL;
    if ( v16 )
    {
      *v7 = 0;
    }
    else
    {
      v16 = v15;
      v7 += v13;
    }
    if ( v8 != -2147024774 )
      return v8;
  }
  if ( a4 )
    *a4 = v7;
  if ( a5 )
    *a5 = v16;
  return v8;
}

```

## disassembly

```asm
0x180009ef8  push    rbx
0x180009efa  push    rsi
0x180009efb  push    rdi
0x180009efc  xor     esi, esi
0x180009efe  mov     rdi, r9
0x180009f01  mov     r10, rdx
0x180009f04  mov     r11, rcx
0x180009f07  test    rdx, rdx
0x180009f0a  jz      loc_180009FD5
0x180009f10  cmp     rdx, 7FFFFFFFh
0x180009f17  jbe     short loc_180009F24
0x180009f19  mov     r8d, 80070057h
0x180009f1f  jmp     loc_180009FE0
0x180009f24  mov     eax, 7FFFFFFEh
0x180009f29  mov     r9, r10
0x180009f2c  mov     rbx, r11
0x180009f2f  mov     rcx, rsi
0x180009f32  test    rax, rax
0x180009f35  jz      short loc_180009F57
0x180009f37  movzx   edx, word ptr [r8]
0x180009f3b  test    dx, dx
0x180009f3e  jz      short loc_180009F57
0x180009f40  mov     [rbx], dx
0x180009f43  add     r8, 2
0x180009f47  add     rbx, 2
0x180009f4b  dec     rax
0x180009f4e  inc     rcx
0x180009f51  sub     r9, 1
0x180009f55  jnz     short loc_180009F32
0x180009f57  test    r9, r9
0x180009f5a  lea     rdx, [rcx-1]
0x180009f5e  mov     rax, r9
0x180009f61  cmovnz  rdx, rcx
0x180009f65  neg     rax
0x180009f68  lea     rcx, [rbx-2]
0x180009f6c  mov     rax, r10
0x180009f6f  sbb     r8d, r8d
0x180009f72  not     r8d
0x180009f75  and     r8d, 8007007Ah
0x180009f7c  test    r9, r9
0x180009f7f  cmovnz  rcx, rbx
0x180009f83  sub     rax, rdx
0x180009f86  mov     [rcx], si
0x180009f89  lea     rcx, [r11+rdx*2]
0x180009f8d  test    r9, r9
0x180009f90  jnz     short loc_180009FB8
0x180009f92  mov     rdx, 7FFFFFFFFFFFFFFFh
0x180009f9c  and     r10, rdx
0x180009f9f  jbe     short loc_180009FA7
0x180009fa1  mov     [r11], si
0x180009fa5  jmp     short loc_180009FAD
0x180009fa7  mov     r10, rax
0x180009faa  mov     r11, rcx
0x180009fad  cmp     r8d, 8007007Ah
0x180009fb4  jnz     short loc_180009FE3
0x180009fb6  jmp     short loc_180009FBE
0x180009fb8  mov     r11, rcx
0x180009fbb  mov     r10, rax
0x180009fbe  test    rdi, rdi
0x180009fc1  jz      short loc_180009FC6
0x180009fc3  mov     [rdi], r11
0x180009fc6  mov     rax, [rsp+18h+arg_20]
0x180009fcb  test    rax, rax
0x180009fce  jz      short loc_180009FE3
0x180009fd0  mov     [rax], r10
0x180009fd3  jmp     short loc_180009FE3
0x180009fd5  mov     r8d, 80070057h
0x180009fdb  test    r10, r10
0x180009fde  jz      short loc_180009FE3
0x180009fe0  mov     [rcx], si
0x180009fe3  mov     eax, r8d
0x180009fe6  pop     rdi
0x180009fe7  pop     rsi
0x180009fe8  pop     rbx
0x180009fe9  retn
```
