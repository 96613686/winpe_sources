# COOBEExpeditedUpdateUSOCallback::UpdateActionCompleted(IMoUsoUpdate *,ushort *,tagActionUxClass,long)

- ea: `0x18007ad00`
- end: `0x18007b20e`
- name: `?UpdateActionCompleted@COOBEExpeditedUpdateUSOCallback@@UEAAJPEAUIMoUsoUpdate@@PEAGW4tagActionUxClass@@J@Z`
- size: `1294`
- prototype: `int __high(struct IMoUsoUpdate *, unsigned __int16 *, enum tagActionUxClass, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x18001d004`
- `0x18002d0e0`
- `0x18002f39c`
- `0x180040898`
- `0x180040918`
- `0x180042068`
- `0x18007ad00`
- `0x18007ce48`
- `0x1800b8834`
- `0x1800bd978`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007aeab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007aeab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007ae49`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007ae49`

## string_xrefs

- `0x18007aeda`: `Windows.Data.Json.JsonObject`
- `0x18007adf4`: `EnableExpeditedUpdateSyncDownloadCompleted`
- `0x18007b199`: `ExpeditedUpdateStatus`
- `0x18007b159`: `UpdateId`
- `0x18007adc8`: `ExpeditedUpdateTask USO action complete - Title: [%s], Action: [%s], ActionClass: [%d], Result: [hr=0x%08X]`
- `0x18007ad5a`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdateusocallbacks.h`
- `0x18007ad92`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdateusocallbacks.h`
- `0x18007af03`: `shell\oobe\machine\plugins\adapters\inc\expeditedupdateusocallbacks.h`
- `0x18007ae3f`: `UpdaterStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COOBEExpeditedUpdateUSOCallback::UpdateActionCompleted(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        BOOL a4,
        int a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // rdx
  HKEY v13; // rcx
  int v14; // r9d
  int v15; // edi
  int v16; // r14d
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, __int64, _QWORD **); // rdi
  __int64 (__fastcall ***v22)(_QWORD, GUID *, _QWORD *); // rsi
  __int64 (__fastcall *v23)(_QWORD, GUID *, _QWORD *); // rdi
  _QWORD *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, GUID *, _QWORD *); // rsi
  __int64 (__fastcall *v30)(_QWORD, GUID *, _QWORD *); // rdi
  _QWORD *v31; // rbx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // rbx
  _QWORD *v33; // rcx
  char v34; // r8
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, PVOID, _QWORD *); // rdi
  _QWORD *v37; // rbx
  HSTRING_HEADER *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-71h]
  _QWORD *v43; // [rsp+30h] [rbp-61h] BYREF
  const WCHAR *v44; // [rsp+38h] [rbp-59h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, _QWORD *); // [rsp+40h] [rbp-51h] BYREF
  __int64 v46; // [rsp+48h] [rbp-49h] BYREF
  __int64 v47; // [rsp+50h] [rbp-41h] BYREF
  const WCHAR *v48; // [rsp+58h] [rbp-39h] BYREF
  __int128 v49; // [rsp+60h] [rbp-31h] BYREF
  __int64 v50; // [rsp+70h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-19h] BYREF
  GUID *v52; // [rsp+90h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v47 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v47);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v44 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)a2 + 112LL))(a2, &v44);
    v10 = v11;
    if ( v11 < 0 )
    {
      v12 = 244;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdateusocallbacks.h",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
      goto LABEL_53;
    }
    bIgnoreCase = a4;
    UnattendLogW(
      0,
      L"ExpeditedUpdateTask USO action complete - Title: [%s], Action: [%s], ActionClass: [%d], Result: [hr=0x%08X]",
      v47,
      a3);
    if ( a4 )
    {
      v15 = a4 - 1;
      if ( !v15 )
      {
        if ( a5 < 0 )
        {
          v16 = 9;
        }
        else
        {
          v16 = 8;
          SHRegSetBOOL(
            v13,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE\\NDUP",
            L"EnableExpeditedUpdateSyncDownloadCompleted",
            v14);
        }
        goto LABEL_22;
      }
      if ( v15 != 1 )
        goto LABEL_52;
    }
    else if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl'::`2'::impl)
           || !a3
           || CompareStringOrdinal(a3, -1, L"UpdaterStart", -1, 0) != 2 )
    {
      goto LABEL_52;
    }
    if ( a5 < 0 )
    {
      v16 = 14;
    }
    else
    {
      v49 = 0;
      v50 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 120LL))(a2, &v49);
      v10 = v11;
      if ( v11 < 0 )
      {
        v12 = 287;
        goto LABEL_5;
      }
      v16 = 13 - (DWORD2(v49) != 4);
    }
LABEL_22:
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
    v46 = a1 + 16;
    if ( a5 < 0 && *(int *)(a1 + 72) >= 0 )
      *(_DWORD *)(a1 + 72) = a5;
    v43 = 0;
    v45 = 0;
    v52 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v17 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)v52, &v45);
    v10 = v17;
    if ( v17 >= 0 )
    {
      v20 = *(_QWORD *)(a1 + 96);
      v21 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v20 + 72LL);
      v43 = 0;
      v17 = v21(v20, v18, &v43);
      v10 = v17;
      if ( v17 >= 0 )
      {
        v22 = v45;
        v23 = (*v45)[7];
        v24 = v43;
        v52 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Status", 7u, 6u);
        v17 = v23(v22, v52, v24);
        v10 = v17;
        if ( v17 >= 0 )
        {
          v26 = *(_QWORD *)(a1 + 96);
          v27 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v26 + 72LL);
          v28 = v43;
          v43 = 0;
          if ( v28 )
            (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
          v17 = v27(v26, v25, &v43);
          v10 = v17;
          if ( v17 >= 0 )
          {
            v29 = v45;
            v30 = (*v45)[7];
            v31 = v43;
            v52 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Result", 7u, 6u);
            v17 = v30(v29, v52, v31);
            v10 = v17;
            if ( v17 >= 0 )
            {
              v32 = v45;
              v33 = v43;
              v43 = 0;
              if ( v33 )
                (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
              v17 = (**v32)(v32, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, (__int64 *)&v43);
              v10 = v17;
              if ( v17 >= 0 )
              {
                v35 = *(_QWORD *)(a1 + 88);
                v36 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD *))(*(_QWORD *)v35 + 56LL);
                v37 = v43;
                v48 = v44;
                v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v48, v34);
                v17 = v36(v35, v38[1].Reserved.Reserved1, v37);
                v10 = v17;
                if ( v17 >= 0 )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl'::`2'::impl) )
                  {
                    v39 = *(_QWORD *)(a1 + 24);
                    memset(&hstringHeader, 0, sizeof(hstringHeader));
                    LOWORD(hstringHeader.Reserved.Reserved1) = 19;
                    *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = a5;
                    v17 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, HSTRING_HEADER *))(*(_QWORD *)v39 + 32LL))(
                            v39,
                            L"StatusCode",
                            &hstringHeader);
                    v10 = v17;
                    if ( v17 < 0 )
                    {
                      v19 = 327;
                      goto LABEL_27;
                    }
                    v17 = INamedPropertyStore_SetString(*(_QWORD *)(a1 + 24), L"UpdateId", v44);
                    v10 = v17;
                    if ( v17 < 0 )
                    {
                      v19 = 328;
                      goto LABEL_27;
                    }
                    v40 = *(_QWORD *)(a1 + 24);
                    memset(&hstringHeader, 0, sizeof(hstringHeader));
                    LOWORD(hstringHeader.Reserved.Reserved1) = 19;
                    *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = v16;
                    v17 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, HSTRING_HEADER *))(*(_QWORD *)v40 + 32LL))(
                            v40,
                            L"ExpeditedUpdateStatus",
                            &hstringHeader);
                    v10 = v17;
                    if ( v17 < 0 )
                    {
                      v19 = 329;
                      goto LABEL_27;
                    }
                  }
                  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v45);
                  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v43);
                  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
LABEL_52:
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
                  v10 = 0;
                  goto LABEL_53;
                }
                v19 = 323;
              }
              else
              {
                v19 = 322;
              }
            }
            else
            {
              v19 = 320;
            }
          }
          else
          {
            v19 = 319;
          }
        }
        else
        {
          v19 = 317;
        }
      }
      else
      {
        v19 = 316;
      }
    }
    else
    {
      v19 = 314;
    }
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdateusocallbacks.h",
      (const char *)(unsigned int)v17,
      bIgnoreCase);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v45);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v46);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF1,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\expeditedupdateusocallbacks.h",
    (const char *)(unsigned int)v9,
    bIgnoreCase);
LABEL_53:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
  return v10;
}

```

## disassembly

```asm
0x18007ad00  push    rbp
0x18007ad02  push    rbx
0x18007ad03  push    rsi
0x18007ad04  push    rdi
0x18007ad05  push    r12
0x18007ad07  push    r13
0x18007ad09  push    r14
0x18007ad0b  push    r15
0x18007ad0d  lea     rbp, [rsp-17h]
0x18007ad12  sub     rsp, 0A8h
0x18007ad19  mov     rax, cs:__security_cookie
0x18007ad20  xor     rax, rsp
0x18007ad23  mov     [rbp+4Fh+var_48], rax
0x18007ad27  mov     edi, r9d
0x18007ad2a  mov     r14, r8
0x18007ad2d  mov     rsi, rdx
0x18007ad30  mov     r15, rcx
0x18007ad33  xor     r13d, r13d
0x18007ad36  mov     [rbp+4Fh+var_90], r13
0x18007ad3a  mov     rax, [rdx]
0x18007ad3d  lea     rdx, [rbp+4Fh+var_90]
0x18007ad41  mov     rcx, rsi
0x18007ad44  mov     rax, [rax+18h]
0x18007ad48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad4d  mov     ebx, eax
0x18007ad4f  test    eax, eax
0x18007ad51  jns     short loc_18007AD70
0x18007ad53  mov     rcx, [rbp+57h]; this
0x18007ad57  mov     r9d, eax; char *
0x18007ad5a  lea     r8, aShellOobeMachi_23; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007ad61  mov     edx, 0F1h; void *
0x18007ad66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ad6b  jmp     loc_18007B1E3
0x18007ad70  mov     [rbp+4Fh+var_A8], r13
0x18007ad74  mov     rax, [rsi]
0x18007ad77  lea     rdx, [rbp+4Fh+var_A8]
0x18007ad7b  mov     rcx, rsi
0x18007ad7e  mov     rax, [rax+70h]
0x18007ad82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad87  mov     ebx, eax
0x18007ad89  test    eax, eax
0x18007ad8b  jns     short loc_18007ADB4
0x18007ad8d  mov     edx, 0F4h; void *
0x18007ad92  lea     r8, aShellOobeMachi_23; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007ad99  mov     r9d, eax; char *
0x18007ad9c  mov     rcx, [rbp+57h]; this
0x18007ada0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ada5  nop
0x18007ada6  lea     rcx, [rbp+4Fh+var_A8]
0x18007adaa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007adaf  jmp     loc_18007B1E3
0x18007adb4  mov     r12d, [rbp+4Fh+arg_20]
0x18007adb8  mov     [rsp+0E0h+var_B8], r12d
0x18007adbd  mov     [rsp+0E0h+bIgnoreCase], edi
0x18007adc1  mov     r9, r14
0x18007adc4  mov     r8, [rbp+4Fh+var_90]
0x18007adc8  lea     rdx, aExpeditedupdat_7; "ExpeditedUpdateTask USO action complete"...
0x18007adcf  xor     ecx, ecx
0x18007add1  call    UnattendLogW
0x18007add6  test    edi, edi
0x18007add8  jz      short loc_18007AE17
0x18007adda  sub     edi, 1
0x18007addd  jz      short loc_18007ADE9
0x18007addf  cmp     edi, 1
0x18007ade2  jz      short loc_18007AE58
0x18007ade4  jmp     loc_18007B1D7
0x18007ade9  test    r12d, r12d
0x18007adec  js      short loc_18007AE0C
0x18007adee  mov     r14d, 8
0x18007adf4  lea     r8, aEnableexpedite_4; "EnableExpeditedUpdateSyncDownloadComple"...
0x18007adfb  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18007ae02  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18007ae07  jmp     loc_18007AEA4
0x18007ae0c  mov     r14d, 9
0x18007ae12  jmp     loc_18007AEA4
0x18007ae17  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus> `wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl(void)'::`2'::impl
0x18007ae1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(void)
0x18007ae23  test    al, al
0x18007ae25  jz      loc_18007B1D7
0x18007ae2b  test    r14, r14
0x18007ae2e  jz      loc_18007B1D7
0x18007ae34  mov     [rsp+0E0h+bIgnoreCase], r13d; int
0x18007ae39  or      edx, 0FFFFFFFFh; cchCount1
0x18007ae3c  mov     r9d, edx; cchCount2
0x18007ae3f  lea     r8, aUpdaterstart; "UpdaterStart"
0x18007ae46  mov     rcx, r14; lpString1
0x18007ae49  call    cs:__imp_CompareStringOrdinal
0x18007ae4f  cmp     eax, 2
0x18007ae52  jnz     loc_18007B1D7
0x18007ae58  test    r12d, r12d
0x18007ae5b  js      short loc_18007AE9E
0x18007ae5d  xorps   xmm0, xmm0
0x18007ae60  xor     eax, eax
0x18007ae62  movups  [rbp+4Fh+var_80], xmm0
0x18007ae66  mov     [rbp+4Fh+var_70], rax
0x18007ae6a  mov     rax, [rsi]
0x18007ae6d  lea     rdx, [rbp+4Fh+var_80]
0x18007ae71  mov     rcx, rsi
0x18007ae74  mov     rax, [rax+78h]
0x18007ae78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae7d  mov     ebx, eax
0x18007ae7f  test    eax, eax
0x18007ae81  jns     short loc_18007AE8D
0x18007ae83  mov     edx, 11Fh
0x18007ae88  jmp     loc_18007AD92
0x18007ae8d  mov     eax, dword ptr [rbp+4Fh+var_80+8]
0x18007ae90  sub     eax, 4
0x18007ae93  neg     eax
0x18007ae95  sbb     r14d, r14d
0x18007ae98  add     r14d, 0Dh
0x18007ae9c  jmp     short loc_18007AEA4
0x18007ae9e  mov     r14d, 0Eh
0x18007aea4  lea     rbx, [r15+10h]
0x18007aea8  mov     rcx, rbx; SRWLock
0x18007aeab  call    cs:__imp_AcquireSRWLockExclusive
0x18007aeb1  mov     [rbp+4Fh+var_98], rbx
0x18007aeb5  test    r12d, r12d
0x18007aeb8  jns     short loc_18007AEC4
0x18007aeba  cmp     [r15+48h], r13d
0x18007aebe  jl      short loc_18007AEC4
0x18007aec0  mov     [r15+48h], r12d
0x18007aec4  mov     [rbp+4Fh+var_B0], r13
0x18007aec8  mov     [rbp+4Fh+var_A0], r13
0x18007aecc  mov     [rbp+4Fh+var_50], r13
0x18007aed0  mov     r9d, 1Ch; unsigned int
0x18007aed6  lea     r8d, [r9+1]; unsigned int
0x18007aeda  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007aee1  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18007aee5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007aeea  nop
0x18007aeeb  lea     rdx, [rbp+4Fh+var_A0]
0x18007aeef  mov     rcx, [rbp+4Fh+var_50]
0x18007aef3  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18007aef8  mov     ebx, eax
0x18007aefa  test    eax, eax
0x18007aefc  jns     short loc_18007AF39
0x18007aefe  mov     edx, 13Ah; void *
0x18007af03  lea     r8, aShellOobeMachi_23; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007af0a  mov     r9d, eax; char *
0x18007af0d  mov     rcx, [rbp+57h]; this
0x18007af11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007af16  nop
0x18007af17  lea     rcx, [rbp+4Fh+var_A0]
0x18007af1b  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007af20  nop
0x18007af21  lea     rcx, [rbp+4Fh+var_B0]
0x18007af25  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007af2a  nop
0x18007af2b  lea     rcx, [rbp+4Fh+var_98]
0x18007af2f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18007af34  jmp     loc_18007ADA6
0x18007af39  mov     rbx, [r15+60h]
0x18007af3d  mov     rax, [rbx]
0x18007af40  mov     rdi, [rax+48h]
0x18007af44  mov     rcx, [rbp+4Fh+var_B0]
0x18007af48  mov     [rbp+4Fh+var_B0], r13
0x18007af4c  test    rcx, rcx
0x18007af4f  jz      short loc_18007AF5E
0x18007af51  mov     rdx, [rcx]
0x18007af54  mov     rax, [rdx+10h]
0x18007af58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af5d  nop
0x18007af5e  movd    xmm1, r14d
0x18007af63  cvtdq2pd xmm1, xmm1
0x18007af67  lea     r8, [rbp+4Fh+var_B0]
0x18007af6b  mov     rcx, rbx
0x18007af6e  mov     rax, rdi
0x18007af71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af76  mov     ebx, eax
0x18007af78  test    eax, eax
0x18007af7a  jns     short loc_18007AF83
0x18007af7c  mov     edx, 13Ch
0x18007af81  jmp     short loc_18007AF03
0x18007af83  mov     rsi, [rbp+4Fh+var_A0]
0x18007af87  mov     rax, [rsi]
0x18007af8a  mov     rdi, [rax+38h]
0x18007af8e  mov     rbx, [rbp+4Fh+var_B0]
0x18007af92  mov     [rbp+4Fh+var_50], r13
0x18007af96  mov     r9d, 6; unsigned int
0x18007af9c  lea     r8d, [r9+1]; unsigned int
0x18007afa0  lea     rdx, aStatus; "Status"
0x18007afa7  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18007afab  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007afb0  nop
0x18007afb1  mov     r8, rbx
0x18007afb4  mov     rdx, [rbp+4Fh+var_50]
0x18007afb8  mov     rcx, rsi
0x18007afbb  mov     rax, rdi
0x18007afbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007afc3  mov     ebx, eax
0x18007afc5  test    eax, eax
0x18007afc7  jns     short loc_18007AFD3
0x18007afc9  mov     edx, 13Dh
0x18007afce  jmp     loc_18007AF03
0x18007afd3  mov     rbx, [r15+60h]
0x18007afd7  mov     rax, [rbx]
0x18007afda  mov     rdi, [rax+48h]
0x18007afde  mov     rcx, [rbp+4Fh+var_B0]
0x18007afe2  mov     [rbp+4Fh+var_B0], r13
0x18007afe6  test    rcx, rcx
0x18007afe9  jz      short loc_18007AFF8
0x18007afeb  mov     rdx, [rcx]
0x18007afee  mov     rax, [rdx+10h]
0x18007aff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aff7  nop
0x18007aff8  movd    xmm1, r12d
0x18007affd  cvtdq2pd xmm1, xmm1
0x18007b001  lea     r8, [rbp+4Fh+var_B0]
0x18007b005  mov     rcx, rbx
0x18007b008  mov     rax, rdi
0x18007b00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b010  mov     ebx, eax
0x18007b012  test    eax, eax
0x18007b014  jns     short loc_18007B020
0x18007b016  mov     edx, 13Fh
0x18007b01b  jmp     loc_18007AF03
0x18007b020  mov     rsi, [rbp+4Fh+var_A0]
0x18007b024  mov     rax, [rsi]
0x18007b027  mov     rdi, [rax+38h]
0x18007b02b  mov     rbx, [rbp+4Fh+var_B0]
0x18007b02f  mov     [rbp+4Fh+var_50], r13
0x18007b033  mov     r9d, 6; unsigned int
0x18007b039  lea     r8d, [r9+1]; unsigned int
0x18007b03d  lea     rdx, aResult; "Result"
0x18007b044  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x18007b048  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007b04d  nop
0x18007b04e  mov     r8, rbx
0x18007b051  mov     rdx, [rbp+4Fh+var_50]
0x18007b055  mov     rcx, rsi
0x18007b058  mov     rax, rdi
0x18007b05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b060  mov     ebx, eax
0x18007b062  test    eax, eax
0x18007b064  jns     short loc_18007B070
0x18007b066  mov     edx, 140h
0x18007b06b  jmp     loc_18007AF03
0x18007b070  mov     rbx, [rbp+4Fh+var_A0]
0x18007b074  mov     rcx, [rbp+4Fh+var_B0]
0x18007b078  mov     [rbp+4Fh+var_B0], r13
0x18007b07c  test    rcx, rcx
0x18007b07f  jz      short loc_18007B08E
0x18007b081  mov     rax, [rcx]
0x18007b084  mov     rax, [rax+10h]
0x18007b088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b08d  nop
0x18007b08e  mov     rax, [rbx]
0x18007b091  lea     r8, [rbp+4Fh+var_B0]
0x18007b095  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18007b09c  mov     rcx, rbx
0x18007b09f  mov     rax, [rax]
0x18007b0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b0a7  mov     ebx, eax
0x18007b0a9  test    eax, eax
0x18007b0ab  jns     short loc_18007B0B7
0x18007b0ad  mov     edx, 142h
0x18007b0b2  jmp     loc_18007AF03
0x18007b0b7  mov     rsi, [r15+58h]
0x18007b0bb  mov     rax, [rsi]
0x18007b0be  mov     rdi, [rax+38h]
0x18007b0c2  mov     rbx, [rbp+4Fh+var_B0]
0x18007b0c6  mov     rdx, [rbp+4Fh+var_A8]
0x18007b0ca  mov     [rbp+4Fh+var_88], rdx
0x18007b0ce  lea     rdx, [rbp+4Fh+var_88]
0x18007b0d2  lea     rcx, [rbp+4Fh+hstringHeader]
0x18007b0d6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007b0db  nop
0x18007b0dc  mov     r8, rbx
0x18007b0df  mov     rdx, [rax+18h]
0x18007b0e3  mov     rcx, rsi
0x18007b0e6  mov     rax, rdi
0x18007b0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b0ee  mov     ebx, eax
0x18007b0f0  test    eax, eax
0x18007b0f2  jns     short loc_18007B0FE
0x18007b0f4  mov     edx, 143h
0x18007b0f9  jmp     loc_18007AF03
0x18007b0fe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus> `wil::Feature<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::GetImpl(void)'::`2'::impl
0x18007b105  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeNdupOngoingUpdatesStatus>::__private_IsEnabled(void)
0x18007b10a  test    al, al
0x18007b10c  jz      loc_18007B1B9
0x18007b112  mov     rcx, [r15+18h]
0x18007b116  xorps   xmm0, xmm0
0x18007b119  xor     eax, eax
0x18007b11b  movups  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm0
0x18007b11f  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+10h], rax
0x18007b123  lea     edi, [rax+13h]
0x18007b126  mov     word ptr [rbp+4Fh+hstringHeader.Reserved], di
0x18007b12a  mov     dword ptr [rbp+4Fh+hstringHeader.Reserved+8], r12d
0x18007b12e  mov     rax, [rcx]
0x18007b131  lea     r8, [rbp+4Fh+hstringHeader]
0x18007b135  lea     rdx, aStatuscode; "StatusCode"
0x18007b13c  mov     rax, [rax+20h]
0x18007b140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b145  mov     ebx, eax
0x18007b147  test    eax, eax
0x18007b149  jns     short loc_18007B155
0x18007b14b  mov     edx, 147h
0x18007b150  jmp     loc_18007AF03
0x18007b155  mov     r8, [rbp+4Fh+var_A8]
  ... truncated ...
```
