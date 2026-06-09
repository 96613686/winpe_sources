# EapLm::Peer::EapLibraryManagerRuntime::ValidateThirdPartyProcess(EapHost::EapMethodType const &,SmartPointer<EapLm::Peer::IEapMethodRuntime>)

- ea: `0x180011d28`
- end: `0x180012001`
- name: `?ValidateThirdPartyProcess@EapLibraryManagerRuntime@Peer@EapLm@@QEAAXAEBVEapMethodType@EapHost@@V?$SmartPointer@UIEapMethodRuntime@Peer@EapLm@@@@@Z`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011a04`

## callees

- `0x180002af0`
- `0x180004af8`
- `0x180004d1c`
- `0x18000a21c`
- `0x180011cb8`
- `0x180011d28`
- `0x1800120c4`
- `0x18001e7c0`
- `0x180030b08`
- `0x180039010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180011df9`
- `ntdll!EtwEventEnabled` at `0x180011df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f42`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180011e9e`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180011e9e`

## string_xrefs

- `0x180011fa3`: `COM Error`
- `0x180011fed`: `COM Error`
- `0x180011faa`: `Create Third Party Proxy`
- `0x180011ff4`: `Create Third Party Proxy`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::Peer::EapLibraryManagerRuntime::ValidateThirdPartyProcess(
        __int64 a1,
        __int64 a2,
        ReferenceCounted **a3)
{
  __int64 v5; // rbx
  int v6; // r15d
  unsigned int v7; // edx
  bool v8; // zf
  __int64 v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  DWORD v14; // eax
  DWORD LastError; // eax
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v19[2048]; // [rsp+50h] [rbp-B0h] BYREF

  v18[1] = a3;
  v5 = 0;
  v6 = *(_DWORD *)(a2 + 24);
  v16 = 0;
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(v18, a1 + 960);
  v7 = *(_DWORD *)(a1 + 952);
  if ( !v7 )
    goto LABEL_7;
  while ( 1 )
  {
    v8 = (_DWORD)v5 == 32;
    if ( (unsigned int)v5 >= 0x20 )
      break;
    if ( v6 == *(_DWORD *)(a1 + 24 * v5 + 160) )
      goto LABEL_8;
    v5 = (unsigned int)(v5 + 1);
    if ( (unsigned int)v5 >= v7 )
    {
      v8 = (_DWORD)v5 == 32;
      break;
    }
  }
  if ( !v8 )
  {
LABEL_7:
    if ( (_DWORD)v5 != v7 )
    {
LABEL_8:
      v9 = (unsigned int)v5;
      v10 = 3 * v5;
      v11 = *(_QWORD *)(a1 + 8 * v10 + 176);
      if ( v11 )
      {
        v17 = 0;
        if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 24LL))(v11, &v17) >= 0 )
        {
LABEL_22:
          v13 = *(_QWORD *)(a1 + 8 * v10 + 176);
          goto LABEL_24;
        }
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
          && (int)StringCchPrintfA(
                    v19,
                    0x800u,
                    " Eap3Host process for the author id: %d not found. Hosting Eap Session in new process.",
                    v6) >= 0
          && (byte_18004F981 & 8) != 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v19);
        }
      }
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
      }
      if ( CoGetClassObject(
             &GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059,
             0x10004u,
             0,
             &GUID_00000001_0000_0000_c000_000000000046,
             (LPVOID *)(a1 + 168 + 8 * v10)) < 0 )
      {
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
        }
        LastError = GetLastError();
        EapHost::EapException::Throw(L"Create Third Party Proxy", L"COM Error", LastError);
      }
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 *))(**(_QWORD **)(a1 + 24 * v9 + 168) + 24LL))(
             *(_QWORD *)(a1 + 24 * v9 + 168),
             0,
             &GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae,
             &v16) < 0 )
      {
        v14 = GetLastError();
        EapHost::EapException::Throw(L"Create Third Party Proxy", L"COM Error", v14);
      }
      v12 = v16;
      v16 = 0;
      *(_QWORD *)(a1 + 8 * v10 + 176) = v12;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
      }
      goto LABEL_22;
    }
  }
  v13 = 0;
LABEL_24:
  (*(void (__fastcall **)(ReferenceCounted *, __int64))(*(_QWORD *)*a3 + 112LL))(*a3, v13);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v18[0] + 16LL));
  ComPointer<IUnknown>::Release(&v16);
  if ( *a3 )
    ReferenceCounted::Release(*a3);
}

```

## disassembly

```asm
0x180011d28  mov     [rsp-8+arg_8], rbx
0x180011d2d  mov     [rsp-8+arg_18], rsi
0x180011d32  push    rbp
0x180011d33  push    rdi
0x180011d34  push    r13
0x180011d36  push    r14
0x180011d38  push    r15
0x180011d3a  lea     rbp, [rsp-760h]
0x180011d42  sub     rsp, 860h
0x180011d49  mov     rax, cs:__security_cookie
0x180011d50  xor     rax, rsp
0x180011d53  mov     [rbp+780h+var_30], rax
0x180011d5a  mov     rsi, r8
0x180011d5d  mov     rdi, rcx
0x180011d60  mov     [rsp+880h+var_838], r8
0x180011d65  xor     ebx, ebx
0x180011d67  mov     r15d, [rdx+18h]
0x180011d6b  mov     [rsp+880h+var_850], rbx
0x180011d70  lea     rdx, [rcx+3C0h]
0x180011d77  lea     rcx, [rsp+880h+var_840]
0x180011d7c  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180011d81  nop
0x180011d82  mov     edx, [rdi+3B8h]
0x180011d88  test    edx, edx
0x180011d8a  jz      short loc_180011DAE
0x180011d8c  cmp     ebx, 20h ; ' '
0x180011d8f  jnb     short loc_180011DA8
0x180011d91  lea     rcx, [rbx+rbx*2]
0x180011d95  cmp     r15d, [rdi+rcx*8+0A0h]
0x180011d9d  jz      short loc_180011DB6
0x180011d9f  inc     ebx
0x180011da1  cmp     ebx, edx
0x180011da3  jb      short loc_180011D8C
0x180011da5  cmp     ebx, 20h ; ' '
0x180011da8  jz      loc_180011F27
0x180011dae  cmp     ebx, edx
0x180011db0  jz      loc_180011F27
0x180011db6  mov     r14d, ebx
0x180011db9  lea     rbx, [rbx+rbx*2]
0x180011dbd  mov     rcx, [rdi+rbx*8+0B0h]
0x180011dc5  test    rcx, rcx
0x180011dc8  jz      short loc_180011E47
0x180011dca  mov     [rsp+880h+var_848], 0
0x180011dd2  mov     rax, [rcx]
0x180011dd5  lea     rdx, [rsp+880h+var_848]
0x180011dda  mov     rax, [rax+18h]
0x180011dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011de3  test    eax, eax
0x180011de5  jns     loc_180011F1D
0x180011deb  lea     rdx, DebugErrorEvent
0x180011df2  mov     rcx, cs:eaphost_Context
0x180011df9  call    cs:__imp_EtwEventEnabled
0x180011e00  nop     dword ptr [rax+rax+00h]
0x180011e05  test    al, al
0x180011e07  jz      short loc_180011E47
0x180011e09  mov     r9d, r15d
0x180011e0c  lea     r8, aEap3hostProces; " Eap3Host process for the author id: %d"...
0x180011e13  mov     edx, 800h; unsigned __int64
0x180011e18  lea     rcx, [rsp+880h+var_830]; char *
0x180011e1d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011e22  test    eax, eax
0x180011e24  js      short loc_180011E47
0x180011e26  test    cs:byte_18004F981, 8
0x180011e2d  jz      short loc_180011E47
0x180011e2f  lea     r8, [rsp+880h+var_830]
0x180011e34  lea     rdx, DebugErrorEvent
0x180011e3b  lea     rcx, eaphost_Context
0x180011e42  call    McTemplateU0s_EtwEventWriteTransfer
0x180011e47  lea     r13, WPP_GLOBAL_Control
0x180011e4e  mov     r15b, 4
0x180011e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e58  cmp     rcx, r13
0x180011e5b  jz      short loc_180011E78
0x180011e5d  test    [rcx+1Ch], r15b
0x180011e61  jz      short loc_180011E78
0x180011e63  mov     edx, 0Ch
0x180011e68  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180011e6f  mov     rcx, [rcx+10h]
0x180011e73  call    WPP_SF_
0x180011e78  lea     rax, [rdi+0A8h]
0x180011e7f  lea     rax, [rax+rbx*8]
0x180011e83  mov     [rsp+880h+ppv], rax; ppv
0x180011e88  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180011e8f  xor     r8d, r8d; pvReserved
0x180011e92  mov     edx, 10004h; dwClsContext
0x180011e97  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x180011e9e  call    cs:__imp_CoGetClassObject
0x180011ea5  nop     dword ptr [rax+rax+00h]
0x180011eaa  test    eax, eax
0x180011eac  js      loc_180011FB7
0x180011eb2  lea     rax, [r14+r14*2]
0x180011eb6  mov     rcx, [rdi+rax*8+0A8h]
0x180011ebe  mov     rax, [rcx]
0x180011ec1  lea     r9, [rsp+880h+var_850]
0x180011ec6  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x180011ecd  xor     edx, edx
0x180011ecf  mov     rax, [rax+18h]
0x180011ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed8  test    eax, eax
0x180011eda  js      loc_180011F93
0x180011ee0  mov     rax, [rsp+880h+var_850]
0x180011ee5  mov     [rsp+880h+var_850], 0
0x180011eee  mov     [rdi+rbx*8+0B0h], rax
0x180011ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180011efd  cmp     rcx, r13
0x180011f00  jz      short loc_180011F1D
0x180011f02  test    [rcx+1Ch], r15b
0x180011f06  jz      short loc_180011F1D
0x180011f08  mov     edx, 0Eh
0x180011f0d  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180011f14  mov     rcx, [rcx+10h]
0x180011f18  call    WPP_SF_
0x180011f1d  mov     rdx, [rdi+rbx*8+0B0h]
0x180011f25  jmp     short loc_180011F29
0x180011f27  xor     edx, edx
0x180011f29  mov     rcx, [rsi]
0x180011f2c  mov     rax, [rcx]
0x180011f2f  mov     rax, [rax+70h]
0x180011f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f38  nop
0x180011f39  mov     rcx, [rsp+880h+var_840]
0x180011f3e  add     rcx, 10h; lpCriticalSection
0x180011f42  call    cs:__imp_LeaveCriticalSection
0x180011f49  nop     dword ptr [rax+rax+00h]
0x180011f4e  nop
0x180011f4f  lea     rcx, [rsp+880h+var_850]
0x180011f54  call    ?Release@?$ComPointer@UIUnknown@@@@AEAAXXZ; ComPointer<IUnknown>::Release(void)
0x180011f59  nop
0x180011f5a  mov     rcx, [rsi]; this
0x180011f5d  test    rcx, rcx
0x180011f60  jz      short loc_180011F67
0x180011f62  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180011f67  mov     rcx, [rbp+780h+var_30]
0x180011f6e  xor     rcx, rsp; StackCookie
0x180011f71  call    __security_check_cookie
0x180011f76  lea     r11, [rsp+880h+var_20]
0x180011f7e  mov     rbx, [r11+38h]
0x180011f82  mov     rsi, [r11+48h]
0x180011f86  mov     rsp, r11
0x180011f89  pop     r15
0x180011f8b  pop     r14
0x180011f8d  pop     r13
0x180011f8f  pop     rdi
0x180011f90  pop     rbp
0x180011f91  retn
0x180011f93  call    cs:__imp_GetLastError
0x180011f9a  nop     dword ptr [rax+rax+00h]
0x180011f9f  nop
0x180011fa0  mov     r8d, eax; int
0x180011fa3  lea     rdx, aComError; "COM Error"
0x180011faa  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180011fb1  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180011fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fbe  cmp     rcx, r13
0x180011fc1  jz      short loc_180011FDE
0x180011fc3  test    [rcx+1Ch], r15b
0x180011fc7  jz      short loc_180011FDE
0x180011fc9  mov     edx, 0Dh
0x180011fce  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180011fd5  mov     rcx, [rcx+10h]
0x180011fd9  call    WPP_SF_
0x180011fde  call    cs:__imp_GetLastError
0x180011fe5  nop     dword ptr [rax+rax+00h]
0x180011fea  mov     r8d, eax; int
0x180011fed  lea     rdx, aComError; "COM Error"
0x180011ff4  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180011ffb  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
