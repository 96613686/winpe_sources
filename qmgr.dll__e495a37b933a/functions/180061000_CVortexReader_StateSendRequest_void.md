# CVortexReader::StateSendRequest(void)

- ea: `0x180061000`
- end: `0x18006177e`
- name: `?StateSendRequest@CVortexReader@@MEAAXXZ`
- size: `1918`
- prototype: `void __fastcall(CVortexReader *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180008b70`
- `0x18000db20`
- `0x18000f5f0`
- `0x18001d7f0`
- `0x18003b3fc`
- `0x180061000`
- `0x180084138`
- `0x18009d024`
- `0x18009e9c8`
- `0x18009ea08`
- `0x1800a3444`
- `0x1800ab738`
- `0x1800ab7fc`
- `0x1800acacc`
- `0x1800bd044`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061391`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061391`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800615a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180061662`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800615a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180061662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800611dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006175e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800611dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006175e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006163a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006168e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006163a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006168e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800612a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800612a3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006142b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006142b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CVortexReader::StateSendRequest(CVortexReader *this)
{
  LONGLONG v2; // rsi
  DWORD LastError; // eax
  signed int v4; // ebx
  unsigned __int64 v5; // rax
  signed int v6; // eax
  _DWORD *v7; // rax
  signed int v8; // eax
  _QWORD *v9; // rdi
  __int64 v10; // r9
  EVENT_LOG *v11; // rcx
  _QWORD *v12; // rsi
  signed int v13; // eax
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  DWORD v17; // eax
  void *v18; // [rsp+50h] [rbp-79h] BYREF
  char v19; // [rsp+58h] [rbp-71h]
  void *v20; // [rsp+60h] [rbp-69h]
  void *v21; // [rsp+68h] [rbp-61h]
  void *v22; // [rsp+70h] [rbp-59h]
  __int64 v23; // [rsp+78h] [rbp-51h]
  void *v24; // [rsp+80h] [rbp-49h]
  void **pExceptionObject; // [rsp+90h] [rbp-39h] BYREF
  __int128 v26; // [rsp+98h] [rbp-31h]
  int v27; // [rsp+A8h] [rbp-21h]
  int v28; // [rsp+ACh] [rbp-1Dh]
  int v29; // [rsp+B0h] [rbp-19h]
  LARGE_INTEGER PerformanceCount; // [rsp+130h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids, this);
  *((_DWORD *)this + 65782) = 12157;
  if ( !*((_QWORD *)this + 32920) || CVortexReader::IsForceOrigin(this) )
  {
    if ( (*((_BYTE *)this + 889) & *((_BYTE *)this + 888)) != 0 && !*((_BYTE *)this + 840) )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
      ApplySchemeCredentials(
        *((_QWORD *)this + 83),
        (_DWORD)this + 724,
        *((_DWORD *)this + 211),
        *((_DWORD *)this + 212),
        *((CCredentialsContainer **)this + 100),
        (CVortexReader *)((char *)this + 263304),
        *((_QWORD *)this + 80) + 92LL,
        *((_QWORD *)this + 80) + 606LL,
        (__int64)this + 856);
    }
    if ( *((_QWORD *)this + 102) )
    {
      CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)&v18, (CVortexReader *)((char *)this + 263304));
      CCustomHeaders::Get(*((_QWORD *)this + 102), &PerformanceCount);
      v2 = PerformanceCount.QuadPart + 12;
      if ( PerformanceCount.QuadPart != -12 && *(_QWORD *)PerformanceCount.QuadPart )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
        }
        if ( !(*(unsigned int (__fastcall **)(_QWORD, LONGLONG, __int64, __int64))(**((_QWORD **)this + 83) + 8LL))(
                *((_QWORD *)this + 83),
                v2,
                0xFFFFFFFFLL,
                2684354560LL) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              (int)WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids,
              v2,
              LastError);
          if ( v4 > 0 )
            v4 = (unsigned __int16)v4 | 0x80070000;
          v26 = 0;
          pExceptionObject = &ComError::`vftable';
          v27 = v4;
          v28 = 479;
          v29 = 1;
          throw (ComError *)&pExceptionObject;
        }
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
        }
      }
      GenericStringHandle<unsigned short>::FreeIt(&PerformanceCount);
      CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&v18);
    }
    *((_BYTE *)this + 263440) = 1;
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    *((LARGE_INTEGER *)this + 32933) = PerformanceCount;
    *((_BYTE *)this + 263456) = 1;
    v5 = *((_QWORD *)this + 20);
    if ( v5 >= *((_QWORD *)this + 32922) && v5 < *((_QWORD *)this + 32923) || *((_BYTE *)this + 263397) )
    {
      if ( CVortexReader::IsForceOrigin(this) )
      {
        CNestedImpersonation::CNestedImpersonation(
          (CNestedImpersonation *)&v18,
          (CVortexReader *)((char *)this + 263304));
        v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 32917) + 24LL))(
               *((_QWORD *)this + 32917),
               *((_QWORD *)this + 83));
        if ( v6 )
        {
          if ( v6 > 0 )
            v6 = (unsigned __int16)v6 | 0x80070000;
          v26 = 0;
          pExceptionObject = &ComError::`vftable';
          v27 = v6;
          v28 = 528;
          v29 = 1;
          throw (ComError *)&pExceptionObject;
        }
        CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&v18);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
        }
        *((_QWORD *)this + 32918) = 0;
      }
    }
    else
    {
      CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v18);
      v19 = 0;
      v20 = (void *)*((_QWORD *)this + 32913);
      _InterlockedIncrement((volatile signed __int32 *)v20 + 2);
      v21 = 0;
      v7 = HeapAlloc(hBitsHeap, 8u, 4u);
      if ( !v7 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
        v26 = 0;
        pExceptionObject = &ComError::`vftable';
        v27 = -2147024882;
        v28 = 0;
        v29 = 1;
        throw (ComError *)&pExceptionObject;
      }
      *v7 = 1;
      v22 = v7;
      v23 = 0;
      _InterlockedIncrement(&dword_180145058);
      v24 = &GenericStringHandle<unsigned short>::s_EmptyString;
      if ( !v19 )
      {
        if ( !ImpersonateLoggedOnUser(*(HANDLE *)v20) )
        {
          v8 = GetLastError();
          if ( v8 > 0 )
            v8 = (unsigned __int16)v8 | 0x80070000;
          v26 = 0;
          pExceptionObject = &ComError::`vftable';
          v27 = v8;
          v28 = 0;
          v29 = 1;
          throw (ComError *)&pExceptionObject;
        }
        v19 = 1;
      }
      v9 = (_QWORD *)((char *)this + 263344);
      v10 = *((_QWORD *)this + 32918);
      if ( v10 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids, v10);
            v11 = WPP_GLOBAL_Control;
          }
          if ( v11 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x1000) != 0 )
            WPP_SF_q(*((_QWORD *)v11 + 2), 29, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids, *v9);
        }
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 32917) + 80LL))(*((_QWORD *)this + 32917), *v9);
        *v9 = 0;
        v12 = (_QWORD *)((char *)this + 263344);
      }
      else
      {
        v12 = (_QWORD *)((char *)this + 263344);
      }
      v13 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 32917) + 16LL))(
              *((_QWORD *)this + 32917),
              (char *)this + 263344,
              *((_QWORD *)this + 83));
      if ( v13 == 50 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
          v12 = (_QWORD *)((char *)this + 263344);
        }
        *((_QWORD *)this + 32918) = 0;
      }
      else if ( v13 )
      {
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        v26 = 0;
        pExceptionObject = &ComError::`vftable';
        v27 = v13;
        v28 = 511;
        v29 = 1;
        throw (ComError *)&pExceptionObject;
      }
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids, *v12);
      if ( v19 )
      {
        SetThreadToken(0, *(HANDLE *)v18);
        v19 = 0;
      }
      v14 = v24;
      if ( v24 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
          operator delete(v24, 0x10u);
        v24 = 0;
      }
      if ( v23 )
        std::default_delete<AppPackageInfo>::operator()(v14, v23);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22, 0xFFFFFFFF) == 1 )
      {
        operator delete(v22, 4u);
        operator delete(v21, 0);
        v22 = 0;
        v21 = 0;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20 + 2, 0xFFFFFFFF) == 1 )
      {
        v15 = v20;
        if ( (unsigned __int64)(*(_QWORD *)v20 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v20);
          *(_QWORD *)v20 = 0;
          v15 = v20;
        }
        operator delete(v15, 0x10u);
        v20 = 0;
      }
      SetThreadToken(0, *(HANDLE *)v18);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 2, 0xFFFFFFFF) == 1 )
      {
        v16 = v18;
        if ( (unsigned __int64)(*(_QWORD *)v18 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v18);
          *(_QWORD *)v18 = 0;
          v16 = v18;
        }
        operator delete(v16, 0x10u);
      }
    }
    if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, CVortexReader *))(**((_QWORD **)this + 83) + 40LL))(
            *((_QWORD *)this + 83),
            0,
            0,
            0,
            0,
            0,
            this) )
    {
      v17 = GetLastError();
      CHttpReader::DealWithSendError(this, v17);
    }
  }
  else
  {
    (*(void (__fastcall **)(char *, _QWORD, _QWORD, __int64))(*((_QWORD *)this + 65) + 56LL))(
      (char *)this + 520,
      0,
      *((_QWORD *)this + 22),
      5);
  }
}

```

## disassembly

```asm
0x180061000  push    rbp
0x180061002  push    rbx
0x180061003  push    rsi
0x180061004  push    rdi
0x180061005  push    r14
0x180061007  push    r15
0x180061009  lea     rbp, [rsp-2Fh]
0x18006100e  sub     rsp, 0F8h
0x180061015  mov     rbx, rcx
0x180061018  lea     r15, WPP_GLOBAL_Control
0x18006101f  mov     rcx, cs:WPP_GLOBAL_Control
0x180061026  cmp     rcx, r15
0x180061029  jz      short loc_18006104C
0x18006102b  test    dword ptr [rcx+1Ch], 800h
0x180061032  jz      short loc_18006104C
0x180061034  mov     edx, 17h
0x180061039  mov     r9, rbx
0x18006103c  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x180061043  mov     rcx, [rcx+10h]
0x180061047  call    WPP_SF_q
0x18006104c  mov     dword ptr [rbx+403D8h], 2F7Dh
0x180061056  cmp     qword ptr [rbx+404C0h], 0
0x18006105e  jz      short loc_180061093
0x180061060  mov     rcx, rbx; this
0x180061063  call    ?IsForceOrigin@CVortexReader@@QEBA_NXZ; CVortexReader::IsForceOrigin(void)
0x180061068  test    al, al
0x18006106a  jnz     short loc_180061093
0x18006106c  lea     rcx, [rbx+208h]
0x180061073  mov     rax, [rcx]
0x180061076  mov     r9d, 5
0x18006107c  mov     r8, [rbx+0B0h]
0x180061083  xor     edx, edx
0x180061085  mov     rax, [rax+38h]
0x180061089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006108e  jmp     loc_18006176E
0x180061093  movzx   eax, byte ptr [rbx+379h]
0x18006109a  test    [rbx+378h], al
0x1800610a0  jz      loc_18006113E
0x1800610a6  cmp     byte ptr [rbx+348h], 0
0x1800610ad  jnz     loc_18006113E
0x1800610b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800610ba  cmp     rcx, r15
0x1800610bd  jz      short loc_1800610DD
0x1800610bf  test    dword ptr [rcx+1Ch], 800h
0x1800610c6  jz      short loc_1800610DD
0x1800610c8  mov     edx, 18h
0x1800610cd  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x1800610d4  mov     rcx, [rcx+10h]
0x1800610d8  call    WPP_SF_
0x1800610dd  mov     rax, [rbx+280h]
0x1800610e4  lea     rcx, [rbx+358h]
0x1800610eb  lea     r8, [rax+25Eh]
0x1800610f2  add     rax, 5Ch ; '\'
0x1800610f6  lea     r9, [rbx+40488h]
0x1800610fd  lea     rdx, [rbx+2D4h]; int
0x180061104  mov     [rsp+120h+var_E0], rcx; __int64
0x180061109  mov     [rsp+120h+var_E8], r8; __int64
0x18006110e  mov     [rsp+120h+var_F0], rax; __int64
0x180061113  mov     [rsp+120h+var_F8], r9; struct TokenHandle *
0x180061118  mov     rax, [rbx+320h]
0x18006111f  mov     [rsp+120h+var_100], rax; CCredentialsContainer *
0x180061124  mov     r9d, [rbx+350h]; int
0x18006112b  mov     r8d, [rbx+34Ch]; int
0x180061132  mov     rcx, [rbx+298h]; int
0x180061139  call    ?ApplySchemeCredentials@@YA_NPEAVIHttpRequest@@PEAKKKPEBVCCredentialsContainer@@AEBVTokenHandle@@PEAG4AEAV?$GenericStringHandle@G@@@Z; ApplySchemeCredentials(IHttpRequest *,ulong *,ulong,ulong,CCredentialsContainer const *,TokenHandle const &,ushort *,ushort *,GenericStringHandle<ushort> &)
0x18006113e  lea     rdi, [rbx+40488h]
0x180061145  cmp     qword ptr [rbx+330h], 0
0x18006114d  jz      loc_180061291
0x180061153  mov     rdx, rdi; struct TokenHandle *
0x180061156  lea     rcx, [rbp+57h+var_D0]; this
0x18006115a  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x18006115f  nop
0x180061160  lea     rdx, [rbp+57h+PerformanceCount]
0x180061164  mov     rcx, [rbx+330h]
0x18006116b  call    ?Get@CCustomHeaders@@QEAA?AV?$GenericStringHandle@G@@XZ; CCustomHeaders::Get(void)
0x180061170  nop
0x180061171  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x180061175  lea     rsi, [rax+0Ch]
0x180061179  test    rsi, rsi
0x18006117c  jz      loc_18006127E
0x180061182  cmp     qword ptr [rax], 0
0x180061186  jbe     loc_18006127E
0x18006118c  mov     rcx, cs:WPP_GLOBAL_Control
0x180061193  cmp     rcx, r15
0x180061196  jz      short loc_1800611B6
0x180061198  test    dword ptr [rcx+1Ch], 800h
0x18006119f  jz      short loc_1800611B6
0x1800611a1  mov     edx, 19h
0x1800611a6  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x1800611ad  mov     rcx, [rcx+10h]
0x1800611b1  call    WPP_SF_
0x1800611b6  mov     rcx, [rbx+298h]
0x1800611bd  mov     rax, [rcx]
0x1800611c0  mov     r9d, 0A0000000h
0x1800611c6  mov     r8d, 0FFFFFFFFh
0x1800611cc  mov     rdx, rsi
0x1800611cf  mov     rax, [rax+8]
0x1800611d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800611d8  test    eax, eax
0x1800611da  jnz     short loc_180061253
0x1800611dc  call    cs:__imp_GetLastError
0x1800611e2  mov     ebx, eax
0x1800611e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800611eb  cmp     rcx, r15
0x1800611ee  jz      short loc_180061212
0x1800611f0  test    byte ptr [rcx+1Ch], 4
0x1800611f4  jz      short loc_180061212
0x1800611f6  mov     edx, 1Ah
0x1800611fb  mov     dword ptr [rsp+120h+var_100], eax
0x1800611ff  mov     r9, rsi
0x180061202  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x180061209  mov     rcx, [rcx+10h]
0x18006120d  call    WPP_SF_Sd
0x180061212  test    ebx, ebx
0x180061214  jle     short loc_18006121F
0x180061216  movzx   ebx, bx
0x180061219  or      ebx, 80070000h
0x18006121f  xorps   xmm0, xmm0
0x180061222  movups  [rbp+57h+var_88], xmm0
0x180061226  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18006122d  mov     [rbp+57h+pExceptionObject], rcx
0x180061231  mov     [rbp+57h+var_78], ebx
0x180061234  mov     [rbp+57h+var_74], 1DFh
0x18006123b  mov     [rbp+57h+var_70], 1
0x180061242  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180061249  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006124d  call    _CxxThrowException_0
0x180061253  mov     rcx, cs:WPP_GLOBAL_Control
0x18006125a  cmp     rcx, r15
0x18006125d  jz      short loc_18006127E
0x18006125f  test    dword ptr [rcx+1Ch], 800h
0x180061266  jz      short loc_18006127E
0x180061268  mov     edx, 1Bh
0x18006126d  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x180061274  mov     rcx, [rcx+10h]
0x180061278  call    WPP_SF_
0x18006127d  nop
0x18006127e  lea     rcx, [rbp+57h+PerformanceCount]
0x180061282  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x180061287  nop
0x180061288  lea     rcx, [rbp+57h+var_D0]; this
0x18006128c  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x180061291  mov     byte ptr [rbx+40510h], 1
0x180061298  xor     r14d, r14d
0x18006129b  mov     qword ptr [rbp+57h+PerformanceCount], r14
0x18006129f  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800612a3  call    cs:__imp_QueryPerformanceCounter
0x1800612a9  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x1800612ad  mov     [rbx+40528h], rax
0x1800612b4  mov     byte ptr [rbx+40520h], 1
0x1800612bb  mov     rax, [rbx+0A0h]
0x1800612c2  cmp     rax, [rbx+404D0h]
0x1800612c9  jb      loc_180061355
0x1800612cf  cmp     rax, [rbx+404D8h]
0x1800612d6  jnb     short loc_180061355
0x1800612d8  mov     rcx, rbx; this
0x1800612db  call    ?IsForceOrigin@CVortexReader@@QEBA_NXZ; CVortexReader::IsForceOrigin(void)
0x1800612e0  cmp     al, 1
0x1800612e2  jnz     loc_1800616FF
0x1800612e8  mov     rdx, rdi; struct TokenHandle *
0x1800612eb  lea     rcx, [rbp+57h+var_D0]; this
0x1800612ef  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x1800612f4  nop
0x1800612f5  mov     rcx, [rbx+404A8h]
0x1800612fc  mov     rax, [rcx]
0x1800612ff  mov     rdx, [rbx+298h]
0x180061306  mov     rax, [rax+18h]
0x18006130a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006130f  test    eax, eax
0x180061311  jz      loc_1800616F4
0x180061317  jle     short loc_180061321
0x180061319  movzx   eax, ax
0x18006131c  or      eax, 80070000h
0x180061321  xorps   xmm0, xmm0
0x180061324  movups  [rbp+57h+var_88], xmm0
0x180061328  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18006132f  mov     [rbp+57h+pExceptionObject], rcx
0x180061333  mov     [rbp+57h+var_78], eax
0x180061336  mov     [rbp+57h+var_74], 210h
0x18006133d  mov     [rbp+57h+var_70], 1
0x180061344  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006134b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006134f  call    _CxxThrowException_0
0x180061355  cmp     [rbx+404E5h], r14b
0x18006135c  jnz     loc_1800612D8
0x180061362  lea     rcx, [rbp+57h+var_D0]; this
0x180061366  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x18006136b  nop
0x18006136c  mov     [rbp+57h+var_C8], 0
0x180061370  mov     rax, [rdi]
0x180061373  mov     [rbp+57h+var_C0], rax
0x180061377  lock inc dword ptr [rax+8]
0x18006137b  mov     [rbp+57h+var_B8], r14
0x18006137f  mov     edx, 8; dwFlags
0x180061384  mov     r8d, 4; dwBytes
0x18006138a  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180061391  call    cs:__imp_HeapAlloc
0x180061397  test    rax, rax
0x18006139a  jnz     short loc_1800613FE
0x18006139c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800613a3  cmp     rcx, r15
0x1800613a6  jz      short loc_1800613C9
0x1800613a8  test    byte ptr [rcx+1Ch], 4
0x1800613ac  jz      short loc_1800613C9
0x1800613ae  mov     edx, 0Ah
0x1800613b3  mov     r9d, 4
0x1800613b9  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800613c0  mov     rcx, [rcx+10h]
0x1800613c4  call    WPP_SF_d
0x1800613c9  xorps   xmm0, xmm0
0x1800613cc  movups  [rbp+57h+var_88], xmm0
0x1800613d0  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800613d7  mov     [rbp+57h+pExceptionObject], rcx
0x1800613db  mov     [rbp+57h+var_78], 8007000Eh
0x1800613e2  mov     [rbp+57h+var_74], r14d
0x1800613e6  mov     [rbp+57h+var_70], 1
0x1800613ed  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800613f4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800613f8  call    _CxxThrowException_0
0x1800613fe  mov     dword ptr [rax], 1
0x180061404  mov     [rbp+57h+var_B0], rax
0x180061408  mov     [rbp+57h+var_A8], r14
0x18006140c  lock inc cs:dword_180145058
0x180061413  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18006141a  mov     [rbp+57h+var_A0], rax
0x18006141e  cmp     [rbp+57h+var_C8], 0
0x180061422  jnz     short loc_18006147C
0x180061424  mov     rcx, [rbp+57h+var_C0]
0x180061428  mov     rcx, [rcx]; hToken
0x18006142b  call    cs:__imp_ImpersonateLoggedOnUser
0x180061431  test    eax, eax
0x180061433  jnz     short loc_180061478
0x180061435  call    cs:__imp_GetLastError
0x18006143b  test    eax, eax
0x18006143d  jle     short loc_180061447
0x18006143f  movzx   eax, ax
0x180061442  or      eax, 80070000h
0x180061447  xorps   xmm0, xmm0
0x18006144a  movups  [rbp+57h+var_88], xmm0
0x18006144e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180061455  mov     [rbp+57h+pExceptionObject], rcx
0x180061459  mov     [rbp+57h+var_78], eax
0x18006145c  mov     [rbp+57h+var_74], r14d
0x180061460  mov     [rbp+57h+var_70], 1
0x180061467  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006146e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180061472  call    _CxxThrowException_0
0x180061478  mov     [rbp+57h+var_C8], 1
0x18006147c  lea     rdi, [rbx+404B0h]
0x180061483  mov     r9, [rdi]
0x180061486  test    r9, r9
0x180061489  jz      short loc_180061504
0x18006148b  mov     rcx, cs:WPP_GLOBAL_Control
0x180061492  cmp     rcx, r15
0x180061495  jz      short loc_1800614E2
0x180061497  test    dword ptr [rcx+1Ch], 1000h
0x18006149e  jz      short loc_1800614BC
0x1800614a0  mov     edx, 1Ch
0x1800614a5  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x1800614ac  mov     rcx, [rcx+10h]
0x1800614b0  call    WPP_SF_q
0x1800614b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800614bc  cmp     rcx, r15
0x1800614bf  jz      short loc_1800614E2
0x1800614c1  test    dword ptr [rcx+1Ch], 1000h
0x1800614c8  jz      short loc_1800614E2
0x1800614ca  mov     edx, 1Dh
0x1800614cf  mov     r9, [rdi]
0x1800614d2  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x1800614d9  mov     rcx, [rcx+10h]
0x1800614dd  call    WPP_SF_q
0x1800614e2  mov     rcx, [rbx+404A8h]
0x1800614e9  mov     rax, [rcx]
0x1800614ec  mov     rdx, [rdi]
0x1800614ef  mov     rax, [rax+50h]
0x1800614f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800614f8  mov     [rdi], r14
0x1800614fb  lea     rsi, [rbx+404B0h]
0x180061502  jmp     short loc_180061507
0x180061504  mov     rsi, rdi
0x180061507  mov     rcx, [rbx+404A8h]
0x18006150e  mov     rax, [rcx]
0x180061511  mov     r8, [rbx+298h]
0x180061518  mov     rdx, rdi
0x18006151b  mov     rax, [rax+10h]
0x18006151f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061524  cmp     eax, 32h ; '2'
0x180061527  jnz     loc_1800616AE
0x18006152d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061534  cmp     rcx, r15
0x180061537  jz      short loc_18006155E
0x180061539  test    dword ptr [rcx+1Ch], 1000h
0x180061540  jz      short loc_18006155E
0x180061542  mov     edx, 1Eh
0x180061547  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x18006154e  mov     rcx, [rcx+10h]
0x180061552  call    WPP_SF_
0x180061557  lea     rsi, [rbx+404B0h]
0x18006155e  mov     [rbx+404B0h], r14
0x180061565  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
