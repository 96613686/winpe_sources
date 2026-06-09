# PpfTransformStore::MarkUpdateInProgress(HKEY__ *,bool)

- ea: `0x180039354`
- end: `0x1800395cc`
- name: `?MarkUpdateInProgress@PpfTransformStore@@AEAAJPEAUHKEY__@@_N@Z`
- size: `632`
- prototype: `__int64 __fastcall(PpfTransformStore *this, HKEY, unsigned __int8)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180015ff8`
- `0x18003796c`
- `0x180038d80`
- `0x18003ad7c`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18001aff0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180039354`
- `0x1800395d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039429`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800394bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039429`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800394bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003940a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003949d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003940a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003949d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003941b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039483`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800394ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800395a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003941b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039483`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800394ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800395a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039548`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039548`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003955f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003955f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800394ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800394ec`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003957c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003957c`

## string_xrefs

- `0x18003937f`: `PpfTransformStore::MarkUpdateInProgress`
- `0x180039378`: `Marking update in progress: %u`
- `0x18003951b`: `UpdateInProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall PpfTransformStore::MarkUpdateInProgress(PpfTransformStore *this, HKEY a2, unsigned __int8 a3)
{
  HKEY v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  PpfTransformStore *v8; // rcx
  HKEY v9; // rdi
  DWORD LastError; // ebx
  int v11; // eax
  __int64 v12; // rdx
  HKEY v13; // rsi
  DWORD v14; // edi
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF
  int Data; // [rsp+70h] [rbp+40h] BYREF
  HKEY v22; // [rsp+78h] [rbp+48h] BYREF

  hKey = (HKEY)this;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    0x59u,
    "PpfTransformStore::MarkUpdateInProgress",
    "Marking update in progress: %u",
    a3);
  v5 = 0;
  v22 = 0;
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
  {
    v6 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)&v22);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)v6,
        phkResult);
      goto LABEL_30;
    }
    v5 = v22;
  }
  hKey = 0;
  if ( !a2 )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
    {
      v9 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v9);
        SetLastError(LastError);
      }
      hKey = 0;
      v11 = PpfTransformStore::OpenTransformsKey(v8, 0x20006u, 0, &hKey, 0);
      v7 = v11;
      if ( v11 < 0 )
      {
        v12 = 102;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
          (const char *)(unsigned int)v11,
          phkResult);
        goto LABEL_12;
      }
    }
    else
    {
      v13 = hKey;
      if ( hKey )
      {
        v14 = GetLastError();
        RegCloseKey(v13);
        SetLastError(v14);
      }
      hKey = 0;
      v15 = RegOpenKeyExW(v5, L"Control\\PCRPF\\Transforms", 0, 0x20006u, &hKey);
      if ( v15 )
      {
        v16 = 106;
LABEL_18:
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v16,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
               (const char *)v15,
               phkResult);
LABEL_12:
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_30;
      }
    }
    a2 = hKey;
  }
  if ( a3 )
  {
    Data = 1;
    v15 = RegSetValueExW(a2, L"UpdateInProgress", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v15 )
    {
      v16 = 115;
      goto LABEL_18;
    }
  }
  else
  {
    v15 = RegDeleteValueW(a2, L"UpdateInProgress");
    if ( (v15 & 0xFFFFFFFD) != 0 )
    {
      v16 = 124;
      goto LABEL_18;
    }
  }
  v11 = RegFlushKey(a2);
  v7 = v11;
  if ( v11 < 0 )
  {
    v12 = 126;
    goto LABEL_11;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v7 = 0;
LABEL_30:
  PpfSystemCcsKey::~PpfSystemCcsKey(&v22);
  return v7;
}

```

## disassembly

```asm
0x180039354  mov     [rsp-28h+arg_8], rbx
0x180039359  mov     [rsp-28h+hKey], rcx
0x18003935e  push    rbp
0x18003935f  push    rsi
0x180039360  push    rdi
0x180039361  push    r12
0x180039363  push    r14
0x180039365  mov     rbp, rsp
0x180039368  sub     rsp, 30h
0x18003936c  movzx   r14d, r8b
0x180039370  mov     rdi, rdx
0x180039373  mov     dword ptr [rsp+30h+phkResult], r14d; int
0x180039378  lea     r9, aMarkingUpdateI; "Marking update in progress: %u"
0x18003937f  lea     r8, aPpftransformst_0; "PpfTransformStore::MarkUpdateInProgress"
0x180039386  mov     edx, 59h ; 'Y'; unsigned int
0x18003938b  lea     r12, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180039392  mov     rcx, r12; char *
0x180039395  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003939a  xor     ebx, ebx
0x18003939c  mov     [rbp+arg_18], rbx
0x1800393a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x1800393a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x1800393ac  test    al, al
0x1800393ae  jnz     short loc_1800393DC
0x1800393b0  lea     rcx, [rbp+arg_18]; this
0x1800393b4  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x1800393b9  mov     ebx, eax
0x1800393bb  test    eax, eax
0x1800393bd  jns     short loc_1800393D8
0x1800393bf  mov     rcx, [rbp+28h]; this
0x1800393c3  mov     r9d, eax; char *
0x1800393c6  mov     r8, r12; unsigned int
0x1800393c9  mov     edx, 5Eh ; '^'; void *
0x1800393ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800393d3  jmp     loc_1800395AF
0x1800393d8  mov     rbx, [rbp+arg_18]
0x1800393dc  mov     [rbp+hKey], 0
0x1800393e4  test    rdi, rdi
0x1800393e7  jnz     loc_18003951B
0x1800393ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x1800393f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x1800393f9  test    al, al
0x1800393fb  jz      loc_180039494
0x180039401  mov     rdi, [rbp+hKey]
0x180039405  test    rdi, rdi
0x180039408  jz      short loc_180039435
0x18003940a  call    cs:__imp_GetLastError
0x180039411  nop     dword ptr [rax+rax+00h]
0x180039416  mov     ebx, eax
0x180039418  mov     rcx, rdi; hKey
0x18003941b  call    cs:__imp_RegCloseKey
0x180039422  nop     dword ptr [rax+rax+00h]
0x180039427  mov     ecx, ebx; dwErrCode
0x180039429  call    cs:__imp_SetLastError
0x180039430  nop     dword ptr [rax+rax+00h]
0x180039435  mov     [rbp+hKey], 0
0x18003943d  mov     [rsp+30h+phkResult], 0; int
0x180039446  lea     r9, [rbp+hKey]; HKEY *
0x18003944a  xor     r8d, r8d; bool
0x18003944d  mov     edx, 20006h; unsigned int
0x180039452  call    ?OpenTransformsKey@PpfTransformStore@@AEAAJK_NPEAPEAUHKEY__@@PEAPEAX@Z; PpfTransformStore::OpenTransformsKey(ulong,bool,HKEY__ * *,void * *)
0x180039457  mov     ebx, eax
0x180039459  test    eax, eax
0x18003945b  jns     loc_180039517
0x180039461  mov     edx, 66h ; 'f'; void *
0x180039466  mov     r8, r12; unsigned int
0x180039469  mov     r9d, eax; char *
0x18003946c  mov     rcx, [rbp+28h]; this
0x180039470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039475  nop
0x180039476  mov     rcx, [rbp+hKey]; hKey
0x18003947a  test    rcx, rcx
0x18003947d  jz      loc_1800395AF
0x180039483  call    cs:__imp_RegCloseKey
0x18003948a  nop     dword ptr [rax+rax+00h]
0x18003948f  jmp     loc_1800395AF
0x180039494  mov     rsi, [rbp+hKey]
0x180039498  test    rsi, rsi
0x18003949b  jz      short loc_1800394C8
0x18003949d  call    cs:__imp_GetLastError
0x1800394a4  nop     dword ptr [rax+rax+00h]
0x1800394a9  mov     edi, eax
0x1800394ab  mov     rcx, rsi; hKey
0x1800394ae  call    cs:__imp_RegCloseKey
0x1800394b5  nop     dword ptr [rax+rax+00h]
0x1800394ba  mov     ecx, edi; dwErrCode
0x1800394bc  call    cs:__imp_SetLastError
0x1800394c3  nop     dword ptr [rax+rax+00h]
0x1800394c8  mov     [rbp+hKey], 0
0x1800394d0  lea     rax, [rbp+hKey]
0x1800394d4  mov     [rsp+30h+phkResult], rax; unsigned int
0x1800394d9  mov     r9d, 20006h; samDesired
0x1800394df  xor     r8d, r8d; ulOptions
0x1800394e2  lea     rdx, aControlPcrpfTr; "Control\\PCRPF\\Transforms"
0x1800394e9  mov     rcx, rbx; hKey
0x1800394ec  call    cs:__imp_RegOpenKeyExW
0x1800394f3  nop     dword ptr [rax+rax+00h]
0x1800394f8  test    eax, eax
0x1800394fa  jz      short loc_180039517
0x1800394fc  mov     edx, 6Ah ; 'j'; void *
0x180039501  mov     rcx, [rbp+28h]; this
0x180039505  mov     r9d, eax; char *
0x180039508  mov     r8, r12; unsigned int
0x18003950b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180039510  mov     ebx, eax
0x180039512  jmp     loc_180039476
0x180039517  mov     rdi, [rbp+hKey]
0x18003951b  lea     rdx, aUpdateinprogre; "UpdateInProgress"
0x180039522  mov     rcx, rdi; hKey
0x180039525  test    r14b, r14b
0x180039528  jz      short loc_18003955F
0x18003952a  mov     [rbp+Data], 1
0x180039531  mov     r9d, 4; dwType
0x180039537  mov     [rsp+30h+cbData], r9d; cbData
0x18003953c  lea     rax, [rbp+Data]
0x180039540  mov     [rsp+30h+phkResult], rax; lpData
0x180039545  xor     r8d, r8d; Reserved
0x180039548  call    cs:__imp_RegSetValueExW
0x18003954f  nop     dword ptr [rax+rax+00h]
0x180039554  test    eax, eax
0x180039556  jz      short loc_180039579
0x180039558  mov     edx, 73h ; 's'
0x18003955d  jmp     short loc_180039501
0x18003955f  call    cs:__imp_RegDeleteValueW
0x180039566  nop     dword ptr [rax+rax+00h]
0x18003956b  test    eax, 0FFFFFFFDh
0x180039570  jz      short loc_180039579
0x180039572  mov     edx, 7Ch ; '|'
0x180039577  jmp     short loc_180039501
0x180039579  mov     rcx, rdi; hKey
0x18003957c  call    cs:__imp_RegFlushKey
0x180039583  nop     dword ptr [rax+rax+00h]
0x180039588  mov     ebx, eax
0x18003958a  test    eax, eax
0x18003958c  jns     short loc_180039598
0x18003958e  mov     edx, 7Eh ; '~'
0x180039593  jmp     loc_180039466
0x180039598  mov     rcx, [rbp+hKey]; hKey
0x18003959c  test    rcx, rcx
0x18003959f  jz      short loc_1800395AD
0x1800395a1  call    cs:__imp_RegCloseKey
0x1800395a8  nop     dword ptr [rax+rax+00h]
0x1800395ad  xor     ebx, ebx
0x1800395af  lea     rcx, [rbp+arg_18]; this
0x1800395b3  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800395b8  mov     eax, ebx
0x1800395ba  mov     rbx, [rsp+30h+arg_8]
0x1800395bf  add     rsp, 30h
0x1800395c3  pop     r14
0x1800395c5  pop     r12
0x1800395c7  pop     rdi
0x1800395c8  pop     rsi
0x1800395c9  pop     rbp
0x1800395ca  retn
```
