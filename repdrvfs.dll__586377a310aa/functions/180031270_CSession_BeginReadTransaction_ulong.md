# CSession::BeginReadTransaction(ulong)

- ea: `0x180031270`
- end: `0x1800313a6`
- name: `?BeginReadTransaction@CSession@@UEAAJK@Z`
- size: `310`
- prototype: `__int64 __fastcall(CSession *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x1800037a0`
- `0x180003fb0`
- `0x180031270`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800312ba`
- `wbemcomn!GetMemLogObject` at `0x180031320`
- `wbemcomn!GetMemLogObject` at `0x1800312ba`
- `wbemcomn!GetMemLogObject` at `0x180031320`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800312c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003132e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800312c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003132e`

## pseudocode

```c
__int64 __fastcall CSession::BeginReadTransaction(CSession *this, unsigned int a2)
{
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v4; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  if ( (unsigned int)CLock::ReadLock((CLock *)&g_readWriteLock, a2) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217407);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
    }
    return 2147749889LL;
  }
  else if ( g_bShuttingDown )
  {
    CLock::ReadUnlock((CLock *)&g_readWriteLock);
    v4 = GetMemLogObject();
    CMemoryLog::Write(v4, -2147217357);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
    }
    return 2147749939LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 0);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180031270  push    rsi
0x180031272  sub     rsp, 20h
0x180031276  mov     rcx, cs:WPP_GLOBAL_Control
0x18003127d  lea     rsi, WPP_GLOBAL_Control
0x180031284  cmp     rcx, rsi
0x180031287  jz      short loc_1800312AA
0x180031289  test    byte ptr [rcx+1Ch], 1
0x18003128d  jz      short loc_1800312AA
0x18003128f  cmp     byte ptr [rcx+19h], 5
0x180031293  jb      short loc_1800312AA
0x180031295  mov     rcx, [rcx+10h]
0x180031299  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800312a0  mov     edx, 42h ; 'B'
0x1800312a5  call    WPP_SF_
0x1800312aa  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x1800312b1  call    ?ReadLock@CLock@@QEAAHK@Z; CLock::ReadLock(ulong)
0x1800312b6  test    eax, eax
0x1800312b8  jz      short loc_18003130B
0x1800312ba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800312c0  mov     rcx, rax
0x1800312c3  mov     edx, 80041001h
0x1800312c8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800312ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312d5  cmp     rcx, rsi
0x1800312d8  jz      short loc_180031301
0x1800312da  test    byte ptr [rcx+1Ch], 1
0x1800312de  jz      short loc_180031301
0x1800312e0  cmp     byte ptr [rcx+19h], 2
0x1800312e4  jb      short loc_180031301
0x1800312e6  mov     rcx, [rcx+10h]
0x1800312ea  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800312f1  mov     edx, 43h ; 'C'
0x1800312f6  mov     r9d, 80041001h
0x1800312fc  call    WPP_SF_d
0x180031301  mov     eax, 80041001h
0x180031306  jmp     loc_1800313A0
0x18003130b  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x180031312  jz      short loc_18003136E
0x180031314  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x18003131b  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180031320  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180031326  mov     rcx, rax
0x180031329  mov     edx, 80041033h
0x18003132e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180031334  mov     rcx, cs:WPP_GLOBAL_Control
0x18003133b  cmp     rcx, rsi
0x18003133e  jz      short loc_180031367
0x180031340  test    byte ptr [rcx+1Ch], 1
0x180031344  jz      short loc_180031367
0x180031346  cmp     byte ptr [rcx+19h], 2
0x18003134a  jb      short loc_180031367
0x18003134c  mov     rcx, [rcx+10h]
0x180031350  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180031357  mov     edx, 44h ; 'D'
0x18003135c  mov     r9d, 80041033h
0x180031362  call    WPP_SF_d
0x180031367  mov     eax, 80041033h
0x18003136c  jmp     short loc_1800313A0
0x18003136e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031375  cmp     rcx, rsi
0x180031378  jz      short loc_18003139E
0x18003137a  test    byte ptr [rcx+1Ch], 1
0x18003137e  jz      short loc_18003139E
0x180031380  cmp     byte ptr [rcx+19h], 2
0x180031384  jb      short loc_18003139E
0x180031386  mov     rcx, [rcx+10h]
0x18003138a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180031391  mov     edx, 45h ; 'E'
0x180031396  xor     r9d, r9d
0x180031399  call    WPP_SF_d
0x18003139e  xor     eax, eax
0x1800313a0  add     rsp, 20h
0x1800313a4  pop     rsi
0x1800313a5  retn
```
