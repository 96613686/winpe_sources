# IP_MODULE::DoPreBeginRequest(IHttpContext *,STTABLE *,CONFIG_OBJECT *)

- ea: `0x1800047a4`
- end: `0x180004f01`
- name: `?DoPreBeginRequest@IP_MODULE@@AEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVSTTABLE@@PEAVCONFIG_OBJECT@@@Z`
- size: `1885`
- prototype: `__int64 __fastcall(__int64, struct IHttpContext *, struct STTABLE *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800062b0`

## callees

- `0x180001948`
- `0x180001cd4`
- `0x180002510`
- `0x1800044c8`
- `0x1800047a4`
- `0x180004f8c`
- `0x180005168`
- `0x180005ab8`
- `0x180006500`
- `0x1800067c0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004949`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000499c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004cac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ecc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004949`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000499c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004cac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ecc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a46`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004a4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004a4c`
- `iisutil!PuDbgPrint` at `0x180004897`
- `iisutil!PuDbgPrint` at `0x180004923`
- `iisutil!PuDbgPrint` at `0x180004b37`
- `iisutil!PuDbgPrint` at `0x180004d46`
- `iisutil!PuDbgPrint` at `0x180004897`
- `iisutil!PuDbgPrint` at `0x180004923`
- `iisutil!PuDbgPrint` at `0x180004b37`
- `iisutil!PuDbgPrint` at `0x180004d46`

## string_xrefs

- `0x18000487a`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`
- `0x1800048e0`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`
- `0x180004afa`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`
- `0x180004d09`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`

## pseudocode

```c
__int64 __fastcall IP_MODULE::DoPreBeginRequest(__int64 a1, struct IHttpContext *a2, struct STTABLE *a3, __int64 a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  struct IHttpResponse *v10; // rsi
  int ClientIP; // eax
  ALLOW_LIST *v12; // rcx
  int IpRecord; // eax
  struct IP_RECORD *v14; // rbx
  unsigned int v15; // r12d
  ULONGLONG TickCount64; // rax
  unsigned int *v17; // rdx
  unsigned int v18; // r15d
  unsigned int v19; // r14d
  unsigned int v20; // edx
  HINSTANCE v22; // rcx
  __int64 v23; // rax
  void (__fastcall *v24)(struct IHttpResponse *, HLOCAL, _QWORD, __int64); // rax
  char *v25; // rcx
  char *v26; // rax
  unsigned int v27; // edx
  int v28; // r8d
  HINSTANCE v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r8
  void (__fastcall *v32)(struct IHttpResponse *, char *, __int64, __int64); // rax
  struct IP_RECORD *v33; // [rsp+50h] [rbp-B0h] BYREF
  struct REQUEST_CONTEXT *v34; // [rsp+58h] [rbp-A8h] BYREF
  void **v35; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v36; // [rsp+68h] [rbp-98h]
  int v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+74h] [rbp-8Ch]
  _BYTE v39[68]; // [rsp+7Ch] [rbp-84h] BYREF
  void **v40; // [rsp+C0h] [rbp-40h] BYREF
  HLOCAL v41; // [rsp+C8h] [rbp-38h]
  int v42; // [rsp+D0h] [rbp-30h]
  int v43; // [rsp+D4h] [rbp-2Ch]
  _BYTE v44[68]; // [rsp+DCh] [rbp-24h] BYREF
  void **v45; // [rsp+120h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+128h] [rbp+28h]
  int v47; // [rsp+130h] [rbp+30h]
  int v48; // [rsp+134h] [rbp+34h]
  _BYTE v49[68]; // [rsp+13Ch] [rbp+3Ch] BYREF
  void **v50; // [rsp+180h] [rbp+80h] BYREF
  HLOCAL v51; // [rsp+188h] [rbp+88h]
  unsigned int v52; // [rsp+190h] [rbp+90h]
  _BYTE v53[68]; // [rsp+19Ch] [rbp+9Ch] BYREF
  void **v54; // [rsp+1E0h] [rbp+E0h] BYREF
  HLOCAL v55; // [rsp+1E8h] [rbp+E8h]
  unsigned int v56; // [rsp+1F0h] [rbp+F0h]
  char v57; // [rsp+1FCh] [rbp+FCh] BYREF
  void **v58; // [rsp+240h] [rbp+140h] BYREF
  char *v59; // [rsp+248h] [rbp+148h]
  int v60; // [rsp+250h] [rbp+150h]
  char v61; // [rsp+25Ch] [rbp+15Ch] BYREF

  STBUFF::STBUFF((STBUFF *)&v50, (int)a2);
  STBUFF::STBUFF((STBUFF *)&v40, v7);
  STBUFF::STBUFF((STBUFF *)&v35, v8);
  v33 = 0;
  v34 = 0;
  STBUFF::STBUFF((STBUFF *)&v45, v9);
  v10 = (struct IHttpResponse *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  (*(void (__fastcall **)(struct IHttpResponse *, __int64))(*(_QWORD *)v10 + 112LL))(v10, 9);
  ClientIP = IP_MODULE::GetClientIP(a2, (struct STBUFF *)&v35, (struct STBUFF *)&v50, (struct STBUFF *)&v40);
  if ( ClientIP < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
        411,
        "IP_MODULE::DoPreBeginRequest",
        "Finished to get client IP in GlobalPreBeginRequest.  Error 0x%08x (%d).\n",
        ClientIP,
        ClientIP);
    goto LABEL_59;
  }
  v12 = *(ALLOW_LIST **)(a4 + 200);
  if ( !v12 || !(unsigned int)ALLOW_LIST::QueryIpAllowed(v12, (struct sockaddr *)v41) )
    goto LABEL_18;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    *((_BYTE *)v51 + v52) = 0;
    *((_BYTE *)v51 + v52 + 1) = 0;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
      428,
      "IP_MODULE::DoPreBeginRequest",
      "Skipping checks on allowed client %s.\n",
      (const char *)v51);
  }
  if ( !*(_DWORD *)(a4 + 20) )
    goto LABEL_9;
  v37 = 0;
  v52 = 0;
  if ( (int)IP_MODULE::GetXFFClientIp(a2, (struct CONFIG_OBJECT *)a4, (struct STBUFF *)&v35, (struct STBUFF *)&v50) < 0 )
    goto LABEL_59;
  if ( v52 )
  {
LABEL_18:
    IpRecord = IP_MODULE::GetIpRecord(a3, (struct STBUFF *)&v50, (struct STBUFF *)&v35, &v33);
    v14 = v33;
    if ( IpRecord < 0 )
      goto LABEL_56;
    if ( v33 )
    {
      if ( (int)IP_MODULE::CacheIpRecord(v33, a2, &v34) >= 0 )
      {
        v15 = *(_DWORD *)(a4 + 36);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v14 + 248));
        TickCount64 = GetTickCount64();
        v17 = (unsigned int *)((char *)v14 + 228);
        if ( TickCount64 > *((_QWORD *)v14 + 29) + (unsigned __int64)v15 )
        {
          *v17 = 0;
          *((_QWORD *)v14 + 29) = TickCount64;
        }
        ++*v17;
        ++*((_DWORD *)v14 + 56);
        v18 = *v17;
        v19 = *((_DWORD *)v14 + 56);
        *((_DWORD *)v14 + 60) = v15;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v14 + 248));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 6, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(struct IP_RECORD *, __int64))v14)(v14, 1);
        v20 = *(_DWORD *)(a4 + 32);
        if ( v19 > v20 && v20 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            *((_BYTE *)v51 + v52) = 0;
            *((_BYTE *)v51 + v52 + 1) = 0;
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
              522,
              "IP_MODULE::DoPreBeginRequest",
              "Concurrent requests exceeded for client %s. Allowed %d, actual %d.\n",
              (const char *)v51,
              v20,
              v19);
          }
          if ( *(_DWORD *)(a4 + 24) )
          {
            *((_WORD *)v34 + 12) = 501;
LABEL_31:
            v45 = &STBUFF::`vftable';
            if ( hMem != v49 )
            {
              LocalFree(hMem);
              v48 = 64;
              hMem = v49;
            }
            v47 = 0;
            v35 = &STBUFF::`vftable';
            if ( v36 != v39 )
            {
              LocalFree(v36);
              v38 = 64;
              v36 = v39;
            }
            v37 = 0;
            v40 = &STBUFF::`vftable';
            if ( v41 != v44 )
            {
              LocalFree(v41);
              v43 = 64;
              v41 = v44;
            }
            v50 = &STBUFF::`vftable';
            goto LABEL_38;
          }
          STBUFF::STBUFF((STBUFF *)&v54, v20);
          LODWORD(v33) = 0;
          if ( LoadResourceString(v22, 0x3EEu, (struct STBUFF *)&v54, (unsigned int *)&v33) >= 0 )
          {
            v23 = *(_QWORD *)v10;
            *((_BYTE *)v55 + v56) = 0;
            v24 = *(void (__fastcall **)(struct IHttpResponse *, HLOCAL, _QWORD, __int64))(v23 + 192);
            *((_BYTE *)v55 + v56 + 1) = 0;
            v24(v10, v55, (unsigned int)v33, 1);
          }
          IP_MODULE::SetStatus(v10, *(_DWORD *)(a4 + 304), 0x1F5u);
          v25 = (char *)v55;
          v54 = &STBUFF::`vftable';
          v26 = &v57;
        }
        else
        {
          v27 = *(_DWORD *)(a4 + 28);
          if ( v18 <= v27 )
            goto LABEL_31;
          if ( !v27 )
            goto LABEL_31;
          v28 = *(_DWORD *)(a4 + 36);
          if ( !v28 )
            goto LABEL_31;
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            *((_BYTE *)v51 + v52) = 0;
            *((_BYTE *)v51 + v52 + 1) = 0;
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
              568,
              "IP_MODULE::DoPreBeginRequest",
              "Maximum request rate exceeded for client %s. Allowed %d, actual %d, perMS %d\n",
              (const char *)v51,
              v27,
              v18,
              v28);
          }
          if ( *(_DWORD *)(a4 + 24) )
          {
            *((_WORD *)v34 + 12) = 502;
            goto LABEL_31;
          }
          STBUFF::STBUFF((STBUFF *)&v58, v27);
          LODWORD(v33) = 0;
          if ( LoadResourceString(v29, 0x3F0u, (struct STBUFF *)&v58, (unsigned int *)&v33) >= 0 )
          {
            v30 = *(_QWORD *)v10;
            v31 = (unsigned int)v33;
            v59[v60] = 0;
            v32 = *(void (__fastcall **)(struct IHttpResponse *, char *, __int64, __int64))(v30 + 192);
            v59[v60 + 1] = 0;
            v32(v10, v59, v31, 1);
          }
          IP_MODULE::SetStatus(v10, *(_DWORD *)(a4 + 304), 0x1F6u);
          v25 = v59;
          v58 = &STBUFF::`vftable';
          v26 = &v61;
        }
        if ( v25 != v26 )
          LocalFree(v25);
        goto LABEL_59;
      }
LABEL_56:
      if ( v14 && _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 6, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(struct IP_RECORD *, __int64))v14)(v14, 1);
    }
LABEL_59:
    v45 = &STBUFF::`vftable';
    if ( hMem != v49 )
    {
      LocalFree(hMem);
      v48 = 64;
      hMem = v49;
    }
    v47 = 0;
    v35 = &STBUFF::`vftable';
    if ( v36 != v39 )
    {
      LocalFree(v36);
      v38 = 64;
      v36 = v39;
    }
    v37 = 0;
    v40 = &STBUFF::`vftable';
    if ( v41 != v44 )
    {
      LocalFree(v41);
      v43 = 64;
      v41 = v44;
    }
    v42 = 0;
    v50 = &STBUFF::`vftable';
    if ( v51 != v53 )
      LocalFree(v51);
    return 1;
  }
LABEL_9:
  v45 = &STBUFF::`vftable';
  if ( hMem != v49 )
  {
    LocalFree(hMem);
    v48 = 64;
    hMem = v49;
  }
  v35 = &STBUFF::`vftable';
  v47 = 0;
  if ( v36 != v39 )
  {
    LocalFree(v36);
    v38 = 64;
    v36 = v39;
  }
  v37 = 0;
  v40 = &STBUFF::`vftable';
  if ( v41 != v44 )
  {
    LocalFree(v41);
    v43 = 64;
    v41 = v44;
  }
  v50 = &STBUFF::`vftable';
LABEL_38:
  v42 = 0;
  if ( v51 != v53 )
    LocalFree(v51);
  return 0;
}

```

## disassembly

```asm
0x1800047a4  mov     [rsp-8+arg_0], rbx
0x1800047a9  push    rbp
0x1800047aa  push    rsi
0x1800047ab  push    rdi
0x1800047ac  push    r12
0x1800047ae  push    r13
0x1800047b0  push    r14
0x1800047b2  push    r15
0x1800047b4  lea     rbp, [rsp-1B0h]
0x1800047bc  sub     rsp, 2B0h
0x1800047c3  mov     rax, cs:__security_cookie
0x1800047ca  xor     rax, rsp
0x1800047cd  mov     [rbp+1E0h+var_40], rax
0x1800047d4  lea     rcx, [rbp+1E0h+var_160]; this
0x1800047db  mov     rdi, r9
0x1800047de  mov     rbx, r8
0x1800047e1  mov     r14, rdx
0x1800047e4  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x1800047e9  lea     rcx, [rbp+1E0h+var_220]; this
0x1800047ed  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x1800047f2  lea     rcx, [rsp+2E0h+var_280]; this
0x1800047f7  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x1800047fc  xor     r12d, r12d
0x1800047ff  lea     rcx, [rbp+1E0h+var_1C0]; this
0x180004803  mov     [rsp+2E0h+var_290], r12
0x180004808  mov     [rsp+2E0h+var_288], r12
0x18000480d  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180004812  mov     rax, [r14]
0x180004815  mov     rcx, r14
0x180004818  mov     rax, [rax+20h]
0x18000481c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004821  mov     rsi, rax
0x180004824  lea     edx, [r12+9]
0x180004829  mov     rcx, [rax]
0x18000482c  mov     rax, [rcx+70h]
0x180004830  mov     rcx, rsi
0x180004833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004838  lea     r9, [rbp+1E0h+var_220]; struct STBUFF *
0x18000483c  mov     rcx, r14; struct IHttpContext *
0x18000483f  lea     r8, [rbp+1E0h+var_160]; struct STBUFF *
0x180004846  lea     rdx, [rsp+2E0h+var_280]; struct STBUFF *
0x18000484b  call    ?GetClientIP@IP_MODULE@@CAJPEAVIHttpContext@@PEAVSTBUFF@@11@Z; IP_MODULE::GetClientIP(IHttpContext *,STBUFF *,STBUFF *,STBUFF *)
0x180004850  lea     r15, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180004857  test    eax, eax
0x180004859  jns     short loc_1800048A2
0x18000485b  test    byte ptr cs:g_dwDebugFlags, 3
0x180004862  jz      loc_180004E34
0x180004868  mov     rcx, cs:g_pDebug
0x18000486f  lea     r9, aIpModuleDopreb; "IP_MODULE::DoPreBeginRequest"
0x180004876  mov     [rsp+2E0h+var_2B0], eax
0x18000487a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004881  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x180004885  mov     r8d, 19Bh
0x18000488b  lea     rax, aFinishedToGetC; "Finished to get client IP in GlobalPreB"...
0x180004892  mov     [rsp+2E0h+var_2C0], rax
0x180004897  call    cs:__imp_PuDbgPrint
0x18000489d  jmp     loc_180004E34
0x1800048a2  mov     rcx, [rdi+0C8h]; this
0x1800048a9  test    rcx, rcx
0x1800048ac  jz      loc_1800049F1
0x1800048b2  mov     rdx, [rbp+1E0h+var_218]; struct sockaddr *
0x1800048b6  call    ?QueryIpAllowed@ALLOW_LIST@@QEAAHPEAUsockaddr@@@Z; ALLOW_LIST::QueryIpAllowed(sockaddr *)
0x1800048bb  test    eax, eax
0x1800048bd  jz      loc_1800049F1
0x1800048c3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800048ca  jz      short loc_180004929
0x1800048cc  mov     ecx, [rbp+1E0h+var_150]
0x1800048d2  lea     r9, aIpModuleDopreb; "IP_MODULE::DoPreBeginRequest"
0x1800048d9  mov     rax, [rbp+1E0h+var_158]
0x1800048e0  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800048e7  mov     r8d, 1ACh
0x1800048ed  mov     [rcx+rax], r12b
0x1800048f1  mov     ecx, [rbp+1E0h+var_150]
0x1800048f7  mov     rax, [rbp+1E0h+var_158]
0x1800048fe  inc     ecx
0x180004900  mov     [rcx+rax], r12b
0x180004904  mov     rax, [rbp+1E0h+var_158]
0x18000490b  mov     rcx, cs:g_pDebug
0x180004912  mov     [rsp+2E0h+var_2B8], rax
0x180004917  lea     rax, aSkippingChecks; "Skipping checks on allowed client %s.\n"
0x18000491e  mov     [rsp+2E0h+var_2C0], rax
0x180004923  call    cs:__imp_PuDbgPrint
0x180004929  cmp     [rdi+14h], r12d
0x18000492d  jnz     loc_1800049B9
0x180004933  mov     rcx, [rbp+1E0h+hMem]; hMem
0x180004937  lea     rax, [rbp+1E0h+var_1A4]
0x18000493b  mov     [rbp+1E0h+var_1C0], r15
0x18000493f  mov     ebx, 40h ; '@'
0x180004944  cmp     rcx, rax
0x180004947  jz      short loc_18000495A
0x180004949  call    cs:__imp_LocalFree
0x18000494f  lea     rax, [rbp+1E0h+var_1A4]
0x180004953  mov     [rbp+1E0h+var_1AC], ebx
0x180004956  mov     [rbp+1E0h+hMem], rax
0x18000495a  mov     rcx, [rsp+2E0h+var_278]; hMem
0x18000495f  lea     rax, [rsp+2E0h+var_264]
0x180004964  mov     [rsp+2E0h+var_280], r15
0x180004969  mov     [rbp+1E0h+var_1B0], r12d
0x18000496d  cmp     rcx, rax
0x180004970  jz      short loc_180004986
0x180004972  call    cs:__imp_LocalFree
0x180004978  lea     rax, [rsp+2E0h+var_264]
0x18000497d  mov     [rsp+2E0h+var_26C], ebx
0x180004981  mov     [rsp+2E0h+var_278], rax
0x180004986  mov     rcx, [rbp+1E0h+var_218]; hMem
0x18000498a  lea     rax, [rbp+1E0h+var_204]
0x18000498e  mov     [rsp+2E0h+var_270], r12d
0x180004993  mov     [rbp+1E0h+var_220], r15
0x180004997  cmp     rcx, rax
0x18000499a  jz      short loc_1800049AD
0x18000499c  call    cs:__imp_LocalFree
0x1800049a2  lea     rax, [rbp+1E0h+var_204]
0x1800049a6  mov     [rbp+1E0h+var_20C], ebx
0x1800049a9  mov     [rbp+1E0h+var_218], rax
0x1800049ad  mov     [rbp+1E0h+var_160], r15
0x1800049b4  jmp     loc_180004BDA
0x1800049b9  lea     r9, [rbp+1E0h+var_160]; struct STBUFF *
0x1800049c0  mov     [rsp+2E0h+var_270], r12d
0x1800049c5  lea     r8, [rsp+2E0h+var_280]; struct STBUFF *
0x1800049ca  mov     [rbp+1E0h+var_150], r12d
0x1800049d1  mov     rdx, rdi; struct CONFIG_OBJECT *
0x1800049d4  mov     rcx, r14; struct IHttpContext *
0x1800049d7  call    ?GetXFFClientIp@IP_MODULE@@CAJPEAVIHttpContext@@PEAVCONFIG_OBJECT@@PEAVSTBUFF@@2@Z; IP_MODULE::GetXFFClientIp(IHttpContext *,CONFIG_OBJECT *,STBUFF *,STBUFF *)
0x1800049dc  test    eax, eax
0x1800049de  js      loc_180004E34
0x1800049e4  cmp     [rbp+1E0h+var_150], r12d
0x1800049eb  jz      loc_180004933
0x1800049f1  lea     r9, [rsp+2E0h+var_290]; struct IP_RECORD **
0x1800049f6  mov     rcx, rbx; this
0x1800049f9  lea     r8, [rsp+2E0h+var_280]; struct STBUFF *
0x1800049fe  lea     rdx, [rbp+1E0h+var_160]; struct STBUFF *
0x180004a05  call    ?GetIpRecord@IP_MODULE@@CAJPEAVSTTABLE@@PEAVSTBUFF@@1PEAPEAVIP_RECORD@@@Z; IP_MODULE::GetIpRecord(STTABLE *,STBUFF *,STBUFF *,IP_RECORD * *)
0x180004a0a  mov     rbx, [rsp+2E0h+var_290]
0x180004a0f  test    eax, eax
0x180004a11  js      loc_180004E0A
0x180004a17  test    rbx, rbx
0x180004a1a  jz      loc_180004E34
0x180004a20  lea     r8, [rsp+2E0h+var_288]; struct REQUEST_CONTEXT **
0x180004a25  mov     rdx, r14; struct IHttpContext *
0x180004a28  mov     rcx, rbx; struct IP_RECORD *
0x180004a2b  call    ?CacheIpRecord@IP_MODULE@@CAJPEAVIP_RECORD@@PEAVIHttpContext@@PEAPEAVREQUEST_CONTEXT@@@Z; IP_MODULE::CacheIpRecord(IP_RECORD *,IHttpContext *,REQUEST_CONTEXT * *)
0x180004a30  test    eax, eax
0x180004a32  js      loc_180004E0A
0x180004a38  mov     r12d, [rdi+24h]
0x180004a3c  lea     r13, [rbx+0F8h]
0x180004a43  mov     rcx, r13; lpCriticalSection
0x180004a46  call    cs:__imp_EnterCriticalSection
0x180004a4c  call    cs:__imp_GetTickCount64
0x180004a52  mov     ecx, r12d
0x180004a55  lea     rdx, [rbx+0E4h]
0x180004a5c  add     rcx, [rbx+0E8h]
0x180004a63  cmp     rax, rcx
0x180004a66  jbe     short loc_180004A75
0x180004a68  mov     dword ptr [rdx], 0
0x180004a6e  mov     [rbx+0E8h], rax
0x180004a75  inc     dword ptr [rdx]
0x180004a77  mov     rcx, r13; lpCriticalSection
0x180004a7a  inc     dword ptr [rbx+0E0h]
0x180004a80  mov     r15d, [rdx]
0x180004a83  mov     r14d, [rbx+0E0h]
0x180004a8a  mov     [rbx+0F0h], r12d
0x180004a91  call    cs:__imp_LeaveCriticalSection
0x180004a97  or      eax, 0FFFFFFFFh
0x180004a9a  lock xadd [rbx+18h], eax
0x180004a9f  cmp     eax, 1
0x180004aa2  jnz     short loc_180004AB7
0x180004aa4  mov     rax, [rbx]
0x180004aa7  mov     edx, 1
0x180004aac  mov     rcx, rbx
0x180004aaf  mov     rax, [rax]
0x180004ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab7  mov     edx, [rdi+20h]
0x180004aba  xor     r12d, r12d
0x180004abd  cmp     r14d, edx
0x180004ac0  jbe     loc_180004CB7
0x180004ac6  test    edx, edx
0x180004ac8  jz      loc_180004CB7
0x180004ace  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004ad5  jz      short loc_180004B3D
0x180004ad7  mov     ecx, [rbp+1E0h+var_150]
0x180004add  lea     r9, aIpModuleDopreb; "IP_MODULE::DoPreBeginRequest"
0x180004ae4  mov     rax, [rbp+1E0h+var_158]
0x180004aeb  mov     r8d, 20Ah
0x180004af1  mov     [rsp+2E0h+var_2A8], r14d
0x180004af6  mov     [rsp+2E0h+var_2B0], edx
0x180004afa  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004b01  mov     [rcx+rax], r12b
0x180004b05  mov     ecx, [rbp+1E0h+var_150]
0x180004b0b  mov     rax, [rbp+1E0h+var_158]
0x180004b12  inc     ecx
0x180004b14  mov     [rcx+rax], r12b
0x180004b18  mov     rax, [rbp+1E0h+var_158]
0x180004b1f  mov     rcx, cs:g_pDebug
0x180004b26  mov     [rsp+2E0h+var_2B8], rax
0x180004b2b  lea     rax, aConcurrentRequ; "Concurrent requests exceeded for client"...
0x180004b32  mov     [rsp+2E0h+var_2C0], rax
0x180004b37  call    cs:__imp_PuDbgPrint
0x180004b3d  cmp     [rdi+18h], r12d
0x180004b41  jz      loc_180004BFE
0x180004b47  mov     rax, [rsp+2E0h+var_288]
0x180004b4c  mov     word ptr [rax+18h], 1F5h
0x180004b52  mov     rcx, [rbp+1E0h+hMem]; hMem
0x180004b56  lea     rax, [rbp+1E0h+var_1A4]
0x180004b5a  lea     rdi, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180004b61  mov     ebx, 40h ; '@'
0x180004b66  mov     [rbp+1E0h+var_1C0], rdi
0x180004b6a  cmp     rcx, rax
0x180004b6d  jz      short loc_180004B80
0x180004b6f  call    cs:__imp_LocalFree
0x180004b75  lea     rax, [rbp+1E0h+var_1A4]
0x180004b79  mov     [rbp+1E0h+var_1AC], ebx
0x180004b7c  mov     [rbp+1E0h+hMem], rax
0x180004b80  mov     rcx, [rsp+2E0h+var_278]; hMem
0x180004b85  lea     rax, [rsp+2E0h+var_264]
0x180004b8a  mov     [rbp+1E0h+var_1B0], r12d
0x180004b8e  mov     [rsp+2E0h+var_280], rdi
0x180004b93  cmp     rcx, rax
0x180004b96  jz      short loc_180004BAC
0x180004b98  call    cs:__imp_LocalFree
0x180004b9e  lea     rax, [rsp+2E0h+var_264]
0x180004ba3  mov     [rsp+2E0h+var_26C], ebx
0x180004ba7  mov     [rsp+2E0h+var_278], rax
0x180004bac  mov     rcx, [rbp+1E0h+var_218]; hMem
0x180004bb0  lea     rax, [rbp+1E0h+var_204]
0x180004bb4  mov     [rsp+2E0h+var_270], r12d
0x180004bb9  mov     [rbp+1E0h+var_220], rdi
0x180004bbd  cmp     rcx, rax
0x180004bc0  jz      short loc_180004BD3
0x180004bc2  call    cs:__imp_LocalFree
0x180004bc8  lea     rax, [rbp+1E0h+var_204]
0x180004bcc  mov     [rbp+1E0h+var_20C], ebx
0x180004bcf  mov     [rbp+1E0h+var_218], rax
0x180004bd3  mov     [rbp+1E0h+var_160], rdi
0x180004bda  mov     rcx, [rbp+1E0h+var_158]; hMem
0x180004be1  lea     rax, [rbp+1E0h+var_144]
0x180004be8  mov     [rbp+1E0h+var_210], r12d
0x180004bec  cmp     rcx, rax
0x180004bef  jz      short loc_180004BF7
0x180004bf1  call    cs:__imp_LocalFree
0x180004bf7  xor     eax, eax
0x180004bf9  jmp     loc_180004ED7
0x180004bfe  lea     rcx, [rbp+1E0h+var_100]; this
0x180004c05  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180004c0a  lea     r9, [rsp+2E0h+var_290]; unsigned int *
0x180004c0f  mov     dword ptr [rsp+2E0h+var_290], r12d
0x180004c14  lea     r8, [rbp+1E0h+var_100]; struct STBUFF *
0x180004c1b  mov     edx, 3EEh; unsigned int
0x180004c20  call    ?LoadResourceString@@YAJPEAUHINSTANCE__@@KPEAVSTBUFF@@PEAK@Z; LoadResourceString(HINSTANCE__ *,ulong,STBUFF *,ulong *)
0x180004c25  test    eax, eax
0x180004c27  js      short loc_180004C73
0x180004c29  mov     edx, [rbp+1E0h+var_F0]
0x180004c2f  mov     r9d, 1
0x180004c35  mov     rcx, [rbp+1E0h+var_F8]
0x180004c3c  mov     rax, [rsi]
0x180004c3f  mov     [rdx+rcx], r12b
0x180004c43  mov     r8d, [rbp+1E0h+var_F0]
0x180004c4a  mov     rcx, [rbp+1E0h+var_F8]
0x180004c51  inc     r8d
0x180004c54  mov     rax, [rax+0C0h]
0x180004c5b  mov     [r8+rcx], r12b
0x180004c5f  mov     rcx, rsi
0x180004c62  mov     r8d, dword ptr [rsp+2E0h+var_290]
0x180004c67  mov     rdx, [rbp+1E0h+var_F8]
0x180004c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c73  mov     edx, [rdi+130h]; unsigned int
0x180004c79  mov     r8d, 1F5h; unsigned int
0x180004c7f  mov     rcx, rsi; struct IHttpResponse *
0x180004c82  call    ?SetStatus@IP_MODULE@@CAJPEAVIHttpResponse@@KK@Z; IP_MODULE::SetStatus(IHttpResponse *,ulong,ulong)
0x180004c87  mov     rcx, [rbp+1E0h+var_F8]; hMem
0x180004c8e  lea     r15, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180004c95  mov     [rbp+1E0h+var_100], r15
0x180004c9c  lea     rax, [rbp+1E0h+var_E4]
0x180004ca3  cmp     rcx, rax
0x180004ca6  jz      loc_180004E34
0x180004cac  call    cs:__imp_LocalFree
0x180004cb2  jmp     loc_180004E34
0x180004cb7  mov     edx, [rdi+1Ch]
0x180004cba  cmp     r15d, edx
0x180004cbd  jbe     loc_180004B52
0x180004cc3  test    edx, edx
0x180004cc5  jz      loc_180004B52
0x180004ccb  mov     r8d, [rdi+24h]
0x180004ccf  test    r8d, r8d
0x180004cd2  jz      loc_180004B52
0x180004cd8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004cdf  jz      short loc_180004D4C
0x180004ce1  mov     ecx, [rbp+1E0h+var_150]
0x180004ce7  lea     r9, aIpModuleDopreb; "IP_MODULE::DoPreBeginRequest"
0x180004cee  mov     rax, [rbp+1E0h+var_158]
0x180004cf5  mov     [rsp+2E0h+var_2A0], r8d
0x180004cfa  mov     r8d, 238h
0x180004d00  mov     [rsp+2E0h+var_2A8], r15d
0x180004d05  mov     [rsp+2E0h+var_2B0], edx
0x180004d09  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004d10  mov     [rcx+rax], r12b
0x180004d14  mov     ecx, [rbp+1E0h+var_150]
0x180004d1a  mov     rax, [rbp+1E0h+var_158]
0x180004d21  inc     ecx
0x180004d23  mov     [rcx+rax], r12b
0x180004d27  mov     rax, [rbp+1E0h+var_158]
  ... truncated ...
```
