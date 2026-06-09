# CHidPairing::_StartPairing(void)

- ea: `0x1800b2254`
- end: `0x1800b249b`
- name: `?_StartPairing@CHidPairing@@AEAAJXZ`
- size: `583`
- prototype: `__int64 __fastcall(CHidPairing *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1c8c`

## callees

- `0x180003470`
- `0x18000b358`
- `0x1800b16d8`
- `0x1800b2254`
- `0x1800b24a4`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b22ff`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b23f0`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b22ff`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800b23f0`
- `deviceassociation!DafStartEnumCeremonies` at `0x1800b22c1`
- `deviceassociation!DafStartEnumCeremonies` at `0x1800b22c1`
- `deviceassociation!DafStartFinalize` at `0x1800b2428`
- `deviceassociation!DafStartFinalize` at `0x1800b2428`
- `deviceassociation!DafStartReadCeremonyData` at `0x1800b23b9`
- `deviceassociation!DafStartReadCeremonyData` at `0x1800b23b9`
- `deviceassociation!DafSelectCeremony` at `0x1800b2327`
- `deviceassociation!DafSelectCeremony` at `0x1800b2327`
- `deviceassociation!DafCreateAssociationContext` at `0x1800b229b`
- `deviceassociation!DafCreateAssociationContext` at `0x1800b229b`

## string_xrefs

- `0x1800b2465`: `CHidPairing::_StartPairing - Failed to create Association Context: hr=0x%08X`

## pseudocode

```c
__int64 __fastcall CHidPairing::_StartPairing(CHidPairing *this)
{
  _QWORD *v2; // r14
  int AssociationContext; // eax
  HRESULT CeremonyData; // ebx
  int started; // eax
  int v6; // eax
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  _OWORD *v9; // rax
  const wchar_t *v10; // r8
  size_t v11; // r9
  HRESULT v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  LPDWORD lpdwindex; // [rsp+20h] [rbp-68h]
  DWORD dwindex; // [rsp+30h] [rbp-58h] BYREF
  DWORD v19; // [rsp+34h] [rbp-54h] BYREF
  _BYTE v20[24]; // [rsp+38h] [rbp-50h] BYREF

  UnattendLogW(0, L"CHidPairing::_StartPairing - Starting pairing with %s", *((_QWORD *)this + 14));
  v2 = (_QWORD *)((char *)this + 288);
  AssociationContext = DafCreateAssociationContext(*((_QWORD *)this + 14), 0, 0, 0, (char *)this + 288);
  CeremonyData = AssociationContext;
  if ( AssociationContext < 0 )
  {
    UnattendLogW(
      1,
      L"CHidPairing::_StartPairing - Failed to create Association Context: hr=0x%08X",
      (unsigned int)AssociationContext);
    goto LABEL_23;
  }
  started = DafStartEnumCeremonies(*v2, 0, 0, CHidPairing::s_DafEnumCeremoniesCallback, this);
  CeremonyData = started;
  if ( started < 0 )
  {
    UnattendLogW(
      1,
      L"CHidPairing::_StartPairing - Failed to start enumerate ceremonies: hr=0x%08X",
      (unsigned int)started);
  }
  else
  {
    dwindex = 0;
    UnattendLogW(0, L"CHidPairing::_StartPairing - Waiting for ceremony enumeration to end");
    CeremonyData = CoWaitForMultipleHandles(1u, 0xFFFFFFFF, 1u, (LPHANDLE)this + 39, &dwindex);
    if ( CeremonyData >= 0 )
    {
      CeremonyData = *((_DWORD *)this + 98);
      if ( CeremonyData >= 0 )
      {
        v6 = DafSelectCeremony(*v2, *((_QWORD *)this + 51));
        CeremonyData = v6;
        if ( v6 < 0 )
        {
          UnattendLogW(1, L"CHidPairing::_StartPairing - Failed to select ceremony: hr=0x%08X", (unsigned int)v6);
          goto LABEL_23;
        }
        v9 = (_OWORD *)*((_QWORD *)this + 51);
        v10 = (const wchar_t *)*((_QWORD *)this + 13);
        v11 = -1;
        *(_OWORD *)v20 = 0;
        *(_OWORD *)&v20[8] = *v9;
        do
          ++v11;
        while ( v10[v11] );
        _AllocStringWorker<CTCoAllocPolicy>(v8, v7, v10, v11, (__int64)lpdwindex, (void **)v20);
        v12 = CHidPairing::_PostMessageWithData(this, 0, 24, v20);
        v13 = (_QWORD *)*((_QWORD *)this + 51);
        CeremonyData = v12;
        v14 = *v13 - DAF_Ceremony_PinDisplay;
        if ( *v13 == DAF_Ceremony_PinDisplay )
          v14 = v13[1] + 0x4BCEAD8541486357LL;
        if ( !v14 )
        {
          v15 = *v2;
          v19 = 0;
          CeremonyData = DafStartReadCeremonyData(v15, CHidPairing::s_DafReadCeremonyDataCallback, this);
          if ( CeremonyData < 0 )
            goto LABEL_23;
          UnattendLogW(0, L"CHidPairing::_StartPairing - Waiting for PIN generation");
          CeremonyData = CoWaitForMultipleHandles(1u, 0xFFFFFFFF, 1u, (LPHANDLE)this + 44, &v19);
          if ( CeremonyData >= 0 )
          {
            CeremonyData = *((_DWORD *)this + 99);
            if ( CeremonyData >= 0 )
              goto LABEL_16;
          }
          UnattendLogW(1, L"CHidPairing::_StartPairing - Failed to generate PIN: hr=0x%08X", (unsigned int)CeremonyData);
        }
        if ( CeremonyData >= 0 )
        {
LABEL_16:
          CeremonyData = DafStartFinalize(*v2, &CHidPairing::s_DafFinalizeCompleteCallback, this);
          goto LABEL_20;
        }
LABEL_23:
        CHidPairing::_StopPairing(this);
        return (unsigned int)CeremonyData;
      }
    }
    UnattendLogW(
      1,
      L"CHidPairing::_StartPairing - Failed to enumerate ceremonies: hr=0x%08X",
      (unsigned int)CeremonyData);
  }
LABEL_20:
  if ( CeremonyData < 0 )
    goto LABEL_23;
  return (unsigned int)CeremonyData;
}

```

## disassembly

```asm
0x1800b2254  push    rbx
0x1800b2256  push    rbp
0x1800b2257  push    rsi
0x1800b2258  push    rdi
0x1800b2259  push    r14
0x1800b225b  sub     rsp, 60h
0x1800b225f  mov     rax, cs:__security_cookie
0x1800b2266  xor     rax, rsp
0x1800b2269  mov     [rsp+88h+var_38], rax
0x1800b226e  mov     r8, [rcx+70h]
0x1800b2272  lea     rdx, aChidpairingSta_6; "CHidPairing::_StartPairing - Starting p"...
0x1800b2279  mov     rdi, rcx
0x1800b227c  xor     ecx, ecx
0x1800b227e  call    UnattendLogW
0x1800b2283  mov     rcx, [rdi+70h]
0x1800b2287  lea     r14, [rdi+120h]
0x1800b228e  xor     r9d, r9d
0x1800b2291  mov     [rsp+88h+lpdwindex], r14
0x1800b2296  xor     r8d, r8d
0x1800b2299  xor     edx, edx
0x1800b229b  call    cs:__imp_DafCreateAssociationContext
0x1800b22a1  xor     ebp, ebp
0x1800b22a3  mov     ebx, eax
0x1800b22a5  test    eax, eax
0x1800b22a7  js      loc_1800B2465
0x1800b22ad  mov     rcx, [r14]
0x1800b22b0  lea     r9, ?s_DafEnumCeremoniesCallback@CHidPairing@@SAXKPEBU_CEREMONY@@PEAXJ@Z; CHidPairing::s_DafEnumCeremoniesCallback(ulong,_CEREMONY const *,void *,long)
0x1800b22b7  xor     r8d, r8d
0x1800b22ba  mov     [rsp+88h+lpdwindex], rdi
0x1800b22bf  xor     edx, edx
0x1800b22c1  call    cs:__imp_DafStartEnumCeremonies
0x1800b22c7  mov     ebx, eax
0x1800b22c9  test    eax, eax
0x1800b22cb  js      loc_1800B244B
0x1800b22d1  lea     rdx, aChidpairingSta_19; "CHidPairing::_StartPairing - Waiting fo"...
0x1800b22d8  mov     [rsp+88h+dwindex], ebp
0x1800b22dc  xor     ecx, ecx
0x1800b22de  call    UnattendLogW
0x1800b22e3  lea     esi, [rbp+1]
0x1800b22e6  or      edx, 0FFFFFFFFh; dwTimeout
0x1800b22e9  lea     rax, [rsp+88h+dwindex]
0x1800b22ee  mov     r8d, esi; cHandles
0x1800b22f1  mov     ecx, esi; dwFlags
0x1800b22f3  mov     [rsp+88h+lpdwindex], rax; lpdwindex
0x1800b22f8  lea     r9, [rdi+138h]; pHandles
0x1800b22ff  call    cs:__imp_CoWaitForMultipleHandles
0x1800b2305  mov     ebx, eax
0x1800b2307  test    eax, eax
0x1800b2309  js      loc_1800B243D
0x1800b230f  mov     ebx, [rdi+188h]
0x1800b2315  test    ebx, ebx
0x1800b2317  js      loc_1800B243D
0x1800b231d  mov     rdx, [rdi+198h]
0x1800b2324  mov     rcx, [r14]
0x1800b2327  call    cs:__imp_DafSelectCeremony
0x1800b232d  mov     ebx, eax
0x1800b232f  test    eax, eax
0x1800b2331  js      loc_1800B2432
0x1800b2337  mov     rax, [rdi+198h]
0x1800b233e  xorps   xmm0, xmm0
0x1800b2341  mov     r8, [rdi+68h]
0x1800b2345  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800b2349  movups  xmmword ptr [rsp+88h+var_50], xmm0
0x1800b234e  movups  xmm0, xmmword ptr [rax]
0x1800b2351  movdqu  xmmword ptr [rsp+88h+var_50+8], xmm0
0x1800b2357  inc     r9
0x1800b235a  cmp     [r8+r9*2], bp
0x1800b235f  jnz     short loc_1800B2357
0x1800b2361  lea     rax, [rsp+88h+var_50]
0x1800b2366  mov     [rsp+88h+var_60], rax
0x1800b236b  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800b2370  xor     edx, edx
0x1800b2372  lea     r9, [rsp+88h+var_50]
0x1800b2377  mov     rcx, rdi
0x1800b237a  lea     r8d, [rdx+18h]
0x1800b237e  call    ?_PostMessageWithData@CHidPairing@@AEAAJW4HID_NOTIFICATION_TYPE@@_KPEBX@Z; CHidPairing::_PostMessageWithData(HID_NOTIFICATION_TYPE,unsigned __int64,void const *)
0x1800b2383  mov     rcx, [rdi+198h]
0x1800b238a  mov     ebx, eax
0x1800b238c  mov     rax, [rcx]
0x1800b238f  sub     rax, cs:DAF_Ceremony_PinDisplay
0x1800b2396  jnz     short loc_1800B23A3
0x1800b2398  mov     rax, [rcx+8]
0x1800b239c  sub     rax, cs:qword_1800DE7A8
0x1800b23a3  test    rax, rax
0x1800b23a6  jnz     short loc_1800B2417
0x1800b23a8  mov     rcx, [r14]
0x1800b23ab  lea     rdx, ?s_DafReadCeremonyDataCallback@CHidPairing@@SAXKQEAEPEAXJ@Z; CHidPairing::s_DafReadCeremonyDataCallback(ulong,uchar * const,void *,long)
0x1800b23b2  mov     r8, rdi
0x1800b23b5  mov     [rsp+88h+var_54], ebp
0x1800b23b9  call    cs:__imp_DafStartReadCeremonyData
0x1800b23bf  mov     ebx, eax
0x1800b23c1  test    eax, eax
0x1800b23c3  js      loc_1800B2479
0x1800b23c9  lea     rdx, aChidpairingSta_18; "CHidPairing::_StartPairing - Waiting fo"...
0x1800b23d0  xor     ecx, ecx
0x1800b23d2  call    UnattendLogW
0x1800b23d7  lea     rax, [rsp+88h+var_54]
0x1800b23dc  mov     r8d, esi; cHandles
0x1800b23df  lea     r9, [rdi+160h]; pHandles
0x1800b23e6  mov     [rsp+88h+lpdwindex], rax; lpdwindex
0x1800b23eb  or      edx, 0FFFFFFFFh; dwTimeout
0x1800b23ee  mov     ecx, esi; dwFlags
0x1800b23f0  call    cs:__imp_CoWaitForMultipleHandles
0x1800b23f6  mov     ebx, eax
0x1800b23f8  test    eax, eax
0x1800b23fa  js      short loc_1800B2406
0x1800b23fc  mov     ebx, [rdi+18Ch]
0x1800b2402  test    ebx, ebx
0x1800b2404  jns     short loc_1800B241B
0x1800b2406  mov     r8d, ebx
0x1800b2409  lea     rdx, aChidpairingSta; "CHidPairing::_StartPairing - Failed to "...
0x1800b2410  mov     ecx, esi
0x1800b2412  call    UnattendLogW
0x1800b2417  test    ebx, ebx
0x1800b2419  js      short loc_1800B2479
0x1800b241b  mov     rcx, [r14]
0x1800b241e  lea     rdx, ?s_DafFinalizeCompleteCallback@CHidPairing@@SAXW4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; CHidPairing::s_DafFinalizeCompleteCallback(_DAF_ASSOCIATION_STATUS,void *,long)
0x1800b2425  mov     r8, rdi
0x1800b2428  call    cs:__imp_DafStartFinalize
0x1800b242e  mov     ebx, eax
0x1800b2430  jmp     short loc_1800B245F
0x1800b2432  lea     rdx, aChidpairingSta_9; "CHidPairing::_StartPairing - Failed to "...
0x1800b2439  mov     ecx, esi
0x1800b243b  jmp     short loc_1800B2471
0x1800b243d  mov     r8d, ebx
0x1800b2440  lea     rdx, aChidpairingSta_10; "CHidPairing::_StartPairing - Failed to "...
0x1800b2447  mov     ecx, esi
0x1800b2449  jmp     short loc_1800B245A
0x1800b244b  mov     r8d, eax
0x1800b244e  lea     rdx, aChidpairingSta_14; "CHidPairing::_StartPairing - Failed to "...
0x1800b2455  mov     ecx, 1
0x1800b245a  call    UnattendLogW
0x1800b245f  test    ebx, ebx
0x1800b2461  jns     short loc_1800B2481
0x1800b2463  jmp     short loc_1800B2479
0x1800b2465  lea     rdx, aChidpairingSta_7; "CHidPairing::_StartPairing - Failed to "...
0x1800b246c  mov     ecx, 1
0x1800b2471  mov     r8d, eax
0x1800b2474  call    UnattendLogW
0x1800b2479  mov     rcx, rdi; this
0x1800b247c  call    ?_StopPairing@CHidPairing@@AEAAXXZ; CHidPairing::_StopPairing(void)
0x1800b2481  mov     eax, ebx
0x1800b2483  mov     rcx, [rsp+88h+var_38]
0x1800b2488  xor     rcx, rsp; StackCookie
0x1800b248b  call    __security_check_cookie
0x1800b2490  add     rsp, 60h
0x1800b2494  pop     r14
0x1800b2496  pop     rdi
0x1800b2497  pop     rsi
0x1800b2498  pop     rbp
0x1800b2499  pop     rbx
0x1800b249a  retn
```
