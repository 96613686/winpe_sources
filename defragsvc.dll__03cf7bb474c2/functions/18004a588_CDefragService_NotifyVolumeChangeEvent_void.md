# CDefragService::_NotifyVolumeChangeEvent(void)

- ea: `0x18004a588`
- end: `0x18004a66c`
- name: `?_NotifyVolumeChangeEvent@CDefragService@@AEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(CDefragService *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004a570`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18003655c`
- `0x18004a588`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a5e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a5e9`

## string_xrefs

- `0x18004a59e`: `CDefragService::_NotifyVolumeChangeEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDefragService::_NotifyVolumeChangeEvent(CDefragService *this)
{
  unsigned int v1; // ebx
  _DWORD v3[18]; // [rsp+30h] [rbp-48h] BYREF
  CDefragService *v4; // [rsp+80h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+10h] BYREF

  v4 = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v3, "CDefragService::_NotifyVolumeChangeEvent", 1110, 1);
  ppv = 0;
  v4 = 0;
  if ( CoCreateInstance(&CLSID_CDefragEngine, 0, 4u, &IID_IDefragEngine, &ppv) >= 0
    && ppv
    && (**(int (__fastcall ***)(LPVOID, GUID *, CDefragService **))ppv)(ppv, &IID_IDefragEnginePriv, &v4) >= 0
    && v4 )
  {
    (*(void (__fastcall **)(CDefragService *))(*(_QWORD *)v4 + 200LL))(v4);
  }
  v1 = v3[0];
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v4);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v3);
  return v1;
}

```

## disassembly

```asm
0x18004a588  mov     [rsp+arg_0], rcx
0x18004a58d  push    rbx
0x18004a58e  sub     rsp, 70h
0x18004a592  mov     r9d, 1; unsigned __int16
0x18004a598  mov     r8d, 456h; unsigned __int16
0x18004a59e  lea     rdx, aCdefragservice_7; "CDefragService::_NotifyVolumeChangeEven"...
0x18004a5a5  lea     rcx, [rsp+78h+var_48]; this
0x18004a5aa  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004a5af  nop
0x18004a5b0  mov     [rsp+78h+arg_8], 0
0x18004a5bc  mov     [rsp+78h+arg_0], 0
0x18004a5c8  lea     rax, [rsp+78h+arg_8]
0x18004a5d0  mov     [rsp+78h+ppv], rax; ppv
0x18004a5d5  lea     r9, IID_IDefragEngine; riid
0x18004a5dc  xor     edx, edx; pUnkOuter
0x18004a5de  lea     r8d, [rdx+4]; dwClsContext
0x18004a5e2  lea     rcx, CLSID_CDefragEngine; rclsid
0x18004a5e9  call    cs:__imp_CoCreateInstance
0x18004a5ef  test    eax, eax
0x18004a5f1  js      short loc_18004A63A
0x18004a5f3  mov     rcx, [rsp+78h+arg_8]
0x18004a5fb  test    rcx, rcx
0x18004a5fe  jz      short loc_18004A63A
0x18004a600  mov     rax, [rcx]
0x18004a603  lea     r8, [rsp+78h+arg_0]
0x18004a60b  lea     rdx, IID_IDefragEnginePriv
0x18004a612  mov     rax, [rax]
0x18004a615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a61a  test    eax, eax
0x18004a61c  js      short loc_18004A63A
0x18004a61e  mov     rcx, [rsp+78h+arg_0]
0x18004a626  test    rcx, rcx
0x18004a629  jz      short loc_18004A63A
0x18004a62b  mov     rax, [rcx]
0x18004a62e  mov     rax, [rax+0C8h]
0x18004a635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a63a  mov     ebx, [rsp+78h+var_48]
0x18004a63e  lea     rcx, [rsp+78h+arg_0]
0x18004a646  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a64b  nop
0x18004a64c  lea     rcx, [rsp+78h+arg_8]
0x18004a654  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004a659  nop
0x18004a65a  lea     rcx, [rsp+78h+var_48]; this
0x18004a65f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004a664  mov     eax, ebx
0x18004a666  add     rsp, 70h
0x18004a66a  pop     rbx
0x18004a66b  retn
```
