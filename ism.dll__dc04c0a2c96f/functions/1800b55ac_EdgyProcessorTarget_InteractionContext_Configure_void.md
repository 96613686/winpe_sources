# EdgyProcessorTarget::InteractionContext::Configure(void)

- ea: `0x1800b55ac`
- end: `0x1800b56c9`
- name: `?Configure@InteractionContext@EdgyProcessorTarget@@QEAAXXZ`
- size: `285`
- prototype: `void __fastcall(EdgyProcessorTarget::InteractionContext *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1801a8bd8`
- `0x1801a9474`

## callees

- `0x18008dcac`
- `0x1800b55ac`

## import_xrefs

- `NInput!ResetInteractionContext` at `0x1800b55ec`
- `NInput!ResetInteractionContext` at `0x1800b55ec`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1800b569a`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1800b569a`
- `NInput!CreateInteractionContext` at `0x1800b55c8`
- `NInput!CreateInteractionContext` at `0x1800b55c8`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1800b5669`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1800b5669`
- `NInput!SetPropertyInteractionContext` at `0x1800b560a`
- `NInput!SetPropertyInteractionContext` at `0x1800b5638`
- `NInput!SetPropertyInteractionContext` at `0x1800b560a`
- `NInput!SetPropertyInteractionContext` at `0x1800b5638`

## pseudocode

```c
void __fastcall EdgyProcessorTarget::InteractionContext::Configure(EdgyProcessorTarget::InteractionContext *this)
{
  _QWORD *v1; // rbx
  int InteractionContext; // eax
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9[4]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    ResetInteractionContext();
  }
  else
  {
    InteractionContext = CreateInteractionContext(v1);
    if ( InteractionContext < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x366,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\edgylegacy\\processor\\edgytarget.cpp",
        (const char *)(unsigned int)InteractionContext,
        v9[0]);
  }
  v4 = *v1;
  *(__m128i *)v9 = _mm_load_si128((const __m128i *)&_xmm);
  v5 = SetPropertyInteractionContext(v4, 3);
  if ( v5 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x372,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\edgylegacy\\processor\\edgytarget.cpp",
      (const char *)(unsigned int)v5,
      v9[0]);
  v6 = SetPropertyInteractionContext(*v1, 2);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x373,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\edgylegacy\\processor\\edgytarget.cpp",
      (const char *)(unsigned int)v6,
      v9[0]);
  v7 = SetInteractionConfigurationInteractionContext(*v1, 2, v9);
  if ( v7 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x374,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\edgylegacy\\processor\\edgytarget.cpp",
      (const char *)(unsigned int)v7,
      v9[0]);
  v8 = RegisterOutputCallbackInteractionContext(*v1, EdgyProcessorTarget::InteractionContext::StaticCallback, this);
  if ( v8 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x375,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\edgylegacy\\processor\\edgytarget.cpp",
      (const char *)(unsigned int)v8,
      v9[0]);
}

```

## disassembly

```asm
0x1800b55ac  mov     [rsp+arg_0], rbx
0x1800b55b1  push    rdi
0x1800b55b2  sub     rsp, 30h
0x1800b55b6  lea     rbx, [rcx+8]
0x1800b55ba  mov     rdi, rcx
0x1800b55bd  mov     rcx, [rbx]
0x1800b55c0  test    rcx, rcx
0x1800b55c3  jnz     short loc_1800B55EC
0x1800b55c5  mov     rcx, rbx
0x1800b55c8  call    cs:__imp_CreateInteractionContext
0x1800b55ce  test    eax, eax
0x1800b55d0  jns     short loc_1800B55F2
0x1800b55d2  mov     rcx, [rsp+38h]; this
0x1800b55d7  lea     r8, aOnecoreuapWind_230; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b55de  mov     r9d, eax; char *
0x1800b55e1  mov     edx, 366h; void *
0x1800b55e6  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b55ec  call    cs:__imp_ResetInteractionContext
0x1800b55f2  movdqa  xmm0, cs:__xmm@00000001000000040000000100000005
0x1800b55fa  xor     r8d, r8d
0x1800b55fd  mov     rcx, [rbx]
0x1800b5600  movdqu  xmmword ptr [rsp+38h+var_18], xmm0; int
0x1800b5606  lea     edx, [r8+3]
0x1800b560a  call    cs:__imp_SetPropertyInteractionContext
0x1800b5610  test    eax, eax
0x1800b5612  jns     short loc_1800B562E
0x1800b5614  mov     rcx, [rsp+38h]; this
0x1800b5619  lea     r8, aOnecoreuapWind_230; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b5620  mov     r9d, eax; char *
0x1800b5623  mov     edx, 372h; void *
0x1800b5628  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b562e  mov     rcx, [rbx]
0x1800b5631  xor     r8d, r8d
0x1800b5634  lea     edx, [r8+2]
0x1800b5638  call    cs:__imp_SetPropertyInteractionContext
0x1800b563e  test    eax, eax
0x1800b5640  jns     short loc_1800B565C
0x1800b5642  mov     rcx, [rsp+38h]; this
0x1800b5647  lea     r8, aOnecoreuapWind_230; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b564e  mov     r9d, eax; char *
0x1800b5651  mov     edx, 373h; void *
0x1800b5656  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b565c  mov     rcx, [rbx]
0x1800b565f  lea     r8, [rsp+38h+var_18]
0x1800b5664  mov     edx, 2
0x1800b5669  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x1800b566f  test    eax, eax
0x1800b5671  jns     short loc_1800B568D
0x1800b5673  mov     rcx, [rsp+38h]; this
0x1800b5678  lea     r8, aOnecoreuapWind_230; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b567f  mov     r9d, eax; char *
0x1800b5682  mov     edx, 374h; void *
0x1800b5687  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b568d  mov     rcx, [rbx]
0x1800b5690  lea     rdx, ?StaticCallback@InteractionContext@EdgyProcessorTarget@@CAXPEAXPEBUINTERACTION_CONTEXT_OUTPUT@@@Z; EdgyProcessorTarget::InteractionContext::StaticCallback(void *,INTERACTION_CONTEXT_OUTPUT const *)
0x1800b5697  mov     r8, rdi
0x1800b569a  call    cs:__imp_RegisterOutputCallbackInteractionContext
0x1800b56a0  test    eax, eax
0x1800b56a2  jns     short loc_1800B56BE
0x1800b56a4  mov     rcx, [rsp+38h]; this
0x1800b56a9  lea     r8, aOnecoreuapWind_230; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b56b0  mov     r9d, eax; char *
0x1800b56b3  mov     edx, 375h; void *
0x1800b56b8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b56be  mov     rbx, [rsp+38h+arg_0]
0x1800b56c3  add     rsp, 30h
0x1800b56c7  pop     rdi
0x1800b56c8  retn
```
