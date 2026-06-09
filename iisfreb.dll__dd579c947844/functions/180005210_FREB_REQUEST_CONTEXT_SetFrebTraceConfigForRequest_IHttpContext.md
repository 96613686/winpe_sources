# FREB_REQUEST_CONTEXT::SetFrebTraceConfigForRequest(IHttpContext *)

- ea: `0x180005210`
- end: `0x18000539e`
- name: `?SetFrebTraceConfigForRequest@FREB_REQUEST_CONTEXT@@QEAAJPEAVIHttpContext@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(FREB_REQUEST_CONTEXT *__hidden this, struct IHttpContext *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800023cc`
- `0x180002798`

## callees

- `0x180005210`
- `0x180009734`
- `0x18000a6a8`
- `0x18000ac90`
- `0x18000b010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800052fe`
- `iisutil!PuDbgPrint` at `0x1800052fe`
- `iisutil!PuDbgPrintError` at `0x180005370`
- `iisutil!PuDbgPrintError` at `0x180005370`

## string_xrefs

- `0x1800052c2`: `FREB_REQUEST_CONTEXT::SetFrebTraceConfigForRequest`
- `0x180005358`: `FREB_REQUEST_CONTEXT::SetFrebTraceConfigForRequest`
- `0x1800052d0`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_request_context.cxx`
- `0x180005369`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_request_context.cxx`
- `0x18000534c`: `SetTraceConfiguration() failed\n`

## pseudocode

```c
__int64 __fastcall FREB_REQUEST_CONTEXT::SetFrebTraceConfigForRequest(
        FREB_REQUEST_CONTEXT *this,
        struct IHttpContext *a2)
{
  __int64 v3; // rax
  __int64 v4; // rsi
  __int64 v5; // r15
  unsigned int v6; // ebx
  unsigned int v7; // esi
  __int64 v8; // rdi
  __int64 v9; // rbx
  const struct _GUID *v10; // rcx
  int v11; // eax
  FREB_LOG_NT_EVENT_TABLE *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-58h] BYREF
  char v15[40]; // [rsp+48h] [rbp-50h] BYREF

  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
  v4 = *((_QWORD *)this + 10);
  v5 = v3;
  if ( v4 )
  {
    v7 = *(_DWORD *)(v4 + 216);
    v6 = 0;
    v8 = 0;
    if ( v7 )
    {
      while ( 1 )
      {
        v9 = *(_QWORD *)(*((_QWORD *)this + 10) + 208LL) + 40 * v8;
        if ( g_dwDebugFlags < 0 )
        {
          v10 = *(const struct _GUID **)v9;
          v14 = 39;
          if ( (int)FREB_XML_SERIALIZER::ConvertCLSIDToString(v10, v15, &v14) < 0 )
            strcpy(v15, "?");
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_request_context.cxx",
              235,
              "FREB_REQUEST_CONTEXT::SetFrebTraceConfigForRequest",
              "Freb: enable tracing for the current request -provider:%s, area:%d, verbosity:%d\n",
              v15,
              *(_DWORD *)(v9 + 8),
              *(_DWORD *)(v9 + 12));
        }
        v11 = (*(__int64 (__fastcall **)(__int64, void *, __int64, __int64))(*(_QWORD *)v5 + 8LL))(
                v5,
                g_pModuleContext,
                v9,
                1);
        v6 = v11;
        if ( v11 < 0 )
          break;
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= v7 )
          return v6;
      }
      FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(v12, v11);
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_request_context.cxx",
          248,
          "FREB_REQUEST_CONTEXT::SetFrebTraceConfigForRequest",
          v6,
          "SetTraceConfiguration() failed\n");
    }
  }
  else
  {
    return (unsigned int)-2147024883;
  }
  return v6;
}

```

## disassembly

```asm
0x180005210  mov     [rsp+arg_10], rbx
0x180005215  mov     [rsp+arg_18], rsi
0x18000521a  push    rdi
0x18000521b  push    r14
0x18000521d  push    r15
0x18000521f  sub     rsp, 80h
0x180005226  mov     rax, cs:__security_cookie
0x18000522d  xor     rax, rsp
0x180005230  mov     [rsp+98h+var_28], rax
0x180005235  mov     rax, [rdx]
0x180005238  mov     r14, rcx
0x18000523b  mov     rcx, rdx
0x18000523e  mov     rax, [rax+110h]
0x180005245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000524a  mov     rsi, [r14+50h]
0x18000524e  mov     r15, rax
0x180005251  test    rsi, rsi
0x180005254  jnz     short loc_180005260
0x180005256  mov     ebx, 8007000Dh
0x18000525b  jmp     loc_180005376
0x180005260  mov     esi, [rsi+0D8h]
0x180005266  xor     ebx, ebx
0x180005268  xor     edi, edi
0x18000526a  test    esi, esi
0x18000526c  jz      loc_180005376
0x180005272  test    cs:g_dwDebugFlags, 80000000h
0x18000527c  lea     rdx, [rdi+rdi*4]
0x180005280  mov     rax, [r14+50h]
0x180005284  mov     rcx, [rax+0D0h]
0x18000528b  lea     rbx, [rcx+rdx*8]
0x18000528f  jz      short loc_180005304
0x180005291  mov     rcx, [rbx]; struct _GUID *
0x180005294  lea     r8, [rsp+98h+var_58]; unsigned int *
0x180005299  lea     rdx, [rsp+98h+var_50]; char *
0x18000529e  mov     [rsp+98h+var_58], 27h ; '''
0x1800052a6  call    ?ConvertCLSIDToString@FREB_XML_SERIALIZER@@SAJPEBU_GUID@@PEADPEAK@Z; FREB_XML_SERIALIZER::ConvertCLSIDToString(_GUID const *,char *,ulong *)
0x1800052ab  test    eax, eax
0x1800052ad  jns     short loc_1800052B6
0x1800052af  mov     word ptr [rsp+98h+var_50], 3Fh ; '?'
0x1800052b6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800052bd  jz      short loc_180005304
0x1800052bf  mov     eax, [rbx+0Ch]
0x1800052c2  lea     r9, aFrebRequestCon_1; "FREB_REQUEST_CONTEXT::SetFrebTraceConfi"...
0x1800052c9  mov     rcx, cs:g_pDebug
0x1800052d0  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800052d7  mov     [rsp+98h+var_60], eax
0x1800052db  mov     r8d, 0EBh
0x1800052e1  mov     eax, [rbx+8]
0x1800052e4  mov     [rsp+98h+var_68], eax
0x1800052e8  lea     rax, [rsp+98h+var_50]
0x1800052ed  mov     [rsp+98h+var_70], rax
0x1800052f2  lea     rax, aFrebEnableTrac; "Freb: enable tracing for the current re"...
0x1800052f9  mov     [rsp+98h+var_78], rax
0x1800052fe  call    cs:__imp_PuDbgPrint
0x180005304  mov     rax, [r15]
0x180005307  mov     r9d, 1
0x18000530d  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180005314  mov     r8, rbx
0x180005317  mov     rcx, r15
0x18000531a  mov     rax, [rax+8]
0x18000531e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005323  mov     ebx, eax
0x180005325  test    eax, eax
0x180005327  js      short loc_180005335
0x180005329  inc     edi
0x18000532b  cmp     edi, esi
0x18000532d  jb      loc_180005272
0x180005333  jmp     short loc_180005376
0x180005335  mov     edx, ebx; int
0x180005337  call    ?LogEventFrebRuntimeError@FREB_LOG_NT_EVENT_TABLE@@QEAAXJ@Z; FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(long)
0x18000533c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005343  jz      short loc_180005376
0x180005345  mov     rcx, cs:g_pDebug
0x18000534c  lea     rax, aSettraceconfig; "SetTraceConfiguration() failed\n"
0x180005353  mov     [rsp+98h+var_70], rax
0x180005358  lea     r9, aFrebRequestCon_1; "FREB_REQUEST_CONTEXT::SetFrebTraceConfi"...
0x18000535f  mov     r8d, 0F8h
0x180005365  mov     dword ptr [rsp+98h+var_78], ebx
0x180005369  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005370  call    cs:__imp_PuDbgPrintError
0x180005376  mov     eax, ebx
0x180005378  mov     rcx, [rsp+98h+var_28]
0x18000537d  xor     rcx, rsp; StackCookie
0x180005380  call    __security_check_cookie
0x180005385  lea     r11, [rsp+98h+var_18]
0x18000538d  mov     rbx, [r11+30h]
0x180005391  mov     rsi, [r11+38h]
0x180005395  mov     rsp, r11
0x180005398  pop     r15
0x18000539a  pop     r14
0x18000539c  pop     rdi
0x18000539d  retn
```
