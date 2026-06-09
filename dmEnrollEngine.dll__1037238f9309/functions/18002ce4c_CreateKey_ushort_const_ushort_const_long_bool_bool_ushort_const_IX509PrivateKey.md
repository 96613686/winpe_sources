# CreateKey(ushort const *,ushort const *,long,bool,bool,ushort const *,IX509PrivateKey * *)

- ea: `0x18002ce4c`
- end: `0x18002d265`
- name: `?CreateKey@@YAJPEBG0J_N10PEAPEAUIX509PrivateKey@@@Z`
- size: `1049`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *, unsigned int, unsigned __int8, bool, OLECHAR *psza, struct IX509PrivateKey **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cda4`

## callees

- `0x1800128c4`
- `0x1800140d0`
- `0x180020cb4`
- `0x18002ce4c`
- `0x18003c968`
- `0x18003dba8`
- `0x18004e314`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ceb6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cfd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ceb6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cfd6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cef3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cf67`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cf8b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cef3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cf67`
- `OLEAUT32!__imp_SysAllocString` at `0x18002cf8b`

## string_xrefs

- `0x18002ce75`: `CreateKey`
- `0x18002ced5`: `CoCreateInstance IObjectId`
- `0x18002cfee`: `CoCreateInstance IX509PrivateKey`
- `0x18002d1a8`: `IX509PrivateKey->Create`
- `0x18002d1f8`: `IX509PrivateKey->Create`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CreateKey(
        OLECHAR *psz,
        OLECHAR *a2,
        unsigned int a3,
        unsigned __int8 a4,
        bool a5,
        OLECHAR *psza,
        struct IX509PrivateKey **a7)
{
  unsigned __int16 v7; // r15
  HRESULT v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  OLECHAR *v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  OLECHAR *v17; // rdi
  OLECHAR *v18; // rbx
  HRESULT v19; // eax
  __int64 v20; // rcx
  HRESULT v21; // esi
  const wchar_t *v22; // r8
  int v23; // eax
  __int64 v24; // rcx
  const wchar_t *v25; // r8
  __int64 v26; // r9
  struct IX509PrivateKey *v27; // rcx
  __int64 v28; // rdx
  int v30; // [rsp+30h] [rbp-41h] BYREF
  LPVOID v31; // [rsp+38h] [rbp-39h] BYREF
  OLECHAR *v32; // [rsp+40h] [rbp-31h] BYREF
  OLECHAR *v33; // [rsp+48h] [rbp-29h] BYREF
  OLECHAR *v34; // [rsp+50h] [rbp-21h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-19h] BYREF
  _BYTE v36[8]; // [rsp+60h] [rbp-11h] BYREF
  _QWORD v37[9]; // [rsp+68h] [rbp-9h] BYREF

  v7 = a4;
  v30 = 0;
  v37[0] = "CreateKey";
  v37[1] = &v30;
  ppv = 0;
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&ppv);
  v11 = CoCreateInstance(
          &GUID_884e2000_217d_11da_b2a4_000e7bbb2b09,
          0,
          1u,
          &GUID_728ab300_217d_11da_b2a4_000e7bbb2b09,
          &ppv);
  v13 = v11;
  v30 = v11;
  if ( v11 >= 0 )
  {
    v14 = SysAllocString(a2);
    v32 = v14;
    if ( !v14 )
    {
LABEL_5:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
      v13 = -2147024882;
      goto LABEL_46;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 64LL))(ppv, v14);
    v13 = v15;
    v30 = v15;
    if ( v15 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v16,
          FunctionFailedEvent,
          L"IObjectId->InitializeFromAlgorithmName",
          (unsigned int)v15);
        v13 = v30;
      }
      goto LABEL_9;
    }
    v17 = SysAllocString(psz);
    v33 = v17;
    if ( !v17 )
    {
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
      goto LABEL_5;
    }
    v18 = SysAllocString(psza);
    v34 = v18;
    if ( !v18 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
      goto LABEL_11;
    }
    v31 = 0;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v31);
    v19 = CoCreateInstance(
            &GUID_884e200c_217d_11da_b2a4_000e7bbb2b09,
            0,
            1u,
            &GUID_728ab30c_217d_11da_b2a4_000e7bbb2b09,
            &v31);
    v21 = v19;
    v30 = v19;
    if ( v19 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      {
LABEL_18:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v31);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
        v13 = v21;
        goto LABEL_46;
      }
      v22 = L"CoCreateInstance IX509PrivateKey";
LABEL_17:
      McTemplateU0zq_EventWriteTransfer(v20, FunctionFailedEvent, v22, (unsigned int)v19);
      v21 = v30;
      goto LABEL_18;
    }
    v19 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v31 + 256LL))(v31, ppv);
    v21 = v19;
    v30 = v19;
    if ( v19 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_18;
      v22 = L"IX509PrivateKey->put_Algorithm";
      goto LABEL_17;
    }
    v19 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v31 + 288LL))(v31, a3);
    v21 = v19;
    v30 = v19;
    if ( v19 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_18;
      v22 = L"IX509PrivateKey->put_Length";
      goto LABEL_17;
    }
    v23 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v31 + 128LL))(v31, v18);
    v13 = v23;
    v30 = v23;
    if ( v23 >= 0 )
    {
      v23 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v31 + 208LL))(v31, v17);
      v13 = v23;
      v30 = v23;
      if ( v23 >= 0 )
      {
        v23 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v31 + 352LL))(v31, v7);
        v13 = v23;
        v30 = v23;
        if ( v23 >= 0 )
        {
          if ( !a5
            || (v23 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v31 + 304LL))(v31, 3),
                v13 = v23,
                v30 = v23,
                v23 >= 0) )
          {
            EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v36, "IX509PrivateKey->Create");
            v30 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 64LL))(v31);
            EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v36);
            v13 = v30;
            if ( v30 >= 0 )
            {
              v27 = (struct IX509PrivateKey *)v31;
              v31 = 0;
              *a7 = v27;
              Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v31);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
              v13 = 0;
              goto LABEL_46;
            }
            if ( v30 == -2146893809 || (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
              goto LABEL_30;
            v26 = (unsigned int)v30;
            v25 = L"IX509PrivateKey->Create";
            goto LABEL_29;
          }
          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
            goto LABEL_30;
          v25 = L"IX509PrivateKey->put_ExportPolicy";
        }
        else
        {
          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
            goto LABEL_30;
          v25 = L"IX509PrivateKey->put_MachineContext";
        }
      }
      else
      {
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
          goto LABEL_30;
        v25 = L"IX509PrivateKey->put_ProviderName";
      }
    }
    else
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      {
LABEL_30:
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v31);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
LABEL_9:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
        goto LABEL_46;
      }
      v25 = L"IX509PrivateKey->put_ContainerName";
    }
    v26 = (unsigned int)v23;
LABEL_29:
    McTemplateU0zq_EventWriteTransfer(v24, FunctionFailedEvent, v25, v26);
    v13 = v30;
    goto LABEL_30;
  }
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(v12, FunctionFailedEvent, L"CoCreateInstance IObjectId", (unsigned int)v11);
    v13 = v30;
  }
LABEL_46:
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&ppv);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v37, v28);
  return v13;
}

```

## disassembly

```asm
0x18002ce4c  push    rbp
0x18002ce4e  push    rbx
0x18002ce4f  push    rsi
0x18002ce50  push    rdi
0x18002ce51  push    r14
0x18002ce53  push    r15
0x18002ce55  lea     rbp, [rsp-17h]
0x18002ce5a  sub     rsp, 88h
0x18002ce61  movzx   r15d, r9b
0x18002ce65  mov     r14d, r8d
0x18002ce68  mov     rdi, rdx
0x18002ce6b  mov     rsi, rcx
0x18002ce6e  mov     [rbp+3Fh+var_80], 0
0x18002ce75  lea     rax, aCreatekey; "CreateKey"
0x18002ce7c  mov     [rbp+3Fh+var_48], rax
0x18002ce80  lea     rax, [rbp+3Fh+var_80]
0x18002ce84  mov     [rbp+3Fh+var_40], rax
0x18002ce88  mov     [rbp+3Fh+var_58], 0
0x18002ce90  lea     rcx, [rbp+3Fh+var_58]
0x18002ce94  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18002ce99  lea     rax, [rbp+3Fh+var_58]
0x18002ce9d  mov     [rsp+0B0h+ppv], rax; ppv
0x18002cea2  lea     r9, _GUID_728ab300_217d_11da_b2a4_000e7bbb2b09; riid
0x18002cea9  xor     edx, edx; pUnkOuter
0x18002ceab  lea     r8d, [rdx+1]; dwClsContext
0x18002ceaf  lea     rcx, _GUID_884e2000_217d_11da_b2a4_000e7bbb2b09; rclsid
0x18002ceb6  call    cs:__imp_CoCreateInstance
0x18002cebc  mov     ebx, eax
0x18002cebe  mov     [rbp+3Fh+var_80], eax
0x18002cec1  test    eax, eax
0x18002cec3  jns     short loc_18002CEF0
0x18002cec5  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002cecc  jz      loc_18002D240
0x18002ced2  mov     r9d, eax
0x18002ced5  lea     r8, aCocreateinstan_3; "CoCreateInstance IObjectId"
0x18002cedc  lea     rdx, FunctionFailedEvent
0x18002cee3  call    McTemplateU0zq_EventWriteTransfer
0x18002cee8  mov     ebx, [rbp+3Fh+var_80]
0x18002ceeb  jmp     loc_18002D240
0x18002cef0  mov     rcx, rdi; psz
0x18002cef3  call    cs:__imp_SysAllocString
0x18002cef9  mov     [rbp+3Fh+var_70], rax
0x18002cefd  test    rax, rax
0x18002cf00  jnz     short loc_18002CF15
0x18002cf02  lea     rcx, [rbp+3Fh+var_70]
0x18002cf06  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cf0b  mov     ebx, 8007000Eh
0x18002cf10  jmp     loc_18002D240
0x18002cf15  mov     rcx, [rbp+3Fh+var_58]
0x18002cf19  mov     rdx, [rcx]
0x18002cf1c  mov     r8, [rdx+40h]
0x18002cf20  mov     rdx, rax
0x18002cf23  mov     rax, r8
0x18002cf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf2b  mov     ebx, eax
0x18002cf2d  mov     [rbp+3Fh+var_80], eax
0x18002cf30  test    eax, eax
0x18002cf32  jns     short loc_18002CF64
0x18002cf34  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002cf3b  jz      short loc_18002CF56
0x18002cf3d  mov     r9d, eax
0x18002cf40  lea     r8, aIobjectidIniti_0; "IObjectId->InitializeFromAlgorithmName"
0x18002cf47  lea     rdx, FunctionFailedEvent
0x18002cf4e  call    McTemplateU0zq_EventWriteTransfer
0x18002cf53  mov     ebx, [rbp+3Fh+var_80]
0x18002cf56  lea     rcx, [rbp+3Fh+var_70]
0x18002cf5a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cf5f  jmp     loc_18002D240
0x18002cf64  mov     rcx, rsi; psz
0x18002cf67  call    cs:__imp_SysAllocString
0x18002cf6d  mov     rdi, rax
0x18002cf70  mov     [rbp+3Fh+var_68], rax
0x18002cf74  test    rax, rax
0x18002cf77  jnz     short loc_18002CF87
0x18002cf79  lea     rcx, [rbp+3Fh+var_68]
0x18002cf7d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cf82  jmp     loc_18002CF02
0x18002cf87  mov     rcx, [rbp+3Fh+psz]; psz
0x18002cf8b  call    cs:__imp_SysAllocString
0x18002cf91  mov     rbx, rax
0x18002cf94  mov     [rbp+3Fh+var_60], rax
0x18002cf98  test    rax, rax
0x18002cf9b  jnz     short loc_18002CFA8
0x18002cf9d  lea     rcx, [rbp+3Fh+var_60]
0x18002cfa1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cfa6  jmp     short loc_18002CF79
0x18002cfa8  mov     [rbp+3Fh+var_78], 0
0x18002cfb0  lea     rcx, [rbp+3Fh+var_78]
0x18002cfb4  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18002cfb9  lea     rax, [rbp+3Fh+var_78]
0x18002cfbd  mov     [rsp+0B0h+ppv], rax; ppv
0x18002cfc2  lea     r9, _GUID_728ab30c_217d_11da_b2a4_000e7bbb2b09; riid
0x18002cfc9  xor     edx, edx; pUnkOuter
0x18002cfcb  lea     r8d, [rdx+1]; dwClsContext
0x18002cfcf  lea     rcx, _GUID_884e200c_217d_11da_b2a4_000e7bbb2b09; rclsid
0x18002cfd6  call    cs:__imp_CoCreateInstance
0x18002cfdc  mov     esi, eax
0x18002cfde  mov     [rbp+3Fh+var_80], eax
0x18002cfe1  test    eax, eax
0x18002cfe3  jns     short loc_18002D035
0x18002cfe5  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002cfec  jz      short loc_18002D007
0x18002cfee  lea     r8, aCocreateinstan_4; "CoCreateInstance IX509PrivateKey"
0x18002cff5  mov     r9d, eax
0x18002cff8  lea     rdx, FunctionFailedEvent
0x18002cfff  call    McTemplateU0zq_EventWriteTransfer
0x18002d004  mov     esi, [rbp+3Fh+var_80]
0x18002d007  lea     rcx, [rbp+3Fh+var_78]
0x18002d00b  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18002d010  nop
0x18002d011  lea     rcx, [rbp+3Fh+var_60]
0x18002d015  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d01a  nop
0x18002d01b  lea     rcx, [rbp+3Fh+var_68]
0x18002d01f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d024  nop
0x18002d025  lea     rcx, [rbp+3Fh+var_70]
0x18002d029  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d02e  mov     ebx, esi
0x18002d030  jmp     loc_18002D240
0x18002d035  mov     rcx, [rbp+3Fh+var_78]
0x18002d039  mov     rax, [rcx]
0x18002d03c  mov     rdx, [rbp+3Fh+var_58]
0x18002d040  mov     rax, [rax+100h]
0x18002d047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d04c  mov     esi, eax
0x18002d04e  mov     [rbp+3Fh+var_80], eax
0x18002d051  test    eax, eax
0x18002d053  jns     short loc_18002D067
0x18002d055  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002d05c  jz      short loc_18002D007
0x18002d05e  lea     r8, aIx509privateke_4; "IX509PrivateKey->put_Algorithm"
0x18002d065  jmp     short loc_18002CFF5
0x18002d067  mov     rcx, [rbp+3Fh+var_78]
0x18002d06b  mov     rax, [rcx]
0x18002d06e  mov     edx, r14d
0x18002d071  mov     rax, [rax+120h]
0x18002d078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d07d  mov     esi, eax
0x18002d07f  mov     [rbp+3Fh+var_80], eax
0x18002d082  test    eax, eax
0x18002d084  jns     short loc_18002D09F
0x18002d086  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002d08d  jz      loc_18002D007
0x18002d093  lea     r8, aIx509privateke_6; "IX509PrivateKey->put_Length"
0x18002d09a  jmp     loc_18002CFF5
0x18002d09f  mov     rcx, [rbp+3Fh+var_78]
0x18002d0a3  mov     rax, [rcx]
0x18002d0a6  mov     rdx, rbx
0x18002d0a9  mov     rax, [rax+80h]
0x18002d0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b5  mov     ebx, eax
0x18002d0b7  mov     [rbp+3Fh+var_80], eax
0x18002d0ba  test    eax, eax
0x18002d0bc  jns     short loc_18002D102
0x18002d0be  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002d0c5  jz      short loc_18002D0E0
0x18002d0c7  lea     r8, aIx509privateke_1; "IX509PrivateKey->put_ContainerName"
0x18002d0ce  mov     r9d, eax
0x18002d0d1  lea     rdx, FunctionFailedEvent
0x18002d0d8  call    McTemplateU0zq_EventWriteTransfer
0x18002d0dd  mov     ebx, [rbp+3Fh+var_80]
0x18002d0e0  lea     rcx, [rbp+3Fh+var_78]
0x18002d0e4  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18002d0e9  nop
0x18002d0ea  lea     rcx, [rbp+3Fh+var_60]
0x18002d0ee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d0f3  nop
0x18002d0f4  lea     rcx, [rbp+3Fh+var_68]
0x18002d0f8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d0fd  jmp     loc_18002CF56
0x18002d102  mov     rcx, [rbp+3Fh+var_78]
0x18002d106  mov     rax, [rcx]
0x18002d109  mov     rdx, rdi
0x18002d10c  mov     rax, [rax+0D0h]
0x18002d113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d118  mov     ebx, eax
0x18002d11a  mov     [rbp+3Fh+var_80], eax
0x18002d11d  test    eax, eax
0x18002d11f  jns     short loc_18002D133
0x18002d121  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002d128  jz      short loc_18002D0E0
0x18002d12a  lea     r8, aIx509privateke_2; "IX509PrivateKey->put_ProviderName"
0x18002d131  jmp     short loc_18002D0CE
0x18002d133  mov     rcx, [rbp+3Fh+var_78]
0x18002d137  mov     rax, [rcx]
0x18002d13a  movzx   edx, r15w
0x18002d13e  mov     rax, [rax+160h]
0x18002d145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d14a  mov     ebx, eax
0x18002d14c  mov     [rbp+3Fh+var_80], eax
0x18002d14f  test    eax, eax
0x18002d151  jns     short loc_18002D168
0x18002d153  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002d15a  jz      short loc_18002D0E0
0x18002d15c  lea     r8, aIx509privateke_3; "IX509PrivateKey->put_MachineContext"
0x18002d163  jmp     loc_18002D0CE
0x18002d168  cmp     [rbp+3Fh+arg_20], 0
0x18002d16c  jz      short loc_18002D1A8
0x18002d16e  mov     rcx, [rbp+3Fh+var_78]
0x18002d172  mov     rax, [rcx]
0x18002d175  mov     edx, 3
0x18002d17a  mov     rax, [rax+130h]
0x18002d181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d186  mov     ebx, eax
0x18002d188  mov     [rbp+3Fh+var_80], eax
0x18002d18b  test    eax, eax
0x18002d18d  jns     short loc_18002D1A8
0x18002d18f  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002d196  jz      loc_18002D0E0
0x18002d19c  lea     r8, aIx509privateke; "IX509PrivateKey->put_ExportPolicy"
0x18002d1a3  jmp     loc_18002D0CE
0x18002d1a8  lea     rdx, aIx509privateke_0; "IX509PrivateKey->Create"
0x18002d1af  lea     rcx, [rbp+3Fh+var_50]; this
0x18002d1b3  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x18002d1b8  nop
0x18002d1b9  mov     rcx, [rbp+3Fh+var_78]
0x18002d1bd  mov     rax, [rcx]
0x18002d1c0  mov     rax, [rax+40h]
0x18002d1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1c9  mov     [rbp+3Fh+var_80], eax
0x18002d1cc  lea     rcx, [rbp+3Fh+var_50]; this
0x18002d1d0  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18002d1d5  mov     ebx, [rbp+3Fh+var_80]
0x18002d1d8  test    ebx, ebx
0x18002d1da  jns     short loc_18002D204
0x18002d1dc  cmp     ebx, 8009000Fh
0x18002d1e2  jz      loc_18002D0E0
0x18002d1e8  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 4
0x18002d1ef  jz      loc_18002D0E0
0x18002d1f5  mov     r9d, ebx
0x18002d1f8  lea     r8, aIx509privateke_5; "IX509PrivateKey->Create"
0x18002d1ff  jmp     loc_18002D0D1
0x18002d204  mov     rcx, [rbp+3Fh+var_78]
0x18002d208  mov     [rbp+3Fh+var_78], 0
0x18002d210  mov     rax, [rbp+3Fh+arg_30]
0x18002d214  mov     [rax], rcx
0x18002d217  lea     rcx, [rbp+3Fh+var_78]
0x18002d21b  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18002d220  nop
0x18002d221  lea     rcx, [rbp+3Fh+var_60]
0x18002d225  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d22a  nop
0x18002d22b  lea     rcx, [rbp+3Fh+var_68]
0x18002d22f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d234  nop
0x18002d235  lea     rcx, [rbp+3Fh+var_70]
0x18002d239  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d23e  xor     ebx, ebx
0x18002d240  lea     rcx, [rbp+3Fh+var_58]
0x18002d244  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18002d249  nop
0x18002d24a  lea     rcx, [rbp+3Fh+var_48]; this
0x18002d24e  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002d253  mov     eax, ebx
0x18002d255  add     rsp, 88h
0x18002d25c  pop     r15
0x18002d25e  pop     r14
0x18002d260  pop     rdi
0x18002d261  pop     rsi
0x18002d262  pop     rbx
0x18002d263  pop     rbp
0x18002d264  retn
```
