# AikEnrollTask::GetTrigger(_TASK_TRIGGER_TYPE2,bool,ITrigger * *)

- ea: `0x180015abc`
- end: `0x1800160fa`
- name: `?GetTrigger@AikEnrollTask@@QEAAJW4_TASK_TRIGGER_TYPE2@@_NPEAPEAUITrigger@@@Z`
- size: `1598`
- prototype: `__int64 __fastcall(BSTR *this, unsigned int, char, struct ITrigger **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800154ec`
- `0x1800161f4`
- `0x180016570`

## callees

- `0x180008ab0`
- `0x18000cc34`
- `0x180011814`
- `0x180015abc`
- `0x18001c724`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015c16`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015c16`
- `OLEAUT32!__imp_SysAllocString` at `0x180015aff`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b44`
- `OLEAUT32!__imp_SysAllocString` at `0x180015bb3`
- `OLEAUT32!__imp_SysAllocString` at `0x180015aff`
- `OLEAUT32!__imp_SysAllocString` at `0x180015b44`
- `OLEAUT32!__imp_SysAllocString` at `0x180015bb3`
- `OLEAUT32!__imp_SysFreeString` at `0x180015b7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ec3`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ef6`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f85`
- `OLEAUT32!__imp_SysFreeString` at `0x18001605c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800160a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800160b4`
- `OLEAUT32!__imp_SysFreeString` at `0x180015b7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ec3`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ef6`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f85`
- `OLEAUT32!__imp_SysFreeString` at `0x18001605c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800160a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800160b4`

## string_xrefs

- `0x180015b3d`: `\Microsoft\Windows\CertificateServicesClient`
- `0x180015af8`: `AIKCertEnrollTask`
- `0x180015b21`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015b68`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015bda`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015c29`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015c98`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015cd5`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015d18`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015d5d`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015d9f`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015de8`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015f3c`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015f6f`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015fad`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015fdd`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180016027`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x1800160ca`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
__int64 __fastcall AikEnrollTask::GetTrigger(BSTR *this, unsigned int a2, char a3, struct ITrigger **a4)
{
  unsigned __int16 *v6; // rax
  unsigned int v7; // esi
  unsigned __int16 *v9; // rax
  OLECHAR *v10; // rcx
  const OLECHAR *v11; // r12
  OLECHAR *v12; // rbx
  unsigned __int16 *v13; // rax
  OLECHAR *v14; // rcx
  HRESULT v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // r15d
  struct ITrigger *v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  const unsigned __int16 *v27; // r8
  int v28; // eax
  int v29; // eax
  int ppv; // [rsp+28h] [rbp-99h]
  int ppva; // [rsp+28h] [rbp-99h]
  struct ITrigger *v32; // [rsp+38h] [rbp-89h] BYREF
  LPVOID v33; // [rsp+40h] [rbp-81h] BYREF
  __int64 v34; // [rsp+48h] [rbp-79h] BYREF
  int v35; // [rsp+50h] [rbp-71h] BYREF
  int v36; // [rsp+54h] [rbp-6Dh] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-69h] BYREF
  BSTR v38; // [rsp+60h] [rbp-61h] BYREF
  BSTR v39; // [rsp+68h] [rbp-59h] BYREF
  int v40[4]; // [rsp+78h] [rbp-49h] BYREF
  __int64 v41; // [rsp+88h] [rbp-39h]
  __int128 v42; // [rsp+98h] [rbp-29h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-19h]
  __int128 v44; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v45; // [rsp+C8h] [rbp+7h]
  __int128 v46; // [rsp+D8h] [rbp+17h] BYREF
  __int64 v47; // [rsp+E8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  *a4 = 0;
  if ( *this )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
      (const char *)0x800704DFLL,
      ppv);
    return 2147943647LL;
  }
  else
  {
    v6 = SysAllocString(L"AIKCertEnrollTask");
    ATL::CComBSTR::Attach(this, v6);
    if ( !*this )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)0x8007000ELL,
        ppv);
      return v7;
    }
    v38 = 0;
    v9 = SysAllocString(L"\\Microsoft\\Windows\\CertificateServicesClient");
    ATL::CComBSTR::Attach(&v38, v9);
    if ( !v38 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11C,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)0x8007000ELL,
        ppv);
      v10 = 0;
LABEL_7:
      SysFreeString(v10);
      return v7;
    }
    v11 = 0;
    if ( a2 == 1 )
    {
      v11 = L"RetryTrigger";
    }
    else if ( a2 == 9 )
    {
      v11 = L"LogonTrigger";
    }
    v12 = 0;
    v39 = 0;
    if ( v11 )
    {
      v13 = SysAllocString(v11);
      ATL::CComBSTR::Attach(&v39, v13);
      v12 = v39;
      if ( !v39 )
      {
        v7 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
          (const char *)0x8007000ELL,
          ppv);
        v14 = 0;
LABEL_54:
        SysFreeString(v14);
        v10 = v38;
        goto LABEL_7;
      }
    }
    v33 = 0;
    v15 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v33);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v15,
        ppva);
LABEL_53:
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v33);
      v14 = v12;
      goto LABEL_54;
    }
    *(_OWORD *)v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v16 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v33 + 80LL))(
            v33,
            &v46,
            &v44,
            &v42);
    v7 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v16,
        (int)v40);
      goto LABEL_53;
    }
    v17 = (*(__int64 (__fastcall **)(LPVOID, BSTR, char *))(*(_QWORD *)v33 + 56LL))(v33, v38, (char *)this + 8);
    v7 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v17,
        (int)v40);
      goto LABEL_53;
    }
    v34 = 0;
    v18 = (*(__int64 (__fastcall **)(BSTR, BSTR, __int64 *))(*(_QWORD *)this[1] + 104LL))(this[1], *this, &v34);
    v7 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v18,
        (int)v40);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
      goto LABEL_53;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v34 + 152LL))(v34, (char *)this + 16);
    v7 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x151,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v19,
        (int)v40);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
      goto LABEL_53;
    }
    v20 = (*(__int64 (__fastcall **)(BSTR, char *))(*(_QWORD *)this[2] + 72LL))(this[2], (char *)this + 24);
    v7 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v20,
        (int)v40);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
      goto LABEL_53;
    }
    v35 = 0;
    v21 = (*(__int64 (__fastcall **)(BSTR, int *))(*(_QWORD *)this[3] + 56LL))(this[3], &v35);
    v7 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v21,
        (int)v40);
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
      goto LABEL_53;
    }
    v32 = 0;
    v22 = 1;
    v23 = 0;
    while ( v22 <= v35 )
    {
      v24 = (*(__int64 (__fastcall **)(BSTR, _QWORD, struct ITrigger **))(*(_QWORD *)this[3] + 64LL))(
              this[3],
              (unsigned int)v22,
              &v32);
      v7 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x164,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
          (const char *)(unsigned int)v24,
          (int)v40);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v32);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
        goto LABEL_53;
      }
      v23 = v32;
      if ( v32 )
      {
        v36 = 0;
        v25 = ((__int64 (__fastcall *)(struct ITrigger *, int *))v32->lpVtbl->get_Type)(v32, &v36);
        v7 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16A,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
            (const char *)(unsigned int)v25,
            (int)v40);
          ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v32);
          ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
          goto LABEL_53;
        }
        if ( v36 == a2 )
        {
          bstrString = 0;
          v26 = ((__int64 (__fastcall *)(struct ITrigger *, BSTR *))v32->lpVtbl->get_Id)(v32, &bstrString);
          v7 = v26;
          if ( v26 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x170,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
              (const char *)(unsigned int)v26,
              (int)v40);
            SysFreeString(bstrString);
            ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v32);
            ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
            goto LABEL_53;
          }
          if ( !v12 || bstrString && NgcUtils::AreStringsEqual(bstrString, v11, v27) )
          {
            *((_DWORD *)this + 8) = v22;
            SysFreeString(bstrString);
            v23 = v32;
            break;
          }
          SysFreeString(bstrString);
        }
        v23 = v32;
        if ( v32 )
        {
          ((void (__fastcall *)(struct ITrigger *))v32->lpVtbl->Release)(v32);
          v23 = 0;
          v32 = 0;
        }
      }
      ++v22;
    }
    if ( v23 )
      goto LABEL_56;
    if ( a3 )
    {
      v28 = (*(__int64 (__fastcall **)(BSTR, _QWORD, struct ITrigger **))(*(_QWORD *)this[3] + 80LL))(this[3], a2, &v32);
      v7 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x186,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
          (const char *)(unsigned int)v28,
          (int)v40);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v32);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
        goto LABEL_53;
      }
      v29 = ((__int64 (__fastcall *)(struct ITrigger *, OLECHAR *))v32->lpVtbl->put_Id)(v32, v12);
      v7 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18A,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
          (const char *)(unsigned int)v29,
          (int)v40);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v32);
        ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
        goto LABEL_53;
      }
      v23 = v32;
      if ( v32 )
      {
LABEL_56:
        v32 = 0;
        *a4 = v23;
      }
    }
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v32);
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v34);
    ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v33);
    SysFreeString(v12);
    SysFreeString(v38);
    return 0;
  }
}

```

## disassembly

```asm
0x180015abc  mov     rax, rsp
0x180015abf  mov     [rax+8], rbx
0x180015ac3  mov     [rax+10h], rsi
0x180015ac7  mov     [rax+20h], r9
0x180015acb  mov     [rax+18h], r8b
0x180015acf  push    rbp
0x180015ad0  push    r12
0x180015ad2  push    r13
0x180015ad4  push    r14
0x180015ad6  push    r15
0x180015ad8  lea     rbp, [rax-5Fh]
0x180015adc  sub     rsp, 0F0h
0x180015ae3  mov     r13d, edx
0x180015ae6  mov     r14, rcx
0x180015ae9  xor     r15d, r15d
0x180015aec  mov     [r9], r15
0x180015aef  cmp     [rcx], r15
0x180015af2  jnz     loc_1800160BE
0x180015af8  lea     rcx, aAikcertenrollt; "AIKCertEnrollTask"
0x180015aff  call    cs:__imp_SysAllocString
0x180015b05  mov     rdx, rax; unsigned __int16 *
0x180015b08  mov     rcx, r14; this
0x180015b0b  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180015b10  cmp     [r14], r15
0x180015b13  jnz     short loc_180015B39
0x180015b15  mov     rcx, [rbp+5Fh]; this
0x180015b19  mov     esi, 8007000Eh
0x180015b1e  mov     r9d, esi; char *
0x180015b21  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015b28  mov     edx, 118h; void *
0x180015b2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b32  mov     eax, esi
0x180015b34  jmp     loc_1800160DD
0x180015b39  mov     [rbp+57h+var_B8], r15
0x180015b3d  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\CertificateServic"...
0x180015b44  call    cs:__imp_SysAllocString
0x180015b4a  mov     rdx, rax; unsigned __int16 *
0x180015b4d  lea     rcx, [rbp+57h+var_B8]; this
0x180015b51  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180015b56  cmp     [rbp+57h+var_B8], r15
0x180015b5a  jnz     short loc_180015B84
0x180015b5c  mov     rcx, [rbp+5Fh]; this
0x180015b60  mov     esi, 8007000Eh
0x180015b65  mov     r9d, esi; char *
0x180015b68  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015b6f  mov     edx, 11Ch; void *
0x180015b74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b79  nop
0x180015b7a  xor     ecx, ecx; bstrString
0x180015b7c  call    cs:__imp_SysFreeString
0x180015b82  jmp     short loc_180015B32
0x180015b84  mov     r12, r15
0x180015b87  mov     ecx, r13d
0x180015b8a  sub     ecx, 1
0x180015b8d  jz      short loc_180015B9D
0x180015b8f  cmp     ecx, 8
0x180015b92  jnz     short loc_180015BA4
0x180015b94  lea     r12, aLogontrigger; "LogonTrigger"
0x180015b9b  jmp     short loc_180015BA4
0x180015b9d  lea     r12, aRetrytrigger; "RetryTrigger"
0x180015ba4  mov     rbx, r15
0x180015ba7  mov     [rbp+57h+var_B0], rbx
0x180015bab  test    r12, r12
0x180015bae  jz      short loc_180015BF3
0x180015bb0  mov     rcx, r12; psz
0x180015bb3  call    cs:__imp_SysAllocString
0x180015bb9  mov     rdx, rax; unsigned __int16 *
0x180015bbc  lea     rcx, [rbp+57h+var_B0]; this
0x180015bc0  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180015bc5  mov     rbx, [rbp+57h+var_B0]
0x180015bc9  test    rbx, rbx
0x180015bcc  jnz     short loc_180015BF3
0x180015bce  mov     rcx, [rbp+5Fh]; this
0x180015bd2  mov     esi, 8007000Eh
0x180015bd7  mov     r9d, esi; char *
0x180015bda  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015be1  mov     edx, 12Ch; void *
0x180015be6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015beb  nop
0x180015bec  xor     ecx, ecx
0x180015bee  jmp     loc_18001605C
0x180015bf3  mov     [rsp+110h+var_D8], r15
0x180015bf8  lea     rax, [rsp+110h+var_D8]
0x180015bfd  mov     qword ptr [rsp+110h+ppv], rax; int
0x180015c02  lea     r9, IID_ITaskService; riid
0x180015c09  xor     edx, edx; pUnkOuter
0x180015c0b  lea     r8d, [rdx+1]; dwClsContext
0x180015c0f  lea     rcx, CLSID_TaskScheduler; rclsid
0x180015c16  call    cs:__imp_CoCreateInstance
0x180015c1c  mov     esi, eax
0x180015c1e  test    eax, eax
0x180015c20  jns     short loc_180015C40
0x180015c22  mov     rcx, [rbp+5Fh]; this
0x180015c26  mov     r9d, eax; char *
0x180015c29  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015c30  mov     edx, 136h; void *
0x180015c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015c3a  nop
0x180015c3b  jmp     loc_18001604E
0x180015c40  xorps   xmm1, xmm1
0x180015c43  xor     eax, eax
0x180015c45  mov     rcx, [rsp+110h+var_D8]
0x180015c4a  movaps  xmmword ptr [rbp+57h+var_A0], xmm1
0x180015c4e  mov     [rbp+57h+var_90], rax
0x180015c52  movaps  [rbp+57h+var_80], xmm1
0x180015c56  mov     [rbp+57h+var_70], rax
0x180015c5a  movaps  [rbp+57h+var_60], xmm1
0x180015c5e  mov     [rbp+57h+var_50], rax
0x180015c62  movaps  [rbp+57h+var_40], xmm1
0x180015c66  mov     [rbp+57h+var_30], rax
0x180015c6a  mov     rax, [rcx]
0x180015c6d  lea     rdx, [rbp+57h+var_A0]
0x180015c71  mov     qword ptr [rsp+110h+ppv], rdx; int
0x180015c76  lea     r9, [rbp+57h+var_80]
0x180015c7a  lea     r8, [rbp+57h+var_60]
0x180015c7e  lea     rdx, [rbp+57h+var_40]
0x180015c82  mov     rax, [rax+50h]
0x180015c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c8b  mov     esi, eax
0x180015c8d  test    eax, eax
0x180015c8f  jns     short loc_180015CAF
0x180015c91  mov     rcx, [rbp+5Fh]; this
0x180015c95  mov     r9d, eax; char *
0x180015c98  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015c9f  mov     edx, 13Fh; void *
0x180015ca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ca9  nop
0x180015caa  jmp     loc_18001604E
0x180015caf  mov     rcx, [rsp+110h+var_D8]
0x180015cb4  mov     rax, [rcx]
0x180015cb7  lea     r8, [r14+8]
0x180015cbb  mov     rdx, [rbp+57h+var_B8]
0x180015cbf  mov     rax, [rax+38h]
0x180015cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cc8  mov     esi, eax
0x180015cca  test    eax, eax
0x180015ccc  jns     short loc_180015CEC
0x180015cce  mov     rcx, [rbp+5Fh]; this
0x180015cd2  mov     r9d, eax; char *
0x180015cd5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015cdc  mov     edx, 146h; void *
0x180015ce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ce6  nop
0x180015ce7  jmp     loc_18001604E
0x180015cec  mov     [rbp+57h+var_D0], 0
0x180015cf4  mov     rcx, [r14+8]
0x180015cf8  mov     rax, [rcx]
0x180015cfb  lea     r8, [rbp+57h+var_D0]
0x180015cff  mov     rdx, [r14]
0x180015d02  mov     rax, [rax+68h]
0x180015d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d0b  mov     esi, eax
0x180015d0d  test    eax, eax
0x180015d0f  jns     short loc_180015D39
0x180015d11  mov     rcx, [rbp+5Fh]; this
0x180015d15  mov     r9d, eax; char *
0x180015d18  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015d1f  mov     edx, 14Ch; void *
0x180015d24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015d29  nop
0x180015d2a  lea     rcx, [rbp+57h+var_D0]
0x180015d2e  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180015d33  nop
0x180015d34  jmp     loc_18001604E
0x180015d39  mov     rcx, [rbp+57h+var_D0]
0x180015d3d  mov     rax, [rcx]
0x180015d40  lea     rdx, [r14+10h]
0x180015d44  mov     rax, [rax+98h]
0x180015d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d50  mov     esi, eax
0x180015d52  test    eax, eax
0x180015d54  jns     short loc_180015D7E
0x180015d56  mov     rcx, [rbp+5Fh]; this
0x180015d5a  mov     r9d, eax; char *
0x180015d5d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015d64  mov     edx, 151h; void *
0x180015d69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015d6e  nop
0x180015d6f  lea     rcx, [rbp+57h+var_D0]
0x180015d73  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180015d78  nop
0x180015d79  jmp     loc_18001604E
0x180015d7e  mov     rcx, [r14+10h]
0x180015d82  mov     rax, [rcx]
0x180015d85  lea     rdx, [r14+18h]
0x180015d89  mov     rax, [rax+48h]
0x180015d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d92  mov     esi, eax
0x180015d94  test    eax, eax
0x180015d96  jns     short loc_180015DC0
0x180015d98  mov     rcx, [rbp+5Fh]; this
0x180015d9c  mov     r9d, eax; char *
0x180015d9f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015da6  mov     edx, 156h; void *
0x180015dab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015db0  nop
0x180015db1  lea     rcx, [rbp+57h+var_D0]
0x180015db5  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180015dba  nop
0x180015dbb  jmp     loc_18001604E
0x180015dc0  mov     [rbp+57h+var_C8], 0
0x180015dc7  mov     rcx, [r14+18h]
0x180015dcb  mov     rax, [rcx]
0x180015dce  lea     rdx, [rbp+57h+var_C8]
0x180015dd2  mov     rax, [rax+38h]
0x180015dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ddb  mov     esi, eax
0x180015ddd  test    eax, eax
0x180015ddf  jns     short loc_180015E09
0x180015de1  mov     rcx, [rbp+5Fh]; this
0x180015de5  mov     r9d, eax; char *
0x180015de8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015def  mov     edx, 15Dh; void *
0x180015df4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015df9  nop
0x180015dfa  lea     rcx, [rbp+57h+var_D0]
0x180015dfe  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180015e03  nop
0x180015e04  jmp     loc_18001604E
0x180015e09  mov     [rsp+110h+var_E0], 0
0x180015e12  mov     r15d, 1
0x180015e18  mov     rcx, [rsp+110h+var_E0]
0x180015e1d  cmp     r15d, [rbp+57h+var_C8]
0x180015e21  jg      loc_180015F01
0x180015e27  mov     rcx, [r14+18h]
0x180015e2b  mov     rax, [rcx]
0x180015e2e  lea     r8, [rsp+110h+var_E0]
0x180015e33  mov     edx, r15d
0x180015e36  mov     rax, [rax+40h]
0x180015e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e3f  mov     esi, eax
0x180015e41  test    eax, eax
0x180015e43  js      loc_180015FD6
0x180015e49  mov     rcx, [rsp+110h+var_E0]
0x180015e4e  test    rcx, rcx
0x180015e51  jz      loc_180015EE6
0x180015e57  mov     [rbp+57h+var_C4], 0
0x180015e5e  mov     rax, [rcx]
0x180015e61  lea     rdx, [rbp+57h+var_C4]
0x180015e65  mov     rax, [rax+38h]
0x180015e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e6e  mov     esi, eax
0x180015e70  test    eax, eax
0x180015e72  js      loc_180015FA6
0x180015e78  cmp     [rbp+57h+var_C4], r13d
0x180015e7c  jnz     short loc_180015EC9
0x180015e7e  mov     [rbp+57h+bstrString], 0
0x180015e86  mov     rcx, [rsp+110h+var_E0]
0x180015e8b  mov     rax, [rcx]
0x180015e8e  lea     rdx, [rbp+57h+bstrString]
0x180015e92  mov     rax, [rax+40h]
0x180015e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e9b  mov     esi, eax
0x180015e9d  test    eax, eax
0x180015e9f  js      loc_180015F68
0x180015ea5  test    rbx, rbx
0x180015ea8  jz      short loc_180015EEE
0x180015eaa  mov     rcx, [rbp+57h+bstrString]; this
0x180015eae  test    rcx, rcx
0x180015eb1  jz      short loc_180015EBF
0x180015eb3  mov     rdx, r12; unsigned __int16 *
0x180015eb6  call    ?AreStringsEqual@NgcUtils@@YA_NPEBG0@Z; NgcUtils::AreStringsEqual(ushort const *,ushort const *)
0x180015ebb  test    al, al
0x180015ebd  jnz     short loc_180015EEE
0x180015ebf  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180015ec3  call    cs:__imp_SysFreeString
0x180015ec9  mov     rcx, [rsp+110h+var_E0]
0x180015ece  test    rcx, rcx
0x180015ed1  jz      short loc_180015EE6
0x180015ed3  mov     rax, [rcx]
0x180015ed6  mov     rax, [rax+10h]
0x180015eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015edf  xor     ecx, ecx
0x180015ee1  mov     [rsp+110h+var_E0], rcx
0x180015ee6  inc     r15d
0x180015ee9  jmp     loc_180015E1D
0x180015eee  mov     [r14+20h], r15d
0x180015ef2  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180015ef6  call    cs:__imp_SysFreeString
0x180015efc  mov     rcx, [rsp+110h+var_E0]
0x180015f01  test    rcx, rcx
0x180015f04  jnz     loc_180016076
0x180015f0a  cmp     [rbp+57h+arg_10], cl
0x180015f0d  jz      loc_180016086
0x180015f13  mov     rcx, [r14+18h]
0x180015f17  mov     rax, [rcx]
0x180015f1a  lea     r8, [rsp+110h+var_E0]
0x180015f1f  mov     edx, r13d
0x180015f22  mov     rax, [rax+50h]
0x180015f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f2b  mov     esi, eax
0x180015f2d  test    eax, eax
0x180015f2f  jns     loc_180016006
0x180015f35  mov     rcx, [rbp+5Fh]; this
0x180015f39  mov     r9d, eax; char *
0x180015f3c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015f43  mov     edx, 186h; void *
0x180015f48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f4d  nop
0x180015f4e  lea     rcx, [rsp+110h+var_E0]
  ... truncated ...
```
