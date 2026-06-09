# RpcDSSRemoveExpiredTokens

- ea: `0x180007800`
- end: `0x180007866`
- name: `RpcDSSRemoveExpiredTokens`
- size: `102`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006f78`
- `0x180007800`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000d68c`

## string_xrefs

- `0x18000780b`: `DSSRemoveExpiredTokens started.`
- `0x180007826`: `DSSRemoveExpiredTokens finished.`
- `0x18000784f`: `RpcDSSRemoveExpiredTokens`

## pseudocode

```c
__int64 __fastcall RpcDSSRemoveExpiredTokens(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  DSLogger *v4; // rax
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  DSLogger *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  DSLogger *v15; // rax
  int v17; // [rsp+20h] [rbp-18h]

  v4 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                     a1,
                     a2,
                     a3,
                     a4);
  DSLogger::LogServiceApiStarted(v4, L"DSSRemoveExpiredTokens started.");
  v5 = DSSRemoveExpiredTokens();
  v10 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                      v7,
                      v6,
                      v8,
                      v9);
  DSLogger::LogServiceApiCompleted(v10, L"DSSRemoveExpiredTokens finished.");
  if ( v5 < 0 )
  {
    v15 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v12,
                        v11,
                        v13,
                        v14);
    v17 = v5;
    DSLogger::LogError(v15, L"RpcDSSRemoveExpiredTokens", 0x165u, L"hr=0x%x.", v17);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007800  push    rbx
0x180007802  sub     rsp, 30h
0x180007806  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000780b  lea     rdx, aDssremoveexpir_0; "DSSRemoveExpiredTokens started."
0x180007812  mov     rcx, rax; this
0x180007815  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x18000781a  call    ?DSSRemoveExpiredTokens@@YAJXZ; DSSRemoveExpiredTokens(void)
0x18000781f  mov     ebx, eax
0x180007821  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007826  lea     rdx, aDssremoveexpir; "DSSRemoveExpiredTokens finished."
0x18000782d  mov     rcx, rax; this
0x180007830  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x180007835  test    ebx, ebx
0x180007837  jns     short loc_18000785E
0x180007839  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000783e  lea     r9, aHr0xX; "hr=0x%x."
0x180007845  mov     [rsp+38h+var_18], ebx
0x180007849  mov     r8d, 165h; unsigned int
0x18000784f  lea     rdx, aRpcdssremoveex; "RpcDSSRemoveExpiredTokens"
0x180007856  mov     rcx, rax; this
0x180007859  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000785e  mov     eax, ebx
0x180007860  add     rsp, 30h
0x180007864  pop     rbx
0x180007865  retn
```
