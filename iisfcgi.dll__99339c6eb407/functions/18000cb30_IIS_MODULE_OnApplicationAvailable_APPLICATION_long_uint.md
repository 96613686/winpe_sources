# IIS_MODULE::OnApplicationAvailable(APPLICATION *,long,uint)

- ea: `0x18000cb30`
- end: `0x18000cf55`
- name: `?OnApplicationAvailable@IIS_MODULE@@UEAAXPEAVAPPLICATION@@JI@Z`
- size: `1061`
- prototype: `void __fastcall(IIS_MODULE *this, struct APPLICATION *, int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180006a0c`
- `0x180006ce8`
- `0x18000b3ac`
- `0x18000b564`
- `0x18000bb5c`
- `0x18000cb30`
- `0x18000dc5c`
- `0x18000df0c`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cbce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cbce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ceec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ceec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cf28`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cf28`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000ccaa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000ccaa`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cbac`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cbac`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000cc86`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000cc86`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000ccbd`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000ccbd`

## pseudocode

```c
void __fastcall IIS_MODULE::OnApplicationAvailable(IIS_MODULE *this, struct APPLICATION *a2, int a3, unsigned int a4)
{
  IIS_MODULE *v4; // r14
  int v6; // r12d
  __int64 v7; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  struct IHttpTraceContext *v12; // rsi
  int v13; // r13d
  int Params; // ebx
  int (__fastcall **v15)(struct IHttpTraceContext *, GUID **); // rax
  struct _GUID *v16; // rdx
  __int64 v17; // r15
  int v18; // ebx
  bool v19; // zf
  int v20; // r15d
  int (__fastcall **v21)(struct IHttpTraceContext *, GUID **); // rax
  int (__fastcall **v22)(struct IHttpTraceContext *, GUID **); // rax
  int (__fastcall *v23)(struct IHttpTraceContext *, GUID **); // rax
  int (__fastcall **v24)(struct IHttpTraceContext *, GUID **); // rax
  const struct _GUID *v25; // rdx
  int v26; // eax
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  int v28; // [rsp+34h] [rbp-CCh]
  char v29[4]; // [rsp+38h] [rbp-C8h]
  char v30[4]; // [rsp+3Ch] [rbp-C4h]
  GUID *v31; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+48h] [rbp-B8h]
  int v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  unsigned int v35; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  _QWORD v37[6]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v38; // [rsp+B0h] [rbp-50h]
  int v39; // [rsp+C0h] [rbp-40h]
  int v40; // [rsp+C4h] [rbp-3Ch]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  GUID **v42; // [rsp+D0h] [rbp-30h]
  _BYTE v43[32]; // [rsp+E0h] [rbp-20h] BYREF
  const unsigned __int16 *v44; // [rsp+100h] [rbp+0h]

  v4 = (IIS_MODULE *)((char *)this - 8);
  v35 = a4;
  v6 = 0;
  v7 = *((_QWORD *)this + 20);
  v27 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  v11 = *((_QWORD *)this + 20);
  v36 = v10;
  v12 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 272LL))(v11);
  STRU::STRU((STRU *)v43);
  *(_DWORD *)v30 = 0;
  v13 = 0;
  HIDWORD(v32) = 0;
  v28 = 0;
  *(_DWORD *)v29 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( *((_DWORD *)this + 20) )
  {
    Params = -2147023901;
  }
  else if ( a2 )
  {
    (*(void (__fastcall **)(IIS_MODULE *))(*(_QWORD *)v4 + 64LL))(v4);
    *((_QWORD *)this + 4) = a2;
    v31 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v15 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v12;
    v32 = 0;
    if ( (*v15)(v12, &v31) >= 0 && DWORD2(v32) && ((_DWORD)v32 == 4096 || (v32 & 0x1000) != 0) )
    {
      v17 = *((_QWORD *)this + 4);
      EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 112));
      v18 = STRU::Copy((STRU *)v43, (const struct STRU *)(v17 + 312));
      if ( v18 >= 0 )
      {
        if ( *(_DWORD *)(v17 + 416)
          && ((v18 = STRU::Append((STRU *)v43, L" "), v18 < 0)
           || (v18 = STRU::Append((STRU *)v43, (const struct STRU *)(v17 + 368)), v18 < 0)) )
        {
          v13 = v28;
        }
        else
        {
          v19 = *(_DWORD *)(v17 + 256) == 1;
          *(_DWORD *)v29 = *(_DWORD *)(v17 + 256);
          v13 = v19;
          *(_DWORD *)v30 = *(_DWORD *)(v17 + 252);
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 112));
      if ( v18 >= 0 )
        IISFastCGIEvents::FASTCGI_ASSIGN_PROCESS::RaiseEvent(v12, v16, v44, v13, v30[0], v29[0]);
    }
    Params = IIS_MODULE::CreateParams(v4, (struct IHttpContext *)v16);
    if ( Params >= 0 )
    {
      v20 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v36 + 144LL))(v36) )
      {
        v20 = 1;
        *((_DWORD *)this + 35) = 0;
        v6 = 1;
        v27 = 1;
      }
      v31 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v21 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v12;
      v32 = 0;
      if ( (*v21)(v12, &v31) >= 0 && DWORD2(v32) && ((_DWORD)v32 == 4096 || (v32 & 0x1000) != 0) )
      {
        v37[1] = 4096;
        v37[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v37[3] = 18;
        v37[2] = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
        v41 = 1;
        v37[4] = L"FASTCGI_START";
        v37[5] = 1;
        v31 = (GUID *)L"ContextId";
        v42 = &v31;
        v22 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v12;
        v38 = 0;
        v39 = 0;
        v40 = 1;
        v23 = v22[2];
        LODWORD(v32) = 72;
        *((_QWORD *)&v32 + 1) = 0;
        v33 = 16;
        v34 = 0;
        v23(v12, (GUID **)v37);
      }
      Params = APPLICATION::SendFcgiParams(
                 *((APPLICATION **)this + 4),
                 *((struct _FCGI_PARAM **)this + 14),
                 *((_DWORD *)this + 30),
                 v20,
                 *((_DWORD *)this + 56),
                 v4);
      operator delete(*((void **)this + 14));
      *((_QWORD *)this + 14) = 0;
      if ( Params >= 0 )
      {
        if ( v20 )
        {
          v31 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
          v24 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v12;
          v32 = 0;
          if ( (*v24)(v12, &v31) >= 0 && DWORD2(v32) && DWORD1(v32) >= 5 && ((_DWORD)v32 == 4096 || (v32 & 0x1000) != 0) )
            IISFastCGIEvents::FASTCGI_WAITING_FOR_RESPONSE::RaiseEvent(v12, v25);
        }
        else
        {
          v26 = IIS_MODULE::BeginReceiveEntity(v4, &v27);
          v6 = v27;
          Params = v26;
        }
      }
    }
  }
  else
  {
    Params = 0;
    IIS_MODULE::EndResponse(v4, 0, a3, v35, 0, 0);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( Params < 0 || v6 && (Params = APPLICATION::StartIISSends(*((APPLICATION **)this + 4)), Params < 0) )
    IIS_MODULE::EndResponse(v4, 0, Params, 0, 0, 0);
  STRU::~STRU((STRU *)v43);
}

```

## disassembly

```asm
0x18000cb30  mov     [rsp-8+arg_8], rbx
0x18000cb35  push    rbp
0x18000cb36  push    rsi
0x18000cb37  push    rdi
0x18000cb38  push    r12
0x18000cb3a  push    r13
0x18000cb3c  push    r14
0x18000cb3e  push    r15
0x18000cb40  lea     rbp, [rsp-20h]
0x18000cb45  sub     rsp, 120h
0x18000cb4c  mov     rax, cs:__security_cookie
0x18000cb53  xor     rax, rsp
0x18000cb56  mov     [rbp+50h+var_38], rax
0x18000cb5a  lea     r14, [rcx-8]
0x18000cb5e  mov     [rsp+150h+var_E8], r9d
0x18000cb63  mov     rdi, rcx
0x18000cb66  xor     r12d, r12d
0x18000cb69  mov     rcx, [r14+0A8h]
0x18000cb70  mov     r15d, r8d
0x18000cb73  mov     rbx, rdx
0x18000cb76  mov     [rsp+150h+var_120], r12d
0x18000cb7b  mov     rax, [rcx]
0x18000cb7e  mov     rax, [rax+18h]
0x18000cb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb87  mov     rdx, [rdi+0A0h]
0x18000cb8e  mov     [rsp+150h+var_E0], rax
0x18000cb93  mov     rcx, [rdx]
0x18000cb96  mov     rax, [rcx+110h]
0x18000cb9d  mov     rcx, rdx
0x18000cba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cba5  lea     rcx, [rbp+50h+var_70]
0x18000cba9  mov     rsi, rax
0x18000cbac  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cbb2  xor     eax, eax
0x18000cbb4  mov     dword ptr [rsp+150h+var_114], r12d
0x18000cbb9  xor     r13d, r13d
0x18000cbbc  mov     dword ptr [rsp+150h+var_108+0Ch], eax
0x18000cbc0  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000cbc4  mov     [rsp+150h+var_11C], r13d
0x18000cbc9  mov     dword ptr [rsp+150h+var_118], r12d
0x18000cbce  call    cs:__imp_EnterCriticalSection
0x18000cbd4  cmp     [rdi+50h], r12d
0x18000cbd8  jz      short loc_18000CBE4
0x18000cbda  mov     ebx, 800703E3h
0x18000cbdf  jmp     loc_18000CEE8
0x18000cbe4  mov     rcx, r14; this
0x18000cbe7  test    rbx, rbx
0x18000cbea  jnz     short loc_18000CC0D
0x18000cbec  mov     r9d, [rsp+150h+var_E8]; unsigned int
0x18000cbf1  mov     r8d, r15d; int
0x18000cbf4  mov     [rsp+150h+var_128], r13; unsigned __int16 *
0x18000cbf9  xor     edx, edx; int
0x18000cbfb  mov     [rsp+150h+var_130], r13; struct IAppHostConfigException *
0x18000cc00  mov     ebx, r13d
0x18000cc03  call    ?EndResponse@IIS_MODULE@@AEAAXHJIPEAUIAppHostConfigException@@PEBG@Z; IIS_MODULE::EndResponse(int,long,uint,IAppHostConfigException *,ushort const *)
0x18000cc08  jmp     loc_18000CEE8
0x18000cc0d  mov     rax, [r14]
0x18000cc10  mov     rax, [rax+40h]
0x18000cc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc19  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000cc20  mov     [rdi+20h], rbx
0x18000cc24  mov     [rsp+150h+var_110], rax
0x18000cc29  lea     rdx, [rsp+150h+var_110]
0x18000cc2e  mov     rax, [rsi]
0x18000cc31  xorps   xmm0, xmm0
0x18000cc34  mov     rcx, rsi
0x18000cc37  movdqu  xmmword ptr [rsp+48h], xmm0
0x18000cc3d  mov     rax, [rax]
0x18000cc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc45  mov     ecx, 1000h
0x18000cc4a  test    eax, eax
0x18000cc4c  js      loc_18000CD21
0x18000cc52  cmp     dword ptr [rsp+150h+var_108+8], r12d
0x18000cc57  jz      loc_18000CD21
0x18000cc5d  cmp     dword ptr [rsp+150h+var_108], ecx
0x18000cc61  jz      short loc_18000CC6D
0x18000cc63  test    dword ptr [rsp+150h+var_108], ecx
0x18000cc67  jz      loc_18000CD21
0x18000cc6d  mov     r15, [rdi+20h]
0x18000cc71  lea     rcx, [r15+70h]; lpCriticalSection
0x18000cc75  call    cs:__imp_EnterCriticalSection
0x18000cc7b  lea     rdx, [r15+138h]
0x18000cc82  lea     rcx, [rbp+50h+var_70]
0x18000cc86  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000cc8c  mov     ebx, eax
0x18000cc8e  test    eax, eax
0x18000cc90  js      short loc_18000CCF0
0x18000cc92  lea     r13, [r15+170h]
0x18000cc99  cmp     [r13+30h], r12d
0x18000cc9d  jz      short loc_18000CCC9
0x18000cc9f  lea     rdx, asc_180011F64; " "
0x18000cca6  lea     rcx, [rbp+50h+var_70]
0x18000ccaa  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000ccb0  mov     ebx, eax
0x18000ccb2  test    eax, eax
0x18000ccb4  js      short loc_18000CCEB
0x18000ccb6  mov     rdx, r13
0x18000ccb9  lea     rcx, [rbp+50h+var_70]
0x18000ccbd  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18000ccc3  mov     ebx, eax
0x18000ccc5  test    eax, eax
0x18000ccc7  js      short loc_18000CCEB
0x18000ccc9  mov     eax, [r15+100h]
0x18000ccd0  xor     r13d, r13d
0x18000ccd3  cmp     eax, 1
0x18000ccd6  mov     dword ptr [rsp+150h+var_118], eax
0x18000ccda  mov     eax, [r15+0FCh]
0x18000cce1  setz    r13b
0x18000cce5  mov     dword ptr [rsp+150h+var_114], eax
0x18000cce9  jmp     short loc_18000CCF0
0x18000cceb  mov     r13d, [rsp+150h+var_11C]
0x18000ccf0  lea     rcx, [r15+70h]; lpCriticalSection
0x18000ccf4  call    cs:__imp_LeaveCriticalSection
0x18000ccfa  test    ebx, ebx
0x18000ccfc  js      short loc_18000CD21
0x18000ccfe  mov     eax, dword ptr [rsp+150h+var_118]
0x18000cd02  mov     r9d, r13d; int
0x18000cd05  mov     dword ptr [rsp+150h+var_128], eax; char
0x18000cd09  mov     rcx, rsi; struct IHttpTraceContext *
0x18000cd0c  mov     eax, dword ptr [rsp+150h+var_114]
0x18000cd10  mov     dword ptr [rsp+150h+var_130], eax; char
0x18000cd14  lea     rax, [rbp+50h+var_70]
0x18000cd18  mov     r8, [rax+20h]; unsigned __int16 *
0x18000cd1c  call    ?RaiseEvent@FASTCGI_ASSIGN_PROCESS@IISFastCGIEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGHKK@Z; IISFastCGIEvents::FASTCGI_ASSIGN_PROCESS::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,int,ulong,ulong)
0x18000cd21  mov     rcx, r14; this
0x18000cd24  call    ?CreateParams@IIS_MODULE@@AEAAJPEAVIHttpContext@@@Z; IIS_MODULE::CreateParams(IHttpContext *)
0x18000cd29  xor     r13d, r13d
0x18000cd2c  mov     ebx, eax
0x18000cd2e  test    eax, eax
0x18000cd30  js      loc_18000CEE8
0x18000cd36  mov     rcx, [rsp+150h+var_E0]
0x18000cd3b  mov     r15d, r13d
0x18000cd3e  mov     rax, [rcx]
0x18000cd41  mov     rax, [rax+90h]
0x18000cd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd4d  lea     ebx, [r13+1]
0x18000cd51  test    eax, eax
0x18000cd53  jnz     short loc_18000CD66
0x18000cd55  mov     r15d, ebx
0x18000cd58  mov     [rdi+8Ch], r13d
0x18000cd5f  mov     r12d, ebx
0x18000cd62  mov     [rsp+150h+var_120], ebx
0x18000cd66  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000cd6d  xorps   xmm0, xmm0
0x18000cd70  mov     [rsp+150h+var_110], rax
0x18000cd75  lea     rdx, [rsp+150h+var_110]
0x18000cd7a  mov     rax, [rsi]
0x18000cd7d  mov     rcx, rsi
0x18000cd80  movdqu  [rsp+150h+var_108], xmm0
0x18000cd86  mov     rax, [rax]
0x18000cd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd8e  test    eax, eax
0x18000cd90  js      loc_18000CE44
0x18000cd96  cmp     dword ptr [rsp+150h+var_108+8], r13d
0x18000cd9b  jz      loc_18000CE44
0x18000cda1  mov     ecx, 1000h
0x18000cda6  cmp     dword ptr [rsp+150h+var_108], ecx
0x18000cdaa  jz      short loc_18000CDB6
0x18000cdac  test    dword ptr [rsp+150h+var_108], ecx
0x18000cdb0  jz      loc_18000CE44
0x18000cdb6  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000cdbd  mov     [rbp+50h+var_C8], rcx
0x18000cdc1  mov     [rbp+50h+var_D0], rax
0x18000cdc5  lea     rdx, [rbp+50h+var_D0]
0x18000cdc9  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000cdd0  mov     [rbp+50h+var_B8], 12h
0x18000cdd8  mov     [rbp+50h+var_C0], rax
0x18000cddc  xorps   xmm0, xmm0
0x18000cddf  lea     rax, aFastcgiStart; "FASTCGI_START"
0x18000cde6  mov     [rbp+50h+var_88], 1
0x18000cdee  mov     [rbp+50h+var_B0], rax
0x18000cdf2  mov     rcx, rsi
0x18000cdf5  lea     rax, aContextid; "ContextId"
0x18000cdfc  mov     [rbp+50h+var_A8], 1
0x18000ce04  mov     [rsp+150h+var_110], rax
0x18000ce09  lea     rax, [rsp+150h+var_110]
0x18000ce0e  mov     [rbp+50h+var_80], rax
0x18000ce12  mov     rax, [rsi]
0x18000ce15  movdqa  [rbp+50h+var_A0], xmm0
0x18000ce1a  mov     [rbp+50h+var_90], r13d
0x18000ce1e  mov     [rbp+50h+var_8C], ebx
0x18000ce21  mov     rax, [rax+10h]
0x18000ce25  mov     dword ptr [rsp+150h+var_108], 48h ; 'H'
0x18000ce2d  mov     qword ptr [rsp+150h+var_108+8], r13
0x18000ce32  mov     [rsp+150h+var_F8], 10h
0x18000ce3a  mov     [rsp+150h+var_F0], r13
0x18000ce3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce44  mov     eax, [rdi+0E0h]
0x18000ce4a  mov     r9d, r15d; int
0x18000ce4d  mov     r8d, [rdi+78h]; unsigned int
0x18000ce51  mov     rdx, [rdi+70h]; struct _FCGI_PARAM *
0x18000ce55  mov     rcx, [rdi+20h]; this
0x18000ce59  mov     [rsp+150h+var_128], r14; struct IAPPLICATION_CALLBACK *
0x18000ce5e  mov     dword ptr [rsp+150h+var_130], eax; unsigned int
0x18000ce62  call    ?SendFcgiParams@APPLICATION@@QEAAJPEAU_FCGI_PARAM@@KHKPEAVIAPPLICATION_CALLBACK@@@Z; APPLICATION::SendFcgiParams(_FCGI_PARAM *,ulong,int,ulong,IAPPLICATION_CALLBACK *)
0x18000ce67  mov     rcx, [rdi+70h]; Block
0x18000ce6b  mov     ebx, eax
0x18000ce6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ce72  mov     [rdi+70h], r13
0x18000ce76  test    ebx, ebx
0x18000ce78  js      short loc_18000CEE8
0x18000ce7a  test    r15d, r15d
0x18000ce7d  jz      short loc_18000CED4
0x18000ce7f  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000ce86  xorps   xmm0, xmm0
0x18000ce89  mov     [rsp+150h+var_110], rax
0x18000ce8e  lea     rdx, [rsp+150h+var_110]
0x18000ce93  mov     rax, [rsi]
0x18000ce96  mov     rcx, rsi
0x18000ce99  movdqu  [rsp+150h+var_108], xmm0
0x18000ce9f  mov     rax, [rax]
0x18000cea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cea7  test    eax, eax
0x18000cea9  js      short loc_18000CEE8
0x18000ceab  cmp     dword ptr [rsp+150h+var_108+8], r13d
0x18000ceb0  jz      short loc_18000CEE8
0x18000ceb2  cmp     dword ptr [rsp+150h+var_108+4], 5
0x18000ceb7  jb      short loc_18000CEE8
0x18000ceb9  mov     eax, 1000h
0x18000cebe  cmp     dword ptr [rsp+150h+var_108], eax
0x18000cec2  jz      short loc_18000CECA
0x18000cec4  test    dword ptr [rsp+150h+var_108], eax
0x18000cec8  jz      short loc_18000CEE8
0x18000ceca  mov     rcx, rsi; struct IHttpTraceContext *
0x18000cecd  call    ?RaiseEvent@FASTCGI_WAITING_FOR_RESPONSE@IISFastCGIEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISFastCGIEvents::FASTCGI_WAITING_FOR_RESPONSE::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000ced2  jmp     short loc_18000CEE8
0x18000ced4  lea     rdx, [rsp+150h+var_120]; int *
0x18000ced9  mov     rcx, r14; this
0x18000cedc  call    ?BeginReceiveEntity@IIS_MODULE@@AEAAJPEAH@Z; IIS_MODULE::BeginReceiveEntity(int *)
0x18000cee1  mov     r12d, [rsp+150h+var_120]
0x18000cee6  mov     ebx, eax
0x18000cee8  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000ceec  call    cs:__imp_LeaveCriticalSection
0x18000cef2  test    ebx, ebx
0x18000cef4  js      short loc_18000CF0A
0x18000cef6  test    r12d, r12d
0x18000cef9  jz      short loc_18000CF24
0x18000cefb  mov     rcx, [rdi+20h]; this
0x18000ceff  call    ?StartIISSends@APPLICATION@@QEAAJXZ; APPLICATION::StartIISSends(void)
0x18000cf04  mov     ebx, eax
0x18000cf06  test    eax, eax
0x18000cf08  jns     short loc_18000CF24
0x18000cf0a  mov     [rsp+150h+var_128], r13; unsigned __int16 *
0x18000cf0f  xor     r9d, r9d; unsigned int
0x18000cf12  mov     r8d, ebx; int
0x18000cf15  mov     [rsp+150h+var_130], r13; struct IAppHostConfigException *
0x18000cf1a  xor     edx, edx; int
0x18000cf1c  mov     rcx, r14; this
0x18000cf1f  call    ?EndResponse@IIS_MODULE@@AEAAXHJIPEAUIAppHostConfigException@@PEBG@Z; IIS_MODULE::EndResponse(int,long,uint,IAppHostConfigException *,ushort const *)
0x18000cf24  lea     rcx, [rbp+50h+var_70]
0x18000cf28  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cf2e  mov     rcx, [rbp+50h+var_38]
0x18000cf32  xor     rcx, rsp; StackCookie
0x18000cf35  call    __security_check_cookie
0x18000cf3a  mov     rbx, [rsp+150h+arg_8]
0x18000cf42  add     rsp, 120h
0x18000cf49  pop     r15
0x18000cf4b  pop     r14
0x18000cf4d  pop     r13
0x18000cf4f  pop     r12
0x18000cf51  pop     rdi
0x18000cf52  pop     rsi
0x18000cf53  pop     rbp
0x18000cf54  retn
```
