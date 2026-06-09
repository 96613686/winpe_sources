# ConnectToPNRPNode(void *)

- ea: `0x140026270`
- end: `0x14002673d`
- name: `?ConnectToPNRPNode@@YAKPEAX@Z`
- size: `1229`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x140026270`
- `0x14002c0a4`
- `0x140034ce4`
- `0x140038c7c`
- `0x140039060`
- `0x14003fbc4`
- `0x140040220`
- `0x140040390`
- `0x140040a30`
- `0x140041704`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14002671b`
- `KERNEL32!HeapFree` at `0x14002671b`
- `KERNEL32!GetProcessHeap` at `0x1400265b0`
- `KERNEL32!GetProcessHeap` at `0x140026707`
- `KERNEL32!GetProcessHeap` at `0x1400265b0`
- `KERNEL32!GetProcessHeap` at `0x140026707`
- `KERNEL32!HeapAlloc` at `0x1400265c8`
- `KERNEL32!HeapAlloc` at `0x1400265c8`
- `USER32!PostMessageW` at `0x14002634f`
- `USER32!PostMessageW` at `0x14002634f`
- `msvcrt!_time64` at `0x140026541`
- `msvcrt!_time64` at `0x140026541`
- `ole32!CoUninitialize` at `0x140026383`
- `ole32!CoUninitialize` at `0x140026383`
- `ole32!CoInitialize` at `0x1400263d9`
- `ole32!CoInitialize` at `0x1400263d9`
- `OLEAUT32!__imp_SysAllocString` at `0x140026510`
- `OLEAUT32!__imp_SysAllocString` at `0x140026622`
- `OLEAUT32!__imp_SysAllocString` at `0x140026510`
- `OLEAUT32!__imp_SysAllocString` at `0x140026622`
- `OLEAUT32!__imp_SysFreeString` at `0x140026363`
- `OLEAUT32!__imp_SysFreeString` at `0x140026377`
- `OLEAUT32!__imp_SysFreeString` at `0x140026500`
- `OLEAUT32!__imp_SysFreeString` at `0x1400266ee`
- `OLEAUT32!__imp_SysFreeString` at `0x140026363`
- `OLEAUT32!__imp_SysFreeString` at `0x140026377`
- `OLEAUT32!__imp_SysFreeString` at `0x140026500`
- `OLEAUT32!__imp_SysFreeString` at `0x1400266ee`
- `OLEAUT32!__imp_SysStringLen` at `0x1400264a9`
- `OLEAUT32!__imp_SysStringLen` at `0x1400264a9`

## string_xrefs

- `0x140026323`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140026401`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140026484`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002667e`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x1400266ca`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConnectToPNRPNode(CRATicket *Parameter)
{
  CEventLogger *v2; // rcx
  OLECHAR *v3; // rsi
  BSTR v4; // rdi
  int v5; // ebx
  LPARAM v6; // r9
  UINT v7; // edx
  HRESULT v9; // eax
  CEventLogger *v10; // rcx
  unsigned int v11; // r9d
  signed int UserPassword; // eax
  CEventLogger *v13; // rcx
  CEventLogger *v14; // rcx
  CEventLogger *v15; // rcx
  __time64_t v16; // r14
  unsigned int v17; // edx
  HANDLE ProcessHeap; // rax
  CEventLogger *v19; // rcx
  unsigned __int16 **v20; // r15
  int v21; // eax
  CEventLogger *v22; // rcx
  unsigned __int16 *v23; // rax
  unsigned int v24; // r9d
  signed int EncryptedDataAsBSTR; // eax
  CEventLogger *v26; // rcx
  __int64 i; // r14
  OLECHAR *v28; // rcx
  HANDLE v29; // rax
  unsigned int v30; // [rsp+28h] [rbp-D8h]
  BSTR pbstr; // [rsp+30h] [rbp-D0h] BYREF
  __time64_t Time; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int8 v33[16]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v35[6]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v36[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+A0h] [rbp-60h]
  OLECHAR psz[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v39; // [rsp+C8h] [rbp-38h]

  memset_0(psz, 0, 0x800u);
  v3 = 0;
  v4 = 0;
  pbstr = 0;
  Time = 0;
  *(_OWORD *)v33 = 0;
  memset(v35, 0, sizeof(v35));
  *(_OWORD *)ppv = 0;
  v36[0] = 0;
  v37 = 0;
  v36[1] = 0;
  if ( !Parameter )
  {
    v5 = -2147467261;
    CEventLogger::LogError(
      v2,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x13A7u,
      L"ConnectToPNRPNode",
      0x80004003);
LABEL_3:
    v6 = 1;
    v7 = 32792;
    goto LABEL_4;
  }
  v9 = CoInitialize(0);
  v5 = v9;
  if ( v9 < 0 )
  {
    v11 = 5033;
LABEL_13:
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v11,
      L"ConnectToPNRPNode",
      v9);
    goto LABEL_14;
  }
  UserPassword = CRATicket::get_UserPassword(Parameter, &pbstr, 1);
  v5 = UserPassword;
  if ( UserPassword < 0 )
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x13AEu,
      L"ConnectToPNRPNode",
      UserPassword);
    v4 = pbstr;
    goto LABEL_14;
  }
  v4 = pbstr;
  if ( SysStringLen(pbstr) < 0xC )
  {
    v5 = -2147024809;
    CEventLogger::LogError(
      v14,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x13B5u,
      L"ConnectToPNRPNode",
      0x80070057);
    goto LABEL_3;
  }
  v9 = CRATicket::put_UserPassword(Parameter, v4);
  v5 = v9;
  if ( v9 < 0 )
  {
    v11 = 5052;
    goto LABEL_13;
  }
  *(_QWORD *)psz = *(_QWORD *)v4;
  v39 = *((_DWORD *)v4 + 2);
  SysFreeString(v4);
  v4 = SysAllocString(psz);
  if ( !v4 )
  {
    v5 = -2147024882;
    CEventLogger::LogError(
      v15,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x13C4u,
      L"ConnectToPNRPNode",
      0x8007000E);
    goto LABEL_3;
  }
  _time64(&Time);
  v16 = Time / 3600;
  v9 = CXMLStrList::Initialize(
         ppv,
         (unsigned __int16 *)((unsigned __int128)(Time * (__int128)0x48D159E26AF37C05LL) >> 64));
  v5 = v9;
  if ( v9 < 0 )
  {
    v11 = 5065;
    goto LABEL_13;
  }
  v9 = CPNRPResolver::Initialize((CPNRPResolver *)v36, v17, *((HINSTANCE *)_AtlModule + 78));
  v5 = v9;
  if ( v9 < 0 )
  {
    v11 = 5069;
    goto LABEL_13;
  }
  ProcessHeap = GetProcessHeap();
  v20 = (unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, 0x18u);
  if ( !v20 )
  {
    v5 = -2147024882;
    CEventLogger::LogError(
      v19,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x13CFu,
      L"ConnectToPNRPNode",
      0x8007000E);
    goto LABEL_3;
  }
  v21 = StringCchPrintfW(psz, 0x400u, L"%s%d", v4, v16);
  v5 = v21;
  if ( v21 < 0 )
  {
    v24 = 5082;
LABEL_39:
    v30 = v21;
    goto LABEL_40;
  }
  v23 = SysAllocString(psz);
  v3 = v23;
  if ( v23 )
  {
    v21 = CRAEncryption::DeriveBytes((CRAEncryption *)v35, v23, v33, 0x10u);
    v5 = v21;
    if ( v21 >= 0 )
    {
      EncryptedDataAsBSTR = GetEncryptedDataAsBSTR(0x10u, v33, v20);
      v5 = EncryptedDataAsBSTR;
      if ( EncryptedDataAsBSTR < 0 )
      {
        CEventLogger::LogError(
          v26,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x13E8u,
          L"ConnectToPNRPNode",
          EncryptedDataAsBSTR);
      }
      else
      {
        v5 = -2147467263;
        CEventLogger::LogError(
          v26,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x13ECu,
          L"ConnectToPNRPNode",
          0x80004001);
      }
      goto LABEL_41;
    }
    v24 = 5091;
    goto LABEL_39;
  }
  v5 = -2147024882;
  v30 = -2147024882;
  v24 = 5086;
LABEL_40:
  CEventLogger::LogError(
    v22,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    v24,
    L"ConnectToPNRPNode",
    v30);
LABEL_41:
  for ( i = 0; i != 3; ++i )
  {
    v28 = v20[i];
    if ( v28 )
    {
      SysFreeString(v28);
      v20[i] = 0;
    }
  }
  v29 = GetProcessHeap();
  HeapFree(v29, 0, v20);
  if ( v5 >= 0 )
  {
    v6 = 0;
    v7 = 32797;
    goto LABEL_4;
  }
LABEL_14:
  if ( v5 != -2147024844 )
    goto LABEL_3;
  ShowErrorMessage(0x214u, 0x28Au, *((HWND *)_AtlModule + 10), 0, (unsigned __int16 *)0xFFFE, 0);
  v6 = 0;
  v7 = 16;
LABEL_4:
  PostMessageW(*((HWND *)_AtlModule + 10), v7, 0, v6);
  if ( v3 )
    SysFreeString(v3);
  if ( v4 )
    SysFreeString(v4);
  CoUninitialize();
  if ( ppv[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
  CRAEncryption::~CRAEncryption((CRAEncryption *)v35);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140026270  push    rbp
0x140026272  push    rbx
0x140026273  push    rsi
0x140026274  push    rdi
0x140026275  push    r12
0x140026277  push    r13
0x140026279  push    r14
0x14002627b  push    r15
0x14002627d  lea     rbp, [rsp-7D8h]
0x140026285  sub     rsp, 8D8h
0x14002628c  mov     rax, cs:__security_cookie
0x140026293  xor     rax, rsp
0x140026296  mov     [rbp+810h+var_50], rax
0x14002629d  mov     r14, rcx
0x1400262a0  xor     edx, edx; Val
0x1400262a2  mov     r8d, 800h; Size
0x1400262a8  lea     rcx, [rbp+810h+psz]; void *
0x1400262ac  call    memset_0
0x1400262b1  xor     r13d, r13d
0x1400262b4  mov     esi, r13d
0x1400262b7  mov     edi, r13d
0x1400262ba  mov     [rsp+910h+pbstr], r13
0x1400262bf  mov     [rsp+910h+Time], r13
0x1400262c4  xorps   xmm0, xmm0
0x1400262c7  movups  xmmword ptr [rsp+910h+var_8D0], xmm0
0x1400262cc  mov     [rsp+910h+var_8B0], r13
0x1400262d1  mov     [rsp+910h+var_8A8], r13
0x1400262d6  mov     [rsp+910h+var_8A0], r13
0x1400262db  mov     [rsp+910h+var_898], r13
0x1400262e0  mov     [rbp+810h+var_890], r13
0x1400262e4  mov     [rbp+810h+var_888], r13
0x1400262e8  movdqu  xmmword ptr [rsp+910h+ppv], xmm0
0x1400262ee  mov     [rbp+810h+var_880], r13
0x1400262f2  movdqu  [rbp+810h+var_870], xmm0
0x1400262f7  mov     [rbp+810h+var_878], r13
0x1400262fb  test    r14, r14
0x1400262fe  jnz     loc_1400263D7
0x140026304  mov     ebx, 80004003h
0x140026309  mov     [rsp+910h+var_8E8], 80004003h; unsigned int
0x140026311  mov     r9d, 13A7h; unsigned int
0x140026317  lea     rax, aConnecttopnrpn; "ConnectToPNRPNode"
0x14002631e  mov     [rsp+910h+var_8F0], rax; unsigned __int16 *
0x140026323  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002632a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140026331  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140026336  mov     r9d, 1; lParam
0x14002633c  mov     edx, 8018h; Msg
0x140026341  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140026348  xor     r8d, r8d; wParam
0x14002634b  mov     rcx, [rcx+50h]; hWnd
0x14002634f  call    cs:__imp_PostMessageW
0x140026356  nop     dword ptr [rax+rax+00h]
0x14002635b  test    rsi, rsi
0x14002635e  jz      short loc_14002636F
0x140026360  mov     rcx, rsi; bstrString
0x140026363  call    cs:__imp_SysFreeString
0x14002636a  nop     dword ptr [rax+rax+00h]
0x14002636f  test    rdi, rdi
0x140026372  jz      short loc_140026383
0x140026374  mov     rcx, rdi; bstrString
0x140026377  call    cs:__imp_SysFreeString
0x14002637e  nop     dword ptr [rax+rax+00h]
0x140026383  call    cs:__imp_CoUninitialize
0x14002638a  nop     dword ptr [rax+rax+00h]
0x14002638f  nop
0x140026390  mov     rcx, [rsp+910h+ppv]
0x140026395  test    rcx, rcx
0x140026398  jz      short loc_1400263A7
0x14002639a  mov     rax, [rcx]
0x14002639d  mov     rax, [rax+10h]
0x1400263a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400263a6  nop
0x1400263a7  lea     rcx, [rsp+910h+var_8B0]; this
0x1400263ac  call    ??1CRAEncryption@@QEAA@XZ; CRAEncryption::~CRAEncryption(void)
0x1400263b1  mov     eax, ebx
0x1400263b3  mov     rcx, [rbp+810h+var_50]
0x1400263ba  xor     rcx, rsp; StackCookie
0x1400263bd  call    __security_check_cookie
0x1400263c2  add     rsp, 8D8h
0x1400263c9  pop     r15
0x1400263cb  pop     r14
0x1400263cd  pop     r13
0x1400263cf  pop     r12
0x1400263d1  pop     rdi
0x1400263d2  pop     rsi
0x1400263d3  pop     rbx
0x1400263d4  pop     rbp
0x1400263d5  retn
0x1400263d7  xor     ecx, ecx; pvReserved
0x1400263d9  call    cs:__imp_CoInitialize
0x1400263e0  nop     dword ptr [rax+rax+00h]
0x1400263e5  mov     ebx, eax
0x1400263e7  test    eax, eax
0x1400263e9  jns     short loc_140026455
0x1400263eb  mov     r9d, 13A9h; unsigned int
0x1400263f1  mov     [rsp+910h+var_8E8], eax; unsigned int
0x1400263f5  lea     rax, aConnecttopnrpn; "ConnectToPNRPNode"
0x1400263fc  mov     [rsp+910h+var_8F0], rax; unsigned __int16 *
0x140026401  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140026408  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002640f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140026414  cmp     ebx, 80070034h
0x14002641a  jnz     loc_140026336
0x140026420  mov     [rsp+910h+var_8E8], r13d; int
0x140026425  mov     [rsp+910h+var_8F0], 0FFFEh; unsigned __int16 *
0x14002642e  xor     r9d, r9d; int
0x140026431  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140026438  mov     r8, [r8+50h]; HWND
0x14002643c  mov     edx, 28Ah; int
0x140026441  lea     ecx, [rdx-76h]; int
0x140026444  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x140026449  xor     r9d, r9d
0x14002644c  lea     edx, [r9+10h]
0x140026450  jmp     loc_140026341
0x140026455  mov     r8d, 1; int
0x14002645b  lea     rdx, [rsp+910h+pbstr]; unsigned __int16 **
0x140026460  mov     rcx, r14; this
0x140026463  call    ?get_UserPassword@CRATicket@@QEAAJPEAPEAGH@Z; CRATicket::get_UserPassword(ushort * *,int)
0x140026468  mov     ebx, eax
0x14002646a  test    eax, eax
0x14002646c  jns     short loc_1400264A1
0x14002646e  mov     [rsp+910h+var_8E8], eax; unsigned int
0x140026472  lea     rax, aConnecttopnrpn; "ConnectToPNRPNode"
0x140026479  mov     [rsp+910h+var_8F0], rax; unsigned __int16 *
0x14002647e  mov     r9d, 13AEh; unsigned int
0x140026484  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002648b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140026492  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140026497  mov     rdi, [rsp+910h+pbstr]
0x14002649c  jmp     loc_140026414
0x1400264a1  mov     rdi, [rsp+910h+pbstr]
0x1400264a6  mov     rcx, rdi; pbstr
0x1400264a9  call    cs:__imp_SysStringLen
0x1400264b0  nop     dword ptr [rax+rax+00h]
0x1400264b5  cmp     eax, 0Ch
0x1400264b8  jnb     short loc_1400264D2
0x1400264ba  mov     ebx, 80070057h
0x1400264bf  mov     [rsp+910h+var_8E8], 80070057h
0x1400264c7  mov     r9d, 13B5h
0x1400264cd  jmp     loc_140026317
0x1400264d2  mov     rdx, rdi; unsigned __int16 *
0x1400264d5  mov     rcx, r14; this
0x1400264d8  call    ?put_UserPassword@CRATicket@@QEAAJPEAG@Z; CRATicket::put_UserPassword(ushort *)
0x1400264dd  mov     ebx, eax
0x1400264df  test    eax, eax
0x1400264e1  jns     short loc_1400264EE
0x1400264e3  mov     r9d, 13BCh
0x1400264e9  jmp     loc_1400263F1
0x1400264ee  movsd   xmm0, qword ptr [rdi]
0x1400264f2  movsd   qword ptr [rbp+810h+psz], xmm0
0x1400264f7  mov     eax, [rdi+8]
0x1400264fa  mov     [rbp+810h+var_848], eax
0x1400264fd  mov     rcx, rdi; bstrString
0x140026500  call    cs:__imp_SysFreeString
0x140026507  nop     dword ptr [rax+rax+00h]
0x14002650c  lea     rcx, [rbp+810h+psz]; psz
0x140026510  call    cs:__imp_SysAllocString
0x140026517  nop     dword ptr [rax+rax+00h]
0x14002651c  mov     rdi, rax
0x14002651f  test    rax, rax
0x140026522  jnz     short loc_14002653C
0x140026524  mov     ebx, 8007000Eh
0x140026529  mov     [rsp+910h+var_8E8], 8007000Eh
0x140026531  mov     r9d, 13C4h
0x140026537  jmp     loc_140026317
0x14002653c  lea     rcx, [rsp+910h+Time]; Time
0x140026541  call    cs:__imp__time64
0x140026548  nop     dword ptr [rax+rax+00h]
0x14002654d  mov     rax, 48D159E26AF37C05h
0x140026557  imul    [rsp+910h+Time]
0x14002655c  mov     r14, rdx
0x14002655f  sar     r14, 0Ah
0x140026563  mov     rax, r14
0x140026566  shr     rax, 3Fh
0x14002656a  add     r14, rax
0x14002656d  lea     rcx, [rsp+910h+ppv]; ppv
0x140026572  call    ?Initialize@CXMLStrList@@QEAAJPEAG@Z; CXMLStrList::Initialize(ushort *)
0x140026577  mov     ebx, eax
0x140026579  test    eax, eax
0x14002657b  jns     short loc_140026588
0x14002657d  mov     r9d, 13C9h
0x140026583  jmp     loc_1400263F1
0x140026588  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002658f  mov     r8, [r8+270h]; HINSTANCE
0x140026596  lea     rcx, [rbp+810h+var_880]; this
0x14002659a  call    ?Initialize@CPNRPResolver@@QEAAJKPEAUHINSTANCE__@@@Z; CPNRPResolver::Initialize(ulong,HINSTANCE__ *)
0x14002659f  mov     ebx, eax
0x1400265a1  test    eax, eax
0x1400265a3  jns     short loc_1400265B0
0x1400265a5  mov     r9d, 13CDh
0x1400265ab  jmp     loc_1400263F1
0x1400265b0  call    cs:__imp_GetProcessHeap
0x1400265b7  nop     dword ptr [rax+rax+00h]
0x1400265bc  mov     rcx, rax; hHeap
0x1400265bf  mov     edx, 8; dwFlags
0x1400265c4  lea     r8d, [rdx+10h]; dwBytes
0x1400265c8  call    cs:__imp_HeapAlloc
0x1400265cf  nop     dword ptr [rax+rax+00h]
0x1400265d4  mov     r15, rax
0x1400265d7  test    rax, rax
0x1400265da  jnz     short loc_1400265F4
0x1400265dc  mov     ebx, 8007000Eh
0x1400265e1  mov     [rsp+910h+var_8E8], 8007000Eh
0x1400265e9  mov     r9d, 13CFh
0x1400265ef  jmp     loc_140026317
0x1400265f4  lea     eax, [r14+r13]
0x1400265f8  mov     dword ptr [rsp+910h+var_8F0], eax
0x1400265fc  mov     r9, rdi
0x1400265ff  lea     r8, aSD; "%s%d"
0x140026606  mov     edx, 400h; unsigned __int64
0x14002660b  lea     rcx, [rbp+810h+psz]; unsigned __int16 *
0x14002660f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140026614  mov     ebx, eax
0x140026616  test    eax, eax
0x140026618  js      loc_1400266B9
0x14002661e  lea     rcx, [rbp+810h+psz]; psz
0x140026622  call    cs:__imp_SysAllocString
0x140026629  nop     dword ptr [rax+rax+00h]
0x14002662e  mov     rsi, rax
0x140026631  test    rax, rax
0x140026634  jnz     short loc_14002664B
0x140026636  mov     ebx, 8007000Eh
0x14002663b  mov     [rsp+910h+var_8E8], 8007000Eh
0x140026643  mov     r9d, 13DEh
0x140026649  jmp     short loc_1400266C3
0x14002664b  mov     r14d, 10h
0x140026651  mov     r9d, r14d; unsigned int
0x140026654  lea     r8, [rsp+910h+var_8D0]; unsigned __int8 *
0x140026659  mov     rdx, rax; unsigned __int16 *
0x14002665c  lea     rcx, [rsp+910h+var_8B0]; this
0x140026661  call    ?DeriveBytes@CRAEncryption@@QEAAJPEAGPEAEI@Z; CRAEncryption::DeriveBytes(ushort *,uchar *,uint)
0x140026666  mov     ebx, eax
0x140026668  test    eax, eax
0x14002666a  js      short loc_1400266B1
0x14002666c  mov     r8, r15; unsigned __int16 **
0x14002666f  lea     rdx, [rsp+910h+var_8D0]; unsigned __int8 *
0x140026674  mov     ecx, r14d; unsigned int
0x140026677  call    ?GetEncryptedDataAsBSTR@@YAJKQEAEPEAPEAG@Z; GetEncryptedDataAsBSTR(ulong,uchar * const,ushort * *)
0x14002667c  mov     ebx, eax
0x14002667e  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140026685  lea     rdx, Recoverable_Error
0x14002668c  test    eax, eax
0x14002668e  js      short loc_1400266A5
0x140026690  mov     ebx, 80004001h
0x140026695  mov     [rsp+910h+var_8E8], 80004001h
0x14002669d  mov     r9d, 13ECh
0x1400266a3  jmp     short loc_1400266D1
0x1400266a5  mov     [rsp+910h+var_8E8], eax
0x1400266a9  mov     r9d, 13E8h
0x1400266af  jmp     short loc_1400266D1
0x1400266b1  mov     r9d, 13E3h
0x1400266b7  jmp     short loc_1400266BF
0x1400266b9  mov     r9d, 13DAh; unsigned int
0x1400266bf  mov     [rsp+910h+var_8E8], eax; unsigned int
0x1400266c3  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400266ca  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400266d1  lea     rax, aConnecttopnrpn; "ConnectToPNRPNode"
0x1400266d8  mov     [rsp+910h+var_8F0], rax; unsigned __int16 *
0x1400266dd  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400266e2  mov     r14, r13
0x1400266e5  mov     rcx, [r15+r14*8]; bstrString
0x1400266e9  test    rcx, rcx
0x1400266ec  jz      short loc_1400266FE
0x1400266ee  call    cs:__imp_SysFreeString
0x1400266f5  nop     dword ptr [rax+rax+00h]
0x1400266fa  mov     [r15+r14*8], r13
0x1400266fe  inc     r14
0x140026701  cmp     r14, 3
0x140026705  jnz     short loc_1400266E5
0x140026707  call    cs:__imp_GetProcessHeap
0x14002670e  nop     dword ptr [rax+rax+00h]
0x140026713  mov     rcx, rax; hHeap
0x140026716  mov     r8, r15; lpMem
0x140026719  xor     edx, edx; dwFlags
0x14002671b  call    cs:__imp_HeapFree
0x140026722  nop     dword ptr [rax+rax+00h]
0x140026727  test    ebx, ebx
0x140026729  js      loc_140026414
0x14002672f  xor     r9d, r9d
0x140026732  mov     edx, 801Dh
0x140026737  jmp     loc_140026341
```
