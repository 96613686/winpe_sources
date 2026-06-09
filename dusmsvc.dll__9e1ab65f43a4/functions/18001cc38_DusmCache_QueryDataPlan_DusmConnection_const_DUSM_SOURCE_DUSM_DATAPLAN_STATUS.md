# DusmCache::QueryDataPlan(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS *)

- ea: `0x18001cc38`
- end: `0x18001ce5b`
- name: `?QueryDataPlan@DusmCache@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_DATAPLAN_STATUS@@@Z`
- size: `547`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x180014db0`
- `0x1800151d0`
- `0x180015670`
- `0x1800309c0`

## callees

- `0x180003724`
- `0x180007c90`
- `0x180012fcc`
- `0x180013444`
- `0x18001742c`
- `0x18001b708`
- `0x18001b754`
- `0x18001cc38`
- `0x18001d87c`
- `0x18001fb2c`
- `0x180028f48`
- `0x18002a860`

## string_xrefs

- `0x18001ce21`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001ce49`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001ce37`: `DusmCache::QueryDataPlan::source::public`
- `0x18001ce0f`: `DusmCache::QueryDataPlan::source::default`

## pseudocode

```c
__int64 __fastcall DusmCache::QueryDataPlan(const struct DusmConnection *a1, unsigned int a2, __int64 a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // r14d
  unsigned int Source; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int128 v13; // xmm1
  int v14; // eax
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  const char *v17; // [rsp+28h] [rbp-61h]
  __int64 v18; // [rsp+40h] [rbp-49h] BYREF
  __int64 v19; // [rsp+48h] [rbp-41h] BYREF
  __int64 v20; // [rsp+50h] [rbp-39h] BYREF
  __int64 v21; // [rsp+58h] [rbp-31h] BYREF
  __int128 v22; // [rsp+60h] [rbp-29h] BYREF
  __int128 v23; // [rsp+70h] [rbp-19h]
  __int128 v24; // [rsp+80h] [rbp-9h]
  __int128 v25; // [rsp+90h] [rbp+7h]
  int v26; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *(_OWORD *)a3 = UNKNOWN_DATA_PLAN;
  v5 = a2;
  *(_OWORD *)(a3 + 16) = xmmword_180050F90;
  *(_OWORD *)(a3 + 32) = xmmword_180050FA0;
  *(_OWORD *)(a3 + 48) = xmmword_180050FB0;
  *(_DWORD *)(a3 + 64) = 0;
  v6 = *((_DWORD *)a1 + 4);
  if ( a2 == 1 )
  {
    if ( v6 == 3 )
    {
      Source = DusmStore::QuerySource((__int64)a1);
      v5 = Source;
      if ( Source != 2 && Source != 3 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x30A,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
          (const char *)0xD,
          (unsigned int)"DusmCache::QueryDataPlan::source::public",
          v17);
    }
    else
    {
      v5 = 2;
    }
  }
  else if ( a2 - 2 > 1 )
  {
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x312,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::QueryDataPlan::source::default",
      v17);
  }
  v22 = UNKNOWN_DATA_PLAN;
  v23 = xmmword_180050F90;
  v24 = xmmword_180050FA0;
  v25 = xmmword_180050FB0;
  v26 = 0;
  if ( !(unsigned int)DusmStore::QueryDataPlan((__int64)a1, v5, &v22) )
    return 0;
  if ( !(unsigned int)DusmIsValidDataPlan(&v22) )
  {
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v9, v8) + 8) > 5u )
    {
      v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a1 + 144);
      v19 = DusmMediaTypeToSz(v6);
      v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a1 + 48);
      v21 = (__int64)a1 + 32;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v10,
        (int)&byte_180056BDF,
        v10,
        v11,
        &v21,
        (const WCHAR **)&v20,
        (const WCHAR **)&v19,
        (const WCHAR **)&v18);
    }
    DusmCache::DeleteInvalidDataPlan(a1, v5);
    return 0;
  }
  DusmCore::RetrieveDataPlanValues(a1, (struct _DUSM_DATAPLAN_STATUS *)&v22);
  v13 = v23;
  v14 = v26;
  *(_OWORD *)a3 = v22;
  v15 = v24;
  *(_OWORD *)(a3 + 16) = v13;
  v16 = v25;
  *(_OWORD *)(a3 + 32) = v15;
  *(_OWORD *)(a3 + 48) = v16;
  *(_DWORD *)(a3 + 64) = v14;
  return 1;
}

```

## disassembly

```asm
0x18001cc38  push    rbp
0x18001cc3a  push    rbx
0x18001cc3b  push    rsi
0x18001cc3c  push    rdi
0x18001cc3d  push    r14
0x18001cc3f  lea     rbp, [rsp-37h]
0x18001cc44  sub     rsp, 0C0h
0x18001cc4b  mov     rax, cs:__security_cookie
0x18001cc52  xor     rax, rsp
0x18001cc55  mov     [rbp+57h+var_30], rax
0x18001cc59  movaps  xmm0, cs:?UNKNOWN_DATA_PLAN@@3U_DUSM_DATAPLAN_STATUS@@B; _DUSM_DATAPLAN_STATUS const UNKNOWN_DATA_PLAN
0x18001cc60  mov     rsi, rcx
0x18001cc63  movups  xmmword ptr [r8], xmm0
0x18001cc67  mov     rdi, r8
0x18001cc6a  mov     ebx, edx
0x18001cc6c  movaps  xmm1, cs:xmmword_180050F90
0x18001cc73  movups  xmmword ptr [r8+10h], xmm1
0x18001cc78  movaps  xmm0, cs:xmmword_180050FA0
0x18001cc7f  movups  xmmword ptr [r8+20h], xmm0
0x18001cc84  movaps  xmm1, cs:xmmword_180050FB0
0x18001cc8b  movups  xmmword ptr [r8+30h], xmm1
0x18001cc90  mov     eax, cs:dword_180050FC0
0x18001cc96  mov     [r8+40h], eax
0x18001cc9a  mov     r14d, [rcx+10h]
0x18001cc9e  mov     ecx, edx
0x18001cca0  sub     ecx, 1
0x18001cca3  jz      short loc_18001CCB5
0x18001cca5  sub     ecx, 1
0x18001cca8  jz      short loc_18001CCDA
0x18001ccaa  cmp     ecx, 1
0x18001ccad  jnz     loc_18001CE0B
0x18001ccb3  jmp     short loc_18001CCDA
0x18001ccb5  cmp     r14d, 3
0x18001ccb9  jnz     short loc_18001CCD5
0x18001ccbb  mov     rcx, rsi
0x18001ccbe  call    ?QuerySource@DusmStore@@SA?AW4_DUSM_SOURCE@@AEBVDusmConnection@@@Z; DusmStore::QuerySource(DusmConnection const &)
0x18001ccc3  mov     ebx, eax
0x18001ccc5  cmp     eax, 2
0x18001ccc8  jz      short loc_18001CCDA
0x18001ccca  cmp     eax, r14d
0x18001cccd  jnz     loc_18001CE33
0x18001ccd3  jmp     short loc_18001CCDA
0x18001ccd5  mov     ebx, 2
0x18001ccda  movaps  xmm0, cs:?UNKNOWN_DATA_PLAN@@3U_DUSM_DATAPLAN_STATUS@@B; _DUSM_DATAPLAN_STATUS const UNKNOWN_DATA_PLAN
0x18001cce1  lea     r8, [rbp+57h+var_80]
0x18001cce5  movaps  xmm1, cs:xmmword_180050F90
0x18001ccec  mov     edx, ebx
0x18001ccee  mov     eax, cs:dword_180050FC0
0x18001ccf4  mov     rcx, rsi
0x18001ccf7  movaps  [rbp+57h+var_80], xmm0
0x18001ccfb  movaps  xmm0, cs:xmmword_180050FA0
0x18001cd02  movaps  [rbp+57h+var_70], xmm1
0x18001cd06  movaps  xmm1, cs:xmmword_180050FB0
0x18001cd0d  movaps  [rbp+57h+var_60], xmm0
0x18001cd11  movaps  [rbp+57h+var_50], xmm1
0x18001cd15  mov     [rbp+57h+var_40], eax
0x18001cd18  call    ?QueryDataPlan@DusmStore@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@AEAU_DUSM_DATAPLAN_STATUS@@@Z; DusmStore::QueryDataPlan(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS &)
0x18001cd1d  test    eax, eax
0x18001cd1f  jz      loc_18001CDB7
0x18001cd25  mov     edx, ebx
0x18001cd27  lea     rcx, [rbp+57h+var_80]
0x18001cd2b  call    ?DusmIsValidDataPlan@@YAHAEBU_DUSM_DATAPLAN_STATUS@@W4_DUSM_SOURCE@@@Z; DusmIsValidDataPlan(_DUSM_DATAPLAN_STATUS const &,_DUSM_SOURCE)
0x18001cd30  test    eax, eax
0x18001cd32  jnz     loc_18001CDD3
0x18001cd38  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001cd3d  mov     r8, [rax+8]
0x18001cd41  mov     eax, [r8]
0x18001cd44  cmp     eax, 5
0x18001cd47  jbe     short loc_18001CDAD
0x18001cd49  lea     rcx, [rsi+90h]
0x18001cd50  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cd55  mov     ecx, r14d
0x18001cd58  mov     [rbp+57h+var_A0], rax
0x18001cd5c  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18001cd61  lea     rcx, [rsi+30h]
0x18001cd65  mov     [rbp+57h+var_98], rax
0x18001cd69  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cd6e  mov     [rbp+57h+var_90], rax
0x18001cd72  lea     rdx, byte_180056BDF; int
0x18001cd79  lea     rax, [rsi+20h]
0x18001cd7d  mov     rcx, r8; int
0x18001cd80  mov     [rbp+57h+var_88], rax
0x18001cd84  lea     rax, [rbp+57h+var_A0]
0x18001cd88  mov     [rsp+0E0h+var_A8], rax; __int64
0x18001cd8d  lea     rax, [rbp+57h+var_98]
0x18001cd91  mov     [rsp+0E0h+var_B0], rax; __int64
0x18001cd96  lea     rax, [rbp+57h+var_90]
0x18001cd9a  mov     [rsp+0E0h+var_B8], rax; __int64
0x18001cd9f  lea     rax, [rbp+57h+var_88]
0x18001cda3  mov     qword ptr [rsp+0E0h+var_C0], rax; __int64
0x18001cda8  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18001cdad  mov     edx, ebx
0x18001cdaf  mov     rcx, rsi
0x18001cdb2  call    ?DeleteInvalidDataPlan@DusmCache@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@@Z; DusmCache::DeleteInvalidDataPlan(DusmConnection const &,_DUSM_SOURCE)
0x18001cdb7  xor     eax, eax
0x18001cdb9  mov     rcx, [rbp+57h+var_30]
0x18001cdbd  xor     rcx, rsp; StackCookie
0x18001cdc0  call    __security_check_cookie
0x18001cdc5  add     rsp, 0C0h
0x18001cdcc  pop     r14
0x18001cdce  pop     rdi
0x18001cdcf  pop     rsi
0x18001cdd0  pop     rbx
0x18001cdd1  pop     rbp
0x18001cdd2  retn
0x18001cdd3  lea     rdx, [rbp+57h+var_80]; struct _DUSM_DATAPLAN_STATUS *
0x18001cdd7  mov     rcx, rsi; struct DusmConnection *
0x18001cdda  call    ?RetrieveDataPlanValues@DusmCore@@SAXAEBVDusmConnection@@PEAU_DUSM_DATAPLAN_STATUS@@@Z; DusmCore::RetrieveDataPlanValues(DusmConnection const &,_DUSM_DATAPLAN_STATUS *)
0x18001cddf  movaps  xmm0, [rbp+57h+var_80]
0x18001cde3  movaps  xmm1, [rbp+57h+var_70]
0x18001cde7  mov     eax, [rbp+57h+var_40]
0x18001cdea  movups  xmmword ptr [rdi], xmm0
0x18001cded  movaps  xmm0, [rbp+57h+var_60]
0x18001cdf1  movups  xmmword ptr [rdi+10h], xmm1
0x18001cdf5  movaps  xmm1, [rbp+57h+var_50]
0x18001cdf9  movups  xmmword ptr [rdi+20h], xmm0
0x18001cdfd  movups  xmmword ptr [rdi+30h], xmm1
0x18001ce01  mov     [rdi+40h], eax
0x18001ce04  mov     eax, 1
0x18001ce09  jmp     short loc_18001CDB9
0x18001ce0b  mov     rcx, [rbp+5Fh]; this
0x18001ce0f  lea     rax, aDusmcacheQuery_6; "DusmCache::QueryDataPlan::source::defau"...
0x18001ce16  mov     r9d, 57h ; 'W'; char *
0x18001ce1c  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x18001ce21  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001ce28  mov     edx, 312h; void *
0x18001ce2d  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001ce33  mov     rcx, [rbp+5Fh]; this
0x18001ce37  lea     rax, aDusmcacheQuery; "DusmCache::QueryDataPlan::source::publi"...
0x18001ce3e  mov     r9d, 0Dh; char *
0x18001ce44  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x18001ce49  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001ce50  mov     edx, 30Ah; void *
0x18001ce55  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
