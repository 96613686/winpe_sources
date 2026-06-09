# IkeCloseSockets

- ea: `0x18006fa50`
- end: `0x18006fc43`
- name: `IkeCloseSockets`
- size: `499`
- prototype: `int()`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

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
- `0x18006fa50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fbbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fbd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fbef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fc08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fbbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fbd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fbef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fc08`
- `WS2_32!__imp_closesocket` at `0x18006fb59`
- `WS2_32!__imp_closesocket` at `0x18006fb72`
- `WS2_32!__imp_closesocket` at `0x18006fb8b`
- `WS2_32!__imp_closesocket` at `0x18006fba4`
- `WS2_32!__imp_closesocket` at `0x18006fb59`
- `WS2_32!__imp_closesocket` at `0x18006fb72`
- `WS2_32!__imp_closesocket` at `0x18006fb8b`
- `WS2_32!__imp_closesocket` at `0x18006fba4`
- `WS2_32!__imp_WSACleanup` at `0x18006fc1c`
- `WS2_32!__imp_WSACleanup` at `0x18006fc1c`

## pseudocode

```c
int IkeCloseSockets()
{
  __int64 v0; // rcx
  __int64 v1; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v3; // rcx
  int TlsMmLuid; // eax
  __int64 v5; // rcx
  const WCHAR *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  LPCRITICAL_SECTION v9; // rax
  SOCKET SpinCount; // rcx
  SOCKET DebugInfo; // rcx
  SOCKET v12; // rcx
  SOCKET OwningThread; // rcx
  HANDLE LockSemaphore; // rcx
  void *v15; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v16; // rcx
  void *v17; // rcx
  __int64 v19; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v20[32]; // [rsp+40h] [rbp-68h] BYREF
  __int64 *v21; // [rsp+60h] [rbp-48h]
  __int64 v22; // [rsp+68h] [rbp-40h]
  _BYTE v23[16]; // [rsp+70h] [rbp-38h] BYREF
  const char *v24; // [rsp+80h] [rbp-28h]
  __int64 v25; // [rsp+88h] [rbp-20h]

  TraceLogHelper("IkeCloseSockets", 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v1 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v0);
    TlsMmLuid = IkeGetTlsMmLuid(v3);
    WPP_SF_iS(v1, 15, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v19 = IkeGetTlsMmLuid(v0);
    v21 = &v19;
    v22 = 8;
    v6 = (const WCHAR *)IkeGetTlsPeerAddr(v5);
    tlgCreate1Sz_wchar_t((__int64)v23, v6);
    v25 = 24;
    v24 = "Closing all the sockets";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)byte_1801538ED,
      v7,
      v8,
      5,
      (__int64)v20);
  }
  v9 = gIkeExtGlobals;
  SpinCount = gIkeExtGlobals[71].SpinCount;
  if ( SpinCount )
  {
    closesocket(SpinCount);
    v9 = gIkeExtGlobals;
  }
  DebugInfo = (SOCKET)v9[72].DebugInfo;
  if ( DebugInfo )
  {
    closesocket(DebugInfo);
    v9 = gIkeExtGlobals;
  }
  v12 = *(_QWORD *)&v9[72].LockCount;
  if ( v12 )
  {
    closesocket(v12);
    v9 = gIkeExtGlobals;
  }
  OwningThread = (SOCKET)v9[72].OwningThread;
  if ( OwningThread )
  {
    closesocket(OwningThread);
    v9 = gIkeExtGlobals;
  }
  LockSemaphore = v9[72].LockSemaphore;
  if ( LockSemaphore )
  {
    CloseHandle(LockSemaphore);
    v9 = gIkeExtGlobals;
  }
  v15 = (void *)v9[72].SpinCount;
  if ( v15 )
  {
    CloseHandle(v15);
    v9 = gIkeExtGlobals;
  }
  v16 = v9[73].DebugInfo;
  if ( v16 )
  {
    CloseHandle(v16);
    v9 = gIkeExtGlobals;
  }
  v17 = *(void **)&v9[73].LockCount;
  if ( v17 )
    CloseHandle(v17);
  TraceLogHelper("IkeCloseSockets", 0);
  return WSACleanup();
}

```

## disassembly

```asm
0x18006fa50  mov     [rsp+arg_0], rbx
0x18006fa55  push    rdi
0x18006fa56  sub     rsp, 0A0h
0x18006fa5d  mov     rax, cs:__security_cookie
0x18006fa64  xor     rax, rsp
0x18006fa67  mov     [rsp+0A8h+var_18], rax
0x18006fa6f  mov     edx, 1
0x18006fa74  lea     rcx, aIkeclosesocket; "IkeCloseSockets"
0x18006fa7b  call    TraceLogHelper
0x18006fa80  mov     rdi, cs:WPP_GLOBAL_Control
0x18006fa87  lea     rax, WPP_GLOBAL_Control
0x18006fa8e  cmp     rdi, rax
0x18006fa91  jz      short loc_18006FACC
0x18006fa93  cmp     byte ptr [rdi+19h], 4
0x18006fa97  jb      short loc_18006FACC
0x18006fa99  test    byte ptr [rdi+1Ch], 10h
0x18006fa9d  jz      short loc_18006FACC
0x18006fa9f  mov     rdi, [rdi+10h]
0x18006faa3  call    IkeGetTlsPeerAddr
0x18006faa8  mov     rbx, rax
0x18006faab  call    IkeGetTlsMmLuid
0x18006fab0  mov     r9, rax
0x18006fab3  mov     [rsp+0A8h+var_88], rbx
0x18006fab8  mov     edx, 0Fh
0x18006fabd  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x18006fac4  mov     rcx, rdi
0x18006fac7  call    WPP_SF_iS
0x18006facc  mov     eax, cs:dword_180173278
0x18006fad2  cmp     eax, 4
0x18006fad5  jbe     short loc_18006FB46
0x18006fad7  call    IkeGetTlsMmLuid
0x18006fadc  mov     [rsp+0A8h+var_78], rax
0x18006fae1  lea     rax, [rsp+0A8h+var_78]
0x18006fae6  mov     [rsp+0A8h+var_48], rax
0x18006faeb  mov     [rsp+0A8h+var_40], 8
0x18006faf4  call    IkeGetTlsPeerAddr
0x18006faf9  mov     rdx, rax
0x18006fafc  lea     rcx, [rsp+0A8h+var_38]
0x18006fb01  call    _tlgCreate1Sz_wchar_t
0x18006fb06  lea     rcx, aClosingAllTheS; "Closing all the sockets"
0x18006fb0d  mov     [rsp+0A8h+var_20], 18h
0x18006fb19  lea     rax, [rsp+0A8h+var_68]
0x18006fb1e  mov     [rsp+0A8h+var_28], rcx
0x18006fb26  mov     [rsp+0A8h+var_80], rax
0x18006fb2b  lea     rcx, dword_180173278
0x18006fb32  lea     rdx, byte_1801538ED
0x18006fb39  mov     dword ptr [rsp+0A8h+var_88], 5
0x18006fb41  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18006fb46  mov     rax, cs:gIkeExtGlobals
0x18006fb4d  mov     rcx, [rax+0B38h]; s
0x18006fb54  test    rcx, rcx
0x18006fb57  jz      short loc_18006FB66
0x18006fb59  call    cs:__imp_closesocket
0x18006fb5f  mov     rax, cs:gIkeExtGlobals
0x18006fb66  mov     rcx, [rax+0B40h]; s
0x18006fb6d  test    rcx, rcx
0x18006fb70  jz      short loc_18006FB7F
0x18006fb72  call    cs:__imp_closesocket
0x18006fb78  mov     rax, cs:gIkeExtGlobals
0x18006fb7f  mov     rcx, [rax+0B48h]; s
0x18006fb86  test    rcx, rcx
0x18006fb89  jz      short loc_18006FB98
0x18006fb8b  call    cs:__imp_closesocket
0x18006fb91  mov     rax, cs:gIkeExtGlobals
0x18006fb98  mov     rcx, [rax+0B50h]; s
0x18006fb9f  test    rcx, rcx
0x18006fba2  jz      short loc_18006FBB1
0x18006fba4  call    cs:__imp_closesocket
0x18006fbaa  mov     rax, cs:gIkeExtGlobals
0x18006fbb1  mov     rcx, [rax+0B58h]; hObject
0x18006fbb8  test    rcx, rcx
0x18006fbbb  jz      short loc_18006FBCA
0x18006fbbd  call    cs:__imp_CloseHandle
0x18006fbc3  mov     rax, cs:gIkeExtGlobals
0x18006fbca  mov     rcx, [rax+0B60h]; hObject
0x18006fbd1  test    rcx, rcx
0x18006fbd4  jz      short loc_18006FBE3
0x18006fbd6  call    cs:__imp_CloseHandle
0x18006fbdc  mov     rax, cs:gIkeExtGlobals
0x18006fbe3  mov     rcx, [rax+0B68h]; hObject
0x18006fbea  test    rcx, rcx
0x18006fbed  jz      short loc_18006FBFC
0x18006fbef  call    cs:__imp_CloseHandle
0x18006fbf5  mov     rax, cs:gIkeExtGlobals
0x18006fbfc  mov     rcx, [rax+0B70h]; hObject
0x18006fc03  test    rcx, rcx
0x18006fc06  jz      short loc_18006FC0E
0x18006fc08  call    cs:__imp_CloseHandle
0x18006fc0e  xor     edx, edx
0x18006fc10  lea     rcx, aIkeclosesocket; "IkeCloseSockets"
0x18006fc17  call    TraceLogHelper
0x18006fc1c  call    cs:__imp_WSACleanup
0x18006fc22  mov     rcx, [rsp+0A8h+var_18]
0x18006fc2a  xor     rcx, rsp; StackCookie
0x18006fc2d  call    __security_check_cookie
0x18006fc32  mov     rbx, [rsp+0A8h+arg_0]
0x18006fc3a  add     rsp, 0A0h
0x18006fc41  pop     rdi
0x18006fc42  retn
```
