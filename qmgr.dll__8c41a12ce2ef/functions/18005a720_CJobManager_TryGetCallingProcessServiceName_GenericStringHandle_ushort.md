# CJobManager::TryGetCallingProcessServiceName(GenericStringHandle<ushort> *)

- ea: `0x18005a720`
- end: `0x18005ab95`
- name: `?TryGetCallingProcessServiceName@CJobManager@@SAXPEAV?$GenericStringHandle@G@@@Z`
- size: `1141`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18005a660`

## callees

- `0x180006640`
- `0x18000dcb0`
- `0x180029304`
- `0x18003dcb0`
- `0x18005a720`
- `0x18005aba0`
- `0x18007aab4`
- `0x180099740`
- `0x18009d024`
- `0x1800a1114`
- `0x1800a3444`
- `0x1800acacc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005a8b0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005a978`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005a8b0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005a978`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a94c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a9a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a94c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a9a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CJobManager::TryGetCallingProcessServiceName(void **a1)
{
  char *v2; // rsi
  wchar_t v3; // r9
  const wchar_t *v4; // rcx
  wchar_t *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  wchar_t *v9; // rcx
  int ServiceNamesFromToken; // ecx
  void *v11; // rcx
  __int64 v12; // rsi
  void *v13; // rcx
  void *v14; // rcx
  char *v15; // r14
  wchar_t *v16; // r8
  const wchar_t *v17; // rax
  wchar_t v18; // cx
  __int64 v19; // r12
  wchar_t *v20; // rcx
  void *v21; // [rsp+30h] [rbp-1B8h] BYREF
  char v22; // [rsp+38h] [rbp-1B0h]
  void *v23; // [rsp+40h] [rbp-1A8h]
  void *v24; // [rsp+48h] [rbp-1A0h]
  void *v25; // [rsp+50h] [rbp-198h]
  __int64 v26; // [rsp+58h] [rbp-190h]
  void *v27; // [rsp+60h] [rbp-188h]
  void *v28; // [rsp+68h] [rbp-180h] BYREF
  _BYTE *v29; // [rsp+70h] [rbp-178h]
  __int64 v30; // [rsp+78h] [rbp-170h]
  const ComError *v31; // [rsp+80h] [rbp-168h] BYREF
  void **pExceptionObject; // [rsp+90h] [rbp-158h] BYREF
  __int128 v33; // [rsp+98h] [rbp-150h]
  int v34; // [rsp+A8h] [rbp-140h]
  int v35; // [rsp+ACh] [rbp-13Ch]
  int v36; // [rsp+B0h] [rbp-138h]
  void **v37; // [rsp+F0h] [rbp-F8h] BYREF
  __int128 v38; // [rsp+F8h] [rbp-F0h]
  int v39; // [rsp+108h] [rbp-E0h]
  int v40; // [rsp+10Ch] [rbp-DCh]
  int v41; // [rsp+110h] [rbp-D8h]
  void **v42; // [rsp+150h] [rbp-98h] BYREF
  __int128 v43; // [rsp+158h] [rbp-90h]
  int v44; // [rsp+168h] [rbp-80h]
  int v45; // [rsp+16Ch] [rbp-7Ch]
  int v46; // [rsp+170h] [rbp-78h]

  try
  {
    v2 = (char *)operator new(0x1Eu);
    *(_QWORD *)v2 = 7;
    *((_DWORD *)v2 + 2) = 1;
    v5 = (wchar_t *)(v2 + 12);
    *((_WORD *)v2 + 6) = 0;
    v19 = 2147483646;
    v6 = 2147483646;
    v4 = L"Unknown";
    v7 = 8;
    do
    {
      if ( !v6 )
        break;
      v3 = *v4;
      if ( !*v4 )
        break;
      ++v4;
      *v5++ = v3;
      --v6;
      --v7;
    }
    while ( v7 );
    v8 = v7 == 0 ? 0x8007007A : 0;
    v9 = v5 - 1;
    if ( v7 )
      v9 = v5;
    *v9 = 0;
    if ( !v7 )
    {
      v33 = 0;
      pExceptionObject = &ComError::`vftable';
      v34 = -2147024774;
      v35 = 894;
      v36 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( *a1 && _InterlockedExchangeAdd((volatile signed __int32 *)*a1 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a1, 0x10u);
    *a1 = v2;
    std::vector<_GUID>::vector<_GUID>(&v28, v5, v7, v8);
    CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)&v21);
    ServiceNamesFromToken = ServiceUserTokenHelper::GetServiceNamesFromToken(*(HANDLE *)v23, 1, (__int64)&v28);
    if ( ServiceNamesFromToken < 0 )
    {
      v38 = 0;
      v37 = &ComError::`vftable';
      v39 = ServiceNamesFromToken;
      v40 = 6320;
      v41 = 1;
      throw (ComError *)&v37;
    }
    if ( v22 )
    {
      SetThreadToken(0, *(HANDLE *)v21);
      v22 = 0;
    }
    v11 = v27;
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 2, 0xFFFFFFFF) == 1 )
        operator delete(v27, 0x10u);
      v27 = 0;
    }
    if ( v26 )
      std::default_delete<AppPackageInfo>::operator()(v11, v26);
    v12 = 4;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25, 0xFFFFFFFF) == 1 )
    {
      operator delete(v25, 4u);
      operator delete(v24, 0);
      v25 = 0;
      v24 = 0;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 + 2, 0xFFFFFFFF) == 1 )
    {
      v13 = v23;
      if ( (unsigned __int64)(*(_QWORD *)v23 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v23);
        *(_QWORD *)v23 = 0;
        v13 = v23;
      }
      operator delete(v13, 0x10u);
      v23 = 0;
    }
    SetThreadToken(0, *(HANDLE *)v21);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 2, 0xFFFFFFFF) == 1 )
    {
      v14 = v21;
      if ( (unsigned __int64)(*(_QWORD *)v21 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v21);
        *(_QWORD *)v21 = 0;
        v14 = v21;
      }
      operator delete(v14, 0x10u);
    }
    if ( v29 == v28 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
      v15 = (char *)operator new(0x16u);
      *(_QWORD *)v15 = 3;
      *((_DWORD *)v15 + 2) = 1;
      v16 = (wchar_t *)(v15 + 12);
      *((_WORD *)v15 + 6) = 0;
      v17 = L"N/A";
      do
      {
        if ( !v19 )
          break;
        v18 = *v17;
        if ( !*v17 )
          break;
        ++v17;
        *v16++ = v18;
        --v19;
        --v12;
      }
      while ( v12 );
      v20 = v16 - 1;
      if ( v12 )
        v20 = v16;
      *v20 = 0;
      if ( !v12 )
      {
        v43 = 0;
        v42 = &ComError::`vftable';
        v44 = -2147024774;
        v45 = 894;
        v46 = 1;
        throw (ComError *)&v42;
      }
      if ( *a1 && !_InterlockedDecrement((volatile signed __int32 *)*a1 + 2) )
        operator delete(*a1, 0x10u);
      *a1 = v15;
    }
    else if ( v29 - (_BYTE *)v28 == 8 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          280,
          &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
          *(_QWORD *)v28 + 12LL);
      GenericStringHandle<unsigned short>::operator=(a1, v28);
    }
    else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
    }
    if ( v28 )
    {
      std::_Destroy_range<std::allocator<GenericStringHandle<unsigned short>>>(v28);
      std::_Deallocate<16>(v28, (v30 - (_QWORD)v28) & 0xFFFFFFFFFFFFFFF8uLL);
    }
  }
  catch ( const ComError *v31 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        282,
        &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
        *((unsigned int *)v31 + 6),
        *((_DWORD *)v31 + 7));
  }
}

```

## disassembly

```asm
0x18005a720  push    rbx
0x18005a722  push    rsi
0x18005a723  push    rdi
0x18005a724  push    r12
0x18005a726  push    r13
0x18005a728  push    r14
0x18005a72a  sub     rsp, 1B8h
0x18005a731  mov     rdi, rcx
0x18005a734  mov     ecx, 1Eh; dwBytes
0x18005a739  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a73e  mov     rsi, rax
0x18005a741  mov     qword ptr [rax], 7
0x18005a748  mov     r14d, 1
0x18005a74e  mov     [rax+8], r14d
0x18005a752  lea     rdx, [rax+0Ch]
0x18005a756  xor     r13d, r13d
0x18005a759  mov     [rdx], r13w
0x18005a75d  mov     r12d, 7FFFFFFEh
0x18005a763  mov     eax, r12d
0x18005a766  lea     rcx, aUnknown_0; "Unknown"
0x18005a76d  lea     r8d, [r14+7]
0x18005a771  test    rax, rax
0x18005a774  jz      short loc_18005A794
0x18005a776  movzx   r9d, word ptr [rcx]
0x18005a77a  test    r9w, r9w
0x18005a77e  jz      short loc_18005A794
0x18005a780  add     rcx, 2
0x18005a784  mov     [rdx], r9w
0x18005a788  add     rdx, 2
0x18005a78c  sub     rax, r14
0x18005a78f  sub     r8, r14
0x18005a792  jnz     short loc_18005A771
0x18005a794  mov     rax, r8
0x18005a797  neg     rax
0x18005a79a  sbb     r9d, r9d
0x18005a79d  not     r9d
0x18005a7a0  and     r9d, 8007007Ah
0x18005a7a7  lea     rcx, [rdx-2]
0x18005a7ab  test    r8, r8
0x18005a7ae  cmovnz  rcx, rdx
0x18005a7b2  mov     [rcx], r13w
0x18005a7b6  jnz     short loc_18005A801
0x18005a7b8  xorps   xmm0, xmm0
0x18005a7bb  movups  [rsp+1E8h+var_150], xmm0
0x18005a7c3  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005a7ca  mov     [rsp+1E8h+pExceptionObject], rax
0x18005a7d2  mov     [rsp+1E8h+var_140], r9d
0x18005a7da  mov     [rsp+1E8h+var_13C], 37Eh
0x18005a7e5  mov     [rsp+1E8h+var_138], r14d
0x18005a7ed  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005a7f4  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x18005a7fc  call    _CxxThrowException_0
0x18005a801  mov     rcx, [rdi]
0x18005a804  or      ebx, 0FFFFFFFFh
0x18005a807  test    rcx, rcx
0x18005a80a  jz      short loc_18005A822
0x18005a80c  mov     eax, ebx
0x18005a80e  lock xadd [rcx+8], eax
0x18005a813  add     eax, ebx
0x18005a815  jnz     short loc_18005A822
0x18005a817  lea     edx, [rbx+11h]; unsigned __int64
0x18005a81a  mov     rcx, [rdi]; void *
0x18005a81d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a822  mov     [rdi], rsi
0x18005a825  lea     rcx, [rsp+1E8h+var_180]
0x18005a82a  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18005a82f  nop
0x18005a830  lea     rcx, [rsp+1E8h+var_1B8]; this
0x18005a835  call    ??0CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::CNestedImpersonation(void)
0x18005a83a  nop
0x18005a83b  lea     r8, [rsp+1E8h+var_180]
0x18005a840  mov     dl, r14b
0x18005a843  mov     rcx, [rsp+1E8h+var_1A8]
0x18005a848  mov     rcx, [rcx]; TokenHandle
0x18005a84b  call    ?GetServiceNamesFromToken@ServiceUserTokenHelper@@SAJPEAX_NPEAV?$vector@V?$GenericStringHandle@G@@V?$allocator@V?$GenericStringHandle@G@@@std@@@std@@@Z; ServiceUserTokenHelper::GetServiceNamesFromToken(void *,bool,std::vector<GenericStringHandle<ushort>> *)
0x18005a850  mov     ecx, eax
0x18005a852  test    eax, eax
0x18005a854  jns     short loc_18005A89F
0x18005a856  xorps   xmm0, xmm0
0x18005a859  movups  [rsp+1E8h+var_F0], xmm0
0x18005a861  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005a868  mov     [rsp+1E8h+var_F8], rax
0x18005a870  mov     [rsp+1E8h+var_E0], ecx
0x18005a877  mov     [rsp+1E8h+var_DC], 18B0h
0x18005a882  mov     [rsp+1E8h+var_D8], r14d
0x18005a88a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005a891  lea     rcx, [rsp+1E8h+var_F8]; pExceptionObject
0x18005a899  call    _CxxThrowException_0
0x18005a89f  cmp     [rsp+1E8h+var_1B0], r13b
0x18005a8a4  jz      short loc_18005A8BB
0x18005a8a6  mov     rdx, [rsp+1E8h+var_1B8]
0x18005a8ab  mov     rdx, [rdx]; Token
0x18005a8ae  xor     ecx, ecx; Thread
0x18005a8b0  call    cs:__imp_SetThreadToken
0x18005a8b6  mov     [rsp+1E8h+var_1B0], r13b
0x18005a8bb  mov     rcx, [rsp+1E8h+var_188]
0x18005a8c0  test    rcx, rcx
0x18005a8c3  jz      short loc_18005A8E2
0x18005a8c5  mov     eax, ebx
0x18005a8c7  lock xadd [rcx+8], eax
0x18005a8cc  add     eax, ebx
0x18005a8ce  jnz     short loc_18005A8DD
0x18005a8d0  lea     edx, [rax+10h]; unsigned __int64
0x18005a8d3  mov     rcx, [rsp+1E8h+var_188]; void *
0x18005a8d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a8dd  mov     [rsp+1E8h+var_188], r13
0x18005a8e2  mov     rdx, [rsp+1E8h+var_190]
0x18005a8e7  test    rdx, rdx
0x18005a8ea  jz      short loc_18005A8F1
0x18005a8ec  call    ??R?$default_delete@UAppPackageInfo@@@std@@QEBAXPEAUAppPackageInfo@@@Z; std::default_delete<AppPackageInfo>::operator()(AppPackageInfo *)
0x18005a8f1  mov     rax, [rsp+1E8h+var_198]
0x18005a8f6  mov     ecx, ebx
0x18005a8f8  lock xadd [rax], ecx
0x18005a8fc  add     ecx, ebx
0x18005a8fe  mov     esi, 4
0x18005a903  jnz     short loc_18005A927
0x18005a905  mov     edx, esi; unsigned __int64
0x18005a907  mov     rcx, [rsp+1E8h+var_198]; void *
0x18005a90c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a911  xor     edx, edx; unsigned __int64
0x18005a913  mov     rcx, [rsp+1E8h+var_1A0]; void *
0x18005a918  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a91d  mov     [rsp+1E8h+var_198], r13
0x18005a922  mov     [rsp+1E8h+var_1A0], r13
0x18005a927  mov     rcx, [rsp+1E8h+var_1A8]
0x18005a92c  mov     eax, ebx
0x18005a92e  lock xadd [rcx+8], eax
0x18005a933  add     eax, ebx
0x18005a935  jnz     short loc_18005A96E
0x18005a937  mov     rcx, [rsp+1E8h+var_1A8]
0x18005a93c  mov     rdx, [rcx]
0x18005a93f  lea     rax, [rdx-1]
0x18005a943  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a947  ja      short loc_18005A95F
0x18005a949  mov     rcx, rdx; hObject
0x18005a94c  call    cs:__imp_CloseHandle
0x18005a952  mov     rax, [rsp+1E8h+var_1A8]
0x18005a957  mov     [rax], r13
0x18005a95a  mov     rcx, [rsp+1E8h+var_1A8]; void *
0x18005a95f  mov     edx, 10h; unsigned __int64
0x18005a964  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a969  mov     [rsp+1E8h+var_1A8], r13
0x18005a96e  mov     rdx, [rsp+1E8h+var_1B8]
0x18005a973  mov     rdx, [rdx]; Token
0x18005a976  xor     ecx, ecx; Thread
0x18005a978  call    cs:__imp_SetThreadToken
0x18005a97e  mov     rcx, [rsp+1E8h+var_1B8]
0x18005a983  mov     eax, ebx
0x18005a985  lock xadd [rcx+8], eax
0x18005a98a  add     eax, ebx
0x18005a98c  jnz     short loc_18005A9C0
0x18005a98e  mov     rcx, [rsp+1E8h+var_1B8]
0x18005a993  mov     rdx, [rcx]
0x18005a996  lea     rax, [rdx-1]
0x18005a99a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a99e  ja      short loc_18005A9B6
0x18005a9a0  mov     rcx, rdx; hObject
0x18005a9a3  call    cs:__imp_CloseHandle
0x18005a9a9  mov     rax, [rsp+1E8h+var_1B8]
0x18005a9ae  mov     [rax], r13
0x18005a9b1  mov     rcx, [rsp+1E8h+var_1B8]; void *
0x18005a9b6  mov     edx, 10h; unsigned __int64
0x18005a9bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a9c0  mov     rax, [rsp+1E8h+var_178]
0x18005a9c5  sub     rax, [rsp+1E8h+var_180]
0x18005a9ca  jnz     loc_18005AAD9
0x18005a9d0  lea     rax, WPP_GLOBAL_Control
0x18005a9d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a9de  cmp     rcx, rax
0x18005a9e1  jz      short loc_18005A9FE
0x18005a9e3  test    [rcx+1Ch], r14b
0x18005a9e7  jz      short loc_18005A9FE
0x18005a9e9  mov     edx, 117h
0x18005a9ee  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18005a9f5  mov     rcx, [rcx+10h]
0x18005a9f9  call    WPP_SF_
0x18005a9fe  mov     ecx, 16h; dwBytes
0x18005aa03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005aa08  mov     r14, rax
0x18005aa0b  mov     qword ptr [rax], 3
0x18005aa12  mov     dword ptr [rax+8], 1
0x18005aa19  lea     r8, [rax+0Ch]
0x18005aa1d  mov     [r8], r13w
0x18005aa21  lea     rax, aNA; "N/A"
0x18005aa28  test    r12, r12
0x18005aa2b  jz      short loc_18005AA4A
0x18005aa2d  movzx   ecx, word ptr [rax]
0x18005aa30  test    cx, cx
0x18005aa33  jz      short loc_18005AA4A
0x18005aa35  add     rax, 2
0x18005aa39  mov     [r8], cx
0x18005aa3d  add     r8, 2
0x18005aa41  dec     r12
0x18005aa44  sub     rsi, 1
0x18005aa48  jnz     short loc_18005AA28
0x18005aa4a  mov     rax, rsi
0x18005aa4d  neg     rax
0x18005aa50  sbb     edx, edx
0x18005aa52  not     edx
0x18005aa54  and     edx, 8007007Ah
0x18005aa5a  lea     rcx, [r8-2]
0x18005aa5e  test    rsi, rsi
0x18005aa61  cmovnz  rcx, r8
0x18005aa65  mov     [rcx], r13w
0x18005aa69  jnz     short loc_18005AAB6
0x18005aa6b  xorps   xmm0, xmm0
0x18005aa6e  movups  [rsp+1E8h+var_90], xmm0
0x18005aa76  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005aa7d  mov     [rsp+1E8h+var_98], rax
0x18005aa85  mov     [rsp+1E8h+var_80], edx
0x18005aa8c  mov     [rsp+1E8h+var_7C], 37Eh
0x18005aa97  mov     [rsp+1E8h+var_78], 1
0x18005aaa2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005aaa9  lea     rcx, [rsp+1E8h+var_98]; pExceptionObject
0x18005aab1  call    _CxxThrowException_0
0x18005aab6  mov     rcx, [rdi]
0x18005aab9  test    rcx, rcx
0x18005aabc  jz      short loc_18005AAD4
0x18005aabe  mov     eax, ebx
0x18005aac0  lock xadd [rcx+8], eax
0x18005aac5  add     eax, ebx
0x18005aac7  jnz     short loc_18005AAD4
0x18005aac9  lea     edx, [rax+10h]; unsigned __int64
0x18005aacc  mov     rcx, [rdi]; void *
0x18005aacf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005aad4  mov     [rdi], r14
0x18005aad7  jmp     short loc_18005AB57
0x18005aad9  cmp     rax, 8
0x18005aadd  jnz     short loc_18005AB28
0x18005aadf  lea     rax, WPP_GLOBAL_Control
0x18005aae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aaed  cmp     rcx, rax
0x18005aaf0  jz      short loc_18005AB19
0x18005aaf2  test    [rcx+1Ch], r14b
0x18005aaf6  jz      short loc_18005AB19
0x18005aaf8  mov     rax, [rsp+1E8h+var_180]
0x18005aafd  mov     r9, [rax]
0x18005ab00  add     r9, 0Ch
0x18005ab04  mov     edx, 118h
0x18005ab09  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18005ab10  mov     rcx, [rcx+10h]
0x18005ab14  call    WPP_SF_S
0x18005ab19  mov     rdx, [rsp+1E8h+var_180]
0x18005ab1e  mov     rcx, rdi
0x18005ab21  call    ??4?$GenericStringHandle@G@@QEAAAEAV0@AEBV0@@Z; GenericStringHandle<ushort>::operator=(GenericStringHandle<ushort> const &)
0x18005ab26  jmp     short loc_18005AB57
0x18005ab28  lea     rax, WPP_GLOBAL_Control
0x18005ab2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab36  cmp     rcx, rax
0x18005ab39  jz      short loc_18005AB57
0x18005ab3b  test    byte ptr [rcx+1Ch], 2
0x18005ab3f  jz      short loc_18005AB57
0x18005ab41  mov     edx, 119h
0x18005ab46  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18005ab4d  mov     rcx, [rcx+10h]
0x18005ab51  call    WPP_SF_
0x18005ab56  nop
0x18005ab57  mov     rcx, [rsp+1E8h+var_180]; void *
0x18005ab5c  test    rcx, rcx
0x18005ab5f  jz      short loc_18005AB82
0x18005ab61  mov     rdx, [rsp+1E8h+var_178]
0x18005ab66  call    ??$_Destroy_range@V?$allocator@V?$GenericStringHandle@G@@@std@@@std@@YAXPEAV?$GenericStringHandle@G@@QEAV1@AEAV?$allocator@V?$GenericStringHandle@G@@@0@@Z; std::_Destroy_range<std::allocator<GenericStringHandle<ushort>>>(GenericStringHandle<ushort> *,GenericStringHandle<ushort> * const,std::allocator<GenericStringHandle<ushort>> &)
0x18005ab6b  mov     rcx, [rsp+1E8h+var_180]
0x18005ab70  mov     rdx, [rsp+1E8h+var_170]
0x18005ab75  sub     rdx, rcx
0x18005ab78  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005ab7c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005ab81  nop
0x18005ab82  jmp     short $+2
0x18005ab84  add     rsp, 1B8h
0x18005ab8b  pop     r14
0x18005ab8d  pop     r13
0x18005ab8f  pop     r12
0x18005ab91  pop     rdi
0x18005ab92  pop     rsi
0x18005ab93  pop     rbx
0x18005ab94  retn
```
