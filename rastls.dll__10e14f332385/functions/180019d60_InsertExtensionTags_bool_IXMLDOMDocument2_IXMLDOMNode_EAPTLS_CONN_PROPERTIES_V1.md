# InsertExtensionTags(bool,IXMLDOMDocument2 * *,IXMLDOMNode * *,_EAPTLS_CONN_PROPERTIES_V1 *)

- ea: `0x180019d60`
- end: `0x18001a1d6`
- name: `?InsertExtensionTags@@YAK_NPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `1142`
- prototype: `unsigned int __fastcall(bool, struct IXMLDOMDocument2 **, struct IXMLDOMNode **, struct _EAPTLS_CONN_PROPERTIES_V1 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007ec0`
- `0x18001cbf0`

## callees

- `0x180004bd0`
- `0x180019d60`
- `0x18007c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180019daf`
- `OLEAUT32!__imp_SysAllocString` at `0x180019deb`
- `OLEAUT32!__imp_SysAllocString` at `0x180019e0a`
- `OLEAUT32!__imp_SysAllocString` at `0x180019e4e`
- `OLEAUT32!__imp_SysAllocString` at `0x180019fd2`
- `OLEAUT32!__imp_SysAllocString` at `0x180019ff1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a02d`
- `OLEAUT32!__imp_SysAllocString` at `0x180019daf`
- `OLEAUT32!__imp_SysAllocString` at `0x180019deb`
- `OLEAUT32!__imp_SysAllocString` at `0x180019e0a`
- `OLEAUT32!__imp_SysAllocString` at `0x180019e4e`
- `OLEAUT32!__imp_SysAllocString` at `0x180019fd2`
- `OLEAUT32!__imp_SysAllocString` at `0x180019ff1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a02d`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f65`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a1bc`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f65`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a1bc`
- `OLEAUT32!__imp_VariantInit` at `0x180019e2e`
- `OLEAUT32!__imp_VariantInit` at `0x180019e45`
- `OLEAUT32!__imp_VariantInit` at `0x180019e97`
- `OLEAUT32!__imp_VariantInit` at `0x18001a00d`
- `OLEAUT32!__imp_VariantInit` at `0x18001a024`
- `OLEAUT32!__imp_VariantInit` at `0x18001a06e`
- `OLEAUT32!__imp_VariantInit` at `0x180019e2e`
- `OLEAUT32!__imp_VariantInit` at `0x180019e45`
- `OLEAUT32!__imp_VariantInit` at `0x180019e97`
- `OLEAUT32!__imp_VariantInit` at `0x18001a00d`
- `OLEAUT32!__imp_VariantInit` at `0x18001a024`
- `OLEAUT32!__imp_VariantInit` at `0x18001a06e`
- `OLEAUT32!__imp_VariantClear` at `0x180019eea`
- `OLEAUT32!__imp_VariantClear` at `0x180019f6f`
- `OLEAUT32!__imp_VariantClear` at `0x18001a0c1`
- `OLEAUT32!__imp_VariantClear` at `0x18001a133`
- `OLEAUT32!__imp_VariantClear` at `0x180019eea`
- `OLEAUT32!__imp_VariantClear` at `0x180019f6f`
- `OLEAUT32!__imp_VariantClear` at `0x18001a0c1`
- `OLEAUT32!__imp_VariantClear` at `0x18001a133`

## string_xrefs

- `0x180019d98`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2`
- `0x180019da8`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2`

## pseudocode

```c
__int64 __fastcall InsertExtensionTags(
        char a1,
        struct IXMLDOMDocument2 **a2,
        struct IXMLDOMNode **a3,
        struct _EAPTLS_CONN_PROPERTIES_V1 *a4)
{
  bool v6; // zf
  const OLECHAR *v7; // rcx
  OLECHAR *v9; // rbx
  unsigned int v10; // edi
  const OLECHAR *v11; // rcx
  OLECHAR *v12; // r14
  OLECHAR *v13; // r13
  BSTR v14; // rax
  IRecordInfo *pRecInfo; // xmm6_8
  __int64 *v16; // rdi
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64 *, _BYTE *, OLECHAR *, OLECHAR *, __int64 **); // rax
  __int64 v19; // rax
  struct _EAPTLS_CONTROL_BLOCK *v20; // rcx
  __int64 v21; // rdx
  const OLECHAR *v22; // rcx
  const OLECHAR *v23; // rdi
  BSTR v24; // rsi
  BSTR v25; // rax
  IRecordInfo *v26; // xmm6_8
  __int64 v27; // r14
  __int64 *v28; // rdi
  __int64 v29; // rax
  __int64 (__fastcall *v30)(__int64 *, _BYTE *, BSTR, OLECHAR *, __int64 **); // rax
  __int64 v31; // rax
  __int64 *v33; // [rsp+38h] [rbp-59h] BYREF
  __int64 v34; // [rsp+40h] [rbp-51h] BYREF
  VARIANTARG v35; // [rsp+48h] [rbp-49h] BYREF
  VARIANTARG v36; // [rsp+60h] [rbp-31h] BYREF
  _BYTE v37[24]; // [rsp+78h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp+7h] BYREF
  __int128 v39; // [rsp+B0h] [rbp+1Fh]

  v34 = 0;
  v6 = a1 == 0;
  v7 = L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2";
  memset(&pvarg, 0, sizeof(pvarg));
  if ( v6 )
    v7 = L"http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2";
  v9 = SysAllocString(v7);
  if ( !v9 )
  {
    v10 = -2147024882;
    goto LABEL_36;
  }
  v11 = L"false";
  if ( (*((_BYTE *)a4 + 8) & 2) == 0 )
    v11 = L"true";
  v12 = SysAllocString(v11);
  if ( !v12 )
  {
    v10 = -2147024882;
    goto LABEL_36;
  }
  v13 = SysAllocString(L"PerformServerValidation");
  if ( !v13 )
  {
    v10 = -2147024882;
    goto LABEL_36;
  }
  VariantInit(&pvarg);
  memset(&v36, 0, sizeof(v36));
  VariantInit(&v36);
  v14 = SysAllocString(v12);
  pRecInfo = v36.pRecInfo;
  v16 = (__int64 *)*a2;
  v36.llVal = (LONGLONG)v14;
  v36.vt = 8;
  *(_QWORD *)&v39 = *a3;
  pvarg = v36;
  v33 = 0;
  memset(&v35, 0, sizeof(v35));
  VariantInit(&v35);
  v35.lVal = 1;
  v35.vt = 3;
  v17 = *v16;
  *(_QWORD *)&v37[16] = v35.pRecInfo;
  v18 = *(__int64 (__fastcall **)(__int64 *, _BYTE *, OLECHAR *, OLECHAR *, __int64 **))(v17 + 448);
  *(_OWORD *)v37 = *(_OWORD *)&v35.vt;
  v10 = v18(v16, v37, v13, v9, &v33);
  VariantClear(&v35);
  if ( !v10 )
  {
    strcpy(v37, "\b");
    v19 = *v33;
    *(_OWORD *)&v37[2] = *(_OWORD *)&v36.decVal.scale;
    *(_QWORD *)&v37[16] = pRecInfo;
    v10 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v19 + 248))(v33, v37);
    if ( !v10 )
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *))(*(_QWORD *)v39 + 168LL))(v39, v33, &v34);
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
  SysFreeString(v13);
  SysFreeString(v12);
  VariantClear(&pvarg);
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v10 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_36;
    v21 = 67;
    goto LABEL_35;
  }
  v22 = L"false";
  if ( (*((_BYTE *)a4 + 8) & 4) == 0 )
    v22 = L"true";
  v23 = SysAllocString(v22);
  if ( !v23 )
  {
    v10 = -2147024882;
    goto LABEL_36;
  }
  v24 = SysAllocString(L"AcceptServerName");
  if ( !v24 )
  {
    v10 = -2147024882;
    goto LABEL_36;
  }
  VariantInit(&pvarg);
  memset(&v35, 0, sizeof(v35));
  VariantInit(&v35);
  v25 = SysAllocString(v23);
  v26 = v35.pRecInfo;
  v27 = (__int64)*a3;
  v28 = (__int64 *)*a2;
  v35.llVal = (LONGLONG)v25;
  v35.vt = 8;
  v33 = 0;
  pvarg = v35;
  memset(&v36, 0, sizeof(v36));
  VariantInit(&v36);
  v36.lVal = 1;
  v36.vt = 3;
  v29 = *v28;
  *(_QWORD *)&v37[16] = v36.pRecInfo;
  v30 = *(__int64 (__fastcall **)(__int64 *, _BYTE *, BSTR, OLECHAR *, __int64 **))(v29 + 448);
  *(_OWORD *)v37 = *(_OWORD *)&v36.vt;
  v10 = v30(v28, v37, v24, v9, &v33);
  VariantClear(&v36);
  if ( !v10 )
  {
    strcpy(v37, "\b");
    v31 = *v33;
    *(_OWORD *)&v37[2] = *(_OWORD *)&v35.decVal.scale;
    *(_QWORD *)&v37[16] = v26;
    v10 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v31 + 248))(v33, v37);
    if ( !v10 )
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v27 + 168LL))(v27, v33, &v34);
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
  VariantClear(&pvarg);
  if ( v10 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v21 = 68;
LABEL_35:
      WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v10);
    }
  }
LABEL_36:
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v9 )
    SysFreeString(v9);
  return v10;
}

```

## disassembly

```asm
0x180019d60  mov     rax, rsp
0x180019d63  push    rbp
0x180019d64  push    rbx
0x180019d65  lea     rbp, [rax-5Fh]
0x180019d69  sub     rsp, 0D8h
0x180019d70  mov     [rax+8], rsi
0x180019d74  xorps   xmm0, xmm0
0x180019d77  mov     [rax+18h], r12
0x180019d7b  mov     rsi, r9
0x180019d7e  mov     [rax-18h], r13
0x180019d82  mov     r12, rdx
0x180019d85  mov     [rax-28h], r15
0x180019d89  xor     r13d, r13d
0x180019d8c  xor     eax, eax
0x180019d8e  mov     [rbp+57h+var_A8], r13
0x180019d92  test    cl, cl
0x180019d94  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180019d98  lea     rcx, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/M"...
0x180019d9f  mov     r15, r8
0x180019da2  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180019da6  jnz     short loc_180019DAF
0x180019da8  lea     rcx, aHttpWwwMicroso_9; "http://www.microsoft.com/provisioning/E"...
0x180019daf  call    cs:__imp_SysAllocString
0x180019db5  mov     [rsp+0E0h+arg_8], rdi
0x180019dbd  mov     rbx, rax
0x180019dc0  test    rax, rax
0x180019dc3  jnz     short loc_180019DCF
0x180019dc5  mov     edi, 8007000Eh
0x180019dca  jmp     loc_18001A178
0x180019dcf  test    byte ptr [rsi+8], 2
0x180019dd3  lea     rcx, aFalse; "false"
0x180019dda  mov     [rsp+0E0h+var_18], r14
0x180019de2  jnz     short loc_180019DEB
0x180019de4  lea     rcx, String2; "true"
0x180019deb  call    cs:__imp_SysAllocString
0x180019df1  mov     r14, rax
0x180019df4  test    rax, rax
0x180019df7  jnz     short loc_180019E03
0x180019df9  mov     edi, 8007000Eh
0x180019dfe  jmp     loc_18001A170
0x180019e03  lea     rcx, aPerformserverv; "PerformServerValidation"
0x180019e0a  call    cs:__imp_SysAllocString
0x180019e10  mov     r13, rax
0x180019e13  test    rax, rax
0x180019e16  jnz     short loc_180019E22
0x180019e18  mov     edi, 8007000Eh
0x180019e1d  jmp     loc_18001A170
0x180019e22  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180019e26  movaps  [rsp+0E0h+var_38+8], xmm6
0x180019e2e  call    cs:__imp_VariantInit
0x180019e34  xorps   xmm0, xmm0
0x180019e37  lea     rcx, [rbp+57h+var_88]; pvarg
0x180019e3b  xor     eax, eax
0x180019e3d  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x180019e41  mov     qword ptr [rbp+57h+var_88+10h], rax
0x180019e45  call    cs:__imp_VariantInit
0x180019e4b  mov     rcx, r14; psz
0x180019e4e  call    cs:__imp_SysAllocString
0x180019e54  movsd   xmm6, qword ptr [rbp+57h+var_88+10h]
0x180019e59  lea     rcx, [rbp+57h+var_A0]; pvarg
0x180019e5d  mov     rdi, [r12]
0x180019e61  mov     qword ptr [rbp+57h+var_88+8], rax
0x180019e65  mov     eax, 8
0x180019e6a  mov     word ptr [rbp+57h+var_88], ax
0x180019e6e  movups  xmm0, xmmword ptr [rbp+57h+var_88]
0x180019e72  mov     rax, [r15]
0x180019e75  mov     qword ptr [rbp+57h+var_38], rax
0x180019e79  xor     eax, eax
0x180019e7b  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180019e7f  mov     [rbp+57h+var_B0], 0
0x180019e87  xorps   xmm0, xmm0
0x180019e8a  movsd   qword ptr [rbp+57h+pvarg+10h], xmm6
0x180019e8f  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x180019e93  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x180019e97  call    cs:__imp_VariantInit
0x180019e9d  movsd   xmm1, qword ptr [rbp+57h+var_A0+10h]
0x180019ea2  lea     rcx, [rbp+57h+var_B0]
0x180019ea6  mov     eax, 3
0x180019eab  mov     dword ptr [rbp+57h+var_A0+8], 1
0x180019eb2  mov     word ptr [rbp+57h+var_A0], ax
0x180019eb6  lea     rdx, [rbp+57h+var_70]
0x180019eba  mov     rax, [rdi]
0x180019ebd  mov     r9, rbx
0x180019ec0  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x180019ec4  mov     [rsp+20h], rcx
0x180019ec9  mov     r8, r13
0x180019ecc  mov     rcx, rdi
0x180019ecf  movsd   [rbp+57h+var_60], xmm1
0x180019ed4  mov     rax, [rax+1C0h]
0x180019edb  movaps  [rbp+57h+var_70], xmm0
0x180019edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ee4  lea     rcx, [rbp+57h+var_A0]; pvarg
0x180019ee8  mov     edi, eax
0x180019eea  call    cs:__imp_VariantClear
0x180019ef0  test    edi, edi
0x180019ef2  jnz     short loc_180019F44
0x180019ef4  mov     rcx, [rbp+57h+var_B0]
0x180019ef8  lea     rdx, [rbp+57h+var_70]
0x180019efc  movups  xmm0, xmmword ptr [rbp+57h+var_88+2]
0x180019f00  mov     eax, 8
0x180019f05  mov     word ptr [rbp+57h+var_70], ax
0x180019f09  mov     rax, [rcx]
0x180019f0c  movups  [rbp+57h+var_70+2], xmm0
0x180019f10  movsd   [rbp+57h+var_60], xmm6
0x180019f15  mov     rax, [rax+0F8h]
0x180019f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f21  mov     edi, eax
0x180019f23  test    eax, eax
0x180019f25  jnz     short loc_180019F44
0x180019f27  mov     rcx, qword ptr [rbp+57h+var_38]
0x180019f2b  lea     r8, [rbp+57h+var_A8]
0x180019f2f  mov     rdx, [rbp+57h+var_B0]
0x180019f33  mov     rax, [rcx]
0x180019f36  mov     rax, [rax+0A8h]
0x180019f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f42  mov     edi, eax
0x180019f44  mov     rcx, [rbp+57h+var_B0]
0x180019f48  test    rcx, rcx
0x180019f4b  jz      short loc_180019F59
0x180019f4d  mov     rax, [rcx]
0x180019f50  mov     rax, [rax+10h]
0x180019f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f59  mov     rcx, r13; bstrString
0x180019f5c  call    cs:__imp_SysFreeString
0x180019f62  mov     rcx, r14; bstrString
0x180019f65  call    cs:__imp_SysFreeString
0x180019f6b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180019f6f  call    cs:__imp_VariantClear
0x180019f75  mov     rdx, [rbp+57h+var_A8]
0x180019f79  test    rdx, rdx
0x180019f7c  jz      short loc_180019F96
0x180019f7e  mov     rax, [rdx]
0x180019f81  mov     rcx, rdx
0x180019f84  mov     rax, [rax+10h]
0x180019f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f8d  xor     r13d, r13d
0x180019f90  mov     [rbp+57h+var_A8], r13
0x180019f94  jmp     short loc_180019F99
0x180019f96  xor     r13d, r13d
0x180019f99  test    edi, edi
0x180019f9b  jz      short loc_180019FBE
0x180019f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fa4  lea     rax, WPP_GLOBAL_Control
0x180019fab  cmp     rcx, rax
0x180019fae  jz      loc_18001A168
0x180019fb4  mov     edx, 43h ; 'C'
0x180019fb9  jmp     loc_18001A155
0x180019fbe  test    byte ptr [rsi+8], 4
0x180019fc2  lea     rcx, aFalse; "false"
0x180019fc9  jnz     short loc_180019FD2
0x180019fcb  lea     rcx, String2; "true"
0x180019fd2  call    cs:__imp_SysAllocString
0x180019fd8  mov     rdi, rax
0x180019fdb  test    rax, rax
0x180019fde  jnz     short loc_180019FEA
0x180019fe0  mov     edi, 8007000Eh
0x180019fe5  jmp     loc_18001A168
0x180019fea  lea     rcx, aAcceptserverna; "AcceptServerName"
0x180019ff1  call    cs:__imp_SysAllocString
0x180019ff7  mov     rsi, rax
0x180019ffa  test    rax, rax
0x180019ffd  jnz     short loc_18001A009
0x180019fff  mov     edi, 8007000Eh
0x18001a004  jmp     loc_18001A168
0x18001a009  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001a00d  call    cs:__imp_VariantInit
0x18001a013  xorps   xmm0, xmm0
0x18001a016  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18001a01a  xor     eax, eax
0x18001a01c  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18001a020  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x18001a024  call    cs:__imp_VariantInit
0x18001a02a  mov     rcx, rdi; psz
0x18001a02d  call    cs:__imp_SysAllocString
0x18001a033  movsd   xmm6, qword ptr [rbp+57h+var_A0+10h]
0x18001a038  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001a03c  mov     r14, [r15]
0x18001a03f  mov     rdi, [r12]
0x18001a043  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18001a047  mov     eax, 8
0x18001a04c  mov     word ptr [rbp+57h+var_A0], ax
0x18001a050  xor     eax, eax
0x18001a052  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x18001a056  mov     [rbp+57h+var_B0], r13
0x18001a05a  movsd   qword ptr [rbp+57h+pvarg+10h], xmm6
0x18001a05f  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001a063  mov     qword ptr [rbp+57h+var_88+10h], rax
0x18001a067  xorps   xmm0, xmm0
0x18001a06a  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18001a06e  call    cs:__imp_VariantInit
0x18001a074  movsd   xmm1, qword ptr [rbp+57h+var_88+10h]
0x18001a079  lea     rcx, [rbp+57h+var_B0]
0x18001a07d  mov     eax, 3
0x18001a082  mov     dword ptr [rbp+57h+var_88+8], 1
0x18001a089  mov     word ptr [rbp+57h+var_88], ax
0x18001a08d  lea     rdx, [rbp+57h+var_70]
0x18001a091  mov     rax, [rdi]
0x18001a094  mov     r9, rbx
0x18001a097  movups  xmm0, xmmword ptr [rbp+57h+var_88]
0x18001a09b  mov     [rsp+20h], rcx
0x18001a0a0  mov     r8, rsi
0x18001a0a3  mov     rcx, rdi
0x18001a0a6  movsd   [rbp+57h+var_60], xmm1
0x18001a0ab  mov     rax, [rax+1C0h]
0x18001a0b2  movaps  [rbp+57h+var_70], xmm0
0x18001a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0bb  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001a0bf  mov     edi, eax
0x18001a0c1  call    cs:__imp_VariantClear
0x18001a0c7  test    edi, edi
0x18001a0c9  jnz     short loc_18001A11A
0x18001a0cb  mov     rcx, [rbp+57h+var_B0]
0x18001a0cf  lea     rdx, [rbp+57h+var_70]
0x18001a0d3  movups  xmm0, xmmword ptr [rbp+57h+var_A0+2]
0x18001a0d7  mov     eax, 8
0x18001a0dc  mov     word ptr [rbp+57h+var_70], ax
0x18001a0e0  mov     rax, [rcx]
0x18001a0e3  movups  [rbp+57h+var_70+2], xmm0
0x18001a0e7  movsd   [rbp+57h+var_60], xmm6
0x18001a0ec  mov     rax, [rax+0F8h]
0x18001a0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0f8  mov     edi, eax
0x18001a0fa  test    eax, eax
0x18001a0fc  jnz     short loc_18001A11A
0x18001a0fe  mov     rax, [r14]
0x18001a101  lea     r8, [rbp+57h+var_A8]
0x18001a105  mov     rdx, [rbp+57h+var_B0]
0x18001a109  mov     rcx, r14
0x18001a10c  mov     rax, [rax+0A8h]
0x18001a113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a118  mov     edi, eax
0x18001a11a  mov     rcx, [rbp+57h+var_B0]
0x18001a11e  test    rcx, rcx
0x18001a121  jz      short loc_18001A12F
0x18001a123  mov     rax, [rcx]
0x18001a126  mov     rax, [rax+10h]
0x18001a12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a12f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001a133  call    cs:__imp_VariantClear
0x18001a139  test    edi, edi
0x18001a13b  jz      short loc_18001A168
0x18001a13d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a144  lea     rax, WPP_GLOBAL_Control
0x18001a14b  cmp     rcx, rax
0x18001a14e  jz      short loc_18001A168
0x18001a150  mov     edx, 44h ; 'D'
0x18001a155  mov     rcx, [rcx+10h]
0x18001a159  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001a160  mov     r9d, edi
0x18001a163  call    WPP_SF_d
0x18001a168  movaps  xmm6, [rsp+0E0h+var_38+8]
0x18001a170  mov     r14, [rsp+0E0h+var_18]
0x18001a178  mov     rdx, [rbp+57h+var_A8]
0x18001a17c  mov     r15, [rsp+0E0h+var_20]
0x18001a184  mov     r12, [rsp+0E0h+arg_10]
0x18001a18c  mov     rsi, [rsp+0E0h+arg_0]
0x18001a194  test    rdx, rdx
0x18001a197  jz      short loc_18001A1AC
0x18001a199  mov     rcx, [rdx]
0x18001a19c  mov     rax, [rcx+10h]
0x18001a1a0  mov     rcx, rdx
0x18001a1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1a8  mov     [rbp+57h+var_A8], r13
0x18001a1ac  mov     r13, [rsp+0D0h]
0x18001a1b4  test    rbx, rbx
0x18001a1b7  jz      short loc_18001A1C2
0x18001a1b9  mov     rcx, rbx; bstrString
0x18001a1bc  call    cs:__imp_SysFreeString
0x18001a1c2  mov     eax, edi
0x18001a1c4  mov     rdi, [rsp+0E0h+arg_8]
0x18001a1cc  add     rsp, 0D8h
0x18001a1d3  pop     rbx
0x18001a1d4  pop     rbp
0x18001a1d5  retn
```
