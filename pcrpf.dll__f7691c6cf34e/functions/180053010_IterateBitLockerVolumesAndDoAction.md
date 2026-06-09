# IterateBitLockerVolumesAndDoAction

- ea: `0x180053010`
- end: `0x18005322e`
- name: `IterateBitLockerVolumesAndDoAction`
- size: `542`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180052134`
- `0x180053280`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x18000b59c`
- `0x180013e6c`
- `0x18002d5ec`
- `0x180053010`
- `0x180059010`

## import_xrefs

- `FVEAPI!FveOpenVolumeByHandle` at `0x1800530aa`
- `FVEAPI!FveOpenVolumeByHandle` at `0x1800530aa`
- `FVEAPI!FveGetVolumeNameW` at `0x18005310f`
- `FVEAPI!FveGetVolumeNameW` at `0x18005310f`
- `FVEAPI!FveCloseHandle` at `0x1800531dc`
- `FVEAPI!FveCloseHandle` at `0x1800531dc`
- `FVEAPI!FveFindNextVolume` at `0x1800531be`
- `FVEAPI!FveFindNextVolume` at `0x1800531be`
- `FVEAPI!FveFindFirstVolume` at `0x18005306a`
- `FVEAPI!FveFindFirstVolume` at `0x18005306a`
- `FVEAPI!FveCloseVolume` at `0x1800531a8`
- `FVEAPI!FveCloseVolume` at `0x1800531a8`

## string_xrefs

- `0x1800530d0`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180053138`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180053188`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x1800530c1`: `Failed FveOpenVolumeByHandle, continuing`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IterateBitLockerVolumesAndDoAction(unsigned __int8 a1, __int64 a2)
{
  unsigned int v3; // esi
  int v4; // ebx
  unsigned int v5; // r14d
  int v6; // eax
  __int64 v7; // rcx
  int v8; // esi
  __int64 v9; // rcx
  int v11[2]; // [rsp+20h] [rbp-E0h]
  char *v12; // [rsp+28h] [rbp-D8h]
  char v13[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[528]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v3 = a1;
  v17[1] = a2;
  v4 = 0;
  v16[0] = 1;
  v16[1] = -1;
  v14 = 0;
  if ( (int)FveFindFirstVolume(&v14, v16) >= 0 )
  {
    v5 = v3;
    do
    {
      *(_QWORD *)v13 = 0;
      v11[0] = 0;
      v6 = FveOpenVolumeByHandle(v14, 0, v5, 0xFFFFFFFFLL, *(_QWORD *)v11, v13);
      if ( v6 >= 0 )
      {
        memset_0(v18, 0, 0x208u);
        v15 = 260;
        FveGetVolumeNameW(*(_QWORD *)v13, &v15, v18);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
          0x39u,
          "IterateBitLockerVolumesAndDoAction",
          "Iterating BitLocker volume: '%ws'",
          v18);
        v17[0] = *(_QWORD *)v13;
        v7 = *(_QWORD *)(a2 + 112);
        if ( !v7 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 32LL))(v7, v17);
        if ( v8 < 0 )
        {
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x3E,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
            (const char *)(unsigned int)v8,
            (int)"Failed ActionPerVolume, continuing",
            v12);
          if ( v4 >= 0 )
            v4 = v8;
        }
      }
      else
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x31,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
          (const char *)(unsigned int)v6,
          (int)"Failed FveOpenVolumeByHandle, continuing",
          v12);
      }
      if ( *(_QWORD *)v13 )
        FveCloseVolume();
    }
    while ( (int)FveFindNextVolume(v14, v16) >= 0 );
  }
  if ( v14 )
    FveCloseHandle();
  v9 = *(_QWORD *)(a2 + 112);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180053010  mov     [rsp-8+arg_0], rbx
0x180053015  mov     [rsp-8+arg_10], rsi
0x18005301a  push    rbp
0x18005301b  push    rdi
0x18005301c  push    r14
0x18005301e  lea     rbp, [rsp-180h]
0x180053026  sub     rsp, 280h
0x18005302d  mov     rax, cs:__security_cookie
0x180053034  xor     rax, rsp
0x180053037  mov     [rbp+190h+var_20], rax
0x18005303e  mov     rdi, rdx
0x180053041  movzx   esi, cl
0x180053044  mov     [rsp+290h+var_238], rdx
0x180053049  xor     ebx, ebx
0x18005304b  mov     [rsp+290h+var_248], 1
0x180053053  mov     [rsp+290h+var_244], 0FFFFFFFFh
0x18005305b  mov     [rsp+290h+var_258], rbx
0x180053060  lea     rdx, [rsp+290h+var_248]
0x180053065  lea     rcx, [rsp+290h+var_258]
0x18005306a  call    cs:__imp_FveFindFirstVolume
0x180053071  nop     dword ptr [rax+rax+00h]
0x180053076  test    eax, eax
0x180053078  js      loc_1800531D2
0x18005307e  mov     r14d, esi
0x180053081  mov     qword ptr [rsp+290h+var_260], 0
0x18005308a  lea     rax, [rsp+290h+var_260]
0x18005308f  mov     [rsp+290h+var_268], rax; char *
0x180053094  mov     [rsp+290h+var_270], 0
0x18005309c  or      r9d, 0FFFFFFFFh
0x1800530a0  mov     r8d, r14d
0x1800530a3  xor     edx, edx
0x1800530a5  mov     rcx, [rsp+290h+var_258]
0x1800530aa  call    cs:__imp_FveOpenVolumeByHandle
0x1800530b1  nop     dword ptr [rax+rax+00h]
0x1800530b6  test    eax, eax
0x1800530b8  jns     short loc_1800530E6
0x1800530ba  mov     rcx, [rbp+198h]; this
0x1800530c1  lea     rdx, aFailedFveopenv; "Failed FveOpenVolumeByHandle, continuin"...
0x1800530c8  mov     qword ptr [rsp+290h+var_270], rdx; int
0x1800530cd  mov     r9d, eax; char *
0x1800530d0  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800530d7  mov     edx, 31h ; '1'; void *
0x1800530dc  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800530e1  jmp     loc_18005319E
0x1800530e6  xor     edx, edx; Val
0x1800530e8  mov     r8d, 208h; Size
0x1800530ee  lea     rcx, [rsp+290h+var_230]; void *
0x1800530f3  call    memset_0
0x1800530f8  mov     [rsp+290h+var_250], 104h
0x180053100  lea     r8, [rsp+290h+var_230]
0x180053105  lea     rdx, [rsp+290h+var_250]
0x18005310a  mov     rcx, qword ptr [rsp+290h+var_260]
0x18005310f  call    cs:__imp_FveGetVolumeNameW
0x180053116  nop     dword ptr [rax+rax+00h]
0x18005311b  lea     rax, [rsp+290h+var_230]
0x180053120  mov     qword ptr [rsp+290h+var_270], rax
0x180053125  lea     r9, aIteratingBitlo; "Iterating BitLocker volume: '%ws'"
0x18005312c  lea     r8, aIteratebitlock; "IterateBitLockerVolumesAndDoAction"
0x180053133  mov     edx, 39h ; '9'; unsigned int
0x180053138  lea     rcx, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005313f  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180053144  mov     rax, qword ptr [rsp+290h+var_260]
0x180053149  mov     [rsp+290h+var_240], rax
0x18005314e  mov     rcx, [rdi+70h]; this
0x180053152  test    rcx, rcx
0x180053155  jz      loc_180053228
0x18005315b  mov     rax, [rcx]
0x18005315e  lea     rdx, [rsp+290h+var_240]
0x180053163  mov     rax, [rax+20h]
0x180053167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005316c  mov     esi, eax
0x18005316e  test    eax, eax
0x180053170  jns     short loc_18005319E
0x180053172  mov     rcx, [rbp+198h]; this
0x180053179  lea     rax, aFailedActionpe; "Failed ActionPerVolume, continuing"
0x180053180  mov     qword ptr [rsp+290h+var_270], rax; int
0x180053185  mov     r9d, esi; char *
0x180053188  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005318f  mov     edx, 3Eh ; '>'; void *
0x180053194  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053199  test    ebx, ebx
0x18005319b  cmovns  ebx, esi
0x18005319e  mov     rcx, qword ptr [rsp+290h+var_260]
0x1800531a3  test    rcx, rcx
0x1800531a6  jz      short loc_1800531B4
0x1800531a8  call    cs:__imp_FveCloseVolume
0x1800531af  nop     dword ptr [rax+rax+00h]
0x1800531b4  lea     rdx, [rsp+290h+var_248]
0x1800531b9  mov     rcx, [rsp+290h+var_258]
0x1800531be  call    cs:__imp_FveFindNextVolume
0x1800531c5  nop     dword ptr [rax+rax+00h]
0x1800531ca  test    eax, eax
0x1800531cc  jns     loc_180053081
0x1800531d2  mov     rcx, [rsp+290h+var_258]
0x1800531d7  test    rcx, rcx
0x1800531da  jz      short loc_1800531E9
0x1800531dc  call    cs:__imp_FveCloseHandle
0x1800531e3  nop     dword ptr [rax+rax+00h]
0x1800531e8  nop
0x1800531e9  mov     rcx, [rdi+70h]
0x1800531ed  test    rcx, rcx
0x1800531f0  jz      short loc_1800531FE
0x1800531f2  mov     rdx, [rcx]
0x1800531f5  mov     rax, [rdx+18h]
0x1800531f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531fe  mov     eax, ebx
0x180053200  mov     rcx, [rbp+190h+var_20]
0x180053207  xor     rcx, rsp; StackCookie
0x18005320a  call    __security_check_cookie
0x18005320f  lea     r11, [rsp+290h+var_10]
0x180053217  mov     rbx, [r11+20h]
0x18005321b  mov     rsi, [r11+30h]
0x18005321f  mov     rsp, r11
0x180053222  pop     r14
0x180053224  pop     rdi
0x180053225  pop     rbp
0x180053226  retn
0x180053228  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
