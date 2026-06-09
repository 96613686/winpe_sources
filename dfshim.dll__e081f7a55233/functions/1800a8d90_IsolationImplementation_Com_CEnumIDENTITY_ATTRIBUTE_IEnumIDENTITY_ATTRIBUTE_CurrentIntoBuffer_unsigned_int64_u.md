# IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE::IEnumIDENTITY_ATTRIBUTE_CurrentIntoBuffer(unsigned __int64,uchar * const,unsigned __int64 *)

- ea: `0x1800a8d90`
- end: `0x1800a8f46`
- name: `?IEnumIDENTITY_ATTRIBUTE_CurrentIntoBuffer@CEnumIDENTITY_ATTRIBUTE@Com@IsolationImplementation@@IEAAJ_KQEAEPEA_K@Z`
- size: `438`
- prototype: `int(IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE *__hidden this, unsigned __int64, unsigned __int8 *const, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800a8d80`

## callees

- `0x180012910`
- `0x180012acc`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800191c8`
- `0x1800a8d90`
- `0x180107718`
- `0x1801078b8`
- `0x18012a030`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8e5a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8ed6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8e5a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a8ed6`

## string_xrefs

- `0x1800a8db0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`
- `0x1800a8e63`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`
- `0x1800a8edf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`
- `0x1800a8f16`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumidentityattribute.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE::IEnumIDENTITY_ATTRIBUTE_CurrentIntoBuffer(
        IsolationImplementation::Com::CEnumIDENTITY_ATTRIBUTE *this,
        const struct Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE *a2,
        unsigned __int8 *const a3,
        unsigned __int64 *a4)
{
  unsigned int v8; // ebx
  int IdentityAttributeEnumeratorData; // eax
  unsigned int v10; // r14d
  int v11; // edx
  Windows::ErrorHandling::COM *v12; // rcx
  IsolationImplementation::Com *v13; // r14
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // r9d
  unsigned __int64 *v19; // [rsp+20h] [rbp-20h] BYREF
  int v20; // [rsp+28h] [rbp-18h]
  unsigned int v21; // [rsp+30h] [rbp-10h]
  __int64 v22; // [rsp+78h] [rbp+38h] BYREF
  IsolationImplementation::Com *v23; // [rsp+88h] [rbp+48h] BYREF

  v21 = -2147023537;
  v19 = (unsigned __int64 *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp";
  v23 = 0;
  v22 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 && a3 )
    memset_thunk_772440563353939046(a3, 0, (size_t)a2);
  if ( !a4 )
  {
    v20 = 120;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v19);
    return v21;
  }
  if ( a2 && !a3 )
  {
    v20 = 121;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v19);
    return v21;
  }
  v8 = 1;
  IdentityAttributeEnumeratorData = RtlFetchIdentityAttributeEnumeratorData(*((_QWORD *)this + 2), 1, &v23, &v22);
  v10 = IdentityAttributeEnumeratorData;
  if ( IdentityAttributeEnumeratorData < 0 )
  {
    if ( IdentityAttributeEnumeratorData == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp",
      (const char *)0x7F,
      v10,
      (unsigned int)v19);
    v12 = (Windows::ErrorHandling::COM *)v10;
    return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(v12, v11);
  }
  if ( !v22 )
    return v8;
  v13 = v23;
  if ( !v23 )
  {
    v20 = 131;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v19,
      &v19);
    return v21;
  }
  v14 = RtlMoveIdentityAttributeEnumeratorPosition(*((_QWORD *)this + 2), -1, 0);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( v14 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp",
      (const char *)0x8B,
      v15,
      (unsigned int)v19);
    v12 = (Windows::ErrorHandling::COM *)v15;
    return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(v12, v11);
  }
  v16 = IsolationImplementation::Com::CopyOut(v13, a2, (unsigned __int64)a3, a4, v19);
  v8 = v16;
  if ( v16 >= 0 )
    return 0;
  else
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumidentityattribute.cpp",
      (const char *)0x91,
      v16,
      v17);
  return v8;
}

```

## disassembly

```asm
0x1800a8d90  mov     [rsp-28h+arg_0], rbx
0x1800a8d95  mov     [rsp-28h+arg_10], rsi
0x1800a8d9a  push    rbp
0x1800a8d9b  push    rdi
0x1800a8d9c  push    r13
0x1800a8d9e  push    r14
0x1800a8da0  push    r15
0x1800a8da2  mov     rbp, rsp
0x1800a8da5  sub     rsp, 40h
0x1800a8da9  mov     [rbp+var_10], 8007054Fh
0x1800a8db0  lea     rax, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8db7  mov     [rbp+var_20], rax
0x1800a8dbb  mov     r15, r9
0x1800a8dbe  mov     [rbp+arg_18], 0
0x1800a8dc6  mov     rdi, r8
0x1800a8dc9  mov     [rbp+arg_8], 0
0x1800a8dd1  mov     rsi, rdx
0x1800a8dd4  mov     r13, rcx
0x1800a8dd7  test    r9, r9
0x1800a8dda  jz      short loc_1800A8DE3
0x1800a8ddc  mov     qword ptr [r9], 0
0x1800a8de3  test    rsi, rsi
0x1800a8de6  jz      short loc_1800A8DFA
0x1800a8de8  test    rdi, rdi
0x1800a8deb  jz      short loc_1800A8DFA
0x1800a8ded  mov     r8, rsi; Size
0x1800a8df0  xor     edx, edx; Val
0x1800a8df2  mov     rcx, rdi; void *
0x1800a8df5  call    memset$thunk$772440563353939046
0x1800a8dfa  test    r15, r15
0x1800a8dfd  jnz     short loc_1800A8E17
0x1800a8dff  lea     rcx, [rbp+var_20]
0x1800a8e03  mov     [rbp+var_18], 78h ; 'x'
0x1800a8e0a  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800a8e0f  mov     ebx, [rbp+var_10]
0x1800a8e12  jmp     loc_1800A8F2B
0x1800a8e17  test    rsi, rsi
0x1800a8e1a  jz      short loc_1800A8E33
0x1800a8e1c  test    rdi, rdi
0x1800a8e1f  jnz     short loc_1800A8E33
0x1800a8e21  mov     [rbp+var_18], 79h ; 'y'
0x1800a8e28  lea     rcx, [rbp+var_20]
0x1800a8e2c  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800a8e31  jmp     short loc_1800A8E0F
0x1800a8e33  mov     rcx, [r13+10h]
0x1800a8e37  lea     r9, [rbp+arg_8]
0x1800a8e3b  mov     ebx, 1
0x1800a8e40  lea     r8, [rbp+arg_18]
0x1800a8e44  mov     edx, ebx
0x1800a8e46  call    RtlFetchIdentityAttributeEnumeratorData
0x1800a8e4b  mov     r14d, eax
0x1800a8e4e  test    eax, eax
0x1800a8e50  jns     short loc_1800A8E8B
0x1800a8e52  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a8e58  jnz     short loc_1800A8E60
0x1800a8e5a  call    cs:__imp_DebugBreak
0x1800a8e60  mov     r9d, r14d; int
0x1800a8e63  lea     rdx, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8e6a  mov     r8d, 7Fh; char *
0x1800a8e70  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a8e77  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a8e7c  mov     ecx, r14d; this
0x1800a8e7f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a8e84  mov     ebx, eax
0x1800a8e86  jmp     loc_1800A8F2B
0x1800a8e8b  cmp     [rbp+arg_8], 0
0x1800a8e90  jz      loc_1800A8F2B
0x1800a8e96  mov     r14, [rbp+arg_18]
0x1800a8e9a  test    r14, r14
0x1800a8e9d  jnz     short loc_1800A8EB8
0x1800a8e9f  mov     [rbp+var_18], 83h
0x1800a8ea6  lea     rdx, [rbp+var_20]
0x1800a8eaa  lea     rcx, [rbp+var_20]
0x1800a8eae  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800a8eb3  jmp     loc_1800A8E0F
0x1800a8eb8  mov     rcx, [r13+10h]
0x1800a8ebc  xor     r8d, r8d
0x1800a8ebf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a8ec3  call    RtlMoveIdentityAttributeEnumeratorPosition
0x1800a8ec8  mov     ebx, eax
0x1800a8eca  test    eax, eax
0x1800a8ecc  jns     short loc_1800A8EFC
0x1800a8ece  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a8ed4  jnz     short loc_1800A8EDC
0x1800a8ed6  call    cs:__imp_DebugBreak
0x1800a8edc  mov     r9d, ebx; int
0x1800a8edf  lea     rdx, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8ee6  mov     r8d, 8Bh; char *
0x1800a8eec  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a8ef3  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a8ef8  mov     ecx, ebx
0x1800a8efa  jmp     short loc_1800A8E7F
0x1800a8efc  mov     r9, r15; void *
0x1800a8eff  mov     r8, rdi; unsigned __int64
0x1800a8f02  mov     rdx, rsi; struct Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE *
0x1800a8f05  mov     rcx, r14; this
0x1800a8f08  call    ?CopyOut@Com@IsolationImplementation@@YAJAEBU_IDENTITY_ATTRIBUTE@Rtl@Isolation@Windows@@_KPEAXAEA_K@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE const &,unsigned __int64,void *,unsigned __int64 &)
0x1800a8f0d  mov     ebx, eax
0x1800a8f0f  test    eax, eax
0x1800a8f11  jns     short loc_1800A8F29
0x1800a8f13  mov     r8d, eax; int
0x1800a8f16  lea     rcx, aOnecoreComNetf_101; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a8f1d  mov     edx, 91h; char *
0x1800a8f22  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a8f27  jmp     short loc_1800A8F2B
0x1800a8f29  xor     ebx, ebx
0x1800a8f2b  lea     r11, [rsp+40h+var_s0]
0x1800a8f30  mov     eax, ebx
0x1800a8f32  mov     rbx, [r11+30h]
0x1800a8f36  mov     rsi, [r11+40h]
0x1800a8f3a  mov     rsp, r11
0x1800a8f3d  pop     r15
0x1800a8f3f  pop     r14
0x1800a8f41  pop     r13
0x1800a8f43  pop     rdi
0x1800a8f44  pop     rbp
0x1800a8f45  retn
```
