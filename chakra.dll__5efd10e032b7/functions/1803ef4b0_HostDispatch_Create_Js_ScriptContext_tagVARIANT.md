# HostDispatch::Create(Js::ScriptContext *,tagVARIANT *)

- ea: `0x1803ef4b0`
- end: `0x1803ef567`
- name: `?Create@HostDispatch@@SAPEAV1@PEAVScriptContext@Js@@PEAUtagVARIANT@@@Z`
- size: `183`
- prototype: `struct HostDispatch *__fastcall(struct Js::ScriptContext *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18008cd34`

## callees

- `0x18008da24`
- `0x18008dd00`
- `0x1800afef0`
- `0x1803e9c50`
- `0x1803ef4b0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1803ef4fa`
- `OLEAUT32!__imp_VariantInit` at `0x1803ef4fa`
- `OLEAUT32!__imp_VariantCopy` at `0x1803ef50f`
- `OLEAUT32!__imp_VariantCopy` at `0x1803ef50f`

## pseudocode

```c
struct HostDispatch *__fastcall HostDispatch::Create(struct Js::ScriptContext *a1, struct tagVARIANT *a2)
{
  Memory::Recycler *v2; // rbp
  char *v4; // rsi
  char v5; // dl
  HRESULT v6; // eax
  __int64 v7; // rbx
  HostDispatch *v8; // rax

  v2 = (Memory::Recycler *)*((_QWORD *)a1 + 126);
  v4 = Memory::Recycler::AllocTrackedLeafInlined(v2, 0x28u);
  v5 = v4[8] & 0xFB;
  *(_QWORD *)v4 = &HostVariant::`vftable';
  v4[8] = v5 | 2;
  VariantInit((VARIANTARG *)(v4 + 16));
  v6 = VariantCopy((VARIANTARG *)(v4 + 16), a2);
  if ( v6 < 0 )
    Js::JavascriptError::ThrowError(a1, v6, 0);
  v7 = *(_QWORD *)(*((_QWORD *)a1 + 183) + 16LL);
  v8 = (HostDispatch *)Memory::Recycler::AllocFinalizedInlined(v2, 0x40u);
  return HostDispatch::HostDispatch(
           v8,
           (struct HostVariant *)v4,
           *(struct Js::StaticType **)(*(_QWORD *)(v7 + 176) + 32LL));
}

```

## disassembly

```asm
0x1803ef4b0  mov     rax, rsp
0x1803ef4b3  mov     [rax+18h], rbx
0x1803ef4b7  mov     [rax+10h], rdx
0x1803ef4bb  mov     [rax+8], rcx
0x1803ef4bf  push    rbp
0x1803ef4c0  push    rsi
0x1803ef4c1  push    rdi
0x1803ef4c2  sub     rsp, 20h
0x1803ef4c6  mov     rbp, [rcx+3F0h]
0x1803ef4cd  mov     rdi, rcx
0x1803ef4d0  mov     rcx, rbp; this
0x1803ef4d3  mov     edx, 28h ; '('; unsigned __int64
0x1803ef4d8  call    ?AllocTrackedLeafInlined@Recycler@Memory@@QEAAPEAD_K@Z; Memory::Recycler::AllocTrackedLeafInlined(unsigned __int64)
0x1803ef4dd  mov     rsi, rax
0x1803ef4e0  lea     rax, ??_7HostVariant@@6B@; const HostVariant::`vftable'
0x1803ef4e7  mov     dl, [rsi+8]
0x1803ef4ea  lea     rcx, [rsi+10h]; pvarg
0x1803ef4ee  and     dl, 0FBh
0x1803ef4f1  mov     [rsi], rax
0x1803ef4f4  or      dl, 2
0x1803ef4f7  mov     [rsi+8], dl
0x1803ef4fa  call    cs:__imp_VariantInit
0x1803ef501  nop     dword ptr [rax+rax+00h]
0x1803ef506  mov     rdx, [rsp+38h+pvargSrc]; pvargSrc
0x1803ef50b  lea     rcx, [rsi+10h]; pvargDest
0x1803ef50f  call    cs:__imp_VariantCopy
0x1803ef516  nop     dword ptr [rax+rax+00h]
0x1803ef51b  test    eax, eax
0x1803ef51d  jns     short loc_1803EF52D
0x1803ef51f  xor     r8d, r8d; unsigned __int16 *
0x1803ef522  mov     edx, eax; int
0x1803ef524  mov     rcx, rdi; struct Js::ScriptContext *
0x1803ef527  call    ?ThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@HPEBG@Z; Js::JavascriptError::ThrowError(Js::ScriptContext *,int,ushort const *)
0x1803ef52d  mov     rax, [rdi+5B8h]
0x1803ef534  mov     edx, 40h ; '@'; unsigned __int64
0x1803ef539  mov     rcx, rbp; this
0x1803ef53c  mov     rbx, [rax+10h]
0x1803ef540  call    ?AllocFinalizedInlined@Recycler@Memory@@QEAAPEAD_K@Z; Memory::Recycler::AllocFinalizedInlined(unsigned __int64)
0x1803ef545  mov     r8, [rbx+0B0h]
0x1803ef54c  mov     rdx, rsi; struct HostVariant *
0x1803ef54f  mov     rcx, rax; this
0x1803ef552  mov     r8, [r8+20h]; struct Js::StaticType *
0x1803ef556  mov     rbx, [rsp+38h+arg_10]
0x1803ef55b  add     rsp, 20h
0x1803ef55f  pop     rdi
0x1803ef560  pop     rsi
0x1803ef561  pop     rbp
0x1803ef562  jmp     ??0HostDispatch@@IEAA@PEAVHostVariant@@PEAVStaticType@Js@@@Z; HostDispatch::HostDispatch(HostVariant *,Js::StaticType *)
```
