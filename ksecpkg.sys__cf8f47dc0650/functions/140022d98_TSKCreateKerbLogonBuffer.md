# TSKCreateKerbLogonBuffer

- ea: `0x140022d98`
- end: `0x140022f17`
- name: `TSKCreateKerbLogonBuffer`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140022718`

## callees

- `0x1400102c0`
- `0x1400105c0`
- `0x140020008`
- `0x140022d98`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140022ddd`
- `ntoskrnl!ExAllocatePool2` at `0x140022e21`
- `ntoskrnl!ExAllocatePool2` at `0x140022ddd`
- `ntoskrnl!ExAllocatePool2` at `0x140022e21`

## pseudocode

```c
__int64 __fastcall TSKCreateKerbLogonBuffer(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4)
{
  unsigned int v7; // ebx
  void *Pool2; // rax
  void *v9; // rsi
  unsigned int v10; // r12d
  _WORD *v11; // rax
  _WORD *v12; // r14
  unsigned int v13; // edi
  size_t v14; // r8
  const void *v15; // rdx
  size_t v16; // r8
  char *v17; // rbx
  const void *v18; // rdx
  size_t v19; // r8
  const void *v20; // rdx
  char *v21; // rcx

  v7 = 256;
  if ( TSGlobalPoolType != PagedPool )
    v7 = 64;
  Pool2 = (void *)ExAllocatePool2(v7, 232, 1802531668);
  v9 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  memset(Pool2, 0, 0xE8u);
  v10 = *a2 + *a1 + *a3 + 70;
  v11 = (_WORD *)ExAllocatePool2(v7, v10, 1802531668);
  v12 = v11;
  if ( !v11 )
  {
    TSKFreePrimaryCredentials(v9);
    return (unsigned int)-1073741670;
  }
  v13 = 0;
  memset(v11, 0, v10);
  v14 = *a2;
  v15 = (const void *)*((_QWORD *)a2 + 1);
  *(_DWORD *)v12 = 2;
  v12[4] = v14;
  *((_QWORD *)v12 + 2) = 64;
  v12[5] = v14 + 2;
  memmove(v12 + 32, v15, v14);
  v16 = *a3;
  v17 = (char *)v12 + (unsigned __int16)v12[5] + 64;
  v18 = (const void *)*((_QWORD *)a3 + 1);
  v12[20] = v16;
  v12[21] = v16 + 2;
  *((_QWORD *)v12 + 6) = v17 - (char *)v12;
  memmove(v17, v18, v16);
  v19 = *a1;
  v20 = (const void *)*((_QWORD *)a1 + 1);
  v21 = &v17[(unsigned __int16)v12[21]];
  v12[12] = v19;
  v12[13] = v19 + 2;
  *((_QWORD *)v12 + 4) = v21 - (char *)v12;
  memmove(v21, v20, v19);
  *((_QWORD *)v9 + 19) = v12;
  *((_DWORD *)v9 + 40) = v10;
  *a4 = v9;
  return v13;
}

```

## disassembly

```asm
0x140022d98  mov     [rsp+arg_18], r9
0x140022d9d  push    rbx
0x140022d9e  push    rbp
0x140022d9f  push    rsi
0x140022da0  push    rdi
0x140022da1  push    r12
0x140022da3  push    r13
0x140022da5  push    r14
0x140022da7  push    r15
0x140022da9  sub     rsp, 28h
0x140022dad  cmp     cs:?TSGlobalPoolType@@3W4_POOL_TYPE@@A, 1; _POOL_TYPE TSGlobalPoolType
0x140022db4  mov     r13, rcx
0x140022db7  mov     ecx, 40h ; '@'
0x140022dbc  mov     rbp, r8
0x140022dbf  mov     r15, rdx
0x140022dc2  mov     ebx, 100h
0x140022dc7  cmovnz  ebx, ecx
0x140022dca  mov     edi, 6B707354h
0x140022dcf  mov     r14d, 0E8h
0x140022dd5  mov     ecx, ebx
0x140022dd7  mov     r8d, edi
0x140022dda  mov     edx, r14d
0x140022ddd  call    cs:__imp_ExAllocatePool2
0x140022de4  nop     dword ptr [rax+rax+00h]
0x140022de9  mov     rsi, rax
0x140022dec  test    rax, rax
0x140022def  jz      loc_140022EFE
0x140022df5  mov     r8d, r14d; Size
0x140022df8  xor     edx, edx; Val
0x140022dfa  mov     rcx, rax; void *
0x140022dfd  call    memset
0x140022e02  movzx   edx, word ptr [r13+0]
0x140022e07  mov     r8d, edi
0x140022e0a  movzx   eax, word ptr [r15]
0x140022e0e  mov     ecx, ebx
0x140022e10  movzx   r12d, word ptr [rbp+0]
0x140022e15  add     edx, eax
0x140022e17  add     r12d, 46h ; 'F'
0x140022e1b  add     r12d, edx
0x140022e1e  mov     edx, r12d
0x140022e21  call    cs:__imp_ExAllocatePool2
0x140022e28  nop     dword ptr [rax+rax+00h]
0x140022e2d  mov     r14, rax
0x140022e30  test    rax, rax
0x140022e33  jz      loc_140022EF6
0x140022e39  mov     r8d, r12d; Size
0x140022e3c  xor     edx, edx; Val
0x140022e3e  mov     rcx, rax; void *
0x140022e41  xor     edi, edi
0x140022e43  call    memset
0x140022e48  movzx   r8d, word ptr [r15]; Size
0x140022e4c  lea     ecx, [rdi+2]
0x140022e4f  mov     rdx, [r15+8]; Src
0x140022e53  lea     rbx, [r14+40h]
0x140022e57  mov     [r14], ecx
0x140022e5a  mov     [r14+8], r8w
0x140022e5f  lea     eax, [rcx+r8]
0x140022e63  mov     qword ptr [r14+10h], 40h ; '@'
0x140022e6b  mov     rcx, rbx; void *
0x140022e6e  mov     [r14+0Ah], ax
0x140022e73  call    memmove
0x140022e78  movzx   eax, word ptr [r14+0Ah]
0x140022e7d  lea     r15d, [rdi+2]
0x140022e81  movzx   r8d, word ptr [rbp+0]; Size
0x140022e86  add     rbx, rax
0x140022e89  mov     rdx, [rbp+8]; Src
0x140022e8d  mov     rcx, rbx; void *
0x140022e90  mov     [r14+28h], r8w
0x140022e95  lea     eax, [r15+r8]
0x140022e99  mov     [r14+2Ah], ax
0x140022e9e  mov     rax, rbx
0x140022ea1  sub     rax, r14
0x140022ea4  mov     [r14+30h], rax
0x140022ea8  call    memmove
0x140022ead  movzx   r8d, word ptr [r13+0]; Size
0x140022eb2  movzx   ecx, word ptr [r14+2Ah]
0x140022eb7  mov     rdx, [r13+8]; Src
0x140022ebb  add     rcx, rbx; void *
0x140022ebe  mov     [r14+18h], r8w
0x140022ec3  lea     eax, [r15+r8]
0x140022ec7  mov     [r14+1Ah], ax
0x140022ecc  mov     rax, rcx
0x140022ecf  sub     rax, r14
0x140022ed2  mov     [r14+20h], rax
0x140022ed6  call    memmove
0x140022edb  mov     rax, [rsp+68h+arg_18]
0x140022ee3  mov     [rsi+98h], r14
0x140022eea  mov     [rsi+0A0h], r12d
0x140022ef1  mov     [rax], rsi
0x140022ef4  jmp     short loc_140022F03
0x140022ef6  mov     rcx, rsi; P
0x140022ef9  call    TSKFreePrimaryCredentials
0x140022efe  mov     edi, 0C000009Ah
0x140022f03  mov     eax, edi
0x140022f05  add     rsp, 28h
0x140022f09  pop     r15
0x140022f0b  pop     r14
0x140022f0d  pop     r13
0x140022f0f  pop     r12
0x140022f11  pop     rdi
0x140022f12  pop     rsi
0x140022f13  pop     rbp
0x140022f14  pop     rbx
0x140022f15  retn
```
