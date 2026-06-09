# ASN1_CreateEncoder

- ea: `0x180007980`
- end: `0x180007ab2`
- name: `ASN1_CreateEncoder`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800078b0`

## callees

- `0x180007980`
- `0x180007c70`
- `0x180009b8a`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007aa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007aa5`

## pseudocode

```c
__int64 __fastcall ASN1_CreateEncoder(__int64 a1, _QWORD *a2, _BYTE *a3, int a4, __int64 a5)
{
  _BYTE **v9; // rax
  _BYTE **v10; // rbx
  int v11; // eax
  int v12; // ecx

  if ( !a1 || !a2 )
    return 4294966287LL;
  *a2 = 0;
  v9 = (_BYTE **)LocalAlloc(0x40u, 0x50u);
  v10 = v9;
  if ( !v9 )
    return 4294966290LL;
  memset_0(v9, 0, 0x50u);
  *(_DWORD *)v10 = 1145261637;
  v11 = *(_DWORD *)(a1 + 8);
  *((_DWORD *)v10 + 14) = v11;
  v10[1] = (_BYTE *)a1;
  if ( a3 )
  {
    if ( a4 )
    {
      v11 |= 8u;
      v10[2] = a3;
      *((_DWORD *)v10 + 14) = v11;
      v10[5] = a3;
      *((_DWORD *)v10 + 6) = a4;
    }
  }
  if ( !a5 )
  {
    v10[8] = v10;
    *((_DWORD *)v10 + 13) = *(_DWORD *)(a1 + 4);
    goto LABEL_11;
  }
  v10[8] = (_BYTE *)a5;
  v12 = *(_DWORD *)(a5 + 52);
  *((_DWORD *)v10 + 13) = v12;
  if ( (v11 & 8) == 0 )
  {
    if ( (v12 & 0x700) == 0 )
    {
      LocalFree(v10);
      return 4294966283LL;
    }
    if ( (unsigned int)ASN1EncCheck(v10, 1) )
    {
      *v10[2] = 0;
      goto LABEL_10;
    }
    LocalFree(v10);
    return 4294966290LL;
  }
LABEL_10:
  *(_QWORD *)(a5 + 72) = v10;
LABEL_11:
  *a2 = v10;
  return 0;
}

```

## disassembly

```asm
0x180007980  mov     [rsp+arg_10], rbp
0x180007985  push    rsi
0x180007986  push    rdi
0x180007987  push    r14
0x180007989  sub     rsp, 20h
0x18000798d  mov     r14d, r9d
0x180007990  mov     rbp, r8
0x180007993  mov     rdi, rdx
0x180007996  mov     rsi, rcx
0x180007999  test    rcx, rcx
0x18000799c  jz      loc_180007A72
0x1800079a2  test    rdx, rdx
0x1800079a5  jz      loc_180007A72
0x1800079ab  mov     qword ptr [rdx], 0
0x1800079b2  mov     ecx, 40h ; '@'; uFlags
0x1800079b7  mov     edx, 50h ; 'P'; uBytes
0x1800079bc  mov     [rsp+38h+arg_8], rbx
0x1800079c1  call    cs:__imp_LocalAlloc
0x1800079c7  mov     rbx, rax
0x1800079ca  test    rax, rax
0x1800079cd  jz      loc_180007A6B
0x1800079d3  xor     edx, edx; Val
0x1800079d5  mov     r8d, 50h ; 'P'; Size
0x1800079db  mov     rcx, rax; void *
0x1800079de  call    memset_0
0x1800079e3  mov     dword ptr [rbx], 44434E45h
0x1800079e9  mov     eax, [rsi+8]
0x1800079ec  mov     [rbx+38h], eax
0x1800079ef  mov     [rbx+8], rsi
0x1800079f3  test    rbp, rbp
0x1800079f6  jnz     loc_180007A85
0x1800079fc  mov     rbp, [rsp+38h+arg_20]
0x180007a01  test    rbp, rbp
0x180007a04  jz      short loc_180007A56
0x180007a06  mov     [rbx+40h], rbp
0x180007a0a  mov     ecx, [rbp+34h]
0x180007a0d  mov     [rbx+34h], ecx
0x180007a10  bt      eax, 3
0x180007a14  jb      short loc_180007A3A
0x180007a16  test    ecx, 700h
0x180007a1c  mov     rcx, rbx; hMem
0x180007a1f  jz      loc_180007AA5
0x180007a25  mov     edx, 1
0x180007a2a  call    ASN1EncCheck
0x180007a2f  test    eax, eax
0x180007a31  jz      short loc_180007A62
0x180007a33  mov     rax, [rbx+10h]
0x180007a37  mov     byte ptr [rax], 0
0x180007a3a  mov     [rbp+48h], rbx
0x180007a3e  mov     [rdi], rbx
0x180007a41  xor     eax, eax
0x180007a43  mov     rbx, [rsp+38h+arg_8]
0x180007a48  mov     rbp, [rsp+38h+arg_10]
0x180007a4d  add     rsp, 20h
0x180007a51  pop     r14
0x180007a53  pop     rdi
0x180007a54  pop     rsi
0x180007a55  retn
0x180007a56  mov     [rbx+40h], rbx
0x180007a5a  mov     eax, [rsi+4]
0x180007a5d  mov     [rbx+34h], eax
0x180007a60  jmp     short loc_180007A3E
0x180007a62  mov     rcx, rbx; hMem
0x180007a65  call    cs:__imp_LocalFree
0x180007a6b  mov     eax, 0FFFFFC12h
0x180007a70  jmp     short loc_180007A43
0x180007a72  mov     rbp, [rsp+38h+arg_10]
0x180007a77  mov     eax, 0FFFFFC0Fh
0x180007a7c  add     rsp, 20h
0x180007a80  pop     r14
0x180007a82  pop     rdi
0x180007a83  pop     rsi
0x180007a84  retn
0x180007a85  test    r14d, r14d
0x180007a88  jz      loc_1800079FC
0x180007a8e  or      eax, 8
0x180007a91  mov     [rbx+10h], rbp
0x180007a95  mov     [rbx+38h], eax
0x180007a98  mov     [rbx+28h], rbp
0x180007a9c  mov     [rbx+18h], r14d
0x180007aa0  jmp     loc_1800079FC
0x180007aa5  call    cs:__imp_LocalFree
0x180007aab  mov     eax, 0FFFFFC0Bh
0x180007ab0  jmp     short loc_180007A43
```
