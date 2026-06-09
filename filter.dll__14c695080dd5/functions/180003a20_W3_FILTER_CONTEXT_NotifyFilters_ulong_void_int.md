# W3_FILTER_CONTEXT::NotifyFilters(ulong,void *,int *)

- ea: `0x180003a20`
- end: `0x180003f6b`
- name: `?NotifyFilters@W3_FILTER_CONTEXT@@QEAAJKPEAXPEAH@Z`
- size: `1355`
- prototype: `__int64 __fastcall(W3_FILTER_CONTEXT *__hidden this, unsigned int, void *, int *)`
- caller_count: `7`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180001320`
- `0x180001d20`
- `0x180002a40`
- `0x180002c60`
- `0x180002fc0`
- `0x180004bf0`
- `0x18000a3e0`

## callees

- `0x180003a20`
- `0x180003f80`
- `0x180004440`
- `0x180004b80`
- `0x18000af04`
- `0x18000b1e8`
- `0x18000b75c`
- `0x18000c12c`
- `0x18000c648`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cfd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003b37`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003b37`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003adb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003adb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003c81`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003e66`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003c81`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003e66`
- `iisutil!PuDbgPrint` at `0x180003cf2`
- `iisutil!PuDbgPrint` at `0x180003cf2`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003a6a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003a6a`

## string_xrefs

- `0x180003ceb`: `servercommon\inetsrv\iis\iisrearc\iis70\isapifilters\filter.cxx`
- `0x180003f14`: `SF_STATUS_REQ_READ_NEXT`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::NotifyFilters(W3_FILTER_CONTEXT *this, unsigned int a2, void *a3, int *a4)
{
  void *v4; // rsi
  __int64 v8; // r15
  __int64 i; // rdi
  __int64 v10; // r13
  __int64 v11; // rax
  void *ClientContext; // rax
  bool v13; // zf
  unsigned __int16 *Str; // rax
  __int64 v15; // rcx
  int (__fastcall ***v16)(_QWORD, GUID **); // rax
  int v17; // eax
  __int64 v18; // rcx
  int v19; // esi
  int (__fastcall ***v20)(_QWORD, GUID **); // rax
  void *v21; // r8
  unsigned int v22; // r13d
  signed int LastError; // edi
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  struct IHttpTraceContext *v28; // rax
  const struct _GUID *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rcx
  const wchar_t *v32; // rax
  struct IHttpTraceContext *v33; // rax
  const struct _GUID *v34; // rdx
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+48h] [rbp-B8h]
  void *v38; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v39; // [rsp+58h] [rbp-A8h]
  __int64 v40; // [rsp+60h] [rbp-A0h]
  GUID *v41; // [rsp+68h] [rbp-98h] BYREF
  __int128 v42; // [rsp+70h] [rbp-90h]
  GUID *v43; // [rsp+80h] [rbp-80h] BYREF
  __int128 v44; // [rsp+88h] [rbp-78h]
  _QWORD v45[6]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v46; // [rsp+D0h] [rbp-30h]
  int v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+E4h] [rbp-1Ch]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  const wchar_t **v50; // [rsp+F0h] [rbp-10h]
  const wchar_t *v51; // [rsp+100h] [rbp+0h] BYREF
  int v52; // [rsp+108h] [rbp+8h]
  __int64 v53; // [rsp+110h] [rbp+10h]
  int v54; // [rsp+118h] [rbp+18h]
  __int64 v55; // [rsp+120h] [rbp+20h]
  const wchar_t *v56; // [rsp+128h] [rbp+28h]
  int v57; // [rsp+130h] [rbp+30h]
  int *v58; // [rsp+138h] [rbp+38h]
  int v59; // [rsp+140h] [rbp+40h]
  const wchar_t *v60; // [rsp+148h] [rbp+48h]
  _BYTE v61[64]; // [rsp+150h] [rbp+50h] BYREF
  char v62[256]; // [rsp+190h] [rbp+90h] BYREF

  v4 = a3;
  STRA::STRA((STRA *)v61, v62, 0x100u);
  if ( !a4 )
  {
    STRA::~STRA((STRA *)v61);
    return 2147942487LL;
  }
  *a4 = 0;
  v40 = *((_QWORD *)this + 8);
  v8 = *((_QWORD *)this + 14);
  v37 = *((_DWORD *)this + 70);
  if ( *((_QWORD *)this + 3) )
    W3_FILTER_CONTEXT::RaiseEventPreCall(this, a2, v4, (struct STRA *)v61);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *(_DWORD *)(v8 + 16) )
      goto LABEL_27;
    v10 = *((_QWORD *)BUFFER::QueryPtr((BUFFER *)(v8 + 24)) + i);
    if ( !*((_DWORD *)this + 64) )
      break;
    if ( (unsigned int)W3_FILTER_CONTEXT::IsDisableNotificationNeeded(this, i, a2) )
      goto LABEL_10;
LABEL_24:
    ;
  }
  v11 = 60;
  if ( *((_DWORD *)this + 15) )
    v11 = 64;
  if ( (a2 & *(_DWORD *)(v11 + v10)) == 0 )
    goto LABEL_24;
LABEL_10:
  if ( *(_DWORD *)(v10 + 128) )
    ClientContext = W3_FILTER_CONTEXT::QueryClientContext(this, (void *)v10);
  else
    ClientContext = 0;
  *((_QWORD *)this + 8) = ClientContext;
  v13 = *((_QWORD *)this + 3) == 0;
  v38 = ClientContext;
  *((_DWORD *)this + 70) = i;
  if ( !v13 )
  {
    Str = STRU::QueryStr((STRU *)(v10 + 72));
    v15 = *((_QWORD *)this + 3);
    v39 = Str;
    v16 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 272LL))(v15);
    v41 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v42 = 0;
    if ( (**v16)(v16, &v41) >= 0 && DWORD2(v42) && ((_DWORD)v42 == 8 || (v42 & 8) != 0) )
    {
      v33 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      IISFilterEvents::FILTER_START::RaiseEvent(v33, v34, v39);
    }
  }
  v17 = (*(__int64 (__fastcall **)(char *, _QWORD, void *))(v10 + 32))((char *)this + 40, a2, v4);
  v18 = *((_QWORD *)this + 3);
  v19 = v17;
  if ( v18 )
  {
    v20 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 272LL))(v18);
    v43 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v44 = 0;
    if ( (**v20)(v20, &v43) >= 0 && DWORD2(v44) && ((_DWORD)v44 == 8 || (v44 & 8) != 0) )
    {
      v30 = *((_QWORD *)this + 3);
      v36 = v19;
      v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 272LL))(v30);
      v45[1] = 8;
      v45[3] = 2;
      v49 = 2;
      v45[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v45[5] = 1;
      v45[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
      v45[4] = L"FILTER_END";
      v51 = L"ContextId";
      v56 = L"NotificationStatus";
      v58 = &v36;
      v46 = 0;
      v47 = 0;
      v48 = 1;
      v52 = 72;
      v53 = 0;
      v54 = 16;
      v55 = 0;
      v57 = 19;
      v59 = 4;
      switch ( v36 )
      {
        case 134217728:
          v32 = L"SF_STATUS_REQ_FINISHED";
          break;
        case 134217729:
          v32 = L"SF_STATUS_REQ_FINISHED_KEEP_CONN";
          break;
        case 134217730:
          v32 = L"SF_STATUS_REQ_NEXT_NOTIFICATION";
          break;
        case 134217731:
          v32 = L"SF_STATUS_REQ_HANDLED_NOTIFICATION";
          break;
        case 134217732:
          v32 = L"SF_STATUS_REQ_ERROR";
          break;
        case 134217733:
          v32 = L"SF_STATUS_REQ_READ_NEXT";
          break;
        default:
          v32 = 0;
          break;
      }
      v60 = v32;
      v50 = &v51;
      (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v31 + 16LL))(v31, v45);
    }
  }
  v21 = (void *)*((_QWORD *)this + 8);
  if ( v38 != v21 || *(_DWORD *)(v10 + 128) )
  {
    W3_FILTER_CONTEXT::SetClientContext(this, (void *)v10, v21);
    *(_DWORD *)(v10 + 128) = 1;
  }
  switch ( v19 )
  {
    case 134217729:
    case 134217728:
      *a4 = 1;
LABEL_26:
      v4 = a3;
LABEL_27:
      v22 = 0;
      goto LABEL_28;
    case 134217730:
      goto LABEL_23;
    case 134217731:
      goto LABEL_26;
  }
  if ( v19 != 134217732 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapifilters\\filter.cxx",
        1388,
        "W3_FILTER_CONTEXT::NotifyFilters",
        "Unknown status code from filter %d\n",
        v19);
LABEL_23:
    v4 = a3;
    goto LABEL_24;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    if ( LastError <= 0 )
      v22 = LastError;
    else
      v22 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v22 = -2147024883;
  }
  v25 = *((_QWORD *)this + 3);
  if ( v25 )
  {
    v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 272LL))(v25);
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v26, v27, 2) )
    {
      v28 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      IISFilterEvents::FILTER_ERROR::RaiseEvent(v28, v29, LastError);
    }
  }
  v4 = a3;
LABEL_28:
  if ( *((_QWORD *)this + 3) )
    W3_FILTER_CONTEXT::RaiseEventPostCall(this, a2, v4, (struct STRA *)v61);
  *((_QWORD *)this + 8) = v40;
  *((_DWORD *)this + 70) = v37;
  STRA::~STRA((STRA *)v61);
  return v22;
}

```

## disassembly

```asm
0x180003a20  push    rbp
0x180003a22  push    rbx
0x180003a23  push    rsi
0x180003a24  push    r12
0x180003a26  push    r14
0x180003a28  lea     rbp, [rsp-1C0h]
0x180003a30  sub     rsp, 2C0h
0x180003a37  mov     rax, cs:__security_cookie
0x180003a3e  xor     rax, rsp
0x180003a41  mov     [rbp+1E0h+var_50], rax
0x180003a48  mov     rsi, r8
0x180003a4b  mov     [rsp+2E0h+var_2B0], r8
0x180003a50  mov     r12d, edx
0x180003a53  mov     rbx, rcx
0x180003a56  mov     r8d, 100h
0x180003a5c  lea     rdx, [rbp+1E0h+var_150]
0x180003a63  lea     rcx, [rbp+1E0h+var_190]
0x180003a67  mov     r14, r9
0x180003a6a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180003a70  test    r14, r14
0x180003a73  jz      loc_180003E62
0x180003a79  mov     [rsp+2E0h+var_28], rdi
0x180003a81  mov     [rsp+2E0h+var_30], r13
0x180003a89  xor     r13d, r13d
0x180003a8c  mov     [r14], r13d
0x180003a8f  mov     rax, [rbx+40h]
0x180003a93  mov     [rsp+2E0h+var_280], rax
0x180003a98  mov     eax, [rbx+118h]
0x180003a9e  mov     [rsp+2E0h+var_38], r15
0x180003aa6  mov     r15, [rbx+70h]
0x180003aaa  mov     [rsp+2E0h+var_298], eax
0x180003aae  mov     [rsp+2E0h+var_2A8], r13d
0x180003ab3  cmp     [rbx+18h], r13
0x180003ab7  jz      short loc_180003ACB
0x180003ab9  lea     r9, [rbp+1E0h+var_190]; struct STRA *
0x180003abd  mov     r8, rsi; void *
0x180003ac0  mov     edx, r12d; unsigned int
0x180003ac3  mov     rcx, rbx; this
0x180003ac6  call    ?RaiseEventPreCall@W3_FILTER_CONTEXT@@AEAAJKPEAXPEAVSTRA@@@Z; W3_FILTER_CONTEXT::RaiseEventPreCall(ulong,void *,STRA *)
0x180003acb  xor     edi, edi
0x180003acd  cmp     edi, [r15+10h]
0x180003ad1  jnb     loc_180003C3C
0x180003ad7  lea     rcx, [r15+18h]
0x180003adb  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003ae1  cmp     dword ptr [rbx+100h], 0
0x180003ae8  mov     r13, [rax+rdi*8]
0x180003aec  jnz     loc_180003E76
0x180003af2  cmp     dword ptr [rbx+3Ch], 0
0x180003af6  mov     eax, 3Ch ; '<'
0x180003afb  mov     ecx, 40h ; '@'
0x180003b00  cmovnz  eax, ecx
0x180003b03  test    [rax+r13], r12d
0x180003b07  jz      loc_180003C29
0x180003b0d  cmp     dword ptr [r13+80h], 0
0x180003b15  jnz     loc_180003E90
0x180003b1b  xor     eax, eax
0x180003b1d  mov     [rbx+40h], rax
0x180003b21  cmp     qword ptr [rbx+18h], 0
0x180003b26  mov     [rsp+2E0h+var_290], rax
0x180003b2b  mov     [rbx+118h], edi
0x180003b31  jz      short loc_180003B8C
0x180003b33  lea     rcx, [r13+48h]
0x180003b37  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003b3d  mov     rcx, [rbx+18h]
0x180003b41  mov     [rsp+2E0h+var_288], rax
0x180003b46  mov     rax, [rcx]
0x180003b49  mov     rax, [rax+110h]
0x180003b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b55  mov     rcx, rax
0x180003b58  lea     rdx, [rsp+2E0h+var_278]
0x180003b5d  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180003b64  xorps   xmm0, xmm0
0x180003b67  mov     [rsp+2E0h+var_278], rax
0x180003b6c  movdqu  [rsp+2E0h+var_270], xmm0
0x180003b72  mov     rax, [rcx]
0x180003b75  mov     rax, [rax]
0x180003b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b7d  test    eax, eax
0x180003b7f  js      short loc_180003B8C
0x180003b81  cmp     dword ptr [rsp+2E0h+var_270+8], 0
0x180003b86  jnz     loc_180003EA0
0x180003b8c  mov     rax, [r13+20h]
0x180003b90  lea     rcx, [rbx+28h]
0x180003b94  mov     r8, rsi
0x180003b97  mov     edx, r12d
0x180003b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b9f  mov     rcx, [rbx+18h]
0x180003ba3  mov     esi, eax
0x180003ba5  test    rcx, rcx
0x180003ba8  jz      short loc_180003BEC
0x180003baa  mov     rax, [rcx]
0x180003bad  mov     rax, [rax+110h]
0x180003bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb9  mov     rcx, rax
0x180003bbc  lea     rdx, [rbp+1E0h+var_260]
0x180003bc0  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180003bc7  xorps   xmm0, xmm0
0x180003bca  mov     [rbp+1E0h+var_260], rax
0x180003bce  movdqu  [rbp+1E0h+var_258], xmm0
0x180003bd3  mov     rax, [rcx]
0x180003bd6  mov     rax, [rax]
0x180003bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bde  test    eax, eax
0x180003be0  js      short loc_180003BEC
0x180003be2  cmp     dword ptr [rbp+1E0h+var_258+8], 0
0x180003be6  jnz     loc_180003ED7
0x180003bec  mov     r8, [rbx+40h]; void *
0x180003bf0  cmp     [rsp+2E0h+var_290], r8
0x180003bf5  jnz     loc_180003F50
0x180003bfb  cmp     dword ptr [r13+80h], 0
0x180003c03  jnz     loc_180003F50
0x180003c09  cmp     esi, 8000001h
0x180003c0f  jz      short loc_180003C30
0x180003c11  mov     ecx, esi
0x180003c13  sub     ecx, 8000000h
0x180003c19  jz      short loc_180003C30
0x180003c1b  sub     ecx, 2
0x180003c1e  jnz     loc_180003CB0
0x180003c24  mov     rsi, [rsp+2E0h+var_2B0]
0x180003c29  inc     edi
0x180003c2b  jmp     loc_180003ACD
0x180003c30  mov     dword ptr [r14], 1
0x180003c37  mov     rsi, [rsp+2E0h+var_2B0]
0x180003c3c  mov     r13d, [rsp+2E0h+var_2A8]
0x180003c41  cmp     qword ptr [rbx+18h], 0
0x180003c46  mov     r15, [rsp+2E0h+var_38]
0x180003c4e  mov     rdi, [rsp+2E0h+var_28]
0x180003c56  jz      short loc_180003C6A
0x180003c58  lea     r9, [rbp+1E0h+var_190]; struct STRA *
0x180003c5c  mov     r8, rsi; void *
0x180003c5f  mov     edx, r12d; unsigned int
0x180003c62  mov     rcx, rbx; this
0x180003c65  call    ?RaiseEventPostCall@W3_FILTER_CONTEXT@@AEAAJKPEAXPEAVSTRA@@@Z; W3_FILTER_CONTEXT::RaiseEventPostCall(ulong,void *,STRA *)
0x180003c6a  mov     rax, [rsp+2E0h+var_280]
0x180003c6f  lea     rcx, [rbp+1E0h+var_190]
0x180003c73  mov     [rbx+40h], rax
0x180003c77  mov     eax, [rsp+2E0h+var_298]
0x180003c7b  mov     [rbx+118h], eax
0x180003c81  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003c87  mov     eax, r13d
0x180003c8a  mov     r13, [rsp+2E0h+var_30]
0x180003c92  mov     rcx, [rbp+1E0h+var_50]
0x180003c99  xor     rcx, rsp; StackCookie
0x180003c9c  call    __security_check_cookie
0x180003ca1  add     rsp, 2C0h
0x180003ca8  pop     r14
0x180003caa  pop     r12
0x180003cac  pop     rsi
0x180003cad  pop     rbx
0x180003cae  pop     rbp
0x180003caf  retn
0x180003cb0  sub     ecx, 1
0x180003cb3  jz      short loc_180003C37
0x180003cb5  cmp     ecx, 1
0x180003cb8  jz      short loc_180003CFD
0x180003cba  test    cs:g_dwDebugFlags, 3
0x180003cc1  jz      loc_180003C24
0x180003cc7  mov     rcx, cs:g_pDebug
0x180003cce  lea     rax, aUnknownStatusC; "Unknown status code from filter %d\n"
0x180003cd5  mov     [rsp+2E0h+var_2B8], esi
0x180003cd9  lea     r9, aW3FilterContex_2; "W3_FILTER_CONTEXT::NotifyFilters"
0x180003ce0  mov     r8d, 56Ch
0x180003ce6  mov     [rsp+2E0h+var_2C0], rax
0x180003ceb  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003cf2  call    cs:__imp_PuDbgPrint
0x180003cf8  jmp     loc_180003C24
0x180003cfd  call    cs:__imp_GetLastError
0x180003d03  mov     edi, eax
0x180003d05  test    eax, eax
0x180003d07  jnz     short loc_180003D22
0x180003d09  mov     r13d, 8007000Dh
0x180003d0f  mov     rcx, [rbx+18h]
0x180003d13  test    rcx, rcx
0x180003d16  jnz     short loc_180003D33
0x180003d18  mov     rsi, [rsp+2E0h+var_2B0]
0x180003d1d  jmp     loc_180003C41
0x180003d22  test    edi, edi
0x180003d24  jle     short loc_180003D74
0x180003d26  movzx   r13d, di
0x180003d2a  or      r13d, 80070000h
0x180003d31  jmp     short loc_180003D0F
0x180003d33  mov     rax, [rcx]
0x180003d36  mov     rax, [rax+110h]
0x180003d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d42  mov     r8d, 2
0x180003d48  mov     rcx, rax
0x180003d4b  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180003d50  test    eax, eax
0x180003d52  jz      short loc_180003D18
0x180003d54  mov     rcx, [rbx+18h]
0x180003d58  mov     rax, [rcx]
0x180003d5b  mov     rax, [rax+110h]
0x180003d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d67  mov     rcx, rax; struct IHttpTraceContext *
0x180003d6a  mov     r8d, edi; unsigned int
0x180003d6d  call    ?RaiseEvent@FILTER_ERROR@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISFilterEvents::FILTER_ERROR::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x180003d72  jmp     short loc_180003D18
0x180003d74  mov     r13d, edi
0x180003d77  jmp     short loc_180003D0F
0x180003d79  mov     rcx, [rbx+18h]
0x180003d7d  mov     [rsp+2E0h+var_2A0], esi
0x180003d81  mov     rax, [rcx]
0x180003d84  mov     rax, [rax+110h]
0x180003d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d90  mov     rcx, rax
0x180003d93  mov     [rbp+1E0h+var_238], 8
0x180003d9b  xor     edx, edx
0x180003d9d  mov     [rbp+1E0h+var_228], 2
0x180003da5  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180003dac  mov     [rbp+1E0h+var_1F8], 2
0x180003db4  mov     [rbp+1E0h+var_240], rax
0x180003db8  xorps   xmm0, xmm0
0x180003dbb  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180003dc2  mov     [rbp+1E0h+var_218], 1
0x180003dca  mov     [rbp+1E0h+var_230], rax
0x180003dce  lea     rax, aFilterEnd; "FILTER_END"
0x180003dd5  mov     [rbp+1E0h+var_220], rax
0x180003dd9  lea     rax, aContextid; "ContextId"
0x180003de0  mov     [rbp+1E0h+var_1E0], rax
0x180003de4  lea     rax, aNotificationst; "NotificationStatus"
0x180003deb  mov     [rbp+1E0h+var_1B8], rax
0x180003def  lea     rax, [rsp+2E0h+var_2A0]
0x180003df4  mov     [rbp+1E0h+var_1A8], rax
0x180003df8  mov     eax, [rsp+2E0h+var_2A0]
0x180003dfc  movdqa  [rbp+1E0h+var_210], xmm0
0x180003e01  mov     [rbp+1E0h+var_200], edx
0x180003e04  mov     [rbp+1E0h+var_1FC], 1
0x180003e0b  mov     [rbp+1E0h+var_1D8], 48h ; 'H'
0x180003e12  mov     [rbp+1E0h+var_1D0], rdx
0x180003e16  mov     [rbp+1E0h+var_1C8], 10h
0x180003e1d  mov     [rbp+1E0h+var_1C0], rdx
0x180003e21  mov     [rbp+1E0h+var_1B0], 13h
0x180003e28  mov     [rbp+1E0h+var_1A0], 4
0x180003e2f  cmp     eax, 8000000h
0x180003e34  jnz     loc_180003EF1
0x180003e3a  lea     rax, aSfStatusReqFin_0; "SF_STATUS_REQ_FINISHED"
0x180003e41  mov     [rbp+1E0h+var_198], rax
0x180003e45  lea     rdx, [rbp+1E0h+var_240]
0x180003e49  lea     rax, [rbp+1E0h+var_1E0]
0x180003e4d  mov     [rbp+1E0h+var_1F0], rax
0x180003e51  mov     rax, [rcx]
0x180003e54  mov     rax, [rax+10h]
0x180003e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e5d  jmp     loc_180003BEC
0x180003e62  lea     rcx, [rbp+1E0h+var_190]
0x180003e66  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003e6c  mov     eax, 80070057h
0x180003e71  jmp     loc_180003C92
0x180003e76  mov     r8d, r12d; unsigned int
0x180003e79  mov     edx, edi; unsigned int
0x180003e7b  mov     rcx, rbx; this
0x180003e7e  call    ?IsDisableNotificationNeeded@W3_FILTER_CONTEXT@@QEAAHKK@Z; W3_FILTER_CONTEXT::IsDisableNotificationNeeded(ulong,ulong)
0x180003e83  test    eax, eax
0x180003e85  jz      loc_180003C29
0x180003e8b  jmp     loc_180003B0D
0x180003e90  mov     rdx, r13; void *
0x180003e93  mov     rcx, rbx; this
0x180003e96  call    ?QueryClientContext@W3_FILTER_CONTEXT@@QEAAPEAXPEAX@Z; W3_FILTER_CONTEXT::QueryClientContext(void *)
0x180003e9b  jmp     loc_180003B1D
0x180003ea0  mov     rax, qword ptr [rsp+2E0h+var_270]
0x180003ea5  cmp     eax, 8
0x180003ea8  jz      short loc_180003EB2
0x180003eaa  test    al, 8
0x180003eac  jz      loc_180003B8C
0x180003eb2  mov     rcx, [rbx+18h]
0x180003eb6  mov     rax, [rcx]
0x180003eb9  mov     rax, [rax+110h]
0x180003ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec5  mov     r8, [rsp+2E0h+var_288]; unsigned __int16 *
0x180003eca  mov     rcx, rax; struct IHttpTraceContext *
0x180003ecd  call    ?RaiseEvent@FILTER_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISFilterEvents::FILTER_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x180003ed2  jmp     loc_180003B8C
0x180003ed7  mov     rax, qword ptr [rbp+1E0h+var_258]
0x180003edb  cmp     eax, 8
0x180003ede  jz      loc_180003D79
0x180003ee4  test    al, 8
0x180003ee6  jz      loc_180003BEC
0x180003eec  jmp     loc_180003D79
0x180003ef1  sub     eax, 8000001h
0x180003ef6  jz      short loc_180003F44
0x180003ef8  sub     eax, 1
0x180003efb  jz      short loc_180003F38
0x180003efd  sub     eax, 1
0x180003f00  jz      short loc_180003F2C
0x180003f02  sub     eax, 1
0x180003f05  jz      short loc_180003F20
0x180003f07  cmp     eax, 1
0x180003f0a  jz      short loc_180003F14
0x180003f0c  mov     rax, rdx
0x180003f0f  jmp     loc_180003E41
0x180003f14  lea     rax, aSfStatusReqRea; "SF_STATUS_REQ_READ_NEXT"
0x180003f1b  jmp     loc_180003E41
0x180003f20  lea     rax, aSfStatusReqErr; "SF_STATUS_REQ_ERROR"
0x180003f27  jmp     loc_180003E41
0x180003f2c  lea     rax, aSfStatusReqHan; "SF_STATUS_REQ_HANDLED_NOTIFICATION"
0x180003f33  jmp     loc_180003E41
0x180003f38  lea     rax, aSfStatusReqNex; "SF_STATUS_REQ_NEXT_NOTIFICATION"
0x180003f3f  jmp     loc_180003E41
0x180003f44  lea     rax, aSfStatusReqFin; "SF_STATUS_REQ_FINISHED_KEEP_CONN"
0x180003f4b  jmp     loc_180003E41
  ... truncated ...
```
