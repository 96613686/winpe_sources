# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000abd4`
- end: `0x18000ac8f`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bc44`
- `0x18000f2b8`
- `0x18000fca8`

## callees

- `0x18000abd4`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000abd4  mov     [rsp+arg_0], rbx
0x18000abd9  mov     [rsp+arg_8], rdi
0x18000abde  lea     rax, [rdx-1]
0x18000abe2  mov     r10d, 7FFFFFFEh
0x18000abe8  mov     r9, rdx
0x18000abeb  mov     rbx, rcx
0x18000abee  cmp     rax, r10
0x18000abf1  ja      loc_18000AC7D
0x18000abf7  mov     r11, rdx
0x18000abfa  mov     rax, rcx
0x18000abfd  xor     edi, edi
0x18000abff  cmp     [rax], di
0x18000ac02  jz      short loc_18000AC0E
0x18000ac04  add     rax, 2
0x18000ac08  sub     r11, 1
0x18000ac0c  jnz     short loc_18000ABFF
0x18000ac0e  mov     rax, r11
0x18000ac11  mov     rcx, r9
0x18000ac14  neg     rax
0x18000ac17  mov     rax, r11
0x18000ac1a  sbb     edx, edx
0x18000ac1c  sub     rcx, r11
0x18000ac1f  not     edx
0x18000ac21  and     edx, 80070057h
0x18000ac27  neg     rax
0x18000ac2a  sbb     rax, rax
0x18000ac2d  and     rax, rcx
0x18000ac30  test    r11, r11
0x18000ac33  jz      short loc_18000AC82
0x18000ac35  sub     r9, rax
0x18000ac38  lea     rax, [rbx+rax*2]
0x18000ac3c  jz      short loc_18000AC60
0x18000ac3e  test    r10, r10
0x18000ac41  jz      short loc_18000AC60
0x18000ac43  movzx   ecx, word ptr [r8]
0x18000ac47  test    cx, cx
0x18000ac4a  jz      short loc_18000AC60
0x18000ac4c  mov     [rax], cx
0x18000ac4f  add     r8, 2
0x18000ac53  add     rax, 2
0x18000ac57  dec     r10
0x18000ac5a  sub     r9, 1
0x18000ac5e  jnz     short loc_18000AC3E
0x18000ac60  test    r9, r9
0x18000ac63  lea     rcx, [rax-2]
0x18000ac67  cmovnz  rcx, rax
0x18000ac6b  neg     r9
0x18000ac6e  sbb     edx, edx
0x18000ac70  not     edx
0x18000ac72  and     edx, 8007007Ah
0x18000ac78  mov     [rcx], di
0x18000ac7b  jmp     short loc_18000AC82
0x18000ac7d  mov     edx, 80070057h
0x18000ac82  mov     rbx, [rsp+arg_0]
0x18000ac87  mov     eax, edx
0x18000ac89  mov     rdi, [rsp+arg_8]
0x18000ac8e  retn
```
