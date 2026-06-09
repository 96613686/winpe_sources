# CLTApp::OnDelete(ISimpleTableWrite *,ISimpleTableControl *,__MIDL___MIDL_itf_registrar_0000_0000_0001,ulong,ulong)

- ea: `0x18003b83c`
- end: `0x18003bb76`
- name: `?OnDelete@CLTApp@@AEAAJPEAUISimpleTableWrite@@PEAUISimpleTableControl@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@KK@Z`
- size: `826`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ef60`

## callees

- `0x18003a8b4`
- `0x18003ae88`
- `0x18003b36c`
- `0x18003b83c`
- `0x18003eda0`
- `0x180043c9c`
- `0x180043cd4`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003b9c2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003b9d6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003b9ea`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003b9c2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003b9d6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003b9ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTApp::OnDelete(CLTApp *a1, __int64 a2, __int64 a3, int a4, unsigned int a5, unsigned int a6)
{
  unsigned int v8; // r14d
  int Dispenser; // ebx
  int v10; // edi
  PSID v11; // rbx
  const struct _GUID *v12; // rdx
  CLTApp *v13; // rcx
  struct ISimpleTableDispenser *v14; // rdi
  const struct _GUID *v15; // rdx
  CLTApp *v16; // rcx
  const struct _GUID *v17; // rdx
  CLTApp *v18; // rcx
  const struct _GUID *v19; // rdx
  CLTApp *v20; // rcx
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  void *v23; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+54h] [rbp-ACh] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-A0h] BYREF
  struct ISimpleTableDispenser *v28; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v29[2]; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+84h] [rbp-7Ch]
  _QWORD v32[2]; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+9Ch] [rbp-64h]
  void *v35; // [rsp+A0h] [rbp-60h] BYREF
  int v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+ACh] [rbp-54h]
  int v38; // [rsp+B0h] [rbp-50h]
  int v39; // [rsp+B4h] [rbp-4Ch]
  int *v40; // [rsp+B8h] [rbp-48h] BYREF
  int v41; // [rsp+C0h] [rbp-40h]
  int v42; // [rsp+C4h] [rbp-3Ch]
  int v43; // [rsp+C8h] [rbp-38h]
  int v44; // [rsp+CCh] [rbp-34h]
  void *v45; // [rsp+D0h] [rbp-30h]
  int v46; // [rsp+D8h] [rbp-28h]
  int v47; // [rsp+DCh] [rbp-24h]
  int v48; // [rsp+E0h] [rbp-20h]
  int v49; // [rsp+E4h] [rbp-1Ch]
  struct _GUID v50; // [rsp+F0h] [rbp-10h] BYREF
  PSID pSid1; // [rsp+100h] [rbp+0h] BYREF
  int v52; // [rsp+108h] [rbp+8h]

  v28 = 0;
  v22 = 0;
  v25 = 0;
  v23 = 0;
  v24 = 1;
  v8 = 0x200000;
  if ( a4 != 1 )
    v8 = 0x400000;
  v40 = &v24;
  v41 = 0;
  v42 = -268435451;
  v43 = 19;
  v44 = 4;
  v45 = 0;
  v46 = 0;
  v47 = 9;
  v48 = 72;
  v49 = 16;
  v29[0] = 0;
  v29[1] = 0;
  v30 = 72;
  v31 = 16;
  v32[0] = 0;
  v32[1] = 0;
  v33 = 72;
  v34 = 16;
  v35 = 0;
  v36 = 0;
  v37 = 2;
  v38 = 72;
  v39 = 16;
  v27 = 0;
  v26 = 0;
  Dispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, _QWORD, int *, void **))(*(_QWORD *)a2 + 152LL))(
                a2,
                0,
                &v22,
                0,
                &v25,
                &v23);
  if ( Dispenser >= 0 )
  {
    Dispenser = (*(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD, int *, unsigned __int16 **))(*(_QWORD *)a2 + 152LL))(
                  a2,
                  8,
                  &v22,
                  0,
                  &v26,
                  &v27);
    if ( Dispenser >= 0 )
    {
      v10 = 1;
      pSid1 = 0;
      v52 = 0;
      if ( (int)CSid::InitializeFromName((CSid *)&pSid1, v27) >= 0 )
      {
        v11 = pSid1;
        if ( EqualSid(pSid1, &CSid::x_sidSystem)
          || EqualSid(v11, &CSid::x_sidLocalService)
          || EqualSid(v11, &CSid::x_sidNetworkService) )
        {
          v10 = 0;
        }
      }
      CSid::Initialize((CSid *)&pSid1);
      if ( !v10
        || (v50 = *(struct _GUID *)v23, Dispenser = CLTApp::AddToIdentityList(a1, &v50, 0, 0, 0), Dispenser >= 0) )
      {
        v45 = v23;
        v29[0] = v23;
        v32[0] = v23;
        v35 = v23;
        Dispenser = CLTApp::GetDispenser(a1, &v28);
        v14 = v28;
        if ( Dispenser >= 0 )
        {
          if ( a6 && !a5 || (Dispenser = CLTApp::ResetPropsToAllowDeletion(v13, v23, v28, a5, a6), Dispenser >= 0) )
          {
            Dispenser = CLTApp::DeleteQuery(
                          v13,
                          v12,
                          &tidCOMSERVICES_CLASSES,
                          v14,
                          (struct __MIDL___MIDL_itf_stable_0000_0000_0002 *)&v40,
                          2u,
                          v8);
            if ( Dispenser >= 0 )
            {
              Dispenser = CLTApp::DeleteQuery(
                            v16,
                            v15,
                            &tidCOMSERVICES_LT_ROLEDEFINITION,
                            v14,
                            (struct __MIDL___MIDL_itf_stable_0000_0000_0002 *)v29,
                            1u,
                            0);
              if ( Dispenser >= 0 )
              {
                Dispenser = CLTApp::DeleteQuery(
                              v18,
                              v17,
                              &tidCOMSERVICES_SERVICES,
                              v14,
                              (struct __MIDL___MIDL_itf_stable_0000_0000_0002 *)v32,
                              1u,
                              0);
                if ( Dispenser >= 0 )
                  Dispenser = CLTApp::DeleteQuery(
                                v20,
                                v19,
                                &tidCOMSERVICES_LEGACYCLASSES_INTERNAL,
                                v14,
                                (struct __MIDL___MIDL_itf_stable_0000_0000_0002 *)&v35,
                                1u,
                                0);
              }
            }
          }
        }
        if ( v14 )
          (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
  }
  return (unsigned int)Dispenser;
}

```

## disassembly

```asm
0x18003b83c  mov     [rsp-8+arg_10], rbx
0x18003b841  mov     [rsp-8+arg_18], rsi
0x18003b846  push    rbp
0x18003b847  push    rdi
0x18003b848  push    r12
0x18003b84a  push    r14
0x18003b84c  push    r15
0x18003b84e  lea     rbp, [rsp-250h]
0x18003b856  sub     rsp, 350h
0x18003b85d  mov     rax, cs:__security_cookie
0x18003b864  xor     rax, rsp
0x18003b867  mov     [rbp+270h+var_30], rax
0x18003b86e  mov     rdi, rdx
0x18003b871  mov     rsi, rcx
0x18003b874  xor     r15d, r15d
0x18003b877  mov     [rsp+370h+var_308], r15
0x18003b87c  mov     [rsp+370h+var_330], r15d
0x18003b881  mov     [rsp+370h+var_31C], r15d
0x18003b886  mov     [rsp+370h+var_328], r15
0x18003b88b  lea     r12d, [r15+1]
0x18003b88f  mov     [rsp+370h+var_320], r12d
0x18003b894  mov     eax, 400000h
0x18003b899  mov     r14d, 200000h
0x18003b89f  cmp     r9d, r12d
0x18003b8a2  cmovnz  r14d, eax
0x18003b8a6  lea     rax, [rsp+370h+var_320]
0x18003b8ab  mov     [rbp+270h+var_2B8], rax
0x18003b8af  mov     [rbp+270h+var_2B0], r15d
0x18003b8b3  mov     [rbp+270h+var_2AC], 0F0000005h
0x18003b8ba  mov     [rbp+270h+var_2A8], 13h
0x18003b8c1  mov     [rbp+270h+var_2A4], 4
0x18003b8c8  mov     [rbp+270h+var_2A0], r15
0x18003b8cc  mov     [rbp+270h+var_298], r15d
0x18003b8d0  mov     [rbp+270h+var_294], 9
0x18003b8d7  lea     ecx, [r15+48h]
0x18003b8db  mov     [rbp+270h+var_290], ecx
0x18003b8de  lea     eax, [rcx-38h]
0x18003b8e1  mov     [rbp+270h+var_28C], eax
0x18003b8e4  mov     [rsp+370h+var_300], r15
0x18003b8e9  mov     [rsp+370h+var_2F8], r15
0x18003b8ee  mov     [rbp+270h+var_2F0], ecx
0x18003b8f1  mov     [rbp+270h+var_2EC], eax
0x18003b8f4  mov     [rbp+270h+var_2E8], r15
0x18003b8f8  mov     [rbp+270h+var_2E0], r15
0x18003b8fc  mov     [rbp+270h+var_2D8], ecx
0x18003b8ff  mov     [rbp+270h+var_2D4], eax
0x18003b902  mov     [rbp+270h+var_2D0], r15
0x18003b906  mov     [rbp+270h+var_2C8], r15d
0x18003b90a  mov     [rbp+270h+var_2C4], 2
0x18003b911  mov     [rbp+270h+var_2C0], ecx
0x18003b914  mov     [rbp+270h+var_2BC], eax
0x18003b917  mov     [rsp+370h+var_310], r15
0x18003b91c  mov     [rsp+370h+var_318], r15d
0x18003b921  mov     rax, [rdx]
0x18003b924  lea     rcx, [rsp+370h+var_328]
0x18003b929  mov     qword ptr [rsp+370h+var_348], rcx
0x18003b92e  lea     rcx, [rsp+370h+var_31C]
0x18003b933  mov     [rsp+370h+var_350], rcx
0x18003b938  xor     r9d, r9d
0x18003b93b  lea     r8, [rsp+370h+var_330]
0x18003b940  xor     edx, edx
0x18003b942  mov     rcx, rdi
0x18003b945  mov     rax, [rax+98h]
0x18003b94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b951  mov     ebx, eax
0x18003b953  test    eax, eax
0x18003b955  js      loc_18003BB49
0x18003b95b  mov     rax, [rdi]
0x18003b95e  lea     rcx, [rsp+370h+var_310]
0x18003b963  mov     qword ptr [rsp+370h+var_348], rcx
0x18003b968  lea     rcx, [rsp+370h+var_318]
0x18003b96d  mov     [rsp+370h+var_350], rcx
0x18003b972  xor     r9d, r9d
0x18003b975  lea     r8, [rsp+370h+var_330]
0x18003b97a  lea     edx, [r15+8]
0x18003b97e  mov     rcx, rdi
0x18003b981  mov     rax, [rax+98h]
0x18003b988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b98d  mov     ebx, eax
0x18003b98f  test    eax, eax
0x18003b991  js      loc_18003BB49
0x18003b997  mov     edi, r12d
0x18003b99a  mov     [rbp+270h+pSid1], r15
0x18003b99e  mov     [rbp+270h+var_268], r15d
0x18003b9a2  mov     rdx, [rsp+370h+var_310]; unsigned __int16 *
0x18003b9a7  lea     rcx, [rbp+270h+pSid1]; this
0x18003b9ab  call    ?InitializeFromName@CSid@@QEAAJPEAG@Z; CSid::InitializeFromName(ushort *)
0x18003b9b0  test    eax, eax
0x18003b9b2  js      short loc_18003B9F7
0x18003b9b4  lea     rdx, ?x_sidSystem@CSid@@0U_SID1@1@B; pSid2
0x18003b9bb  mov     rbx, [rbp+270h+pSid1]
0x18003b9bf  mov     rcx, rbx; pSid1
0x18003b9c2  call    cs:__imp_EqualSid
0x18003b9c8  test    eax, eax
0x18003b9ca  jnz     short loc_18003B9F4
0x18003b9cc  lea     rdx, ?x_sidLocalService@CSid@@0U_SID1@1@B; pSid2
0x18003b9d3  mov     rcx, rbx; pSid1
0x18003b9d6  call    cs:__imp_EqualSid
0x18003b9dc  test    eax, eax
0x18003b9de  jnz     short loc_18003B9F4
0x18003b9e0  lea     rdx, ?x_sidNetworkService@CSid@@0U_SID1@1@B; pSid2
0x18003b9e7  mov     rcx, rbx; pSid1
0x18003b9ea  call    cs:__imp_EqualSid
0x18003b9f0  test    eax, eax
0x18003b9f2  jz      short loc_18003B9F7
0x18003b9f4  mov     edi, r15d
0x18003b9f7  lea     rcx, [rbp+270h+pSid1]; this
0x18003b9fb  call    ?Initialize@CSid@@AEAAXXZ; CSid::Initialize(void)
0x18003ba00  test    edi, edi
0x18003ba02  jz      short loc_18003BA32
0x18003ba04  mov     rax, [rsp+370h+var_328]
0x18003ba09  movups  xmm0, xmmword ptr [rax]
0x18003ba0c  movdqu  xmmword ptr [rbp+270h+var_280.Data1], xmm0
0x18003ba11  mov     [rsp+370h+var_350], r15; unsigned __int16 *
0x18003ba16  xor     r9d, r9d; unsigned __int16 *
0x18003ba19  xor     r8d, r8d; unsigned __int16 *
0x18003ba1c  lea     rdx, [rbp+270h+var_280]; struct _GUID
0x18003ba20  mov     rcx, rsi; this
0x18003ba23  call    ?AddToIdentityList@CLTApp@@AEAAJU_GUID@@PEAG11@Z; CLTApp::AddToIdentityList(_GUID,ushort *,ushort *,ushort *)
0x18003ba28  mov     ebx, eax
0x18003ba2a  test    eax, eax
0x18003ba2c  js      loc_18003BB49
0x18003ba32  mov     rax, [rsp+370h+var_328]
0x18003ba37  mov     [rbp+270h+var_2A0], rax
0x18003ba3b  mov     [rsp+370h+var_300], rax
0x18003ba40  mov     [rbp+270h+var_2E8], rax
0x18003ba44  mov     [rbp+270h+var_2D0], rax
0x18003ba48  lea     rdx, [rsp+370h+var_308]; struct ISimpleTableDispenser **
0x18003ba4d  mov     rcx, rsi; this
0x18003ba50  call    ?GetDispenser@CLTApp@@AEAAJPEAPEAUISimpleTableDispenser@@@Z; CLTApp::GetDispenser(ISimpleTableDispenser * *)
0x18003ba55  mov     ebx, eax
0x18003ba57  mov     rdi, [rsp+370h+var_308]
0x18003ba5c  test    eax, eax
0x18003ba5e  js      loc_18003BB35
0x18003ba64  mov     r9d, [rbp+270h+arg_20]; unsigned int
0x18003ba6b  mov     eax, [rbp+270h+arg_28]
0x18003ba71  test    eax, eax
0x18003ba73  jz      short loc_18003BA7A
0x18003ba75  test    r9d, r9d
0x18003ba78  jz      short loc_18003BA95
0x18003ba7a  mov     dword ptr [rsp+370h+var_350], eax; unsigned int
0x18003ba7e  mov     r8, rdi; struct ISimpleTableDispenser *
0x18003ba81  mov     rdx, [rsp+370h+var_328]; void *
0x18003ba86  call    ?ResetPropsToAllowDeletion@CLTApp@@AEAAJPEAXPEAUISimpleTableDispenser@@KK@Z; CLTApp::ResetPropsToAllowDeletion(void *,ISimpleTableDispenser *,ulong,ulong)
0x18003ba8b  mov     ebx, eax
0x18003ba8d  test    eax, eax
0x18003ba8f  js      loc_18003BB35
0x18003ba95  mov     [rsp+370h+var_340], r14d; unsigned int
0x18003ba9a  mov     [rsp+370h+var_348], 2; unsigned int
0x18003baa2  lea     rax, [rbp+270h+var_2B8]
0x18003baa6  mov     [rsp+370h+var_350], rax; struct __MIDL___MIDL_itf_stable_0000_0000_0002 *
0x18003baab  mov     r9, rdi; struct ISimpleTableDispenser *
0x18003baae  lea     r8, tidCOMSERVICES_CLASSES; struct _GUID *
0x18003bab5  call    ?DeleteQuery@CLTApp@@AEAAJAEBU_GUID@@0PEAUISimpleTableDispenser@@PEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@KK@Z; CLTApp::DeleteQuery(_GUID const &,_GUID const &,ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0002 *,ulong,ulong)
0x18003baba  mov     ebx, eax
0x18003babc  test    eax, eax
0x18003babe  js      short loc_18003BB35
0x18003bac0  mov     [rsp+370h+var_340], r15d; unsigned int
0x18003bac5  mov     [rsp+370h+var_348], r12d; unsigned int
0x18003baca  lea     rax, [rsp+370h+var_300]
0x18003bacf  mov     [rsp+370h+var_350], rax; struct __MIDL___MIDL_itf_stable_0000_0000_0002 *
0x18003bad4  mov     r9, rdi; struct ISimpleTableDispenser *
0x18003bad7  lea     r8, tidCOMSERVICES_LT_ROLEDEFINITION; struct _GUID *
0x18003bade  call    ?DeleteQuery@CLTApp@@AEAAJAEBU_GUID@@0PEAUISimpleTableDispenser@@PEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@KK@Z; CLTApp::DeleteQuery(_GUID const &,_GUID const &,ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0002 *,ulong,ulong)
0x18003bae3  mov     ebx, eax
0x18003bae5  test    eax, eax
0x18003bae7  js      short loc_18003BB35
0x18003bae9  mov     [rsp+370h+var_340], r15d; unsigned int
0x18003baee  mov     [rsp+370h+var_348], r12d; unsigned int
0x18003baf3  lea     rax, [rbp+270h+var_2E8]
0x18003baf7  mov     [rsp+370h+var_350], rax; struct __MIDL___MIDL_itf_stable_0000_0000_0002 *
0x18003bafc  mov     r9, rdi; struct ISimpleTableDispenser *
0x18003baff  lea     r8, tidCOMSERVICES_SERVICES; struct _GUID *
0x18003bb06  call    ?DeleteQuery@CLTApp@@AEAAJAEBU_GUID@@0PEAUISimpleTableDispenser@@PEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@KK@Z; CLTApp::DeleteQuery(_GUID const &,_GUID const &,ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0002 *,ulong,ulong)
0x18003bb0b  mov     ebx, eax
0x18003bb0d  test    eax, eax
0x18003bb0f  js      short loc_18003BB35
0x18003bb11  mov     [rsp+370h+var_340], r15d; unsigned int
0x18003bb16  mov     [rsp+370h+var_348], r12d; unsigned int
0x18003bb1b  lea     rax, [rbp+270h+var_2D0]
0x18003bb1f  mov     [rsp+370h+var_350], rax; struct __MIDL___MIDL_itf_stable_0000_0000_0002 *
0x18003bb24  mov     r9, rdi; struct ISimpleTableDispenser *
0x18003bb27  lea     r8, tidCOMSERVICES_LEGACYCLASSES_INTERNAL; struct _GUID *
0x18003bb2e  call    ?DeleteQuery@CLTApp@@AEAAJAEBU_GUID@@0PEAUISimpleTableDispenser@@PEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@KK@Z; CLTApp::DeleteQuery(_GUID const &,_GUID const &,ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0002 *,ulong,ulong)
0x18003bb33  mov     ebx, eax
0x18003bb35  test    rdi, rdi
0x18003bb38  jz      short loc_18003BB49
0x18003bb3a  mov     rax, [rdi]
0x18003bb3d  mov     rcx, rdi
0x18003bb40  mov     rax, [rax+10h]
0x18003bb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb49  mov     eax, ebx
0x18003bb4b  mov     rcx, [rbp+270h+var_30]
0x18003bb52  xor     rcx, rsp; StackCookie
0x18003bb55  call    __security_check_cookie
0x18003bb5a  lea     r11, [rsp+370h+var_20]
0x18003bb62  mov     rbx, [r11+40h]
0x18003bb66  mov     rsi, [r11+48h]
0x18003bb6a  mov     rsp, r11
0x18003bb6d  pop     r15
0x18003bb6f  pop     r14
0x18003bb71  pop     r12
0x18003bb73  pop     rdi
0x18003bb74  pop     rbp
0x18003bb75  retn
```
