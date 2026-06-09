# COskOptionsDlg::GenerateSliderAccessibleText(void)

- ea: `0x140018174`
- end: `0x14001829d`
- name: `?GenerateSliderAccessibleText@COskOptionsDlg@@AEAAXXZ`
- size: `297`
- prototype: `void __fastcall(COskOptionsDlg *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140018390`

## callees

- `0x140018174`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `USER32!LoadStringW` at `0x1400181d8`
- `USER32!LoadStringW` at `0x1400181d8`
- `USER32!GetDlgItem` at `0x1400181e6`
- `USER32!GetDlgItem` at `0x140018237`
- `USER32!GetDlgItem` at `0x1400181e6`
- `USER32!GetDlgItem` at `0x140018237`
- `ole32!CoCreateInstance` at `0x1400181b3`
- `ole32!CoCreateInstance` at `0x1400181b3`

## pseudocode

```c
void __fastcall COskOptionsDlg::GenerateSliderAccessibleText(HWND *this)
{
  __int64 **v1; // rdi
  HWND DlgItem; // rax
  __int64 *v4; // rcx
  __int64 v5; // rdx
  HWND v6; // rax
  __int64 *v7; // rcx
  __int64 v8; // rdx
  GUID v9; // [rsp+40h] [rbp-228h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-218h] BYREF

  v1 = (__int64 **)(this + 1);
  if ( CoCreateInstance(
         &CLSID_AccPropServices,
         0,
         0x15u,
         &GUID_6e26e776_04f0_495d_80e4_3330352e3169,
         (LPVOID *)this + 1) >= 0 )
  {
    LoadStringW(g_hInstance, 0x3F5u, Buffer, 256);
    DlgItem = GetDlgItem(*this, 5017);
    v4 = *v1;
    v5 = **v1;
    v9 = PROPID_ACC_VALUEMAP;
    if ( (*(int (__fastcall **)(__int64 *, HWND, __int64, _QWORD, GUID *, WCHAR *))(v5 + 56))(
           v4,
           DlgItem,
           4294967292LL,
           0,
           &v9,
           Buffer) >= 0 )
    {
      v6 = GetDlgItem(*this, 5020);
      v7 = *v1;
      v8 = **v1;
      v9 = PROPID_ACC_VALUEMAP;
      (*(void (__fastcall **)(__int64 *, HWND, __int64, _QWORD, GUID *, WCHAR *))(v8 + 56))(
        v7,
        v6,
        4294967292LL,
        0,
        &v9,
        Buffer);
    }
  }
}

```

## disassembly

```asm
0x140018174  mov     [rsp+arg_8], rbx
0x140018179  push    rdi
0x14001817a  sub     rsp, 260h
0x140018181  mov     rax, cs:__security_cookie
0x140018188  xor     rax, rsp
0x14001818b  mov     [rsp+268h+var_18], rax
0x140018193  lea     rdi, [rcx+8]
0x140018197  xor     edx, edx; pUnkOuter
0x140018199  mov     rbx, rcx
0x14001819c  mov     [rsp+268h+ppv], rdi; ppv
0x1400181a1  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x1400181a8  lea     rcx, CLSID_AccPropServices; rclsid
0x1400181af  lea     r8d, [rdx+15h]; dwClsContext
0x1400181b3  call    cs:__imp_CoCreateInstance
0x1400181b9  test    eax, eax
0x1400181bb  js      loc_14001827C
0x1400181c1  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1400181c8  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1400181cd  mov     r9d, 100h; cchBufferMax
0x1400181d3  mov     edx, 3F5h; uID
0x1400181d8  call    cs:__imp_LoadStringW
0x1400181de  mov     rcx, [rbx]; hDlg
0x1400181e1  mov     edx, 1399h; nIDDlgItem
0x1400181e6  call    cs:__imp_GetDlgItem
0x1400181ec  mov     rcx, [rdi]
0x1400181ef  xor     r9d, r9d
0x1400181f2  movups  xmm0, xmmword ptr cs:PROPID_ACC_VALUEMAP.Data1
0x1400181f9  mov     r10, rax
0x1400181fc  mov     r8d, 0FFFFFFFCh
0x140018202  mov     rdx, [rcx]
0x140018205  movdqu  [rsp+268h+var_228], xmm0
0x14001820b  mov     rax, [rdx+38h]
0x14001820f  lea     rdx, [rsp+268h+Buffer]
0x140018214  mov     [rsp+268h+var_240], rdx
0x140018219  lea     rdx, [rsp+268h+var_228]
0x14001821e  mov     [rsp+268h+ppv], rdx
0x140018223  mov     rdx, r10
0x140018226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001822b  test    eax, eax
0x14001822d  js      short loc_14001827C
0x14001822f  mov     rcx, [rbx]; hDlg
0x140018232  mov     edx, 139Ch; nIDDlgItem
0x140018237  call    cs:__imp_GetDlgItem
0x14001823d  mov     rcx, [rdi]
0x140018240  xor     r9d, r9d
0x140018243  movups  xmm0, xmmword ptr cs:PROPID_ACC_VALUEMAP.Data1
0x14001824a  mov     r10, rax
0x14001824d  mov     r8d, 0FFFFFFFCh
0x140018253  mov     rdx, [rcx]
0x140018256  movdqu  [rsp+268h+var_228], xmm0
0x14001825c  mov     rax, [rdx+38h]
0x140018260  lea     rdx, [rsp+268h+Buffer]
0x140018265  mov     [rsp+268h+var_240], rdx
0x14001826a  lea     rdx, [rsp+268h+var_228]
0x14001826f  mov     [rsp+268h+ppv], rdx
0x140018274  mov     rdx, r10
0x140018277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001827c  mov     rcx, [rsp+268h+var_18]
0x140018284  xor     rcx, rsp; StackCookie
0x140018287  call    __security_check_cookie
0x14001828c  mov     rbx, [rsp+268h+arg_8]
0x140018294  add     rsp, 260h
0x14001829b  pop     rdi
0x14001829c  retn
```
