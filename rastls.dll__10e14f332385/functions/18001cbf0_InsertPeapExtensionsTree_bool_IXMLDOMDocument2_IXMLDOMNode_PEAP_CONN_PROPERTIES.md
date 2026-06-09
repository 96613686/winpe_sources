# InsertPeapExtensionsTree(bool,IXMLDOMDocument2 * *,IXMLDOMNode * *,_PEAP_CONN_PROPERTIES *)

- ea: `0x18001cbf0`
- end: `0x18001cea9`
- name: `?InsertPeapExtensionsTree@@YAK_NPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_PEAP_CONN_PROPERTIES@@@Z`
- size: `697`
- prototype: `unsigned int(bool, struct IXMLDOMDocument2 **, struct IXMLDOMNode **, struct _PEAP_CONN_PROPERTIES *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006400`

## callees

- `0x180004bd0`
- `0x180017ab8`
- `0x180019d60`
- `0x18001cbf0`
- `0x18001ceb0`
- `0x18007c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001cc2e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cc4f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cc76`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cc2e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cc4f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cc76`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd59`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ce80`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ce96`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd59`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ce80`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ce96`
- `OLEAUT32!__imp_VariantInit` at `0x18001cc9a`
- `OLEAUT32!__imp_VariantInit` at `0x18001ccbf`
- `OLEAUT32!__imp_VariantInit` at `0x18001cc9a`
- `OLEAUT32!__imp_VariantInit` at `0x18001ccbf`
- `OLEAUT32!__imp_VariantClear` at `0x18001cd12`
- `OLEAUT32!__imp_VariantClear` at `0x18001cd63`
- `OLEAUT32!__imp_VariantClear` at `0x18001cd12`
- `OLEAUT32!__imp_VariantClear` at `0x18001cd63`

## string_xrefs

- `0x18001cc48`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV2`
- `0x18001cc05`: `http://www.microsoft.com/provisioning/MsPeapConnectionPropertiesV1`
- `0x18001cc67`: `PeapExtensions`

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
0x18001cbf0  mov     rax, rsp
0x18001cbf3  push    rbp
0x18001cbf4  push    rbx
0x18001cbf5  push    rdi
0x18001cbf6  lea     rbp, [rax-5Fh]
0x18001cbfa  sub     rsp, 0A0h
0x18001cc01  mov     [rax+8], rsi
0x18001cc05  lea     rcx, aHttpWwwMicroso_1; "http://www.microsoft.com/provisioning/M"...
0x18001cc0c  mov     [rax+18h], r13
0x18001cc10  xorps   xmm0, xmm0
0x18001cc13  mov     [rax-20h], r14
0x18001cc17  mov     r13, r9
0x18001cc1a  xor     eax, eax
0x18001cc1c  mov     rbx, r8
0x18001cc1f  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001cc23  mov     r14, rdx
0x18001cc26  mov     [rbp+57h+var_80], rax
0x18001cc2a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001cc2e  call    cs:__imp_SysAllocString
0x18001cc34  mov     rsi, rax
0x18001cc37  test    rax, rax
0x18001cc3a  jnz     short loc_18001CC48
0x18001cc3c  xor     edi, edi
0x18001cc3e  mov     ebx, 8007000Eh
0x18001cc43  jmp     loc_18001CE4B
0x18001cc48  lea     rcx, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/M"...
0x18001cc4f  call    cs:__imp_SysAllocString
0x18001cc55  mov     rdi, rax
0x18001cc58  test    rax, rax
0x18001cc5b  jnz     short loc_18001CC67
0x18001cc5d  mov     ebx, 8007000Eh
0x18001cc62  jmp     loc_18001CE4B
0x18001cc67  lea     rcx, aPeapextensions; "PeapExtensions"
0x18001cc6e  mov     [rsp+0B0h+var_20], r15
0x18001cc76  call    cs:__imp_SysAllocString
0x18001cc7c  mov     r15, rax
0x18001cc7f  test    rax, rax
0x18001cc82  jnz     short loc_18001CC8E
0x18001cc84  mov     ebx, 8007000Eh
0x18001cc89  jmp     loc_18001CE43
0x18001cc8e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001cc92  mov     [rsp+0B0h+arg_8], r12
0x18001cc9a  call    cs:__imp_VariantInit
0x18001cca0  mov     r12, [rbx]
0x18001cca3  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001cca7  mov     rbx, [r14]
0x18001ccaa  xor     eax, eax
0x18001ccac  xorps   xmm0, xmm0
0x18001ccaf  mov     word ptr [rbp+57h+pvarg], ax
0x18001ccb3  mov     [rbp+57h+var_78], rax
0x18001ccb7  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18001ccbb  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18001ccbf  call    cs:__imp_VariantInit
0x18001ccc5  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x18001ccca  lea     rcx, [rbp+57h+var_78]
0x18001ccce  mov     eax, 3
0x18001ccd3  mov     dword ptr [rbp+57h+var_70+8], 1
0x18001ccda  mov     word ptr [rbp+57h+var_70], ax
0x18001ccde  lea     rdx, [rbp+57h+var_40]
0x18001cce2  mov     rax, [rbx]
0x18001cce5  mov     r9, rsi
0x18001cce8  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x18001ccec  mov     [rsp+20h], rcx
0x18001ccf1  mov     r8, r15
0x18001ccf4  mov     rcx, rbx
0x18001ccf7  movsd   [rbp+57h+var_30], xmm1
0x18001ccfc  mov     rax, [rax+1C0h]
0x18001cd03  movaps  [rbp+57h+var_40], xmm0
0x18001cd07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd0c  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001cd10  mov     ebx, eax
0x18001cd12  call    cs:__imp_VariantClear
0x18001cd18  test    ebx, ebx
0x18001cd1a  jnz     short loc_18001CD39
0x18001cd1c  mov     rax, [r12]
0x18001cd20  lea     r8, [rbp+57h+var_80]
0x18001cd24  mov     rdx, [rbp+57h+var_78]
0x18001cd28  mov     rcx, r12
0x18001cd2b  mov     rax, [rax+0A8h]
0x18001cd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd37  mov     ebx, eax
0x18001cd39  mov     rcx, [rbp+57h+var_78]
0x18001cd3d  mov     r12, [rsp+0B0h+arg_8]
0x18001cd45  test    rcx, rcx
0x18001cd48  jz      short loc_18001CD56
0x18001cd4a  mov     rax, [rcx]
0x18001cd4d  mov     rax, [rax+10h]
0x18001cd51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd56  mov     rcx, r15; bstrString
0x18001cd59  call    cs:__imp_SysFreeString
0x18001cd5f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001cd63  call    cs:__imp_VariantClear
0x18001cd69  test    ebx, ebx
0x18001cd6b  jz      short loc_18001CD8E
0x18001cd6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd74  lea     rax, WPP_GLOBAL_Control
0x18001cd7b  cmp     rcx, rax
0x18001cd7e  jz      loc_18001CE43
0x18001cd84  mov     edx, 5Eh ; '^'
0x18001cd89  jmp     loc_18001CE30
0x18001cd8e  lea     r9, [r13+10h]; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18001cd92  mov     rdx, r14; struct IXMLDOMDocument2 **
0x18001cd95  lea     r8, [rbp+57h+var_80]; struct IXMLDOMNode **
0x18001cd99  mov     cl, 1; bool
0x18001cd9b  call    ?InsertExtensionTags@@YAK_NPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; InsertExtensionTags(bool,IXMLDOMDocument2 * *,IXMLDOMNode * *,_EAPTLS_CONN_PROPERTIES_V1 *)
0x18001cda0  mov     ebx, eax
0x18001cda2  test    eax, eax
0x18001cda4  jz      short loc_18001CDC4
0x18001cda6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdad  lea     rax, WPP_GLOBAL_Control
0x18001cdb4  cmp     rcx, rax
0x18001cdb7  jz      loc_18001CE43
0x18001cdbd  mov     edx, 5Fh ; '_'
0x18001cdc2  jmp     short loc_18001CE30
0x18001cdc4  mov     r9, r13; struct _PEAP_CONN_PROPERTIES *
0x18001cdc7  lea     r8, [rbp+57h+var_80]; struct IXMLDOMNode **
0x18001cdcb  mov     rdx, r14; struct IXMLDOMDocument2 **
0x18001cdce  mov     rcx, rdi; unsigned __int16 *
0x18001cdd1  call    ?InsertIdentityPrivacyTree@@YAKPEAGPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@PEAU_PEAP_CONN_PROPERTIES@@@Z; InsertIdentityPrivacyTree(ushort *,IXMLDOMDocument2 * *,IXMLDOMNode * *,_PEAP_CONN_PROPERTIES *)
0x18001cdd6  mov     ebx, eax
0x18001cdd8  test    eax, eax
0x18001cdda  jz      short loc_18001CDF6
0x18001cddc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cde3  lea     rax, WPP_GLOBAL_Control
0x18001cdea  cmp     rcx, rax
0x18001cded  jz      short loc_18001CE43
0x18001cdef  mov     edx, 60h ; '`'
0x18001cdf4  jmp     short loc_18001CE30
0x18001cdf6  mov     eax, [r13+18h]
0x18001cdfa  and     eax, 220h
0x18001cdff  cmp     eax, 200h
0x18001ce04  jnz     short loc_18001CE43
0x18001ce06  lea     rdx, [rbp+57h+var_80]; struct IXMLDOMNode **
0x18001ce0a  mov     rcx, r14; struct IXMLDOMDocument2 **
0x18001ce0d  call    ?InsertPEAPV3TagsTree@@YAKPEAPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMNode@@@Z; InsertPEAPV3TagsTree(IXMLDOMDocument2 * *,IXMLDOMNode * *)
0x18001ce12  mov     ebx, eax
0x18001ce14  test    eax, eax
0x18001ce16  jz      short loc_18001CE43
0x18001ce18  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce1f  lea     rax, WPP_GLOBAL_Control
0x18001ce26  cmp     rcx, rax
0x18001ce29  jz      short loc_18001CE43
0x18001ce2b  mov     edx, 61h ; 'a'
0x18001ce30  mov     rcx, [rcx+10h]
0x18001ce34  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18001ce3b  mov     r9d, ebx
0x18001ce3e  call    WPP_SF_d
0x18001ce43  mov     r15, [rsp+0B0h+var_20]
0x18001ce4b  mov     rcx, [rbp+57h+var_80]
0x18001ce4f  mov     r14, [rsp+98h]
0x18001ce57  mov     r13, [rsp+0B0h+arg_10]
0x18001ce5f  test    rcx, rcx
0x18001ce62  jz      short loc_18001CE78
0x18001ce64  mov     rax, [rcx]
0x18001ce67  mov     rax, [rax+10h]
0x18001ce6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce70  mov     [rbp+57h+var_80], 0
0x18001ce78  test    rsi, rsi
0x18001ce7b  jz      short loc_18001CE86
0x18001ce7d  mov     rcx, rsi; bstrString
0x18001ce80  call    cs:__imp_SysFreeString
0x18001ce86  mov     rsi, [rsp+0B0h+arg_0]
0x18001ce8e  test    rdi, rdi
0x18001ce91  jz      short loc_18001CE9C
0x18001ce93  mov     rcx, rdi; bstrString
0x18001ce96  call    cs:__imp_SysFreeString
0x18001ce9c  mov     eax, ebx
0x18001ce9e  add     rsp, 0A0h
0x18001cea5  pop     rdi
0x18001cea6  pop     rbx
0x18001cea7  pop     rbp
0x18001cea8  retn
```
