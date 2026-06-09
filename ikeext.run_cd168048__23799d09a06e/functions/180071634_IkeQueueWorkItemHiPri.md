# IkeQueueWorkItemHiPri

- ea: `0x180071634`
- end: `0x18007179d`
- name: `IkeQueueWorkItemHiPri`
- size: `361`
- prototype: `__int64 __fastcall(PTP_SIMPLE_CALLBACK pfns, PVOID pv)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18003a2e0`
- `0x1800713b0`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x180008388`
- `0x180018af0`
- `0x1800488f0`
- `0x18004890c`
- `0x180050850`
- `0x18005bc40`
- `0x180071634`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007173f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007173f`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180071735`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180071735`

## string_xrefs

- `0x18007174b`: `TrySubmitThreadpoolCallback`
- `0x1800716e1`: `Queuing work to high priority thread pool`

## pseudocode

```c
__int64 __fastcall IkeQueueWorkItemHiPri(PTP_SIMPLE_CALLBACK pfns, PVOID pv, __int64 a3, __int64 a4)
{
  __int64 v6; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int TlsMmLuid; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  DWORD LastError; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v21; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v22[32]; // [rsp+40h] [rbp-78h] BYREF
  __int64 *v23; // [rsp+60h] [rbp-58h]
  __int64 v24; // [rsp+68h] [rbp-50h]
  _BYTE v25[16]; // [rsp+70h] [rbp-48h] BYREF
  const char *v26; // [rsp+80h] [rbp-38h]
  __int64 v27; // [rsp+88h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(pfns);
    TlsMmLuid = IkeGetTlsMmLuid(v9, v8, v10, v11);
    WPP_SF_iS(v6, 16, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v21 = IkeGetTlsMmLuid(pfns, pv, a3, a4);
    v23 = &v21;
    v24 = 8;
    v14 = IkeGetTlsPeerAddr(v13);
    tlgCreate1Sz_wchar_t(v25, v14);
    v27 = 42;
    v26 = "Queuing work to high priority thread pool";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180153825,
      v15,
      v16,
      5,
      (__int64)v22);
  }
  if ( TrySubmitThreadpoolCallback(pfns, pv, (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[78].LockCount) )
  {
    IkeGlobalStatsUpdateCurrentQueuedWorkitems(1);
  }
  else
  {
    LastError = GetLastError();
    v19 = WfpReportSysErrorAsWinError(v18, "TrySubmitThreadpoolCallback", LastError, 1);
  }
  return IkeReturnError(v19, "IkeQueueWorkItemHiPri");
}

```

## disassembly

```asm
0x180071634  mov     [rsp+arg_10], rbx
0x180071639  push    rbp
0x18007163a  push    rsi
0x18007163b  push    rdi
0x18007163c  sub     rsp, 0A0h
0x180071643  mov     rax, cs:__security_cookie
0x18007164a  xor     rax, rsp
0x18007164d  mov     [rsp+0B8h+var_28], rax
0x180071655  mov     rbp, rdx
0x180071658  mov     rsi, rcx
0x18007165b  mov     rdi, cs:WPP_GLOBAL_Control
0x180071662  lea     rax, WPP_GLOBAL_Control
0x180071669  cmp     rdi, rax
0x18007166c  jz      short loc_1800716A7
0x18007166e  cmp     byte ptr [rdi+19h], 4
0x180071672  jb      short loc_1800716A7
0x180071674  test    byte ptr [rdi+1Ch], 10h
0x180071678  jz      short loc_1800716A7
0x18007167a  mov     rdi, [rdi+10h]
0x18007167e  call    IkeGetTlsPeerAddr
0x180071683  mov     rbx, rax
0x180071686  call    IkeGetTlsMmLuid
0x18007168b  mov     r9, rax
0x18007168e  mov     [rsp+0B8h+var_98], rbx
0x180071693  mov     edx, 10h
0x180071698  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x18007169f  mov     rcx, rdi
0x1800716a2  call    WPP_SF_iS
0x1800716a7  mov     eax, cs:dword_180173278
0x1800716ad  cmp     eax, 4
0x1800716b0  jbe     short loc_180071721
0x1800716b2  call    IkeGetTlsMmLuid
0x1800716b7  mov     [rsp+0B8h+var_88], rax
0x1800716bc  lea     rax, [rsp+0B8h+var_88]
0x1800716c1  mov     [rsp+0B8h+var_58], rax
0x1800716c6  mov     [rsp+0B8h+var_50], 8
0x1800716cf  call    IkeGetTlsPeerAddr
0x1800716d4  mov     rdx, rax
0x1800716d7  lea     rcx, [rsp+0B8h+var_48]
0x1800716dc  call    _tlgCreate1Sz_wchar_t
0x1800716e1  lea     rcx, aQueuingWorkToH; "Queuing work to high priority thread po"...
0x1800716e8  mov     [rsp+0B8h+var_30], 2Ah ; '*'
0x1800716f4  lea     rax, [rsp+0B8h+var_78]
0x1800716f9  mov     [rsp+0B8h+var_38], rcx
0x180071701  mov     [rsp+0B8h+var_90], rax
0x180071706  lea     rcx, dword_180173278
0x18007170d  lea     rdx, byte_180153825
0x180071714  mov     dword ptr [rsp+0B8h+var_98], 5
0x18007171c  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180071721  mov     r8, cs:gIkeExtGlobals
0x180071728  mov     rdx, rbp; pv
0x18007172b  add     r8, 0C38h; pcbe
0x180071732  mov     rcx, rsi; pfns
0x180071735  call    cs:__imp_TrySubmitThreadpoolCallback
0x18007173b  test    eax, eax
0x18007173d  jnz     short loc_18007175F
0x18007173f  call    cs:__imp_GetLastError
0x180071745  mov     r9d, 1
0x18007174b  lea     rdx, aTrysubmitthrea; "TrySubmitThreadpoolCallback"
0x180071752  mov     r8d, eax
0x180071755  call    WfpReportSysErrorAsWinError
0x18007175a  mov     r8, rax
0x18007175d  jmp     short loc_18007176B
0x18007175f  xor     r8d, r8d
0x180071762  lea     ecx, [r8+1]
0x180071766  call    IkeGlobalStatsUpdateCurrentQueuedWorkitems
0x18007176b  lea     rdx, aIkequeueworkit; "IkeQueueWorkItemHiPri"
0x180071772  mov     rcx, r8
0x180071775  call    IkeReturnError
0x18007177a  mov     rcx, [rsp+0B8h+var_28]
0x180071782  xor     rcx, rsp; StackCookie
0x180071785  call    __security_check_cookie
0x18007178a  mov     rbx, [rsp+0B8h+arg_10]
0x180071792  add     rsp, 0A0h
0x180071799  pop     rdi
0x18007179a  pop     rsi
0x18007179b  pop     rbp
0x18007179c  retn
```
