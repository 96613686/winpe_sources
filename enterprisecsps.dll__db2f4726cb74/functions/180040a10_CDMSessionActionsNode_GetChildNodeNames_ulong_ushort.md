# CDMSessionActionsNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180040a10`
- end: `0x1800410ab`
- name: `?GetChildNodeNames@CDMSessionActionsNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1691`
- prototype: `__int64 __fastcall(CDMSessionActionsNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000d4d4`
- `0x180025ac0`
- `0x18002dcc8`
- `0x180040a10`
- `0x1800439e8`
- `0x180043b0c`
- `0x180043c0c`
- `0x180043cc4`
- `0x1800446c0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180040b38`
- `OLEAUT32!__imp_SysFreeString` at `0x180040bba`
- `OLEAUT32!__imp_SysFreeString` at `0x180040ca6`
- `OLEAUT32!__imp_SysFreeString` at `0x180040d36`
- `OLEAUT32!__imp_SysFreeString` at `0x180040db7`
- `OLEAUT32!__imp_SysFreeString` at `0x180040ef8`
- `OLEAUT32!__imp_SysFreeString` at `0x180040f56`
- `OLEAUT32!__imp_SysFreeString` at `0x18004105e`
- `OLEAUT32!__imp_SysFreeString` at `0x180040b38`
- `OLEAUT32!__imp_SysFreeString` at `0x180040bba`
- `OLEAUT32!__imp_SysFreeString` at `0x180040ca6`
- `OLEAUT32!__imp_SysFreeString` at `0x180040d36`
- `OLEAUT32!__imp_SysFreeString` at `0x180040db7`
- `OLEAUT32!__imp_SysFreeString` at `0x180040ef8`
- `OLEAUT32!__imp_SysFreeString` at `0x180040f56`
- `OLEAUT32!__imp_SysFreeString` at `0x18004105e`
- `DMCmnUtils!CreateBstrArray` at `0x180040aed`
- `DMCmnUtils!CreateBstrArray` at `0x180040c57`
- `DMCmnUtils!CreateBstrArray` at `0x180040cea`
- `DMCmnUtils!CreateBstrArray` at `0x180040ea4`
- `DMCmnUtils!CreateBstrArray` at `0x18004100e`
- `DMCmnUtils!CreateBstrArray` at `0x180040aed`
- `DMCmnUtils!CreateBstrArray` at `0x180040c57`
- `DMCmnUtils!CreateBstrArray` at `0x180040cea`
- `DMCmnUtils!CreateBstrArray` at `0x180040ea4`
- `DMCmnUtils!CreateBstrArray` at `0x18004100e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dd1`

## string_xrefs

- `0x180040ad1`: `NodeUri`
- `0x180040cc2`: `CheckinAlertConfiguration`

## pseudocode

```c
__int64 __fastcall CDMSessionActionsNode::GetChildNodeNames(CDMSessionActionsNode *this, unsigned int *a2, LPVOID *a3)
{
  unsigned int v6; // esi
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  const unsigned __int16 *v12; // r9
  const unsigned __int16 *v13; // r8
  int v14; // eax
  unsigned int v15; // r14d
  BSTR *v16; // rax
  unsigned int m; // edi
  BSTR *v18; // rcx
  int AllNodeIds; // eax
  BSTR *v20; // rdx
  unsigned int n; // edi
  BSTR *v22; // rcx
  const unsigned __int16 *v23; // rbx
  const unsigned __int16 *v24; // rdi
  DMSessionActionsHelper *v25; // rcx
  int v26; // eax
  BSTR *v27; // rdx
  unsigned int jj; // edi
  int v29; // eax
  unsigned int kk; // edi
  int AllServerIds; // eax
  BSTR *v33; // rax
  unsigned int k; // edi
  unsigned int v35; // eax
  DMSessionActionsHelper *v36; // rcx
  int v37; // eax
  unsigned int i; // edi
  unsigned int ii; // edi
  DMSessionActionsHelper *v40; // rcx
  int v41; // eax
  unsigned int j; // edi
  int v43; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v44; // [rsp+20h] [rbp-40h]
  int v45; // [rsp+20h] [rbp-40h]
  int v46; // [rsp+20h] [rbp-40h]
  int v47; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v48; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v49; // [rsp+20h] [rbp-40h]
  int v50; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v51; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v52; // [rsp+20h] [rbp-40h]
  int v53; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v54; // [rsp+28h] [rbp-38h]
  unsigned __int16 *v55; // [rsp+28h] [rbp-38h]
  unsigned __int16 *v56; // [rsp+28h] [rbp-38h]
  unsigned __int16 *v57; // [rsp+28h] [rbp-38h]
  int v58[2]; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v59; // [rsp+38h] [rbp-28h]
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  const unsigned __int16 *v61; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v62; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v64; // [rsp+A8h] [rbp+48h] BYREF
  HKEY v65; // [rsp+B8h] [rbp+58h] BYREF

  v64 = 0;
  pv = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    v6 = 0;
    *a3 = 0;
    v7 = *((_DWORD *)this + 11);
    if ( v7 > 6 )
    {
      v35 = v7 - 7;
      if ( v35 )
      {
        if ( v35 != 3 )
          goto LABEL_47;
        v54 = (unsigned __int16 *)*((_QWORD *)this + 16);
        v48 = (unsigned __int16 *)*((_QWORD *)this + 18);
        LODWORD(v65) = 0;
        DMSessionActionsHelper::DoesRegValueExist(this, (int *)&v65, qword_180157928, L"WindowSize", v48, v54);
        v55 = (unsigned __int16 *)*((_QWORD *)this + 16);
        v49 = (unsigned __int16 *)*((_QWORD *)this + 18);
        v58[0] = 0;
        DMSessionActionsHelper::DoesRegValueExist(v36, v58, qword_180157928, L"MaxBatchSize", v49, v55);
        v61 = (const unsigned __int16 *)((unsigned __int64)L"WindowSize" & -(__int64)((_DWORD)v65 != 0));
        v62 = (unsigned __int64)L"MaxBatchSize" & -(__int64)(v58[0] != 0);
        v37 = CreateBstrArray((unsigned __int16 ***)&pv, &v64, &v61, 2u);
        v15 = v37;
        if ( v37 >= 0 )
          goto LABEL_56;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3AD,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
          (const char *)(unsigned int)v37,
          v50);
        v27 = (BSTR *)pv;
        if ( !pv )
          return v15;
        for ( i = 0; i < v64; ++i )
        {
          SysFreeString(v27[i]);
          v27 = (BSTR *)pv;
        }
      }
      else
      {
        v56 = (unsigned __int16 *)*((_QWORD *)this + 16);
        v51 = (unsigned __int16 *)*((_QWORD *)this + 18);
        LODWORD(v65) = 0;
        DMSessionActionsHelper::DoesRegValueExist(
          this,
          (int *)&v65,
          qword_180157920,
          L"MaxSkippedSessionsInLowPowerState",
          v51,
          v56);
        v57 = (unsigned __int16 *)*((_QWORD *)this + 16);
        v52 = (unsigned __int16 *)*((_QWORD *)this + 18);
        v58[0] = 0;
        DMSessionActionsHelper::DoesRegValueExist(
          v40,
          v58,
          qword_180157920,
          L"MaxTimeSessionsSkippedInLowPowerState",
          v52,
          v57);
        v61 = (const unsigned __int16 *)((unsigned __int64)L"MaxSkippedSessionsInLowPowerState"
                                       & -(__int64)((_DWORD)v65 != 0));
        v62 = (unsigned __int64)L"MaxTimeSessionsSkippedInLowPowerState" & -(__int64)(v58[0] != 0);
        v41 = CreateBstrArray((unsigned __int16 ***)&pv, &v64, &v61, 2u);
        v15 = v41;
        if ( v41 >= 0 )
          goto LABEL_56;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x395,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
          (const char *)(unsigned int)v41,
          v53);
        v27 = (BSTR *)pv;
        if ( !pv )
          return v15;
        for ( j = 0; j < v64; ++j )
        {
          SysFreeString(v27[j]);
          v27 = (BSTR *)pv;
        }
      }
    }
    else
    {
      if ( v7 == 6 )
        goto LABEL_47;
      if ( !v7 )
      {
        AllServerIds = DMSessionActionsHelper::GetAllServerIds(
                         this,
                         &v64,
                         (unsigned __int16 ***)&pv,
                         *((const unsigned __int16 **)this + 18));
        v6 = AllServerIds;
        if ( AllServerIds < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x341,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
            (const char *)(unsigned int)AllServerIds,
            v43);
          v33 = (BSTR *)pv;
          if ( pv )
          {
            for ( k = 0; k < v64; ++k )
            {
              SysFreeString(v33[k]);
              v33 = (BSTR *)pv;
            }
LABEL_37:
            v22 = v33;
LABEL_38:
            CoTaskMemFree(v22);
          }
          return v6;
        }
LABEL_56:
        *a3 = pv;
        *a2 = v64;
        return v6;
      }
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 == 1 )
              {
                v12 = (const unsigned __int16 *)*((_QWORD *)this + 16);
                v13 = (const unsigned __int16 *)*((_QWORD *)this + 18);
                v44 = (unsigned __int16 *)*((_QWORD *)this + 17);
                LODWORD(v65) = 0;
                DMSessionActionsHelper::DoesNodeUriExist(this, (int *)&v65, v13, v12, v44);
                *(_QWORD *)v58 = (unsigned __int64)L"NodeUri" & -(__int64)((_DWORD)v65 != 0);
                v14 = CreateBstrArray((unsigned __int16 ***)&pv, &v64, (const unsigned __int16 **)v58, 1u);
                v15 = v14;
                if ( v14 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x37D,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
                    (const char *)(unsigned int)v14,
                    v45);
                  v16 = (BSTR *)pv;
                  if ( pv )
                  {
                    for ( m = 0; m < v64; ++m )
                    {
                      SysFreeString(v16[m]);
                      v16 = (BSTR *)pv;
                    }
                    v18 = v16;
                    goto LABEL_31;
                  }
                  return v15;
                }
                goto LABEL_56;
              }
              goto LABEL_47;
            }
            AllNodeIds = DMSessionActionsHelper::GetAllNodeIds(
                           this,
                           &v64,
                           (unsigned __int16 ***)&pv,
                           *((const unsigned __int16 **)this + 18),
                           *((const unsigned __int16 **)this + 16));
            v6 = AllNodeIds;
            if ( AllNodeIds < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x36C,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
                (const char *)(unsigned int)AllNodeIds,
                v46);
              v20 = (BSTR *)pv;
              if ( pv )
              {
                for ( n = 0; n < v64; ++n )
                {
                  SysFreeString(v20[n]);
                  v20 = (BSTR *)pv;
                }
                v22 = v20;
                goto LABEL_38;
              }
              return v6;
            }
            goto LABEL_56;
          }
LABEL_47:
          v6 = -2046820335;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3B8,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
            (const char *)0x86000011LL,
            v43);
          v33 = (BSTR *)pv;
          if ( !pv )
            return v6;
          for ( ii = 0; ii < v64; ++ii )
          {
            SysFreeString(v33[ii]);
            v33 = (BSTR *)pv;
          }
          goto LABEL_37;
        }
        v23 = (const unsigned __int16 *)*((_QWORD *)this + 16);
        v24 = (const unsigned __int16 *)*((_QWORD *)this + 18);
        v65 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v65,
          0);
        LODWORD(v24) = DMSessionActionsHelper::GetNodesKey(v25, &v65, v24, v23, 0) >= 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v65);
        *(_QWORD *)v58 = L"AlertData";
        v59 = (const wchar_t *)((unsigned __int64)L"Nodes" & -(__int64)((_DWORD)v24 != 0));
        v26 = CreateBstrArray((unsigned __int16 ***)&pv, &v64, (const unsigned __int16 **)v58, 2u);
        v15 = v26;
        if ( v26 >= 0 )
          goto LABEL_56;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x365,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
          (const char *)(unsigned int)v26,
          v47);
        v27 = (BSTR *)pv;
        if ( !pv )
          return v15;
        for ( jj = 0; jj < v64; ++jj )
        {
          SysFreeString(v27[jj]);
          v27 = (BSTR *)pv;
        }
      }
      else
      {
        *(_QWORD *)v58 = L"CheckinAlertConfiguration";
        v59 = L"PowerSettings";
        v29 = CreateBstrArray((unsigned __int16 ***)&pv, &v64, (const unsigned __int16 **)v58, 2u);
        v15 = v29;
        if ( v29 >= 0 )
          goto LABEL_56;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x351,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmsessionactions\\dmsessionactionsnode.cpp",
          (const char *)(unsigned int)v29,
          v43);
        v27 = (BSTR *)pv;
        if ( !pv )
          return v15;
        for ( kk = 0; kk < v64; ++kk )
        {
          SysFreeString(v27[kk]);
          v27 = (BSTR *)pv;
        }
      }
    }
    v18 = v27;
LABEL_31:
    CoTaskMemFree(v18);
    return v15;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180040a10  mov     [rsp-38h+arg_0], rbx
0x180040a15  push    rbp
0x180040a16  push    rsi
0x180040a17  push    rdi
0x180040a18  push    r12
0x180040a1a  push    r13
0x180040a1c  push    r14
0x180040a1e  push    r15
0x180040a20  mov     rbp, rsp
0x180040a23  sub     rsp, 60h
0x180040a27  xor     r13d, r13d
0x180040a2a  mov     r15, r8
0x180040a2d  mov     [rbp+arg_8], r13d
0x180040a31  mov     r12, rdx
0x180040a34  mov     [rbp+pv], r13
0x180040a38  mov     rdi, rcx
0x180040a3b  test    rdx, rdx
0x180040a3e  jz      loc_18004108D
0x180040a44  test    r8, r8
0x180040a47  jz      loc_18004108D
0x180040a4d  mov     [rdx], r13d
0x180040a50  mov     esi, r13d
0x180040a53  mov     [r8], r13
0x180040a56  mov     eax, [rcx+2Ch]
0x180040a59  cmp     eax, 6
0x180040a5c  ja      loc_180040DE4
0x180040a62  jz      loc_180040F14
0x180040a68  test    eax, eax
0x180040a6a  jz      loc_180040D64
0x180040a70  sub     eax, 1
0x180040a73  jz      loc_180040CC2
0x180040a79  sub     eax, 1
0x180040a7c  jz      loc_180040BD9
0x180040a82  sub     eax, 1
0x180040a85  jz      loc_180040F14
0x180040a8b  sub     eax, 1
0x180040a8e  jz      loc_180040B57
0x180040a94  cmp     eax, 1
0x180040a97  jnz     loc_180040F14
0x180040a9d  mov     rax, [rcx+88h]
0x180040aa4  lea     rdx, [rbp+arg_18]; int *
0x180040aa8  mov     r9, [rcx+80h]; unsigned __int16 *
0x180040aaf  mov     r8, [rcx+90h]; unsigned __int16 *
0x180040ab6  mov     [rsp+60h+var_40], rax; int
0x180040abb  mov     dword ptr [rbp+arg_18], r13d
0x180040abf  call    ?DoesNodeUriExist@DMSessionActionsHelper@@QEAAJPEAHPEBG11@Z; DMSessionActionsHelper::DoesNodeUriExist(int *,ushort const *,ushort const *,ushort const *)
0x180040ac4  mov     eax, dword ptr [rbp+arg_18]
0x180040ac7  lea     ebx, [r13+1]
0x180040acb  neg     eax
0x180040acd  lea     r8, [rbp+var_30]
0x180040ad1  lea     rax, aNodeuri_1; "NodeUri"
0x180040ad8  mov     r9d, ebx
0x180040adb  sbb     rcx, rcx
0x180040ade  lea     rdx, [rbp+arg_8]
0x180040ae2  and     rcx, rax
0x180040ae5  mov     qword ptr [rbp+var_30], rcx
0x180040ae9  lea     rcx, [rbp+pv]
0x180040aed  call    cs:__imp_?CreateBstrArray@@YAJPEAPEAPEAGPEAKPEAPEBGK@Z; CreateBstrArray(ushort * * *,ulong *,ushort const * *,ulong)
0x180040af4  nop     dword ptr [rax+rax+00h]
0x180040af9  mov     r14d, eax
0x180040afc  test    eax, eax
0x180040afe  jns     loc_18004107A
0x180040b04  mov     rcx, [rbp+38h]; this
0x180040b08  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180040b0f  mov     r9d, eax; char *
0x180040b12  mov     edx, 37Dh; void *
0x180040b17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040b1c  mov     rax, [rbp+pv]
0x180040b20  test    rax, rax
0x180040b23  jz      loc_180040D5C
0x180040b29  mov     edi, r13d
0x180040b2c  cmp     [rbp+arg_8], r13d
0x180040b30  jbe     short loc_180040B4F
0x180040b32  mov     ecx, edi
0x180040b34  mov     rcx, [rax+rcx*8]; bstrString
0x180040b38  call    cs:__imp_SysFreeString
0x180040b3f  nop     dword ptr [rax+rax+00h]
0x180040b44  mov     rax, [rbp+pv]
0x180040b48  add     edi, ebx
0x180040b4a  cmp     edi, [rbp+arg_8]
0x180040b4d  jb      short loc_180040B32
0x180040b4f  mov     rcx, rax; this
0x180040b52  jmp     loc_180040D50
0x180040b57  mov     rax, [rcx+80h]
0x180040b5e  lea     r8, [rbp+pv]; unsigned __int16 ***
0x180040b62  mov     r9, [rcx+90h]; unsigned __int16 *
0x180040b69  lea     rdx, [rbp+arg_8]; unsigned int *
0x180040b6d  mov     [rsp+60h+var_40], rax; int
0x180040b72  call    ?GetAllNodeIds@DMSessionActionsHelper@@QEAAJPEAKPEAPEAPEAGPEBG2@Z; DMSessionActionsHelper::GetAllNodeIds(ulong *,ushort * * *,ushort const *,ushort const *)
0x180040b77  mov     esi, eax
0x180040b79  test    eax, eax
0x180040b7b  jns     loc_18004107A
0x180040b81  mov     rcx, [rbp+38h]; this
0x180040b85  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180040b8c  mov     r9d, eax; char *
0x180040b8f  mov     edx, 36Ch; void *
0x180040b94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040b99  mov     rdx, [rbp+pv]
0x180040b9d  test    rdx, rdx
0x180040ba0  jz      loc_180040DDD
0x180040ba6  mov     edi, r13d
0x180040ba9  cmp     [rbp+arg_8], r13d
0x180040bad  jbe     short loc_180040BD1
0x180040baf  mov     ebx, 1
0x180040bb4  mov     ecx, edi
0x180040bb6  mov     rcx, [rdx+rcx*8]; bstrString
0x180040bba  call    cs:__imp_SysFreeString
0x180040bc1  nop     dword ptr [rax+rax+00h]
0x180040bc6  mov     rdx, [rbp+pv]
0x180040bca  add     edi, ebx
0x180040bcc  cmp     edi, [rbp+arg_8]
0x180040bcf  jb      short loc_180040BB4
0x180040bd1  mov     rcx, rdx
0x180040bd4  jmp     loc_180040DD1
0x180040bd9  mov     rbx, [rcx+80h]
0x180040be0  xor     edx, edx
0x180040be2  mov     rdi, [rcx+90h]
0x180040be9  lea     rcx, [rbp+arg_18]
0x180040bed  mov     [rbp+arg_18], r13
0x180040bf1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040bf6  mov     r9, rbx; unsigned __int16 *
0x180040bf9  mov     dword ptr [rsp+60h+var_40], r13d; int
0x180040bfe  mov     r8, rdi; unsigned __int16 *
0x180040c01  lea     rdx, [rbp+arg_18]; HKEY *
0x180040c05  call    ?GetNodesKey@DMSessionActionsHelper@@QEAAJPEAPEAUHKEY__@@PEBG1H@Z; DMSessionActionsHelper::GetNodesKey(HKEY__ * *,ushort const *,ushort const *,int)
0x180040c0a  mov     ebx, 1
0x180040c0f  mov     edi, r13d
0x180040c12  cmp     eax, 80070002h
0x180040c17  jz      short loc_180040C1E
0x180040c19  test    eax, eax
0x180040c1b  cmovns  edi, ebx
0x180040c1e  lea     rcx, [rbp+arg_18]
0x180040c22  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040c27  lea     rax, aAlertdata_0; "AlertData"
0x180040c2e  neg     edi
0x180040c30  mov     qword ptr [rbp+var_30], rax
0x180040c34  lea     rcx, aNodes_0; "Nodes"
0x180040c3b  sbb     rax, rax
0x180040c3e  lea     r8, [rbp+var_30]
0x180040c42  and     rax, rcx
0x180040c45  lea     rdx, [rbp+arg_8]
0x180040c49  lea     rcx, [rbp+pv]
0x180040c4d  mov     [rbp+var_28], rax
0x180040c51  mov     r9d, 2
0x180040c57  call    cs:__imp_?CreateBstrArray@@YAJPEAPEAPEAGPEAKPEAPEBGK@Z; CreateBstrArray(ushort * * *,ulong *,ushort const * *,ulong)
0x180040c5e  nop     dword ptr [rax+rax+00h]
0x180040c63  mov     r14d, eax
0x180040c66  test    eax, eax
0x180040c68  jns     loc_18004107A
0x180040c6e  mov     rcx, [rbp+38h]; this
0x180040c72  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180040c79  mov     r9d, eax; char *
0x180040c7c  mov     edx, 365h; void *
0x180040c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040c86  mov     rdx, [rbp+pv]
0x180040c8a  test    rdx, rdx
0x180040c8d  jz      loc_180040D5C
0x180040c93  mov     edi, r13d
0x180040c96  cmp     [rbp+arg_8], r13d
0x180040c9a  jbe     loc_180040D4D
0x180040ca0  mov     ecx, edi
0x180040ca2  mov     rcx, [rdx+rcx*8]; bstrString
0x180040ca6  call    cs:__imp_SysFreeString
0x180040cad  nop     dword ptr [rax+rax+00h]
0x180040cb2  mov     rdx, [rbp+pv]
0x180040cb6  add     edi, ebx
0x180040cb8  cmp     edi, [rbp+arg_8]
0x180040cbb  jb      short loc_180040CA0
0x180040cbd  jmp     loc_180040D4D
0x180040cc2  lea     rax, aCheckinalertco_0; "CheckinAlertConfiguration"
0x180040cc9  mov     r9d, 2
0x180040ccf  mov     qword ptr [rbp+var_30], rax
0x180040cd3  lea     r8, [rbp+var_30]
0x180040cd7  lea     rax, aPowersettings_0; "PowerSettings"
0x180040cde  lea     rdx, [rbp+arg_8]
0x180040ce2  mov     [rbp+var_28], rax
0x180040ce6  lea     rcx, [rbp+pv]
0x180040cea  call    cs:__imp_?CreateBstrArray@@YAJPEAPEAPEAGPEAKPEAPEBGK@Z; CreateBstrArray(ushort * * *,ulong *,ushort const * *,ulong)
0x180040cf1  nop     dword ptr [rax+rax+00h]
0x180040cf6  mov     r14d, eax
0x180040cf9  test    eax, eax
0x180040cfb  jns     loc_18004107A
0x180040d01  mov     rcx, [rbp+38h]; this
0x180040d05  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180040d0c  mov     r9d, eax; char *
0x180040d0f  mov     edx, 351h; void *
0x180040d14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040d19  mov     rdx, [rbp+pv]
0x180040d1d  test    rdx, rdx
0x180040d20  jz      short loc_180040D5C
0x180040d22  mov     edi, r13d
0x180040d25  cmp     [rbp+arg_8], r13d
0x180040d29  jbe     short loc_180040D4D
0x180040d2b  mov     ebx, 1
0x180040d30  mov     ecx, edi
0x180040d32  mov     rcx, [rdx+rcx*8]; bstrString
0x180040d36  call    cs:__imp_SysFreeString
0x180040d3d  nop     dword ptr [rax+rax+00h]
0x180040d42  mov     rdx, [rbp+pv]
0x180040d46  add     edi, ebx
0x180040d48  cmp     edi, [rbp+arg_8]
0x180040d4b  jb      short loc_180040D30
0x180040d4d  mov     rcx, rdx; pv
0x180040d50  call    cs:__imp_CoTaskMemFree
0x180040d57  nop     dword ptr [rax+rax+00h]
0x180040d5c  mov     eax, r14d
0x180040d5f  jmp     loc_180041092
0x180040d64  mov     r9, [rcx+90h]; unsigned __int16 *
0x180040d6b  lea     r8, [rbp+pv]; unsigned __int16 ***
0x180040d6f  lea     rdx, [rbp+arg_8]; unsigned int *
0x180040d73  call    ?GetAllServerIds@DMSessionActionsHelper@@QEAAJPEAKPEAPEAPEAGPEBG@Z; DMSessionActionsHelper::GetAllServerIds(ulong *,ushort * * *,ushort const *)
0x180040d78  mov     esi, eax
0x180040d7a  test    eax, eax
0x180040d7c  jns     loc_18004107A
0x180040d82  mov     rcx, [rbp+38h]; this
0x180040d86  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180040d8d  mov     r9d, eax; char *
0x180040d90  mov     edx, 341h; void *
0x180040d95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040d9a  mov     rax, [rbp+pv]
0x180040d9e  test    rax, rax
0x180040da1  jz      short loc_180040DDD
0x180040da3  mov     edi, r13d
0x180040da6  cmp     [rbp+arg_8], r13d
0x180040daa  jbe     short loc_180040DCE
0x180040dac  mov     ebx, 1
0x180040db1  mov     ecx, edi
0x180040db3  mov     rcx, [rax+rcx*8]; bstrString
0x180040db7  call    cs:__imp_SysFreeString
0x180040dbe  nop     dword ptr [rax+rax+00h]
0x180040dc3  mov     rax, [rbp+pv]
0x180040dc7  add     edi, ebx
0x180040dc9  cmp     edi, [rbp+arg_8]
0x180040dcc  jb      short loc_180040DB1
0x180040dce  mov     rcx, rax; pv
0x180040dd1  call    cs:__imp_CoTaskMemFree
0x180040dd8  nop     dword ptr [rax+rax+00h]
0x180040ddd  mov     eax, esi
0x180040ddf  jmp     loc_180041092
0x180040de4  sub     eax, 7
0x180040de7  jz      loc_180040F72
0x180040ded  sub     eax, 1
0x180040df0  jz      loc_180040F14
0x180040df6  sub     eax, 1
0x180040df9  jz      loc_180040F14
0x180040dff  sub     eax, 1
0x180040e02  jnz     loc_180040F14
0x180040e08  mov     rax, [rcx+80h]
0x180040e0f  lea     r14, aWindowsize_0; "WindowSize"
0x180040e16  mov     r8, cs:qword_180157928; unsigned __int16 *
0x180040e1d  lea     rdx, [rbp+arg_18]; int *
0x180040e21  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180040e26  mov     r9, r14; unsigned __int16 *
0x180040e29  mov     rax, [rcx+90h]
0x180040e30  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x180040e35  mov     dword ptr [rbp+arg_18], r13d
0x180040e39  call    ?DoesRegValueExist@DMSessionActionsHelper@@QEAAJPEAHPEBG111@Z; DMSessionActionsHelper::DoesRegValueExist(int *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180040e3e  mov     rax, [rdi+80h]
0x180040e45  lea     rbx, aMaxbatchsize_0; "MaxBatchSize"
0x180040e4c  mov     r8, cs:qword_180157928; unsigned __int16 *
0x180040e53  lea     rdx, [rbp+var_30]; int *
0x180040e57  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180040e5c  mov     r9, rbx; unsigned __int16 *
0x180040e5f  mov     rax, [rdi+90h]
0x180040e66  mov     [rsp+60h+var_40], rax; int
0x180040e6b  mov     [rbp+var_30], r13d
0x180040e6f  call    ?DoesRegValueExist@DMSessionActionsHelper@@QEAAJPEAHPEBG111@Z; DMSessionActionsHelper::DoesRegValueExist(int *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180040e74  mov     eax, dword ptr [rbp+arg_18]
0x180040e77  lea     r8, [rbp+var_18]
0x180040e7b  neg     eax
0x180040e7d  lea     rdx, [rbp+arg_8]
0x180040e81  mov     eax, [rbp+var_30]
0x180040e84  mov     r9d, 2
0x180040e8a  sbb     rcx, rcx
0x180040e8d  and     rcx, r14
0x180040e90  mov     [rbp+var_18], rcx
0x180040e94  neg     eax
0x180040e96  sbb     rcx, rcx
0x180040e99  and     rcx, rbx
0x180040e9c  mov     [rbp+var_10], rcx
0x180040ea0  lea     rcx, [rbp+pv]
0x180040ea4  call    cs:__imp_?CreateBstrArray@@YAJPEAPEAPEAGPEAKPEAPEBGK@Z; CreateBstrArray(ushort * * *,ulong *,ushort const * *,ulong)
0x180040eab  nop     dword ptr [rax+rax+00h]
0x180040eb0  mov     r14d, eax
0x180040eb3  test    eax, eax
0x180040eb5  jns     loc_18004107A
0x180040ebb  mov     rcx, [rbp+38h]; this
0x180040ebf  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180040ec6  mov     r9d, eax; char *
0x180040ec9  mov     edx, 3ADh; void *
0x180040ece  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040ed3  mov     rdx, [rbp+pv]
0x180040ed7  test    rdx, rdx
0x180040eda  jz      loc_180040D5C
0x180040ee0  mov     edi, r13d
0x180040ee3  cmp     [rbp+arg_8], r13d
0x180040ee7  jbe     loc_180040D4D
0x180040eed  mov     ebx, 1
0x180040ef2  mov     ecx, edi
0x180040ef4  mov     rcx, [rdx+rcx*8]; bstrString
  ... truncated ...
```
