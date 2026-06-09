# CPolicyCriticalSection::InitializeLockTrackingContext(_POLICY_SECTION_CONTEXT *,ulong)

- ea: `0x180092b90`
- end: `0x180092e0a`
- name: `?InitializeLockTrackingContext@CPolicyCriticalSection@@CAXPEAU_POLICY_SECTION_CONTEXT@@K@Z`
- size: `634`
- prototype: `void __fastcall(struct _POLICY_SECTION_CONTEXT *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000bbe0`

## callees

- `0x180075ec0`
- `0x18007d320`
- `0x18007de08`
- `0x180092b90`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180092cbf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180092d63`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180092cbf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180092d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092d35`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180092d79`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180092d79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180092d90`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180092c17`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180092c34`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180092c17`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180092c34`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180092bbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180092bbf`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180092bf6`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180092bf6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180092ce0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180092ce0`

## string_xrefs

- `0x180092c64`: `InitializeLockTrackingContext: OpenProcess failed for PID:0x%x - Error 0x%x`
- `0x180092c9b`: `InitializeLockTrackingContext: OpenProcess failed for PID:0x%x - Error 0x%x`
- `0x180092cb8`: `OpenProcessFailed`

## pseudocode

```c
void __fastcall CPolicyCriticalSection::InitializeLockTrackingContext(struct _POLICY_SECTION_CONTEXT *a1, int a2)
{
  unsigned int v4; // eax
  DWORD v5; // r8d
  HANDLE v6; // rdi
  void (*v7)(unsigned int, const unsigned __int16 *, ...); // rdi
  DWORD v8; // eax
  DWORD v9; // eax
  void (*v10)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD LastError; // eax
  DWORD v12; // eax
  DWORD v13; // ecx
  DWORD pSessionId; // [rsp+30h] [rbp-B8h] BYREF
  DWORD dwSize[3]; // [rsp+34h] [rbp-B4h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v17[56]; // [rsp+48h] [rbp-A0h] BYREF
  DWORD dwProcessId; // [rsp+80h] [rbp-68h]

  if ( a1 )
  {
    GetSystemTimeAsFileTime((LPFILETIME)a1 + 4);
    if ( (a2 & 0x20000000) != 0 )
    {
      memset_0(v17, 0, 0x68u);
      RpcCallAttributes[0] = 3;
      RpcCallAttributes[1] = 16;
      v4 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
      if ( v4 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"InitializeLockTrackingContext: RpcServerInqCallAttributesW failed: 0x%x", v4);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"InitializeLockTrackingContext: RpcServerInqCallAttributesW failed: 0x%x", v4);
          }
        }
      }
      else
      {
        v5 = dwProcessId;
        *((_DWORD *)a1 + 12) = dwProcessId;
        v6 = OpenProcess(0x400u, 0, v5);
        if ( v6 || (v6 = OpenProcess(0x1000u, 0, *((_DWORD *)a1 + 12))) != 0 )
        {
          dwSize[0] = 260;
          if ( !QueryFullProcessImageNameW(v6, 0, (LPWSTR)a1 + 26, dwSize) )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              v10 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                LastError = GetLastError();
                v10(
                  2u,
                  L"InitializeLockTrackingContext: QueryFullProcessImageName failed for PID:0x%x - Error 0x%x",
                  *((unsigned int *)a1 + 12),
                  LastError);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                v12 = GetLastError();
                RedirectDebugMsg(
                  2u,
                  L"InitializeLockTrackingContext: QueryFullProcessImageName failed for PID:0x%x - Error 0x%x",
                  *((unsigned int *)a1 + 12),
                  v12);
              }
            }
            _o_wcscpy_s((char *)a1 + 52, 260, L"QueryProcessNameFailed");
          }
          v13 = *((_DWORD *)a1 + 12);
          pSessionId = 0;
          if ( ProcessIdToSessionId(v13, &pSessionId) )
            *((_DWORD *)a1 + 143) = pSessionId;
          CloseHandle(v6);
        }
        else
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v7 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v8 = GetLastError();
              v7(
                2u,
                L"InitializeLockTrackingContext: OpenProcess failed for PID:0x%x - Error 0x%x",
                *((unsigned int *)a1 + 12),
                v8);
            }
            else if ( g_lpDebugMsgContextInstance )
            {
              if ( g_lpDebugMsgContext )
              {
                v9 = GetLastError();
                RedirectDebugMsg(
                  2u,
                  L"InitializeLockTrackingContext: OpenProcess failed for PID:0x%x - Error 0x%x",
                  *((unsigned int *)a1 + 12),
                  v9);
              }
            }
          }
          _o_wcscpy_s((char *)a1 + 52, 260, L"OpenProcessFailed");
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180092b90  test    rcx, rcx
0x180092b93  jz      locret_180092E09
0x180092b99  push    rbx
0x180092b9a  push    rbp
0x180092b9b  push    rsi
0x180092b9c  push    rdi
0x180092b9d  sub     rsp, 0C8h
0x180092ba4  mov     rax, cs:__security_cookie
0x180092bab  xor     rax, rsp
0x180092bae  mov     [rsp+0E8h+var_38], rax
0x180092bb6  mov     rbx, rcx
0x180092bb9  mov     edi, edx
0x180092bbb  add     rcx, 20h ; ' '; lpSystemTimeAsFileTime
0x180092bbf  call    cs:__imp_GetSystemTimeAsFileTime
0x180092bc5  bt      edi, 1Dh
0x180092bc9  jnb     loc_180092DEE
0x180092bcf  xor     edx, edx; Val
0x180092bd1  lea     rcx, [rsp+0E8h+var_A0]; void *
0x180092bd6  lea     r8d, [rdx+68h]; Size
0x180092bda  call    memset_0
0x180092bdf  lea     rdx, [rsp+0E8h+RpcCallAttributes]; RpcCallAttributes
0x180092be4  mov     [rsp+0E8h+RpcCallAttributes], 3
0x180092bec  xor     ecx, ecx; ClientBinding
0x180092bee  mov     [rsp+0E8h+var_A4], 10h
0x180092bf6  call    cs:__imp_RpcServerInqCallAttributesW
0x180092bfc  test    eax, eax
0x180092bfe  jnz     loc_180092D98
0x180092c04  mov     r8d, [rsp+0E8h+dwProcessId]; dwProcessId
0x180092c0c  xor     edx, edx; bInheritHandle
0x180092c0e  mov     ecx, 400h; dwDesiredAccess
0x180092c13  mov     [rbx+30h], r8d
0x180092c17  call    cs:__imp_OpenProcess
0x180092c1d  mov     rdi, rax
0x180092c20  test    rax, rax
0x180092c23  jnz     loc_180092CCA
0x180092c29  mov     r8d, [rbx+30h]; dwProcessId
0x180092c2d  xor     edx, edx; bInheritHandle
0x180092c2f  mov     ecx, 1000h; dwDesiredAccess
0x180092c34  call    cs:__imp_OpenProcess
0x180092c3a  mov     rdi, rax
0x180092c3d  test    rax, rax
0x180092c40  jnz     loc_180092CCA
0x180092c46  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x180092c4c  jz      short loc_180092CAF
0x180092c4e  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180092c55  test    rdi, rdi
0x180092c58  jz      short loc_180092C7D
0x180092c5a  call    cs:__imp_GetLastError
0x180092c60  mov     r8d, [rbx+30h]
0x180092c64  lea     rdx, aInitializelock; "InitializeLockTrackingContext: OpenProc"...
0x180092c6b  mov     r9d, eax
0x180092c6e  mov     ecx, 2
0x180092c73  mov     rax, rdi
0x180092c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092c7b  jmp     short loc_180092CAF
0x180092c7d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180092c85  jz      short loc_180092CAF
0x180092c87  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180092c8f  jz      short loc_180092CAF
0x180092c91  call    cs:__imp_GetLastError
0x180092c97  mov     r8d, [rbx+30h]
0x180092c9b  lea     rdx, aInitializelock; "InitializeLockTrackingContext: OpenProc"...
0x180092ca2  mov     r9d, eax
0x180092ca5  mov     ecx, 2; unsigned int
0x180092caa  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180092caf  lea     rcx, [rbx+34h]
0x180092cb3  mov     edx, 104h
0x180092cb8  lea     r8, aOpenprocessfai; "OpenProcessFailed"
0x180092cbf  call    cs:__imp__o_wcscpy_s
0x180092cc5  jmp     loc_180092DEE
0x180092cca  lea     r9, [rsp+0E8h+dwSize]; lpdwSize
0x180092ccf  mov     [rsp+0E8h+dwSize], 104h
0x180092cd7  lea     r8, [rbx+34h]; lpExeName
0x180092cdb  xor     edx, edx; dwFlags
0x180092cdd  mov     rcx, rdi; hProcess
0x180092ce0  call    cs:__imp_QueryFullProcessImageNameW
0x180092ce6  test    eax, eax
0x180092ce8  jnz     short loc_180092D69
0x180092cea  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x180092cf0  jz      short loc_180092D53
0x180092cf2  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180092cf9  test    rsi, rsi
0x180092cfc  jz      short loc_180092D21
0x180092cfe  call    cs:__imp_GetLastError
0x180092d04  mov     r8d, [rbx+30h]
0x180092d08  lea     rdx, aInitializelock_1; "InitializeLockTrackingContext: QueryFul"...
0x180092d0f  mov     r9d, eax
0x180092d12  mov     ecx, 2
0x180092d17  mov     rax, rsi
0x180092d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092d1f  jmp     short loc_180092D53
0x180092d21  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180092d29  jz      short loc_180092D53
0x180092d2b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180092d33  jz      short loc_180092D53
0x180092d35  call    cs:__imp_GetLastError
0x180092d3b  mov     r8d, [rbx+30h]
0x180092d3f  lea     rdx, aInitializelock_1; "InitializeLockTrackingContext: QueryFul"...
0x180092d46  mov     r9d, eax
0x180092d49  mov     ecx, 2; unsigned int
0x180092d4e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180092d53  lea     r8, aQueryprocessna; "QueryProcessNameFailed"
0x180092d5a  mov     edx, 104h
0x180092d5f  lea     rcx, [rbx+34h]
0x180092d63  call    cs:__imp__o_wcscpy_s
0x180092d69  mov     ecx, [rbx+30h]; dwProcessId
0x180092d6c  lea     rdx, [rsp+0E8h+pSessionId]; pSessionId
0x180092d71  mov     [rsp+0E8h+pSessionId], 0
0x180092d79  call    cs:__imp_ProcessIdToSessionId
0x180092d7f  test    eax, eax
0x180092d81  jz      short loc_180092D8D
0x180092d83  mov     eax, [rsp+0E8h+pSessionId]
0x180092d87  mov     [rbx+23Ch], eax
0x180092d8d  mov     rcx, rdi; hObject
0x180092d90  call    cs:__imp_CloseHandle
0x180092d96  jmp     short loc_180092DEE
0x180092d98  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180092d9f  jz      short loc_180092DEE
0x180092da1  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180092da8  test    r9, r9
0x180092dab  jz      short loc_180092DC6
0x180092dad  mov     r8d, eax
0x180092db0  lea     rdx, aInitializelock_0; "InitializeLockTrackingContext: RpcServe"...
0x180092db7  mov     rax, r9
0x180092dba  mov     ecx, 2
0x180092dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092dc4  jmp     short loc_180092DEE
0x180092dc6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180092dce  jz      short loc_180092DEE
0x180092dd0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180092dd8  jz      short loc_180092DEE
0x180092dda  mov     r8d, eax
0x180092ddd  lea     rdx, aInitializelock_0; "InitializeLockTrackingContext: RpcServe"...
0x180092de4  mov     ecx, 2; unsigned int
0x180092de9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180092dee  mov     rcx, [rsp+0E8h+var_38]
0x180092df6  xor     rcx, rsp; StackCookie
0x180092df9  call    __security_check_cookie
0x180092dfe  add     rsp, 0C8h
0x180092e05  pop     rdi
0x180092e06  pop     rsi
0x180092e07  pop     rbp
0x180092e08  pop     rbx
0x180092e09  retn
```
