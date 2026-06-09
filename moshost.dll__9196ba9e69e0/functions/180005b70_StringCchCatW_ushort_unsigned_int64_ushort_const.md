# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005b70`
- end: `0x180005c19`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ad8`
- `0x180005cdc`

## callees

- `0x180005b70`

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
0x180005b70  mov     [rsp+arg_0], rbx
0x180005b75  mov     [rsp+arg_8], rdi
0x180005b7a  mov     r9d, 104h
0x180005b80  mov     rbx, rcx
0x180005b83  mov     r10d, r9d
0x180005b86  mov     rax, rcx
0x180005b89  xor     edi, edi
0x180005b8b  cmp     [rax], di
0x180005b8e  jz      short loc_180005B9A
0x180005b90  add     rax, 2
0x180005b94  sub     r10, 1
0x180005b98  jnz     short loc_180005B8B
0x180005b9a  mov     rax, r10
0x180005b9d  mov     rcx, r9
0x180005ba0  neg     rax
0x180005ba3  mov     rax, r10
0x180005ba6  sbb     edx, edx
0x180005ba8  sub     rcx, r10
0x180005bab  not     edx
0x180005bad  and     edx, 80070057h
0x180005bb3  neg     rax
0x180005bb6  sbb     r11, r11
0x180005bb9  and     r11, rcx
0x180005bbc  test    r10, r10
0x180005bbf  jz      short loc_180005C0C
0x180005bc1  lea     rax, [rbx+r11*2]
0x180005bc5  mov     ecx, 7FFFFFFEh
0x180005bca  sub     r9, r11
0x180005bcd  jz      short loc_180005BF1
0x180005bcf  test    rcx, rcx
0x180005bd2  jz      short loc_180005BF1
0x180005bd4  movzx   edx, word ptr [r8]
0x180005bd8  test    dx, dx
0x180005bdb  jz      short loc_180005BF1
0x180005bdd  mov     [rax], dx
0x180005be0  add     r8, 2
0x180005be4  add     rax, 2
0x180005be8  dec     rcx
0x180005beb  sub     r9, 1
0x180005bef  jnz     short loc_180005BCF
0x180005bf1  test    r9, r9
0x180005bf4  lea     rcx, [rax-2]
0x180005bf8  cmovnz  rcx, rax
0x180005bfc  neg     r9
0x180005bff  sbb     edx, edx
0x180005c01  not     edx
0x180005c03  and     edx, 8007007Ah
0x180005c09  mov     [rcx], di
0x180005c0c  mov     rbx, [rsp+arg_0]
0x180005c11  mov     eax, edx
0x180005c13  mov     rdi, [rsp+arg_8]
0x180005c18  retn
```
