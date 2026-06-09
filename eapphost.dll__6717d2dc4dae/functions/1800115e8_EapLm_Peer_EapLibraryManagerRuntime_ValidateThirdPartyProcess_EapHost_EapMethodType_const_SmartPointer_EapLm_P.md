# EapLm::Peer::EapLibraryManagerRuntime::ValidateThirdPartyProcess(EapHost::EapMethodType const &,SmartPointer<EapLm::Peer::IEapMethodRuntime>)

- ea: `0x1800115e8`
- end: `0x1800118a2`
- name: `?ValidateThirdPartyProcess@EapLibraryManagerRuntime@Peer@EapLm@@QEAAXAEBVEapMethodType@EapHost@@V?$SmartPointer@UIEapMethodRuntime@Peer@EapLm@@@@@Z`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800112d4`

## callees

- `0x180002a90`
- `0x180004988`
- `0x180004b98`
- `0x180009dc4`
- `0x180011578`
- `0x1800115e8`
- `0x180011958`
- `0x18001dcbc`
- `0x18002f93c`
- `0x180038010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800116b9`
- `ntdll!EtwEventEnabled` at `0x1800116b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011885`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011885`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800117f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800117f6`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180011758`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180011758`

## string_xrefs

- `0x18001184a`: `COM Error`
- `0x18001188e`: `COM Error`
- `0x180011851`: `Create Third Party Proxy`
- `0x180011895`: `Create Third Party Proxy`

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
          && (byte_18004E841 & 8) != 0 )
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
0x1800115e8  mov     [rsp-8+arg_8], rbx
0x1800115ed  mov     [rsp-8+arg_18], rsi
0x1800115f2  push    rbp
0x1800115f3  push    rdi
0x1800115f4  push    r13
0x1800115f6  push    r14
0x1800115f8  push    r15
0x1800115fa  lea     rbp, [rsp-760h]
0x180011602  sub     rsp, 860h
0x180011609  mov     rax, cs:__security_cookie
0x180011610  xor     rax, rsp
0x180011613  mov     [rbp+780h+var_30], rax
0x18001161a  mov     rsi, r8
0x18001161d  mov     rdi, rcx
0x180011620  mov     [rsp+880h+var_838], r8
0x180011625  xor     ebx, ebx
0x180011627  mov     r15d, [rdx+18h]
0x18001162b  mov     [rsp+880h+var_850], rbx
0x180011630  lea     rdx, [rcx+3C0h]
0x180011637  lea     rcx, [rsp+880h+var_840]
0x18001163c  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180011641  nop
0x180011642  mov     edx, [rdi+3B8h]
0x180011648  test    edx, edx
0x18001164a  jz      short loc_18001166E
0x18001164c  cmp     ebx, 20h ; ' '
0x18001164f  jnb     short loc_180011668
0x180011651  lea     rcx, [rbx+rbx*2]
0x180011655  cmp     r15d, [rdi+rcx*8+0A0h]
0x18001165d  jz      short loc_180011676
0x18001165f  inc     ebx
0x180011661  cmp     ebx, edx
0x180011663  jb      short loc_18001164C
0x180011665  cmp     ebx, 20h ; ' '
0x180011668  jz      loc_1800117DB
0x18001166e  cmp     ebx, edx
0x180011670  jz      loc_1800117DB
0x180011676  mov     r14d, ebx
0x180011679  lea     rbx, [rbx+rbx*2]
0x18001167d  mov     rcx, [rdi+rbx*8+0B0h]
0x180011685  test    rcx, rcx
0x180011688  jz      short loc_180011701
0x18001168a  mov     [rsp+880h+var_848], 0
0x180011692  mov     rax, [rcx]
0x180011695  lea     rdx, [rsp+880h+var_848]
0x18001169a  mov     rax, [rax+18h]
0x18001169e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a3  test    eax, eax
0x1800116a5  jns     loc_1800117D1
0x1800116ab  lea     rdx, DebugErrorEvent
0x1800116b2  mov     rcx, cs:eaphost_Context
0x1800116b9  call    cs:__imp_EtwEventEnabled
0x1800116bf  test    al, al
0x1800116c1  jz      short loc_180011701
0x1800116c3  mov     r9d, r15d
0x1800116c6  lea     r8, aEap3hostProces; " Eap3Host process for the author id: %d"...
0x1800116cd  mov     edx, 800h; unsigned __int64
0x1800116d2  lea     rcx, [rsp+880h+var_830]; char *
0x1800116d7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800116dc  test    eax, eax
0x1800116de  js      short loc_180011701
0x1800116e0  test    cs:byte_18004E841, 8
0x1800116e7  jz      short loc_180011701
0x1800116e9  lea     r8, [rsp+880h+var_830]
0x1800116ee  lea     rdx, DebugErrorEvent
0x1800116f5  lea     rcx, eaphost_Context
0x1800116fc  call    McTemplateU0s_EtwEventWriteTransfer
0x180011701  lea     r13, WPP_GLOBAL_Control
0x180011708  mov     r15b, 4
0x18001170b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011712  cmp     rcx, r13
0x180011715  jz      short loc_180011732
0x180011717  test    [rcx+1Ch], r15b
0x18001171b  jz      short loc_180011732
0x18001171d  mov     edx, 0Ch
0x180011722  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x180011729  mov     rcx, [rcx+10h]
0x18001172d  call    WPP_SF_
0x180011732  lea     rax, [rdi+0A8h]
0x180011739  lea     rax, [rax+rbx*8]
0x18001173d  mov     [rsp+880h+ppv], rax; ppv
0x180011742  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180011749  xor     r8d, r8d; pvReserved
0x18001174c  mov     edx, 10004h; dwClsContext
0x180011751  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x180011758  call    cs:__imp_CoGetClassObject
0x18001175e  test    eax, eax
0x180011760  js      loc_18001185E
0x180011766  lea     rax, [r14+r14*2]
0x18001176a  mov     rcx, [rdi+rax*8+0A8h]
0x180011772  mov     rax, [rcx]
0x180011775  lea     r9, [rsp+880h+var_850]
0x18001177a  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x180011781  xor     edx, edx
0x180011783  mov     rax, [rax+18h]
0x180011787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001178c  test    eax, eax
0x18001178e  js      loc_180011840
0x180011794  mov     rax, [rsp+880h+var_850]
0x180011799  mov     [rsp+880h+var_850], 0
0x1800117a2  mov     [rdi+rbx*8+0B0h], rax
0x1800117aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117b1  cmp     rcx, r13
0x1800117b4  jz      short loc_1800117D1
0x1800117b6  test    [rcx+1Ch], r15b
0x1800117ba  jz      short loc_1800117D1
0x1800117bc  mov     edx, 0Eh
0x1800117c1  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x1800117c8  mov     rcx, [rcx+10h]
0x1800117cc  call    WPP_SF_
0x1800117d1  mov     rdx, [rdi+rbx*8+0B0h]
0x1800117d9  jmp     short loc_1800117DD
0x1800117db  xor     edx, edx
0x1800117dd  mov     rcx, [rsi]
0x1800117e0  mov     rax, [rcx]
0x1800117e3  mov     rax, [rax+70h]
0x1800117e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117ec  nop
0x1800117ed  mov     rcx, [rsp+880h+var_840]
0x1800117f2  add     rcx, 10h; lpCriticalSection
0x1800117f6  call    cs:__imp_LeaveCriticalSection
0x1800117fc  nop
0x1800117fd  lea     rcx, [rsp+880h+var_850]
0x180011802  call    ?Release@?$ComPointer@UIUnknown@@@@AEAAXXZ; ComPointer<IUnknown>::Release(void)
0x180011807  nop
0x180011808  mov     rcx, [rsi]; this
0x18001180b  test    rcx, rcx
0x18001180e  jz      short loc_180011815
0x180011810  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180011815  mov     rcx, [rbp+780h+var_30]
0x18001181c  xor     rcx, rsp; StackCookie
0x18001181f  call    __security_check_cookie
0x180011824  lea     r11, [rsp+880h+var_20]
0x18001182c  mov     rbx, [r11+38h]
0x180011830  mov     rsi, [r11+48h]
0x180011834  mov     rsp, r11
0x180011837  pop     r15
0x180011839  pop     r14
0x18001183b  pop     r13
0x18001183d  pop     rdi
0x18001183e  pop     rbp
0x18001183f  retn
0x180011840  call    cs:__imp_GetLastError
0x180011846  nop
0x180011847  mov     r8d, eax; int
0x18001184a  lea     rdx, aComError; "COM Error"
0x180011851  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180011858  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18001185e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011865  cmp     rcx, r13
0x180011868  jz      short loc_180011885
0x18001186a  test    [rcx+1Ch], r15b
0x18001186e  jz      short loc_180011885
0x180011870  mov     edx, 0Dh
0x180011875  lea     r8, WPP_41872ebd2966363aea4e531fa6ff18b1_Traceguids
0x18001187c  mov     rcx, [rcx+10h]
0x180011880  call    WPP_SF_
0x180011885  call    cs:__imp_GetLastError
0x18001188b  mov     r8d, eax; int
0x18001188e  lea     rdx, aComError; "COM Error"
0x180011895  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x18001189c  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
