# DiscpCreateTargetAddress

- ea: `0x1800060e0`
- end: `0x1800061a1`
- name: `DiscpCreateTargetAddress`
- size: `193`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, int, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006a84`

## callees

- `0x180001cfe`
- `0x18000325c`
- `0x1800060e0`

## import_xrefs

- `ISCSIUM!DiscpTextAddrToBinary` at `0x18000613e`
- `ISCSIUM!DiscpTextAddrToBinary` at `0x18000613e`
- `ISCSIUM!DiscpAllocMemory` at `0x18000611a`
- `ISCSIUM!DiscpAllocMemory` at `0x18000611a`
- `ISCSIUM!DiscpFreeMemory` at `0x180006181`
- `ISCSIUM!DiscpFreeMemory` at `0x180006181`

## pseudocode

```c
__int64 __fastcall DiscpCreateTargetAddress(STRSAFE_LPCWSTR pszSrc, int a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // rax
  unsigned int v9; // ebp
  unsigned int v10; // edi
  char *v11; // rax
  char *v12; // rbx
  __int64 v13; // rdx
  unsigned int v14; // edi

  v4 = -1;
  do
    ++v4;
  while ( pszSrc[v4] );
  v9 = v4 + 1;
  v10 = 2 * (v4 + 1) + 120;
  v11 = (char *)DiscpAllocMemory(v10);
  v12 = v11;
  if ( v11 )
  {
    memset_0(v11, 0, v10);
    LOBYTE(v13) = 1;
    v14 = DiscpTextAddrToBinary(pszSrc, v13, v12 + 56);
    if ( v14 )
    {
      DiscpFreeMemory(v12);
    }
    else
    {
      *((_QWORD *)v12 + 5) = v12 + 32;
      *((_QWORD *)v12 + 4) = v12 + 32;
      *((_QWORD *)v12 + 6) = v12 + 120;
      *((_DWORD *)v12 + 4) = 1;
      *((_DWORD *)v12 + 6) = a2;
      *((_QWORD *)v12 + 11) = a3;
      StringCchCopyW((STRSAFE_LPWSTR)v12 + 60, v9, pszSrc);
      *a4 = v12;
      return 0;
    }
  }
  else
  {
    return 8;
  }
  return v14;
}

```

## disassembly

```asm
0x1800060e0  push    rbx
0x1800060e2  push    rbp
0x1800060e3  push    rsi
0x1800060e4  push    rdi
0x1800060e5  push    r12
0x1800060e7  push    r13
0x1800060e9  push    r14
0x1800060eb  push    r15
0x1800060ed  sub     rsp, 28h
0x1800060f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800060f5  mov     r14, r9
0x1800060f8  xor     r13d, r13d
0x1800060fb  mov     r15, r8
0x1800060fe  mov     r12d, edx
0x180006101  mov     rsi, rcx
0x180006104  inc     rax
0x180006107  cmp     [rcx+rax*2], r13w
0x18000610c  jnz     short loc_180006104
0x18000610e  lea     ebp, [rax+1]
0x180006111  lea     edi, ds:78h[rbp*2]
0x180006118  mov     ecx, edi
0x18000611a  call    cs:__imp_DiscpAllocMemory
0x180006120  mov     rbx, rax
0x180006123  test    rax, rax
0x180006126  jz      short loc_180006189
0x180006128  mov     r8d, edi; Size
0x18000612b  xor     edx, edx; Val
0x18000612d  mov     rcx, rax; void *
0x180006130  call    memset_0
0x180006135  lea     r8, [rbx+38h]
0x180006139  mov     dl, 1
0x18000613b  mov     rcx, rsi
0x18000613e  call    cs:__imp_DiscpTextAddrToBinary
0x180006144  mov     edi, eax
0x180006146  test    eax, eax
0x180006148  jnz     short loc_18000617E
0x18000614a  lea     rax, [rbx+20h]
0x18000614e  mov     edx, ebp; cchDest
0x180006150  lea     rcx, [rbx+78h]; pszDest
0x180006154  mov     [rax+8], rax
0x180006158  mov     r8, rsi; pszSrc
0x18000615b  mov     [rax], rax
0x18000615e  mov     [rbx+30h], rcx
0x180006162  mov     dword ptr [rbx+10h], 1
0x180006169  mov     [rbx+18h], r12d
0x18000616d  mov     [rbx+58h], r15
0x180006171  call    StringCchCopyW
0x180006176  mov     [r14], rbx
0x180006179  mov     edi, r13d
0x18000617c  jmp     short loc_18000618E
0x18000617e  mov     rcx, rbx
0x180006181  call    cs:__imp_DiscpFreeMemory
0x180006187  jmp     short loc_18000618E
0x180006189  mov     edi, 8
0x18000618e  mov     eax, edi
0x180006190  add     rsp, 28h
0x180006194  pop     r15
0x180006196  pop     r14
0x180006198  pop     r13
0x18000619a  pop     r12
0x18000619c  pop     rdi
0x18000619d  pop     rsi
0x18000619e  pop     rbp
0x18000619f  pop     rbx
0x1800061a0  retn
```
