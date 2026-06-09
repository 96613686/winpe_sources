# CControlPanelPage::LayoutInitialized(void)

- ea: `0x180016114`
- end: `0x1800162c2`
- name: `?LayoutInitialized@CControlPanelPage@@UEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(CControlPanelPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000f410`

## callees

- `0x180016114`
- `0x180018a80`
- `0x18001a010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180016208`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180016208`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x180016191`
- `SHLWAPI!__imp_IUnknown_ProfferService` at `0x180016191`

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
0x180016114  mov     [rsp-8+arg_8], rbx
0x180016119  push    rbp
0x18001611a  lea     rbp, [rsp-170h]
0x180016122  sub     rsp, 270h
0x180016129  mov     rax, cs:__security_cookie
0x180016130  xor     rax, rsp
0x180016133  mov     [rbp+170h+var_10], rax
0x18001613a  mov     rbx, rcx
0x18001613d  add     rcx, 0FFFFFFFFFFFFFF20h
0x180016144  cmp     dword ptr [rcx+0E8h], 0
0x18001614b  jnz     loc_1800162A0
0x180016151  mov     rax, [rcx]
0x180016154  lea     r8, [rsp+270h+var_240]
0x180016159  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x180016160  mov     [rsp+270h+var_240], 0
0x180016169  mov     rax, [rax+170h]
0x180016170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016175  test    eax, eax
0x180016177  js      loc_1800162A0
0x18001617d  mov     r8, [rsp+270h+var_240]
0x180016182  lea     r9, [rbx+8]
0x180016186  mov     rcx, [rbx-8]
0x18001618a  lea     rdx, IID_IShellSearchTargetServices
0x180016191  call    cs:__imp_IUnknown_ProfferService
0x180016197  mov     rcx, [rsp+270h+var_240]
0x18001619c  lea     r8, [rsp+270h+var_228]
0x1800161a1  mov     [rsp+270h+var_228], 0
0x1800161aa  lea     rdx, _GUID_dda3a58a_43da_4a43_a5f2_f7abf6e3c026
0x1800161b1  mov     rax, [rcx]
0x1800161b4  mov     rax, [rax]
0x1800161b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161bc  test    eax, eax
0x1800161be  js      loc_18001628F
0x1800161c4  mov     rcx, [rsp+270h+var_228]
0x1800161c9  lea     rdx, [rsp+270h+var_220]
0x1800161ce  mov     r8d, 104h
0x1800161d4  mov     rax, [rcx]
0x1800161d7  mov     rax, [rax+18h]
0x1800161db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161e0  test    eax, eax
0x1800161e2  js      loc_18001627E
0x1800161e8  mov     rcx, [rbx-8]; punk
0x1800161ec  lea     r9, [rsp+270h+ppvOut]; ppvOut
0x1800161f1  lea     r8, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a; riid
0x1800161f8  mov     [rsp+270h+ppvOut], 0
0x180016201  lea     rdx, SID_SNavBar; guidService
0x180016208  call    cs:__imp_IUnknown_QueryService
0x18001620e  test    eax, eax
0x180016210  js      short loc_18001627E
0x180016212  mov     rcx, [rsp+270h+ppvOut]
0x180016217  lea     r9, [rsp+270h+var_238]
0x18001621c  mov     [rsp+270h+var_238], 0
0x180016225  lea     r8, _GUID_111f7c32_0546_4227_8b7f_c53a0b114a0f
0x18001622c  lea     rdx, OID_OSearchControl
0x180016233  mov     rax, [rcx]
0x180016236  mov     rax, [rax+18h]
0x18001623a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001623f  test    eax, eax
0x180016241  js      short loc_18001626D
0x180016243  mov     rcx, [rsp+270h+var_238]
0x180016248  lea     rdx, [rsp+270h+var_220]
0x18001624d  xor     r8d, r8d
0x180016250  mov     rax, [rcx]
0x180016253  mov     rax, [rax+40h]
0x180016257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001625c  mov     rcx, [rsp+270h+var_238]
0x180016261  mov     rax, [rcx]
0x180016264  mov     rax, [rax+10h]
0x180016268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001626d  mov     rcx, [rsp+270h+ppvOut]
0x180016272  mov     rax, [rcx]
0x180016275  mov     rax, [rax+10h]
0x180016279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001627e  mov     rcx, [rsp+270h+var_228]
0x180016283  mov     rax, [rcx]
0x180016286  mov     rax, [rax+10h]
0x18001628a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001628f  mov     rcx, [rsp+270h+var_240]
0x180016294  mov     rax, [rcx]
0x180016297  mov     rax, [rax+10h]
0x18001629b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162a0  xor     eax, eax
0x1800162a2  mov     rcx, [rbp+170h+var_10]
0x1800162a9  xor     rcx, rsp; StackCookie
0x1800162ac  call    __security_check_cookie
0x1800162b1  mov     rbx, [rsp+270h+arg_8]
0x1800162b9  add     rsp, 270h
0x1800162c0  pop     rbp
0x1800162c1  retn
```
