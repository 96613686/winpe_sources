# CConfigPolicy::RemoveAttribute(ushort *,long,tagVARIANT)

- ea: `0x18003cdf0`
- end: `0x18003cf2f`
- name: `?RemoveAttribute@CConfigPolicy@@UEAAJPEAGJUtagVARIANT@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(CConfigPolicy *__hidden this, OLECHAR *psz, enum _ATTRIBUTEID, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800377e8`

## callees

- `0x18003cdf0`
- `0x18003d248`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003ce26`
- `OLEAUT32!__imp_SysAllocString` at `0x18003ce26`
- `OLEAUT32!__imp_VariantClear` at `0x18003cef3`
- `OLEAUT32!__imp_VariantClear` at `0x18003cef3`

## string_xrefs

- `0x18003cebf`: `RemoveAttribute(): Error %lx Couldn't remove the Attribute from the Policy!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::RemoveAttribute(
        CConfigPolicy *this,
        OLECHAR *psz,
        enum _ATTRIBUTEID a3,
        struct tagVARIANT *a4)
{
  BSTR v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  HRESULT v11; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-E0h] BYREF
  struct tagVARIANT v14; // [rsp+40h] [rbp-C0h] BYREF
  struct tagVARIANT v15; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v8 = SysAllocString(psz);
  if ( !v8 && psz )
    _com_issue_error(-2147024882);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)v8;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v14 = *a4;
  v15 = pvarg;
  v9 = CConfigPolicy::RemoveVariantAttributeHelper(this, &v15, a3, &v14);
  v10 = v9;
  if ( v9 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v16) = 0;
    FormatRRASErrorString(
      &v16,
      L"RemoveAttribute(): Error %lx Couldn't remove the Attribute from the Policy!",
      (unsigned int)v9);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      xmmword_180078BA0,
      &v16);
  }
  v11 = VariantClear(&pvarg);
  if ( v11 < 0 )
    _com_issue_error(v11);
  return v10;
}

```

## disassembly

```asm
0x18003cdf0  push    rbp
0x18003cdf2  push    rbx
0x18003cdf3  push    rsi
0x18003cdf4  push    rdi
0x18003cdf5  push    r14
0x18003cdf7  lea     rbp, [rsp-790h]
0x18003cdff  sub     rsp, 890h
0x18003ce06  mov     rax, cs:__security_cookie
0x18003ce0d  xor     rax, rsp
0x18003ce10  mov     [rbp+7B0h+var_30], rax
0x18003ce17  mov     rdi, r9
0x18003ce1a  mov     r14d, r8d
0x18003ce1d  mov     rbx, rdx
0x18003ce20  mov     rsi, rcx
0x18003ce23  mov     rcx, rdx; psz
0x18003ce26  call    cs:__imp_SysAllocString
0x18003ce2c  test    rax, rax
0x18003ce2f  jnz     short loc_18003CE3A
0x18003ce31  test    rbx, rbx
0x18003ce34  jnz     loc_18003CF24
0x18003ce3a  mov     ecx, 8
0x18003ce3f  mov     word ptr [rsp+8B0h+pvarg], cx
0x18003ce44  mov     qword ptr [rsp+8B0h+pvarg+8], rax
0x18003ce49  xor     eax, eax
0x18003ce4b  mov     [rbp+7B0h+var_830], eax
0x18003ce4e  xor     edx, edx; Val
0x18003ce50  mov     r8d, 7FCh; Size
0x18003ce56  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18003ce5a  call    memset_0
0x18003ce5f  movups  xmm0, xmmword ptr [rdi]
0x18003ce62  movaps  xmmword ptr [rsp+8B0h+var_870], xmm0
0x18003ce67  movsd   xmm1, qword ptr [rdi+10h]
0x18003ce6c  movsd   qword ptr [rsp+8B0h+var_870+10h], xmm1
0x18003ce72  movups  xmm0, xmmword ptr [rsp+8B0h+pvarg]
0x18003ce77  movaps  xmmword ptr [rsp+8B0h+var_850], xmm0
0x18003ce7c  movsd   xmm1, qword ptr [rsp+8B0h+pvarg+10h]
0x18003ce82  movsd   qword ptr [rsp+8B0h+var_850+10h], xmm1
0x18003ce88  lea     r9, [rsp+8B0h+var_870]; struct tagVARIANT
0x18003ce8d  mov     r8d, r14d; enum _ATTRIBUTEID
0x18003ce90  lea     rdx, [rsp+8B0h+var_850]; struct tagVARIANT
0x18003ce95  mov     rcx, rsi; this
0x18003ce98  call    ?RemoveVariantAttributeHelper@CConfigPolicy@@AEAAJUtagVARIANT@@W4_ATTRIBUTEID@@0@Z; CConfigPolicy::RemoveVariantAttributeHelper(tagVARIANT,_ATTRIBUTEID,tagVARIANT)
0x18003ce9d  mov     ebx, eax
0x18003ce9f  test    eax, eax
0x18003cea1  jns     short loc_18003CEEE
0x18003cea3  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003ceaa  jz      short loc_18003CEEE
0x18003ceac  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003ceb4  jz      short loc_18003CEEE
0x18003ceb6  xor     ecx, ecx
0x18003ceb8  mov     word ptr [rbp+7B0h+var_830], cx
0x18003cebc  mov     r8d, eax
0x18003cebf  lea     rdx, aRemoveattribut; "RemoveAttribute(): Error %lx Couldn't r"...
0x18003cec6  lea     rcx, [rbp+7B0h+var_830]
0x18003ceca  call    FormatRRASErrorString
0x18003cecf  lea     r8, [rbp+7B0h+var_830]
0x18003ced3  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003ceda  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003cee1  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003cee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ceed  nop
0x18003ceee  lea     rcx, [rsp+8B0h+pvarg]; pvarg
0x18003cef3  call    cs:__imp_VariantClear
0x18003cef9  test    eax, eax
0x18003cefb  js      short loc_18003CF1C
0x18003cefd  mov     eax, ebx
0x18003ceff  mov     rcx, [rbp+7B0h+var_30]
0x18003cf06  xor     rcx, rsp; StackCookie
0x18003cf09  call    __security_check_cookie
0x18003cf0e  add     rsp, 890h
0x18003cf15  pop     r14
0x18003cf17  pop     rdi
0x18003cf18  pop     rsi
0x18003cf19  pop     rbx
0x18003cf1a  pop     rbp
0x18003cf1b  retn
0x18003cf1c  mov     ecx, eax; int
0x18003cf1e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003cf24  mov     ecx, 8007000Eh; int
0x18003cf29  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
