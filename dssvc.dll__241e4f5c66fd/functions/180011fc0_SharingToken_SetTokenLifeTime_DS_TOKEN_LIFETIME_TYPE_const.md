# SharingToken::SetTokenLifeTime(_DS_TOKEN_LIFETIME_TYPE const &)

- ea: `0x180011fc0`
- end: `0x1800120a5`
- name: `?SetTokenLifeTime@SharingToken@@AEAAJAEBW4_DS_TOKEN_LIFETIME_TYPE@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(SharingToken *__hidden this, const enum _DS_TOKEN_LIFETIME_TYPE *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011c64`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000f468`
- `0x180011fc0`
- `0x1800195ac`
- `0x180019720`
- `0x1800197a4`

## string_xrefs

- `0x18001206e`: `SharingToken::SetTokenLifeTimes failed. HR=0x%x`
- `0x18001207f`: `SharingToken::SetTokenLifeTime`

## pseudocode

```c
__int64 __fastcall SharingToken::SetTokenLifeTime(SharingToken *this, const enum _DS_TOKEN_LIFETIME_TYPE *a2)
{
  __m128d v2; // xmm0
  int *v5; // rax
  int *v6; // rdi
  struct _FILETIME *v7; // rdx
  __int64 v8; // rcx
  int CurrentTimeAsFileTime; // ebx
  __int64 v10; // r8
  struct _FILETIME v11; // rax
  const struct _FILETIME *v12; // rdx
  __m128d v13; // xmm6
  const struct _FILETIME *v14; // rdx
  int *v15; // rax
  int v17; // [rsp+20h] [rbp-58h]
  __int128 v18; // [rsp+30h] [rbp-48h]
  struct _FILETIME FileTime; // [rsp+90h] [rbp+18h] BYREF
  struct _FILETIME v20; // [rsp+98h] [rbp+20h] BYREF

  v5 = tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get((__int64)this);
  FileTime = 0;
  v6 = v5;
  CurrentTimeAsFileTime = DSUtils::GetCurrentTimeAsFileTime(&FileTime, v7);
  if ( CurrentTimeAsFileTime < 0 )
  {
    v15 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v8);
    v17 = CurrentTimeAsFileTime;
    DSLogger::LogError(
      (DSLogger *)v15,
      L"SharingToken::SetTokenLifeTime",
      170,
      L"SharingToken::SetTokenLifeTimes failed. HR=0x%x",
      v17);
  }
  else
  {
    if ( *(_DWORD *)a2 )
      ++v6;
    v11 = DSUtils::FileTimeAddMilliSeconds(
            (DSUtils *)&FileTime,
            (const struct _FILETIME *)(unsigned int)(1000 * *v6),
            v10);
    *(struct _FILETIME *)&v18 = FileTime;
    v20 = v11;
    *((struct _FILETIME *)&v18 + 1) = v11;
    v2.m128d_f64[0] = DSUtils::GetDaysSince1900FromFileTime(&FileTime, v12);
    v13 = v2;
    v2.m128d_f64[0] = DSUtils::GetDaysSince1900FromFileTime(&v20, v14);
    *((_DWORD *)this + 21) = *(_DWORD *)a2;
    *(_OWORD *)((char *)this + 88) = v18;
    *(__m128d *)((char *)this + 104) = _mm_unpacklo_pd(v13, v2);
  }
  return (unsigned int)CurrentTimeAsFileTime;
}

```

## disassembly

```asm
0x180011fc0  mov     [rsp+arg_0], rbx
0x180011fc5  push    rbp
0x180011fc6  push    rsi
0x180011fc7  push    rdi
0x180011fc8  sub     rsp, 60h
0x180011fcc  movaps  [rsp+78h+var_28], xmm6
0x180011fd1  mov     rsi, rdx
0x180011fd4  mov     rbp, rcx
0x180011fd7  call    ?get@?$_LazyImpl@VTokenLifeManager@@V?$lazy_construct@VTokenLifeManager@@@tlx@@V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@3@@tlx@@QEAAAEAVTokenLifeManager@@XZ; tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get(void)
0x180011fdc  lea     rcx, [rsp+78h+FileTime]; lpFileTime
0x180011fe4  mov     qword ptr [rsp+78h+FileTime.dwLowDateTime], 0
0x180011ff0  mov     rdi, rax
0x180011ff3  call    ?GetCurrentTimeAsFileTime@DSUtils@@YAJPEAU_FILETIME@@@Z; DSUtils::GetCurrentTimeAsFileTime(_FILETIME *)
0x180011ff8  mov     ebx, eax
0x180011ffa  test    eax, eax
0x180011ffc  js      short loc_180012069
0x180011ffe  cmp     dword ptr [rsi], 0
0x180012001  jz      short loc_180012007
0x180012003  add     rdi, 4
0x180012007  imul    edx, [rdi], 3E8h; struct _FILETIME *
0x18001200d  lea     rcx, [rsp+78h+FileTime]; this
0x180012015  call    ?FileTimeAddMilliSeconds@DSUtils@@YA?AU_FILETIME@@AEBU2@_J@Z; DSUtils::FileTimeAddMilliSeconds(_FILETIME const &,__int64)
0x18001201a  mov     rcx, qword ptr [rsp+78h+FileTime.dwLowDateTime]
0x180012022  mov     qword ptr [rsp+78h+var_48], rcx
0x180012027  lea     rcx, [rsp+78h+FileTime]; this
0x18001202f  mov     qword ptr [rsp+78h+arg_18.dwLowDateTime], rax
0x180012037  mov     qword ptr [rsp+78h+var_48+8], rax
0x18001203c  call    ?GetDaysSince1900FromFileTime@DSUtils@@YANAEBU_FILETIME@@@Z; DSUtils::GetDaysSince1900FromFileTime(_FILETIME const &)
0x180012041  lea     rcx, [rsp+78h+arg_18]; this
0x180012049  movaps  xmm6, xmm0
0x18001204c  call    ?GetDaysSince1900FromFileTime@DSUtils@@YANAEBU_FILETIME@@@Z; DSUtils::GetDaysSince1900FromFileTime(_FILETIME const &)
0x180012051  mov     eax, [rsi]
0x180012053  movups  xmm1, [rsp+78h+var_48]
0x180012058  mov     [rbp+54h], eax
0x18001205b  unpcklpd xmm6, xmm0
0x18001205f  movups  xmmword ptr [rbp+58h], xmm1
0x180012063  movups  xmmword ptr [rbp+68h], xmm6
0x180012067  jmp     short loc_18001208E
0x180012069  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001206e  lea     r9, aSharingtokenSe; "SharingToken::SetTokenLifeTimes failed."...
0x180012075  mov     [rsp+78h+var_58], ebx
0x180012079  mov     r8d, 0AAh; unsigned int
0x18001207f  lea     rdx, aSharingtokenSe_0; "SharingToken::SetTokenLifeTime"
0x180012086  mov     rcx, rax; this
0x180012089  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001208e  movaps  xmm6, [rsp+78h+var_28]
0x180012093  mov     eax, ebx
0x180012095  mov     rbx, [rsp+78h+arg_0]
0x18001209d  add     rsp, 60h
0x1800120a1  pop     rdi
0x1800120a2  pop     rsi
0x1800120a3  pop     rbp
0x1800120a4  retn
```
