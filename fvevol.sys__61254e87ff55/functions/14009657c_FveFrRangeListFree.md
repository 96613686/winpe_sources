# FveFrRangeListFree

- ea: `0x14009657c`
- end: `0x1400966b8`
- name: `FveFrRangeListFree`
- size: `316`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14002f3d8`
- `0x14005a27c`
- `0x140072194`
- `0x140079a40`
- `0x140095ec0`
- `0x1400960d0`
- `0x1400962dc`
- `0x1400c20e0`
- `0x1400c5f08`

## callees

- `0x140018b38`
- `0x140022bf0`
- `0x140023040`
- `0x14009657c`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14009660f`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14009660f`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400965dc`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400965dc`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140096686`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140096686`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400965f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096627`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400966aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400965f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096627`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400966aa`

## pseudocode

```c
void *__fastcall FveFrRangeListFree(char *a1)
{
  char *v2; // rax
  __int64 v3; // rcx
  char **v4; // rdx
  _QWORD *v5; // rax
  struct _RTL_AVL_TABLE *v6; // rcx
  void *v7; // rcx
  __int128 Buffer; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h]

  v10 = 0;
  Buffer = 0;
  if ( *((_QWORD *)a1 + 2) )
  {
    v2 = a1 + 72;
    v3 = *((_QWORD *)a1 + 9);
    if ( (char *)v3 != v2 )
    {
      if ( *(char **)(v3 + 8) != v2 || (v4 = (char **)*((_QWORD *)v2 + 1), *v4 != v2) )
        __fastfail(3u);
      *v4 = (char *)v3;
      *(_QWORD *)(v3 + 8) = v4;
    }
    while ( 1 )
    {
      v5 = RtlEnumerateGenericTableAvl(*(PRTL_AVL_TABLE *)a1, 1u);
      v6 = *(struct _RTL_AVL_TABLE **)a1;
      if ( !v5 )
        break;
      Buffer = *(_OWORD *)v5;
      HIDWORD(v10) = HIDWORD(v5[2]);
      LODWORD(v10) = 3;
      RtlDeleteElementGenericTableAvl(v6, &Buffer);
    }
    if ( v6 )
    {
      ExFreePoolWithTag(v6, *((_DWORD *)a1 + 15));
      *(_QWORD *)a1 = 0;
    }
    ExDeleteLookasideListEx(*((PLOOKASIDE_LIST_EX *)a1 + 1));
    v7 = (void *)*((_QWORD *)a1 + 1);
    if ( v7 )
    {
      ExFreePoolWithTag(v7, *((_DWORD *)a1 + 15));
      *((_QWORD *)a1 + 1) = 0;
    }
    if ( *((_QWORD *)a1 + 8) )
    {
      FveRangeListFree();
      ExFreePoolWithTag(*((PVOID *)a1 + 8), *((_DWORD *)a1 + 14));
    }
  }
  return memset(a1, 0, 0x58u);
}

```

## disassembly

```asm
0x14009657c  push    rbx
0x14009657e  sub     rsp, 40h
0x140096582  mov     rax, cs:__security_cookie
0x140096589  xor     rax, rsp
0x14009658c  mov     [rsp+48h+var_10], rax
0x140096591  xor     eax, eax
0x140096593  xorps   xmm0, xmm0
0x140096596  mov     rbx, rcx
0x140096599  mov     [rsp+48h+var_18], rax
0x14009659e  movups  [rsp+48h+Buffer], xmm0
0x1400965a3  cmp     [rcx+10h], rax
0x1400965a7  jz      loc_140096644
0x1400965ad  lea     rax, [rcx+48h]
0x1400965b1  mov     rcx, [rax]
0x1400965b4  cmp     rcx, rax
0x1400965b7  jz      short loc_1400965D7
0x1400965b9  cmp     [rcx+8], rax
0x1400965bd  jnz     loc_140096697
0x1400965c3  mov     rdx, [rax+8]
0x1400965c7  cmp     [rdx], rax
0x1400965ca  jnz     loc_140096697
0x1400965d0  mov     [rdx], rcx
0x1400965d3  mov     [rcx+8], rdx
0x1400965d7  mov     rcx, [rbx]; Table
0x1400965da  mov     dl, 1; Restart
0x1400965dc  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400965e3  nop     dword ptr [rax+rax+00h]
0x1400965e8  mov     rcx, [rbx]; Table
0x1400965eb  test    rax, rax
0x1400965ee  jnz     short loc_140096666
0x1400965f0  test    rcx, rcx
0x1400965f3  jz      short loc_14009660B
0x1400965f5  mov     edx, [rbx+3Ch]; Tag
0x1400965f8  call    cs:__imp_ExFreePoolWithTag
0x1400965ff  nop     dword ptr [rax+rax+00h]
0x140096604  mov     qword ptr [rbx], 0
0x14009660b  mov     rcx, [rbx+8]; Lookaside
0x14009660f  call    cs:__imp_ExDeleteLookasideListEx
0x140096616  nop     dword ptr [rax+rax+00h]
0x14009661b  mov     rcx, [rbx+8]; P
0x14009661f  test    rcx, rcx
0x140096622  jz      short loc_14009663B
0x140096624  mov     edx, [rbx+3Ch]; Tag
0x140096627  call    cs:__imp_ExFreePoolWithTag
0x14009662e  nop     dword ptr [rax+rax+00h]
0x140096633  mov     qword ptr [rbx+8], 0
0x14009663b  mov     rcx, [rbx+40h]
0x14009663f  test    rcx, rcx
0x140096642  jnz     short loc_14009669E
0x140096644  xor     edx, edx; Val
0x140096646  mov     rcx, rbx; void *
0x140096649  lea     r8d, [rdx+58h]; Size
0x14009664d  call    memset
0x140096652  mov     rcx, [rsp+48h+var_10]
0x140096657  xor     rcx, rsp; StackCookie
0x14009665a  call    __security_check_cookie
0x14009665f  add     rsp, 40h
0x140096663  pop     rbx
0x140096664  retn
0x140096666  movups  xmm0, xmmword ptr [rax]
0x140096669  lea     rdx, [rsp+48h+Buffer]; Buffer
0x14009666e  movups  [rsp+48h+Buffer], xmm0
0x140096673  movsd   xmm1, qword ptr [rax+10h]
0x140096678  movsd   [rsp+48h+var_18], xmm1
0x14009667e  mov     dword ptr [rsp+48h+var_18], 3
0x140096686  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14009668d  nop     dword ptr [rax+rax+00h]
0x140096692  jmp     loc_1400965D7
0x140096697  mov     ecx, 3
0x14009669c  int     29h; Win8: RtlFailFast(ecx)
0x14009669e  call    FveRangeListFree
0x1400966a3  mov     edx, [rbx+38h]; Tag
0x1400966a6  mov     rcx, [rbx+40h]; P
0x1400966aa  call    cs:__imp_ExFreePoolWithTag
0x1400966b1  nop     dword ptr [rax+rax+00h]
0x1400966b6  jmp     short loc_140096644
```
