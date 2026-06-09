# CBTree::ReplaceBySuccessor(SIdxKeyTable *,ushort,char * *,int *,ulong * const,long &)

- ea: `0x180027eb4`
- end: `0x180028224`
- name: `?ReplaceBySuccessor@CBTree@@AEAAKPEAVSIdxKeyTable@@GPEAPEADPEAHQEAKAEAJ@Z`
- size: `880`
- prototype: `unsigned int __usercall@<eax>(CBTree *__hidden this@<rcx>, struct SIdxKeyTable *@<rdx>, unsigned __int16@<r8w>, char **@<r9>, int *, unsigned int *const, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011904`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000eee0`
- `0x1800109d0`
- `0x180010fa0`
- `0x1800114bc`
- `0x1800129a0`
- `0x180012aac`
- `0x180027eb4`
- `0x18002822c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180027f9a`
- `wbemcomn!GetMemLogObject` at `0x180028009`
- `wbemcomn!GetMemLogObject` at `0x1800280b1`
- `wbemcomn!GetMemLogObject` at `0x18002812a`
- `wbemcomn!GetMemLogObject` at `0x1800281cd`
- `wbemcomn!GetMemLogObject` at `0x180027f9a`
- `wbemcomn!GetMemLogObject` at `0x180028009`
- `wbemcomn!GetMemLogObject` at `0x1800280b1`
- `wbemcomn!GetMemLogObject` at `0x18002812a`
- `wbemcomn!GetMemLogObject` at `0x1800281cd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027fa5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028014`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800280bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028135`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800281d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027fa5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028014`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800280bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028135`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800281d8`

## pseudocode

```c
__int64 __fastcall CBTree::ReplaceBySuccessor(
        CBTree *this,
        struct SIdxKeyTable *a2,
        unsigned __int16 a3,
        char **a4,
        int *a5,
        unsigned int *const a6,
        int *a7)
{
  __int64 v7; // rsi
  int *v10; // r14
  int v11; // r13d
  unsigned int SuccessorNode; // edi
  SIdxKeyTable *v13; // rbx
  CMemoryLog *v14; // rax
  CVarObjHeap *v15; // rcx
  __int64 v16; // rdx
  int v17; // r12d
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  int *v20; // rdi
  unsigned int v21; // ebx
  CMemoryLog *v22; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned int v25; // [rsp+40h] [rbp-58h] BYREF
  SIdxKeyTable *v26; // [rsp+48h] [rbp-50h] BYREF

  v7 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  v10 = a7;
  v11 = *a7;
  v26 = 0;
  v25 = 0;
  SuccessorNode = CBTree::FindSuccessorNode(this, a2, v7, &v26, &v25, a6, a7);
  if ( SuccessorNode )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, SuccessorNode);
LABEL_36:
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return SuccessorNode;
    }
    v16 = 165;
    goto LABEL_40;
  }
  v13 = v26;
  if ( !v26 )
    goto LABEL_36;
  a7 = 0;
  SuccessorNode = SIdxKeyTable::GetKeyAt(v26, 0, (char **)&a7);
  if ( SuccessorNode )
  {
    SIdxKeyTable::Release(v13);
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, SuccessorNode);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return SuccessorNode;
    }
    v16 = 166;
LABEL_40:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, SuccessorNode);
    return SuccessorNode;
  }
  v17 = **((_DWORD **)v13 + 4);
  SuccessorNode = SIdxKeyTable::RemoveKey(v13, 0);
  if ( SuccessorNode )
  {
    _BtrMemFree(a7);
    SIdxKeyTable::Release(v13);
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, SuccessorNode);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return SuccessorNode;
    }
    v16 = 167;
    goto LABEL_40;
  }
  if ( ((100
       * (*(_DWORD *)(*((_QWORD *)v13 + 8) + 36LL)
        + 2 * (**((_DWORD **)v13 + 8) + *((_DWORD *)v13 + 15) + 5 * (*((_DWORD *)v13 + 3) + 5))))
      & 0xFFFFE000) < 0x42000 )
    *a5 = 1;
  SuccessorNode = CBTree::WriteIdxPage(this, v13);
  SIdxKeyTable::Release(v13);
  if ( SuccessorNode )
  {
    _BtrMemFree(a7);
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, SuccessorNode);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return SuccessorNode;
    }
    v16 = 168;
    goto LABEL_40;
  }
  SIdxKeyTable::RemoveKey(a2, v7);
  v20 = a7;
  v21 = SIdxKeyTable::AddKey((void **)a2, (char *)a7, v7, v17);
  if ( v21 )
  {
    _BtrMemFree(v20);
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, v21);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v21);
    }
    return v21;
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)a2 + 5) + 4 * v7) = v25;
    *a4 = (char *)v20;
    *v10 = v11;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 0);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180027eb4  mov     [rsp+arg_18], r9
0x180027eb9  push    rbx
0x180027eba  push    rbp
0x180027ebb  push    rsi
0x180027ebc  push    rdi
0x180027ebd  push    r12
0x180027ebf  push    r13
0x180027ec1  push    r14
0x180027ec3  push    r15
0x180027ec5  sub     rsp, 58h
0x180027ec9  movzx   esi, r8w
0x180027ecd  mov     rbp, rdx
0x180027ed0  mov     r15, rcx
0x180027ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180027eda  lea     rax, WPP_GLOBAL_Control
0x180027ee1  lea     r12, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180027ee8  cmp     rcx, rax
0x180027eeb  jz      short loc_180027F0A
0x180027eed  test    byte ptr [rcx+1Ch], 1
0x180027ef1  jz      short loc_180027F0A
0x180027ef3  cmp     byte ptr [rcx+19h], 5
0x180027ef7  jb      short loc_180027F0A
0x180027ef9  mov     rcx, [rcx+10h]
0x180027efd  mov     edx, 0A4h
0x180027f02  mov     r8, r12
0x180027f05  call    WPP_SF_
0x180027f0a  mov     r14, [rsp+98h+arg_30]
0x180027f12  lea     r9, [rsp+98h+var_50]; struct SIdxKeyTable **
0x180027f17  mov     rax, [rsp+98h+arg_28]
0x180027f1f  movzx   r8d, si; unsigned __int16
0x180027f23  mov     [rsp+98h+var_68], r14; int *
0x180027f28  mov     rdx, rbp; struct SIdxKeyTable *
0x180027f2b  mov     [rsp+98h+var_70], rax; unsigned int *
0x180027f30  mov     rcx, r15; this
0x180027f33  mov     r13d, [r14]
0x180027f36  lea     rax, [rsp+98h+var_58]
0x180027f3b  mov     [rsp+98h+var_78], rax; unsigned int *
0x180027f40  mov     [rsp+98h+var_50], 0
0x180027f49  mov     [rsp+98h+var_58], 0
0x180027f51  call    ?FindSuccessorNode@CBTree@@AEAAKPEAVSIdxKeyTable@@GPEAPEAV2@PEAKQEAKAEAJ@Z; CBTree::FindSuccessorNode(SIdxKeyTable *,ushort,SIdxKeyTable * *,ulong *,ulong * const,long &)
0x180027f56  mov     edi, eax
0x180027f58  test    eax, eax
0x180027f5a  jnz     loc_1800281CD
0x180027f60  mov     rbx, [rsp+98h+var_50]
0x180027f65  test    rbx, rbx
0x180027f68  jz      loc_1800281DE
0x180027f6e  xor     edx, edx; unsigned __int16
0x180027f70  mov     [rsp+98h+arg_30], 0
0x180027f7c  lea     r8, [rsp+98h+arg_30]; char **
0x180027f84  mov     rcx, rbx; this
0x180027f87  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x180027f8c  mov     edi, eax
0x180027f8e  mov     rcx, rbx; this
0x180027f91  test    eax, eax
0x180027f93  jz      short loc_180027FE0
0x180027f95  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180027f9a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180027fa0  mov     rcx, rax
0x180027fa3  mov     edx, edi
0x180027fa5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180027fab  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fb2  lea     rax, WPP_GLOBAL_Control
0x180027fb9  cmp     rcx, rax
0x180027fbc  jz      loc_180028211
0x180027fc2  test    byte ptr [rcx+1Ch], 1
0x180027fc6  jz      loc_180028211
0x180027fcc  cmp     byte ptr [rcx+19h], 2
0x180027fd0  jb      loc_180028211
0x180027fd6  mov     edx, 0A6h
0x180027fdb  jmp     loc_180028202
0x180027fe0  mov     rax, [rbx+20h]
0x180027fe4  xor     edx, edx; unsigned __int16
0x180027fe6  mov     r12d, [rax]
0x180027fe9  call    ?RemoveKey@SIdxKeyTable@@QEAAKG@Z; SIdxKeyTable::RemoveKey(ushort)
0x180027fee  mov     edi, eax
0x180027ff0  test    eax, eax
0x180027ff2  jz      short loc_180028056
0x180027ff4  mov     rcx, [rsp+98h+arg_30]; void *
0x180027ffc  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180028001  mov     rcx, rbx; this
0x180028004  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180028009  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002800f  mov     rcx, rax
0x180028012  mov     edx, edi
0x180028014  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002801a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028021  lea     rax, WPP_GLOBAL_Control
0x180028028  cmp     rcx, rax
0x18002802b  jz      loc_180028211
0x180028031  test    byte ptr [rcx+1Ch], 1
0x180028035  jz      loc_180028211
0x18002803b  cmp     byte ptr [rcx+19h], 2
0x18002803f  jb      loc_180028211
0x180028045  mov     edx, 0A7h
0x18002804a  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180028051  jmp     loc_180028205
0x180028056  mov     rdx, [rbx+40h]
0x18002805a  mov     eax, [rbx+0Ch]
0x18002805d  add     eax, 5
0x180028060  lea     ecx, [rax+rax*4]
0x180028063  mov     eax, [rdx+24h]
0x180028066  add     ecx, [rbx+3Ch]
0x180028069  add     ecx, [rdx]
0x18002806b  lea     ecx, [rax+rcx*2]
0x18002806e  imul    eax, ecx, 64h ; 'd'
0x180028071  and     eax, 0FFFFE000h
0x180028076  cmp     eax, 42000h
0x18002807b  jnb     short loc_18002808B
0x18002807d  mov     rax, [rsp+98h+arg_20]
0x180028085  mov     dword ptr [rax], 1
0x18002808b  mov     rdx, rbx; struct SIdxKeyTable *
0x18002808e  mov     rcx, r15; this
0x180028091  call    ?WriteIdxPage@CBTree@@AEAAKPEAVSIdxKeyTable@@@Z; CBTree::WriteIdxPage(SIdxKeyTable *)
0x180028096  mov     rcx, rbx; this
0x180028099  mov     edi, eax
0x18002809b  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x1800280a0  test    edi, edi
0x1800280a2  jz      short loc_1800280F7
0x1800280a4  mov     rcx, [rsp+98h+arg_30]; void *
0x1800280ac  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x1800280b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800280b7  mov     rcx, rax
0x1800280ba  mov     edx, edi
0x1800280bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800280c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280c9  lea     rax, WPP_GLOBAL_Control
0x1800280d0  cmp     rcx, rax
0x1800280d3  jz      loc_180028211
0x1800280d9  test    byte ptr [rcx+1Ch], 1
0x1800280dd  jz      loc_180028211
0x1800280e3  cmp     byte ptr [rcx+19h], 2
0x1800280e7  jb      loc_180028211
0x1800280ed  mov     edx, 0A8h
0x1800280f2  jmp     loc_18002804A
0x1800280f7  movzx   edx, si; unsigned __int16
0x1800280fa  mov     rcx, rbp; this
0x1800280fd  call    ?RemoveKey@SIdxKeyTable@@QEAAKG@Z; SIdxKeyTable::RemoveKey(ushort)
0x180028102  mov     rdi, [rsp+98h+arg_30]
0x18002810a  mov     r9d, r12d; unsigned int
0x18002810d  mov     rdx, rdi; char *
0x180028110  movzx   r8d, si; unsigned __int16
0x180028114  mov     rcx, rbp; this
0x180028117  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x18002811c  mov     ebx, eax
0x18002811e  test    eax, eax
0x180028120  jz      short loc_180028179
0x180028122  mov     rcx, rdi; void *
0x180028125  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18002812a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028130  mov     rcx, rax
0x180028133  mov     edx, ebx
0x180028135  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002813b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028142  lea     rax, WPP_GLOBAL_Control
0x180028149  cmp     rcx, rax
0x18002814c  jz      short loc_180028172
0x18002814e  test    byte ptr [rcx+1Ch], 1
0x180028152  jz      short loc_180028172
0x180028154  cmp     byte ptr [rcx+19h], 2
0x180028158  jb      short loc_180028172
0x18002815a  mov     rcx, [rcx+10h]
0x18002815e  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180028165  mov     edx, 0A9h
0x18002816a  mov     r9d, ebx
0x18002816d  call    WPP_SF_d
0x180028172  mov     eax, ebx
0x180028174  jmp     loc_180028213
0x180028179  mov     rcx, [rbp+28h]
0x18002817d  mov     eax, [rsp+98h+var_58]
0x180028181  mov     [rcx+rsi*4], eax
0x180028184  mov     rax, [rsp+98h+arg_18]
0x18002818c  mov     [rax], rdi
0x18002818f  mov     [r14], r13d
0x180028192  mov     rcx, cs:WPP_GLOBAL_Control
0x180028199  lea     rax, WPP_GLOBAL_Control
0x1800281a0  cmp     rcx, rax
0x1800281a3  jz      short loc_1800281C9
0x1800281a5  test    byte ptr [rcx+1Ch], 1
0x1800281a9  jz      short loc_1800281C9
0x1800281ab  cmp     byte ptr [rcx+19h], 2
0x1800281af  jb      short loc_1800281C9
0x1800281b1  mov     rcx, [rcx+10h]
0x1800281b5  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x1800281bc  mov     edx, 0AAh
0x1800281c1  xor     r9d, r9d
0x1800281c4  call    WPP_SF_d
0x1800281c9  xor     eax, eax
0x1800281cb  jmp     short loc_180028213
0x1800281cd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800281d3  mov     rcx, rax
0x1800281d6  mov     edx, edi
0x1800281d8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800281de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281e5  lea     rax, WPP_GLOBAL_Control
0x1800281ec  cmp     rcx, rax
0x1800281ef  jz      short loc_180028211
0x1800281f1  test    byte ptr [rcx+1Ch], 1
0x1800281f5  jz      short loc_180028211
0x1800281f7  cmp     byte ptr [rcx+19h], 2
0x1800281fb  jb      short loc_180028211
0x1800281fd  mov     edx, 0A5h
0x180028202  mov     r8, r12
0x180028205  mov     rcx, [rcx+10h]
0x180028209  mov     r9d, edi
0x18002820c  call    WPP_SF_d
0x180028211  mov     eax, edi
0x180028213  add     rsp, 58h
0x180028217  pop     r15
0x180028219  pop     r14
0x18002821b  pop     r13
0x18002821d  pop     r12
0x18002821f  pop     rdi
0x180028220  pop     rsi
0x180028221  pop     rbp
0x180028222  pop     rbx
0x180028223  retn
```
