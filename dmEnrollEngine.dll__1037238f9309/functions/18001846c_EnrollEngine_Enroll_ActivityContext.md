# EnrollEngine::Enroll(ActivityContext *)

- ea: `0x18001846c`
- end: `0x180018813`
- name: `?Enroll@EnrollEngine@@AEAAJPEAVActivityContext@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(EnrollEngine *__hidden this, struct ActivityContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e5dc`

## callees

- `0x1800071c0`
- `0x18000e0d0`
- `0x18000e508`
- `0x18001846c`
- `0x18001883c`
- `0x180018888`
- `0x1800189ac`
- `0x1800189f8`
- `0x180018a7c`
- `0x180018ac0`
- `0x180035c54`
- `0x18003dccc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001870d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180018732`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001875a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180018782`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001870d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180018732`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001875a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180018782`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800184f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800184f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018538`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800185ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018538`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800185ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018612`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018630`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018612`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018630`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Enroll *__fastcall EnrollEngine::Enroll(Enroll *this, struct ActivityContext *a2)
{
  int v2; // r14d
  LSTATUS v3; // eax
  int v4; // ebx
  LSTATUS ValueW; // eax
  BOOL v6; // esi
  LSTATUS v7; // eax
  BOOL v8; // edi
  int InitializedOrchestrator; // ebx
  __int64 v10; // rax
  OrchestratorFactory *v11; // rdi
  __int64 v12; // rcx
  struct Orchestrator *v13; // rdx
  int v15; // [rsp+40h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-61h] BYREF
  struct Orchestrator *v17; // [rsp+50h] [rbp-59h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-51h] BYREF
  DWORD v19; // [rsp+5Ch] [rbp-4Dh] BYREF
  int v20; // [rsp+60h] [rbp-49h] BYREF
  int v21; // [rsp+64h] [rbp-45h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-41h] BYREF
  std::_Ref_count_base *v23; // [rsp+70h] [rbp-39h]
  struct Orchestrator *v24; // [rsp+78h] [rbp-31h] BYREF
  std::_Ref_count_base *v25[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v26; // [rsp+90h] [rbp-19h] BYREF
  _QWORD v27[13]; // [rsp+98h] [rbp-11h] BYREF
  int v28; // [rsp+110h] [rbp+67h] BYREF
  int v29; // [rsp+114h] [rbp+6Bh]
  struct ActivityContext *v30; // [rsp+118h] [rbp+6Fh] BYREF
  int v31; // [rsp+120h] [rbp+77h] BYREF
  __int64 pvData; // [rsp+128h] [rbp+7Fh] BYREF

  v30 = a2;
  v29 = HIDWORD(this);
  v28 = 0;
  v20 = -2147467259;
  v21 = -2147467259;
  v31 = 12;
  v17 = 0;
  v24 = 0;
  v26 = 0;
  *(_OWORD *)v25 = 0;
  hkey = 0;
  v2 = 1;
  LODWORD(pvData) = 0;
  pcbData = 4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\MDM",
         0,
         0x20119u,
         &hkey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    ValueW = RegGetValueW(hkey, 0, L"DisableRegistration", 0x18u, 0, &pvData, &pcbData);
    v4 = ValueW;
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v4 == -2147024894 || v4 == -2147023267 )
  {
    v6 = 0;
  }
  else
  {
    if ( v4 < 0 )
      goto LABEL_25;
    v6 = pvData != 0;
  }
  hKey = 0;
  v15 = 0;
  v19 = 4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v4 = EEDBManager::OpenEnrollmentsHKEY(131097, &hKey);
  if ( v4 >= 0 )
  {
    v7 = RegGetValueW(hKey, 0, L"ExternallyManaged", 0x18u, 0, &v15, &v19);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
  }
  if ( v4 == -2147024894 || v4 == -2147023267 )
  {
    v8 = 0;
    v4 = 0;
  }
  else
  {
    v8 = 1;
    if ( v4 >= 0 )
      v8 = v15 != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 >= 0 && (v6 || v8) )
    v2 = 0;
LABEL_25:
  if ( hkey )
    RegCloseKey(hkey);
  if ( v4 < 0 || !v2 )
  {
    InitializedOrchestrator = -2145910774;
    goto LABEL_51;
  }
  if ( !qword_1800AF748 )
    goto LABEL_30;
  pvData = qword_1800AF748;
  v28 = 0;
  v10 = std::make_shared<OrchestratorFactory,EEDBManager &,IActivityContextStore * &>(&hkey, &off_1800AF740, &pvData);
  std::shared_ptr<OrchestratorFactory>::operator=(v25, v10);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v11 = v25[0];
  if ( !v25[0] )
  {
LABEL_30:
    InitializedOrchestrator = -2147024882;
    goto LABEL_51;
  }
  InitializedOrchestrator = OrchestratorFactory::Initialize(v25[0]);
  v28 = InitializedOrchestrator;
  if ( InitializedOrchestrator >= 0 )
  {
    InitializedOrchestrator = OrchestratorFactory::GetInitializedOrchestrator(v11, &v24);
    v28 = InitializedOrchestrator;
    if ( InitializedOrchestrator >= 0 )
    {
      v13 = v17;
      v17 = v24;
      if ( v13 )
        std::default_delete<Orchestrator>::operator()(v12, v13);
      if ( v30 != (struct ActivityContext *)-8LL )
      {
        if ( (unsigned int)_o__wcsnicmp((char *)v30 + 448) )
        {
          if ( (unsigned int)_o__wcsnicmp((char *)v30 + 448) )
          {
            if ( (unsigned int)_o__wcsnicmp((char *)v30 + 448) )
            {
              if ( (unsigned int)_o__wcsnicmp((char *)v30 + 448) )
              {
                InitializedOrchestrator = -2147024809;
                goto LABEL_51;
              }
              v31 = 10;
            }
            else
            {
              v31 = 8;
            }
          }
          else
          {
            v31 = 1;
          }
        }
        else
        {
          v31 = 0;
        }
        v27[0] = &v28;
        v27[1] = &v17;
        v27[2] = &v31;
        v27[3] = &v30;
        v27[4] = &v20;
        v27[5] = &v21;
        InitializedOrchestrator = wil::ResultFromException__lambda_516202c355856d3a818d04a5c449478e___(v27);
        goto LABEL_52;
      }
      InitializedOrchestrator = -2147418113;
LABEL_51:
      v28 = InitializedOrchestrator;
    }
  }
LABEL_52:
  if ( v25[1] )
    std::_Ref_count_base::_Decref(v25[1]);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v26);
  std::unique_ptr<Orchestrator>::~unique_ptr<Orchestrator>(&v17);
  return (Enroll *)(unsigned int)InitializedOrchestrator;
}

```

## disassembly

```asm
0x18001846c  mov     [rsp-8+arg_8], rdx
0x180018471  mov     [rsp-8+arg_0], rcx
0x180018476  push    rbp
0x180018477  push    rbx
0x180018478  push    rsi
0x180018479  push    rdi
0x18001847a  push    r14
0x18001847c  push    r15
0x18001847e  lea     rbp, [rsp-2Fh]
0x180018483  sub     rsp, 0D8h
0x18001848a  xor     r15d, r15d
0x18001848d  mov     dword ptr [rbp+57h+arg_0], r15d
0x180018491  mov     eax, 80004005h
0x180018496  mov     [rbp+57h+var_A0], eax
0x180018499  mov     [rbp+57h+var_9C], eax
0x18001849c  mov     [rbp+57h+arg_10], 0Ch
0x1800184a3  mov     [rbp+57h+var_B0], r15
0x1800184a7  mov     [rbp+57h+var_88], r15
0x1800184ab  mov     [rbp+57h+var_70], r15
0x1800184af  xorps   xmm0, xmm0
0x1800184b2  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800184b7  mov     [rbp+57h+hkey], r15
0x1800184bb  lea     r14d, [r15+1]
0x1800184bf  mov     dword ptr [rbp+57h+arg_18], r15d
0x1800184c3  mov     [rbp+57h+var_A8], 4
0x1800184ca  xor     edx, edx
0x1800184cc  lea     rcx, [rbp+57h+hkey]
0x1800184d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800184d5  lea     rax, [rbp+57h+hkey]
0x1800184d9  mov     [rsp+100h+phkResult], rax; phkResult
0x1800184de  mov     r9d, 20119h; samDesired
0x1800184e4  xor     r8d, r8d; ulOptions
0x1800184e7  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800184ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800184f5  call    cs:__imp_RegOpenKeyExW
0x1800184fb  mov     ebx, eax
0x1800184fd  test    eax, eax
0x1800184ff  jle     short loc_18001850A
0x180018501  movzx   ebx, ax
0x180018504  or      ebx, 80070000h
0x18001850a  test    ebx, ebx
0x18001850c  js      short loc_18001854D
0x18001850e  lea     rax, [rbp+57h+var_A8]
0x180018512  mov     [rsp+100h+pcbData], rax; pcbData
0x180018517  lea     rax, [rbp+57h+arg_18]
0x18001851b  mov     [rsp+100h+pvData], rax; pvData
0x180018520  mov     [rsp+100h+phkResult], r15; pdwType
0x180018525  mov     r9d, 18h; dwFlags
0x18001852b  lea     r8, aDisableregistr; "DisableRegistration"
0x180018532  xor     edx, edx; lpSubKey
0x180018534  mov     rcx, [rbp+57h+hkey]; hkey
0x180018538  call    cs:__imp_RegGetValueW
0x18001853e  mov     ebx, eax
0x180018540  test    eax, eax
0x180018542  jle     short loc_18001854D
0x180018544  movzx   ebx, ax
0x180018547  or      ebx, 80070000h
0x18001854d  mov     edi, 8007065Dh
0x180018552  cmp     ebx, 80070002h
0x180018558  jz      short loc_180018573
0x18001855a  cmp     ebx, edi
0x18001855c  jz      short loc_180018573
0x18001855e  test    ebx, ebx
0x180018560  js      loc_180018627
0x180018566  mov     esi, r15d
0x180018569  cmp     dword ptr [rbp+57h+arg_18], r15d
0x18001856d  setnz   sil
0x180018571  jmp     short loc_180018576
0x180018573  mov     esi, r15d
0x180018576  mov     [rbp+57h+hKey], r15
0x18001857a  mov     [rbp+57h+var_C0], r15d
0x18001857e  mov     [rbp+57h+var_A4], 4
0x180018585  xor     edx, edx
0x180018587  lea     rcx, [rbp+57h+hKey]
0x18001858b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180018590  lea     rdx, [rbp+57h+hKey]; HKEY *
0x180018594  mov     ecx, 20019h; unsigned int
0x180018599  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x18001859e  mov     ebx, eax
0x1800185a0  test    eax, eax
0x1800185a2  js      short loc_1800185E3
0x1800185a4  lea     rax, [rbp+57h+var_A4]
0x1800185a8  mov     [rsp+100h+pcbData], rax; pcbData
0x1800185ad  lea     rax, [rbp+57h+var_C0]
0x1800185b1  mov     [rsp+100h+pvData], rax; pvData
0x1800185b6  mov     [rsp+100h+phkResult], r15; pdwType
0x1800185bb  mov     r9d, 18h; dwFlags
0x1800185c1  lea     r8, aExternallymana; "ExternallyManaged"
0x1800185c8  xor     edx, edx; lpSubKey
0x1800185ca  mov     rcx, [rbp+57h+hKey]; hkey
0x1800185ce  call    cs:__imp_RegGetValueW
0x1800185d4  mov     ebx, eax
0x1800185d6  test    eax, eax
0x1800185d8  jle     short loc_1800185E3
0x1800185da  movzx   ebx, ax
0x1800185dd  or      ebx, 80070000h
0x1800185e3  cmp     ebx, 80070002h
0x1800185e9  jz      short loc_180018603
0x1800185eb  cmp     ebx, edi
0x1800185ed  jz      short loc_180018603
0x1800185ef  mov     edi, r14d
0x1800185f2  test    ebx, ebx
0x1800185f4  js      short loc_180018609
0x1800185f6  mov     edi, r15d
0x1800185f9  cmp     [rbp+57h+var_C0], r15d
0x1800185fd  setnz   dil
0x180018601  jmp     short loc_180018609
0x180018603  mov     edi, r15d
0x180018606  mov     ebx, r15d
0x180018609  mov     rcx, [rbp+57h+hKey]; hKey
0x18001860d  test    rcx, rcx
0x180018610  jz      short loc_180018618
0x180018612  call    cs:__imp_RegCloseKey
0x180018618  test    ebx, ebx
0x18001861a  js      short loc_180018627
0x18001861c  test    esi, esi
0x18001861e  jnz     short loc_180018624
0x180018620  test    edi, edi
0x180018622  jz      short loc_180018627
0x180018624  mov     r14d, r15d
0x180018627  mov     rcx, [rbp+57h+hkey]; hKey
0x18001862b  test    rcx, rcx
0x18001862e  jz      short loc_180018636
0x180018630  call    cs:__imp_RegCloseKey
0x180018636  test    ebx, ebx
0x180018638  js      loc_1800187D7
0x18001863e  test    r14d, r14d
0x180018641  jz      loc_1800187D7
0x180018647  mov     rax, cs:qword_1800AF748
0x18001864e  test    rax, rax
0x180018651  jnz     short loc_18001865D
0x180018653  mov     ebx, 8007000Eh
0x180018658  jmp     loc_1800187DC
0x18001865d  mov     [rbp+57h+arg_18], rax
0x180018661  mov     dword ptr [rbp+57h+arg_0], r15d
0x180018665  lea     r8, [rbp+57h+arg_18]
0x180018669  lea     rdx, off_1800AF740
0x180018670  lea     rcx, [rbp+57h+hkey]
0x180018674  call    ??$make_shared@VOrchestratorFactory@@AEAVEEDBManager@@AEAPEAVIActivityContextStore@@@std@@YA?AV?$shared_ptr@VOrchestratorFactory@@@0@AEAVEEDBManager@@AEAPEAVIActivityContextStore@@@Z; std::make_shared<OrchestratorFactory,EEDBManager &,IActivityContextStore * &>(EEDBManager &,IActivityContextStore * &)
0x180018679  mov     rdx, rax
0x18001867c  lea     rcx, [rbp+57h+var_80]
0x180018680  call    ??4?$shared_ptr@VOrchestratorFactory@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<OrchestratorFactory>::operator=(std::shared_ptr<OrchestratorFactory> &&)
0x180018685  mov     rcx, [rbp+57h+var_90]; this
0x180018689  test    rcx, rcx
0x18001868c  jz      short loc_180018693
0x18001868e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018693  mov     rdi, [rbp+57h+var_80]
0x180018697  test    rdi, rdi
0x18001869a  jz      short loc_180018653
0x18001869c  mov     rcx, rdi; this
0x18001869f  call    ?Initialize@OrchestratorFactory@@QEAAJXZ; OrchestratorFactory::Initialize(void)
0x1800186a4  mov     ebx, eax
0x1800186a6  mov     dword ptr [rbp+57h+arg_0], eax
0x1800186a9  test    eax, eax
0x1800186ab  js      loc_1800187DF
0x1800186b1  lea     rdx, [rbp+57h+var_88]; struct Orchestrator **
0x1800186b5  mov     rcx, rdi; this
0x1800186b8  call    ?GetInitializedOrchestrator@OrchestratorFactory@@QEAAJPEAPEAVOrchestrator@@@Z; OrchestratorFactory::GetInitializedOrchestrator(Orchestrator * *)
0x1800186bd  mov     ebx, eax
0x1800186bf  mov     dword ptr [rbp+57h+arg_0], eax
0x1800186c2  test    eax, eax
0x1800186c4  js      loc_1800187DF
0x1800186ca  mov     rdx, [rbp+57h+var_B0]
0x1800186ce  mov     rax, [rbp+57h+var_88]
0x1800186d2  mov     [rbp+57h+var_B0], rax
0x1800186d6  test    rdx, rdx
0x1800186d9  jz      short loc_1800186E0
0x1800186db  call    ??R?$default_delete@VOrchestrator@@@std@@QEBAXPEAVOrchestrator@@@Z; std::default_delete<Orchestrator>::operator()(Orchestrator *)
0x1800186e0  mov     rcx, [rbp+57h+arg_8]
0x1800186e4  lea     rax, [rcx+8]
0x1800186e8  test    rax, rax
0x1800186eb  jnz     short loc_1800186F7
0x1800186ed  mov     ebx, 8000FFFFh
0x1800186f2  jmp     loc_1800187DC
0x1800186f7  add     rcx, 1C0h
0x1800186fe  mov     ebx, 104h
0x180018703  mov     r8d, ebx
0x180018706  mov     rdx, cs:off_1800AF218; "OR_MDMENROLL"
0x18001870d  call    cs:__imp__o__wcsnicmp
0x180018713  test    eax, eax
0x180018715  jnz     short loc_18001871D
0x180018717  mov     [rbp+57h+arg_10], r15d
0x18001871b  jmp     short loc_180018793
0x18001871d  mov     rcx, [rbp+57h+arg_8]
0x180018721  add     rcx, 1C0h
0x180018728  mov     r8, rbx
0x18001872b  mov     rdx, cs:off_1800AF228; "OR_LOCALENROLL"
0x180018732  call    cs:__imp__o__wcsnicmp
0x180018738  test    eax, eax
0x18001873a  jnz     short loc_180018745
0x18001873c  mov     [rbp+57h+arg_10], 1
0x180018743  jmp     short loc_180018793
0x180018745  mov     rcx, [rbp+57h+arg_8]
0x180018749  add     rcx, 1C0h
0x180018750  mov     r8, rbx
0x180018753  mov     rdx, cs:off_1800AF298; "OR_AADENROLL"
0x18001875a  call    cs:__imp__o__wcsnicmp
0x180018760  test    eax, eax
0x180018762  jnz     short loc_18001876D
0x180018764  mov     [rbp+57h+arg_10], 8
0x18001876b  jmp     short loc_180018793
0x18001876d  mov     rcx, [rbp+57h+arg_8]
0x180018771  add     rcx, 1C0h
0x180018778  mov     r8, rbx
0x18001877b  mov     rdx, cs:off_1800AF2B8; "OR_MMPCENROLL"
0x180018782  call    cs:__imp__o__wcsnicmp
0x180018788  test    eax, eax
0x18001878a  jnz     short loc_1800187D0
0x18001878c  mov     [rbp+57h+arg_10], 0Ah
0x180018793  lea     rax, [rbp+57h+arg_0]
0x180018797  mov     [rbp+57h+var_68], rax
0x18001879b  lea     rax, [rbp+57h+var_B0]
0x18001879f  mov     [rbp+57h+var_60], rax
0x1800187a3  lea     rax, [rbp+57h+arg_10]
0x1800187a7  mov     [rbp+57h+var_58], rax
0x1800187ab  lea     rax, [rbp+57h+arg_8]
0x1800187af  mov     [rbp+57h+var_50], rax
0x1800187b3  lea     rax, [rbp+57h+var_A0]
0x1800187b7  mov     [rbp+57h+var_48], rax
0x1800187bb  lea     rax, [rbp+57h+var_9C]
0x1800187bf  mov     [rbp+57h+var_40], rax
0x1800187c3  lea     rcx, [rbp+57h+var_68]
0x1800187c7  call    wil__ResultFromException__lambda_516202c355856d3a818d04a5c449478e___
0x1800187cc  mov     ebx, eax
0x1800187ce  jmp     short loc_1800187DF
0x1800187d0  mov     ebx, 80070057h
0x1800187d5  jmp     short loc_1800187DC
0x1800187d7  mov     ebx, 8018000Ah
0x1800187dc  mov     dword ptr [rbp+57h+arg_0], ebx
0x1800187df  mov     rcx, [rbp+57h+var_80+8]; this
0x1800187e3  test    rcx, rcx
0x1800187e6  jz      short loc_1800187EE
0x1800187e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800187ed  nop
0x1800187ee  lea     rcx, [rbp+57h+var_70]
0x1800187f2  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800187f7  nop
0x1800187f8  lea     rcx, [rbp+57h+var_B0]
0x1800187fc  call    ??1?$unique_ptr@VOrchestrator@@U?$default_delete@VOrchestrator@@@std@@@std@@QEAA@XZ; std::unique_ptr<Orchestrator>::~unique_ptr<Orchestrator>(void)
0x180018801  mov     eax, ebx
0x180018803  add     rsp, 0D8h
0x18001880a  pop     r15
0x18001880c  pop     r14
0x18001880e  pop     rdi
0x18001880f  pop     rsi
0x180018810  pop     rbx
0x180018811  pop     rbp
0x180018812  retn
```
