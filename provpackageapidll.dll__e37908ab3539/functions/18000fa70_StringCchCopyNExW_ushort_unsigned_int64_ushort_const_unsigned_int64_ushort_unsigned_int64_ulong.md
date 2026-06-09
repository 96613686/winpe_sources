# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x18000fa70`
- end: `0x18000fb4f`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `223`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f040`

## callees

- `0x18000fa70`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        unsigned __int16 **a5,
        unsigned __int64 *a6)
{
  unsigned int v9; // edx
  unsigned __int64 v10; // r8
  unsigned __int16 *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned __int16 *v14; // rcx

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || a4 >= 0x7FFFFFFF )
    {
      v9 = -2147024809;
      *a1 = 0;
    }
    else
    {
      v10 = a2;
      v11 = a1;
      v12 = 0;
      do
      {
        if ( !a4 )
          break;
        if ( !*a3 )
          break;
        *v11++ = *a3++;
        --a4;
        ++v12;
        --v10;
      }
      while ( v10 );
      v13 = v12 - 1;
      if ( v10 )
        v13 = v12;
      v14 = v11 - 1;
      v9 = v10 == 0 ? 0x8007007A : 0;
      if ( v10 )
        v14 = v11;
      *v14 = 0;
      if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147024774 )
      {
        if ( a5 )
          *a5 = &a1[v13];
        if ( a6 )
          *a6 = a2 - v13;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x18000fa70  mov     [rsp+arg_0], rbx
0x18000fa75  mov     [rsp+arg_8], rdi
0x18000fa7a  xor     edi, edi
0x18000fa7c  mov     rax, r8
0x18000fa7f  mov     r10, rdx
0x18000fa82  mov     r11, rcx
0x18000fa85  test    rdx, rdx
0x18000fa88  jz      loc_18000FB34
0x18000fa8e  mov     ecx, 7FFFFFFFh
0x18000fa93  cmp     rdx, rcx
0x18000fa96  jbe     short loc_18000FAA2
0x18000fa98  mov     edx, 80070057h
0x18000fa9d  jmp     loc_18000FB3E
0x18000faa2  cmp     r9, rcx
0x18000faa5  jnb     short loc_18000FA98
0x18000faa7  mov     r8, r10
0x18000faaa  mov     rbx, r11
0x18000faad  mov     rcx, rdi
0x18000fab0  test    r9, r9
0x18000fab3  jz      short loc_18000FAD4
0x18000fab5  movzx   edx, word ptr [rax]
0x18000fab8  test    dx, dx
0x18000fabb  jz      short loc_18000FAD4
0x18000fabd  mov     [rbx], dx
0x18000fac0  add     rax, 2
0x18000fac4  add     rbx, 2
0x18000fac8  dec     r9
0x18000facb  inc     rcx
0x18000face  sub     r8, 1
0x18000fad2  jnz     short loc_18000FAB0
0x18000fad4  test    r8, r8
0x18000fad7  lea     r9, [rcx-1]
0x18000fadb  mov     rax, r8
0x18000fade  cmovnz  r9, rcx
0x18000fae2  neg     rax
0x18000fae5  lea     rcx, [rbx-2]
0x18000fae9  sbb     edx, edx
0x18000faeb  not     edx
0x18000faed  and     edx, 8007007Ah
0x18000faf3  test    r8, r8
0x18000faf6  cmovnz  rcx, rbx
0x18000fafa  mov     [rcx], di
0x18000fafd  mov     ecx, 80000000h
0x18000fb02  lea     eax, [rdx+rcx]
0x18000fb05  test    ecx, eax
0x18000fb07  jnz     short loc_18000FB11
0x18000fb09  cmp     edx, 8007007Ah
0x18000fb0f  jnz     short loc_18000FB42
0x18000fb11  mov     rcx, [rsp+arg_20]
0x18000fb16  test    rcx, rcx
0x18000fb19  jz      short loc_18000FB22
0x18000fb1b  lea     rax, [r11+r9*2]
0x18000fb1f  mov     [rcx], rax
0x18000fb22  mov     rax, [rsp+arg_28]
0x18000fb27  test    rax, rax
0x18000fb2a  jz      short loc_18000FB42
0x18000fb2c  sub     r10, r9
0x18000fb2f  mov     [rax], r10
0x18000fb32  jmp     short loc_18000FB42
0x18000fb34  mov     edx, 80070057h
0x18000fb39  test    r10, r10
0x18000fb3c  jz      short loc_18000FB42
0x18000fb3e  mov     [r11], di
0x18000fb42  mov     rbx, [rsp+arg_0]
0x18000fb47  mov     eax, edx
0x18000fb49  mov     rdi, [rsp+arg_8]
0x18000fb4e  retn
```
