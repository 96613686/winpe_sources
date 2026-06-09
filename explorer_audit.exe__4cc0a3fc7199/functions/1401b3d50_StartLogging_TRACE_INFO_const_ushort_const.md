# StartLogging(_TRACE_INFO const *,ushort const *)

- ea: `0x1401b3d50`
- end: `0x1401b3f31`
- name: `?StartLogging@@YAJPEBU_TRACE_INFO@@PEBG@Z`
- size: `481`
- prototype: `__int64 __fastcall(const struct _TRACE_INFO *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14009ae00`

## callees

- `0x140016b10`
- `0x1401040e0`
- `0x140104ce0`
- `0x1401b3d50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1401b3e5e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1401b3f0d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1401b3e5e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1401b3f0d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1401b3dd2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1401b3dd2`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x1401b3e14`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x1401b3e14`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1401b3df6`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1401b3df6`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectory` at `0x1401b3de6`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectory` at `0x1401b3de6`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1401b3eda`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1401b3eda`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x1401b3f03`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x1401b3f03`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1401b3e3a`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1401b3e75`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1401b3e3a`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1401b3e75`

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
                   (LPCGUID)((char *)&unk_140252E50 + 24 * v5),
                   1u,
                   4u,
                   *((_QWORD *)&unk_140252E50 + 3 * v5 + 2),
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
0x1401b3d50  push    rbp
0x1401b3d52  push    rbx
0x1401b3d53  push    rdi
0x1401b3d54  push    r14
0x1401b3d56  lea     rbp, [rsp-3F8h]
0x1401b3d5e  sub     rsp, 4F8h
0x1401b3d65  mov     rax, cs:__security_cookie
0x1401b3d6c  xor     rax, rsp
0x1401b3d6f  mov     [rbp+410h+var_30], rax
0x1401b3d76  mov     ebx, 488h
0x1401b3d7b  lea     rcx, [rsp+510h+Properties]; void *
0x1401b3d80  mov     r8d, ebx; Size
0x1401b3d83  xor     edx, edx; Val
0x1401b3d85  call    memset_0
0x1401b3d8a  mov     rcx, cs:off_1401DF5E8; "%LocalAppData%\\Microsoft\\Windows\\Exp"...
0x1401b3d91  lea     rdx, [rbp+410h+pszPath]
0x1401b3d95  mov     rdi, cs:InstanceName
0x1401b3d9c  mov     r14d, 104h
0x1401b3da2  mov     [rsp+510h+Properties.Wnode.BufferSize], ebx
0x1401b3da6  mov     r8d, r14d
0x1401b3da9  mov     [rsp+510h+Properties.Wnode.Flags], 20000h
0x1401b3db1  mov     ebx, 80004005h
0x1401b3db6  mov     [rbp+410h+Properties.BufferSize], 8
0x1401b3dbd  mov     [rbp+410h+Properties.LogFileMode], 20801h
0x1401b3dc4  mov     [rbp+410h+Properties.LogFileNameOffset], 78h ; 'x'
0x1401b3dcb  mov     [rbp+410h+Properties.LoggerNameOffset], 280h
0x1401b3dd2  call    cs:__imp_SHExpandEnvironmentStringsW
0x1401b3dd8  test    eax, eax
0x1401b3dda  jz      loc_1401B3F13
0x1401b3de0  lea     rdx, [rbp+410h+pszPath]; pszPath
0x1401b3de4  xor     ecx, ecx; hwnd
0x1401b3de6  call    cs:__imp_SHCreateDirectory
0x1401b3dec  mov     r8, rdi; pszMore
0x1401b3def  lea     rcx, [rbp+410h+pszPath]; pszPath
0x1401b3df3  mov     edx, r14d; cchPath
0x1401b3df6  call    cs:__imp_PathCchAppend
0x1401b3dfc  mov     ebx, eax
0x1401b3dfe  test    eax, eax
0x1401b3e00  js      loc_1401B3F13
0x1401b3e06  lea     r8, pszExt; ".etl"
0x1401b3e0d  mov     edx, r14d; cchPath
0x1401b3e10  lea     rcx, [rbp+410h+pszPath]; pszPath
0x1401b3e14  call    cs:__imp_PathCchAddExtension
0x1401b3e1a  mov     ebx, eax
0x1401b3e1c  test    eax, eax
0x1401b3e1e  js      loc_1401B3F13
0x1401b3e24  lea     r8, [rsp+510h+Properties]; Properties
0x1401b3e29  mov     [rsp+510h+TraceHandle], 0
0x1401b3e32  mov     rdx, rdi; InstanceName
0x1401b3e35  lea     rcx, [rsp+510h+TraceHandle]; TraceHandle
0x1401b3e3a  call    cs:__imp_StartTraceW
0x1401b3e40  mov     ebx, eax
0x1401b3e42  mov     r14d, 80070000h
0x1401b3e48  test    eax, eax
0x1401b3e4a  jle     short loc_1401B3E52
0x1401b3e4c  movzx   ebx, ax
0x1401b3e4f  or      ebx, r14d
0x1401b3e52  cmp     ebx, 80070057h
0x1401b3e58  jnz     short loc_1401B3E90
0x1401b3e5a  lea     rcx, [rbp+410h+pszPath]; lpFileName
0x1401b3e5e  call    cs:__imp_DeleteFileW
0x1401b3e64  test    eax, eax
0x1401b3e66  jz      short loc_1401B3E89
0x1401b3e68  lea     r8, [rsp+510h+Properties]; Properties
0x1401b3e6d  mov     rdx, rdi; InstanceName
0x1401b3e70  lea     rcx, [rsp+510h+TraceHandle]; TraceHandle
0x1401b3e75  call    cs:__imp_StartTraceW
0x1401b3e7b  mov     ebx, eax
0x1401b3e7d  test    eax, eax
0x1401b3e7f  jle     short loc_1401B3E90
0x1401b3e81  movzx   ebx, ax
0x1401b3e84  or      ebx, r14d
0x1401b3e87  jmp     short loc_1401B3E90
0x1401b3e89  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1401b3e8e  mov     ebx, eax
0x1401b3e90  test    ebx, ebx
0x1401b3e92  js      short loc_1401B3F13
0x1401b3e94  xor     edi, edi
0x1401b3e96  test    ebx, ebx
0x1401b3e98  js      short loc_1401B3EF7
0x1401b3e9a  mov     rax, cs:off_1401DF5F8
0x1401b3ea1  lea     rcx, [rdi+rdi*2]
0x1401b3ea5  mov     [rsp+510h+EnableParameters], 0; EnableParameters
0x1401b3eae  mov     r9b, 4; Level
0x1401b3eb1  mov     [rsp+510h+Timeout], 0; Timeout
0x1401b3eb9  mov     r8d, 1; ControlCode
0x1401b3ebf  mov     [rsp+510h+MatchAllKeyword], 0; MatchAllKeyword
0x1401b3ec8  lea     rdx, [rax+rcx*8]; ProviderId
0x1401b3ecc  mov     rcx, [rsp+510h+TraceHandle]; TraceHandle
0x1401b3ed1  mov     rax, [rdx+10h]
0x1401b3ed5  mov     [rsp+510h+MatchAnyKeyword], rax; MatchAnyKeyword
0x1401b3eda  call    cs:__imp_EnableTraceEx2
0x1401b3ee0  mov     ebx, eax
0x1401b3ee2  test    eax, eax
0x1401b3ee4  jle     short loc_1401B3EEC
0x1401b3ee6  movzx   ebx, ax
0x1401b3ee9  or      ebx, r14d
0x1401b3eec  inc     edi
0x1401b3eee  cmp     edi, 1
0x1401b3ef1  jb      short loc_1401B3E96
0x1401b3ef3  test    ebx, ebx
0x1401b3ef5  jns     short loc_1401B3F13
0x1401b3ef7  mov     rcx, [rsp+510h+TraceHandle]; TraceHandle
0x1401b3efc  lea     r8, [rsp+510h+Properties]; Properties
0x1401b3f01  xor     edx, edx; InstanceName
0x1401b3f03  call    cs:__imp_StopTraceW
0x1401b3f09  lea     rcx, [rbp+410h+pszPath]; lpFileName
0x1401b3f0d  call    cs:__imp_DeleteFileW
0x1401b3f13  mov     eax, ebx
0x1401b3f15  mov     rcx, [rbp+410h+var_30]
0x1401b3f1c  xor     rcx, rsp; StackCookie
0x1401b3f1f  call    __security_check_cookie
0x1401b3f24  add     rsp, 4F8h
0x1401b3f2b  pop     r14
0x1401b3f2d  pop     rdi
0x1401b3f2e  pop     rbx
0x1401b3f2f  pop     rbp
0x1401b3f30  retn
```
