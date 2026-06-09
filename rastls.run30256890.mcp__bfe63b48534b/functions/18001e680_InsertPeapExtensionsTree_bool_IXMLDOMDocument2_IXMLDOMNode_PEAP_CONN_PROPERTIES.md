# InsertPeapExtensionsTree(bool,IXMLDOMDocument2 * *,IXMLDOMNode * *,_PEAP_CONN_PROPERTIES *)

- ea: `0x18001e680`
- end: `0x18001e976`
- name: `?InsertPeapExtensionsTree@@YAK_NPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_PEAP_CONN_PROPERTIES@@@Z`
- size: `758`
- prototype: `unsigned int(bool, struct IXMLDOMDocument2 **, struct IXMLDOMNode **, struct _PEAP_CONN_PROPERTIES *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006960`

## callees

- `0x180005010`
- `0x180019274`
- `0x18001b5f0`
- `0x18001e680`
- `0x18001e980`
- `0x180082010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001e6be`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e6e5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e712`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e6be`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e6e5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e712`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e80d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e940`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e95c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e80d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e940`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e95c`
- `OLEAUT32!__imp_VariantInit` at `0x18001e73c`
- `OLEAUT32!__imp_VariantInit` at `0x18001e767`
- `OLEAUT32!__imp_VariantInit` at `0x18001e73c`
- `OLEAUT32!__imp_VariantInit` at `0x18001e767`
- `OLEAUT32!__imp_VariantClear` at `0x18001e7c0`
- `OLEAUT32!__imp_VariantClear` at `0x18001e81d`
- `OLEAUT32!__imp_VariantClear` at `0x18001e7c0`
- `OLEAUT32!__imp_VariantClear` at `0x18001e81d`

## string_xrefs

- `0x18001e6de`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2`
- `0x18001e695`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV1`
- `0x18001e703`: `PeapExtensions`

## pseudocode

```c
__int64 __fastcall InsertPeapExtensionsTree(
        __int64 a1,
        struct IXMLDOMDocument2 **a2,
        struct IXMLDOMNode **a3,
        struct _PEAP_CONN_PROPERTIES *a4)
{
  OLECHAR *v7; // rsi
  unsigned __int16 *v8; // rdi
  unsigned int inserted; // ebx
  OLECHAR *v10; // r15
  __int64 v11; // r12
  struct IXMLDOMDocument2 *v12; // rbx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *createNode)(IXMLDOMDocument2 *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  struct _EAPTLS_CONTROL_BLOCK *v15; // rcx
  __int64 v16; // rdx
  struct IXMLDOMNode *v18; // [rsp+38h] [rbp-29h] BYREF
  __int64 v19; // [rsp+40h] [rbp-21h] BYREF
  VARIANTARG v20; // [rsp+48h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-1h] BYREF
  __int128 v22; // [rsp+78h] [rbp+17h] BYREF
  IRecordInfo *pRecInfo; // [rsp+88h] [rbp+27h]

  v18 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v7 = SysAllocString(L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV1");
  if ( !v7 )
  {
    v8 = 0;
    inserted = -2147024882;
    goto LABEL_25;
  }
  v8 = SysAllocString(L"http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2");
  if ( !v8 )
  {
    inserted = -2147024882;
    goto LABEL_25;
  }
  v10 = SysAllocString(L"PeapExtensions");
  if ( !v10 )
  {
    inserted = -2147024882;
    goto LABEL_25;
  }
  VariantInit(&pvarg);
  v11 = (__int64)*a3;
  v12 = *a2;
  pvarg.vt = 0;
  v19 = 0;
  memset(&v20, 0, sizeof(v20));
  VariantInit(&v20);
  v20.lVal = 1;
  v20.vt = 3;
  lpVtbl = v12->lpVtbl;
  pRecInfo = v20.pRecInfo;
  createNode = lpVtbl->createNode;
  v22 = *(_OWORD *)&v20.vt;
  inserted = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int128 *, OLECHAR *, OLECHAR *, __int64 *))createNode)(
               v12,
               &v22,
               v10,
               v7,
               &v19);
  VariantClear(&v20);
  if ( !inserted )
    inserted = (*(__int64 (__fastcall **)(__int64, __int64, struct IXMLDOMNode **))(*(_QWORD *)v11 + 168LL))(
                 v11,
                 v19,
                 &v18);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  SysFreeString(v10);
  VariantClear(&pvarg);
  if ( inserted )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_25;
    v16 = 94;
    goto LABEL_24;
  }
  inserted = InsertExtensionTags(1, a2, &v18, (struct _PEAP_CONN_PROPERTIES *)((char *)a4 + 16));
  if ( inserted )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_25;
    v16 = 95;
    goto LABEL_24;
  }
  inserted = InsertIdentityPrivacyTree(v8, a2, &v18, a4);
  if ( inserted )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_25;
    v16 = 96;
    goto LABEL_24;
  }
  if ( (*((_DWORD *)a4 + 6) & 0x220) == 0x200 )
  {
    inserted = InsertPEAPV3TagsTree(a2, &v18);
    if ( inserted )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v16 = 97;
LABEL_24:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, inserted);
      }
    }
  }
LABEL_25:
  if ( v18 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
    v18 = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  if ( v8 )
    SysFreeString(v8);
  return inserted;
}

```

## disassembly

```asm
0x18001e680  mov     rax, rsp
0x18001e683  push    rbp
0x18001e684  push    rbx
0x18001e685  push    rdi
0x18001e686  lea     rbp, [rax-5Fh]
0x18001e68a  sub     rsp, 0A0h
0x18001e691  mov     [rax+8], rsi
0x18001e695  lea     rcx, aHttpWwwMicroso_1; "http://www.microsoft.com/provisioning/M"...
0x18001e69c  mov     [rax+18h], r13
0x18001e6a0  xorps   xmm0, xmm0
0x18001e6a3  mov     [rax-20h], r14
0x18001e6a7  mov     r13, r9
0x18001e6aa  xor     eax, eax
0x18001e6ac  mov     rbx, r8
0x18001e6af  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001e6b3  mov     r14, rdx
0x18001e6b6  mov     [rbp+57h+var_80], rax
0x18001e6ba  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001e6be  call    cs:__imp_SysAllocString
0x18001e6c5  nop     dword ptr [rax+rax+00h]
0x18001e6ca  mov     rsi, rax
0x18001e6cd  test    rax, rax
0x18001e6d0  jnz     short loc_18001E6DE
0x18001e6d2  xor     edi, edi
0x18001e6d4  mov     ebx, 8007000Eh
0x18001e6d9  jmp     loc_18001E90B
0x18001e6de  lea     rcx, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/M"...
0x18001e6e5  call    cs:__imp_SysAllocString
0x18001e6ec  nop     dword ptr [rax+rax+00h]
0x18001e6f1  mov     rdi, rax
0x18001e6f4  test    rax, rax
0x18001e6f7  jnz     short loc_18001E703
0x18001e6f9  mov     ebx, 8007000Eh
0x18001e6fe  jmp     loc_18001E90B
0x18001e703  lea     rcx, aPeapextensions; "PeapExtensions"
0x18001e70a  mov     [rsp+0B0h+var_20], r15
0x18001e712  call    cs:__imp_SysAllocString
0x18001e719  nop     dword ptr [rax+rax+00h]
0x18001e71e  mov     r15, rax
0x18001e721  test    rax, rax
0x18001e724  jnz     short loc_18001E730
0x18001e726  mov     ebx, 8007000Eh
0x18001e72b  jmp     loc_18001E903
0x18001e730  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001e734  mov     [rsp+0B0h+arg_8], r12
0x18001e73c  call    cs:__imp_VariantInit
0x18001e743  nop     dword ptr [rax+rax+00h]
0x18001e748  mov     r12, [rbx]
0x18001e74b  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001e74f  mov     rbx, [r14]
0x18001e752  xor     eax, eax
0x18001e754  xorps   xmm0, xmm0
0x18001e757  mov     word ptr [rbp+57h+pvarg], ax
0x18001e75b  mov     [rbp+57h+var_78], rax
0x18001e75f  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18001e763  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18001e767  call    cs:__imp_VariantInit
0x18001e76e  nop     dword ptr [rax+rax+00h]
0x18001e773  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x18001e778  lea     rcx, [rbp+57h+var_78]
0x18001e77c  mov     eax, 3
0x18001e781  mov     dword ptr [rbp+57h+var_70+8], 1
0x18001e788  mov     word ptr [rbp+57h+var_70], ax
0x18001e78c  lea     rdx, [rbp+57h+var_40]
0x18001e790  mov     rax, [rbx]
0x18001e793  mov     r9, rsi
0x18001e796  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x18001e79a  mov     [rsp+20h], rcx
0x18001e79f  mov     r8, r15
0x18001e7a2  mov     rcx, rbx
0x18001e7a5  movsd   [rbp+57h+var_30], xmm1
0x18001e7aa  mov     rax, [rax+1C0h]
0x18001e7b1  movaps  [rbp+57h+var_40], xmm0
0x18001e7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7ba  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001e7be  mov     ebx, eax
0x18001e7c0  call    cs:__imp_VariantClear
0x18001e7c7  nop     dword ptr [rax+rax+00h]
0x18001e7cc  test    ebx, ebx
0x18001e7ce  jnz     short loc_18001E7ED
0x18001e7d0  mov     rax, [r12]
0x18001e7d4  lea     r8, [rbp+57h+var_80]
0x18001e7d8  mov     rdx, [rbp+57h+var_78]
0x18001e7dc  mov     rcx, r12
0x18001e7df  mov     rax, [rax+0A8h]
0x18001e7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7eb  mov     ebx, eax
0x18001e7ed  mov     rcx, [rbp+57h+var_78]
0x18001e7f1  mov     r12, [rsp+0B0h+arg_8]
0x18001e7f9  test    rcx, rcx
0x18001e7fc  jz      short loc_18001E80A
0x18001e7fe  mov     rax, [rcx]
0x18001e801  mov     rax, [rax+10h]
0x18001e805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e80a  mov     rcx, r15; bstrString
0x18001e80d  call    cs:__imp_SysFreeString
0x18001e814  nop     dword ptr [rax+rax+00h]
0x18001e819  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001e81d  call    cs:__imp_VariantClear
0x18001e824  nop     dword ptr [rax+rax+00h]
0x18001e829  test    ebx, ebx
0x18001e82b  jz      short loc_18001E84E
0x18001e82d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e834  lea     rax, WPP_GLOBAL_Control
0x18001e83b  cmp     rcx, rax
0x18001e83e  jz      loc_18001E903
0x18001e844  mov     edx, 5Eh ; '^'
0x18001e849  jmp     loc_18001E8F0
0x18001e84e  lea     r9, [r13+10h]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18001e852  mov     rdx, r14; struct IXMLDOMDocument2 **
0x18001e855  lea     r8, [rbp+57h+var_80]; struct IXMLDOMNode **
0x18001e859  mov     cl, 1; bool
0x18001e85b  call    ?InsertExtensionTags@@YAK_NPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; InsertExtensionTags(bool,IXMLDOMDocument2 * *,IXMLDOMNode * *,_EAPTLS_CONN_PROPERTIES_V1 *)
0x18001e860  mov     ebx, eax
0x18001e862  test    eax, eax
0x18001e864  jz      short loc_18001E884
0x18001e866  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e86d  lea     rax, WPP_GLOBAL_Control
0x18001e874  cmp     rcx, rax
0x18001e877  jz      loc_18001E903
0x18001e87d  mov     edx, 5Fh ; '_'
0x18001e882  jmp     short loc_18001E8F0
0x18001e884  mov     r9, r13; struct _PEAP_CONN_PROPERTIES *
0x18001e887  lea     r8, [rbp+57h+var_80]; struct IXMLDOMNode **
0x18001e88b  mov     rdx, r14; struct IXMLDOMDocument2 **
0x18001e88e  mov     rcx, rdi; unsigned __int16 *
0x18001e891  call    ?InsertIdentityPrivacyTree@@YAKPEAGPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_PEAP_CONN_PROPERTIES@@@Z; InsertIdentityPrivacyTree(ushort *,IXMLDOMDocument2 * *,IXMLDOMNode * *,_PEAP_CONN_PROPERTIES *)
0x18001e896  mov     ebx, eax
0x18001e898  test    eax, eax
0x18001e89a  jz      short loc_18001E8B6
0x18001e89c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8a3  lea     rax, WPP_GLOBAL_Control
0x18001e8aa  cmp     rcx, rax
0x18001e8ad  jz      short loc_18001E903
0x18001e8af  mov     edx, 60h ; '`'
0x18001e8b4  jmp     short loc_18001E8F0
0x18001e8b6  mov     eax, [r13+18h]
0x18001e8ba  and     eax, 220h
0x18001e8bf  cmp     eax, 200h
0x18001e8c4  jnz     short loc_18001E903
0x18001e8c6  lea     rdx, [rbp+57h+var_80]; struct IXMLDOMNode **
0x18001e8ca  mov     rcx, r14; struct IXMLDOMDocument2 **
0x18001e8cd  call    ?InsertPEAPV3TagsTree@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@@Z; InsertPEAPV3TagsTree(IXMLDOMDocument2 * *,IXMLDOMNode * *)
0x18001e8d2  mov     ebx, eax
0x18001e8d4  test    eax, eax
0x18001e8d6  jz      short loc_18001E903
0x18001e8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8df  lea     rax, WPP_GLOBAL_Control
0x18001e8e6  cmp     rcx, rax
0x18001e8e9  jz      short loc_18001E903
0x18001e8eb  mov     edx, 61h ; 'a'
0x18001e8f0  mov     rcx, [rcx+10h]
0x18001e8f4  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001e8fb  mov     r9d, ebx
0x18001e8fe  call    WPP_SF_d
0x18001e903  mov     r15, [rsp+0B0h+var_20]
0x18001e90b  mov     rcx, [rbp+57h+var_80]
0x18001e90f  mov     r14, [rsp+98h]
0x18001e917  mov     r13, [rsp+0B0h+arg_10]
0x18001e91f  test    rcx, rcx
0x18001e922  jz      short loc_18001E938
0x18001e924  mov     rax, [rcx]
0x18001e927  mov     rax, [rax+10h]
0x18001e92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e930  mov     [rbp+57h+var_80], 0
0x18001e938  test    rsi, rsi
0x18001e93b  jz      short loc_18001E94C
0x18001e93d  mov     rcx, rsi; bstrString
0x18001e940  call    cs:__imp_SysFreeString
0x18001e947  nop     dword ptr [rax+rax+00h]
0x18001e94c  mov     rsi, [rsp+0B0h+arg_0]
0x18001e954  test    rdi, rdi
0x18001e957  jz      short loc_18001E968
0x18001e959  mov     rcx, rdi; bstrString
0x18001e95c  call    cs:__imp_SysFreeString
0x18001e963  nop     dword ptr [rax+rax+00h]
0x18001e968  mov     eax, ebx
0x18001e96a  add     rsp, 0A0h
0x18001e971  pop     rdi
0x18001e972  pop     rbx
0x18001e973  pop     rbp
0x18001e974  retn
```
