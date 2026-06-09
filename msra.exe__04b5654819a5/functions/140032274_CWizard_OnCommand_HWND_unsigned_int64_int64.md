# CWizard::OnCommand(HWND__ *,unsigned __int64,__int64)

- ea: `0x140032274`
- end: `0x1400328f3`
- name: `?OnCommand@CWizard@@QEAAJPEAUHWND__@@_K_J@Z`
- size: `1663`
- prototype: `__int64 __fastcall(CWizard *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140034200`

## callees

- `0x140002463`
- `0x1400044f8`
- `0x14000e8b8`
- `0x140016a34`
- `0x1400269f0`
- `0x140027ce0`
- `0x1400290c4`
- `0x14002b26c`
- `0x14002c0a4`
- `0x14002c670`
- `0x14002cb94`
- `0x1400313e4`
- `0x140032274`
- `0x140033d68`
- `0x140034ce4`
- `0x140037e7c`
- `0x1400383c8`
- `0x140038470`
- `0x14003af44`
- `0x14003c8c8`
- `0x140040220`
- `0x14004ad80`

## import_xrefs

- `USER32!SendMessageW` at `0x14003271a`
- `USER32!SendMessageW` at `0x140032740`
- `USER32!SendMessageW` at `0x140032769`
- `USER32!SendMessageW` at `0x14003280b`
- `USER32!SendMessageW` at `0x1400328af`
- `USER32!SendMessageW` at `0x14003271a`
- `USER32!SendMessageW` at `0x140032740`
- `USER32!SendMessageW` at `0x140032769`
- `USER32!SendMessageW` at `0x14003280b`
- `USER32!SendMessageW` at `0x1400328af`
- `USER32!SetDlgItemTextW` at `0x1400327cf`
- `USER32!SetDlgItemTextW` at `0x1400327cf`
- `USER32!PostMessageW` at `0x14003284d`
- `USER32!PostMessageW` at `0x14003284d`
- `USER32!GetWindowTextLengthW` at `0x14003287a`
- `USER32!GetWindowTextLengthW` at `0x14003287a`
- `USER32!GetParent` at `0x1400327f0`
- `USER32!GetParent` at `0x140032833`
- `USER32!GetParent` at `0x140032895`
- `USER32!GetParent` at `0x1400327f0`
- `USER32!GetParent` at `0x140032833`
- `USER32!GetParent` at `0x140032895`
- `OLEAUT32!__imp_SysAllocString` at `0x1400327a6`
- `OLEAUT32!__imp_SysAllocString` at `0x1400327a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400326a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400326be`
- `OLEAUT32!__imp_SysFreeString` at `0x140032795`
- `OLEAUT32!__imp_SysFreeString` at `0x1400326a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400326be`
- `OLEAUT32!__imp_SysFreeString` at `0x140032795`

## string_xrefs

- `0x14003239e`: `CWizard::OnCommand`
- `0x1400324a8`: `CWizard::OnCommand`
- `0x140032518`: `CWizard::OnCommand`

## pseudocode

```c
__int64 __fastcall CWizard::OnCommand(CWizard *this, HWND a2, unsigned __int64 a3, HWND a4)
{
  unsigned int v5; // esi
  CEventLogger *v6; // rcx
  OLECHAR *v7; // r12
  CRATicket *v10; // rdi
  __int64 v11; // r8
  signed int FileNameAsBSTR; // eax
  CEventLogger *v13; // rcx
  unsigned int v14; // r9d
  int v15; // eax
  struct CReadWriteLock *v16; // r8
  __int64 v17; // rdx
  int v18; // r14d
  int v19; // r13d
  signed int Ticket; // eax
  CEventLogger *v21; // rcx
  unsigned int v22; // r9d
  CEventLogger *v23; // rcx
  CRemoteAssistanceApp *v24; // rcx
  CRemoteAssistanceApp *v25; // rcx
  unsigned int v26; // edx
  __int64 v27; // r8
  unsigned __int64 v28; // r14
  int v29; // eax
  WPARAM v30; // rbx
  CSqmManager *v31; // rcx
  CEventLogger *v32; // rbx
  OLECHAR *v33; // rcx
  BSTR v34; // rax
  __int64 v35; // rbx
  HWND v36; // rax
  HWND v37; // rax
  int v38; // ebx
  int WindowTextLengthW; // eax
  int v40; // ecx
  unsigned int v41; // ebx
  HWND Parent; // rax
  int v44; // [rsp+20h] [rbp-E0h]
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v46; // [rsp+48h] [rbp-B8h] BYREF
  CRATicket *v47; // [rsp+50h] [rbp-B0h]
  OLECHAR lParam[1024]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = 0;
  v6 = _AtlModule;
  v7 = 0;
  bstrString = 0;
  v46 = 0;
  v10 = (CRATicket *)*((_QWORD *)_AtlModule + 104);
  *((_QWORD *)this + 1) = a2;
  v47 = v10;
  if ( (unsigned __int16)a3 <= 0x424u )
  {
    if ( (unsigned __int16)a3 != 1060 )
    {
      switch ( (unsigned __int16)a3 )
      {
        case 0xF7u:
          CSqmManager::RecordUIUsage(v6, 0xF7u);
          v26 = 2013;
          break;
        case 0xF8u:
          CSqmManager::RecordUIUsage(v6, 0xF8u);
          if ( (unsigned int)CRemoteAssistanceApp::CanUserBeNovice(v25, 0, 1, *((HWND *)this + 1)) == 1 )
            v26 = 2012;
          else
            v26 = (unsigned int)TakeLock(1) != 0 ? 2005 : 107;
          break;
        case 0x11Eu:
          v18 = 0;
          CSqmManager::RecordUIUsage(v6, 0x11Eu);
          v19 = -2147467259;
          Ticket = CreatePassword((CEventLogger *)0xC, &v46);
          v7 = v46;
          v5 = Ticket;
          if ( Ticket >= 0 )
          {
            Ticket = CRATicket::put_UserPassword(v47, v46);
            v5 = Ticket;
            if ( Ticket >= 0 )
            {
              v18 = TakeLock(1);
              if ( !v18 )
              {
                v19 = -2147483099;
                CEventLogger::LogError(
                  v23,
                  &Recoverable_Error,
                  L"base\\diagnosis\\ra\\ui\\wizard.cpp",
                  0x156u,
                  L"CWizard::OnCommand",
                  0);
                v5 = -2147467259;
                goto LABEL_27;
              }
              CSqmManager::StartTimer((CEventLogger *)((char *)_AtlModule + 496), 1u);
              Ticket = CRATicket::CreateTicket(*((LPVOID **)_AtlModule + 104));
              v5 = Ticket;
              if ( Ticket >= 0 )
              {
                CSqmManager::StopTimer((CEventLogger *)((char *)_AtlModule + 496), 1u, 1);
                CWizard::SetCurrentPage(this, 0x7D4u);
                goto LABEL_48;
              }
              v19 = -2147483122;
              v22 = 346;
            }
            else
            {
              v22 = 331;
            }
          }
          else
          {
            v22 = 330;
          }
          CEventLogger::LogError(
            v21,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\wizard.cpp",
            v22,
            L"CWizard::OnCommand",
            Ticket);
LABEL_27:
          ShowRASpecificError(v19, a2, 1);
          CRemoteAssistanceApp::ResetTicketAndClearVC(v24);
          if ( v18 )
          {
            ReleaseLock(1);
            goto LABEL_46;
          }
LABEL_48:
          if ( v7 )
            SysFreeString(v7);
          return v5;
        case 0x11Fu:
          CSqmManager::RecordUIUsage(v6, 0x11Fu);
          FileNameAsBSTR = GetFileNameAsBSTR(L"msrcincident", a2, v11, 2u, 0, 0x22Bu, &bstrString);
          v5 = FileNameAsBSTR;
          if ( FileNameAsBSTR < 0 )
          {
            v14 = 364;
LABEL_11:
            CEventLogger::LogError(
              v13,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\ui\\wizard.cpp",
              v14,
              L"CWizard::OnCommand",
              FileNameAsBSTR);
            goto LABEL_46;
          }
          v15 = CreatePassword((CEventLogger *)0xC, &v46);
          v7 = v46;
          v5 = v15;
          if ( v15 < 0 || CRATicket::put_UserPassword(v10, v46) < 0 )
          {
            ShowErrorMessage(0x213u, 0x28Au, a2, 0, (unsigned __int16 *)0xFFFE, 0);
            goto LABEL_46;
          }
          FileNameAsBSTR = EscalateAsFile(bstrString, v10, v16, a2, v44);
          v5 = FileNameAsBSTR;
          if ( FileNameAsBSTR < 0 )
          {
            v14 = 387;
            goto LABEL_11;
          }
          v17 = 111;
          goto LABEL_45;
        case 0x41Au:
          CSqmManager::RecordUIUsage(v6, 0x41Au);
          *((_DWORD *)_AtlModule + 251) = 1;
          ReleaseLock(1);
          CWizard::CloseDownWizard(this, 0xFFFFFFFFLL, 9);
          return v5;
        default:
          goto LABEL_46;
      }
LABEL_33:
      CWizard::SetCurrentPage(this, v26);
      return v5;
    }
    CSqmManager::RecordUIUsage(v6, 0x424u);
    *((_DWORD *)this + 9) = 1;
LABEL_36:
    v26 = 2010;
    *(_DWORD *)(*((_QWORD *)_AtlModule + 104) + 136LL) = 7;
    goto LABEL_33;
  }
  switch ( (unsigned __int16)a3 )
  {
    case 0x42Bu:
      if ( WORD1(a3) == 768 )
      {
        v38 = 17 - (*((_DWORD *)v6 + 211) != 0);
        WindowTextLengthW = GetWindowTextLengthW(a4);
        v40 = v38 | 2;
        if ( !WindowTextLengthW )
          v40 = v38;
        v41 = v40;
        Parent = GetParent(a2);
        SendMessageW(Parent, 0x470u, 0, v41);
      }
      break;
    case 0x42Cu:
      v28 = a3 >> 16;
      if ( (unsigned __int16)(WORD1(a3) - 1) <= 1u )
      {
        memset_0(lParam, 0, sizeof(lParam));
        v29 = SendMessageW(a4, 0x188u, 0, 0);
        if ( v29 != -1 )
        {
          v30 = v29;
          if ( (unsigned int)SendMessageW(a4, 0x18Au, v29, 0) - 1 <= 0x3FE )
          {
            if ( (int)SendMessageW(a4, 0x189u, v30, (LPARAM)lParam) > 0 )
            {
              v32 = _AtlModule;
              v33 = (OLECHAR *)*((_QWORD *)_AtlModule + 82);
              if ( lParam != v33 )
              {
                SysFreeString(v33);
                v34 = SysAllocString(lParam);
                *((_QWORD *)v32 + 82) = v34;
                if ( !v34 )
                  ATL::AtlThrowImpl(-2147024882);
              }
              SetDlgItemTextW(a2, 1067, lParam);
              v35 = -(__int64)(*((_DWORD *)_AtlModule + 211) != 0);
              v36 = GetParent(a2);
              SendMessageW(v36, 0x470u, 0, v35 + 19);
            }
            if ( (_WORD)v28 == 2 )
            {
              CSqmManager::RecordUIUsage(v31, 0x42Cu);
              v37 = GetParent(a2);
              PostMessageW(v37, 0x471u, 1u, 0);
            }
          }
        }
      }
      break;
    case 0x42Du:
      CSqmManager::RecordUIUsage(v6, 0x42Du);
      *((_DWORD *)this + 9) = 0;
      goto LABEL_36;
    case 0x42Eu:
      CSqmManager::RecordUIUsage(v6, 0x42Eu);
      FileNameAsBSTR = GetFileNameAsBSTR(L"msrcIncident", a2, v27, 0x1000u, 1, 0, &bstrString);
      v5 = FileNameAsBSTR;
      if ( FileNameAsBSTR < 0 )
      {
        v14 = 300;
        goto LABEL_11;
      }
      if ( (int)CRATicket::LoadRATicket(*((OLECHAR ***)_AtlModule + 104), bstrString) < 0 )
      {
LABEL_46:
        if ( bstrString )
          SysFreeString(bstrString);
        goto LABEL_48;
      }
      v17 = 112;
LABEL_45:
      CWizard::CloseDownWizard(this, v17, 1);
      goto LABEL_46;
    default:
      goto LABEL_46;
  }
  return v5;
}

```

## disassembly

```asm
0x140032274  mov     [rsp-8+arg_10], rbx
0x140032279  push    rbp
0x14003227a  push    rsi
0x14003227b  push    rdi
0x14003227c  push    r12
0x14003227e  push    r13
0x140032280  push    r14
0x140032282  push    r15
0x140032284  lea     rbp, [rsp-770h]
0x14003228c  sub     rsp, 870h
0x140032293  mov     rax, cs:__security_cookie
0x14003229a  xor     rax, rsp
0x14003229d  mov     [rbp+7A0h+var_40], rax
0x1400322a4  mov     rbx, rcx
0x1400322a7  xor     esi, esi
0x1400322a9  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; this
0x1400322b0  xor     r12d, r12d
0x1400322b3  mov     r15, rdx
0x1400322b6  mov     [rsp+8A0h+bstrString], rsi
0x1400322bb  mov     eax, 424h
0x1400322c0  mov     [rsp+8A0h+var_858], r12
0x1400322c5  mov     r13, r9
0x1400322c8  mov     r14, r8
0x1400322cb  mov     rdi, [rcx+340h]
0x1400322d2  mov     [rbx+8], rdx
0x1400322d6  movzx   edx, r8w
0x1400322da  mov     [rsp+8A0h+var_850], rdi
0x1400322df  cmp     edx, eax
0x1400322e1  ja      loc_140032606
0x1400322e7  jz      loc_1400325D9
0x1400322ed  mov     eax, 0F7h
0x1400322f2  sub     edx, eax
0x1400322f4  jz      loc_1400325CB
0x1400322fa  sub     edx, 1
0x1400322fd  jz      loc_140032582
0x140032303  sub     edx, 26h ; '&'
0x140032306  jz      loc_140032439
0x14003230c  sub     edx, 1
0x14003230f  jz      short loc_140032352
0x140032311  cmp     edx, 2FBh
0x140032317  jnz     loc_14003269C
0x14003231d  mov     edx, 41Ah; unsigned int
0x140032322  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140032327  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14003232e  lea     edi, [rsi+1]
0x140032331  mov     ecx, edi; int
0x140032333  mov     [rax+3ECh], edi
0x140032339  call    ?ReleaseLock@@YAXH@Z; ReleaseLock(int)
0x14003233e  lea     r8d, [rsi+9]
0x140032342  or      edx, 0FFFFFFFFh
0x140032345  mov     rcx, rbx
0x140032348  call    ?CloseDownWizard@CWizard@@AEAAXIW4_RATYPE@@@Z; CWizard::CloseDownWizard(uint,_RATYPE)
0x14003234d  jmp     loc_1400328BB
0x140032352  mov     edx, 11Fh; unsigned int
0x140032357  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x14003235c  lea     rax, [rsp+8A0h+bstrString]
0x140032361  mov     r9d, 2; unsigned int
0x140032367  mov     [rsp+8A0h+var_870], rax; unsigned __int16 **
0x14003236c  lea     rcx, aMsrcincident_0; "msrcincident"
0x140032373  mov     [rsp+8A0h+uID], 22Bh; uID
0x14003237b  mov     rdx, r15; HWND
0x14003237e  mov     dword ptr [rsp+8A0h+var_880], esi; int
0x140032382  call    ?GetFileNameAsBSTR@@YAJPEAGPEAUHWND__@@HKHHPEAPEAG@Z; GetFileNameAsBSTR(ushort *,HWND__ *,int,ulong,int,int,ushort * *)
0x140032387  mov     esi, eax
0x140032389  test    eax, eax
0x14003238b  jns     short loc_1400323BB
0x14003238d  mov     r9d, 16Ch; unsigned int
0x140032393  mov     [rsp+8A0h+uID], eax; unsigned int
0x140032397  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x14003239e  lea     rax, aCwizardOncomma; "CWizard::OnCommand"
0x1400323a5  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400323ac  mov     [rsp+8A0h+var_880], rax; unsigned __int16 *
0x1400323b1  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400323b6  jmp     loc_14003269C
0x1400323bb  lea     rdx, [rsp+8A0h+var_858]; unsigned __int16 **
0x1400323c0  mov     ecx, 0Ch; unsigned int
0x1400323c5  call    ?CreatePassword@@YAJIPEAPEAG@Z; CreatePassword(uint,ushort * *)
0x1400323ca  mov     r12, [rsp+8A0h+var_858]
0x1400323cf  mov     esi, eax
0x1400323d1  test    eax, eax
0x1400323d3  js      short loc_140032410
0x1400323d5  mov     rdx, r12; unsigned __int16 *
0x1400323d8  mov     rcx, rdi; this
0x1400323db  call    ?put_UserPassword@CRATicket@@QEAAJPEAG@Z; CRATicket::put_UserPassword(ushort *)
0x1400323e0  test    eax, eax
0x1400323e2  js      short loc_140032410
0x1400323e4  mov     rcx, [rsp+8A0h+bstrString]; unsigned __int16 *
0x1400323e9  mov     r9, r15; HWND
0x1400323ec  mov     rdx, rdi; this
0x1400323ef  call    ?EscalateAsFile@@YAJPEAGPEAVCRATicket@@PEAVCReadWriteLock@@PEAUHWND__@@H@Z; EscalateAsFile(ushort *,CRATicket *,CReadWriteLock *,HWND__ *,int)
0x1400323f4  mov     esi, eax
0x1400323f6  test    eax, eax
0x1400323f8  jns     short loc_140032402
0x1400323fa  mov     r9d, 183h
0x140032400  jmp     short loc_140032393
0x140032402  mov     edx, 6Fh ; 'o'
0x140032407  lea     r8d, [rdx-6Eh]
0x14003240b  jmp     loc_140032694
0x140032410  mov     edx, 28Ah; int
0x140032415  mov     [rsp+8A0h+uID], 0; int
0x14003241d  xor     r9d, r9d; int
0x140032420  mov     [rsp+8A0h+var_880], 0FFFEh; unsigned __int16 *
0x140032429  mov     r8, r15; HWND
0x14003242c  lea     ecx, [rdx-77h]; int
0x14003242f  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x140032434  jmp     loc_14003269C
0x140032439  mov     edx, 11Eh; unsigned int
0x14003243e  xor     r14d, r14d
0x140032441  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140032446  lea     rdx, [rsp+8A0h+var_858]; unsigned __int16 **
0x14003244b  mov     r13d, 80004005h
0x140032451  lea     ecx, [r14+0Ch]; unsigned int
0x140032455  call    ?CreatePassword@@YAJIPEAPEAG@Z; CreatePassword(uint,ushort * *)
0x14003245a  mov     r12, [rsp+8A0h+var_858]
0x14003245f  mov     esi, eax
0x140032461  lea     edi, [r14+1]
0x140032465  test    eax, eax
0x140032467  jns     short loc_140032474
0x140032469  mov     r9d, 14Ah
0x14003246f  jmp     loc_14003250D
0x140032474  mov     rcx, [rsp+8A0h+var_850]; this
0x140032479  mov     rdx, r12; unsigned __int16 *
0x14003247c  call    ?put_UserPassword@CRATicket@@QEAAJPEAG@Z; CRATicket::put_UserPassword(ushort *)
0x140032481  mov     esi, eax
0x140032483  test    eax, eax
0x140032485  jns     short loc_14003248F
0x140032487  mov     r9d, 14Bh
0x14003248d  jmp     short loc_14003250D
0x14003248f  mov     ecx, edi; int
0x140032491  call    ?TakeLock@@YAHH@Z; TakeLock(int)
0x140032496  mov     r14d, eax
0x140032499  test    eax, eax
0x14003249b  jnz     short loc_1400324D3
0x14003249d  mov     [rsp+8A0h+uID], eax; unsigned int
0x1400324a1  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x1400324a8  lea     rax, aCwizardOncomma; "CWizard::OnCommand"
0x1400324af  mov     r9d, 156h; unsigned int
0x1400324b5  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400324bc  mov     [rsp+8A0h+var_880], rax; unsigned __int16 *
0x1400324c1  mov     r13d, 80000225h
0x1400324c7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400324cc  mov     esi, 80004005h
0x1400324d1  jmp     short loc_140032530
0x1400324d3  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400324da  mov     edx, edi; unsigned int
0x1400324dc  add     rcx, 1F0h; this
0x1400324e3  call    ?StartTimer@CSqmManager@@QEAAXK@Z; CSqmManager::StartTimer(ulong)
0x1400324e8  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400324ef  mov     rcx, [rcx+340h]; this
0x1400324f6  call    ?CreateTicket@CRATicket@@QEAAJXZ; CRATicket::CreateTicket(void)
0x1400324fb  mov     esi, eax
0x1400324fd  test    eax, eax
0x1400324ff  jns     short loc_140032558
0x140032501  mov     r13d, 8000020Eh
0x140032507  mov     r9d, 15Ah; unsigned int
0x14003250d  mov     [rsp+8A0h+uID], eax; unsigned int
0x140032511  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x140032518  lea     rax, aCwizardOncomma; "CWizard::OnCommand"
0x14003251f  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140032526  mov     [rsp+8A0h+var_880], rax; unsigned __int16 *
0x14003252b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140032530  mov     r8d, edi; int
0x140032533  mov     rdx, r15; HWND
0x140032536  mov     ecx, r13d; int
0x140032539  call    ?ShowRASpecificError@@YAHJPEAUHWND__@@H@Z; ShowRASpecificError(long,HWND__ *,int)
0x14003253e  call    ?ResetTicketAndClearVC@CRemoteAssistanceApp@@QEAAJXZ; CRemoteAssistanceApp::ResetTicketAndClearVC(void)
0x140032543  test    r14d, r14d
0x140032546  jz      loc_1400326B2
0x14003254c  mov     ecx, edi; int
0x14003254e  call    ?ReleaseLock@@YAXH@Z; ReleaseLock(int)
0x140032553  jmp     loc_14003269C
0x140032558  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14003255f  mov     r8d, edi; int
0x140032562  add     rcx, 1F0h; this
0x140032569  mov     edx, edi; unsigned int
0x14003256b  call    ?StopTimer@CSqmManager@@QEAAKKH@Z; CSqmManager::StopTimer(ulong,int)
0x140032570  mov     edx, 7D4h; unsigned int
0x140032575  mov     rcx, rbx; this
0x140032578  call    ?SetCurrentPage@CWizard@@QEAAXI@Z; CWizard::SetCurrentPage(uint)
0x14003257d  jmp     loc_1400326B2
0x140032582  mov     edx, 0F8h; unsigned int
0x140032587  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x14003258c  mov     r9, [rbx+8]; HWND
0x140032590  mov     edi, 1
0x140032595  mov     r8d, edi; int
0x140032598  xor     edx, edx; int
0x14003259a  call    ?CanUserBeNovice@CRemoteAssistanceApp@@QEAAHHHPEAUHWND__@@@Z; CRemoteAssistanceApp::CanUserBeNovice(int,int,HWND__ *)
0x14003259f  cmp     eax, edi
0x1400325a1  jnz     short loc_1400325AA
0x1400325a3  mov     edx, 7DCh
0x1400325a8  jmp     short loc_1400325BE
0x1400325aa  mov     ecx, edi; int
0x1400325ac  call    ?TakeLock@@YAHH@Z; TakeLock(int)
0x1400325b1  neg     eax
0x1400325b3  sbb     edx, edx
0x1400325b5  and     edx, 76Ah
0x1400325bb  add     edx, 6Bh ; 'k'; unsigned int
0x1400325be  mov     rcx, rbx; this
0x1400325c1  call    ?SetCurrentPage@CWizard@@QEAAXI@Z; CWizard::SetCurrentPage(uint)
0x1400325c6  jmp     loc_1400328BB
0x1400325cb  mov     edx, eax; unsigned int
0x1400325cd  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x1400325d2  mov     edx, 7DDh
0x1400325d7  jmp     short loc_1400325BE
0x1400325d9  mov     edx, eax; unsigned int
0x1400325db  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x1400325e0  mov     dword ptr [rbx+24h], 1
0x1400325e7  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400325ee  mov     edx, 7DAh
0x1400325f3  mov     rcx, [rax+340h]
0x1400325fa  mov     dword ptr [rcx+88h], 7
0x140032604  jmp     short loc_1400325BE
0x140032606  sub     edx, 42Bh
0x14003260c  jz      loc_14003285B
0x140032612  sub     edx, 1
0x140032615  jz      loc_1400326E1
0x14003261b  sub     edx, 1
0x14003261e  jz      loc_1400326CF
0x140032624  cmp     edx, 1
0x140032627  jnz     short loc_14003269C
0x140032629  mov     edx, 42Eh; unsigned int
0x14003262e  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140032633  lea     rax, [rsp+8A0h+bstrString]
0x140032638  mov     edi, 1
0x14003263d  mov     [rsp+8A0h+var_870], rax; unsigned __int16 **
0x140032642  lea     rcx, aMsrcincident; "msrcIncident"
0x140032649  mov     [rsp+8A0h+uID], esi; uID
0x14003264d  mov     r9d, 1000h; unsigned int
0x140032653  mov     rdx, r15; HWND
0x140032656  mov     dword ptr [rsp+8A0h+var_880], edi; int
0x14003265a  call    ?GetFileNameAsBSTR@@YAJPEAGPEAUHWND__@@HKHHPEAPEAG@Z; GetFileNameAsBSTR(ushort *,HWND__ *,int,ulong,int,int,ushort * *)
0x14003265f  mov     esi, eax
0x140032661  test    eax, eax
0x140032663  jns     short loc_140032670
0x140032665  mov     r9d, 12Ch
0x14003266b  jmp     loc_140032393
0x140032670  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140032677  mov     rdx, [rsp+8A0h+bstrString]; unsigned __int16 *
0x14003267c  mov     rcx, [rcx+340h]; this
0x140032683  call    ?LoadRATicket@CRATicket@@QEAAJPEAG@Z; CRATicket::LoadRATicket(ushort *)
0x140032688  test    eax, eax
0x14003268a  js      short loc_14003269C
0x14003268c  mov     r8d, edi
0x14003268f  mov     edx, 70h ; 'p'
0x140032694  mov     rcx, rbx
0x140032697  call    ?CloseDownWizard@CWizard@@AEAAXIW4_RATYPE@@@Z; CWizard::CloseDownWizard(uint,_RATYPE)
0x14003269c  mov     rcx, [rsp+8A0h+bstrString]; bstrString
0x1400326a1  test    rcx, rcx
0x1400326a4  jz      short loc_1400326B2
0x1400326a6  call    cs:__imp_SysFreeString
0x1400326ad  nop     dword ptr [rax+rax+00h]
0x1400326b2  test    r12, r12
0x1400326b5  jz      loc_1400328BB
0x1400326bb  mov     rcx, r12; bstrString
0x1400326be  call    cs:__imp_SysFreeString
0x1400326c5  nop     dword ptr [rax+rax+00h]
0x1400326ca  jmp     loc_1400328BB
0x1400326cf  mov     edx, 42Dh; unsigned int
0x1400326d4  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x1400326d9  mov     [rbx+24h], esi
0x1400326dc  jmp     loc_1400325E7
0x1400326e1  shr     r14, 10h
0x1400326e5  mov     edi, 1
0x1400326ea  movzx   eax, r14w
0x1400326ee  sub     ax, di
0x1400326f1  cmp     ax, di
0x1400326f4  ja      loc_1400328BB
0x1400326fa  xor     edx, edx; Val
0x1400326fc  lea     rcx, [rsp+8A0h+lParam]; void *
0x140032701  mov     r8d, 800h; Size
0x140032707  call    memset_0
0x14003270c  xor     r9d, r9d; lParam
0x14003270f  xor     r8d, r8d; wParam
0x140032712  mov     edx, 188h; Msg
0x140032717  mov     rcx, r13; hWnd
0x14003271a  call    cs:__imp_SendMessageW
0x140032721  nop     dword ptr [rax+rax+00h]
0x140032726  cmp     eax, 0FFFFFFFFh
0x140032729  jz      loc_1400328BB
0x14003272f  movsxd  rbx, eax
0x140032732  xor     r9d, r9d; lParam
0x140032735  mov     r8, rbx; wParam
0x140032738  mov     edx, 18Ah; Msg
0x14003273d  mov     rcx, r13; hWnd
0x140032740  call    cs:__imp_SendMessageW
0x140032747  nop     dword ptr [rax+rax+00h]
0x14003274c  sub     eax, edi
0x14003274e  cmp     eax, 3FEh
0x140032753  ja      loc_1400328BB
0x140032759  lea     r9, [rsp+8A0h+lParam]; lParam
0x14003275e  mov     r8, rbx; wParam
0x140032761  mov     edx, 189h; Msg
0x140032766  mov     rcx, r13; hWnd
0x140032769  call    cs:__imp_SendMessageW
0x140032770  nop     dword ptr [rax+rax+00h]
0x140032775  test    eax, eax
0x140032777  jle     loc_140032817
0x14003277d  mov     rbx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140032784  lea     rax, [rsp+8A0h+lParam]
0x140032789  mov     rcx, [rbx+290h]; bstrString
  ... truncated ...
```
