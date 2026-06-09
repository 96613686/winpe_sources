# CMFD3D12Buffer::GetCopyableFootprints(uint,D3D12_PLACED_SUBRESOURCE_FOOTPRINT *,uint *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180059be4`
- end: `0x180059f14`
- name: `?GetCopyableFootprints@CMFD3D12Buffer@@IEAAJIPEAUD3D12_PLACED_SUBRESOURCE_FOOTPRINT@@PEAIPEA_K2@Z`
- size: `816`
- prototype: `__int64 __fastcall(CMFD3D12Buffer *__hidden this, unsigned int, struct D3D12_PLACED_SUBRESOURCE_FOOTPRINT *, unsigned int *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005af70`
- `0x18005d000`

## callees

- `0x180024220`
- `0x180056930`
- `0x180059be4`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059d28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059e19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059d28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059de0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059cdf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059dd0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059cdf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059dd0`

## string_xrefs

- `0x180059d40`: `CMFD3D12Buffer::GetCopyableFootprints`
- `0x180059e31`: `CMFD3D12Buffer::GetCopyableFootprints`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMFD3D12Buffer::GetCopyableFootprints(
        CMFD3D12Buffer *this,
        unsigned int a2,
        struct D3D12_PLACED_SUBRESOURCE_FOOTPRINT *a3,
        unsigned int *a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6)
{
  __int64 v10; // rax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v12)(_QWORD, GUID *, __int64 *); // rax
  int v13; // esi
  CallStackTracing *v14; // rdi
  CallStackContext *v15; // r14
  DWORD v16; // r15d
  CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  __int64 v19; // rax
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v21)(_QWORD, GUID *, __int64 *); // rax
  CallStackTracing *v22; // rdi
  CallStackContext *v23; // r14
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  CallStackTracing *v26; // rcx
  __int64 v27; // rax
  __int64 v29; // [rsp+50h] [rbp-99h] BYREF
  __int64 v30; // [rsp+58h] [rbp-91h] BYREF
  unsigned __int64 *v31; // [rsp+60h] [rbp-89h]
  __int128 v32; // [rsp+68h] [rbp-81h] BYREF
  __int128 v33; // [rsp+78h] [rbp-71h]
  __m128i v34; // [rsp+88h] [rbp-61h]
  __int64 v35; // [rsp+98h] [rbp-51h]
  _BYTE v36[28]; // [rsp+A0h] [rbp-49h] BYREF
  int v37; // [rsp+BCh] [rbp-2Dh]

  v31 = a6;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 35) + 80LL))(*((_QWORD *)this + 35), v36);
  v32 = *(_OWORD *)v10;
  v33 = *(_OWORD *)(v10 + 16);
  v34 = *(__m128i *)(v10 + 32);
  v35 = *(_QWORD *)(v10 + 48);
  if ( _mm_cvtsi128_si32(_mm_srli_si128(v34, 12)) == 4 )
  {
    v29 = 0;
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 35);
    v12 = *v11;
    v29 = 0;
    v13 = (*v12)(v11, &GUID_4f9b2e01_3883_4973_80ca_59d2f45f25b5, &v29);
    if ( v13 >= 0 )
    {
      v30 = 0;
      v20 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 37);
      v21 = *v20;
      v30 = 0;
      v13 = (*v21)(v20, &GUID_24499bcb_4364_4c06_9007_a334f1748f18, &v30);
      if ( v13 >= 0 )
      {
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 24LL))(v29, v36);
        v37 = 65537;
        (*(void (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD, _QWORD, struct D3D12_PLACED_SUBRESOURCE_FOOTPRINT *, unsigned int *, unsigned __int64 *, unsigned __int64 *))(*(_QWORD *)v30 + 64LL))(
          v30,
          v36,
          0,
          a2,
          0,
          a3,
          a4,
          a5,
          v31);
      }
      else
      {
        v22 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v23 = (CallStackTracing *)((char *)v22 + 208);
          LastError = GetLastError();
          Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v22 + 3));
          if ( Value )
          {
            v23 = Value;
          }
          else if ( !GetLastError() )
          {
            v26 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)&qword_18009CF60;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
            }
            v27 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
            if ( v27 )
              v23 = (CallStackContext *)v27;
          }
          SetLastError(LastError);
          if ( *((_DWORD *)v23 + 499) != v13 )
            CallStackContext::TraceFailure(v23, "CMFD3D12Buffer::GetCopyableFootprints", 781, v13);
        }
      }
      wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(&v30);
    }
    else
    {
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v15 = (CallStackTracing *)((char *)v14 + 208);
        v16 = GetLastError();
        v17 = (CallStackContext *)TlsGetValue(*((_DWORD *)v14 + 3));
        if ( v17 )
        {
          v15 = v17;
        }
        else if ( !GetLastError() )
        {
          v18 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v19 = (**(__int64 (__fastcall ***)(CallStackTracing *))v18)(v18);
          if ( v19 )
            v15 = (CallStackContext *)v19;
        }
        SetLastError(v16);
        if ( *((_DWORD *)v15 + 499) != v13 )
          CallStackContext::TraceFailure(v15, "CMFD3D12Buffer::GetCopyableFootprints", 778, v13);
      }
    }
    wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(&v29);
  }
  else
  {
    v13 = 0;
    HIDWORD(v33) = 65537;
    (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, _QWORD, struct D3D12_PLACED_SUBRESOURCE_FOOTPRINT *, unsigned int *, unsigned __int64 *, unsigned __int64 *))(**((_QWORD **)this + 37) + 304LL))(
      *((_QWORD *)this + 37),
      &v32,
      0,
      a2,
      0,
      a3,
      a4,
      a5,
      v31);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180059be4  push    rbp
0x180059be6  push    rsi
0x180059be7  push    rdi
0x180059be8  push    r12
0x180059bea  push    r13
0x180059bec  push    r14
0x180059bee  push    r15
0x180059bf0  lea     rbp, [rsp-17h]
0x180059bf5  sub     rsp, 100h
0x180059bfc  mov     rax, cs:__security_cookie
0x180059c03  xor     rax, rsp
0x180059c06  mov     [rbp+47h+var_40], rax
0x180059c0a  mov     r12, r9
0x180059c0d  mov     r15, r8
0x180059c10  mov     r14d, edx
0x180059c13  mov     rdi, rcx
0x180059c16  mov     r13, [rbp+47h+arg_20]
0x180059c1a  mov     rax, [rbp+47h+arg_28]
0x180059c1e  mov     [rsp+130h+var_D0], rax
0x180059c23  mov     rcx, [rcx+118h]
0x180059c2a  mov     rax, [rcx]
0x180059c2d  lea     rdx, [rbp+47h+var_90]
0x180059c31  mov     rax, [rax+50h]
0x180059c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c3a  movups  xmm0, xmmword ptr [rax]
0x180059c3d  movups  [rsp+130h+var_C8], xmm0
0x180059c42  movups  xmm1, xmmword ptr [rax+10h]
0x180059c46  movups  [rbp+47h+var_B8], xmm1
0x180059c4a  movups  xmm2, xmmword ptr [rax+20h]
0x180059c4e  movups  [rbp+47h+var_A8], xmm2
0x180059c52  movsd   xmm0, qword ptr [rax+30h]
0x180059c57  movsd   [rbp+47h+var_98], xmm0
0x180059c5c  psrldq  xmm2, 0Ch
0x180059c61  movd    eax, xmm2
0x180059c65  cmp     eax, 4
0x180059c68  jnz     loc_180059EAB
0x180059c6e  mov     [rsp+130h+var_E0], 0
0x180059c77  mov     rcx, [rdi+118h]
0x180059c7e  mov     rax, [rcx]
0x180059c81  mov     [rsp+130h+var_E0], 0
0x180059c8a  lea     r8, [rsp+130h+var_E0]
0x180059c8f  lea     rdx, _GUID_4f9b2e01_3883_4973_80ca_59d2f45f25b5
0x180059c96  mov     rax, [rax]
0x180059c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c9e  mov     esi, eax
0x180059ca0  test    eax, eax
0x180059ca2  jns     loc_180059D5F
0x180059ca8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059caf  test    rdi, rdi
0x180059cb2  jnz     short loc_180059CC2
0x180059cb4  lea     rdi, qword_18009CF60
0x180059cbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180059cc2  cmp     byte ptr [rdi+8], 0
0x180059cc6  jz      loc_180059D50
0x180059ccc  lea     r14, [rdi+0D0h]
0x180059cd3  call    cs:__imp_GetLastError
0x180059cd9  mov     r15d, eax
0x180059cdc  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180059cdf  call    cs:__imp_TlsGetValue
0x180059ce5  test    rax, rax
0x180059ce8  jz      short loc_180059CEF
0x180059cea  mov     r14, rax
0x180059ced  jmp     short loc_180059D25
0x180059cef  call    cs:__imp_GetLastError
0x180059cf5  test    eax, eax
0x180059cf7  jnz     short loc_180059D25
0x180059cf9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059d00  test    rcx, rcx
0x180059d03  jnz     short loc_180059D13
0x180059d05  lea     rcx, qword_18009CF60
0x180059d0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180059d13  mov     rax, [rcx]
0x180059d16  mov     rax, [rax]
0x180059d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d1e  test    rax, rax
0x180059d21  cmovnz  r14, rax
0x180059d25  mov     ecx, r15d; dwErrCode
0x180059d28  call    cs:__imp_SetLastError
0x180059d2e  cmp     [r14+7CCh], esi
0x180059d35  jz      short loc_180059D50
0x180059d37  mov     r9d, esi; int
0x180059d3a  mov     r8d, 30Ah; int
0x180059d40  lea     rdx, aCmfd3d12buffer_11; "CMFD3D12Buffer::GetCopyableFootprints"
0x180059d47  mov     rcx, r14; this
0x180059d4a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180059d4f  nop
0x180059d50  lea     rcx, [rsp+130h+var_E0]
0x180059d55  call    ??1?$com_ptr_t@UID3D12Fence@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(void)
0x180059d5a  jmp     loc_180059EF3
0x180059d5f  mov     [rsp+130h+var_D8], 0
0x180059d68  mov     rcx, [rdi+128h]
0x180059d6f  mov     rax, [rcx]
0x180059d72  mov     [rsp+130h+var_D8], 0
0x180059d7b  lea     r8, [rsp+130h+var_D8]
0x180059d80  lea     rdx, _GUID_24499bcb_4364_4c06_9007_a334f1748f18
0x180059d87  mov     rax, [rax]
0x180059d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d8f  mov     esi, eax
0x180059d91  test    eax, eax
0x180059d93  jns     loc_180059E50
0x180059d99  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059da0  test    rdi, rdi
0x180059da3  jnz     short loc_180059DB3
0x180059da5  lea     rdi, qword_18009CF60
0x180059dac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180059db3  cmp     byte ptr [rdi+8], 0
0x180059db7  jz      loc_180059E41
0x180059dbd  lea     r14, [rdi+0D0h]
0x180059dc4  call    cs:__imp_GetLastError
0x180059dca  mov     r15d, eax
0x180059dcd  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180059dd0  call    cs:__imp_TlsGetValue
0x180059dd6  test    rax, rax
0x180059dd9  jz      short loc_180059DE0
0x180059ddb  mov     r14, rax
0x180059dde  jmp     short loc_180059E16
0x180059de0  call    cs:__imp_GetLastError
0x180059de6  test    eax, eax
0x180059de8  jnz     short loc_180059E16
0x180059dea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059df1  test    rcx, rcx
0x180059df4  jnz     short loc_180059E04
0x180059df6  lea     rcx, qword_18009CF60
0x180059dfd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180059e04  mov     rax, [rcx]
0x180059e07  mov     rax, [rax]
0x180059e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e0f  test    rax, rax
0x180059e12  cmovnz  r14, rax
0x180059e16  mov     ecx, r15d; dwErrCode
0x180059e19  call    cs:__imp_SetLastError
0x180059e1f  cmp     [r14+7CCh], esi
0x180059e26  jz      short loc_180059E41
0x180059e28  mov     r9d, esi; int
0x180059e2b  mov     r8d, 30Dh; int
0x180059e31  lea     rdx, aCmfd3d12buffer_11; "CMFD3D12Buffer::GetCopyableFootprints"
0x180059e38  mov     rcx, r14; this
0x180059e3b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180059e40  nop
0x180059e41  lea     rcx, [rsp+130h+var_D8]
0x180059e46  call    ??1?$com_ptr_t@UID3D12Fence@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D12Fence,wil::err_returncode_policy>::~com_ptr_t<ID3D12Fence,wil::err_returncode_policy>(void)
0x180059e4b  jmp     loc_180059D50
0x180059e50  mov     rcx, [rsp+130h+var_E0]
0x180059e55  mov     rax, [rcx]
0x180059e58  lea     rdx, [rbp+47h+var_90]
0x180059e5c  mov     rax, [rax+18h]
0x180059e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e65  mov     [rbp+47h+var_74], 10001h
0x180059e6c  mov     rcx, [rsp+130h+var_D8]
0x180059e71  mov     rax, [rcx]
0x180059e74  mov     rdx, [rsp+130h+var_D0]
0x180059e79  mov     [rsp+130h+var_F0], rdx
0x180059e7e  mov     [rsp+130h+var_F8], r13
0x180059e83  mov     [rsp+130h+var_100], r12
0x180059e88  mov     [rsp+130h+var_108], r15
0x180059e8d  mov     [rsp+130h+var_110], 0
0x180059e96  mov     r9d, r14d
0x180059e99  xor     r8d, r8d
0x180059e9c  lea     rdx, [rbp+47h+var_90]
0x180059ea0  mov     rax, [rax+40h]
0x180059ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ea9  jmp     short loc_180059E41
0x180059eab  xor     esi, esi
0x180059ead  mov     dword ptr [rbp+47h+var_B8+0Ch], 10001h
0x180059eb4  mov     rcx, [rdi+128h]
0x180059ebb  mov     rax, [rcx]
0x180059ebe  mov     rdx, [rsp+130h+var_D0]
0x180059ec3  mov     [rsp+130h+var_F0], rdx
0x180059ec8  mov     [rsp+130h+var_F8], r13
0x180059ecd  mov     [rsp+130h+var_100], r12
0x180059ed2  mov     [rsp+130h+var_108], r15
0x180059ed7  mov     [rsp+130h+var_110], rsi
0x180059edc  mov     r9d, r14d
0x180059edf  xor     r8d, r8d
0x180059ee2  lea     rdx, [rsp+130h+var_C8]
0x180059ee7  mov     rax, [rax+130h]
0x180059eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ef3  mov     eax, esi
0x180059ef5  mov     rcx, [rbp+47h+var_40]
0x180059ef9  xor     rcx, rsp; StackCookie
0x180059efc  call    __security_check_cookie
0x180059f01  add     rsp, 100h
0x180059f08  pop     r15
0x180059f0a  pop     r14
0x180059f0c  pop     r13
0x180059f0e  pop     r12
0x180059f10  pop     rdi
0x180059f11  pop     rsi
0x180059f12  pop     rbp
0x180059f13  retn
```
