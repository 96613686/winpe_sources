# EapLm::Peer::ThirdPartyEapMethodConfig::InvokeIdentityUi(uint,ConstBuffer const &,ConstBuffer const &,HWND__ *,TempBuffer<0> &,BasicSimpleString<wchar_t> &)

- ea: `0x18001f440`
- end: `0x18001f596`
- name: `?InvokeIdentityUi@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXIAEBUConstBuffer@@0PEAUHWND__@@AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180013d10`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x18001f440`
- `0x18001fd10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001f4f4`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18001f4f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f51e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f51e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f568`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::InvokeIdentityUi(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        void **a7)
{
  void *v7; // rbx
  EapLm::Peer::ThirdPartyEapMethodConfig *v8; // rcx
  unsigned int v9[2]; // [rsp+30h] [rbp-F8h] BYREF
  __int128 *v10; // [rsp+38h] [rbp-F0h]
  _DWORD v11[4]; // [rsp+40h] [rbp-E8h] BYREF
  __int128 v12; // [rsp+50h] [rbp-D8h] BYREF
  int v13; // [rsp+60h] [rbp-C8h]
  __int64 v14; // [rsp+68h] [rbp-C0h]
  __int64 v15; // [rsp+70h] [rbp-B8h]
  __int64 v16; // [rsp+78h] [rbp-B0h]
  __int64 v17; // [rsp+80h] [rbp-A8h]
  void **v18; // [rsp+88h] [rbp-A0h]
  __int64 v19; // [rsp+90h] [rbp-98h]
  LPVOID v20; // [rsp+98h] [rbp-90h] BYREF
  _BYTE v21[96]; // [rsp+A0h] [rbp-88h] BYREF

  v11[0] = 0;
  v20 = 0;
  v12 = *(_OWORD *)(a1 + 16);
  v16 = a5;
  v13 = a2;
  v14 = a3;
  v15 = a4;
  v17 = a6;
  v18 = a7;
  v19 = 0;
  *(_QWORD *)v9 = 1;
  v10 = &v12;
  v7 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, unsigned int (__fastcall *)(void *), unsigned int *, _DWORD, _DWORD *))_o__beginthreadex)(
                 0,
                 0,
                 thirdPartyUIInvocationThread,
                 v9,
                 0,
                 v11);
  EapLm::Peer::ThirdPartyEapMethodConfig::WaitForCOMcallCompletion(v8, v7);
  CloseHandle(v7);
  if ( (v9[1] & 0x80000000) != 0 )
  {
    CoTaskMemFree(*((LPVOID *)v10 + 8));
    EapHost::EapError::EapError((EapHost::EapError *)v21, *((const struct _EAP_ERROR **)v10 + 9), v9[1]);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v21);
  }
  try
  {
    BasicSimpleString<wchar_t>::Assign(a7, *((_QWORD *)v10 + 8));
    CoTaskMemFree(*((LPVOID *)v10 + 8));
  }
  catch ( std::bad_alloc )
  {
    CoTaskMemFree(*((LPVOID *)v10 + 8));
    throw;
  }
  com_ptr<_EAP_ERROR>::Clear(&v20);
}

```

## disassembly

```asm
0x18001f440  mov     r11, rsp
0x18001f443  push    rbx
0x18001f444  push    rdi
0x18001f445  sub     rsp, 118h
0x18001f44c  mov     rax, cs:__security_cookie
0x18001f453  xor     rax, rsp
0x18001f456  mov     [rsp+128h+var_28], rax
0x18001f45e  mov     rax, [rsp+128h+arg_20]
0x18001f466  mov     r10, [rsp+128h+arg_28]
0x18001f46e  mov     rdi, [rsp+128h+arg_30]
0x18001f476  mov     [rsp+128h+var_E8], 0
0x18001f47e  mov     qword ptr [r11-90h], 0
0x18001f489  movups  xmm0, xmmword ptr [rcx+10h]
0x18001f48d  movdqu  [rsp+128h+var_D8], xmm0
0x18001f493  mov     [rsp+128h+var_B0], rax
0x18001f498  mov     [rsp+128h+var_C8], edx
0x18001f49c  mov     [rsp+128h+var_C0], r8
0x18001f4a1  mov     [rsp+128h+var_B8], r9
0x18001f4a6  mov     [r11-0A8h], r10
0x18001f4ad  mov     [r11-0A0h], rdi
0x18001f4b4  mov     qword ptr [r11-98h], 0
0x18001f4bf  mov     qword ptr [rsp+128h+var_F8], 1
0x18001f4c8  lea     rax, [rsp+128h+var_D8]
0x18001f4cd  mov     [rsp+128h+var_F0], rax
0x18001f4d2  lea     rax, [rsp+128h+var_E8]
0x18001f4d7  mov     [rsp+128h+var_100], rax
0x18001f4dc  mov     [rsp+128h+var_108], 0
0x18001f4e4  lea     r9, [rsp+128h+var_F8]
0x18001f4e9  lea     r8, ?thirdPartyUIInvocationThread@@YAIPEAX@Z; thirdPartyUIInvocationThread(void *)
0x18001f4f0  xor     edx, edx
0x18001f4f2  xor     ecx, ecx
0x18001f4f4  call    cs:__imp__o__beginthreadex
0x18001f4fa  mov     rbx, rax
0x18001f4fd  mov     rdx, rax; void *
0x18001f500  call    ?WaitForCOMcallCompletion@ThirdPartyEapMethodConfig@Peer@EapLm@@AEAAXPEAX@Z; EapLm::Peer::ThirdPartyEapMethodConfig::WaitForCOMcallCompletion(void *)
0x18001f505  mov     rcx, rbx; hObject
0x18001f508  call    cs:__imp_CloseHandle
0x18001f50e  cmp     [rsp+128h+var_F8+4], 0
0x18001f513  jge     short loc_18001F54E
0x18001f515  mov     rcx, [rsp+128h+var_F0]
0x18001f51a  mov     rcx, [rcx+40h]; pv
0x18001f51e  call    cs:__imp_CoTaskMemFree
0x18001f524  mov     r8d, [rsp+128h+var_F8+4]; unsigned int
0x18001f529  mov     rdx, [rsp+128h+var_F0]
0x18001f52e  mov     rdx, [rdx+48h]; struct _EAP_ERROR *
0x18001f532  lea     rcx, [rsp+128h+var_88]; this
0x18001f53a  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001f53f  nop
0x18001f540  lea     rcx, [rsp+128h+var_88]; struct EapHost::EapError *
0x18001f548  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001f54e  mov     rdx, [rsp+128h+var_F0]
0x18001f553  mov     rdx, [rdx+40h]
0x18001f557  mov     rcx, rdi
0x18001f55a  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001f55f  mov     rcx, [rsp+128h+var_F0]
0x18001f564  mov     rcx, [rcx+40h]; pv
0x18001f568  call    cs:__imp_CoTaskMemFree
0x18001f56e  nop
0x18001f56f  lea     rcx, [rsp+128h+var_90]
0x18001f577  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001f57c  mov     rcx, [rsp+128h+var_28]
0x18001f584  xor     rcx, rsp; StackCookie
0x18001f587  call    __security_check_cookie
0x18001f58c  add     rsp, 118h
0x18001f593  pop     rdi
0x18001f594  pop     rbx
0x18001f595  retn
```
