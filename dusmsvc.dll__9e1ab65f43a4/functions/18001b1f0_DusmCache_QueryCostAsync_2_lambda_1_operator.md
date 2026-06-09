# _DusmCache::QueryCostAsync_::_2_::_lambda_1_::operator()

- ea: `0x18001b1f0`
- end: `0x18001b343`
- name: `_DusmCache::QueryCostAsync_::_2_::_lambda_1_::operator()`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001db00`

## callees

- `0x18001b1f0`
- `0x18001cee0`
- `0x18001d674`
- `0x18001d87c`
- `0x180034d24`
- `0x1800381b8`
- `0x18003aa18`

## string_xrefs

- `0x18001b330`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001b320`: `DusmCache::QueryCostAsync::SubmitWork::mediaType`

## pseudocode

```c
void __fastcall DusmCache::QueryCostAsync_::_2_::_lambda_1_::operator()(__int64 a1)
{
  __int64 v1; // rbx
  int v2; // esi
  int v3; // ecx
  int v4; // ecx
  __int64 v5; // r14
  int v6; // edi
  void *v7; // rdx
  wil *v8; // rcx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  wil *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ebx
  const wil::ResultException *v15; // rdi
  _DWORD *v16; // r8
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // rdx
  int v20; // edi
  __int64 v21; // rcx
  int v22; // ebx
  _DWORD *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  const char *v26; // [rsp+28h] [rbp-90h]
  int v27; // [rsp+50h] [rbp-68h]
  int v28; // [rsp+54h] [rbp-64h]
  int v29; // [rsp+54h] [rbp-64h]
  int v30; // [rsp+58h] [rbp-60h] BYREF
  int v31; // [rsp+5Ch] [rbp-5Ch] BYREF
  __int64 v32; // [rsp+60h] [rbp-58h] BYREF
  int v33; // [rsp+68h] [rbp-50h] BYREF
  __int64 v34; // [rsp+70h] [rbp-48h]
  const WCHAR *v35; // [rsp+78h] [rbp-40h] BYREF
  const wchar_t *v36; // [rsp+80h] [rbp-38h] BYREF
  const wil::ResultException *v37; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  try
  {
    v1 = a1;
    v34 = a1;
    v32 = UNKNOWN_COST_DATA;
    v2 = 0;
    v3 = *(_DWORD *)(a1 + 8) - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        if ( v4 != 1 )
          wil::details::in1diag3::Throw_Win32Msg(
            retaddr,
            (void *)0x1D1,
            (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
            (const char *)0x57,
            (unsigned int)"DusmCache::QueryCostAsync::SubmitWork::mediaType",
            v26);
        v5 = v1 + 16;
        v6 = DusmWwan::QueryCost(v1 + 16, *(unsigned int *)(v1 + 336), &v32);
      }
      else
      {
        v5 = v1 + 16;
        v6 = (unsigned __int8)DusmWlan::QueryCost(v1 + 16, *(unsigned int *)(v1 + 336), &v32);
      }
    }
    else
    {
      v5 = v1 + 16;
      v6 = DusmEthernet::QueryCost(v1 + 16, *(unsigned int *)(v1 + 336), &v32);
    }
    v27 = v6;
    DusmCache::SetCostCache(
      (__int64)DusmCache::s_pInstance,
      v5,
      *(_DWORD *)(v1 + 336),
      (unsigned int *)&v32,
      v6 == 0,
      0);
  }
  catch ( const wil::ResultException *v37 )
  {
    if ( (wil::ResultFromCaughtException(v8) & 0x1FFF0000) == 0x70000 )
      v14 = (unsigned __int16)wil::ResultFromCaughtException(v11);
    else
      v14 = wil::ResultFromCaughtException(v11);
    v28 = v14;
    v15 = v37;
    v16 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8);
    if ( *v16 > 5u )
    {
      v35 = (const WCHAR *)*((_QWORD *)v15 + 6);
      v33 = *((_DWORD *)v15 + 22);
      v36 = (const wchar_t *)*((_QWORD *)v15 + 10);
      v30 = *((_DWORD *)v15 + 8);
      v31 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        (int)v16,
        (int)&byte_180057103,
        (__int64)v16,
        v17,
        (__int64)&v31,
        (__int64)&v30,
        &v36,
        (__int64)&v33,
        &v35);
    }
    v1 = v34;
    v2 = v28;
    v6 = v27;
  }
  catch ( ... )
  {
    v18 = wil::ResultFromCaughtException(v8);
    v20 = v18;
    v21 = v18 & 0x1FFF0000;
    v22 = (unsigned __int16)v18;
    if ( (_DWORD)v21 != 458752 )
      v22 = v18;
    v29 = v22;
    v23 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v21, v19) + 8);
    if ( *v23 > 5u )
    {
      v31 = v20;
      v30 = v22;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (int)v23,
        (int)byte_1800570D1,
        v24,
        v25,
        (__int64)&v30,
        (__int64)&v31);
    }
    v1 = v34;
    v2 = v29;
    v6 = v27;
  }
  v9 = *(_DWORD **)(v1 + 344);
  if ( v2 )
  {
    *v9 = v2;
  }
  else
  {
    *v9 = 0;
    *(_DWORD *)(*(_QWORD *)(v1 + 344) + 8LL) = v6;
    v10 = UNKNOWN_COST_DATA;
    if ( v6 )
      v10 = v32;
    *(_QWORD *)(*(_QWORD *)(v1 + 344) + 12LL) = v10;
  }
  wil::details::SetEvent(*(wil::details **)(*(_QWORD *)(v1 + 344) + 24LL), v7);
}

```

## disassembly

```asm
0x18001b1f0  push    rbx
0x18001b1f2  push    rsi
0x18001b1f3  push    rdi
0x18001b1f4  push    r14
0x18001b1f6  sub     rsp, 98h
0x18001b1fd  mov     rbx, rcx
0x18001b200  mov     [rsp+0B8h+var_48], rcx
0x18001b205  mov     [rsp+0B8h+var_68], 0
0x18001b20d  mov     rax, cs:?UNKNOWN_COST_DATA@@3U_DUSM_CONNECTION_COST_DATA@@B; _DUSM_CONNECTION_COST_DATA const UNKNOWN_COST_DATA
0x18001b214  mov     [rsp+0B8h+var_58], rax
0x18001b219  xor     esi, esi
0x18001b21b  mov     ecx, [rcx+8]
0x18001b21e  sub     ecx, 1
0x18001b221  jz      short loc_18001B268
0x18001b223  sub     ecx, 1
0x18001b226  jz      short loc_18001B24C
0x18001b228  cmp     ecx, 1
0x18001b22b  jnz     loc_18001B318
0x18001b231  lea     r14, [rbx+10h]
0x18001b235  lea     r8, [rsp+0B8h+var_58]
0x18001b23a  mov     edx, [rbx+150h]
0x18001b240  mov     rcx, r14
0x18001b243  call    ?QueryCost@DusmWwan@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z; DusmWwan::QueryCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *)
0x18001b248  mov     edi, eax
0x18001b24a  jmp     short loc_18001B281
0x18001b24c  lea     r14, [rbx+10h]
0x18001b250  lea     r8, [rsp+0B8h+var_58]
0x18001b255  mov     edx, [rbx+150h]
0x18001b25b  mov     rcx, r14
0x18001b25e  call    ?QueryCost@DusmWlan@@SA_NAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z; DusmWlan::QueryCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *)
0x18001b263  movzx   edi, al
0x18001b266  jmp     short loc_18001B281
0x18001b268  lea     r14, [rbx+10h]
0x18001b26c  lea     r8, [rsp+0B8h+var_58]
0x18001b271  mov     edx, [rbx+150h]
0x18001b277  mov     rcx, r14
0x18001b27a  call    ?QueryCost@DusmEthernet@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z; DusmEthernet::QueryCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *)
0x18001b27f  mov     edi, eax
0x18001b281  mov     [rsp+0B8h+var_68], edi
0x18001b285  xor     eax, eax
0x18001b287  test    edi, edi
0x18001b289  setz    al
0x18001b28c  mov     [rsp+0B8h+var_90], 0
0x18001b294  mov     [rsp+0B8h+var_98], eax
0x18001b298  lea     r9, [rsp+0B8h+var_58]
0x18001b29d  mov     r8d, [rbx+150h]
0x18001b2a4  mov     rdx, r14
0x18001b2a7  mov     rcx, cs:?s_pInstance@DusmCache@@0PEAV1@EA; DusmCache * DusmCache::s_pInstance
0x18001b2ae  call    ?SetCostCache@DusmCache@@AEAAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@HH@Z; DusmCache::SetCostCache(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int,int)
0x18001b2b3  nop
0x18001b2b4  jmp     short loc_18001B2C3
0x18001b2b6  mov     rbx, [rsp+0B8h+var_48]
0x18001b2bb  mov     esi, [rsp+0B8h+var_64]
0x18001b2bf  mov     edi, [rsp+0B8h+var_68]
0x18001b2c3  mov     rax, [rbx+158h]
0x18001b2ca  test    esi, esi
0x18001b2cc  jz      short loc_18001B2D2
0x18001b2ce  mov     [rax], esi
0x18001b2d0  jmp     short loc_18001B2FC
0x18001b2d2  mov     dword ptr [rax], 0
0x18001b2d8  mov     rax, [rbx+158h]
0x18001b2df  mov     [rax+8], edi
0x18001b2e2  mov     rcx, cs:?UNKNOWN_COST_DATA@@3U_DUSM_CONNECTION_COST_DATA@@B; _DUSM_CONNECTION_COST_DATA const UNKNOWN_COST_DATA
0x18001b2e9  test    edi, edi
0x18001b2eb  cmovnz  rcx, [rsp+0B8h+var_58]
0x18001b2f1  mov     rax, [rbx+158h]
0x18001b2f8  mov     [rax+0Ch], rcx
0x18001b2fc  mov     rcx, [rbx+158h]
0x18001b303  mov     rcx, [rcx+18h]; this
0x18001b307  add     rsp, 98h
0x18001b30e  pop     r14
0x18001b310  pop     rdi
0x18001b311  pop     rsi
0x18001b312  pop     rbx
0x18001b313  jmp     ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18001b318  mov     rcx, [rsp+0B8h]; this
0x18001b320  lea     rax, aDusmcacheQuery_5; "DusmCache::QueryCostAsync::SubmitWork::"...
0x18001b327  mov     qword ptr [rsp+0B8h+var_98], rax; unsigned int
0x18001b32c  lea     r9d, [rsi+57h]; char *
0x18001b330  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001b337  mov     edx, 1D1h; void *
0x18001b33c  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
