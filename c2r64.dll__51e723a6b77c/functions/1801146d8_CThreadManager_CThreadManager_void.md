# CThreadManager::~CThreadManager(void)

- ea: `0x1801146d8`
- end: `0x180114896`
- name: `??1CThreadManager@@MEAA@XZ`
- size: `446`
- prototype: `void __fastcall(CThreadManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1801149a0`

## callees

- `0x18001f760`
- `0x1800264b4`
- `0x1801069a0`
- `0x180107694`
- `0x18010d2c4`
- `0x1801145dc`
- `0x1801146d8`
- `0x1801148b8`
- `0x180115050`
- `0x180116288`
- `0x1801174dc`
- `0x1801175b0`
- `0x180146090`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180114807`
- `KERNEL32!DeleteCriticalSection` at `0x180114807`
- `KERNEL32!FlsFree` at `0x1801147e8`
- `KERNEL32!FlsFree` at `0x1801147e8`
- `KERNEL32!CloseHandle` at `0x18011478d`
- `KERNEL32!CloseHandle` at `0x18011478d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CThreadManager::~CThreadManager(CThreadManager *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  CMainThreadState *v7; // rcx
  DWORD v8; // ecx
  __int64 v9; // rdi
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &CThreadManager::`vftable'{for `ITpThreadManagerInternal'};
  *((_QWORD *)this + 1) = &CThreadManager::`vftable'{for `CWorkOwner'};
  CThreadManager::StartShutdown(this);
  CThreadManager::HrEndShutdown(this);
  CThreadManager::DumpLeaks(this);
  if ( *((_DWORD *)this + 150) )
    MsoShipAssertTagProc(507553755);
  v2 = *((_QWORD *)this + 11);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 11) = 0;
  }
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 4) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 24);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 24) = 0;
  }
  v6 = *((_QWORD *)this + 25);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 25) = 0;
  }
  v7 = (CMainThreadState *)*((_QWORD *)this + 9);
  if ( v7 )
  {
    CMainThreadState::Release(v7);
    *((_QWORD *)this + 9) = 0;
  }
  CThreadManager::ReleaseAllResources(this);
  v8 = *((_DWORD *)this + 10);
  if ( v8 != -1 )
    FlsFree(v8);
  SafeRelease<CTpWorkObject>((char *)this + 80);
  v9 = *((_QWORD *)this + 22);
  if ( v9 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
    operator delete((void *)v9);
    *((_QWORD *)this + 22) = 0;
  }
  v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 8);
  if ( v10 )
    (**v10)(v10, 1);
  v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 7);
  if ( v11 )
    (**v11)(v11, 1);
  CTpQueue::~CTpQueue((__int64 **)this + 58);
  CTpQueue::~CTpQueue((__int64 **)this + 42);
  CTpQueue::~CTpQueue((__int64 **)this + 26);
  CHandleList::~CHandleList((CThreadManager *)((char *)this + 96));
  CWorkOwner::~CWorkOwner((CThreadManager *)((char *)this + 8));
}

```

## disassembly

```asm
0x1801146d8  mov     [rsp+arg_0], rbx
0x1801146dd  mov     [rsp+arg_8], rsi
0x1801146e2  push    rdi
0x1801146e3  sub     rsp, 20h
0x1801146e7  mov     rbx, rcx
0x1801146ea  lea     rax, ??_7CThreadManager@@6BITpThreadManagerInternal@@@; const CThreadManager::`vftable'{for `ITpThreadManagerInternal'}
0x1801146f1  mov     [rcx], rax
0x1801146f4  lea     rax, ??_7CThreadManager@@6BCWorkOwner@@@; const CThreadManager::`vftable'{for `CWorkOwner'}
0x1801146fb  mov     [rcx+8], rax
0x1801146ff  call    ?StartShutdown@CThreadManager@@UEAAXXZ; CThreadManager::StartShutdown(void)
0x180114704  mov     rcx, rbx
0x180114707  call    ?HrEndShutdown@CThreadManager@@QEAAJW4eShutdownMode@@@Z; CThreadManager::HrEndShutdown(eShutdownMode)
0x18011470c  mov     rcx, rbx; this
0x18011470f  call    ?DumpLeaks@CThreadManager@@UEAAXXZ; CThreadManager::DumpLeaks(void)
0x180114714  cmp     dword ptr [rbx+258h], 0
0x18011471b  jz      short loc_180114727
0x18011471d  mov     ecx, 1E40A7DBh
0x180114722  call    MsoShipAssertTagProc
0x180114727  mov     rcx, [rbx+58h]
0x18011472b  test    rcx, rcx
0x18011472e  jz      short loc_180114745
0x180114730  mov     rax, [rcx]
0x180114733  mov     rax, [rax+10h]
0x180114737  call    cs:__guard_dispatch_icall_fptr
0x18011473d  mov     qword ptr [rbx+58h], 0
0x180114745  mov     rcx, [rbx+18h]
0x180114749  test    rcx, rcx
0x18011474c  jz      short loc_180114763
0x18011474e  mov     rax, [rcx]
0x180114751  mov     rax, [rax+10h]
0x180114755  call    cs:__guard_dispatch_icall_fptr
0x18011475b  mov     qword ptr [rbx+18h], 0
0x180114763  mov     rcx, [rbx+20h]
0x180114767  test    rcx, rcx
0x18011476a  jz      short loc_180114781
0x18011476c  mov     rax, [rcx]
0x18011476f  mov     rax, [rax+10h]
0x180114773  call    cs:__guard_dispatch_icall_fptr
0x180114779  mov     qword ptr [rbx+20h], 0
0x180114781  mov     rcx, [rbx+0C0h]; hObject
0x180114788  test    rcx, rcx
0x18011478b  jz      short loc_18011479E
0x18011478d  call    cs:__imp_CloseHandle
0x180114793  mov     qword ptr [rbx+0C0h], 0
0x18011479e  mov     rcx, [rbx+0C8h]
0x1801147a5  test    rcx, rcx
0x1801147a8  jz      short loc_1801147C2
0x1801147aa  mov     rax, [rcx]
0x1801147ad  mov     rax, [rax+10h]
0x1801147b1  call    cs:__guard_dispatch_icall_fptr
0x1801147b7  mov     qword ptr [rbx+0C8h], 0
0x1801147c2  mov     rcx, [rbx+48h]; this
0x1801147c6  test    rcx, rcx
0x1801147c9  jz      short loc_1801147D8
0x1801147cb  call    ?Release@CMainThreadState@@QEAAKXZ; CMainThreadState::Release(void)
0x1801147d0  mov     qword ptr [rbx+48h], 0
0x1801147d8  mov     rcx, rbx; this
0x1801147db  call    ?ReleaseAllResources@CThreadManager@@IEAAXXZ; CThreadManager::ReleaseAllResources(void)
0x1801147e0  mov     ecx, [rbx+28h]; dwFlsIndex
0x1801147e3  cmp     ecx, 0FFFFFFFFh
0x1801147e6  jz      short loc_1801147EE
0x1801147e8  call    cs:__imp_FlsFree
0x1801147ee  lea     rcx, [rbx+50h]
0x1801147f2  call    ??$SafeRelease@VCTpWorkObject@@@@YAXAEAPEAVCTpWorkObject@@@Z; SafeRelease<CTpWorkObject>(CTpWorkObject * &)
0x1801147f7  mov     rdi, [rbx+0B0h]
0x1801147fe  test    rdi, rdi
0x180114801  jz      short loc_180114821
0x180114803  lea     rcx, [rdi+8]; lpCriticalSection
0x180114807  call    cs:__imp_DeleteCriticalSection
0x18011480d  nop
0x18011480e  mov     rcx, rdi; void *
0x180114811  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180114816  mov     qword ptr [rbx+0B0h], 0
0x180114821  mov     rcx, [rbx+40h]
0x180114825  mov     edi, 1
0x18011482a  test    rcx, rcx
0x18011482d  jz      short loc_18011483D
0x18011482f  mov     rax, [rcx]
0x180114832  mov     edx, edi
0x180114834  mov     rax, [rax]
0x180114837  call    cs:__guard_dispatch_icall_fptr
0x18011483d  mov     rcx, [rbx+38h]
0x180114841  test    rcx, rcx
0x180114844  jz      short loc_180114854
0x180114846  mov     rax, [rcx]
0x180114849  mov     edx, edi
0x18011484b  mov     rax, [rax]
0x18011484e  call    cs:__guard_dispatch_icall_fptr
0x180114854  lea     rcx, [rbx+1D0h]; this
0x18011485b  call    ??1CTpQueue@@QEAA@XZ; CTpQueue::~CTpQueue(void)
0x180114860  lea     rcx, [rbx+150h]; this
0x180114867  call    ??1CTpQueue@@QEAA@XZ; CTpQueue::~CTpQueue(void)
0x18011486c  lea     rcx, [rbx+0D0h]; this
0x180114873  call    ??1CTpQueue@@QEAA@XZ; CTpQueue::~CTpQueue(void)
0x180114878  lea     rcx, [rbx+60h]; this
0x18011487c  call    ??1CHandleList@@QEAA@XZ; CHandleList::~CHandleList(void)
0x180114881  lea     rcx, [rbx+8]; this
0x180114885  mov     rbx, [rsp+28h+arg_0]
0x18011488a  mov     rsi, [rsp+28h+arg_8]
0x18011488f  add     rsp, 20h
0x180114893  pop     rdi
0x180114894  jmp     short ??1CWorkOwner@@UEAA@XZ; CWorkOwner::~CWorkOwner(void)
```
