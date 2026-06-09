# CControlPanelPage::LayoutInitialized(void)

- ea: `0x18002fb70`
- end: `0x18002fd1e`
- name: `?LayoutInitialized@CControlPanelPage@@UEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180010250`

## callees

- `0x18002fb70`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18002fc64`
- `SHCORE!IUnknown_QueryService` at `0x18002fc64`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18002fbed`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x18002fbed`

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
0x18002fb70  mov     [rsp-8+arg_8], rbx
0x18002fb75  push    rbp
0x18002fb76  lea     rbp, [rsp-170h]
0x18002fb7e  sub     rsp, 270h
0x18002fb85  mov     rax, cs:__security_cookie
0x18002fb8c  xor     rax, rsp
0x18002fb8f  mov     [rbp+170h+var_10], rax
0x18002fb96  mov     rbx, rcx
0x18002fb99  add     rcx, 0FFFFFFFFFFFFFF20h
0x18002fba0  cmp     dword ptr [rcx+0E8h], 0
0x18002fba7  jnz     loc_18002FCFC
0x18002fbad  mov     rax, [rcx]
0x18002fbb0  lea     r8, [rsp+270h+var_240]
0x18002fbb5  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18002fbbc  mov     [rsp+270h+var_240], 0
0x18002fbc5  mov     rax, [rax+170h]
0x18002fbcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbd1  test    eax, eax
0x18002fbd3  js      loc_18002FCFC
0x18002fbd9  mov     r8, [rsp+270h+var_240]
0x18002fbde  lea     r9, [rbx+8]
0x18002fbe2  mov     rcx, [rbx-8]
0x18002fbe6  lea     rdx, IID_IShellSearchTargetServices
0x18002fbed  call    cs:__imp_IUnknown_ProfferService
0x18002fbf3  mov     rcx, [rsp+270h+var_240]
0x18002fbf8  lea     r8, [rsp+270h+var_228]
0x18002fbfd  mov     [rsp+270h+var_228], 0
0x18002fc06  lea     rdx, _GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026
0x18002fc0d  mov     rax, [rcx]
0x18002fc10  mov     rax, [rax]
0x18002fc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc18  test    eax, eax
0x18002fc1a  js      loc_18002FCEB
0x18002fc20  mov     rcx, [rsp+270h+var_228]
0x18002fc25  lea     rdx, [rsp+270h+var_220]
0x18002fc2a  mov     r8d, 104h
0x18002fc30  mov     rax, [rcx]
0x18002fc33  mov     rax, [rax+18h]
0x18002fc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc3c  test    eax, eax
0x18002fc3e  js      loc_18002FCDA
0x18002fc44  mov     rcx, [rbx-8]; punk
0x18002fc48  lea     r9, [rsp+270h+ppvOut]; ppvOut
0x18002fc4d  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a; riid
0x18002fc54  mov     [rsp+270h+ppvOut], 0
0x18002fc5d  lea     rdx, SID_SNavBar; guidService
0x18002fc64  call    cs:__imp_IUnknown_QueryService
0x18002fc6a  test    eax, eax
0x18002fc6c  js      short loc_18002FCDA
0x18002fc6e  mov     rcx, [rsp+270h+ppvOut]
0x18002fc73  lea     r9, [rsp+270h+var_238]
0x18002fc78  mov     [rsp+270h+var_238], 0
0x18002fc81  lea     r8, _GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f
0x18002fc88  lea     rdx, OID_OSearchControl
0x18002fc8f  mov     rax, [rcx]
0x18002fc92  mov     rax, [rax+18h]
0x18002fc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc9b  test    eax, eax
0x18002fc9d  js      short loc_18002FCC9
0x18002fc9f  mov     rcx, [rsp+270h+var_238]
0x18002fca4  lea     rdx, [rsp+270h+var_220]
0x18002fca9  xor     r8d, r8d
0x18002fcac  mov     rax, [rcx]
0x18002fcaf  mov     rax, [rax+40h]
0x18002fcb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcb8  mov     rcx, [rsp+270h+var_238]
0x18002fcbd  mov     rax, [rcx]
0x18002fcc0  mov     rax, [rax+10h]
0x18002fcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcc9  mov     rcx, [rsp+270h+ppvOut]
0x18002fcce  mov     rax, [rcx]
0x18002fcd1  mov     rax, [rax+10h]
0x18002fcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcda  mov     rcx, [rsp+270h+var_228]
0x18002fcdf  mov     rax, [rcx]
0x18002fce2  mov     rax, [rax+10h]
0x18002fce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fceb  mov     rcx, [rsp+270h+var_240]
0x18002fcf0  mov     rax, [rcx]
0x18002fcf3  mov     rax, [rax+10h]
0x18002fcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcfc  xor     eax, eax
0x18002fcfe  mov     rcx, [rbp+170h+var_10]
0x18002fd05  xor     rcx, rsp; StackCookie
0x18002fd08  call    __security_check_cookie
0x18002fd0d  mov     rbx, [rsp+270h+arg_8]
0x18002fd15  add     rsp, 270h
0x18002fd1c  pop     rbp
0x18002fd1d  retn
```
