# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005254`
- end: `0x1400052fd`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000321c`
- `0x1400053bc`

## callees

- `0x140005254`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140005254  mov     [rsp+arg_0], rbx
0x140005259  mov     [rsp+arg_8], rdi
0x14000525e  mov     r9d, 104h
0x140005264  mov     rbx, rcx
0x140005267  mov     r10d, r9d
0x14000526a  mov     rax, rcx
0x14000526d  xor     edi, edi
0x14000526f  cmp     [rax], di
0x140005272  jz      short loc_14000527E
0x140005274  add     rax, 2
0x140005278  sub     r10, 1
0x14000527c  jnz     short loc_14000526F
0x14000527e  mov     rax, r10
0x140005281  mov     rcx, r9
0x140005284  neg     rax
0x140005287  mov     rax, r10
0x14000528a  sbb     edx, edx
0x14000528c  sub     rcx, r10
0x14000528f  not     edx
0x140005291  and     edx, 80070057h
0x140005297  neg     rax
0x14000529a  sbb     r11, r11
0x14000529d  and     r11, rcx
0x1400052a0  test    r10, r10
0x1400052a3  jz      short loc_1400052F0
0x1400052a5  lea     rax, [rbx+r11*2]
0x1400052a9  mov     ecx, 7FFFFFFEh
0x1400052ae  sub     r9, r11
0x1400052b1  jz      short loc_1400052D5
0x1400052b3  test    rcx, rcx
0x1400052b6  jz      short loc_1400052D5
0x1400052b8  movzx   edx, word ptr [r8]
0x1400052bc  test    dx, dx
0x1400052bf  jz      short loc_1400052D5
0x1400052c1  mov     [rax], dx
0x1400052c4  add     r8, 2
0x1400052c8  add     rax, 2
0x1400052cc  dec     rcx
0x1400052cf  sub     r9, 1
0x1400052d3  jnz     short loc_1400052B3
0x1400052d5  test    r9, r9
0x1400052d8  lea     rcx, [rax-2]
0x1400052dc  cmovnz  rcx, rax
0x1400052e0  neg     r9
0x1400052e3  sbb     edx, edx
0x1400052e5  not     edx
0x1400052e7  and     edx, 8007007Ah
0x1400052ed  mov     [rcx], di
0x1400052f0  mov     rbx, [rsp+arg_0]
0x1400052f5  mov     eax, edx
0x1400052f7  mov     rdi, [rsp+arg_8]
0x1400052fc  retn
```
