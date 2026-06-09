# CDMClientEnhancedAppLayerSecurityNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180035d90`
- end: `0x180035fe0`
- name: `?GetChildNodeNames@CDMClientEnhancedAppLayerSecurityNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `592`
- prototype: `__int64 __fastcall(CDMClientEnhancedAppLayerSecurityNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x18000d4d4`
- `0x180021944`
- `0x180026f4c`
- `0x180027490`
- `0x1800274c4`
- `0x180035d90`
- `0x180036b00`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180035e3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e60`
- `OLEAUT32!__imp_SysFreeString` at `0x180035f70`
- `OLEAUT32!__imp_SysFreeString` at `0x180035f94`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180035e60`
- `OLEAUT32!__imp_SysFreeString` at `0x180035f70`
- `OLEAUT32!__imp_SysFreeString` at `0x180035f94`
- `DMCmnUtils!CreateBstrArray` at `0x180035f3e`
- `DMCmnUtils!CreateBstrArray` at `0x180035f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035e7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035e7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035fae`

## string_xrefs

- `0x180035ee1`: `SecurityMode`

## pseudocode

```c
__int64 __fastcall CDMClientEnhancedAppLayerSecurityNode::GetChildNodeNames(
        CDMClientEnhancedAppLayerSecurityNode *this,
        unsigned int *a2,
        LPVOID *a3)
{
  struct CConfigServiceProvider2Impl *v6; // rcx
  unsigned __int16 *EnrollmentId2; // rax
  bool *v8; // r8
  int v9; // ecx
  OLECHAR *v10; // rbx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  unsigned int v14; // edi
  BSTR *v15; // rax
  unsigned int i; // ebx
  bool *v18; // r8
  const unsigned __int16 *v19; // rdx
  bool *v20; // r9
  bool *v21; // r9
  int v22; // eax
  unsigned int v23; // r15d
  BSTR *v24; // rax
  unsigned int j; // ebx
  int v26; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v27; // [rsp+24h] [rbp-3Ch] BYREF
  LPVOID pv; // [rsp+28h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-30h] BYREF
  const unsigned __int16 *v30[4]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v27 = 0;
  pv = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  *a2 = 0;
  *a3 = 0;
  v6 = (struct CConfigServiceProvider2Impl *)*((_QWORD *)this + 16);
  bstrString = 0;
  EnrollmentId2 = GetEnrollmentId2(v6);
  ATL::CComBSTR::operator=(&bstrString, EnrollmentId2);
  v9 = *((_DWORD *)this + 11);
  v10 = bstrString;
  v11 = v9 - 64;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( (unsigned int)(v13 - 1) >= 2 )
        {
          v14 = -2147024809;
LABEL_10:
          SysFreeString(v10);
          v15 = (BSTR *)pv;
          if ( pv )
          {
            for ( i = 0; i < v27; ++i )
            {
              SysFreeString(v15[i]);
              v15 = (BSTR *)pv;
            }
            CoTaskMemFree(v15);
          }
          return v14;
        }
      }
    }
    v14 = -2046820335;
LABEL_9:
    *a3 = pv;
    *a2 = v27;
    pv = 0;
    goto LABEL_10;
  }
  LOBYTE(v26) = 0;
  v14 = 0;
  DMClient::DoesSecurityModeExists((DMClient *)bstrString, (const unsigned __int16 *)&v26, v8);
  BYTE1(v26) = 0;
  DMClient::DoesUseCertIfRevocationCheckOfflineExists(
    (DMClient *)v10,
    (const unsigned __int16 *)((char *)&v26 + 1),
    v18);
  BYTE2(v26) = 0;
  LOBYTE(v19) = 1;
  DMClient::DoesEnhancedAppLayerSecurityCertExists((DMClient *)v10, v19, (bool)&v26 + 2, v20);
  HIBYTE(v26) = 0;
  DMClient::DoesEnhancedAppLayerSecurityCertExists((DMClient *)v10, 0, (bool)&v26 + 3, v21);
  v30[0] = (const unsigned __int16 *)((unsigned __int64)L"SecurityMode" & -(__int64)((_BYTE)v26 != 0));
  v30[1] = (const unsigned __int16 *)((unsigned __int64)L"UseCertIfRevocationCheckOffline" & -(__int64)(BYTE1(v26) != 0));
  v30[2] = (const unsigned __int16 *)((unsigned __int64)L"Cert0" & -(__int64)(BYTE2(v26) != 0));
  v30[3] = (const unsigned __int16 *)((unsigned __int64)L"Cert1" & -(__int64)(HIBYTE(v26) != 0));
  v22 = CreateBstrArray((unsigned __int16 ***)&pv, &v27, v30, 4u);
  v23 = v22;
  if ( v22 >= 0 )
    goto LABEL_9;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xFCB,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclientnode.cpp",
    (const char *)(unsigned int)v22,
    v26);
  SysFreeString(v10);
  v24 = (BSTR *)pv;
  if ( pv )
  {
    for ( j = 0; j < v27; ++j )
    {
      SysFreeString(v24[j]);
      v24 = (BSTR *)pv;
    }
    CoTaskMemFree(v24);
  }
  return v23;
}

```

## disassembly

```asm
0x180035d90  push    rbp
0x180035d92  push    rbx
0x180035d93  push    rsi
0x180035d94  push    rdi
0x180035d95  push    r12
0x180035d97  push    r14
0x180035d99  push    r15
0x180035d9b  mov     rbp, rsp
0x180035d9e  sub     rsp, 60h
0x180035da2  mov     rax, cs:__security_cookie
0x180035da9  xor     rax, rsp
0x180035dac  mov     [rbp+var_8], rax
0x180035db0  xor     r12d, r12d
0x180035db3  mov     rsi, r8
0x180035db6  mov     [rbp+var_3C], r12d
0x180035dba  mov     r14, rdx
0x180035dbd  mov     [rbp+pv], r12
0x180035dc1  mov     rbx, rcx
0x180035dc4  test    rdx, rdx
0x180035dc7  jz      loc_180035FBF
0x180035dcd  test    r8, r8
0x180035dd0  jz      loc_180035FBF
0x180035dd6  mov     [rdx], r12d
0x180035dd9  mov     [r8], r12
0x180035ddc  mov     rcx, [rcx+80h]; struct CConfigServiceProvider2Impl *
0x180035de3  mov     [rbp+bstrString], r12
0x180035de7  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x180035dec  mov     rdx, rax
0x180035def  lea     rcx, [rbp+bstrString]
0x180035df3  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180035df8  mov     ecx, [rbx+2Ch]
0x180035dfb  mov     rbx, [rbp+bstrString]
0x180035dff  sub     ecx, 40h ; '@'
0x180035e02  jz      loc_180035E8D
0x180035e08  sub     ecx, 1
0x180035e0b  jz      short loc_180035E23
0x180035e0d  sub     ecx, 1
0x180035e10  jz      short loc_180035E23
0x180035e12  sub     ecx, 1
0x180035e15  jz      short loc_180035E23
0x180035e17  cmp     ecx, 1
0x180035e1a  jz      short loc_180035E23
0x180035e1c  mov     edi, 80070057h
0x180035e21  jmp     short loc_180035E39
0x180035e23  mov     edi, 86000011h
0x180035e28  mov     rax, [rbp+pv]
0x180035e2c  mov     [rsi], rax
0x180035e2f  mov     eax, [rbp+var_3C]
0x180035e32  mov     [r14], eax
0x180035e35  mov     [rbp+pv], r12
0x180035e39  mov     rcx, rbx; bstrString
0x180035e3c  call    cs:__imp_SysFreeString
0x180035e43  nop     dword ptr [rax+rax+00h]
0x180035e48  mov     rax, [rbp+pv]
0x180035e4c  test    rax, rax
0x180035e4f  jz      short loc_180035E86
0x180035e51  mov     ebx, r12d
0x180035e54  cmp     [rbp+var_3C], r12d
0x180035e58  jbe     short loc_180035E77
0x180035e5a  mov     ecx, ebx
0x180035e5c  mov     rcx, [rax+rcx*8]; bstrString
0x180035e60  call    cs:__imp_SysFreeString
0x180035e67  nop     dword ptr [rax+rax+00h]
0x180035e6c  mov     rax, [rbp+pv]
0x180035e70  inc     ebx
0x180035e72  cmp     ebx, [rbp+var_3C]
0x180035e75  jb      short loc_180035E5A
0x180035e77  mov     rcx, rax; pv
0x180035e7a  call    cs:__imp_CoTaskMemFree
0x180035e81  nop     dword ptr [rax+rax+00h]
0x180035e86  mov     eax, edi
0x180035e88  jmp     loc_180035FC4
0x180035e8d  lea     rdx, [rbp+var_40]; unsigned __int16 *
0x180035e91  mov     byte ptr [rbp+var_40], r12b
0x180035e95  mov     rcx, rbx; this
0x180035e98  mov     edi, r12d
0x180035e9b  call    ?DoesSecurityModeExists@DMClient@@YAJPEBGPEA_N@Z; DMClient::DoesSecurityModeExists(ushort const *,bool *)
0x180035ea0  lea     rdx, [rbp+var_40+1]; unsigned __int16 *
0x180035ea4  mov     byte ptr [rbp+var_40+1], r12b
0x180035ea8  mov     rcx, rbx; this
0x180035eab  call    ?DoesUseCertIfRevocationCheckOfflineExists@DMClient@@YAJPEBGPEA_N@Z; DMClient::DoesUseCertIfRevocationCheckOfflineExists(ushort const *,bool *)
0x180035eb0  lea     r8, [rbp+var_3E]; bool
0x180035eb4  mov     [rbp+var_3E], r12b
0x180035eb8  mov     dl, 1; unsigned __int16 *
0x180035eba  mov     rcx, rbx; this
0x180035ebd  call    ?DoesEnhancedAppLayerSecurityCertExists@DMClient@@YAJPEBG_NPEA_N@Z; DMClient::DoesEnhancedAppLayerSecurityCertExists(ushort const *,bool,bool *)
0x180035ec2  lea     r8, [rbp+var_3D]; bool
0x180035ec6  mov     [rbp+var_3D], r12b
0x180035eca  xor     edx, edx; unsigned __int16 *
0x180035ecc  mov     rcx, rbx; this
0x180035ecf  call    ?DoesEnhancedAppLayerSecurityCertExists@DMClient@@YAJPEBG_NPEA_N@Z; DMClient::DoesEnhancedAppLayerSecurityCertExists(ushort const *,bool,bool *)
0x180035ed4  mov     al, byte ptr [rbp+var_40]
0x180035ed7  lea     r8, [rbp+var_28]
0x180035edb  neg     al
0x180035edd  lea     rdx, [rbp+var_3C]
0x180035ee1  lea     rax, aSecuritymode_0; "SecurityMode"
0x180035ee8  mov     r9d, 4
0x180035eee  sbb     rcx, rcx
0x180035ef1  and     rcx, rax
0x180035ef4  mov     al, byte ptr [rbp+var_40+1]
0x180035ef7  neg     al
0x180035ef9  mov     [rbp+var_28], rcx
0x180035efd  lea     rax, aUsecertifrevoc_0; "UseCertIfRevocationCheckOffline"
0x180035f04  sbb     rcx, rcx
0x180035f07  and     rcx, rax
0x180035f0a  mov     al, [rbp+var_3E]
0x180035f0d  neg     al
0x180035f0f  mov     [rbp+var_20], rcx
0x180035f13  lea     rax, aCert0_0; "Cert0"
0x180035f1a  sbb     rcx, rcx
0x180035f1d  and     rcx, rax
0x180035f20  mov     al, [rbp+var_3D]
0x180035f23  mov     [rbp+var_18], rcx
0x180035f27  neg     al
0x180035f29  lea     rax, aCert1_0; "Cert1"
0x180035f30  sbb     rcx, rcx
0x180035f33  and     rcx, rax
0x180035f36  mov     [rbp+var_10], rcx
0x180035f3a  lea     rcx, [rbp+pv]
0x180035f3e  call    cs:__imp_?CreateBstrArray@@YAJPEAPEAPEAGPEAKPEAPEBGK@Z; CreateBstrArray(ushort * * *,ulong *,ushort const * *,ulong)
0x180035f45  nop     dword ptr [rax+rax+00h]
0x180035f4a  mov     r15d, eax
0x180035f4d  test    eax, eax
0x180035f4f  jns     loc_180035E28
0x180035f55  mov     rcx, [rbp+38h]; this
0x180035f59  lea     r8, aOnecoreuapAdmi_63; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180035f60  mov     r9d, eax; char *
0x180035f63  mov     edx, 0FCBh; void *
0x180035f68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f6d  mov     rcx, rbx; bstrString
0x180035f70  call    cs:__imp_SysFreeString
0x180035f77  nop     dword ptr [rax+rax+00h]
0x180035f7c  mov     rax, [rbp+pv]
0x180035f80  test    rax, rax
0x180035f83  jz      short loc_180035FBA
0x180035f85  mov     ebx, r12d
0x180035f88  cmp     [rbp+var_3C], r12d
0x180035f8c  jbe     short loc_180035FAB
0x180035f8e  mov     ecx, ebx
0x180035f90  mov     rcx, [rax+rcx*8]; bstrString
0x180035f94  call    cs:__imp_SysFreeString
0x180035f9b  nop     dword ptr [rax+rax+00h]
0x180035fa0  mov     rax, [rbp+pv]
0x180035fa4  inc     ebx
0x180035fa6  cmp     ebx, [rbp+var_3C]
0x180035fa9  jb      short loc_180035F8E
0x180035fab  mov     rcx, rax; pv
0x180035fae  call    cs:__imp_CoTaskMemFree
0x180035fb5  nop     dword ptr [rax+rax+00h]
0x180035fba  mov     eax, r15d
0x180035fbd  jmp     short loc_180035FC4
0x180035fbf  mov     eax, 80070057h
0x180035fc4  mov     rcx, [rbp+var_8]
0x180035fc8  xor     rcx, rsp; StackCookie
0x180035fcb  call    __security_check_cookie
0x180035fd0  add     rsp, 60h
0x180035fd4  pop     r15
0x180035fd6  pop     r14
0x180035fd8  pop     r12
0x180035fda  pop     rdi
0x180035fdb  pop     rsi
0x180035fdc  pop     rbx
0x180035fdd  pop     rbp
0x180035fde  retn
```
