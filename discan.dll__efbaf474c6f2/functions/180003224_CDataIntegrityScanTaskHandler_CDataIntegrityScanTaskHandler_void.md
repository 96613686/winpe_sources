# CDataIntegrityScanTaskHandler::~CDataIntegrityScanTaskHandler(void)

- ea: `0x180003224`
- end: `0x1800032ef`
- name: `??1CDataIntegrityScanTaskHandler@@QEAA@XZ`
- size: `203`
- prototype: `void __fastcall(CDataIntegrityScanTaskHandler *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000306c`
- `0x1800030b8`

## callees

- `0x180001bc4`
- `0x180003158`
- `0x180003180`
- `0x1800031a0`
- `0x180003204`
- `0x180003224`
- `0x180013948`

## pseudocode

```c
void __fastcall CDataIntegrityScanTaskHandler::~CDataIntegrityScanTaskHandler(CDataIntegrityScanTaskHandler *this)
{
  void *v1; // rdi

  v1 = (void *)*((_QWORD *)this + 50);
  if ( v1 )
  {
    CSystemScanner::~CSystemScanner(*((CSystemScanner **)this + 50));
    operator delete(v1);
  }
  *((_QWORD *)this + 50) = 0;
  CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>((struct _TP_WORK **)this + 33);
  CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>((struct _TP_WORK **)this + 31);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 224);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 200);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 184);
  CHandleT<_TP_WAIT *,ThreadPoolWaitTrait>::~CHandleT<_TP_WAIT *,ThreadPoolWaitTrait>((struct _TP_WAIT **)this + 21);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 152);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 136);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 120);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 104);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 88);
  CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>((char *)this + 72);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CDataIntegrityScanTaskHandler *)((char *)this + 24));
}

```

## disassembly

```asm
0x180003224  mov     [rsp+arg_0], rbx
0x180003229  push    rdi
0x18000322a  sub     rsp, 20h
0x18000322e  mov     rdi, [rcx+190h]
0x180003235  mov     rbx, rcx
0x180003238  test    rdi, rdi
0x18000323b  jz      short loc_18000324D
0x18000323d  mov     rcx, rdi; this
0x180003240  call    ??1CSystemScanner@@QEAA@XZ; CSystemScanner::~CSystemScanner(void)
0x180003245  mov     rcx, rdi; Block
0x180003248  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000324d  lea     rcx, [rbx+108h]; void *
0x180003254  mov     qword ptr [rbx+190h], 0
0x18000325f  call    ??1?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAA@XZ; CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(void)
0x180003264  lea     rcx, [rbx+0F8h]; void *
0x18000326b  call    ??1?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAA@XZ; CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(void)
0x180003270  lea     rcx, [rbx+0E0h]
0x180003277  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x18000327c  lea     rcx, [rbx+0C8h]
0x180003283  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x180003288  lea     rcx, [rbx+0B8h]
0x18000328f  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x180003294  lea     rcx, [rbx+0A8h]
0x18000329b  call    ??1?$CHandleT@PEAU_TP_WAIT@@UThreadPoolWaitTrait@@@@QEAA@XZ; CHandleT<_TP_WAIT *,ThreadPoolWaitTrait>::~CHandleT<_TP_WAIT *,ThreadPoolWaitTrait>(void)
0x1800032a0  lea     rcx, [rbx+98h]
0x1800032a7  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x1800032ac  lea     rcx, [rbx+88h]
0x1800032b3  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x1800032b8  lea     rcx, [rbx+78h]
0x1800032bc  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x1800032c1  lea     rcx, [rbx+68h]
0x1800032c5  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x1800032ca  lea     rcx, [rbx+58h]
0x1800032ce  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x1800032d3  lea     rcx, [rbx+48h]
0x1800032d7  call    ??1?$CHandleT@PEAXUObjectHandleTrait@@@@QEAA@XZ; CHandleT<void *,ObjectHandleTrait>::~CHandleT<void *,ObjectHandleTrait>(void)
0x1800032dc  lea     rcx, [rbx+18h]; this
0x1800032e0  mov     rbx, [rsp+28h+arg_0]
0x1800032e5  add     rsp, 20h
0x1800032e9  pop     rdi
0x1800032ea  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
