# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x18000259c`
- end: `0x1800028d3`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `823`
- prototype: `__int64 __fastcall(int, __int64, struct IHttpContext *, void (__fastcall ***)(_QWORD, __int64), __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001ce0`
- `0x180001e80`

## callees

- `0x180001938`
- `0x18000259c`
- `0x18000337c`
- `0x180004678`
- `0x1800065c8`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall RequestDoWork(
        int a1,
        __int64 a2,
        struct IHttpContext *a3,
        void (__fastcall ***a4)(_QWORD, __int64),
        __int64 a5)
{
  int v8; // esi
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  W3_CGI_HANDLER *v12; // rax
  W3_CGI_HANDLER *v13; // rsi
  int (__fastcall ***v14)(_QWORD, GUID **); // rax
  int (__fastcall **v15)(_QWORD, GUID **); // rcx
  __int64 *v16; // rcx
  __int64 v17; // rax
  void (__fastcall *v18)(__int64 *, _QWORD *); // rax
  __int64 v19; // rax
  int v20; // ebx
  __int64 (__fastcall ***v21)(_QWORD, void *); // rax
  __int64 v22; // rdi
  unsigned int v23; // ebx
  unsigned int v24; // eax
  __int64 v25; // [rsp+40h] [rbp-71h] BYREF
  struct INativeSectionException *v26; // [rsp+48h] [rbp-69h] BYREF
  GUID *v27; // [rsp+50h] [rbp-61h] BYREF
  __int128 v28; // [rsp+58h] [rbp-59h]
  int v29; // [rsp+68h] [rbp-49h]
  __int64 v30; // [rsp+70h] [rbp-41h]
  _QWORD v31[6]; // [rsp+80h] [rbp-31h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-1h]
  int v33; // [rsp+C0h] [rbp+Fh]
  int v34; // [rsp+C4h] [rbp+13h]
  __int64 v35; // [rsp+C8h] [rbp+17h]
  GUID **v36; // [rsp+D0h] [rbp+1Fh]

  v26 = 0;
  v25 = 0;
  if ( a1 != 128 )
    return 0;
  if ( a5 )
  {
    v21 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
    v22 = (**v21)(v21, g_pCgiHandlerContext);
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
    v24 = (**(__int64 (__fastcall ***)(__int64))a5)(a5);
    return W3_CGI_HANDLER::OnCompletion(v22, v24, v23);
  }
  else
  {
    v8 = CGI_META_STORED_CONTEXT::SetupParsedMetadata(a3, &v26);
    if ( v8 < 0 )
    {
      if ( v26 )
        (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v26)(
          v26,
          &IID_IAppHostConfigException,
          &v25);
      v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9) + 536) = 0;
      v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v10 + 24LL))(
        v10,
        500,
        "Internal Server Error",
        19,
        v8,
        v25,
        0);
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v25 = 0;
      }
      if ( v26 )
      {
        (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v26 + 16LL))(v26);
        v26 = 0;
      }
      v11 = (unsigned int)v8;
      goto LABEL_12;
    }
    v12 = (W3_CGI_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a3 + 144LL))(
                              a3,
                              8408);
    if ( !v12 || (v13 = W3_CGI_HANDLER::W3_CGI_HANDLER(v12, a3)) == 0 )
    {
      v11 = 2147942408LL;
LABEL_12:
      (**a4)(a4, v11);
      return 2;
    }
    v14 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
    v27 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v15 = *v14;
    v28 = 0;
    if ( (*v15)(v14, &v27) >= 0 && DWORD2(v28) && ((_DWORD)v28 == 32 || (v28 & 0x20) != 0) )
    {
      v16 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 272LL))(a3);
      v31[1] = 32;
      v31[3] = 1;
      v31[5] = 1;
      v31[2] = &`IISCGIEvents::GetAreaGuid'::`2'::AreaGuid;
      v34 = 1;
      v31[4] = L"CGI_START";
      v35 = 1;
      v27 = (GUID *)L"ContextId";
      v36 = &v27;
      v17 = *v16;
      v31[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v32 = 0;
      v33 = 0;
      v18 = *(void (__fastcall **)(__int64 *, _QWORD *))(v17 + 16);
      LODWORD(v28) = 72;
      *((_QWORD *)&v28 + 1) = 0;
      v29 = 16;
      v30 = 0;
      v18(v16, v31);
    }
    v19 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
    v20 = (*(__int64 (__fastcall **)(__int64, W3_CGI_HANDLER *, void *))(*(_QWORD *)v19 + 8LL))(
            v19,
            v13,
            g_pCgiHandlerContext);
    if ( v20 < 0 )
    {
      (**(void (__fastcall ***)(W3_CGI_HANDLER *))v13)(v13);
      (**a4)(a4, (unsigned int)v20);
      return 2;
    }
    return W3_CGI_HANDLER::DoWork((__int64)v13);
  }
}

```

## disassembly

```asm
0x18000259c  push    rbp
0x18000259e  push    rbx
0x18000259f  push    rsi
0x1800025a0  push    rdi
0x1800025a1  push    r15
0x1800025a3  lea     rbp, [rsp-2Fh]
0x1800025a8  sub     rsp, 0E0h
0x1800025af  mov     [rbp+4Fh+var_B8], 0
0x1800025b7  mov     rdi, r9
0x1800025ba  mov     [rbp+4Fh+var_C0], 0
0x1800025c2  mov     rbx, r8
0x1800025c5  cmp     ecx, 80h
0x1800025cb  jz      short loc_1800025D4
0x1800025cd  xor     eax, eax
0x1800025cf  jmp     loc_1800028C5
0x1800025d4  mov     rsi, [rbp+4Fh+arg_20]
0x1800025d8  mov     rcx, rbx; struct IHttpContext *
0x1800025db  test    rsi, rsi
0x1800025de  jnz     loc_180002872
0x1800025e4  lea     rdx, [rbp+4Fh+var_B8]; struct INativeSectionException **
0x1800025e8  call    ?SetupParsedMetadata@CGI_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; CGI_META_STORED_CONTEXT::SetupParsedMetadata(IHttpContext *,INativeSectionException * *)
0x1800025ed  mov     esi, eax
0x1800025ef  test    eax, eax
0x1800025f1  jns     loc_1800026DC
0x1800025f7  mov     rcx, [rbp+4Fh+var_B8]
0x1800025fb  test    rcx, rcx
0x1800025fe  jz      short loc_180002616
0x180002600  mov     rdx, [rcx]
0x180002603  lea     r8, [rbp+4Fh+var_C0]
0x180002607  mov     rax, [rdx]
0x18000260a  lea     rdx, IID_IAppHostConfigException
0x180002611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002616  mov     rax, [rbx]
0x180002619  mov     rcx, rbx
0x18000261c  mov     rax, [rax+20h]
0x180002620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002625  mov     rdx, rax
0x180002628  mov     rcx, [rax]
0x18000262b  mov     rax, [rcx+8]
0x18000262f  mov     rcx, rdx
0x180002632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002637  xor     ecx, ecx
0x180002639  mov     [rax+218h], cx
0x180002640  mov     rcx, rbx
0x180002643  mov     rax, [rbx]
0x180002646  mov     rax, [rax+20h]
0x18000264a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000264f  mov     r10, rax
0x180002652  mov     [rsp+100h+var_D0], 0
0x18000265a  mov     edx, 1F4h
0x18000265f  lea     r8, aInternalServer; "Internal Server Error"
0x180002666  mov     r9d, 13h
0x18000266c  mov     rcx, [rax]
0x18000266f  mov     rax, [rcx+18h]
0x180002673  mov     rcx, [rbp+4Fh+var_C0]
0x180002677  mov     [rsp+100h+var_D8], rcx
0x18000267c  mov     rcx, r10
0x18000267f  mov     [rsp+100h+var_E0], esi
0x180002683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002688  mov     rcx, [rbp+4Fh+var_C0]
0x18000268c  test    rcx, rcx
0x18000268f  jz      short loc_1800026A5
0x180002691  mov     rax, [rcx]
0x180002694  mov     rax, [rax+10h]
0x180002698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000269d  mov     [rbp+4Fh+var_C0], 0
0x1800026a5  mov     rcx, [rbp+4Fh+var_B8]
0x1800026a9  test    rcx, rcx
0x1800026ac  jz      short loc_1800026C2
0x1800026ae  mov     rax, [rcx]
0x1800026b1  mov     rax, [rax+10h]
0x1800026b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ba  mov     [rbp+4Fh+var_B8], 0
0x1800026c2  mov     edx, esi
0x1800026c4  mov     rax, [rdi]
0x1800026c7  mov     rax, [rax]
0x1800026ca  mov     rcx, rdi
0x1800026cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026d2  mov     eax, 2
0x1800026d7  jmp     loc_1800028C5
0x1800026dc  mov     rax, [rbx]
0x1800026df  mov     edx, 20D8h
0x1800026e4  mov     rcx, rbx
0x1800026e7  mov     rax, [rax+90h]
0x1800026ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026f3  test    rax, rax
0x1800026f6  jz      loc_180002868
0x1800026fc  mov     rdx, rbx; struct IHttpContext *
0x1800026ff  mov     rcx, rax; this
0x180002702  call    ??0W3_CGI_HANDLER@@QEAA@PEAVIHttpContext@@@Z; W3_CGI_HANDLER::W3_CGI_HANDLER(IHttpContext *)
0x180002707  mov     rsi, rax
0x18000270a  test    rax, rax
0x18000270d  jz      loc_180002868
0x180002713  mov     rcx, [rbx]
0x180002716  mov     rax, [rcx+110h]
0x18000271d  mov     rcx, rbx
0x180002720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002725  mov     r8, rax
0x180002728  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18000272f  xorps   xmm0, xmm0
0x180002732  mov     [rbp+4Fh+var_B0], r15
0x180002736  lea     rdx, [rbp+4Fh+var_B0]
0x18000273a  mov     rcx, [rax]
0x18000273d  movdqu  [rbp+4Fh+var_A8], xmm0
0x180002742  mov     rax, [rcx]
0x180002745  mov     rcx, r8
0x180002748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000274d  test    eax, eax
0x18000274f  js      loc_180002812
0x180002755  cmp     dword ptr [rbp+4Fh+var_A8+8], 0
0x180002759  jz      loc_180002812
0x18000275f  cmp     dword ptr [rbp+4Fh+var_A8], 20h ; ' '
0x180002763  jz      short loc_18000276F
0x180002765  test    byte ptr [rbp+4Fh+var_A8], 20h
0x180002769  jz      loc_180002812
0x18000276f  mov     rax, [rbx]
0x180002772  mov     rcx, rbx
0x180002775  mov     rax, [rax+110h]
0x18000277c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002781  mov     rcx, rax
0x180002784  mov     [rbp+4Fh+var_78], 20h ; ' '
0x18000278c  mov     edx, 1
0x180002791  mov     [rbp+4Fh+var_68], 1
0x180002799  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800027a0  mov     [rbp+4Fh+var_58], rdx
0x1800027a4  mov     [rbp+4Fh+var_70], rax
0x1800027a8  xorps   xmm0, xmm0
0x1800027ab  lea     rax, aCgiStart; "CGI_START"
0x1800027b2  mov     [rbp+4Fh+var_3C], edx
0x1800027b5  mov     [rbp+4Fh+var_60], rax
0x1800027b9  lea     rdx, [rbp+4Fh+var_80]
0x1800027bd  lea     rax, aContextid; "ContextId"
0x1800027c4  mov     [rbp+4Fh+var_38], 1
0x1800027cc  mov     [rbp+4Fh+var_B0], rax
0x1800027d0  lea     rax, [rbp+4Fh+var_B0]
0x1800027d4  mov     [rbp+4Fh+var_30], rax
0x1800027d8  mov     rax, [rcx]
0x1800027db  mov     [rbp+4Fh+var_80], r15
0x1800027df  movdqa  [rbp+4Fh+var_50], xmm0
0x1800027e4  mov     [rbp+4Fh+var_40], 0
0x1800027eb  mov     rax, [rax+10h]
0x1800027ef  mov     dword ptr [rbp+4Fh+var_A8], 48h ; 'H'
0x1800027f6  mov     qword ptr [rbp+4Fh+var_A8+8], 0
0x1800027fe  mov     [rbp+4Fh+var_98], 10h
0x180002805  mov     [rbp+4Fh+var_90], 0
0x18000280d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002812  mov     rax, [rbx]
0x180002815  mov     rcx, rbx
0x180002818  mov     rax, [rax+38h]
0x18000281c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002821  mov     r8, cs:?g_pCgiHandlerContext@@3PEAXEA; void * g_pCgiHandlerContext
0x180002828  mov     r9, rax
0x18000282b  mov     rdx, rsi
0x18000282e  mov     rcx, [rax]
0x180002831  mov     rax, [rcx+8]
0x180002835  mov     rcx, r9
0x180002838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000283d  mov     ebx, eax
0x18000283f  test    eax, eax
0x180002841  jns     short loc_18000285E
0x180002843  mov     rcx, [rsi]
0x180002846  mov     rax, [rcx]
0x180002849  mov     rcx, rsi
0x18000284c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002851  mov     rcx, [rdi]
0x180002854  mov     edx, ebx
0x180002856  mov     rax, [rcx]
0x180002859  jmp     loc_1800026CA
0x18000285e  mov     rcx, rsi
0x180002861  call    ?DoWork@W3_CGI_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; W3_CGI_HANDLER::DoWork(void)
0x180002866  jmp     short loc_1800028C5
0x180002868  mov     edx, 80070008h
0x18000286d  jmp     loc_1800026C4
0x180002872  mov     rax, [r8]
0x180002875  mov     rax, [rax+38h]
0x180002879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000287e  mov     rdx, cs:?g_pCgiHandlerContext@@3PEAXEA; void * g_pCgiHandlerContext
0x180002885  mov     r8, rax
0x180002888  mov     rcx, [rax]
0x18000288b  mov     rax, [rcx]
0x18000288e  mov     rcx, r8
0x180002891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002896  mov     rdx, [rsi]
0x180002899  mov     rdi, rax
0x18000289c  mov     rcx, rsi
0x18000289f  mov     rax, [rdx+8]
0x1800028a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a8  mov     rdx, [rsi]
0x1800028ab  mov     ebx, eax
0x1800028ad  mov     rcx, rsi
0x1800028b0  mov     rax, [rdx]
0x1800028b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b8  mov     r8d, ebx
0x1800028bb  mov     edx, eax
0x1800028bd  mov     rcx, rdi
0x1800028c0  call    ?OnCompletion@W3_CGI_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KJ@Z; W3_CGI_HANDLER::OnCompletion(ulong,long)
0x1800028c5  add     rsp, 0E0h
0x1800028cc  pop     r15
0x1800028ce  pop     rdi
0x1800028cf  pop     rsi
0x1800028d0  pop     rbx
0x1800028d1  pop     rbp
0x1800028d2  retn
```
