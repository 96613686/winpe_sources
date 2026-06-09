# AdaIsSchemaExtInstalled(int *)

- ea: `0x1800e88d4`
- end: `0x1800e8f25`
- name: `?AdaIsSchemaExtInstalled@@YAJPEAH@Z`
- size: `1617`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180068630`
- `0x1800e8f2c`
- `0x1800e9804`

## callees

- `0x1800090c0`
- `0x1800e8894`
- `0x1800e88d4`
- `0x1800e9e84`
- `0x1800ea0bc`
- `0x1800ea4ac`
- `0x1800ea7b8`
- `0x1800eaac4`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e8ee4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e8ee4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e8ac6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e8ac6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8ab2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8b22`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8d9e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8ef3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8f02`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8ab2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8b22`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8d9e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8ef3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8f02`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e8ae9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e8ae9`
- `OLEAUT32!__imp_VariantInit` at `0x1800e8917`
- `OLEAUT32!__imp_VariantInit` at `0x1800e8917`
- `OLEAUT32!__imp_VariantClear` at `0x1800e8c4a`
- `OLEAUT32!__imp_VariantClear` at `0x1800e8d29`
- `OLEAUT32!__imp_VariantClear` at `0x1800e8ed2`
- `OLEAUT32!__imp_VariantClear` at `0x1800e8c4a`
- `OLEAUT32!__imp_VariantClear` at `0x1800e8d29`
- `OLEAUT32!__imp_VariantClear` at `0x1800e8ed2`
- `OLEAUT32!__imp_VarBstrCat` at `0x1800e8b0d`
- `OLEAUT32!__imp_VarBstrCat` at `0x1800e8b0d`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800e8b88`
- `ext-ms-win-adsi-activeds-l1-1-0!ADsOpenObject` at `0x1800e8b88`

## pseudocode

```c
__int64 __fastcall AdaIsSchemaExtInstalled(int *a1)
{
  OLECHAR *v2; // rbx
  OLECHAR *v3; // r12
  HRESULT v4; // edi
  unsigned int v5; // eax
  const unsigned __int16 *v6; // rcx
  unsigned int NamingContext; // eax
  __int64 i; // rax
  __int64 v9; // r13
  const OLECHAR *v10; // rdi
  int v11; // ecx
  HRESULT v12; // eax
  int v13; // r12d
  unsigned int MustContain; // eax
  unsigned int MayContain; // eax
  unsigned int v16; // eax
  HRESULT (__stdcall *Get)(IADs *, BSTR, VARIANT *); // rdi
  ATL::CComBSTR *v18; // rax
  PVOID *v19; // rcx
  unsigned int v20; // eax
  HRESULT (__stdcall *v21)(IADs *, BSTR, VARIANT *); // rdi
  ATL::CComBSTR *v22; // rax
  BSTR bstrVal; // rax
  int v24; // edx
  int v25; // ecx
  __int64 v26; // rdx
  VARIANTARG pvarg; // [rsp+30h] [rbp-99h] BYREF
  BSTR pbstrResult; // [rsp+48h] [rbp-81h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-79h] BYREF
  BSTR v31; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v32[4]; // [rsp+60h] [rbp-69h]
  int v33; // [rsp+64h] [rbp-65h]
  const size_t *v34; // [rsp+68h] [rbp-61h]
  char v35; // [rsp+70h] [rbp-59h]
  int v36; // [rsp+74h] [rbp-55h]
  const wchar_t *v37; // [rsp+78h] [rbp-51h]
  char v38; // [rsp+80h] [rbp-49h]
  int v39; // [rsp+84h] [rbp-45h]
  const wchar_t *v40; // [rsp+88h] [rbp-41h]
  char v41; // [rsp+90h] [rbp-39h]
  int v42; // [rsp+94h] [rbp-35h]
  const wchar_t *v43; // [rsp+98h] [rbp-31h]
  char v44; // [rsp+A0h] [rbp-29h]
  int v45; // [rsp+A4h] [rbp-25h]
  const wchar_t *v46; // [rsp+A8h] [rbp-21h]
  OLECHAR *psz[14]; // [rsp+B0h] [rbp-19h]
  bool v48; // [rsp+130h] [rbp+67h] BYREF
  int v49; // [rsp+138h] [rbp+6Fh]
  BSTR pbstr; // [rsp+140h] [rbp+77h] BYREF
  struct IADs *ppObject; // [rsp+148h] [rbp+7Fh] BYREF

  pbstr = 0;
  ppObject = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v2 = 0;
  v48 = 0;
  v3 = 0;
  VariantInit(&pvarg);
  v32[0] = 1;
  v33 = -1;
  v35 = 1;
  psz[0] = L"LDAP://CN=ms-FVE-RecoveryInformation,";
  psz[1] = L"LDAP://CN=ms-FVE-RecoveryGuid,";
  psz[2] = L"LDAP://CN=ms-FVE-RecoveryPassword,";
  psz[3] = L"LDAP://CN=ms-FVE-VolumeGuid,";
  psz[4] = L"LDAP://CN=ms-FVE-KeyPackage,";
  v34 = &cchOriginalDestLength;
  v40 = L"2.5.5.12";
  v36 = 4;
  v37 = L"2.5.5.10";
  v38 = 1;
  v39 = 64;
  v41 = 1;
  v42 = 4;
  v43 = L"2.5.5.10";
  v44 = 1;
  v45 = 4;
  v46 = L"2.5.5.10";
  if ( !a1 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, 2147942487LL);
    goto LABEL_91;
  }
  *a1 = 0;
  v5 = AdapInitializeCOM(&v48);
  v4 = v5;
  if ( !v5 )
    goto LABEL_10;
  v6 = (const unsigned __int16 *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v5);
  if ( v4 >= 0 )
  {
LABEL_10:
    NamingContext = AdapGetNamingContext(v6, &pbstr);
    v4 = NamingContext;
    if ( NamingContext )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
          NamingContext);
      if ( v4 < 0 )
        goto LABEL_90;
    }
    for ( i = 0; ; i = (unsigned int)(v49 + 1) )
    {
      v49 = i;
      if ( (unsigned int)i >= 5 )
      {
        *a1 = 1;
        goto LABEL_90;
      }
      v9 = 2 * i;
      if ( v32[16 * i] )
      {
        v10 = psz[i];
        if ( v10 != v2 )
        {
          SysFreeString(v2);
          if ( v10 )
          {
            v2 = SysAllocString(v10);
            if ( !v2 )
              ATL::AtlThrowImpl(v11);
          }
          else
          {
            v2 = 0;
          }
        }
        v3 = pbstr;
        if ( SysStringLen(pbstr) )
        {
          pbstrResult = 0;
          v4 = VarBstrCat(v2, v3, &pbstrResult);
          if ( v4 < 0 || (SysFreeString(v2), v2 = pbstrResult, v4) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                43,
                WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
                (unsigned int)v4);
            if ( v4 < 0 )
              break;
          }
        }
        v12 = ADsOpenObject(v2, 0, 0, 0xC5u, &IID_IADs, (void **)&ppObject);
        v4 = v12;
        if ( v12 < 0 )
        {
          *a1 = 0;
          if ( v12 == -2147016656 )
            v4 = 1;
          break;
        }
        v13 = *(&v33 + 2 * v9);
        if ( v13 == -1 )
        {
          MustContain = AdapSchemaSystemMustContain(ppObject);
          v4 = MustContain;
          if ( MustContain )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                44,
                WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
                MustContain);
            if ( v4 < 0 )
              goto LABEL_90;
            if ( v4 == 1 )
              goto LABEL_44;
          }
          MayContain = AdapSchemaMayContain(ppObject);
          v4 = MayContain;
          if ( MayContain )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                45,
                WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
                MayContain);
            if ( v4 < 0 )
              goto LABEL_90;
            if ( v4 == 1 )
            {
LABEL_44:
              *a1 = 0;
              goto LABEL_90;
            }
          }
        }
        else
        {
          v16 = VariantClear(&pvarg);
          v4 = v16;
          if ( v16 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v16);
            if ( v4 < 0 )
              goto LABEL_90;
          }
          Get = ppObject->lpVtbl->Get;
          v18 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"oMSyntax");
          v4 = ((__int64 (__fastcall *)(struct IADs *, _QWORD, VARIANTARG *))Get)(ppObject, *(_QWORD *)v18, &pvarg);
          SysFreeString(bstrString);
          if ( v4 )
          {
            v19 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
                (unsigned int)v4);
              v19 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v4 < 0 )
              goto LABEL_90;
          }
          else
          {
            v19 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( pvarg.vt != 3 )
          {
            v4 = -2144272373;
            if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
            {
              v26 = 48;
              goto LABEL_83;
            }
LABEL_90:
            v3 = pbstr;
            break;
          }
          if ( pvarg.lVal != v13 )
            goto LABEL_79;
          v20 = VariantClear(&pvarg);
          v4 = v20;
          if ( v20 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v20);
            if ( v4 < 0 )
              goto LABEL_90;
          }
          v21 = ppObject->lpVtbl->Get;
          v22 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v31, L"attributeSyntax");
          v4 = ((__int64 (__fastcall *)(struct IADs *, _QWORD, VARIANTARG *))v21)(ppObject, *(_QWORD *)v22, &pvarg);
          SysFreeString(v31);
          if ( v4 )
          {
            v19 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50,
                WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
                (unsigned int)v4);
              v19 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v4 < 0 )
              goto LABEL_90;
          }
          else
          {
            v19 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( pvarg.vt != 8 )
          {
            v4 = -2144272373;
            if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
            {
              v26 = 51;
LABEL_83:
              WPP_SF_d(v19[2], v26, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, 2150694923LL);
              goto LABEL_90;
            }
            goto LABEL_90;
          }
          bstrVal = pvarg.bstrVal;
          do
          {
            v24 = *(unsigned __int16 *)((char *)(&v34)[v9] + (_QWORD)bstrVal - pvarg.llVal);
            v25 = *bstrVal - v24;
            if ( v25 )
              break;
            ++bstrVal;
          }
          while ( v24 );
          if ( v25 )
          {
LABEL_79:
            *a1 = 0;
            v4 = 1;
            goto LABEL_90;
          }
        }
        if ( ppObject )
        {
          ((void (__fastcall *)(struct IADs *))ppObject->lpVtbl->Release)(ppObject);
          ppObject = 0;
        }
      }
    }
  }
LABEL_91:
  if ( ppObject )
  {
    ((void (__fastcall *)(struct IADs *))ppObject->lpVtbl->Release)(ppObject);
    ppObject = 0;
  }
  VariantClear(&pvarg);
  if ( v48 )
    CoUninitialize();
  SysFreeString(v3);
  SysFreeString(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800e88d4  push    rbp
0x1800e88d6  push    rbx
0x1800e88d7  push    rsi
0x1800e88d8  push    rdi
0x1800e88d9  push    r12
0x1800e88db  push    r13
0x1800e88dd  push    r14
0x1800e88df  push    r15
0x1800e88e1  lea     rbp, [rsp-1Fh]
0x1800e88e6  sub     rsp, 0E8h
0x1800e88ed  xor     esi, esi
0x1800e88ef  mov     r15, rcx
0x1800e88f2  xorps   xmm0, xmm0
0x1800e88f5  mov     [rbp+57h+pbstr], rsi
0x1800e88f9  xor     eax, eax
0x1800e88fb  mov     [rbp+57h+arg_18], rsi
0x1800e88ff  lea     rcx, [rsp+120h+pvarg]; pvarg
0x1800e8904  mov     qword ptr [rsp+120h+pvarg+10h], rax
0x1800e8909  movups  xmmword ptr [rsp+120h+pvarg], xmm0
0x1800e890e  mov     ebx, esi
0x1800e8910  mov     [rbp+57h+arg_0], sil
0x1800e8914  mov     r12d, esi
0x1800e8917  call    cs:__imp_VariantInit
0x1800e891e  nop     dword ptr [rax+rax+00h]
0x1800e8923  mov     [rbp+57h+var_C0], 1
0x1800e8927  lea     edx, [rsi+4]
0x1800e892a  mov     [rbp+57h+var_BC], 0FFFFFFFFh
0x1800e8931  lea     rcx, a25510; "2.5.5.10"
0x1800e8938  mov     [rbp+57h+var_B0], 1
0x1800e893c  lea     rax, aLdapCnMsFveRec_1; "LDAP://CN=ms-FVE-RecoveryInformation,"
0x1800e8943  mov     [rbp+57h+psz], rax
0x1800e8947  lea     rax, aLdapCnMsFveRec_0; "LDAP://CN=ms-FVE-RecoveryGuid,"
0x1800e894e  mov     [rbp+57h+var_68], rax
0x1800e8952  lea     rax, aLdapCnMsFveRec; "LDAP://CN=ms-FVE-RecoveryPassword,"
0x1800e8959  mov     [rbp+57h+var_60], rax
0x1800e895d  lea     rax, aLdapCnMsFveVol; "LDAP://CN=ms-FVE-VolumeGuid,"
0x1800e8964  mov     [rbp+57h+var_58], rax
0x1800e8968  lea     rax, aLdapCnMsFveKey; "LDAP://CN=ms-FVE-KeyPackage,"
0x1800e896f  mov     [rbp+57h+var_50], rax
0x1800e8973  lea     rax, cchOriginalDestLength
0x1800e897a  mov     [rbp+57h+var_B8], rax
0x1800e897e  lea     rax, a25512; "2.5.5.12"
0x1800e8985  mov     [rbp+57h+var_98], rax
0x1800e8989  lea     r13d, [rsi+40h]
0x1800e898d  mov     [rbp+57h+var_AC], edx
0x1800e8990  mov     [rbp+57h+var_A8], rcx
0x1800e8994  mov     [rbp+57h+var_A0], 1
0x1800e8998  mov     [rbp+57h+var_9C], r13d
0x1800e899c  mov     [rbp+57h+var_90], 1
0x1800e89a0  mov     [rbp+57h+var_8C], edx
0x1800e89a3  mov     [rbp+57h+var_88], rcx
0x1800e89a7  mov     [rbp+57h+var_80], 1
0x1800e89ab  mov     [rbp+57h+var_7C], edx
0x1800e89ae  mov     [rbp+57h+var_78], rcx
0x1800e89b2  test    r15, r15
0x1800e89b5  jnz     short loc_1800E89FA
0x1800e89b7  mov     edi, 80070057h
0x1800e89bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e89c3  lea     rsi, WPP_GLOBAL_Control
0x1800e89ca  cmp     rcx, rsi
0x1800e89cd  jz      loc_1800E8EB0
0x1800e89d3  test    [rcx+1Ch], r13b
0x1800e89d7  jz      loc_1800E8EB0
0x1800e89dd  mov     rcx, [rcx+10h]
0x1800e89e1  lea     edx, [r12+28h]
0x1800e89e6  mov     r9d, edi
0x1800e89e9  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e89f0  call    WPP_SF_d
0x1800e89f5  jmp     loc_1800E8EB0
0x1800e89fa  lea     rcx, [rbp+57h+arg_0]; bool *
0x1800e89fe  mov     [r15], esi
0x1800e8a01  call    ?AdapInitializeCOM@@YAJPEA_N@Z; AdapInitializeCOM(bool *)
0x1800e8a06  lea     rsi, WPP_GLOBAL_Control
0x1800e8a0d  mov     edi, eax
0x1800e8a0f  lea     r14, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e8a16  test    eax, eax
0x1800e8a18  jz      short loc_1800E8A48
0x1800e8a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8a21  cmp     rcx, rsi
0x1800e8a24  jz      short loc_1800E8A40
0x1800e8a26  test    [rcx+1Ch], r13b
0x1800e8a2a  jz      short loc_1800E8A40
0x1800e8a2c  mov     rcx, [rcx+10h]
0x1800e8a30  mov     edx, 29h ; ')'
0x1800e8a35  mov     r9d, eax
0x1800e8a38  mov     r8, r14
0x1800e8a3b  call    WPP_SF_d
0x1800e8a40  test    edi, edi
0x1800e8a42  js      loc_1800E8EB0
0x1800e8a48  lea     rdx, [rbp+57h+pbstr]; unsigned __int16 **
0x1800e8a4c  call    ?AdapGetNamingContext@@YAJPEBGPEAPEAG@Z; AdapGetNamingContext(ushort const *,ushort * *)
0x1800e8a51  mov     edi, eax
0x1800e8a53  test    eax, eax
0x1800e8a55  jz      short loc_1800E8A85
0x1800e8a57  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8a5e  cmp     rcx, rsi
0x1800e8a61  jz      short loc_1800E8A7D
0x1800e8a63  test    [rcx+1Ch], r13b
0x1800e8a67  jz      short loc_1800E8A7D
0x1800e8a69  mov     rcx, [rcx+10h]
0x1800e8a6d  mov     edx, 2Ah ; '*'
0x1800e8a72  mov     r9d, eax
0x1800e8a75  mov     r8, r14
0x1800e8a78  call    WPP_SF_d
0x1800e8a7d  test    edi, edi
0x1800e8a7f  js      loc_1800E8EAC
0x1800e8a85  xor     eax, eax
0x1800e8a87  mov     [rbp+57h+arg_8], eax
0x1800e8a8a  cmp     eax, 5
0x1800e8a8d  jnb     loc_1800E8EA5
0x1800e8a93  mov     r13, rax
0x1800e8a96  add     r13, r13
0x1800e8a99  cmp     [rbp+r13*8+57h+var_C0], 0
0x1800e8a9f  jz      loc_1800E8E36
0x1800e8aa5  mov     rdi, [rbp+rax*8+57h+psz]
0x1800e8aaa  cmp     rdi, rbx
0x1800e8aad  jz      short loc_1800E8AE2
0x1800e8aaf  mov     rcx, rbx; bstrString
0x1800e8ab2  call    cs:__imp_SysFreeString
0x1800e8ab9  nop     dword ptr [rax+rax+00h]
0x1800e8abe  test    rdi, rdi
0x1800e8ac1  jz      short loc_1800E8AE0
0x1800e8ac3  mov     rcx, rdi; psz
0x1800e8ac6  call    cs:__imp_SysAllocString
0x1800e8acd  nop     dword ptr [rax+rax+00h]
0x1800e8ad2  mov     rbx, rax
0x1800e8ad5  test    rax, rax
0x1800e8ad8  jnz     short loc_1800E8AE2
0x1800e8ada  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800e8ae0  xor     ebx, ebx
0x1800e8ae2  mov     r12, [rbp+57h+pbstr]
0x1800e8ae6  mov     rcx, r12; pbstr
0x1800e8ae9  call    cs:__imp_SysStringLen
0x1800e8af0  nop     dword ptr [rax+rax+00h]
0x1800e8af5  test    eax, eax
0x1800e8af7  jz      short loc_1800E8B65
0x1800e8af9  lea     r8, [rsp+120h+pbstrResult]; pbstrResult
0x1800e8afe  mov     [rsp+120h+pbstrResult], 0
0x1800e8b07  mov     rdx, r12; bstrRight
0x1800e8b0a  mov     rcx, rbx; bstrLeft
0x1800e8b0d  call    cs:__imp_VarBstrCat
0x1800e8b14  nop     dword ptr [rax+rax+00h]
0x1800e8b19  mov     edi, eax
0x1800e8b1b  test    eax, eax
0x1800e8b1d  js      short loc_1800E8B37
0x1800e8b1f  mov     rcx, rbx; bstrString
0x1800e8b22  call    cs:__imp_SysFreeString
0x1800e8b29  nop     dword ptr [rax+rax+00h]
0x1800e8b2e  mov     rbx, [rsp+120h+pbstrResult]
0x1800e8b33  test    edi, edi
0x1800e8b35  jz      short loc_1800E8B65
0x1800e8b37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8b3e  cmp     rcx, rsi
0x1800e8b41  jz      short loc_1800E8B5D
0x1800e8b43  test    byte ptr [rcx+1Ch], 40h
0x1800e8b47  jz      short loc_1800E8B5D
0x1800e8b49  mov     rcx, [rcx+10h]
0x1800e8b4d  mov     edx, 2Bh ; '+'
0x1800e8b52  mov     r9d, edi
0x1800e8b55  mov     r8, r14
0x1800e8b58  call    WPP_SF_d
0x1800e8b5d  test    edi, edi
0x1800e8b5f  js      loc_1800E8EB0
0x1800e8b65  lea     rax, [rbp+57h+arg_18]
0x1800e8b69  mov     r9d, 0C5h; dwReserved
0x1800e8b6f  mov     [rsp+120h+ppObject], rax; ppObject
0x1800e8b74  xor     r8d, r8d; lpszPassword
0x1800e8b77  lea     rax, IID_IADs
0x1800e8b7e  xor     edx, edx; lpszUserName
0x1800e8b80  mov     rcx, rbx; lpszPathName
0x1800e8b83  mov     [rsp+120h+riid], rax; riid
0x1800e8b88  call    cs:__imp_ADsOpenObject
0x1800e8b8f  nop     dword ptr [rax+rax+00h]
0x1800e8b94  mov     edi, eax
0x1800e8b96  test    eax, eax
0x1800e8b98  js      loc_1800E8E90
0x1800e8b9e  mov     r12d, [rbp+r13*8+57h+var_BC]
0x1800e8ba3  cmp     r12d, 0FFFFFFFFh
0x1800e8ba7  jnz     loc_1800E8C45
0x1800e8bad  mov     rcx, [rbp+57h+arg_18]; struct IADs *
0x1800e8bb1  call    ?AdapSchemaSystemMustContain@@YAJPEAUIADs@@@Z; AdapSchemaSystemMustContain(IADs *)
0x1800e8bb6  mov     edi, eax
0x1800e8bb8  test    eax, eax
0x1800e8bba  jz      short loc_1800E8BEF
0x1800e8bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8bc3  cmp     rcx, rsi
0x1800e8bc6  jz      short loc_1800E8BE2
0x1800e8bc8  test    byte ptr [rcx+1Ch], 40h
0x1800e8bcc  jz      short loc_1800E8BE2
0x1800e8bce  mov     rcx, [rcx+10h]
0x1800e8bd2  lea     edx, [r12+2Dh]
0x1800e8bd7  mov     r9d, eax
0x1800e8bda  mov     r8, r14
0x1800e8bdd  call    WPP_SF_d
0x1800e8be2  test    edi, edi
0x1800e8be4  js      loc_1800E8EAC
0x1800e8bea  cmp     edi, 1
0x1800e8bed  jz      short loc_1800E8C39
0x1800e8bef  mov     rcx, [rbp+57h+arg_18]; struct IADs *
0x1800e8bf3  call    ?AdapSchemaMayContain@@YAJPEAUIADs@@@Z; AdapSchemaMayContain(IADs *)
0x1800e8bf8  mov     edi, eax
0x1800e8bfa  test    eax, eax
0x1800e8bfc  jz      loc_1800E8E19
0x1800e8c02  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8c09  cmp     rcx, rsi
0x1800e8c0c  jz      short loc_1800E8C28
0x1800e8c0e  test    byte ptr [rcx+1Ch], 40h
0x1800e8c12  jz      short loc_1800E8C28
0x1800e8c14  mov     rcx, [rcx+10h]
0x1800e8c18  mov     edx, 2Dh ; '-'
0x1800e8c1d  mov     r9d, eax
0x1800e8c20  mov     r8, r14
0x1800e8c23  call    WPP_SF_d
0x1800e8c28  test    edi, edi
0x1800e8c2a  js      loc_1800E8EAC
0x1800e8c30  cmp     edi, 1
0x1800e8c33  jnz     loc_1800E8E19
0x1800e8c39  mov     dword ptr [r15], 0
0x1800e8c40  jmp     loc_1800E8EAC
0x1800e8c45  lea     rcx, [rsp+120h+pvarg]; pvarg
0x1800e8c4a  call    cs:__imp_VariantClear
0x1800e8c51  nop     dword ptr [rax+rax+00h]
0x1800e8c56  mov     edi, eax
0x1800e8c58  test    eax, eax
0x1800e8c5a  jz      short loc_1800E8C8A
0x1800e8c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8c63  cmp     rcx, rsi
0x1800e8c66  jz      short loc_1800E8C82
0x1800e8c68  test    byte ptr [rcx+1Ch], 40h
0x1800e8c6c  jz      short loc_1800E8C82
0x1800e8c6e  mov     rcx, [rcx+10h]
0x1800e8c72  mov     edx, 2Eh ; '.'
0x1800e8c77  mov     r9d, eax
0x1800e8c7a  mov     r8, r14
0x1800e8c7d  call    WPP_SF_d
0x1800e8c82  test    edi, edi
0x1800e8c84  js      loc_1800E8EAC
0x1800e8c8a  mov     rax, [rbp+57h+arg_18]
0x1800e8c8e  lea     rdx, aOmsyntax; "oMSyntax"
0x1800e8c95  mov     rcx, [rax]
0x1800e8c98  mov     rdi, [rcx+78h]
0x1800e8c9c  lea     rcx, [rbp+57h+bstrString]; this
0x1800e8ca0  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800e8ca5  mov     rcx, [rbp+57h+arg_18]
0x1800e8ca9  lea     r8, [rsp+120h+pvarg]
0x1800e8cae  mov     rdx, [rax]
0x1800e8cb1  mov     rax, rdi
0x1800e8cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8cb9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800e8cbd  mov     edi, eax
0x1800e8cbf  call    cs:__imp_SysFreeString
0x1800e8cc6  nop     dword ptr [rax+rax+00h]
0x1800e8ccb  test    edi, edi
0x1800e8ccd  jz      short loc_1800E8D06
0x1800e8ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8cd6  cmp     rcx, rsi
0x1800e8cd9  jz      short loc_1800E8CFC
0x1800e8cdb  test    byte ptr [rcx+1Ch], 40h
0x1800e8cdf  jz      short loc_1800E8CFC
0x1800e8ce1  mov     rcx, [rcx+10h]
0x1800e8ce5  mov     edx, 2Fh ; '/'
0x1800e8cea  mov     r9d, edi
0x1800e8ced  mov     r8, r14
0x1800e8cf0  call    WPP_SF_d
0x1800e8cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8cfc  test    edi, edi
0x1800e8cfe  js      loc_1800E8EAC
0x1800e8d04  jmp     short loc_1800E8D0D
0x1800e8d06  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8d0d  cmp     word ptr [rsp+120h+pvarg], 3
0x1800e8d13  jnz     loc_1800E8E75
0x1800e8d19  cmp     dword ptr [rsp+120h+pvarg+8], r12d
0x1800e8d1e  jnz     loc_1800E8E40
0x1800e8d24  lea     rcx, [rsp+120h+pvarg]; pvarg
0x1800e8d29  call    cs:__imp_VariantClear
0x1800e8d30  nop     dword ptr [rax+rax+00h]
0x1800e8d35  mov     edi, eax
0x1800e8d37  test    eax, eax
0x1800e8d39  jz      short loc_1800E8D69
0x1800e8d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8d42  cmp     rcx, rsi
0x1800e8d45  jz      short loc_1800E8D61
0x1800e8d47  test    byte ptr [rcx+1Ch], 40h
0x1800e8d4b  jz      short loc_1800E8D61
0x1800e8d4d  mov     rcx, [rcx+10h]
0x1800e8d51  mov     edx, 31h ; '1'
0x1800e8d56  mov     r9d, eax
0x1800e8d59  mov     r8, r14
0x1800e8d5c  call    WPP_SF_d
0x1800e8d61  test    edi, edi
0x1800e8d63  js      loc_1800E8EAC
0x1800e8d69  mov     rax, [rbp+57h+arg_18]
0x1800e8d6d  lea     rdx, aAttributesynta; "attributeSyntax"
0x1800e8d74  mov     rcx, [rax]
0x1800e8d77  mov     rdi, [rcx+78h]
0x1800e8d7b  lea     rcx, [rbp+57h+var_C8]; this
0x1800e8d7f  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800e8d84  mov     rcx, [rbp+57h+arg_18]
0x1800e8d88  lea     r8, [rsp+120h+pvarg]
0x1800e8d8d  mov     rdx, [rax]
  ... truncated ...
```
