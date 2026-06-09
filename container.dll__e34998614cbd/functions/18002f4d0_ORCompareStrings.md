# ORCompareStrings

- ea: `0x18002f4d0`
- end: `0x18002f625`
- name: `ORCompareStrings`
- size: `341`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d694`
- `0x18002d854`
- `0x18002f034`

## callees

- `0x18002f3f8`
- `0x18002f4d0`
- `0x18002f62c`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18002f55a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002f581`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002f55a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002f581`

## pseudocode

```c
__int64 __fastcall ORCompareStrings(int a1, __int64 a2, unsigned __int64 a3, int a4, __int64 a5, unsigned __int64 a6)
{
  __int64 v6; // rax
  __int64 v9; // r12
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  bool v12; // zf
  unsigned int v13; // ebx
  unsigned int v14; // r14d
  unsigned int v15; // r15d
  _QWORD v17[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v18; // [rsp+30h] [rbp-18h] BYREF

  v6 = a5;
  v18 = 0;
  if ( !a4 )
  {
    LOWORD(v18) = a6;
    WORD1(v18) = a6;
    *((_QWORD *)&v18 + 1) = a5;
  }
  if ( a1 )
  {
    if ( a4 )
    {
      v9 = 0;
      v10 = a3;
      v11 = a6;
      v12 = a3 == 0;
      v13 = 1;
      while ( 1 )
      {
        *(_QWORD *)&v18 = v11;
        v17[0] = v10;
        if ( v12 || !v11 )
          break;
        v14 = *(unsigned __int8 *)(v9 + a2);
        v15 = *(unsigned __int8 *)(v6 + v9);
        if ( (_WORD)v14 != (_WORD)v15 )
        {
          if ( v14 >= 0x61 )
          {
            if ( v14 <= 0x7A )
              LOWORD(v14) = v14 - 32;
            else
              LOWORD(v14) = RtlUpcaseUnicodeChar(*(unsigned __int8 *)(v9 + a2));
          }
          if ( v15 >= 0x61 )
          {
            if ( v15 <= 0x7A )
              LOWORD(v15) = v15 - 32;
            else
              LOWORD(v15) = RtlUpcaseUnicodeChar(v15);
          }
          if ( (unsigned __int16)v14 < (unsigned __int16)v15 )
            return (unsigned int)-1;
          if ( (unsigned __int16)v14 > (unsigned __int16)v15 )
            return v13;
          v6 = a5;
          v11 = v18;
          v10 = v17[0];
        }
        --v10;
        --v11;
        ++v9;
        v12 = v10 == 0;
      }
      if ( a3 <= a6 )
        return (unsigned int)-(a3 < a6);
      return v13;
    }
    else
    {
      return (unsigned int)-ORCompareCompressedString(&v18, a2, a3);
    }
  }
  else
  {
    LOWORD(v17[0]) = a3;
    HIDWORD(v17[0]) = 0;
    WORD1(v17[0]) = a3;
    v17[1] = a2;
    if ( a4 )
      return ORCompareCompressedString(v17, a5, a6);
    else
      return ORCompareUnicodeString(v17, &v18);
  }
}

```

## disassembly

```asm
0x18002f4d0  push    rbp
0x18002f4d2  push    rbx
0x18002f4d3  push    rsi
0x18002f4d4  push    rdi
0x18002f4d5  push    r12
0x18002f4d7  push    r13
0x18002f4d9  push    r14
0x18002f4db  push    r15
0x18002f4dd  mov     rbp, rsp
0x18002f4e0  sub     rsp, 48h
0x18002f4e4  mov     rsi, [rbp+arg_28]
0x18002f4e8  xorps   xmm0, xmm0
0x18002f4eb  mov     rax, [rbp+arg_20]
0x18002f4ef  mov     rdi, r8
0x18002f4f2  mov     r13, rdx
0x18002f4f5  movups  [rbp+var_18], xmm0
0x18002f4f9  test    r9d, r9d
0x18002f4fc  jnz     short loc_18002F50A
0x18002f4fe  mov     word ptr [rbp+var_18], si
0x18002f502  mov     word ptr [rbp+var_18+2], si
0x18002f506  mov     qword ptr [rbp+var_18+8], rax
0x18002f50a  test    ecx, ecx
0x18002f50c  jz      loc_18002F5E3
0x18002f512  test    r9d, r9d
0x18002f515  jz      loc_18002F5D6
0x18002f51b  xor     r12d, r12d
0x18002f51e  mov     rdx, rdi
0x18002f521  mov     rcx, rsi
0x18002f524  test    rdi, rdi
0x18002f527  lea     ebx, [r12+1]
0x18002f52c  jmp     loc_18002F5B8
0x18002f531  test    rcx, rcx
0x18002f534  jz      loc_18002F5C6
0x18002f53a  movzx   r14d, byte ptr [r12+r13]
0x18002f53f  movzx   r15d, byte ptr [rax+r12]
0x18002f544  cmp     r14w, r15w
0x18002f548  jz      short loc_18002F5AC
0x18002f54a  cmp     r14d, 61h ; 'a'
0x18002f54e  jb      short loc_18002F571
0x18002f550  cmp     r14d, 7Ah ; 'z'
0x18002f554  jbe     short loc_18002F56C
0x18002f556  movzx   ecx, r14w; Source
0x18002f55a  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002f561  nop     dword ptr [rax+rax+00h]
0x18002f566  movzx   r14d, ax
0x18002f56a  jmp     short loc_18002F571
0x18002f56c  sub     r14w, 20h ; ' '
0x18002f571  cmp     r15d, 61h ; 'a'
0x18002f575  jb      short loc_18002F598
0x18002f577  cmp     r15d, 7Ah ; 'z'
0x18002f57b  jbe     short loc_18002F593
0x18002f57d  movzx   ecx, r15w; Source
0x18002f581  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002f588  nop     dword ptr [rax+rax+00h]
0x18002f58d  movzx   r15d, ax
0x18002f591  jmp     short loc_18002F598
0x18002f593  sub     r15w, 20h ; ' '
0x18002f598  cmp     r14w, r15w
0x18002f59c  jb      short loc_18002F5D1
0x18002f59e  ja      short loc_18002F5CD
0x18002f5a0  mov     rax, [rbp+arg_20]
0x18002f5a4  mov     rcx, qword ptr [rbp+var_18]
0x18002f5a8  mov     rdx, [rbp+var_28]
0x18002f5ac  sub     rdx, rbx
0x18002f5af  sub     rcx, rbx
0x18002f5b2  add     r12, rbx
0x18002f5b5  test    rdx, rdx
0x18002f5b8  mov     qword ptr [rbp+var_18], rcx
0x18002f5bc  mov     [rbp+var_28], rdx
0x18002f5c0  jnz     loc_18002F531
0x18002f5c6  cmp     rdi, rsi
0x18002f5c9  ja      short loc_18002F5CD
0x18002f5cb  sbb     ebx, ebx
0x18002f5cd  mov     eax, ebx
0x18002f5cf  jmp     short loc_18002F613
0x18002f5d1  or      ebx, 0FFFFFFFFh
0x18002f5d4  jmp     short loc_18002F5CD
0x18002f5d6  lea     rcx, [rbp+var_18]
0x18002f5da  call    ORCompareCompressedString
0x18002f5df  neg     eax
0x18002f5e1  jmp     short loc_18002F613
0x18002f5e3  xor     ecx, ecx
0x18002f5e5  mov     word ptr [rbp+var_28], di
0x18002f5e9  mov     dword ptr [rbp+var_28+4], ecx
0x18002f5ec  lea     rcx, [rbp+var_28]
0x18002f5f0  mov     word ptr [rbp+var_28+2], di
0x18002f5f4  mov     [rbp+var_20], r13
0x18002f5f8  test    r9d, r9d
0x18002f5fb  jz      short loc_18002F60A
0x18002f5fd  mov     r8, rsi
0x18002f600  mov     rdx, rax
0x18002f603  call    ORCompareCompressedString
0x18002f608  jmp     short loc_18002F613
0x18002f60a  lea     rdx, [rbp+var_18]
0x18002f60e  call    ORCompareUnicodeString
0x18002f613  add     rsp, 48h
0x18002f617  pop     r15
0x18002f619  pop     r14
0x18002f61b  pop     r13
0x18002f61d  pop     r12
0x18002f61f  pop     rdi
0x18002f620  pop     rsi
0x18002f621  pop     rbx
0x18002f622  pop     rbp
0x18002f623  retn
```
