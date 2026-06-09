# DiscpGetIPAddressFromDataBlock

- ea: `0x180018f24`
- end: `0x180019030`
- name: `DiscpGetIPAddressFromDataBlock`
- size: `268`
- prototype: `__int64 __fastcall(wchar_t **, __int64 *, unsigned int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008af8`
- `0x180008e84`
- `0x180017e50`
- `0x180018e80`

## callees

- `0x180018f24`
- `0x18001ae6c`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180018fa9`
- `ISCSIUM!DiscpAllocMemory` at `0x180018fe7`
- `ISCSIUM!DiscpAllocMemory` at `0x180018fa9`
- `ISCSIUM!DiscpAllocMemory` at `0x180018fe7`
- `ISCSIUM!DiscpCopyString` at `0x180019018`
- `ISCSIUM!DiscpCopyString` at `0x180019018`

## pseudocode

```c
__int64 __fastcall DiscpGetIPAddressFromDataBlock(wchar_t **a1, __int64 *a2, unsigned int *a3, __int64 a4)
{
  unsigned int v5; // ecx
  __int64 v7; // rdi
  unsigned int v8; // r8d
  wchar_t *v9; // rax
  size_t v11; // rdx
  int v12; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  v5 = *a3;
  v13 = 0;
  if ( v5 >= 0x22 )
  {
    v7 = *a2;
    v14 = v5;
    v8 = *(unsigned __int16 *)(v7 + 32) + 34;
    if ( v5 >= v8 )
    {
      *a2 = v7 + v8;
      *a3 -= v8;
      switch ( *(_DWORD *)v7 )
      {
        case 0:
          v13 = v7 + 32;
          return DiscpCopyString(a1, &v12, &v13, a4, &v14);
        case 1:
          v9 = *a1;
          if ( *a1 )
          {
            if ( (unsigned int)a4 < 0x14 )
              return 4026466305LL;
          }
          else
          {
            v9 = (wchar_t *)DiscpAllocMemory(42);
            *a1 = v9;
            if ( !v9 )
              return 8;
          }
          v11 = 21;
          goto LABEL_12;
        case 2:
          v9 = *a1;
          if ( *a1 )
          {
            if ( (unsigned int)a4 < 0x32 )
              return 4026466305LL;
            goto LABEL_11;
          }
          v9 = (wchar_t *)DiscpAllocMemory(102);
          *a1 = v9;
          if ( v9 )
          {
LABEL_11:
            v11 = 51;
LABEL_12:
            DiscpIpAddressToString(v9, v11);
            return 0;
          }
          return 8;
      }
    }
  }
  return 4026466329LL;
}

```

## disassembly

```asm
0x180018f24  mov     rax, rsp
0x180018f27  mov     [rax+8], rbx
0x180018f2b  push    rdi
0x180018f2c  sub     rsp, 40h
0x180018f30  mov     rbx, rcx
0x180018f33  mov     dword ptr [rax-18h], 0
0x180018f3a  mov     ecx, [r8]
0x180018f3d  mov     r10, r8
0x180018f40  mov     qword ptr [rax-10h], 0
0x180018f48  cmp     ecx, 22h ; '"'
0x180018f4b  jb      loc_180019020
0x180018f51  mov     rdi, [rdx]
0x180018f54  mov     [rax+18h], ecx
0x180018f57  lea     r11, [rdi+20h]
0x180018f5b  movzx   r8d, word ptr [r11]
0x180018f5f  add     r8d, 22h ; '"'
0x180018f63  cmp     ecx, r8d
0x180018f66  jb      loc_180019020
0x180018f6c  mov     eax, r8d
0x180018f6f  add     rax, rdi
0x180018f72  mov     [rdx], rax
0x180018f75  sub     [r10], r8d
0x180018f78  mov     ecx, [rdi]
0x180018f7a  test    ecx, ecx
0x180018f7c  jz      short loc_180018FFC
0x180018f7e  sub     ecx, 1
0x180018f81  jz      short loc_180018FD2
0x180018f83  cmp     ecx, 1
0x180018f86  jnz     loc_180019020
0x180018f8c  mov     rax, [rbx]
0x180018f8f  test    rax, rax
0x180018f92  jz      short loc_180018FA4
0x180018f94  cmp     r9d, 32h ; '2'
0x180018f98  jnb     short loc_180018FBE
0x180018f9a  mov     eax, 0EFFF0001h
0x180018f9f  jmp     loc_180019025
0x180018fa4  mov     ecx, 66h ; 'f'
0x180018fa9  call    cs:__imp_DiscpAllocMemory
0x180018faf  mov     [rbx], rax
0x180018fb2  test    rax, rax
0x180018fb5  jnz     short loc_180018FBE
0x180018fb7  mov     eax, 8
0x180018fbc  jmp     short loc_180019025
0x180018fbe  mov     edx, 33h ; '3'; cchDest
0x180018fc3  mov     r8, rdi
0x180018fc6  mov     rcx, rax; pszDest
0x180018fc9  call    DiscpIpAddressToString
0x180018fce  xor     eax, eax
0x180018fd0  jmp     short loc_180019025
0x180018fd2  mov     rax, [rbx]
0x180018fd5  test    rax, rax
0x180018fd8  jz      short loc_180018FE2
0x180018fda  cmp     r9d, 14h
0x180018fde  jnb     short loc_180018FF5
0x180018fe0  jmp     short loc_180018F9A
0x180018fe2  mov     ecx, 2Ah ; '*'
0x180018fe7  call    cs:__imp_DiscpAllocMemory
0x180018fed  mov     [rbx], rax
0x180018ff0  test    rax, rax
0x180018ff3  jz      short loc_180018FB7
0x180018ff5  mov     edx, 15h
0x180018ffa  jmp     short loc_180018FC3
0x180018ffc  lea     rax, [rsp+48h+arg_10]
0x180019001  mov     [rsp+48h+var_10], r11
0x180019006  lea     r8, [rsp+48h+var_10]
0x18001900b  mov     [rsp+48h+var_28], rax
0x180019010  lea     rdx, [rsp+48h+var_18]
0x180019015  mov     rcx, rbx
0x180019018  call    cs:__imp_DiscpCopyString
0x18001901e  jmp     short loc_180019025
0x180019020  mov     eax, 0EFFF0019h
0x180019025  mov     rbx, [rsp+48h+arg_0]
0x18001902a  add     rsp, 40h
0x18001902e  pop     rdi
0x18001902f  retn
```
