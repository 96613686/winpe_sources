# GestureTracker::ResetAndInitializeInteractionContext(void)

- ea: `0x1800e87a8`
- end: `0x1800e88ce`
- name: `?ResetAndInitializeInteractionContext@GestureTracker@@AEAAJXZ`
- size: `294`
- prototype: `int(GestureTracker *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007b734`
- `0x1800e86a0`

## callees

- `0x18008dcac`
- `0x1800e87a8`

## import_xrefs

- `NInput!ResetInteractionContext` at `0x1800e87be`
- `NInput!ResetInteractionContext` at `0x1800e87be`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1800e88a2`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1800e88a2`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1800e8870`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1800e8870`
- `NInput!SetPropertyInteractionContext` at `0x1800e87e0`
- `NInput!SetPropertyInteractionContext` at `0x1800e880f`
- `NInput!SetPropertyInteractionContext` at `0x1800e883e`
- `NInput!SetPropertyInteractionContext` at `0x1800e87e0`
- `NInput!SetPropertyInteractionContext` at `0x1800e880f`
- `NInput!SetPropertyInteractionContext` at `0x1800e883e`

## string_xrefs

- `0x1800e87ef`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\gesturetracker.cpp`
- `0x1800e881e`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\gesturetracker.cpp`
- `0x1800e884d`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\gesturetracker.cpp`
- `0x1800e887f`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\gesturetracker.cpp`
- `0x1800e88b1`: `onecoreuap\windows\moderncore\inputv2\contextualprocessors\components\inputgestures\system\gesturetracker.cpp`

## pseudocode

```c
__int64 __fastcall GestureTracker::ResetAndInitializeInteractionContext(GestureTracker *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v11; // [rsp+30h] [rbp+8h] BYREF
  int v12; // [rsp+34h] [rbp+Ch]

  if ( *((_QWORD *)this + 4) )
  {
    ResetInteractionContext();
    v2 = *((_QWORD *)this + 4);
    v11 = 1;
    v12 = 2055;
    v3 = SetPropertyInteractionContext(v2, 1);
    if ( v3 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\system\\"
                      "gesturetracker.cpp",
        (const char *)(unsigned int)v3,
        v9);
    v4 = SetPropertyInteractionContext(*((_QWORD *)this + 4), 3);
    if ( v4 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\system\\"
                      "gesturetracker.cpp",
        (const char *)(unsigned int)v4,
        v9);
    v5 = SetPropertyInteractionContext(*((_QWORD *)this + 4), 2);
    if ( v5 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\system\\"
                      "gesturetracker.cpp",
        (const char *)(unsigned int)v5,
        v9);
    v6 = SetInteractionConfigurationInteractionContext(*((_QWORD *)this + 4), 1, &v11);
    if ( v6 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\system\\"
                      "gesturetracker.cpp",
        (const char *)(unsigned int)v6,
        v9);
    v7 = RegisterOutputCallbackInteractionContext(
           *((_QWORD *)this + 4),
           GestureTracker::s_InteractionOutputCallback,
           this);
    if ( v7 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\components\\inputgestures\\system\\"
                      "gesturetracker.cpp",
        (const char *)(unsigned int)v7,
        v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800e87a8  push    rbx; int
0x1800e87aa  sub     rsp, 20h
0x1800e87ae  mov     rbx, rcx
0x1800e87b1  mov     rcx, [rcx+20h]
0x1800e87b5  test    rcx, rcx
0x1800e87b8  jz      loc_1800E88C6
0x1800e87be  call    cs:__imp_ResetInteractionContext
0x1800e87c4  mov     rcx, [rbx+20h]
0x1800e87c8  mov     edx, 1
0x1800e87cd  mov     r8d, edx
0x1800e87d0  mov     [rsp+28h+arg_0], 1
0x1800e87d8  mov     [rsp+28h+arg_4], 807h
0x1800e87e0  call    cs:__imp_SetPropertyInteractionContext
0x1800e87e6  test    eax, eax
0x1800e87e8  jns     short loc_1800E8804
0x1800e87ea  mov     rcx, [rsp+28h]; this
0x1800e87ef  lea     r8, aOnecoreuapWind_101; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e87f6  mov     r9d, eax; char *
0x1800e87f9  mov     edx, 2Fh ; '/'; void *
0x1800e87fe  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800e8804  mov     rcx, [rbx+20h]
0x1800e8808  xor     r8d, r8d
0x1800e880b  lea     edx, [r8+3]
0x1800e880f  call    cs:__imp_SetPropertyInteractionContext
0x1800e8815  test    eax, eax
0x1800e8817  jns     short loc_1800E8833
0x1800e8819  mov     rcx, [rsp+28h]; this
0x1800e881e  lea     r8, aOnecoreuapWind_101; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e8825  mov     r9d, eax; char *
0x1800e8828  mov     edx, 30h ; '0'; void *
0x1800e882d  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800e8833  mov     rcx, [rbx+20h]
0x1800e8837  xor     r8d, r8d
0x1800e883a  lea     edx, [r8+2]
0x1800e883e  call    cs:__imp_SetPropertyInteractionContext
0x1800e8844  test    eax, eax
0x1800e8846  jns     short loc_1800E8862
0x1800e8848  mov     rcx, [rsp+28h]; this
0x1800e884d  lea     r8, aOnecoreuapWind_101; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e8854  mov     r9d, eax; char *
0x1800e8857  mov     edx, 31h ; '1'; void *
0x1800e885c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800e8862  mov     rcx, [rbx+20h]
0x1800e8866  lea     r8, [rsp+28h+arg_0]
0x1800e886b  mov     edx, 1
0x1800e8870  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x1800e8876  test    eax, eax
0x1800e8878  jns     short loc_1800E8894
0x1800e887a  mov     rcx, [rsp+28h]; this
0x1800e887f  lea     r8, aOnecoreuapWind_101; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e8886  mov     r9d, eax; char *
0x1800e8889  mov     edx, 32h ; '2'; void *
0x1800e888e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800e8894  mov     rcx, [rbx+20h]
0x1800e8898  lea     rdx, ?s_InteractionOutputCallback@GestureTracker@@CAXPEAXPEBUINTERACTION_CONTEXT_OUTPUT@@@Z; GestureTracker::s_InteractionOutputCallback(void *,INTERACTION_CONTEXT_OUTPUT const *)
0x1800e889f  mov     r8, rbx
0x1800e88a2  call    cs:__imp_RegisterOutputCallbackInteractionContext
0x1800e88a8  test    eax, eax
0x1800e88aa  jns     short loc_1800E88C6
0x1800e88ac  mov     rcx, [rsp+28h]; this
0x1800e88b1  lea     r8, aOnecoreuapWind_101; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e88b8  mov     r9d, eax; char *
0x1800e88bb  mov     edx, 33h ; '3'; void *
0x1800e88c0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800e88c6  xor     eax, eax
0x1800e88c8  add     rsp, 20h
0x1800e88cc  pop     rbx
0x1800e88cd  retn
```
