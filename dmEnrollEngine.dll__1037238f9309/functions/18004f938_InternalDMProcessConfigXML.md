# InternalDMProcessConfigXML

- ea: `0x18004f938`
- end: `0x18004fc94`
- name: `InternalDMProcessConfigXML`
- size: `860`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004ff88`

## callees

- `0x18000dd20`
- `0x18000e508`
- `0x1800128c4`
- `0x1800140d0`
- `0x18004e210`
- `0x18004e2f8`
- `0x18004e314`
- `0x18004f938`
- `0x180051dd0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f9c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f9c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc38`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc38`
- `OLEAUT32!__imp_SysFreeString` at `0x18004fc4a`

## string_xrefs

- `0x18004fb42`: `OMADM::TargetedUserSID`
- `0x18004f986`: `InternalDMProcessConfigXML`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InternalDMProcessConfigXML(
        __int64 a1,
        BSTR *a2,
        const wchar_t *a3,
        _WORD *a4,
        _WORD *a5,
        __int16 a6)
{
  _OWORD *v10; // rcx
  _OWORD *v11; // rdx
  _OWORD *v12; // rcx
  _OWORD *v13; // rcx
  const wchar_t *v14; // rax
  _OWORD *v15; // rcx
  _OWORD *v16; // rcx
  unsigned int v17; // ebx
  __int64 v18; // rdx
  HRESULT v20; // [rsp+30h] [rbp-79h] BYREF
  __int128 v21; // [rsp+38h] [rbp-71h] BYREF
  _OWORD *v22; // [rsp+48h] [rbp-61h] BYREF
  _OWORD *v23; // [rsp+50h] [rbp-59h]
  _OWORD *v24; // [rsp+58h] [rbp-51h]
  LPVOID ppv; // [rsp+60h] [rbp-49h] BYREF
  BSTR bstrString[2]; // [rsp+68h] [rbp-41h] BYREF
  BSTR v27; // [rsp+78h] [rbp-31h]
  _BYTE v28[8]; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v29[2]; // [rsp+88h] [rbp-21h] BYREF
  __int128 v30; // [rsp+98h] [rbp-11h] BYREF
  unsigned int v31[4]; // [rsp+A8h] [rbp-1h] BYREF

  v20 = 0;
  v30 = 0;
  *(_OWORD *)v31 = 0;
  *(_OWORD *)bstrString = 0;
  v27 = 0;
  ppv = 0;
  utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>(&v22);
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v28, "InternalDMProcessConfigXML");
  v29[0] = "InternalDMProcessConfigXML";
  v29[1] = &v20;
  v20 = CoCreateInstance(
          &GUID_f4477ad6_6b3a_411b_9ecc_7ce89b665401,
          0,
          1u,
          &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
          &ppv);
  if ( v20 < 0 )
    goto LABEL_37;
  *(_QWORD *)&v21 = L"OMADM::WapEnrollmentProvisioning";
  *((_QWORD *)&v21 + 1) = L"True";
  v10 = v23;
  v11 = v24;
  if ( v23 == v24 )
  {
    if ( !(unsigned __int8)utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(
                             &v22,
                             &v21) )
      goto LABEL_36;
    v11 = v24;
    v12 = v23;
  }
  else
  {
    *v23 = v21;
    v12 = v10 + 1;
    v23 = v12;
  }
  *(_QWORD *)&v21 = L"OMADM::ServerID";
  *((_QWORD *)&v21 + 1) = a3;
  if ( v12 == v11 )
  {
    if ( !(unsigned __int8)utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(
                             &v22,
                             &v21) )
      goto LABEL_36;
    a3 = (const wchar_t *)*((_QWORD *)&v21 + 1);
    v11 = v24;
    v13 = v23;
  }
  else
  {
    *v12 = v21;
    v13 = v12 + 1;
    v23 = v13;
  }
  *(_QWORD *)&v21 = L"OMADM::Integrity";
  if ( a6 == 0x4000 )
  {
    v14 = L"SYSTEM";
  }
  else
  {
    v14 = L"MEDIUM";
    if ( a6 != 0x2000 )
      v14 = a3;
  }
  *((_QWORD *)&v21 + 1) = v14;
  if ( v13 == v11 )
  {
    if ( !(unsigned __int8)utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(
                             &v22,
                             &v21) )
      goto LABEL_36;
    v11 = v24;
    v15 = v23;
  }
  else
  {
    *v13 = v21;
    v15 = v13 + 1;
    v23 = v15;
  }
  if ( !a4 || !*a4 )
  {
    v20 = -2147024809;
    goto LABEL_37;
  }
  *(_QWORD *)&v21 = L"OMADM::AccountID";
  *((_QWORD *)&v21 + 1) = a4;
  if ( v15 == v11 )
  {
    if ( !(unsigned __int8)utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(
                             &v22,
                             &v21) )
      goto LABEL_36;
    v11 = v24;
    v16 = v23;
  }
  else
  {
    *v15 = v21;
    v16 = v15 + 1;
    v23 = v16;
  }
  if ( a5 && *a5 )
  {
    *(_QWORD *)&v21 = L"OMADM::TargetedUserSID";
    *((_QWORD *)&v21 + 1) = a5;
    if ( v16 != v11 )
    {
      *v16++ = v21;
      v23 = v16;
      goto LABEL_30;
    }
    if ( (unsigned __int8)utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(
                            &v22,
                            &v21) )
    {
      v16 = v23;
      goto LABEL_30;
    }
LABEL_36:
    v20 = -2147024882;
    goto LABEL_37;
  }
LABEL_30:
  if ( v22 == v16 || (*(_QWORD *)&v31[2] = v22, v20 = ULongLongToULong(v16 - v22, v31), v20 >= 0) )
  {
    v20 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, &v30, 32);
    if ( v20 >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, a1, 0, 0, 0);
      v20 = (*(__int64 (__fastcall **)(LPVOID, BSTR *, __int64))(*(_QWORD *)ppv + 40LL))(ppv, bstrString, 24);
      if ( v20 >= 0 )
      {
        *a2 = bstrString[0];
        bstrString[0] = 0;
        v20 = (HRESULT)bstrString[1];
      }
    }
  }
LABEL_37:
  SysFreeString(bstrString[0]);
  bstrString[0] = 0;
  SysFreeString(v27);
  v27 = 0;
  v17 = v20;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v29, v18);
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v28);
  utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_Uninit(&v22);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&ppv);
  return v17;
}

```

## disassembly

```asm
0x18004f938  push    rbp
0x18004f93a  push    rbx
0x18004f93b  push    rsi
0x18004f93c  push    rdi
0x18004f93d  push    r14
0x18004f93f  push    r15
0x18004f941  lea     rbp, [rsp-1Fh]
0x18004f946  sub     rsp, 0C8h
0x18004f94d  mov     rdi, r9
0x18004f950  mov     rbx, r8
0x18004f953  mov     rsi, rdx
0x18004f956  mov     r14, rcx
0x18004f959  mov     [rbp+47h+var_C0], 0
0x18004f960  xorps   xmm0, xmm0
0x18004f963  movups  [rbp+47h+var_58], xmm0
0x18004f967  movups  xmmword ptr [rbp+47h+var_48], xmm0
0x18004f96b  xorps   xmm1, xmm1
0x18004f96e  xor     eax, eax
0x18004f970  movups  xmmword ptr [rbp+47h+bstrString], xmm1
0x18004f974  mov     [rbp+47h+var_78], rax
0x18004f978  mov     [rbp+47h+var_90], rax
0x18004f97c  lea     rcx, [rbp+47h+var_A8]
0x18004f980  call    ??0?$vector@UtagWAPAttribute@@V?$allocator@UtagWAPAttribute@@@utl@@@utl@@QEAA@XZ; utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>(void)
0x18004f985  nop
0x18004f986  lea     r15, aInternaldmproc; "InternalDMProcessConfigXML"
0x18004f98d  mov     rdx, r15; char *
0x18004f990  lea     rcx, [rbp+47h+var_70]; this
0x18004f994  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x18004f999  nop
0x18004f99a  mov     [rbp+47h+var_68], r15
0x18004f99e  lea     rax, [rbp+47h+var_C0]
0x18004f9a2  mov     [rbp+47h+var_60], rax
0x18004f9a6  lea     rax, [rbp+47h+var_90]
0x18004f9aa  mov     [rsp+0F0h+ppv], rax; ppv
0x18004f9af  lea     r9, _GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd; riid
0x18004f9b6  xor     edx, edx; pUnkOuter
0x18004f9b8  lea     r8d, [rdx+1]; dwClsContext
0x18004f9bc  lea     rcx, _GUID_f4477ad6_6b3a_411b_9ecc_7ce89b665401; rclsid
0x18004f9c3  call    cs:__imp_CoCreateInstance
0x18004f9c9  mov     [rbp+47h+var_C0], eax
0x18004f9cc  test    eax, eax
0x18004f9ce  js      loc_18004FC34
0x18004f9d4  lea     rax, aOmadmWapenroll; "OMADM::WapEnrollmentProvisioning"
0x18004f9db  mov     qword ptr [rbp+47h+var_B8], rax
0x18004f9df  lea     rax, aTrue_0; "True"
0x18004f9e6  mov     qword ptr [rbp+47h+var_B8+8], rax
0x18004f9ea  mov     rcx, [rbp+47h+var_A0]
0x18004f9ee  mov     rdx, [rbp+47h+var_98]
0x18004f9f2  cmp     rcx, rdx
0x18004f9f5  jz      short loc_18004FA09
0x18004f9f7  movups  xmm0, [rbp+47h+var_B8]
0x18004f9fb  movdqu  xmmword ptr [rcx], xmm0
0x18004f9ff  add     rcx, 10h
0x18004fa03  mov     [rbp+47h+var_A0], rcx
0x18004fa07  jmp     short loc_18004FA26
0x18004fa09  lea     rdx, [rbp+47h+var_B8]
0x18004fa0d  lea     rcx, [rbp+47h+var_A8]
0x18004fa11  call    ??$_PushBackOne2@AEBUtagWAPAttribute@@@?$vector@UtagWAPAttribute@@V?$allocator@UtagWAPAttribute@@@utl@@@utl@@AEAA_NAEBUtagWAPAttribute@@@Z; utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(tagWAPAttribute const &)
0x18004fa16  test    al, al
0x18004fa18  jz      loc_18004FC2D
0x18004fa1e  mov     rdx, [rbp+47h+var_98]
0x18004fa22  mov     rcx, [rbp+47h+var_A0]
0x18004fa26  lea     rax, aOmadmServerid; "OMADM::ServerID"
0x18004fa2d  mov     qword ptr [rbp+47h+var_B8], rax
0x18004fa31  mov     qword ptr [rbp+47h+var_B8+8], rbx
0x18004fa35  cmp     rcx, rdx
0x18004fa38  jz      short loc_18004FA4C
0x18004fa3a  movups  xmm0, [rbp+47h+var_B8]
0x18004fa3e  movdqu  xmmword ptr [rcx], xmm0
0x18004fa42  add     rcx, 10h
0x18004fa46  mov     [rbp+47h+var_A0], rcx
0x18004fa4a  jmp     short loc_18004FA6D
0x18004fa4c  lea     rdx, [rbp+47h+var_B8]
0x18004fa50  lea     rcx, [rbp+47h+var_A8]
0x18004fa54  call    ??$_PushBackOne2@AEBUtagWAPAttribute@@@?$vector@UtagWAPAttribute@@V?$allocator@UtagWAPAttribute@@@utl@@@utl@@AEAA_NAEBUtagWAPAttribute@@@Z; utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(tagWAPAttribute const &)
0x18004fa59  test    al, al
0x18004fa5b  jz      loc_18004FC2D
0x18004fa61  mov     rbx, qword ptr [rbp+47h+var_B8+8]
0x18004fa65  mov     rdx, [rbp+47h+var_98]
0x18004fa69  mov     rcx, [rbp+47h+var_A0]
0x18004fa6d  lea     rax, aOmadmIntegrity; "OMADM::Integrity"
0x18004fa74  mov     qword ptr [rbp+47h+var_B8], rax
0x18004fa78  mov     eax, 4000h
0x18004fa7d  cmp     ax, [rbp+47h+arg_28]
0x18004fa81  jnz     short loc_18004FA8C
0x18004fa83  lea     rax, aSystem; "SYSTEM"
0x18004fa8a  jmp     short loc_18004FAA2
0x18004fa8c  lea     rax, aMedium; "MEDIUM"
0x18004fa93  mov     r8d, 2000h
0x18004fa99  cmp     r8w, [rbp+47h+arg_28]
0x18004fa9e  cmovnz  rax, rbx
0x18004faa2  mov     qword ptr [rbp+47h+var_B8+8], rax
0x18004faa6  cmp     rcx, rdx
0x18004faa9  jz      short loc_18004FABD
0x18004faab  movups  xmm0, [rbp+47h+var_B8]
0x18004faaf  movdqu  xmmword ptr [rcx], xmm0
0x18004fab3  add     rcx, 10h
0x18004fab7  mov     [rbp+47h+var_A0], rcx
0x18004fabb  jmp     short loc_18004FADA
0x18004fabd  lea     rdx, [rbp+47h+var_B8]
0x18004fac1  lea     rcx, [rbp+47h+var_A8]
0x18004fac5  call    ??$_PushBackOne2@AEBUtagWAPAttribute@@@?$vector@UtagWAPAttribute@@V?$allocator@UtagWAPAttribute@@@utl@@@utl@@AEAA_NAEBUtagWAPAttribute@@@Z; utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(tagWAPAttribute const &)
0x18004faca  test    al, al
0x18004facc  jz      loc_18004FC2D
0x18004fad2  mov     rdx, [rbp+47h+var_98]
0x18004fad6  mov     rcx, [rbp+47h+var_A0]
0x18004fada  test    rdi, rdi
0x18004fadd  jz      loc_18004FC24
0x18004fae3  xor     eax, eax
0x18004fae5  cmp     ax, [rdi]
0x18004fae8  jz      loc_18004FC24
0x18004faee  lea     rax, aOmadmAccountid; "OMADM::AccountID"
0x18004faf5  mov     qword ptr [rbp+47h+var_B8], rax
0x18004faf9  mov     qword ptr [rbp+47h+var_B8+8], rdi
0x18004fafd  cmp     rcx, rdx
0x18004fb00  jz      short loc_18004FB14
0x18004fb02  movups  xmm0, [rbp+47h+var_B8]
0x18004fb06  movdqu  xmmword ptr [rcx], xmm0
0x18004fb0a  add     rcx, 10h
0x18004fb0e  mov     [rbp+47h+var_A0], rcx
0x18004fb12  jmp     short loc_18004FB31
0x18004fb14  lea     rdx, [rbp+47h+var_B8]
0x18004fb18  lea     rcx, [rbp+47h+var_A8]
0x18004fb1c  call    ??$_PushBackOne2@AEBUtagWAPAttribute@@@?$vector@UtagWAPAttribute@@V?$allocator@UtagWAPAttribute@@@utl@@@utl@@AEAA_NAEBUtagWAPAttribute@@@Z; utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(tagWAPAttribute const &)
0x18004fb21  test    al, al
0x18004fb23  jz      loc_18004FC2D
0x18004fb29  mov     rdx, [rbp+47h+var_98]
0x18004fb2d  mov     rcx, [rbp+47h+var_A0]
0x18004fb31  mov     r8, [rbp+47h+arg_20]
0x18004fb35  test    r8, r8
0x18004fb38  jz      short loc_18004FB81
0x18004fb3a  xor     eax, eax
0x18004fb3c  cmp     ax, [r8]
0x18004fb40  jz      short loc_18004FB81
0x18004fb42  lea     rax, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x18004fb49  mov     qword ptr [rbp+47h+var_B8], rax
0x18004fb4d  mov     qword ptr [rbp+47h+var_B8+8], r8
0x18004fb51  cmp     rcx, rdx
0x18004fb54  jz      short loc_18004FB68
0x18004fb56  movups  xmm0, [rbp+47h+var_B8]
0x18004fb5a  movdqu  xmmword ptr [rcx], xmm0
0x18004fb5e  add     rcx, 10h
0x18004fb62  mov     [rbp+47h+var_A0], rcx
0x18004fb66  jmp     short loc_18004FB81
0x18004fb68  lea     rdx, [rbp+47h+var_B8]
0x18004fb6c  lea     rcx, [rbp+47h+var_A8]
0x18004fb70  call    ??$_PushBackOne2@AEBUtagWAPAttribute@@@?$vector@UtagWAPAttribute@@V?$allocator@UtagWAPAttribute@@@utl@@@utl@@AEAA_NAEBUtagWAPAttribute@@@Z; utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_PushBackOne2<tagWAPAttribute const &>(tagWAPAttribute const &)
0x18004fb75  test    al, al
0x18004fb77  jz      loc_18004FC2D
0x18004fb7d  mov     rcx, [rbp+47h+var_A0]
0x18004fb81  mov     rax, [rbp+47h+var_A8]
0x18004fb85  cmp     rax, rcx
0x18004fb88  jz      short loc_18004FBA9
0x18004fb8a  mov     qword ptr [rbp+47h+var_48+8], rax
0x18004fb8e  sub     rcx, rax
0x18004fb91  sar     rcx, 4; unsigned __int64
0x18004fb95  lea     rdx, [rbp+47h+var_48]; unsigned int *
0x18004fb99  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004fb9e  mov     [rbp+47h+var_C0], eax
0x18004fba1  test    eax, eax
0x18004fba3  js      loc_18004FC34
0x18004fba9  mov     rcx, [rbp+47h+var_90]
0x18004fbad  mov     rax, [rcx]
0x18004fbb0  mov     r8d, 20h ; ' '
0x18004fbb6  lea     rdx, [rbp+47h+var_58]
0x18004fbba  mov     rax, [rax+18h]
0x18004fbbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbc3  mov     [rbp+47h+var_C0], eax
0x18004fbc6  test    eax, eax
0x18004fbc8  js      short loc_18004FC34
0x18004fbca  mov     rcx, [rbp+47h+var_90]
0x18004fbce  mov     rax, [rcx]
0x18004fbd1  mov     [rsp+0F0h+ppv], 0
0x18004fbda  xor     r9d, r9d
0x18004fbdd  xor     r8d, r8d
0x18004fbe0  mov     rdx, r14
0x18004fbe3  mov     rax, [rax+20h]
0x18004fbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbec  mov     rcx, [rbp+47h+var_90]
0x18004fbf0  mov     rax, [rcx]
0x18004fbf3  mov     r8d, 18h
0x18004fbf9  lea     rdx, [rbp+47h+bstrString]
0x18004fbfd  mov     rax, [rax+28h]
0x18004fc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc06  mov     [rbp+47h+var_C0], eax
0x18004fc09  test    eax, eax
0x18004fc0b  js      short loc_18004FC34
0x18004fc0d  mov     rax, [rbp+47h+bstrString]
0x18004fc11  mov     [rsi], rax
0x18004fc14  mov     [rbp+47h+bstrString], 0
0x18004fc1c  mov     eax, dword ptr [rbp+47h+bstrString+8]
0x18004fc1f  mov     [rbp+47h+var_C0], eax
0x18004fc22  jmp     short loc_18004FC34
0x18004fc24  mov     [rbp+47h+var_C0], 80070057h
0x18004fc2b  jmp     short loc_18004FC34
0x18004fc2d  mov     [rbp+47h+var_C0], 8007000Eh
0x18004fc34  mov     rcx, [rbp+47h+bstrString]; bstrString
0x18004fc38  call    cs:__imp_SysFreeString
0x18004fc3e  mov     [rbp+47h+bstrString], 0
0x18004fc46  mov     rcx, [rbp+47h+var_78]; bstrString
0x18004fc4a  call    cs:__imp_SysFreeString
0x18004fc50  mov     [rbp+47h+var_78], 0
0x18004fc58  mov     ebx, [rbp+47h+var_C0]
0x18004fc5b  lea     rcx, [rbp+47h+var_68]; this
0x18004fc5f  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18004fc64  nop
0x18004fc65  lea     rcx, [rbp+47h+var_70]; this
0x18004fc69  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18004fc6e  nop
0x18004fc6f  lea     rcx, [rbp+47h+var_A8]
0x18004fc73  call    ?_Uninit@?$vector@UtagWAPAttribute@@V?$allocator@UtagWAPAttribute@@@utl@@@utl@@AEAAXXZ; utl::vector<tagWAPAttribute,utl::allocator<tagWAPAttribute>>::_Uninit(void)
0x18004fc78  nop
0x18004fc79  lea     rcx, [rbp+47h+var_90]
0x18004fc7d  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18004fc82  mov     eax, ebx
0x18004fc84  add     rsp, 0C8h
0x18004fc8b  pop     r15
0x18004fc8d  pop     r14
0x18004fc8f  pop     rdi
0x18004fc90  pop     rsi
0x18004fc91  pop     rbx
0x18004fc92  pop     rbp
0x18004fc93  retn
```
