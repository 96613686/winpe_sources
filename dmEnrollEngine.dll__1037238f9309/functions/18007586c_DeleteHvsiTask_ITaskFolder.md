# DeleteHvsiTask(ITaskFolder *)

- ea: `0x18007586c`
- end: `0x180075b01`
- name: `?DeleteHvsiTask@@YAJPEAUITaskFolder@@@Z`
- size: `661`
- prototype: `__int64 __fastcall(struct ITaskFolder *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180068324`

## callees

- `0x180011724`
- `0x18001191c`
- `0x180011938`
- `0x18002e570`
- `0x18003c968`
- `0x1800434d0`
- `0x180075730`
- `0x18007574c`
- `0x18007576c`
- `0x18007578c`
- `0x18007586c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180075a49`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180075a49`
- `OLEAUT32!__imp_SysFreeString` at `0x180075981`
- `OLEAUT32!__imp_SysFreeString` at `0x180075a0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180075aa9`
- `OLEAUT32!__imp_SysFreeString` at `0x180075981`
- `OLEAUT32!__imp_SysFreeString` at `0x180075a0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180075aa9`

## string_xrefs

- `0x1800758ff`: `onecoreuap\admin\enterprisemgmt\hvsi\hvsitasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeleteHvsiTask(struct ITaskFolder *a1)
{
  __int64 v2; // rax
  unsigned int v3; // ebx
  HRESULT (__stdcall *GetFolder)(ITaskFolder *, BSTR, ITaskFolder **); // rbx
  _bstr_t *v5; // rax
  __int64 v6; // rdx
  BSTR *v7; // rbx
  BSTR v8; // rcx
  __int64 v9; // rbx
  void (__fastcall *v10)(__int64, __int64, _QWORD); // rsi
  _bstr_t *v11; // rax
  __int64 v12; // rdx
  BSTR *v13; // rbx
  BSTR v14; // rcx
  HRESULT (__stdcall *DeleteFolder)(ITaskFolder *, BSTR, LONG); // rbx
  _bstr_t *v16; // rax
  __int64 v17; // rdx
  BSTR *v18; // rbx
  BSTR v19; // rcx
  int v21; // [rsp+20h] [rbp-69h]
  void *Block; // [rsp+30h] [rbp-59h] BYREF
  __int64 v23; // [rsp+38h] [rbp-51h] BYREF
  void *v24; // [rsp+40h] [rbp-49h] BYREF
  void **v25; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int16 *v26; // [rsp+50h] [rbp-39h] BYREF
  char v27; // [rsp+58h] [rbp-31h]
  _BYTE v28[40]; // [rsp+60h] [rbp-29h] BYREF
  char v29; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v31; // [rsp+F0h] [rbp+67h] BYREF
  int PolicyUpdatedAccountId; // [rsp+F8h] [rbp+6Fh] BYREF
  int v33; // [rsp+100h] [rbp+77h] BYREF

  PolicyUpdatedAccountId = 0;
  v31 = 0;
  v33 = 0;
  v24 = 0;
  v23 = 0;
  v2 = lambda_43cc7f3db1072f3c4dab85bbf3dc270e_::_lambda_43cc7f3db1072f3c4dab85bbf3dc270e_(
         (unsigned int)&v29,
         (unsigned int)&v24,
         (unsigned int)&PolicyUpdatedAccountId,
         (unsigned int)&v31,
         (__int64)&v33);
  wil::ScopeExit__lambda_43cc7f3db1072f3c4dab85bbf3dc270e___(v28, v2);
  v25 = &v24;
  v26 = 0;
  v27 = 1;
  PolicyUpdatedAccountId = GetPolicyUpdatedAccountId(&v26);
  wil::details::out_param_t<std::unique_ptr<unsigned short [0]>>::~out_param_t<std::unique_ptr<unsigned short [0]>>((__int64)&v25);
  if ( a1 )
  {
    GetFolder = a1->lpVtbl->GetFolder;
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v23);
    v5 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"\\Microsoft\\Windows\\EnterpriseMgmt\\VirtulizationBasedIsolation");
    if ( *(_QWORD *)v5 )
      v6 = **(_QWORD **)v5;
    else
      v6 = 0;
    v31 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, __int64 *))GetFolder)(a1, v6, &v23);
    v7 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v7 )
    {
      if ( *v7 )
      {
        SysFreeString(*v7);
        *v7 = 0;
      }
      v8 = v7[1];
      if ( v8 )
      {
        operator delete(v8);
        v7[1] = 0;
      }
      operator delete(v7);
    }
    if ( v31 >= 0 )
    {
      v9 = v23;
      v10 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v23 + 120LL);
      v11 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"Virtualization based Isolation master policy change");
      if ( *(_QWORD *)v11 )
        v12 = **(_QWORD **)v11;
      else
        v12 = 0;
      v10(v9, v12, 0);
      v13 = (BSTR *)Block;
      if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v13 )
      {
        if ( *v13 )
        {
          SysFreeString(*v13);
          *v13 = 0;
        }
        v14 = v13[1];
        if ( v14 )
        {
          operator delete(v14);
          v13[1] = 0;
        }
        operator delete(v13);
      }
      RegDeleteKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\HVSICSP", 0, 0);
    }
    DeleteFolder = a1->lpVtbl->DeleteFolder;
    v16 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"\\Microsoft\\Windows\\EnterpriseMgmt\\VirtulizationBasedIsolation");
    if ( *(_QWORD *)v16 )
      v17 = **(_QWORD **)v16;
    else
      v17 = 0;
    ((void (__fastcall *)(struct ITaskFolder *, __int64, _QWORD))DeleteFolder)(a1, v17, 0);
    v18 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v18 )
    {
      if ( *v18 )
      {
        SysFreeString(*v18);
        *v18 = 0;
      }
      v19 = v18[1];
      if ( v19 )
      {
        operator delete(v19);
        v18[1] = 0;
      }
      operator delete(v18);
    }
    v3 = 0;
  }
  else
  {
    v3 = -2147467261;
    v33 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\hvsi\\hvsitasks.cpp",
      (const char *)0x80004003LL,
      v21);
  }
  wil::details::ScopeExitFn__lambda_43cc7f3db1072f3c4dab85bbf3dc270e___::_ScopeExitFn__lambda_43cc7f3db1072f3c4dab85bbf3dc270e___(v28);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v23);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v24);
  return v3;
}

```

## disassembly

```asm
0x18007586c  push    rbp
0x18007586e  push    rbx
0x18007586f  push    rsi
0x180075870  push    rdi
0x180075871  push    r12
0x180075873  push    r14
0x180075875  lea     rbp, [rsp-2Fh]
0x18007587a  sub     rsp, 0B8h
0x180075881  mov     rdi, rcx
0x180075884  xor     r14d, r14d
0x180075887  mov     [rbp+57h+arg_8], r14d
0x18007588b  mov     [rbp+57h+arg_0], r14d
0x18007588f  mov     [rbp+57h+arg_10], r14d
0x180075893  mov     [rbp+57h+var_A0], r14
0x180075897  mov     [rbp+57h+var_A8], r14
0x18007589b  lea     rax, [rbp+57h+arg_10]
0x18007589f  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800758a4  lea     r9, [rbp+57h+arg_0]
0x1800758a8  lea     r8, [rbp+57h+arg_8]
0x1800758ac  lea     rdx, [rbp+57h+var_A0]
0x1800758b0  lea     rcx, [rbp+57h+var_58]
0x1800758b4  call    _lambda_43cc7f3db1072f3c4dab85bbf3dc270e____lambda_43cc7f3db1072f3c4dab85bbf3dc270e_
0x1800758b9  mov     rdx, rax
0x1800758bc  lea     rcx, [rbp+57h+var_80]
0x1800758c0  call    wil__ScopeExit__lambda_43cc7f3db1072f3c4dab85bbf3dc270e___
0x1800758c5  nop
0x1800758c6  lea     rax, [rbp+57h+var_A0]
0x1800758ca  mov     [rbp+57h+var_98], rax
0x1800758ce  mov     [rbp+57h+var_90], r14
0x1800758d2  mov     [rbp+57h+var_88], 1
0x1800758d6  lea     rcx, [rbp+57h+var_90]; unsigned __int16 **
0x1800758da  call    ?GetPolicyUpdatedAccountId@@YAJPEAPEAG@Z; GetPolicyUpdatedAccountId(ushort * *)
0x1800758df  mov     [rbp+57h+arg_8], eax
0x1800758e2  lea     rcx, [rbp+57h+var_98]
0x1800758e6  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort [0]>>::~out_param_t<std::unique_ptr<ushort [0]>>(void)
0x1800758eb  test    rdi, rdi
0x1800758ee  jnz     short loc_180075915
0x1800758f0  mov     ebx, 80004003h
0x1800758f5  mov     [rbp+57h+arg_10], ebx
0x1800758f8  mov     rcx, [rbp+5Fh]; this
0x1800758fc  mov     r9d, ebx; char *
0x1800758ff  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\hvsi"...
0x180075906  mov     edx, 8Eh; void *
0x18007590b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075910  jmp     loc_180075AD2
0x180075915  mov     rax, [rdi]
0x180075918  mov     rbx, [rax+48h]
0x18007591c  lea     rcx, [rbp+57h+var_A8]
0x180075920  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180075925  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt\\V"...
0x18007592c  lea     rcx, [rbp+57h+Block]; this
0x180075930  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180075935  nop
0x180075936  mov     rdx, [rax]
0x180075939  test    rdx, rdx
0x18007593c  jz      short loc_180075943
0x18007593e  mov     rdx, [rdx]
0x180075941  jmp     short loc_180075946
0x180075943  mov     rdx, r14
0x180075946  lea     r8, [rbp+57h+var_A8]
0x18007594a  mov     rcx, rdi
0x18007594d  mov     rax, rbx
0x180075950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075955  mov     [rbp+57h+arg_0], eax
0x180075958  mov     r12d, 18h
0x18007595e  mov     rbx, [rbp+57h+Block]
0x180075962  test    rbx, rbx
0x180075965  jz      short loc_1800759A7
0x180075967  or      eax, 0FFFFFFFFh
0x18007596a  lock xadd [rbx+10h], eax
0x18007596f  cmp     eax, 1
0x180075972  jnz     short loc_1800759A7
0x180075974  test    rbx, rbx
0x180075977  jz      short loc_1800759A7
0x180075979  mov     rcx, [rbx]; bstrString
0x18007597c  test    rcx, rcx
0x18007597f  jz      short loc_18007598A
0x180075981  call    cs:__imp_SysFreeString
0x180075987  mov     [rbx], r14
0x18007598a  mov     rcx, [rbx+8]; Block
0x18007598e  test    rcx, rcx
0x180075991  jz      short loc_18007599C
0x180075993  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075998  mov     [rbx+8], r14
0x18007599c  mov     rdx, r12
0x18007599f  mov     rcx, rbx; Block
0x1800759a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800759a7  cmp     [rbp+57h+arg_0], r14d
0x1800759ab  jl      loc_180075A4F
0x1800759b1  mov     rbx, [rbp+57h+var_A8]
0x1800759b5  mov     rax, [rbx]
0x1800759b8  mov     rsi, [rax+78h]
0x1800759bc  lea     rdx, aVirtualization; "Virtualization based Isolation master p"...
0x1800759c3  lea     rcx, [rbp+57h+Block]; this
0x1800759c7  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800759cc  nop
0x1800759cd  mov     rdx, [rax]
0x1800759d0  test    rdx, rdx
0x1800759d3  jz      short loc_1800759DA
0x1800759d5  mov     rdx, [rdx]
0x1800759d8  jmp     short loc_1800759DD
0x1800759da  mov     rdx, r14
0x1800759dd  xor     r8d, r8d
0x1800759e0  mov     rcx, rbx
0x1800759e3  mov     rax, rsi
0x1800759e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800759eb  nop
0x1800759ec  mov     rbx, [rbp+57h+Block]
0x1800759f0  test    rbx, rbx
0x1800759f3  jz      short loc_180075A35
0x1800759f5  or      eax, 0FFFFFFFFh
0x1800759f8  lock xadd [rbx+10h], eax
0x1800759fd  cmp     eax, 1
0x180075a00  jnz     short loc_180075A35
0x180075a02  test    rbx, rbx
0x180075a05  jz      short loc_180075A35
0x180075a07  mov     rcx, [rbx]; bstrString
0x180075a0a  test    rcx, rcx
0x180075a0d  jz      short loc_180075A18
0x180075a0f  call    cs:__imp_SysFreeString
0x180075a15  mov     [rbx], r14
0x180075a18  mov     rcx, [rbx+8]; Block
0x180075a1c  test    rcx, rcx
0x180075a1f  jz      short loc_180075A2A
0x180075a21  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075a26  mov     [rbx+8], r14
0x180075a2a  mov     rdx, r12
0x180075a2d  mov     rcx, rbx; Block
0x180075a30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075a35  xor     r9d, r9d; Reserved
0x180075a38  xor     r8d, r8d; samDesired
0x180075a3b  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\HVSICSP"
0x180075a42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075a49  call    cs:__imp_RegDeleteKeyExW
0x180075a4f  mov     rax, [rdi]
0x180075a52  mov     rbx, [rax+60h]
0x180075a56  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\EnterpriseMgmt\\V"...
0x180075a5d  lea     rcx, [rbp+57h+Block]; this
0x180075a61  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180075a66  nop
0x180075a67  mov     rdx, [rax]
0x180075a6a  test    rdx, rdx
0x180075a6d  jz      short loc_180075A74
0x180075a6f  mov     rdx, [rdx]
0x180075a72  jmp     short loc_180075A77
0x180075a74  mov     rdx, r14
0x180075a77  xor     r8d, r8d
0x180075a7a  mov     rcx, rdi
0x180075a7d  mov     rax, rbx
0x180075a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a85  nop
0x180075a86  mov     rbx, [rbp+57h+Block]
0x180075a8a  test    rbx, rbx
0x180075a8d  jz      short loc_180075ACF
0x180075a8f  or      eax, 0FFFFFFFFh
0x180075a92  lock xadd [rbx+10h], eax
0x180075a97  cmp     eax, 1
0x180075a9a  jnz     short loc_180075ACF
0x180075a9c  test    rbx, rbx
0x180075a9f  jz      short loc_180075ACF
0x180075aa1  mov     rcx, [rbx]; bstrString
0x180075aa4  test    rcx, rcx
0x180075aa7  jz      short loc_180075AB2
0x180075aa9  call    cs:__imp_SysFreeString
0x180075aaf  mov     [rbx], r14
0x180075ab2  mov     rcx, [rbx+8]; Block
0x180075ab6  test    rcx, rcx
0x180075ab9  jz      short loc_180075AC4
0x180075abb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075ac0  mov     [rbx+8], r14
0x180075ac4  mov     rdx, r12
0x180075ac7  mov     rcx, rbx; Block
0x180075aca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075acf  mov     ebx, r14d
0x180075ad2  lea     rcx, [rbp+57h+var_80]
0x180075ad6  call    wil__details__ScopeExitFn__lambda_43cc7f3db1072f3c4dab85bbf3dc270e______ScopeExitFn__lambda_43cc7f3db1072f3c4dab85bbf3dc270e___
0x180075adb  nop
0x180075adc  lea     rcx, [rbp+57h+var_A8]
0x180075ae0  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180075ae5  nop
0x180075ae6  lea     rcx, [rbp+57h+var_A0]
0x180075aea  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180075aef  mov     eax, ebx
0x180075af1  add     rsp, 0B8h
0x180075af8  pop     r14
0x180075afa  pop     r12
0x180075afc  pop     rdi
0x180075afd  pop     rsi
0x180075afe  pop     rbx
0x180075aff  pop     rbp
0x180075b00  retn
```
