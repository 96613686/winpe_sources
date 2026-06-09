# FTP_SERVERP::~FTP_SERVERP(void)

- ea: `0x180005568`
- end: `0x180005624`
- name: `??1FTP_SERVERP@@UEAA@XZ`
- size: `188`
- prototype: `void __fastcall(FTP_SERVERP *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005760`

## callees

- `0x180001250`
- `0x180005568`
- `0x18000562c`
- `0x18001a62c`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180005586`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800055a9`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800055f6`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180005586`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800055a9`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800055f6`
- `iisutil!??1CEtwTracer@@QEAA@XZ` at `0x180005609`
- `iisutil!??1CEtwTracer@@QEAA@XZ` at `0x180005609`
- `iisutil!??1CSpinLock@@QEAA@XZ` at `0x1800055e9`
- `iisutil!??1CSpinLock@@QEAA@XZ` at `0x1800055e9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800055c0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800055c0`

## pseudocode

```c
void __fastcall FTP_SERVERP::~FTP_SERVERP(FTP_SERVERP *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &FTP_SERVERP::`vftable';
  CReaderWriterLock3::~CReaderWriterLock3((FTP_SERVERP *)((char *)this + 416));
  *((_QWORD *)this + 40) = &FTP_HOST_MONITOR::`vftable';
  FTP_HOST_MONITOR::Terminate((FTP_SERVERP *)((char *)this + 320));
  CReaderWriterLock3::~CReaderWriterLock3((FTP_SERVERP *)((char *)this + 396));
  *((_QWORD *)this + 40) = &FTP_TIMEOUT_MONITOR_ENTRY::`vftable';
  STRU::~STRU((char *)this + 248);
  v2 = (void *)*((_QWORD *)this + 25);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 25) = 0;
  }
  CSpinLock::~CSpinLock((FTP_SERVERP *)((char *)this + 240));
  CReaderWriterLock3::~CReaderWriterLock3((FTP_SERVERP *)((char *)this + 168));
  FTP_TIMEOUT_MONITOR::~FTP_TIMEOUT_MONITOR((FTP_SERVERP *)((char *)this + 112));
  CEtwTracer::~CEtwTracer((FTP_SERVERP *)((char *)this + 16));
  *(_QWORD *)this = &FTP_SERVER::`vftable';
}

```

## disassembly

```asm
0x180005568  mov     [rsp+arg_0], rbx
0x18000556d  push    rdi
0x18000556e  sub     rsp, 20h
0x180005572  mov     rdi, rcx
0x180005575  lea     rax, ??_7FTP_SERVERP@@6B@; const FTP_SERVERP::`vftable'
0x18000557c  mov     [rcx], rax
0x18000557f  add     rcx, 1A0h
0x180005586  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000558c  lea     rbx, [rdi+140h]
0x180005593  lea     rax, ??_7FTP_HOST_MONITOR@@6B@; const FTP_HOST_MONITOR::`vftable'
0x18000559a  mov     [rbx], rax
0x18000559d  mov     rcx, rbx; this
0x1800055a0  call    ?Terminate@FTP_HOST_MONITOR@@QEAAXXZ; FTP_HOST_MONITOR::Terminate(void)
0x1800055a5  lea     rcx, [rbx+4Ch]
0x1800055a9  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800055af  lea     rax, ??_7FTP_TIMEOUT_MONITOR_ENTRY@@6B@; const FTP_TIMEOUT_MONITOR_ENTRY::`vftable'
0x1800055b6  mov     [rbx], rax
0x1800055b9  lea     rcx, [rdi+0F8h]
0x1800055c0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800055c6  mov     rcx, [rdi+0C8h]; Block
0x1800055cd  test    rcx, rcx
0x1800055d0  jz      short loc_1800055E2
0x1800055d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800055d7  mov     qword ptr [rdi+0C8h], 0
0x1800055e2  lea     rcx, [rdi+0F0h]
0x1800055e9  call    cs:__imp_??1CSpinLock@@QEAA@XZ; CSpinLock::~CSpinLock(void)
0x1800055ef  lea     rcx, [rdi+0A8h]
0x1800055f6  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800055fc  lea     rcx, [rdi+70h]; this
0x180005600  call    ??1FTP_TIMEOUT_MONITOR@@QEAA@XZ; FTP_TIMEOUT_MONITOR::~FTP_TIMEOUT_MONITOR(void)
0x180005605  lea     rcx, [rdi+10h]
0x180005609  call    cs:__imp_??1CEtwTracer@@QEAA@XZ; CEtwTracer::~CEtwTracer(void)
0x18000560f  lea     rax, ??_7FTP_SERVER@@6B@; const FTP_SERVER::`vftable'
0x180005616  mov     [rdi], rax
0x180005619  mov     rbx, [rsp+28h+arg_0]
0x18000561e  add     rsp, 20h
0x180005622  pop     rdi
0x180005623  retn
```
