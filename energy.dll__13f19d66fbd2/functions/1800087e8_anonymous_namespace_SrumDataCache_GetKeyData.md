# _anonymous_namespace_::SrumDataCache::GetKeyData

- ea: `0x1800087e8`
- end: `0x180008a44`
- name: `_anonymous_namespace_::SrumDataCache::GetKeyData`
- size: `604`
- prototype: `__int64 __fastcall(_Mtx_t)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180007590`
- `0x180007920`

## callees

- `0x1800087e8`
- `0x18000b6f0`
- `0x1800247c0`
- `0x180025278`
- `0x180029118`
- `0x1800431d8`
- `0x1800433e8`
- `0x18004ca90`
- `0x18004d8d8`
- `0x180096010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180008a29`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180008a3d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180008a29`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180008a3d`
- `msvcp_win!_Mtx_unlock` at `0x18000891a`
- `msvcp_win!_Mtx_unlock` at `0x18000891a`
- `msvcp_win!_Mtx_lock` at `0x180008830`
- `msvcp_win!_Mtx_lock` at `0x180008830`
- `ntdll!RtlLengthSid` at `0x180008866`
- `ntdll!RtlLengthSid` at `0x180008872`
- `ntdll!RtlLengthSid` at `0x1800088b3`
- `ntdll!RtlLengthSid` at `0x1800088bf`
- `ntdll!RtlLengthSid` at `0x180008866`
- `ntdll!RtlLengthSid` at `0x180008872`
- `ntdll!RtlLengthSid` at `0x1800088b3`
- `ntdll!RtlLengthSid` at `0x1800088bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008929`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008929`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall anonymous_namespace_::SrumDataCache::GetKeyData(char *a1, _QWORD *a2, PSID *a3)
{
  __int64 v6; // rcx
  __int64 *v7; // rbx
  __int64 *v8; // rdi
  ULONG v9; // r12d
  ULONG v10; // eax
  ULONG v11; // edi
  ULONG v12; // eax
  __int64 v13; // rax
  __int64 v15; // rax
  volatile signed __int32 *v16; // rdi
  PSID v17; // [rsp+38h] [rbp-69h] BYREF
  _BYTE v18[4]; // [rsp+40h] [rbp-61h] BYREF
  int i; // [rsp+44h] [rbp-5Dh]
  _BYTE v20[8]; // [rsp+50h] [rbp-51h] BYREF
  volatile signed __int32 *v21; // [rsp+58h] [rbp-49h]
  _Mtx_t v22; // [rsp+60h] [rbp-41h]
  __int64 *v23; // [rsp+68h] [rbp-39h] BYREF
  _BYTE v24[32]; // [rsp+78h] [rbp-29h] BYREF
  _BYTE v25[32]; // [rsp+98h] [rbp-9h] BYREF

  v22 = (_Mtx_t)a1;
  if ( _Mtx_lock((_Mtx_t)a1) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)a1 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)a1 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x180008A43LL);
  }
  v7 = (__int64 *)*((_QWORD *)a1 + 10);
  v8 = (__int64 *)v7[1];
  for ( i = 0; !*((_BYTE *)v8 + 25); v8 = (__int64 *)*v8 )
  {
    v9 = RtlLengthSid((PSID)v8[4]);
    v10 = RtlLengthSid(*a3);
    if ( v9 < v10 || v9 <= v10 && memcmp_0((const void *)v8[4], *a3, v9) < 0 )
      v8 += 2;
    else
      v7 = v8;
  }
  if ( *((_BYTE *)v7 + 25)
    || (v11 = RtlLengthSid(*a3), v12 = RtlLengthSid((PSID)v7[4]), v11 < v12)
    || v11 <= v12 && memcmp_0(*a3, (const void *)v7[4], v11) < 0
    || v7 == *((__int64 **)a1 + 10) )
  {
    v15 = anonymous_namespace_::SrumDataCache::BuildKeyData(v6, v24, a3);
    std::make_shared<SrumKeyData,SrumKeyData>(v20, v15);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v25);
    std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v24);
    v17 = *a3;
    *a3 = 0;
    std::shared_ptr<SrumKeyData>::shared_ptr<SrumKeyData>(v18, v20);
    std::_Tree_std::_Tmap_traits__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData__std::less__anonymous_namespace_::OwnedSid__std::allocator_std::pair__anonymous_namespace_::OwnedSid_const__std::shared_ptr_SrumKeyData______0___::_Emplace_std::pair__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData_____(
      a1 + 80,
      &v23,
      &v17);
    v7 = v23;
    std::pair__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData___::_pair__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData___(&v17);
    v16 = v21;
    if ( v21 )
    {
      if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
  *a2 = 0;
  a2[1] = 0;
  v13 = v7[6];
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  *a2 = v7[5];
  a2[1] = v7[6];
  _Mtx_unlock((_Mtx_t)a1);
  if ( *a3 )
  {
    LocalFree(*a3);
    *a3 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800087e8  mov     rax, rsp
0x1800087eb  mov     [rax+20h], rbx
0x1800087ef  mov     [rax+18h], r8
0x1800087f3  mov     [rax+10h], rdx
0x1800087f7  push    rbp
0x1800087f8  push    rsi
0x1800087f9  push    rdi
0x1800087fa  push    r12
0x1800087fc  push    r13
0x1800087fe  push    r14
0x180008800  push    r15
0x180008802  lea     rbp, [rax-5Fh]
0x180008806  sub     rsp, 0C0h
0x18000880d  mov     rax, cs:__security_cookie
0x180008814  xor     rax, rsp
0x180008817  mov     [rbp+57h+var_40], rax
0x18000881b  mov     rsi, r8
0x18000881e  mov     r14, rdx
0x180008821  mov     r15, rcx
0x180008824  mov     [rbp+57h+var_C8], rdx
0x180008828  mov     [rbp+57h+var_C8], r8
0x18000882c  mov     [rbp+57h+var_98], rcx
0x180008830  call    cs:__imp__Mtx_lock
0x180008836  test    eax, eax
0x180008838  jnz     loc_180008A24
0x18000883e  cmp     dword ptr [r15+4Ch], 7FFFFFFFh
0x180008846  jz      loc_180008A30
0x18000884c  lea     r13, [r15+50h]
0x180008850  mov     rbx, [r13+0]
0x180008854  mov     rdi, [rbx+8]
0x180008858  xor     eax, eax
0x18000885a  mov     [rbp+57h+var_B4], eax
0x18000885d  cmp     [rdi+19h], al
0x180008860  jnz     short loc_1800088A6
0x180008862  mov     rcx, [rdi+20h]; Sid
0x180008866  call    cs:__imp_RtlLengthSid
0x18000886c  mov     r12d, eax
0x18000886f  mov     rcx, [rsi]; Sid
0x180008872  call    cs:__imp_RtlLengthSid
0x180008878  cmp     r12d, eax
0x18000887b  jb      loc_180008960
0x180008881  ja      short loc_18000889A
0x180008883  mov     r8d, r12d; Size
0x180008886  mov     rdx, [rsi]; Buf2
0x180008889  mov     rcx, [rdi+20h]; Buf1
0x18000888d  call    memcmp_0
0x180008892  test    eax, eax
0x180008894  js      loc_180008960
0x18000889a  mov     rbx, rdi
0x18000889d  mov     rdi, [rdi]
0x1800088a0  cmp     byte ptr [rdi+19h], 0
0x1800088a4  jz      short loc_180008862
0x1800088a6  cmp     byte ptr [rbx+19h], 0
0x1800088aa  jnz     loc_180008969
0x1800088b0  mov     rcx, [rsi]; Sid
0x1800088b3  call    cs:__imp_RtlLengthSid
0x1800088b9  mov     edi, eax
0x1800088bb  mov     rcx, [rbx+20h]; Sid
0x1800088bf  call    cs:__imp_RtlLengthSid
0x1800088c5  cmp     edi, eax
0x1800088c7  jb      loc_180008969
0x1800088cd  ja      short loc_1800088E6
0x1800088cf  mov     r8d, edi; Size
0x1800088d2  mov     rdx, [rbx+20h]; Buf2
0x1800088d6  mov     rcx, [rsi]; Buf1
0x1800088d9  call    memcmp_0
0x1800088de  test    eax, eax
0x1800088e0  js      loc_180008969
0x1800088e6  cmp     rbx, [r13+0]
0x1800088ea  jz      short loc_180008969
0x1800088ec  mov     qword ptr [r14], 0
0x1800088f3  mov     qword ptr [r14+8], 0
0x1800088fb  mov     rax, [rbx+30h]
0x1800088ff  test    rax, rax
0x180008902  jz      short loc_180008908
0x180008904  lock inc dword ptr [rax+8]
0x180008908  mov     rax, [rbx+28h]
0x18000890c  mov     [r14], rax
0x18000890f  mov     rdx, [rbx+30h]
0x180008913  mov     [r14+8], rdx
0x180008917  mov     rcx, r15; _Mtx_t
0x18000891a  call    cs:__imp__Mtx_unlock
0x180008920  nop
0x180008921  mov     rcx, [rsi]; hMem
0x180008924  test    rcx, rcx
0x180008927  jz      short loc_180008936
0x180008929  call    cs:__imp_LocalFree
0x18000892f  mov     qword ptr [rsi], 0
0x180008936  mov     rax, r14
0x180008939  mov     rcx, [rbp+57h+var_40]
0x18000893d  xor     rcx, rsp; StackCookie
0x180008940  call    __security_check_cookie
0x180008945  mov     rbx, [rsp+0F0h+arg_18]
0x18000894d  add     rsp, 0C0h
0x180008954  pop     r15
0x180008956  pop     r14
0x180008958  pop     r13
0x18000895a  pop     r12
0x18000895c  pop     rdi
0x18000895d  pop     rsi
0x18000895e  pop     rbp
0x18000895f  retn
0x180008960  add     rdi, 10h
0x180008964  jmp     loc_18000889D
0x180008969  mov     r8, rsi
0x18000896c  lea     rdx, [rbp+57h+var_80]
0x180008970  call    _anonymous_namespace___SrumDataCache__BuildKeyData
0x180008975  nop
0x180008976  mov     rdx, rax
0x180008979  lea     rcx, [rbp+57h+var_A8]
0x18000897d  call    ??$make_shared@USrumKeyData@@U1@@std@@YA?AV?$shared_ptr@USrumKeyData@@@0@$$QEAUSrumKeyData@@@Z; std::make_shared<SrumKeyData,SrumKeyData>(SrumKeyData &&)
0x180008982  nop
0x180008983  lea     rcx, [rbp+57h+var_60]; void *
0x180008987  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18000898c  lea     rcx, [rbp+57h+var_80]; void *
0x180008990  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x180008995  mov     rax, [rsi]
0x180008998  mov     [rbp+57h+var_C0], rax
0x18000899c  mov     qword ptr [rsi], 0
0x1800089a3  lea     rdx, [rbp+57h+var_A8]
0x1800089a7  lea     rcx, [rbp+57h+var_B8]
0x1800089ab  call    ??0?$shared_ptr@USrumKeyData@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<SrumKeyData>::shared_ptr<SrumKeyData>(std::shared_ptr<SrumKeyData> const &)
0x1800089b0  nop
0x1800089b1  lea     r8, [rbp+57h+var_C0]
0x1800089b5  lea     rdx, [rbp+57h+var_90]
0x1800089b9  mov     rcx, r13
0x1800089bc  call    std___Tree_std___Tmap_traits__anonymous_namespace___OwnedSid_std__shared_ptr_SrumKeyData__std__less__anonymous_namespace___OwnedSid__std__allocator_std__pair__anonymous_namespace___OwnedSid_const__std__shared_ptr_SrumKeyData______0______Emplace_std__pair__anonymous_namespace___OwnedSid_std__shared_ptr_SrumKeyData_____
0x1800089c1  mov     rbx, [rbp+57h+var_90]
0x1800089c5  lea     rcx, [rbp+57h+var_C0]
0x1800089c9  call    std__pair__anonymous_namespace___OwnedSid_std__shared_ptr_SrumKeyData______pair__anonymous_namespace___OwnedSid_std__shared_ptr_SrumKeyData___
0x1800089ce  nop
0x1800089cf  mov     rdi, [rbp+57h+var_A0]
0x1800089d3  test    rdi, rdi
0x1800089d6  jz      loc_1800088EC
0x1800089dc  or      r12d, 0FFFFFFFFh
0x1800089e0  mov     eax, r12d
0x1800089e3  lock xadd [rdi+8], eax
0x1800089e8  add     eax, r12d
0x1800089eb  jnz     loc_1800088EC
0x1800089f1  mov     rax, [rdi]
0x1800089f4  mov     rcx, rdi
0x1800089f7  mov     rax, [rax]
0x1800089fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089ff  mov     eax, r12d
0x180008a02  lock xadd [rdi+0Ch], eax
0x180008a07  add     eax, r12d
0x180008a0a  jnz     loc_1800088EC
0x180008a10  mov     rax, [rdi]
0x180008a13  mov     rcx, rdi
0x180008a16  mov     rax, [rax+8]
0x180008a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a1f  jmp     loc_1800088EC
0x180008a24  mov     ecx, 5
0x180008a29  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180008a2f  int     3; Trap to Debugger
0x180008a30  mov     dword ptr [r15+4Ch], 7FFFFFFEh
0x180008a38  mov     ecx, 6
0x180008a3d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
