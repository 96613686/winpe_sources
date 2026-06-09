# WEBSOCKET_MODULE::OnBeginRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800079b0`
- end: `0x180007e68`
- name: `?OnBeginRequest@WEBSOCKET_MODULE@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(__int64, struct IHttpContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002e44`
- `0x1800079b0`
- `0x18000838c`
- `0x180009010`

## import_xrefs

- `msvcrt!tolower` at `0x180007b88`
- `msvcrt!tolower` at `0x180007b92`
- `msvcrt!tolower` at `0x180007b88`
- `msvcrt!tolower` at `0x180007b92`
- `msvcrt!_stricmp` at `0x180007b2e`
- `msvcrt!_stricmp` at `0x180007b2e`
- `iisutil!PuDbgPrint` at `0x180007d04`
- `iisutil!PuDbgPrint` at `0x180007d04`

## string_xrefs

- `0x180007cfd`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\module.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_MODULE::OnBeginRequest(__int64 a1, struct IHttpContext *a2)
{
  __int64 v3; // rax
  void *v4; // r12
  __int64 v5; // rbx
  int v6; // eax
  WEBSOCKET_MODULE *v7; // rcx
  volatile signed __int32 *v8; // r13
  int v9; // esi
  __int64 v10; // r10
  __int64 v11; // r10
  const char *v12; // rax
  _BYTE *v13; // rax
  _BYTE *v14; // r14
  const char *v15; // rax
  _BYTE *v16; // r13
  int v17; // ebx
  int v18; // edi
  bool v19; // zf
  void (__fastcall ***v20)(_QWORD, __int64, __int64); // rax
  _QWORD *v21; // rax
  __int64 v22; // rax
  int (__fastcall ***v23)(_QWORD, GUID **); // rax
  int (__fastcall **v24)(_QWORD, GUID **); // rcx
  __int64 v25; // rax
  __int64 *v26; // r8
  __int64 v27; // rcx
  void (__fastcall *v28)(__int64 *, _QWORD *); // rax
  const char *v30; // [rsp+40h] [rbp-C0h] BYREF
  struct WEBSOCKET_CONFIG *v31; // [rsp+48h] [rbp-B8h] BYREF
  struct IAppHostConfigException *v32; // [rsp+50h] [rbp-B0h] BYREF
  GUID *v33; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v34; // [rsp+60h] [rbp-A0h]
  _QWORD v35[5]; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+98h] [rbp-68h]
  int v37; // [rsp+9Ch] [rbp-64h]
  __int128 v38; // [rsp+A0h] [rbp-60h]
  int v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+B4h] [rbp-4Ch]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  const wchar_t **v42; // [rsp+C0h] [rbp-40h]
  const wchar_t *v43; // [rsp+D0h] [rbp-30h] BYREF
  int v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  int v46; // [rsp+E8h] [rbp-18h]
  __int64 v47; // [rsp+F0h] [rbp-10h]
  const wchar_t *v48; // [rsp+F8h] [rbp-8h]
  int v49; // [rsp+100h] [rbp+0h]
  const char **v50; // [rsp+108h] [rbp+8h]
  int v51; // [rsp+110h] [rbp+10h]
  __int64 v52; // [rsp+118h] [rbp+18h]
  __int16 v53; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int16 v54; // [rsp+178h] [rbp+78h] BYREF

  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v53 = 0;
  v54 = 0;
  v31 = 0;
  v4 = 0;
  v32 = 0;
  v5 = v3;
  v6 = WEBSOCKET_CONFIG::ReadConfig(a2, &v31, &v32);
  v8 = (volatile signed __int32 *)v31;
  v9 = v6;
  if ( v6 < 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, struct IAppHostConfigException *, _DWORD))(*(_QWORD *)v10 + 24LL))(
      v10,
      500,
      "Internal Server Error",
      19,
      v9,
      v32,
      0);
    goto LABEL_27;
  }
  if ( !*((_DWORD *)v31 + 3) )
    goto LABEL_27;
  v9 = WEBSOCKET_MODULE::SetWebSocketVersionServerVariable(v7, a2);
  if ( v9 < 0 )
  {
LABEL_5:
    v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v11 + 24LL))(
      v11,
      500,
      "Internal Server Error",
      0,
      v9,
      0,
      0);
    goto LABEL_27;
  }
  if ( (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 16LL))(v5, 28) )
  {
    if ( (*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, "Sec-WebSocket-Key", 0) )
    {
      if ( (*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v5 + 24LL))(
             v5,
             "Sec-WebSocket-Version",
             0) )
      {
        v12 = (const char *)(*(__int64 (__fastcall **)(__int64, const char *, __int16 *))(*(_QWORD *)v5 + 24LL))(
                              v5,
                              "Upgrade",
                              &v53);
        if ( v53 == 9 && !_stricmp(v12, "websocket") )
        {
          v13 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, const char *, unsigned __int16 *))(*(_QWORD *)v5 + 24LL))(
                           v5,
                           "Connection",
                           &v54);
          v14 = v13;
          if ( v54 >= 7u )
          {
            if ( *v13 )
            {
              while ( 1 )
              {
                v15 = "upgrade";
                v16 = v14;
                v30 = "upgrade";
                do
                {
                  if ( !*v15 )
                    break;
                  v17 = (char)*v16;
                  v18 = tolower(*v15);
                  v19 = tolower(v17) == v18;
                  v15 = v30;
                  if ( !v19 )
                    break;
                  v15 = v30 + 1;
                  ++v16;
                  ++v30;
                }
                while ( *v16 );
                v8 = (volatile signed __int32 *)v31;
                if ( !*v15 )
                  break;
                if ( !*++v14 )
                  goto LABEL_27;
              }
              if ( v14 )
              {
                v20 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
                (**v20)(v20, 30, 1);
                v9 = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, const wchar_t *))(*(_QWORD *)a2 + 136LL))(
                       a2,
                       "IIS_WEBSOCK",
                       L"websockets");
                if ( v9 < 0 )
                  goto LABEL_5;
                v21 = operator new(0x10u);
                v4 = v21;
                if ( v21 )
                {
                  *((_DWORD *)v21 + 2) = 0;
                  *v21 = &REQUEST_CONTEXT::`vftable';
                  v22 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
                  v9 = (*(__int64 (__fastcall **)(__int64, void *, void *))(*(_QWORD *)v22 + 8LL))(
                         v22,
                         v4,
                         g_pWebSocketModuleId);
                  if ( v9 >= 0 )
                    v4 = 0;
                }
                else
                {
                  v9 = -2147024882;
                  v4 = 0;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_27:
  if ( v8 && _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 1);
  if ( v4 )
    operator delete(v4);
  if ( v9 >= 0 )
    return 0;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\module.cxx",
      174,
      "WEBSOCKET_MODULE::OnBeginRequest",
      "ERROR = %08x\n",
      v9);
  v23 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
  v33 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v24 = *v23;
  v34 = 0;
  if ( (*v24)(v23, &v33) >= 0 && DWORD2(v34) && DWORD1(v34) >= 4 && ((_DWORD)v34 == 0x4000 || (v34 & 0x4000) != 0) )
  {
    v25 = *(_QWORD *)a2;
    LODWORD(v30) = v9;
    v26 = (__int64 *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v25 + 272))(a2);
    v35[1] = 0x4000;
    v35[3] = 1;
    v35[2] = &`IISWebSocketEvents::GetAreaGuid'::`2'::AreaGuid;
    v50 = &v30;
    v35[4] = L"WEBSOCKET_INITIALIZE_FAILED";
    v42 = &v43;
    v27 = *v26;
    v43 = L"ContextId";
    v41 = 2;
    v48 = L"ErrorCode";
    v28 = *(void (__fastcall **)(__int64 *, _QWORD *))(v27 + 16);
    v35[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v36 = 1;
    v37 = 4;
    v38 = 0;
    v39 = 0;
    v40 = 1;
    v44 = 72;
    v45 = 0;
    v46 = 16;
    v47 = 0;
    v49 = 19;
    v51 = 4;
    v52 = 0;
    v28(v26, v35);
  }
  return 2;
}

```

## disassembly

```asm
0x1800079b0  mov     [rsp-8+arg_0], rbx
0x1800079b5  push    rbp
0x1800079b6  push    rsi
0x1800079b7  push    rdi
0x1800079b8  push    r12
0x1800079ba  push    r13
0x1800079bc  push    r14
0x1800079be  push    r15
0x1800079c0  lea     rbp, [rsp-20h]
0x1800079c5  sub     rsp, 120h
0x1800079cc  mov     rax, [rdx]
0x1800079cf  mov     rcx, rdx
0x1800079d2  mov     r15, rdx
0x1800079d5  mov     rax, [rax+18h]
0x1800079d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079de  xor     edi, edi
0x1800079e0  lea     r8, [rsp+150h+var_100]; struct IAppHostConfigException **
0x1800079e5  lea     rdx, [rsp+150h+var_108]; struct WEBSOCKET_CONFIG **
0x1800079ea  mov     [rbp+50h+arg_8], di
0x1800079ee  mov     rcx, r15; struct IHttpContext *
0x1800079f1  mov     [rbp+50h+arg_18], di
0x1800079f5  mov     [rsp+150h+var_108], rdi
0x1800079fa  mov     r12d, edi
0x1800079fd  mov     [rsp+150h+var_100], rdi
0x180007a02  mov     rbx, rax
0x180007a05  call    ?ReadConfig@WEBSOCKET_CONFIG@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAUIAppHostConfigException@@@Z; WEBSOCKET_CONFIG::ReadConfig(IHttpContext *,WEBSOCKET_CONFIG * *,IAppHostConfigException * *)
0x180007a0a  mov     r13, [rsp+150h+var_108]
0x180007a0f  mov     esi, eax
0x180007a11  test    eax, eax
0x180007a13  jns     short loc_180007A5D
0x180007a15  mov     rcx, [r15]
0x180007a18  mov     rax, [rcx+20h]
0x180007a1c  mov     rcx, r15
0x180007a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a24  mov     r10, rax
0x180007a27  mov     [rsp+150h+var_120], edi
0x180007a2b  lea     r9d, [rdi+13h]
0x180007a2f  mov     rcx, [rax]
0x180007a32  mov     rax, [rcx+18h]
0x180007a36  mov     rcx, [rsp+150h+var_100]
0x180007a3b  mov     [rsp+150h+var_128], rcx
0x180007a40  mov     edx, 1F4h
0x180007a45  mov     dword ptr [rsp+150h+var_130], esi
0x180007a49  lea     r8, aInternalServer; "Internal Server Error"
0x180007a50  mov     rcx, r10
0x180007a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a58  jmp     loc_180007C8E
0x180007a5d  cmp     [r13+0Ch], edi
0x180007a61  jz      loc_180007C8E
0x180007a67  mov     rdx, r15; struct IHttpContext *
0x180007a6a  call    ?SetWebSocketVersionServerVariable@WEBSOCKET_MODULE@@AEAAJPEAVIHttpContext@@@Z; WEBSOCKET_MODULE::SetWebSocketVersionServerVariable(IHttpContext *)
0x180007a6f  mov     esi, eax
0x180007a71  test    eax, eax
0x180007a73  jns     short loc_180007A9C
0x180007a75  mov     rax, [r15]
0x180007a78  mov     rcx, r15
0x180007a7b  mov     rax, [rax+20h]
0x180007a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a84  mov     r10, rax
0x180007a87  mov     [rsp+150h+var_120], edi
0x180007a8b  xor     r9d, r9d
0x180007a8e  mov     [rsp+150h+var_128], rdi
0x180007a93  mov     rcx, [rax]
0x180007a96  mov     rax, [rcx+18h]
0x180007a9a  jmp     short loc_180007A40
0x180007a9c  mov     rax, [rbx]
0x180007a9f  xor     r8d, r8d
0x180007aa2  mov     rcx, rbx
0x180007aa5  mov     rax, [rax+10h]
0x180007aa9  lea     edx, [r8+1Ch]
0x180007aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab2  test    rax, rax
0x180007ab5  jz      loc_180007C8E
0x180007abb  mov     rax, [rbx]
0x180007abe  lea     rdx, aSecWebsocketKe; "Sec-WebSocket-Key"
0x180007ac5  xor     r8d, r8d
0x180007ac8  mov     rcx, rbx
0x180007acb  mov     rax, [rax+18h]
0x180007acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad4  test    rax, rax
0x180007ad7  jz      loc_180007C8E
0x180007add  mov     rax, [rbx]
0x180007ae0  lea     rdx, aSecWebsocketVe; "Sec-WebSocket-Version"
0x180007ae7  xor     r8d, r8d
0x180007aea  mov     rcx, rbx
0x180007aed  mov     rax, [rax+18h]
0x180007af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af6  test    rax, rax
0x180007af9  jz      loc_180007C8E
0x180007aff  mov     rax, [rbx]
0x180007b02  lea     r8, [rbp+50h+arg_8]
0x180007b06  lea     rdx, aUpgrade_0; "Upgrade"
0x180007b0d  mov     rcx, rbx
0x180007b10  mov     rax, [rax+18h]
0x180007b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b19  cmp     [rbp+50h+arg_8], 9
0x180007b1e  jnz     loc_180007C8E
0x180007b24  lea     rdx, aWebsocket; "websocket"
0x180007b2b  mov     rcx, rax; String1
0x180007b2e  call    cs:__imp__stricmp
0x180007b34  test    eax, eax
0x180007b36  jnz     loc_180007C8E
0x180007b3c  mov     rax, [rbx]
0x180007b3f  lea     r8, [rbp+50h+arg_18]
0x180007b43  lea     rdx, aConnection; "Connection"
0x180007b4a  mov     rcx, rbx
0x180007b4d  mov     rax, [rax+18h]
0x180007b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b56  cmp     [rbp+50h+arg_18], 7
0x180007b5b  mov     r14, rax
0x180007b5e  jb      loc_180007C8E
0x180007b64  cmp     [rax], dil
0x180007b67  jz      loc_180007C8E
0x180007b6d  lea     rax, aUpgrade; "upgrade"
0x180007b74  mov     r13, r14
0x180007b77  mov     [rsp+150h+var_110], rax
0x180007b7c  movsx   ecx, byte ptr [rax]; C
0x180007b7f  test    cl, cl
0x180007b81  jz      short loc_180007BB8
0x180007b83  movsx   ebx, byte ptr [r13+0]
0x180007b88  call    cs:__imp_tolower
0x180007b8e  mov     ecx, ebx; C
0x180007b90  mov     edi, eax
0x180007b92  call    cs:__imp_tolower
0x180007b98  cmp     eax, edi
0x180007b9a  mov     rax, [rsp+150h+var_110]
0x180007b9f  jnz     short loc_180007BB6
0x180007ba1  inc     rax
0x180007ba4  inc     r13
0x180007ba7  xor     edi, edi
0x180007ba9  mov     [rsp+150h+var_110], rax
0x180007bae  cmp     [r13+0], dil
0x180007bb2  jnz     short loc_180007B7C
0x180007bb4  jmp     short loc_180007BB8
0x180007bb6  xor     edi, edi
0x180007bb8  mov     r13, [rsp+150h+var_108]
0x180007bbd  cmp     [rax], dil
0x180007bc0  jz      short loc_180007BCF
0x180007bc2  inc     r14
0x180007bc5  cmp     [r14], dil
0x180007bc8  jnz     short loc_180007B6D
0x180007bca  jmp     loc_180007C8E
0x180007bcf  test    r14, r14
0x180007bd2  jz      loc_180007C8E
0x180007bd8  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180007bdf  mov     rax, [rcx]
0x180007be2  mov     rax, [rax+60h]
0x180007be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007beb  mov     r9, rax
0x180007bee  mov     edx, 1Eh
0x180007bf3  mov     rcx, [rax]
0x180007bf6  lea     r8d, [rdx-1Dh]
0x180007bfa  mov     rax, [rcx]
0x180007bfd  mov     rcx, r9
0x180007c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c05  mov     rax, [r15]
0x180007c08  lea     r8, aWebsockets; "websockets"
0x180007c0f  lea     rdx, aIisWebsock; "IIS_WEBSOCK"
0x180007c16  mov     rcx, r15
0x180007c19  mov     rax, [rax+88h]
0x180007c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c25  mov     esi, eax
0x180007c27  test    eax, eax
0x180007c29  js      loc_180007A75
0x180007c2f  mov     ecx, 10h; Size
0x180007c34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c39  mov     r12, rax
0x180007c3c  test    rax, rax
0x180007c3f  jz      short loc_180007C86
0x180007c41  lea     rax, ??_7REQUEST_CONTEXT@@6B@; const REQUEST_CONTEXT::`vftable'
0x180007c48  mov     [r12+8], edi
0x180007c4d  mov     [r12], rax
0x180007c51  mov     rcx, r15
0x180007c54  mov     rax, [r15]
0x180007c57  mov     rax, [rax+38h]
0x180007c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c60  mov     r8, cs:?g_pWebSocketModuleId@@3PEAXEA; void * g_pWebSocketModuleId
0x180007c67  mov     r9, rax
0x180007c6a  mov     rdx, r12
0x180007c6d  mov     rcx, [rax]
0x180007c70  mov     rax, [rcx+8]
0x180007c74  mov     rcx, r9
0x180007c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c7c  test    eax, eax
0x180007c7e  mov     esi, eax
0x180007c80  cmovns  r12, rdi
0x180007c84  jmp     short loc_180007C8E
0x180007c86  mov     esi, 8007000Eh
0x180007c8b  mov     r12, rdi
0x180007c8e  test    r13, r13
0x180007c91  jz      short loc_180007CBB
0x180007c93  or      eax, 0FFFFFFFFh
0x180007c96  lock xadd [r13+8], eax
0x180007c9c  cmp     eax, 1
0x180007c9f  jnz     short loc_180007CBB
0x180007ca1  test    r13, r13
0x180007ca4  jz      short loc_180007CBB
0x180007ca6  mov     rax, [r13+0]
0x180007caa  mov     edx, 1
0x180007caf  mov     rcx, r13
0x180007cb2  mov     rax, [rax+8]
0x180007cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cbb  test    r12, r12
0x180007cbe  jz      short loc_180007CC8
0x180007cc0  mov     rcx, r12; Block
0x180007cc3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007cc8  test    esi, esi
0x180007cca  jns     loc_180007E4B
0x180007cd0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007cd7  jz      short loc_180007D0A
0x180007cd9  mov     rcx, cs:g_pDebug
0x180007ce0  lea     rax, aError08x; "ERROR = %08x\n"
0x180007ce7  mov     dword ptr [rsp+150h+var_128], esi
0x180007ceb  lea     r9, aWebsocketModul_0; "WEBSOCKET_MODULE::OnBeginRequest"
0x180007cf2  mov     r8d, 0AEh
0x180007cf8  mov     [rsp+150h+var_130], rax
0x180007cfd  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007d04  call    cs:__imp_PuDbgPrint
0x180007d0a  mov     rax, [r15]
0x180007d0d  mov     rcx, r15
0x180007d10  mov     rax, [rax+110h]
0x180007d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1c  mov     r8, rax
0x180007d1f  lea     r13, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180007d26  xorps   xmm0, xmm0
0x180007d29  mov     [rsp+150h+var_F8], r13
0x180007d2e  lea     rdx, [rsp+150h+var_F8]
0x180007d33  mov     rcx, [rax]
0x180007d36  movdqu  [rsp+150h+var_F0], xmm0
0x180007d3c  mov     rax, [rcx]
0x180007d3f  mov     rcx, r8
0x180007d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d47  mov     r12d, 2
0x180007d4d  test    eax, eax
0x180007d4f  js      loc_180007E46
0x180007d55  cmp     dword ptr [rsp+150h+var_F0+8], edi
0x180007d59  jz      loc_180007E46
0x180007d5f  lea     r14d, [r12+2]
0x180007d64  cmp     dword ptr [rsp+150h+var_F0+4], r14d
0x180007d69  jb      loc_180007E46
0x180007d6f  mov     ebx, 4000h
0x180007d74  cmp     dword ptr [rsp+150h+var_F0], ebx
0x180007d78  jz      short loc_180007D84
0x180007d7a  test    dword ptr [rsp+150h+var_F0], ebx
0x180007d7e  jz      loc_180007E46
0x180007d84  mov     rax, [r15]
0x180007d87  mov     rcx, r15
0x180007d8a  mov     dword ptr [rsp+150h+var_110], esi
0x180007d8e  mov     rax, [rax+110h]
0x180007d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d9a  mov     r8, rax
0x180007d9d  mov     [rsp+150h+var_D8], rbx
0x180007da2  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISWebSocketEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISWebSocketEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180007da9  mov     [rbp+50h+var_C8], 1
0x180007db1  mov     [rbp+50h+var_D0], rax
0x180007db5  lea     rcx, [rsp+150h+var_110]
0x180007dba  mov     [rbp+50h+var_48], rcx
0x180007dbe  lea     rax, aWebsocketIniti; "WEBSOCKET_INITIALIZE_FAILED"
0x180007dc5  mov     [rbp+50h+var_C0], rax
0x180007dc9  lea     rcx, [rbp+50h+var_80]
0x180007dcd  mov     [rbp+50h+var_90], rcx
0x180007dd1  lea     rax, aContextid; "ContextId"
0x180007dd8  mov     rcx, [r8]
0x180007ddb  lea     rdx, [rsp+150h+var_E0]
0x180007de0  mov     [rbp+50h+var_80], rax
0x180007de4  xorps   xmm0, xmm0
0x180007de7  lea     rax, aErrorcode; "ErrorCode"
0x180007dee  mov     [rbp+50h+var_98], r12
0x180007df2  mov     [rbp+50h+var_58], rax
0x180007df6  mov     rax, [rcx+10h]
0x180007dfa  mov     rcx, r8
0x180007dfd  mov     [rsp+150h+var_E0], r13
0x180007e02  mov     [rbp+50h+var_B8], 1
0x180007e09  mov     [rbp+50h+var_B4], r14d
0x180007e0d  movdqa  [rbp+50h+var_B0], xmm0
0x180007e12  mov     [rbp+50h+var_A0], edi
0x180007e15  mov     [rbp+50h+var_9C], 1
0x180007e1c  mov     [rbp+50h+var_78], 48h ; 'H'
0x180007e23  mov     [rbp+50h+var_70], rdi
0x180007e27  mov     [rbp+50h+var_68], 10h
0x180007e2e  mov     [rbp+50h+var_60], rdi
0x180007e32  mov     [rbp+50h+var_50], 13h
0x180007e39  mov     [rbp+50h+var_40], r14d
0x180007e3d  mov     [rbp+50h+var_38], rdi
0x180007e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e46  mov     eax, r12d
0x180007e49  jmp     short loc_180007E4D
0x180007e4b  xor     eax, eax
0x180007e4d  mov     rbx, [rsp+150h+arg_0]
0x180007e55  add     rsp, 120h
0x180007e5c  pop     r15
0x180007e5e  pop     r14
0x180007e60  pop     r13
0x180007e62  pop     r12
0x180007e64  pop     rdi
0x180007e65  pop     rsi
0x180007e66  pop     rbp
0x180007e67  retn
```
