# LKRhash::CLKRLinearHashTable::_DeleteNode(LKRhash::CBucket *,LKRhash::CNodeClump * &,LKRhash::CNodeClump * &,int &)

- ea: `0x180004790`
- end: `0x180004902`
- name: `?_DeleteNode@CLKRLinearHashTable@LKRhash@@AEAA_NPEAVCBucket@2@AEAPEAVCNodeClump@2@1AEAH@Z`
- size: `370`
- prototype: `bool __usercall@<al>(LKRhash::CLKRLinearHashTable *__hidden this@<rcx>, struct LKRhash::CBucket *@<rdx>, struct LKRhash::CNodeClump **@<r8>, struct LKRhash::CNodeClump **@<r9>, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019de8`
- `0x180019f9c`

## callees

- `0x180004790`
- `0x18001a284`
- `0x18001d010`

## pseudocode

```c
char __fastcall LKRhash::CLKRLinearHashTable::_DeleteNode(
        LKRhash::CLKRLinearHashTable *this,
        struct LKRhash::CNodeClump **a2,
        struct LKRhash::CNodeClump **a3,
        struct LKRhash::CNodeClump **a4,
        int *a5)
{
  __int64 v9; // rax
  __int64 v10; // rbp
  struct LKRhash::CNodeClump *v11; // r8
  int v12; // eax
  int v13; // r9d
  __int64 v15; // rsi
  __int64 v16; // r10
  struct LKRhash::CNodeClump *v17; // rcx
  struct LKRhash::CNodeClump *v18; // rax
  char *v19; // rdx

  v9 = *a5;
  if ( (unsigned int)v9 > 3 )
    return 0;
  (*((void (__fastcall **)(_QWORD, __int64))this + 7))(*((_QWORD *)*a3 + v9 + 3), 0xFFFFFFFFLL);
  v10 = *a5;
  v11 = *a3;
  v12 = *a5;
  while ( *((_QWORD *)v11 + 2) )
  {
    v11 = (struct LKRhash::CNodeClump *)*((_QWORD *)v11 + 2);
    v12 = 0;
  }
  for ( ; v12 != 4; ++v12 )
  {
    if ( *((_DWORD *)v11 + v12) == 31678523 )
      break;
  }
  v13 = v12 - 1;
  if ( (unsigned int)(v12 - 1) > 3 )
    return 0;
  v15 = *((_QWORD *)v11 + v12 + 2);
  v16 = 4LL * v12 - 4;
  if ( !v15 && *(_DWORD *)((char *)v11 + v16) == 31678523 )
    return 0;
  if ( v12 != 4 && (*((_QWORD *)v11 + v12 + 3) || *((_DWORD *)v11 + v12) != 31678523) )
    return 0;
  *((_QWORD *)*a3 + v10 + 3) = v15;
  *((_DWORD *)*a3 + v10) = *(_DWORD *)((char *)v11 + v16);
  v17 = (struct LKRhash::CNodeClump *)(a2 + 1);
  *((_QWORD *)v11 + v12 + 2) = 0;
  *(_DWORD *)((char *)v11 + v16) = 31678523;
  if ( (_DWORD)v10 )
  {
    *a5 = v10 - 1;
  }
  else if ( *a3 == v17 )
  {
    *a5 = -1;
  }
  else
  {
    v18 = *a4;
    *a5 = 4;
    *a3 = v18;
    if ( v18 == v17 )
    {
      *a4 = 0;
    }
    else
    {
      *a4 = v17;
      if ( a2[3] != v18 )
      {
        v19 = (char *)(a2 + 1);
        do
          v19 = (char *)*((_QWORD *)v19 + 2);
        while ( *((struct LKRhash::CNodeClump **)v19 + 2) != v18 );
        *a4 = (struct LKRhash::CNodeClump *)v19;
      }
    }
  }
  if ( !v13 && v11 != v17 )
  {
    if ( a2[3] != v11 )
    {
      do
        v17 = (struct LKRhash::CNodeClump *)*((_QWORD *)v17 + 2);
      while ( *((struct LKRhash::CNodeClump **)v17 + 2) != v11 );
    }
    *((_QWORD *)v17 + 2) = 0;
    LKRhash::CLKRLinearHashTable::_FreeNodeClump(this, v11);
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 30);
  return 1;
}

```

## disassembly

```asm
0x180004790  push    rbx
0x180004792  push    rbp
0x180004793  push    rsi
0x180004794  push    rdi
0x180004795  push    r12
0x180004797  push    r13
0x180004799  push    r14
0x18000479b  push    r15
0x18000479d  sub     rsp, 28h
0x1800047a1  mov     rdi, [rsp+68h+arg_20]
0x1800047a9  mov     r13, r9
0x1800047ac  mov     r14, r8
0x1800047af  mov     r15, rdx
0x1800047b2  mov     rbx, rcx
0x1800047b5  movsxd  rax, dword ptr [rdi]
0x1800047b8  cmp     eax, 3
0x1800047bb  ja      short loc_180004803
0x1800047bd  mov     rcx, [r8]
0x1800047c0  mov     edx, 0FFFFFFFFh
0x1800047c5  mov     rcx, [rcx+rax*8+18h]
0x1800047ca  mov     rax, [rbx+38h]
0x1800047ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d3  mov     r12, [r14]
0x1800047d6  movsxd  rbp, dword ptr [rdi]
0x1800047d9  mov     r8, r12
0x1800047dc  mov     eax, ebp
0x1800047de  mov     rcx, [r8+10h]
0x1800047e2  test    rcx, rcx
0x1800047e5  jnz     short loc_18000481F
0x1800047e7  cmp     eax, 4
0x1800047ea  jz      short loc_1800047F9
0x1800047ec  movsxd  rcx, eax
0x1800047ef  cmp     dword ptr [r8+rcx*4], 1E3603Bh
0x1800047f7  jnz     short loc_180004816
0x1800047f9  lea     r9d, [rax-1]
0x1800047fd  cmp     r9d, 3
0x180004801  jbe     short loc_180004826
0x180004803  xor     al, al
0x180004805  add     rsp, 28h
0x180004809  pop     r15
0x18000480b  pop     r14
0x18000480d  pop     r13
0x18000480f  pop     r12
0x180004811  pop     rdi
0x180004812  pop     rsi
0x180004813  pop     rbp
0x180004814  pop     rbx
0x180004815  retn
0x180004816  inc     eax
0x180004818  cmp     eax, 4
0x18000481b  jnz     short loc_1800047EC
0x18000481d  jmp     short loc_1800047F9
0x18000481f  mov     r8, rcx
0x180004822  xor     eax, eax
0x180004824  jmp     short loc_1800047DE
0x180004826  movsxd  rcx, eax
0x180004829  mov     rsi, [r8+rcx*8+10h]
0x18000482e  lea     r11, [r8+rcx*8]
0x180004832  lea     r10, ds:0FFFFFFFFFFFFFFFCh[rcx*4]
0x18000483a  test    rsi, rsi
0x18000483d  jnz     short loc_180004849
0x18000483f  cmp     dword ptr [r10+r8], 1E3603Bh
0x180004847  jz      short loc_180004803
0x180004849  cmp     eax, 4
0x18000484c  jz      short loc_180004860
0x18000484e  cmp     qword ptr [r8+rcx*8+18h], 0
0x180004854  jnz     short loc_180004803
0x180004856  cmp     dword ptr [r8+rcx*4], 1E3603Bh
0x18000485e  jnz     short loc_180004803
0x180004860  mov     [r12+rbp*8+18h], rsi
0x180004865  xor     esi, esi
0x180004867  mov     rcx, [r14]
0x18000486a  mov     eax, [r10+r8]
0x18000486e  mov     [rcx+rbp*4], eax
0x180004871  lea     rcx, [r15+8]
0x180004875  mov     [r11+10h], rsi
0x180004879  mov     dword ptr [r10+r8], 1E3603Bh
0x180004881  test    ebp, ebp
0x180004883  jnz     short loc_1800048A5
0x180004885  cmp     [r14], rcx
0x180004888  jnz     short loc_1800048AC
0x18000488a  mov     dword ptr [rdi], 0FFFFFFFFh
0x180004890  test    r9d, r9d
0x180004893  jnz     short loc_18000489A
0x180004895  cmp     r8, rcx
0x180004898  jnz     short loc_1800048E1
0x18000489a  lock dec dword ptr [rbx+78h]
0x18000489e  mov     al, 1
0x1800048a0  jmp     loc_180004805
0x1800048a5  lea     eax, [rbp-1]
0x1800048a8  mov     [rdi], eax
0x1800048aa  jmp     short loc_180004890
0x1800048ac  mov     rax, [r13+0]
0x1800048b0  mov     dword ptr [rdi], 4
0x1800048b6  mov     [r14], rax
0x1800048b9  cmp     rax, rcx
0x1800048bc  jnz     short loc_1800048C4
0x1800048be  mov     [r13+0], rsi
0x1800048c2  jmp     short loc_180004890
0x1800048c4  mov     [r13+0], rcx
0x1800048c8  cmp     [r15+18h], rax
0x1800048cc  jz      short loc_180004890
0x1800048ce  mov     rdx, rcx
0x1800048d1  mov     rdx, [rdx+10h]
0x1800048d5  cmp     [rdx+10h], rax
0x1800048d9  jnz     short loc_1800048D1
0x1800048db  mov     [r13+0], rdx
0x1800048df  jmp     short loc_180004890
0x1800048e1  cmp     [rcx+10h], r8
0x1800048e5  jz      short loc_1800048F1
0x1800048e7  mov     rcx, [rcx+10h]
0x1800048eb  cmp     [rcx+10h], r8
0x1800048ef  jnz     short loc_1800048E7
0x1800048f1  mov     [rcx+10h], rsi
0x1800048f5  mov     rdx, r8; struct LKRhash::CNodeClump *
0x1800048f8  mov     rcx, rbx; this
0x1800048fb  call    ?_FreeNodeClump@CLKRLinearHashTable@LKRhash@@AEAA_NPEAVCNodeClump@2@@Z; LKRhash::CLKRLinearHashTable::_FreeNodeClump(LKRhash::CNodeClump *)
0x180004900  jmp     short loc_18000489A
```
