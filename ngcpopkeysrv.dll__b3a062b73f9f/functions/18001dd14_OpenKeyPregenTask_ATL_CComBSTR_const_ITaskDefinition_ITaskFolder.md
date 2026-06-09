# OpenKeyPregenTask(ATL::CComBSTR const &,ITaskDefinition * *,ITaskFolder * *)

- ea: `0x18001dd14`
- end: `0x18001df9c`
- name: `?OpenKeyPregenTask@@YAJAEBVCComBSTR@ATL@@PEAPEAUITaskDefinition@@PEAPEAUITaskFolder@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(const struct ATL::CComBSTR *, struct ITaskDefinition **, struct ITaskFolder **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d764`

## callees

- `0x18000b0fc`
- `0x18001d6c8`
- `0x18001d730`
- `0x18001dd14`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ddb3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ddb3`
- `OLEAUT32!__imp_SysAllocString` at `0x18001dd47`
- `OLEAUT32!__imp_SysAllocString` at `0x18001dd47`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dd7e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dd7e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df7b`

## string_xrefs

- `0x18001dd40`: `\Microsoft\Windows\CertificateServicesClient`
- `0x18001dd6a`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001de1b`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001de60`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001deac`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001def5`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall OpenKeyPregenTask(
        const struct ATL::CComBSTR *a1,
        struct ITaskDefinition **a2,
        struct ITaskFolder **a3)
{
  unsigned __int16 *v6; // rax
  HRESULT v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  struct ITaskFolder *v14; // rcx
  struct ITaskDefinition *v15; // rcx
  int ppv; // [rsp+20h] [rbp-69h]
  int *ppva; // [rsp+20h] [rbp-69h]
  __int64 v18; // [rsp+30h] [rbp-59h] BYREF
  struct ITaskDefinition *v19; // [rsp+38h] [rbp-51h] BYREF
  LPVOID v20; // [rsp+40h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-41h] BYREF
  int v22[4]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v23; // [rsp+60h] [rbp-29h]
  __int128 v24; // [rsp+70h] [rbp-19h] BYREF
  __int64 v25; // [rsp+80h] [rbp-9h]
  __int128 v26; // [rsp+90h] [rbp+7h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+17h]
  __int128 v28; // [rsp+B0h] [rbp+27h] BYREF
  __int64 v29; // [rsp+C0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  struct ITaskFolder *v31; // [rsp+108h] [rbp+7Fh] BYREF

  bstrString = 0;
  v6 = SysAllocString(L"\\Microsoft\\Windows\\CertificateServicesClient");
  ATL::CComBSTR::Attach((ATL::CComBSTR *)&bstrString, v6);
  if ( !bstrString )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)0x8009000ELL,
      ppv);
    SysFreeString(0);
    return 2148073486LL;
  }
  v20 = 0;
  v8 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v20);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 99;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)(unsigned int)v8,
      (int)ppva);
    goto LABEL_23;
  }
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  ppva = v22;
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v20 + 80LL))(
         v20,
         &v28,
         &v26,
         &v24);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 108;
    goto LABEL_7;
  }
  v31 = 0;
  v11 = (*(__int64 (__fastcall **)(LPVOID, BSTR, struct ITaskFolder **))(*(_QWORD *)v20 + 56LL))(v20, bstrString, &v31);
  v9 = v11;
  if ( v11 >= 0 )
  {
    v18 = 0;
    v12 = ((__int64 (__fastcall *)(struct ITaskFolder *, _QWORD, __int64 *))v31->lpVtbl->GetTask)(
            v31,
            *(_QWORD *)a1,
            &v18);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v19 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, struct ITaskDefinition **))(*(_QWORD *)v18 + 152LL))(v18, &v19);
      v9 = v13;
      if ( v13 >= 0 )
      {
        v14 = v31;
        if ( v31 && a3 )
        {
          *a3 = v31;
          ((void (__fastcall *)(struct ITaskFolder *))v14->lpVtbl->AddRef)(v14);
        }
        v15 = v19;
        if ( v19 )
        {
          if ( a2 )
          {
            *a2 = v19;
            ((void (__fastcall *)(struct ITaskDefinition *))v15->lpVtbl->AddRef)(v15);
          }
        }
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v19);
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v18);
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v31);
        v9 = 0;
        goto LABEL_23;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
        (const char *)(unsigned int)v13,
        (int)v22);
      wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v19);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
        (const char *)(unsigned int)v12,
        (int)v22);
    }
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v18);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)(unsigned int)v11,
      (int)v22);
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v31);
LABEL_23:
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v20);
  SysFreeString(bstrString);
  return v9;
}

```

## disassembly

```asm
0x18001dd14  mov     [rsp-8+arg_0], rsi
0x18001dd19  mov     [rsp-8+arg_8], rdi
0x18001dd1e  push    rbp
0x18001dd1f  push    r14
0x18001dd21  push    r15
0x18001dd23  lea     rbp, [rsp-47h]
0x18001dd28  sub     rsp, 0D0h
0x18001dd2f  mov     rsi, r8
0x18001dd32  mov     r14, rdx
0x18001dd35  mov     r15, rcx
0x18001dd38  mov     [rbp+57h+bstrString], 0
0x18001dd40  lea     rcx, aMicrosoftWindo; "\\Microsoft\\Windows\\CertificateServic"...
0x18001dd47  call    cs:__imp_SysAllocString
0x18001dd4d  mov     rdx, rax; unsigned __int16 *
0x18001dd50  lea     rcx, [rbp+57h+bstrString]; this
0x18001dd54  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x18001dd59  cmp     [rbp+57h+bstrString], 0
0x18001dd5e  jnz     short loc_18001DD8E
0x18001dd60  mov     rcx, [rbp+5Fh]; this
0x18001dd64  mov     r9d, 8009000Eh; char *
0x18001dd6a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001dd71  mov     edx, 5Ah ; 'Z'; void *
0x18001dd76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dd7b  nop
0x18001dd7c  xor     ecx, ecx; bstrString
0x18001dd7e  call    cs:__imp_SysFreeString
0x18001dd84  mov     eax, 8009000Eh
0x18001dd89  jmp     loc_18001DF83
0x18001dd8e  mov     [rbp+57h+var_A0], 0
0x18001dd96  lea     rax, [rbp+57h+var_A0]
0x18001dd9a  mov     [rsp+0E0h+ppv], rax; ppv
0x18001dd9f  lea     r9, IID_ITaskService; riid
0x18001dda6  xor     edx, edx; pUnkOuter
0x18001dda8  lea     r8d, [rdx+1]; dwClsContext
0x18001ddac  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001ddb3  call    cs:__imp_CoCreateInstance
0x18001ddb9  mov     edi, eax
0x18001ddbb  test    eax, eax
0x18001ddbd  jns     short loc_18001DDC6
0x18001ddbf  mov     edx, 63h ; 'c'
0x18001ddc4  jmp     short loc_18001DE1B
0x18001ddc6  xorps   xmm1, xmm1
0x18001ddc9  xor     eax, eax
0x18001ddcb  mov     rcx, [rbp+57h+var_A0]
0x18001ddcf  movaps  xmmword ptr [rbp+57h+var_90], xmm1
0x18001ddd3  mov     [rbp+57h+var_80], rax
0x18001ddd7  movaps  [rbp+57h+var_70], xmm1
0x18001dddb  mov     [rbp+57h+var_60], rax
0x18001dddf  movaps  [rbp+57h+var_50], xmm1
0x18001dde3  mov     [rbp+57h+var_40], rax
0x18001dde7  movaps  [rbp+57h+var_30], xmm1
0x18001ddeb  mov     [rbp+57h+var_20], rax
0x18001ddef  mov     rax, [rcx]
0x18001ddf2  lea     rdx, [rbp+57h+var_90]
0x18001ddf6  mov     [rsp+0E0h+ppv], rdx; int
0x18001ddfb  lea     r9, [rbp+57h+var_70]
0x18001ddff  lea     r8, [rbp+57h+var_50]
0x18001de03  lea     rdx, [rbp+57h+var_30]
0x18001de07  mov     rax, [rax+50h]
0x18001de0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de10  mov     edi, eax
0x18001de12  test    eax, eax
0x18001de14  jns     short loc_18001DE33
0x18001de16  mov     edx, 6Ch ; 'l'; void *
0x18001de1b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001de22  mov     r9d, eax; char *
0x18001de25  mov     rcx, [rbp+5Fh]; this
0x18001de29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de2e  jmp     loc_18001DF6D
0x18001de33  mov     [rbp+57h+arg_18], 0
0x18001de3b  mov     rcx, [rbp+57h+var_A0]
0x18001de3f  mov     rax, [rcx]
0x18001de42  lea     r8, [rbp+57h+arg_18]
0x18001de46  mov     rdx, [rbp+57h+bstrString]
0x18001de4a  mov     rax, [rax+38h]
0x18001de4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de53  mov     edi, eax
0x18001de55  test    eax, eax
0x18001de57  jns     short loc_18001DE80
0x18001de59  mov     rcx, [rbp+5Fh]; this
0x18001de5d  mov     r9d, eax; char *
0x18001de60  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001de67  mov     edx, 74h ; 't'; void *
0x18001de6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de71  nop
0x18001de72  lea     rcx, [rbp+57h+arg_18]
0x18001de76  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001de7b  jmp     loc_18001DF6D
0x18001de80  mov     [rbp+57h+var_B0], 0
0x18001de88  mov     rcx, [rbp+57h+arg_18]
0x18001de8c  mov     rax, [rcx]
0x18001de8f  lea     r8, [rbp+57h+var_B0]
0x18001de93  mov     rdx, [r15]
0x18001de96  mov     rax, [rax+68h]
0x18001de9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de9f  mov     edi, eax
0x18001dea1  test    eax, eax
0x18001dea3  jns     short loc_18001DEC9
0x18001dea5  mov     rcx, [rbp+5Fh]; this
0x18001dea9  mov     r9d, eax; char *
0x18001deac  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001deb3  mov     edx, 7Ah ; 'z'; void *
0x18001deb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001debd  nop
0x18001debe  lea     rcx, [rbp+57h+var_B0]
0x18001dec2  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001dec7  jmp     short loc_18001DE72
0x18001dec9  mov     [rbp+57h+var_A8], 0
0x18001ded1  mov     rcx, [rbp+57h+var_B0]
0x18001ded5  mov     rax, [rcx]
0x18001ded8  lea     rdx, [rbp+57h+var_A8]
0x18001dedc  mov     rax, [rax+98h]
0x18001dee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dee8  mov     edi, eax
0x18001deea  test    eax, eax
0x18001deec  jns     short loc_18001DF12
0x18001deee  mov     rcx, [rbp+5Fh]; this
0x18001def2  mov     r9d, eax; char *
0x18001def5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001defc  mov     edx, 80h; void *
0x18001df01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df06  nop
0x18001df07  lea     rcx, [rbp+57h+var_A8]
0x18001df0b  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001df10  jmp     short loc_18001DEBE
0x18001df12  mov     rcx, [rbp+57h+arg_18]
0x18001df16  test    rcx, rcx
0x18001df19  jz      short loc_18001DF30
0x18001df1b  test    rsi, rsi
0x18001df1e  jz      short loc_18001DF30
0x18001df20  mov     [rsi], rcx
0x18001df23  mov     rax, [rcx]
0x18001df26  mov     rax, [rax+8]
0x18001df2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df2f  nop
0x18001df30  mov     rcx, [rbp+57h+var_A8]
0x18001df34  test    rcx, rcx
0x18001df37  jz      short loc_18001DF4E
0x18001df39  test    r14, r14
0x18001df3c  jz      short loc_18001DF4E
0x18001df3e  mov     [r14], rcx
0x18001df41  mov     rax, [rcx]
0x18001df44  mov     rax, [rax+8]
0x18001df48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df4d  nop
0x18001df4e  lea     rcx, [rbp+57h+var_A8]
0x18001df52  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001df57  nop
0x18001df58  lea     rcx, [rbp+57h+var_B0]
0x18001df5c  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001df61  nop
0x18001df62  lea     rcx, [rbp+57h+arg_18]
0x18001df66  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001df6b  xor     edi, edi
0x18001df6d  lea     rcx, [rbp+57h+var_A0]
0x18001df71  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001df76  nop
0x18001df77  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001df7b  call    cs:__imp_SysFreeString
0x18001df81  mov     eax, edi
0x18001df83  lea     r11, [rsp+0E0h+var_10]
0x18001df8b  mov     rsi, [r11+20h]
0x18001df8f  mov     rdi, [r11+28h]
0x18001df93  mov     rsp, r11
0x18001df96  pop     r15
0x18001df98  pop     r14
0x18001df9a  pop     rbp
0x18001df9b  retn
```
