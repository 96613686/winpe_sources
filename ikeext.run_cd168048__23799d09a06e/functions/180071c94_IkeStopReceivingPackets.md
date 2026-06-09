# IkeStopReceivingPackets

- ea: `0x180071c94`
- end: `0x180071f7e`
- name: `IkeStopReceivingPackets`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180058100`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x180071c94`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071db1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071dfd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071e49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071e95`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071db1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071dfd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071e49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180071e95`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071d98`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071dc8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071de4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071e14`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071e30`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071e60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071e7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071eac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071d98`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071dc8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071de4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071e14`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071e30`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071e60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071e7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180071eac`

## pseudocode

```c
__int64 IkeStopReceivingPackets()
{
  __int64 v0; // rdi
  __int64 TlsPeerAddr; // rbx
  int TlsMmLuid; // eax
  __int64 v3; // rax
  int v4; // r8d
  int v5; // r9d
  LPCRITICAL_SECTION v6; // rax
  struct _TP_WAIT *DebugInfo; // rcx
  struct _TP_WAIT *v8; // rcx
  struct _TP_WAIT *OwningThread; // rcx
  struct _TP_WAIT *LockSemaphore; // rcx
  __int64 v11; // rdi
  __int64 v12; // rbx
  int v13; // eax
  __int64 result; // rax
  __int64 v15; // rax
  int v16; // r8d
  _QWORD v17[2]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v19; // [rsp+60h] [rbp-9h]
  __int64 v20; // [rsp+68h] [rbp-1h]
  _BYTE v21[16]; // [rsp+70h] [rbp+7h] BYREF
  const char *v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]

  TraceLogHelper("IkeStopReceivingPackets", 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v0 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr();
    TlsMmLuid = IkeGetTlsMmLuid();
    WPP_SF_iS(v0, 27, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v17[0] = IkeGetTlsMmLuid();
    v19 = v17;
    v20 = 8;
    v3 = IkeGetTlsPeerAddr();
    tlgCreate1Sz_wchar_t(v21, v3);
    v23 = 31;
    v22 = "Stopping the Receive callbacks";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)&unk_180153598,
      v4,
      v5,
      5,
      (__int64)v18);
  }
  v6 = gIkeExtGlobals;
  DebugInfo = (struct _TP_WAIT *)gIkeExtGlobals[82].DebugInfo;
  if ( DebugInfo )
  {
    WaitForThreadpoolWaitCallbacks(DebugInfo, 1);
    SetThreadpoolWait((PTP_WAIT)gIkeExtGlobals[82].DebugInfo, 0, 0);
    WaitForThreadpoolWaitCallbacks((PTP_WAIT)gIkeExtGlobals[82].DebugInfo, 1);
    v6 = gIkeExtGlobals;
  }
  v8 = *(struct _TP_WAIT **)&v6[82].LockCount;
  if ( v8 )
  {
    WaitForThreadpoolWaitCallbacks(v8, 1);
    SetThreadpoolWait(*(PTP_WAIT *)&gIkeExtGlobals[82].LockCount, 0, 0);
    WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)&gIkeExtGlobals[82].LockCount, 1);
    v6 = gIkeExtGlobals;
  }
  OwningThread = (struct _TP_WAIT *)v6[82].OwningThread;
  if ( OwningThread )
  {
    WaitForThreadpoolWaitCallbacks(OwningThread, 1);
    SetThreadpoolWait((PTP_WAIT)gIkeExtGlobals[82].OwningThread, 0, 0);
    WaitForThreadpoolWaitCallbacks((PTP_WAIT)gIkeExtGlobals[82].OwningThread, 1);
    v6 = gIkeExtGlobals;
  }
  LockSemaphore = (struct _TP_WAIT *)v6[82].LockSemaphore;
  if ( LockSemaphore )
  {
    WaitForThreadpoolWaitCallbacks(LockSemaphore, 1);
    SetThreadpoolWait((PTP_WAIT)gIkeExtGlobals[82].LockSemaphore, 0, 0);
    WaitForThreadpoolWaitCallbacks((PTP_WAIT)gIkeExtGlobals[82].LockSemaphore, 1);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v12 = IkeGetTlsPeerAddr();
    v13 = IkeGetTlsMmLuid();
    WPP_SF_iS(v11, 28, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, v13, v12);
  }
  result = (unsigned int)dword_180173278;
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v17[0] = IkeGetTlsMmLuid();
    v19 = v17;
    v20 = 8;
    v15 = IkeGetTlsPeerAddr();
    tlgCreate1Sz_wchar_t(v21, v15);
    v23 = 39;
    v22 = "Receive callbacks successfully stopped";
    return tlgWriteTransfer_EtwEventWriteTransfer(
             (unsigned int)&dword_180173278,
             (unsigned int)&byte_18015354F,
             v16,
             (unsigned int)"Receive callbacks successfully stopped",
             5,
             (__int64)v18);
  }
  return result;
}

```

## disassembly

```asm
0x180071c94  push    rbp
0x180071c96  push    rbx
0x180071c97  push    rdi
0x180071c98  push    r14
0x180071c9a  push    r15
0x180071c9c  lea     rbp, [rsp-37h]
0x180071ca1  sub     rsp, 0A0h
0x180071ca8  mov     rax, cs:__security_cookie
0x180071caf  xor     rax, rsp
0x180071cb2  mov     [rbp+57h+var_30], rax
0x180071cb6  mov     r14d, 1
0x180071cbc  lea     rcx, aIkestopreceivi; "IkeStopReceivingPackets"
0x180071cc3  mov     edx, r14d
0x180071cc6  call    TraceLogHelper
0x180071ccb  mov     rdi, cs:WPP_GLOBAL_Control
0x180071cd2  lea     r15, WPP_GLOBAL_Control
0x180071cd9  cmp     rdi, r15
0x180071cdc  jz      short loc_180071D16
0x180071cde  cmp     byte ptr [rdi+19h], 4
0x180071ce2  jb      short loc_180071D16
0x180071ce4  test    byte ptr [rdi+1Ch], 10h
0x180071ce8  jz      short loc_180071D16
0x180071cea  mov     rdi, [rdi+10h]
0x180071cee  call    IkeGetTlsPeerAddr
0x180071cf3  mov     rbx, rax
0x180071cf6  call    IkeGetTlsMmLuid
0x180071cfb  mov     r9, rax
0x180071cfe  mov     [rsp+0C0h+var_A0], rbx
0x180071d03  lea     edx, [r14+1Ah]
0x180071d07  mov     rcx, rdi
0x180071d0a  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x180071d11  call    WPP_SF_iS
0x180071d16  mov     eax, cs:dword_180173278
0x180071d1c  cmp     eax, 4
0x180071d1f  jbe     short loc_180071D82
0x180071d21  call    IkeGetTlsMmLuid
0x180071d26  mov     [rbp+57h+var_90], rax
0x180071d2a  lea     rax, [rbp+57h+var_90]
0x180071d2e  mov     [rbp+57h+var_60], rax
0x180071d32  mov     [rbp+57h+var_58], 8
0x180071d3a  call    IkeGetTlsPeerAddr
0x180071d3f  mov     rdx, rax
0x180071d42  lea     rcx, [rbp+57h+var_50]
0x180071d46  call    _tlgCreate1Sz_wchar_t
0x180071d4b  lea     rcx, aStoppingTheRec; "Stopping the Receive callbacks"
0x180071d52  mov     [rbp+57h+var_38], 1Fh
0x180071d5a  lea     rax, [rbp+57h+var_80]
0x180071d5e  mov     [rbp+57h+var_40], rcx
0x180071d62  mov     [rsp+0C0h+var_98], rax
0x180071d67  lea     rcx, dword_180173278
0x180071d6e  lea     rdx, unk_180153598
0x180071d75  mov     dword ptr [rsp+0C0h+var_A0], 5
0x180071d7d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180071d82  mov     rax, cs:gIkeExtGlobals
0x180071d89  mov     rcx, [rax+0CD0h]; pwa
0x180071d90  test    rcx, rcx
0x180071d93  jz      short loc_180071DD5
0x180071d95  mov     edx, r14d; fCancelPendingCallbacks
0x180071d98  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180071d9e  mov     rcx, cs:gIkeExtGlobals
0x180071da5  xor     r8d, r8d; pftTimeout
0x180071da8  xor     edx, edx; h
0x180071daa  mov     rcx, [rcx+0CD0h]; pwa
0x180071db1  call    cs:__imp_SetThreadpoolWait
0x180071db7  mov     rcx, cs:gIkeExtGlobals
0x180071dbe  mov     edx, r14d; fCancelPendingCallbacks
0x180071dc1  mov     rcx, [rcx+0CD0h]; pwa
0x180071dc8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180071dce  mov     rax, cs:gIkeExtGlobals
0x180071dd5  mov     rcx, [rax+0CD8h]; pwa
0x180071ddc  test    rcx, rcx
0x180071ddf  jz      short loc_180071E21
0x180071de1  mov     edx, r14d; fCancelPendingCallbacks
0x180071de4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180071dea  mov     rcx, cs:gIkeExtGlobals
0x180071df1  xor     r8d, r8d; pftTimeout
0x180071df4  xor     edx, edx; h
0x180071df6  mov     rcx, [rcx+0CD8h]; pwa
0x180071dfd  call    cs:__imp_SetThreadpoolWait
0x180071e03  mov     rcx, cs:gIkeExtGlobals
0x180071e0a  mov     edx, r14d; fCancelPendingCallbacks
0x180071e0d  mov     rcx, [rcx+0CD8h]; pwa
0x180071e14  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180071e1a  mov     rax, cs:gIkeExtGlobals
0x180071e21  mov     rcx, [rax+0CE0h]; pwa
0x180071e28  test    rcx, rcx
0x180071e2b  jz      short loc_180071E6D
0x180071e2d  mov     edx, r14d; fCancelPendingCallbacks
0x180071e30  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180071e36  mov     rcx, cs:gIkeExtGlobals
0x180071e3d  xor     r8d, r8d; pftTimeout
0x180071e40  xor     edx, edx; h
0x180071e42  mov     rcx, [rcx+0CE0h]; pwa
0x180071e49  call    cs:__imp_SetThreadpoolWait
0x180071e4f  mov     rcx, cs:gIkeExtGlobals
0x180071e56  mov     edx, r14d; fCancelPendingCallbacks
0x180071e59  mov     rcx, [rcx+0CE0h]; pwa
0x180071e60  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180071e66  mov     rax, cs:gIkeExtGlobals
0x180071e6d  mov     rcx, [rax+0CE8h]; pwa
0x180071e74  test    rcx, rcx
0x180071e77  jz      short loc_180071EB2
0x180071e79  mov     edx, r14d; fCancelPendingCallbacks
0x180071e7c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180071e82  mov     rcx, cs:gIkeExtGlobals
0x180071e89  xor     r8d, r8d; pftTimeout
0x180071e8c  xor     edx, edx; h
0x180071e8e  mov     rcx, [rcx+0CE8h]; pwa
0x180071e95  call    cs:__imp_SetThreadpoolWait
0x180071e9b  mov     rcx, cs:gIkeExtGlobals
0x180071ea2  mov     edx, r14d; fCancelPendingCallbacks
0x180071ea5  mov     rcx, [rcx+0CE8h]; pwa
0x180071eac  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180071eb2  mov     rdi, cs:WPP_GLOBAL_Control
0x180071eb9  cmp     rdi, r15
0x180071ebc  jz      short loc_180071EF7
0x180071ebe  cmp     byte ptr [rdi+19h], 4
0x180071ec2  jb      short loc_180071EF7
0x180071ec4  test    byte ptr [rdi+1Ch], 10h
0x180071ec8  jz      short loc_180071EF7
0x180071eca  mov     rdi, [rdi+10h]
0x180071ece  call    IkeGetTlsPeerAddr
0x180071ed3  mov     rbx, rax
0x180071ed6  call    IkeGetTlsMmLuid
0x180071edb  mov     r9, rax
0x180071ede  mov     [rsp+0C0h+var_A0], rbx
0x180071ee3  mov     edx, 1Ch
0x180071ee8  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x180071eef  mov     rcx, rdi
0x180071ef2  call    WPP_SF_iS
0x180071ef7  mov     eax, cs:dword_180173278
0x180071efd  cmp     eax, 4
0x180071f00  jbe     short loc_180071F63
0x180071f02  call    IkeGetTlsMmLuid
0x180071f07  mov     [rbp+57h+var_90], rax
0x180071f0b  lea     rax, [rbp+57h+var_90]
0x180071f0f  mov     [rbp+57h+var_60], rax
0x180071f13  mov     [rbp+57h+var_58], 8
0x180071f1b  call    IkeGetTlsPeerAddr
0x180071f20  mov     rdx, rax
0x180071f23  lea     rcx, [rbp+57h+var_50]
0x180071f27  call    _tlgCreate1Sz_wchar_t
0x180071f2c  lea     rax, [rbp+57h+var_80]
0x180071f30  mov     [rbp+57h+var_38], 27h ; '''
0x180071f38  lea     r9, aReceiveCallbac; "Receive callbacks successfully stopped"
0x180071f3f  mov     [rsp+0C0h+var_98], rax
0x180071f44  lea     rdx, byte_18015354F
0x180071f4b  mov     dword ptr [rsp+0C0h+var_A0], 5
0x180071f53  lea     rcx, dword_180173278
0x180071f5a  mov     [rbp+57h+var_40], r9
0x180071f5e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180071f63  mov     rcx, [rbp+57h+var_30]
0x180071f67  xor     rcx, rsp; StackCookie
0x180071f6a  call    __security_check_cookie
0x180071f6f  add     rsp, 0A0h
0x180071f76  pop     r15
0x180071f78  pop     r14
0x180071f7a  pop     rdi
0x180071f7b  pop     rbx
0x180071f7c  pop     rbp
0x180071f7d  retn
```
