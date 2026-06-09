# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x14003b010`
- end: `0x14003b12a`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002140`
- `0x14003b010`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x14003b0e0`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x14003b10d`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x14003b0e0`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x14003b10d`
- `MSVCP140!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x14003b03a`
- `MSVCP140!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x14003b03a`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  __int64 result; // rax
  size_t v7; // rdi
  const void *v8; // rdx
  int v9; // ecx
  size_t v10; // rbx
  _QWORD *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  size_t v14; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
  {
    _mm_lfence();
    return std::streambuf::xsgetn();
  }
  else
  {
    v7 = a3;
    v8 = **(const void ***)(a1 + 56);
    if ( v8 )
      v9 = **(_DWORD **)(a1 + 80);
    else
      v9 = 0;
    if ( v9 )
    {
      v10 = a3;
      if ( v9 < (unsigned __int64)a3 )
        v10 = v9;
      memcpy_0(a2, v8, v10);
      a2 += v10;
      v7 = a3 - v10;
      **(_DWORD **)(a1 + 80) -= v10;
      **(_QWORD **)(a1 + 56) += (int)v10;
    }
    if ( *(_QWORD *)(a1 + 128) )
    {
      v11 = *(_QWORD **)(a1 + 24);
      if ( *v11 == a1 + 112 )
      {
        v12 = *(_QWORD *)(a1 + 136);
        v13 = *(_QWORD *)(a1 + 144);
        *v11 = v12;
        **(_QWORD **)(a1 + 56) = v12;
        **(_DWORD **)(a1 + 80) = v13 - v12;
      }
      while ( v7 > 0xFFF )
      {
        v14 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
        a2 += v14;
        v7 -= v14;
        if ( v14 != 4095 )
          goto LABEL_20;
      }
      if ( v7 )
        v7 -= fread(a2, 1u, v7, *(FILE **)(a1 + 128));
    }
LABEL_20:
    result = a3 - v7;
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x14003b010  push    rbx
0x14003b012  push    rbp
0x14003b013  push    rsi
0x14003b014  push    rdi
0x14003b015  push    r14
0x14003b017  sub     rsp, 20h
0x14003b01b  mov     rbp, r8
0x14003b01e  mov     r14, rdx
0x14003b021  mov     rsi, rcx
0x14003b024  test    r8, r8
0x14003b027  jg      short loc_14003B030
0x14003b029  xor     eax, eax
0x14003b02b  jmp     loc_14003B11F
0x14003b030  cmp     qword ptr [rcx+68h], 0
0x14003b035  jz      short loc_14003B045
0x14003b037  lfence
0x14003b03a  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x14003b040  jmp     loc_14003B11F
0x14003b045  mov     rax, [rcx+38h]
0x14003b049  mov     rdi, rbp
0x14003b04c  mov     rdx, [rax]; Src
0x14003b04f  test    rdx, rdx
0x14003b052  jz      short loc_14003B05C
0x14003b054  mov     rax, [rcx+50h]
0x14003b058  mov     ecx, [rax]
0x14003b05a  jmp     short loc_14003B05E
0x14003b05c  xor     ecx, ecx
0x14003b05e  movsxd  rax, ecx
0x14003b061  test    ecx, ecx
0x14003b063  jz      short loc_14003B090
0x14003b065  cmp     rax, rbp
0x14003b068  mov     rbx, rbp
0x14003b06b  mov     rcx, r14; void *
0x14003b06e  cmovb   rbx, rax
0x14003b072  mov     r8, rbx; Size
0x14003b075  call    memcpy_0
0x14003b07a  mov     rax, [rsi+50h]
0x14003b07e  add     r14, rbx
0x14003b081  sub     rdi, rbx
0x14003b084  sub     [rax], ebx
0x14003b086  mov     rcx, [rsi+38h]
0x14003b08a  movsxd  rax, ebx
0x14003b08d  add     [rcx], rax
0x14003b090  cmp     qword ptr [rsi+80h], 0
0x14003b098  jz      short loc_14003B116
0x14003b09a  mov     r8, [rsi+18h]
0x14003b09e  lea     rax, [rsi+70h]
0x14003b0a2  cmp     [r8], rax
0x14003b0a5  jnz     short loc_14003B0C7
0x14003b0a7  mov     rcx, [rsi+88h]
0x14003b0ae  mov     rdx, [rsi+90h]
0x14003b0b5  mov     [r8], rcx
0x14003b0b8  sub     edx, ecx
0x14003b0ba  mov     rax, [rsi+38h]
0x14003b0be  mov     [rax], rcx
0x14003b0c1  mov     rax, [rsi+50h]
0x14003b0c5  mov     [rax], edx
0x14003b0c7  mov     ebx, 0FFFh
0x14003b0cc  jmp     short loc_14003B0F1
0x14003b0ce  mov     r9, [rsi+80h]; Stream
0x14003b0d5  mov     r8, rbx; ElementCount
0x14003b0d8  mov     edx, 1; ElementSize
0x14003b0dd  mov     rcx, r14; Buffer
0x14003b0e0  call    cs:__imp_fread
0x14003b0e6  add     r14, rax
0x14003b0e9  sub     rdi, rax
0x14003b0ec  cmp     rax, rbx
0x14003b0ef  jnz     short loc_14003B116
0x14003b0f1  cmp     rdi, rbx
0x14003b0f4  ja      short loc_14003B0CE
0x14003b0f6  test    rdi, rdi
0x14003b0f9  jz      short loc_14003B116
0x14003b0fb  mov     r9, [rsi+80h]; Stream
0x14003b102  mov     r8, rdi; ElementCount
0x14003b105  mov     edx, 1; ElementSize
0x14003b10a  mov     rcx, r14; Buffer
0x14003b10d  call    cs:__imp_fread
0x14003b113  sub     rdi, rax
0x14003b116  sub     rbp, rdi
0x14003b119  mov     rax, rbp
0x14003b11c  lfence
0x14003b11f  add     rsp, 20h
0x14003b123  pop     r14
0x14003b125  pop     rdi
0x14003b126  pop     rsi
0x14003b127  pop     rbp
0x14003b128  pop     rbx
0x14003b129  retn
```
