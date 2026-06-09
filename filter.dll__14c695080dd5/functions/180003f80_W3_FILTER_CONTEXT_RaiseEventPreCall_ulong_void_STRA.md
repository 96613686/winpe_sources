# W3_FILTER_CONTEXT::RaiseEventPreCall(ulong,void *,STRA *)

- ea: `0x180003f80`
- end: `0x18000442c`
- name: `?RaiseEventPreCall@W3_FILTER_CONTEXT@@AEAAJKPEAXPEAVSTRA@@@Z`
- size: `1196`
- prototype: `__int64 __fastcall(W3_FILTER_CONTEXT *__hidden this, unsigned int, void *, struct STRA *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003a20`
- `0x18000af48`

## callees

- `0x180003f80`
- `0x180004b80`
- `0x1800077a0`
- `0x18000b3ac`
- `0x18000b54c`
- `0x18000b6ac`
- `0x18000b838`
- `0x18000bba4`
- `0x18000bd04`
- `0x18000bdb4`
- `0x18000c418`
- `0x18000d010`

## import_xrefs

- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000408a`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000408a`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::RaiseEventPreCall(
        W3_FILTER_CONTEXT *this,
        unsigned int a2,
        _DWORD *a3,
        struct STRA *a4)
{
  int v4; // ebx
  int (__fastcall ***v8)(_QWORD, GUID **); // rax
  const char *v9; // rbx
  struct IHttpTraceContext *v10; // rax
  const struct _GUID *v11; // rdx
  int v12; // eax
  int (__fastcall ***v13)(_QWORD, GUID **); // rax
  int (__fastcall ***v15)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v16; // rax
  const struct _GUID *v17; // rdx
  unsigned int v18; // edx
  unsigned int v19; // edx
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // ebx
  int v23; // edi
  const char *v24; // rsi
  const char *v25; // rbp
  const char *v26; // r14
  const char *v27; // r15
  const char *v28; // r12
  const char *v29; // r13
  struct IHttpTraceContext *v30; // rax
  const struct _GUID *v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rdx
  struct IHttpTraceContext *v34; // rax
  const struct _GUID *v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rdx
  unsigned int v38; // ebx
  struct IHttpTraceContext *v39; // rax
  const struct _GUID *v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdx
  struct IHttpTraceContext *v43; // rax
  const struct _GUID *v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rdx
  int v47; // ebx
  int v48; // edi
  int v49; // esi
  const char *v50; // rbp
  const char *v51; // r14
  struct IHttpTraceContext *v52; // rax
  const struct _GUID *v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rdx
  int v56; // ebx
  const char *v57; // rdi
  const char *v58; // rsi
  struct IHttpTraceContext *v59; // rax
  const struct _GUID *v60; // rdx
  struct IHttpTraceContext *v61; // rax
  const struct _GUID *v62; // rdx
  char *v63; // [rsp+38h] [rbp-60h]
  GUID *v64; // [rsp+50h] [rbp-48h] BYREF
  __int128 v65; // [rsp+58h] [rbp-40h]

  v4 = 0;
  if ( a2 == 0x4000000 )
  {
    v13 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
    v64 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v65 = 0;
    if ( (**v13)(v13, &v64) >= 0 && DWORD2(v65) && DWORD1(v65) >= 4 && ((_DWORD)v65 == 8 || (v65 & 8) != 0) )
    {
      v61 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      v12 = IISFilterEvents::FILTER_AUTH_COMPLETE_START::RaiseEvent(v61, v62);
      goto LABEL_43;
    }
  }
  else if ( a2 == 0x4000 )
  {
    v15 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
    v64 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v65 = 0;
    if ( (**v15)(v15, &v64) >= 0 && DWORD2(v65) && DWORD1(v65) >= 4 && ((_DWORD)v65 == 8 || (v65 & 8) != 0) )
    {
      v16 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      v12 = IISFilterEvents::FILTER_PREPROC_HEADERS_START::RaiseEvent(v16, v17);
      goto LABEL_43;
    }
  }
  else if ( a2 <= 0x400 )
  {
    if ( a2 == 1024 )
    {
      v41 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v41, v42, 4) )
      {
        v43 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        v12 = IISFilterEvents::FILTER_SEND_RAW_DATA_START::RaiseEvent(v43, v44);
        goto LABEL_43;
      }
    }
    else
    {
      v18 = a2 - 64;
      if ( v18 )
      {
        v19 = v18 - 64;
        if ( v19 )
        {
          if ( v19 == 384 )
          {
            v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
            if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v20, v21, 4) )
            {
              v22 = a3[13];
              v23 = a3[12];
              v24 = (const char *)*((_QWORD *)a3 + 5);
              v25 = (const char *)*((_QWORD *)a3 + 4);
              v26 = (const char *)*((_QWORD *)a3 + 3);
              v27 = (const char *)*((_QWORD *)a3 + 2);
              v28 = (const char *)*((_QWORD *)a3 + 1);
              v29 = *(const char **)a3;
              v30 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
              v12 = IISFilterEvents::FILTER_LOG_START::RaiseEvent(v30, v31, v29, v28, v27, v26, v25, v24, v23, v22);
              goto LABEL_43;
            }
          }
        }
        else
        {
          v32 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
          if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v32, v33, 4) )
          {
            v34 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
            v12 = IISFilterEvents::FILTER_END_OF_REQUEST_START::RaiseEvent(v34, v35);
            goto LABEL_43;
          }
        }
      }
      else
      {
        v36 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v36, v37, 4) )
        {
          v38 = a3[6];
          v39 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
          v12 = IISFilterEvents::FILTER_SEND_RESPONSE_START::RaiseEvent(v39, v40, v38);
          goto LABEL_43;
        }
      }
    }
  }
  else
  {
    switch ( a2 )
    {
      case 0x800u:
        v54 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v54, v55, 4) )
        {
          v56 = a3[4];
          v57 = (const char *)*((_QWORD *)a3 + 1);
          v58 = *(const char **)a3;
          v59 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
          v12 = IISFilterEvents::FILTER_ACCESS_DENIED_START::RaiseEvent(v59, v60, v58, v57, v56);
          goto LABEL_43;
        }
        break;
      case 0x1000u:
        v45 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v45, v46, 4) )
        {
          v47 = a3[7];
          v48 = a3[6];
          v49 = a3[5];
          v50 = (const char *)*((_QWORD *)a3 + 1);
          v51 = *(const char **)a3;
          v52 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
          v12 = IISFilterEvents::FILTER_URL_MAP_START::RaiseEvent(v52, v53, v51, v50, v49, v48, v47, v63);
          goto LABEL_43;
        }
        break;
      case 0x2000u:
        v8 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
        v64 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v65 = 0;
        if ( (**v8)(v8, &v64) >= 0 && DWORD2(v65) && DWORD1(v65) >= 4 && ((_DWORD)v65 == 8 || (v65 & 8) != 0) )
        {
          v9 = *(const char **)a3;
          v10 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
          v4 = IISFilterEvents::FILTER_AUTHENTICATION_START::RaiseEvent(v10, v11, v9);
          if ( v4 >= 0 )
          {
            v12 = STRA::Copy(a4, *((const char **)a3 + 2));
LABEL_43:
            v4 = v12;
          }
        }
        break;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003f80  mov     [rsp+arg_10], rbx
0x180003f85  mov     [rsp+arg_18], rbp
0x180003f8a  mov     [rsp+arg_0], rcx
0x180003f8f  push    rsi
0x180003f90  push    rdi
0x180003f91  push    r13
0x180003f93  push    r14
0x180003f95  push    r15
0x180003f97  sub     rsp, 70h
0x180003f9b  xor     ebx, ebx
0x180003f9d  mov     rdi, r9
0x180003fa0  mov     r13, r8
0x180003fa3  mov     r15, rcx
0x180003fa6  cmp     edx, 4000000h
0x180003fac  jz      loc_180004095
0x180003fb2  cmp     edx, 4000h
0x180003fb8  jz      loc_1800040FC
0x180003fbe  cmp     edx, 400h
0x180003fc4  jbe     loc_180004179
0x180003fca  cmp     edx, 800h
0x180003fd0  jz      loc_180004391
0x180003fd6  cmp     edx, 1000h
0x180003fdc  jz      loc_180004322
0x180003fe2  cmp     edx, 2000h
0x180003fe8  jnz     loc_1800040E1
0x180003fee  mov     rcx, [rcx+18h]
0x180003ff2  mov     rax, [rcx]
0x180003ff5  mov     rax, [rax+110h]
0x180003ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004001  mov     r8, rax
0x180004004  lea     rdx, [rsp+98h+var_48]
0x180004009  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004010  xorps   xmm0, xmm0
0x180004013  mov     [rsp+98h+var_48], rax
0x180004018  movdqu  [rsp+98h+var_40], xmm0
0x18000401e  mov     rcx, [r8]
0x180004021  mov     rax, [rcx]
0x180004024  mov     rcx, r8
0x180004027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000402c  test    eax, eax
0x18000402e  js      loc_1800040E1
0x180004034  cmp     dword ptr [rsp+98h+var_40+8], ebx
0x180004038  jz      loc_1800040E1
0x18000403e  cmp     dword ptr [rsp+98h+var_40+4], 4
0x180004043  jb      loc_1800040E1
0x180004049  mov     rax, qword ptr [rsp+98h+var_40]
0x18000404e  cmp     eax, 8
0x180004051  jz      short loc_18000405B
0x180004053  test    al, 8
0x180004055  jz      loc_1800040E1
0x18000405b  mov     rcx, [r15+18h]
0x18000405f  mov     rbx, [r13+0]
0x180004063  mov     rax, [rcx]
0x180004066  mov     rax, [rax+110h]
0x18000406d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004072  mov     r8, rbx; char *
0x180004075  mov     rcx, rax; struct IHttpTraceContext *
0x180004078  call    ?RaiseEvent@FILTER_AUTHENTICATION_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD@Z; IISFilterEvents::FILTER_AUTHENTICATION_START::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *)
0x18000407d  mov     ebx, eax
0x18000407f  test    eax, eax
0x180004081  js      short loc_1800040E1
0x180004083  mov     rdx, [r13+10h]
0x180004087  mov     rcx, rdi
0x18000408a  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004090  jmp     loc_180004425
0x180004095  mov     rcx, [rcx+18h]
0x180004099  mov     rax, [rcx]
0x18000409c  mov     rax, [rax+110h]
0x1800040a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040a8  mov     r8, rax
0x1800040ab  lea     rdx, [rsp+98h+var_48]
0x1800040b0  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800040b7  xorps   xmm0, xmm0
0x1800040ba  mov     [rsp+98h+var_48], rax
0x1800040bf  movdqu  [rsp+98h+var_40], xmm0
0x1800040c5  mov     rcx, [r8]
0x1800040c8  mov     rax, [rcx]
0x1800040cb  mov     rcx, r8
0x1800040ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040d3  test    eax, eax
0x1800040d5  js      short loc_1800040E1
0x1800040d7  cmp     dword ptr [rsp+98h+var_40+8], ebx
0x1800040db  jnz     loc_1800043ED
0x1800040e1  lea     r11, [rsp+98h+var_28]
0x1800040e6  mov     eax, ebx
0x1800040e8  mov     rbx, [r11+40h]
0x1800040ec  mov     rbp, [r11+48h]
0x1800040f0  mov     rsp, r11
0x1800040f3  pop     r15
0x1800040f5  pop     r14
0x1800040f7  pop     r13
0x1800040f9  pop     rdi
0x1800040fa  pop     rsi
0x1800040fb  retn
0x1800040fc  mov     rcx, [rcx+18h]
0x180004100  mov     rax, [rcx]
0x180004103  mov     rax, [rax+110h]
0x18000410a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000410f  mov     r8, rax
0x180004112  lea     rdx, [rsp+98h+var_48]
0x180004117  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000411e  xorps   xmm0, xmm0
0x180004121  mov     [rsp+98h+var_48], rax
0x180004126  movdqu  [rsp+98h+var_40], xmm0
0x18000412c  mov     rcx, [r8]
0x18000412f  mov     rax, [rcx]
0x180004132  mov     rcx, r8
0x180004135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413a  test    eax, eax
0x18000413c  js      short loc_1800040E1
0x18000413e  cmp     dword ptr [rsp+98h+var_40+8], ebx
0x180004142  jz      short loc_1800040E1
0x180004144  cmp     dword ptr [rsp+98h+var_40+4], 4
0x180004149  jb      short loc_1800040E1
0x18000414b  mov     rax, qword ptr [rsp+98h+var_40]
0x180004150  cmp     eax, 8
0x180004153  jz      short loc_180004159
0x180004155  test    al, 8
0x180004157  jz      short loc_1800040E1
0x180004159  mov     rcx, [r15+18h]
0x18000415d  mov     rax, [rcx]
0x180004160  mov     rax, [rax+110h]
0x180004167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416c  mov     rcx, rax; struct IHttpTraceContext *
0x18000416f  call    ?RaiseEvent@FILTER_PREPROC_HEADERS_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_PREPROC_HEADERS_START::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x180004174  jmp     loc_180004425
0x180004179  jz      loc_1800042D9
0x18000417f  sub     edx, 40h ; '@'
0x180004182  jz      loc_180004289
0x180004188  sub     edx, 40h ; '@'
0x18000418b  jz      loc_180004240
0x180004191  cmp     edx, 180h
0x180004197  jnz     loc_1800040E1
0x18000419d  mov     rcx, [rcx+18h]
0x1800041a1  mov     rax, [rcx]
0x1800041a4  mov     rax, [rax+110h]
0x1800041ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b0  mov     r8d, 4
0x1800041b6  mov     rcx, rax
0x1800041b9  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800041be  test    eax, eax
0x1800041c0  jz      loc_1800040E1
0x1800041c6  mov     ebx, [r13+34h]
0x1800041ca  mov     edi, [r13+30h]
0x1800041ce  mov     rsi, [r13+28h]
0x1800041d2  mov     rbp, [r13+20h]
0x1800041d6  mov     r14, [r13+18h]
0x1800041da  mov     r15, [r13+10h]
0x1800041de  mov     rcx, [rsp+98h+arg_0]
0x1800041e6  mov     [rsp+98h+arg_8], r12
0x1800041ee  mov     r12, [r13+8]
0x1800041f2  mov     r13, [r13+0]
0x1800041f6  mov     rcx, [rcx+18h]
0x1800041fa  mov     rax, [rcx]
0x1800041fd  mov     rax, [rax+110h]
0x180004204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004209  mov     dword ptr [rsp+98h+var_50], ebx; char
0x18000420d  mov     r9, r12; char *
0x180004210  mov     dword ptr [rsp+98h+var_58], edi; char
0x180004214  mov     r8, r13; char *
0x180004217  mov     [rsp+98h+var_60], rsi; char *
0x18000421c  mov     rcx, rax; struct IHttpTraceContext *
0x18000421f  mov     [rsp+98h+var_68], rbp; char *
0x180004224  mov     [rsp+98h+var_70], r14; char *
0x180004229  mov     [rsp+98h+var_78], r15; char *
0x18000422e  call    ?RaiseEvent@FILTER_LOG_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD22222KK@Z; IISFilterEvents::FILTER_LOG_START::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,ulong)
0x180004233  mov     r12, [rsp+98h+arg_8]
0x18000423b  jmp     loc_180004425
0x180004240  mov     rcx, [rcx+18h]
0x180004244  mov     rax, [rcx]
0x180004247  mov     rax, [rax+110h]
0x18000424e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004253  mov     r8d, 4
0x180004259  mov     rcx, rax
0x18000425c  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180004261  test    eax, eax
0x180004263  jz      loc_1800040E1
0x180004269  mov     rcx, [r15+18h]
0x18000426d  mov     rax, [rcx]
0x180004270  mov     rax, [rax+110h]
0x180004277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000427c  mov     rcx, rax; struct IHttpTraceContext *
0x18000427f  call    ?RaiseEvent@FILTER_END_OF_REQUEST_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_END_OF_REQUEST_START::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x180004284  jmp     loc_180004425
0x180004289  mov     rcx, [rcx+18h]
0x18000428d  mov     rax, [rcx]
0x180004290  mov     rax, [rax+110h]
0x180004297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000429c  mov     r8d, 4
0x1800042a2  mov     rcx, rax
0x1800042a5  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800042aa  test    eax, eax
0x1800042ac  jz      loc_1800040E1
0x1800042b2  mov     rcx, [r15+18h]
0x1800042b6  mov     ebx, [r13+18h]
0x1800042ba  mov     rax, [rcx]
0x1800042bd  mov     rax, [rax+110h]
0x1800042c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c9  mov     r8d, ebx; unsigned int
0x1800042cc  mov     rcx, rax; struct IHttpTraceContext *
0x1800042cf  call    ?RaiseEvent@FILTER_SEND_RESPONSE_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@K@Z; IISFilterEvents::FILTER_SEND_RESPONSE_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong)
0x1800042d4  jmp     loc_180004425
0x1800042d9  mov     rcx, [rcx+18h]
0x1800042dd  mov     rax, [rcx]
0x1800042e0  mov     rax, [rax+110h]
0x1800042e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ec  mov     r8d, 4
0x1800042f2  mov     rcx, rax
0x1800042f5  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800042fa  test    eax, eax
0x1800042fc  jz      loc_1800040E1
0x180004302  mov     rcx, [r15+18h]
0x180004306  mov     rax, [rcx]
0x180004309  mov     rax, [rax+110h]
0x180004310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004315  mov     rcx, rax; struct IHttpTraceContext *
0x180004318  call    ?RaiseEvent@FILTER_SEND_RAW_DATA_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_SEND_RAW_DATA_START::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000431d  jmp     loc_180004425
0x180004322  mov     rcx, [rcx+18h]
0x180004326  mov     rax, [rcx]
0x180004329  mov     rax, [rax+110h]
0x180004330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004335  mov     r8d, 4
0x18000433b  mov     rcx, rax
0x18000433e  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180004343  test    eax, eax
0x180004345  jz      loc_1800040E1
0x18000434b  mov     rcx, [r15+18h]
0x18000434f  mov     ebx, [r13+1Ch]
0x180004353  mov     edi, [r13+18h]
0x180004357  mov     esi, [r13+14h]
0x18000435b  mov     rax, [rcx]
0x18000435e  mov     rbp, [r13+8]
0x180004362  mov     r14, [r13+0]
0x180004366  mov     rax, [rax+110h]
0x18000436d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004372  mov     dword ptr [rsp+98h+var_68], ebx; char
0x180004376  mov     r9, rbp; char *
0x180004379  mov     dword ptr [rsp+98h+var_70], edi; char
0x18000437d  mov     r8, r14; char *
0x180004380  mov     rcx, rax; struct IHttpTraceContext *
0x180004383  mov     dword ptr [rsp+98h+var_78], esi; char
0x180004387  call    ?RaiseEvent@FILTER_URL_MAP_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2KKK2@Z; IISFilterEvents::FILTER_URL_MAP_START::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,ulong,ulong,ulong,char const *)
0x18000438c  jmp     loc_180004425
0x180004391  mov     rcx, [rcx+18h]
0x180004395  mov     rax, [rcx]
0x180004398  mov     rax, [rax+110h]
0x18000439f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a4  mov     r8d, 4
0x1800043aa  mov     rcx, rax
0x1800043ad  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800043b2  test    eax, eax
0x1800043b4  jz      loc_1800040E1
0x1800043ba  mov     rcx, [r15+18h]
0x1800043be  mov     ebx, [r13+10h]
0x1800043c2  mov     rdi, [r13+8]
0x1800043c6  mov     rsi, [r13+0]
0x1800043ca  mov     rax, [rcx]
0x1800043cd  mov     rax, [rax+110h]
0x1800043d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043d9  mov     r9, rdi; char *
0x1800043dc  mov     dword ptr [rsp+98h+var_78], ebx; char
0x1800043e0  mov     r8, rsi; char *
0x1800043e3  mov     rcx, rax; struct IHttpTraceContext *
0x1800043e6  call    ?RaiseEvent@FILTER_ACCESS_DENIED_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2K@Z; IISFilterEvents::FILTER_ACCESS_DENIED_START::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,ulong)
0x1800043eb  jmp     short loc_180004425
0x1800043ed  cmp     dword ptr [rsp+98h+var_40+4], 4
0x1800043f2  jb      loc_1800040E1
0x1800043f8  mov     rax, qword ptr [rsp+98h+var_40]
0x1800043fd  cmp     eax, 8
0x180004400  jz      short loc_18000440A
0x180004402  test    al, 8
0x180004404  jz      loc_1800040E1
0x18000440a  mov     rcx, [r15+18h]
0x18000440e  mov     rax, [rcx]
0x180004411  mov     rax, [rax+110h]
0x180004418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000441d  mov     rcx, rax; struct IHttpTraceContext *
0x180004420  call    ?RaiseEvent@FILTER_AUTH_COMPLETE_START@IISFilterEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFilterEvents::FILTER_AUTH_COMPLETE_START::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x180004425  mov     ebx, eax
0x180004427  jmp     loc_1800040E1
```
