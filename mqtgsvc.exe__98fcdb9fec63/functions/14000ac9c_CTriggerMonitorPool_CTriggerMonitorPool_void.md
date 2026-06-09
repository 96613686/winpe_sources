# CTriggerMonitorPool::~CTriggerMonitorPool(void)

- ea: `0x14000ac9c`
- end: `0x14000ae3a`
- name: `??1CTriggerMonitorPool@@EEAA@XZ`
- size: `414`
- prototype: `void __fastcall(CTriggerMonitorPool *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000aeb0`

## callees

- `0x140003868`
- `0x14000393c`
- `0x140004538`
- `0x140004eb4`
- `0x140005e20`
- `0x140006458`
- `0x14000799c`
- `0x14000ab3c`
- `0x14000ac9c`
- `0x14000cb7c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000ad09`
- `KERNEL32!LeaveCriticalSection` at `0x14000ad09`
- `KERNEL32!DeleteCriticalSection` at `0x14000ad44`
- `KERNEL32!DeleteCriticalSection` at `0x14000ae1f`
- `KERNEL32!DeleteCriticalSection` at `0x14000ad44`
- `KERNEL32!DeleteCriticalSection` at `0x14000ae1f`
- `msvcrt!free` at `0x14000ad71`
- `msvcrt!free` at `0x14000ad87`
- `msvcrt!free` at `0x14000adda`
- `msvcrt!free` at `0x14000adf0`
- `msvcrt!free` at `0x14000ad71`
- `msvcrt!free` at `0x14000ad87`
- `msvcrt!free` at `0x14000adda`
- `msvcrt!free` at `0x14000adf0`

## pseudocode

```c
void __fastcall CTriggerMonitorPool::~CTriggerMonitorPool(CTriggerMonitorPool *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 v3; // rbx
  _QWORD **v4; // rax
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _QWORD **v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rcx
  _QWORD *v11; // rdi
  CReference *v12; // rcx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  char v14; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &CTriggerMonitorPool::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  CCriticalSection::Lock((CTriggerMonitorPool *)((char *)this + 224));
  v3 = **((_QWORD **)this + 26);
  while ( v3 != *((_QWORD *)this + 26) )
  {
    v13 = *(_QWORD *)(v3 + 16);
    v3 = *(_QWORD *)std::list<CRuntimeRuleInfo *>::erase((char *)this + 200, &v14, v3);
    P<CAdminMessage>::~P<CAdminMessage>(&v13);
  }
  LeaveCriticalSection(v2);
  _bstr_t::_Free((CTriggerMonitorPool *)((char *)this + 288));
  _bstr_t::_Free((CTriggerMonitorPool *)((char *)this + 280));
  _bstr_t::_Free((CTriggerMonitorPool *)((char *)this + 272));
  SafeRelease<CQueue>(*((CReference **)this + 33));
  DeleteCriticalSection(v2);
  v4 = (_QWORD **)*((_QWORD *)this + 26);
  v5 = *v4;
  *v4 = v4;
  *(_QWORD *)(*((_QWORD *)this + 26) + 8LL) = *((_QWORD *)this + 26);
  *((_QWORD *)this + 27) = 0;
  v6 = (_QWORD *)*((_QWORD *)this + 26);
  if ( v5 != v6 )
  {
    do
    {
      v7 = (_QWORD *)*v5;
      free(v5);
      v5 = v7;
      v6 = (_QWORD *)*((_QWORD *)this + 26);
    }
    while ( v7 != v6 );
  }
  free(v6);
  *((_QWORD *)this + 26) = 0;
  v8 = (_QWORD **)*((_QWORD *)this + 23);
  v9 = *v8;
  *v8 = v8;
  *(_QWORD *)(*((_QWORD *)this + 23) + 8LL) = *((_QWORD *)this + 23);
  *((_QWORD *)this + 24) = 0;
  v10 = (_QWORD *)*((_QWORD *)this + 23);
  if ( v9 != v10 )
  {
    do
    {
      v11 = (_QWORD *)*v9;
      v12 = (CReference *)v9[2];
      if ( v12 )
        CReference::Release(v12);
      free(v9);
      v9 = v11;
      v10 = (_QWORD *)*((_QWORD *)this + 23);
    }
    while ( v11 != v10 );
  }
  free(v10);
  *((_QWORD *)this + 23) = 0;
  R<IObjectContext>::~R<IObjectContext>((__int64 *)this + 21);
  CHandle::~CHandle((void **)this + 19);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  CThread::~CThread(this);
}

```

## disassembly

```asm
0x14000ac9c  mov     [rsp+arg_10], rbx
0x14000aca1  push    rbp
0x14000aca2  push    rsi
0x14000aca3  push    rdi
0x14000aca4  sub     rsp, 20h
0x14000aca8  mov     rsi, rcx
0x14000acab  lea     rax, ??_7CTriggerMonitorPool@@6B@; const CTriggerMonitorPool::`vftable'
0x14000acb2  mov     [rcx], rax
0x14000acb5  lea     rdi, [rcx+0E0h]
0x14000acbc  mov     rcx, rdi; this
0x14000acbf  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x14000acc4  mov     rbx, [rsi+0D0h]
0x14000accb  mov     rbx, [rbx]
0x14000acce  lea     rbp, [rsi+0C8h]
0x14000acd5  cmp     rbx, [rsi+0D0h]
0x14000acdc  jz      short loc_14000AD06
0x14000acde  mov     rax, [rbx+10h]
0x14000ace2  mov     [rsp+38h+arg_0], rax
0x14000ace7  mov     r8, rbx
0x14000acea  lea     rdx, [rsp+38h+arg_8]
0x14000acef  mov     rcx, rbp
0x14000acf2  call    ?erase@?$list@PEAVCRuntimeRuleInfo@@V?$allocator@PEAVCRuntimeRuleInfo@@@std@@@std@@QEAA?AViterator@12@V312@@Z; std::list<CRuntimeRuleInfo *>::erase(std::list<CRuntimeRuleInfo *>::iterator)
0x14000acf7  mov     rbx, [rax]
0x14000acfa  lea     rcx, [rsp+38h+arg_0]
0x14000acff  call    ??1?$P@VCAdminMessage@@@@QEAA@XZ; P<CAdminMessage>::~P<CAdminMessage>(void)
0x14000ad04  jmp     short loc_14000ACD5
0x14000ad06  mov     rcx, rdi; lpCriticalSection
0x14000ad09  call    cs:__imp_LeaveCriticalSection
0x14000ad0f  nop
0x14000ad10  lea     rcx, [rsi+120h]; this
0x14000ad17  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000ad1c  lea     rcx, [rsi+118h]; this
0x14000ad23  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000ad28  lea     rcx, [rsi+110h]; this
0x14000ad2f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000ad34  mov     rcx, [rsi+108h]
0x14000ad3b  call    ??$SafeRelease@VCQueue@@@@YAXPEAVCQueue@@@Z; SafeRelease<CQueue>(CQueue *)
0x14000ad40  nop
0x14000ad41  mov     rcx, rdi; lpCriticalSection
0x14000ad44  call    cs:__imp_DeleteCriticalSection
0x14000ad4a  nop
0x14000ad4b  mov     rax, [rbp+8]
0x14000ad4f  mov     rcx, [rax]; Block
0x14000ad52  mov     [rax], rax
0x14000ad55  mov     rax, [rbp+8]
0x14000ad59  mov     [rax+8], rax
0x14000ad5d  mov     qword ptr [rbp+10h], 0
0x14000ad65  mov     rax, [rbp+8]
0x14000ad69  cmp     rcx, rax
0x14000ad6c  jz      short loc_14000AD84
0x14000ad6e  mov     rbx, [rcx]
0x14000ad71  call    cs:__imp_free
0x14000ad77  nop
0x14000ad78  mov     rcx, rbx
0x14000ad7b  mov     rax, [rbp+8]
0x14000ad7f  cmp     rbx, rax
0x14000ad82  jnz     short loc_14000AD6E
0x14000ad84  mov     rcx, rax; Block
0x14000ad87  call    cs:__imp_free
0x14000ad8d  nop
0x14000ad8e  mov     qword ptr [rbp+8], 0
0x14000ad96  mov     rax, [rsi+0B8h]
0x14000ad9d  mov     rbx, [rax]
0x14000ada0  mov     [rax], rax
0x14000ada3  mov     rax, [rsi+0B8h]
0x14000adaa  mov     [rax+8], rax
0x14000adae  mov     qword ptr [rsi+0C0h], 0
0x14000adb9  mov     rcx, [rsi+0B8h]
0x14000adc0  cmp     rbx, rcx
0x14000adc3  jz      short loc_14000ADF0
0x14000adc5  mov     rdi, [rbx]
0x14000adc8  mov     rcx, [rbx+10h]; this
0x14000adcc  test    rcx, rcx
0x14000adcf  jz      short loc_14000ADD7
0x14000add1  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x14000add6  nop
0x14000add7  mov     rcx, rbx; Block
0x14000adda  call    cs:__imp_free
0x14000ade0  nop
0x14000ade1  mov     rbx, rdi
0x14000ade4  mov     rcx, [rsi+0B8h]; Block
0x14000adeb  cmp     rdi, rcx
0x14000adee  jnz     short loc_14000ADC5
0x14000adf0  call    cs:__imp_free
0x14000adf6  nop
0x14000adf7  mov     qword ptr [rsi+0B8h], 0
0x14000ae02  lea     rcx, [rsi+0A8h]
0x14000ae09  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000ae0e  lea     rcx, [rsi+98h]; this
0x14000ae15  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x14000ae1a  nop
0x14000ae1b  lea     rcx, [rsi+60h]; lpCriticalSection
0x14000ae1f  call    cs:__imp_DeleteCriticalSection
0x14000ae25  nop
0x14000ae26  mov     rcx, rsi; this
0x14000ae29  mov     rbx, [rsp+38h+arg_10]
0x14000ae2e  add     rsp, 20h
0x14000ae32  pop     rdi
0x14000ae33  pop     rsi
0x14000ae34  pop     rbp
0x14000ae35  jmp     ??1CThread@@UEAA@XZ; CThread::~CThread(void)
```
