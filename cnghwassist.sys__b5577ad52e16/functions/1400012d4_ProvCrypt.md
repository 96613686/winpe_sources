# ProvCrypt

- ea: `0x1400012d4`
- end: `0x140001427`
- name: `ProvCrypt`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ad0`
- `0x140001de0`

## callees

- `0x1400012d4`
- `0x140001430`

## import_xrefs

- `ntoskrnl!KeBugCheck` at `0x14000141a`
- `ntoskrnl!KeBugCheck` at `0x14000141a`

## pseudocode

```c
__int64 __fastcall ProvCrypt(
        __int64 a1,
        UCHAR *a2,
        unsigned int a3,
        __int64 a4,
        UCHAR *a5,
        ULONG a6,
        UCHAR *a7,
        ULONG a8,
        _DWORD *a9,
        ULONG a10)
{
  unsigned int v10; // edi
  int v13; // edx
  UCHAR *v14; // r12
  ULONG v15; // r15d
  ULONG v16; // ebx
  int v17; // r14d
  UCHAR *v18; // rsi
  ULONG v20; // [rsp+B0h] [rbp+18h] BYREF

  v20 = 0;
  v10 = a3;
  if ( a4 )
    return (unsigned int)-1073741811;
  v14 = a5;
  v15 = a6;
  if ( a5 && (a6 != 16 || *(_DWORD *)(a1 + 8) == 2) )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v16 = a8;
    v17 = 0;
    v18 = a7;
    if ( a3 <= 0x100000 )
    {
LABEL_10:
      v13 = ProvCryptChunk(a1, a2, v10, 0, v14, v15, v18, v16, &v20, a10);
      if ( v13 >= 0 )
        *a9 = v17 + v20;
    }
    else
    {
      while ( 1 )
      {
        if ( v16 < 0x100000 )
          KeBugCheck(0x6C746166u);
        v13 = ProvCryptChunk(a1, a2, 0x100000u, 0, v14, v15, v18, 0x100000u, &v20, a10 & 0xFFFFFFFE);
        if ( v13 < 0 )
          break;
        v17 += 0x100000;
        a2 += 0x100000;
        v10 -= 0x100000;
        v18 += 0x100000;
        v16 -= 0x100000;
        if ( v10 <= 0x100000 )
          goto LABEL_10;
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400012d4  mov     rax, rsp
0x1400012d7  push    rbx
0x1400012d8  push    rbp
0x1400012d9  push    rsi
0x1400012da  push    rdi
0x1400012db  push    r12
0x1400012dd  push    r13
0x1400012df  push    r14
0x1400012e1  push    r15
0x1400012e3  sub     rsp, 58h
0x1400012e7  mov     dword ptr [rax+18h], 0
0x1400012ee  mov     edi, r8d
0x1400012f1  mov     rbp, rdx
0x1400012f4  mov     r13, rcx
0x1400012f7  test    r9, r9
0x1400012fa  jz      short loc_140001306
0x1400012fc  mov     edx, 0C000000Dh
0x140001301  jmp     loc_140001401
0x140001306  mov     r12, [rsp+98h+arg_20]
0x14000130e  mov     r15d, [rsp+98h+arg_28]
0x140001316  test    r12, r12
0x140001319  jz      short loc_140001327
0x14000131b  cmp     r15d, 10h
0x14000131f  jnz     short loc_1400012FC
0x140001321  cmp     dword ptr [rcx+8], 2
0x140001325  jz      short loc_1400012FC
0x140001327  mov     ebx, [rsp+98h+arg_38]
0x14000132e  xor     r14d, r14d
0x140001331  mov     rsi, [rsp+98h+arg_30]
0x140001339  mov     ecx, 100000h
0x14000133e  cmp     r8d, ecx
0x140001341  jbe     short loc_1400013AB
0x140001343  cmp     ebx, ecx
0x140001345  jb      loc_140001415
0x14000134b  mov     eax, [rsp+98h+arg_48]
0x140001352  mov     r8d, ecx
0x140001355  and     eax, 0FFFFFFFEh
0x140001358  xor     r9d, r9d
0x14000135b  mov     [rsp+98h+var_50], eax
0x14000135f  mov     rdx, rbp
0x140001362  lea     rax, [rsp+98h+arg_10]
0x14000136a  mov     [rsp+98h+var_58], rax
0x14000136f  mov     [rsp+98h+var_60], ecx
0x140001373  mov     rcx, r13
0x140001376  mov     [rsp+98h+var_68], rsi
0x14000137b  mov     [rsp+98h+var_70], r15d
0x140001380  mov     [rsp+98h+var_78], r12
0x140001385  call    ProvCryptChunk
0x14000138a  mov     edx, eax
0x14000138c  test    eax, eax
0x14000138e  js      short loc_140001401
0x140001390  mov     ecx, 100000h
0x140001395  mov     eax, 0FFF00000h
0x14000139a  add     r14d, ecx
0x14000139d  add     rbp, rcx
0x1400013a0  add     edi, eax
0x1400013a2  add     rsi, rcx
0x1400013a5  add     ebx, eax
0x1400013a7  cmp     edi, ecx
0x1400013a9  ja      short loc_140001343
0x1400013ab  mov     eax, [rsp+98h+arg_48]
0x1400013b2  xor     r9d, r9d
0x1400013b5  mov     [rsp+98h+var_50], eax
0x1400013b9  mov     r8d, edi
0x1400013bc  lea     rax, [rsp+98h+arg_10]
0x1400013c4  mov     rdx, rbp
0x1400013c7  mov     [rsp+98h+var_58], rax
0x1400013cc  mov     rcx, r13
0x1400013cf  mov     [rsp+98h+var_60], ebx
0x1400013d3  mov     [rsp+98h+var_68], rsi
0x1400013d8  mov     [rsp+98h+var_70], r15d
0x1400013dd  mov     [rsp+98h+var_78], r12
0x1400013e2  call    ProvCryptChunk
0x1400013e7  mov     edx, eax
0x1400013e9  test    eax, eax
0x1400013eb  js      short loc_140001401
0x1400013ed  mov     rax, [rsp+98h+arg_40]
0x1400013f5  mov     ecx, [rsp+98h+arg_10]
0x1400013fc  add     ecx, r14d
0x1400013ff  mov     [rax], ecx
0x140001401  mov     eax, edx
0x140001403  add     rsp, 58h
0x140001407  pop     r15
0x140001409  pop     r14
0x14000140b  pop     r13
0x14000140d  pop     r12
0x14000140f  pop     rdi
0x140001410  pop     rsi
0x140001411  pop     rbp
0x140001412  pop     rbx
0x140001413  retn
0x140001415  mov     ecx, 6C746166h; BugCheckCode
0x14000141a  call    cs:__imp_KeBugCheck
```
