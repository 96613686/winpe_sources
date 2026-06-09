# EapLm::Peer::EapLibraryManagerRuntime::ValidateThirdPartyProcess(EapHost::EapMethodType const &,SmartPointer<EapLm::Peer::IEapMethodRuntime>)

- ea: `0x1800224cc`
- end: `0x180022786`
- name: `?ValidateThirdPartyProcess@EapLibraryManagerRuntime@Peer@EapLm@@QEAAXAEBVEapMethodType@EapHost@@V?$SmartPointer@UIEapMethodRuntime@Peer@EapLm@@@@@Z`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022234`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x18000d0e8`
- `0x180012c10`
- `0x180012d18`
- `0x180015534`
- `0x180016400`
- `0x18001b154`
- `0x1800224cc`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18002259d`
- `ntdll!EtwEventEnabled` at `0x18002259d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800226da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800226da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022769`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18002263c`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18002263c`

## string_xrefs

- `0x18002272e`: `COM Error`
- `0x180022772`: `COM Error`
- `0x180022735`: `Create Third Party Proxy`
- `0x180022779`: `Create Third Party Proxy`

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
          && (byte_18004AF81 & 8) != 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v19);
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
      if ( CoGetClassObject(
             &GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059,
             0x10004u,
             0,
             &GUID_00000001_0000_0000_c000_000000000046,
             (LPVOID *)(a1 + 168 + 8 * v10)) < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids);
      goto LABEL_22;
    }
  }
  v13 = 0;
LABEL_24:
  (*(void (__fastcall **)(ReferenceCounted *, __int64))(*(_QWORD *)*a3 + 112LL))(*a3, v13);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v18[0] + 16LL));
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v16);
  if ( *a3 )
    ReferenceCounted::Release(*a3);
}

```

## disassembly

```asm
0x1800224cc  mov     [rsp-8+arg_8], rbx
0x1800224d1  mov     [rsp-8+arg_18], rsi
0x1800224d6  push    rbp
0x1800224d7  push    rdi
0x1800224d8  push    r13
0x1800224da  push    r14
0x1800224dc  push    r15
0x1800224de  lea     rbp, [rsp-760h]
0x1800224e6  sub     rsp, 860h
0x1800224ed  mov     rax, cs:__security_cookie
0x1800224f4  xor     rax, rsp
0x1800224f7  mov     [rbp+780h+var_30], rax
0x1800224fe  mov     rsi, r8
0x180022501  mov     rdi, rcx
0x180022504  mov     [rsp+880h+var_838], r8
0x180022509  xor     ebx, ebx
0x18002250b  mov     r15d, [rdx+18h]
0x18002250f  mov     [rsp+880h+var_850], rbx
0x180022514  lea     rdx, [rcx+3C0h]
0x18002251b  lea     rcx, [rsp+880h+var_840]
0x180022520  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180022525  nop
0x180022526  mov     edx, [rdi+3B8h]
0x18002252c  test    edx, edx
0x18002252e  jz      short loc_180022552
0x180022530  cmp     ebx, 20h ; ' '
0x180022533  jnb     short loc_18002254C
0x180022535  lea     rcx, [rbx+rbx*2]
0x180022539  cmp     r15d, [rdi+rcx*8+0A0h]
0x180022541  jz      short loc_18002255A
0x180022543  inc     ebx
0x180022545  cmp     ebx, edx
0x180022547  jb      short loc_180022530
0x180022549  cmp     ebx, 20h ; ' '
0x18002254c  jz      loc_1800226BF
0x180022552  cmp     ebx, edx
0x180022554  jz      loc_1800226BF
0x18002255a  mov     r14d, ebx
0x18002255d  lea     rbx, [rbx+rbx*2]
0x180022561  mov     rcx, [rdi+rbx*8+0B0h]
0x180022569  test    rcx, rcx
0x18002256c  jz      short loc_1800225E5
0x18002256e  mov     [rsp+880h+var_848], 0
0x180022576  mov     rax, [rcx]
0x180022579  lea     rdx, [rsp+880h+var_848]
0x18002257e  mov     rax, [rax+18h]
0x180022582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022587  test    eax, eax
0x180022589  jns     loc_1800226B5
0x18002258f  lea     rdx, DebugErrorEvent
0x180022596  mov     rcx, cs:eaphost_Context
0x18002259d  call    cs:__imp_EtwEventEnabled
0x1800225a3  test    al, al
0x1800225a5  jz      short loc_1800225E5
0x1800225a7  mov     r9d, r15d
0x1800225aa  lea     r8, aEap3hostProces; " Eap3Host process for the author id: %d"...
0x1800225b1  mov     edx, 800h; unsigned __int64
0x1800225b6  lea     rcx, [rsp+880h+var_830]; char *
0x1800225bb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800225c0  test    eax, eax
0x1800225c2  js      short loc_1800225E5
0x1800225c4  test    cs:byte_18004AF81, 8
0x1800225cb  jz      short loc_1800225E5
0x1800225cd  lea     r8, [rsp+880h+var_830]
0x1800225d2  lea     rdx, DebugErrorEvent
0x1800225d9  lea     rcx, eaphost_Context
0x1800225e0  call    McTemplateU0s_EtwEventWriteTransfer
0x1800225e5  lea     r13, WPP_GLOBAL_Control
0x1800225ec  mov     r15b, 4
0x1800225ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225f6  cmp     rcx, r13
0x1800225f9  jz      short loc_180022616
0x1800225fb  test    [rcx+1Ch], r15b
0x1800225ff  jz      short loc_180022616
0x180022601  mov     edx, 0Ch
0x180022606  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x18002260d  mov     rcx, [rcx+10h]
0x180022611  call    WPP_SF_
0x180022616  lea     rax, [rdi+0A8h]
0x18002261d  lea     rax, [rax+rbx*8]
0x180022621  mov     [rsp+880h+ppv], rax; ppv
0x180022626  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18002262d  xor     r8d, r8d; pvReserved
0x180022630  mov     edx, 10004h; dwClsContext
0x180022635  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x18002263c  call    cs:__imp_CoGetClassObject
0x180022642  test    eax, eax
0x180022644  js      loc_180022742
0x18002264a  lea     rax, [r14+r14*2]
0x18002264e  mov     rcx, [rdi+rax*8+0A8h]
0x180022656  mov     rax, [rcx]
0x180022659  lea     r9, [rsp+880h+var_850]
0x18002265e  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x180022665  xor     edx, edx
0x180022667  mov     rax, [rax+18h]
0x18002266b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022670  test    eax, eax
0x180022672  js      loc_180022724
0x180022678  mov     rax, [rsp+880h+var_850]
0x18002267d  mov     [rsp+880h+var_850], 0
0x180022686  mov     [rdi+rbx*8+0B0h], rax
0x18002268e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022695  cmp     rcx, r13
0x180022698  jz      short loc_1800226B5
0x18002269a  test    [rcx+1Ch], r15b
0x18002269e  jz      short loc_1800226B5
0x1800226a0  mov     edx, 0Eh
0x1800226a5  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x1800226ac  mov     rcx, [rcx+10h]
0x1800226b0  call    WPP_SF_
0x1800226b5  mov     rdx, [rdi+rbx*8+0B0h]
0x1800226bd  jmp     short loc_1800226C1
0x1800226bf  xor     edx, edx
0x1800226c1  mov     rcx, [rsi]
0x1800226c4  mov     rax, [rcx]
0x1800226c7  mov     rax, [rax+70h]
0x1800226cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226d0  nop
0x1800226d1  mov     rcx, [rsp+880h+var_840]
0x1800226d6  add     rcx, 10h; lpCriticalSection
0x1800226da  call    cs:__imp_LeaveCriticalSection
0x1800226e0  nop
0x1800226e1  lea     rcx, [rsp+880h+var_850]
0x1800226e6  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800226eb  nop
0x1800226ec  mov     rcx, [rsi]; this
0x1800226ef  test    rcx, rcx
0x1800226f2  jz      short loc_1800226F9
0x1800226f4  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x1800226f9  mov     rcx, [rbp+780h+var_30]
0x180022700  xor     rcx, rsp; StackCookie
0x180022703  call    __security_check_cookie
0x180022708  lea     r11, [rsp+880h+var_20]
0x180022710  mov     rbx, [r11+38h]
0x180022714  mov     rsi, [r11+48h]
0x180022718  mov     rsp, r11
0x18002271b  pop     r15
0x18002271d  pop     r14
0x18002271f  pop     r13
0x180022721  pop     rdi
0x180022722  pop     rbp
0x180022723  retn
0x180022724  call    cs:__imp_GetLastError
0x18002272a  nop
0x18002272b  mov     r8d, eax; int
0x18002272e  lea     rdx, aComError; "COM Error"
0x180022735  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x18002273c  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180022742  mov     rcx, cs:WPP_GLOBAL_Control
0x180022749  cmp     rcx, r13
0x18002274c  jz      short loc_180022769
0x18002274e  test    [rcx+1Ch], r15b
0x180022752  jz      short loc_180022769
0x180022754  mov     edx, 0Dh
0x180022759  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180022760  mov     rcx, [rcx+10h]
0x180022764  call    WPP_SF_
0x180022769  call    cs:__imp_GetLastError
0x18002276f  mov     r8d, eax; int
0x180022772  lea     rdx, aComError; "COM Error"
0x180022779  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180022780  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
