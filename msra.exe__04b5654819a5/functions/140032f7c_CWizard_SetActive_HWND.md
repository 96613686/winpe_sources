# CWizard::SetActive(HWND__ *)

- ea: `0x140032f7c`
- end: `0x140033d60`
- name: `?SetActive@CWizard@@AEAAIPEAUHWND__@@@Z`
- size: `3556`
- prototype: `unsigned int(CWizard *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `20`
- tags: ``

## callers

- `0x140032bf0`

## callees

- `0x140002463`
- `0x140016a34`
- `0x140029334`
- `0x14002c0a4`
- `0x14002c670`
- `0x14002cb94`
- `0x140032f7c`
- `0x140034ce4`
- `0x140035d04`
- `0x140037e7c`
- `0x1400383c8`
- `0x140038470`
- `0x14003af44`
- `0x14003fa5c`
- `0x140041998`
- `0x140041a4c`
- `0x140041cc8`
- `0x140043c34`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!QueueUserWorkItem` at `0x140033308`
- `KERNEL32!QueueUserWorkItem` at `0x1400335d0`
- `KERNEL32!QueueUserWorkItem` at `0x140033308`
- `KERNEL32!QueueUserWorkItem` at `0x1400335d0`
- `KERNEL32!CreateThread` at `0x14003353d`
- `KERNEL32!CreateThread` at `0x14003353d`
- `KERNEL32!GetModuleHandleW` at `0x14003321d`
- `KERNEL32!GetModuleHandleW` at `0x140033629`
- `KERNEL32!GetModuleHandleW` at `0x140033958`
- `KERNEL32!GetModuleHandleW` at `0x140033a7e`
- `KERNEL32!GetModuleHandleW` at `0x140033ac6`
- `KERNEL32!GetModuleHandleW` at `0x14003321d`
- `KERNEL32!GetModuleHandleW` at `0x140033629`
- `KERNEL32!GetModuleHandleW` at `0x140033958`
- `KERNEL32!GetModuleHandleW` at `0x140033a7e`
- `KERNEL32!GetModuleHandleW` at `0x140033ac6`
- `KERNEL32!LocalFree` at `0x140033d0a`
- `KERNEL32!LocalFree` at `0x140033d0a`
- `KERNEL32!CloseHandle` at `0x140033cf4`
- `KERNEL32!CloseHandle` at `0x140033cf4`
- `KERNEL32!GetLastError` at `0x14003331c`
- `KERNEL32!GetLastError` at `0x14003332c`
- `KERNEL32!GetLastError` at `0x1400335e4`
- `KERNEL32!GetLastError` at `0x1400335f4`
- `KERNEL32!GetLastError` at `0x14003331c`
- `KERNEL32!GetLastError` at `0x14003332c`
- `KERNEL32!GetLastError` at `0x1400335e4`
- `KERNEL32!GetLastError` at `0x1400335f4`
- `KERNEL32!FormatMessageW` at `0x1400339ec`
- `KERNEL32!FormatMessageW` at `0x1400339ec`
- `KERNEL32!WaitForSingleObject` at `0x1400333ae`
- `KERNEL32!WaitForSingleObject` at `0x14003369a`
- `KERNEL32!WaitForSingleObject` at `0x140033b77`
- `KERNEL32!WaitForSingleObject` at `0x140033c20`
- `KERNEL32!WaitForSingleObject` at `0x1400333ae`
- `KERNEL32!WaitForSingleObject` at `0x14003369a`
- `KERNEL32!WaitForSingleObject` at `0x140033b77`
- `KERNEL32!WaitForSingleObject` at `0x140033c20`
- `USER32!SendMessageW` at `0x1400330d3`
- `USER32!SendMessageW` at `0x14003326e`
- `USER32!SendMessageW` at `0x14003329f`
- `USER32!SendMessageW` at `0x1400334d0`
- `USER32!SendMessageW` at `0x140033519`
- `USER32!SendMessageW` at `0x1400335af`
- `USER32!SendMessageW` at `0x140033713`
- `USER32!SendMessageW` at `0x14003372c`
- `USER32!SendMessageW` at `0x1400337f8`
- `USER32!SendMessageW` at `0x140033865`
- `USER32!SendMessageW` at `0x1400338d1`
- `USER32!SendMessageW` at `0x140033a51`
- `USER32!SendMessageW` at `0x1400330d3`
- `USER32!SendMessageW` at `0x14003326e`
- `USER32!SendMessageW` at `0x14003329f`
- `USER32!SendMessageW` at `0x1400334d0`
- `USER32!SendMessageW` at `0x140033519`
- `USER32!SendMessageW` at `0x1400335af`
- `USER32!SendMessageW` at `0x140033713`
- `USER32!SendMessageW` at `0x14003372c`
- `USER32!SendMessageW` at `0x1400337f8`
- `USER32!SendMessageW` at `0x140033865`
- `USER32!SendMessageW` at `0x1400338d1`
- `USER32!SendMessageW` at `0x140033a51`
- `USER32!ShowWindow` at `0x1400332c7`
- `USER32!ShowWindow` at `0x1400332ec`
- `USER32!ShowWindow` at `0x140033401`
- `USER32!ShowWindow` at `0x140033469`
- `USER32!ShowWindow` at `0x14003348e`
- `USER32!ShowWindow` at `0x1400334b6`
- `USER32!ShowWindow` at `0x1400334fb`
- `USER32!ShowWindow` at `0x1400332c7`
- `USER32!ShowWindow` at `0x1400332ec`
- `USER32!ShowWindow` at `0x140033401`
- `USER32!ShowWindow` at `0x140033469`
- `USER32!ShowWindow` at `0x14003348e`
- `USER32!ShowWindow` at `0x1400334b6`
- `USER32!ShowWindow` at `0x1400334fb`
- `USER32!LoadStringW` at `0x14003323e`
- `USER32!LoadStringW` at `0x14003364a`
- `USER32!LoadStringW` at `0x140033979`
- `USER32!LoadStringW` at `0x140033a9f`
- `USER32!LoadStringW` at `0x140033ae7`
- `USER32!LoadStringW` at `0x14003323e`
- `USER32!LoadStringW` at `0x14003364a`
- `USER32!LoadStringW` at `0x140033979`
- `USER32!LoadStringW` at `0x140033a9f`
- `USER32!LoadStringW` at `0x140033ae7`
- `USER32!GetDlgItem` at `0x140033282`
- `USER32!GetDlgItem` at `0x1400332b3`
- `USER32!GetDlgItem` at `0x1400332db`
- `USER32!GetDlgItem` at `0x14003336b`
- `USER32!GetDlgItem` at `0x1400333cb`
- `USER32!GetDlgItem` at `0x1400333f0`
- `USER32!GetDlgItem` at `0x140033412`
- `USER32!GetDlgItem` at `0x14003343a`
- `USER32!GetDlgItem` at `0x140033455`
- `USER32!GetDlgItem` at `0x14003347d`
- `USER32!GetDlgItem` at `0x1400334a2`
- `USER32!GetDlgItem` at `0x1400334e4`
- `USER32!GetDlgItem` at `0x1400336bb`
- `USER32!GetDlgItem` at `0x1400336f6`
- `USER32!GetDlgItem` at `0x14003388d`
- `USER32!GetDlgItem` at `0x140033a0c`
- `USER32!GetDlgItem` at `0x140033a34`
- `USER32!GetDlgItem` at `0x140033282`
- `USER32!GetDlgItem` at `0x1400332b3`
- `USER32!GetDlgItem` at `0x1400332db`
- `USER32!GetDlgItem` at `0x14003336b`
- `USER32!GetDlgItem` at `0x1400333cb`
- `USER32!GetDlgItem` at `0x1400333f0`
- `USER32!GetDlgItem` at `0x140033412`
- `USER32!GetDlgItem` at `0x14003343a`
- `USER32!GetDlgItem` at `0x140033455`
- `USER32!GetDlgItem` at `0x14003347d`
- `USER32!GetDlgItem` at `0x1400334a2`
- `USER32!GetDlgItem` at `0x1400334e4`
- `USER32!GetDlgItem` at `0x1400336bb`
- `USER32!GetDlgItem` at `0x1400336f6`
- `USER32!GetDlgItem` at `0x14003388d`
- `USER32!GetDlgItem` at `0x140033a0c`
- `USER32!GetDlgItem` at `0x140033a34`
- `USER32!SetDlgItemTextW` at `0x140033674`
- `USER32!SetDlgItemTextW` at `0x140033674`
- `USER32!PostMessageW` at `0x1400330ff`
- `USER32!PostMessageW` at `0x140033a6b`
- `USER32!PostMessageW` at `0x1400330ff`
- `USER32!PostMessageW` at `0x140033a6b`
- `USER32!EnableWindow` at `0x14003337c`
- `USER32!EnableWindow` at `0x1400333dc`
- `USER32!EnableWindow` at `0x140033426`
- `USER32!EnableWindow` at `0x1400336cc`
- `USER32!EnableWindow` at `0x14003337c`
- `USER32!EnableWindow` at `0x1400333dc`
- `USER32!EnableWindow` at `0x140033426`
- `USER32!EnableWindow` at `0x1400336cc`
- `USER32!GetWindowTextLengthW` at `0x14003389c`
- `USER32!GetWindowTextLengthW` at `0x14003389c`
- `USER32!SetWindowTextW` at `0x140033a20`
- `USER32!SetWindowTextW` at `0x140033a20`
- `USER32!GetParent` at `0x1400330b9`
- `USER32!GetParent` at `0x1400330e2`
- `USER32!GetParent` at `0x1400338b7`
- `USER32!GetParent` at `0x1400330b9`
- `USER32!GetParent` at `0x1400330e2`
- `USER32!GetParent` at `0x1400338b7`
- `OLEAUT32!__imp_SysAllocString` at `0x140033938`
- `OLEAUT32!__imp_SysAllocString` at `0x140033938`
- `OLEAUT32!__imp_SysFreeString` at `0x14003380c`
- `OLEAUT32!__imp_SysFreeString` at `0x140033ccc`
- `OLEAUT32!__imp_SysFreeString` at `0x140033ce0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003380c`
- `OLEAUT32!__imp_SysFreeString` at `0x140033ccc`
- `OLEAUT32!__imp_SysFreeString` at `0x140033ce0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWizard::SetActive(CWizard *this, HWND a2)
{
  OLECHAR *v4; // r14
  unsigned int v5; // r12d
  int v6; // r13d
  CEventLogger *v7; // rcx
  const OLECHAR **v8; // r15
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rbx
  WPARAM v12; // rbx
  HWND Parent; // rax
  HWND v14; // rax
  CSqmManager *v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  CEventLogger *v22; // rcx
  unsigned int v23; // r9d
  HANDLE Thread; // r15
  int Ticket; // eax
  CSqmManager *v26; // rcx
  CEventLogger *v27; // rcx
  HMODULE ModuleHandleW; // rax
  HWND v29; // rax
  HWND v30; // rax
  HWND v31; // rax
  CEventLogger *v32; // rcx
  signed int v33; // eax
  CSqmManager *v34; // rcx
  HWND v35; // rax
  unsigned int v36; // edx
  CEventLogger *v37; // rbx
  void *v38; // rcx
  HWND v39; // rax
  HWND v40; // rax
  int v41; // edx
  HWND v42; // rax
  HWND v43; // rax
  HWND v44; // rax
  HWND v45; // rbx
  HWND v46; // rbx
  CEventLogger *v47; // rcx
  CEventLogger *v48; // rcx
  signed int LastError; // eax
  HMODULE v50; // rax
  int v51; // edx
  CEventLogger *v52; // rbx
  void *v53; // rcx
  HWND DlgItem; // rax
  HWND v55; // r15
  CEventLogger *v56; // rcx
  int v57; // ebx
  int v58; // eax
  __int64 **i; // rdx
  signed int v60; // eax
  int Name; // eax
  int v62; // ebx
  HWND v63; // rax
  int WindowTextLengthW; // eax
  int v65; // ecx
  unsigned int v66; // ebx
  HWND v67; // rax
  int v68; // eax
  int v69; // eax
  int v70; // eax
  int v71; // eax
  signed int NoviceName; // eax
  CEventLogger *v73; // rcx
  OLECHAR *v74; // rbx
  HMODULE v75; // rax
  CEventLogger *v76; // rcx
  unsigned int v77; // r9d
  HWND v78; // rax
  HWND v79; // rax
  HMODULE v80; // rax
  HMODULE v81; // rax
  __int64 v82; // rcx
  CEventLogger *v83; // rbx
  void *v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  CEventLogger *v87; // rbx
  void *v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v93; // [rsp+50h] [rbp-B0h] BYREF
  LPARAM lParam; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v95[4]; // [rsp+60h] [rbp-A0h] BYREF
  va_list Arguments[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v97[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v98; // [rsp+A0h] [rbp-60h]
  __int128 v99; // [rsp+A8h] [rbp-58h]
  int v100; // [rsp+B8h] [rbp-48h]
  unsigned int v101; // [rsp+C0h] [rbp-40h] BYREF
  int v102; // [rsp+C4h] [rbp-3Ch]
  _QWORD v103[3]; // [rsp+2A8h] [rbp+1A8h] BYREF
  WCHAR Buffer[1024]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v101 = 0;
  v102 = 1;
  v103[1] = v103;
  v103[0] = v103;
  v99 = 0;
  v100 = 0;
  memset(v97, 0, sizeof(v97));
  v98 = 0;
  v4 = 0;
  lParam = 0;
  v93 = 0;
  v5 = 0;
  v6 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  *(_QWORD *)v95 = 0;
  *(_OWORD *)Arguments = 0;
  bstrString = 0;
  v7 = _AtlModule;
  v8 = (const OLECHAR **)*((_QWORD *)_AtlModule + 104);
  *((_DWORD *)_AtlModule + 206) = -1;
  *((_DWORD *)v7 + 207) = -1;
  *((_QWORD *)this + 1) = a2;
  v9 = 0;
  while ( *(_DWORD *)&byte_140063730[12 * v9 + 4] != *(_DWORD *)this )
  {
    if ( (unsigned int)++v9 >= 0xE )
      goto LABEL_6;
  }
  *((_DWORD *)v7 + 206) = *(_DWORD *)&byte_140063730[12 * v9 + 8];
  *((_DWORD *)v7 + 207) = *(_DWORD *)&byte_140063730[12 * v9];
LABEL_6:
  if ( *((_DWORD *)v7 + 207) == -1 || (v10 = 1, *((_DWORD *)v7 + 211)) )
    v10 = 0;
  v11 = 16;
  if ( *((_DWORD *)v7 + 206) != -1 )
    v11 = 18;
  v12 = v10 | v11;
  Parent = GetParent(a2);
  SendMessageW(Parent, 0x470u, 0, v12);
  v14 = GetParent(a2);
  PostMessageW(v14, 0x48Au, v12, 22);
  *((_QWORD *)_AtlModule + 101) = a2;
  CSqmManager::RecordUIUsage(v15, *(_DWORD *)this);
  v16 = *(_DWORD *)this;
  if ( *(_DWORD *)this <= 0x7DBu )
  {
    if ( v16 != 2011 )
    {
      v17 = v16 - 108;
      if ( !v17 )
      {
        v52 = _AtlModule;
        v53 = (void *)*((_QWORD *)_AtlModule + 132);
        if ( v53 )
          WaitForSingleObject(v53, 0);
        if ( *((_DWORD *)v52 + 262) == 2 )
        {
          DlgItem = GetDlgItem(a2, 1069);
          EnableWindow(DlgItem, 0);
          *((_DWORD *)_AtlModule + 134) = 4;
        }
        goto LABEL_23;
      }
      v18 = v17 - 1893;
      if ( v18 )
      {
        v19 = v18 - 3;
        if ( !v19 )
        {
          if ( !QueueUserWorkItem(LaunchEmailThreadFunc, a2, 0x10u) )
          {
            if ( GetLastError() )
            {
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              LastError = -2147467259;
            }
            CEventLogger::LogError(
              v48,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\ui\\wizard.cpp",
              0x4BDu,
              L"CWizard::SetActive",
              LastError);
          }
          goto LABEL_23;
        }
        v20 = v19 - 2;
        if ( !v20 )
        {
          v43 = GetDlgItem(a2, 1055);
          ShowWindow(v43, 5);
          v44 = GetDlgItem(a2, 1056);
          ShowWindow(v44, 0);
          v45 = GetDlgItem(a2, 1054);
          ShowWindow(v45, 0);
          SendMessageW(v45, 0x14Bu, 0, 0);
          v46 = GetDlgItem(a2, 1079);
          ShowWindow(v46, 5);
          SendMessageW(v46, 0x40Au, 1u, 50);
          Thread = CreateThread(0, 0, GetOfferRASessionsThreadFunc, a2, 0, 0);
          if ( !Thread )
          {
            CEventLogger::LogError(
              v47,
              &Critical_Error,
              L"base\\diagnosis\\ra\\ui\\wizard.cpp",
              0x524u,
              L"CWizard::SetActive",
              0);
            ShowErrorMessage(0x213u, 0x28Au, a2, 0, (unsigned __int16 *)0xFFFE, 0);
            SendMessageW(a2, 0x471u, 5u, 0);
          }
          goto LABEL_132;
        }
        v21 = v20 - 3;
        if ( !v21 )
        {
          if ( IsEmailClientAvailable() )
          {
            v36 = 17006;
          }
          else
          {
            v35 = GetDlgItem(a2, 286);
            EnableWindow(v35, 0);
            v36 = 17005;
          }
          CSqmManager::RecordUIUsage(v34, v36);
          v37 = _AtlModule;
          v38 = (void *)*((_QWORD *)_AtlModule + 132);
          if ( v38 )
            WaitForSingleObject(v38, 0);
          if ( *((_DWORD *)v37 + 262) == 2 )
          {
            v39 = GetDlgItem(a2, 1060);
            EnableWindow(v39, 0);
            v40 = GetDlgItem(a2, 296);
            v41 = 0;
          }
          else
          {
            v42 = GetDlgItem(a2, 1060);
            EnableWindow(v42, 1);
            v40 = GetDlgItem(a2, 296);
            v41 = 1;
          }
          ShowWindow(v40, v41);
          goto LABEL_23;
        }
        if ( v21 != 1 )
        {
LABEL_23:
          Thread = 0;
LABEL_132:
          v74 = bstrString;
          goto LABEL_133;
        }
        if ( *((_DWORD *)this + 9) == 1 )
        {
          if ( !(unsigned int)TakeLock(1) )
          {
            v6 = -2147483099;
            v23 = 1224;
LABEL_22:
            CEventLogger::LogError(
              v22,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\ui\\wizard.cpp",
              v23,
              L"CWizard::SetActive",
              0);
            goto LABEL_23;
          }
          CSqmManager::StartTimer((CEventLogger *)((char *)_AtlModule + 496), 1u);
          Ticket = CRATicket::CreateTicket(*((LPVOID **)_AtlModule + 104));
          v26 = (CEventLogger *)((char *)_AtlModule + 496);
          if ( Ticket < 0 )
          {
            CSqmManager::StopTimer(v26, 1u, 1);
            v6 = -2147483122;
            CEventLogger::LogError(
              v27,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\ui\\wizard.cpp",
              0x4D1u,
              L"CWizard::SetActive",
              0x8000020E);
            goto LABEL_23;
          }
          CSqmManager::StopTimer(v26, 1u, 1);
        }
        else
        {
          ModuleHandleW = GetModuleHandleW(0);
          if ( !LoadStringW(ModuleHandleW, 0x1F7u, Buffer, 1024) )
          {
            v23 = 1250;
            goto LABEL_22;
          }
          SendMessageW(a2, 0x47Eu, 0xAu, (LPARAM)Buffer);
        }
        v29 = GetDlgItem(a2, 1083);
        SendMessageW(v29, 0x40Au, 1u, 50);
        v30 = GetDlgItem(a2, 1082);
        ShowWindow(v30, 5);
        v31 = GetDlgItem(a2, 1084);
        ShowWindow(v31, 0);
        if ( !QueueUserWorkItem(TestPNRPConnection, a2, 0x10u) )
        {
          if ( GetLastError() )
          {
            v33 = GetLastError();
            if ( v33 > 0 )
              v33 = (unsigned __int16)v33 | 0x80070000;
          }
          else
          {
            v33 = -2147467259;
          }
          CEventLogger::LogError(
            v32,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\wizard.cpp",
            0x4F8u,
            L"CWizard::SetActive",
            v33);
        }
        goto LABEL_23;
      }
      CRemoteAssistanceApp::ResetTicketAndClearVC((CRemoteAssistanceApp *)0x7DB);
      v50 = GetModuleHandleW(0);
      if ( !LoadStringW(v50, 0x2FAu, Buffer, 1024) )
      {
        v23 = 1178;
        goto LABEL_22;
      }
      v51 = 1087;
LABEL_56:
      SetDlgItemTextW(a2, v51, Buffer);
      goto LABEL_23;
    }
    v55 = GetDlgItem(a2, 1068);
    SendMessageW(v55, 0x184u, 0, 0);
    SendMessageW(v55, 0xBu, 0, 0);
    if ( (int)GetInvitationManagerLoaded((struct CRAInvitationHistoryManager *)&v101, 2) >= 0 )
    {
      v102 = 2;
      v93 = v101;
    }
    v57 = 0;
    if ( v93 )
    {
      do
      {
        if ( v57 < 0 || v57 > (int)(v101 - 1) )
        {
          CEventLogger::LogError(
            v56,
            &Recoverable_Error,
            (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
            0x37Cu,
            L"CRAInvitationHistoryManager::get_InvitationItem",
            0x80070057);
        }
        else
        {
          v58 = v57;
          for ( i = (__int64 **)v103[0]; ; i = (__int64 **)*i )
          {
            v56 = (CEventLogger *)v103;
            if ( i == v103 || v58 <= 0 )
              break;
            --v58;
          }
          if ( i != v103 )
          {
            v60 = CRAInvitationHistoryManager::CloneHistoryItem(
                    (CRAInvitationHistoryManager *)v103,
                    (struct CRAInvitationHistoryItem *)i[2],
                    (struct CRAInvitationHistoryItem *)v97);
            if ( v60 >= 0 )
            {
              if ( v100 == 3 )
              {
                Name = CRAInvitationHistoryItem::get_Name((CRAInvitationHistoryItem *)v97, (unsigned __int16 **)&lParam);
                v4 = (OLECHAR *)lParam;
                if ( Name >= 0 )
                {
                  SendMessageW(v55, 0x180u, 0, lParam);
                  if ( v4 )
                  {
                    SysFreeString(v4);
                    v4 = 0;
                    lParam = 0;
                  }
                }
              }
            }
            else
            {
              CEventLogger::LogError(
                v56,
                &Recoverable_Error,
                (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
                0x394u,
                L"CRAInvitationHistoryManager::get_InvitationItem",
                v60);
            }
          }
        }
        ++v57;
      }
      while ( v57 < v93 );
      v5 = 0;
    }
    SendMessageW(v55, 0xBu, 1u, 0);
    v62 = 17 - (*((_DWORD *)_AtlModule + 211) != 0);
    v63 = GetDlgItem(a2, 1067);
    WindowTextLengthW = GetWindowTextLengthW(v63);
    v65 = v62 | 2;
    if ( !WindowTextLengthW )
      v65 = v62;
    v66 = v65;
    v67 = GetParent(a2);
    SendMessageW(v67, 0x470u, 0, v66);
LABEL_131:
    Thread = 0;
    goto LABEL_132;
  }
  v68 = v16 - 2012;
  if ( !v68 )
  {
    v86 = *((_QWORD *)this + 2);
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 72LL))(v86);
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 2) + 48LL))(*((_QWORD *)this + 2), &v93);
      v87 = _AtlModule;
      *((_DWORD *)_AtlModule + 135) = v93;
    }
    else
    {
      v87 = _AtlModule;
    }
    if ( !v93 )
      goto LABEL_123;
    v88 = (void *)*((_QWORD *)v87 + 132);
    if ( v88 )
      WaitForSingleObject(v88, 0);
    if ( *((_DWORD *)v87 + 262) == 2 )
    {
LABEL_123:
      v89 = 0;
      while ( *(_DWORD *)&byte_140063730[12 * v89 + 4] != 2009 )
      {
        v89 = (unsigned int)(v89 + 1);
        if ( (int)v89 >= 14 )
          goto LABEL_128;
      }
      *(_DWORD *)&byte_140063730[12 * v89] = 107;
LABEL_128:
      *(_DWORD *)this = 2009;
      v5 = 2009;
    }
    if ( *((_DWORD *)this + 8) == 1 )
    {
      *(_DWORD *)this = 2009;
      v5 = 2009;
      *((_DWORD *)this + 8) = 0;
    }
    goto LABEL_131;
  }
  v69 = v68 - 1;
  if ( !v69 )
  {
    v82 = *((_QWORD *)this + 3);
    if ( v82 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 72LL))(v82);
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3), &v93);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3), 0);
      v83 = _AtlModule;
      *((_DWORD *)_AtlModule + 135) = v93;
    }
    else
    {
      v83 = _AtlModule;
    }
    if ( v93 )
    {
      v84 = (void *)*((_QWORD *)v83 + 132);
      if ( v84 )
        WaitForSingleObject(v84, 0);
      if ( *((_DWORD *)v83 + 262) != 2 )
        goto LABEL_23;
    }
    v85 = 0;
    while ( *(_DWORD *)&byte_140063730[12 * v85 + 4] != 108 )
    {
      v85 = (unsigned int)(v85 + 1);
      if ( (int)v85 >= 14 )
        goto LABEL_115;
    }
    *(_DWORD *)&byte_140063730[12 * v85] = 107;
LABEL_115:
    *(_DWORD *)this = 108;
    v5 = 108;
    goto LABEL_131;
  }
  v70 = v69 - 1;
  if ( !v70 )
  {
    v81 = GetModuleHandleW(0);
    if ( !LoadStringW(v81, 0x2F9u, Buffer, 1024) )
    {
      v23 = 1200;
      goto LABEL_22;
    }
    v51 = 1085;
    goto LABEL_56;
  }
  v71 = v70 - 1;
  if ( !v71 )
  {
    v80 = GetModuleHandleW(0);
    if ( !LoadStringW(v80, 0x2F8u, Buffer, 1024) )
    {
      v23 = 1189;
      goto LABEL_22;
    }
    v51 = 1086;
    goto LABEL_56;
  }
  if ( v71 != 1 )
    goto LABEL_23;
  NoviceName = CRATicket::get_NoviceName((CRATicket *)v8, &bstrString);
  if ( NoviceName < 0 )
  {
    CEventLogger::LogError(
      v73,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\wizard.cpp",
      0x5BFu,
      L"CWizard::SetActive",
      NoviceName);
    goto LABEL_23;
  }
  v4 = SysAllocString(v8[69]);
  v74 = bstrString;
  Arguments[0] = (va_list)bstrString;
  Arguments[1] = (va_list)v4;
  v75 = GetModuleHandleW(0);
  if ( LoadStringW(v75, 0x21Du, Buffer, 1024) )
  {
    if ( FormatMessageW(0x2500u, Buffer, 0, 0, v95, 1u, Arguments) )
    {
      v78 = GetDlgItem(a2, 1021);
      SetWindowTextW(v78, *(LPCWSTR *)v95);
      v79 = GetDlgItem(a2, 1024);
      SendMessageW(v79, 0x40Au, 1u, 50);
      PostMessageW(a2, 0x801Au, 0, 1);
      goto LABEL_93;
    }
    v77 = 1491;
  }
  else
  {
    v77 = 1480;
  }
  CEventLogger::LogError(v76, &Recoverable_Error, L"base\\diagnosis\\ra\\ui\\wizard.cpp", v77, L"CWizard::SetActive", 0);
LABEL_93:
  Thread = 0;
LABEL_133:
  if ( *(_DWORD *)this != 2013 )
  {
    v90 = *((_QWORD *)this + 3);
    if ( v90 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v90 + 32LL))(v90, 1);
  }
  if ( v6 < 0 )
  {
    ShowRASpecificError(v6, a2, 1);
    *(_DWORD *)this = 2009;
    v5 = 2009;
  }
  if ( v4 )
    SysFreeString(v4);
  if ( v74 )
    SysFreeString(v74);
  if ( Thread )
    CloseHandle(Thread);
  if ( *(_QWORD *)v95 )
  {
    LocalFree(*(HLOCAL *)v95);
    *(_QWORD *)v95 = 0;
  }
  CRAInvitationHistoryItem::~CRAInvitationHistoryItem((CRAInvitationHistoryItem *)v97);
  CRAInvitationHistoryManager::EmptyList((CRAInvitationHistoryManager *)&v101);
  return v5;
}

```

## disassembly

```asm
0x140032f7c  mov     [rsp-8+arg_10], rbx
0x140032f81  push    rbp
0x140032f82  push    rsi
0x140032f83  push    rdi
0x140032f84  push    r12
0x140032f86  push    r13
0x140032f88  push    r14
0x140032f8a  push    r15
0x140032f8c  lea     rbp, [rsp-9D0h]
0x140032f94  sub     rsp, 0AD0h
0x140032f9b  mov     rax, cs:__security_cookie
0x140032fa2  xor     rax, rsp
0x140032fa5  mov     [rbp+0A00h+var_40], rax
0x140032fac  mov     rdi, rdx
0x140032faf  mov     rsi, rcx
0x140032fb2  xor     ebx, ebx
0x140032fb4  mov     [rbp+0A00h+var_A40], ebx
0x140032fb7  mov     [rbp+0A00h+var_A3C], 1
0x140032fbe  lea     rax, [rbp+0A00h+var_858]
0x140032fc5  mov     [rbp+0A00h+var_850], rax
0x140032fcc  lea     rax, [rbp+0A00h+var_858]
0x140032fd3  mov     [rbp+0A00h+var_858], rax
0x140032fda  xorps   xmm0, xmm0
0x140032fdd  movups  [rbp+0A00h+var_A58], xmm0
0x140032fe1  mov     [rbp+0A00h+var_A48], ebx
0x140032fe4  xorps   xmm1, xmm1
0x140032fe7  movdqa  [rbp+0A00h+var_A80], xmm1
0x140032fec  movdqa  [rbp+0A00h+var_A70], xmm0
0x140032ff1  mov     [rbp+0A00h+var_A60], rbx
0x140032ff5  mov     r14d, ebx
0x140032ff8  mov     [rsp+0B00h+lParam], rbx
0x140032ffd  mov     [rsp+0B00h+var_AB0], ebx
0x140033001  mov     r12d, ebx
0x140033004  mov     r13d, ebx
0x140033007  xor     edx, edx; Val
0x140033009  mov     r8d, 800h; Size
0x14003300f  lea     rcx, [rbp+0A00h+Buffer]; void *
0x140033016  call    memset_0
0x14003301b  mov     qword ptr [rsp+0B00h+var_AA0], rbx
0x140033020  xorps   xmm0, xmm0
0x140033023  movups  xmmword ptr [rsp+0B00h+var_A90], xmm0
0x140033028  mov     [rsp+0B00h+bstrString], rbx
0x14003302d  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140033034  mov     r15, [rcx+340h]
0x14003303b  or      r11d, 0FFFFFFFFh
0x14003303f  mov     [rcx+338h], r11d
0x140033046  mov     [rcx+33Ch], r11d
0x14003304d  mov     [rsi+8], rdi
0x140033051  mov     edx, ebx
0x140033053  mov     r9d, [rsi]
0x140033056  lea     r10, byte_140063730
0x14003305d  mov     eax, edx
0x14003305f  lea     r8, [rax+rax*2]
0x140033063  cmp     [r10+r8*4+4], r9d
0x140033068  jz      short loc_140033073
0x14003306a  inc     edx
0x14003306c  cmp     edx, 0Eh
0x14003306f  jb      short loc_14003305D
0x140033071  jmp     short loc_140033088
0x140033073  mov     eax, [r10+r8*4+8]
0x140033078  mov     [rcx+338h], eax
0x14003307e  mov     eax, [r10+r8*4]
0x140033082  mov     [rcx+33Ch], eax
0x140033088  cmp     [rcx+33Ch], r11d
0x14003308f  jz      short loc_14003309E
0x140033091  cmp     [rcx+34Ch], ebx
0x140033097  mov     eax, 1
0x14003309c  jz      short loc_1400330A1
0x14003309e  mov     rax, rbx
0x1400330a1  mov     ebx, 10h
0x1400330a6  lea     edx, [rbx+2]
0x1400330a9  cmp     [rcx+338h], r11d
0x1400330b0  cmovnz  ebx, edx
0x1400330b3  or      rbx, rax
0x1400330b6  mov     rcx, rdi; hWnd
0x1400330b9  call    cs:__imp_GetParent
0x1400330c0  nop     dword ptr [rax+rax+00h]
0x1400330c5  mov     rcx, rax; hWnd
0x1400330c8  mov     r9, rbx; lParam
0x1400330cb  xor     r8d, r8d; wParam
0x1400330ce  mov     edx, 470h; Msg
0x1400330d3  call    cs:__imp_SendMessageW
0x1400330da  nop     dword ptr [rax+rax+00h]
0x1400330df  mov     rcx, rdi; hWnd
0x1400330e2  call    cs:__imp_GetParent
0x1400330e9  nop     dword ptr [rax+rax+00h]
0x1400330ee  mov     rcx, rax; hWnd
0x1400330f1  mov     r9d, 16h; lParam
0x1400330f7  mov     r8, rbx; wParam
0x1400330fa  mov     edx, 48Ah; Msg
0x1400330ff  call    cs:__imp_PostMessageW
0x140033106  nop     dword ptr [rax+rax+00h]
0x14003310b  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140033112  mov     [rax+328h], rdi
0x140033119  mov     edx, [rsi]; unsigned int
0x14003311b  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140033120  mov     eax, [rsi]
0x140033122  mov     ecx, 7DBh; this
0x140033127  cmp     eax, ecx
0x140033129  ja      loc_1400338E2
0x14003312f  jz      loc_1400336EE
0x140033135  sub     eax, 6Ch ; 'l'
0x140033138  jz      loc_140033685
0x14003313e  sub     eax, 765h
0x140033143  jz      loc_140033622
0x140033149  sub     eax, 3
0x14003314c  jz      loc_1400335C0
0x140033152  sub     eax, 2
0x140033155  jz      loc_14003344D
0x14003315b  sub     eax, 3
0x14003315e  jz      loc_14003335A
0x140033164  cmp     eax, 1
0x140033167  jnz     short loc_1400331AF
0x140033169  mov     ebx, eax
0x14003316b  cmp     [rsi+24h], ebx
0x14003316e  jnz     loc_14003321B
0x140033174  mov     ecx, ebx; int
0x140033176  call    ?TakeLock@@YAHH@Z; TakeLock(int)
0x14003317b  test    eax, eax
0x14003317d  jnz     short loc_1400331B7
0x14003317f  mov     r13d, 80000225h
0x140033185  mov     r9d, 4C8h; unsigned int
0x14003318b  mov     dword ptr [rsp+0B00h+lpThreadId], r12d; unsigned int
0x140033190  lea     rax, aCwizardSetacti; "CWizard::SetActive"
0x140033197  mov     qword ptr [rsp+0B00h+dwCreationFlags], rax; unsigned __int16 *
0x14003319c  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x1400331a3  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400331aa  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400331af  mov     r15, r12
0x1400331b2  jmp     loc_140033C7D
0x1400331b7  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400331be  add     rcx, 1F0h; this
0x1400331c5  mov     edx, ebx; unsigned int
0x1400331c7  call    ?StartTimer@CSqmManager@@QEAAXK@Z; CSqmManager::StartTimer(ulong)
0x1400331cc  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400331d3  mov     rcx, [rcx+340h]; this
0x1400331da  call    ?CreateTicket@CRATicket@@QEAAJXZ; CRATicket::CreateTicket(void)
0x1400331df  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400331e6  mov     r8d, ebx; int
0x1400331e9  mov     edx, ebx; unsigned int
0x1400331eb  add     rcx, 1F0h; this
0x1400331f2  test    eax, eax
0x1400331f4  jns     short loc_140033214
0x1400331f6  call    ?StopTimer@CSqmManager@@QEAAKKH@Z; CSqmManager::StopTimer(ulong,int)
0x1400331fb  mov     r13d, 8000020Eh
0x140033201  mov     dword ptr [rsp+0B00h+lpThreadId], 8000020Eh
0x140033209  mov     r9d, 4D1h
0x14003320f  jmp     loc_140033190
0x140033214  call    ?StopTimer@CSqmManager@@QEAAKKH@Z; CSqmManager::StopTimer(ulong,int)
0x140033219  jmp     short loc_14003327A
0x14003321b  xor     ecx, ecx; lpModuleName
0x14003321d  call    cs:__imp_GetModuleHandleW
0x140033224  nop     dword ptr [rax+rax+00h]
0x140033229  mov     rcx, rax; hInstance
0x14003322c  mov     r9d, 400h; cchBufferMax
0x140033232  lea     r8, [rbp+0A00h+Buffer]; lpBuffer
0x140033239  mov     edx, 1F7h; uID
0x14003323e  call    cs:__imp_LoadStringW
0x140033245  nop     dword ptr [rax+rax+00h]
0x14003324a  test    eax, eax
0x14003324c  jnz     short loc_140033259
0x14003324e  mov     r9d, 4E2h
0x140033254  jmp     loc_14003318B
0x140033259  lea     r9, [rbp+0A00h+Buffer]; lParam
0x140033260  mov     edx, 47Eh; Msg
0x140033265  mov     r8d, 0Ah; wParam
0x14003326b  mov     rcx, rdi; hWnd
0x14003326e  call    cs:__imp_SendMessageW
0x140033275  nop     dword ptr [rax+rax+00h]
0x14003327a  mov     edx, 43Bh; nIDDlgItem
0x14003327f  mov     rcx, rdi; hDlg
0x140033282  call    cs:__imp_GetDlgItem
0x140033289  nop     dword ptr [rax+rax+00h]
0x14003328e  mov     r9d, 32h ; '2'; lParam
0x140033294  mov     r8, rbx; wParam
0x140033297  mov     edx, 40Ah; Msg
0x14003329c  mov     rcx, rax; hWnd
0x14003329f  call    cs:__imp_SendMessageW
0x1400332a6  nop     dword ptr [rax+rax+00h]
0x1400332ab  mov     edx, 43Ah; nIDDlgItem
0x1400332b0  mov     rcx, rdi; hDlg
0x1400332b3  call    cs:__imp_GetDlgItem
0x1400332ba  nop     dword ptr [rax+rax+00h]
0x1400332bf  mov     rcx, rax; hWnd
0x1400332c2  mov     edx, 5; nCmdShow
0x1400332c7  call    cs:__imp_ShowWindow
0x1400332ce  nop     dword ptr [rax+rax+00h]
0x1400332d3  mov     edx, 43Ch; nIDDlgItem
0x1400332d8  mov     rcx, rdi; hDlg
0x1400332db  call    cs:__imp_GetDlgItem
0x1400332e2  nop     dword ptr [rax+rax+00h]
0x1400332e7  xor     edx, edx; nCmdShow
0x1400332e9  mov     rcx, rax; hWnd
0x1400332ec  call    cs:__imp_ShowWindow
0x1400332f3  nop     dword ptr [rax+rax+00h]
0x1400332f8  mov     r8d, 10h; Flags
0x1400332fe  mov     rdx, rdi; Context
0x140033301  lea     rcx, ?TestPNRPConnection@@YAKPEAX@Z; Function
0x140033308  call    cs:__imp_QueueUserWorkItem
0x14003330f  nop     dword ptr [rax+rax+00h]
0x140033314  test    eax, eax
0x140033316  jnz     loc_1400331AF
0x14003331c  call    cs:__imp_GetLastError
0x140033323  nop     dword ptr [rax+rax+00h]
0x140033328  test    eax, eax
0x14003332a  jz      short loc_140033346
0x14003332c  call    cs:__imp_GetLastError
0x140033333  nop     dword ptr [rax+rax+00h]
0x140033338  test    eax, eax
0x14003333a  jle     short loc_14003334B
0x14003333c  movzx   eax, ax
0x14003333f  or      eax, 80070000h
0x140033344  jmp     short loc_14003334B
0x140033346  mov     eax, 80004005h
0x14003334b  mov     dword ptr [rsp+0B00h+lpThreadId], eax
0x14003334f  mov     r9d, 4F8h
0x140033355  jmp     loc_140033190
0x14003335a  call    ?IsEmailClientAvailable@@YA_NXZ; IsEmailClientAvailable(void)
0x14003335f  test    al, al
0x140033361  jnz     short loc_14003338F
0x140033363  mov     edx, 11Eh; nIDDlgItem
0x140033368  mov     rcx, rdi; hDlg
0x14003336b  call    cs:__imp_GetDlgItem
0x140033372  nop     dword ptr [rax+rax+00h]
0x140033377  mov     rcx, rax; hWnd
0x14003337a  xor     edx, edx; bEnable
0x14003337c  call    cs:__imp_EnableWindow
0x140033383  nop     dword ptr [rax+rax+00h]
0x140033388  mov     edx, 426Dh
0x14003338d  jmp     short loc_140033394
0x14003338f  mov     edx, 426Eh; unsigned int
0x140033394  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140033399  mov     rbx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400333a0  mov     rcx, [rbx+420h]; hHandle
0x1400333a7  test    rcx, rcx
0x1400333aa  jz      short loc_1400333BA
0x1400333ac  xor     edx, edx; dwMilliseconds
0x1400333ae  call    cs:__imp_WaitForSingleObject
0x1400333b5  nop     dword ptr [rax+rax+00h]
0x1400333ba  mov     edx, 424h; nIDDlgItem
0x1400333bf  mov     rcx, rdi; hDlg
0x1400333c2  cmp     dword ptr [rbx+418h], 2
0x1400333c9  jnz     short loc_140033412
0x1400333cb  call    cs:__imp_GetDlgItem
0x1400333d2  nop     dword ptr [rax+rax+00h]
0x1400333d7  mov     rcx, rax; hWnd
0x1400333da  xor     edx, edx; bEnable
0x1400333dc  call    cs:__imp_EnableWindow
0x1400333e3  nop     dword ptr [rax+rax+00h]
0x1400333e8  mov     edx, 128h; nIDDlgItem
0x1400333ed  mov     rcx, rdi; hDlg
0x1400333f0  call    cs:__imp_GetDlgItem
0x1400333f7  nop     dword ptr [rax+rax+00h]
0x1400333fc  xor     edx, edx; nCmdShow
0x1400333fe  mov     rcx, rax; hWnd
0x140033401  call    cs:__imp_ShowWindow
0x140033408  nop     dword ptr [rax+rax+00h]
0x14003340d  jmp     loc_1400331AF
0x140033412  call    cs:__imp_GetDlgItem
0x140033419  nop     dword ptr [rax+rax+00h]
0x14003341e  mov     rcx, rax; hWnd
0x140033421  mov     edx, 1; bEnable
0x140033426  call    cs:__imp_EnableWindow
0x14003342d  nop     dword ptr [rax+rax+00h]
0x140033432  mov     edx, 128h; nIDDlgItem
0x140033437  mov     rcx, rdi; hDlg
0x14003343a  call    cs:__imp_GetDlgItem
0x140033441  nop     dword ptr [rax+rax+00h]
0x140033446  mov     edx, 1
0x14003344b  jmp     short loc_1400333FE
0x14003344d  mov     edx, 41Fh; nIDDlgItem
0x140033452  mov     rcx, rdi; hDlg
0x140033455  call    cs:__imp_GetDlgItem
0x14003345c  nop     dword ptr [rax+rax+00h]
0x140033461  mov     edx, 5; nCmdShow
0x140033466  mov     rcx, rax; hWnd
0x140033469  call    cs:__imp_ShowWindow
0x140033470  nop     dword ptr [rax+rax+00h]
0x140033475  mov     edx, 420h; nIDDlgItem
0x14003347a  mov     rcx, rdi; hDlg
0x14003347d  call    cs:__imp_GetDlgItem
0x140033484  nop     dword ptr [rax+rax+00h]
0x140033489  xor     edx, edx; nCmdShow
0x14003348b  mov     rcx, rax; hWnd
0x14003348e  call    cs:__imp_ShowWindow
0x140033495  nop     dword ptr [rax+rax+00h]
0x14003349a  mov     edx, 41Eh; nIDDlgItem
0x14003349f  mov     rcx, rdi; hDlg
0x1400334a2  call    cs:__imp_GetDlgItem
0x1400334a9  nop     dword ptr [rax+rax+00h]
0x1400334ae  mov     rbx, rax
0x1400334b1  xor     edx, edx; nCmdShow
0x1400334b3  mov     rcx, rax; hWnd
0x1400334b6  call    cs:__imp_ShowWindow
0x1400334bd  nop     dword ptr [rax+rax+00h]
0x1400334c2  xor     r9d, r9d; lParam
0x1400334c5  xor     r8d, r8d; wParam
0x1400334c8  mov     edx, 14Bh; Msg
0x1400334cd  mov     rcx, rbx; hWnd
0x1400334d0  call    cs:__imp_SendMessageW
  ... truncated ...
```
