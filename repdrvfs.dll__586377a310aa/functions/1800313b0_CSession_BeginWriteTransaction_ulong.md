# CSession::BeginWriteTransaction(ulong)

- ea: `0x1800313b0`
- end: `0x18003153e`
- name: `?BeginWriteTransaction@CSession@@UEAAJK@Z`
- size: `398`
- prototype: `__int64 __fastcall(CSession *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001c898`
- `0x18001d258`
- `0x18001d5f0`
- `0x1800313b0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180031404`
- `wbemcomn!GetMemLogObject` at `0x180031465`
- `wbemcomn!GetMemLogObject` at `0x1800314bd`
- `wbemcomn!GetMemLogObject` at `0x180031404`
- `wbemcomn!GetMemLogObject` at `0x180031465`
- `wbemcomn!GetMemLogObject` at `0x1800314bd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031414`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031475`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800314c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031414`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031475`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800314c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSession::BeginWriteTransaction(CSession *this, unsigned int a2)
{
  CSession *v3; // rcx
  CMemoryLog *MemLogObject; // rax
  unsigned int v5; // ebx
  CVarObjHeap *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  if ( (unsigned int)CLock::WriteLock((CLock *)&g_readWriteLock, a2) )
  {
    MemLogObject = GetMemLogObject();
    v5 = -2147217407;
    CMemoryLog::Write(MemLogObject, -2147217407);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v7 = 62;
    v8 = 2147749889LL;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v8);
    return v5;
  }
  if ( g_bShuttingDown )
  {
    CLock::WriteUnlock((CLock *)&g_readWriteLock);
    v10 = GetMemLogObject();
    v5 = -2147217357;
    CMemoryLog::Write(v10, -2147217357);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v7 = 63;
    v8 = 2147749939LL;
    goto LABEL_10;
  }
  v5 = CSession::InternalBeginTransaction(v3, 1);
  if ( v5 )
  {
    CLock::WriteUnlock((CLock *)&g_readWriteLock);
    if ( (v5 & 0x80000000) != 0 )
    {
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, v5);
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v7 = 64;
    v8 = v5;
    goto LABEL_10;
  }
  *((_BYTE *)this + 168) = 1;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800313b0  push    rbx
0x1800313b2  push    rbp
0x1800313b3  push    rdi
0x1800313b4  push    r14
0x1800313b6  sub     rsp, 28h
0x1800313ba  mov     rdi, rcx
0x1800313bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313c4  lea     rbp, WPP_GLOBAL_Control
0x1800313cb  lea     r14, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800313d2  cmp     rcx, rbp
0x1800313d5  jz      short loc_1800313F4
0x1800313d7  test    byte ptr [rcx+1Ch], 1
0x1800313db  jz      short loc_1800313F4
0x1800313dd  cmp     byte ptr [rcx+19h], 5
0x1800313e1  jb      short loc_1800313F4
0x1800313e3  mov     rcx, [rcx+10h]
0x1800313e7  mov     edx, 3Dh ; '='
0x1800313ec  mov     r8, r14
0x1800313ef  call    WPP_SF_
0x1800313f4  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x1800313fb  call    ?WriteLock@CLock@@QEAAHK@Z; CLock::WriteLock(ulong)
0x180031400  test    eax, eax
0x180031402  jz      short loc_180031450
0x180031404  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003140a  mov     ebx, 80041001h
0x18003140f  mov     rcx, rax
0x180031412  mov     edx, ebx
0x180031414  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003141a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031421  cmp     rcx, rbp
0x180031424  jz      short loc_180031449
0x180031426  test    byte ptr [rcx+1Ch], 1
0x18003142a  jz      short loc_180031449
0x18003142c  cmp     byte ptr [rcx+19h], 2
0x180031430  jb      short loc_180031449
0x180031432  mov     edx, 3Eh ; '>'
0x180031437  mov     r9d, 80041001h
0x18003143d  mov     rcx, [rcx+10h]
0x180031441  mov     r8, r14
0x180031444  call    WPP_SF_d
0x180031449  mov     eax, ebx
0x18003144b  jmp     loc_180031534
0x180031450  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x180031457  jz      short loc_1800314A0
0x180031459  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x180031460  call    ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x180031465  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003146b  mov     ebx, 80041033h
0x180031470  mov     rcx, rax
0x180031473  mov     edx, ebx
0x180031475  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003147b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031482  cmp     rcx, rbp
0x180031485  jz      short loc_180031449
0x180031487  test    byte ptr [rcx+1Ch], 1
0x18003148b  jz      short loc_180031449
0x18003148d  cmp     byte ptr [rcx+19h], 2
0x180031491  jb      short loc_180031449
0x180031493  mov     edx, 3Fh ; '?'
0x180031498  mov     r9d, 80041033h
0x18003149e  jmp     short loc_18003143D
0x1800314a0  mov     dl, 1; bool
0x1800314a2  call    ?InternalBeginTransaction@CSession@@IEAAJ_N@Z; CSession::InternalBeginTransaction(bool)
0x1800314a7  mov     ebx, eax
0x1800314a9  test    eax, eax
0x1800314ab  jz      short loc_1800314FF
0x1800314ad  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x1800314b4  call    ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x1800314b9  test    ebx, ebx
0x1800314bb  jns     short loc_1800314CE
0x1800314bd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800314c3  mov     rcx, rax
0x1800314c6  mov     edx, ebx
0x1800314c8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800314ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800314d5  cmp     rcx, rbp
0x1800314d8  jz      loc_180031449
0x1800314de  test    byte ptr [rcx+1Ch], 1
0x1800314e2  jz      loc_180031449
0x1800314e8  cmp     byte ptr [rcx+19h], 2
0x1800314ec  jb      loc_180031449
0x1800314f2  mov     edx, 40h ; '@'
0x1800314f7  mov     r9d, ebx
0x1800314fa  jmp     loc_18003143D
0x1800314ff  mov     byte ptr [rdi+0A8h], 1
0x180031506  mov     rcx, cs:WPP_GLOBAL_Control
0x18003150d  cmp     rcx, rbp
0x180031510  jz      short loc_180031532
0x180031512  test    byte ptr [rcx+1Ch], 1
0x180031516  jz      short loc_180031532
0x180031518  cmp     byte ptr [rcx+19h], 2
0x18003151c  jb      short loc_180031532
0x18003151e  mov     rcx, [rcx+10h]
0x180031522  mov     edx, 41h ; 'A'
0x180031527  xor     r9d, r9d
0x18003152a  mov     r8, r14
0x18003152d  call    WPP_SF_d
0x180031532  xor     eax, eax
0x180031534  add     rsp, 28h
0x180031538  pop     r14
0x18003153a  pop     rdi
0x18003153b  pop     rbp
0x18003153c  pop     rbx
0x18003153d  retn
```
