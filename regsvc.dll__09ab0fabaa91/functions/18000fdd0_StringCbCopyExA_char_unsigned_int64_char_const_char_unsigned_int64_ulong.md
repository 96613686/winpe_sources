# StringCbCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)

- ea: `0x18000fdd0`
- end: `0x18000fe9a`
- name: `?StringCbCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z`
- size: `202`
- prototype: `__int64 __fastcall(char *, unsigned __int64, char *, char **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e1a8`

## callees

- `0x18000fdd0`

## pseudocode

```c
__int64 __fastcall StringCbCopyExA(char *a1, unsigned __int64 a2, char *a3, char **a4, unsigned __int64 *a5)
{
  unsigned __int64 v7; // r10
  unsigned int v8; // edx
  __int64 v9; // rax
  unsigned __int64 v10; // r8
  char *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r11
  char *v14; // rax

  v7 = a2;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( a2 <= 0x7FFFFFFF )
  {
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
    if ( v10 )
      v14 = v11;
    *v14 = 0;
    v8 = v10 == 0 ? 0x8007007A : 0;
    if ( v10 )
    {
      a1 += v13;
      v7 -= v13;
    }
    else
    {
      *a1 = 0;
      if ( v8 != -2147024774 )
        return v8;
    }
    if ( a4 )
      *a4 = a1;
    if ( a5 )
      *a5 = v7;
  }
  else
  {
    v8 = -2147024809;
    *a1 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18000fdd0  mov     [rsp+arg_0], rbx
0x18000fdd5  mov     [rsp+arg_8], rdi
0x18000fdda  mov     rbx, r9
0x18000fddd  mov     r11, r8
0x18000fde0  mov     r10, rdx
0x18000fde3  test    rdx, rdx
0x18000fde6  jz      loc_18000FE80
0x18000fdec  cmp     rdx, 7FFFFFFFh
0x18000fdf3  jbe     short loc_18000FDFF
0x18000fdf5  mov     edx, 80070057h
0x18000fdfa  jmp     loc_18000FE8A
0x18000fdff  mov     eax, 7FFFFFFEh
0x18000fe04  mov     r8, r10
0x18000fe07  mov     r9, rcx
0x18000fe0a  xor     edx, edx
0x18000fe0c  test    rax, rax
0x18000fe0f  jz      short loc_18000FE2E
0x18000fe11  mov     dil, [r11]
0x18000fe14  test    dil, dil
0x18000fe17  jz      short loc_18000FE2E
0x18000fe19  mov     [r9], dil
0x18000fe1c  inc     r11
0x18000fe1f  inc     r9
0x18000fe22  dec     rax
0x18000fe25  inc     rdx
0x18000fe28  sub     r8, 1
0x18000fe2c  jnz     short loc_18000FE0C
0x18000fe2e  test    r8, r8
0x18000fe31  lea     r11, [rdx-1]
0x18000fe35  mov     rax, r8
0x18000fe38  mov     edi, 8007007Ah
0x18000fe3d  cmovnz  r11, rdx
0x18000fe41  neg     rax
0x18000fe44  lea     rax, [r9-1]
0x18000fe48  sbb     edx, edx
0x18000fe4a  test    r8, r8
0x18000fe4d  not     edx
0x18000fe4f  cmovnz  rax, r9
0x18000fe53  mov     byte ptr [rax], 0
0x18000fe56  and     edx, edi
0x18000fe58  jns     short loc_18000FE63
0x18000fe5a  mov     byte ptr [rcx], 0
0x18000fe5d  cmp     edx, edi
0x18000fe5f  jnz     short loc_18000FE8D
0x18000fe61  jmp     short loc_18000FE69
0x18000fe63  add     rcx, r11
0x18000fe66  sub     r10, r11
0x18000fe69  test    rbx, rbx
0x18000fe6c  jz      short loc_18000FE71
0x18000fe6e  mov     [rbx], rcx
0x18000fe71  mov     rax, [rsp+arg_20]
0x18000fe76  test    rax, rax
0x18000fe79  jz      short loc_18000FE8D
0x18000fe7b  mov     [rax], r10
0x18000fe7e  jmp     short loc_18000FE8D
0x18000fe80  mov     edx, 80070057h
0x18000fe85  test    r10, r10
0x18000fe88  jz      short loc_18000FE8D
0x18000fe8a  mov     byte ptr [rcx], 0
0x18000fe8d  mov     rbx, [rsp+arg_0]
0x18000fe92  mov     eax, edx
0x18000fe94  mov     rdi, [rsp+arg_8]
0x18000fe99  retn
```
