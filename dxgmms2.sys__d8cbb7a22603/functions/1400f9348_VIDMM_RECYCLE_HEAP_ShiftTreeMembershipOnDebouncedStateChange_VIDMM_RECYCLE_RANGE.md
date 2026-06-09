# VIDMM_RECYCLE_HEAP::ShiftTreeMembershipOnDebouncedStateChange(VIDMM_RECYCLE_RANGE *)

- ea: `0x1400f9348`
- end: `0x1400f9688`
- name: `?ShiftTreeMembershipOnDebouncedStateChange@VIDMM_RECYCLE_HEAP@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z`
- size: `832`
- prototype: `void __fastcall(VIDMM_RECYCLE_HEAP *__hidden this, struct VIDMM_RECYCLE_RANGE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400f5d04`
- `0x1400f7698`
- `0x1400fadb8`

## callees

- `0x1400ad26c`
- `0x1400f9348`
- `0x1400fa96c`
- `0x1400faa38`
- `0x1400fac80`
- `0x1400faecc`
- `0x1400fb054`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f94bf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f94bf`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f93da`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f93da`
- `watchdog!WdLogSingleEntry2` at `0x1400f939f`
- `watchdog!WdLogSingleEntry2` at `0x1400f939f`
- `watchdog!WdLogSingleEntry5` at `0x1400f9639`
- `watchdog!WdLogSingleEntry5` at `0x1400f9639`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f9612`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_RECYCLE_HEAP::ShiftTreeMembershipOnDebouncedStateChange(
        VIDMM_RECYCLE_HEAP *this,
        struct VIDMM_RECYCLE_RANGE *a2)
{
  __int64 v4; // rsi
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r10
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r9
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // edx
  char *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // r15
  __int64 v17; // r8
  __int64 v18; // rbx
  __int64 Multirange; // r13
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8

  if ( *((_DWORD *)a2 + 16) != 4 )
  {
    if ( *((_DWORD *)a2 + 16) != 5 )
    {
      v6 = 3;
      v5 = 3;
      goto LABEL_23;
    }
    v4 = *((_QWORD *)a2 + 18);
    v5 = 1;
    goto LABEL_4;
  }
  v5 = 0;
  v4 = *((_QWORD *)a2 + 19);
  v13 = **(_DWORD **)(*((_QWORD *)a2 + 9) + 32LL);
  if ( (unsigned int)(v13 - 3) <= 3 || (v6 = 1, (unsigned int)(v13 - 9) <= 1) )
LABEL_4:
    v6 = 2;
  if ( !v4 )
  {
LABEL_23:
    VIDMM_RECYCLE_HEAP::RemoveRangeFromTree(this, v5, a2);
    VIDMM_RECYCLE_HEAP::AddRangeToTree(this, v6, a2);
    return;
  }
  WdLogSingleEntry2(4, v4, v5);
  WdLogGlobalForLineNumber = 8471;
  if ( v5 )
    v14 = (char *)this + 56;
  else
    v14 = (char *)this + 48;
  RtlAvlRemoveNode(v14, v4);
  v7 = *(_QWORD *)(v4 + 32);
  v8 = *(_QWORD *)(v4 + 40);
  *(_DWORD *)(v4 + 88) = 3;
  v9 = *((_QWORD *)a2 + 4);
  v10 = *((_QWORD *)a2 + 5);
  if ( v7 < v9 )
  {
    if ( v8 > v10 )
    {
      v15 = *((_QWORD *)a2 + 15);
      v16 = 0;
      v17 = *((_QWORD *)a2 + 9);
      v18 = *(_QWORD *)(v4 + 72);
      if ( v15 != v17 + 72 )
        v16 = (_QWORD *)(v15 - 120);
      Multirange = VIDMM_RECYCLE_HEAP_MGR::CreateMultirange(
                     *((_QWORD *)this + 1),
                     *(unsigned int *)(v4 + 144),
                     v17,
                     v10,
                     v8);
      *(_QWORD *)(Multirange + 64) = v16;
      *(_QWORD *)(Multirange + 72) = v18;
      VIDMM_RECYCLE_MULTIRANGE::ShrinkTo((VIDMM_RECYCLE_MULTIRANGE *)v4, *(_QWORD *)(v4 + 32), *((_QWORD *)a2 + 4));
      while ( 1 )
      {
        v20 = *(_DWORD *)(Multirange + 144);
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            if ( v21 == 1 )
              v16[19] = Multirange;
          }
          else
          {
            v16[18] = Multirange;
          }
        }
        else
        {
          v16[17] = Multirange;
        }
        if ( v16 == *(_QWORD **)(Multirange + 72) )
          break;
        v22 = v16[15];
        v23 = v16[9];
        v16 = 0;
        if ( v22 != v23 + 72 )
          v16 = (_QWORD *)(v22 - 120);
      }
      if ( *((_DWORD *)a2 + 16) == 4 )
      {
        *((_QWORD *)a2 + 19) = 0;
      }
      else if ( *((_DWORD *)a2 + 16) == 5 )
      {
        *((_QWORD *)a2 + 18) = 0;
      }
      VIDMM_RECYCLE_HEAP::AddMultirangeToTree(this, v5, v4);
      v24 = Multirange;
      goto LABEL_40;
    }
LABEL_36:
    VIDMM_RECYCLE_MULTIRANGE::ShrinkTo((VIDMM_RECYCLE_MULTIRANGE *)v4, v7, v9);
    if ( *((_DWORD *)a2 + 16) == 4 )
    {
      *((_QWORD *)a2 + 19) = 0;
    }
    else if ( *((_DWORD *)a2 + 16) == 5 )
    {
      *((_QWORD *)a2 + 18) = 0;
    }
    v24 = v4;
LABEL_40:
    VIDMM_RECYCLE_HEAP::AddMultirangeToTree(this, v5, v24);
    return;
  }
  if ( v8 > v10 )
  {
    v9 = v8;
    v7 = *((_QWORD *)a2 + 5);
    goto LABEL_36;
  }
  v11 = *((_QWORD *)this + 1);
  VIDMM_RECYCLE_MULTIRANGE::Destroy((VIDMM_RECYCLE_MULTIRANGE *)v4);
  v12 = *(unsigned int *)(v11 + 1620);
  if ( (unsigned int)v12 >= 4 )
  {
    ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v11 + 1320), (PVOID)v4);
  }
  else
  {
    *(_QWORD *)(v11 + 8 * v12 + 1656) = v4;
    ++*(_DWORD *)(v11 + 1620);
  }
  --*(_DWORD *)(v11 + 1688);
  if ( *((_DWORD *)a2 + 16) == 4 )
  {
    *((_QWORD *)a2 + 19) = 0;
  }
  else if ( *((_DWORD *)a2 + 16) == 5 )
  {
    *((_QWORD *)a2 + 18) = 0;
  }
}

```

## disassembly

```asm
0x1400f9348  push    rbx
0x1400f934a  push    rbp
0x1400f934b  push    rsi
0x1400f934c  push    rdi
0x1400f934d  push    r13
0x1400f934f  push    r14
0x1400f9351  push    r15
0x1400f9353  sub     rsp, 30h
0x1400f9357  mov     rbp, rcx
0x1400f935a  mov     r13d, 4
0x1400f9360  mov     ecx, [rdx+40h]
0x1400f9363  mov     rdi, rdx
0x1400f9366  sub     ecx, r13d
0x1400f9369  jz      loc_1400F9467
0x1400f936f  cmp     ecx, 1
0x1400f9372  jnz     loc_1400F94D9
0x1400f9378  mov     rsi, [rdx+90h]
0x1400f937f  mov     r15d, ecx
0x1400f9382  mov     r14d, ecx
0x1400f9385  mov     ebx, 2
0x1400f938a  test    rsi, rsi
0x1400f938d  jz      loc_1400F94E1
0x1400f9393  mov     r8d, r14d
0x1400f9396  mov     rdx, rsi
0x1400f9399  mov     ecx, r13d
0x1400f939c  mov     ebx, r14d
0x1400f939f  call    cs:__imp_WdLogSingleEntry2
0x1400f93a6  nop     dword ptr [rax+rax+00h]
0x1400f93ab  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f93b5  mov     ecx, r14d
0x1400f93b8  test    r14d, r14d
0x1400f93bb  jz      loc_1400F94AC
0x1400f93c1  sub     ecx, 1
0x1400f93c4  jz      loc_1400F94D0
0x1400f93ca  cmp     ecx, 1
0x1400f93cd  jnz     loc_1400F9612
0x1400f93d3  lea     rcx, [rbp+40h]
0x1400f93d7  mov     rdx, rsi
0x1400f93da  call    cs:__imp_RtlAvlRemoveNode
0x1400f93e1  nop     dword ptr [rax+rax+00h]
0x1400f93e6  mov     rdx, [rsi+20h]
0x1400f93ea  mov     r10, [rsi+28h]
0x1400f93ee  mov     dword ptr [rsi+58h], 3
0x1400f93f5  mov     r8, [rdi+20h]
0x1400f93f9  mov     r9, [rdi+28h]
0x1400f93fd  cmp     rdx, r8
0x1400f9400  jb      loc_1400F9501
0x1400f9406  cmp     r10, r9
0x1400f9409  ja      loc_1400F9598
0x1400f940f  mov     rbx, [rbp+8]
0x1400f9413  mov     rcx, rsi; this
0x1400f9416  call    ?Destroy@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::Destroy(void)
0x1400f941b  mov     eax, [rbx+654h]
0x1400f9421  cmp     eax, r13d
0x1400f9424  jnb     loc_1400F94B5
0x1400f942a  mov     [rbx+rax*8+678h], rsi
0x1400f9432  add     [rbx+654h], r15d
0x1400f9439  dec     dword ptr [rbx+698h]
0x1400f943f  mov     ecx, [rdi+40h]
0x1400f9442  sub     ecx, r13d
0x1400f9445  jz      short loc_1400F949F
0x1400f9447  cmp     ecx, 1
0x1400f944a  jnz     short loc_1400F9457
0x1400f944c  mov     qword ptr [rdi+90h], 0
0x1400f9457  add     rsp, 30h
0x1400f945b  pop     r15
0x1400f945d  pop     r14
0x1400f945f  pop     r13
0x1400f9461  pop     rdi
0x1400f9462  pop     rsi
0x1400f9463  pop     rbp
0x1400f9464  pop     rbx
0x1400f9465  retn
0x1400f9467  mov     rax, [rdx+48h]
0x1400f946b  xor     r14d, r14d
0x1400f946e  mov     rsi, [rdx+98h]
0x1400f9475  mov     rcx, [rax+20h]
0x1400f9479  lea     r15d, [r14+1]
0x1400f947d  mov     edx, [rcx]
0x1400f947f  lea     eax, [rdx-3]
0x1400f9482  cmp     eax, 3
0x1400f9485  jbe     loc_1400F9385
0x1400f948b  lea     eax, [rdx-9]
0x1400f948e  mov     ebx, r15d
0x1400f9491  cmp     eax, r15d
0x1400f9494  jbe     loc_1400F9385
0x1400f949a  jmp     loc_1400F938A
0x1400f949f  mov     qword ptr [rdi+98h], 0
0x1400f94aa  jmp     short loc_1400F9457
0x1400f94ac  lea     rcx, [rbp+30h]
0x1400f94b0  jmp     loc_1400F93D7
0x1400f94b5  mov     rcx, [rbx+528h]; Lookaside
0x1400f94bc  mov     rdx, rsi; Entry
0x1400f94bf  call    cs:__imp_ExFreeToLookasideListEx
0x1400f94c6  nop     dword ptr [rax+rax+00h]
0x1400f94cb  jmp     loc_1400F9439
0x1400f94d0  lea     rcx, [rbp+38h]
0x1400f94d4  jmp     loc_1400F93D7
0x1400f94d9  mov     ebx, 3
0x1400f94de  mov     r14d, ebx
0x1400f94e1  mov     r8, rdi
0x1400f94e4  mov     edx, r14d
0x1400f94e7  mov     rcx, rbp
0x1400f94ea  call    ?RemoveRangeFromTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP::RemoveRangeFromTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_RANGE *)
0x1400f94ef  mov     r8, rdi
0x1400f94f2  mov     edx, ebx
0x1400f94f4  mov     rcx, rbp
0x1400f94f7  call    ?AddRangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP::AddRangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_RANGE *)
0x1400f94fc  jmp     loc_1400F9457
0x1400f9501  cmp     r10, r9
0x1400f9504  jbe     loc_1400F959E
0x1400f950a  mov     rdx, [rdi+78h]
0x1400f950e  xor     r15d, r15d
0x1400f9511  mov     r8, [rdi+48h]
0x1400f9515  mov     rbx, [rsi+48h]
0x1400f9519  mov     [rsp+68h+var_48], r10
0x1400f951e  lea     rax, [rdx-78h]
0x1400f9522  lea     rcx, [r8+48h]
0x1400f9526  cmp     rdx, rcx
0x1400f9529  mov     edx, [rsi+90h]
0x1400f952f  mov     rcx, [rbp+8]
0x1400f9533  cmovnz  r15, rax
0x1400f9537  call    ?CreateMultirange@VIDMM_RECYCLE_HEAP_MGR@@QEAAPEAVVIDMM_RECYCLE_MULTIRANGE@@W4VIDMM_RECYCLE_MULTIRANGE_STATE@@PEAVVIDMM_RECYCLE_BLOCK@@_K2@Z; VIDMM_RECYCLE_HEAP_MGR::CreateMultirange(VIDMM_RECYCLE_MULTIRANGE_STATE,VIDMM_RECYCLE_BLOCK *,unsigned __int64,unsigned __int64)
0x1400f953c  mov     rcx, rsi; this
0x1400f953f  mov     r13, rax
0x1400f9542  mov     [rax+40h], r15
0x1400f9546  mov     [rax+48h], rbx
0x1400f954a  mov     r8, [rdi+20h]; unsigned __int64
0x1400f954e  mov     rdx, [rsi+20h]; unsigned __int64
0x1400f9552  call    ?ShrinkTo@VIDMM_RECYCLE_MULTIRANGE@@QEAAX_K0@Z; VIDMM_RECYCLE_MULTIRANGE::ShrinkTo(unsigned __int64,unsigned __int64)
0x1400f9557  mov     eax, [r13+90h]
0x1400f955e  test    eax, eax
0x1400f9560  jz      loc_1400F964F
0x1400f9566  sub     eax, 1
0x1400f9569  jnz     loc_1400F95FD
0x1400f956f  mov     [r15+90h], r13
0x1400f9576  cmp     r15, [r13+48h]
0x1400f957a  jz      short loc_1400F95CE
0x1400f957c  mov     rdx, [r15+78h]
0x1400f9580  mov     rcx, [r15+48h]
0x1400f9584  xor     r15d, r15d
0x1400f9587  add     rcx, 48h ; 'H'
0x1400f958b  cmp     rdx, rcx
0x1400f958e  lea     rax, [rdx-78h]
0x1400f9592  cmovnz  r15, rax
0x1400f9596  jmp     short loc_1400F9557
0x1400f9598  mov     r8, r10; unsigned __int64
0x1400f959b  mov     rdx, r9; unsigned __int64
0x1400f959e  mov     rcx, rsi; this
0x1400f95a1  call    ?ShrinkTo@VIDMM_RECYCLE_MULTIRANGE@@QEAAX_K0@Z; VIDMM_RECYCLE_MULTIRANGE::ShrinkTo(unsigned __int64,unsigned __int64)
0x1400f95a6  mov     eax, [rdi+40h]
0x1400f95a9  sub     eax, r13d
0x1400f95ac  jz      loc_1400F9678
0x1400f95b2  cmp     eax, 1
0x1400f95b5  jz      loc_1400F9668
0x1400f95bb  mov     r8, rsi
0x1400f95be  mov     edx, r14d
0x1400f95c1  mov     rcx, rbp
0x1400f95c4  call    ?AddMultirangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP::AddMultirangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_MULTIRANGE *)
0x1400f95c9  jmp     loc_1400F9457
0x1400f95ce  mov     ecx, [rdi+40h]
0x1400f95d1  sub     ecx, 4
0x1400f95d4  jz      loc_1400F965B
0x1400f95da  cmp     ecx, 1
0x1400f95dd  jnz     short loc_1400F95EA
0x1400f95df  mov     qword ptr [rdi+90h], 0
0x1400f95ea  mov     r8, rsi
0x1400f95ed  mov     edx, r14d
0x1400f95f0  mov     rcx, rbp
0x1400f95f3  call    ?AddMultirangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP::AddMultirangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_MULTIRANGE *)
0x1400f95f8  mov     r8, r13
0x1400f95fb  jmp     short loc_1400F95BE
0x1400f95fd  cmp     eax, 1
0x1400f9600  jnz     loc_1400F9576
0x1400f9606  mov     [r15+98h], r13
0x1400f960d  jmp     loc_1400F9576
0x1400f9612  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f9619  mov     [rax], r15d
0x1400f961c  xor     ecx, ecx
0x1400f961e  mov     [rsp+68h+var_40], 0
0x1400f9627  mov     edx, 10Eh
0x1400f962c  mov     [rsp+68h+var_48], rbx
0x1400f9631  lea     r9d, [rcx+10h]
0x1400f9635  lea     r8d, [rcx+34h]
0x1400f9639  call    cs:__imp_WdLogSingleEntry5
0x1400f9640  nop     dword ptr [rax+rax+00h]
0x1400f9645  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400f964f  mov     [r15+88h], r13
0x1400f9656  jmp     loc_1400F9576
0x1400f965b  mov     qword ptr [rdi+98h], 0
0x1400f9666  jmp     short loc_1400F95EA
0x1400f9668  mov     qword ptr [rdi+90h], 0
0x1400f9673  jmp     loc_1400F95BB
0x1400f9678  mov     qword ptr [rdi+98h], 0
0x1400f9683  jmp     loc_1400F95BB
```
