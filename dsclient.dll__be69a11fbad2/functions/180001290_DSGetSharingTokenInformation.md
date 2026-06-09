# DSGetSharingTokenInformation

- ea: `0x180001290`
- end: `0x1800013f2`
- name: `DSGetSharingTokenInformation`
- size: `354`
- prototype: `__int64 __fastcall(_WORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001200`
- `0x180001290`
- `0x180001e10`
- `0x180001e50`
- `0x180001ed0`
- `0x180002200`
- `0x180002350`
- `0x18000313c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800013ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800013ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000136c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000136c`

## string_xrefs

- `0x1800013ce`: `DSGetSharingTokenInformation`
- `0x1800012d3`: `DSGetSharingTokenInformation started.`
- `0x18000132b`: `DSGetSharingTokenInformation finished.`

## pseudocode

```c
__int64 __fastcall DSGetSharingTokenInformation(_WORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  DSLogger *v4; // rax
  int v5; // ebx
  DSLogger *v6; // rax
  DSLogger *v7; // rdi
  BOOL fPending; // [rsp+30h] [rbp-58h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-50h] BYREF
  __int64 v11; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v12[5]; // [rsp+48h] [rbp-40h] BYREF
  _WORD *v13; // [rsp+90h] [rbp+8h] BYREF
  __int64 v14; // [rsp+98h] [rbp+10h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+20h] BYREF

  v16 = a4;
  v15 = a3;
  v14 = a2;
  v13 = a1;
  if ( a1 && *a1 && a2 && a3 && a4 )
  {
    v4 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    DSLogger::LogClientApiStarted(v4, L"DSGetSharingTokenInformation started.");
    v12[0] = &v13;
    v12[1] = &v14;
    v12[2] = &v15;
    v12[3] = &v16;
    v5 = MakeServiceCall__lambda_3079517f2af4cbfbefea45414700e547_(v12);
    if ( v5 >= 0 )
    {
      v6 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
      DSLogger::LogClientApiCompleted(v6, L"DSGetSharingTokenInformation finished.");
      return (unsigned int)v5;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&DSLoggerSingleton, 0, &fPending, &Context);
  v7 = (DSLogger *)Context;
  if ( !Context )
  {
    dword_18000FA50 = McGenEventRegister_EventRegister() == 0;
    v7 = (DSLogger *)&dword_18000FA50;
    v11 = 0;
    InitOnceComplete(&DSLoggerSingleton, 0, &dword_18000FA50);
    tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(&v11);
  }
  DSLogger::LogError(v7, L"DSGetSharingTokenInformation", 0x190u, L"hr=0x%x.", v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001290  mov     [rsp+arg_18], r9
0x180001295  mov     [rsp+arg_10], r8
0x18000129a  mov     [rsp+arg_8], rdx
0x18000129f  mov     [rsp+arg_0], rcx
0x1800012a4  push    rbx
0x1800012a5  sub     rsp, 80h
0x1800012ac  test    rcx, rcx
0x1800012af  jz      loc_18000133F
0x1800012b5  cmp     word ptr [rcx], 0
0x1800012b9  jz      loc_18000133F
0x1800012bf  test    rdx, rdx
0x1800012c2  jz      short loc_18000133F
0x1800012c4  test    r8, r8
0x1800012c7  jz      short loc_18000133F
0x1800012c9  test    r9, r9
0x1800012cc  jz      short loc_18000133F
0x1800012ce  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800012d3  lea     rdx, aDsgetsharingto_2; "DSGetSharingTokenInformation started."
0x1800012da  mov     rcx, rax; this
0x1800012dd  call    ?LogClientApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiStarted(ushort const *)
0x1800012e2  lea     rax, [rsp+88h+arg_0]
0x1800012ea  mov     [rsp+88h+var_40], rax
0x1800012ef  lea     rcx, [rsp+88h+var_40]
0x1800012f4  lea     rax, [rsp+88h+arg_8]
0x1800012fc  mov     [rsp+88h+var_38], rax
0x180001301  lea     rax, [rsp+88h+arg_10]
0x180001309  mov     [rsp+88h+var_30], rax
0x18000130e  lea     rax, [rsp+88h+arg_18]
0x180001316  mov     [rsp+88h+var_28], rax
0x18000131b  call    MakeServiceCall__lambda_3079517f2af4cbfbefea45414700e547___; MakeServiceCall__lambda_3079517f2af4cbfbefea45414700e547_
0x180001320  mov     ebx, eax
0x180001322  test    eax, eax
0x180001324  js      short loc_180001344
0x180001326  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000132b  lea     rdx, aDsgetsharingto_1; "DSGetSharingTokenInformation finished."
0x180001332  mov     rcx, rax; this
0x180001335  call    ?LogClientApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiCompleted(ushort const *)
0x18000133a  jmp     loc_1800013E7
0x18000133f  mov     ebx, 80070057h
0x180001344  mov     [rsp+88h+var_10], rsi
0x180001349  lea     r9, [rsp+88h+Context]; lpContext
0x18000134e  xor     esi, esi
0x180001350  mov     [rsp+88h+var_18], rdi
0x180001355  lea     r8, [rsp+88h+fPending]; fPending
0x18000135a  mov     [rsp+88h+fPending], esi
0x18000135e  xor     edx, edx; dwFlags
0x180001360  mov     [rsp+88h+Context], rsi
0x180001365  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x18000136c  call    cs:__imp_InitOnceBeginInitialize
0x180001372  mov     rdi, [rsp+88h+Context]
0x180001377  test    rdi, rdi
0x18000137a  jnz     short loc_1800013BD
0x18000137c  mov     cs:dword_18000FA50, esi
0x180001382  call    McGenEventRegister_EventRegister
0x180001387  test    eax, eax
0x180001389  jnz     short loc_180001395
0x18000138b  mov     cs:dword_18000FA50, 1
0x180001395  lea     rdi, dword_18000FA50
0x18000139c  mov     [rsp+88h+var_48], rsi
0x1800013a1  mov     r8, rdi; lpContext
0x1800013a4  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1800013ab  xor     edx, edx; dwFlags
0x1800013ad  call    cs:__imp_InitOnceComplete
0x1800013b3  lea     rcx, [rsp+88h+var_48]
0x1800013b8  call    ??1_Initializer@?$_LazyImpl@VAutoRpcBinding@@V?$lazy_construct@VAutoRpcBinding@@@tlx@@V?$static_lazy@VAutoRpcBinding@@$0A@V?$lazy_construct@VAutoRpcBinding@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<AutoRpcBinding,tlx::lazy_construct<AutoRpcBinding>,tlx::static_lazy<AutoRpcBinding,0,tlx::lazy_construct<AutoRpcBinding>>>::_Initializer::~_Initializer(void)
0x1800013bd  lea     r9, aHr0xX; "hr=0x%x."
0x1800013c4  mov     [rsp+88h+var_68], ebx
0x1800013c8  mov     r8d, 190h; unsigned int
0x1800013ce  lea     rdx, aDsgetsharingto_0; "DSGetSharingTokenInformation"
0x1800013d5  mov     rcx, rdi; this
0x1800013d8  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800013dd  mov     rdi, [rsp+88h+var_18]
0x1800013e2  mov     rsi, [rsp+88h+var_10]
0x1800013e7  mov     eax, ebx
0x1800013e9  add     rsp, 80h
0x1800013f0  pop     rbx
0x1800013f1  retn
```
