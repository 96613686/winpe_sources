# HrOnCommandStatus(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x1800459f0`
- end: `0x180045bf2`
- name: `?HrOnCommandStatus@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x1800020b0`
- `0x180005c8c`
- `0x18001c91c`
- `0x18001c9f8`
- `0x18001cdb0`
- `0x18001ce7c`
- `0x18001d580`
- `0x18001e1e0`
- `0x1800227b0`
- `0x180034ba0`
- `0x180040a5c`
- `0x1800459f0`
- `0x180045bf8`
- `0x18004a540`
- `0x18004bf00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180045b7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180045b7f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180045b3b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180045b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045b88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045b88`
- `ole32!StringFromGUID2` at `0x180045b09`
- `ole32!StringFromGUID2` at `0x180045b09`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HrOnCommandStatus(ConFoldPidl_v3 ***a1, HWND a2)
{
  ConFoldPidl_v3 **v4; // rsi
  ConFoldPidl_v3 *v5; // rcx
  int Win32Error; // ebx
  HANDLE MutexW; // rdi
  unsigned int v8; // edx
  struct IUnknown *v10; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v11[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+38h] [rbp-C8h]
  _QWORD v13[42]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[48]; // [rsp+210h] [rbp+110h] BYREF

  CConFoldEntry::CConFoldEntry((CConFoldEntry *)v11);
  v10 = 0;
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v13,
    "NetworkConnectionAction");
  v13[0] = &NetworkLegacyUxTelemetry::NetworkConnectionAction::`vftable';
  NetworkLegacyUxTelemetry::NetworkConnectionAction::StartActivity(
    (NetworkLegacyUxTelemetry::NetworkConnectionAction *)v13,
    L"ShowStatus");
  v4 = *a1;
  v5 = **a1;
  if ( v5 && (unsigned __int64)(a1[1] - v4) <= 1 )
  {
    Win32Error = ConFoldPidl_v3::ConvertToConFoldEntry(v5, (struct CConFoldEntry *)v11);
    if ( Win32Error >= 0
      && (v12 == 2 || v12 == 8 || v12 == 9 || v12 == 10 || v12 == 12 || ((v12 - 7) & 0xFFFFFFFB) != 0) )
    {
      Win32Error = HrNetConFromPidl(*a1, &v10, 1);
      if ( Win32Error >= 0 )
      {
        SetLUAParent(v10, a2);
        StringFromGUID2((const GUID *const)((char *)*v4 + 28), sz, 39);
        Win32Error = StringCchCatW(sz, 0x2Fu, L":status");
        if ( Win32Error >= 0 )
        {
          MutexW = CreateMutexW(0, 1, sz);
          if ( MutexW )
          {
            if ( GetLastError() == 183 )
              ActivateDialog(1, v10);
            else
              Win32Error = HrOnCommandStatusInternal((const struct CConFoldEntry *)v11, v8);
            ReleaseMutex(MutexW);
            CloseHandle(MutexW);
          }
          else
          {
            Win32Error = HrFromLastWin32Error();
          }
        }
      }
    }
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v13,
      (unsigned int)Win32Error);
    NetworkLegacyUxTelemetry::NetworkConnectionAction::~NetworkConnectionAction((NetworkLegacyUxTelemetry::NetworkConnectionAction *)v13);
    CConFoldEntry::~CConFoldEntry((CConFoldEntry *)v11);
    return (unsigned int)Win32Error;
  }
  else
  {
    NetworkLegacyUxTelemetry::NetworkConnectionAction::~NetworkConnectionAction((NetworkLegacyUxTelemetry::NetworkConnectionAction *)v13);
    CConFoldEntry::~CConFoldEntry((CConFoldEntry *)v11);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800459f0  mov     [rsp-8+arg_10], rbx
0x1800459f5  mov     [rsp-8+arg_18], rsi
0x1800459fa  push    rbp
0x1800459fb  push    rdi
0x1800459fc  push    r14
0x1800459fe  lea     rbp, [rsp-180h]
0x180045a06  sub     rsp, 280h
0x180045a0d  mov     rax, cs:__security_cookie
0x180045a14  xor     rax, rsp
0x180045a17  mov     [rbp+190h+var_20], rax
0x180045a1e  mov     r14, rdx
0x180045a21  mov     rdi, rcx
0x180045a24  lea     rcx, [rsp+290h+var_260]; this
0x180045a29  call    ??0CConFoldEntry@@QEAA@XZ; CConFoldEntry::CConFoldEntry(void)
0x180045a2e  nop
0x180045a2f  mov     [rsp+290h+var_270], 0
0x180045a38  lea     rdx, aNetworkconnect; "NetworkConnectionAction"
0x180045a3f  lea     rcx, [rbp+190h+var_1D0]
0x180045a43  call    ??0?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180045a48  lea     rax, ??_7NetworkConnectionAction@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::NetworkConnectionAction::`vftable'
0x180045a4f  mov     [rbp+190h+var_1D0], rax
0x180045a53  lea     rdx, aShowstatus; "ShowStatus"
0x180045a5a  lea     rcx, [rbp+190h+var_1D0]; this
0x180045a5e  call    ?StartActivity@NetworkConnectionAction@NetworkLegacyUxTelemetry@@QEAAXPEBG@Z; NetworkLegacyUxTelemetry::NetworkConnectionAction::StartActivity(ushort const *)
0x180045a63  mov     rsi, [rdi]
0x180045a66  mov     rcx, [rsi]; this
0x180045a69  test    rcx, rcx
0x180045a6c  jz      loc_180045BB2
0x180045a72  mov     rax, [rdi+8]
0x180045a76  sub     rax, rsi
0x180045a79  sar     rax, 3
0x180045a7d  cmp     rax, 1
0x180045a81  ja      loc_180045BB2
0x180045a87  lea     rdx, [rsp+290h+var_260]; struct CConFoldEntry *
0x180045a8c  call    ?ConvertToConFoldEntry@ConFoldPidl_v3@@QEBAJAEAVCConFoldEntry@@@Z; ConFoldPidl_v3::ConvertToConFoldEntry(CConFoldEntry &)
0x180045a91  mov     ebx, eax
0x180045a93  test    eax, eax
0x180045a95  js      loc_180045B8E
0x180045a9b  mov     r8d, [rsp+290h+var_258]
0x180045aa0  mov     edx, r8d
0x180045aa3  sub     edx, 2
0x180045aa6  jz      short loc_180045ACB
0x180045aa8  sub     edx, 6
0x180045aab  jz      short loc_180045ACB
0x180045aad  sub     edx, 1
0x180045ab0  jz      short loc_180045ACB
0x180045ab2  sub     edx, 1
0x180045ab5  jz      short loc_180045ACB
0x180045ab7  cmp     edx, 2
0x180045aba  jz      short loc_180045ACB
0x180045abc  lea     eax, [r8-7]
0x180045ac0  test    eax, 0FFFFFFFBh
0x180045ac5  jz      loc_180045B8E
0x180045acb  mov     r8d, 1
0x180045ad1  lea     rdx, [rsp+290h+var_270]
0x180045ad6  mov     rcx, [rdi]
0x180045ad9  call    ?HrNetConFromPidl@@YAJAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@PEAPEAUINetConnection@@H@Z; HrNetConFromPidl(CPConFoldPidl<ConFoldPidl_v3> const &,INetConnection * *,int)
0x180045ade  mov     ebx, eax
0x180045ae0  test    eax, eax
0x180045ae2  js      loc_180045B8E
0x180045ae8  mov     rdx, r14; HWND
0x180045aeb  mov     rcx, [rsp+290h+var_270]; struct IUnknown *
0x180045af0  call    ?SetLUAParent@@YAXPEAUIUnknown@@PEAUHWND__@@@Z; SetLUAParent(IUnknown *,HWND__ *)
0x180045af5  mov     rcx, [rsi]
0x180045af8  add     rcx, 1Ch; rguid
0x180045afc  mov     r8d, 27h ; '''; cchMax
0x180045b02  lea     rdx, [rbp+190h+sz]; lpsz
0x180045b09  call    cs:__imp_StringFromGUID2
0x180045b0f  lea     r8, aStatus_0; ":status"
0x180045b16  mov     edx, 2Fh ; '/'; unsigned __int64
0x180045b1b  lea     rcx, [rbp+190h+sz]; unsigned __int16 *
0x180045b22  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180045b27  mov     ebx, eax
0x180045b29  test    eax, eax
0x180045b2b  js      short loc_180045B8E
0x180045b2d  lea     r8, [rbp+190h+sz]; lpName
0x180045b34  mov     edx, 1; bInitialOwner
0x180045b39  xor     ecx, ecx; lpMutexAttributes
0x180045b3b  call    cs:__imp_CreateMutexW
0x180045b41  mov     rdi, rax
0x180045b44  test    rax, rax
0x180045b47  jnz     short loc_180045B52
0x180045b49  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180045b4e  mov     ebx, eax
0x180045b50  jmp     short loc_180045B8E
0x180045b52  call    cs:__imp_GetLastError
0x180045b58  cmp     eax, 0B7h
0x180045b5d  jnz     short loc_180045B70
0x180045b5f  mov     rdx, [rsp+290h+var_270]
0x180045b64  mov     ecx, 1
0x180045b69  call    ?ActivateDialog@@YAXW4DIALOG_TYPE@@PEAUINetConnection@@@Z; ActivateDialog(DIALOG_TYPE,INetConnection *)
0x180045b6e  jmp     short loc_180045B7C
0x180045b70  lea     rcx, [rsp+290h+var_260]; struct CConFoldEntry *
0x180045b75  call    ?HrOnCommandStatusInternal@@YAJAEBVCConFoldEntry@@K@Z; HrOnCommandStatusInternal(CConFoldEntry const &,ulong)
0x180045b7a  mov     ebx, eax
0x180045b7c  mov     rcx, rdi; hMutex
0x180045b7f  call    cs:__imp_ReleaseMutex
0x180045b85  mov     rcx, rdi; hObject
0x180045b88  call    cs:__imp_CloseHandle
0x180045b8e  mov     edx, ebx
0x180045b90  lea     rcx, [rbp+190h+var_1D0]
0x180045b94  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180045b99  nop
0x180045b9a  lea     rcx, [rbp+190h+var_1D0]; this
0x180045b9e  call    ??1NetworkConnectionAction@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::NetworkConnectionAction::~NetworkConnectionAction(void)
0x180045ba3  nop
0x180045ba4  lea     rcx, [rsp+290h+var_260]; this
0x180045ba9  call    ??1CConFoldEntry@@QEAA@XZ; CConFoldEntry::~CConFoldEntry(void)
0x180045bae  mov     eax, ebx
0x180045bb0  jmp     short loc_180045BCB
0x180045bb2  lea     rcx, [rbp+190h+var_1D0]; this
0x180045bb6  call    ??1NetworkConnectionAction@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::NetworkConnectionAction::~NetworkConnectionAction(void)
0x180045bbb  nop
0x180045bbc  lea     rcx, [rsp+290h+var_260]; this
0x180045bc1  call    ??1CConFoldEntry@@QEAA@XZ; CConFoldEntry::~CConFoldEntry(void)
0x180045bc6  mov     eax, 80070057h
0x180045bcb  mov     rcx, [rbp+190h+var_20]
0x180045bd2  xor     rcx, rsp; StackCookie
0x180045bd5  call    __security_check_cookie
0x180045bda  lea     r11, [rsp+290h+var_10]
0x180045be2  mov     rbx, [r11+30h]
0x180045be6  mov     rsi, [r11+38h]
0x180045bea  mov     rsp, r11
0x180045bed  pop     r14
0x180045bef  pop     rdi
0x180045bf0  pop     rbp
0x180045bf1  retn
```
