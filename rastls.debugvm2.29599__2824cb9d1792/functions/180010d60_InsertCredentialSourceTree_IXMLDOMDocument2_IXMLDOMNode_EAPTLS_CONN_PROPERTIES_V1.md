# InsertCredentialSourceTree(IXMLDOMDocument2 * *,IXMLDOMNode * *,_EAPTLS_CONN_PROPERTIES_V1 *)

- ea: `0x180010d60`
- end: `0x180011343`
- name: `?InsertCredentialSourceTree@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `1507`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 **, struct IXMLDOMNode **, struct _EAPTLS_CONN_PROPERTIES_V1 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ec0`

## callees

- `0x180004bd0`
- `0x180010d60`
- `0x180011350`
- `0x18007c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010dac`
- `OLEAUT32!__imp_SysAllocString` at `0x180010dcd`
- `OLEAUT32!__imp_SysAllocString` at `0x180010eb4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001103c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800110a7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800110db`
- `OLEAUT32!__imp_SysAllocString` at `0x180011295`
- `OLEAUT32!__imp_SysAllocString` at `0x180010dac`
- `OLEAUT32!__imp_SysAllocString` at `0x180010dcd`
- `OLEAUT32!__imp_SysAllocString` at `0x180010eb4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001103c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800110a7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800110db`
- `OLEAUT32!__imp_SysAllocString` at `0x180011295`
- `OLEAUT32!__imp_SysFreeString` at `0x180010e8a`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ed6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001100f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001119d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800111a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800112f7`
- `OLEAUT32!__imp_SysFreeString` at `0x180010e8a`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ed6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001100f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001119d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800111a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800112f7`
- `OLEAUT32!__imp_VariantInit` at `0x180010deb`
- `OLEAUT32!__imp_VariantInit` at `0x180010e11`
- `OLEAUT32!__imp_VariantInit` at `0x180010f6f`
- `OLEAUT32!__imp_VariantInit` at `0x180010f96`
- `OLEAUT32!__imp_VariantInit` at `0x1800110d2`
- `OLEAUT32!__imp_VariantInit` at `0x18001111c`
- `OLEAUT32!__imp_VariantInit` at `0x1800112b1`
- `OLEAUT32!__imp_VariantInit` at `0x180010deb`
- `OLEAUT32!__imp_VariantInit` at `0x180010e11`
- `OLEAUT32!__imp_VariantInit` at `0x180010f6f`
- `OLEAUT32!__imp_VariantInit` at `0x180010f96`
- `OLEAUT32!__imp_VariantInit` at `0x1800110d2`
- `OLEAUT32!__imp_VariantInit` at `0x18001111c`
- `OLEAUT32!__imp_VariantInit` at `0x1800112b1`
- `OLEAUT32!__imp_VariantClear` at `0x180010e64`
- `OLEAUT32!__imp_VariantClear` at `0x180010e94`
- `OLEAUT32!__imp_VariantClear` at `0x180010fe9`
- `OLEAUT32!__imp_VariantClear` at `0x180011019`
- `OLEAUT32!__imp_VariantClear` at `0x18001116f`
- `OLEAUT32!__imp_VariantClear` at `0x1800111b0`
- `OLEAUT32!__imp_VariantClear` at `0x180011301`
- `OLEAUT32!__imp_VariantClear` at `0x180010e64`
- `OLEAUT32!__imp_VariantClear` at `0x180010e94`
- `OLEAUT32!__imp_VariantClear` at `0x180010fe9`
- `OLEAUT32!__imp_VariantClear` at `0x180011019`
- `OLEAUT32!__imp_VariantClear` at `0x18001116f`
- `OLEAUT32!__imp_VariantClear` at `0x1800111b0`
- `OLEAUT32!__imp_VariantClear` at `0x180011301`

## string_xrefs

- `0x180010d99`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1`

## pseudocode

```c
__int64 __fastcall InsertCredentialSourceTree(
        struct IXMLDOMDocument2 **a1,
        struct IXMLDOMNode **a2,
        struct _EAPTLS_CONN_PROPERTIES_V1 *a3)
{
  OLECHAR *v6; // rsi
  OLECHAR *v7; // rdi
  __int64 v8; // r12
  struct IXMLDOMDocument2 *v9; // rbx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *createNode)(IXMLDOMDocument2 *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  unsigned int v12; // ebx
  OLECHAR *v13; // rdi
  struct IXMLDOMNode *v15; // r12
  struct IXMLDOMDocument2 *v16; // rbx
  struct IXMLDOMDocument2Vtbl *v17; // rax
  HRESULT (__stdcall *v18)(IXMLDOMDocument2 *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  const OLECHAR *v19; // rcx
  OLECHAR *v20; // rdi
  OLECHAR *v21; // r14
  BSTR v22; // rax
  IRecordInfo *pRecInfo; // xmm6_8
  struct IXMLDOMNode *v24; // r12
  struct IXMLDOMDocument2 *v25; // rbx
  struct IXMLDOMDocument2Vtbl *v26; // rax
  HRESULT (__stdcall *v27)(IXMLDOMDocument2 *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  struct _EAPTLS_CONTROL_BLOCK *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  unsigned __int16 *v31; // rdi
  struct IXMLDOMDocument2 *v32; // rcx
  __int64 *v33; // [rsp+38h] [rbp-59h] BYREF
  VARIANTARG v34; // [rsp+40h] [rbp-51h] BYREF
  struct IXMLDOMNode *v35; // [rsp+58h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-31h] BYREF
  struct tagVARIANT v37; // [rsp+78h] [rbp-19h] BYREF
  __int64 v38; // [rsp+98h] [rbp+7h] BYREF
  VARIANTARG v39; // [rsp+A0h] [rbp+Fh] BYREF
  struct IXMLDOMNode *v40; // [rsp+110h] [rbp+7Fh] BYREF

  v40 = 0;
  v35 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v38 = 0;
  v6 = SysAllocString(L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1");
  if ( v6 )
  {
    v7 = SysAllocString(L"CredentialsSource");
    if ( v7 )
    {
      VariantInit(&pvarg);
      v8 = (__int64)*a2;
      v9 = *a1;
      pvarg.vt = 0;
      memset(&v34, 0, sizeof(v34));
      v33 = 0;
      VariantInit(&v34);
      v34.lVal = 1;
      v34.vt = 3;
      lpVtbl = v9->lpVtbl;
      v37.pRecInfo = v34.pRecInfo;
      createNode = lpVtbl->createNode;
      *(_OWORD *)&v37.vt = *(_OWORD *)&v34.vt;
      v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct tagVARIANT *, OLECHAR *, OLECHAR *, __int64 **))createNode)(
              v9,
              &v37,
              v7,
              v6,
              &v33);
      VariantClear(&v34);
      if ( !v12 )
        v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, struct IXMLDOMNode **))(*(_QWORD *)v8 + 168LL))(
                v8,
                v33,
                &v40);
      if ( v33 )
        (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
      SysFreeString(v7);
      VariantClear(&pvarg);
      if ( v12 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_11;
        v29 = 98;
      }
      else if ( (*((_BYTE *)a3 + 8) & 1) != 0 )
      {
        v13 = SysAllocString(L"CertificateStore");
        if ( !v13 )
        {
          v12 = -2147024882;
LABEL_11:
          SysFreeString(v6);
          goto LABEL_12;
        }
        VariantInit(&pvarg);
        v15 = v40;
        v16 = *a1;
        pvarg.vt = 0;
        memset(&v34, 0, sizeof(v34));
        v33 = 0;
        VariantInit(&v34);
        v34.lVal = 1;
        v34.vt = 3;
        v17 = v16->lpVtbl;
        v37.pRecInfo = v34.pRecInfo;
        v18 = v17->createNode;
        *(_OWORD *)&v37.vt = *(_OWORD *)&v34.vt;
        v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct tagVARIANT *, OLECHAR *, OLECHAR *, __int64 **))v18)(
                v16,
                &v37,
                v13,
                v6,
                &v33);
        VariantClear(&v34);
        if ( !v12 )
          v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *, struct IXMLDOMNode **))v15->lpVtbl->appendChild)(
                  v15,
                  v33,
                  &v35);
        if ( v33 )
          (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
        SysFreeString(v13);
        VariantClear(&pvarg);
        if ( v12 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_11;
          v29 = 99;
        }
        else
        {
          v19 = L"true";
          if ( (*((_BYTE *)a3 + 8) & 0x10) == 0 )
            v19 = L"false";
          v20 = SysAllocString(v19);
          if ( !v20 )
          {
            v12 = -2147024882;
            goto LABEL_11;
          }
          v21 = SysAllocString(L"SimpleCertSelection");
          if ( !v21 )
          {
            v12 = -2147024882;
            goto LABEL_11;
          }
          memset(&v39, 0, sizeof(v39));
          VariantInit(&v39);
          v22 = SysAllocString(v20);
          pRecInfo = v39.pRecInfo;
          v24 = v35;
          v25 = *a1;
          v39.llVal = (LONGLONG)v22;
          v39.vt = 8;
          v33 = 0;
          pvarg = v39;
          memset(&v34, 0, sizeof(v34));
          VariantInit(&v34);
          v34.lVal = 1;
          v34.vt = 3;
          v26 = v25->lpVtbl;
          v37.pRecInfo = v34.pRecInfo;
          v27 = v26->createNode;
          *(_OWORD *)&v37.vt = *(_OWORD *)&v34.vt;
          v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct tagVARIANT *, OLECHAR *, OLECHAR *, __int64 **))v27)(
                  v25,
                  &v37,
                  v21,
                  v6,
                  &v33);
          VariantClear(&v34);
          if ( !v12 )
          {
            v37.vt = 8;
            v30 = *v33;
            *(_OWORD *)&v37.decVal.scale = *(_OWORD *)&v39.decVal.scale;
            v37.pRecInfo = pRecInfo;
            v12 = (*(__int64 (__fastcall **)(__int64 *, struct tagVARIANT *))(v30 + 248))(v33, &v37);
            if ( !v12 )
              v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *, __int64 *))v24->lpVtbl->appendChild)(
                      v24,
                      v33,
                      &v38);
          }
          if ( v33 )
            (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
          SysFreeString(v21);
          SysFreeString(v20);
          VariantClear(&pvarg);
          if ( !v12 )
            goto LABEL_11;
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_11;
          v29 = 100;
        }
      }
      else
      {
        v31 = SysAllocString(L"SmartCard");
        if ( !v31 )
        {
          v12 = -2147024882;
          goto LABEL_11;
        }
        VariantInit(&pvarg);
        v32 = *a1;
        pvarg.vt = 0;
        v37 = pvarg;
        v12 = AddNode(v32, v40, v6, v31, &v37, &v35);
        SysFreeString(v31);
        VariantClear(&pvarg);
        if ( !v12 )
          goto LABEL_11;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_11;
        v29 = 101;
      }
      WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v12);
      goto LABEL_11;
    }
    v12 = -2147024882;
    goto LABEL_11;
  }
  v12 = -2147024882;
LABEL_12:
  if ( v40 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v40->lpVtbl->Release)(v40);
    v40 = 0;
  }
  if ( v35 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v35->lpVtbl->Release)(v35);
    v35 = 0;
  }
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  return v12;
}

```

## disassembly

```asm
0x180010d60  mov     rax, rsp
0x180010d63  push    rbp
0x180010d64  push    rbx
0x180010d65  lea     rbp, [rax-5Fh]
0x180010d69  sub     rsp, 0D8h
0x180010d70  mov     [rax+8], rsi
0x180010d74  xorps   xmm0, xmm0
0x180010d77  mov     [rax-18h], r13
0x180010d7b  mov     rbx, rdx
0x180010d7e  mov     [rax-20h], r14
0x180010d82  xor     r13d, r13d
0x180010d85  mov     [rax-28h], r15
0x180010d89  mov     r14, r8
0x180010d8c  mov     r15, rcx
0x180010d8f  mov     [rbp+57h+arg_18], r13
0x180010d93  xor     eax, eax
0x180010d95  mov     [rbp+57h+var_90], r13
0x180010d99  lea     rcx, aHttpWwwMicroso_4; "http://www.microsoft.com/provisioning/E"...
0x180010da0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180010da4  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180010da8  mov     [rbp+57h+var_50], r13
0x180010dac  call    cs:__imp_SysAllocString
0x180010db2  mov     rsi, rax
0x180010db5  test    rax, rax
0x180010db8  jz      loc_1800111DF
0x180010dbe  lea     rcx, aCredentialssou; "CredentialsSource"
0x180010dc5  mov     [rsp+0E0h+arg_8], rdi
0x180010dcd  call    cs:__imp_SysAllocString
0x180010dd3  mov     rdi, rax
0x180010dd6  test    rax, rax
0x180010dd9  jz      loc_180010F61
0x180010ddf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180010de3  mov     [rsp+0E0h+arg_10], r12
0x180010deb  call    cs:__imp_VariantInit
0x180010df1  mov     r12, [rbx]
0x180010df4  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180010df8  mov     rbx, [r15]
0x180010dfb  xorps   xmm0, xmm0
0x180010dfe  xor     eax, eax
0x180010e00  mov     word ptr [rbp+57h+pvarg], r13w
0x180010e05  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180010e09  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x180010e0d  mov     [rbp+57h+var_B0], r13
0x180010e11  call    cs:__imp_VariantInit
0x180010e17  movsd   xmm1, qword ptr [rbp+57h+var_A8+10h]
0x180010e1c  lea     rcx, [rbp+57h+var_B0]
0x180010e20  mov     eax, 3
0x180010e25  mov     dword ptr [rbp+57h+var_A8+8], 1
0x180010e2c  mov     word ptr [rbp+57h+var_A8], ax
0x180010e30  lea     rdx, [rbp+57h+var_70]
0x180010e34  mov     rax, [rbx]
0x180010e37  mov     r9, rsi
0x180010e3a  movups  xmm0, xmmword ptr [rbp+57h+var_A8]
0x180010e3e  mov     [rsp+0E0h+var_C0], rcx
0x180010e43  mov     r8, rdi
0x180010e46  mov     rcx, rbx
0x180010e49  movsd   qword ptr [rbp+57h+var_70+10h], xmm1
0x180010e4e  mov     rax, [rax+1C0h]
0x180010e55  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x180010e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e5e  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180010e62  mov     ebx, eax
0x180010e64  call    cs:__imp_VariantClear
0x180010e6a  test    ebx, ebx
0x180010e6c  jz      loc_180010F3F
0x180010e72  mov     rcx, [rbp+57h+var_B0]
0x180010e76  test    rcx, rcx
0x180010e79  jz      short loc_180010E87
0x180010e7b  mov     rax, [rcx]
0x180010e7e  mov     rax, [rax+10h]
0x180010e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e87  mov     rcx, rdi; bstrString
0x180010e8a  call    cs:__imp_SysFreeString
0x180010e90  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180010e94  call    cs:__imp_VariantClear
0x180010e9a  test    ebx, ebx
0x180010e9c  jnz     loc_1800111E9
0x180010ea2  test    byte ptr [r14+8], 1
0x180010ea7  jz      loc_18001128E
0x180010ead  lea     rcx, aCertificatesto; "CertificateStore"
0x180010eb4  call    cs:__imp_SysAllocString
0x180010eba  mov     rdi, rax
0x180010ebd  test    rax, rax
0x180010ec0  jnz     loc_180010F6B
0x180010ec6  mov     ebx, 8007000Eh
0x180010ecb  mov     r12, [rsp+0E0h+arg_10]
0x180010ed3  mov     rcx, rsi; bstrString
0x180010ed6  call    cs:__imp_SysFreeString
0x180010edc  mov     rdi, [rsp+0E0h+arg_8]
0x180010ee4  mov     rcx, [rbp+57h+arg_18]
0x180010ee8  mov     r15, [rsp+0E0h+var_20]
0x180010ef0  mov     r14, [rsp+0E0h+var_18]
0x180010ef8  mov     rsi, [rsp+0E0h+arg_0]
0x180010f00  test    rcx, rcx
0x180010f03  jnz     loc_180011054
0x180010f09  mov     rcx, [rbp+57h+var_90]
0x180010f0d  test    rcx, rcx
0x180010f10  jnz     loc_180011069
0x180010f16  mov     rcx, [rbp+57h+var_50]
0x180010f1a  mov     r13, [rsp+0D0h]
0x180010f22  test    rcx, rcx
0x180010f25  jz      short loc_180010F33
0x180010f27  mov     rax, [rcx]
0x180010f2a  mov     rax, [rax+10h]
0x180010f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f33  mov     eax, ebx
0x180010f35  add     rsp, 0D8h
0x180010f3c  pop     rbx
0x180010f3d  pop     rbp
0x180010f3e  retn
0x180010f3f  mov     rax, [r12]
0x180010f43  lea     r8, [rbp+57h+arg_18]
0x180010f47  mov     rdx, [rbp+57h+var_B0]
0x180010f4b  mov     rcx, r12
0x180010f4e  mov     rax, [rax+0A8h]
0x180010f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f5a  mov     ebx, eax
0x180010f5c  jmp     loc_180010E72
0x180010f61  mov     ebx, 8007000Eh
0x180010f66  jmp     loc_180010ED3
0x180010f6b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180010f6f  call    cs:__imp_VariantInit
0x180010f75  mov     r12, [rbp+57h+arg_18]
0x180010f79  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180010f7d  mov     rbx, [r15]
0x180010f80  xorps   xmm0, xmm0
0x180010f83  xor     eax, eax
0x180010f85  mov     word ptr [rbp+57h+pvarg], r13w
0x180010f8a  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180010f8e  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x180010f92  mov     [rbp+57h+var_B0], r13
0x180010f96  call    cs:__imp_VariantInit
0x180010f9c  movsd   xmm1, qword ptr [rbp+57h+var_A8+10h]
0x180010fa1  lea     rcx, [rbp+57h+var_B0]
0x180010fa5  mov     eax, 3
0x180010faa  mov     dword ptr [rbp+57h+var_A8+8], 1
0x180010fb1  mov     word ptr [rbp+57h+var_A8], ax
0x180010fb5  lea     rdx, [rbp+57h+var_70]
0x180010fb9  mov     rax, [rbx]
0x180010fbc  mov     r9, rsi
0x180010fbf  movups  xmm0, xmmword ptr [rbp+57h+var_A8]
0x180010fc3  mov     [rsp+0E0h+var_C0], rcx
0x180010fc8  mov     r8, rdi
0x180010fcb  mov     rcx, rbx
0x180010fce  movsd   qword ptr [rbp+57h+var_70+10h], xmm1
0x180010fd3  mov     rax, [rax+1C0h]
0x180010fda  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x180010fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fe3  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180010fe7  mov     ebx, eax
0x180010fe9  call    cs:__imp_VariantClear
0x180010fef  test    ebx, ebx
0x180010ff1  jz      loc_18001107E
0x180010ff7  mov     rcx, [rbp+57h+var_B0]
0x180010ffb  test    rcx, rcx
0x180010ffe  jz      short loc_18001100C
0x180011000  mov     rax, [rcx]
0x180011003  mov     rax, [rax+10h]
0x180011007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001100c  mov     rcx, rdi; bstrString
0x18001100f  call    cs:__imp_SysFreeString
0x180011015  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180011019  call    cs:__imp_VariantClear
0x18001101f  test    ebx, ebx
0x180011021  jnz     loc_18001120A
0x180011027  test    byte ptr [r14+8], 10h
0x18001102c  lea     rcx, String2; "true"
0x180011033  jnz     short loc_18001103C
0x180011035  lea     rcx, aFalse; "false"
0x18001103c  call    cs:__imp_SysAllocString
0x180011042  mov     rdi, rax
0x180011045  test    rax, rax
0x180011048  jnz     short loc_1800110A0
0x18001104a  mov     ebx, 8007000Eh
0x18001104f  jmp     loc_180010ECB
0x180011054  mov     rax, [rcx]
0x180011057  mov     rax, [rax+10h]
0x18001105b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011060  mov     [rbp+57h+arg_18], r13
0x180011064  jmp     loc_180010F09
0x180011069  mov     rax, [rcx]
0x18001106c  mov     rax, [rax+10h]
0x180011070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011075  mov     [rbp+57h+var_90], r13
0x180011079  jmp     loc_180010F16
0x18001107e  mov     rax, [r12]
0x180011082  lea     r8, [rbp+57h+var_90]
0x180011086  mov     rdx, [rbp+57h+var_B0]
0x18001108a  mov     rcx, r12
0x18001108d  mov     rax, [rax+0A8h]
0x180011094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011099  mov     ebx, eax
0x18001109b  jmp     loc_180010FF7
0x1800110a0  lea     rcx, aSimplecertsele; "SimpleCertSelection"
0x1800110a7  call    cs:__imp_SysAllocString
0x1800110ad  mov     r14, rax
0x1800110b0  test    rax, rax
0x1800110b3  jz      loc_18001122B
0x1800110b9  xorps   xmm0, xmm0
0x1800110bc  movaps  xmmword ptr [rsp+0B0h], xmm6
0x1800110c4  xor     eax, eax
0x1800110c6  lea     rcx, [rbp+57h+var_48]; pvarg
0x1800110ca  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800110ce  mov     qword ptr [rbp+57h+var_48+10h], rax
0x1800110d2  call    cs:__imp_VariantInit
0x1800110d8  mov     rcx, rdi; psz
0x1800110db  call    cs:__imp_SysAllocString
0x1800110e1  movsd   xmm6, qword ptr [rbp+57h+var_48+10h]
0x1800110e6  lea     rcx, [rbp+57h+var_A8]; pvarg
0x1800110ea  mov     r12, [rbp+57h+var_90]
0x1800110ee  mov     rbx, [r15]
0x1800110f1  mov     qword ptr [rbp+57h+var_48+8], rax
0x1800110f5  mov     eax, 8
0x1800110fa  mov     word ptr [rbp+57h+var_48], ax
0x1800110fe  xor     eax, eax
0x180011100  movups  xmm0, xmmword ptr [rbp+57h+var_48]
0x180011104  mov     [rbp+57h+var_B0], r13
0x180011108  movsd   qword ptr [rbp+57h+pvarg+10h], xmm6
0x18001110d  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180011111  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x180011115  xorps   xmm0, xmm0
0x180011118  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x18001111c  call    cs:__imp_VariantInit
0x180011122  movsd   xmm1, qword ptr [rbp+57h+var_A8+10h]
0x180011127  lea     rcx, [rbp+57h+var_B0]
0x18001112b  mov     eax, 3
0x180011130  mov     dword ptr [rbp+57h+var_A8+8], 1
0x180011137  mov     word ptr [rbp+57h+var_A8], ax
0x18001113b  lea     rdx, [rbp+57h+var_70]
0x18001113f  mov     rax, [rbx]
0x180011142  mov     r9, rsi
0x180011145  movups  xmm0, xmmword ptr [rbp+57h+var_A8]
0x180011149  mov     [rsp+0E0h+var_C0], rcx
0x18001114e  mov     r8, r14
0x180011151  mov     rcx, rbx
0x180011154  movsd   qword ptr [rbp+57h+var_70+10h], xmm1
0x180011159  mov     rax, [rax+1C0h]
0x180011160  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x180011164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011169  lea     rcx, [rbp+57h+var_A8]; pvarg
0x18001116d  mov     ebx, eax
0x18001116f  call    cs:__imp_VariantClear
0x180011175  test    ebx, ebx
0x180011177  jz      loc_180011235
0x18001117d  mov     rcx, [rbp+57h+var_B0]
0x180011181  movaps  xmm6, xmmword ptr [rsp+0B0h]
0x180011189  test    rcx, rcx
0x18001118c  jz      short loc_18001119A
0x18001118e  mov     rax, [rcx]
0x180011191  mov     rax, [rax+10h]
0x180011195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001119a  mov     rcx, r14; bstrString
0x18001119d  call    cs:__imp_SysFreeString
0x1800111a3  mov     rcx, rdi; bstrString
0x1800111a6  call    cs:__imp_SysFreeString
0x1800111ac  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800111b0  call    cs:__imp_VariantClear
0x1800111b6  test    ebx, ebx
0x1800111b8  jz      loc_180010ECB
0x1800111be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111c5  lea     rax, WPP_GLOBAL_Control
0x1800111cc  cmp     rcx, rax
0x1800111cf  jz      loc_180010ECB
0x1800111d5  mov     edx, 64h ; 'd'
0x1800111da  jmp     loc_18001132B
0x1800111df  mov     ebx, 8007000Eh
0x1800111e4  jmp     loc_180010EE4
0x1800111e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111f0  lea     rax, WPP_GLOBAL_Control
0x1800111f7  cmp     rcx, rax
0x1800111fa  jz      loc_180010ECB
0x180011200  mov     edx, 62h ; 'b'
0x180011205  jmp     loc_18001132B
0x18001120a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011211  lea     rax, WPP_GLOBAL_Control
0x180011218  cmp     rcx, rax
0x18001121b  jz      loc_180010ECB
0x180011221  mov     edx, 63h ; 'c'
0x180011226  jmp     loc_18001132B
0x18001122b  mov     ebx, 8007000Eh
0x180011230  jmp     loc_180010ECB
0x180011235  mov     rcx, [rbp+57h+var_B0]
0x180011239  lea     rdx, [rbp+57h+var_70]
0x18001123d  movups  xmm0, xmmword ptr [rbp+57h+var_48+2]
0x180011241  mov     eax, 8
0x180011246  mov     word ptr [rbp+57h+var_70], ax
0x18001124a  mov     rax, [rcx]
0x18001124d  movups  xmmword ptr [rbp+57h+var_70+2], xmm0
0x180011251  movsd   qword ptr [rbp+57h+var_70+10h], xmm6
0x180011256  mov     rax, [rax+0F8h]
0x18001125d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011262  mov     ebx, eax
0x180011264  test    eax, eax
0x180011266  jnz     loc_18001117D
0x18001126c  mov     rax, [r12]
0x180011270  lea     r8, [rbp+57h+var_50]
0x180011274  mov     rdx, [rbp+57h+var_B0]
0x180011278  mov     rcx, r12
0x18001127b  mov     rax, [rax+0A8h]
0x180011282  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
