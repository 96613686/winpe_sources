# DSRemoveSharingToken

- ea: `0x180003460`
- end: `0x180003511`
- name: `DSRemoveSharingToken`
- size: `177`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001200`
- `0x180001ae0`
- `0x180001e50`
- `0x180001ed0`
- `0x180002350`
- `0x1800031a8`
- `0x180003460`
- `0x180003c20`

## string_xrefs

- `0x18000347d`: `DSRemoveSharingToken started.`
- `0x1800034cb`: `DSRemoveSharingToken finished.`
- `0x1800034f7`: `DSRemoveSharingToken`

## pseudocode

```c
__int64 __fastcall DSRemoveSharingToken(unsigned __int16 *a1)
{
  int *v2; // rax
  int v3; // ebx
  int i; // esi
  int v5; // edx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int *v9; // rax
  int *v10; // rax
  int v12; // [rsp+20h] [rbp-38h]

  if ( !a1 || !*a1 )
  {
    v3 = -2147024809;
LABEL_11:
    v10 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
    v12 = v3;
    DSLogger::LogError((DSLogger *)v10, L"DSRemoveSharingToken", 452, L"hr=0x%x.", v12);
    return (unsigned int)v3;
  }
  v2 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
  DSLogger::LogClientApiStarted((DSLogger *)v2, L"DSRemoveSharingToken started.");
  v3 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( CheckForRpcRetry(v3) )
    {
      v3 = EnsureDSSvcRunning(v6, v5, v7, v8);
      if ( v3 < 0 )
        break;
    }
    v3 = DSCRemoveSharingToken(a1);
    if ( !CheckForRpcRetry(v3) )
      break;
  }
  if ( v3 < 0 )
    goto LABEL_11;
  v9 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
  DSLogger::LogClientApiCompleted((DSLogger *)v9, L"DSRemoveSharingToken finished.");
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003460  push    rbx
0x180003462  push    rbp
0x180003463  push    rsi
0x180003464  push    rdi
0x180003465  sub     rsp, 38h
0x180003469  xor     ebp, ebp
0x18000346b  mov     rdi, rcx
0x18000346e  test    rcx, rcx
0x180003471  jz      short loc_1800034DC
0x180003473  cmp     [rcx], bp
0x180003476  jz      short loc_1800034DC
0x180003478  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000347d  lea     rdx, aDsremovesharin_0; "DSRemoveSharingToken started."
0x180003484  mov     rcx, rax; this
0x180003487  call    ?LogClientApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiStarted(ushort const *)
0x18000348c  mov     ebx, ebp
0x18000348e  mov     esi, ebp
0x180003490  mov     ecx, ebx; int
0x180003492  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180003497  test    eax, eax
0x180003499  jz      short loc_1800034A6
0x18000349b  call    ?EnsureDSSvcRunning@@YAJXZ; EnsureDSSvcRunning(void)
0x1800034a0  mov     ebx, eax
0x1800034a2  test    eax, eax
0x1800034a4  js      short loc_1800034C2
0x1800034a6  mov     rcx, rdi; unsigned __int16 *
0x1800034a9  call    ?DSCRemoveSharingToken@@YAJPEBG@Z; DSCRemoveSharingToken(ushort const *)
0x1800034ae  mov     ecx, eax; int
0x1800034b0  mov     ebx, eax
0x1800034b2  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x1800034b7  test    eax, eax
0x1800034b9  jz      short loc_1800034C2
0x1800034bb  inc     esi
0x1800034bd  cmp     esi, 2
0x1800034c0  jl      short loc_180003490
0x1800034c2  test    ebx, ebx
0x1800034c4  js      short loc_1800034E1
0x1800034c6  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800034cb  lea     rdx, aDsremovesharin_2; "DSRemoveSharingToken finished."
0x1800034d2  mov     rcx, rax; this
0x1800034d5  call    ?LogClientApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiCompleted(ushort const *)
0x1800034da  jmp     short loc_180003506
0x1800034dc  mov     ebx, 80070057h
0x1800034e1  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800034e6  lea     r9, aHr0xX; "hr=0x%x."
0x1800034ed  mov     [rsp+58h+var_38], ebx
0x1800034f1  mov     r8d, 1C4h; unsigned int
0x1800034f7  lea     rdx, aDsremovesharin_1; "DSRemoveSharingToken"
0x1800034fe  mov     rcx, rax; this
0x180003501  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180003506  mov     eax, ebx
0x180003508  add     rsp, 38h
0x18000350c  pop     rdi
0x18000350d  pop     rsi
0x18000350e  pop     rbp
0x18000350f  pop     rbx
0x180003510  retn
```
