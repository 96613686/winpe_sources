# PpfGenerateFinalPcrValuesForPpfEventLog

- ea: `0x18001b440`
- end: `0x18001b50e`
- name: `PpfGenerateFinalPcrValuesForPpfEventLog`
- size: `206`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800107e8`
- `0x1800141f4`

## callees

- `0x180003270`
- `0x18000c458`
- `0x18000c5cc`
- `0x18000ca1c`
- `0x18000e260`
- `0x1800181fc`
- `0x18001838c`
- `0x18001b440`
- `0x180029908`

## string_xrefs

- `0x18001b4b0`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall PpfGenerateFinalPcrValuesForPpfEventLog(
        __int64 a1,
        unsigned int a2,
        unsigned __int16 a3,
        __int64 a4)
{
  int FinalPcrValues; // eax
  unsigned int v9; // ebx
  int v11[2]; // [rsp+20h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v11,
    (__int64)"PpfGenerateFinalPcrValuesForPpfEventLogActivity");
  *(_QWORD *)v11 = &PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::`vftable';
  PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::StartActivity((PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity *)v11);
  FinalPcrValues = PpfEvtLogGenerateFinalPcrValues(a1, a2, a3, a4);
  if ( FinalPcrValues >= 0 )
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v11);
    v9 = 0;
  }
  else
  {
    v9 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x45A,
           (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
           (const char *)(unsigned int)FinalPcrValues);
  }
  *(_QWORD *)v11 = &PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::`vftable';
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v11);
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v11);
  return v9;
}

```

## disassembly

```asm
0x18001b440  push    rbx
0x18001b442  push    rbp
0x18001b443  push    rsi
0x18001b444  push    rdi
0x18001b445  push    r14
0x18001b447  sub     rsp, 180h
0x18001b44e  mov     rax, cs:__security_cookie
0x18001b455  xor     rax, rsp
0x18001b458  mov     [rsp+1A8h+var_38], rax
0x18001b460  mov     edi, edx
0x18001b462  mov     rbx, rcx
0x18001b465  lea     rdx, aPpfgeneratefin_0; "PpfGenerateFinalPcrValuesForPpfEventLog"...
0x18001b46c  mov     rbp, r9
0x18001b46f  lea     rcx, [rsp+1A8h+var_188]
0x18001b474  movzx   esi, r8w
0x18001b478  call    ??0?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001b47d  lea     r14, ??_7PpfGenerateFinalPcrValuesForPpfEventLogActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::`vftable'
0x18001b484  lea     rcx, [rsp+1A8h+var_188]; this
0x18001b489  mov     qword ptr [rsp+1A8h+var_188], r14; int
0x18001b48e  call    ?StartActivity@PpfGenerateFinalPcrValuesForPpfEventLogActivity@PpfTraceLoggingProvider@@QEAAXXZ; PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::StartActivity(void)
0x18001b493  mov     r9, rbp
0x18001b496  movzx   r8d, si
0x18001b49a  mov     edx, edi
0x18001b49c  mov     rcx, rbx
0x18001b49f  call    PpfEvtLogGenerateFinalPcrValues
0x18001b4a4  test    eax, eax
0x18001b4a6  jns     short loc_18001B4C8
0x18001b4a8  mov     rcx, [rsp+1A8h]; this
0x18001b4b0  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001b4b7  mov     r9d, eax; char *
0x18001b4ba  mov     edx, 45Ah; void *
0x18001b4bf  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001b4c4  mov     ebx, eax
0x18001b4c6  jmp     short loc_18001B4D4
0x18001b4c8  lea     rcx, [rsp+1A8h+var_188]
0x18001b4cd  call    ?Stop@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001b4d2  xor     ebx, ebx
0x18001b4d4  lea     rcx, [rsp+1A8h+var_188]
0x18001b4d9  mov     qword ptr [rsp+1A8h+var_188], r14
0x18001b4de  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001b4e3  lea     rcx, [rsp+1A8h+var_188]
0x18001b4e8  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001b4ed  mov     eax, ebx
0x18001b4ef  mov     rcx, [rsp+1A8h+var_38]
0x18001b4f7  xor     rcx, rsp; StackCookie
0x18001b4fa  call    __security_check_cookie
0x18001b4ff  add     rsp, 180h
0x18001b506  pop     r14
0x18001b508  pop     rdi
0x18001b509  pop     rsi
0x18001b50a  pop     rbp
0x18001b50b  pop     rbx
0x18001b50c  retn
```
