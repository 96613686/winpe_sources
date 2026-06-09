# RpcDSSRemoveSharingToken

- ea: `0x180007870`
- end: `0x180007937`
- name: `RpcDSSRemoveSharingToken`
- size: `199`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800038f8`
- `0x180006070`
- `0x180006cb0`
- `0x180006f78`
- `0x180007870`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000d7b8`

## string_xrefs

- `0x180007896`: `DSSRemoveSharingToken started.`
- `0x1800078b4`: `DSSRemoveSharingToken finished.`
- `0x1800078e4`: `RpcDSSRemoveSharingToken`

## pseudocode

```c
__int64 __fastcall RpcDSSRemoveSharingToken(__int64 a1, const unsigned __int16 *a2, __int64 a3, __int64 a4)
{
  DSLogger *v6; // rax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  DSLogger *v12; // rax
  DSLogger *v13; // rax
  __int64 *v14; // rax
  int v16; // [rsp+20h] [rbp-38h]
  _BYTE v17[40]; // [rsp+30h] [rbp-28h] BYREF
  int v18; // [rsp+68h] [rbp+10h] BYREF
  __int64 v19; // [rsp+70h] [rbp+18h] BYREF

  if ( !a2 || !*a2 )
  {
    v7 = -2147024809;
LABEL_6:
    v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        a1,
                        a2,
                        a3,
                        a4);
    v16 = v7;
    DSLogger::LogError(v13, L"RpcDSSRemoveSharingToken", 0x118u, L"hr=0x%x.", v16);
    goto LABEL_7;
  }
  v6 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                     a1,
                     a2,
                     a3,
                     a4);
  DSLogger::LogServiceApiStarted(v6, L"DSSRemoveSharingToken started.");
  v7 = DSSRemoveSharingToken(a2);
  v12 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                      v9,
                      v8,
                      v10,
                      v11);
  DSLogger::LogServiceApiCompleted(v12, L"DSSRemoveSharingToken finished.");
  if ( v7 < 0 )
    goto LABEL_6;
LABEL_7:
  v14 = (__int64 *)RpcClientProcessInfo(v17, a1);
  v18 = v7;
  v19 = *v14;
  DataSharingServiceTelemetry::DSSRemove<unsigned long,unsigned short const *>(&v18, &v19);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007870  mov     [rsp+arg_0], rbx
0x180007875  mov     [rsp+arg_18], rsi
0x18000787a  push    rdi
0x18000787b  sub     rsp, 50h
0x18000787f  xor     esi, esi
0x180007881  mov     rbx, rdx
0x180007884  mov     rdi, rcx
0x180007887  test    rdx, rdx
0x18000788a  jz      short loc_1800078C9
0x18000788c  cmp     [rdx], si
0x18000788f  jz      short loc_1800078C9
0x180007891  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007896  lea     rdx, aDssremoveshari_1; "DSSRemoveSharingToken started."
0x18000789d  mov     rcx, rax; this
0x1800078a0  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x1800078a5  mov     rcx, rbx; unsigned __int16 *
0x1800078a8  call    ?DSSRemoveSharingToken@@YAJPEBG@Z; DSSRemoveSharingToken(ushort const *)
0x1800078ad  mov     ebx, eax
0x1800078af  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800078b4  lea     rdx, aDssremoveshari; "DSSRemoveSharingToken finished."
0x1800078bb  mov     rcx, rax; this
0x1800078be  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x1800078c3  test    ebx, ebx
0x1800078c5  jns     short loc_1800078F3
0x1800078c7  jmp     short loc_1800078CE
0x1800078c9  mov     ebx, 80070057h
0x1800078ce  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800078d3  lea     r9, aHr0xX; "hr=0x%x."
0x1800078da  mov     [rsp+58h+var_38], ebx
0x1800078de  mov     r8d, 118h; unsigned int
0x1800078e4  lea     rdx, aRpcdssremovesh; "RpcDSSRemoveSharingToken"
0x1800078eb  mov     rcx, rax; this
0x1800078ee  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800078f3  mov     rdx, rdi
0x1800078f6  lea     rcx, [rsp+58h+var_28]
0x1800078fb  call    ?RpcClientProcessInfo@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAX@Z; RpcClientProcessInfo(void *)
0x180007900  lea     rdx, [rsp+58h+arg_10]
0x180007905  mov     [rsp+58h+arg_8], ebx
0x180007909  mov     rcx, [rax]
0x18000790c  mov     [rsp+58h+arg_10], rcx
0x180007911  lea     rcx, [rsp+58h+arg_8]
0x180007916  call    ??$DSSRemove@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z; DataSharingServiceTelemetry::DSSRemove<ulong,ushort const *>(ulong &&,ushort const * &&)
0x18000791b  lea     rcx, [rsp+58h+var_28]
0x180007920  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180007925  mov     rsi, [rsp+58h+arg_18]
0x18000792a  mov     eax, ebx
0x18000792c  mov     rbx, [rsp+58h+arg_0]
0x180007931  add     rsp, 50h
0x180007935  pop     rdi
0x180007936  retn
```
