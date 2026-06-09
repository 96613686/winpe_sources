# winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x18000e740`
- end: `0x18000e980`
- name: `??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `576`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `14`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000e678`
- `0x18000e6a0`
- `0x18000e6c8`
- `0x18000e6f0`
- `0x18000e718`
- `0x18000e988`
- `0x18000e9b0`
- `0x18000e9d8`
- `0x18000ea00`
- `0x18000ea28`
- `0x18000ea50`
- `0x18000ea78`
- `0x18000eaa0`
- `0x180010e04`

## callees

- `0x180002cb7`
- `0x180002ce7`
- `0x180002d0b`
- `0x180003989`
- `0x1800039ad`
- `0x180007eac`
- `0x180008194`
- `0x180008274`
- `0x1800083ec`
- `0x18000e740`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e979`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000e979`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000e8cc`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000e8cc`

## pseudocode

```c
__int64 __fastcall winrt::hresult_error::hresult_error(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  BSTR *v7; // rbx
  BSTR v8; // r14
  BSTR v9; // r15
  BSTR v10; // rdi
  void (__fastcall *v11)(BSTR, __int64); // r14
  void (__fastcall ***v12)(_QWORD, __int64 *, BSTR *); // rcx
  volatile signed __int32 *v13; // rbx
  UINT v14; // r14d
  BSTR v15; // r15
  OLECHAR *v16; // rbx
  unsigned int v17; // edx
  int v18; // eax
  HANDLE ProcessHeap; // rax
  BSTR pbstr; // [rsp+20h] [rbp-10h] BYREF
  BSTR v22; // [rsp+28h] [rbp-8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp+30h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = -1430532899;
  *(_DWORD *)(a1 + 12) = a2;
  v7 = (BSTR *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  if ( pperrinfo )
  {
    pbstr = 0;
    ((void (__fastcall *)(IErrorInfo *, __int64 *, BSTR *))pperrinfo->lpVtbl->QueryInterface)(
      pperrinfo,
      winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>,
      &pbstr);
    v8 = pbstr;
    v22 = pbstr;
  }
  else
  {
    v22 = 0;
    v8 = 0;
  }
  if ( v7 == &v22 )
  {
    v9 = *v7;
    if ( v8 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v22);
  }
  else
  {
    if ( *v7 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v7);
    *v7 = v8;
    v9 = v8;
  }
  if ( v9 )
  {
    v10 = *v7;
    v11 = *(void (__fastcall **)(BSTR, __int64))(*(_QWORD *)*v7 + 32LL);
    if ( *(_QWORD *)a1 )
    {
      WINRT_IMPL_SysFreeString(*(BSTR *)a1);
      *(_QWORD *)a1 = 0;
    }
    v11(v10, a1);
    v12 = (void (__fastcall ***)(_QWORD, __int64 *, BSTR *))*v7;
    if ( *v7 )
    {
      pbstr = 0;
      (**v12)(v12, winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>, &pbstr);
      if ( pbstr )
      {
        (*(void (__fastcall **)(BSTR, _QWORD))(*(_QWORD *)pbstr + 40LL))(pbstr, 0);
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&pbstr);
      }
    }
  }
  else
  {
    pbstr = 0;
    if ( pperrinfo )
    {
      ((void (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &pbstr);
      v13 = 0;
      if ( pbstr )
      {
        v14 = SysStringLen_0(pbstr);
        v15 = pbstr;
        v16 = &pbstr[v14 - 1];
        if ( v14 )
        {
          while ( (unsigned int)_o_iswspace(*v16) )
          {
            --v16;
            if ( !--v14 )
              goto LABEL_21;
          }
          v13 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v14, v17);
          memcpy_s((void *const)(v13 + 7), 2LL * v14, v15, 2LL * v14);
        }
        else
        {
LABEL_21:
          v13 = 0;
        }
      }
    }
    else
    {
      v13 = 0;
    }
    winrt::hresult_error::originate(a1, a2, v13, a4);
    if ( v13 )
    {
      v18 = _InterlockedDecrement(v13 + 6);
      if ( v18 )
      {
        if ( v18 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v13);
      }
    }
    if ( pbstr )
      WINRT_IMPL_SysFreeString(pbstr);
  }
  if ( pperrinfo )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18000e740  mov     [rsp-28h+arg_8], rbx
0x18000e745  mov     [rsp-28h+arg_10], rsi
0x18000e74a  push    rbp
0x18000e74b  push    rdi
0x18000e74c  push    r12
0x18000e74e  push    r14
0x18000e750  push    r15
0x18000e752  mov     rbp, rsp
0x18000e755  sub     rsp, 30h
0x18000e759  mov     r12, r9
0x18000e75c  mov     edi, edx
0x18000e75e  mov     rsi, rcx
0x18000e761  mov     qword ptr [rcx], 0
0x18000e768  mov     dword ptr [rcx+8], 0AABBCCDDh
0x18000e76f  mov     [rcx+0Ch], edx
0x18000e772  lea     rbx, [rcx+10h]
0x18000e776  mov     qword ptr [rbx], 0
0x18000e77d  mov     [rbp+pperrinfo], 0
0x18000e785  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000e789  xor     ecx, ecx; dwReserved
0x18000e78b  call    GetErrorInfo_0
0x18000e790  mov     rcx, [rbp+pperrinfo]
0x18000e794  test    rcx, rcx
0x18000e797  jnz     short loc_18000E7A2
0x18000e799  mov     [rbp+var_8], rcx
0x18000e79d  xor     r14d, r14d
0x18000e7a0  jmp     short loc_18000E7C8
0x18000e7a2  mov     [rbp+pbstr], 0
0x18000e7aa  mov     rax, [rcx]
0x18000e7ad  lea     r8, [rbp+pbstr]
0x18000e7b1  lea     rdx, ??$guid_v@UIRestrictedErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IRestrictedErrorInfo>
0x18000e7b8  mov     rax, [rax]
0x18000e7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7c0  mov     r14, [rbp+pbstr]
0x18000e7c4  mov     [rbp+var_8], r14
0x18000e7c8  lea     rax, [rbp+var_8]
0x18000e7cc  cmp     rbx, rax
0x18000e7cf  jz      short loc_18000E7E7
0x18000e7d1  cmp     qword ptr [rbx], 0
0x18000e7d5  jz      short loc_18000E7DF
0x18000e7d7  mov     rcx, rbx
0x18000e7da  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000e7df  mov     [rbx], r14
0x18000e7e2  mov     r15, r14
0x18000e7e5  jmp     short loc_18000E7F8
0x18000e7e7  mov     r15, [rbx]
0x18000e7ea  test    r14, r14
0x18000e7ed  jz      short loc_18000E7F8
0x18000e7ef  lea     rcx, [rbp+var_8]
0x18000e7f3  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000e7f8  test    r15, r15
0x18000e7fb  jz      loc_18000E884
0x18000e801  mov     rdi, [rbx]
0x18000e804  mov     rax, [rdi]
0x18000e807  mov     r14, [rax+20h]
0x18000e80b  mov     rcx, [rsi]; bstrString
0x18000e80e  test    rcx, rcx
0x18000e811  jz      short loc_18000E81F
0x18000e813  call    WINRT_IMPL_SysFreeString
0x18000e818  mov     qword ptr [rsi], 0
0x18000e81f  mov     rdx, rsi
0x18000e822  mov     rcx, rdi
0x18000e825  mov     rax, r14
0x18000e828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e82d  mov     rcx, [rbx]
0x18000e830  test    rcx, rcx
0x18000e833  jz      loc_18000E94B
0x18000e839  mov     [rbp+pbstr], 0
0x18000e841  mov     rax, [rcx]
0x18000e844  lea     r8, [rbp+pbstr]
0x18000e848  lea     rdx, ??$guid_v@UILanguageExceptionErrorInfo2@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::ILanguageExceptionErrorInfo2>
0x18000e84f  mov     rax, [rax]
0x18000e852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e857  mov     rcx, [rbp+pbstr]
0x18000e85b  mov     [rbp+pbstr], rcx
0x18000e85f  test    rcx, rcx
0x18000e862  jz      loc_18000E94B
0x18000e868  mov     rax, [rcx]
0x18000e86b  xor     edx, edx
0x18000e86d  mov     rax, [rax+28h]
0x18000e871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e876  lea     rcx, [rbp+pbstr]
0x18000e87a  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000e87f  jmp     loc_18000E94B
0x18000e884  mov     [rbp+pbstr], 0
0x18000e88c  mov     rcx, [rbp+pperrinfo]
0x18000e890  test    rcx, rcx
0x18000e893  jz      short loc_18000E906
0x18000e895  mov     rax, [rcx]
0x18000e898  lea     rdx, [rbp+pbstr]
0x18000e89c  mov     rax, [rax+28h]
0x18000e8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a5  xor     ebx, ebx
0x18000e8a7  mov     rcx, [rbp+pbstr]; pbstr
0x18000e8ab  test    rcx, rcx
0x18000e8ae  jz      short loc_18000E908
0x18000e8b0  call    SysStringLen_0
0x18000e8b5  mov     r14d, eax
0x18000e8b8  mov     r15, [rbp+pbstr]
0x18000e8bc  mov     ebx, eax
0x18000e8be  dec     rbx
0x18000e8c1  lea     rbx, [r15+rbx*2]
0x18000e8c5  test    eax, eax
0x18000e8c7  jz      short loc_18000E8E0
0x18000e8c9  movzx   ecx, word ptr [rbx]
0x18000e8cc  call    cs:__imp__o_iswspace
0x18000e8d2  test    eax, eax
0x18000e8d4  jz      short loc_18000E8E4
0x18000e8d6  sub     rbx, 2
0x18000e8da  add     r14d, 0FFFFFFFFh
0x18000e8de  jnz     short loc_18000E8C9
0x18000e8e0  xor     ebx, ebx
0x18000e8e2  jmp     short loc_18000E908
0x18000e8e4  mov     ecx, r14d; this
0x18000e8e7  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18000e8ec  mov     rbx, rax
0x18000e8ef  mov     edx, r14d
0x18000e8f2  add     rdx, rdx; DestinationSize
0x18000e8f5  lea     rcx, [rax+1Ch]; Destination
0x18000e8f9  mov     r9, rdx; SourceSize
0x18000e8fc  mov     r8, r15; Source
0x18000e8ff  call    memcpy_s
0x18000e904  jmp     short loc_18000E8E2
0x18000e906  xor     ebx, ebx
0x18000e908  mov     r9, r12
0x18000e90b  mov     r8, rbx
0x18000e90e  mov     edx, edi
0x18000e910  mov     rcx, rsi
0x18000e913  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18000e918  test    rbx, rbx
0x18000e91b  jz      short loc_18000E93D
0x18000e91d  or      eax, 0FFFFFFFFh
0x18000e920  lock xadd [rbx+18h], eax
0x18000e925  sub     eax, 1
0x18000e928  jnz     short loc_18000E975
0x18000e92a  nop
0x18000e92b  call    WINRT_IMPL_GetProcessHeap
0x18000e930  mov     rcx, rax; hHeap
0x18000e933  mov     r8, rbx; lpMem
0x18000e936  xor     edx, edx; dwFlags
0x18000e938  call    WINRT_IMPL_HeapFree
0x18000e93d  mov     rcx, [rbp+pbstr]; bstrString
0x18000e941  test    rcx, rcx
0x18000e944  jz      short loc_18000E94B
0x18000e946  call    WINRT_IMPL_SysFreeString
0x18000e94b  cmp     [rbp+pperrinfo], 0
0x18000e950  jz      short loc_18000E95B
0x18000e952  lea     rcx, [rbp+pperrinfo]
0x18000e956  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000e95b  mov     rax, rsi
0x18000e95e  mov     rbx, [rsp+30h+arg_8]
0x18000e963  mov     rsi, [rsp+30h+arg_10]
0x18000e968  add     rsp, 30h
0x18000e96c  pop     r15
0x18000e96e  pop     r14
0x18000e970  pop     r12
0x18000e972  pop     rdi
0x18000e973  pop     rbp
0x18000e974  retn
0x18000e975  test    eax, eax
0x18000e977  jns     short loc_18000E93D
0x18000e979  call    cs:__imp_abort
```
