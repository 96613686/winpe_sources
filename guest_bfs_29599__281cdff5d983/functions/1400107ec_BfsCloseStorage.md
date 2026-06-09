# BfsCloseStorage

- ea: `0x1400107ec`
- end: `0x1400108fa`
- name: `BfsCloseStorage`
- size: `270`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400061d0`
- `0x14000ceb4`

## callees

- `0x1400107ec`
- `0x140011404`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140010891`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140010891`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400108bd`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400108bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001081a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001084e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001085f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010879`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400108e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001081a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001084e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001085f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010879`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400108e2`
- `FLTMGR!FltClose` at `0x140010803`
- `FLTMGR!FltClose` at `0x140010803`

## pseudocode

```c
void __fastcall BfsCloseStorage(_QWORD *P)
{
  void *v2; // rcx
  void *v3; // rcx
  void **v4; // rbx
  void *v5; // rdi
  void **v6; // rax
  struct _RTL_AVL_TABLE *v7; // rbx
  char *p_DeleteCount; // rdi

  v2 = (void *)P[1];
  if ( v2 )
    FltClose(v2);
  v3 = (void *)P[2];
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  v4 = (void **)P[8];
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( *((void ***)v5 + 1) != v4 || (v6 = *(void ***)v5, *(void **)(*(_QWORD *)v5 + 8LL) != v5) )
      __fastfail(3u);
    *v4 = v6;
    v6[1] = v4;
    ExFreePoolWithTag(*((PVOID *)v5 + 2), 0);
    ExFreePoolWithTag(v5, 0);
  }
  ExFreePoolWithTag(v4, 0);
  v7 = (struct _RTL_AVL_TABLE *)(P + 10);
  while ( 1 )
  {
    p_DeleteCount = (char *)RtlEnumerateGenericTableAvl(v7, 1u);
    if ( !p_DeleteCount )
      break;
LABEL_15:
    if ( RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(p_DeleteCount + 40)) )
      BfsDereferenceTableEntry((volatile signed __int32 *)p_DeleteCount);
    else
      v7 = (struct _RTL_AVL_TABLE *)(p_DeleteCount + 40);
  }
  if ( v7 != (struct _RTL_AVL_TABLE *)(P + 10) )
  {
    p_DeleteCount = (char *)&v7[-1].DeleteCount;
    v7 = (struct _RTL_AVL_TABLE *)&v7[1].BalancedRoot.Parent[1];
    goto LABEL_15;
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x1400107ec  push    rbx
0x1400107ee  push    rbp
0x1400107ef  push    rsi
0x1400107f0  push    rdi
0x1400107f1  push    r14
0x1400107f3  sub     rsp, 20h
0x1400107f7  mov     rsi, rcx
0x1400107fa  mov     rcx, [rcx+8]; FileHandle
0x1400107fe  test    rcx, rcx
0x140010801  jz      short loc_14001080F
0x140010803  call    cs:__imp_FltClose
0x14001080a  nop     dword ptr [rax+rax+00h]
0x14001080f  mov     rcx, [rsi+10h]; P
0x140010813  test    rcx, rcx
0x140010816  jz      short loc_140010826
0x140010818  xor     edx, edx; Tag
0x14001081a  call    cs:__imp_ExFreePoolWithTag
0x140010821  nop     dword ptr [rax+rax+00h]
0x140010826  mov     rbx, [rsi+40h]
0x14001082a  mov     rdi, [rbx]
0x14001082d  cmp     rdi, rbx
0x140010830  jz      short loc_140010874
0x140010832  cmp     [rdi+8], rbx
0x140010836  jnz     short loc_14001086D
0x140010838  mov     rax, [rdi]
0x14001083b  cmp     [rax+8], rdi
0x14001083f  jnz     short loc_14001086D
0x140010841  mov     [rbx], rax
0x140010844  xor     edx, edx; Tag
0x140010846  mov     [rax+8], rbx
0x14001084a  mov     rcx, [rdi+10h]; P
0x14001084e  call    cs:__imp_ExFreePoolWithTag
0x140010855  nop     dword ptr [rax+rax+00h]
0x14001085a  xor     edx, edx; Tag
0x14001085c  mov     rcx, rdi; P
0x14001085f  call    cs:__imp_ExFreePoolWithTag
0x140010866  nop     dword ptr [rax+rax+00h]
0x14001086b  jmp     short loc_14001082A
0x14001086d  mov     ecx, 3
0x140010872  int     29h; Win8: RtlFailFast(ecx)
0x140010874  xor     edx, edx; Tag
0x140010876  mov     rcx, rbx; P
0x140010879  call    cs:__imp_ExFreePoolWithTag
0x140010880  nop     dword ptr [rax+rax+00h]
0x140010885  lea     rbp, [rsi+50h]
0x140010889  mov     rbx, rbp
0x14001088c  mov     dl, 1; Restart
0x14001088e  mov     rcx, rbx; Table
0x140010891  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140010898  nop     dword ptr [rax+rax+00h]
0x14001089d  mov     rdi, rax
0x1400108a0  test    rax, rax
0x1400108a3  jnz     short loc_1400108B9
0x1400108a5  cmp     rbx, rbp
0x1400108a8  jz      short loc_1400108DD
0x1400108aa  lea     rdi, [rbx-28h]
0x1400108ae  mov     rbx, [rdi+90h]
0x1400108b5  add     rbx, 20h ; ' '
0x1400108b9  lea     rcx, [rdi+28h]; Table
0x1400108bd  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x1400108c4  nop     dword ptr [rax+rax+00h]
0x1400108c9  test    al, al
0x1400108cb  jz      short loc_1400108D7
0x1400108cd  mov     rcx, rdi; Buffer
0x1400108d0  call    BfsDereferenceTableEntry
0x1400108d5  jmp     short loc_14001088C
0x1400108d7  lea     rbx, [rdi+28h]
0x1400108db  jmp     short loc_14001088C
0x1400108dd  xor     edx, edx; Tag
0x1400108df  mov     rcx, rsi; P
0x1400108e2  call    cs:__imp_ExFreePoolWithTag
0x1400108e9  nop     dword ptr [rax+rax+00h]
0x1400108ee  add     rsp, 20h
0x1400108f2  pop     r14
0x1400108f4  pop     rdi
0x1400108f5  pop     rsi
0x1400108f6  pop     rbp
0x1400108f7  pop     rbx
0x1400108f8  retn
```
