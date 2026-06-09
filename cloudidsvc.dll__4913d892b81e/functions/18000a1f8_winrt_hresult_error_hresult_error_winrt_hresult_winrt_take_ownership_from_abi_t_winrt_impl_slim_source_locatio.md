# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x18000a1f8`
- end: `0x18000a3d7`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `479`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `14`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000a0e8`
- `0x18000a110`
- `0x18000a138`
- `0x18000a160`
- `0x18000a188`
- `0x18000a3e0`
- `0x18000a408`
- `0x18000a430`
- `0x18000a458`
- `0x18000a480`
- `0x18000a4a8`
- `0x18000a4d0`
- `0x18000a4f8`
- `0x18000cb70`

## callees

- `0x1800025ad`
- `0x1800025c5`
- `0x18000a1f8`
- `0x18000ab64`
- `0x18000c6c0`
- `0x18000c6ec`
- `0x18000c88c`
- `0x18000cd9c`
- `0x18000ce2c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 *v4; // rsi
  __int64 v8; // rbx
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, __int64); // rbx
  void (__fastcall ***v11)(_QWORD, __int64 *, BSTR *); // rcx
  void (__fastcall **v12)(_QWORD, __int64 *, BSTR *); // rax
  IErrorInfo *v13; // rbx
  HRESULT (__stdcall *GetDescription)(IErrorInfo *, BSTR *); // rsi
  UINT v15; // eax
  IErrorInfo **v16; // rax
  IErrorInfo *v18; // [rsp+20h] [rbp-28h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-20h] BYREF
  _BYTE v20[24]; // [rsp+30h] [rbp-18h] BYREF
  BSTR pbstr; // [rsp+80h] [rbp+38h] BYREF

  *(_QWORD *)a1 = 0;
  v4 = (__int64 *)(a1 + 16);
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  pbstr = 0;
  if ( pperrinfo )
    ((void (__fastcall *)(IErrorInfo *, __int64 *, BSTR *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &pbstr);
  v8 = *(_QWORD *)winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(v4, &pbstr);
  if ( pbstr )
    winrt::com_ptr<winrt::impl::ILanguageExceptionErrorInfo2>::unconditional_release_ref(&pbstr);
  if ( v8 )
  {
    v9 = *v4;
    v10 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*v4 + 32LL);
    winrt::handle_type<winrt::impl::bstr_traits>::close(a1);
    v10(v9, a1);
    v11 = (void (__fastcall ***)(_QWORD, __int64 *, BSTR *))*v4;
    if ( *v4 )
    {
      v12 = *v11;
      pbstr = 0;
      (*v12)(v11, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &pbstr);
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::ILanguageExceptionErrorInfo2>::unconditional_release_ref(&pbstr);
      }
    }
  }
  else
  {
    v13 = pperrinfo;
    pbstr = 0;
    if ( pperrinfo )
    {
      GetDescription = pperrinfo->lpVtbl->GetDescription;
      winrt::handle_type<winrt::impl::bstr_traits>::close(&pbstr);
      ((void (__fastcall *)(IErrorInfo *, BSTR *))GetDescription)(v13, &pbstr);
      v13 = 0;
      v18 = 0;
      if ( pbstr )
      {
        v15 = SysStringLen_0(pbstr);
        v16 = (IErrorInfo **)winrt::impl::trim_hresult_message(v20, pbstr, v15);
        if ( &v18 != v16 )
        {
          v13 = *v16;
          *v16 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
          v18 = v13;
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(v20);
      }
    }
    else
    {
      v18 = 0;
    }
    winrt::hresult_error::originate(a1, a2, v13, a4, v18);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
    winrt::handle_type<winrt::impl::bstr_traits>::close(&pbstr);
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::ILanguageExceptionErrorInfo2>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000a1f8  push    rbp
0x18000a1fa  push    rbx
0x18000a1fb  push    rsi
0x18000a1fc  push    rdi
0x18000a1fd  push    r14
0x18000a1ff  push    r15
0x18000a201  mov     rbp, rsp
0x18000a204  sub     rsp, 48h
0x18000a208  mov     qword ptr [rcx], 0
0x18000a20f  lea     rsi, [rcx+10h]
0x18000a213  mov     dword ptr [rcx+8], 0AABBCCDDh
0x18000a21a  mov     edi, edx
0x18000a21c  mov     [rcx+0Ch], edx
0x18000a21f  mov     r14, rcx
0x18000a222  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000a226  mov     qword ptr [rsi], 0
0x18000a22d  xor     ecx, ecx; dwReserved
0x18000a22f  mov     [rbp+pperrinfo], 0
0x18000a237  mov     r15, r9
0x18000a23a  call    GetErrorInfo_0
0x18000a23f  mov     rcx, [rbp+pperrinfo]
0x18000a243  mov     [rbp+pbstr], 0
0x18000a24b  test    rcx, rcx
0x18000a24e  jz      short loc_18000A26E
0x18000a250  mov     rax, [rcx]
0x18000a253  lea     r8, [rbp+pbstr]
0x18000a257  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x18000a25e  mov     rax, [rax]
0x18000a261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a266  mov     rax, [rbp+pbstr]
0x18000a26a  mov     [rbp+pbstr], rax
0x18000a26e  lea     rdx, [rbp+pbstr]
0x18000a272  mov     rcx, rsi
0x18000a275  call    ??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)
0x18000a27a  cmp     [rbp+pbstr], 0
0x18000a27f  mov     rbx, [rax]
0x18000a282  jz      short loc_18000A28D
0x18000a284  lea     rcx, [rbp+pbstr]
0x18000a288  call    ?unconditional_release_ref@?$com_ptr@UILanguageExceptionErrorInfo2@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::ILanguageExceptionErrorInfo2>::unconditional_release_ref(void)
0x18000a28d  test    rbx, rbx
0x18000a290  jz      short loc_18000A309
0x18000a292  mov     rdi, [rsi]
0x18000a295  mov     rcx, r14
0x18000a298  mov     rax, [rdi]
0x18000a29b  mov     rbx, [rax+20h]
0x18000a29f  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x18000a2a4  mov     rdx, r14
0x18000a2a7  mov     rcx, rdi
0x18000a2aa  mov     rax, rbx
0x18000a2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2b2  mov     rcx, [rsi]
0x18000a2b5  test    rcx, rcx
0x18000a2b8  jz      loc_18000A3B7
0x18000a2be  mov     rax, [rcx]
0x18000a2c1  lea     r8, [rbp+pbstr]
0x18000a2c5  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x18000a2cc  mov     [rbp+pbstr], 0
0x18000a2d4  mov     rax, [rax]
0x18000a2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2dc  mov     rcx, [rbp+pbstr]
0x18000a2e0  mov     [rbp+pbstr], rcx
0x18000a2e4  test    rcx, rcx
0x18000a2e7  jz      loc_18000A3B7
0x18000a2ed  mov     rax, [rcx]
0x18000a2f0  xor     edx, edx
0x18000a2f2  mov     rax, [rax+28h]
0x18000a2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2fb  lea     rcx, [rbp+pbstr]
0x18000a2ff  call    ?unconditional_release_ref@?$com_ptr@UILanguageExceptionErrorInfo2@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::ILanguageExceptionErrorInfo2>::unconditional_release_ref(void)
0x18000a304  jmp     loc_18000A3B7
0x18000a309  mov     rbx, [rbp+pperrinfo]
0x18000a30d  mov     [rbp+pbstr], 0
0x18000a315  test    rbx, rbx
0x18000a318  jnz     short loc_18000A320
0x18000a31a  mov     [rbp+var_28], rbx
0x18000a31e  jmp     short loc_18000A395
0x18000a320  mov     rax, [rbx]
0x18000a323  lea     rcx, [rbp+pbstr]
0x18000a327  mov     rsi, [rax+28h]
0x18000a32b  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x18000a330  lea     rdx, [rbp+pbstr]
0x18000a334  mov     rcx, rbx
0x18000a337  mov     rax, rsi
0x18000a33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a33f  mov     rcx, [rbp+pbstr]; pbstr
0x18000a343  xor     ebx, ebx
0x18000a345  mov     [rbp+var_28], rbx
0x18000a349  test    rcx, rcx
0x18000a34c  jz      short loc_18000A395
0x18000a34e  call    SysStringLen_0
0x18000a353  mov     rdx, [rbp+pbstr]
0x18000a357  lea     rcx, [rbp+var_18]
0x18000a35b  mov     r8d, eax
0x18000a35e  call    ?trim_hresult_message@impl@winrt@@YA?AUhstring@2@QEBGI@Z; winrt::impl::trim_hresult_message(ushort const * const,uint)
0x18000a363  lea     rcx, [rbp+var_28]
0x18000a367  cmp     rcx, rax
0x18000a36a  jz      short loc_18000A38C
0x18000a36c  mov     rbx, [rax]
0x18000a36f  lea     rcx, [rbp+var_28]
0x18000a373  mov     qword ptr [rax], 0
0x18000a37a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000a37f  lea     rcx, [rbp+var_28]
0x18000a383  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000a388  mov     [rbp+var_28], rbx
0x18000a38c  lea     rcx, [rbp+var_18]
0x18000a390  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000a395  mov     r9, r15
0x18000a398  mov     r8, rbx
0x18000a39b  mov     edx, edi
0x18000a39d  mov     rcx, r14
0x18000a3a0  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18000a3a5  lea     rcx, [rbp+var_28]
0x18000a3a9  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000a3ae  lea     rcx, [rbp+pbstr]
0x18000a3b2  call    ?close@?$handle_type@Ubstr_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::bstr_traits>::close(void)
0x18000a3b7  cmp     [rbp+pperrinfo], 0
0x18000a3bc  jz      short loc_18000A3C7
0x18000a3be  lea     rcx, [rbp+pperrinfo]
0x18000a3c2  call    ?unconditional_release_ref@?$com_ptr@UILanguageExceptionErrorInfo2@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::ILanguageExceptionErrorInfo2>::unconditional_release_ref(void)
0x18000a3c7  mov     rax, r14
0x18000a3ca  add     rsp, 48h
0x18000a3ce  pop     r15
0x18000a3d0  pop     r14
0x18000a3d2  pop     rdi
0x18000a3d3  pop     rsi
0x18000a3d4  pop     rbx
0x18000a3d5  pop     rbp
0x18000a3d6  retn
```
