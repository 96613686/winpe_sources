# CConfigPolicy::UpdateCondition(ushort *,ushort *,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>)

- ea: `0x18003daf0`
- end: `0x18003dd9e`
- name: `?UpdateCondition@CConfigPolicy@@AEAAJPEAG0V?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(__int64, const OLECHAR *, const OLECHAR *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003835c`

## callees

- `0x18003daf0`
- `0x18003e908`
- `0x18003edbc`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003db43`
- `OLEAUT32!__imp_SysAllocString` at `0x18003db9b`
- `OLEAUT32!__imp_SysAllocString` at `0x18003dc56`
- `OLEAUT32!__imp_SysAllocString` at `0x18003db43`
- `OLEAUT32!__imp_SysAllocString` at `0x18003db9b`
- `OLEAUT32!__imp_SysAllocString` at `0x18003dc56`
- `OLEAUT32!__imp_VariantClear` at `0x18003db7e`
- `OLEAUT32!__imp_VariantClear` at `0x18003dc39`
- `OLEAUT32!__imp_VariantClear` at `0x18003dd0a`
- `OLEAUT32!__imp_VariantClear` at `0x18003db7e`
- `OLEAUT32!__imp_VariantClear` at `0x18003dc39`
- `OLEAUT32!__imp_VariantClear` at `0x18003dd0a`

## string_xrefs

- `0x18003dc28`: `CConfigPolicy::UpdateCondition(): Error %lx Couldn't get an SDO for the existing Condition object!`
- `0x18003dcd6`: `CConfigPolicy::UpdateCondition(): Error %lx Couldn't set the Condition's value!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::UpdateCondition(__int64 a1, const OLECHAR *a2, const OLECHAR *a3, _QWORD *a4)
{
  IRecordInfo *v7; // rax
  HRESULT v8; // eax
  IRecordInfo *v9; // rax
  __int64 v10; // rcx
  int ObjectFromCollection; // eax
  int v12; // edi
  __int64 v13; // rbx
  HRESULT v14; // eax
  IRecordInfo *v15; // rax
  __int128 v16; // xmm6
  IRecordInfo *v17; // xmm7_8
  HRESULT v18; // eax
  VARIANTARG pvarg; // [rsp+28h] [rbp-E0h] BYREF
  IRecordInfo *v21; // [rsp+40h] [rbp-C8h]
  __int64 v22; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG v23; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD *v24; // [rsp+78h] [rbp-90h]
  int v25; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v26[2044]; // [rsp+8Ch] [rbp-7Ch] BYREF

  v24 = a4;
  v22 = 0;
  v7 = (IRecordInfo *)SysAllocString(&word_180059138);
  if ( !v7 )
    _com_issue_error(-2147024882);
  pvarg.iVal = 8;
  pvarg.pRecInfo = v7;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v8 = VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v8 < 0 )
    _com_issue_error(v8);
  if ( a2 )
  {
    v9 = (IRecordInfo *)SysAllocString(a2);
    if ( !v9 )
      goto LABEL_32;
    pvarg.pRecInfo = v9;
  }
  else
  {
    pvarg.pRecInfo = 0;
  }
  pvarg.iVal = 8;
  v10 = *a4;
  *(_QWORD *)&pvarg.vt = v10;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  *(_OWORD *)&v23.vt = *(_OWORD *)&pvarg.decVal.Lo32;
  v23.pRecInfo = v21;
  ObjectFromCollection = GetObjectFromCollection((__int64)&v23, (struct IUnknown **)&pvarg, &v22);
  v12 = ObjectFromCollection;
  v13 = v22;
  if ( ObjectFromCollection < 0 )
  {
    if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v25,
        L"CConfigPolicy::UpdateCondition(): Error %lx Couldn't get an SDO for the existing Condition object!",
        (unsigned int)ObjectFromCollection);
LABEL_24:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
        gSdoUtilEtwContext,
        xmmword_180078BA0,
        &v25);
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  v14 = VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v14 < 0 )
    _com_issue_error(v14);
  if ( !a3 )
  {
    pvarg.pRecInfo = 0;
    goto LABEL_18;
  }
  v15 = (IRecordInfo *)SysAllocString(a3);
  if ( !v15 )
LABEL_32:
    _com_issue_error(-2147024882);
  pvarg.pRecInfo = v15;
LABEL_18:
  pvarg.iVal = 8;
  v16 = *(_OWORD *)&pvarg.decVal.Lo32;
  v17 = v21;
  *(_QWORD *)&pvarg.vt = v13;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  *(_OWORD *)&v23.vt = v16;
  v23.pRecInfo = v17;
  v12 = PutSdoProperty((struct IUnknown **)&pvarg, 0x400u, &v23);
  if ( v12 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(
      &v25,
      L"CConfigPolicy::UpdateCondition(): Error %lx Couldn't set the Condition's value!",
      (unsigned int)v12);
    goto LABEL_24;
  }
LABEL_25:
  v18 = VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v18 < 0 )
    _com_issue_error(v18);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( *a4 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 16LL))(*a4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003daf0  mov     rax, rsp
0x18003daf3  mov     [rax+8], rbx
0x18003daf7  push    rbp
0x18003daf8  push    rsi
0x18003daf9  push    rdi
0x18003dafa  push    r12
0x18003dafc  push    r14
0x18003dafe  lea     rbp, [rax-7D8h]
0x18003db05  sub     rsp, 8B0h
0x18003db0c  movaps  xmmword ptr [rax-38h], xmm6
0x18003db10  movaps  xmmword ptr [rax-48h], xmm7
0x18003db14  mov     rax, cs:__security_cookie
0x18003db1b  xor     rax, rsp
0x18003db1e  mov     [rbp+7D0h+var_50], rax
0x18003db25  mov     r14, r9
0x18003db28  mov     rsi, r8
0x18003db2b  mov     rbx, rdx
0x18003db2e  mov     [rsp+8D0h+var_860], r9
0x18003db33  mov     [rsp+8D0h+var_890], 0
0x18003db3c  lea     rcx, word_180059138; psz
0x18003db43  call    cs:__imp_SysAllocString
0x18003db49  test    rax, rax
0x18003db4c  jz      loc_18003DD83
0x18003db52  mov     r12d, 8
0x18003db58  mov     word ptr [rsp+8D0h+pvarg+8], r12w
0x18003db5e  mov     qword ptr [rsp+8D0h+pvarg+10h], rax
0x18003db63  xor     eax, eax
0x18003db65  mov     [rbp+7D0h+var_850], eax
0x18003db68  xor     edx, edx; Val
0x18003db6a  mov     r8d, 7FCh; Size
0x18003db70  lea     rcx, [rbp+7D0h+var_84C]; void *
0x18003db74  call    memset_0
0x18003db79  lea     rcx, [rsp+8D0h+pvarg+8]; pvarg
0x18003db7e  call    cs:__imp_VariantClear
0x18003db84  test    eax, eax
0x18003db86  js      loc_18003DD8E
0x18003db8c  test    rbx, rbx
0x18003db8f  jnz     short loc_18003DB98
0x18003db91  mov     qword ptr [rsp+8D0h+pvarg+10h], rbx
0x18003db96  jmp     short loc_18003DBAF
0x18003db98  mov     rcx, rbx; psz
0x18003db9b  call    cs:__imp_SysAllocString
0x18003dba1  test    rax, rax
0x18003dba4  jz      loc_18003DD78
0x18003dbaa  mov     qword ptr [rsp+8D0h+pvarg+10h], rax
0x18003dbaf  mov     word ptr [rsp+8D0h+pvarg+8], r12w
0x18003dbb5  mov     rcx, [r14]
0x18003dbb8  mov     qword ptr [rsp+8D0h+pvarg], rcx
0x18003dbbd  test    rcx, rcx
0x18003dbc0  jz      short loc_18003DBCF
0x18003dbc2  mov     rax, [rcx]
0x18003dbc5  mov     rax, [rax+8]
0x18003dbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbce  nop
0x18003dbcf  movups  xmm0, xmmword ptr [rsp+8D0h+pvarg+8]
0x18003dbd4  movaps  xmmword ptr [rsp+8D0h+var_888+8], xmm0
0x18003dbd9  movsd   xmm1, [rsp+8D0h+var_898]
0x18003dbdf  movsd   [rsp+8D0h+var_870], xmm1
0x18003dbe5  lea     r8, [rsp+8D0h+var_890]
0x18003dbea  lea     rdx, [rsp+8D0h+pvarg]
0x18003dbef  lea     rcx, [rsp+8D0h+var_888+8]
0x18003dbf4  call    ?GetObjectFromCollection@@YAJUtagVARIANT@@V?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; GetObjectFromCollection(tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &)
0x18003dbf9  mov     edi, eax
0x18003dbfb  mov     rbx, [rsp+8D0h+var_890]
0x18003dc00  test    eax, eax
0x18003dc02  jns     short loc_18003DC34
0x18003dc04  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003dc0b  jz      loc_18003DD05
0x18003dc11  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003dc19  jz      loc_18003DD05
0x18003dc1f  xor     ecx, ecx
0x18003dc21  mov     word ptr [rbp+7D0h+var_850], cx
0x18003dc25  mov     r8d, eax
0x18003dc28  lea     rdx, aCconfigpolicyU_0; "CConfigPolicy::UpdateCondition(): Error"...
0x18003dc2f  jmp     loc_18003DCDD
0x18003dc34  lea     rcx, [rsp+8D0h+pvarg+8]; pvarg
0x18003dc39  call    cs:__imp_VariantClear
0x18003dc3f  test    eax, eax
0x18003dc41  js      loc_18003DD96
0x18003dc47  test    rsi, rsi
0x18003dc4a  jnz     short loc_18003DC53
0x18003dc4c  mov     qword ptr [rsp+8D0h+pvarg+10h], rsi
0x18003dc51  jmp     short loc_18003DC6A
0x18003dc53  mov     rcx, rsi; psz
0x18003dc56  call    cs:__imp_SysAllocString
0x18003dc5c  test    rax, rax
0x18003dc5f  jz      loc_18003DD78
0x18003dc65  mov     qword ptr [rsp+8D0h+pvarg+10h], rax
0x18003dc6a  mov     word ptr [rsp+8D0h+pvarg+8], r12w
0x18003dc70  movups  xmm6, xmmword ptr [rsp+8D0h+pvarg+8]
0x18003dc75  movsd   xmm7, [rsp+8D0h+var_898]
0x18003dc7b  mov     qword ptr [rsp+8D0h+pvarg], rbx
0x18003dc80  test    rbx, rbx
0x18003dc83  jz      short loc_18003DC95
0x18003dc85  mov     rax, [rbx]
0x18003dc88  mov     rcx, rbx
0x18003dc8b  mov     rax, [rax+8]
0x18003dc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc94  nop
0x18003dc95  movaps  xmmword ptr [rsp+8D0h+var_888+8], xmm6
0x18003dc9a  movsd   [rsp+8D0h+var_870], xmm7
0x18003dca0  lea     r8, [rsp+8D0h+var_888+8]
0x18003dca5  mov     edx, 400h
0x18003dcaa  lea     rcx, [rsp+8D0h+pvarg]
0x18003dcaf  call    ?PutSdoProperty@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JUtagVARIANT@@@Z; PutSdoProperty(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,tagVARIANT)
0x18003dcb4  mov     edi, eax
0x18003dcb6  test    eax, eax
0x18003dcb8  jns     short loc_18003DD05
0x18003dcba  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003dcc1  jz      short loc_18003DD05
0x18003dcc3  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003dccb  jz      short loc_18003DD05
0x18003dccd  xor     eax, eax
0x18003dccf  mov     word ptr [rbp+7D0h+var_850], ax
0x18003dcd3  mov     r8d, edi
0x18003dcd6  lea     rdx, aCconfigpolicyU; "CConfigPolicy::UpdateCondition(): Error"...
0x18003dcdd  lea     rcx, [rbp+7D0h+var_850]
0x18003dce1  call    FormatRRASErrorString
0x18003dce6  lea     r8, [rbp+7D0h+var_850]
0x18003dcea  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003dcf1  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003dcf8  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003dcff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd04  nop
0x18003dd05  lea     rcx, [rsp+8D0h+pvarg+8]; pvarg
0x18003dd0a  call    cs:__imp_VariantClear
0x18003dd10  test    eax, eax
0x18003dd12  js      short loc_18003DD70
0x18003dd14  test    rbx, rbx
0x18003dd17  jz      short loc_18003DD29
0x18003dd19  mov     rax, [rbx]
0x18003dd1c  mov     rcx, rbx
0x18003dd1f  mov     rax, [rax+10h]
0x18003dd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd28  nop
0x18003dd29  mov     rcx, [r14]
0x18003dd2c  test    rcx, rcx
0x18003dd2f  jz      short loc_18003DD3E
0x18003dd31  mov     rax, [rcx]
0x18003dd34  mov     rax, [rax+10h]
0x18003dd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd3d  nop
0x18003dd3e  mov     eax, edi
0x18003dd40  mov     rcx, [rbp+7D0h+var_50]
0x18003dd47  xor     rcx, rsp; StackCookie
0x18003dd4a  call    __security_check_cookie
0x18003dd4f  lea     r11, [rsp+8D0h+var_20]
0x18003dd57  mov     rbx, [r11+30h]
0x18003dd5b  movaps  xmm6, xmmword ptr [r11-10h]
0x18003dd60  movaps  xmm7, xmmword ptr [r11-20h]
0x18003dd65  mov     rsp, r11
0x18003dd68  pop     r14
0x18003dd6a  pop     r12
0x18003dd6c  pop     rdi
0x18003dd6d  pop     rsi
0x18003dd6e  pop     rbp
0x18003dd6f  retn
0x18003dd70  mov     ecx, eax; int
0x18003dd72  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003dd78  mov     ecx, 8007000Eh; int
0x18003dd7d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003dd83  mov     ecx, 8007000Eh; int
0x18003dd88  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003dd8e  mov     ecx, eax; int
0x18003dd90  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003dd96  mov     ecx, eax; int
0x18003dd98  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
