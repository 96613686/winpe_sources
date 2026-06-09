# InsertCredentialSourceTree(IXMLDOMDocument2 * *,IXMLDOMNode * *,_EAPTLS_CONN_PROPERTIES_V1 *)

- ea: `0x180011d80`
- end: `0x180012406`
- name: `?InsertCredentialSourceTree@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `1670`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 **, struct IXMLDOMNode **, struct _EAPTLS_CONN_PROPERTIES_V1 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800086a0`

## callees

- `0x180005010`
- `0x180011d80`
- `0x180012410`
- `0x180082010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011dcc`
- `OLEAUT32!__imp_SysAllocString` at `0x180011df3`
- `OLEAUT32!__imp_SysAllocString` at `0x180011efe`
- `OLEAUT32!__imp_SysAllocString` at `0x1800120b1`
- `OLEAUT32!__imp_SysAllocString` at `0x180012122`
- `OLEAUT32!__imp_SysAllocString` at `0x180012162`
- `OLEAUT32!__imp_SysAllocString` at `0x180012340`
- `OLEAUT32!__imp_SysAllocString` at `0x180011dcc`
- `OLEAUT32!__imp_SysAllocString` at `0x180011df3`
- `OLEAUT32!__imp_SysAllocString` at `0x180011efe`
- `OLEAUT32!__imp_SysAllocString` at `0x1800120b1`
- `OLEAUT32!__imp_SysAllocString` at `0x180012122`
- `OLEAUT32!__imp_SysAllocString` at `0x180012162`
- `OLEAUT32!__imp_SysAllocString` at `0x180012340`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ec8`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f26`
- `OLEAUT32!__imp_SysFreeString` at `0x180012078`
- `OLEAUT32!__imp_SysFreeString` at `0x180012236`
- `OLEAUT32!__imp_SysFreeString` at `0x180012245`
- `OLEAUT32!__imp_SysFreeString` at `0x1800123ae`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ec8`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f26`
- `OLEAUT32!__imp_SysFreeString` at `0x180012078`
- `OLEAUT32!__imp_SysFreeString` at `0x180012236`
- `OLEAUT32!__imp_SysFreeString` at `0x180012245`
- `OLEAUT32!__imp_SysFreeString` at `0x1800123ae`
- `OLEAUT32!__imp_VariantInit` at `0x180011e17`
- `OLEAUT32!__imp_VariantInit` at `0x180011e43`
- `OLEAUT32!__imp_VariantInit` at `0x180011fc6`
- `OLEAUT32!__imp_VariantInit` at `0x180011ff3`
- `OLEAUT32!__imp_VariantInit` at `0x180012153`
- `OLEAUT32!__imp_VariantInit` at `0x1800121a9`
- `OLEAUT32!__imp_VariantInit` at `0x180012362`
- `OLEAUT32!__imp_VariantInit` at `0x180011e17`
- `OLEAUT32!__imp_VariantInit` at `0x180011e43`
- `OLEAUT32!__imp_VariantInit` at `0x180011fc6`
- `OLEAUT32!__imp_VariantInit` at `0x180011ff3`
- `OLEAUT32!__imp_VariantInit` at `0x180012153`
- `OLEAUT32!__imp_VariantInit` at `0x1800121a9`
- `OLEAUT32!__imp_VariantInit` at `0x180012362`
- `OLEAUT32!__imp_VariantClear` at `0x180011e9c`
- `OLEAUT32!__imp_VariantClear` at `0x180011ed8`
- `OLEAUT32!__imp_VariantClear` at `0x18001204c`
- `OLEAUT32!__imp_VariantClear` at `0x180012088`
- `OLEAUT32!__imp_VariantClear` at `0x180012202`
- `OLEAUT32!__imp_VariantClear` at `0x180012255`
- `OLEAUT32!__imp_VariantClear` at `0x1800123be`
- `OLEAUT32!__imp_VariantClear` at `0x180011e9c`
- `OLEAUT32!__imp_VariantClear` at `0x180011ed8`
- `OLEAUT32!__imp_VariantClear` at `0x18001204c`
- `OLEAUT32!__imp_VariantClear` at `0x180012088`
- `OLEAUT32!__imp_VariantClear` at `0x180012202`
- `OLEAUT32!__imp_VariantClear` at `0x180012255`
- `OLEAUT32!__imp_VariantClear` at `0x1800123be`

## string_xrefs

- `0x180011db9`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1`

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
0x180011d80  mov     rax, rsp
0x180011d83  push    rbp
0x180011d84  push    rbx
0x180011d85  lea     rbp, [rax-5Fh]
0x180011d89  sub     rsp, 0D8h
0x180011d90  mov     [rax+8], rsi
0x180011d94  xorps   xmm0, xmm0
0x180011d97  mov     [rax-18h], r13
0x180011d9b  mov     rbx, rdx
0x180011d9e  mov     [rax-20h], r14
0x180011da2  xor     r13d, r13d
0x180011da5  mov     [rax-28h], r15
0x180011da9  mov     r14, r8
0x180011dac  mov     r15, rcx
0x180011daf  mov     [rbp+57h+arg_18], r13
0x180011db3  xor     eax, eax
0x180011db5  mov     [rbp+57h+var_90], r13
0x180011db9  lea     rcx, aHttpWwwMicroso_4; "http://www.microsoft.com/provisioning/E"...
0x180011dc0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180011dc4  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180011dc8  mov     [rbp+57h+var_50], r13
0x180011dcc  call    cs:__imp_SysAllocString
0x180011dd3  nop     dword ptr [rax+rax+00h]
0x180011dd8  mov     rsi, rax
0x180011ddb  test    rax, rax
0x180011dde  jz      loc_18001228A
0x180011de4  lea     rcx, aCredentialssou; "CredentialsSource"
0x180011deb  mov     [rsp+0E0h+arg_8], rdi
0x180011df3  call    cs:__imp_SysAllocString
0x180011dfa  nop     dword ptr [rax+rax+00h]
0x180011dff  mov     rdi, rax
0x180011e02  test    rax, rax
0x180011e05  jz      loc_180011FB8
0x180011e0b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180011e0f  mov     [rsp+0E0h+arg_10], r12
0x180011e17  call    cs:__imp_VariantInit
0x180011e1e  nop     dword ptr [rax+rax+00h]
0x180011e23  mov     r12, [rbx]
0x180011e26  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180011e2a  mov     rbx, [r15]
0x180011e2d  xorps   xmm0, xmm0
0x180011e30  xor     eax, eax
0x180011e32  mov     word ptr [rbp+57h+pvarg], r13w
0x180011e37  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180011e3b  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x180011e3f  mov     [rbp+57h+var_B0], r13
0x180011e43  call    cs:__imp_VariantInit
0x180011e4a  nop     dword ptr [rax+rax+00h]
0x180011e4f  movsd   xmm1, qword ptr [rbp+57h+var_A8+10h]
0x180011e54  lea     rcx, [rbp+57h+var_B0]
0x180011e58  mov     eax, 3
0x180011e5d  mov     dword ptr [rbp+57h+var_A8+8], 1
0x180011e64  mov     word ptr [rbp+57h+var_A8], ax
0x180011e68  lea     rdx, [rbp+57h+var_70]
0x180011e6c  mov     rax, [rbx]
0x180011e6f  mov     r9, rsi
0x180011e72  movups  xmm0, xmmword ptr [rbp+57h+var_A8]
0x180011e76  mov     [rsp+0E0h+var_C0], rcx
0x180011e7b  mov     r8, rdi
0x180011e7e  mov     rcx, rbx
0x180011e81  movsd   qword ptr [rbp+57h+var_70+10h], xmm1
0x180011e86  mov     rax, [rax+1C0h]
0x180011e8d  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x180011e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e96  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180011e9a  mov     ebx, eax
0x180011e9c  call    cs:__imp_VariantClear
0x180011ea3  nop     dword ptr [rax+rax+00h]
0x180011ea8  test    ebx, ebx
0x180011eaa  jz      loc_180011F96
0x180011eb0  mov     rcx, [rbp+57h+var_B0]
0x180011eb4  test    rcx, rcx
0x180011eb7  jz      short loc_180011EC5
0x180011eb9  mov     rax, [rcx]
0x180011ebc  mov     rax, [rax+10h]
0x180011ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ec5  mov     rcx, rdi; bstrString
0x180011ec8  call    cs:__imp_SysFreeString
0x180011ecf  nop     dword ptr [rax+rax+00h]
0x180011ed4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180011ed8  call    cs:__imp_VariantClear
0x180011edf  nop     dword ptr [rax+rax+00h]
0x180011ee4  test    ebx, ebx
0x180011ee6  jnz     loc_180012294
0x180011eec  test    byte ptr [r14+8], 1
0x180011ef1  jz      loc_180012339
0x180011ef7  lea     rcx, aCertificatesto; "CertificateStore"
0x180011efe  call    cs:__imp_SysAllocString
0x180011f05  nop     dword ptr [rax+rax+00h]
0x180011f0a  mov     rdi, rax
0x180011f0d  test    rax, rax
0x180011f10  jnz     loc_180011FC2
0x180011f16  mov     ebx, 8007000Eh
0x180011f1b  mov     r12, [rsp+0E0h+arg_10]
0x180011f23  mov     rcx, rsi; bstrString
0x180011f26  call    cs:__imp_SysFreeString
0x180011f2d  nop     dword ptr [rax+rax+00h]
0x180011f32  mov     rdi, [rsp+0E0h+arg_8]
0x180011f3a  mov     rcx, [rbp+57h+arg_18]
0x180011f3e  mov     r15, [rsp+0E0h+var_20]
0x180011f46  mov     r14, [rsp+0E0h+var_18]
0x180011f4e  mov     rsi, [rsp+0E0h+arg_0]
0x180011f56  test    rcx, rcx
0x180011f59  jnz     loc_1800120CF
0x180011f5f  mov     rcx, [rbp+57h+var_90]
0x180011f63  test    rcx, rcx
0x180011f66  jnz     loc_1800120E4
0x180011f6c  mov     rcx, [rbp+57h+var_50]
0x180011f70  mov     r13, [rsp+0D0h]
0x180011f78  test    rcx, rcx
0x180011f7b  jz      short loc_180011F89
0x180011f7d  mov     rax, [rcx]
0x180011f80  mov     rax, [rax+10h]
0x180011f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f89  mov     eax, ebx
0x180011f8b  add     rsp, 0D8h
0x180011f92  pop     rbx
0x180011f93  pop     rbp
0x180011f94  retn
0x180011f96  mov     rax, [r12]
0x180011f9a  lea     r8, [rbp+57h+arg_18]
0x180011f9e  mov     rdx, [rbp+57h+var_B0]
0x180011fa2  mov     rcx, r12
0x180011fa5  mov     rax, [rax+0A8h]
0x180011fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fb1  mov     ebx, eax
0x180011fb3  jmp     loc_180011EB0
0x180011fb8  mov     ebx, 8007000Eh
0x180011fbd  jmp     loc_180011F23
0x180011fc2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180011fc6  call    cs:__imp_VariantInit
0x180011fcd  nop     dword ptr [rax+rax+00h]
0x180011fd2  mov     r12, [rbp+57h+arg_18]
0x180011fd6  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180011fda  mov     rbx, [r15]
0x180011fdd  xorps   xmm0, xmm0
0x180011fe0  xor     eax, eax
0x180011fe2  mov     word ptr [rbp+57h+pvarg], r13w
0x180011fe7  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x180011feb  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x180011fef  mov     [rbp+57h+var_B0], r13
0x180011ff3  call    cs:__imp_VariantInit
0x180011ffa  nop     dword ptr [rax+rax+00h]
0x180011fff  movsd   xmm1, qword ptr [rbp+57h+var_A8+10h]
0x180012004  lea     rcx, [rbp+57h+var_B0]
0x180012008  mov     eax, 3
0x18001200d  mov     dword ptr [rbp+57h+var_A8+8], 1
0x180012014  mov     word ptr [rbp+57h+var_A8], ax
0x180012018  lea     rdx, [rbp+57h+var_70]
0x18001201c  mov     rax, [rbx]
0x18001201f  mov     r9, rsi
0x180012022  movups  xmm0, xmmword ptr [rbp+57h+var_A8]
0x180012026  mov     [rsp+0E0h+var_C0], rcx
0x18001202b  mov     r8, rdi
0x18001202e  mov     rcx, rbx
0x180012031  movsd   qword ptr [rbp+57h+var_70+10h], xmm1
0x180012036  mov     rax, [rax+1C0h]
0x18001203d  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x180012041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012046  lea     rcx, [rbp+57h+var_A8]; pvarg
0x18001204a  mov     ebx, eax
0x18001204c  call    cs:__imp_VariantClear
0x180012053  nop     dword ptr [rax+rax+00h]
0x180012058  test    ebx, ebx
0x18001205a  jz      loc_1800120F9
0x180012060  mov     rcx, [rbp+57h+var_B0]
0x180012064  test    rcx, rcx
0x180012067  jz      short loc_180012075
0x180012069  mov     rax, [rcx]
0x18001206c  mov     rax, [rax+10h]
0x180012070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012075  mov     rcx, rdi; bstrString
0x180012078  call    cs:__imp_SysFreeString
0x18001207f  nop     dword ptr [rax+rax+00h]
0x180012084  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180012088  call    cs:__imp_VariantClear
0x18001208f  nop     dword ptr [rax+rax+00h]
0x180012094  test    ebx, ebx
0x180012096  jnz     loc_1800122B5
0x18001209c  test    byte ptr [r14+8], 10h
0x1800120a1  lea     rcx, String2; "true"
0x1800120a8  jnz     short loc_1800120B1
0x1800120aa  lea     rcx, aFalse; "false"
0x1800120b1  call    cs:__imp_SysAllocString
0x1800120b8  nop     dword ptr [rax+rax+00h]
0x1800120bd  mov     rdi, rax
0x1800120c0  test    rax, rax
0x1800120c3  jnz     short loc_18001211B
0x1800120c5  mov     ebx, 8007000Eh
0x1800120ca  jmp     loc_180011F1B
0x1800120cf  mov     rax, [rcx]
0x1800120d2  mov     rax, [rax+10h]
0x1800120d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120db  mov     [rbp+57h+arg_18], r13
0x1800120df  jmp     loc_180011F5F
0x1800120e4  mov     rax, [rcx]
0x1800120e7  mov     rax, [rax+10h]
0x1800120eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120f0  mov     [rbp+57h+var_90], r13
0x1800120f4  jmp     loc_180011F6C
0x1800120f9  mov     rax, [r12]
0x1800120fd  lea     r8, [rbp+57h+var_90]
0x180012101  mov     rdx, [rbp+57h+var_B0]
0x180012105  mov     rcx, r12
0x180012108  mov     rax, [rax+0A8h]
0x18001210f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012114  mov     ebx, eax
0x180012116  jmp     loc_180012060
0x18001211b  lea     rcx, aSimplecertsele; "SimpleCertSelection"
0x180012122  call    cs:__imp_SysAllocString
0x180012129  nop     dword ptr [rax+rax+00h]
0x18001212e  mov     r14, rax
0x180012131  test    rax, rax
0x180012134  jz      loc_1800122D6
0x18001213a  xorps   xmm0, xmm0
0x18001213d  movaps  xmmword ptr [rsp+0B0h], xmm6
0x180012145  xor     eax, eax
0x180012147  lea     rcx, [rbp+57h+var_48]; pvarg
0x18001214b  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18001214f  mov     qword ptr [rbp+57h+var_48+10h], rax
0x180012153  call    cs:__imp_VariantInit
0x18001215a  nop     dword ptr [rax+rax+00h]
0x18001215f  mov     rcx, rdi; psz
0x180012162  call    cs:__imp_SysAllocString
0x180012169  nop     dword ptr [rax+rax+00h]
0x18001216e  movsd   xmm6, qword ptr [rbp+57h+var_48+10h]
0x180012173  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180012177  mov     r12, [rbp+57h+var_90]
0x18001217b  mov     rbx, [r15]
0x18001217e  mov     qword ptr [rbp+57h+var_48+8], rax
0x180012182  mov     eax, 8
0x180012187  mov     word ptr [rbp+57h+var_48], ax
0x18001218b  xor     eax, eax
0x18001218d  movups  xmm0, xmmword ptr [rbp+57h+var_48]
0x180012191  mov     [rbp+57h+var_B0], r13
0x180012195  movsd   qword ptr [rbp+57h+pvarg+10h], xmm6
0x18001219a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001219e  mov     qword ptr [rbp+57h+var_A8+10h], rax
0x1800121a2  xorps   xmm0, xmm0
0x1800121a5  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800121a9  call    cs:__imp_VariantInit
0x1800121b0  nop     dword ptr [rax+rax+00h]
0x1800121b5  movsd   xmm1, qword ptr [rbp+57h+var_A8+10h]
0x1800121ba  lea     rcx, [rbp+57h+var_B0]
0x1800121be  mov     eax, 3
0x1800121c3  mov     dword ptr [rbp+57h+var_A8+8], 1
0x1800121ca  mov     word ptr [rbp+57h+var_A8], ax
0x1800121ce  lea     rdx, [rbp+57h+var_70]
0x1800121d2  mov     rax, [rbx]
0x1800121d5  mov     r9, rsi
0x1800121d8  movups  xmm0, xmmword ptr [rbp+57h+var_A8]
0x1800121dc  mov     [rsp+0E0h+var_C0], rcx
0x1800121e1  mov     r8, r14
0x1800121e4  mov     rcx, rbx
0x1800121e7  movsd   qword ptr [rbp+57h+var_70+10h], xmm1
0x1800121ec  mov     rax, [rax+1C0h]
0x1800121f3  movaps  xmmword ptr [rbp+57h+var_70], xmm0
0x1800121f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121fc  lea     rcx, [rbp+57h+var_A8]; pvarg
0x180012200  mov     ebx, eax
0x180012202  call    cs:__imp_VariantClear
0x180012209  nop     dword ptr [rax+rax+00h]
0x18001220e  test    ebx, ebx
0x180012210  jz      loc_1800122E0
0x180012216  mov     rcx, [rbp+57h+var_B0]
0x18001221a  movaps  xmm6, xmmword ptr [rsp+0B0h]
0x180012222  test    rcx, rcx
0x180012225  jz      short loc_180012233
0x180012227  mov     rax, [rcx]
0x18001222a  mov     rax, [rax+10h]
0x18001222e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012233  mov     rcx, r14; bstrString
0x180012236  call    cs:__imp_SysFreeString
0x18001223d  nop     dword ptr [rax+rax+00h]
0x180012242  mov     rcx, rdi; bstrString
0x180012245  call    cs:__imp_SysFreeString
0x18001224c  nop     dword ptr [rax+rax+00h]
0x180012251  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180012255  call    cs:__imp_VariantClear
0x18001225c  nop     dword ptr [rax+rax+00h]
0x180012261  test    ebx, ebx
0x180012263  jz      loc_180011F1B
0x180012269  mov     rcx, cs:WPP_GLOBAL_Control
0x180012270  lea     rax, WPP_GLOBAL_Control
0x180012277  cmp     rcx, rax
0x18001227a  jz      loc_180011F1B
0x180012280  mov     edx, 64h ; 'd'
0x180012285  jmp     loc_1800123EE
0x18001228a  mov     ebx, 8007000Eh
0x18001228f  jmp     loc_180011F3A
0x180012294  mov     rcx, cs:WPP_GLOBAL_Control
0x18001229b  lea     rax, WPP_GLOBAL_Control
0x1800122a2  cmp     rcx, rax
0x1800122a5  jz      loc_180011F1B
0x1800122ab  mov     edx, 62h ; 'b'
0x1800122b0  jmp     loc_1800123EE
0x1800122b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122bc  lea     rax, WPP_GLOBAL_Control
0x1800122c3  cmp     rcx, rax
0x1800122c6  jz      loc_180011F1B
  ... truncated ...
```
