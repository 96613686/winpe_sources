# RpcDSSDelegateSharingToken

- ea: `0x180007440`
- end: `0x18000751c`
- name: `RpcDSSDelegateSharingToken`
- size: `220`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const struct _DS_SHARE_SCOPE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003754`
- `0x180006070`
- `0x180006cb0`
- `0x180006f78`
- `0x180007440`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000ceb4`

## string_xrefs

- `0x180007475`: `DSSDelegateSharingToken started.`
- `0x180007496`: `DSSDelegateSharingToken finished.`
- `0x1800074c6`: `RpcDSSDelegateSharingToken`

## pseudocode

```c
__int64 __fastcall RpcDSSDelegateSharingToken(__int64 a1, const unsigned __int16 *a2, const struct _DS_SHARE_SCOPE *a3)
{
  DSLogger *v6; // rax
  int v7; // ebx
  DSLogger *v8; // rax
  DSLogger *v9; // rax
  __int64 *v10; // rax
  int v12; // [rsp+20h] [rbp-48h]
  _BYTE v13[56]; // [rsp+30h] [rbp-38h] BYREF
  int v14; // [rsp+78h] [rbp+10h] BYREF
  __int64 v15; // [rsp+88h] [rbp+20h] BYREF

  if ( !a2 || !*a2 || !a3 || (unsigned int)(*(_DWORD *)a3 - 1) > 0x13 )
  {
    v7 = -2147024809;
LABEL_8:
    v9 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v12 = v7;
    DSLogger::LogError(v9, L"RpcDSSDelegateSharingToken", 0x102u, L"hr=0x%x.", v12);
    goto LABEL_9;
  }
  v6 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogServiceApiStarted(v6, L"DSSDelegateSharingToken started.");
  v7 = DSSDelegateSharingToken(a2, a3);
  v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogServiceApiCompleted(v8, L"DSSDelegateSharingToken finished.");
  if ( v7 < 0 )
    goto LABEL_8;
LABEL_9:
  v10 = (__int64 *)RpcClientProcessInfo(v13, a1);
  v14 = v7;
  v15 = *v10;
  DataSharingServiceTelemetry::DSSDelegate<unsigned long,unsigned short const *>(&v14, &v15);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007440  mov     [rsp+arg_0], rbx
0x180007445  push    rbp
0x180007446  push    rsi
0x180007447  push    rdi
0x180007448  sub     rsp, 50h
0x18000744c  xor     ebp, ebp
0x18000744e  mov     rbx, r8
0x180007451  mov     rdi, rdx
0x180007454  mov     rsi, rcx
0x180007457  test    rdx, rdx
0x18000745a  jz      short loc_1800074AB
0x18000745c  cmp     [rdx], bp
0x18000745f  jz      short loc_1800074AB
0x180007461  test    rbx, rbx
0x180007464  jz      short loc_1800074AB
0x180007466  mov     eax, [r8]
0x180007469  dec     eax
0x18000746b  cmp     eax, 13h
0x18000746e  ja      short loc_1800074AB
0x180007470  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007475  lea     rdx, aDssdelegatesha_1; "DSSDelegateSharingToken started."
0x18000747c  mov     rcx, rax; this
0x18000747f  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x180007484  mov     rdx, rbx; struct _DS_SHARE_SCOPE *
0x180007487  mov     rcx, rdi; unsigned __int16 *
0x18000748a  call    ?DSSDelegateSharingToken@@YAJPEBGPEBU_DS_SHARE_SCOPE@@@Z; DSSDelegateSharingToken(ushort const *,_DS_SHARE_SCOPE const *)
0x18000748f  mov     ebx, eax
0x180007491  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007496  lea     rdx, aDssdelegatesha; "DSSDelegateSharingToken finished."
0x18000749d  mov     rcx, rax; this
0x1800074a0  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x1800074a5  test    ebx, ebx
0x1800074a7  jns     short loc_1800074D5
0x1800074a9  jmp     short loc_1800074B0
0x1800074ab  mov     ebx, 80070057h
0x1800074b0  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800074b5  lea     r9, aHr0xX; "hr=0x%x."
0x1800074bc  mov     [rsp+68h+var_48], ebx
0x1800074c0  mov     r8d, 102h; unsigned int
0x1800074c6  lea     rdx, aRpcdssdelegate; "RpcDSSDelegateSharingToken"
0x1800074cd  mov     rcx, rax; this
0x1800074d0  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800074d5  mov     rdx, rsi
0x1800074d8  lea     rcx, [rsp+68h+var_38]
0x1800074dd  call    ?RpcClientProcessInfo@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAX@Z; RpcClientProcessInfo(void *)
0x1800074e2  lea     rdx, [rsp+68h+arg_18]
0x1800074ea  mov     [rsp+68h+arg_8], ebx
0x1800074ee  mov     rcx, [rax]
0x1800074f1  mov     [rsp+68h+arg_18], rcx
0x1800074f9  lea     rcx, [rsp+68h+arg_8]
0x1800074fe  call    ??$DSSDelegate@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z; DataSharingServiceTelemetry::DSSDelegate<ulong,ushort const *>(ulong &&,ushort const * &&)
0x180007503  lea     rcx, [rsp+68h+var_38]
0x180007508  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000750d  mov     eax, ebx
0x18000750f  mov     rbx, [rsp+68h+arg_0]
0x180007514  add     rsp, 50h
0x180007518  pop     rdi
0x180007519  pop     rsi
0x18000751a  pop     rbp
0x18000751b  retn
```
