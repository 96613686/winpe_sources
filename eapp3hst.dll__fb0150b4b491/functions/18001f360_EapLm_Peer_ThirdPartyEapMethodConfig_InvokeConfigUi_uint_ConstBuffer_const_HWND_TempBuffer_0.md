# EapLm::Peer::ThirdPartyEapMethodConfig::InvokeConfigUi(uint,ConstBuffer const &,HWND__ *,TempBuffer<0> &)

- ea: `0x18001f360`
- end: `0x18001f438`
- name: `?InvokeConfigUi@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXIAEBUConstBuffer@@PEAUHWND__@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x18001f360`
- `0x18001fd10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001f3da`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001f3da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f3ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f3ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::InvokeConfigUi(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  void *v5; // rbx
  EapLm::Peer::ThirdPartyEapMethodConfig *v6; // rcx
  int v7; // [rsp+30h] [rbp-81h] BYREF
  unsigned int v8[2]; // [rsp+38h] [rbp-79h] BYREF
  const struct _EAP_ERROR **v9; // [rsp+40h] [rbp-71h]
  __int128 v10; // [rsp+48h] [rbp-69h] BYREF
  int v11; // [rsp+58h] [rbp-59h]
  __int64 v12; // [rsp+60h] [rbp-51h]
  __int64 v13; // [rsp+68h] [rbp-49h]
  __int64 v14; // [rsp+70h] [rbp-41h]
  LPVOID v15; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v16[96]; // [rsp+80h] [rbp-31h] BYREF

  v7 = 0;
  *(_QWORD *)v8 = 0;
  v15 = 0;
  v10 = *(_OWORD *)(a1 + 16);
  v13 = a4;
  v11 = a2;
  v12 = a3;
  v14 = a5;
  v9 = (const struct _EAP_ERROR **)&v10;
  v5 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 (__fastcall *)(_DWORD *), unsigned int *, _DWORD, int *))_o__beginthreadex)(
                 0,
                 0,
                 thirdPartyUIInvocationThread,
                 v8,
                 0,
                 &v7);
  EapLm::Peer::ThirdPartyEapMethodConfig::WaitForCOMcallCompletion(v6, v5);
  CloseHandle(v5);
  if ( (v8[1] & 0x80000000) != 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v16, v9[6], v8[1]);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v16);
  }
  com_ptr<_EAP_ERROR>::Clear(&v15);
}

```

## disassembly

```asm
0x18001f360  push    rbp
0x18001f362  push    rbx
0x18001f363  lea     rbp, [rsp-47h]
0x18001f368  sub     rsp, 0F8h
0x18001f36f  mov     rax, cs:__security_cookie
0x18001f376  xor     rax, rsp
0x18001f379  mov     [rbp+4Fh+var_20], rax
0x18001f37d  mov     rax, [rbp+4Fh+arg_20]
0x18001f381  mov     [rsp+100h+var_D0], 0
0x18001f389  mov     qword ptr [rbp+4Fh+var_C8], 0
0x18001f391  mov     [rbp+4Fh+var_88], 0
0x18001f399  movups  xmm0, xmmword ptr [rcx+10h]
0x18001f39d  movdqu  [rbp+4Fh+var_B8], xmm0
0x18001f3a2  mov     [rbp+4Fh+var_98], r9
0x18001f3a6  mov     [rbp+4Fh+var_A8], edx
0x18001f3a9  mov     [rbp+4Fh+var_A0], r8
0x18001f3ad  mov     [rbp+4Fh+var_90], rax
0x18001f3b1  lea     rax, [rbp+4Fh+var_B8]
0x18001f3b5  mov     [rbp+4Fh+var_C0], rax
0x18001f3b9  lea     rax, [rsp+100h+var_D0]
0x18001f3be  mov     [rsp+100h+var_D8], rax
0x18001f3c3  mov     [rsp+100h+var_E0], 0
0x18001f3cb  lea     r9, [rbp+4Fh+var_C8]
0x18001f3cf  lea     r8, ?thirdPartyUIInvocationThread@@YAIPEAX@Z; thirdPartyUIInvocationThread(void *)
0x18001f3d6  xor     edx, edx
0x18001f3d8  xor     ecx, ecx
0x18001f3da  call    cs:__imp__o__beginthreadex
0x18001f3e0  mov     rbx, rax
0x18001f3e3  mov     rdx, rax; void *
0x18001f3e6  call    ?WaitForCOMcallCompletion@ThirdPartyEapMethodConfig@Peer@EapLm@@AEAAXPEAX@Z; EapLm::Peer::ThirdPartyEapMethodConfig::WaitForCOMcallCompletion(void *)
0x18001f3eb  mov     rcx, rbx; hObject
0x18001f3ee  call    cs:__imp_CloseHandle
0x18001f3f4  mov     r8d, [rbp+4Fh+var_C8+4]; unsigned int
0x18001f3f8  test    r8d, r8d
0x18001f3fb  jns     short loc_18001F419
0x18001f3fd  mov     rdx, [rbp+4Fh+var_C0]
0x18001f401  mov     rdx, [rdx+30h]; struct _EAP_ERROR *
0x18001f405  lea     rcx, [rbp+4Fh+var_80]; this
0x18001f409  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001f40e  nop
0x18001f40f  lea     rcx, [rbp+4Fh+var_80]; struct EapHost::EapError *
0x18001f413  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001f419  lea     rcx, [rbp+4Fh+var_88]
0x18001f41d  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001f422  mov     rcx, [rbp+4Fh+var_20]
0x18001f426  xor     rcx, rsp; StackCookie
0x18001f429  call    __security_check_cookie
0x18001f42e  add     rsp, 0F8h
0x18001f435  pop     rbx
0x18001f436  pop     rbp
0x18001f437  retn
```
