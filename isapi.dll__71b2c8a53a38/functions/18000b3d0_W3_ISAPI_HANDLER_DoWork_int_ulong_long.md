# W3_ISAPI_HANDLER::DoWork(int,ulong,long)

- ea: `0x18000b3d0`
- end: `0x18000b827`
- name: `?DoWork@W3_ISAPI_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@HKJ@Z`
- size: `1111`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002d9c`

## callees

- `0x1800038ec`
- `0x18000b30c`
- `0x18000b360`
- `0x18000b3d0`
- `0x18000b8f0`
- `0x18000bd8c`
- `0x18000be78`
- `0x18000bf64`
- `0x18000c15c`
- `0x18000c2b4`
- `0x18000c7d8`
- `0x1800107c8`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000b44c`
- `iisutil!PuDbgPrint` at `0x18000b641`
- `iisutil!PuDbgPrint` at `0x18000b70e`
- `iisutil!PuDbgPrint` at `0x18000b44c`
- `iisutil!PuDbgPrint` at `0x18000b641`
- `iisutil!PuDbgPrint` at `0x18000b70e`

## string_xrefs

- `0x18000b445`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_handler.cxx`
- `0x18000b63a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_handler.cxx`
- `0x18000b6f0`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_handler.cxx`
- `0x18000b61d`: `Attempt to process ISAPI request failed.  Error 0x%08x.\n`

## pseudocode

```c
__int64 __fastcall W3_ISAPI_HANDLER::DoWork(__int64 a1, int a2, unsigned int a3, unsigned int a4)
{
  __int64 v5; // rcx
  __int64 v9; // rax
  int v10; // r8d
  __int64 v11; // r15
  int *v12; // rdx
  __int64 v14; // rax
  struct IHttpTraceContext *v15; // rax
  const struct _GUID *v16; // rdx
  struct IHttpContext *v17; // rcx
  int ParsedData; // ebx
  __int64 v19; // rcx
  __int64 v20; // rax
  struct IHttpTraceContext *v21; // rax
  const struct _GUID *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  void (__fastcall *v26)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD); // rax
  struct IHttpServer *v27; // rcx
  struct IIsapiCore **v28; // r14
  struct IHttpTraceContext *v29; // rax
  const unsigned __int16 *v30; // rbx
  struct IHttpTraceContext *v31; // rax
  const struct _GUID *v32; // rdx
  struct IIsapiCore *v33; // rcx
  struct ISAPI_META_CONTEXT *v34; // [rsp+70h] [rbp+8h] BYREF
  int v35; // [rsp+78h] [rbp+10h] BYREF

  v5 = *(_QWORD *)(a1 + 8);
  v35 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  v10 = g_dwDebugFlags;
  v11 = v9;
  LOBYTE(v12) = (g_dwDebugFlags & 3) != 0;
  if ( ((unsigned __int8)v12 & ((g_dwDebugFlags & 0x20000000) != 0)) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_handler.cxx",
      78,
      "W3_ISAPI_HANDLER::DoWork",
      "IsapiDoWork called for new request.\r\n");
  if ( a2 )
  {
    if ( *(_DWORD *)(a1 + 40) >= 2u )
      return W3_ISAPI_HANDLER::OnCompletion(a1, a3, a4);
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v14, 0, 0) )
    {
      v15 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
      IISGeneralEvents::GENERAL_ISAPI_HANDLER::RaiseEvent(v15, v16);
    }
    v17 = *(struct IHttpContext **)(a1 + 8);
    v34 = 0;
    ParsedData = ISAPI_META_CONTEXT::GetParsedData(v17, &v34);
    if ( ParsedData < 0 )
      goto LABEL_21;
    if ( (*((_DWORD *)v34 + 3) & 0x204) == 0 )
    {
      *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) + 536) = 0;
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v11 + 24LL))(
        v11,
        403,
        "Forbidden",
        1,
        -2147024891,
        0,
        0);
LABEL_39:
      W3_ISAPI_HANDLER::SetRequestHandledAndTrace((W3_ISAPI_HANDLER *)a1);
      return 2;
    }
  }
  ParsedData = W3_ISAPI_HANDLER::InitCoreData(
                 (W3_ISAPI_HANDLER *)a1,
                 v12,
                 v10,
                 a3,
                 a4,
                 (struct ISAPI_META_CONTEXT *)&v35);
  if ( ParsedData < 0 )
  {
LABEL_21:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_handler.cxx",
        290,
        "W3_ISAPI_HANDLER::DoWork",
        "Attempt to process ISAPI request failed.  Error 0x%08x.\r\n",
        ParsedData);
    v25 = *(_QWORD *)(a1 + 16);
    *(_DWORD *)(a1 + 40) = 4;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 248LL))(v25);
    v26 = *(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v11 + 24LL);
    if ( ParsedData == -2147023901 )
      v26(v11, 400, "Bad Request", 0, -2147023901, 0, 0);
    else
      v26(v11, 500, "Internal Server Error", 0, ParsedData, 0, 0);
    goto LABEL_39;
  }
  if ( v35 )
    return 1;
  v19 = *(_QWORD *)(a1 + 8);
  LODWORD(v34) = 0;
  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 272LL))(v19);
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v20, 0, 0) )
  {
    v21 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
    IISISAPIEvents::ISAPI_START::RaiseEvent(v21, v22);
  }
  v23 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 8) + 144LL))(*(_QWORD *)(a1 + 8), 72);
  if ( v23 )
  {
    v24 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)v23 = &ISAPI_REQUEST::`vftable';
    *(_QWORD *)(v23 + 24) = v24;
    *(_DWORD *)(v23 + 8) = 1230197329;
    *(_DWORD *)(v23 + 12) = 1;
    *(_QWORD *)(v23 + 16) = 0;
    *(_QWORD *)(v23 + 32) = a1;
    *(_QWORD *)(v23 + 40) = 0;
    *(_DWORD *)(v23 + 48) = 0;
    *(_QWORD *)(v23 + 56) = 0;
    *(_DWORD *)(v23 + 64) = 0;
  }
  else
  {
    v23 = 0;
  }
  *(_QWORD *)(a1 + 16) = v23;
  if ( !v23 )
  {
    ParsedData = -2147024882;
    goto LABEL_21;
  }
  ParsedData = ISAPI_REQUEST::Create((ISAPI_REQUEST *)v23);
  if ( ParsedData < 0 )
    goto LABEL_21;
  v27 = g_pGlobalInfo;
  *(_DWORD *)(a1 + 40) = 2;
  (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v27 + 24LL))(v27);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x20000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_handler.cxx",
      209,
      "W3_ISAPI_HANDLER::DoWork",
      "Processing ISAPI_REQUEST %p OOP.\r\n",
      *(const void **)(a1 + 16));
  v28 = (struct IIsapiCore **)(a1 + 16);
  v29 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
  if ( (unsigned int)WWWIsapiExtensionTraceProvider::CheckTracingEnabled(v29, 0) )
  {
    v30 = *(const unsigned __int16 **)(*(_QWORD *)(a1 + 24) + 24LL);
    v31 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 272LL))(*(_QWORD *)(a1 + 8));
    W3IsapiEvents::CALL_ISAPI_EXTENSION::RaiseEvent(v31, v32, v30);
  }
  else
  {
    v28 = (struct IIsapiCore **)(a1 + 16);
  }
  ParsedData = ProcessIsapiRequest(
                 *v28,
                 *(struct ISAPI_CORE_DATA **)(a1 + 24),
                 *(struct ISAPI_DLL **)(a1 + 32),
                 (unsigned int *)&v34);
  (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
  if ( ParsedData < 0 )
  {
    *(_DWORD *)(a1 + 40) = 3;
    goto LABEL_21;
  }
  v33 = *v28;
  if ( (_DWORD)v34 == 3 )
  {
    (*(void (__fastcall **)(struct IIsapiCore *))(*(_QWORD *)v33 + 248LL))(v33);
    return 1;
  }
  *(_DWORD *)(a1 + 40) = 4;
  (*(void (__fastcall **)(struct IIsapiCore *))(*(_QWORD *)v33 + 248LL))(v33);
  W3_ISAPI_HANDLER::SetRequestHandledAndTrace((W3_ISAPI_HANDLER *)a1);
  return 0;
}

```

## disassembly

```asm
0x18000b3d0  mov     [rsp+arg_10], rbx
0x18000b3d5  mov     [rsp+arg_18], rbp
0x18000b3da  push    rsi
0x18000b3db  push    rdi
0x18000b3dc  push    r12
0x18000b3de  push    r14
0x18000b3e0  push    r15
0x18000b3e2  sub     rsp, 40h
0x18000b3e6  mov     rdi, rcx
0x18000b3e9  xor     r12d, r12d
0x18000b3ec  mov     rcx, [rcx+8]
0x18000b3f0  mov     esi, r9d
0x18000b3f3  mov     [rsp+68h+arg_8], r12d
0x18000b3f8  mov     ebp, r8d
0x18000b3fb  mov     ebx, edx
0x18000b3fd  mov     rax, [rcx]
0x18000b400  mov     rax, [rax+20h]
0x18000b404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b409  mov     r8d, cs:g_dwDebugFlags
0x18000b410  mov     r15, rax
0x18000b413  test    r8b, 3
0x18000b417  setnz   dl
0x18000b41a  bt      r8d, 1Dh
0x18000b41f  setb    cl
0x18000b422  test    cl, dl
0x18000b424  jz      short loc_18000B452
0x18000b426  mov     rcx, cs:g_pDebug
0x18000b42d  lea     rax, aIsapidoworkCal; "IsapiDoWork called for new request.\r\n"
0x18000b434  lea     r9, aW3IsapiHandler_1; "W3_ISAPI_HANDLER::DoWork"
0x18000b43b  mov     qword ptr [rsp+68h+var_48], rax
0x18000b440  lea     r8d, [r12+4Eh]
0x18000b445  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b44c  call    cs:__imp_PuDbgPrint
0x18000b452  test    ebx, ebx
0x18000b454  jz      short loc_18000B472
0x18000b456  cmp     dword ptr [rdi+28h], 2
0x18000b45a  jb      loc_18000B523
0x18000b460  mov     r8d, esi
0x18000b463  mov     edx, ebp
0x18000b465  mov     rcx, rdi
0x18000b468  call    ?OnCompletion@W3_ISAPI_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KJ@Z; W3_ISAPI_HANDLER::OnCompletion(ulong,long)
0x18000b46d  jmp     loc_18000B80E
0x18000b472  mov     rcx, [rdi+8]
0x18000b476  mov     rax, [rcx]
0x18000b479  mov     rax, [rax+110h]
0x18000b480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b485  xor     r8d, r8d
0x18000b488  xor     edx, edx
0x18000b48a  mov     rcx, rax
0x18000b48d  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000b492  test    eax, eax
0x18000b494  jz      short loc_18000B4B1
0x18000b496  mov     rcx, [rdi+8]
0x18000b49a  mov     rax, [rcx]
0x18000b49d  mov     rax, [rax+110h]
0x18000b4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4a9  mov     rcx, rax; struct IHttpTraceContext *
0x18000b4ac  call    ?RaiseEvent@GENERAL_ISAPI_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISGeneralEvents::GENERAL_ISAPI_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000b4b1  mov     rcx, [rdi+8]; struct IHttpContext *
0x18000b4b5  lea     rdx, [rsp+68h+arg_0]; struct ISAPI_META_CONTEXT **
0x18000b4ba  mov     [rsp+68h+arg_0], r12
0x18000b4bf  call    ?GetParsedData@ISAPI_META_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@@Z; ISAPI_META_CONTEXT::GetParsedData(IHttpContext *,ISAPI_META_CONTEXT * *)
0x18000b4c4  mov     ebx, eax
0x18000b4c6  test    eax, eax
0x18000b4c8  js      loc_18000B60D
0x18000b4ce  mov     rax, [rsp+68h+arg_0]
0x18000b4d3  test    dword ptr [rax+0Ch], 204h
0x18000b4da  jnz     short loc_18000B523
0x18000b4dc  mov     rax, [r15]
0x18000b4df  mov     rcx, r15
0x18000b4e2  mov     rax, [rax+8]
0x18000b4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4eb  mov     [rsp+68h+var_38], r12d
0x18000b4f0  lea     r8, aForbidden; "Forbidden"
0x18000b4f7  mov     [rsp+68h+var_40], r12
0x18000b4fc  mov     edx, 193h
0x18000b501  mov     r9d, 1
0x18000b507  mov     [rsp+68h+var_48], 80070005h
0x18000b50f  mov     [rax+218h], r12w
0x18000b517  mov     rax, [r15]
0x18000b51a  mov     rax, [rax+18h]
0x18000b51e  jmp     loc_18000B7F9
0x18000b523  lea     rax, [rsp+68h+arg_8]
0x18000b528  mov     r9d, ebp; unsigned int
0x18000b52b  mov     [rsp+68h+var_40], rax; struct ISAPI_META_CONTEXT *
0x18000b530  mov     rcx, rdi; this
0x18000b533  mov     [rsp+68h+var_48], esi; int
0x18000b537  call    ?InitCoreData@W3_ISAPI_HANDLER@@QEAAJPEAHHKJ0@Z; W3_ISAPI_HANDLER::InitCoreData(int *,int,ulong,long,int *)
0x18000b53c  mov     ebx, eax
0x18000b53e  test    eax, eax
0x18000b540  js      loc_18000B60D
0x18000b546  cmp     [rsp+68h+arg_8], r12d
0x18000b54b  jz      short loc_18000B557
0x18000b54d  mov     eax, 1
0x18000b552  jmp     loc_18000B80E
0x18000b557  mov     rcx, [rdi+8]
0x18000b55b  mov     dword ptr [rsp+68h+arg_0], r12d
0x18000b560  mov     rax, [rcx]
0x18000b563  mov     rax, [rax+110h]
0x18000b56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b56f  xor     r8d, r8d
0x18000b572  xor     edx, edx
0x18000b574  mov     rcx, rax
0x18000b577  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000b57c  test    eax, eax
0x18000b57e  jz      short loc_18000B59B
0x18000b580  mov     rcx, [rdi+8]
0x18000b584  mov     rax, [rcx]
0x18000b587  mov     rax, [rax+110h]
0x18000b58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b593  mov     rcx, rax; struct IHttpTraceContext *
0x18000b596  call    ?RaiseEvent@ISAPI_START@IISISAPIEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISISAPIEvents::ISAPI_START::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x18000b59b  mov     rcx, [rdi+8]
0x18000b59f  mov     edx, 48h ; 'H'
0x18000b5a4  mov     rax, [rcx]
0x18000b5a7  mov     rax, [rax+90h]
0x18000b5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b3  mov     rcx, rax
0x18000b5b6  test    rax, rax
0x18000b5b9  jz      short loc_18000B5F5
0x18000b5bb  mov     rax, [rdi+8]
0x18000b5bf  lea     rdx, ??_7ISAPI_REQUEST@@6B@; const ISAPI_REQUEST::`vftable'
0x18000b5c6  mov     [rcx], rdx
0x18000b5c9  mov     [rcx+18h], rax
0x18000b5cd  mov     dword ptr [rcx+8], 49535251h
0x18000b5d4  mov     dword ptr [rcx+0Ch], 1
0x18000b5db  mov     [rcx+10h], r12
0x18000b5df  mov     [rcx+20h], rdi
0x18000b5e3  mov     [rcx+28h], r12
0x18000b5e7  mov     [rcx+30h], r12d
0x18000b5eb  mov     [rcx+38h], r12
0x18000b5ef  mov     [rcx+40h], r12d
0x18000b5f3  jmp     short loc_18000B5F8
0x18000b5f5  mov     rcx, r12; this
0x18000b5f8  lea     rsi, [rdi+10h]
0x18000b5fc  mov     [rsi], rcx
0x18000b5ff  test    rcx, rcx
0x18000b602  jnz     loc_18000B69C
0x18000b608  mov     ebx, 8007000Eh
0x18000b60d  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b614  jz      short loc_18000B647
0x18000b616  mov     rcx, cs:g_pDebug
0x18000b61d  lea     rax, aAttemptToProce; "Attempt to process ISAPI request failed"...
0x18000b624  mov     dword ptr [rsp+68h+var_40], ebx
0x18000b628  lea     r9, aW3IsapiHandler_1; "W3_ISAPI_HANDLER::DoWork"
0x18000b62f  mov     r8d, 122h
0x18000b635  mov     qword ptr [rsp+68h+var_48], rax
0x18000b63a  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b641  call    cs:__imp_PuDbgPrint
0x18000b647  mov     rcx, [rdi+10h]
0x18000b64b  mov     dword ptr [rdi+28h], 4
0x18000b652  test    rcx, rcx
0x18000b655  jz      short loc_18000B666
0x18000b657  mov     rax, [rcx]
0x18000b65a  mov     rax, [rax+0F8h]
0x18000b661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b666  mov     rax, [r15]
0x18000b669  mov     ecx, 800703E3h
0x18000b66e  xor     r9d, r9d
0x18000b671  mov     [rsp+68h+var_38], r12d
0x18000b676  mov     [rsp+68h+var_40], r12
0x18000b67b  mov     rax, [rax+18h]
0x18000b67f  cmp     ebx, ecx
0x18000b681  jnz     loc_18000B7E9
0x18000b687  mov     edx, 190h
0x18000b68c  mov     [rsp+68h+var_48], ecx
0x18000b690  lea     r8, aBadRequest; "Bad Request"
0x18000b697  jmp     loc_18000B7F9
0x18000b69c  call    ?Create@ISAPI_REQUEST@@QEAAJXZ; ISAPI_REQUEST::Create(void)
0x18000b6a1  mov     ebx, eax
0x18000b6a3  test    eax, eax
0x18000b6a5  js      loc_18000B60D
0x18000b6ab  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000b6b2  lea     rbp, [rdi+28h]
0x18000b6b6  mov     dword ptr [rbp+0], 2
0x18000b6bd  mov     rax, [rcx]
0x18000b6c0  mov     rax, [rax+18h]
0x18000b6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c9  mov     eax, cs:g_dwDebugFlags
0x18000b6cf  test    al, 3
0x18000b6d1  setnz   cl
0x18000b6d4  bt      eax, 1Dh
0x18000b6d8  setb    al
0x18000b6db  test    al, cl
0x18000b6dd  jz      short loc_18000B71A
0x18000b6df  mov     rax, [rsi]
0x18000b6e2  lea     r9, aW3IsapiHandler_1; "W3_ISAPI_HANDLER::DoWork"
0x18000b6e9  mov     rcx, cs:g_pDebug
0x18000b6f0  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b6f7  mov     [rsp+68h+var_40], rax
0x18000b6fc  mov     r8d, 0D1h
0x18000b702  lea     rax, aProcessingIsap; "Processing ISAPI_REQUEST %p OOP.\r\n"
0x18000b709  mov     qword ptr [rsp+68h+var_48], rax
0x18000b70e  call    cs:__imp_PuDbgPrint
0x18000b714  lea     r14, [rdi+10h]
0x18000b718  jmp     short loc_18000B71D
0x18000b71a  mov     r14, rsi
0x18000b71d  mov     rcx, [rdi+8]
0x18000b721  mov     rax, [rcx]
0x18000b724  mov     rax, [rax+110h]
0x18000b72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b730  xor     edx, edx; unsigned int
0x18000b732  mov     rcx, rax; struct IHttpTraceContext *
0x18000b735  call    ?CheckTracingEnabled@WWWIsapiExtensionTraceProvider@@SAHPEAVIHttpTraceContext@@K@Z; WWWIsapiExtensionTraceProvider::CheckTracingEnabled(IHttpTraceContext *,ulong)
0x18000b73a  test    eax, eax
0x18000b73c  jz      short loc_18000B76A
0x18000b73e  mov     rax, [rdi+18h]
0x18000b742  mov     rcx, [rdi+8]
0x18000b746  mov     rbx, [rax+18h]
0x18000b74a  mov     rax, [rcx]
0x18000b74d  mov     rax, [rax+110h]
0x18000b754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b759  mov     r8, rbx; unsigned __int16 *
0x18000b75c  mov     rcx, rax; struct IHttpTraceContext *
0x18000b75f  call    ?RaiseEvent@CALL_ISAPI_EXTENSION@W3IsapiEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; W3IsapiEvents::CALL_ISAPI_EXTENSION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x18000b764  lea     rsi, [rdi+28h]
0x18000b768  jmp     short loc_18000B770
0x18000b76a  mov     r14, rsi
0x18000b76d  mov     rsi, rbp
0x18000b770  mov     r8, [rdi+20h]; struct ISAPI_DLL *
0x18000b774  lea     r9, [rsp+68h+arg_0]; unsigned int *
0x18000b779  mov     rdx, [rdi+18h]; struct ISAPI_CORE_DATA *
0x18000b77d  mov     rcx, [r14]; struct IIsapiCore *
0x18000b780  call    ?ProcessIsapiRequest@@YAJPEAVIIsapiCore@@PEAUISAPI_CORE_DATA@@PEAVISAPI_DLL@@PEAK@Z; ProcessIsapiRequest(IIsapiCore *,ISAPI_CORE_DATA *,ISAPI_DLL *,ulong *)
0x18000b785  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000b78c  mov     ebx, eax
0x18000b78e  mov     rax, [rcx]
0x18000b791  mov     rax, [rax+20h]
0x18000b795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b79a  test    ebx, ebx
0x18000b79c  jns     short loc_18000B7AA
0x18000b79e  mov     dword ptr [rbp+0], 3
0x18000b7a5  jmp     loc_18000B60D
0x18000b7aa  cmp     dword ptr [rsp+68h+arg_0], 3
0x18000b7af  mov     rcx, [r14]
0x18000b7b2  jz      short loc_18000B7D5
0x18000b7b4  mov     dword ptr [rsi], 4
0x18000b7ba  mov     rax, [rcx]
0x18000b7bd  mov     rax, [rax+0F8h]
0x18000b7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7c9  mov     rcx, rdi; this
0x18000b7cc  call    ?SetRequestHandledAndTrace@W3_ISAPI_HANDLER@@AEAAJXZ; W3_ISAPI_HANDLER::SetRequestHandledAndTrace(void)
0x18000b7d1  xor     eax, eax
0x18000b7d3  jmp     short loc_18000B80E
0x18000b7d5  mov     rax, [rcx]
0x18000b7d8  mov     rax, [rax+0F8h]
0x18000b7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7e4  jmp     loc_18000B54D
0x18000b7e9  mov     edx, 1F4h
0x18000b7ee  mov     [rsp+68h+var_48], ebx
0x18000b7f2  lea     r8, aInternalServer; "Internal Server Error"
0x18000b7f9  mov     rcx, r15
0x18000b7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b801  mov     rcx, rdi; this
0x18000b804  call    ?SetRequestHandledAndTrace@W3_ISAPI_HANDLER@@AEAAJXZ; W3_ISAPI_HANDLER::SetRequestHandledAndTrace(void)
0x18000b809  mov     eax, 2
0x18000b80e  lea     r11, [rsp+68h+var_28]
0x18000b813  mov     rbx, [r11+40h]
0x18000b817  mov     rbp, [r11+48h]
0x18000b81b  mov     rsp, r11
0x18000b81e  pop     r15
0x18000b820  pop     r14
0x18000b822  pop     r12
0x18000b824  pop     rdi
0x18000b825  pop     rsi
0x18000b826  retn
```
