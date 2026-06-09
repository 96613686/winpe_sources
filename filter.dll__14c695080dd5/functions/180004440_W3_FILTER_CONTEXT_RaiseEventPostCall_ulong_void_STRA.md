# W3_FILTER_CONTEXT::RaiseEventPostCall(ulong,void *,STRA *)

- ea: `0x180004440`
- end: `0x180004891`
- name: `?RaiseEventPostCall@W3_FILTER_CONTEXT@@AEAAJKPEAXPEAVSTRA@@@Z`
- size: `1105`
- prototype: `__int64 __fastcall(W3_FILTER_CONTEXT *__hidden this, unsigned int, void *, struct STRA *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180003a20`
- `0x18000af48`

## callees

- `0x180004440`
- `0x1800048a0`
- `0x180004b80`
- `0x180006380`
- `0x180007bf0`
- `0x180008720`
- `0x18000b49c`
- `0x18000b5fc`
- `0x18000baf4`
- `0x18000bc54`
- `0x18000c21c`
- `0x18000d010`

## import_xrefs

- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x18000468b`
- `iisutil!?Equals@STRA@@QEBA_NPEBD@Z` at `0x18000468b`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::RaiseEventPostCall(
        W3_FILTER_CONTEXT *this,
        unsigned int a2,
        void *a3,
        struct STRA *a4)
{
  unsigned int v4; // ebx
  int (__fastcall ***v8)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v9; // rax
  const struct _GUID *v10; // rdx
  int (__fastcall ***v12)(_QWORD, GUID **); // rax
  unsigned int v14; // edx
  unsigned int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // ebx
  int v19; // edi
  const char *v20; // rsi
  const char *v21; // rbp
  const char *v22; // r14
  const char *v23; // r15
  const char *v24; // r12
  const char *v25; // r13
  struct IHttpTraceContext *v26; // rax
  const struct _GUID *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  bool v30; // al
  const char *v31; // rbx
  int v32; // edi
  struct IHttpTraceContext *v33; // rax
  const struct _GUID *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rdx
  struct IHttpTraceContext *v37; // rax
  const struct _GUID *v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rdx
  struct IHttpTraceContext *v41; // rax
  const struct _GUID *v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rdx
  struct IHttpTraceContext *v45; // rax
  const struct _GUID *v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rdx
  int v49; // ebx
  int v50; // edi
  int v51; // esi
  const char *v52; // rbp
  const char *v53; // r14
  struct IHttpTraceContext *v54; // rax
  const struct _GUID *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rdx
  struct IHttpTraceContext *v58; // rax
  const struct _GUID *v59; // rdx
  struct IHttpTraceContext *v60; // rax
  const struct _GUID *v61; // rdx
  GUID *v62; // [rsp+50h] [rbp-48h] BYREF
  __int128 v63; // [rsp+58h] [rbp-40h]

  v4 = 0;
  if ( a2 == 0x4000000 )
  {
    v12 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
    v62 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v63 = 0;
    if ( (**v12)(v12, &v62) >= 0 && DWORD2(v63) && DWORD1(v63) >= 4 && ((_DWORD)v63 == 8 || (v63 & 8) != 0) )
    {
      v60 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      return (unsigned int)IISFilterEvents::FILTER_AUTH_COMPLETE_END::RaiseEvent(v60, v61);
    }
  }
  else if ( a2 == 0x4000 )
  {
    v8 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
    v62 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v63 = 0;
    if ( (**v8)(v8, &v62) >= 0 && DWORD2(v63) && DWORD1(v63) >= 4 && ((_DWORD)v63 == 8 || (v63 & 8) != 0) )
    {
      v9 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      return (unsigned int)IISFilterEvents::FILTER_PREPROC_HEADERS_END::RaiseEvent(v9, v10);
    }
  }
  else if ( a2 > 0x400 )
  {
    switch ( a2 )
    {
      case 0x800u:
        v56 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        if ( !(unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v56, v57, 4) )
          return v4;
        v58 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        return (unsigned int)IISFilterEvents::FILTER_ACCESS_DENIED_END::RaiseEvent(v58, v59);
      case 0x1000u:
        v47 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        if ( !(unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v47, v48, 4) )
          return v4;
        v49 = *((_DWORD *)a3 + 7);
        v50 = *((_DWORD *)a3 + 6);
        v51 = *((_DWORD *)a3 + 5);
        v52 = (const char *)*((_QWORD *)a3 + 1);
        v53 = *(const char **)a3;
        v54 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        return (unsigned int)IISFilterEvents::FILTER_URL_MAP_END::RaiseEvent(v54, v55, v53, v52, v51, v50, v49);
      case 0x2000u:
        v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v28, v29, 4) )
        {
          v30 = STRA::Equals(a4, *((const char **)a3 + 2));
          v31 = *(const char **)a3;
          v32 = !v30;
          v33 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
          return (unsigned int)IISFilterEvents::FILTER_AUTHENTICATION_END::RaiseEvent(v33, v34, v31, v32);
        }
        break;
    }
  }
  else
  {
    if ( a2 == 1024 )
    {
      v43 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      if ( !(unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v43, v44, 4) )
        return v4;
      v45 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      return (unsigned int)IISFilterEvents::FILTER_SEND_RAW_DATA_END::RaiseEvent(v45, v46);
    }
    v14 = a2 - 64;
    if ( !v14 )
    {
      v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      if ( !(unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v39, v40, 4) )
        return v4;
      v41 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      return (unsigned int)IISFilterEvents::FILTER_SEND_RESPONSE_END::RaiseEvent(v41, v42);
    }
    v15 = v14 - 64;
    if ( !v15 )
    {
      v35 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      if ( !(unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v35, v36, 4) )
        return v4;
      v37 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      return (unsigned int)IISFilterEvents::FILTER_END_OF_REQUEST_END::RaiseEvent(v37, v38);
    }
    if ( v15 == 384 )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v16, v17, 4) )
      {
        v18 = *((_DWORD *)a3 + 13);
        v19 = *((_DWORD *)a3 + 12);
        v20 = (const char *)*((_QWORD *)a3 + 5);
        v21 = (const char *)*((_QWORD *)a3 + 4);
        v22 = (const char *)*((_QWORD *)a3 + 3);
        v23 = (const char *)*((_QWORD *)a3 + 2);
        v24 = (const char *)*((_QWORD *)a3 + 1);
        v25 = *(const char **)a3;
        v26 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        return (unsigned int)IISFilterEvents::FILTER_LOG_END::RaiseEvent(
                               v26,
                               v27,
                               v25,
                               v24,
                               v23,
                               v22,
                               v21,
                               v20,
                               v19,
                               v18);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180004440  mov     [rsp+arg_10], rbx
0x180004445  mov     [rsp+arg_18], rbp
0x18000444a  mov     [rsp+arg_0], rcx
0x18000444f  push    rsi
0x180004450  push    rdi
0x180004451  push    r13
0x180004453  push    r14
0x180004455  push    r15
0x180004457  sub     rsp, 70h
0x18000445b  xor     ebx, ebx
0x18000445d  mov     rdi, r9
0x180004460  mov     r13, r8
0x180004463  mov     r15, rcx
0x180004466  cmp     edx, 4000000h
0x18000446c  jz      loc_180004503
0x180004472  cmp     edx, 4000h
0x180004478  jnz     loc_18000456A
0x18000447e  mov     rcx, [rcx+18h]
0x180004482  mov     rax, [rcx]
0x180004485  mov     rax, [rax+110h]
0x18000448c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004491  mov     r8, rax
0x180004494  lea     rdx, [rsp+98h+var_48]
0x180004499  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800044a0  xorps   xmm0, xmm0
0x1800044a3  mov     [rsp+98h+var_48], rax
0x1800044a8  movdqu  [rsp+98h+var_40], xmm0
0x1800044ae  mov     rcx, [r8]
0x1800044b1  mov     rax, [rcx]
0x1800044b4  mov     rcx, r8
0x1800044b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044bc  test    eax, eax
0x1800044be  js      loc_18000454F
0x1800044c4  cmp     dword ptr [rsp+98h+var_40+8], ebx
0x1800044c8  jz      loc_18000454F
0x1800044ce  cmp     dword ptr [rsp+98h+var_40+4], 4
0x1800044d3  jb      short loc_18000454F
0x1800044d5  mov     rax, qword ptr [rsp+98h+var_40]
0x1800044da  cmp     eax, 8
0x1800044dd  jz      short loc_1800044E3
0x1800044df  test    al, 8
0x1800044e1  jz      short loc_18000454F
0x1800044e3  mov     rcx, [r15+18h]
0x1800044e7  mov     rax, [rcx]
0x1800044ea  mov     rax, [rax+110h]
0x1800044f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044f6  mov     rcx, rax; struct IHttpTraceContext *
0x1800044f9  call    ?RaiseEvent@FILTER_PREPROC_HEADERS_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_PREPROC_HEADERS_END::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x1800044fe  jmp     loc_180004630
0x180004503  mov     rcx, [rcx+18h]
0x180004507  mov     rax, [rcx]
0x18000450a  mov     rax, [rax+110h]
0x180004511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004516  mov     r8, rax
0x180004519  lea     rdx, [rsp+98h+var_48]
0x18000451e  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004525  xorps   xmm0, xmm0
0x180004528  mov     [rsp+98h+var_48], rax
0x18000452d  movdqu  [rsp+98h+var_40], xmm0
0x180004533  mov     rcx, [r8]
0x180004536  mov     rax, [rcx]
0x180004539  mov     rcx, r8
0x18000453c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004541  test    eax, eax
0x180004543  js      short loc_18000454F
0x180004545  cmp     dword ptr [rsp+98h+var_40+8], ebx
0x180004549  jnz     loc_180004854
0x18000454f  lea     r11, [rsp+98h+var_28]
0x180004554  mov     eax, ebx
0x180004556  mov     rbx, [r11+40h]
0x18000455a  mov     rbp, [r11+48h]
0x18000455e  mov     rsp, r11
0x180004561  pop     r15
0x180004563  pop     r14
0x180004565  pop     r13
0x180004567  pop     rdi
0x180004568  pop     rsi
0x180004569  retn
0x18000456a  cmp     edx, 400h
0x180004570  ja      loc_180004637
0x180004576  jz      loc_180004753
0x18000457c  sub     edx, 40h ; '@'
0x18000457f  jz      loc_18000470A
0x180004585  sub     edx, 40h ; '@'
0x180004588  jz      loc_1800046C1
0x18000458e  cmp     edx, 180h
0x180004594  jnz     short loc_18000454F
0x180004596  mov     rcx, [rcx+18h]
0x18000459a  mov     rax, [rcx]
0x18000459d  mov     rax, [rax+110h]
0x1800045a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a9  mov     r8d, 4
0x1800045af  mov     rcx, rax
0x1800045b2  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800045b7  test    eax, eax
0x1800045b9  jz      short loc_18000454F
0x1800045bb  mov     ebx, [r13+34h]
0x1800045bf  mov     edi, [r13+30h]
0x1800045c3  mov     rsi, [r13+28h]
0x1800045c7  mov     rbp, [r13+20h]
0x1800045cb  mov     r14, [r13+18h]
0x1800045cf  mov     r15, [r13+10h]
0x1800045d3  mov     rcx, [rsp+98h+arg_0]
0x1800045db  mov     [rsp+98h+arg_8], r12
0x1800045e3  mov     r12, [r13+8]
0x1800045e7  mov     r13, [r13+0]
0x1800045eb  mov     rcx, [rcx+18h]
0x1800045ef  mov     rax, [rcx]
0x1800045f2  mov     rax, [rax+110h]
0x1800045f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045fe  mov     dword ptr [rsp+98h+var_50], ebx; char
0x180004602  mov     r9, r12; char *
0x180004605  mov     dword ptr [rsp+98h+var_58], edi; char
0x180004609  mov     r8, r13; char *
0x18000460c  mov     [rsp+98h+var_60], rsi; char *
0x180004611  mov     rcx, rax; struct IHttpTraceContext *
0x180004614  mov     [rsp+98h+var_68], rbp; char *
0x180004619  mov     [rsp+98h+var_70], r14; char *
0x18000461e  mov     [rsp+98h+var_78], r15; char *
0x180004623  call    ?RaiseEvent@FILTER_LOG_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD22222KK@Z; IISFilterEvents::FILTER_LOG_END::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,ulong)
0x180004628  mov     r12, [rsp+98h+arg_8]
0x180004630  mov     ebx, eax
0x180004632  jmp     loc_18000454F
0x180004637  cmp     edx, 800h
0x18000463d  jz      loc_18000480B
0x180004643  cmp     edx, 1000h
0x180004649  jz      loc_18000479C
0x18000464f  cmp     edx, 2000h
0x180004655  jnz     loc_18000454F
0x18000465b  mov     rcx, [rcx+18h]
0x18000465f  mov     rax, [rcx]
0x180004662  mov     rax, [rax+110h]
0x180004669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000466e  mov     r8d, 4
0x180004674  mov     rcx, rax
0x180004677  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000467c  test    eax, eax
0x18000467e  jz      loc_18000454F
0x180004684  mov     rdx, [r13+10h]
0x180004688  mov     rcx, rdi
0x18000468b  call    cs:__imp_?Equals@STRA@@QEBA_NPEBD@Z; STRA::Equals(char const *)
0x180004691  mov     rcx, [r15+18h]
0x180004695  mov     rbx, [r13+0]
0x180004699  movzx   edi, al
0x18000469c  xor     edi, 1
0x18000469f  mov     rax, [rcx]
0x1800046a2  mov     rax, [rax+110h]
0x1800046a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ae  mov     r9d, edi; int
0x1800046b1  mov     r8, rbx; char *
0x1800046b4  mov     rcx, rax; struct IHttpTraceContext *
0x1800046b7  call    ?RaiseEvent@FILTER_AUTHENTICATION_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBDH@Z; IISFilterEvents::FILTER_AUTHENTICATION_END::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,int)
0x1800046bc  jmp     loc_180004630
0x1800046c1  mov     rcx, [rcx+18h]
0x1800046c5  mov     rax, [rcx]
0x1800046c8  mov     rax, [rax+110h]
0x1800046cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d4  mov     r8d, 4
0x1800046da  mov     rcx, rax
0x1800046dd  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800046e2  test    eax, eax
0x1800046e4  jz      loc_18000454F
0x1800046ea  mov     rcx, [r15+18h]
0x1800046ee  mov     rax, [rcx]
0x1800046f1  mov     rax, [rax+110h]
0x1800046f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fd  mov     rcx, rax; struct IHttpTraceContext *
0x180004700  call    ?RaiseEvent@FILTER_END_OF_REQUEST_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_END_OF_REQUEST_END::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x180004705  jmp     loc_180004630
0x18000470a  mov     rcx, [rcx+18h]
0x18000470e  mov     rax, [rcx]
0x180004711  mov     rax, [rax+110h]
0x180004718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000471d  mov     r8d, 4
0x180004723  mov     rcx, rax
0x180004726  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000472b  test    eax, eax
0x18000472d  jz      loc_18000454F
0x180004733  mov     rcx, [r15+18h]
0x180004737  mov     rax, [rcx]
0x18000473a  mov     rax, [rax+110h]
0x180004741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004746  mov     rcx, rax; struct IHttpTraceContext *
0x180004749  call    ?RaiseEvent@FILTER_SEND_RESPONSE_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_SEND_RESPONSE_END::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000474e  jmp     loc_180004630
0x180004753  mov     rcx, [rcx+18h]
0x180004757  mov     rax, [rcx]
0x18000475a  mov     rax, [rax+110h]
0x180004761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004766  mov     r8d, 4
0x18000476c  mov     rcx, rax
0x18000476f  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180004774  test    eax, eax
0x180004776  jz      loc_18000454F
0x18000477c  mov     rcx, [r15+18h]
0x180004780  mov     rax, [rcx]
0x180004783  mov     rax, [rax+110h]
0x18000478a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000478f  mov     rcx, rax; struct IHttpTraceContext *
0x180004792  call    ?RaiseEvent@FILTER_SEND_RAW_DATA_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_SEND_RAW_DATA_END::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x180004797  jmp     loc_180004630
0x18000479c  mov     rcx, [rcx+18h]
0x1800047a0  mov     rax, [rcx]
0x1800047a3  mov     rax, [rax+110h]
0x1800047aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047af  mov     r8d, 4
0x1800047b5  mov     rcx, rax
0x1800047b8  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800047bd  test    eax, eax
0x1800047bf  jz      loc_18000454F
0x1800047c5  mov     rcx, [r15+18h]
0x1800047c9  mov     ebx, [r13+1Ch]
0x1800047cd  mov     edi, [r13+18h]
0x1800047d1  mov     esi, [r13+14h]
0x1800047d5  mov     rax, [rcx]
0x1800047d8  mov     rbp, [r13+8]
0x1800047dc  mov     r14, [r13+0]
0x1800047e0  mov     rax, [rax+110h]
0x1800047e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ec  mov     dword ptr [rsp+98h+var_68], ebx; char
0x1800047f0  mov     r9, rbp; char *
0x1800047f3  mov     dword ptr [rsp+98h+var_70], edi; char
0x1800047f7  mov     r8, r14; char *
0x1800047fa  mov     rcx, rax; struct IHttpTraceContext *
0x1800047fd  mov     dword ptr [rsp+98h+var_78], esi; char
0x180004801  call    ?RaiseEvent@FILTER_URL_MAP_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2KKK2@Z; IISFilterEvents::FILTER_URL_MAP_END::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,ulong,ulong,ulong,char const *)
0x180004806  jmp     loc_180004630
0x18000480b  mov     rcx, [rcx+18h]
0x18000480f  mov     rax, [rcx]
0x180004812  mov     rax, [rax+110h]
0x180004819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481e  mov     r8d, 4
0x180004824  mov     rcx, rax
0x180004827  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000482c  test    eax, eax
0x18000482e  jz      loc_18000454F
0x180004834  mov     rcx, [r15+18h]
0x180004838  mov     rax, [rcx]
0x18000483b  mov     rax, [rax+110h]
0x180004842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004847  mov     rcx, rax; struct IHttpTraceContext *
0x18000484a  call    ?RaiseEvent@FILTER_ACCESS_DENIED_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_ACCESS_DENIED_END::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000484f  jmp     loc_180004630
0x180004854  cmp     dword ptr [rsp+98h+var_40+4], 4
0x180004859  jb      loc_18000454F
0x18000485f  mov     rax, qword ptr [rsp+98h+var_40]
0x180004864  cmp     eax, 8
0x180004867  jz      short loc_180004871
0x180004869  test    al, 8
0x18000486b  jz      loc_18000454F
0x180004871  mov     rcx, [r15+18h]
0x180004875  mov     rax, [rcx]
0x180004878  mov     rax, [rax+110h]
0x18000487f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004884  mov     rcx, rax; struct IHttpTraceContext *
0x180004887  call    ?RaiseEvent@FILTER_AUTH_COMPLETE_END@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_AUTH_COMPLETE_END::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000488c  jmp     loc_180004630
```
