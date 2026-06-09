# Pku2uBuildFullServiceName

- ea: `0x14000d9b0`
- end: `0x14000da8d`
- name: `Pku2uBuildFullServiceName`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1400291a0`

## callees

- `0x14000d9b0`
- `0x1400102c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000da06`
- `ntoskrnl!ExAllocatePool2` at `0x14000da06`

## pseudocode

```c
__int64 __fastcall Pku2uBuildFullServiceName(const void **a1, const void **a2, __int64 a3)
{
  int v3; // r9d
  int v5; // edx
  unsigned int v6; // edx
  __int64 v9; // rdx
  char *Pool2; // rax
  char *v11; // rbp
  __int64 v12; // rcx
  char *v13; // rax
  char *v14; // rbx
  char *v15; // rbx
  __int64 result; // rax

  v3 = *(unsigned __int16 *)a1;
  v5 = *(unsigned __int16 *)a2 + 2;
  *(_QWORD *)(a3 + 8) = 0;
  v6 = v3 + v5;
  if ( v6 >= 0xFFFD )
    return 3221225495LL;
  *(_WORD *)a3 = v6;
  v9 = (unsigned __int16)(v6 + 2);
  *(_WORD *)(a3 + 2) = v9;
  Pool2 = (char *)ExAllocatePool2(256, v9, 1130525264);
  *(_QWORD *)(a3 + 8) = Pool2;
  v11 = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  memmove(Pool2, a1[1], *(unsigned __int16 *)a1);
  v12 = *(unsigned __int16 *)a1;
  v13 = &v11[v12];
  v14 = &v11[v12];
  if ( (_WORD)v12 )
  {
    if ( *(_WORD *)a2 )
    {
      *(_WORD *)v13 = 92;
      v14 = v13 + 2;
    }
  }
  memmove(v14, a2[1], *(unsigned __int16 *)a2);
  v15 = &v14[*(unsigned __int16 *)a2];
  *(_WORD *)a3 = (_WORD)v15 - *(_WORD *)(a3 + 8);
  result = 0;
  *(_WORD *)v15 = 0;
  return result;
}

```

## disassembly

```asm
0x14000d9b0  mov     [rsp+arg_8], rbx
0x14000d9b5  mov     [rsp+arg_10], rbp
0x14000d9ba  push    rsi
0x14000d9bb  push    rdi
0x14000d9bc  push    r14
0x14000d9be  sub     rsp, 20h
0x14000d9c2  movzx   r9d, word ptr [rcx]
0x14000d9c6  mov     rdi, rdx
0x14000d9c9  movzx   edx, word ptr [rdx]
0x14000d9cc  xor     r14d, r14d
0x14000d9cf  add     edx, 2
0x14000d9d2  mov     [r8+8], r14
0x14000d9d6  add     edx, r9d
0x14000d9d9  mov     rsi, r8
0x14000d9dc  mov     rbx, rcx
0x14000d9df  cmp     edx, 0FFFDh
0x14000d9e5  jnb     loc_14000DA74
0x14000d9eb  mov     [r8], dx
0x14000d9ef  add     dx, 2
0x14000d9f3  movzx   edx, dx
0x14000d9f6  mov     [r8+2], dx
0x14000d9fb  mov     ecx, 100h
0x14000da00  mov     r8d, 43627250h
0x14000da06  call    cs:__imp_ExAllocatePool2
0x14000da0d  nop     dword ptr [rax+rax+00h]
0x14000da12  mov     [rsi+8], rax
0x14000da16  mov     rbp, rax
0x14000da19  test    rax, rax
0x14000da1c  jz      short loc_14000DA74
0x14000da1e  movzx   r8d, word ptr [rbx]; Size
0x14000da22  mov     rcx, rax; void *
0x14000da25  mov     rdx, [rbx+8]; Src
0x14000da29  call    memmove
0x14000da2e  movzx   ecx, word ptr [rbx]
0x14000da31  lea     rax, [rcx+rbp]
0x14000da35  mov     rbx, rax
0x14000da38  test    cx, cx
0x14000da3b  jz      short loc_14000DA4C
0x14000da3d  cmp     [rdi], r14w
0x14000da41  jz      short loc_14000DA4C
0x14000da43  mov     word ptr [rax], 5Ch ; '\'
0x14000da48  lea     rbx, [rax+2]
0x14000da4c  movzx   r8d, word ptr [rdi]; Size
0x14000da50  mov     rcx, rbx; void *
0x14000da53  mov     rdx, [rdi+8]; Src
0x14000da57  call    memmove
0x14000da5c  movzx   eax, word ptr [rdi]
0x14000da5f  add     rbx, rax
0x14000da62  movzx   eax, bx
0x14000da65  sub     ax, [rsi+8]
0x14000da69  mov     [rsi], ax
0x14000da6c  xor     eax, eax
0x14000da6e  mov     [rbx], r14w
0x14000da72  jmp     short loc_14000DA79
0x14000da74  mov     eax, 0C0000017h
0x14000da79  mov     rbx, [rsp+38h+arg_8]
0x14000da7e  mov     rbp, [rsp+38h+arg_10]
0x14000da83  add     rsp, 20h
0x14000da87  pop     r14
0x14000da89  pop     rdi
0x14000da8a  pop     rsi
0x14000da8b  retn
```
