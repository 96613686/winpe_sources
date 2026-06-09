# bCopyMonoPointer

- ea: `0x140014540`
- end: `0x140014669`
- name: `bCopyMonoPointer`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014338`

## callees

- `0x140014540`
- `0x140037340`
- `0x140037640`

## pseudocode

```c
__int64 __fastcall bCopyMonoPointer(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  unsigned int v5; // r15d
  __int64 v6; // rax
  char *v7; // rbp
  char *v8; // r14
  __int64 v9; // rcx
  unsigned int v10; // edx
  int v11; // r9d
  char *v12; // rdi
  __int64 v13; // rax
  char *v14; // rbx
  unsigned int v15; // esi
  __int64 v16; // r12
  __int64 v17; // r13
  size_t v18; // r15
  unsigned int v20; // [rsp+50h] [rbp+8h]

  v2 = *(_DWORD *)(a2 + 32);
  if ( v2 > *(_DWORD *)(a1 + 80) )
    return 0;
  v5 = *(_DWORD *)(a2 + 36);
  if ( v5 > 2 * *(_DWORD *)(a1 + 84) )
    return 0;
  v6 = (unsigned int)(*(_DWORD *)(a1 + 28) * *(_DWORD *)(a1 + 24));
  v7 = *(char **)(a1 + 40);
  v8 = &v7[v6];
  memset(v7, 255, (unsigned int)v6);
  memset(v8, 0, (unsigned int)(*(_DWORD *)(a1 + 28) * *(_DWORD *)(a1 + 24)));
  v9 = *(int *)(a2 + 64);
  v10 = (v2 + 7) >> 3;
  v11 = -*(_DWORD *)(a2 + 64);
  if ( *(int *)(a2 + 64) > 0 )
    v11 = *(_DWORD *)(a2 + 64);
  if ( (*(_BYTE *)(a2 + 78) & 1) != 0 )
    v12 = *(char **)(a2 + 48);
  else
    v12 = (char *)(*(_QWORD *)(a2 + 48) + v11 * (v5 - 1));
  v20 = v5 >> 1;
  v13 = *(int *)(a1 + 28);
  v14 = &v12[(int)((v5 >> 1) * v9)];
  v15 = 0;
  if ( v5 >> 1 )
  {
    v16 = v9;
    v17 = v13;
    v18 = v10;
    do
    {
      memmove(v7, v12, v18);
      memmove(v8, v14, v18);
      v12 += v16;
      v14 += v16;
      v7 += v17;
      v8 += v17;
      ++v15;
    }
    while ( v15 < v20 );
  }
  return 1;
}

```

## disassembly

```asm
0x140014540  push    rbx
0x140014542  push    rsi
0x140014543  push    rdi
0x140014544  push    r15
0x140014546  sub     rsp, 28h
0x14001454a  mov     edi, [rdx+20h]
0x14001454d  mov     rbx, rdx
0x140014550  mov     rsi, rcx
0x140014553  cmp     edi, [rcx+50h]
0x140014556  ja      loc_140014655
0x14001455c  mov     eax, [rcx+54h]
0x14001455f  mov     r15d, [rdx+24h]
0x140014563  add     eax, eax
0x140014565  cmp     r15d, eax
0x140014568  ja      loc_140014655
0x14001456e  mov     eax, [rcx+18h]
0x140014571  mov     edx, 0FFh; Val
0x140014576  imul    eax, [rcx+1Ch]
0x14001457a  mov     [rsp+48h+arg_8], rbp
0x14001457f  mov     rbp, [rcx+28h]
0x140014583  mov     [rsp+48h+var_28], r14
0x140014588  mov     rcx, rbp; void *
0x14001458b  mov     r8d, eax; Size
0x14001458e  lea     r14, [rax+rbp]
0x140014592  call    memset
0x140014597  mov     r8d, [rsi+18h]
0x14001459b  xor     edx, edx; Val
0x14001459d  imul    r8d, [rsi+1Ch]; Size
0x1400145a2  mov     rcx, r14; void *
0x1400145a5  call    memset
0x1400145aa  movsxd  rcx, dword ptr [rbx+40h]
0x1400145ae  lea     edx, [rdi+7]
0x1400145b1  mov     r8, [rbx+30h]
0x1400145b5  mov     r9d, ecx
0x1400145b8  shr     edx, 3
0x1400145bb  neg     r9d
0x1400145be  cmovs   r9d, ecx
0x1400145c2  test    byte ptr [rbx+4Eh], 1
0x1400145c6  jz      loc_140014659
0x1400145cc  mov     rdi, r8
0x1400145cf  shr     r15d, 1
0x1400145d2  mov     eax, ecx
0x1400145d4  imul    eax, r15d
0x1400145d8  mov     [rsp+48h+arg_0], r15d
0x1400145dd  movsxd  rbx, eax
0x1400145e0  movsxd  rax, dword ptr [rsi+1Ch]
0x1400145e4  add     rbx, rdi
0x1400145e7  xor     esi, esi
0x1400145e9  test    r15d, r15d
0x1400145ec  jz      short loc_14001463B
0x1400145ee  mov     [rsp+48h+arg_10], r12
0x1400145f3  mov     r12, rcx
0x1400145f6  mov     [rsp+48h+arg_18], r13
0x1400145fb  mov     r13, rax
0x1400145fe  mov     r15d, edx
0x140014601  mov     r8, r15; Size
0x140014604  mov     rdx, rdi; Src
0x140014607  mov     rcx, rbp; void *
0x14001460a  call    memmove
0x14001460f  mov     r8, r15; Size
0x140014612  mov     rdx, rbx; Src
0x140014615  mov     rcx, r14; void *
0x140014618  call    memmove
0x14001461d  add     rdi, r12
0x140014620  add     rbx, r12
0x140014623  add     rbp, r13
0x140014626  add     r14, r13
0x140014629  inc     esi
0x14001462b  cmp     esi, [rsp+48h+arg_0]
0x14001462f  jb      short loc_140014601
0x140014631  mov     r13, [rsp+48h+arg_18]
0x140014636  mov     r12, [rsp+48h+arg_10]
0x14001463b  mov     r14, [rsp+48h+var_28]
0x140014640  mov     eax, 1
0x140014645  mov     rbp, [rsp+48h+arg_8]
0x14001464a  add     rsp, 28h
0x14001464e  pop     r15
0x140014650  pop     rdi
0x140014651  pop     rsi
0x140014652  pop     rbx
0x140014653  retn
0x140014655  xor     eax, eax
0x140014657  jmp     short loc_14001464A
0x140014659  lea     edi, [r15-1]
0x14001465d  imul    edi, r9d
0x140014661  add     rdi, r8
0x140014664  jmp     loc_1400145CF
```
