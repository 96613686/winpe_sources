# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800021ec`
- end: `0x1800025a8`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `956`
- prototype: `__int64 __fastcall(int, __int64, struct IHttpContext *, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001a50`
- `0x180001cb0`

## callees

- `0x1800021ec`
- `0x180002758`
- `0x1800035c6`
- `0x1800035f0`
- `0x180004010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x1800024a0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800024b9`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800024a0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800024b9`
- `iisutil!?Escape@STRA@@QEAAJ_N0@Z` at `0x180002459`
- `iisutil!?Escape@STRA@@QEAAJ_N0@Z` at `0x180002459`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJAEBVSTRU@@@Z` at `0x180002444`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJAEBVSTRU@@@Z` at `0x180002444`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002436`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002436`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002268`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002268`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800024aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800024c3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800024aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800024c3`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, __int64 a2, struct IHttpContext *a3, __int64 a4, __int64 a5)
{
  unsigned int v7; // esi
  int v8; // edi
  int (__fastcall ***v9)(_QWORD, GUID **); // rax
  int (__fastcall **v10)(_QWORD, GUID **); // rcx
  __int64 v11; // rdi
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeSectionException *v21; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  _QWORD v24[6]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v25; // [rsp+A0h] [rbp-60h]
  int v26; // [rsp+B0h] [rbp-50h]
  int v27; // [rsp+B4h] [rbp-4Ch]
  int v28; // [rsp+B8h] [rbp-48h]
  _QWORD v29[2]; // [rsp+BCh] [rbp-44h] BYREF
  GUID *v30; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v31; // [rsp+D8h] [rbp-28h]
  const wchar_t *v32; // [rsp+F0h] [rbp-10h] BYREF
  int v33; // [rsp+F8h] [rbp-8h]
  __int64 v34; // [rsp+100h] [rbp+0h]
  int v35; // [rsp+108h] [rbp+8h]
  __int64 v36; // [rsp+110h] [rbp+10h]
  const wchar_t *v37; // [rsp+118h] [rbp+18h]
  int v38; // [rsp+120h] [rbp+20h]
  __int64 v39; // [rsp+128h] [rbp+28h]
  int v40; // [rsp+130h] [rbp+30h]
  __int64 v41; // [rsp+138h] [rbp+38h]
  _BYTE v42[32]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v43; // [rsp+160h] [rbp+60h]
  _BYTE v44[32]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v45; // [rsp+198h] [rbp+98h]
  char v46[1024]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v47[1024]; // [rsp+5B0h] [rbp+4B0h] BYREF

  v21 = 0;
  v20 = 0;
  if ( a1 != 16 )
    return 0;
  v7 = 2;
  if ( !a5 )
  {
    memset_0(v47, 0, sizeof(v47));
    STRU::STRU((STRU *)v42, v47, 0x400u);
    v19 = 0;
    v23 = 0;
    v22 = 0;
    v8 = REDIRECTION_BLOB::CheckUrlRedirection(a3, &v19, (struct STRU *)v42, (struct HTTP_STATUS *)&v22, &v21);
    if ( v8 >= 0 )
    {
      if ( !v19 )
      {
        v7 = 0;
LABEL_19:
        STRU::~STRU((STRU *)v42);
        return v7;
      }
      v9 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
      v30 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v10 = *v9;
      v31 = 0;
      if ( (*v10)(v9, &v30) >= 0 && DWORD2(v31) )
      {
        v11 = v43;
        v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
        v24[3] = 14;
        v24[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v24[1] = 0;
        memset(v29, 0, 12);
        v24[2] = &`IISGeneralEvents::GetAreaGuid'::`2'::AreaGuid;
        v24[4] = L"GENERAL_REDIRECTION_HANDLER";
        v32 = L"ContextId";
        v37 = L"RedirectedURL";
        v24[5] = 1;
        v28 = 2;
        v25 = 0;
        v26 = 0;
        v27 = 1;
        v33 = 72;
        v34 = 0;
        v35 = 16;
        v36 = 0;
        v38 = 31;
        v39 = v11;
        if ( v11 )
        {
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)(v11 + 2 * v14) );
          v13 = 2 * v14 + 2;
        }
        else
        {
          v13 = 0;
        }
        v40 = v13;
        v41 = 0;
        *(_QWORD *)((char *)v29 + 4) = &v32;
        (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v12 + 16LL))(v12, v24);
      }
      v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v15 + 24LL))(
        v15,
        (unsigned __int16)v22,
        *((_QWORD *)&v22 + 1),
        (unsigned __int16)v23,
        0,
        0,
        0);
      STRA::STRA((STRA *)v44, v46, 0x400u);
      v8 = STRA::CopyWToUTF8Unescaped((STRA *)v44, (const struct STRU *)v42);
      if ( v8 >= 0 )
      {
        v8 = STRA::Escape((STRA *)v44, 1, 0);
        if ( v8 >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 152LL))(v16, v45, 0, 0);
          if ( v8 >= 0 )
          {
            STRA::~STRA((STRA *)v44);
            goto LABEL_19;
          }
        }
      }
      STRA::~STRA((STRA *)v44);
    }
    STRU::~STRU((STRU *)v42);
    if ( v21 )
      (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v21)(
        v21,
        &IID_IAppHostConfigException,
        &v20);
    v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17) + 536) = 0;
    v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v18 + 24LL))(
      v18,
      500,
      "Internal Server Error",
      19,
      v8,
      v20,
      0);
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    if ( v21 )
      (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return v7;
}

```

## disassembly

```asm
0x1800021ec  push    rbp
0x1800021ee  push    rbx
0x1800021ef  push    rsi
0x1800021f0  push    rdi
0x1800021f1  push    r12
0x1800021f3  push    r14
0x1800021f5  lea     rbp, [rsp-0CC8h]
0x1800021fd  sub     rsp, 0DC8h
0x180002204  mov     rax, cs:__security_cookie
0x18000220b  xor     rax, rsp
0x18000220e  mov     [rbp+0CF0h+var_40], rax
0x180002215  xor     r14d, r14d
0x180002218  mov     rbx, r8
0x18000221b  mov     [rsp+0DF0h+var_DA0], r14
0x180002220  mov     [rsp+0DF0h+var_DA8], r14
0x180002225  cmp     ecx, 10h
0x180002228  jz      short loc_180002231
0x18000222a  xor     eax, eax
0x18000222c  jmp     loc_180002589
0x180002231  mov     esi, 2
0x180002236  cmp     [rbp+0CF0h+arg_20], r14
0x18000223d  jnz     loc_180002587
0x180002243  xor     edx, edx; Val
0x180002245  lea     rcx, [rbp+0CF0h+var_840]; void *
0x18000224c  mov     r8d, 800h; Size
0x180002252  call    memset_0
0x180002257  mov     r8d, 400h
0x18000225d  lea     rdx, [rbp+0CF0h+var_840]
0x180002264  lea     rcx, [rbp+0CF0h+var_CB0]
0x180002268  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000226e  xor     eax, eax
0x180002270  mov     [rsp+0DF0h+var_DB0], r14d
0x180002275  mov     [rsp+0DF0h+var_D88], rax
0x18000227a  lea     r9, [rsp+0DF0h+var_D98]; struct HTTP_STATUS *
0x18000227f  lea     rax, [rsp+0DF0h+var_DA0]
0x180002284  xorps   xmm0, xmm0
0x180002287  lea     r8, [rbp+0CF0h+var_CB0]; struct STRU *
0x18000228b  mov     [rsp+0DF0h+var_DD0], rax; struct INativeSectionException **
0x180002290  lea     rdx, [rsp+0DF0h+var_DB0]; int *
0x180002295  mov     rcx, rbx; struct IHttpContext *
0x180002298  movups  [rsp+0DF0h+var_D98], xmm0
0x18000229d  call    ?CheckUrlRedirection@REDIRECTION_BLOB@@SAJPEAVIHttpContext@@PEAHPEAVSTRU@@PEAUHTTP_STATUS@@PEAPEAVINativeSectionException@@@Z; REDIRECTION_BLOB::CheckUrlRedirection(IHttpContext *,int *,STRU *,HTTP_STATUS *,INativeSectionException * *)
0x1800022a2  mov     edi, eax
0x1800022a4  test    eax, eax
0x1800022a6  js      loc_1800024BF
0x1800022ac  cmp     [rsp+0DF0h+var_DB0], r14d
0x1800022b1  jnz     short loc_1800022BB
0x1800022b3  mov     esi, r14d
0x1800022b6  jmp     loc_1800024A6
0x1800022bb  mov     rax, [rbx]
0x1800022be  mov     rcx, rbx
0x1800022c1  mov     rax, [rax+110h]
0x1800022c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022cd  mov     r8, rax
0x1800022d0  lea     r12, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800022d7  xorps   xmm0, xmm0
0x1800022da  mov     [rbp+0CF0h+var_D20], r12
0x1800022de  lea     rdx, [rbp+0CF0h+var_D20]
0x1800022e2  mov     rcx, [rax]
0x1800022e5  movdqu  [rbp+0CF0h+var_D18], xmm0
0x1800022ea  mov     rax, [rcx]
0x1800022ed  mov     rcx, r8
0x1800022f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022f5  test    eax, eax
0x1800022f7  js      loc_1800023E5
0x1800022fd  cmp     dword ptr [rbp+0CF0h+var_D18+8], r14d
0x180002301  jz      loc_1800023E5
0x180002307  mov     rax, [rbx]
0x18000230a  mov     rcx, rbx
0x18000230d  mov     rdi, [rbp+0CF0h+var_C90]
0x180002311  mov     rax, [rax+110h]
0x180002318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000231d  mov     rcx, rax
0x180002320  mov     [rbp+0CF0h+var_D68], 0Eh
0x180002328  xor     eax, eax
0x18000232a  mov     [rsp+0DF0h+var_D80], r12
0x18000232f  mov     [rsp+0DF0h+var_D78], rax
0x180002334  xorps   xmm0, xmm0
0x180002337  mov     [rbp+0CF0h+var_D34], rax
0x18000233b  mov     [rbp+0CF0h+var_D2C], eax
0x18000233e  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISGeneralEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISGeneralEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180002345  mov     [rbp+0CF0h+var_D70], rax
0x180002349  lea     rax, aGeneralRedirec; "GENERAL_REDIRECTION_HANDLER"
0x180002350  mov     [rbp+0CF0h+var_D60], rax
0x180002354  lea     rax, aContextid; "ContextId"
0x18000235b  mov     [rbp+0CF0h+var_D00], rax
0x18000235f  lea     rax, aRedirectedurl; "RedirectedURL"
0x180002366  mov     [rbp+0CF0h+var_CD8], rax
0x18000236a  mov     [rbp+0CF0h+var_D58], 1
0x180002372  mov     [rbp+0CF0h+var_D38], esi
0x180002375  movdqa  [rbp+0CF0h+var_D50], xmm0
0x18000237a  mov     [rbp+0CF0h+var_D40], r14d
0x18000237e  mov     [rbp+0CF0h+var_D3C], 1
0x180002385  mov     [rbp+0CF0h+var_CF8], 48h ; 'H'
0x18000238c  mov     [rbp+0CF0h+var_CF0], r14
0x180002390  mov     [rbp+0CF0h+var_CE8], 10h
0x180002397  mov     [rbp+0CF0h+var_CE0], r14
0x18000239b  mov     [rbp+0CF0h+var_CD0], 1Fh
0x1800023a2  mov     [rbp+0CF0h+var_CC8], rdi
0x1800023a6  test    rdi, rdi
0x1800023a9  jnz     short loc_1800023B0
0x1800023ab  mov     eax, r14d
0x1800023ae  jmp     short loc_1800023C5
0x1800023b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800023b4  inc     rax
0x1800023b7  cmp     [rdi+rax*2], r14w
0x1800023bc  jnz     short loc_1800023B4
0x1800023be  lea     eax, ds:2[rax*2]
0x1800023c5  mov     [rbp+0CF0h+var_CC0], eax
0x1800023c8  lea     rdx, [rsp+0DF0h+var_D80]
0x1800023cd  lea     rax, [rbp+0CF0h+var_D00]
0x1800023d1  mov     [rbp+0CF0h+var_CB8], r14
0x1800023d5  mov     [rbp+0CF0h+var_D34+4], rax
0x1800023d9  mov     rax, [rcx]
0x1800023dc  mov     rax, [rax+10h]
0x1800023e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023e5  mov     rax, [rbx]
0x1800023e8  mov     rcx, rbx
0x1800023eb  mov     rax, [rax+20h]
0x1800023ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f4  movzx   r9d, word ptr [rsp+0DF0h+var_D88]
0x1800023fa  mov     r10, rax
0x1800023fd  mov     r8, qword ptr [rsp+0DF0h+var_D98+8]
0x180002402  movzx   edx, word ptr [rsp+0DF0h+var_D98]
0x180002407  mov     rcx, [rax]
0x18000240a  mov     [rsp+0DF0h+var_DC0], r14d
0x18000240f  mov     [rsp+0DF0h+var_DC8], r14
0x180002414  mov     dword ptr [rsp+0DF0h+var_DD0], r14d
0x180002419  mov     rax, [rcx+18h]
0x18000241d  mov     rcx, r10
0x180002420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002425  mov     r8d, 400h
0x18000242b  lea     rdx, [rbp+0CF0h+var_C40]
0x180002432  lea     rcx, [rbp+0CF0h+var_C78]
0x180002436  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000243c  lea     rdx, [rbp+0CF0h+var_CB0]
0x180002440  lea     rcx, [rbp+0CF0h+var_C78]
0x180002444  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJAEBVSTRU@@@Z; STRA::CopyWToUTF8Unescaped(STRU const &)
0x18000244a  mov     edi, eax
0x18000244c  test    eax, eax
0x18000244e  js      short loc_1800024B5
0x180002450  xor     r8d, r8d
0x180002453  lea     rcx, [rbp+0CF0h+var_C78]
0x180002457  mov     dl, 1
0x180002459  call    cs:__imp_?Escape@STRA@@QEAAJ_N0@Z; STRA::Escape(bool,bool)
0x18000245f  mov     edi, eax
0x180002461  test    eax, eax
0x180002463  js      short loc_1800024B5
0x180002465  mov     rax, [rbx]
0x180002468  mov     rcx, rbx
0x18000246b  mov     rax, [rax+20h]
0x18000246f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002474  mov     rdx, [rbp+0CF0h+var_C58]
0x18000247b  mov     r10, rax
0x18000247e  xor     r9d, r9d
0x180002481  xor     r8d, r8d
0x180002484  mov     rcx, [rax]
0x180002487  mov     rax, [rcx+98h]
0x18000248e  mov     rcx, r10
0x180002491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002496  lea     rcx, [rbp+0CF0h+var_C78]
0x18000249a  mov     edi, eax
0x18000249c  test    eax, eax
0x18000249e  js      short loc_1800024B9
0x1800024a0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800024a6  lea     rcx, [rbp+0CF0h+var_CB0]
0x1800024aa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800024b0  jmp     loc_180002587
0x1800024b5  lea     rcx, [rbp+0CF0h+var_C78]
0x1800024b9  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800024bf  lea     rcx, [rbp+0CF0h+var_CB0]
0x1800024c3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800024c9  mov     rcx, [rsp+0DF0h+var_DA0]
0x1800024ce  test    rcx, rcx
0x1800024d1  jz      short loc_1800024EA
0x1800024d3  mov     rax, [rcx]
0x1800024d6  lea     r8, [rsp+0DF0h+var_DA8]
0x1800024db  lea     rdx, IID_IAppHostConfigException
0x1800024e2  mov     rax, [rax]
0x1800024e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024ea  mov     rax, [rbx]
0x1800024ed  mov     rcx, rbx
0x1800024f0  mov     rax, [rax+20h]
0x1800024f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f9  mov     rcx, rax
0x1800024fc  mov     rdx, [rax]
0x1800024ff  mov     rax, [rdx+8]
0x180002503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002508  mov     rcx, rbx
0x18000250b  mov     [rax+218h], r14w
0x180002513  mov     rax, [rbx]
0x180002516  mov     rax, [rax+20h]
0x18000251a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000251f  mov     r10, rax
0x180002522  mov     [rsp+0DF0h+var_DC0], r14d
0x180002527  mov     edx, 1F4h
0x18000252c  lea     r8, aInternalServer; "Internal Server Error"
0x180002533  mov     r9d, 13h
0x180002539  mov     rcx, [rax]
0x18000253c  mov     rax, [rcx+18h]
0x180002540  mov     rcx, [rsp+0DF0h+var_DA8]
0x180002545  mov     [rsp+0DF0h+var_DC8], rcx
0x18000254a  mov     rcx, r10
0x18000254d  mov     dword ptr [rsp+0DF0h+var_DD0], edi
0x180002551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002556  mov     rcx, [rsp+0DF0h+var_DA8]
0x18000255b  test    rcx, rcx
0x18000255e  jz      short loc_180002571
0x180002560  mov     rax, [rcx]
0x180002563  mov     rax, [rax+10h]
0x180002567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000256c  mov     [rsp+0DF0h+var_DA8], r14
0x180002571  mov     rcx, [rsp+0DF0h+var_DA0]
0x180002576  test    rcx, rcx
0x180002579  jz      short loc_180002587
0x18000257b  mov     rax, [rcx]
0x18000257e  mov     rax, [rax+10h]
0x180002582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002587  mov     eax, esi
0x180002589  mov     rcx, [rbp+0CF0h+var_40]
0x180002590  xor     rcx, rsp; StackCookie
0x180002593  call    __security_check_cookie
0x180002598  add     rsp, 0DC8h
0x18000259f  pop     r14
0x1800025a1  pop     r12
0x1800025a3  pop     rdi
0x1800025a4  pop     rsi
0x1800025a5  pop     rbx
0x1800025a6  pop     rbp
0x1800025a7  retn
```
