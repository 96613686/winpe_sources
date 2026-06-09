# SidToStr(void *,ushort *,ulong)

- ea: `0x180019f6c`
- end: `0x18001a04c`
- name: `?SidToStr@@YAXPEAXPEAGK@Z`
- size: `224`
- prototype: `void(void *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180019c40`

## callees

- `0x180019f6c`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180019fb2`
- `msvcrt!swprintf_s` at `0x180019fef`
- `msvcrt!swprintf_s` at `0x18001a025`
- `msvcrt!swprintf_s` at `0x180019fb2`
- `msvcrt!swprintf_s` at `0x180019fef`
- `msvcrt!swprintf_s` at `0x18001a025`

## pseudocode

```c
void __fastcall SidToStr(unsigned __int8 *a1, unsigned __int16 *a2, unsigned int a3)
{
  __int64 v5; // rbp
  int v6; // eax
  wchar_t *v7; // r14
  unsigned __int8 i; // bl
  int v9; // eax
  unsigned int v10; // [rsp+50h] [rbp+18h]

  if ( a3 >= 11 * (unsigned int)a1[1] + 12 )
  {
    v5 = a3;
    v6 = swprintf_s(a2, a3, L"S-%u-", *a1);
    HIBYTE(v10) = a1[4];
    BYTE2(v10) = a1[5];
    BYTE1(v10) = a1[6];
    LOBYTE(v10) = a1[7];
    v7 = &a2[v6 + swprintf_s(&a2[v6], (unsigned int)v5 - (__int64)v6, L"%u", v10)];
    for ( i = 0; i < a1[1]; v7 += v9 )
      v9 = swprintf_s(v7, v5 - (v7 - a2), L"-%u", *(unsigned int *)&a1[4 * i++ + 8]);
  }
  else
  {
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180019f6c  mov     [rsp+arg_0], rbx
0x180019f71  mov     [rsp+arg_8], rbp
0x180019f76  push    rsi
0x180019f77  push    rdi
0x180019f78  push    r14
0x180019f7a  sub     rsp, 20h
0x180019f7e  movzx   eax, byte ptr [rcx+1]
0x180019f82  mov     rsi, rdx
0x180019f85  imul    r9d, eax, 0Bh
0x180019f89  mov     rdi, rcx
0x180019f8c  add     r9d, 0Ch
0x180019f90  cmp     r8d, r9d
0x180019f93  jnb     short loc_180019F9F
0x180019f95  xor     ebx, ebx
0x180019f97  mov     [rdx], bx
0x180019f9a  jmp     loc_18001A039
0x180019f9f  movzx   r9d, byte ptr [rcx]
0x180019fa3  mov     rcx, rsi; Buffer
0x180019fa6  mov     ebp, r8d
0x180019fa9  lea     r8, aSU; "S-%u-"
0x180019fb0  mov     edx, ebp; BufferCount
0x180019fb2  call    cs:__imp_swprintf_s
0x180019fb8  movsxd  rcx, eax
0x180019fbb  mov     edx, ebp
0x180019fbd  mov     al, [rdi+4]
0x180019fc0  lea     r8, aU_0; "%u"
0x180019fc7  mov     byte ptr [rsp+38h+arg_10+3], al
0x180019fcb  sub     rdx, rcx; BufferCount
0x180019fce  mov     al, [rdi+5]
0x180019fd1  mov     byte ptr [rsp+38h+arg_10+2], al
0x180019fd5  lea     rbx, [rsi+rcx*2]
0x180019fd9  mov     al, [rdi+6]
0x180019fdc  mov     rcx, rbx; Buffer
0x180019fdf  mov     byte ptr [rsp+38h+arg_10+1], al
0x180019fe3  mov     al, [rdi+7]
0x180019fe6  mov     byte ptr [rsp+38h+arg_10], al
0x180019fea  mov     r9d, [rsp+38h+arg_10]
0x180019fef  call    cs:__imp_swprintf_s
0x180019ff5  movsxd  rcx, eax
0x180019ff8  lea     r14, [rbx+rcx*2]
0x180019ffc  xor     ebx, ebx
0x180019ffe  cmp     [rdi+1], bl
0x18001a001  jbe     short loc_18001A039
0x18001a003  movzx   r9d, bl
0x18001a007  lea     r8, aU_2; "-%u"
0x18001a00e  mov     rax, r14
0x18001a011  mov     rdx, rbp
0x18001a014  sub     rax, rsi
0x18001a017  mov     rcx, r14; Buffer
0x18001a01a  sar     rax, 1
0x18001a01d  mov     r9d, [rdi+r9*4+8]
0x18001a022  sub     rdx, rax; BufferCount
0x18001a025  call    cs:__imp_swprintf_s
0x18001a02b  movsxd  rcx, eax
0x18001a02e  inc     bl
0x18001a030  lea     r14, [r14+rcx*2]
0x18001a034  cmp     bl, [rdi+1]
0x18001a037  jb      short loc_18001A003
0x18001a039  mov     rbx, [rsp+38h+arg_0]
0x18001a03e  mov     rbp, [rsp+38h+arg_8]
0x18001a043  add     rsp, 20h
0x18001a047  pop     r14
0x18001a049  pop     rdi
0x18001a04a  pop     rsi
0x18001a04b  retn
```
