# StartLogging(_TRACE_INFO const *,ushort const *)

- ea: `0x1401b21b8`
- end: `0x1401b23da`
- name: `?StartLogging@@YAJPEBU_TRACE_INFO@@PEBG@Z`
- size: `546`
- prototype: `__int64 __fastcall(const struct _TRACE_INFO *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400a3f04`

## callees

- `0x14001c330`
- `0x14010e160`
- `0x14010ed90`
- `0x1401b21b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1401b22e4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1401b23af`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1401b22e4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1401b23af`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1401b223a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1401b223a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1401b226a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1401b226a`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x1401b228e`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x1401b228e`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectory` at `0x1401b2254`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectory` at `0x1401b2254`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x1401b239f`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x1401b239f`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1401b2370`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1401b2370`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1401b22ba`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1401b2301`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1401b22ba`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1401b2301`

## pseudocode

```c
__int64 __fastcall StartLogging(const struct _TRACE_INFO *a1, const unsigned __int16 *a2)
{
  int Error; // ebx
  signed int started; // eax
  signed int v4; // eax
  __int64 v5; // rdi
  signed int v6; // eax
  ULONG64 TraceHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[524]; // [rsp+C8h] [rbp-38h] BYREF

  memset_0(&Properties, 0, 0x488u);
  Properties.Wnode.BufferSize = 1160;
  Properties.Wnode.Flags = 0x20000;
  Error = -2147467259;
  Properties.BufferSize = 8;
  Properties.LogFileMode = 133121;
  Properties.LogFileNameOffset = 120;
  Properties.LoggerNameOffset = 640;
  if ( (unsigned int)SHExpandEnvironmentStringsW(L"%LocalAppData%\\Microsoft\\Windows\\Explorer", pszPath, 260) )
  {
    SHCreateDirectory(0, pszPath);
    Error = PathCchAppend(pszPath, 0x104u, L"ExplorerStartupLog");
    if ( Error >= 0 )
    {
      Error = PathCchAddExtension(pszPath, 0x104u, L".etl");
      if ( Error >= 0 )
      {
        TraceHandle[0] = 0;
        started = StartTraceW(TraceHandle, L"ExplorerStartupLog", &Properties);
        Error = started;
        if ( started > 0 )
          Error = (unsigned __int16)started | 0x80070000;
        if ( Error == -2147024809 )
        {
          if ( DeleteFileW(pszPath) )
          {
            v4 = StartTraceW(TraceHandle, L"ExplorerStartupLog", &Properties);
            Error = v4;
            if ( v4 > 0 )
              Error = (unsigned __int16)v4 | 0x80070000;
          }
          else
          {
            Error = ResultFromKnownLastError();
          }
        }
        if ( Error >= 0 )
        {
          v5 = 0;
          while ( Error >= 0 )
          {
            v6 = EnableTraceEx2(
                   TraceHandle[0],
                   (LPCGUID)&qword_14024EF60[3 * v5],
                   1u,
                   4u,
                   qword_14024EF60[3 * v5 + 2],
                   0,
                   0,
                   0);
            Error = v6;
            if ( v6 > 0 )
              Error = (unsigned __int16)v6 | 0x80070000;
            v5 = (unsigned int)(v5 + 1);
            if ( (_DWORD)v5 )
            {
              if ( Error >= 0 )
                return (unsigned int)Error;
              break;
            }
          }
          StopTraceW(TraceHandle[0], 0, &Properties);
          DeleteFileW(pszPath);
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1401b21b8  push    rbp
0x1401b21ba  push    rbx
0x1401b21bb  push    rdi
0x1401b21bc  push    r14
0x1401b21be  lea     rbp, [rsp-3F8h]
0x1401b21c6  sub     rsp, 4F8h
0x1401b21cd  mov     rax, cs:__security_cookie
0x1401b21d4  xor     rax, rsp
0x1401b21d7  mov     [rbp+410h+var_30], rax
0x1401b21de  mov     ebx, 488h
0x1401b21e3  lea     rcx, [rsp+510h+Properties]; void *
0x1401b21e8  mov     r8d, ebx; Size
0x1401b21eb  xor     edx, edx; Val
0x1401b21ed  call    memset_0
0x1401b21f2  mov     rcx, cs:off_1401DD688; "%LocalAppData%\\Microsoft\\Windows\\Exp"...
0x1401b21f9  lea     rdx, [rbp+410h+pszPath]
0x1401b21fd  mov     rdi, cs:InstanceName
0x1401b2204  mov     r14d, 104h
0x1401b220a  mov     [rsp+510h+Properties.Wnode.BufferSize], ebx
0x1401b220e  mov     r8d, r14d
0x1401b2211  mov     [rsp+510h+Properties.Wnode.Flags], 20000h
0x1401b2219  mov     ebx, 80004005h
0x1401b221e  mov     [rbp+410h+Properties.BufferSize], 8
0x1401b2225  mov     [rbp+410h+Properties.LogFileMode], 20801h
0x1401b222c  mov     [rbp+410h+Properties.LogFileNameOffset], 78h ; 'x'
0x1401b2233  mov     [rbp+410h+Properties.LoggerNameOffset], 280h
0x1401b223a  call    cs:__imp_SHExpandEnvironmentStringsW
0x1401b2241  nop     dword ptr [rax+rax+00h]
0x1401b2246  test    eax, eax
0x1401b2248  jz      loc_1401B23BB
0x1401b224e  lea     rdx, [rbp+410h+pszPath]; pszPath
0x1401b2252  xor     ecx, ecx; hwnd
0x1401b2254  call    cs:__imp_SHCreateDirectory
0x1401b225b  nop     dword ptr [rax+rax+00h]
0x1401b2260  mov     r8, rdi; pszMore
0x1401b2263  lea     rcx, [rbp+410h+pszPath]; pszPath
0x1401b2267  mov     edx, r14d; cchPath
0x1401b226a  call    cs:__imp_PathCchAppend
0x1401b2271  nop     dword ptr [rax+rax+00h]
0x1401b2276  mov     ebx, eax
0x1401b2278  test    eax, eax
0x1401b227a  js      loc_1401B23BB
0x1401b2280  lea     r8, pszExt; ".etl"
0x1401b2287  mov     edx, r14d; cchPath
0x1401b228a  lea     rcx, [rbp+410h+pszPath]; pszPath
0x1401b228e  call    cs:__imp_PathCchAddExtension
0x1401b2295  nop     dword ptr [rax+rax+00h]
0x1401b229a  mov     ebx, eax
0x1401b229c  test    eax, eax
0x1401b229e  js      loc_1401B23BB
0x1401b22a4  lea     r8, [rsp+510h+Properties]; Properties
0x1401b22a9  mov     [rsp+510h+TraceHandle], 0
0x1401b22b2  mov     rdx, rdi; InstanceName
0x1401b22b5  lea     rcx, [rsp+510h+TraceHandle]; TraceHandle
0x1401b22ba  call    cs:__imp_StartTraceW
0x1401b22c1  nop     dword ptr [rax+rax+00h]
0x1401b22c6  mov     ebx, eax
0x1401b22c8  mov     r14d, 80070000h
0x1401b22ce  test    eax, eax
0x1401b22d0  jle     short loc_1401B22D8
0x1401b22d2  movzx   ebx, ax
0x1401b22d5  or      ebx, r14d
0x1401b22d8  cmp     ebx, 80070057h
0x1401b22de  jnz     short loc_1401B2322
0x1401b22e0  lea     rcx, [rbp+410h+pszPath]; lpFileName
0x1401b22e4  call    cs:__imp_DeleteFileW
0x1401b22eb  nop     dword ptr [rax+rax+00h]
0x1401b22f0  test    eax, eax
0x1401b22f2  jz      short loc_1401B231B
0x1401b22f4  lea     r8, [rsp+510h+Properties]; Properties
0x1401b22f9  mov     rdx, rdi; InstanceName
0x1401b22fc  lea     rcx, [rsp+510h+TraceHandle]; TraceHandle
0x1401b2301  call    cs:__imp_StartTraceW
0x1401b2308  nop     dword ptr [rax+rax+00h]
0x1401b230d  mov     ebx, eax
0x1401b230f  test    eax, eax
0x1401b2311  jle     short loc_1401B2322
0x1401b2313  movzx   ebx, ax
0x1401b2316  or      ebx, r14d
0x1401b2319  jmp     short loc_1401B2322
0x1401b231b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b2320  mov     ebx, eax
0x1401b2322  test    ebx, ebx
0x1401b2324  js      loc_1401B23BB
0x1401b232a  xor     edi, edi
0x1401b232c  test    ebx, ebx
0x1401b232e  js      short loc_1401B2393
0x1401b2330  mov     rax, cs:off_1401DD698
0x1401b2337  lea     rcx, [rdi+rdi*2]
0x1401b233b  mov     [rsp+510h+EnableParameters], 0; EnableParameters
0x1401b2344  mov     r9b, 4; Level
0x1401b2347  mov     [rsp+510h+Timeout], 0; Timeout
0x1401b234f  mov     r8d, 1; ControlCode
0x1401b2355  mov     [rsp+510h+MatchAllKeyword], 0; MatchAllKeyword
0x1401b235e  lea     rdx, [rax+rcx*8]; ProviderId
0x1401b2362  mov     rcx, [rsp+510h+TraceHandle]; TraceHandle
0x1401b2367  mov     rax, [rdx+10h]
0x1401b236b  mov     [rsp+510h+MatchAnyKeyword], rax; MatchAnyKeyword
0x1401b2370  call    cs:__imp_EnableTraceEx2
0x1401b2377  nop     dword ptr [rax+rax+00h]
0x1401b237c  mov     ebx, eax
0x1401b237e  test    eax, eax
0x1401b2380  jle     short loc_1401B2388
0x1401b2382  movzx   ebx, ax
0x1401b2385  or      ebx, r14d
0x1401b2388  inc     edi
0x1401b238a  cmp     edi, 1
0x1401b238d  jb      short loc_1401B232C
0x1401b238f  test    ebx, ebx
0x1401b2391  jns     short loc_1401B23BB
0x1401b2393  mov     rcx, [rsp+510h+TraceHandle]; TraceHandle
0x1401b2398  lea     r8, [rsp+510h+Properties]; Properties
0x1401b239d  xor     edx, edx; InstanceName
0x1401b239f  call    cs:__imp_StopTraceW
0x1401b23a6  nop     dword ptr [rax+rax+00h]
0x1401b23ab  lea     rcx, [rbp+410h+pszPath]; lpFileName
0x1401b23af  call    cs:__imp_DeleteFileW
0x1401b23b6  nop     dword ptr [rax+rax+00h]
0x1401b23bb  mov     eax, ebx
0x1401b23bd  mov     rcx, [rbp+410h+var_30]
0x1401b23c4  xor     rcx, rsp; StackCookie
0x1401b23c7  call    __security_check_cookie
0x1401b23cc  add     rsp, 4F8h
0x1401b23d3  pop     r14
0x1401b23d5  pop     rdi
0x1401b23d6  pop     rbx
0x1401b23d7  pop     rbp
0x1401b23d8  retn
```
