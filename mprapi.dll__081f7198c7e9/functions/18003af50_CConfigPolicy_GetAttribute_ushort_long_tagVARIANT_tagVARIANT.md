# CConfigPolicy::GetAttribute(ushort *,long,tagVARIANT,tagVARIANT *)

- ea: `0x18003af50`
- end: `0x18003b164`
- name: `?GetAttribute@CConfigPolicy@@UEAAJPEAGJUtagVARIANT@@PEAU2@@Z`
- size: `532`
- prototype: `__int64 __fastcall(CConfigPolicy *this, BSTR pbstr, enum _ATTRIBUTEID, struct tagVARIANT *, struct tagVARIANT *pvargDest)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18003af50`
- `0x18003b16c`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003af8f`
- `OLEAUT32!__imp_SysAllocString` at `0x18003af8f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003afd7`
- `OLEAUT32!__imp_SysStringLen` at `0x18003afd7`
- `OLEAUT32!__imp_VariantInit` at `0x18003afb7`
- `OLEAUT32!__imp_VariantInit` at `0x18003afb7`
- `OLEAUT32!__imp_VariantClear` at `0x18003b10f`
- `OLEAUT32!__imp_VariantClear` at `0x18003b11e`
- `OLEAUT32!__imp_VariantClear` at `0x18003b10f`
- `OLEAUT32!__imp_VariantClear` at `0x18003b11e`
- `OLEAUT32!__imp_VariantCopy` at `0x18003b0b3`
- `OLEAUT32!__imp_VariantCopy` at `0x18003b0b3`

## string_xrefs

- `0x18003b0a2`: `GetAttribute(): Error %lx Couldn't delete specified Attribute!`
- `0x18003b0db`: `GetAttribute(): Error copying Attribute's value (Variant)! %lx`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::GetAttribute(
        CConfigPolicy *this,
        BSTR pbstr,
        enum _ATTRIBUTEID a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *pvargDest)
{
  BSTR v9; // rax
  __int64 v10; // rdx
  const wchar_t *v11; // r8
  HRESULT v12; // ebx
  int AttributeHelper; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  VARIANTARG v17; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  struct tagVARIANT v19; // [rsp+60h] [rbp-A0h] BYREF
  struct tagVARIANT v20; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v9 = SysAllocString(pbstr);
  if ( !v9 && pbstr )
    _com_issue_error(-2147024882);
  v17.vt = 8;
  v17.llVal = (LONGLONG)v9;
  VariantInit(&pvarg);
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  if ( !SysStringLen(pbstr) )
  {
    if ( !gIsSdoUtilEtwTracingAvailable )
      goto LABEL_8;
    v10 = xmmword_180078BA0;
    if ( !(_QWORD)xmmword_180078BA0 )
      goto LABEL_8;
    v11 = L"GetAttribute(): The Policy name must not be empty!";
LABEL_7:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      v10,
      v11);
LABEL_8:
    v12 = -2147024809;
    goto LABEL_22;
  }
  if ( !pvargDest )
  {
    if ( !gIsSdoUtilEtwTracingAvailable )
      goto LABEL_8;
    v10 = xmmword_180078BA0;
    if ( !(_QWORD)xmmword_180078BA0 )
      goto LABEL_8;
    v11 = L"GetAttribute(): Error: return value pointer is NULL!";
    goto LABEL_7;
  }
  v19 = *a4;
  v20 = v17;
  AttributeHelper = CConfigPolicy::GetAttributeHelper(this, &v20, a3, &v19, &pvarg);
  v12 = AttributeHelper;
  if ( AttributeHelper >= 0 )
  {
    v12 = VariantCopy(pvargDest, &pvarg);
    if ( v12 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"GetAttribute(): Error copying Attribute's value (Variant)! %lx", (unsigned int)v12);
      goto LABEL_21;
    }
  }
  else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(
      &v21,
      L"GetAttribute(): Error %lx Couldn't delete specified Attribute!",
      (unsigned int)AttributeHelper);
LABEL_21:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      xmmword_180078BA0,
      &v21);
  }
LABEL_22:
  v14 = VariantClear(&pvarg);
  if ( v14 < 0 )
    _com_issue_error(v14);
  v15 = VariantClear(&v17);
  if ( v15 < 0 )
    _com_issue_error(v15);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003af50  push    rbp
0x18003af52  push    rbx
0x18003af53  push    rsi
0x18003af54  push    rdi
0x18003af55  push    r14
0x18003af57  push    r15
0x18003af59  lea     rbp, [rsp-7B8h]
0x18003af61  sub     rsp, 8B8h
0x18003af68  mov     rax, cs:__security_cookie
0x18003af6f  xor     rax, rsp
0x18003af72  mov     [rbp+7E0h+var_40], rax
0x18003af79  mov     rsi, r9
0x18003af7c  mov     r15d, r8d
0x18003af7f  mov     rbx, rdx
0x18003af82  mov     r14, rcx
0x18003af85  mov     rdi, [rbp+7E0h+pvargDest]
0x18003af8c  mov     rcx, rdx; psz
0x18003af8f  call    cs:__imp_SysAllocString
0x18003af95  test    rax, rax
0x18003af98  jnz     short loc_18003AFA3
0x18003af9a  test    rbx, rbx
0x18003af9d  jnz     loc_18003B151
0x18003afa3  mov     ecx, 8
0x18003afa8  mov     word ptr [rsp+8E0h+var_8B0], cx
0x18003afad  mov     qword ptr [rsp+8E0h+var_8B0+8], rax
0x18003afb2  lea     rcx, [rsp+8E0h+pvarg]; pvarg
0x18003afb7  call    cs:__imp_VariantInit
0x18003afbd  nop
0x18003afbe  xor     eax, eax
0x18003afc0  mov     [rbp+7E0h+var_840], eax
0x18003afc3  xor     edx, edx; Val
0x18003afc5  mov     r8d, 7FCh; Size
0x18003afcb  lea     rcx, [rbp+7E0h+var_83C]; void *
0x18003afcf  call    memset_0
0x18003afd4  mov     rcx, rbx; pbstr
0x18003afd7  call    cs:__imp_SysStringLen
0x18003afdd  test    eax, eax
0x18003afdf  jnz     short loc_18003B019
0x18003afe1  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, eax; int gIsSdoUtilEtwTracingAvailable
0x18003afe7  jz      short loc_18003B00F
0x18003afe9  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003aff0  test    rdx, rdx
0x18003aff3  jz      short loc_18003B00F
0x18003aff5  lea     r8, aGetattributeTh; "GetAttribute(): The Policy name must no"...
0x18003affc  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003b003  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003b00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b00f  mov     ebx, 80070057h
0x18003b014  jmp     loc_18003B10A
0x18003b019  test    rdi, rdi
0x18003b01c  jnz     short loc_18003B03B
0x18003b01e  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, edi; int gIsSdoUtilEtwTracingAvailable
0x18003b024  jz      short loc_18003B00F
0x18003b026  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003b02d  test    rdx, rdx
0x18003b030  jz      short loc_18003B00F
0x18003b032  lea     r8, aGetattributeEr_1; "GetAttribute(): Error: return value poi"...
0x18003b039  jmp     short loc_18003AFFC
0x18003b03b  movups  xmm0, xmmword ptr [rsi]
0x18003b03e  movaps  xmmword ptr [rsp+8E0h+var_880], xmm0
0x18003b043  movsd   xmm1, qword ptr [rsi+10h]
0x18003b048  movsd   qword ptr [rsp+8E0h+var_880+10h], xmm1
0x18003b04e  movups  xmm0, xmmword ptr [rsp+8E0h+var_8B0]
0x18003b053  movaps  xmmword ptr [rbp+7E0h+var_860], xmm0
0x18003b057  movsd   xmm1, qword ptr [rsp+8E0h+var_8B0+10h]
0x18003b05d  movsd   qword ptr [rbp+7E0h+var_860+10h], xmm1
0x18003b062  lea     rax, [rsp+8E0h+pvarg]
0x18003b067  mov     [rsp+8E0h+var_8C0], rax; pvargDest
0x18003b06c  lea     r9, [rsp+8E0h+var_880]; struct tagVARIANT *
0x18003b071  mov     r8d, r15d; enum _ATTRIBUTEID
0x18003b074  lea     rdx, [rbp+7E0h+var_860]; struct tagVARIANT *
0x18003b078  mov     rcx, r14; this
0x18003b07b  call    ?GetAttributeHelper@CConfigPolicy@@AEAAJUtagVARIANT@@W4_ATTRIBUTEID@@0AEAU2@@Z; CConfigPolicy::GetAttributeHelper(tagVARIANT,_ATTRIBUTEID,tagVARIANT,tagVARIANT &)
0x18003b080  mov     ebx, eax
0x18003b082  test    eax, eax
0x18003b084  jns     short loc_18003B0AB
0x18003b086  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003b08d  jz      short loc_18003B10A
0x18003b08f  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003b097  jz      short loc_18003B10A
0x18003b099  xor     ecx, ecx
0x18003b09b  mov     word ptr [rbp+7E0h+var_840], cx
0x18003b09f  mov     r8d, eax
0x18003b0a2  lea     rdx, aGetattributeEr_0; "GetAttribute(): Error %lx Couldn't dele"...
0x18003b0a9  jmp     short loc_18003B0E2
0x18003b0ab  lea     rdx, [rsp+8E0h+pvarg]; pvargSrc
0x18003b0b0  mov     rcx, rdi; pvargDest
0x18003b0b3  call    cs:__imp_VariantCopy
0x18003b0b9  mov     ebx, eax
0x18003b0bb  test    eax, eax
0x18003b0bd  jns     short loc_18003B10A
0x18003b0bf  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003b0c6  jz      short loc_18003B10A
0x18003b0c8  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003b0d0  jz      short loc_18003B10A
0x18003b0d2  xor     eax, eax
0x18003b0d4  mov     word ptr [rbp+7E0h+var_840], ax
0x18003b0d8  mov     r8d, ebx
0x18003b0db  lea     rdx, aGetattributeEr; "GetAttribute(): Error copying Attribute"...
0x18003b0e2  lea     rcx, [rbp+7E0h+var_840]
0x18003b0e6  call    FormatRRASErrorString
0x18003b0eb  lea     r8, [rbp+7E0h+var_840]
0x18003b0ef  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003b0f6  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003b0fd  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003b104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b109  nop
0x18003b10a  lea     rcx, [rsp+8E0h+pvarg]; pvarg
0x18003b10f  call    cs:__imp_VariantClear
0x18003b115  test    eax, eax
0x18003b117  js      short loc_18003B15C
0x18003b119  lea     rcx, [rsp+8E0h+var_8B0]; pvarg
0x18003b11e  call    cs:__imp_VariantClear
0x18003b124  test    eax, eax
0x18003b126  js      short loc_18003B149
0x18003b128  mov     eax, ebx
0x18003b12a  mov     rcx, [rbp+7E0h+var_40]
0x18003b131  xor     rcx, rsp; StackCookie
0x18003b134  call    __security_check_cookie
0x18003b139  add     rsp, 8B8h
0x18003b140  pop     r15
0x18003b142  pop     r14
0x18003b144  pop     rdi
0x18003b145  pop     rsi
0x18003b146  pop     rbx
0x18003b147  pop     rbp
0x18003b148  retn
0x18003b149  mov     ecx, eax; int
0x18003b14b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003b151  mov     ecx, 8007000Eh; int
0x18003b156  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003b15c  mov     ecx, eax; int
0x18003b15e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
