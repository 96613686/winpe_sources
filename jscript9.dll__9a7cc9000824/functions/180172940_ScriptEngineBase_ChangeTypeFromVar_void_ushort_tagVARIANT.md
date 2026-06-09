# ScriptEngineBase::ChangeTypeFromVar(void *,ushort,tagVARIANT *)

- ea: `0x180172940`
- end: `0x180172a65`
- name: `?ChangeTypeFromVar@ScriptEngineBase@@UEAAJPEAXGPEAUtagVARIANT@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(void (__fastcall ***this)(struct Js::ScriptContext *), void *, unsigned __int16, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18003091c`
- `0x1800327fc`
- `0x1800e08d8`
- `0x18010d0b0`
- `0x180172940`
- `0x1802256f0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1801729b1`
- `OLEAUT32!__imp_VariantInit` at `0x1801729b1`
- `OLEAUT32!__imp_VariantClear` at `0x180172a4c`
- `OLEAUT32!__imp_VariantClear` at `0x180172a4c`
- `OLEAUT32!__imp_VariantCopy` at `0x180172a19`
- `OLEAUT32!__imp_VariantCopy` at `0x180172a19`

## pseudocode

```c
__int64 __fastcall ScriptEngineBase::ChangeTypeFromVar(
        void (__fastcall ***this)(struct Js::ScriptContext *),
        void *a2,
        unsigned __int16 a3,
        struct tagVARIANT *a4)
{
  __int64 result; // rax
  struct tagVARIANT *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned __int64 v8; // r10
  int v9; // edi
  HRESULT v10; // eax
  unsigned __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  VARIANTARG pvargSrc; // [rsp+38h] [rbp-20h] BYREF

  if ( !a4 )
    return 2147942487LL;
  v5 = a4;
  v6 = 24;
  do
  {
    LOBYTE(v5->vt) = 0;
    v5 = (struct tagVARIANT *)((char *)v5 + 1);
    --v6;
  }
  while ( v6 );
  v11 = 0;
  memset(&pvargSrc, 0, sizeof(pvargSrc));
  result = ScriptEngineBase::VerifyOnEntry((ScriptEngineBase *)this, 0);
  if ( (int)result >= 0 )
  {
    VariantInit(a4);
    if ( Js::DynamicObject::Is(a2) )
    {
      v9 = ScriptSite::ExternalToPrimitive(v8, v7, &v11, 0);
      if ( v9 < 0 )
        return (unsigned int)v9;
      v8 = v11;
    }
    v9 = DispatchHelper::MarshalJsVarToVariantNoThrow(v8, &pvargSrc, this[1]);
    if ( v9 >= 0 )
    {
      if ( a3 == 12 )
        v10 = VariantCopy(a4, &pvargSrc);
      else
        v10 = ScriptEngine::ChangeType((ScriptEngine *)(this + 24), a4, &pvargSrc, 1033, a3);
      v9 = v10;
      VariantClear(&pvargSrc);
    }
    return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x180172940  mov     rax, rsp
0x180172943  mov     [rax+20h], r9
0x180172947  mov     [rax+18h], r8w
0x18017294c  mov     [rax+10h], rdx
0x180172950  mov     [rax+8], rcx
0x180172954  push    rbp
0x180172955  push    rsi
0x180172956  push    rdi
0x180172957  push    r14
0x180172959  mov     rbp, rsp
0x18017295c  sub     rsp, 58h
0x180172960  cmp     [rbp+pvarg], 0
0x180172965  jnz     short loc_180172971
0x180172967  mov     eax, 80070057h
0x18017296c  jmp     loc_180172A5A
0x180172971  mov     rax, [rbp+pvarg]
0x180172975  mov     ecx, 18h
0x18017297a  mov     byte ptr [rax], 0
0x18017297d  inc     rax
0x180172980  sub     rcx, 1
0x180172984  jnz     short loc_18017297A
0x180172986  mov     r14, [rbp+arg_0]
0x18017298a  xor     eax, eax
0x18017298c  xorps   xmm0, xmm0
0x18017298f  mov     qword ptr [rbp+pvargSrc+10h], rax
0x180172993  mov     rcx, r14; this
0x180172996  mov     [rbp+var_28], rax
0x18017299a  xor     edx, edx; int
0x18017299c  movups  xmmword ptr [rbp+pvargSrc], xmm0
0x1801729a0  call    ?VerifyOnEntry@ScriptEngineBase@@QEAAJH@Z; ScriptEngineBase::VerifyOnEntry(int)
0x1801729a5  test    eax, eax
0x1801729a7  js      loc_180172A5A
0x1801729ad  mov     rcx, [rbp+pvarg]; pvarg
0x1801729b1  call    cs:__imp_VariantInit
0x1801729b8  nop     dword ptr [rax+rax+00h]
0x1801729bd  movzx   esi, [rbp+arg_10]
0x1801729c1  xor     edx, edx
0x1801729c3  mov     r10, [rbp+arg_8]
0x1801729c7  cmp     si, 8
0x1801729cb  mov     rcx, r10; void *
0x1801729ce  setnz   dl
0x1801729d1  inc     edx
0x1801729d3  call    ?Is@DynamicObject@Js@@SA_NPEAX@Z; Js::DynamicObject::Is(void *)
0x1801729d8  test    al, al
0x1801729da  jz      short loc_1801729F5
0x1801729dc  xor     r9d, r9d
0x1801729df  lea     r8, [rbp+var_28]
0x1801729e3  mov     rcx, r10
0x1801729e6  call    ?ExternalToPrimitive@ScriptSite@@SAJPEAVRecyclableObject@Js@@UJavascriptHint@3@PEAPEAXPEAUIServiceProvider@@@Z; ScriptSite::ExternalToPrimitive(Js::RecyclableObject *,Js::JavascriptHint,void * *,IServiceProvider *)
0x1801729eb  mov     edi, eax
0x1801729ed  test    eax, eax
0x1801729ef  js      short loc_180172A58
0x1801729f1  mov     r10, [rbp+var_28]
0x1801729f5  mov     r8, [r14+8]; struct Js::ScriptContext *
0x1801729f9  lea     rdx, [rbp+pvargSrc]; struct tagVARIANT *
0x1801729fd  mov     rcx, r10; void *
0x180172a00  call    ?MarshalJsVarToVariantNoThrow@DispatchHelper@@SAJPEAXPEAUtagVARIANT@@PEAVScriptContext@Js@@@Z; DispatchHelper::MarshalJsVarToVariantNoThrow(void *,tagVARIANT *,Js::ScriptContext *)
0x180172a05  mov     edi, eax
0x180172a07  test    eax, eax
0x180172a09  js      short loc_180172A58
0x180172a0b  cmp     si, 0Ch
0x180172a0f  jnz     short loc_180172A27
0x180172a11  mov     rcx, [rbp+pvarg]; pvargDest
0x180172a15  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x180172a19  call    cs:__imp_VariantCopy
0x180172a20  nop     dword ptr [rax+rax+00h]
0x180172a25  jmp     short loc_180172A46
0x180172a27  mov     rdx, [rbp+pvarg]; struct tagVARIANT *
0x180172a2b  lea     rcx, [r14+0C0h]; this
0x180172a32  mov     r9d, 409h; unsigned int
0x180172a38  mov     [rsp+58h+var_38], si; unsigned __int16
0x180172a3d  lea     r8, [rbp+pvargSrc]; struct tagVARIANT *
0x180172a41  call    ?ChangeType@ScriptEngine@@UEAAJPEAUtagVARIANT@@0KG@Z; ScriptEngine::ChangeType(tagVARIANT *,tagVARIANT *,ulong,ushort)
0x180172a46  lea     rcx, [rbp+pvargSrc]; pvarg
0x180172a4a  mov     edi, eax
0x180172a4c  call    cs:__imp_VariantClear
0x180172a53  nop     dword ptr [rax+rax+00h]
0x180172a58  mov     eax, edi
0x180172a5a  add     rsp, 58h
0x180172a5e  pop     r14
0x180172a60  pop     rdi
0x180172a61  pop     rsi
0x180172a62  pop     rbp
0x180172a63  retn
```
