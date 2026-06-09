# MPCManagerClientFactory::GetForCurrentThread(Windows::Internal::Input::MPCManager::IMPCManagerClient * *)

- ea: `0x1800982f0`
- end: `0x1800984a9`
- name: `?GetForCurrentThread@MPCManagerClientFactory@@UEAAJPEAPEAUIMPCManagerClient@MPCManager@Input@Internal@Windows@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(MPCManagerClientFactory *__hidden this, struct Windows::Internal::Input::MPCManager::IMPCManagerClient **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180069f90`
- `0x18008dcac`
- `0x18008ead4`
- `0x1800982f0`
- `0x1800984b0`
- `0x1800e24c4`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUIOpenExisting` at `0x180098354`
- `CoreMessaging!CoreUIOpenExisting` at `0x180098354`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180098319`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180098319`

## string_xrefs

- `0x18009832a`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\precomp.h`
- `0x180098365`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\precomp.h`
- `0x180098398`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcmanagerclient.cpp`
- `0x180098435`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcmanagerclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MPCManagerClientFactory::GetForCurrentThread(
        MPCManagerClientFactory *this,
        struct Windows::Internal::Input::MPCManager::IMPCManagerClient **a2)
{
  HRESULT ApartmentType; // eax
  int v4; // eax
  bool v5; // bl
  struct Windows::Internal::Input::MPCManager::IMPCManagerClient *v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 pAptType; // [rsp+60h] [rbp+30h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+68h] [rbp+38h] BYREF

  LODWORD(pAptType) = 0;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType((APTTYPE *)&pAptType, &pAptQualifier);
  if ( ApartmentType < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\precomp.h",
      (const char *)(unsigned int)ApartmentType,
      v15[0]);
  if ( !(_DWORD)pAptType || (_DWORD)pAptType == 3 )
    goto LABEL_9;
  pAptType = 0;
  v4 = CoreUIOpenExisting(&pAptType);
  if ( v4 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\precomp.h",
      (const char *)(unsigned int)v4,
      v15[0]);
  v5 = pAptType != 0;
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&pAptType);
  if ( v5 )
  {
LABEL_9:
    v7 = 0;
    v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v9 = *(_QWORD *)(v8 + 16);
    if ( !v9
      || (*(_QWORD *)v15 = 0,
          v10 = (*(__int64 (__fastcall **)(__int64, GUID *, int *))(*(_QWORD *)v9 + 24LL))(
                  v9,
                  &GUID_14d766a1_12f3_404c_ae87_c566719dbe22,
                  v15),
          v7 = *(struct Windows::Internal::Input::MPCManager::IMPCManagerClient **)v15,
          v10 >= 0)
      && *(_QWORD *)v15 )
    {
      *(_QWORD *)v15 = 0;
      if ( v7 )
        (*(void (__fastcall **)(struct Windows::Internal::Input::MPCManager::IMPCManagerClient *))(*(_QWORD *)v7 + 16LL))(v7);
      v11 = Microsoft::WRL::Details::MakeAndInitialize<MPCManagerClient,Windows::Internal::Input::MPCManager::IMPCManagerClient,>(v15);
      if ( v11 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x197,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcmanagerclient.cpp",
          (const char *)(unsigned int)v11,
          v15[0]);
      v12 = (__int64 *)wil::com_weak_copy_failfast<wil::com_ptr_t<Windows::Internal::Input::MPCManager::IMPCManagerClient,wil::err_exception_policy> &>(
                         &pAptType,
                         v15);
      v13 = *v12;
      *v12 = 0;
      v14 = *(_QWORD *)(v8 + 16);
      *(_QWORD *)(v8 + 16) = v13;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&pAptType);
      v7 = *(struct Windows::Internal::Input::MPCManager::IMPCManagerClient **)v15;
    }
    *(_QWORD *)v15 = 0;
    *a2 = v7;
    wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(v15);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcmanagerclient.cpp",
      (const char *)0x8001010ELL,
      v15[0]);
    return 2147549454LL;
  }
}

```

## disassembly

```asm
0x1800982f0  mov     [rsp-18h+arg_0], rbx
0x1800982f5  push    rbp
0x1800982f6  push    rdi
0x1800982f7  push    r14
0x1800982f9  mov     rbp, rsp
0x1800982fc  sub     rsp, 30h
0x180098300  mov     rdi, rdx
0x180098303  mov     dword ptr [rbp+pAptType], 0
0x18009830a  mov     [rbp+pAptQualifier], 0
0x180098311  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x180098315  lea     rcx, [rbp+pAptType]; pAptType
0x180098319  call    cs:__imp_CoGetApartmentType
0x18009831f  mov     rcx, [rbp+18h]; this
0x180098323  test    eax, eax
0x180098325  jns     short loc_18009833C
0x180098327  mov     r9d, eax; char *
0x18009832a  lea     r8, aOnecoreuapWind_128; "onecoreuap\\windows\\moderncore\\inputv"...
0x180098331  mov     edx, 3Fh ; '?'; void *
0x180098336  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18009833c  mov     eax, dword ptr [rbp+pAptType]
0x18009833f  test    eax, eax
0x180098341  jz      short loc_1800983B0
0x180098343  cmp     eax, 3
0x180098346  jz      short loc_1800983B0
0x180098348  mov     [rbp+pAptType], 0
0x180098350  lea     rcx, [rbp+pAptType]
0x180098354  call    cs:__imp_CoreUIOpenExisting
0x18009835a  mov     rcx, [rbp+18h]; this
0x18009835e  test    eax, eax
0x180098360  jns     short loc_180098377
0x180098362  mov     r9d, eax; char *
0x180098365  lea     r8, aOnecoreuapWind_128; "onecoreuap\\windows\\moderncore\\inputv"...
0x18009836c  mov     edx, 46h ; 'F'; void *
0x180098371  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180098377  cmp     [rbp+pAptType], 0
0x18009837c  setnz   bl
0x18009837f  lea     rcx, [rbp+pAptType]
0x180098383  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180098388  test    bl, bl
0x18009838a  jnz     short loc_1800983B0
0x18009838c  mov     rcx, [rbp+18h]; this
0x180098390  mov     ebx, 8001010Eh
0x180098395  mov     r9d, ebx; char *
0x180098398  lea     r8, aOnecoreuapWind_80; "onecoreuap\\windows\\moderncore\\inputv"...
0x18009839f  mov     edx, 192h; void *
0x1800983a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800983a9  mov     eax, ebx
0x1800983ab  jmp     loc_18009849B
0x1800983b0  xor     edx, edx
0x1800983b2  mov     ecx, cs:_tls_index
0x1800983b8  mov     rax, gs:58h
0x1800983c1  mov     r14d, 10h
0x1800983c7  mov     rbx, [rax+rcx*8]
0x1800983cb  mov     rcx, [rbx+r14]
0x1800983cf  test    rcx, rcx
0x1800983d2  jz      short loc_180098404
0x1800983d4  mov     qword ptr [rbp+var_10], rdx
0x1800983d8  mov     rax, [rcx]
0x1800983db  lea     r8, [rbp+var_10]
0x1800983df  lea     rdx, _GUID_14d766a1_12f3_404c_ae87_c566719dbe22
0x1800983e6  mov     rax, [rax+18h]
0x1800983ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800983ef  mov     rdx, qword ptr [rbp+var_10]
0x1800983f3  test    eax, eax
0x1800983f5  js      loc_180098485
0x1800983fb  test    rdx, rdx
0x1800983fe  jz      loc_180098485
0x180098404  mov     qword ptr [rbp+var_10], 0
0x18009840c  test    rdx, rdx
0x18009840f  jz      short loc_180098421
0x180098411  mov     rax, [rdx]
0x180098414  mov     rcx, rdx
0x180098417  mov     rax, [rax+10h]
0x18009841b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098420  nop
0x180098421  lea     rcx, [rbp+var_10]
0x180098425  call    ??$MakeAndInitialize@VMPCManagerClient@@UIMPCManagerClient@MPCManager@Input@Internal@Windows@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMPCManagerClient@MPCManager@Input@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MPCManagerClient,Windows::Internal::Input::MPCManager::IMPCManagerClient,>(Windows::Internal::Input::MPCManager::IMPCManagerClient * *)
0x18009842a  mov     rcx, [rbp+18h]; this
0x18009842e  test    eax, eax
0x180098430  jns     short loc_180098447
0x180098432  mov     r9d, eax; char *
0x180098435  lea     r8, aOnecoreuapWind_80; "onecoreuap\\windows\\moderncore\\inputv"...
0x18009843c  mov     edx, 197h; void *
0x180098441  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180098447  lea     rdx, [rbp+var_10]
0x18009844b  lea     rcx, [rbp+pAptType]
0x18009844f  call    ??$com_weak_copy_failfast@AEAV?$com_ptr_t@UIMPCManagerClient@MPCManager@Input@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_failfast_policy@wil@@@0@AEAV?$com_ptr_t@UIMPCManagerClient@MPCManager@Input@Internal@Windows@@Uerr_exception_policy@wil@@@0@@Z; wil::com_weak_copy_failfast<wil::com_ptr_t<Windows::Internal::Input::MPCManager::IMPCManagerClient,wil::err_exception_policy> &>(wil::com_ptr_t<Windows::Internal::Input::MPCManager::IMPCManagerClient,wil::err_exception_policy> &)
0x180098454  mov     rdx, [rax]
0x180098457  mov     qword ptr [rax], 0
0x18009845e  mov     rcx, [rbx+r14]
0x180098462  mov     [rbx+r14], rdx
0x180098466  test    rcx, rcx
0x180098469  jz      short loc_180098478
0x18009846b  mov     rax, [rcx]
0x18009846e  mov     rax, [rax+10h]
0x180098472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098477  nop
0x180098478  lea     rcx, [rbp+pAptType]
0x18009847c  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180098481  mov     rdx, qword ptr [rbp+var_10]
0x180098485  mov     qword ptr [rbp+var_10], 0
0x18009848d  mov     [rdi], rdx
0x180098490  lea     rcx, [rbp+var_10]
0x180098494  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180098499  xor     eax, eax
0x18009849b  mov     rbx, [rsp+30h+arg_0]
0x1800984a0  add     rsp, 30h
0x1800984a4  pop     r14
0x1800984a6  pop     rdi
0x1800984a7  pop     rbp
0x1800984a8  retn
```
