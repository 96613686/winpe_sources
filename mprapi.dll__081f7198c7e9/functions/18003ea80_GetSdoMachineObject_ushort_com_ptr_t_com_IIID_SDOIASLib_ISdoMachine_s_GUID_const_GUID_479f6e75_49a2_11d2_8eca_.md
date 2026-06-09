# GetSdoMachineObject(ushort *,_com_ptr_t<_com_IIID<SDOIASLib::ISdoMachine,&__s_GUID const _GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519>> &)

- ea: `0x18003ea80`
- end: `0x18003edb4`
- name: `?GetSdoMachineObject@@YAJPEAGAEAV?$_com_ptr_t@V?$_com_IIID@UISdoMachine@SDOIASLib@@$1?_GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519@@3U__s_GUID@@B@@@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPVOID *ppv)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c278`
- `0x18003efa0`

## callees

- `0x180037c8c`
- `0x180037d94`
- `0x18003ea80`
- `0x180050dbc`
- `0x180050e4c`
- `0x180050e60`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003eb19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003eb19`
- `OLEAUT32!__imp_SysStringLen` at `0x18003ec30`
- `OLEAUT32!__imp_SysStringLen` at `0x18003ec30`

## string_xrefs

- `0x18003eb44`: `SdoUtil::GetSdoMachineObject(): CoCreateInstance() returned exception %#x!`
- `0x18003ed40`: `SdoUtil::GetSdoMachineObject(): Failed with error %lx while trying to attach the ISdoMachine to the local computer!`

## pseudocode

```c
__int64 __fastcall GetSdoMachineObject(unsigned __int16 *a1, LPVOID *ppv)
{
  LPVOID *v2; // rsi
  OLECHAR *v3; // r15
  HRESULT Instance; // edi
  unsigned int v5; // r14d
  const wchar_t *v6; // rdx
  const wchar_t *v7; // rdx
  const wchar_t *v8; // r8
  __int64 v9; // rdx
  UINT v10; // eax
  struct IUnknown *v11; // rsi
  _bstr_t *v12; // rax
  _bstr_t *v13; // r15
  __int64 v14; // rdx
  int v15; // eax
  _bstr_t *v16; // rax
  __int64 v17; // rdx
  int v18; // eax
  HRESULT v20; // [rsp+30h] [rbp-888h]
  HRESULT v21; // [rsp+30h] [rbp-888h]
  int v22; // [rsp+34h] [rbp-884h]
  unsigned int v23; // [rsp+34h] [rbp-884h]
  unsigned __int16 *v24; // [rsp+38h] [rbp-880h] BYREF
  LPVOID *v25; // [rsp+40h] [rbp-878h]
  _DWORD v26[4]; // [rsp+48h] [rbp-870h] BYREF
  __int64 v27; // [rsp+58h] [rbp-860h]
  HLOCAL v28; // [rsp+60h] [rbp-858h]
  _DWORD v29[4]; // [rsp+68h] [rbp-850h] BYREF
  __int64 v30; // [rsp+78h] [rbp-840h]
  HLOCAL v31; // [rsp+80h] [rbp-838h]
  int v32; // [rsp+90h] [rbp-828h] BYREF
  _BYTE v33[2044]; // [rsp+94h] [rbp-824h] BYREF

  v2 = ppv;
  v3 = a1;
  v25 = ppv;
  v24 = a1;
  Instance = 0;
  v5 = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  if ( !*v2 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( *v2 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v2 + 16LL))(*v2);
      *v2 = 0;
      Instance = CoCreateInstance(&CLSID_SdoMachine, 0, 1u, &GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519, v2);
      v20 = Instance;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', (_com_error *)v26) )
      {
        v22 = v26[2];
        if ( v27 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        if ( v28 )
          LocalFree(v28);
        __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_18003EB27);
        v5 = v22;
        if ( v22 < 0 )
        {
          if ( !gIsSdoUtilEtwTracingAvailable || !(_QWORD)xmmword_180078BA0 )
            return v5;
          v6 = L"SdoUtil::GetSdoMachineObject(): CoCreateInstance() returned exception %#x!";
LABEL_10:
          LOWORD(v32) = 0;
          FormatRRASErrorString(&v32, v6, v5);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
            gSdoUtilEtwContext,
            xmmword_180078BA0,
            &v32);
          return v5;
        }
        Instance = v20;
        v2 = v25;
        v3 = v24;
      }
    }
    if ( Instance >= 0 )
    {
      if ( *v2 )
      {
        v10 = SysStringLen(v3);
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          v11 = (struct IUnknown *)*v2;
          if ( v10 )
          {
            if ( !v11 )
              _com_issue_error(-2147467261);
            v16 = _bstr_t::_bstr_t((_bstr_t *)&v24, v3);
            v13 = v16;
            v25 = (LPVOID *)v16;
            if ( *(_QWORD *)v16 )
              v17 = **(_QWORD **)v16;
            else
              v17 = 0;
            v18 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v11->lpVtbl[2].AddRef)(v11, v17);
            Instance = v18;
            if ( v18 < 0 )
              _com_issue_errorex(v18, v11, &GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519);
          }
          else
          {
            if ( !v11 )
              _com_issue_error(-2147467261);
            v12 = _bstr_t::_bstr_t((_bstr_t *)&v24, &word_180059138);
            v13 = v12;
            v25 = (LPVOID *)v12;
            if ( *(_QWORD *)v12 )
              v14 = **(_QWORD **)v12;
            else
              v14 = 0;
            v15 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v11->lpVtbl[2].AddRef)(v11, v14);
            Instance = v15;
            if ( v15 < 0 )
              _com_issue_errorex(v15, v11, &GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519);
          }
          _bstr_t::~_bstr_t(v13);
          v21 = Instance;
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &_com_error `RTTI Type Descriptor', (_com_error *)v29) )
          {
            v23 = v29[2];
            if ( v30 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            if ( v31 )
              LocalFree(v31);
            Instance = v21;
            v5 = v23;
            __eh34_try_continuation(2, &_com_error `RTTI Type Descriptor', &loc_18003ECE6);
          }
        }
        if ( (v5 & 0x80000000) != 0 )
        {
          if ( !gIsSdoUtilEtwTracingAvailable || !(_QWORD)xmmword_180078BA0 )
            return v5;
          v6 = L"SdoUtil::GetSdoMachineObject(): pSdoMachine->Attach() returned exception %#x!";
          goto LABEL_10;
        }
        if ( (int)(Instance + 0x80000000) < 0 || Instance == -2147467259 )
          return 0;
        if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
        {
          v7 = L"SdoUtil::GetSdoMachineObject(): Failed with error %lx while trying to attach the ISdoMachine to the local computer!";
          goto LABEL_17;
        }
      }
      else
      {
        Instance = -2147467261;
        if ( gIsSdoUtilEtwTracingAvailable )
        {
          v9 = xmmword_180078BA0;
          if ( (_QWORD)xmmword_180078BA0 )
          {
            v8 = L"SdoUtil::GetSdoMachineObject(): Received NULL ISdoMachine pointer!";
            goto LABEL_18;
          }
        }
      }
    }
    else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      v7 = L"SdoUtil::GetSdoMachineObject(): Failed with error %lx while trying to get an ISdoMachine pointer!";
LABEL_17:
      LOWORD(v32) = 0;
      FormatRRASErrorString(&v32, v7, (unsigned int)Instance);
      v8 = (const wchar_t *)&v32;
      v9 = xmmword_180078BA0;
LABEL_18:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
        gSdoUtilEtwContext,
        v9,
        v8);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003ea80  mov     [rsp+arg_10], rbx
0x18003ea85  mov     [rsp+arg_18], rsi
0x18003ea8a  push    rdi
0x18003ea8b  push    r14
0x18003ea8d  push    r15
0x18003ea8f  sub     rsp, 8A0h
0x18003ea96  mov     rax, cs:__security_cookie
0x18003ea9d  xor     rax, rsp
0x18003eaa0  mov     [rsp+8B8h+var_28], rax
0x18003eaa8  mov     rsi, rdx
0x18003eaab  mov     r15, rcx
0x18003eaae  mov     [rsp+8B8h+var_878], rdx
0x18003eab3  mov     [rsp+8B8h+var_880], rcx
0x18003eab8  xor     ebx, ebx
0x18003eaba  mov     edi, ebx
0x18003eabc  mov     [rsp+8B8h+var_888], ebx
0x18003eac0  mov     r14d, ebx
0x18003eac3  mov     [rsp+8B8h+var_828], ebx
0x18003eaca  xor     edx, edx; Val
0x18003eacc  mov     r8d, 7FCh; Size
0x18003ead2  lea     rcx, [rsp+8B8h+var_824]; void *
0x18003eada  call    memset_0
0x18003eadf  cmp     [rsi], rbx
0x18003eae2  jnz     loc_18003ED4E
0x18003eae8  mov     rcx, [rsi]
0x18003eaeb  test    rcx, rcx
0x18003eaee  jz      short loc_18003EAFD
0x18003eaf0  mov     rax, [rcx]
0x18003eaf3  mov     rax, [rax+10h]
0x18003eaf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eafc  nop
0x18003eafd  mov     [rsi], rbx
0x18003eb00  mov     [rsp+8B8h+ppv], rsi; ppv
0x18003eb05  lea     r9, _GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519; riid
0x18003eb0c  xor     edx, edx; pUnkOuter
0x18003eb0e  lea     r8d, [rdx+1]; dwClsContext
0x18003eb12  lea     rcx, CLSID_SdoMachine; rclsid
0x18003eb19  call    cs:__imp_CoCreateInstance
0x18003eb1f  mov     edi, eax
0x18003eb21  mov     [rsp+8B8h+var_888], eax
0x18003eb25  jmp     short loc_18003EB9B
0x18003eb27  mov     r14d, [rsp+8B8h+var_884]
0x18003eb2c  xor     ebx, ebx
0x18003eb2e  test    r14d, r14d
0x18003eb31  jns     short loc_18003EB8D
0x18003eb33  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003eb39  jz      short loc_18003EB85
0x18003eb3b  cmp     qword ptr cs:xmmword_180078BA0, rbx
0x18003eb42  jz      short loc_18003EB85
0x18003eb44  lea     rdx, aSdoutilGetsdom_0; "SdoUtil::GetSdoMachineObject(): CoCreat"...
0x18003eb4b  mov     r8d, r14d
0x18003eb4e  mov     word ptr [rsp+8B8h+var_828], bx
0x18003eb56  lea     rcx, [rsp+8B8h+var_828]
0x18003eb5e  call    FormatRRASErrorString
0x18003eb63  lea     r8, [rsp+8B8h+var_828]
0x18003eb6b  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003eb72  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003eb79  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003eb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb85  mov     edi, r14d
0x18003eb88  jmp     loc_18003ED4E
0x18003eb8d  mov     edi, [rsp+8B8h+var_888]
0x18003eb91  mov     rsi, [rsp+8B8h+var_878]
0x18003eb96  mov     r15, [rsp+8B8h+var_880]
0x18003eb9b  test    edi, edi
0x18003eb9d  jns     short loc_18003EBFE
0x18003eb9f  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003eba5  jz      loc_18003ED4E
0x18003ebab  cmp     qword ptr cs:xmmword_180078BA0, rbx
0x18003ebb2  jz      loc_18003ED4E
0x18003ebb8  lea     rdx, aSdoutilGetsdom_2; "SdoUtil::GetSdoMachineObject(): Failed "...
0x18003ebbf  mov     r8d, edi
0x18003ebc2  mov     word ptr [rsp+8B8h+var_828], bx
0x18003ebca  lea     rcx, [rsp+8B8h+var_828]
0x18003ebd2  call    FormatRRASErrorString
0x18003ebd7  lea     r8, [rsp+8B8h+var_828]
0x18003ebdf  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003ebe6  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003ebed  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ebf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebf9  jmp     loc_18003ED4E
0x18003ebfe  cmp     [rsi], rbx
0x18003ec01  jnz     short loc_18003EC2D
0x18003ec03  mov     edi, 80004003h
0x18003ec08  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003ec0e  jz      loc_18003ED4E
0x18003ec14  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003ec1b  test    rdx, rdx
0x18003ec1e  jz      loc_18003ED4E
0x18003ec24  lea     r8, aSdoutilGetsdom; "SdoUtil::GetSdoMachineObject(): Receive"...
0x18003ec2b  jmp     short loc_18003EBE6
0x18003ec2d  mov     rcx, r15; pbstr
0x18003ec30  call    cs:__imp_SysStringLen
0x18003ec36  nop
0x18003ec37  mov     rsi, [rsi]
0x18003ec3a  test    eax, eax
0x18003ec3c  jnz     short loc_18003EC8E
0x18003ec3e  test    rsi, rsi
0x18003ec41  jz      loc_18003ED79
0x18003ec47  lea     rdx, word_180059138; unsigned __int16 *
0x18003ec4e  lea     rcx, [rsp+8B8h+var_880]; this
0x18003ec53  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003ec58  mov     r15, rax
0x18003ec5b  mov     [rsp+8B8h+var_878], rax
0x18003ec60  mov     rax, [rsi]
0x18003ec63  mov     r8, [rax+38h]
0x18003ec67  mov     rax, [r15]
0x18003ec6a  test    rax, rax
0x18003ec6d  jz      short loc_18003EC74
0x18003ec6f  mov     rdx, [rax]
0x18003ec72  jmp     short loc_18003EC77
0x18003ec74  mov     rdx, rbx
0x18003ec77  mov     rcx, rsi
0x18003ec7a  mov     rax, r8
0x18003ec7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec82  mov     edi, eax
0x18003ec84  test    eax, eax
0x18003ec86  js      loc_18003ED84
0x18003ec8c  jmp     short loc_18003ECD8
0x18003ec8e  test    rsi, rsi
0x18003ec91  jz      loc_18003ED96
0x18003ec97  mov     rdx, r15; unsigned __int16 *
0x18003ec9a  lea     rcx, [rsp+8B8h+var_880]; this
0x18003ec9f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003eca4  mov     r15, rax
0x18003eca7  mov     [rsp+8B8h+var_878], rax
0x18003ecac  mov     rax, [rsi]
0x18003ecaf  mov     r8, [rax+38h]
0x18003ecb3  mov     rax, [r15]
0x18003ecb6  test    rax, rax
0x18003ecb9  jz      short loc_18003ECC0
0x18003ecbb  mov     rdx, [rax]
0x18003ecbe  jmp     short loc_18003ECC3
0x18003ecc0  mov     rdx, rbx
0x18003ecc3  mov     rcx, rsi
0x18003ecc6  mov     rax, r8
0x18003ecc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecce  mov     edi, eax
0x18003ecd0  test    eax, eax
0x18003ecd2  js      loc_18003EDA1
0x18003ecd8  mov     rcx, r15; this
0x18003ecdb  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003ece0  mov     [rsp+8B8h+var_888], edi
0x18003ece4  jmp     short loc_18003ECF1
0x18003ece6  xor     ebx, ebx
0x18003ece8  mov     edi, [rsp+8B8h+var_888]
0x18003ecec  mov     r14d, [rsp+8B8h+var_884]
0x18003ecf1  test    r14d, r14d
0x18003ecf4  jns     short loc_18003ED1B
0x18003ecf6  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003ecfc  jz      loc_18003EB85
0x18003ed02  cmp     qword ptr cs:xmmword_180078BA0, rbx
0x18003ed09  jz      loc_18003EB85
0x18003ed0f  lea     rdx, aSdoutilGetsdom_1; "SdoUtil::GetSdoMachineObject(): pSdoMac"...
0x18003ed16  jmp     loc_18003EB4B
0x18003ed1b  mov     ecx, 80000000h
0x18003ed20  lea     eax, [rdi+rcx]
0x18003ed23  test    ecx, eax
0x18003ed25  jnz     short loc_18003ED4C
0x18003ed27  cmp     edi, 80004005h
0x18003ed2d  jz      short loc_18003ED4C
0x18003ed2f  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003ed35  jz      short loc_18003ED4E
0x18003ed37  cmp     qword ptr cs:xmmword_180078BA0, rbx
0x18003ed3e  jz      short loc_18003ED4E
0x18003ed40  lea     rdx, aSdoutilGetsdom_3; "SdoUtil::GetSdoMachineObject(): Failed "...
0x18003ed47  jmp     loc_18003EBBF
0x18003ed4c  mov     edi, ebx
0x18003ed4e  mov     eax, edi
0x18003ed50  mov     rcx, [rsp+8B8h+var_28]
0x18003ed58  xor     rcx, rsp; StackCookie
0x18003ed5b  call    __security_check_cookie
0x18003ed60  lea     r11, [rsp+8B8h+var_18]
0x18003ed68  mov     rbx, [r11+30h]
0x18003ed6c  mov     rsi, [r11+38h]
0x18003ed70  mov     rsp, r11
0x18003ed73  pop     r15
0x18003ed75  pop     r14
0x18003ed77  pop     rdi
0x18003ed78  retn
0x18003ed79  mov     ecx, 80004003h; int
0x18003ed7e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003ed84  lea     r8, _GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519; struct _GUID *
0x18003ed8b  mov     rdx, rsi; struct IUnknown *
0x18003ed8e  mov     ecx, eax; int
0x18003ed90  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18003ed96  mov     ecx, 80004003h; int
0x18003ed9b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003eda1  lea     r8, _GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519; struct _GUID *
0x18003eda8  mov     rdx, rsi; struct IUnknown *
0x18003edab  mov     ecx, eax; int
0x18003edad  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
