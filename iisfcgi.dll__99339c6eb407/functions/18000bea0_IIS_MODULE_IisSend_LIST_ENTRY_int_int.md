# IIS_MODULE::IisSend(_LIST_ENTRY *,int,int)

- ea: `0x18000bea0`
- end: `0x18000c386`
- name: `?IisSend@IIS_MODULE@@UEAAJPEAU_LIST_ENTRY@@HH@Z`
- size: `1254`
- prototype: `__int64 __fastcall(IIS_MODULE *__hidden this, struct _LIST_ENTRY *, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005030`
- `0x180009128`
- `0x18000bb5c`
- `0x18000bea0`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bf14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bf14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2ce`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18000c075`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18000c075`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c106`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c106`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c042`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c042`

## pseudocode

```c
__int64 __fastcall IIS_MODULE::IisSend(IIS_MODULE *this, struct _LIST_ENTRY *a2, int a3, int a4)
{
  __int64 v8; // r15
  __int64 v9; // rax
  int (__fastcall ***v10)(_QWORD, GUID **); // r14
  int v11; // esi
  APPLICATION *v12; // rcx
  int (__fastcall **v13)(_QWORD, GUID **); // rax
  int (__fastcall **v14)(_QWORD, GUID **); // rax
  int (__fastcall *v15)(_QWORD, GUID **); // rax
  __int64 v16; // r14
  unsigned int v17; // edx
  __int64 v18; // r9
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v20; // rax
  IIS_MODULE **v21; // rdx
  int (__fastcall ***v22)(_QWORD, GUID **); // r14
  int (__fastcall **v23)(_QWORD, GUID **); // rcx
  int (__fastcall **v24)(_QWORD, GUID **); // rax
  int (__fastcall *v25)(_QWORD, GUID **); // rax
  struct _LIST_ENTRY *v26; // rcx
  struct _LIST_ENTRY *v27; // rax
  _QWORD **v28; // rbx
  _QWORD *v29; // rcx
  _QWORD *v30; // rax
  GUID *v32; // [rsp+40h] [rbp-99h] BYREF
  __int64 v33; // [rsp+48h] [rbp-91h]
  GUID *v34; // [rsp+50h] [rbp-89h]
  __int64 v35; // [rsp+58h] [rbp-81h]
  const wchar_t *v36; // [rsp+60h] [rbp-79h]
  __int64 v37; // [rsp+68h] [rbp-71h]
  __int128 v38; // [rsp+70h] [rbp-69h]
  int v39; // [rsp+80h] [rbp-59h]
  int v40; // [rsp+84h] [rbp-55h]
  __int64 v41; // [rsp+88h] [rbp-51h]
  GUID **v42; // [rsp+90h] [rbp-49h]
  __int128 v43; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v44; // [rsp+B0h] [rbp-29h]
  GUID *v45; // [rsp+C0h] [rbp-19h] BYREF
  __int128 v46; // [rsp+C8h] [rbp-11h]
  int v47; // [rsp+D8h] [rbp-1h]
  _WORD *v48; // [rsp+E0h] [rbp+7h]
  int v49; // [rsp+F0h] [rbp+17h]

  v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 32LL))(*((_QWORD *)this + 21));
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 272LL))(*((_QWORD *)this + 21));
  v43 = 0;
  v10 = (int (__fastcall ***)(_QWORD, GUID **))v9;
  v44 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 22) )
  {
    v11 = -2147023901;
  }
  else
  {
    v11 = 0;
    if ( a4 )
    {
      v12 = (APPLICATION *)*((_QWORD *)this + 5);
      *((_DWORD *)this + 27) = 1;
      if ( v12 )
      {
        APPLICATION::DereferenceApplication(v12);
        *((_QWORD *)this + 5) = 0;
        v45 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v13 = *v10;
        v46 = 0;
        if ( (*v13)(v10, &v45) >= 0 && DWORD2(v46) && ((_DWORD)v46 == 4096 || (v46 & 0x1000) != 0) )
        {
          v33 = 4096;
          v32 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
          v39 = 0;
          v34 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
          *((_QWORD *)&v46 + 1) = 0;
          v36 = L"FASTCGI_END";
          v37 = 1;
          v40 = 1;
          v45 = (GUID *)L"ContextId";
          v42 = &v45;
          v14 = *v10;
          v48 = 0;
          v35 = 19;
          v41 = 1;
          v15 = v14[2];
          v38 = 0;
          LODWORD(v46) = 72;
          v47 = 16;
          v15(v10, &v32);
        }
      }
    }
    if ( !*((_DWORD *)this + 28) || a3 )
    {
      STRU::STRU((STRU *)&v45);
      v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 272LL))(*((_QWORD *)this + 21));
      if ( a2->Flink != a2
        && (int)STRU::CopyA((STRU *)&v45, (const char *)a2->Flink[-1].Flink, (unsigned int)a2->Flink[-1].Blink) < 0 )
      {
        *v48 = 0;
        v49 = 0;
      }
      v17 = a4 != 0 ? 6 : 2;
      if ( !*((_DWORD *)this + 28) )
        v17 = a4 != 0 ? 4 : 0;
      v18 = v17 + 1;
      if ( !a3 )
        v18 = v17;
      (*(void (__fastcall **)(__int64, const wchar_t *, _WORD *, __int64, char))(*(_QWORD *)v16 + 32LL))(
        v16,
        L"FASTCGI_RESPONSE_ERROR",
        v48,
        v18,
        3);
      *((_DWORD *)this + 28) = 1;
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v8 + 24LL))(
        v8,
        500,
        "Internal Server Error",
        0,
        0,
        0,
        0);
      STRU::~STRU((STRU *)&v45);
    }
    while ( 1 )
    {
      Flink = a2->Flink;
      if ( a2->Flink == a2 )
        break;
      if ( Flink->Blink != a2
        || (v20 = Flink->Flink, Flink->Flink->Blink != Flink)
        || (a2->Flink = v20,
            v20->Blink = a2,
            v21 = (IIS_MODULE **)*((_QWORD *)this + 31),
            *v21 != (IIS_MODULE *)((char *)this + 240)) )
      {
LABEL_48:
        __fastfail(3u);
      }
      Flink->Flink = (struct _LIST_ENTRY *)((char *)this + 240);
      Flink->Blink = (struct _LIST_ENTRY *)v21;
      *v21 = (IIS_MODULE *)Flink;
      *((_QWORD *)this + 31) = Flink;
      LODWORD(v43) = 0;
      *((_QWORD *)&v43 + 1) = Flink[-1].Flink;
      LODWORD(v44) = Flink[-1].Blink;
      v11 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v8 + 160LL))(v8, &v43, 0xFFFFFFFFLL);
      if ( v11 < 0 )
        goto LABEL_35;
    }
    if ( a4 )
    {
      v22 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 272LL))(*((_QWORD *)this + 21));
      v45 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v23 = *v22;
      v46 = 0;
      if ( (*v23)(v22, &v45) >= 0 && DWORD2(v46) && DWORD1(v46) >= 4 && ((_DWORD)v46 == 4096 || (v46 & 0x1000) != 0) )
      {
        v33 = 4096;
        v34 = &`IISFastCGIEvents::GetAreaGuid'::`2'::AreaGuid;
        v35 = 11;
        v36 = L"FASTCGI_RESPONSE_WRITTEN";
        v41 = 1;
        v45 = (GUID *)L"ContextId";
        v32 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v42 = &v45;
        v24 = *v22;
        v37 = 0x400000001LL;
        v38 = 0;
        v25 = v24[2];
        v39 = 0;
        v40 = 1;
        LODWORD(v46) = 72;
        *((_QWORD *)&v46 + 1) = 0;
        v47 = 16;
        v48 = 0;
        v25(v22, &v32);
      }
    }
    else
    {
      *((_DWORD *)this + 23) = 1;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v8 + 144LL))(
              v8,
              1,
              1,
              0,
              0);
      if ( v11 < 0 )
        *((_DWORD *)this + 23) = 0;
    }
  }
LABEL_35:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( v11 >= 0 && a4 )
    IIS_MODULE::EndResponse(this, 1, 0, 0, 0, 0);
  while ( 1 )
  {
    v26 = a2->Flink;
    if ( a2->Flink == a2 )
      break;
    if ( v26->Blink != a2 )
      goto LABEL_48;
    v27 = v26->Flink;
    if ( v26->Flink->Blink != v26 )
      goto LABEL_48;
    a2->Flink = v27;
    v27->Blink = a2;
    FCGI_BUFFER::Free((FCGI_BUFFER *)&v26[-2]);
  }
  if ( v11 < 0 )
  {
    v28 = (_QWORD **)((char *)this + 240);
    while ( 1 )
    {
      v29 = *v28;
      if ( *v28 == v28 )
        break;
      if ( (_QWORD **)v29[1] != v28 )
        goto LABEL_48;
      v30 = (_QWORD *)*v29;
      if ( *(_QWORD **)(*v29 + 8LL) != v29 )
        goto LABEL_48;
      *v28 = v30;
      v30[1] = v28;
      FCGI_BUFFER::Free((FCGI_BUFFER *)(v29 - 4));
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000bea0  mov     [rsp-8+arg_10], rbx
0x18000bea5  push    rbp
0x18000bea6  push    rsi
0x18000bea7  push    rdi
0x18000bea8  push    r12
0x18000beaa  push    r13
0x18000beac  push    r14
0x18000beae  push    r15
0x18000beb0  lea     rbp, [rsp-27h]
0x18000beb5  sub     rsp, 100h
0x18000bebc  mov     rax, cs:__security_cookie
0x18000bec3  xor     rax, rsp
0x18000bec6  mov     [rbp+57h+var_38], rax
0x18000beca  mov     rbx, rcx
0x18000becd  mov     r12d, r9d
0x18000bed0  mov     rcx, [rcx+0A8h]
0x18000bed7  mov     r13d, r8d
0x18000beda  mov     rdi, rdx
0x18000bedd  mov     rax, [rcx]
0x18000bee0  mov     rax, [rax+20h]
0x18000bee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee9  mov     rcx, [rbx+0A8h]
0x18000bef0  mov     r15, rax
0x18000bef3  mov     rax, [rcx]
0x18000bef6  mov     rax, [rax+110h]
0x18000befd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf02  xorps   xmm0, xmm0
0x18000bf05  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000bf09  movups  [rbp+57h+var_90], xmm0
0x18000bf0d  mov     r14, rax
0x18000bf10  movups  [rbp+57h+var_80], xmm0
0x18000bf14  call    cs:__imp_EnterCriticalSection
0x18000bf1a  xor     edx, edx
0x18000bf1c  cmp     [rbx+58h], edx
0x18000bf1f  jz      short loc_18000BF2E
0x18000bf21  mov     esi, 800703E3h
0x18000bf26  xor     r13d, r13d
0x18000bf29  jmp     loc_18000C2CA
0x18000bf2e  mov     esi, edx
0x18000bf30  test    r12d, r12d
0x18000bf33  jz      loc_18000C030
0x18000bf39  mov     rcx, [rbx+28h]; this
0x18000bf3d  mov     dword ptr [rbx+6Ch], 1
0x18000bf44  test    rcx, rcx
0x18000bf47  jz      loc_18000C030
0x18000bf4d  call    ?DereferenceApplication@APPLICATION@@QEAAXXZ; APPLICATION::DereferenceApplication(void)
0x18000bf52  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000bf59  mov     [rbx+28h], rsi
0x18000bf5d  mov     [rbp+57h+var_70], rax
0x18000bf61  lea     rdx, [rbp+57h+var_70]
0x18000bf65  mov     rax, [r14]
0x18000bf68  xorps   xmm0, xmm0
0x18000bf6b  mov     rcx, r14
0x18000bf6e  movdqu  [rbp+57h+var_68], xmm0
0x18000bf73  mov     rax, [rax]
0x18000bf76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf7b  xor     edx, edx
0x18000bf7d  test    eax, eax
0x18000bf7f  js      loc_18000C030
0x18000bf85  cmp     dword ptr [rbp+57h+var_68+8], edx
0x18000bf88  jz      loc_18000C030
0x18000bf8e  mov     ecx, 1000h
0x18000bf93  cmp     dword ptr [rbp+57h+var_68], ecx
0x18000bf96  jz      short loc_18000BFA1
0x18000bf98  test    dword ptr [rbp+57h+var_68], ecx
0x18000bf9b  jz      loc_18000C030
0x18000bfa1  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000bfa8  mov     [rsp+130h+var_E8], rcx
0x18000bfad  mov     [rsp+130h+var_F0], rax
0x18000bfb2  xorps   xmm0, xmm0
0x18000bfb5  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000bfbc  mov     [rbp+57h+var_B0], edx
0x18000bfbf  mov     [rsp+130h+var_E0], rax
0x18000bfc4  mov     rcx, r14
0x18000bfc7  lea     rax, aFastcgiEnd; "FASTCGI_END"
0x18000bfce  mov     qword ptr [rbp+57h+var_68+8], rdx
0x18000bfd2  mov     [rbp+57h+var_D0], rax
0x18000bfd6  mov     eax, 1
0x18000bfdb  mov     [rbp+57h+var_C8], rax
0x18000bfdf  mov     [rbp+57h+var_AC], eax
0x18000bfe2  lea     rax, aContextid; "ContextId"
0x18000bfe9  mov     [rbp+57h+var_70], rax
0x18000bfed  lea     rax, [rbp+57h+var_70]
0x18000bff1  mov     [rbp+57h+var_A0], rax
0x18000bff5  mov     rax, [r14]
0x18000bff8  mov     [rbp+57h+var_50], rdx
0x18000bffc  lea     rdx, [rsp+130h+var_F0]
0x18000c001  mov     [rsp+130h+var_D8], 13h
0x18000c00a  mov     [rbp+57h+var_A8], 1
0x18000c012  mov     rax, [rax+10h]
0x18000c016  movdqa  [rbp+57h+var_C0], xmm0
0x18000c01b  mov     dword ptr [rbp+57h+var_68], 48h ; 'H'
0x18000c022  mov     [rbp+57h+var_58], 10h
0x18000c029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c02e  xor     edx, edx
0x18000c030  cmp     [rbx+70h], edx
0x18000c033  jz      short loc_18000C03E
0x18000c035  test    r13d, r13d
0x18000c038  jz      loc_18000C10E
0x18000c03e  lea     rcx, [rbp+57h+var_70]
0x18000c042  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c048  mov     rcx, [rbx+0A8h]
0x18000c04f  mov     rax, [rcx]
0x18000c052  mov     rax, [rax+110h]
0x18000c059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c05e  mov     rdx, [rdi]
0x18000c061  mov     r14, rax
0x18000c064  cmp     rdx, rdi
0x18000c067  jz      short loc_18000C08B
0x18000c069  mov     r8d, [rdx-8]
0x18000c06d  lea     rcx, [rbp+57h+var_70]
0x18000c071  mov     rdx, [rdx-10h]
0x18000c075  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x18000c07b  test    eax, eax
0x18000c07d  jns     short loc_18000C08B
0x18000c07f  mov     rcx, [rbp+57h+var_50]
0x18000c083  xor     edx, edx
0x18000c085  mov     [rcx], dx
0x18000c088  mov     [rbp+57h+var_40], edx
0x18000c08b  mov     r8, [rbp+57h+var_50]
0x18000c08f  mov     eax, r12d
0x18000c092  neg     eax
0x18000c094  mov     byte ptr [rsp+130h+var_110], 3
0x18000c099  mov     rax, [r14]
0x18000c09c  sbb     ecx, ecx
0x18000c09e  and     ecx, 4
0x18000c0a1  cmp     [rbx+70h], esi
0x18000c0a4  mov     rax, [rax+20h]
0x18000c0a8  lea     edx, [rcx+2]
0x18000c0ab  cmovz   edx, ecx
0x18000c0ae  test    r13d, r13d
0x18000c0b1  mov     rcx, r14
0x18000c0b4  lea     r9d, [rdx+1]
0x18000c0b8  cmovz   r9d, edx
0x18000c0bc  lea     rdx, aFastcgiRespons_0; "FASTCGI_RESPONSE_ERROR"
0x18000c0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0c8  xor     r13d, r13d
0x18000c0cb  lea     r8, aInternalServer; "Internal Server Error"
0x18000c0d2  mov     [rsp+130h+var_100], r13d
0x18000c0d7  mov     r14d, 1
0x18000c0dd  mov     [rbx+70h], r14d
0x18000c0e1  xor     r9d, r9d
0x18000c0e4  mov     rax, [r15]
0x18000c0e7  mov     edx, 1F4h
0x18000c0ec  mov     [rsp+130h+var_108], r13
0x18000c0f1  mov     rcx, r15
0x18000c0f4  mov     dword ptr [rsp+130h+var_110], r13d
0x18000c0f9  mov     rax, [rax+18h]
0x18000c0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c102  lea     rcx, [rbp+57h+var_70]
0x18000c106  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c10c  jmp     short loc_18000C115
0x18000c10e  xor     r13d, r13d
0x18000c111  lea     r14d, [r13+1]
0x18000c115  mov     rcx, [rdi]
0x18000c118  cmp     rcx, rdi
0x18000c11b  jz      short loc_18000C194
0x18000c11d  cmp     [rcx+8], rdi
0x18000c121  jnz     loc_18000C356
0x18000c127  mov     rax, [rcx]
0x18000c12a  cmp     [rax+8], rcx
0x18000c12e  jnz     loc_18000C356
0x18000c134  mov     [rdi], rax
0x18000c137  mov     [rax+8], rdi
0x18000c13b  lea     rax, [rbx+0F0h]
0x18000c142  mov     rdx, [rax+8]
0x18000c146  cmp     [rdx], rax
0x18000c149  jnz     loc_18000C356
0x18000c14f  mov     [rcx], rax
0x18000c152  or      r8d, 0FFFFFFFFh
0x18000c156  mov     [rcx+8], rdx
0x18000c15a  mov     [rdx], rcx
0x18000c15d  lea     rdx, [rbp+57h+var_90]
0x18000c161  mov     [rax+8], rcx
0x18000c165  mov     dword ptr [rbp+57h+var_90], r13d
0x18000c169  mov     rax, [rcx-10h]
0x18000c16d  mov     qword ptr [rbp+57h+var_90+8], rax
0x18000c171  mov     eax, [rcx-8]
0x18000c174  mov     rcx, r15
0x18000c177  mov     dword ptr [rbp+57h+var_80], eax
0x18000c17a  mov     rax, [r15]
0x18000c17d  mov     rax, [rax+0A0h]
0x18000c184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c189  mov     esi, eax
0x18000c18b  test    eax, eax
0x18000c18d  jns     short loc_18000C115
0x18000c18f  jmp     loc_18000C2CA
0x18000c194  test    r12d, r12d
0x18000c197  jz      loc_18000C29C
0x18000c19d  mov     rcx, [rbx+0A8h]
0x18000c1a4  mov     rax, [rcx]
0x18000c1a7  mov     rax, [rax+110h]
0x18000c1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1b3  mov     r14, rax
0x18000c1b6  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000c1bd  xorps   xmm0, xmm0
0x18000c1c0  mov     [rbp+57h+var_70], r15
0x18000c1c4  lea     rdx, [rbp+57h+var_70]
0x18000c1c8  mov     rcx, [rax]
0x18000c1cb  movdqu  [rbp+57h+var_68], xmm0
0x18000c1d0  mov     rax, [rcx]
0x18000c1d3  mov     rcx, r14
0x18000c1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1db  test    eax, eax
0x18000c1dd  js      loc_18000C2CA
0x18000c1e3  cmp     dword ptr [rbp+57h+var_68+8], r13d
0x18000c1e7  jz      loc_18000C2CA
0x18000c1ed  cmp     dword ptr [rbp+57h+var_68+4], 4
0x18000c1f1  jb      loc_18000C2CA
0x18000c1f7  mov     ecx, 1000h
0x18000c1fc  cmp     dword ptr [rbp+57h+var_68], ecx
0x18000c1ff  jz      short loc_18000C20A
0x18000c201  test    dword ptr [rbp+57h+var_68], ecx
0x18000c204  jz      loc_18000C2CA
0x18000c20a  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFastCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFastCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x18000c211  mov     [rsp+130h+var_E8], rcx
0x18000c216  mov     [rsp+130h+var_E0], rax
0x18000c21b  lea     rdx, [rsp+130h+var_F0]
0x18000c220  lea     rax, aFastcgiRespons; "FASTCGI_RESPONSE_WRITTEN"
0x18000c227  mov     [rsp+130h+var_D8], 0Bh
0x18000c230  mov     [rbp+57h+var_D0], rax
0x18000c234  xorps   xmm0, xmm0
0x18000c237  lea     rax, aContextid; "ContextId"
0x18000c23e  mov     [rbp+57h+var_A8], 1
0x18000c246  mov     [rbp+57h+var_70], rax
0x18000c24a  mov     rcx, r14
0x18000c24d  lea     rax, [rbp+57h+var_70]
0x18000c251  mov     [rsp+130h+var_F0], r15
0x18000c256  mov     [rbp+57h+var_A0], rax
0x18000c25a  mov     rax, [r14]
0x18000c25d  mov     dword ptr [rbp+57h+var_C8], 1
0x18000c264  mov     dword ptr [rbp+57h+var_C8+4], 4
0x18000c26b  movdqa  [rbp+57h+var_C0], xmm0
0x18000c270  mov     rax, [rax+10h]
0x18000c274  mov     [rbp+57h+var_B0], r13d
0x18000c278  mov     [rbp+57h+var_AC], 1
0x18000c27f  mov     dword ptr [rbp+57h+var_68], 48h ; 'H'
0x18000c286  mov     qword ptr [rbp+57h+var_68+8], r13
0x18000c28a  mov     [rbp+57h+var_58], 10h
0x18000c291  mov     [rbp+57h+var_50], r13
0x18000c295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c29a  jmp     short loc_18000C2CA
0x18000c29c  mov     [rbx+5Ch], r14d
0x18000c2a0  xor     r9d, r9d
0x18000c2a3  mov     rax, [r15]
0x18000c2a6  mov     r8d, r14d
0x18000c2a9  mov     edx, r14d
0x18000c2ac  mov     [rsp+130h+var_110], r13
0x18000c2b1  mov     rcx, r15
0x18000c2b4  mov     rax, [rax+90h]
0x18000c2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c0  mov     esi, eax
0x18000c2c2  test    eax, eax
0x18000c2c4  jns     short loc_18000C2CA
0x18000c2c6  mov     [rbx+5Ch], r13d
0x18000c2ca  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000c2ce  call    cs:__imp_LeaveCriticalSection
0x18000c2d4  test    esi, esi
0x18000c2d6  js      short loc_18000C2F9
0x18000c2d8  test    r12d, r12d
0x18000c2db  jz      short loc_18000C2F9
0x18000c2dd  xor     r9d, r9d; unsigned int
0x18000c2e0  mov     [rsp+130h+var_108], r13; unsigned __int16 *
0x18000c2e5  xor     r8d, r8d; int
0x18000c2e8  mov     [rsp+130h+var_110], r13; struct IAppHostConfigException *
0x18000c2ed  mov     rcx, rbx; this
0x18000c2f0  lea     edx, [r9+1]; int
0x18000c2f4  call    ?EndResponse@IIS_MODULE@@AEAAXHJIPEAUIAppHostConfigException@@PEBG@Z; IIS_MODULE::EndResponse(int,long,uint,IAppHostConfigException *,ushort const *)
0x18000c2f9  mov     rcx, [rdi]
0x18000c2fc  cmp     rcx, rdi
0x18000c2ff  jz      short loc_18000C322
0x18000c301  cmp     [rcx+8], rdi
0x18000c305  jnz     short loc_18000C356
0x18000c307  mov     rax, [rcx]
0x18000c30a  cmp     [rax+8], rcx
0x18000c30e  jnz     short loc_18000C356
0x18000c310  mov     [rdi], rax
0x18000c313  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x18000c317  mov     [rax+8], rdi
0x18000c31b  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x18000c320  jmp     short loc_18000C2F9
0x18000c322  test    esi, esi
0x18000c324  jns     short loc_18000C35D
0x18000c326  add     rbx, 0F0h
0x18000c32d  mov     rcx, [rbx]
0x18000c330  cmp     rcx, rbx
0x18000c333  jz      short loc_18000C35D
0x18000c335  cmp     [rcx+8], rbx
0x18000c339  jnz     short loc_18000C356
0x18000c33b  mov     rax, [rcx]
0x18000c33e  cmp     [rax+8], rcx
0x18000c342  jnz     short loc_18000C356
0x18000c344  mov     [rbx], rax
0x18000c347  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x18000c34b  mov     [rax+8], rbx
0x18000c34f  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x18000c354  jmp     short loc_18000C32D
0x18000c356  mov     ecx, 3
0x18000c35b  int     29h; Win8: RtlFailFast(ecx)
0x18000c35d  mov     eax, esi
  ... truncated ...
```
