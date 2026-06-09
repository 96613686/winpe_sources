# CObjectHeap::DeleteObject(ushort const *)

- ea: `0x180013048`
- end: `0x18001336a`
- name: `?DeleteObject@CObjectHeap@@QEAAJPEBG@Z`
- size: `802`
- prototype: `__int64 __fastcall(CObjectHeap *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014024`
- `0x18001404c`

## callees

- `0x1800012b8`
- `0x18000ca40`
- `0x180013048`
- `0x180013370`
- `0x180013558`
- `0x1800136b8`
- `0x18003d184`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800130bd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800130bd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013124`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001318f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001322e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001329d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001330b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013353`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013124`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001318f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001322e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001329d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001330b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180013353`
- `wbemcomn!GetMemLogObject` at `0x180013064`
- `wbemcomn!GetMemLogObject` at `0x1800130d6`
- `wbemcomn!GetMemLogObject` at `0x180013142`
- `wbemcomn!GetMemLogObject` at `0x1800131dc`
- `wbemcomn!GetMemLogObject` at `0x180013250`
- `wbemcomn!GetMemLogObject` at `0x1800132be`
- `wbemcomn!GetMemLogObject` at `0x180013064`
- `wbemcomn!GetMemLogObject` at `0x1800130d6`
- `wbemcomn!GetMemLogObject` at `0x180013142`
- `wbemcomn!GetMemLogObject` at `0x1800131dc`
- `wbemcomn!GetMemLogObject` at `0x180013250`
- `wbemcomn!GetMemLogObject` at `0x1800132be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013074`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800130e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001314d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800131ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001325b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800132c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013074`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800130e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001314d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800131ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001325b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800132c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CObjectHeap::DeleteObject(CObjectHeap *this, const unsigned __int16 *a2)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int IndexFileName; // ebx
  unsigned __int16 *v7; // rax
  CMemoryLog *v8; // rax
  CObjectHeap *v9; // rcx
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  unsigned __int16 *v14; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v17; // [rsp+78h] [rbp+38h] BYREF

  if ( !*((_DWORD *)this + 2) )
  {
    MemLogObject = GetMemLogObject();
    IndexFileName = 4317;
    CMemoryLog::Write(MemLogObject, 4317);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 4317);
    }
    return IndexFileName;
  }
  v7 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  v14 = v7;
  if ( !v7 )
  {
    v8 = GetMemLogObject();
    IndexFileName = 14;
    CMemoryLog::Write(v8, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 14);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return IndexFileName;
  }
  *v7 = 0;
  IndexFileName = CObjectHeap::GetIndexFileName(this, a2, (struct CFileName *)&v14);
  if ( IndexFileName )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, IndexFileName);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, IndexFileName);
    }
LABEL_37:
    CWin32DefaultArena::WbemMemFree(v14);
    return IndexFileName;
  }
  v16 = 0;
  v15 = 0;
  v17 = 0;
  if ( CObjectHeap::ParseInfoFromIndexFile(v9, v14, &v16, &v15, &v17) == 87 )
  {
    CRepositoryCorruption::SetRepositoryCorrupted(2, 0, 0);
    v11 = GetMemLogObject();
    IndexFileName = 4317;
    CMemoryLog::Write(v11, 4317);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 4317);
    }
    goto LABEL_37;
  }
  IndexFileName = CVarObjHeap::DeleteBuffer((CPageFile **)this + 2, v16, v15);
  if ( IndexFileName )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, IndexFileName);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, IndexFileName);
    }
    goto LABEL_37;
  }
  IndexFileName = CObjectHeap::DeleteIndexFile(this, a2, v14);
  if ( IndexFileName )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, IndexFileName);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, IndexFileName);
    }
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 0);
  }
  CWin32DefaultArena::WbemMemFree(v14);
  return 0;
}

```

## disassembly

```asm
0x180013048  mov     [rsp-18h+arg_8], rbx
0x18001304d  push    rbp
0x18001304e  push    rsi
0x18001304f  push    r14
0x180013051  mov     rbp, rsp
0x180013054  sub     rsp, 40h
0x180013058  mov     r14, rdx
0x18001305b  mov     rsi, rcx
0x18001305e  cmp     dword ptr [rcx+8], 0
0x180013062  jnz     short loc_1800130B8
0x180013064  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001306a  mov     ebx, 10DDh
0x18001306f  mov     edx, ebx
0x180013071  mov     rcx, rax
0x180013074  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001307a  lea     rax, WPP_GLOBAL_Control
0x180013081  mov     rcx, cs:WPP_GLOBAL_Control
0x180013088  cmp     rcx, rax
0x18001308b  jz      short loc_1800130B1
0x18001308d  test    byte ptr [rcx+1Ch], 1
0x180013091  jz      short loc_1800130B1
0x180013093  cmp     byte ptr [rcx+19h], 2
0x180013097  jb      short loc_1800130B1
0x180013099  mov     edx, 31h ; '1'
0x18001309e  mov     r9d, ebx
0x1800130a1  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x1800130a8  mov     rcx, [rcx+10h]
0x1800130ac  call    WPP_SF_d
0x1800130b1  mov     eax, ebx
0x1800130b3  jmp     loc_18001335C
0x1800130b8  mov     ecx, 2E6h
0x1800130bd  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800130c3  mov     [rbp+var_10], rax
0x1800130c7  test    rax, rax
0x1800130ca  jz      short loc_1800130D1
0x1800130cc  xor     ecx, ecx
0x1800130ce  mov     [rax], cx
0x1800130d1  test    rax, rax
0x1800130d4  jnz     short loc_18001312D
0x1800130d6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800130dc  mov     ebx, 0Eh
0x1800130e1  mov     edx, ebx
0x1800130e3  mov     rcx, rax
0x1800130e6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800130ec  lea     rax, WPP_GLOBAL_Control
0x1800130f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130fa  cmp     rcx, rax
0x1800130fd  jz      short loc_180013122
0x1800130ff  test    byte ptr [rcx+1Ch], 1
0x180013103  jz      short loc_180013122
0x180013105  cmp     byte ptr [rcx+19h], 2
0x180013109  jb      short loc_180013122
0x18001310b  lea     edx, [rbx+24h]
0x18001310e  mov     r9d, ebx
0x180013111  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013118  mov     rcx, [rcx+10h]
0x18001311c  call    WPP_SF_d
0x180013121  nop
0x180013122  xor     ecx, ecx
0x180013124  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001312a  nop
0x18001312b  jmp     short loc_1800130B1
0x18001312d  lea     r8, [rbp+var_10]; struct CFileName *
0x180013131  mov     rdx, r14; unsigned __int16 *
0x180013134  mov     rcx, rsi; this
0x180013137  call    ?GetIndexFileName@CObjectHeap@@IEAAJPEBGAEAVCFileName@@@Z; CObjectHeap::GetIndexFileName(ushort const *,CFileName &)
0x18001313c  mov     ebx, eax
0x18001313e  test    eax, eax
0x180013140  jz      short loc_18001319B
0x180013142  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013148  mov     edx, ebx
0x18001314a  mov     rcx, rax
0x18001314d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013153  lea     rax, WPP_GLOBAL_Control
0x18001315a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013161  cmp     rcx, rax
0x180013164  jz      short loc_18001318B
0x180013166  test    byte ptr [rcx+1Ch], 1
0x18001316a  jz      short loc_18001318B
0x18001316c  cmp     byte ptr [rcx+19h], 2
0x180013170  jb      short loc_18001318B
0x180013172  mov     edx, 33h ; '3'
0x180013177  mov     r9d, ebx
0x18001317a  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013181  mov     rcx, [rcx+10h]
0x180013185  call    WPP_SF_d
0x18001318a  nop
0x18001318b  mov     rcx, [rbp+var_10]
0x18001318f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013195  nop
0x180013196  jmp     loc_1800130B1
0x18001319b  mov     [rbp+arg_10], 0
0x1800131a2  mov     [rbp+arg_0], 0
0x1800131a9  mov     [rbp+arg_18], 0
0x1800131b0  lea     rax, [rbp+arg_18]
0x1800131b4  mov     [rsp+40h+var_20], rax; unsigned int *
0x1800131b9  lea     r9, [rbp+arg_0]; unsigned int *
0x1800131bd  lea     r8, [rbp+arg_10]; unsigned int *
0x1800131c1  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x1800131c5  call    ?ParseInfoFromIndexFile@CObjectHeap@@IEAAJPEBGPEAK11@Z; CObjectHeap::ParseInfoFromIndexFile(ushort const *,ulong *,ulong *,ulong *)
0x1800131ca  cmp     eax, 57h ; 'W'
0x1800131cd  jnz     short loc_18001323A
0x1800131cf  xor     r8d, r8d; unsigned int
0x1800131d2  xor     edx, edx; bool
0x1800131d4  lea     ecx, [rax-55h]; int
0x1800131d7  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x1800131dc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800131e2  mov     ebx, 10DDh
0x1800131e7  mov     edx, ebx
0x1800131e9  mov     rcx, rax
0x1800131ec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800131f2  lea     rax, WPP_GLOBAL_Control
0x1800131f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013200  cmp     rcx, rax
0x180013203  jz      short loc_18001322A
0x180013205  test    byte ptr [rcx+1Ch], 1
0x180013209  jz      short loc_18001322A
0x18001320b  cmp     byte ptr [rcx+19h], 2
0x18001320f  jb      short loc_18001322A
0x180013211  mov     edx, 34h ; '4'
0x180013216  mov     r9d, ebx
0x180013219  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013220  mov     rcx, [rcx+10h]
0x180013224  call    WPP_SF_d
0x180013229  nop
0x18001322a  mov     rcx, [rbp+var_10]
0x18001322e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013234  nop
0x180013235  jmp     loc_1800130B1
0x18001323a  lea     rcx, [rsi+10h]; this
0x18001323e  mov     r8d, [rbp+arg_0]; unsigned int
0x180013242  mov     edx, [rbp+arg_10]; unsigned int
0x180013245  call    ?DeleteBuffer@CVarObjHeap@@QEAAKKK@Z; CVarObjHeap::DeleteBuffer(ulong,ulong)
0x18001324a  mov     ebx, eax
0x18001324c  test    eax, eax
0x18001324e  jz      short loc_1800132A9
0x180013250  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013256  mov     edx, ebx
0x180013258  mov     rcx, rax
0x18001325b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013261  lea     rax, WPP_GLOBAL_Control
0x180013268  mov     rcx, cs:WPP_GLOBAL_Control
0x18001326f  cmp     rcx, rax
0x180013272  jz      short loc_180013299
0x180013274  test    byte ptr [rcx+1Ch], 1
0x180013278  jz      short loc_180013299
0x18001327a  cmp     byte ptr [rcx+19h], 2
0x18001327e  jb      short loc_180013299
0x180013280  mov     edx, 35h ; '5'
0x180013285  mov     r9d, ebx
0x180013288  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x18001328f  mov     rcx, [rcx+10h]
0x180013293  call    WPP_SF_d
0x180013298  nop
0x180013299  mov     rcx, [rbp+var_10]
0x18001329d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800132a3  nop
0x1800132a4  jmp     loc_1800130B1
0x1800132a9  mov     r8, [rbp+var_10]; unsigned __int16 *
0x1800132ad  mov     rdx, r14; unsigned __int16 *
0x1800132b0  mov     rcx, rsi; this
0x1800132b3  call    ?DeleteIndexFile@CObjectHeap@@IEAAJPEBG0@Z; CObjectHeap::DeleteIndexFile(ushort const *,ushort const *)
0x1800132b8  mov     ebx, eax
0x1800132ba  test    eax, eax
0x1800132bc  jz      short loc_180013317
0x1800132be  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800132c4  mov     edx, ebx
0x1800132c6  mov     rcx, rax
0x1800132c9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800132cf  lea     rax, WPP_GLOBAL_Control
0x1800132d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132dd  cmp     rcx, rax
0x1800132e0  jz      short loc_180013307
0x1800132e2  test    byte ptr [rcx+1Ch], 1
0x1800132e6  jz      short loc_180013307
0x1800132e8  cmp     byte ptr [rcx+19h], 2
0x1800132ec  jb      short loc_180013307
0x1800132ee  mov     edx, 36h ; '6'
0x1800132f3  mov     r9d, ebx
0x1800132f6  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x1800132fd  mov     rcx, [rcx+10h]
0x180013301  call    WPP_SF_d
0x180013306  nop
0x180013307  mov     rcx, [rbp+var_10]
0x18001330b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013311  nop
0x180013312  jmp     loc_1800130B1
0x180013317  lea     rax, WPP_GLOBAL_Control
0x18001331e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013325  cmp     rcx, rax
0x180013328  jz      short loc_18001334F
0x18001332a  test    byte ptr [rcx+1Ch], 1
0x18001332e  jz      short loc_18001334F
0x180013330  cmp     byte ptr [rcx+19h], 2
0x180013334  jb      short loc_18001334F
0x180013336  mov     edx, 37h ; '7'
0x18001333b  xor     r9d, r9d
0x18001333e  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013345  mov     rcx, [rcx+10h]
0x180013349  call    WPP_SF_d
0x18001334e  nop
0x18001334f  mov     rcx, [rbp+var_10]
0x180013353  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180013359  nop
0x18001335a  xor     eax, eax
0x18001335c  mov     rbx, [rsp+40h+arg_8]
0x180013361  add     rsp, 40h
0x180013365  pop     r14
0x180013367  pop     rsi
0x180013368  pop     rbp
0x180013369  retn
```
