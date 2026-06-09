# RpcDSSCopyFromSharedFile

- ea: `0x180007220`
- end: `0x1800072f8`
- name: `RpcDSSCopyFromSharedFile`
- size: `216`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, wchar_t *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000363c`
- `0x180006070`
- `0x180006cb0`
- `0x180006f78`
- `0x180007220`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000ca4c`

## string_xrefs

- `0x180007251`: `DSSCopyFromSharedFile started.`
- `0x180007272`: `DSSCopyFromSharedFile finished.`
- `0x1800072a2`: `RpcDSSCopyFromSharedFile`

## pseudocode

```c
__int64 __fastcall RpcDSSCopyFromSharedFile(__int64 a1, const unsigned __int16 *a2, wchar_t *a3, __int64 a4)
{
  DSLogger *v7; // rax
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  DSLogger *v13; // rax
  DSLogger *v14; // rax
  __int64 *v15; // rax
  int v17; // [rsp+20h] [rbp-48h]
  _BYTE v18[56]; // [rsp+30h] [rbp-38h] BYREF
  int v19; // [rsp+78h] [rbp+10h] BYREF
  __int64 v20; // [rsp+88h] [rbp+20h] BYREF

  if ( !a2 || !*a2 || !a3 || !*a3 )
  {
    v8 = -2147024809;
LABEL_8:
    v14 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        a1,
                        a2,
                        a3,
                        a4);
    v17 = v8;
    DSLogger::LogError(v14, L"RpcDSSCopyFromSharedFile", 0x154u, L"hr=0x%x.", v17);
    goto LABEL_9;
  }
  v7 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                     a1,
                     a2,
                     a3,
                     a4);
  DSLogger::LogServiceApiStarted(v7, L"DSSCopyFromSharedFile started.");
  v8 = DSSCopyFromSharedFile(a2, a3);
  v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                      v10,
                      v9,
                      v11,
                      v12);
  DSLogger::LogServiceApiCompleted(v13, L"DSSCopyFromSharedFile finished.");
  if ( v8 < 0 )
    goto LABEL_8;
LABEL_9:
  v15 = (__int64 *)RpcClientProcessInfo(v18, a1);
  v19 = v8;
  v20 = *v15;
  DataSharingServiceTelemetry::DSSCopy<unsigned long,unsigned short const *>(&v19, &v20);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007220  mov     [rsp+arg_0], rbx
0x180007225  push    rbp
0x180007226  push    rsi
0x180007227  push    rdi
0x180007228  sub     rsp, 50h
0x18000722c  xor     ebp, ebp
0x18000722e  mov     rbx, r8
0x180007231  mov     rdi, rdx
0x180007234  mov     rsi, rcx
0x180007237  test    rdx, rdx
0x18000723a  jz      short loc_180007287
0x18000723c  cmp     [rdx], bp
0x18000723f  jz      short loc_180007287
0x180007241  test    rbx, rbx
0x180007244  jz      short loc_180007287
0x180007246  cmp     [r8], bp
0x18000724a  jz      short loc_180007287
0x18000724c  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007251  lea     rdx, aDsscopyfromsha; "DSSCopyFromSharedFile started."
0x180007258  mov     rcx, rax; this
0x18000725b  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x180007260  mov     rdx, rbx; Str
0x180007263  mov     rcx, rdi; unsigned __int16 *
0x180007266  call    ?DSSCopyFromSharedFile@@YAJPEBG0@Z; DSSCopyFromSharedFile(ushort const *,ushort const *)
0x18000726b  mov     ebx, eax
0x18000726d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007272  lea     rdx, aDsscopyfromsha_1; "DSSCopyFromSharedFile finished."
0x180007279  mov     rcx, rax; this
0x18000727c  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x180007281  test    ebx, ebx
0x180007283  jns     short loc_1800072B1
0x180007285  jmp     short loc_18000728C
0x180007287  mov     ebx, 80070057h
0x18000728c  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007291  lea     r9, aHr0xX; "hr=0x%x."
0x180007298  mov     [rsp+68h+var_48], ebx
0x18000729c  mov     r8d, 154h; unsigned int
0x1800072a2  lea     rdx, aRpcdsscopyfrom; "RpcDSSCopyFromSharedFile"
0x1800072a9  mov     rcx, rax; this
0x1800072ac  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800072b1  mov     rdx, rsi
0x1800072b4  lea     rcx, [rsp+68h+var_38]
0x1800072b9  call    ?RpcClientProcessInfo@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAX@Z; RpcClientProcessInfo(void *)
0x1800072be  lea     rdx, [rsp+68h+arg_18]
0x1800072c6  mov     [rsp+68h+arg_8], ebx
0x1800072ca  mov     rcx, [rax]
0x1800072cd  mov     [rsp+68h+arg_18], rcx
0x1800072d5  lea     rcx, [rsp+68h+arg_8]
0x1800072da  call    ??$DSSCopy@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z; DataSharingServiceTelemetry::DSSCopy<ulong,ushort const *>(ulong &&,ushort const * &&)
0x1800072df  lea     rcx, [rsp+68h+var_38]
0x1800072e4  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800072e9  mov     eax, ebx
0x1800072eb  mov     rbx, [rsp+68h+arg_0]
0x1800072f0  add     rsp, 50h
0x1800072f4  pop     rdi
0x1800072f5  pop     rsi
0x1800072f6  pop     rbp
0x1800072f7  retn
```
