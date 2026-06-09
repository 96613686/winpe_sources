# CWorkerThread::~CWorkerThread(void)

- ea: `0x180010848`
- end: `0x18001088b`
- name: `??1CWorkerThread@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CWorkerThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef8c`

## callees

- `0x180009690`
- `0x18000ac14`
- `0x180010894`
- `0x1800109d4`

## pseudocode

```c
void __fastcall CWorkerThread::~CWorkerThread(CWorkerThread *this)
{
  CWorkerThread::Stop(this, 1);
  CWorkerThread::ReleaseResources(this);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)this + 3);
  ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>((__int64 *)this + 2);
  ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>((__int64 *)this + 1);
  ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>((__int64 *)this);
}

```

## disassembly

```asm
0x180010848  push    rbx
0x18001084a  sub     rsp, 20h
0x18001084e  mov     edx, 1; int
0x180010853  mov     rbx, rcx
0x180010856  call    ?Stop@CWorkerThread@@QEAAJH@Z; CWorkerThread::Stop(int)
0x18001085b  mov     rcx, rbx; this
0x18001085e  call    ?ReleaseResources@CWorkerThread@@AEAAXXZ; CWorkerThread::ReleaseResources(void)
0x180010863  lea     rcx, [rbx+18h]
0x180010867  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001086c  lea     rcx, [rbx+10h]
0x180010870  call    ??1?$CComPtrBase@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>(void)
0x180010875  lea     rcx, [rbx+8]
0x180010879  call    ??1?$CComPtrBase@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>(void)
0x18001087e  mov     rcx, rbx
0x180010881  add     rsp, 20h
0x180010885  pop     rbx
0x180010886  jmp     ??1?$CComPtrBase@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhConfigMgrPriv>::~CComPtrBase<IFhConfigMgrPriv>(void)
```
