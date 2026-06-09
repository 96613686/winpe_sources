# wistd::__function::__func__lambda_5c32a6839927328f89079234e915d5c1__long___cdecl(void__)_::operator()

- ea: `0x180051ee0`
- end: `0x18005201d`
- name: `wistd::__function::__func__lambda_5c32a6839927328f89079234e915d5c1__long___cdecl(void__)_::operator()`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180009c64`
- `0x180051ee0`
- `0x180052ea4`
- `0x180053234`
- `0x180053898`

## import_xrefs

- `FVEAPI!FveOpenVolumeByHandle` at `0x180051f60`
- `FVEAPI!FveOpenVolumeByHandle` at `0x180051f60`
- `FVEAPI!FveCloseVolume` at `0x180051f94`
- `FVEAPI!FveCloseVolume` at `0x180051ffe`
- `FVEAPI!FveCloseVolume` at `0x180051f94`
- `FVEAPI!FveCloseVolume` at `0x180051ffe`

## string_xrefs

- `0x180051f1f`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180051f77`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180051fc1`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wistd::__function::__func__lambda_5c32a6839927328f89079234e915d5c1__long___cdecl_void____::operator()(
        __int64 a1,
        __int64 *a2)
{
  __int64 v3; // rbx
  unsigned int v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // eax
  int v10[2]; // [rsp+20h] [rbp-10h]
  char *v11; // [rsp+28h] [rbp-8h]
  char *v12; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  char v14; // [rsp+50h] [rbp+20h] BYREF
  __int64 v15; // [rsp+58h] [rbp+28h] BYREF

  v3 = *a2;
  v14 = 0;
  v4 = IsTpmProtectedVolumeWithPcrs(v3, **(unsigned int **)(a1 + 8), &v14);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x12F,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
    (const char *)v4,
    (int)"IsTpmProtectedVolumeWithPcrs",
    v11);
  if ( !v14 )
    return 0;
  v15 = 0;
  v10[0] = 0;
  v5 = FveOpenVolumeByHandle(v3, 0, 1, 0xFFFFFFFFLL, *(_QWORD *)v10, &v15);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 308;
    goto LABEL_4;
  }
  v8 = IsTpmProtectedVolumeWithPcrs(v15, **(unsigned int **)(a1 + 8), &v14);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x137,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
    (const char *)v8,
    (int)"IsTpmProtectedVolumeWithPcrs",
    v12);
  if ( !v14 || (**(_BYTE **)(a1 + 16) = 1, v5 = ResealBitLockerVolume(v15), v6 = v5, v5 >= 0) )
  {
    if ( v15 )
      FveCloseVolume();
    return 0;
  }
  v7 = 315;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
    (const char *)(unsigned int)v5);
  if ( v15 )
    FveCloseVolume();
  return v6;
}

```

## disassembly

```asm
0x180051ee0  mov     [rsp-18h+arg_10], rbx
0x180051ee5  push    rbp
0x180051ee6  push    rdi
0x180051ee7  push    r15
0x180051ee9  mov     rbp, rsp
0x180051eec  sub     rsp, 30h
0x180051ef0  mov     rdi, rcx
0x180051ef3  mov     rbx, [rdx]
0x180051ef6  mov     [rbp+arg_0], 0
0x180051efa  mov     rdx, [rcx+8]
0x180051efe  lea     r8, [rbp+arg_0]
0x180051f02  mov     edx, [rdx]
0x180051f04  mov     rcx, rbx
0x180051f07  call    IsTpmProtectedVolumeWithPcrs
0x180051f0c  mov     rcx, [rbp+18h]; this
0x180051f10  lea     r15, aIstpmprotected; "IsTpmProtectedVolumeWithPcrs"
0x180051f17  mov     qword ptr [rsp+30h+var_10], r15; int
0x180051f1c  mov     r9d, eax; char *
0x180051f1f  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051f26  mov     edx, 12Fh; void *
0x180051f2b  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180051f30  cmp     [rbp+arg_0], 0
0x180051f34  jz      loc_18005200A
0x180051f3a  mov     [rbp+arg_8], 0
0x180051f42  lea     rax, [rbp+arg_8]
0x180051f46  mov     [rsp+30h+var_8], rax; char *
0x180051f4b  mov     [rsp+30h+var_10], 0; int
0x180051f53  or      r9d, 0FFFFFFFFh
0x180051f57  xor     edx, edx
0x180051f59  lea     r8d, [r9+2]
0x180051f5d  mov     rcx, rbx
0x180051f60  call    cs:__imp_FveOpenVolumeByHandle
0x180051f67  nop     dword ptr [rax+rax+00h]
0x180051f6c  mov     ebx, eax
0x180051f6e  test    eax, eax
0x180051f70  jns     short loc_180051FA2
0x180051f72  mov     edx, 134h; void *
0x180051f77  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051f7e  mov     r9d, eax; char *
0x180051f81  mov     rcx, [rbp+18h]; this
0x180051f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051f8a  nop
0x180051f8b  mov     rcx, [rbp+arg_8]
0x180051f8f  test    rcx, rcx
0x180051f92  jz      short loc_18005200C
0x180051f94  call    cs:__imp_FveCloseVolume
0x180051f9b  nop     dword ptr [rax+rax+00h]
0x180051fa0  jmp     short loc_18005200C
0x180051fa2  mov     rdx, [rdi+8]
0x180051fa6  lea     r8, [rbp+arg_0]
0x180051faa  mov     edx, [rdx]
0x180051fac  mov     rcx, [rbp+arg_8]
0x180051fb0  call    IsTpmProtectedVolumeWithPcrs
0x180051fb5  mov     rcx, [rbp+18h]; this
0x180051fb9  mov     qword ptr [rsp+30h+var_10], r15; int
0x180051fbe  mov     r9d, eax; char *
0x180051fc1  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180051fc8  mov     edx, 137h; void *
0x180051fcd  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180051fd2  cmp     [rbp+arg_0], 0
0x180051fd6  jz      short loc_180051FF5
0x180051fd8  mov     rax, [rdi+10h]
0x180051fdc  mov     byte ptr [rax], 1
0x180051fdf  mov     rcx, [rbp+arg_8]
0x180051fe3  call    ResealBitLockerVolume
0x180051fe8  mov     ebx, eax
0x180051fea  test    eax, eax
0x180051fec  jns     short loc_180051FF5
0x180051fee  mov     edx, 13Bh
0x180051ff3  jmp     short loc_180051F77
0x180051ff5  mov     rcx, [rbp+arg_8]
0x180051ff9  test    rcx, rcx
0x180051ffc  jz      short loc_18005200A
0x180051ffe  call    cs:__imp_FveCloseVolume
0x180052005  nop     dword ptr [rax+rax+00h]
0x18005200a  xor     ebx, ebx
0x18005200c  mov     eax, ebx
0x18005200e  mov     rbx, [rsp+30h+arg_10]
0x180052013  add     rsp, 30h
0x180052017  pop     r15
0x180052019  pop     rdi
0x18005201a  pop     rbp
0x18005201b  retn
```
