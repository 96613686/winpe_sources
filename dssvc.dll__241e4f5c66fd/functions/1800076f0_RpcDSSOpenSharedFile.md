# RpcDSSOpenSharedFile

- ea: `0x1800076f0`
- end: `0x1800077ef`
- name: `RpcDSSOpenSharedFile`
- size: `255`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000386c`
- `0x180006070`
- `0x180006cb0`
- `0x180006f78`
- `0x1800076f0`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000d3e4`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007726`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180007726`

## string_xrefs

- `0x180007744`: `DSSOpenSharedFile started.`
- `0x18000776f`: `DSSOpenSharedFile finished.`
- `0x18000779f`: `RpcDSSOpenSharedFile`

## pseudocode

```c
__int64 __fastcall RpcDSSOpenSharedFile(void *a1, const unsigned __int16 *a2, unsigned int a3, unsigned __int64 *a4)
{
  RPC_STATUS v8; // eax
  signed int v9; // ebx
  DSLogger *v10; // rax
  DSLogger *v11; // rax
  DSLogger *v12; // rax
  signed int v14; // [rsp+20h] [rbp-78h]
  signed int v15; // [rsp+30h] [rbp-68h] BYREF
  __int64 v16; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v17[88]; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v18; // [rsp+A8h] [rbp+10h] BYREF

  v18 = 0;
  if ( !a2 || !*a2 || !a4 )
  {
    v9 = -2147024809;
    goto LABEL_10;
  }
  v8 = I_RpcBindingInqLocalClientPID(a1, &v18);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_10;
  }
  v10 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogServiceApiStarted(v10, L"DSSOpenSharedFile started.");
  v9 = DSSOpenSharedFile(a2, v18, a3, a4);
  v11 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  DSLogger::LogServiceApiCompleted(v11, L"DSSOpenSharedFile finished.");
  if ( v9 < 0 )
  {
LABEL_10:
    v12 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v14 = v9;
    DSLogger::LogError(v12, L"RpcDSSOpenSharedFile", 0x13Cu, L"hr=0x%x.", v14);
  }
  v15 = v9;
  v16 = *(_QWORD *)RpcClientProcessInfo(v17, a1);
  DataSharingServiceTelemetry::DSSOpen<unsigned long,unsigned short const *>(&v15, &v16);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800076f0  mov     rax, rsp
0x1800076f3  push    rbx
0x1800076f4  push    rbp
0x1800076f5  push    rsi
0x1800076f6  push    rdi
0x1800076f7  push    r14
0x1800076f9  push    r15
0x1800076fb  sub     rsp, 68h
0x1800076ff  xor     r15d, r15d
0x180007702  mov     rsi, r9
0x180007705  mov     [rax+10h], r15d
0x180007709  mov     r14d, r8d
0x18000770c  mov     rdi, rdx
0x18000770f  mov     rbp, rcx
0x180007712  test    rdx, rdx
0x180007715  jz      short loc_180007784
0x180007717  cmp     [rdx], r15w
0x18000771b  jz      short loc_180007784
0x18000771d  test    r9, r9
0x180007720  jz      short loc_180007784
0x180007722  lea     rdx, [rax+10h]; Pid
0x180007726  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000772c  mov     ebx, eax
0x18000772e  test    eax, eax
0x180007730  jz      short loc_18000773F
0x180007732  jle     short loc_180007789
0x180007734  movzx   ebx, ax
0x180007737  or      ebx, 80070000h
0x18000773d  jmp     short loc_180007789
0x18000773f  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007744  lea     rdx, aDssopensharedf_1; "DSSOpenSharedFile started."
0x18000774b  mov     rcx, rax; this
0x18000774e  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x180007753  mov     edx, [rsp+98h+arg_8]; unsigned int
0x18000775a  mov     r9, rsi; unsigned __int64 *
0x18000775d  mov     r8d, r14d; unsigned int
0x180007760  mov     rcx, rdi; unsigned __int16 *
0x180007763  call    ?DSSOpenSharedFile@@YAJPEBGKKPEA_K@Z; DSSOpenSharedFile(ushort const *,ulong,ulong,unsigned __int64 *)
0x180007768  mov     ebx, eax
0x18000776a  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000776f  lea     rdx, aDssopensharedf_0; "DSSOpenSharedFile finished."
0x180007776  mov     rcx, rax; this
0x180007779  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x18000777e  test    ebx, ebx
0x180007780  jns     short loc_1800077AE
0x180007782  jmp     short loc_180007789
0x180007784  mov     ebx, 80070057h
0x180007789  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000778e  lea     r9, aHr0xX; "hr=0x%x."
0x180007795  mov     [rsp+98h+var_78], ebx
0x180007799  mov     r8d, 13Ch; unsigned int
0x18000779f  lea     rdx, aRpcdssopenshar; "RpcDSSOpenSharedFile"
0x1800077a6  mov     rcx, rax; this
0x1800077a9  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800077ae  mov     rdx, rbp
0x1800077b1  lea     rcx, [rsp+98h+var_58]
0x1800077b6  call    ?RpcClientProcessInfo@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAX@Z; RpcClientProcessInfo(void *)
0x1800077bb  lea     rdx, [rsp+98h+var_60]
0x1800077c0  mov     [rsp+98h+var_68], ebx
0x1800077c4  mov     rcx, [rax]
0x1800077c7  mov     [rsp+98h+var_60], rcx
0x1800077cc  lea     rcx, [rsp+98h+var_68]
0x1800077d1  call    ??$DSSOpen@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z; DataSharingServiceTelemetry::DSSOpen<ulong,ushort const *>(ulong &&,ushort const * &&)
0x1800077d6  lea     rcx, [rsp+98h+var_58]
0x1800077db  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800077e0  mov     eax, ebx
0x1800077e2  add     rsp, 68h
0x1800077e6  pop     r15
0x1800077e8  pop     r14
0x1800077ea  pop     rdi
0x1800077eb  pop     rsi
0x1800077ec  pop     rbp
0x1800077ed  pop     rbx
0x1800077ee  retn
```
