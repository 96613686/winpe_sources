# CLogMgr::_WriteChkPt(_LOGRECHEADER *,_LOGREC *,ulong)

- ea: `0x180008768`
- end: `0x180008800`
- name: `?_WriteChkPt@CLogMgr@@AEAAKPEAU_LOGRECHEADER@@PEAU_LOGREC@@K@Z`
- size: `152`
- prototype: `__int64 __fastcall(CLogMgr *this, struct _LOGRECHEADER *, struct _LOGREC *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006f8c`

## callees

- `0x180009298`
- `0x18000d3ec`
- `0x18000d620`

## pseudocode

```c
__int64 __fastcall CLogMgr::_WriteChkPt(CLogMgr *this, struct _LOGRECHEADER *a2, struct _LOGREC *a3, unsigned int a4)
{
  unsigned int v7; // ebx
  struct _WRITELISTELEMENT *v9; // [rsp+20h] [rbp-38h]
  int v10; // [rsp+20h] [rbp-38h]
  unsigned int v11; // [rsp+30h] [rbp-28h]
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = 0;
  CWriteMap::Init(*((CWriteMap **)this + 78), *((struct CLogStorage **)this + 49), a3 != 0, a3, v9);
  v7 = CLogState::AttemptWrite(
         *((CLogState **)this + 50),
         a2,
         *((struct CWriteMap **)this + 78),
         (_DWORD)this + 616,
         v10,
         a4,
         v11,
         (union _ULARGE_INTEGER *)this + 77,
         &v12);
  CWriteMap::CopyRecord(*((CWriteMap **)this + 78), a2, v12);
  return v7;
}

```

## disassembly

```asm
0x180008768  mov     [rsp+arg_8], rbx
0x18000876d  mov     [rsp+arg_10], rsi
0x180008772  push    rdi
0x180008773  sub     rsp, 50h
0x180008777  mov     rdi, rdx
0x18000877a  mov     [rsp+58h+arg_0], 0
0x180008782  mov     rdx, [rcx+188h]; struct CLogStorage *
0x180008789  mov     rsi, rcx
0x18000878c  mov     rcx, [rcx+270h]; this
0x180008793  mov     ebx, r9d
0x180008796  mov     r9, r8; struct _LOGREC *
0x180008799  xor     r8d, r8d
0x18000879c  test    r9, r9
0x18000879f  setnz   r8b; unsigned int
0x1800087a3  call    ?Init@CWriteMap@@QEAAXPEAVCLogStorage@@KPEAU_LOGREC@@PEAU_WRITELISTELEMENT@@@Z; CWriteMap::Init(CLogStorage *,ulong,_LOGREC *,_WRITELISTELEMENT *)
0x1800087a8  mov     r8, [rsi+270h]; struct CWriteMap *
0x1800087af  lea     rax, [rsp+58h+arg_0]
0x1800087b4  mov     rcx, [rsi+190h]; this
0x1800087bb  lea     r9, [rsi+268h]; int
0x1800087c2  mov     [rsp+58h+var_18], rax; unsigned int *
0x1800087c7  mov     rdx, rdi; struct _LOGRECHEADER *
0x1800087ca  mov     [rsp+58h+var_20], r9; union _ULARGE_INTEGER *
0x1800087cf  mov     [rsp+58h+var_30], ebx; unsigned int
0x1800087d3  call    ?AttemptWrite@CLogState@@QEAAKPEAU_LOGRECHEADER@@AEAVCWriteMap@@HHKKPEAT_ULARGE_INTEGER@@PEAK@Z; CLogState::AttemptWrite(_LOGRECHEADER *,CWriteMap &,int,int,ulong,ulong,_ULARGE_INTEGER *,ulong *)
0x1800087d8  mov     r8d, [rsp+58h+arg_0]; unsigned int
0x1800087dd  mov     rdx, rdi; struct _LOGRECHEADER *
0x1800087e0  mov     rcx, [rsi+270h]; this
0x1800087e7  mov     ebx, eax
0x1800087e9  call    ?CopyRecord@CWriteMap@@QEAAXAEAU_LOGRECHEADER@@K@Z; CWriteMap::CopyRecord(_LOGRECHEADER &,ulong)
0x1800087ee  mov     rsi, [rsp+58h+arg_10]
0x1800087f3  mov     eax, ebx
0x1800087f5  mov     rbx, [rsp+58h+arg_8]
0x1800087fa  add     rsp, 50h
0x1800087fe  pop     rdi
0x1800087ff  retn
```
