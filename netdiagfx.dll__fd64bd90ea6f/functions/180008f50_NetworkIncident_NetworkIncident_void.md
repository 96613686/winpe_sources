# NetworkIncident::~NetworkIncident(void)

- ea: `0x180008f50`
- end: `0x180009127`
- name: `??1NetworkIncident@@QEAA@XZ`
- size: `471`
- prototype: `void __fastcall(NetworkIncident *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callers

- `0x180004178`

## callees

- `0x180005350`
- `0x180006d58`
- `0x180008d38`
- `0x180008db8`
- `0x180008f50`
- `0x1800094d8`
- `0x18000c454`
- `0x18000f498`
- `0x18001006c`
- `0x1800100e8`
- `0x18001b3a8`
- `0x180023388`
- `0x180023990`
- `0x180023ac8`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `ntdll!WinSqmEndSession` at `0x180009028`
- `ntdll!WinSqmEndSession` at `0x180009028`
- `ntdll!WinSqmSetDWORD` at `0x180008fd0`
- `ntdll!WinSqmSetDWORD` at `0x180009003`
- `ntdll!WinSqmSetDWORD` at `0x18000901b`
- `ntdll!WinSqmSetDWORD` at `0x180008fd0`
- `ntdll!WinSqmSetDWORD` at `0x180009003`
- `ntdll!WinSqmSetDWORD` at `0x18000901b`
- `KERNEL32!DeleteCriticalSection` at `0x1800090a4`
- `KERNEL32!DeleteCriticalSection` at `0x1800090a4`
- `KERNEL32!CloseHandle` at `0x180009097`
- `KERNEL32!CloseHandle` at `0x180009097`
- `KERNEL32!DeleteFileW` at `0x180009040`
- `KERNEL32!DeleteFileW` at `0x180009051`
- `KERNEL32!DeleteFileW` at `0x180009040`
- `KERNEL32!DeleteFileW` at `0x180009051`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall NetworkIncident::~NetworkIncident(NetworkIncident *this)
{
  struct NetworkDiagnosticsEngine *v2; // rax
  __int64 v3; // rcx
  __int64 v4; // r8
  unsigned __int64 *TickCount; // rax
  unsigned __int64 v6; // rcx
  const WCHAR *TraceFileName; // rax
  unsigned int v8; // edx
  _QWORD *v9; // rdi
  _QWORD *i; // rbx
  ProblemNode *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  _BYTE v14[16]; // [rsp+30h] [rbp-58h] BYREF

  if ( *((_QWORD *)this + 15) )
  {
    v2 = NetworkDiagnosticsEngine::Instance();
    if ( !v2
      || (v3 = *((_QWORD *)v2 + 4)) == 0
      || (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 8LL))(v3, *((_QWORD *)this + 15)) < 0 )
    {
      UtilCleanupSQMSession(*((struct SQMSession **)this + 15));
    }
  }
  if ( (int)CTraceController::Stop((NetworkIncident *)((char *)this + 128)) < 0 )
    v4 = 2;
  else
    v4 = 0;
  WinSqmSetDWORD(*((_QWORD *)this + 21), 4052, v4);
  TickCount = (unsigned __int64 *)ATL::CTime::GetTickCount(v14);
  v6 = *((_QWORD *)this + 24);
  if ( v6 && *TickCount > v6 )
    WinSqmSetDWORD(*((_QWORD *)this + 21), 4053, (unsigned int)*TickCount - (unsigned int)v6);
  WinSqmSetDWORD(*((_QWORD *)this + 21), 201, 13893632);
  WinSqmEndSession(*((_QWORD *)this + 21));
  *((_QWORD *)this + 21) = 0;
  DeleteFileW(*((LPCWSTR *)this + 28));
  TraceFileName = CTraceController::GetTraceFileName((NetworkIncident *)((char *)this + 128));
  DeleteFileW(TraceFileName);
  std::list<ProblemNode *>::clear((char *)this + 280);
  v9 = (_QWORD *)*((_QWORD *)this + 37);
  for ( i = (_QWORD *)*v9; i != v9; i = (_QWORD *)*i )
  {
    v11 = (ProblemNode *)i[2];
    if ( v11 )
      ProblemNode::`scalar deleting destructor'(v11, v8);
  }
  std::list<ProblemNode *>::clear((char *)this + 296);
  CloseHandle(*((HANDLE *)this + 9));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  if ( (byte_180041BC1 & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v12, StopNDFIncident, v13, 1, v14);
  std::list<ProblemNode *>::~list<ProblemNode *>((char *)this + 296);
  std::list<ProblemNode *>::~list<ProblemNode *>((char *)this + 280);
  std::deque<ProblemNode *>::~deque<ProblemNode *>((char *)this + 240);
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 28) - 24LL));
  CTraceController::~CTraceController((NetworkIncident *)((char *)this + 128));
  std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>((char *)this + 32);
}

```

## disassembly

```asm
0x180008f50  push    rbx
0x180008f52  push    rbp
0x180008f53  push    rsi
0x180008f54  push    rdi
0x180008f55  push    r14
0x180008f57  push    r15
0x180008f59  sub     rsp, 58h
0x180008f5d  mov     rax, cs:__security_cookie
0x180008f64  xor     rax, rsp
0x180008f67  mov     [rsp+88h+var_48], rax
0x180008f6c  mov     rsi, rcx
0x180008f6f  cmp     qword ptr [rcx+78h], 0
0x180008f74  jz      short loc_180008FA6
0x180008f76  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180008f7b  test    rax, rax
0x180008f7e  jz      short loc_180008F9D
0x180008f80  mov     rcx, [rax+20h]
0x180008f84  test    rcx, rcx
0x180008f87  jz      short loc_180008F9D
0x180008f89  mov     rax, [rcx]
0x180008f8c  mov     rdx, [rsi+78h]
0x180008f90  mov     rax, [rax+8]
0x180008f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f99  test    eax, eax
0x180008f9b  jns     short loc_180008FA6
0x180008f9d  mov     rcx, [rsi+78h]; struct SQMSession *
0x180008fa1  call    ?UtilCleanupSQMSession@@YAXPEAVSQMSession@@@Z; UtilCleanupSQMSession(SQMSession *)
0x180008fa6  lea     rbp, [rsi+80h]
0x180008fad  mov     rcx, rbp; this
0x180008fb0  call    ?Stop@CTraceController@@QEAAJXZ; CTraceController::Stop(void)
0x180008fb5  mov     rcx, [rsi+0A8h]
0x180008fbc  mov     edx, 0FD4h
0x180008fc1  test    eax, eax
0x180008fc3  js      short loc_180008FCA
0x180008fc5  xor     r8d, r8d
0x180008fc8  jmp     short loc_180008FD0
0x180008fca  mov     r8d, 2
0x180008fd0  call    cs:__imp_WinSqmSetDWORD
0x180008fd6  lea     rcx, [rsp+88h+var_58]
0x180008fdb  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180008fe0  mov     rcx, [rsi+0C0h]
0x180008fe7  test    rcx, rcx
0x180008fea  jz      short loc_180009009
0x180008fec  mov     r8, [rax]
0x180008fef  cmp     r8, rcx
0x180008ff2  jbe     short loc_180009009
0x180008ff4  sub     r8d, ecx
0x180008ff7  mov     edx, 0FD5h
0x180008ffc  mov     rcx, [rsi+0A8h]
0x180009003  call    cs:__imp_WinSqmSetDWORD
0x180009009  mov     edx, 0C9h
0x18000900e  mov     r8d, 0D40000h
0x180009014  mov     rcx, [rsi+0A8h]
0x18000901b  call    cs:__imp_WinSqmSetDWORD
0x180009021  mov     rcx, [rsi+0A8h]
0x180009028  call    cs:__imp_WinSqmEndSession
0x18000902e  mov     qword ptr [rsi+0A8h], 0
0x180009039  mov     rcx, [rsi+0E0h]; lpFileName
0x180009040  call    cs:__imp_DeleteFileW
0x180009046  mov     rcx, rbp; this
0x180009049  call    ?GetTraceFileName@CTraceController@@QEAAPEBGXZ; CTraceController::GetTraceFileName(void)
0x18000904e  mov     rcx, rax; lpFileName
0x180009051  call    cs:__imp_DeleteFileW
0x180009057  lea     r15, [rsi+118h]
0x18000905e  mov     rcx, r15
0x180009061  call    ?clear@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::clear(void)
0x180009066  lea     r14, [rsi+128h]
0x18000906d  mov     rdi, [r14]
0x180009070  mov     rbx, [rdi]
0x180009073  cmp     rbx, rdi
0x180009076  jz      short loc_18000908B
0x180009078  mov     rcx, [rbx+10h]; this
0x18000907c  test    rcx, rcx
0x18000907f  jz      short loc_180009086
0x180009081  call    ??_GProblemNode@@QEAAPEAXI@Z; ProblemNode::`scalar deleting destructor'(uint)
0x180009086  mov     rbx, [rbx]
0x180009089  jmp     short loc_180009073
0x18000908b  mov     rcx, r14
0x18000908e  call    ?clear@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::clear(void)
0x180009093  mov     rcx, [rsi+48h]; hObject
0x180009097  call    cs:__imp_CloseHandle
0x18000909d  lea     rcx, [rsi+138h]; lpCriticalSection
0x1800090a4  call    cs:__imp_DeleteCriticalSection
0x1800090aa  test    cs:byte_180041BC1, 2
0x1800090b1  jz      short loc_1800090CF
0x1800090b3  lea     rax, [rsp+88h+var_58]
0x1800090b8  mov     [rsp+88h+var_68], rax
0x1800090bd  mov     r9d, 1
0x1800090c3  lea     rdx, StopNDFIncident
0x1800090ca  call    McGenEventWrite_EventWriteTransfer
0x1800090cf  mov     rcx, r14
0x1800090d2  call    ??1?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::~list<ProblemNode *>(void)
0x1800090d7  mov     rcx, r15
0x1800090da  call    ??1?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::~list<ProblemNode *>(void)
0x1800090df  lea     rcx, [rsi+0F0h]
0x1800090e6  call    ??1?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::deque<ProblemNode *>::~deque<ProblemNode *>(void)
0x1800090eb  mov     rcx, [rsi+0E0h]
0x1800090f2  sub     rcx, 18h; this
0x1800090f6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800090fb  mov     rcx, rbp; this
0x1800090fe  call    ??1CTraceController@@QEAA@XZ; CTraceController::~CTraceController(void)
0x180009103  lea     rcx, [rsi+20h]
0x180009107  call    ??1?$vector@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>::~vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>(void)
0x18000910c  nop
0x18000910d  mov     rcx, [rsp+88h+var_48]
0x180009112  xor     rcx, rsp; StackCookie
0x180009115  call    __security_check_cookie
0x18000911a  add     rsp, 58h
0x18000911e  pop     r15
0x180009120  pop     r14
0x180009122  pop     rdi
0x180009123  pop     rsi
0x180009124  pop     rbp
0x180009125  pop     rbx
0x180009126  retn
```
