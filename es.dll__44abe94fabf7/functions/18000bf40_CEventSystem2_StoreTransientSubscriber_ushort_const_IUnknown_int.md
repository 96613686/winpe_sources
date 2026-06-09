# CEventSystem2::StoreTransientSubscriber(ushort const *,IUnknown *,int)

- ea: `0x18000bf40`
- end: `0x18000c77b`
- name: `?StoreTransientSubscriber@CEventSystem2@@UEAAJPEBGPEAUIUnknown@@H@Z`
- size: `2107`
- prototype: `int(CEventSystem2 *__hidden this, const unsigned __int16 *, struct IUnknown *, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000b2d0`
- `0x18000b6e4`
- `0x18000bf40`
- `0x18000c910`
- `0x18000d538`
- `0x18000db24`
- `0x18000db98`
- `0x180010210`
- `0x180010410`
- `0x180012654`
- `0x18001fffc`
- `0x180024a94`
- `0x180025350`
- `0x18003f754`
- `0x1800434ba`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c741`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800439a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c741`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800439a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c41e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c41e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c434`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c523`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c74c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c74c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c47f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c47f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000c19a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000c19a`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18000c186`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18000c186`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bfce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bfce`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000c08f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000c08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c63f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c689`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c63f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c689`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c6b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c6b9`

## string_xrefs

- `0x18000c410`: `com\complus\src\events\shared\locality.cpp`

## pseudocode

```c
__int64 __fastcall CEventSystem2::StoreTransientSubscriber(
        CEventSystem2 *this,
        unsigned __int16 *a2,
        struct IUnknown *a3,
        int a4)
{
  OLECHAR *v5; // rbx
  int v6; // eax
  unsigned __int16 *v7; // rdx
  __int64 v8; // r15
  _DWORD *v9; // rax
  int v10; // esi
  char v11; // r14
  const OLECHAR *v12; // r12
  int v13; // r12d
  HRESULT v14; // eax
  int v15; // edi
  int v16; // esi
  __m128i v17; // xmm6
  unsigned int v18; // eax
  __int64 v19; // r8
  __int64 *i; // rsi
  __int128 v21; // xmm0
  bool v22; // cl
  unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  unsigned __int16 v25; // cx
  int v26; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int128 v29; // xmm0
  CString *v30; // rax
  OLECHAR *v31; // rcx
  OLECHAR *v33; // rcx
  unsigned int v34; // [rsp+48h] [rbp-E0h] BYREF
  int v35; // [rsp+4Ch] [rbp-DCh]
  int v36; // [rsp+50h] [rbp-D8h]
  void *TokenHandle; // [rsp+58h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-C8h] BYREF
  int TokenInformation; // [rsp+6Ch] [rbp-BCh] BYREF
  int v40; // [rsp+70h] [rbp-B8h]
  void *ClientProcess; // [rsp+78h] [rbp-B0h] BYREF
  unsigned int Pid[4]; // [rsp+80h] [rbp-A8h] BYREF
  __int128 v43; // [rsp+90h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+A0h] [rbp-88h] BYREF
  const OLECHAR *v45; // [rsp+A8h] [rbp-80h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-78h] BYREF
  __m128i v47; // [rsp+B8h] [rbp-70h] BYREF
  __int128 v48; // [rsp+D0h] [rbp-58h] BYREF

  TokenHandle = 0;
  v34 = 0;
  ClientProcess = 0;
  if ( *((_DWORD *)this + 98) )
    return 2147549448LL;
  v5 = (OLECHAR *)&dword_180053104;
  *(_QWORD *)&v43 = &dword_180053104;
  if ( a2 && (v6 = safe_lstrlenW(a2), (v8 = v6) != 0) )
  {
    if ( v6 <= 0 )
    {
      v10 = 0;
      v12 = &dword_180053104;
      v11 = 1;
    }
    else
    {
      v9 = CoTaskMemAlloc(2LL * v6 + 14);
      if ( v9 )
      {
        v10 = 0;
        v11 = 1;
        *v9 = 1;
        *((_WORD *)v9 + v8 + 6) = 0;
        v9[1] = v8;
        v9[2] = v8;
        v5 = (OLECHAR *)(v9 + 3);
        *(_QWORD *)&v43 = v9 + 3;
        v12 = (const OLECHAR *)(v9 + 3);
      }
      else
      {
        v10 = -2147024882;
        v12 = &dword_180053104;
        v11 = 1;
      }
      if ( v10 >= 0 )
        CString::Release((struct CStringData *)&qword_1800530F8);
      v7 = a2;
    }
    if ( v10 >= 0 )
    {
      memcpy_0(v5, v7, 2 * v8);
      *((_DWORD *)v12 - 2) = v8;
      v12[v8] = 0;
    }
  }
  else
  {
    v10 = 0;
    CString::Release((CString *)&v43);
    v11 = 1;
    v5 = (OLECHAR *)v43;
  }
  if ( v10 >= 0 )
  {
    if ( !*((_QWORD *)this + 3) )
    {
      ppv = 0;
      v15 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
      if ( v15 < 0 )
      {
        CString::~CString((CString *)&v43);
        return (unsigned int)v15;
      }
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 3, (signed __int64)ppv, 0) )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    v13 = 0;
    v35 = 0;
    v14 = CoSetProxyBlanket(a3, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 2u, 0, 0x40u);
    v15 = v14;
    if ( v14 <= -2147467264 || (unsigned int)(v14 + 2147467261) <= 0x7FFFBFFC )
    {
LABEL_99:
      v31 = v5 - 6;
      if ( v5 - 6 != (OLECHAR *)&qword_1800530F8
        && _InterlockedExchangeAdd((volatile signed __int32 *)v31, 0xFFFFFFFF) == 1 )
      {
        CoTaskMemFree(v31);
      }
      return (unsigned int)v15;
    }
    v16 = 0;
    v36 = 0;
    ppv = 0;
    v15 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, LPVOID *))a3->lpVtbl->QueryInterface)(
            a3,
            &GUID_00000144_0000_0000_c000_000000000046,
            &ppv);
    if ( (unsigned int)(v15 + 2147467263) <= 1 )
    {
      v16 = 1;
      v36 = 1;
      v15 = 0;
      goto LABEL_18;
    }
    if ( v15 < 0 )
    {
LABEL_18:
      if ( v15 < 0 )
        goto LABEL_91;
      if ( (unsigned int)(v16 - 1) <= 1 )
      {
LABEL_20:
        v15 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, GUID *, unsigned int *))(**((_QWORD **)this + 3)
                                                                                           + 24LL))(
                *((_QWORD *)this + 3),
                a3,
                &IID_IUnknown,
                &v34);
        if ( v15 >= 0 )
        {
          Pid[0] = v34;
          Pid[1] = 0;
          *(_QWORD *)&Pid[2] = TokenHandle;
          if ( a4 && !I_RpcOpenClientProcess(0, 0x100000u, &ClientProcess) )
            I_RpcBindingInqLocalClientPID(0, &Pid[1]);
          CSemExclusiveES::Lock((CEventSystem2 *)((char *)this + 112));
          v13 = 1;
          v35 = 1;
          if ( *((_DWORD *)this + 98) )
          {
            v15 = -2147417848;
          }
          else
          {
            v17 = 0;
            v47 = 0;
            v18 = HashKey<unsigned short const *>(a2);
            if ( *((_QWORD *)this + 4) )
            {
              for ( i = *(__int64 **)(*((_QWORD *)this + 4) + 8LL * (v18 % *((_DWORD *)this + 10))); i; i = (__int64 *)*i )
              {
                v23 = (unsigned __int16 *)i[2];
                if ( v19 )
                {
                  v24 = v19 - (_QWORD)v23;
                  while ( 1 )
                  {
                    v25 = *v23;
                    if ( *v23 != *(unsigned __int16 *)((char *)v23 + v24) )
                      break;
                    ++v23;
                    if ( !v25 )
                    {
                      v26 = 0;
                      goto LABEL_50;
                    }
                  }
                  v26 = v25 < *(unsigned __int16 *)((char *)v23 + v24) ? -1 : 1;
                }
                else
                {
                  if ( !*((_DWORD *)v23 - 2) )
                    goto LABEL_27;
                  v26 = 1;
                }
LABEL_50:
                if ( !v26 )
                  goto LABEL_27;
              }
            }
            i = 0;
LABEL_27:
            if ( i )
            {
              v17 = *(__m128i *)(i + 3);
              v47 = v17;
            }
            v21 = *(_OWORD *)Pid;
            if ( *((int *)v5 - 3) < 0 )
            {
              v45 = &dword_180053104;
            }
            else
            {
              v45 = v5;
              _InterlockedAdd((volatile signed __int32 *)v5 - 3, 1u);
            }
            v48 = v21;
            v15 = CMap<CString,unsigned short const *,CEventSystem2::TransientSubscriber,CEventSystem2::TransientSubscriber>::SetAtWithActualKeyType(
                    (char *)this + 32,
                    &v45,
                    &v48);
            if ( v15 >= 0 )
            {
              TokenHandle = 0;
              v34 = 0;
              if ( !i || (v47.m128i_i32[1] = _mm_cvtsi128_si32(_mm_srli_si128(v17, 4))) == 0 )
                v11 = 0;
              v22 = ClientProcess != 0;
              if ( v11 )
              {
                if ( !ClientProcess )
                {
LABEL_39:
                  if ( v11 )
                    CEventSystem2::RemoveWatchedSubscription((CEventSystem2 *)((char *)this - 8), v47.m128i_u32[1], a2);
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
                  v13 = 0;
                  v35 = 0;
                  if ( i )
                    CEventSystem2::ReleaseTransientSubscriber(
                      (CEventSystem2 *)((char *)this - 8),
                      (struct CEventSystem2::TransientSubscriber *)&v47);
                  goto LABEL_91;
                }
                if ( v47.m128i_i32[1] == Pid[1] )
                {
                  v11 = 0;
                  v22 = 0;
                }
              }
              if ( v22 )
              {
                if ( !CEventSystem2::AddWatchedSubscription(
                        (CEventSystem2 *)((char *)this - 8),
                        Pid[1],
                        ClientProcess,
                        (const OLECHAR **)&v43) )
                {
                  Pid[1] = 0;
                  v29 = *(_OWORD *)Pid;
                  v30 = CString::CString((CString *)&v45, (const struct CString *)&v43);
                  v43 = v29;
                  CMap<CString,unsigned short const *,CEventSystem2::TransientSubscriber,CEventSystem2::TransientSubscriber>::SetAtWithActualKeyType(
                    (char *)this + 32,
                    v30,
                    &v43);
                }
                ClientProcess = 0;
              }
              goto LABEL_39;
            }
            v13 = v35;
          }
        }
LABEL_91:
        if ( v13 )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
        if ( ClientProcess )
          CloseHandle(ClientProcess);
        if ( v34 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3), v34);
        if ( TokenHandle )
          CloseHandle(TokenHandle);
        goto LABEL_99;
      }
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
        || (LastError = GetLastError(), v15 = LastError, LastError == 1008) )
      {
        if ( !TokenHandle )
          goto LABEL_20;
        TokenInformation = 0;
        ReturnLength = 4;
        if ( GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
        {
          if ( TokenInformation < 2 )
          {
            v15 = -2147024891;
            goto LABEL_91;
          }
          if ( v16 == 4 && TokenInformation < 3 )
          {
            v40 = 0;
            v15 = TokenGroupsContainNetwork(TokenHandle);
            if ( v15 < 0 )
              goto LABEL_91;
            if ( v40 )
            {
              CloseHandle(TokenHandle);
              TokenHandle = 0;
            }
          }
          goto LABEL_20;
        }
        LastError = GetLastError();
        v15 = LastError;
      }
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_91;
    }
    v46 = 0;
    v15 = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(
            ppv,
            a3,
            2,
            &v46);
    if ( v15 < 0 )
    {
LABEL_66:
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
      goto LABEL_18;
    }
    if ( v46 )
    {
      if ( v46 == 1 )
      {
        v16 = 3;
      }
      else
      {
        if ( v46 != 2 )
        {
          InternalAssert(
            L"com\\complus\\src\\events\\shared\\locality.cpp",
            0x28u,
            0x12u,
            L"!\"Unrecognized locality\"");
          goto LABEL_65;
        }
        v16 = 4;
      }
    }
    else
    {
      v16 = 2;
    }
    v36 = v16;
LABEL_65:
    v15 = 0;
    goto LABEL_66;
  }
  v33 = v5 - 6;
  if ( v5 - 6 != (OLECHAR *)&qword_1800530F8 && _InterlockedExchangeAdd((volatile signed __int32 *)v33, 0xFFFFFFFF) == 1 )
    CoTaskMemFree(v33);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000bf40  mov     rax, rsp
0x18000bf43  mov     [rax+20h], r9d
0x18000bf47  mov     [rax+18h], r8
0x18000bf4b  mov     [rax+10h], rdx
0x18000bf4f  mov     [rax+8], rcx
0x18000bf53  push    rbx
0x18000bf54  push    rsi
0x18000bf55  push    rdi
0x18000bf56  push    r12
0x18000bf58  push    r13
0x18000bf5a  push    r14
0x18000bf5c  push    r15
0x18000bf5e  sub     rsp, 0F0h
0x18000bf65  movaps  xmmword ptr [rax-48h], xmm6
0x18000bf69  mov     r13, rcx
0x18000bf6c  mov     [rsp+128h+TokenHandle], 0
0x18000bf75  mov     [rsp+128h+var_E0], 0
0x18000bf7d  mov     [rsp+128h+ClientProcess], 0
0x18000bf86  cmp     dword ptr [rcx+188h], 0
0x18000bf8d  jnz     loc_18000C701
0x18000bf93  lea     r14, dword_180053104
0x18000bf9a  mov     rbx, r14
0x18000bf9d  mov     [rax-98h], rbx
0x18000bfa4  test    rdx, rdx
0x18000bfa7  jz      loc_18000C70B
0x18000bfad  mov     rcx, rdx; unsigned __int16 *
0x18000bfb0  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000bfb5  movsxd  r15, eax
0x18000bfb8  test    eax, eax
0x18000bfba  jz      loc_18000C70B
0x18000bfc0  jle     loc_18000C662
0x18000bfc6  lea     rcx, ds:0Eh[r15*2]; cb
0x18000bfce  call    cs:__imp_CoTaskMemAlloc
0x18000bfd4  test    rax, rax
0x18000bfd7  jz      loc_18000C6EE
0x18000bfdd  xor     esi, esi
0x18000bfdf  lea     r14d, [rsi+1]
0x18000bfe3  mov     [rax], r14d
0x18000bfe6  xor     ecx, ecx
0x18000bfe8  mov     [rax+r15*2+0Ch], cx
0x18000bfee  mov     [rax+4], r15d
0x18000bff2  mov     [rax+8], r15d
0x18000bff6  lea     rbx, [rax+0Ch]
0x18000bffa  mov     qword ptr [rsp+128h+var_98], rbx
0x18000c002  mov     r12, rbx
0x18000c005  test    esi, esi
0x18000c007  js      short loc_18000C015
0x18000c009  lea     rcx, qword_1800530F8; struct CStringData *
0x18000c010  call    ?Release@CString@@KAXPEAUCStringData@@@Z; CString::Release(CStringData *)
0x18000c015  mov     rdx, [rsp+128h+Src]; Src
0x18000c01d  test    esi, esi
0x18000c01f  js      short loc_18000C03C
0x18000c021  lea     rdi, [r15+r15]
0x18000c025  mov     r8, rdi; Size
0x18000c028  mov     rcx, rbx; void *
0x18000c02b  call    memcpy_0
0x18000c030  mov     [r12-8], r15d
0x18000c035  xor     eax, eax
0x18000c037  mov     [r12+rdi], ax
0x18000c03c  lea     rax, qword_1800530F8
0x18000c043  test    esi, esi
0x18000c045  js      loc_18000C670
0x18000c04b  mov     rax, [r13+18h]
0x18000c04f  test    rax, rax
0x18000c052  jz      loc_18000C693
0x18000c058  xor     r12d, r12d
0x18000c05b  mov     [rsp+128h+var_DC], r12d
0x18000c060  mov     [rsp+128h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18000c068  mov     [rsp+128h+pAuthInfo], r12; pAuthInfo
0x18000c06d  mov     [rsp+128h+dwImpLevel], 2; dwImpLevel
0x18000c075  mov     [rsp+128h+dwAuthnLevel], r12d; dwAuthnLevel
0x18000c07a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c07e  mov     r9, r15; pServerPrincName
0x18000c081  xor     r8d, r8d; dwAuthzSvc
0x18000c084  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000c087  mov     rcx, [rsp+128h+pProxy]; pProxy
0x18000c08f  call    cs:__imp_CoSetProxyBlanket
0x18000c095  mov     edi, eax
0x18000c097  cmp     eax, 80004000h
0x18000c09c  jle     loc_18000C623
0x18000c0a2  lea     ecx, [rax+7FFFBFFDh]
0x18000c0a8  cmp     ecx, 7FFFBFFCh
0x18000c0ae  jbe     loc_18000C623
0x18000c0b4  xor     esi, esi
0x18000c0b6  mov     [rsp+128h+var_D8], esi
0x18000c0ba  mov     [rsp+128h+ppv], rsi
0x18000c0bf  mov     rcx, [rsp+128h+pProxy]
0x18000c0c7  mov     rax, [rcx]
0x18000c0ca  lea     r8, [rsp+128h+ppv]
0x18000c0cf  lea     rdx, _GUID_00000144_0000_0000_c000_000000000046
0x18000c0d6  mov     rax, [rax]
0x18000c0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0de  mov     edi, eax
0x18000c0e0  add     eax, 7FFFBFFFh
0x18000c0e5  cmp     eax, r14d
0x18000c0e8  ja      loc_18000C379
0x18000c0ee  mov     esi, r14d
0x18000c0f1  mov     [rsp+128h+var_D8], r14d
0x18000c0f6  xor     edi, edi
0x18000c0f8  mov     [rsp+128h+var_E4], edi
0x18000c0fc  test    edi, edi
0x18000c0fe  js      loc_18000C5F3
0x18000c104  lea     eax, [rsi-1]
0x18000c107  cmp     eax, r14d
0x18000c10a  ja      loc_18000C41E
0x18000c110  mov     rcx, [r13+18h]
0x18000c114  mov     rax, [rcx]
0x18000c117  lea     r9, [rsp+128h+var_E0]
0x18000c11c  lea     r8, IID_IUnknown
0x18000c123  mov     rdx, [rsp+128h+pProxy]
0x18000c12b  mov     rax, [rax+18h]
0x18000c12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c134  mov     edi, eax
0x18000c136  mov     [rsp+128h+var_E4], eax
0x18000c13a  test    eax, eax
0x18000c13c  js      loc_18000C5F3
0x18000c142  xorps   xmm0, xmm0
0x18000c145  movups  xmmword ptr [rsp+128h+Pid], xmm0
0x18000c14d  mov     eax, [rsp+128h+var_E0]
0x18000c151  mov     [rsp+128h+Pid], eax
0x18000c158  mov     [rsp+128h+Pid+4], 0
0x18000c163  mov     rax, [rsp+128h+TokenHandle]
0x18000c168  mov     qword ptr [rsp+128h+Pid+8], rax
0x18000c170  cmp     [rsp+128h+arg_18], 0
0x18000c178  jz      short loc_18000C1A0
0x18000c17a  lea     r8, [rsp+128h+ClientProcess]; ClientProcess
0x18000c17f  mov     edx, 100000h; DesiredAccess
0x18000c184  xor     ecx, ecx; Binding
0x18000c186  call    cs:__imp_I_RpcOpenClientProcess
0x18000c18c  test    eax, eax
0x18000c18e  jnz     short loc_18000C1A0
0x18000c190  lea     rdx, [rsp+128h+Pid+4]; Pid
0x18000c198  xor     ecx, ecx; Binding
0x18000c19a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000c1a0  lea     rax, [r13+70h]
0x18000c1a4  mov     rcx, rax; this
0x18000c1a7  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18000c1ac  mov     r12d, r14d
0x18000c1af  mov     [rsp+128h+var_DC], r14d
0x18000c1b4  cmp     dword ptr [r13+188h], 0
0x18000c1bc  jnz     loc_18000C33E
0x18000c1c2  xorps   xmm6, xmm6
0x18000c1c5  movups  [rsp+128h+var_70], xmm6
0x18000c1cd  lea     r12, [r13+20h]
0x18000c1d1  mov     r8, [rsp+128h+Src]
0x18000c1d9  mov     rcx, r8
0x18000c1dc  call    ??$HashKey@PEBG@@YAIPEBG@Z; HashKey<ushort const *>(ushort const *)
0x18000c1e1  mov     rsi, [r12]
0x18000c1e5  test    rsi, rsi
0x18000c1e8  jnz     loc_18000C2F3
0x18000c1ee  xor     esi, esi
0x18000c1f0  test    rsi, rsi
0x18000c1f3  jz      short loc_18000C201
0x18000c1f5  movups  xmm6, xmmword ptr [rsi+18h]
0x18000c1f9  movups  [rsp+128h+var_70], xmm6
0x18000c201  movups  xmm0, xmmword ptr [rsp+128h+Pid]
0x18000c209  cmp     dword ptr [rbx-0Ch], 0
0x18000c20d  jl      loc_18000C356
0x18000c213  mov     [rsp+128h+var_80], rbx
0x18000c21b  lock add [rbx-0Ch], r14d
0x18000c220  movdqu  [rsp+128h+var_58], xmm0
0x18000c229  lea     r8, [rsp+128h+var_58]
0x18000c231  lea     rdx, [rsp+128h+var_80]
0x18000c239  mov     rcx, r12
0x18000c23c  call    ?SetAtWithActualKeyType@?$CMap@VCString@@PEBGUTransientSubscriber@CEventSystem2@@U23@@@QEAAJVCString@@UTransientSubscriber@CEventSystem2@@@Z; CMap<CString,ushort const *,CEventSystem2::TransientSubscriber,CEventSystem2::TransientSubscriber>::SetAtWithActualKeyType(CString,CEventSystem2::TransientSubscriber)
0x18000c241  mov     edi, eax
0x18000c243  mov     [rsp+128h+var_E4], eax
0x18000c247  test    eax, eax
0x18000c249  js      loc_18000C34C
0x18000c24f  mov     [rsp+128h+TokenHandle], 0
0x18000c258  mov     [rsp+128h+var_E0], 0
0x18000c260  test    rsi, rsi
0x18000c263  jnz     loc_18000C542
0x18000c269  xor     r14b, r14b
0x18000c26c  mov     [rsp+128h+var_E8], r14b
0x18000c271  mov     r8, [rsp+128h+ClientProcess]; void *
0x18000c276  test    r8, r8
0x18000c279  setnz   cl
0x18000c27c  mov     [rsp+128h+var_E7], cl
0x18000c280  test    r14b, r14b
0x18000c283  jnz     loc_18000C55F
0x18000c289  test    cl, cl
0x18000c28b  jz      short loc_18000C2B6
0x18000c28d  lea     r9, [rsp+128h+var_98]; struct CString *
0x18000c295  mov     edx, [rsp+128h+Pid+4]; unsigned int
0x18000c29c  lea     rcx, [r13-8]; this
0x18000c2a0  call    ?AddWatchedSubscription@CEventSystem2@@AEAA_NKPEAXAEAVCString@@@Z; CEventSystem2::AddWatchedSubscription(ulong,void *,CString &)
0x18000c2a5  test    al, al
0x18000c2a7  jz      loc_18000C58E
0x18000c2ad  mov     [rsp+128h+ClientProcess], 0
0x18000c2b6  test    r14b, r14b
0x18000c2b9  lea     r14, [r13-8]
0x18000c2bd  jnz     loc_18000C5D7
0x18000c2c3  lea     rcx, [r13+70h]; lpCriticalSection
0x18000c2c7  call    cs:__imp_LeaveCriticalSection
0x18000c2cd  xor     r12d, r12d
0x18000c2d0  mov     [rsp+128h+var_DC], r12d
0x18000c2d5  test    rsi, rsi
0x18000c2d8  jz      loc_18000C5F3
0x18000c2de  lea     rdx, [rsp+128h+var_70]; struct CEventSystem2::TransientSubscriber *
0x18000c2e6  mov     rcx, r14; this
0x18000c2e9  call    ?ReleaseTransientSubscriber@CEventSystem2@@AEAAXAEAUTransientSubscriber@1@@Z; CEventSystem2::ReleaseTransientSubscriber(CEventSystem2::TransientSubscriber &)
0x18000c2ee  jmp     loc_18000C5F3
0x18000c2f3  xor     edx, edx
0x18000c2f5  div     dword ptr [r12+8]
0x18000c2fa  mov     rsi, [rsi+rdx*8]
0x18000c2fe  test    rsi, rsi
0x18000c301  jz      loc_18000C1EE
0x18000c307  mov     rax, [rsi+10h]
0x18000c30b  test    r8, r8
0x18000c30e  jz      short loc_18000C36A
0x18000c310  mov     rdx, r8
0x18000c313  sub     rdx, rax
0x18000c316  movzx   ecx, word ptr [rax]
0x18000c319  cmp     cx, [rax+rdx]
0x18000c31d  jnz     short loc_18000C337
0x18000c31f  add     rax, 2
0x18000c323  test    cx, cx
0x18000c326  jnz     short loc_18000C316
0x18000c328  xor     eax, eax
0x18000c32a  test    eax, eax
0x18000c32c  jz      loc_18000C1F0
0x18000c332  mov     rsi, [rsi]
0x18000c335  jmp     short loc_18000C2FE
0x18000c337  sbb     eax, eax
0x18000c339  or      eax, r14d
0x18000c33c  jmp     short loc_18000C32A
0x18000c33e  mov     edi, 80010108h
0x18000c343  mov     [rsp+128h+var_E4], edi
0x18000c347  jmp     loc_18000C5F3
0x18000c34c  mov     r12d, [rsp+128h+var_DC]
0x18000c351  jmp     loc_18000C5F3
0x18000c356  lea     rax, dword_180053104
0x18000c35d  mov     [rsp+128h+var_80], rax
0x18000c365  jmp     loc_18000C220
0x18000c36a  cmp     dword ptr [rax-8], 0
0x18000c36e  jz      loc_18000C1F0
0x18000c374  mov     eax, r14d
0x18000c377  jmp     short loc_18000C32A
0x18000c379  test    edi, edi
0x18000c37b  js      loc_18000C0F8
0x18000c381  mov     [rsp+128h+var_78], rsi
0x18000c389  mov     rcx, [rsp+128h+ppv]
0x18000c38e  mov     rax, [rcx]
0x18000c391  lea     r9, [rsp+128h+var_78]
0x18000c399  mov     r8d, 2
0x18000c39f  mov     rdx, [rsp+128h+pProxy]
0x18000c3a7  mov     rax, [rax+20h]
0x18000c3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b0  mov     edi, eax
0x18000c3b2  test    eax, eax
0x18000c3b4  js      short loc_18000C3D6
0x18000c3b6  mov     rax, [rsp+128h+var_78]
0x18000c3be  test    rax, rax
0x18000c3c1  jz      loc_18000C519
0x18000c3c7  sub     rax, 1
0x18000c3cb  jnz     short loc_18000C3F5
0x18000c3cd  lea     esi, [rax+3]
0x18000c3d0  mov     [rsp+128h+var_D8], esi
0x18000c3d4  xor     edi, edi
0x18000c3d6  mov     rcx, [rsp+128h+ppv]
0x18000c3db  mov     rax, [rcx]
0x18000c3de  mov     rax, [rax+10h]
0x18000c3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e7  mov     [rsp+128h+ppv], 0
0x18000c3f0  jmp     loc_18000C0F8
0x18000c3f5  cmp     rax, 1
0x18000c3f9  jz      loc_18000C50F
0x18000c3ff  mov     r8d, 12h; unsigned __int16
0x18000c405  lea     r9, aUnrecognizedLo; "!\"Unrecognized locality\""
0x18000c40c  lea     edx, [r8+16h]; unsigned int
0x18000c410  lea     rcx, aComComplusSrcE_9; "com\\complus\\src\\events\\shared\\loca"...
0x18000c417  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000c41c  jmp     short loc_18000C3D4
0x18000c41e  call    cs:__imp_GetCurrentThread
0x18000c424  mov     rcx, rax; ThreadHandle
0x18000c427  lea     r9, [rsp+128h+TokenHandle]; TokenHandle
0x18000c42c  mov     r8d, r14d; OpenAsSelf
0x18000c42f  mov     edx, 0Ch; DesiredAccess
0x18000c434  call    cs:__imp_OpenThreadToken
0x18000c43a  test    eax, eax
0x18000c43c  jz      loc_18000C523
0x18000c442  mov     rcx, [rsp+128h+TokenHandle]; TokenHandle
0x18000c447  test    rcx, rcx
0x18000c44a  jz      loc_18000C110
0x18000c450  mov     [rsp+128h+TokenInformation], 0
0x18000c458  mov     [rsp+128h+ReturnLength], 4
0x18000c463  lea     rax, [rsp+128h+ReturnLength]
0x18000c46b  mov     qword ptr [rsp+128h+dwAuthnLevel], rax; ReturnLength
0x18000c470  mov     r9d, 4; TokenInformationLength
0x18000c476  lea     r8, [rsp+128h+TokenInformation]; TokenInformation
0x18000c47b  lea     edx, [r9+5]; TokenInformationClass
0x18000c47f  call    cs:__imp_GetTokenInformation
0x18000c485  test    eax, eax
0x18000c487  jz      short loc_18000C4F1
0x18000c489  cmp     [rsp+128h+TokenInformation], 2
0x18000c48e  jl      loc_18000C538
0x18000c494  cmp     esi, 4
0x18000c497  jnz     loc_18000C110
0x18000c49d  cmp     [rsp+128h+TokenInformation], 3
  ... truncated ...
```
