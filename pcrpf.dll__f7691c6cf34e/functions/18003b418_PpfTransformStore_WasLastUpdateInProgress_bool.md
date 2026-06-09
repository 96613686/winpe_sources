# PpfTransformStore::WasLastUpdateInProgress(bool *)

- ea: `0x18003b418`
- end: `0x18003b634`
- name: `?WasLastUpdateInProgress@PpfTransformStore@@QEAAJPEA_N@Z`
- size: `540`
- prototype: `__int64 __fastcall(PpfTransformStore *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180015ff8`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18001aff0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x1800395d4`
- `0x18003b418`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b476`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b523`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b476`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b504`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b468`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b4ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b611`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b468`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b4ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b611`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003b5bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003b5bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b554`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b554`

## string_xrefs

- `0x18003b5b2`: `UpdateInProgress`
- `0x18003b5e0`: `WasLastUpdateInProgress: %u`
- `0x18003b5e7`: `PpfTransformStore::WasLastUpdateInProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PpfTransformStore::WasLastUpdateInProgress(PpfTransformStore *this, bool *a2)
{
  PpfTransformStore *v3; // rcx
  HKEY v4; // rdi
  DWORD LastError; // ebx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  HKEY v9; // rdi
  DWORD v10; // ebx
  unsigned int ValueW; // eax
  __int64 v12; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  PpfTransformStore *pvData; // [rsp+70h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+38h] BYREF
  HKEY v18; // [rsp+88h] [rbp+40h] BYREF

  pvData = this;
  *a2 = 0;
  v18 = 0;
  hKey = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
  {
    v4 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v4);
      SetLastError(LastError);
    }
    hKey = 0;
    v6 = PpfTransformStore::OpenTransformsKey(v3, 0x20019u, 0, &hKey, 0);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 477;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)v6);
      goto LABEL_9;
    }
  }
  else
  {
    v6 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)&v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 481;
      goto LABEL_8;
    }
    v9 = hKey;
    if ( hKey )
    {
      v10 = GetLastError();
      RegCloseKey(v9);
      SetLastError(v10);
    }
    hKey = 0;
    ValueW = RegOpenKeyExW(v18, L"Control\\PCRPF\\Transforms", 0, 0x20019u, &hKey);
    if ( ValueW )
    {
      v12 = 482;
LABEL_15:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v12,
             (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
             (const char *)ValueW);
LABEL_9:
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_21;
    }
  }
  LODWORD(pvData) = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hKey, 0, L"UpdateInProgress", 0x20000010u, 0, &pvData, &pcbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    v12 = 491;
    goto LABEL_15;
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    0x1EEu,
    "PpfTransformStore::WasLastUpdateInProgress",
    "WasLastUpdateInProgress: %u",
    (_DWORD)pvData);
  *a2 = (_DWORD)pvData != 0;
  if ( hKey )
    RegCloseKey(hKey);
  v7 = 0;
LABEL_21:
  PpfSystemCcsKey::~PpfSystemCcsKey(&v18);
  return v7;
}

```

## disassembly

```asm
0x18003b418  mov     [rsp-20h+arg_0], rcx
0x18003b41d  push    rbp
0x18003b41e  push    rbx
0x18003b41f  push    rsi
0x18003b420  push    rdi
0x18003b421  mov     rbp, rsp
0x18003b424  sub     rsp, 48h
0x18003b428  mov     rsi, rdx
0x18003b42b  mov     byte ptr [rdx], 0
0x18003b42e  mov     [rbp+arg_18], 0
0x18003b436  mov     [rbp+hKey], 0
0x18003b43e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x18003b445  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x18003b44a  test    al, al
0x18003b44c  jz      short loc_18003B4B5
0x18003b44e  mov     rdi, [rbp+hKey]
0x18003b452  test    rdi, rdi
0x18003b455  jz      short loc_18003B482
0x18003b457  call    cs:__imp_GetLastError
0x18003b45e  nop     dword ptr [rax+rax+00h]
0x18003b463  mov     ebx, eax
0x18003b465  mov     rcx, rdi; hKey
0x18003b468  call    cs:__imp_RegCloseKey
0x18003b46f  nop     dword ptr [rax+rax+00h]
0x18003b474  mov     ecx, ebx; dwErrCode
0x18003b476  call    cs:__imp_SetLastError
0x18003b47d  nop     dword ptr [rax+rax+00h]
0x18003b482  mov     [rbp+hKey], 0
0x18003b48a  mov     [rsp+48h+phkResult], 0; void **
0x18003b493  lea     r9, [rbp+hKey]; HKEY *
0x18003b497  xor     r8d, r8d; bool
0x18003b49a  mov     edx, 20019h; unsigned int
0x18003b49f  call    ?OpenTransformsKey@PpfTransformStore@@AEAAJK_NPEAPEAUHKEY__@@PEAPEAX@Z; PpfTransformStore::OpenTransformsKey(ulong,bool,HKEY__ * *,void * *)
0x18003b4a4  mov     ebx, eax
0x18003b4a6  test    eax, eax
0x18003b4a8  jns     loc_18003B583
0x18003b4ae  mov     edx, 1DDh
0x18003b4b3  jmp     short loc_18003B4C9
0x18003b4b5  lea     rcx, [rbp+arg_18]; this
0x18003b4b9  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x18003b4be  mov     ebx, eax
0x18003b4c0  test    eax, eax
0x18003b4c2  jns     short loc_18003B4FB
0x18003b4c4  mov     edx, 1E1h; void *
0x18003b4c9  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003b4d0  mov     r9d, eax; char *
0x18003b4d3  mov     rcx, [rbp+20h]; this
0x18003b4d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b4dc  nop
0x18003b4dd  mov     rcx, [rbp+hKey]; hKey
0x18003b4e1  test    rcx, rcx
0x18003b4e4  jz      loc_18003B61F
0x18003b4ea  call    cs:__imp_RegCloseKey
0x18003b4f1  nop     dword ptr [rax+rax+00h]
0x18003b4f6  jmp     loc_18003B61F
0x18003b4fb  mov     rdi, [rbp+hKey]
0x18003b4ff  test    rdi, rdi
0x18003b502  jz      short loc_18003B52F
0x18003b504  call    cs:__imp_GetLastError
0x18003b50b  nop     dword ptr [rax+rax+00h]
0x18003b510  mov     ebx, eax
0x18003b512  mov     rcx, rdi; hKey
0x18003b515  call    cs:__imp_RegCloseKey
0x18003b51c  nop     dword ptr [rax+rax+00h]
0x18003b521  mov     ecx, ebx; dwErrCode
0x18003b523  call    cs:__imp_SetLastError
0x18003b52a  nop     dword ptr [rax+rax+00h]
0x18003b52f  mov     [rbp+hKey], 0
0x18003b537  lea     rax, [rbp+hKey]
0x18003b53b  mov     [rsp+48h+phkResult], rax; unsigned int
0x18003b540  mov     r9d, 20019h; samDesired
0x18003b546  xor     r8d, r8d; ulOptions
0x18003b549  lea     rdx, aControlPcrpfTr; "Control\\PCRPF\\Transforms"
0x18003b550  mov     rcx, [rbp+arg_18]; hKey
0x18003b554  call    cs:__imp_RegOpenKeyExW
0x18003b55b  nop     dword ptr [rax+rax+00h]
0x18003b560  test    eax, eax
0x18003b562  jz      short loc_18003B583
0x18003b564  mov     edx, 1E2h; void *
0x18003b569  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003b570  mov     r9d, eax; char *
0x18003b573  mov     rcx, [rbp+20h]; this
0x18003b577  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003b57c  mov     ebx, eax
0x18003b57e  jmp     loc_18003B4DD
0x18003b583  mov     dword ptr [rbp+arg_0], 0
0x18003b58a  mov     [rbp+arg_8], 4
0x18003b591  lea     rax, [rbp+arg_8]
0x18003b595  mov     [rsp+48h+pcbData], rax; pcbData
0x18003b59a  lea     rax, [rbp+arg_0]
0x18003b59e  mov     [rsp+48h+pvData], rax; pvData
0x18003b5a3  mov     [rsp+48h+phkResult], 0; pdwType
0x18003b5ac  mov     r9d, 20000010h; dwFlags
0x18003b5b2  lea     r8, aUpdateinprogre; "UpdateInProgress"
0x18003b5b9  xor     edx, edx; lpSubKey
0x18003b5bb  mov     rcx, [rbp+hKey]; hkey
0x18003b5bf  call    cs:__imp_RegGetValueW
0x18003b5c6  nop     dword ptr [rax+rax+00h]
0x18003b5cb  test    eax, 0FFFFFFFDh
0x18003b5d0  jz      short loc_18003B5D9
0x18003b5d2  mov     edx, 1EBh
0x18003b5d7  jmp     short loc_18003B569
0x18003b5d9  mov     eax, dword ptr [rbp+arg_0]
0x18003b5dc  mov     dword ptr [rsp+48h+phkResult], eax
0x18003b5e0  lea     r9, aWaslastupdatei; "WasLastUpdateInProgress: %u"
0x18003b5e7  lea     r8, aPpftransformst_9; "PpfTransformStore::WasLastUpdateInProgr"...
0x18003b5ee  mov     edx, 1EEh; unsigned int
0x18003b5f3  lea     rcx, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003b5fa  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18003b5ff  cmp     dword ptr [rbp+arg_0], 0
0x18003b603  setnz   al
0x18003b606  mov     [rsi], al
0x18003b608  mov     rcx, [rbp+hKey]; hKey
0x18003b60c  test    rcx, rcx
0x18003b60f  jz      short loc_18003B61D
0x18003b611  call    cs:__imp_RegCloseKey
0x18003b618  nop     dword ptr [rax+rax+00h]
0x18003b61d  xor     ebx, ebx
0x18003b61f  lea     rcx, [rbp+arg_18]; this
0x18003b623  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x18003b628  mov     eax, ebx
0x18003b62a  add     rsp, 48h
0x18003b62e  pop     rdi
0x18003b62f  pop     rsi
0x18003b630  pop     rbx
0x18003b631  pop     rbp
0x18003b632  retn
```
