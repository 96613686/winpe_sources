# CControlPanelPage::LayoutInitialized(void)

- ea: `0x18002eafc`
- end: `0x18002ecaa`
- name: `?LayoutInitialized@CControlPanelPage@@UEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180020640`

## callees

- `0x18002eafc`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002ebf0`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18002ebf0`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18002eb79`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18002eb79`

## pseudocode

```c
__int64 __fastcall CControlPanelPage::LayoutInitialized(CControlPanelPage *this)
{
  char *v2; // rcx
  __int64 v3; // rax
  IUnknown *v4; // rcx
  __int64 v6; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v7; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvOut; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v10[528]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = (char *)this - 224;
  if ( !*((_DWORD *)v2 + 58) )
  {
    v3 = *(_QWORD *)v2;
    v6 = 0;
    if ( (*(int (__fastcall **)(char *, GUID *, __int64 *))(v3 + 368))(
           v2,
           &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
           &v6) >= 0 )
    {
      IUnknown_ProfferService(*((_QWORD *)this - 1), &IID_IShellSearchTargetServices, v6, (char *)this + 8);
      v9 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026, &v9) >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v9 + 24LL))(v9, v10, 260) >= 0 )
        {
          v4 = (IUnknown *)*((_QWORD *)this - 1);
          ppvOut = 0;
          if ( IUnknown_QueryService(
                 v4,
                 (const GUID *const)&SID_SNavBar,
                 &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                 &ppvOut) >= 0 )
          {
            v7 = 0;
            if ( (*(int (__fastcall **)(void *, __int64 *, GUID *, __int64 *))(*(_QWORD *)ppvOut + 24LL))(
                   ppvOut,
                   OID_OSearchControl,
                   &GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f,
                   &v7) >= 0 )
            {
              (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v7 + 64LL))(v7, v10, 0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002eafc  mov     [rsp-8+arg_8], rbx
0x18002eb01  push    rbp
0x18002eb02  lea     rbp, [rsp-170h]
0x18002eb0a  sub     rsp, 270h
0x18002eb11  mov     rax, cs:__security_cookie
0x18002eb18  xor     rax, rsp
0x18002eb1b  mov     [rbp+170h+var_10], rax
0x18002eb22  mov     rbx, rcx
0x18002eb25  add     rcx, 0FFFFFFFFFFFFFF20h
0x18002eb2c  cmp     dword ptr [rcx+0E8h], 0
0x18002eb33  jnz     loc_18002EC88
0x18002eb39  mov     rax, [rcx]
0x18002eb3c  lea     r8, [rsp+270h+var_240]
0x18002eb41  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18002eb48  mov     [rsp+270h+var_240], 0
0x18002eb51  mov     rax, [rax+170h]
0x18002eb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb5d  test    eax, eax
0x18002eb5f  js      loc_18002EC88
0x18002eb65  mov     r8, [rsp+270h+var_240]
0x18002eb6a  lea     r9, [rbx+8]
0x18002eb6e  mov     rcx, [rbx-8]
0x18002eb72  lea     rdx, IID_IShellSearchTargetServices
0x18002eb79  call    cs:__imp_IUnknown_ProfferService
0x18002eb7f  mov     rcx, [rsp+270h+var_240]
0x18002eb84  lea     r8, [rsp+270h+var_228]
0x18002eb89  mov     [rsp+270h+var_228], 0
0x18002eb92  lea     rdx, _GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026
0x18002eb99  mov     rax, [rcx]
0x18002eb9c  mov     rax, [rax]
0x18002eb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eba4  test    eax, eax
0x18002eba6  js      loc_18002EC77
0x18002ebac  mov     rcx, [rsp+270h+var_228]
0x18002ebb1  lea     rdx, [rsp+270h+var_220]
0x18002ebb6  mov     r8d, 104h
0x18002ebbc  mov     rax, [rcx]
0x18002ebbf  mov     rax, [rax+18h]
0x18002ebc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebc8  test    eax, eax
0x18002ebca  js      loc_18002EC66
0x18002ebd0  mov     rcx, [rbx-8]; punk
0x18002ebd4  lea     r9, [rsp+270h+ppvOut]; ppvOut
0x18002ebd9  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a; riid
0x18002ebe0  mov     [rsp+270h+ppvOut], 0
0x18002ebe9  lea     rdx, SID_SNavBar; guidService
0x18002ebf0  call    cs:__imp_IUnknown_QueryService
0x18002ebf6  test    eax, eax
0x18002ebf8  js      short loc_18002EC66
0x18002ebfa  mov     rcx, [rsp+270h+ppvOut]
0x18002ebff  lea     r9, [rsp+270h+var_238]
0x18002ec04  mov     [rsp+270h+var_238], 0
0x18002ec0d  lea     r8, _GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f
0x18002ec14  lea     rdx, OID_OSearchControl
0x18002ec1b  mov     rax, [rcx]
0x18002ec1e  mov     rax, [rax+18h]
0x18002ec22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec27  test    eax, eax
0x18002ec29  js      short loc_18002EC55
0x18002ec2b  mov     rcx, [rsp+270h+var_238]
0x18002ec30  lea     rdx, [rsp+270h+var_220]
0x18002ec35  xor     r8d, r8d
0x18002ec38  mov     rax, [rcx]
0x18002ec3b  mov     rax, [rax+40h]
0x18002ec3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec44  mov     rcx, [rsp+270h+var_238]
0x18002ec49  mov     rax, [rcx]
0x18002ec4c  mov     rax, [rax+10h]
0x18002ec50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec55  mov     rcx, [rsp+270h+ppvOut]
0x18002ec5a  mov     rax, [rcx]
0x18002ec5d  mov     rax, [rax+10h]
0x18002ec61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec66  mov     rcx, [rsp+270h+var_228]
0x18002ec6b  mov     rax, [rcx]
0x18002ec6e  mov     rax, [rax+10h]
0x18002ec72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec77  mov     rcx, [rsp+270h+var_240]
0x18002ec7c  mov     rax, [rcx]
0x18002ec7f  mov     rax, [rax+10h]
0x18002ec83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec88  xor     eax, eax
0x18002ec8a  mov     rcx, [rbp+170h+var_10]
0x18002ec91  xor     rcx, rsp; StackCookie
0x18002ec94  call    __security_check_cookie
0x18002ec99  mov     rbx, [rsp+270h+arg_8]
0x18002eca1  add     rsp, 270h
0x18002eca8  pop     rbp
0x18002eca9  retn
```
