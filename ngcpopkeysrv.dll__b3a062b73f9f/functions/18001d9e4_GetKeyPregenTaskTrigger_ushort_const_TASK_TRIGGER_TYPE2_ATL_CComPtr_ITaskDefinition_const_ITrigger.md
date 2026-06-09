# GetKeyPregenTaskTrigger(ushort const *,_TASK_TRIGGER_TYPE2,ATL::CComPtr<ITaskDefinition> const &,ITrigger * *)

- ea: `0x18001d9e4`
- end: `0x18001dc54`
- name: `?GetKeyPregenTaskTrigger@@YAJPEBGW4_TASK_TRIGGER_TYPE2@@AEBV?$CComPtr@UITaskDefinition@@@ATL@@PEAPEAUITrigger@@@Z`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d764`

## callees

- `0x18000b0fc`
- `0x180015000`
- `0x18001d6c8`
- `0x18001d730`
- `0x18001d9e4`
- `0x180028010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001da12`
- `OLEAUT32!__imp_SysAllocString` at `0x18001da12`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da49`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db5d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db85`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dbda`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc38`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da49`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db5d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db85`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dbda`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc38`

## string_xrefs

- `0x18001da35`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001daa7`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001dba0`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001dbc4`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`
- `0x18001dbee`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetKeyPregenTaskTrigger(const OLECHAR *a1, int a2, _QWORD *a3, _QWORD *a4)
{
  unsigned __int16 *v7; // rax
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  int i; // edi
  int v14; // esi
  int v15; // eax
  const unsigned __int16 *v16; // r8
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-30h] BYREF
  __int64 v19; // [rsp+28h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+38h] [rbp-18h] BYREF
  BSTR v22[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v24; // [rsp+88h] [rbp+38h] BYREF

  *a4 = 0;
  v22[0] = 0;
  v7 = SysAllocString(a1);
  ATL::CComBSTR::Attach((ATL::CComBSTR *)v22, v7);
  if ( !v22[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)0x8009000ELL,
      v18);
    SysFreeString(0);
    return 2148073486LL;
  }
  v21 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 72LL))(*a3, &v21);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 161;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)(unsigned int)v9,
      v18);
    goto LABEL_29;
  }
  v24 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 56LL))(v21, &v24);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 166;
    goto LABEL_7;
  }
  v12 = 0;
  v19 = 0;
  for ( i = 1; ; ++i )
  {
    if ( i > v24 )
      goto LABEL_21;
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 64LL))(v21, (unsigned int)i, &v19);
    if ( v14 < 0 )
    {
      v17 = 174;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
        (const char *)(unsigned int)v14,
        v18);
LABEL_27:
      wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v19);
      v10 = v14;
      goto LABEL_29;
    }
    v12 = v19;
    if ( !v19 )
      continue;
    v18 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 56LL))(v19, &v18);
    if ( v14 < 0 )
    {
      v17 = 181;
      goto LABEL_26;
    }
    if ( v18 == a2 )
      break;
LABEL_17:
    v12 = v19;
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v12 = 0;
      v19 = 0;
    }
  }
  bstrString = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 64LL))(v19, &bstrString);
  v14 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)(unsigned int)v15,
      v18);
    SysFreeString(bstrString);
    goto LABEL_27;
  }
  if ( !NgcUtils::AreStringsEqual((NgcUtils *)v22[0], bstrString, v16) )
  {
    SysFreeString(bstrString);
    goto LABEL_17;
  }
  SysFreeString(bstrString);
  v12 = v19;
LABEL_21:
  if ( v12 )
  {
    *a4 = v12;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v19);
    v10 = 0;
  }
  else
  {
    v10 = -2146893779;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)0x8009002DLL,
      v18);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v19);
  }
LABEL_29:
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v21);
  SysFreeString(v22[0]);
  return v10;
}

```

## disassembly

```asm
0x18001d9e4  mov     [rsp-18h+arg_0], rsi
0x18001d9e9  mov     [rsp-18h+arg_8], rdi
0x18001d9ee  push    rbp
0x18001d9ef  push    r14
0x18001d9f1  push    r15
0x18001d9f3  mov     rbp, rsp
0x18001d9f6  sub     rsp, 50h
0x18001d9fa  mov     r15, r9
0x18001d9fd  mov     rdi, r8
0x18001da00  mov     r14d, edx
0x18001da03  mov     qword ptr [r9], 0
0x18001da0a  mov     [rbp+var_10], 0
0x18001da12  call    cs:__imp_SysAllocString
0x18001da18  mov     rdx, rax; unsigned __int16 *
0x18001da1b  lea     rcx, [rbp+var_10]; this
0x18001da1f  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x18001da24  cmp     [rbp+var_10], 0
0x18001da29  jnz     short loc_18001DA59
0x18001da2b  mov     rcx, [rbp+18h]; this
0x18001da2f  mov     r9d, 8009000Eh; char *
0x18001da35  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001da3c  mov     edx, 9Bh; void *
0x18001da41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da46  nop
0x18001da47  xor     ecx, ecx; bstrString
0x18001da49  call    cs:__imp_SysFreeString
0x18001da4f  mov     eax, 8009000Eh
0x18001da54  jmp     loc_18001DC40
0x18001da59  mov     [rbp+var_18], 0
0x18001da61  mov     rcx, [rdi]
0x18001da64  mov     rax, [rcx]
0x18001da67  lea     rdx, [rbp+var_18]
0x18001da6b  mov     rax, [rax+48h]
0x18001da6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da74  mov     edi, eax
0x18001da76  test    eax, eax
0x18001da78  jns     short loc_18001DA81
0x18001da7a  mov     edx, 0A1h
0x18001da7f  jmp     short loc_18001DAA7
0x18001da81  mov     [rbp+arg_18], 0
0x18001da88  mov     rcx, [rbp+var_18]
0x18001da8c  mov     rax, [rcx]
0x18001da8f  lea     rdx, [rbp+arg_18]
0x18001da93  mov     rax, [rax+38h]
0x18001da97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da9c  mov     edi, eax
0x18001da9e  test    eax, eax
0x18001daa0  jns     short loc_18001DABF
0x18001daa2  mov     edx, 0A6h; void *
0x18001daa7  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001daae  mov     r9d, eax; char *
0x18001dab1  mov     rcx, [rbp+18h]; this
0x18001dab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001daba  jmp     loc_18001DC2A
0x18001dabf  xor     ecx, ecx
0x18001dac1  mov     [rbp+var_28], rcx
0x18001dac5  lea     edi, [rcx+1]
0x18001dac8  cmp     edi, [rbp+arg_18]
0x18001dacb  jg      loc_18001DB8F
0x18001dad1  mov     rcx, [rbp+var_18]
0x18001dad5  mov     rax, [rcx]
0x18001dad8  lea     r8, [rbp+var_28]
0x18001dadc  mov     edx, edi
0x18001dade  mov     rax, [rax+40h]
0x18001dae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dae7  mov     esi, eax
0x18001dae9  test    eax, eax
0x18001daeb  js      loc_18001DBE9
0x18001daf1  mov     rcx, [rbp+var_28]
0x18001daf5  test    rcx, rcx
0x18001daf8  jz      loc_18001DB7E
0x18001dafe  mov     [rbp+var_30], 0
0x18001db05  mov     rax, [rcx]
0x18001db08  lea     rdx, [rbp+var_30]
0x18001db0c  mov     rax, [rax+38h]
0x18001db10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db15  mov     esi, eax
0x18001db17  test    eax, eax
0x18001db19  js      loc_18001DBE2
0x18001db1f  cmp     [rbp+var_30], r14d
0x18001db23  jnz     short loc_18001DB63
0x18001db25  mov     [rbp+bstrString], 0
0x18001db2d  mov     rcx, [rbp+var_28]
0x18001db31  mov     rax, [rcx]
0x18001db34  lea     rdx, [rbp+bstrString]
0x18001db38  mov     rax, [rax+40h]
0x18001db3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db41  mov     esi, eax
0x18001db43  test    eax, eax
0x18001db45  js      short loc_18001DBBD
0x18001db47  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18001db4b  mov     rcx, [rbp+var_10]; this
0x18001db4f  call    ?AreStringsEqual@NgcUtils@@YA_NPEBG0@Z; NgcUtils::AreStringsEqual(ushort const *,ushort const *)
0x18001db54  nop
0x18001db55  mov     rcx, [rbp+bstrString]; bstrString
0x18001db59  test    al, al
0x18001db5b  jnz     short loc_18001DB85
0x18001db5d  call    cs:__imp_SysFreeString
0x18001db63  mov     rcx, [rbp+var_28]
0x18001db67  test    rcx, rcx
0x18001db6a  jz      short loc_18001DB7E
0x18001db6c  mov     rax, [rcx]
0x18001db6f  mov     rax, [rax+10h]
0x18001db73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db78  xor     ecx, ecx
0x18001db7a  mov     [rbp+var_28], rcx
0x18001db7e  inc     edi
0x18001db80  jmp     loc_18001DAC8
0x18001db85  call    cs:__imp_SysFreeString
0x18001db8b  mov     rcx, [rbp+var_28]
0x18001db8f  test    rcx, rcx
0x18001db92  jnz     short loc_18001DC0F
0x18001db94  mov     rcx, [rbp+18h]; this
0x18001db98  mov     edi, 8009002Dh
0x18001db9d  mov     r9d, edi; char *
0x18001dba0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001dba7  mov     edx, 0CBh; void *
0x18001dbac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dbb1  nop
0x18001dbb2  lea     rcx, [rbp+var_28]
0x18001dbb6  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001dbbb  jmp     short loc_18001DC2A
0x18001dbbd  mov     rcx, [rbp+18h]; this
0x18001dbc1  mov     r9d, esi; char *
0x18001dbc4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001dbcb  mov     edx, 0BBh; void *
0x18001dbd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dbd5  nop
0x18001dbd6  mov     rcx, [rbp+bstrString]; bstrString
0x18001dbda  call    cs:__imp_SysFreeString
0x18001dbe0  jmp     short loc_18001DC02
0x18001dbe2  mov     edx, 0B5h
0x18001dbe7  jmp     short loc_18001DBEE
0x18001dbe9  mov     edx, 0AEh; void *
0x18001dbee  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001dbf5  mov     r9d, esi; char *
0x18001dbf8  mov     rcx, [rbp+18h]; this
0x18001dbfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc01  nop
0x18001dc02  lea     rcx, [rbp+var_28]
0x18001dc06  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001dc0b  mov     edi, esi
0x18001dc0d  jmp     short loc_18001DC2A
0x18001dc0f  mov     [r15], rcx
0x18001dc12  mov     rax, [rcx]
0x18001dc15  mov     rax, [rax+8]
0x18001dc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc1e  nop
0x18001dc1f  lea     rcx, [rbp+var_28]
0x18001dc23  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001dc28  xor     edi, edi
0x18001dc2a  lea     rcx, [rbp+var_18]
0x18001dc2e  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001dc33  nop
0x18001dc34  mov     rcx, [rbp+var_10]; bstrString
0x18001dc38  call    cs:__imp_SysFreeString
0x18001dc3e  mov     eax, edi
0x18001dc40  mov     rsi, [rsp+50h+arg_0]
0x18001dc45  mov     rdi, [rsp+50h+arg_8]
0x18001dc4a  add     rsp, 50h
0x18001dc4e  pop     r15
0x18001dc50  pop     r14
0x18001dc52  pop     rbp
0x18001dc53  retn
```
