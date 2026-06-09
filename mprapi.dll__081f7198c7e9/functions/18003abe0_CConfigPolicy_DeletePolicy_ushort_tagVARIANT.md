# CConfigPolicy::DeletePolicy(ushort *,tagVARIANT)

- ea: `0x18003abe0`
- end: `0x18003ad64`
- name: `?DeletePolicy@CConfigPolicy@@UEAAJPEAGUtagVARIANT@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(CConfigPolicy *__hidden this, BSTR pbstr, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18003abe0`
- `0x18003ad6c`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003ac14`
- `OLEAUT32!__imp_SysAllocString` at `0x18003ac14`
- `OLEAUT32!__imp_SysStringLen` at `0x18003ac50`
- `OLEAUT32!__imp_SysStringLen` at `0x18003ac50`
- `OLEAUT32!__imp_VariantClear` at `0x18003ad23`
- `OLEAUT32!__imp_VariantClear` at `0x18003ad23`

## string_xrefs

- `0x18003ac6e`: `DeletePolicy(): The Policy name must not be empty!`
- `0x18003acef`: `DeletePolicy(): Error %lx Couldn't delete Policy from the IAS Server!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::DeletePolicy(CConfigPolicy *this, BSTR pbstr, struct tagVARIANT *a3)
{
  BSTR v6; // rax
  unsigned int v7; // ebx
  int v8; // eax
  HRESULT v9; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-E0h] BYREF
  struct tagVARIANT v12; // [rsp+40h] [rbp-C0h] BYREF
  struct tagVARIANT v13; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v15[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v6 = SysAllocString(pbstr);
  if ( !v6 && pbstr )
    _com_issue_error(-2147024882);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)v6;
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  if ( SysStringLen(pbstr) )
  {
    v12 = *a3;
    v13 = pvarg;
    v8 = CConfigPolicy::DeletePolicyHelper(this, &v13, &v12);
    v7 = v8;
    if ( v8 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(
        &v14,
        L"DeletePolicy(): Error %lx Couldn't delete Policy from the IAS Server!",
        (unsigned int)v8);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
        gSdoUtilEtwContext,
        xmmword_180078BA0,
        &v14);
    }
  }
  else
  {
    if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gSdoUtilTemplateFunc)(
        gSdoUtilEtwContext,
        xmmword_180078BA0,
        L"DeletePolicy(): The Policy name must not be empty!");
    v7 = -2147024809;
  }
  v9 = VariantClear(&pvarg);
  if ( v9 < 0 )
    _com_issue_error(v9);
  return v7;
}

```

## disassembly

```asm
0x18003abe0  mov     [rsp-8+arg_18], rbx
0x18003abe5  push    rbp
0x18003abe6  push    rsi
0x18003abe7  push    rdi
0x18003abe8  lea     rbp, [rsp-790h]
0x18003abf0  sub     rsp, 890h
0x18003abf7  mov     rax, cs:__security_cookie
0x18003abfe  xor     rax, rsp
0x18003ac01  mov     [rbp+7A0h+var_20], rax
0x18003ac08  mov     rdi, r8
0x18003ac0b  mov     rbx, rdx
0x18003ac0e  mov     rsi, rcx
0x18003ac11  mov     rcx, rdx; psz
0x18003ac14  call    cs:__imp_SysAllocString
0x18003ac1a  test    rax, rax
0x18003ac1d  jnz     short loc_18003AC28
0x18003ac1f  test    rbx, rbx
0x18003ac22  jnz     loc_18003AD59
0x18003ac28  mov     ecx, 8
0x18003ac2d  mov     word ptr [rsp+8A0h+pvarg], cx
0x18003ac32  mov     qword ptr [rsp+8A0h+pvarg+8], rax
0x18003ac37  xor     eax, eax
0x18003ac39  mov     [rbp+7A0h+var_820], eax
0x18003ac3c  xor     edx, edx; Val
0x18003ac3e  mov     r8d, 7FCh; Size
0x18003ac44  lea     rcx, [rbp+7A0h+var_81C]; void *
0x18003ac48  call    memset_0
0x18003ac4d  mov     rcx, rbx; pbstr
0x18003ac50  call    cs:__imp_SysStringLen
0x18003ac56  test    eax, eax
0x18003ac58  jnz     short loc_18003AC92
0x18003ac5a  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, eax; int gIsSdoUtilEtwTracingAvailable
0x18003ac60  jz      short loc_18003AC88
0x18003ac62  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003ac69  test    rdx, rdx
0x18003ac6c  jz      short loc_18003AC88
0x18003ac6e  lea     r8, aDeletepolicyTh; "DeletePolicy(): The Policy name must no"...
0x18003ac75  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003ac7c  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ac83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac88  mov     ebx, 80070057h
0x18003ac8d  jmp     loc_18003AD1E
0x18003ac92  movups  xmm0, xmmword ptr [rdi]
0x18003ac95  movaps  xmmword ptr [rsp+8A0h+var_860], xmm0
0x18003ac9a  movsd   xmm1, qword ptr [rdi+10h]
0x18003ac9f  movsd   qword ptr [rsp+8A0h+var_860+10h], xmm1
0x18003aca5  movups  xmm0, xmmword ptr [rsp+8A0h+pvarg]
0x18003acaa  movaps  xmmword ptr [rsp+8A0h+var_840], xmm0
0x18003acaf  movsd   xmm1, qword ptr [rsp+8A0h+pvarg+10h]
0x18003acb5  movsd   qword ptr [rsp+8A0h+var_840+10h], xmm1
0x18003acbb  lea     r8, [rsp+8A0h+var_860]; struct tagVARIANT
0x18003acc0  lea     rdx, [rsp+8A0h+var_840]; struct tagVARIANT
0x18003acc5  mov     rcx, rsi; this
0x18003acc8  call    ?DeletePolicyHelper@CConfigPolicy@@AEAAJUtagVARIANT@@0@Z; CConfigPolicy::DeletePolicyHelper(tagVARIANT,tagVARIANT)
0x18003accd  mov     ebx, eax
0x18003accf  test    eax, eax
0x18003acd1  jns     short loc_18003AD1E
0x18003acd3  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003acda  jz      short loc_18003AD1E
0x18003acdc  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003ace4  jz      short loc_18003AD1E
0x18003ace6  xor     ecx, ecx
0x18003ace8  mov     word ptr [rbp+7A0h+var_820], cx
0x18003acec  mov     r8d, eax
0x18003acef  lea     rdx, aDeletepolicyEr; "DeletePolicy(): Error %lx Couldn't dele"...
0x18003acf6  lea     rcx, [rbp+7A0h+var_820]
0x18003acfa  call    FormatRRASErrorString
0x18003acff  lea     r8, [rbp+7A0h+var_820]
0x18003ad03  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003ad0a  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003ad11  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ad18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad1d  nop
0x18003ad1e  lea     rcx, [rsp+8A0h+pvarg]; pvarg
0x18003ad23  call    cs:__imp_VariantClear
0x18003ad29  test    eax, eax
0x18003ad2b  js      short loc_18003AD51
0x18003ad2d  mov     eax, ebx
0x18003ad2f  mov     rcx, [rbp+7A0h+var_20]
0x18003ad36  xor     rcx, rsp; StackCookie
0x18003ad39  call    __security_check_cookie
0x18003ad3e  mov     rbx, [rsp+8A0h+arg_18]
0x18003ad46  add     rsp, 890h
0x18003ad4d  pop     rdi
0x18003ad4e  pop     rsi
0x18003ad4f  pop     rbp
0x18003ad50  retn
0x18003ad51  mov     ecx, eax; int
0x18003ad53  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003ad59  mov     ecx, 8007000Eh; int
0x18003ad5e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
