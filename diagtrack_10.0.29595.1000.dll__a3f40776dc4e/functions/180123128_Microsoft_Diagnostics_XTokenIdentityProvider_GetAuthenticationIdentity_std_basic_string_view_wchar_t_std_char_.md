# Microsoft::Diagnostics::XTokenIdentityProvider::GetAuthenticationIdentity(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180123128`
- end: `0x180123334`
- name: `?GetAuthenticationIdentity@XTokenIdentityProvider@Diagnostics@Microsoft@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `524`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::XTokenIdentityProvider *this, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801498e8`

## callees

- `0x180024558`
- `0x18002abec`
- `0x18002be90`
- `0x18002cae0`
- `0x18002df00`
- `0x1800482ac`
- `0x180123128`
- `0x18012333c`
- `0x180123378`
- `0x1801288a0`
- `0x18020aac0`
- `0x18027b41c`
- `0x180369010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18012329a`
- `msvcp_win!_Mtx_unlock` at `0x18012329a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801232ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801232f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801232ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801232f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180123300`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void *__fastcall Microsoft::Diagnostics::XTokenIdentityProvider::GetAuthenticationIdentity(
        Microsoft::Diagnostics::XTokenIdentityProvider *this,
        void *a2,
        _QWORD *a3)
{
  Microsoft::Diagnostics::XTokenIdentityProvider *v6; // rcx
  int v7; // ebx
  unsigned int i; // r15d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD, const WCHAR *, __int128 *, _QWORD, _QWORD, _DWORD, Microsoft::Diagnostics::XTokenIdentityProvider **, LPVOID *); // rbx
  __int128 *v11; // rcx
  Microsoft::Diagnostics::XTokenIdentityProvider *v12; // rcx
  Microsoft::Diagnostics::XTokenIdentityProvider *v14; // [rsp+60h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-31h] BYREF
  int v16; // [rsp+70h] [rbp-29h]
  _Mtx_t v17; // [rsp+78h] [rbp-21h] BYREF
  char v18; // [rsp+80h] [rbp-19h]
  void *v19; // [rsp+88h] [rbp-11h]
  __int128 v20; // [rsp+90h] [rbp-9h] BYREF
  __int128 v21; // [rsp+A0h] [rbp+7h]

  v19 = a2;
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v17, this);
  std::wstring::wstring(a2);
  v16 = 1;
  if ( !*((_BYTE *)this + 80) )
  {
    v7 = -2147467259;
    for ( i = 0; i < 3; ++i )
    {
      if ( Microsoft::Diagnostics::XTokenIdentityProvider::EnsureXblAuthManager(this) )
      {
        v14 = 0;
        pv = 0;
        v9 = *((_QWORD *)this + 11);
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const WCHAR *, __int128 *, _QWORD, _QWORD, _DWORD, Microsoft::Diagnostics::XTokenIdentityProvider **, LPVOID *))(*(_QWORD *)v9 + 104LL);
        pv = 0;
        v14 = 0;
        v20 = 0;
        v21 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v20, *a3, a3[1]);
        v11 = &v20;
        if ( *((_QWORD *)&v21 + 1) > 7u )
          v11 = (__int128 *)v20;
        v7 = v10(v9, 0, 0, L"POST", v11, 0, 0, 0, &v14, &pv);
        std::wstring::_Tidy_deallocate(&v20);
        if ( v7 >= 0 )
        {
          std::wstring::assign(a2, v14);
          if ( pv )
            CoTaskMemFree(pv);
          v6 = v14;
          if ( v14 )
            CoTaskMemFree(v14);
          break;
        }
        if ( !Microsoft::Diagnostics::XTokenIdentityProvider::IsRpcError(v12, v7) )
        {
          __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&pv);
          __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&v14);
          break;
        }
        wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset((char *)this + 88);
        if ( pv )
          CoTaskMemFree(pv);
        v6 = v14;
        if ( v14 )
          CoTaskMemFree(v14);
      }
    }
    if ( Microsoft::Diagnostics::XTokenIdentityProvider::IsRpcError(v6, v7) )
      Microsoft::Diagnostics::XTokenIdentityProvider::DisableXblAuthManager(this);
  }
  if ( v18 )
    _Mtx_unlock(v17);
  return a2;
}

```

## disassembly

```asm
0x180123128  mov     [rsp-8+arg_18], rbx
0x18012312d  push    rbp
0x18012312e  push    rsi
0x18012312f  push    rdi
0x180123130  push    r12
0x180123132  push    r13
0x180123134  push    r14
0x180123136  push    r15
0x180123138  lea     rbp, [rsp-27h]
0x18012313d  sub     rsp, 0C0h
0x180123144  mov     rax, cs:__security_cookie
0x18012314b  xor     rax, rsp
0x18012314e  mov     [rbp+57h+var_40], rax
0x180123152  mov     r13, r8
0x180123155  mov     rsi, rdx
0x180123158  mov     r14, rcx
0x18012315b  mov     [rbp+57h+var_68], rdx
0x18012315f  mov     [rbp+57h+var_80], 0
0x180123166  mov     rdx, rcx
0x180123169  lea     rcx, [rbp+57h+var_78]
0x18012316d  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180123172  nop
0x180123173  mov     rcx, rsi; void *
0x180123176  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012317b  mov     [rbp+57h+var_80], 1
0x180123182  cmp     byte ptr [r14+50h], 0
0x180123187  jnz     loc_180123290
0x18012318d  mov     ebx, 80004005h
0x180123192  xor     r15d, r15d
0x180123195  cmp     r15d, 3
0x180123199  jnb     loc_180123281
0x18012319f  mov     rcx, r14; this
0x1801231a2  call    ?EnsureXblAuthManager@XTokenIdentityProvider@Diagnostics@Microsoft@@AEAA_NXZ; Microsoft::Diagnostics::XTokenIdentityProvider::EnsureXblAuthManager(void)
0x1801231a7  test    al, al
0x1801231a9  jz      loc_180123306
0x1801231af  mov     [rbp+57h+var_90], 0
0x1801231b7  mov     [rbp+57h+pv], 0
0x1801231bf  mov     rdi, [r14+58h]
0x1801231c3  mov     rax, [rdi]
0x1801231c6  mov     rbx, [rax+68h]
0x1801231ca  mov     [rbp+57h+pv], 0
0x1801231d2  mov     [rbp+57h+var_90], 0
0x1801231da  xorps   xmm0, xmm0
0x1801231dd  movups  [rbp+57h+var_60], xmm0
0x1801231e1  xorps   xmm1, xmm1
0x1801231e4  movdqu  [rbp+57h+var_50], xmm1
0x1801231e9  mov     r8, [r13+8]
0x1801231ed  mov     rdx, [r13+0]
0x1801231f1  lea     rcx, [rbp+57h+var_60]
0x1801231f5  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1801231fa  nop
0x1801231fb  lea     rcx, [rbp+57h+var_60]
0x1801231ff  cmp     qword ptr [rbp+57h+var_50+8], 7
0x180123204  cmova   rcx, qword ptr [rbp+57h+var_60]
0x180123209  lea     rax, [rbp+57h+pv]
0x18012320d  mov     [rsp+0F0h+var_A8], rax
0x180123212  lea     rax, [rbp+57h+var_90]
0x180123216  mov     [rsp+0F0h+var_B0], rax
0x18012321b  xor     eax, eax
0x18012321d  mov     [rsp+0F0h+var_B8], eax
0x180123221  mov     [rsp+0F0h+var_C0], rax
0x180123226  mov     [rsp+0F0h+var_C8], rax
0x18012322b  mov     [rsp+0F0h+var_D0], rcx
0x180123230  lea     r9, pwszVerb; "POST"
0x180123237  xor     r8d, r8d
0x18012323a  xor     edx, edx
0x18012323c  mov     rcx, rdi
0x18012323f  mov     rax, rbx
0x180123242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123247  mov     ebx, eax
0x180123249  lea     rcx, [rbp+57h+var_60]
0x18012324d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180123252  mov     eax, ebx
0x180123254  shr     eax, 1Fh
0x180123257  xor     al, 1
0x180123259  jz      short loc_1801232D2
0x18012325b  mov     rdx, [rbp+57h+var_90]
0x18012325f  mov     rcx, rsi
0x180123262  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180123267  nop
0x180123268  mov     rcx, [rbp+57h+pv]; pv
0x18012326c  test    rcx, rcx
0x18012326f  jz      short loc_180123278
0x180123271  call    cs:__imp_CoTaskMemFree
0x180123277  nop
0x180123278  mov     rcx, [rbp+57h+var_90]; this
0x18012327c  test    rcx, rcx
0x18012327f  jnz     short loc_1801232CA
0x180123281  mov     edx, ebx; int
0x180123283  call    ?IsRpcError@XTokenIdentityProvider@Diagnostics@Microsoft@@AEAA_NJ@Z; Microsoft::Diagnostics::XTokenIdentityProvider::IsRpcError(long)
0x180123288  test    al, al
0x18012328a  jnz     loc_180123326
0x180123290  cmp     [rbp+57h+var_70], 0
0x180123294  jz      short loc_1801232A0
0x180123296  mov     rcx, [rbp+57h+var_78]; _Mtx_t
0x18012329a  call    cs:__imp__Mtx_unlock
0x1801232a0  mov     rax, rsi
0x1801232a3  mov     rcx, [rbp+57h+var_40]
0x1801232a7  xor     rcx, rsp; StackCookie
0x1801232aa  call    __security_check_cookie
0x1801232af  mov     rbx, [rsp+0F0h+arg_18]
0x1801232b7  add     rsp, 0C0h
0x1801232be  pop     r15
0x1801232c0  pop     r14
0x1801232c2  pop     r13
0x1801232c4  pop     r12
0x1801232c6  pop     rdi
0x1801232c7  pop     rsi
0x1801232c8  pop     rbp
0x1801232c9  retn
0x1801232ca  call    cs:__imp_CoTaskMemFree
0x1801232d0  jmp     short loc_180123281
0x1801232d2  mov     edx, ebx; int
0x1801232d4  call    ?IsRpcError@XTokenIdentityProvider@Diagnostics@Microsoft@@AEAA_NJ@Z; Microsoft::Diagnostics::XTokenIdentityProvider::IsRpcError(long)
0x1801232d9  test    al, al
0x1801232db  jz      short loc_18012330E
0x1801232dd  lea     rcx, [r14+58h]
0x1801232e1  call    ?reset@?$com_ptr_t@UIProfileCollection@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IProfileCollection,wil::err_exception_policy>::reset(void)
0x1801232e6  nop
0x1801232e7  mov     rcx, [rbp+57h+pv]; pv
0x1801232eb  test    rcx, rcx
0x1801232ee  jz      short loc_1801232F7
0x1801232f0  call    cs:__imp_CoTaskMemFree
0x1801232f6  nop
0x1801232f7  mov     rcx, [rbp+57h+var_90]; pv
0x1801232fb  test    rcx, rcx
0x1801232fe  jz      short loc_180123306
0x180123300  call    cs:__imp_CoTaskMemFree
0x180123306  inc     r15d
0x180123309  jmp     loc_180123195
0x18012330e  lea     rcx, [rbp+57h+pv]
0x180123312  call    ??1?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
0x180123317  nop
0x180123318  lea     rcx, [rbp+57h+var_90]
0x18012331c  call    ??1?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
0x180123321  jmp     loc_180123281
0x180123326  mov     rcx, r14; this
0x180123329  call    ?DisableXblAuthManager@XTokenIdentityProvider@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::XTokenIdentityProvider::DisableXblAuthManager(void)
0x18012332e  jmp     loc_180123290
```
