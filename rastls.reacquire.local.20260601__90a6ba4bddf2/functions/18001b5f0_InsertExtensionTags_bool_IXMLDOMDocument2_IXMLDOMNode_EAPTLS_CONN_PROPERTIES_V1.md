# InsertExtensionTags(bool,IXMLDOMDocument2 * *,IXMLDOMNode * *,_EAPTLS_CONN_PROPERTIES_V1 *)

- ea: `0x18001b5f0`
- end: `0x18001badf`
- name: `?InsertExtensionTags@@YAK_NPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z`
- size: `1263`
- prototype: `unsigned int __fastcall(bool, struct IXMLDOMDocument2 **, struct IXMLDOMNode **, struct _EAPTLS_CONN_PROPERTIES_V1 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800086a0`
- `0x18001e680`

## callees

- `0x180005010`
- `0x18001b5f0`
- `0x180082010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001b63f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b681`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b6a6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b6fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b8a4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b8c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b917`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b63f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b681`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b6a6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b6fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b8a4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b8c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b917`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b81c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b82b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001babe`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b81c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b82b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001babe`
- `OLEAUT32!__imp_VariantInit` at `0x18001b6d0`
- `OLEAUT32!__imp_VariantInit` at `0x18001b6ed`
- `OLEAUT32!__imp_VariantInit` at `0x18001b74b`
- `OLEAUT32!__imp_VariantInit` at `0x18001b8eb`
- `OLEAUT32!__imp_VariantInit` at `0x18001b908`
- `OLEAUT32!__imp_VariantInit` at `0x18001b95e`
- `OLEAUT32!__imp_VariantInit` at `0x18001b6d0`
- `OLEAUT32!__imp_VariantInit` at `0x18001b6ed`
- `OLEAUT32!__imp_VariantInit` at `0x18001b74b`
- `OLEAUT32!__imp_VariantInit` at `0x18001b8eb`
- `OLEAUT32!__imp_VariantInit` at `0x18001b908`
- `OLEAUT32!__imp_VariantInit` at `0x18001b95e`
- `OLEAUT32!__imp_VariantClear` at `0x18001b7a4`
- `OLEAUT32!__imp_VariantClear` at `0x18001b83b`
- `OLEAUT32!__imp_VariantClear` at `0x18001b9b7`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba2f`
- `OLEAUT32!__imp_VariantClear` at `0x18001b7a4`
- `OLEAUT32!__imp_VariantClear` at `0x18001b83b`
- `OLEAUT32!__imp_VariantClear` at `0x18001b9b7`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba2f`

## string_xrefs

- `0x18001b628`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2`
- `0x18001b638`: `http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2`

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
0x18001b5f0  mov     rax, rsp
0x18001b5f3  push    rbp
0x18001b5f4  push    rbx
0x18001b5f5  lea     rbp, [rax-5Fh]
0x18001b5f9  sub     rsp, 0D8h
0x18001b600  mov     [rax+8], rsi
0x18001b604  xorps   xmm0, xmm0
0x18001b607  mov     [rax+18h], r12
0x18001b60b  mov     rsi, r9
0x18001b60e  mov     [rax-18h], r13
0x18001b612  mov     r12, rdx
0x18001b615  mov     [rax-28h], r15
0x18001b619  xor     r13d, r13d
0x18001b61c  xor     eax, eax
0x18001b61e  mov     [rbp+57h+var_A8], r13
0x18001b622  test    cl, cl
0x18001b624  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001b628  lea     rcx, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/M"...
0x18001b62f  mov     r15, r8
0x18001b632  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001b636  jnz     short loc_18001B63F
0x18001b638  lea     rcx, aHttpWwwMicroso_9; "http://www.microsoft.com/provisioning/E"...
0x18001b63f  call    cs:__imp_SysAllocString
0x18001b646  nop     dword ptr [rax+rax+00h]
0x18001b64b  mov     [rsp+0E0h+arg_8], rdi
0x18001b653  mov     rbx, rax
0x18001b656  test    rax, rax
0x18001b659  jnz     short loc_18001B665
0x18001b65b  mov     edi, 8007000Eh
0x18001b660  jmp     loc_18001BA7A
0x18001b665  test    byte ptr [rsi+8], 2
0x18001b669  lea     rcx, aFalse; "false"
0x18001b670  mov     [rsp+0E0h+var_18], r14
0x18001b678  jnz     short loc_18001B681
0x18001b67a  lea     rcx, String2; "true"
0x18001b681  call    cs:__imp_SysAllocString
0x18001b688  nop     dword ptr [rax+rax+00h]
0x18001b68d  mov     r14, rax
0x18001b690  test    rax, rax
0x18001b693  jnz     short loc_18001B69F
0x18001b695  mov     edi, 8007000Eh
0x18001b69a  jmp     loc_18001BA72
0x18001b69f  lea     rcx, aPerformserverv; "PerformServerValidation"
0x18001b6a6  call    cs:__imp_SysAllocString
0x18001b6ad  nop     dword ptr [rax+rax+00h]
0x18001b6b2  mov     r13, rax
0x18001b6b5  test    rax, rax
0x18001b6b8  jnz     short loc_18001B6C4
0x18001b6ba  mov     edi, 8007000Eh
0x18001b6bf  jmp     loc_18001BA72
0x18001b6c4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001b6c8  movaps  [rsp+0E0h+var_38+8], xmm6
0x18001b6d0  call    cs:__imp_VariantInit
0x18001b6d7  nop     dword ptr [rax+rax+00h]
0x18001b6dc  xorps   xmm0, xmm0
0x18001b6df  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001b6e3  xor     eax, eax
0x18001b6e5  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18001b6e9  mov     qword ptr [rbp+57h+var_88+10h], rax
0x18001b6ed  call    cs:__imp_VariantInit
0x18001b6f4  nop     dword ptr [rax+rax+00h]
0x18001b6f9  mov     rcx, r14; psz
0x18001b6fc  call    cs:__imp_SysAllocString
0x18001b703  nop     dword ptr [rax+rax+00h]
0x18001b708  movsd   xmm6, qword ptr [rbp+57h+var_88+10h]
0x18001b70d  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18001b711  mov     rdi, [r12]
0x18001b715  mov     qword ptr [rbp+57h+var_88+8], rax
0x18001b719  mov     eax, 8
0x18001b71e  mov     word ptr [rbp+57h+var_88], ax
0x18001b722  movups  xmm0, xmmword ptr [rbp+57h+var_88]
0x18001b726  mov     rax, [r15]
0x18001b729  mov     qword ptr [rbp+57h+var_38], rax
0x18001b72d  xor     eax, eax
0x18001b72f  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001b733  mov     [rbp+57h+var_B0], 0
0x18001b73b  xorps   xmm0, xmm0
0x18001b73e  movsd   qword ptr [rbp+57h+pvarg+10h], xmm6
0x18001b743  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18001b747  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x18001b74b  call    cs:__imp_VariantInit
0x18001b752  nop     dword ptr [rax+rax+00h]
0x18001b757  movsd   xmm1, qword ptr [rbp+57h+var_A0+10h]
0x18001b75c  lea     rcx, [rbp+57h+var_B0]
0x18001b760  mov     eax, 3
0x18001b765  mov     dword ptr [rbp+57h+var_A0+8], 1
0x18001b76c  mov     word ptr [rbp+57h+var_A0], ax
0x18001b770  lea     rdx, [rbp+57h+var_70]
0x18001b774  mov     rax, [rdi]
0x18001b777  mov     r9, rbx
0x18001b77a  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x18001b77e  mov     [rsp+20h], rcx
0x18001b783  mov     r8, r13
0x18001b786  mov     rcx, rdi
0x18001b789  movsd   [rbp+57h+var_60], xmm1
0x18001b78e  mov     rax, [rax+1C0h]
0x18001b795  movaps  [rbp+57h+var_70], xmm0
0x18001b799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b79e  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18001b7a2  mov     edi, eax
0x18001b7a4  call    cs:__imp_VariantClear
0x18001b7ab  nop     dword ptr [rax+rax+00h]
0x18001b7b0  test    edi, edi
0x18001b7b2  jnz     short loc_18001B804
0x18001b7b4  mov     rcx, [rbp+57h+var_B0]
0x18001b7b8  lea     rdx, [rbp+57h+var_70]
0x18001b7bc  movups  xmm0, xmmword ptr [rbp+57h+var_88+2]
0x18001b7c0  mov     eax, 8
0x18001b7c5  mov     word ptr [rbp+57h+var_70], ax
0x18001b7c9  mov     rax, [rcx]
0x18001b7cc  movups  [rbp+57h+var_70+2], xmm0
0x18001b7d0  movsd   [rbp+57h+var_60], xmm6
0x18001b7d5  mov     rax, [rax+0F8h]
0x18001b7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7e1  mov     edi, eax
0x18001b7e3  test    eax, eax
0x18001b7e5  jnz     short loc_18001B804
0x18001b7e7  mov     rcx, qword ptr [rbp+57h+var_38]
0x18001b7eb  lea     r8, [rbp+57h+var_A8]
0x18001b7ef  mov     rdx, [rbp+57h+var_B0]
0x18001b7f3  mov     rax, [rcx]
0x18001b7f6  mov     rax, [rax+0A8h]
0x18001b7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b802  mov     edi, eax
0x18001b804  mov     rcx, [rbp+57h+var_B0]
0x18001b808  test    rcx, rcx
0x18001b80b  jz      short loc_18001B819
0x18001b80d  mov     rax, [rcx]
0x18001b810  mov     rax, [rax+10h]
0x18001b814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b819  mov     rcx, r13; bstrString
0x18001b81c  call    cs:__imp_SysFreeString
0x18001b823  nop     dword ptr [rax+rax+00h]
0x18001b828  mov     rcx, r14; bstrString
0x18001b82b  call    cs:__imp_SysFreeString
0x18001b832  nop     dword ptr [rax+rax+00h]
0x18001b837  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001b83b  call    cs:__imp_VariantClear
0x18001b842  nop     dword ptr [rax+rax+00h]
0x18001b847  mov     rdx, [rbp+57h+var_A8]
0x18001b84b  test    rdx, rdx
0x18001b84e  jz      short loc_18001B868
0x18001b850  mov     rax, [rdx]
0x18001b853  mov     rcx, rdx
0x18001b856  mov     rax, [rax+10h]
0x18001b85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b85f  xor     r13d, r13d
0x18001b862  mov     [rbp+57h+var_A8], r13
0x18001b866  jmp     short loc_18001B86B
0x18001b868  xor     r13d, r13d
0x18001b86b  test    edi, edi
0x18001b86d  jz      short loc_18001B890
0x18001b86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b876  lea     rax, WPP_GLOBAL_Control
0x18001b87d  cmp     rcx, rax
0x18001b880  jz      loc_18001BA6A
0x18001b886  mov     edx, 43h ; 'C'
0x18001b88b  jmp     loc_18001BA57
0x18001b890  test    byte ptr [rsi+8], 4
0x18001b894  lea     rcx, aFalse; "false"
0x18001b89b  jnz     short loc_18001B8A4
0x18001b89d  lea     rcx, String2; "true"
0x18001b8a4  call    cs:__imp_SysAllocString
0x18001b8ab  nop     dword ptr [rax+rax+00h]
0x18001b8b0  mov     rdi, rax
0x18001b8b3  test    rax, rax
0x18001b8b6  jnz     short loc_18001B8C2
0x18001b8b8  mov     edi, 8007000Eh
0x18001b8bd  jmp     loc_18001BA6A
0x18001b8c2  lea     rcx, aAcceptserverna; "AcceptServerName"
0x18001b8c9  call    cs:__imp_SysAllocString
0x18001b8d0  nop     dword ptr [rax+rax+00h]
0x18001b8d5  mov     rsi, rax
0x18001b8d8  test    rax, rax
0x18001b8db  jnz     short loc_18001B8E7
0x18001b8dd  mov     edi, 8007000Eh
0x18001b8e2  jmp     loc_18001BA6A
0x18001b8e7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001b8eb  call    cs:__imp_VariantInit
0x18001b8f2  nop     dword ptr [rax+rax+00h]
0x18001b8f7  xorps   xmm0, xmm0
0x18001b8fa  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18001b8fe  xor     eax, eax
0x18001b900  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18001b904  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x18001b908  call    cs:__imp_VariantInit
0x18001b90f  nop     dword ptr [rax+rax+00h]
0x18001b914  mov     rcx, rdi; psz
0x18001b917  call    cs:__imp_SysAllocString
0x18001b91e  nop     dword ptr [rax+rax+00h]
0x18001b923  movsd   xmm6, qword ptr [rbp+57h+var_A0+10h]
0x18001b928  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001b92c  mov     r14, [r15]
0x18001b92f  mov     rdi, [r12]
0x18001b933  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18001b937  mov     eax, 8
0x18001b93c  mov     word ptr [rbp+57h+var_A0], ax
0x18001b940  xor     eax, eax
0x18001b942  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x18001b946  mov     [rbp+57h+var_B0], r13
0x18001b94a  movsd   qword ptr [rbp+57h+pvarg+10h], xmm6
0x18001b94f  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001b953  mov     qword ptr [rbp+57h+var_88+10h], rax
0x18001b957  xorps   xmm0, xmm0
0x18001b95a  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18001b95e  call    cs:__imp_VariantInit
0x18001b965  nop     dword ptr [rax+rax+00h]
0x18001b96a  movsd   xmm1, qword ptr [rbp+57h+var_88+10h]
0x18001b96f  lea     rcx, [rbp+57h+var_B0]
0x18001b973  mov     eax, 3
0x18001b978  mov     dword ptr [rbp+57h+var_88+8], 1
0x18001b97f  mov     word ptr [rbp+57h+var_88], ax
0x18001b983  lea     rdx, [rbp+57h+var_70]
0x18001b987  mov     rax, [rdi]
0x18001b98a  mov     r9, rbx
0x18001b98d  movups  xmm0, xmmword ptr [rbp+57h+var_88]
0x18001b991  mov     [rsp+20h], rcx
0x18001b996  mov     r8, rsi
0x18001b999  mov     rcx, rdi
0x18001b99c  movsd   [rbp+57h+var_60], xmm1
0x18001b9a1  mov     rax, [rax+1C0h]
0x18001b9a8  movaps  [rbp+57h+var_70], xmm0
0x18001b9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9b1  lea     rcx, [rbp+57h+var_88]; pvarg
0x18001b9b5  mov     edi, eax
0x18001b9b7  call    cs:__imp_VariantClear
0x18001b9be  nop     dword ptr [rax+rax+00h]
0x18001b9c3  test    edi, edi
0x18001b9c5  jnz     short loc_18001BA16
0x18001b9c7  mov     rcx, [rbp+57h+var_B0]
0x18001b9cb  lea     rdx, [rbp+57h+var_70]
0x18001b9cf  movups  xmm0, xmmword ptr [rbp+57h+var_A0+2]
0x18001b9d3  mov     eax, 8
0x18001b9d8  mov     word ptr [rbp+57h+var_70], ax
0x18001b9dc  mov     rax, [rcx]
0x18001b9df  movups  [rbp+57h+var_70+2], xmm0
0x18001b9e3  movsd   [rbp+57h+var_60], xmm6
0x18001b9e8  mov     rax, [rax+0F8h]
0x18001b9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9f4  mov     edi, eax
0x18001b9f6  test    eax, eax
0x18001b9f8  jnz     short loc_18001BA16
0x18001b9fa  mov     rax, [r14]
0x18001b9fd  lea     r8, [rbp+57h+var_A8]
0x18001ba01  mov     rdx, [rbp+57h+var_B0]
0x18001ba05  mov     rcx, r14
0x18001ba08  mov     rax, [rax+0A8h]
0x18001ba0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba14  mov     edi, eax
0x18001ba16  mov     rcx, [rbp+57h+var_B0]
0x18001ba1a  test    rcx, rcx
0x18001ba1d  jz      short loc_18001BA2B
0x18001ba1f  mov     rax, [rcx]
0x18001ba22  mov     rax, [rax+10h]
0x18001ba26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba2b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001ba2f  call    cs:__imp_VariantClear
0x18001ba36  nop     dword ptr [rax+rax+00h]
0x18001ba3b  test    edi, edi
0x18001ba3d  jz      short loc_18001BA6A
0x18001ba3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba46  lea     rax, WPP_GLOBAL_Control
0x18001ba4d  cmp     rcx, rax
0x18001ba50  jz      short loc_18001BA6A
0x18001ba52  mov     edx, 44h ; 'D'
0x18001ba57  mov     rcx, [rcx+10h]
0x18001ba5b  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001ba62  mov     r9d, edi
0x18001ba65  call    WPP_SF_d
0x18001ba6a  movaps  xmm6, [rsp+0E0h+var_38+8]
0x18001ba72  mov     r14, [rsp+0E0h+var_18]
0x18001ba7a  mov     rdx, [rbp+57h+var_A8]
0x18001ba7e  mov     r15, [rsp+0E0h+var_20]
0x18001ba86  mov     r12, [rsp+0E0h+arg_10]
0x18001ba8e  mov     rsi, [rsp+0E0h+arg_0]
0x18001ba96  test    rdx, rdx
0x18001ba99  jz      short loc_18001BAAE
0x18001ba9b  mov     rcx, [rdx]
0x18001ba9e  mov     rax, [rcx+10h]
0x18001baa2  mov     rcx, rdx
0x18001baa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baaa  mov     [rbp+57h+var_A8], r13
0x18001baae  mov     r13, [rsp+0D0h]
0x18001bab6  test    rbx, rbx
0x18001bab9  jz      short loc_18001BACA
0x18001babb  mov     rcx, rbx; bstrString
0x18001babe  call    cs:__imp_SysFreeString
0x18001bac5  nop     dword ptr [rax+rax+00h]
0x18001baca  mov     eax, edi
0x18001bacc  mov     rdi, [rsp+0E0h+arg_8]
0x18001bad4  add     rsp, 0D8h
0x18001badb  pop     rbx
0x18001badc  pop     rbp
0x18001badd  retn
```
