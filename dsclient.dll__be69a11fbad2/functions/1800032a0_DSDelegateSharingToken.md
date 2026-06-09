# DSDelegateSharingToken

- ea: `0x1800032a0`
- end: `0x18000336d`
- name: `DSDelegateSharingToken`
- size: `205`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _DS_SHARE_SCOPE *)`
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
- `0x1800032a0`
- `0x180003a7c`

## string_xrefs

- `0x1800032d2`: `DSDelegateSharingToken started.`
- `0x180003325`: `DSDelegateSharingToken finished.`
- `0x180003351`: `DSDelegateSharingToken`

## pseudocode

```c
__int64 __fastcall DSDelegateSharingToken(unsigned __int16 *a1, struct _DS_SHARE_SCOPE *a2)
{
  int *v4; // rax
  int v5; // ebx
  int i; // ebp
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int *v11; // rax
  int *v12; // rax
  int v14; // [rsp+20h] [rbp-38h]

  if ( !a1 || !*a1 || !a2 || (unsigned int)(*(_DWORD *)a2 - 1) > 0x13 )
  {
    v5 = -2147024809;
LABEL_13:
    v12 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
    v14 = v5;
    DSLogger::LogError((DSLogger *)v12, L"DSDelegateSharingToken", 428, L"hr=0x%x.", v14);
    return (unsigned int)v5;
  }
  v4 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
  DSLogger::LogClientApiStarted((DSLogger *)v4, L"DSDelegateSharingToken started.");
  v5 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( CheckForRpcRetry(v5) )
    {
      v5 = EnsureDSSvcRunning(v8, v7, v9, v10);
      if ( v5 < 0 )
        break;
    }
    v5 = DSCDelegateSharingToken(a1, a2);
    if ( !CheckForRpcRetry(v5) )
      break;
  }
  if ( v5 < 0 )
    goto LABEL_13;
  v11 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
  DSLogger::LogClientApiCompleted((DSLogger *)v11, L"DSDelegateSharingToken finished.");
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800032a0  push    rbx
0x1800032a2  push    rbp
0x1800032a3  push    rsi
0x1800032a4  push    rdi
0x1800032a5  push    r14
0x1800032a7  sub     rsp, 30h
0x1800032ab  xor     r14d, r14d
0x1800032ae  mov     rdi, rdx
0x1800032b1  mov     rsi, rcx
0x1800032b4  test    rcx, rcx
0x1800032b7  jz      short loc_180003336
0x1800032b9  cmp     [rcx], r14w
0x1800032bd  jz      short loc_180003336
0x1800032bf  test    rdx, rdx
0x1800032c2  jz      short loc_180003336
0x1800032c4  mov     eax, [rdx]
0x1800032c6  dec     eax
0x1800032c8  cmp     eax, 13h
0x1800032cb  ja      short loc_180003336
0x1800032cd  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800032d2  lea     rdx, aDsdelegateshar_2; "DSDelegateSharingToken started."
0x1800032d9  mov     rcx, rax; this
0x1800032dc  call    ?LogClientApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiStarted(ushort const *)
0x1800032e1  mov     ebx, r14d
0x1800032e4  mov     ebp, r14d
0x1800032e7  mov     ecx, ebx; int
0x1800032e9  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x1800032ee  test    eax, eax
0x1800032f0  jz      short loc_1800032FD
0x1800032f2  call    ?EnsureDSSvcRunning@@YAJXZ; EnsureDSSvcRunning(void)
0x1800032f7  mov     ebx, eax
0x1800032f9  test    eax, eax
0x1800032fb  js      short loc_18000331C
0x1800032fd  mov     rdx, rdi; struct _DS_SHARE_SCOPE *
0x180003300  mov     rcx, rsi; unsigned __int16 *
0x180003303  call    ?DSCDelegateSharingToken@@YAJPEBGPEAU_DS_SHARE_SCOPE@@@Z; DSCDelegateSharingToken(ushort const *,_DS_SHARE_SCOPE *)
0x180003308  mov     ecx, eax; int
0x18000330a  mov     ebx, eax
0x18000330c  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180003311  test    eax, eax
0x180003313  jz      short loc_18000331C
0x180003315  inc     ebp
0x180003317  cmp     ebp, 2
0x18000331a  jl      short loc_1800032E7
0x18000331c  test    ebx, ebx
0x18000331e  js      short loc_18000333B
0x180003320  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180003325  lea     rdx, aDsdelegateshar_0; "DSDelegateSharingToken finished."
0x18000332c  mov     rcx, rax; this
0x18000332f  call    ?LogClientApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogClientApiCompleted(ushort const *)
0x180003334  jmp     short loc_180003360
0x180003336  mov     ebx, 80070057h
0x18000333b  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180003340  lea     r9, aHr0xX; "hr=0x%x."
0x180003347  mov     [rsp+58h+var_38], ebx
0x18000334b  mov     r8d, 1ACh; unsigned int
0x180003351  lea     rdx, aDsdelegateshar_1; "DSDelegateSharingToken"
0x180003358  mov     rcx, rax; this
0x18000335b  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180003360  mov     eax, ebx
0x180003362  add     rsp, 30h
0x180003366  pop     r14
0x180003368  pop     rdi
0x180003369  pop     rsi
0x18000336a  pop     rbp
0x18000336b  pop     rbx
0x18000336c  retn
```
