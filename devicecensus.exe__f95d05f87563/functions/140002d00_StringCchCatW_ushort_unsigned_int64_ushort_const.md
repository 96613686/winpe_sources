# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140002d00`
- end: `0x140002da9`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003610`
- `0x1400039d0`

## callees

- `0x140002d00`

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
0x140002d00  mov     [rsp+arg_0], rbx
0x140002d05  mov     [rsp+arg_8], rdi
0x140002d0a  mov     r9d, 104h
0x140002d10  mov     rbx, rcx
0x140002d13  mov     r10d, r9d
0x140002d16  mov     rax, rcx
0x140002d19  xor     edi, edi
0x140002d1b  cmp     [rax], di
0x140002d1e  jz      short loc_140002D2A
0x140002d20  add     rax, 2
0x140002d24  sub     r10, 1
0x140002d28  jnz     short loc_140002D1B
0x140002d2a  mov     rax, r10
0x140002d2d  mov     rcx, r9
0x140002d30  neg     rax
0x140002d33  mov     rax, r10
0x140002d36  sbb     edx, edx
0x140002d38  sub     rcx, r10
0x140002d3b  not     edx
0x140002d3d  and     edx, 80070057h
0x140002d43  neg     rax
0x140002d46  sbb     r11, r11
0x140002d49  and     r11, rcx
0x140002d4c  test    r10, r10
0x140002d4f  jz      short loc_140002D9C
0x140002d51  lea     rax, [rbx+r11*2]
0x140002d55  mov     ecx, 7FFFFFFEh
0x140002d5a  sub     r9, r11
0x140002d5d  jz      short loc_140002D81
0x140002d5f  test    rcx, rcx
0x140002d62  jz      short loc_140002D81
0x140002d64  movzx   edx, word ptr [r8]
0x140002d68  test    dx, dx
0x140002d6b  jz      short loc_140002D81
0x140002d6d  mov     [rax], dx
0x140002d70  add     r8, 2
0x140002d74  add     rax, 2
0x140002d78  dec     rcx
0x140002d7b  sub     r9, 1
0x140002d7f  jnz     short loc_140002D5F
0x140002d81  test    r9, r9
0x140002d84  lea     rcx, [rax-2]
0x140002d88  cmovnz  rcx, rax
0x140002d8c  neg     r9
0x140002d8f  sbb     edx, edx
0x140002d91  not     edx
0x140002d93  and     edx, 8007007Ah
0x140002d99  mov     [rcx], di
0x140002d9c  mov     rbx, [rsp+arg_0]
0x140002da1  mov     eax, edx
0x140002da3  mov     rdi, [rsp+arg_8]
0x140002da8  retn
```
