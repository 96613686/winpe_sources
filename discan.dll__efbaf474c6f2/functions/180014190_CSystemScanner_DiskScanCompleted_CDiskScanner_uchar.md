# CSystemScanner::DiskScanCompleted(CDiskScanner *,uchar)

- ea: `0x180014190`
- end: `0x1800142cf`
- name: `?DiskScanCompleted@CSystemScanner@@UEAAXPEAVCDiskScanner@@E@Z`
- size: `319`
- prototype: `void __fastcall(CSystemScanner *__hidden this, struct CDiskScanner *, unsigned __int8)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003660`
- `0x180013510`
- `0x1800137d4`
- `0x180013a88`
- `0x180014190`
- `0x180014698`
- `0x180016400`
- `0x180016450`
- `0x180017034`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800141ec`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014248`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800141ec`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014248`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800142ab`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800142ab`

## string_xrefs

- `0x1800141c5`: `CSystemScanner::DiskScanCompleted`

## pseudocode

```c
void __fastcall CSystemScanner::DiskScanCompleted(CSystemScanner *this, struct CDiskScanner *a2, unsigned __int8 a3)
{
  int v3; // esi
  unsigned int Key; // eax
  __int64 v7; // rcx
  int v8; // edi
  unsigned int v9; // ebp
  int v10; // r14d
  __int64 v11; // rdx
  __int64 v12; // r8
  RTL_SRWLOCK *v13; // [rsp+60h] [rbp+8h] BYREF
  char v14; // [rsp+68h] [rbp+10h] BYREF

  v3 = a3;
  *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL) = "CSystemScanner::DiskScanCompleted";
  CTraceImp::CTraceImp((CTraceImp *)&v14);
  if ( a2 )
  {
    v13 = (RTL_SRWLOCK *)((char *)this + 152);
    AcquireSRWLockExclusive((PSRWLOCK)this + 19);
    Key = ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::FindKey(
            (char *)this + 208,
            (char *)a2 + 16);
    if ( Key != -1 )
      ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::RemoveAt(
        v7,
        Key);
    CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::Close((__int64)a2 + 248);
    ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::RemoveAt(
      (char *)this + 160,
      *((_QWORD *)a2 + 9));
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v13);
  }
  if ( (_BYTE)v3 )
    _InterlockedIncrement((volatile signed __int32 *)this + 17);
  v13 = (RTL_SRWLOCK *)((char *)this + 48);
  AcquireSRWLockExclusive((PSRWLOCK)this + 6);
  v8 = --*((_DWORD *)this + 14);
  v9 = *((_DWORD *)this + 15);
  v10 = ++*((_DWORD *)this + 16);
  CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v13);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDDl(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, v9, v10, v8, v3);
  }
  if ( !v8 )
    SubmitThreadpoolWork(*((PTP_WORK *)this + 30));
  CTraceImp::~CTraceImp((CTraceImp *)&v14);
}

```

## disassembly

```asm
0x180014190  mov     [rsp+arg_10], rbx
0x180014195  mov     [rsp+arg_18], rbp
0x18001419a  push    rsi
0x18001419b  push    rdi
0x18001419c  push    r14
0x18001419e  sub     rsp, 40h
0x1800141a2  movzx   esi, r8b
0x1800141a6  mov     rdi, rdx
0x1800141a9  mov     rbx, rcx
0x1800141ac  mov     r9d, cs:_tls_index
0x1800141b3  mov     rax, gs:58h
0x1800141bc  mov     ecx, 10h
0x1800141c1  mov     r9, [rax+r9*8]
0x1800141c5  lea     rax, aCsystemscanner_4; "CSystemScanner::DiskScanCompleted"
0x1800141cc  mov     [rcx+r9], rax
0x1800141d0  lea     rcx, [rsp+58h+arg_8]; this
0x1800141d5  call    ??0CTraceImp@@QEAA@XZ; CTraceImp::CTraceImp(void)
0x1800141da  nop
0x1800141db  test    rdi, rdi
0x1800141de  jz      short loc_180014236
0x1800141e0  lea     rcx, [rbx+98h]; SRWLock
0x1800141e7  mov     [rsp+58h+arg_0], rcx
0x1800141ec  call    cs:__imp_AcquireSRWLockExclusive
0x1800141f2  nop
0x1800141f3  lea     rcx, [rbx+0D0h]
0x1800141fa  lea     rdx, [rdi+10h]
0x1800141fe  call    ?FindKey@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEBAHAEBK@Z; ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::FindKey(ulong const &)
0x180014203  cmp     eax, 0FFFFFFFFh
0x180014206  jz      short loc_18001420F
0x180014208  mov     edx, eax
0x18001420a  call    ?RemoveAt@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEAAHH@Z; ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::RemoveAt(int)
0x18001420f  lea     rcx, [rdi+0F8h]
0x180014216  call    ?Close@?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAAXXZ; CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::Close(void)
0x18001421b  lea     rcx, [rbx+0A0h]
0x180014222  mov     rdx, [rdi+48h]
0x180014226  call    ?RemoveAt@?$CAtlList@V?$CAutoPtr@VCDiskScanner@@@ATL@@V?$CAutoPtrElementTraits@VCDiskScanner@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CAutoPtr<CDiskScanner>,ATL::CAutoPtrElementTraits<CDiskScanner>>::RemoveAt(__POSITION *)
0x18001422b  nop
0x18001422c  lea     rcx, [rsp+58h+arg_0]; this
0x180014231  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180014236  test    sil, sil
0x180014239  jz      short loc_18001423F
0x18001423b  lock inc dword ptr [rbx+44h]
0x18001423f  lea     rcx, [rbx+30h]; SRWLock
0x180014243  mov     [rsp+58h+arg_0], rcx
0x180014248  call    cs:__imp_AcquireSRWLockExclusive
0x18001424e  dec     dword ptr [rbx+38h]
0x180014251  mov     edi, [rbx+38h]
0x180014254  mov     ebp, [rbx+3Ch]
0x180014257  inc     dword ptr [rbx+40h]
0x18001425a  mov     r14d, [rbx+40h]
0x18001425e  lea     rcx, [rsp+58h+arg_0]; this
0x180014263  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180014268  lea     rax, WPP_GLOBAL_Control
0x18001426f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014276  cmp     rcx, rax
0x180014279  jz      short loc_1800142A0
0x18001427b  test    byte ptr [rcx+1Ch], 1
0x18001427f  jz      short loc_1800142A0
0x180014281  cmp     byte ptr [rcx+19h], 4
0x180014285  jb      short loc_1800142A0
0x180014287  mov     [rsp+58h+var_28], esi
0x18001428b  mov     [rsp+58h+var_30], edi
0x18001428f  mov     [rsp+58h+var_38], r14d
0x180014294  mov     r9d, ebp
0x180014297  mov     rcx, [rcx+10h]
0x18001429b  call    WPP_SF_DDDl
0x1800142a0  test    edi, edi
0x1800142a2  jnz     short loc_1800142B2
0x1800142a4  mov     rcx, [rbx+0F0h]; pwk
0x1800142ab  call    cs:__imp_SubmitThreadpoolWork
0x1800142b1  nop
0x1800142b2  lea     rcx, [rsp+58h+arg_8]; this
0x1800142b7  call    ??1CTraceImp@@QEAA@XZ; CTraceImp::~CTraceImp(void)
0x1800142bc  mov     rbx, [rsp+58h+arg_10]
0x1800142c1  mov     rbp, [rsp+58h+arg_18]
0x1800142c6  add     rsp, 40h
0x1800142ca  pop     r14
0x1800142cc  pop     rdi
0x1800142cd  pop     rsi
0x1800142ce  retn
```
