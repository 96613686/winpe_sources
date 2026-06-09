# HostDispatch::Create(Js::ScriptContext *,tagVARIANT *,int)

- ea: `0x18013df44`
- end: `0x18013e041`
- name: `?Create@HostDispatch@@SAPEAV1@PEAVScriptContext@Js@@PEAUtagVARIANT@@H@Z`
- size: `253`
- prototype: `struct HostDispatch *__fastcall(struct Js::ScriptContext *, struct tagVARIANT *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18002f560`
- `0x1801b2af4`

## callees

- `0x18002a504`
- `0x18002a660`
- `0x18002cfbc`
- `0x18002d6cc`
- `0x1800e0908`
- `0x18013df44`
- `0x18013e6a0`
- `0x1801b2aa8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18013df9a`
- `OLEAUT32!__imp_VariantInit` at `0x18013df9a`
- `OLEAUT32!__imp_VariantCopy` at `0x18013dfc2`
- `OLEAUT32!__imp_VariantCopy` at `0x18013dfc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct HostDispatch *__fastcall HostDispatch::Create(struct Js::ScriptContext *a1, struct tagVARIANT *a2, int a3)
{
  Recycler *v4; // rbp
  char *v5; // rsi
  HRESULT v6; // ebx
  char *v7; // rax
  _BYTE v9[64]; // [rsp+28h] [rbp-40h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  v4 = (Recycler *)*((_QWORD *)a1 + 285);
  v5 = Recycler::AllocTrackedLeafInlined(v4, 0x28u);
  *(_QWORD *)v5 = &HostVariant::`vftable';
  *((_DWORD *)v5 + 2) = *((_DWORD *)v5 + 2) & 0xFFFFFFE1 | 2;
  VariantInit((VARIANTARG *)(v5 + 16));
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v9, a1, retaddr);
  v6 = VariantCopy((VARIANTARG *)(v5 + 16), a2);
  ThreadContext::DisposeOnLeaveScript(*((ThreadContext **)a1 + 148));
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v9);
  if ( v6 < 0 )
    Js::JavascriptError::ThrowError(a1, v6, 0);
  *((_DWORD *)v5 + 2) = (8 * a3) ^ (*((_DWORD *)v5 + 2) ^ (8 * a3)) & 0xFFFFFFF7;
  v7 = Recycler::AllocFinalized((void (**)(void))v4, (void (*)(void))0x38);
  return HostDispatch::HostDispatch(
           (HostDispatch *)v7,
           (struct HostVariant *)v5,
           *(struct Js::StaticType **)(*(_QWORD *)a1 + 3440LL));
}

```

## disassembly

```asm
0x18013df44  mov     rax, rsp
0x18013df47  mov     [rax+18h], r8d
0x18013df4b  mov     [rax+10h], rdx
0x18013df4f  mov     [rax+8], rcx
0x18013df53  push    rbp
0x18013df54  push    rsi
0x18013df55  push    rdi
0x18013df56  sub     rsp, 50h
0x18013df5a  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18013df62  mov     [rax+20h], rbx
0x18013df66  mov     rdi, rcx
0x18013df69  mov     rbp, [rcx+8E8h]
0x18013df70  mov     edx, 28h ; '('; unsigned __int64
0x18013df75  mov     rcx, rbp; this
0x18013df78  call    ?AllocTrackedLeafInlined@Recycler@@QEAAPEAD_K@Z; Recycler::AllocTrackedLeafInlined(unsigned __int64)
0x18013df7d  mov     rsi, rax
0x18013df80  lea     rax, ??_7HostVariant@@6B@; const HostVariant::`vftable'
0x18013df87  mov     [rsi], rax
0x18013df8a  mov     ecx, [rsi+8]
0x18013df8d  and     ecx, 0FFFFFFE3h
0x18013df90  or      ecx, 2
0x18013df93  mov     [rsi+8], ecx
0x18013df96  lea     rcx, [rsi+10h]; pvarg
0x18013df9a  call    cs:__imp_VariantInit
0x18013dfa1  nop     dword ptr [rax+rax+00h]
0x18013dfa6  mov     r8, [rsp+68h]
0x18013dfab  mov     rdx, rdi
0x18013dfae  lea     rcx, [rsp+68h+var_40]
0x18013dfb3  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x18013dfb8  nop
0x18013dfb9  mov     rdx, [rsp+68h+pvargSrc]; pvargSrc
0x18013dfbe  lea     rcx, [rsi+10h]; pvargDest
0x18013dfc2  call    cs:__imp_VariantCopy
0x18013dfc9  nop     dword ptr [rax+rax+00h]
0x18013dfce  mov     ebx, eax
0x18013dfd0  mov     rcx, [rdi+4A0h]; this
0x18013dfd7  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x18013dfdc  nop
0x18013dfdd  lea     rcx, [rsp+68h+var_40]
0x18013dfe2  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x18013dfe7  test    ebx, ebx
0x18013dfe9  jns     short loc_18013DFF9
0x18013dfeb  xor     r8d, r8d; unsigned __int16 *
0x18013dfee  mov     edx, ebx; int
0x18013dff0  mov     rcx, rdi; struct Js::ScriptContext *
0x18013dff3  call    ?ThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowError(Js::ScriptContext *,long,ushort const *)
0x18013dff9  mov     eax, [rsp+68h+arg_10]
0x18013e000  shl     eax, 3
0x18013e003  mov     edx, eax
0x18013e005  xor     edx, [rsi+8]
0x18013e008  and     edx, 0FFFFFFF7h
0x18013e00b  xor     edx, eax
0x18013e00d  mov     [rsi+8], edx
0x18013e010  mov     edx, 38h ; '8'; unsigned __int64
0x18013e015  mov     rcx, rbp; this
0x18013e018  call    ?AllocFinalized@Recycler@@QEAAPEAD_K@Z; Recycler::AllocFinalized(unsigned __int64)
0x18013e01d  mov     r8, [rdi]
0x18013e020  mov     r8, [r8+0D70h]; struct Js::StaticType *
0x18013e027  mov     rdx, rsi; struct HostVariant *
0x18013e02a  mov     rcx, rax; this
0x18013e02d  mov     rbx, [rsp+68h+arg_18]
0x18013e035  add     rsp, 50h
0x18013e039  pop     rdi
0x18013e03a  pop     rsi
0x18013e03b  pop     rbp
0x18013e03c  jmp     ??0HostDispatch@@IEAA@PEAVHostVariant@@PEAVStaticType@Js@@@Z; HostDispatch::HostDispatch(HostVariant *,Js::StaticType *)
```
