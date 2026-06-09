# CCommandLineInfo::ParseParamFlag(char const *)

- ea: `0x1801d4730`
- end: `0x1801d4a96`
- name: `?ParseParamFlag@CCommandLineInfo@@IEAAXPEBD@Z`
- size: `870`
- prototype: `void __fastcall(CCommandLineInfo *this, const char *pszParam)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801d4680`
- `0x1801d46f0`

## callees

- `0x18000e0e0`
- `0x18003c330`
- `0x180139860`
- `0x1801d4730`
- `0x1801d5c20`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!lstrcmpA` at `0x1801d4753`
- `KERNEL32!lstrcmpA` at `0x1801d4773`
- `KERNEL32!lstrcmpA` at `0x1801d49a9`
- `KERNEL32!lstrcmpA` at `0x1801d49d2`
- `KERNEL32!lstrcmpA` at `0x1801d4753`
- `KERNEL32!lstrcmpA` at `0x1801d4773`
- `KERNEL32!lstrcmpA` at `0x1801d49a9`
- `KERNEL32!lstrcmpA` at `0x1801d49d2`
- `KERNEL32!CompareStringA` at `0x1801d47b0`
- `KERNEL32!CompareStringA` at `0x1801d47db`
- `KERNEL32!CompareStringA` at `0x1801d4806`
- `KERNEL32!CompareStringA` at `0x1801d4831`
- `KERNEL32!CompareStringA` at `0x1801d485c`
- `KERNEL32!CompareStringA` at `0x1801d4887`
- `KERNEL32!CompareStringA` at `0x1801d48b2`
- `KERNEL32!CompareStringA` at `0x1801d48dd`
- `KERNEL32!CompareStringA` at `0x1801d4a0d`
- `KERNEL32!CompareStringA` at `0x1801d4a47`
- `KERNEL32!CompareStringA` at `0x1801d47b0`
- `KERNEL32!CompareStringA` at `0x1801d47db`
- `KERNEL32!CompareStringA` at `0x1801d4806`
- `KERNEL32!CompareStringA` at `0x1801d4831`
- `KERNEL32!CompareStringA` at `0x1801d485c`
- `KERNEL32!CompareStringA` at `0x1801d4887`
- `KERNEL32!CompareStringA` at `0x1801d48b2`
- `KERNEL32!CompareStringA` at `0x1801d48dd`
- `KERNEL32!CompareStringA` at `0x1801d4a0d`
- `KERNEL32!CompareStringA` at `0x1801d4a47`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x1801d48fa`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x1801d48fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CCommandLineInfo::ParseParamFlag(CCommandLineInfo *this, char *pszParam)
{
  const ATL::CSimpleStringT<wchar_t,0> *v4; // rax
  wchar_t *v5; // rdx
  wchar_t *v6; // rdx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strParam; // [rsp+60h] [rbp+18h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > result; // [rsp+68h] [rbp+20h] BYREF

  if ( !lstrcmpA(pszParam, "pt") )
  {
    this->m_nShellCommand = FilePrintTo;
    return;
  }
  if ( !lstrcmpA(pszParam, "p") )
  {
    this->m_nShellCommand = FilePrint;
    return;
  }
  if ( CompareStringA(0x7Fu, 1u, pszParam, -1, "Register", -1) == 2
    || CompareStringA(0x7Fu, 1u, pszParam, -1, "Regserver", -1) == 2 )
  {
    goto LABEL_31;
  }
  if ( CompareStringA(0x7Fu, 1u, pszParam, -1, "RegisterPerUser", -1) == 2
    || CompareStringA(0x7Fu, 1u, pszParam, -1, "RegserverPerUser", -1) == 2 )
  {
    this->m_bRegisterPerUser = 1;
LABEL_31:
    this->m_nShellCommand = AppRegister;
    return;
  }
  if ( CompareStringA(0x7Fu, 1u, pszParam, -1, "Unregister", -1) == 2
    || CompareStringA(0x7Fu, 1u, pszParam, -1, "Unregserver", -1) == 2 )
  {
    this->m_nShellCommand = AppUnregister;
  }
  else if ( CompareStringA(0x7Fu, 1u, pszParam, -1, "UnregisterPerUser", -1) == 2
         || CompareStringA(0x7Fu, 1u, pszParam, -1, "UnregserverPerUser", -1) == 2 )
  {
    this->m_nShellCommand = AppUnregister;
    this->m_bRegisterPerUser = 1;
  }
  else
  {
    if ( _strnicmp(pszParam, "RestartByRestartManager", 0x17u) )
    {
      if ( !lstrcmpA(pszParam, "ddenoshow") )
      {
        AfxGetModuleState()->m_bUserCtrl = 0;
        this->m_nShellCommand = FileDDENoShow;
        return;
      }
      if ( !lstrcmpA(pszParam, "dde") )
      {
        AfxGetModuleState()->m_bUserCtrl = 0;
        this->m_nShellCommand = FileDDE;
        return;
      }
      if ( CompareStringA(0x7Fu, 1u, pszParam, -1, "Embedding", -1) == 2 )
      {
        AfxGetModuleState()->m_bUserCtrl = 0;
        this->m_bRunEmbedded = 1;
      }
      else
      {
        if ( CompareStringA(0x7Fu, 1u, pszParam, -1, "Automation", -1) != 2 )
          return;
        AfxGetModuleState()->m_bUserCtrl = 0;
        this->m_bRunAutomated = 1;
      }
      this->m_bShowSplash = 0;
      return;
    }
    ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      &strParam,
      (unsigned __int8 *)pszParam);
    if ( *((_DWORD *)strParam.m_pszData - 4) == 60 )
    {
      this->m_nShellCommand = RestartByRestartManager;
      v4 = (const ATL::CSimpleStringT<wchar_t,0> *)ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Right(
                                                     &strParam,
                                                     &result,
                                                     36);
      ATL::CSimpleStringT<wchar_t,1>::operator=(&this->m_strRestartIdentifier, v4);
      v5 = result.m_pszData - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)result.m_pszData - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
    }
    v6 = strParam.m_pszData - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)strParam.m_pszData - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
  }
}

```

## disassembly

```asm
0x1801d4730  mov     [rsp+arg_0], rbx
0x1801d4735  mov     [rsp+arg_8], rbp
0x1801d473a  push    rdi
0x1801d473b  push    r12
0x1801d473d  push    r15
0x1801d473f  sub     rsp, 30h
0x1801d4743  mov     rdi, pszParam
0x1801d4746  mov     rbx, this
0x1801d4749  lea     pszParam, aPt; "pt"
0x1801d4750  mov     this, rdi; lpString1
0x1801d4753  call    cs:__imp_lstrcmpA
0x1801d4759  test    eax, eax
0x1801d475b  jnz     short loc_1801D4769
0x1801d475d  mov     dword ptr [rbx+18h], 3
0x1801d4764  jmp     loc_1801D4A82
0x1801d4769  lea     pszParam, aP_0; "p"
0x1801d4770  mov     this, rdi; lpString1
0x1801d4773  call    cs:__imp_lstrcmpA
0x1801d4779  test    eax, eax
0x1801d477b  jnz     short loc_1801D4789
0x1801d477d  mov     dword ptr [rbx+18h], 2
0x1801d4784  jmp     loc_1801D4A82
0x1801d4789  or      ebp, 0FFFFFFFFh
0x1801d478c  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d4790  lea     rax, aRegister; "Register"
0x1801d4797  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d479c  mov     r9d, ebp; cchCount1
0x1801d479f  mov     r8, rdi; lpString1
0x1801d47a2  lea     r15d, [rbp+2]
0x1801d47a6  mov     edx, r15d; dwCmpFlags
0x1801d47a9  lea     r12d, [r15+7Eh]
0x1801d47ad  mov     ecx, r12d; Locale
0x1801d47b0  call    cs:__imp_CompareStringA
0x1801d47b6  cmp     eax, 2
0x1801d47b9  jz      loc_1801D4A7B
0x1801d47bf  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d47c3  lea     rax, aRegserver; "Regserver"
0x1801d47ca  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d47cf  mov     r9d, ebp; cchCount1
0x1801d47d2  mov     r8, rdi; lpString1
0x1801d47d5  mov     edx, r15d; dwCmpFlags
0x1801d47d8  mov     ecx, r12d; Locale
0x1801d47db  call    cs:__imp_CompareStringA
0x1801d47e1  cmp     eax, 2
0x1801d47e4  jz      loc_1801D4A7B
0x1801d47ea  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d47ee  lea     rax, aRegisterperuse; "RegisterPerUser"
0x1801d47f5  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d47fa  mov     r9d, ebp; cchCount1
0x1801d47fd  mov     r8, rdi; lpString1
0x1801d4800  mov     edx, r15d; dwCmpFlags
0x1801d4803  mov     ecx, r12d; Locale
0x1801d4806  call    cs:__imp_CompareStringA
0x1801d480c  cmp     eax, 2
0x1801d480f  jz      loc_1801D4A77
0x1801d4815  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d4819  lea     rax, aRegserverperus; "RegserverPerUser"
0x1801d4820  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d4825  mov     r9d, ebp; cchCount1
0x1801d4828  mov     r8, rdi; lpString1
0x1801d482b  mov     edx, r15d; dwCmpFlags
0x1801d482e  mov     ecx, r12d; Locale
0x1801d4831  call    cs:__imp_CompareStringA
0x1801d4837  cmp     eax, 2
0x1801d483a  jz      loc_1801D4A77
0x1801d4840  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d4844  lea     rax, aUnregister; "Unregister"
0x1801d484b  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d4850  mov     r9d, ebp; cchCount1
0x1801d4853  mov     r8, rdi; lpString1
0x1801d4856  mov     edx, r15d; dwCmpFlags
0x1801d4859  mov     ecx, r12d; Locale
0x1801d485c  call    cs:__imp_CompareStringA
0x1801d4862  cmp     eax, 2
0x1801d4865  jz      loc_1801D4A6E
0x1801d486b  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d486f  lea     rax, aUnregserver; "Unregserver"
0x1801d4876  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d487b  mov     r9d, ebp; cchCount1
0x1801d487e  mov     r8, rdi; lpString1
0x1801d4881  mov     edx, r15d; dwCmpFlags
0x1801d4884  mov     ecx, r12d; Locale
0x1801d4887  call    cs:__imp_CompareStringA
0x1801d488d  cmp     eax, 2
0x1801d4890  jz      loc_1801D4A6E
0x1801d4896  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d489a  lea     rax, aUnregisterperu; "UnregisterPerUser"
0x1801d48a1  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d48a6  mov     r9d, ebp; cchCount1
0x1801d48a9  mov     r8, rdi; lpString1
0x1801d48ac  mov     edx, r15d; dwCmpFlags
0x1801d48af  mov     ecx, r12d; Locale
0x1801d48b2  call    cs:__imp_CompareStringA
0x1801d48b8  cmp     eax, 2
0x1801d48bb  jz      loc_1801D4A61
0x1801d48c1  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d48c5  lea     rax, aUnregserverper; "UnregserverPerUser"
0x1801d48cc  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d48d1  mov     r9d, ebp; cchCount1
0x1801d48d4  mov     r8, rdi; lpString1
0x1801d48d7  mov     edx, r15d; dwCmpFlags
0x1801d48da  mov     ecx, r12d; Locale
0x1801d48dd  call    cs:__imp_CompareStringA
0x1801d48e3  cmp     eax, 2
0x1801d48e6  jz      loc_1801D4A61
0x1801d48ec  lea     r8d, [rbp+18h]; MaxCount
0x1801d48f0  lea     pszParam, aRestartbyresta_0; "RestartByRestartManager"
0x1801d48f7  mov     this, rdi; String1
0x1801d48fa  call    cs:__imp__strnicmp
0x1801d4900  test    eax, eax
0x1801d4902  jnz     loc_1801D499F
0x1801d4908  mov     pszParam, rdi; pszSrc
0x1801d490b  lea     this, [rsp+48h+strParam]; this
0x1801d4910  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(char const *)
0x1801d4915  nop
0x1801d4916  mov     rax, [rsp+48h+strParam.m_pszData]
0x1801d491b  cmp     dword ptr [rax-10h], 3Ch ; '<'
0x1801d491f  jnz     short loc_1801D4970
0x1801d4921  mov     dword ptr [rbx+18h], 8
0x1801d4928  lea     r8d, [rbp+25h]; nCount
0x1801d492c  lea     pszParam, [rsp+48h+result]; result
0x1801d4931  lea     this, [rsp+48h+strParam]; this
0x1801d4936  call    ?Right@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Right(int)
0x1801d493b  nop
0x1801d493c  lea     this, [rbx+40h]; this
0x1801d4940  mov     pszParam, rax; strSrc
0x1801d4943  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x1801d4948  nop
0x1801d4949  mov     pszParam, [rsp+48h+result.m_pszData]
0x1801d494e  add     pszParam, 0FFFFFFFFFFFFFFE8h
0x1801d4952  mov     eax, ebp
0x1801d4954  lock xadd [pszParam+10h], eax
0x1801d4959  add     eax, ebp
0x1801d495b  test    eax, eax
0x1801d495d  jg      short loc_1801D4970
0x1801d495f  mov     this, [pszParam]
0x1801d4962  mov     rax, [this]
0x1801d4965  mov     rax, [rax+8]
0x1801d4969  call    cs:__guard_dispatch_icall_fptr
0x1801d496f  nop
0x1801d4970  mov     pszParam, [rsp+48h+strParam.m_pszData]
0x1801d4975  add     pszParam, 0FFFFFFFFFFFFFFE8h
0x1801d4979  mov     eax, ebp
0x1801d497b  lock xadd [pszParam+10h], eax
0x1801d4980  add     eax, ebp
0x1801d4982  test    eax, eax
0x1801d4984  jg      loc_1801D4A82
0x1801d498a  mov     this, [pszParam]
0x1801d498d  mov     rax, [this]
0x1801d4990  mov     rax, [rax+8]
0x1801d4994  call    cs:__guard_dispatch_icall_fptr
0x1801d499a  jmp     loc_1801D4A82
0x1801d499f  lea     pszParam, aDdenoshow; "ddenoshow"
0x1801d49a6  mov     this, rdi; lpString1
0x1801d49a9  call    cs:__imp_lstrcmpA
0x1801d49af  test    eax, eax
0x1801d49b1  jnz     short loc_1801D49C8
0x1801d49b3  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1801d49b8  and     dword ptr [rax+64h], 0
0x1801d49bc  mov     dword ptr [rbx+18h], 5
0x1801d49c3  jmp     loc_1801D4A82
0x1801d49c8  lea     pszParam, aDde; "dde"
0x1801d49cf  mov     this, rdi; lpString1
0x1801d49d2  call    cs:__imp_lstrcmpA
0x1801d49d8  test    eax, eax
0x1801d49da  jnz     short loc_1801D49F1
0x1801d49dc  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1801d49e1  and     dword ptr [rax+64h], 0
0x1801d49e5  mov     dword ptr [rbx+18h], 4
0x1801d49ec  jmp     loc_1801D4A82
0x1801d49f1  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d49f5  lea     rax, aEmbedding_0; "Embedding"
0x1801d49fc  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d4a01  mov     r9d, ebp; cchCount1
0x1801d4a04  mov     r8, rdi; lpString1
0x1801d4a07  mov     edx, r15d; dwCmpFlags
0x1801d4a0a  mov     ecx, r12d; Locale
0x1801d4a0d  call    cs:__imp_CompareStringA
0x1801d4a13  cmp     eax, 2
0x1801d4a16  jnz     short loc_1801D4A2B
0x1801d4a18  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1801d4a1d  and     dword ptr [rax+64h], 0
0x1801d4a21  mov     [rbx+0Ch], r15d
0x1801d4a25  and     dword ptr [rbx+8], 0
0x1801d4a29  jmp     short loc_1801D4A82
0x1801d4a2b  mov     [rsp+48h+cchCount2], ebp; cchCount2
0x1801d4a2f  lea     rax, aAutomation; "Automation"
0x1801d4a36  mov     [rsp+48h+lpString2], rax; lpString2
0x1801d4a3b  mov     r9d, ebp; cchCount1
0x1801d4a3e  mov     r8, rdi; lpString1
0x1801d4a41  mov     edx, r15d; dwCmpFlags
0x1801d4a44  mov     ecx, r12d; Locale
0x1801d4a47  call    cs:__imp_CompareStringA
0x1801d4a4d  cmp     eax, 2
0x1801d4a50  jnz     short loc_1801D4A82
0x1801d4a52  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1801d4a57  and     dword ptr [rax+64h], 0
0x1801d4a5b  mov     [rbx+10h], r15d
0x1801d4a5f  jmp     short loc_1801D4A25
0x1801d4a61  mov     dword ptr [rbx+18h], 7
0x1801d4a68  mov     [rbx+14h], r15d
0x1801d4a6c  jmp     short loc_1801D4A82
0x1801d4a6e  mov     dword ptr [rbx+18h], 7
0x1801d4a75  jmp     short loc_1801D4A82
0x1801d4a77  mov     [rbx+14h], r15d
0x1801d4a7b  mov     dword ptr [rbx+18h], 6
0x1801d4a82  mov     rbx, [rsp+48h+arg_0]
0x1801d4a87  mov     rbp, [rsp+48h+arg_8]
0x1801d4a8c  add     rsp, 30h
0x1801d4a90  pop     r15
0x1801d4a92  pop     r12
0x1801d4a94  pop     rdi
0x1801d4a95  retn
```
