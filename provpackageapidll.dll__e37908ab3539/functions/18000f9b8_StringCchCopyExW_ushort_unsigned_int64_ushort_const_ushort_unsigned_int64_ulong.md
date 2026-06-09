# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x18000f9b8`
- end: `0x18000fa67`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `175`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f040`
- `0x18000fb58`

## callees

- `0x18000f9b8`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  __int64 result; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // r8
  unsigned __int16 *v12; // rax
  __int64 v13; // r9
  unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // r10

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v10 = 2147483646;
    v11 = a2;
    v12 = a1;
    v13 = 0;
    do
    {
      if ( !v10 )
        break;
      if ( !*a3 )
        break;
      *v12++ = *a3++;
      --v10;
      ++v13;
      --v11;
    }
    while ( v11 );
    v14 = v12 - 1;
    v15 = v13 - 1;
    if ( v11 )
    {
      v14 = v12;
      v15 = v13;
    }
    v16 = a2 - v15;
    *v14 = 0;
    result = v11 == 0 ? 0x8007007A : 0;
    if ( a4 )
      *a4 = &a1[v15];
    if ( a5 )
      *a5 = v16;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f9b8  push    rbx
0x18000f9ba  push    rsi
0x18000f9bb  push    rdi
0x18000f9bc  xor     esi, esi
0x18000f9be  mov     rdi, r9
0x18000f9c1  mov     r11, r8
0x18000f9c4  mov     r10, rdx
0x18000f9c7  mov     rbx, rcx
0x18000f9ca  test    rdx, rdx
0x18000f9cd  jz      loc_18000FA56
0x18000f9d3  cmp     rdx, 7FFFFFFFh
0x18000f9da  jbe     short loc_18000F9E3
0x18000f9dc  mov     eax, 80070057h
0x18000f9e1  jmp     short loc_18000FA60
0x18000f9e3  mov     ecx, 7FFFFFFEh
0x18000f9e8  mov     r8, r10
0x18000f9eb  mov     rax, rbx
0x18000f9ee  mov     r9, rsi
0x18000f9f1  test    rcx, rcx
0x18000f9f4  jz      short loc_18000FA16
0x18000f9f6  movzx   edx, word ptr [r11]
0x18000f9fa  test    dx, dx
0x18000f9fd  jz      short loc_18000FA16
0x18000f9ff  mov     [rax], dx
0x18000fa02  add     r11, 2
0x18000fa06  add     rax, 2
0x18000fa0a  dec     rcx
0x18000fa0d  inc     r9
0x18000fa10  sub     r8, 1
0x18000fa14  jnz     short loc_18000F9F1
0x18000fa16  test    r8, r8
0x18000fa19  lea     rcx, [rax-2]
0x18000fa1d  lea     rdx, [r9-1]
0x18000fa21  cmovnz  rcx, rax
0x18000fa25  cmovnz  rdx, r9
0x18000fa29  neg     r8
0x18000fa2c  sbb     eax, eax
0x18000fa2e  sub     r10, rdx
0x18000fa31  not     eax
0x18000fa33  mov     [rcx], si
0x18000fa36  and     eax, 8007007Ah
0x18000fa3b  lea     rcx, [rbx+rdx*2]
0x18000fa3f  test    rdi, rdi
0x18000fa42  jz      short loc_18000FA47
0x18000fa44  mov     [rdi], rcx
0x18000fa47  mov     rcx, [rsp+18h+arg_20]
0x18000fa4c  test    rcx, rcx
0x18000fa4f  jz      short loc_18000FA63
0x18000fa51  mov     [rcx], r10
0x18000fa54  jmp     short loc_18000FA63
0x18000fa56  mov     eax, 80070057h
0x18000fa5b  test    r10, r10
0x18000fa5e  jz      short loc_18000FA63
0x18000fa60  mov     [rcx], si
0x18000fa63  pop     rdi
0x18000fa64  pop     rsi
0x18000fa65  pop     rbx
0x18000fa66  retn
```
