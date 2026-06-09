# CControlPanelPage::LayoutInitialized(void)

- ea: `0x18001cbb4`
- end: `0x18001cd62`
- name: `?LayoutInitialized@CControlPanelPage@@UEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180014ee0`

## callees

- `0x180002270`
- `0x18001cbb4`
- `0x180023010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001cca8`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001cca8`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18001cc31`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x18001cc31`

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
            if ( (*(int (__fastcall **)(void *, void *, GUID *, __int64 *))(*(_QWORD *)ppvOut + 24LL))(
                   ppvOut,
                   &OID_OSearchControl,
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
0x18001cbb4  mov     [rsp-8+arg_8], rbx
0x18001cbb9  push    rbp
0x18001cbba  lea     rbp, [rsp-170h]
0x18001cbc2  sub     rsp, 270h
0x18001cbc9  mov     rax, cs:__security_cookie
0x18001cbd0  xor     rax, rsp
0x18001cbd3  mov     [rbp+170h+var_10], rax
0x18001cbda  mov     rbx, rcx
0x18001cbdd  add     rcx, 0FFFFFFFFFFFFFF20h
0x18001cbe4  cmp     dword ptr [rcx+0E8h], 0
0x18001cbeb  jnz     loc_18001CD40
0x18001cbf1  mov     rax, [rcx]
0x18001cbf4  lea     r8, [rsp+270h+var_240]
0x18001cbf9  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18001cc00  mov     [rsp+270h+var_240], 0
0x18001cc09  mov     rax, [rax+170h]
0x18001cc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc15  test    eax, eax
0x18001cc17  js      loc_18001CD40
0x18001cc1d  mov     r8, [rsp+270h+var_240]
0x18001cc22  lea     r9, [rbx+8]
0x18001cc26  mov     rcx, [rbx-8]
0x18001cc2a  lea     rdx, IID_IShellSearchTargetServices
0x18001cc31  call    cs:__imp_IUnknown_ProfferService
0x18001cc37  mov     rcx, [rsp+270h+var_240]
0x18001cc3c  lea     r8, [rsp+270h+var_228]
0x18001cc41  mov     [rsp+270h+var_228], 0
0x18001cc4a  lea     rdx, _GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026
0x18001cc51  mov     rax, [rcx]
0x18001cc54  mov     rax, [rax]
0x18001cc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc5c  test    eax, eax
0x18001cc5e  js      loc_18001CD2F
0x18001cc64  mov     rcx, [rsp+270h+var_228]
0x18001cc69  lea     rdx, [rsp+270h+var_220]
0x18001cc6e  mov     r8d, 104h
0x18001cc74  mov     rax, [rcx]
0x18001cc77  mov     rax, [rax+18h]
0x18001cc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc80  test    eax, eax
0x18001cc82  js      loc_18001CD1E
0x18001cc88  mov     rcx, [rbx-8]; punk
0x18001cc8c  lea     r9, [rsp+270h+ppvOut]; ppvOut
0x18001cc91  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a; riid
0x18001cc98  mov     [rsp+270h+ppvOut], 0
0x18001cca1  lea     rdx, SID_SNavBar; guidService
0x18001cca8  call    cs:__imp_IUnknown_QueryService
0x18001ccae  test    eax, eax
0x18001ccb0  js      short loc_18001CD1E
0x18001ccb2  mov     rcx, [rsp+270h+ppvOut]
0x18001ccb7  lea     r9, [rsp+270h+var_238]
0x18001ccbc  mov     [rsp+270h+var_238], 0
0x18001ccc5  lea     r8, _GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f
0x18001cccc  lea     rdx, OID_OSearchControl
0x18001ccd3  mov     rax, [rcx]
0x18001ccd6  mov     rax, [rax+18h]
0x18001ccda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccdf  test    eax, eax
0x18001cce1  js      short loc_18001CD0D
0x18001cce3  mov     rcx, [rsp+270h+var_238]
0x18001cce8  lea     rdx, [rsp+270h+var_220]
0x18001cced  xor     r8d, r8d
0x18001ccf0  mov     rax, [rcx]
0x18001ccf3  mov     rax, [rax+40h]
0x18001ccf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccfc  mov     rcx, [rsp+270h+var_238]
0x18001cd01  mov     rax, [rcx]
0x18001cd04  mov     rax, [rax+10h]
0x18001cd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd0d  mov     rcx, [rsp+270h+ppvOut]
0x18001cd12  mov     rax, [rcx]
0x18001cd15  mov     rax, [rax+10h]
0x18001cd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd1e  mov     rcx, [rsp+270h+var_228]
0x18001cd23  mov     rax, [rcx]
0x18001cd26  mov     rax, [rax+10h]
0x18001cd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd2f  mov     rcx, [rsp+270h+var_240]
0x18001cd34  mov     rax, [rcx]
0x18001cd37  mov     rax, [rax+10h]
0x18001cd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd40  xor     eax, eax
0x18001cd42  mov     rcx, [rbp+170h+var_10]
0x18001cd49  xor     rcx, rsp; StackCookie
0x18001cd4c  call    __security_check_cookie
0x18001cd51  mov     rbx, [rsp+270h+arg_8]
0x18001cd59  add     rsp, 270h
0x18001cd60  pop     rbp
0x18001cd61  retn
```
