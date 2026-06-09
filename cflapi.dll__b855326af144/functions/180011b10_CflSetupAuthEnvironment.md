# CflSetupAuthEnvironment

- ea: `0x180011b10`
- end: `0x180011dc4`
- name: `CflSetupAuthEnvironment`
- size: `692`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800035bc`
- `0x1800067c4`
- `0x1800084d4`
- `0x180008868`
- `0x180009adc`
- `0x18000d31c`
- `0x18000d8d8`
- `0x180011130`
- `0x180011b10`
- `0x1800132a8`
- `0x18001f2d8`
- `0x18002d50c`
- `0x18002dffc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011b59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011b59`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011b71`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011b71`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180011b77`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180011b77`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamFreeAuthBuffer` at `0x180011cd2`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamFreeAuthBuffer` at `0x180011db7`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamFreeAuthBuffer` at `0x180011cd2`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamFreeAuthBuffer` at `0x180011db7`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetCandidateAccountCredz` at `0x180011c21`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetCandidateAccountCredz` at `0x180011c21`

## string_xrefs

- `0x180011d2c`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180011c85`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180011d10`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180011d94`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
__int64 __fastcall CflSetupAuthEnvironment(_QWORD *a1, _DWORD *a2)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  int CandidateAccountCredz; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r15
  size_t v11; // rdi
  int v12; // eax
  HLOCAL v13; // rbx
  int v15; // [rsp+20h] [rbp-3D8h] BYREF
  DWORD dwSize; // [rsp+24h] [rbp-3D4h] BYREF
  __int64 v17; // [rsp+28h] [rbp-3D0h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp-3C8h]
  _BYTE v19[16]; // [rsp+38h] [rbp-3C0h] BYREF
  char v20; // [rsp+48h] [rbp-3B0h]
  _QWORD v21[42]; // [rsp+60h] [rbp-398h] BYREF
  WCHAR ExeName[264]; // [rsp+1B0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v21,
    "CflSetupAuthEnvironmentActivity");
  v21[0] = &CflApiTraceProvider::CflSetupAuthEnvironmentActivity::`vftable';
  CflApiTraceProvider::CflSetupAuthEnvironmentActivity::StartActivity(
    (CflApiTraceProvider::CflSetupAuthEnvironmentActivity *)v21,
    ExeName,
    CommandLineW);
  if ( a1 && a2 )
  {
    *a1 = 0;
    *a2 = 0;
    if ( (unsigned __int8)IsCamGetCandidateAccountCredzPresent() )
    {
      v20 = 0;
      PwdlessPlat::ImageCustomizations::QueryCustomizations((PwdlessPlat::ImageCustomizations *)v19);
      if ( v20 )
      {
        if ( !(unsigned __int8)CflApi::InCamSession() )
        {
          v15 = 0;
          v17 = 0;
          CandidateAccountCredz = CamGetCandidateAccountCredz(&v15, &v17);
          v7 = CandidateAccountCredz;
          if ( CandidateAccountCredz < 0 )
          {
            v8 = (unsigned int)CandidateAccountCredz;
            v9 = 401;
LABEL_19:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v9,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
              (const char *)v8,
              v15);
LABEL_20:
            if ( v17 )
              CamFreeAuthBuffer();
            goto LABEL_17;
          }
          if ( (unsigned int)v15 < 0x18 || (v10 = v17, v11 = *(unsigned int *)(v17 + 8), (unsigned int)v15 < v11 + 24) )
          {
            v7 = -2147024883;
            v8 = 2147942413LL;
            v9 = 406;
            goto LABEL_19;
          }
          hMem = 0;
          v12 = CflApiNew::AllocBuffer_unsigned_char_((unsigned int)v11);
          v7 = v12;
          if ( v12 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x19D,
              (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
              (const char *)(unsigned int)v12,
              v15);
            if ( hMem )
              CflSecureFreeBuffer(hMem);
            goto LABEL_20;
          }
          v13 = hMem;
          memcpy_0(hMem, (const void *)(v10 + 24), v11);
          *a1 = v13;
          *a2 = v11;
          if ( v17 )
            CamFreeAuthBuffer();
        }
      }
    }
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v21);
    v21[0] = &CflApiTraceProvider::CflSetupAuthEnvironmentActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v21);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v21);
    return 0;
  }
  v7 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x17E,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
    (const char *)0x80004003LL,
    v15);
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x48,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
    (const char *)v7,
    v15);
  v21[0] = &CflApiTraceProvider::CflSetupAuthEnvironmentActivity::`vftable';
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v21);
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v21);
  return v7;
}

```

## disassembly

```asm
0x180011b10  mov     [rsp+arg_10], rbx
0x180011b15  push    rsi
0x180011b16  push    rdi
0x180011b17  push    r13
0x180011b19  push    r14
0x180011b1b  push    r15
0x180011b1d  sub     rsp, 3D0h
0x180011b24  mov     rax, cs:__security_cookie
0x180011b2b  xor     rax, rsp
0x180011b2e  mov     [rsp+3F8h+var_38], rax
0x180011b36  mov     rsi, rdx
0x180011b39  mov     r14, rcx
0x180011b3c  xor     edx, edx; Val
0x180011b3e  mov     r8d, 20Ah; Size
0x180011b44  lea     rcx, [rsp+3F8h+ExeName]; void *
0x180011b4c  call    memset_0
0x180011b51  mov     [rsp+3F8h+dwSize], 105h
0x180011b59  call    cs:__imp_GetCurrentProcess
0x180011b5f  mov     rcx, rax; hProcess
0x180011b62  lea     r9, [rsp+3F8h+dwSize]; lpdwSize
0x180011b67  lea     r8, [rsp+3F8h+ExeName]; lpExeName
0x180011b6f  xor     edx, edx; dwFlags
0x180011b71  call    cs:__imp_QueryFullProcessImageNameW
0x180011b77  call    cs:__imp_GetCommandLineW
0x180011b7d  mov     rbx, rax
0x180011b80  lea     rdx, aCflsetupauthen_0; "CflSetupAuthEnvironmentActivity"
0x180011b87  lea     rcx, [rsp+3F8h+var_398]
0x180011b8c  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011b91  lea     r13, ??_7CflSetupAuthEnvironmentActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetupAuthEnvironmentActivity::`vftable'
0x180011b98  mov     [rsp+3F8h+var_398], r13
0x180011b9d  mov     r8, rbx; unsigned __int16 *
0x180011ba0  lea     rdx, [rsp+3F8h+ExeName]; unsigned __int16 *
0x180011ba8  lea     rcx, [rsp+3F8h+var_398]; this
0x180011bad  call    ?StartActivity@CflSetupAuthEnvironmentActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflSetupAuthEnvironmentActivity::StartActivity(ushort const *,ushort const *)
0x180011bb2  nop
0x180011bb3  test    r14, r14
0x180011bb6  jz      loc_180011D00
0x180011bbc  test    rsi, rsi
0x180011bbf  jz      loc_180011D00
0x180011bc5  mov     qword ptr [r14], 0
0x180011bcc  mov     dword ptr [rsi], 0
0x180011bd2  call    IsCamGetCandidateAccountCredzPresent
0x180011bd7  test    al, al
0x180011bd9  jz      loc_180011CD8
0x180011bdf  mov     [rsp+3F8h+var_3B0], 0
0x180011be4  lea     rcx, [rsp+3F8h+var_3C0]; this
0x180011be9  call    ?QueryCustomizations@ImageCustomizations@PwdlessPlat@@AEAAXXZ; PwdlessPlat::ImageCustomizations::QueryCustomizations(void)
0x180011bee  cmp     [rsp+3F8h+var_3B0], 0
0x180011bf3  jz      loc_180011CD8
0x180011bf9  call    CflApi__InCamSession
0x180011bfe  test    al, al
0x180011c00  jnz     loc_180011CD8
0x180011c06  mov     [rsp+3F8h+var_3D8], 0; int
0x180011c0e  mov     [rsp+3F8h+var_3D0], 0
0x180011c17  lea     rdx, [rsp+3F8h+var_3D0]
0x180011c1c  lea     rcx, [rsp+3F8h+var_3D8]
0x180011c21  call    cs:__imp_CamGetCandidateAccountCredz
0x180011c27  mov     ebx, eax
0x180011c29  test    eax, eax
0x180011c2b  jns     short loc_180011C3A
0x180011c2d  mov     r9d, eax
0x180011c30  mov     edx, 191h
0x180011c35  jmp     loc_180011D94
0x180011c3a  cmp     [rsp+3F8h+var_3D8], 18h
0x180011c3f  jb      loc_180011D87
0x180011c45  mov     r15, [rsp+3F8h+var_3D0]
0x180011c4a  mov     edi, [r15+8]
0x180011c4e  lea     rcx, [rdi+18h]
0x180011c52  mov     eax, [rsp+3F8h+var_3D8]
0x180011c56  cmp     rax, rcx
0x180011c59  jb      loc_180011D87
0x180011c5f  mov     [rsp+3F8h+hMem], 0
0x180011c68  lea     rdx, [rsp+3F8h+hMem]
0x180011c6d  mov     ecx, edi; uBytes
0x180011c6f  call    CflApiNew__AllocBuffer_unsigned_char_
0x180011c74  mov     ebx, eax
0x180011c76  test    eax, eax
0x180011c78  jns     short loc_180011CAF
0x180011c7a  mov     rcx, [rsp+3F8h]; this
0x180011c82  mov     r9d, eax; char *
0x180011c85  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180011c8c  mov     edx, 19Dh; void *
0x180011c91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c96  nop
0x180011c97  mov     rcx, [rsp+3F8h+hMem]; hMem
0x180011c9c  test    rcx, rcx
0x180011c9f  jz      loc_180011DA9
0x180011ca5  call    CflSecureFreeBuffer
0x180011caa  jmp     loc_180011DA9
0x180011caf  lea     rdx, [r15+18h]; Src
0x180011cb3  mov     r8, rdi; Size
0x180011cb6  mov     rbx, [rsp+3F8h+hMem]
0x180011cbb  mov     rcx, rbx; void *
0x180011cbe  call    memcpy_0
0x180011cc3  mov     [r14], rbx
0x180011cc6  mov     [rsi], edi
0x180011cc8  mov     rcx, [rsp+3F8h+var_3D0]
0x180011ccd  test    rcx, rcx
0x180011cd0  jz      short loc_180011CD8
0x180011cd2  call    cs:__imp_CamFreeAuthBuffer
0x180011cd8  lea     rcx, [rsp+3F8h+var_398]
0x180011cdd  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180011ce2  nop
0x180011ce3  mov     [rsp+3F8h+var_398], r13
0x180011ce8  lea     rcx, [rsp+3F8h+var_398]
0x180011ced  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011cf2  lea     rcx, [rsp+3F8h+var_398]
0x180011cf7  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011cfc  xor     eax, eax
0x180011cfe  jmp     short loc_180011D5F
0x180011d00  mov     rcx, [rsp+3F8h]; this
0x180011d08  mov     ebx, 80004003h
0x180011d0d  mov     r9d, ebx; char *
0x180011d10  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180011d17  mov     edx, 17Eh; void *
0x180011d1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d21  mov     rcx, [rsp+3F8h]; this
0x180011d29  mov     r9d, ebx; char *
0x180011d2c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180011d33  mov     edx, 48h ; 'H'; void *
0x180011d38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d3d  nop
0x180011d3e  mov     [rsp+3F8h+var_398], r13
0x180011d43  lea     rcx, [rsp+3F8h+var_398]
0x180011d48  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011d4d  lea     rcx, [rsp+3F8h+var_398]
0x180011d52  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011d57  mov     eax, ebx
0x180011d59  jmp     short loc_180011D5F
0x180011d5b  mov     eax, [rsp+3F8h+dwSize]
0x180011d5f  mov     rcx, [rsp+3F8h+var_38]
0x180011d67  xor     rcx, rsp; StackCookie
0x180011d6a  call    __security_check_cookie
0x180011d6f  mov     rbx, [rsp+3F8h+arg_10]
0x180011d77  add     rsp, 3D0h
0x180011d7e  pop     r15
0x180011d80  pop     r14
0x180011d82  pop     r13
0x180011d84  pop     rdi
0x180011d85  pop     rsi
0x180011d86  retn
0x180011d87  mov     ebx, 8007000Dh
0x180011d8c  mov     r9d, ebx; char *
0x180011d8f  mov     edx, 196h; void *
0x180011d94  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180011d9b  mov     rcx, [rsp+3F8h]; this
0x180011da3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011da8  nop
0x180011da9  mov     rcx, [rsp+3F8h+var_3D0]
0x180011dae  test    rcx, rcx
0x180011db1  jz      loc_180011D21
0x180011db7  call    cs:__imp_CamFreeAuthBuffer
0x180011dbd  jmp     loc_180011D21
```
