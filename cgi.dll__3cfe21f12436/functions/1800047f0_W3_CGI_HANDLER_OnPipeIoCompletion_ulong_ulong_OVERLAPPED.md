# W3_CGI_HANDLER::OnPipeIoCompletion(ulong,ulong,_OVERLAPPED *)

- ea: `0x1800047f0`
- end: `0x180004e48`
- name: `?OnPipeIoCompletion@W3_CGI_HANDLER@@CAXKKPEAU_OVERLAPPED@@@Z`
- size: `1624`
- prototype: `static void(unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002d28`
- `0x180002f10`
- `0x1800047f0`
- `0x180005914`
- `0x180006e46`
- `0x180006e90`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800049c7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800049c7`
- `iisutil!PuDbgPrint` at `0x180004863`
- `iisutil!PuDbgPrint` at `0x180004863`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800048a7`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800048a7`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180004a31`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180004a31`
- `iisutil!QueryLocalizedResourceString` at `0x180004d6c`
- `iisutil!QueryLocalizedResourceString` at `0x180004d6c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004d79`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004d79`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004dc9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004dc9`
- `iisutil!SAFE_snwprintf` at `0x180004d89`
- `iisutil!SAFE_snwprintf` at `0x180004d89`
- `W3TP!ThreadPoolMapErrorCodeIfNecessary` at `0x18000481b`
- `W3TP!ThreadPoolMapErrorCodeIfNecessary` at `0x18000481b`

## string_xrefs

- `0x18000484a`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180004851`: `Error %d on CGI_HANDLER::OnPipeIoCompletion\n`
- `0x18000483f`: `W3_CGI_HANDLER::OnPipeIoCompletion`

## pseudocode

```c
void __fastcall W3_CGI_HANDLER::OnPipeIoCompletion(unsigned int a1, unsigned int a2, struct _OVERLAPPED *a3)
{
  size_t v4; // r14
  unsigned int v5; // eax
  signed int v6; // ebx
  ULONG_PTR *p_InternalHigh; // rdi
  DWORD v8; // r12d
  int *v9; // rsi
  __int64 v10; // rax
  int v11; // eax
  __int64 *v12; // r14
  _QWORD *v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rax
  int (__fastcall ***v16)(_QWORD, GUID **); // rax
  int (__fastcall **v17)(_QWORD, GUID **); // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  int (__fastcall ***v21)(_QWORD, GUID **); // rax
  int (__fastcall **v22)(_QWORD, GUID **); // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  const char *v26; // rax
  const unsigned __int16 *LocalizedResourceString; // rbx
  __int64 v28; // rax
  __int64 v29; // rax
  DWORD ExitCode; // [rsp+40h] [rbp-C0h] BYREF
  GUID *v31; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h]
  unsigned int v33[4]; // [rsp+60h] [rbp-A0h] BYREF
  GUID *v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h]
  GUID *v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  const wchar_t *v38; // [rsp+90h] [rbp-70h]
  int v39; // [rsp+98h] [rbp-68h]
  int v40; // [rsp+9Ch] [rbp-64h]
  __int128 v41; // [rsp+A0h] [rbp-60h]
  int v42; // [rsp+B0h] [rbp-50h]
  int v43; // [rsp+B4h] [rbp-4Ch]
  int v44; // [rsp+B8h] [rbp-48h]
  _QWORD v45[2]; // [rsp+BCh] [rbp-44h] BYREF
  const unsigned __int16 *v46; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v47; // [rsp+E0h] [rbp-20h] BYREF
  int v48; // [rsp+E8h] [rbp-18h]
  __int64 v49; // [rsp+F0h] [rbp-10h]
  int v50; // [rsp+F8h] [rbp-8h]
  __int64 v51; // [rsp+100h] [rbp+0h]
  const wchar_t *v52; // [rsp+108h] [rbp+8h]
  int v53; // [rsp+110h] [rbp+10h]
  __int64 *v54; // [rsp+118h] [rbp+18h]
  int v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  _BYTE v57[32]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v58; // [rsp+150h] [rbp+50h]
  unsigned int v59; // [rsp+160h] [rbp+60h]

  v4 = a2;
  v5 = ThreadPoolMapErrorCodeIfNecessary(a1);
  v6 = v5;
  if ( v5 && v5 != 109 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
      305,
      "W3_CGI_HANDLER::OnPipeIoCompletion",
      "Error %d on CGI_HANDLER::OnPipeIoCompletion\n",
      v5);
  p_InternalHigh = &a3[-260].InternalHigh;
  v8 = 1;
  ExitCode = 1;
  if ( !v6 && (_DWORD)v4 )
  {
    v9 = (int *)(p_InternalHigh + 1);
    if ( *((_DWORD *)p_InternalHigh + 2) == 2 )
    {
      if ( !BUFFER::Resize((BUFFER *)(p_InternalHigh + 1032), v4 + *((_DWORD *)p_InternalHigh + 2076) + 1) )
        goto LABEL_23;
      memcpy_0((void *)(p_InternalHigh[1036] + *((unsigned int *)p_InternalHigh + 2076)), p_InternalHigh + 8, v4);
      *((_DWORD *)p_InternalHigh + 2076) += v4;
      *(_BYTE *)(*((unsigned int *)p_InternalHigh + 2076) + p_InternalHigh[1036]) = 0;
    }
    else if ( *v9 == 3 )
    {
      *((_DWORD *)p_InternalHigh + 2076) = v4;
    }
    v6 = W3_CGI_HANDLER::CGIContinueOnPipeCompletion((W3_CGI_HANDLER *)p_InternalHigh, (int *)&ExitCode);
    if ( v6 >= 0 )
      return;
    v8 = ExitCode;
LABEL_22:
    if ( !v8 )
    {
      v29 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)p_InternalHigh[6] + 32LL))(p_InternalHigh[6]);
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, signed int, _QWORD, _DWORD))(*(_QWORD *)v29 + 24LL))(
        v29,
        400,
        "Bad Request",
        0,
        v6,
        0,
        0);
      goto LABEL_54;
    }
LABEL_23:
    if ( *v9 != 3 && *v9 != 4 )
    {
      ExitCode = 0;
      if ( *((_DWORD *)p_InternalHigh + 2076) )
        v12 = (__int64 *)p_InternalHigh[1036];
      else
        v12 = &qword_18000ACD8;
      if ( GetExitCodeProcess((HANDLE)p_InternalHigh[5], &ExitCode) && ExitCode == -249208029 )
      {
        v46 = 0;
        v13 = p_InternalHigh + 6;
        v14 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)p_InternalHigh[6] + 24LL))(p_InternalHigh[6]);
        v46 = *(const unsigned __int16 **)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) + 72);
        EVENT_LOG::LogEvent((EVENT_LOG *)g_pEventLog, 0xC00008A8, 1u, &v46, 0);
        v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 32LL))(*v13);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v15 + 24LL))(
          v15,
          502,
          "Bad Gateway",
          1,
          0,
          0,
          0);
        v16 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 272LL))(*v13);
        v31 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v17 = *v16;
        v32 = 0;
        if ( (*v17)(v16, &v31) >= 0 && DWORD2(v32) && DWORD1(v32) >= 4 && ((_DWORD)v32 == 32 || (v32 & 0x20) != 0) )
        {
          v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 272LL))(*v13);
          v35 = 32;
          v37 = 4;
          memset(v45, 0, 12);
          v38 = L"CGI_TIMEOUT";
          v39 = 1;
          v43 = 1;
          v47 = L"ContextId";
          v52 = L"Headers";
          v34 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
          v36 = &`IISCGIEvents::GetAreaGuid'::`2'::AreaGuid;
          v40 = 4;
          v44 = 2;
          v41 = 0;
          v42 = 0;
          v48 = 72;
          v49 = 0;
          v50 = 16;
          v51 = 0;
          v53 = 30;
          v54 = v12;
          if ( v12 )
          {
            v19 = -1;
            do
              ++v19;
            while ( *((_BYTE *)v12 + v19) );
LABEL_48:
            v23 = v19 + 1;
            goto LABEL_49;
          }
          goto LABEL_45;
        }
      }
      else
      {
        v13 = p_InternalHigh + 6;
        v20 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)p_InternalHigh[6] + 32LL))(p_InternalHigh[6]);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, DWORD, _QWORD, _DWORD))(*(_QWORD *)v20 + 24LL))(
          v20,
          502,
          "Bad Gateway",
          2,
          ExitCode,
          0,
          0);
        v21 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 272LL))(*v13);
        v31 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v22 = *v21;
        v32 = 0;
        if ( (*v22)(v21, &v31) >= 0 && DWORD2(v32) && DWORD1(v32) >= 4 && ((_DWORD)v32 == 32 || (v32 & 0x20) != 0) )
        {
          v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 272LL))(*v13);
          v35 = 32;
          v37 = 5;
          memset(v45, 0, 12);
          v38 = L"CGI_PREMATURE_TERMINATION";
          v39 = 1;
          v43 = 1;
          v47 = L"ContextId";
          v52 = L"Headers";
          v34 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
          v36 = &`IISCGIEvents::GetAreaGuid'::`2'::AreaGuid;
          v40 = 4;
          v44 = 2;
          v41 = 0;
          v42 = 0;
          v48 = 72;
          v49 = 0;
          v50 = 16;
          v51 = 0;
          v53 = 30;
          v54 = v12;
          if ( v12 )
          {
            v19 = -1;
            do
              ++v19;
            while ( *((_BYTE *)v12 + v19) );
            goto LABEL_48;
          }
LABEL_45:
          v23 = 0;
LABEL_49:
          v55 = v23;
          v56 = 0;
          *(_QWORD *)((char *)v45 + 4) = &v47;
          (*(void (__fastcall **)(__int64, GUID **))(*(_QWORD *)v18 + 16LL))(v18, &v34);
        }
      }
      v24 = *v13;
      v33[0] = 0;
      v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24);
      v26 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 16LL))(v25, 23);
      LocalizedResourceString = QueryLocalizedResourceString(v26, 0x3235u, v33);
      STRU::STRU((STRU *)v57);
      if ( (int)SAFE_snwprintf((struct STRU *)v57, LocalizedResourceString, v12) >= 0 )
      {
        v28 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 32LL))(*v13);
        (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v28 + 192LL))(v28, v58, v59, 1);
      }
      STRU::~STRU((STRU *)v57);
    }
LABEL_54:
    W3_CGI_HANDLER::SetCgiStateDoneWithRequest((W3_CGI_HANDLER *)p_InternalHigh);
    (*(void (__fastcall **)(ULONG_PTR, _QWORD))(*(_QWORD *)p_InternalHigh[6] + 64LL))(p_InternalHigh[6], 0);
    return;
  }
  v9 = (int *)(p_InternalHigh + 1);
  if ( *((_DWORD *)p_InternalHigh + 2) != 1 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_22;
  }
  if ( *((_DWORD *)p_InternalHigh + 2090) )
  {
    v10 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)p_InternalHigh[6] + 32LL))(p_InternalHigh[6]);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 128LL))(v10);
    v11 = 3;
  }
  else
  {
    v11 = 2;
  }
  *v9 = v11;
  *((_DWORD *)p_InternalHigh + 2076) = 0;
  v6 = W3_CGI_HANDLER::CGIReadCGIOutput((W3_CGI_HANDLER *)p_InternalHigh);
  if ( v6 < 0 )
    goto LABEL_22;
}

```

## disassembly

```asm
0x1800047f0  push    rbp
0x1800047f2  push    rbx
0x1800047f3  push    rsi
0x1800047f4  push    rdi
0x1800047f5  push    r12
0x1800047f7  push    r13
0x1800047f9  push    r14
0x1800047fb  lea     rbp, [rsp-70h]
0x180004800  sub     rsp, 170h
0x180004807  mov     rax, cs:__security_cookie
0x18000480e  xor     rax, rsp
0x180004811  mov     [rbp+0A0h+var_38], rax
0x180004815  mov     rdi, r8
0x180004818  mov     r14d, edx
0x18000481b  call    cs:__imp_?ThreadPoolMapErrorCodeIfNecessary@@YAKK@Z; ThreadPoolMapErrorCodeIfNecessary(ulong)
0x180004821  xor     r13d, r13d
0x180004824  mov     ebx, eax
0x180004826  test    eax, eax
0x180004828  jz      short loc_180004869
0x18000482a  cmp     eax, 6Dh ; 'm'
0x18000482d  jz      short loc_180004869
0x18000482f  test    cs:g_dwDebugFlags, 3
0x180004836  jz      short loc_180004869
0x180004838  mov     rcx, cs:g_pDebug
0x18000483f  lea     r9, aW3CgiHandlerOn; "W3_CGI_HANDLER::OnPipeIoCompletion"
0x180004846  mov     dword ptr [rsp+1A0h+var_178], eax
0x18000484a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004851  lea     rax, aErrorDOnCgiHan; "Error %d on CGI_HANDLER::OnPipeIoComple"...
0x180004858  mov     r8d, 131h
0x18000485e  mov     [rsp+1A0h+var_180], rax
0x180004863  call    cs:__imp_PuDbgPrint
0x180004869  add     rdi, 0FFFFFFFFFFFFDF88h
0x180004870  mov     r12d, 1
0x180004876  mov     [rsp+1A0h+ExitCode], r12d
0x18000487b  test    ebx, ebx
0x18000487d  jnz     loc_180004912
0x180004883  test    r14d, r14d
0x180004886  jz      loc_180004912
0x18000488c  lea     rsi, [rdi+8]
0x180004890  cmp     dword ptr [rsi], 2
0x180004893  jnz     short loc_1800048E8
0x180004895  mov     edx, [rdi+2070h]
0x18000489b  lea     rcx, [rdi+2040h]
0x1800048a2  inc     edx
0x1800048a4  add     edx, r14d
0x1800048a7  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800048ad  test    al, al
0x1800048af  jz      loc_180004988
0x1800048b5  mov     ecx, [rdi+2070h]
0x1800048bb  lea     rdx, [rdi+40h]; Src
0x1800048bf  add     rcx, [rdi+2060h]; void *
0x1800048c6  mov     r8, r14; Size
0x1800048c9  call    memcpy_0
0x1800048ce  add     [rdi+2070h], r14d
0x1800048d5  mov     ecx, [rdi+2070h]
0x1800048db  mov     rax, [rdi+2060h]
0x1800048e2  mov     [rcx+rax], r13b
0x1800048e6  jmp     short loc_1800048F4
0x1800048e8  cmp     dword ptr [rsi], 3
0x1800048eb  jnz     short loc_1800048F4
0x1800048ed  mov     [rdi+2070h], r14d
0x1800048f4  lea     rdx, [rsp+1A0h+ExitCode]; int *
0x1800048f9  mov     rcx, rdi; this
0x1800048fc  call    ?CGIContinueOnPipeCompletion@W3_CGI_HANDLER@@AEAAJPEAH@Z; W3_CGI_HANDLER::CGIContinueOnPipeCompletion(int *)
0x180004901  mov     ebx, eax
0x180004903  test    eax, eax
0x180004905  jns     loc_180004E2A
0x18000490b  mov     r12d, [rsp+1A0h+ExitCode]
0x180004910  jmp     short loc_18000497F
0x180004912  lea     rsi, [rdi+8]
0x180004916  cmp     [rsi], r12d
0x180004919  jnz     short loc_180004972
0x18000491b  cmp     [rdi+20A8h], r13d
0x180004922  jz      short loc_180004950
0x180004924  mov     rcx, [rdi+30h]
0x180004928  mov     rax, [rcx]
0x18000492b  mov     rax, [rax+20h]
0x18000492f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004934  mov     rdx, rax
0x180004937  mov     rcx, [rax]
0x18000493a  mov     rax, [rcx+80h]
0x180004941  mov     rcx, rdx
0x180004944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004949  mov     eax, 3
0x18000494e  jmp     short loc_180004955
0x180004950  mov     eax, 2
0x180004955  mov     [rsi], eax
0x180004957  mov     rcx, rdi; this
0x18000495a  mov     [rdi+2070h], r13d
0x180004961  call    ?CGIReadCGIOutput@W3_CGI_HANDLER@@AEAAJXZ; W3_CGI_HANDLER::CGIReadCGIOutput(void)
0x180004966  mov     ebx, eax
0x180004968  test    eax, eax
0x18000496a  jns     loc_180004E2A
0x180004970  jmp     short loc_18000497F
0x180004972  test    ebx, ebx
0x180004974  jle     short loc_18000497F
0x180004976  movzx   ebx, bx
0x180004979  or      ebx, 80070000h
0x18000497f  test    r12d, r12d
0x180004982  jz      loc_180004DD1
0x180004988  cmp     dword ptr [rsi], 3
0x18000498b  jz      loc_180004E10
0x180004991  mov     r12d, 4
0x180004997  cmp     [rsi], r12d
0x18000499a  jz      loc_180004E10
0x1800049a0  mov     [rsp+1A0h+ExitCode], r13d
0x1800049a5  cmp     [rdi+2070h], r13d
0x1800049ac  jbe     short loc_1800049B7
0x1800049ae  mov     r14, [rdi+2060h]
0x1800049b5  jmp     short loc_1800049BE
0x1800049b7  lea     r14, qword_18000ACD8
0x1800049be  mov     rcx, [rdi+28h]; hProcess
0x1800049c2  lea     rdx, [rsp+1A0h+ExitCode]; lpExitCode
0x1800049c7  call    cs:__imp_GetExitCodeProcess
0x1800049cd  test    eax, eax
0x1800049cf  jz      loc_180004B9D
0x1800049d5  cmp     [rsp+1A0h+ExitCode], 0F1256323h
0x1800049dd  jnz     loc_180004B9D
0x1800049e3  mov     [rbp+0A0h+var_D0], r13
0x1800049e7  lea     rsi, [rdi+30h]
0x1800049eb  mov     rcx, [rsi]
0x1800049ee  mov     rax, [rcx]
0x1800049f1  mov     rax, [rax+18h]
0x1800049f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049fa  mov     rdx, rax
0x1800049fd  mov     rcx, [rax]
0x180004a00  mov     rax, [rcx+8]
0x180004a04  mov     rcx, rdx
0x180004a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0c  mov     ebx, 1
0x180004a11  mov     dword ptr [rsp+1A0h+var_180], r13d
0x180004a16  mov     r8d, ebx
0x180004a19  lea     r9, [rbp+0A0h+var_D0]
0x180004a1d  mov     edx, 0C00008A8h
0x180004a22  mov     rcx, [rax+48h]
0x180004a26  mov     [rbp+0A0h+var_D0], rcx
0x180004a2a  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_pEventLog
0x180004a31  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180004a37  mov     rcx, [rsi]
0x180004a3a  mov     rax, [rcx]
0x180004a3d  mov     rax, [rax+20h]
0x180004a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a46  mov     r10, rax
0x180004a49  mov     [rsp+1A0h+var_170], r13d
0x180004a4e  mov     r9d, ebx
0x180004a51  mov     [rsp+1A0h+var_178], r13
0x180004a56  mov     edx, 1F6h
0x180004a5b  mov     dword ptr [rsp+1A0h+var_180], r13d
0x180004a60  mov     rcx, [rax]
0x180004a63  lea     r8, aBadGateway; "Bad Gateway"
0x180004a6a  mov     rax, [rcx+18h]
0x180004a6e  mov     rcx, r10
0x180004a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a76  mov     rcx, [rsi]
0x180004a79  mov     rax, [rcx]
0x180004a7c  mov     rax, [rax+110h]
0x180004a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a88  mov     r8, rax
0x180004a8b  lea     rbx, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004a92  xorps   xmm0, xmm0
0x180004a95  mov     [rsp+1A0h+var_158], rbx
0x180004a9a  lea     rdx, [rsp+1A0h+var_158]
0x180004a9f  mov     rcx, [rax]
0x180004aa2  movdqu  [rsp+1A0h+var_150], xmm0
0x180004aa8  mov     rax, [rcx]
0x180004aab  mov     rcx, r8
0x180004aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab3  test    eax, eax
0x180004ab5  js      loc_180004D32
0x180004abb  cmp     dword ptr [rsp+1A0h+var_150+8], r13d
0x180004ac0  jz      loc_180004D32
0x180004ac6  cmp     dword ptr [rsp+1A0h+var_150+4], r12d
0x180004acb  jb      loc_180004D32
0x180004ad1  cmp     dword ptr [rsp+1A0h+var_150], 20h ; ' '
0x180004ad6  jz      short loc_180004AE3
0x180004ad8  test    byte ptr [rsp+1A0h+var_150], 20h
0x180004add  jz      loc_180004D32
0x180004ae3  mov     rcx, [rsi]
0x180004ae6  mov     rax, [rcx]
0x180004ae9  mov     rax, [rax+110h]
0x180004af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004af5  mov     r8, rax
0x180004af8  mov     [rsp+1A0h+var_128], 20h ; ' '
0x180004b01  xor     eax, eax
0x180004b03  mov     [rbp+0A0h+var_118], r12
0x180004b07  mov     [rbp+0A0h+var_E4], rax
0x180004b0b  lea     rcx, ?AreaGuid@?1??GetAreaGuid@IISCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180004b12  mov     [rbp+0A0h+var_DC], eax
0x180004b15  lea     rax, aCgiTimeout; "CGI_TIMEOUT"
0x180004b1c  mov     [rbp+0A0h+var_110], rax
0x180004b20  mov     eax, 1
0x180004b25  mov     [rbp+0A0h+var_108], eax
0x180004b28  xorps   xmm0, xmm0
0x180004b2b  mov     [rbp+0A0h+var_EC], eax
0x180004b2e  lea     rax, aContextid; "ContextId"
0x180004b35  mov     [rbp+0A0h+var_C0], rax
0x180004b39  lea     rax, aHeaders; "Headers"
0x180004b40  mov     [rbp+0A0h+var_98], rax
0x180004b44  mov     [rsp+1A0h+var_130], rbx
0x180004b49  mov     [rbp+0A0h+var_120], rcx
0x180004b4d  mov     [rbp+0A0h+var_104], r12d
0x180004b51  mov     [rbp+0A0h+var_E8], 2
0x180004b58  movdqa  [rbp+0A0h+var_100], xmm0
0x180004b5d  mov     [rbp+0A0h+var_F0], r13d
0x180004b61  mov     [rbp+0A0h+var_B8], 48h ; 'H'
0x180004b68  mov     [rbp+0A0h+var_B0], r13
0x180004b6c  mov     [rbp+0A0h+var_A8], 10h
0x180004b73  mov     [rbp+0A0h+var_A0], r13
0x180004b77  mov     [rbp+0A0h+var_90], 1Eh
0x180004b7e  mov     [rbp+0A0h+var_88], r14
0x180004b82  test    r14, r14
0x180004b85  jz      loc_180004CFB
0x180004b8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004b8f  inc     rax
0x180004b92  cmp     [r14+rax], r13b
0x180004b96  jnz     short loc_180004B8F
0x180004b98  jmp     loc_180004D0D
0x180004b9d  lea     rsi, [rdi+30h]
0x180004ba1  mov     rcx, [rsi]
0x180004ba4  mov     rax, [rcx]
0x180004ba7  mov     rax, [rax+20h]
0x180004bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb0  mov     r10, rax
0x180004bb3  mov     [rsp+1A0h+var_170], r13d
0x180004bb8  mov     [rsp+1A0h+var_178], r13
0x180004bbd  lea     r8, aBadGateway; "Bad Gateway"
0x180004bc4  mov     edx, 1F6h
0x180004bc9  mov     r9d, 2
0x180004bcf  mov     rcx, [rax]
0x180004bd2  mov     rax, [rcx+18h]
0x180004bd6  mov     ecx, [rsp+1A0h+ExitCode]
0x180004bda  mov     dword ptr [rsp+1A0h+var_180], ecx
0x180004bde  mov     rcx, r10
0x180004be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be6  mov     rcx, [rsi]
0x180004be9  mov     rax, [rcx]
0x180004bec  mov     rax, [rax+110h]
0x180004bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf8  mov     r8, rax
0x180004bfb  lea     rbx, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180004c02  xorps   xmm0, xmm0
0x180004c05  mov     [rsp+1A0h+var_158], rbx
0x180004c0a  lea     rdx, [rsp+1A0h+var_158]
0x180004c0f  mov     rcx, [rax]
0x180004c12  movdqu  [rsp+1A0h+var_150], xmm0
0x180004c18  mov     rax, [rcx]
0x180004c1b  mov     rcx, r8
0x180004c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c23  test    eax, eax
0x180004c25  js      loc_180004D32
0x180004c2b  cmp     dword ptr [rsp+1A0h+var_150+8], r13d
0x180004c30  jz      loc_180004D32
0x180004c36  cmp     dword ptr [rsp+1A0h+var_150+4], r12d
0x180004c3b  jb      loc_180004D32
0x180004c41  cmp     dword ptr [rsp+1A0h+var_150], 20h ; ' '
0x180004c46  jz      short loc_180004C53
0x180004c48  test    byte ptr [rsp+1A0h+var_150], 20h
0x180004c4d  jz      loc_180004D32
0x180004c53  mov     rcx, [rsi]
0x180004c56  mov     rax, [rcx]
0x180004c59  mov     rax, [rax+110h]
0x180004c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c65  mov     r8, rax
0x180004c68  mov     [rsp+1A0h+var_128], 20h ; ' '
0x180004c71  xor     eax, eax
0x180004c73  mov     [rbp+0A0h+var_118], 5
0x180004c7b  mov     [rbp+0A0h+var_E4], rax
0x180004c7f  lea     rcx, ?AreaGuid@?1??GetAreaGuid@IISCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180004c86  mov     [rbp+0A0h+var_DC], eax
0x180004c89  lea     rax, aCgiPrematureTe; "CGI_PREMATURE_TERMINATION"
0x180004c90  mov     [rbp+0A0h+var_110], rax
0x180004c94  mov     eax, 1
0x180004c99  mov     [rbp+0A0h+var_108], eax
0x180004c9c  xorps   xmm0, xmm0
0x180004c9f  mov     [rbp+0A0h+var_EC], eax
0x180004ca2  lea     rax, aContextid; "ContextId"
0x180004ca9  mov     [rbp+0A0h+var_C0], rax
0x180004cad  lea     rax, aHeaders; "Headers"
0x180004cb4  mov     [rbp+0A0h+var_98], rax
0x180004cb8  mov     [rsp+1A0h+var_130], rbx
0x180004cbd  mov     [rbp+0A0h+var_120], rcx
0x180004cc1  mov     [rbp+0A0h+var_104], r12d
0x180004cc5  mov     [rbp+0A0h+var_E8], 2
0x180004ccc  movdqa  [rbp+0A0h+var_100], xmm0
0x180004cd1  mov     [rbp+0A0h+var_F0], r13d
0x180004cd5  mov     [rbp+0A0h+var_B8], 48h ; 'H'
0x180004cdc  mov     [rbp+0A0h+var_B0], r13
0x180004ce0  mov     [rbp+0A0h+var_A8], 10h
0x180004ce7  mov     [rbp+0A0h+var_A0], r13
0x180004ceb  mov     [rbp+0A0h+var_90], 1Eh
0x180004cf2  mov     [rbp+0A0h+var_88], r14
0x180004cf6  test    r14, r14
0x180004cf9  jnz     short loc_180004D00
0x180004cfb  mov     eax, r13d
0x180004cfe  jmp     short loc_180004D0F
0x180004d00  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d04  inc     rax
0x180004d07  cmp     [r14+rax], r13b
0x180004d0b  jnz     short loc_180004D04
0x180004d0d  inc     eax
  ... truncated ...
```
