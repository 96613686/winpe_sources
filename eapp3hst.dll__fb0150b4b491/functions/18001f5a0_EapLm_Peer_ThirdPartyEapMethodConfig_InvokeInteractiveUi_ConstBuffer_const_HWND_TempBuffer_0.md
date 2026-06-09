# EapLm::Peer::ThirdPartyEapMethodConfig::InvokeInteractiveUi(ConstBuffer const &,HWND__ *,TempBuffer<0> &)

- ea: `0x18001f5a0`
- end: `0x18001f66f`
- name: `?InvokeInteractiveUi@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXAEBUConstBuffer@@PEAUHWND__@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x18001f5a0`
- `0x18001fd10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001f611`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001f611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f625`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f625`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::InvokeInteractiveUi(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void *v4; // rbx
  EapLm::Peer::ThirdPartyEapMethodConfig *v5; // rcx
  int v6; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v7[2]; // [rsp+38h] [rbp-71h] BYREF
  const struct _EAP_ERROR **v8; // [rsp+40h] [rbp-69h]
  __int128 v9; // [rsp+48h] [rbp-61h] BYREF
  __int64 v10; // [rsp+58h] [rbp-51h]
  __int64 v11; // [rsp+60h] [rbp-49h]
  __int64 v12; // [rsp+68h] [rbp-41h]
  LPVOID v13; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v14[96]; // [rsp+80h] [rbp-29h] BYREF

  v6 = 0;
  v13 = 0;
  v9 = *(_OWORD *)(a1 + 16);
  v11 = a3;
  v10 = a2;
  v12 = a4;
  *(_QWORD *)v7 = 2;
  v8 = (const struct _EAP_ERROR **)&v9;
  v4 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 (__fastcall *)(_DWORD *), unsigned int *, _DWORD, int *))_o__beginthreadex)(
                 0,
                 0,
                 thirdPartyUIInvocationThread,
                 v7,
                 0,
                 &v6);
  EapLm::Peer::ThirdPartyEapMethodConfig::WaitForCOMcallCompletion(v5, v4);
  CloseHandle(v4);
  if ( (v7[1] & 0x80000000) != 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v14, v8[5], v7[1]);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v14);
  }
  com_ptr<_EAP_ERROR>::Clear(&v13);
}

```

## disassembly

```asm
0x18001f5a0  push    rbp
0x18001f5a2  push    rbx
0x18001f5a3  lea     rbp, [rsp-4Fh]
0x18001f5a8  sub     rsp, 0F8h
0x18001f5af  mov     rax, cs:__security_cookie
0x18001f5b6  xor     rax, rsp
0x18001f5b9  mov     [rbp+57h+var_20], rax
0x18001f5bd  mov     [rbp+57h+var_D0], 0
0x18001f5c4  mov     [rbp+57h+var_90], 0
0x18001f5cc  movups  xmm0, xmmword ptr [rcx+10h]
0x18001f5d0  movdqu  [rbp+57h+var_B8], xmm0
0x18001f5d5  mov     [rbp+57h+var_A0], r8
0x18001f5d9  mov     [rbp+57h+var_A8], rdx
0x18001f5dd  mov     [rbp+57h+var_98], r9
0x18001f5e1  mov     qword ptr [rbp+57h+var_C8], 2
0x18001f5e9  lea     rax, [rbp+57h+var_B8]
0x18001f5ed  mov     [rbp+57h+var_C0], rax
0x18001f5f1  lea     rax, [rbp+57h+var_D0]
0x18001f5f5  mov     [rsp+100h+var_D8], rax
0x18001f5fa  mov     [rsp+100h+var_E0], 0
0x18001f602  lea     r9, [rbp+57h+var_C8]
0x18001f606  lea     r8, ?thirdPartyUIInvocationThread@@YAIPEAX@Z; thirdPartyUIInvocationThread(void *)
0x18001f60d  xor     edx, edx
0x18001f60f  xor     ecx, ecx
0x18001f611  call    cs:__imp__o__beginthreadex
0x18001f617  mov     rbx, rax
0x18001f61a  mov     rdx, rax; void *
0x18001f61d  call    ?WaitForCOMcallCompletion@ThirdPartyEapMethodConfig@Peer@EapLm@@AEAAXPEAX@Z; EapLm::Peer::ThirdPartyEapMethodConfig::WaitForCOMcallCompletion(void *)
0x18001f622  mov     rcx, rbx; hObject
0x18001f625  call    cs:__imp_CloseHandle
0x18001f62b  mov     r8d, [rbp+57h+var_C8+4]; unsigned int
0x18001f62f  test    r8d, r8d
0x18001f632  jns     short loc_18001F650
0x18001f634  mov     rdx, [rbp+57h+var_C0]
0x18001f638  mov     rdx, [rdx+28h]; struct _EAP_ERROR *
0x18001f63c  lea     rcx, [rbp+57h+var_80]; this
0x18001f640  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001f645  nop
0x18001f646  lea     rcx, [rbp+57h+var_80]; struct EapHost::EapError *
0x18001f64a  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001f650  lea     rcx, [rbp+57h+var_90]
0x18001f654  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001f659  mov     rcx, [rbp+57h+var_20]
0x18001f65d  xor     rcx, rsp; StackCookie
0x18001f660  call    __security_check_cookie
0x18001f665  add     rsp, 0F8h
0x18001f66c  pop     rbx
0x18001f66d  pop     rbp
0x18001f66e  retn
```
