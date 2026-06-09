# CJobManager::CheckClientAccess(void)

- ea: `0x18000a680`
- end: `0x18000a9d4`
- name: `?CheckClientAccess@CJobManager@@QEAAJXZ`
- size: `852`
- prototype: `__int64 __fastcall(CJobManager *__hidden this)`
- caller_count: `12`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000a9dc`
- `0x180030480`
- `0x1800361b8`
- `0x18009a170`
- `0x18009a330`
- `0x18009a4c0`
- `0x1800ade30`
- `0x1800ae054`
- `0x1800ae17c`
- `0x1800e4fb0`
- `0x1800e5650`
- `0x1800e61b0`

## callees

- `0x180006640`
- `0x180009e70`
- `0x18000a680`
- `0x18000dcb0`
- `0x180018d00`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800acacc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a89e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a962`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a89e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a962`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a98d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a98d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a76e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a76e`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18000a836`
- `api-ms-win-security-base-l1-1-0!IsTokenRestricted` at `0x18000a836`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CJobManager::CheckClientAccess(CJobManager *this)
{
  PSID v1; // r14
  _DWORD *v2; // rax
  void *v3; // rdi
  PSID v4; // r15
  void *v5; // rdi
  BOOL v6; // r14d
  int v7; // ecx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 result; // rax
  unsigned int v12; // [rsp+20h] [rbp-208h]
  void *v13; // [rsp+28h] [rbp-200h] BYREF
  char v14; // [rsp+30h] [rbp-1F8h]
  void *v15; // [rsp+38h] [rbp-1F0h]
  PSID pSid1; // [rsp+40h] [rbp-1E8h]
  void *v17; // [rsp+48h] [rbp-1E0h]
  __int64 v18; // [rsp+50h] [rbp-1D8h]
  void *v19; // [rsp+58h] [rbp-1D0h]
  void **pExceptionObject; // [rsp+60h] [rbp-1C8h] BYREF
  __int128 v21; // [rsp+68h] [rbp-1C0h]
  int v22; // [rsp+78h] [rbp-1B0h]
  int v23; // [rsp+7Ch] [rbp-1ACh]
  int v24; // [rsp+80h] [rbp-1A8h]
  void **v25; // [rsp+C0h] [rbp-168h] BYREF
  __int128 v26; // [rsp+C8h] [rbp-160h]
  int v27; // [rsp+D8h] [rbp-150h]
  int v28; // [rsp+DCh] [rbp-14Ch]
  int v29; // [rsp+E0h] [rbp-148h]
  void **v30; // [rsp+120h] [rbp-108h] BYREF
  __int128 v31; // [rsp+128h] [rbp-100h]
  int v32; // [rsp+138h] [rbp-F0h]
  int v33; // [rsp+13Ch] [rbp-ECh]
  int v34; // [rsp+140h] [rbp-E8h]
  void **v35; // [rsp+180h] [rbp-A8h] BYREF
  _DWORD v36[22]; // [rsp+188h] [rbp-A0h] BYREF

  try
  {
    CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)&v13);
    if ( !pSid1 )
    {
      v1 = CopyTokenSid(*(HANDLE *)v15);
      v2 = operator new(4u);
      v3 = v2;
      if ( v2 )
        *v2 = 1;
      else
        v3 = 0;
      if ( pSid1 != v1 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17, 0xFFFFFFFF) == 1 )
        {
          operator delete(v17, 4u);
          operator delete(pSid1, 0);
        }
        pSid1 = v1;
        v17 = v3;
        _InterlockedIncrement((volatile signed __int32 *)v3);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
      {
        operator delete(v3, 4u);
        operator delete(v1, 0);
      }
    }
    v4 = pSid1;
    v5 = v17;
    _InterlockedIncrement((volatile signed __int32 *)v17);
    v6 = EqualSid(v4, *((PSID *)g_GlobalInfo + 15));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5, 0xFFFFFFFF) == 1 )
    {
      operator delete(v5, 4u);
      operator delete(v4, 0);
    }
    if ( v6 )
    {
      v21 = 0;
      pExceptionObject = &ComError::`vftable';
      v22 = -2147024891;
      v23 = 0;
      v24 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v7 = DenyAccessIfRemoteUserWithInsufficientPermissions();
    if ( v7 < 0 )
    {
      v26 = 0;
      v25 = &ComError::`vftable';
      v27 = v7;
      v28 = 4687;
      v29 = 1;
      throw (ComError *)&v25;
    }
    if ( IsTokenRestricted(*(HANDLE *)v15) )
    {
      v31 = 0;
      v30 = &ComError::`vftable';
      v32 = -2147024891;
      v33 = 0;
      v34 = 1;
      throw (ComError *)&v30;
    }
    if ( v14 )
    {
      SetThreadToken(0, *(HANDLE *)v13);
      v14 = 0;
    }
    v8 = v19;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 2, 0xFFFFFFFF) == 1 )
        operator delete(v19, 0x10u);
      v19 = 0;
    }
    if ( v18 )
      std::default_delete<AppPackageInfo>::operator()(v8, v18);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17, 0xFFFFFFFF) == 1 )
    {
      operator delete(v17, 4u);
      operator delete(pSid1, 0);
      v17 = 0;
      pSid1 = 0;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, 0xFFFFFFFF) == 1 )
    {
      v9 = v15;
      if ( (unsigned __int64)(*(_QWORD *)v15 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v15);
        *(_QWORD *)v15 = 0;
        v9 = v15;
      }
      operator delete(v9, 0x10u);
      v15 = 0;
    }
    SetThreadToken(0, *(HANDLE *)v13);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 2, 0xFFFFFFFF) == 1 )
    {
      v10 = v13;
      if ( (unsigned __int64)(*(_QWORD *)v13 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v13);
        *(_QWORD *)v13 = 0;
        v10 = v13;
      }
      operator delete(v10, 0x10u);
    }
    result = 0;
  }
  catch ( ComError v35 )
  {
    v12 = v36[4];
    v35 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(v36);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18000a680  push    rbx
0x18000a682  push    rsi
0x18000a683  push    rdi
0x18000a684  push    r12
0x18000a686  push    r14
0x18000a688  push    r15
0x18000a68a  sub     rsp, 1F8h
0x18000a691  mov     rax, cs:__security_cookie
0x18000a698  xor     rax, rsp
0x18000a69b  mov     [rsp+228h+var_48], rax
0x18000a6a3  xor     r12d, r12d
0x18000a6a6  lea     rcx, [rsp+228h+var_200]; this
0x18000a6ab  call    ??0CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::CNestedImpersonation(void)
0x18000a6b0  nop
0x18000a6b1  cmp     [rsp+228h+pSid1], r12
0x18000a6b6  jnz     loc_18000A74B
0x18000a6bc  mov     rcx, [rsp+228h+var_1F0]
0x18000a6c1  mov     rcx, [rcx]; TokenHandle
0x18000a6c4  call    ?CopyTokenSid@@YAPEAXPEAX@Z; CopyTokenSid(void *)
0x18000a6c9  mov     r14, rax
0x18000a6cc  lea     esi, [r12+4]
0x18000a6d1  mov     ecx, esi; dwBytes
0x18000a6d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6d8  mov     rdi, rax
0x18000a6db  test    rax, rax
0x18000a6de  jz      short loc_18000A6E8
0x18000a6e0  mov     dword ptr [rax], 1
0x18000a6e6  jmp     short loc_18000A6EB
0x18000a6e8  mov     rdi, r12
0x18000a6eb  or      ebx, 0FFFFFFFFh
0x18000a6ee  cmp     [rsp+228h+pSid1], r14
0x18000a6f3  jz      short loc_18000A72A
0x18000a6f5  mov     rcx, [rsp+228h+var_1E0]
0x18000a6fa  mov     eax, ebx
0x18000a6fc  lock xadd [rcx], eax
0x18000a700  add     eax, ebx
0x18000a702  jnz     short loc_18000A71D
0x18000a704  mov     rdx, rsi; unsigned __int64
0x18000a707  mov     rcx, [rsp+228h+var_1E0]; void *
0x18000a70c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a711  xor     edx, edx; unsigned __int64
0x18000a713  mov     rcx, [rsp+228h+pSid1]; void *
0x18000a718  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a71d  mov     [rsp+228h+pSid1], r14
0x18000a722  mov     [rsp+228h+var_1E0], rdi
0x18000a727  lock inc dword ptr [rdi]
0x18000a72a  mov     eax, ebx
0x18000a72c  lock xadd [rdi], eax
0x18000a730  add     eax, ebx
0x18000a732  jnz     short loc_18000A753
0x18000a734  mov     rdx, rsi; unsigned __int64
0x18000a737  mov     rcx, rdi; void *
0x18000a73a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a73f  xor     edx, edx; unsigned __int64
0x18000a741  mov     rcx, r14; void *
0x18000a744  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a749  jmp     short loc_18000A753
0x18000a74b  mov     esi, 4
0x18000a750  or      ebx, 0FFFFFFFFh
0x18000a753  mov     r15, [rsp+228h+pSid1]
0x18000a758  mov     rdi, [rsp+228h+var_1E0]
0x18000a75d  lock inc dword ptr [rdi]
0x18000a760  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18000a767  mov     rdx, [rdx+78h]; pSid2
0x18000a76b  mov     rcx, r15; pSid1
0x18000a76e  call    cs:__imp_EqualSid
0x18000a774  mov     r14d, eax
0x18000a777  mov     edx, ebx
0x18000a779  lock xadd [rdi], edx
0x18000a77d  add     edx, ebx
0x18000a77f  jnz     short loc_18000A796
0x18000a781  mov     rdx, rsi; unsigned __int64
0x18000a784  mov     rcx, rdi; void *
0x18000a787  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a78c  xor     edx, edx; unsigned __int64
0x18000a78e  mov     rcx, r15; void *
0x18000a791  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a796  test    r14d, r14d
0x18000a799  jz      short loc_18000A7D8
0x18000a79b  xorps   xmm0, xmm0
0x18000a79e  movups  [rsp+228h+var_1C0], xmm0
0x18000a7a3  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000a7aa  mov     [rsp+228h+pExceptionObject], rax
0x18000a7af  mov     [rsp+228h+var_1B0], 80070005h
0x18000a7b7  mov     [rsp+228h+var_1AC], r12d
0x18000a7bc  mov     [rsp+228h+var_1A8], 1
0x18000a7c7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000a7ce  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x18000a7d3  call    _CxxThrowException_0
0x18000a7d8  call    ?DenyAccessIfRemoteUserWithInsufficientPermissions@@YAJXZ; DenyAccessIfRemoteUserWithInsufficientPermissions(void)
0x18000a7dd  mov     ecx, eax
0x18000a7df  test    eax, eax
0x18000a7e1  jns     short loc_18000A82E
0x18000a7e3  xorps   xmm0, xmm0
0x18000a7e6  movups  [rsp+228h+var_160], xmm0
0x18000a7ee  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000a7f5  mov     [rsp+228h+var_168], rax
0x18000a7fd  mov     [rsp+228h+var_150], ecx
0x18000a804  mov     [rsp+228h+var_14C], 124Fh
0x18000a80f  mov     [rsp+228h+var_148], 1
0x18000a81a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000a821  lea     rcx, [rsp+228h+var_168]; pExceptionObject
0x18000a829  call    _CxxThrowException_0
0x18000a82e  mov     rcx, [rsp+228h+var_1F0]
0x18000a833  mov     rcx, [rcx]; TokenHandle
0x18000a836  call    cs:__imp_IsTokenRestricted
0x18000a83c  test    eax, eax
0x18000a83e  jz      short loc_18000A88D
0x18000a840  xorps   xmm0, xmm0
0x18000a843  movups  [rsp+228h+var_100], xmm0
0x18000a84b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000a852  mov     [rsp+228h+var_108], rax
0x18000a85a  mov     [rsp+228h+var_F0], 80070005h
0x18000a865  mov     [rsp+228h+var_EC], r12d
0x18000a86d  mov     [rsp+228h+var_E8], 1
0x18000a878  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000a87f  lea     rcx, [rsp+228h+var_108]; pExceptionObject
0x18000a887  call    _CxxThrowException_0
0x18000a88d  cmp     [rsp+228h+var_1F8], r12b
0x18000a892  jz      short loc_18000A8A9
0x18000a894  mov     rdx, [rsp+228h+var_200]
0x18000a899  mov     rdx, [rdx]; Token
0x18000a89c  xor     ecx, ecx; Thread
0x18000a89e  call    cs:__imp_SetThreadToken
0x18000a8a4  mov     [rsp+228h+var_1F8], r12b
0x18000a8a9  mov     rcx, [rsp+228h+var_1D0]
0x18000a8ae  test    rcx, rcx
0x18000a8b1  jz      short loc_18000A8D0
0x18000a8b3  mov     eax, ebx
0x18000a8b5  lock xadd [rcx+8], eax
0x18000a8ba  add     eax, ebx
0x18000a8bc  jnz     short loc_18000A8CB
0x18000a8be  lea     edx, [rax+10h]; unsigned __int64
0x18000a8c1  mov     rcx, [rsp+228h+var_1D0]; void *
0x18000a8c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a8cb  mov     [rsp+228h+var_1D0], r12
0x18000a8d0  mov     rdx, [rsp+228h+var_1D8]
0x18000a8d5  test    rdx, rdx
0x18000a8d8  jz      short loc_18000A8DF
0x18000a8da  call    ??R?$default_delete@UAppPackageInfo@@@std@@QEBAXPEAUAppPackageInfo@@@Z; std::default_delete<AppPackageInfo>::operator()(AppPackageInfo *)
0x18000a8df  mov     rax, [rsp+228h+var_1E0]
0x18000a8e4  mov     ecx, ebx
0x18000a8e6  lock xadd [rax], ecx
0x18000a8ea  add     ecx, ebx
0x18000a8ec  jnz     short loc_18000A911
0x18000a8ee  mov     rdx, rsi; unsigned __int64
0x18000a8f1  mov     rcx, [rsp+228h+var_1E0]; void *
0x18000a8f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a8fb  xor     edx, edx; unsigned __int64
0x18000a8fd  mov     rcx, [rsp+228h+pSid1]; void *
0x18000a902  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a907  mov     [rsp+228h+var_1E0], r12
0x18000a90c  mov     [rsp+228h+pSid1], r12
0x18000a911  mov     rcx, [rsp+228h+var_1F0]
0x18000a916  mov     eax, ebx
0x18000a918  lock xadd [rcx+8], eax
0x18000a91d  add     eax, ebx
0x18000a91f  jnz     short loc_18000A958
0x18000a921  mov     rcx, [rsp+228h+var_1F0]
0x18000a926  mov     rdx, [rcx]
0x18000a929  lea     rax, [rdx-1]
0x18000a92d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a931  ja      short loc_18000A949
0x18000a933  mov     rcx, rdx; hObject
0x18000a936  call    cs:__imp_CloseHandle
0x18000a93c  mov     rax, [rsp+228h+var_1F0]
0x18000a941  mov     [rax], r12
0x18000a944  mov     rcx, [rsp+228h+var_1F0]; void *
0x18000a949  mov     edx, 10h; unsigned __int64
0x18000a94e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a953  mov     [rsp+228h+var_1F0], r12
0x18000a958  mov     rdx, [rsp+228h+var_200]
0x18000a95d  mov     rdx, [rdx]; Token
0x18000a960  xor     ecx, ecx; Thread
0x18000a962  call    cs:__imp_SetThreadToken
0x18000a968  mov     rcx, [rsp+228h+var_200]
0x18000a96d  mov     eax, ebx
0x18000a96f  lock xadd [rcx+8], eax
0x18000a974  add     eax, ebx
0x18000a976  jnz     short loc_18000A9AA
0x18000a978  mov     rcx, [rsp+228h+var_200]
0x18000a97d  mov     rdx, [rcx]
0x18000a980  lea     rax, [rdx-1]
0x18000a984  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a988  ja      short loc_18000A9A0
0x18000a98a  mov     rcx, rdx; hObject
0x18000a98d  call    cs:__imp_CloseHandle
0x18000a993  mov     rax, [rsp+228h+var_200]
0x18000a998  mov     [rax], r12
0x18000a99b  mov     rcx, [rsp+228h+var_200]; void *
0x18000a9a0  mov     edx, 10h; unsigned __int64
0x18000a9a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a9aa  xor     eax, eax
0x18000a9ac  jmp     short loc_18000A9B2
0x18000a9ae  mov     eax, [rsp+228h+var_208]
0x18000a9b2  mov     rcx, [rsp+228h+var_48]
0x18000a9ba  xor     rcx, rsp; StackCookie
0x18000a9bd  call    __security_check_cookie
0x18000a9c2  add     rsp, 1F8h
0x18000a9c9  pop     r15
0x18000a9cb  pop     r14
0x18000a9cd  pop     r12
0x18000a9cf  pop     rdi
0x18000a9d0  pop     rsi
0x18000a9d1  pop     rbx
0x18000a9d2  retn
```
