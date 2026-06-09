# RpcDSSCreateSharedFileToken

- ea: `0x180007300`
- end: `0x18000742c`
- name: `RpcDSSCreateSharedFileToken`
- size: `300`
- prototype: `__int64 __fastcall(__int64, _WORD *, _DWORD *, unsigned int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036c8`
- `0x180006070`
- `0x180006cb0`
- `0x180006f78`
- `0x180007300`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000f740`

## string_xrefs

- `0x180007372`: `DSSCreateSharedFileToken started.`
- `0x1800073a4`: `DSSCreateSharedFileToken finished.`
- `0x1800073d4`: `RpcDSSCreateSharedFileToken`

## pseudocode

```c
__int64 __fastcall RpcDSSCreateSharedFileToken(
        __int64 a1,
        _WORD *a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // r14
  DSLogger *v11; // rax
  int v12; // ebx
  DSLogger *v13; // rax
  DSLogger *v14; // rax
  __int64 *v15; // rax
  __int64 v17; // [rsp+20h] [rbp-78h]
  __int64 v18; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v19[96]; // [rsp+38h] [rbp-60h] BYREF

  v6 = a6;
  if ( !a6 || !a2 || !*a2 || !a3 || *a3 > 2u || a3[1] > 7u || (unsigned int)(a3[2] - 1) > 0x13 || a4 > 1 || a5 > 1 )
  {
    v12 = -2147024809;
LABEL_13:
    v14 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    LODWORD(v17) = v12;
    DSLogger::LogError(v14, L"RpcDSSCreateSharedFileToken", 0xB5u, L"hr=0x%x.", v17);
    goto LABEL_14;
  }
  v11 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogServiceApiStarted(v11, L"DSSCreateSharedFileToken started.");
  v12 = DSSCreateSharedFileTokenEx(1, a2, a3, a4, a5, v6);
  v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogServiceApiCompleted(v13, L"DSSCreateSharedFileToken finished.");
  if ( v12 < 0 )
    goto LABEL_13;
LABEL_14:
  v15 = (__int64 *)RpcClientProcessInfo(v19, a1);
  LODWORD(a6) = v12;
  v18 = *v15;
  DataSharingServiceTelemetry::DSSCreate<unsigned long,unsigned short const *>(&a6, &v18);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180007300  push    rbx
0x180007302  push    rbp
0x180007303  push    rsi
0x180007304  push    rdi
0x180007305  push    r12
0x180007307  push    r14
0x180007309  push    r15
0x18000730b  sub     rsp, 60h
0x18000730f  mov     r14, [rsp+98h+arg_28]
0x180007317  xor     r12d, r12d
0x18000731a  mov     ebp, r9d
0x18000731d  mov     rbx, r8
0x180007320  mov     rdi, rdx
0x180007323  mov     r15, rcx
0x180007326  test    r14, r14
0x180007329  jz      loc_1800073B9
0x18000732f  test    rdx, rdx
0x180007332  jz      loc_1800073B9
0x180007338  cmp     [rdx], r12w
0x18000733c  jz      short loc_1800073B9
0x18000733e  test    rbx, rbx
0x180007341  jz      short loc_1800073B9
0x180007343  cmp     dword ptr [r8], 2
0x180007347  ja      short loc_1800073B9
0x180007349  cmp     dword ptr [r8+4], 7
0x18000734e  ja      short loc_1800073B9
0x180007350  mov     eax, [r8+8]
0x180007354  dec     eax
0x180007356  cmp     eax, 13h
0x180007359  ja      short loc_1800073B9
0x18000735b  cmp     r9d, 1
0x18000735f  ja      short loc_1800073B9
0x180007361  mov     esi, [rsp+98h+arg_20]
0x180007368  cmp     esi, 1
0x18000736b  ja      short loc_1800073B9
0x18000736d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007372  lea     rdx, aDsscreateshare_0; "DSSCreateSharedFileToken started."
0x180007379  mov     rcx, rax; this
0x18000737c  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x180007381  mov     r9d, ebp
0x180007384  mov     [rsp+98h+var_70], r14
0x180007389  mov     r8, rbx
0x18000738c  mov     dword ptr [rsp+98h+var_78], esi
0x180007390  mov     rdx, rdi
0x180007393  lea     ecx, [r12+1]
0x180007398  call    DSSCreateSharedFileTokenEx
0x18000739d  mov     ebx, eax
0x18000739f  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800073a4  lea     rdx, aDsscreateshare_2; "DSSCreateSharedFileToken finished."
0x1800073ab  mov     rcx, rax; this
0x1800073ae  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x1800073b3  test    ebx, ebx
0x1800073b5  jns     short loc_1800073E3
0x1800073b7  jmp     short loc_1800073BE
0x1800073b9  mov     ebx, 80070057h
0x1800073be  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800073c3  lea     r9, aHr0xX; "hr=0x%x."
0x1800073ca  mov     dword ptr [rsp+98h+var_78], ebx
0x1800073ce  mov     r8d, 0B5h; unsigned int
0x1800073d4  lea     rdx, aRpcdsscreatesh; "RpcDSSCreateSharedFileToken"
0x1800073db  mov     rcx, rax; this
0x1800073de  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800073e3  mov     rdx, r15
0x1800073e6  lea     rcx, [rsp+98h+var_60]
0x1800073eb  call    ?RpcClientProcessInfo@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAX@Z; RpcClientProcessInfo(void *)
0x1800073f0  lea     rdx, [rsp+98h+var_68]
0x1800073f5  mov     dword ptr [rsp+98h+arg_28], ebx
0x1800073fc  mov     rcx, [rax]
0x1800073ff  mov     [rsp+98h+var_68], rcx
0x180007404  lea     rcx, [rsp+98h+arg_28]
0x18000740c  call    ??$DSSCreate@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z; DataSharingServiceTelemetry::DSSCreate<ulong,ushort const *>(ulong &&,ushort const * &&)
0x180007411  lea     rcx, [rsp+98h+var_60]
0x180007416  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000741b  mov     eax, ebx
0x18000741d  add     rsp, 60h
0x180007421  pop     r15
0x180007423  pop     r14
0x180007425  pop     r12
0x180007427  pop     rdi
0x180007428  pop     rsi
0x180007429  pop     rbp
0x18000742a  pop     rbx
0x18000742b  retn
```
