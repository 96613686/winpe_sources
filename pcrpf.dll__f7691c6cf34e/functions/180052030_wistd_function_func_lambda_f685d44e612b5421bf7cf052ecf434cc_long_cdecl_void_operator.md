# wistd::__function::__func__lambda_f685d44e612b5421bf7cf052ecf434cc__long___cdecl(void__)_::operator()

- ea: `0x180052030`
- end: `0x1800520b2`
- name: `wistd::__function::__func__lambda_f685d44e612b5421bf7cf052ecf434cc__long___cdecl(void__)_::operator()`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180009c64`
- `0x180052030`
- `0x180052ea4`
- `0x180053234`
- `0x180053898`

## string_xrefs

- `0x180052063`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052091`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func__lambda_f685d44e612b5421bf7cf052ecf434cc__long___cdecl_void____::operator()(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  unsigned int v4; // eax
  int v5; // eax
  unsigned int v6; // ebx
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = a1;
  v2 = *a2;
  v3 = *a2;
  LOBYTE(v10) = 0;
  v4 = IsTpmProtectedVolumeWithPcrs(v3, -1, &v10);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0xE6,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
    (const char *)v4,
    (int)"IsTpmProtectedVolumeWithPcrs",
    v8);
  if ( (_BYTE)v10 && (v5 = ResealBitLockerVolume(v2), v6 = v5, v5 < 0) )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)(unsigned int)v5);
  else
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180052030  mov     [rsp+arg_0], rcx
0x180052035  push    rbx
0x180052036  sub     rsp, 30h
0x18005203a  mov     rbx, [rdx]
0x18005203d  lea     r8, [rsp+38h+arg_0]
0x180052042  mov     rcx, rbx
0x180052045  mov     byte ptr [rsp+38h+arg_0], 0
0x18005204a  or      edx, 0FFFFFFFFh
0x18005204d  call    IsTpmProtectedVolumeWithPcrs
0x180052052  mov     rcx, [rsp+38h]; this
0x180052057  lea     rdx, aIstpmprotected; "IsTpmProtectedVolumeWithPcrs"
0x18005205e  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180052063  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005206a  mov     edx, 0E6h; void *
0x18005206f  mov     r9d, eax; char *
0x180052072  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180052077  cmp     byte ptr [rsp+38h+arg_0], 0
0x18005207c  jz      short loc_1800520A7
0x18005207e  mov     rcx, rbx
0x180052081  call    ResealBitLockerVolume
0x180052086  mov     ebx, eax
0x180052088  test    eax, eax
0x18005208a  jns     short loc_1800520A7
0x18005208c  mov     rcx, [rsp+38h]; this
0x180052091  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052098  mov     r9d, eax; char *
0x18005209b  mov     edx, 0E9h; void *
0x1800520a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800520a5  jmp     short loc_1800520A9
0x1800520a7  xor     ebx, ebx
0x1800520a9  mov     eax, ebx
0x1800520ab  add     rsp, 30h
0x1800520af  pop     rbx
0x1800520b0  retn
```
