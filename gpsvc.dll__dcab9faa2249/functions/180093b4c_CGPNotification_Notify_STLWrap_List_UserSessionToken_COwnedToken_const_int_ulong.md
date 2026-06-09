# CGPNotification::Notify(STLWrap_List<_UserSessionToken *> &,COwnedToken const &,int,ulong)

- ea: `0x180093b4c`
- end: `0x180093e84`
- name: `?Notify@CGPNotification@@QEAAKAEAV?$STLWrap_List@PEAU_UserSessionToken@@@@AEBVCOwnedToken@@HK@Z`
- size: `824`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004e260`

## callees

- `0x18000a504`
- `0x18000a52c`
- `0x18004dc40`
- `0x18004f240`
- `0x180075ec0`
- `0x180093b4c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180093d8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180093d8d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180093e4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180093e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d97`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180093e0d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180093e0d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180093e38`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180093e38`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180093e2f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180093e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093e41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093e41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093b99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093c07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093b99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093c07`

## string_xrefs

- `0x180093d48`: `failed to duplicate token with 0x%x.`
- `0x180093d6b`: `failed to duplicate token with 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGPNotification::Notify(__int64 a1, __int64 a2, __int64 a3, DWORD a4)
{
  unsigned int v6; // esi
  HLOCAL v7; // rbx
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v9; // rdx
  DWORD LastError; // ebx
  _QWORD *v11; // rax
  _DWORD *v12; // rdi
  __int64 v13; // r9
  __int64 i; // r8
  __int64 **v15; // rax
  __int64 *v16; // r8
  unsigned int v17; // r9d
  void (*v18)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v19; // rdx
  HANDLE v20; // rax
  void *v21; // rbx
  void *v23; // [rsp+30h] [rbp-20h] BYREF
  void *v24; // [rsp+38h] [rbp-18h] BYREF
  __int64 v25; // [rsp+40h] [rbp-10h] BYREF
  char v26; // [rsp+48h] [rbp-8h]
  void *v27; // [rsp+90h] [rbp+40h] BYREF
  HMODULE phModule; // [rsp+98h] [rbp+48h] BYREF
  DWORD ThreadId; // [rsp+A8h] [rbp+58h] BYREF

  ThreadId = a4;
  v23 = 0;
  v27 = 0;
  phModule = 0;
  if ( *(_QWORD *)a2 )
    v6 = *(_DWORD *)(*(_QWORD *)a2 + 8LL);
  else
    v6 = 0;
  v7 = LocalAlloc(0x40u, 4LL * v6);
  v24 = v7;
  if ( !v7 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
    {
LABEL_12:
      LastError = 14;
      goto LABEL_51;
    }
    v8 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"Failed to allocate storage for session ids");
      goto LABEL_12;
    }
    v9 = L"Failed to allocate storage for session ids";
LABEL_8:
    v8(2u, v9);
    goto LABEL_12;
  }
  v11 = LocalAlloc(0x40u, 0x28u);
  v12 = v11;
  v23 = v11;
  if ( !v11 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_12;
    v8 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"Failed to allocate storage for policy changed info");
      goto LABEL_12;
    }
    v9 = L"Failed to allocate storage for policy changed info";
    goto LABEL_8;
  }
  v11[2] = v7;
  STLWrap_List<_POLICY_SECTION_CONTEXT *>::begin(a2, &v25);
  if ( v26 )
  {
    v13 = 0;
    for ( i = v25; ; i = *v16 )
    {
      v15 = (__int64 **)STLWrap_List<_UserSessionToken *>::end(a2, &v25, i, v13);
      if ( v16 == *v15 )
        break;
      *((_DWORD *)v7 + v17) = *(_DWORD *)(v16[2] + 8);
      v13 = v17 + 1;
    }
  }
  v12[6] = v6;
  LastError = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a3 + 16LL))(a3, v12 + 2);
  if ( LastError )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_51;
    v18 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v19 = L"Failed to find machine information with 0x%x";
LABEL_28:
      v18(2u, v19, LastError);
      goto LABEL_51;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      RedirectDebugMsg(2u, L"Failed to find machine information with 0x%x", LastError);
  }
  else
  {
    LastError = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)a3 + 24LL))(a3, &v27);
    if ( LastError )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_51;
      v18 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v19 = L"failed to duplicate token with 0x%x.";
        goto LABEL_28;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"failed to duplicate token with 0x%x.", LastError);
    }
    else
    {
      *(_QWORD *)v12 = v27;
      if ( GetModuleHandleExW(4u, (LPCWSTR)CGPNotification::NotifyThread, &phModule) )
      {
        *((_QWORD *)v12 + 4) = phModule;
        ThreadId = 0;
        v20 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CGPNotification::NotifyThread, v12, 4u, &ThreadId);
        v21 = v20;
        if ( v20 )
        {
          v23 = 0;
          v27 = 0;
          v24 = 0;
          SetThreadPriority(v20, -15);
          ResumeThread(v21);
          CloseHandle(v21);
        }
        else
        {
          FreeLibrary(phModule);
        }
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_51;
        v18 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v19 = L"Failed to get module handle with 0x%x.";
          goto LABEL_28;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"Failed to get module handle with 0x%x.", LastError);
      }
    }
  }
LABEL_51:
  XHandle::~XHandle(&v27);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v23);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v24);
  return LastError;
}

```

## disassembly

```asm
0x180093b4c  mov     [rsp-38h+ThreadId], r9d
0x180093b51  mov     [rsp-38h+arg_0], rcx
0x180093b56  push    rbp
0x180093b57  push    rbx
0x180093b58  push    rsi
0x180093b59  push    rdi
0x180093b5a  push    r12
0x180093b5c  push    r14
0x180093b5e  push    r15
0x180093b60  mov     rbp, rsp
0x180093b63  sub     rsp, 50h
0x180093b67  mov     r15, r8
0x180093b6a  mov     r14, rdx
0x180093b6d  xor     r12d, r12d
0x180093b70  mov     [rbp+var_20], r12
0x180093b74  mov     [rbp+arg_0], r12
0x180093b78  mov     [rbp+phModule], r12
0x180093b7c  mov     rax, [rdx]
0x180093b7f  test    rax, rax
0x180093b82  jz      short loc_180093B89
0x180093b84  mov     esi, [rax+8]
0x180093b87  jmp     short loc_180093B8C
0x180093b89  mov     esi, r12d
0x180093b8c  mov     edx, esi
0x180093b8e  shl     rdx, 2; uBytes
0x180093b92  mov     edi, 40h ; '@'
0x180093b97  mov     ecx, edi; uFlags
0x180093b99  call    cs:__imp_LocalAlloc
0x180093b9f  mov     rbx, rax
0x180093ba2  mov     [rbp+var_18], rax
0x180093ba6  test    rax, rax
0x180093ba9  jnz     short loc_180093C00
0x180093bab  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180093bb2  jz      short loc_180093BF6
0x180093bb4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093bbb  test    rax, rax
0x180093bbe  jz      short loc_180093BD3
0x180093bc0  lea     rdx, aFailedToAlloca_1; "Failed to allocate storage for session "...
0x180093bc7  mov     ecx, 2
0x180093bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093bd1  jmp     short loc_180093BF6
0x180093bd3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180093bda  jz      short loc_180093BF6
0x180093bdc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093be3  jz      short loc_180093BF6
0x180093be5  lea     rdx, aFailedToAlloca_1; "Failed to allocate storage for session "...
0x180093bec  mov     ecx, 2; unsigned int
0x180093bf1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093bf6  mov     ebx, 0Eh
0x180093bfb  jmp     loc_180093E56
0x180093c00  mov     edx, 28h ; '('; uBytes
0x180093c05  mov     ecx, edi; uFlags
0x180093c07  call    cs:__imp_LocalAlloc
0x180093c0d  mov     rdi, rax
0x180093c10  mov     [rbp+var_20], rax
0x180093c14  test    rax, rax
0x180093c17  jnz     short loc_180093C52
0x180093c19  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180093c20  jz      short loc_180093BF6
0x180093c22  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093c29  test    rax, rax
0x180093c2c  jz      short loc_180093C37
0x180093c2e  lea     rdx, aFailedToAlloca_0; "Failed to allocate storage for policy c"...
0x180093c35  jmp     short loc_180093BC7
0x180093c37  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180093c3e  jz      short loc_180093BF6
0x180093c40  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093c47  jz      short loc_180093BF6
0x180093c49  lea     rdx, aFailedToAlloca_0; "Failed to allocate storage for policy c"...
0x180093c50  jmp     short loc_180093BEC
0x180093c52  mov     [rax+10h], rbx
0x180093c56  lea     rdx, [rbp+var_10]
0x180093c5a  mov     rcx, r14
0x180093c5d  call    ?begin@?$STLWrap_List@PEAU_POLICY_SECTION_CONTEXT@@@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAU_POLICY_SECTION_CONTEXT@@@std@@@std@@@std@@_N@std@@XZ; STLWrap_List<_POLICY_SECTION_CONTEXT *>::begin(void)
0x180093c62  cmp     [rbp+var_8], r12b
0x180093c66  jz      short loc_180093C95
0x180093c68  mov     r9d, r12d
0x180093c6b  mov     r8, [rbp+var_10]
0x180093c6f  lea     rdx, [rbp+var_10]
0x180093c73  mov     rcx, r14
0x180093c76  call    ?end@?$STLWrap_List@PEAU_UserSessionToken@@@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAU_UserSessionToken@@@std@@@std@@@std@@_N@std@@XZ; STLWrap_List<_UserSessionToken *>::end(void)
0x180093c7b  cmp     r8, [rax]
0x180093c7e  jz      short loc_180093C95
0x180093c80  mov     rax, [r8+10h]
0x180093c84  mov     ecx, r9d
0x180093c87  mov     eax, [rax+8]
0x180093c8a  mov     [rbx+rcx*4], eax
0x180093c8d  inc     r9d
0x180093c90  mov     r8, [r8]
0x180093c93  jmp     short loc_180093C6F
0x180093c95  mov     [rdi+18h], esi
0x180093c98  mov     rax, [r15]
0x180093c9b  lea     rdx, [rdi+8]
0x180093c9f  mov     rcx, r15
0x180093ca2  mov     rax, [rax+10h]
0x180093ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093cab  mov     ebx, eax
0x180093cad  test    eax, eax
0x180093caf  jz      short loc_180093D16
0x180093cb1  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180093cb8  jz      loc_180093E56
0x180093cbe  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093cc5  test    rax, rax
0x180093cc8  jz      short loc_180093CE3
0x180093cca  lea     rdx, aFailedToFindMa; "Failed to find machine information with"...
0x180093cd1  mov     r8d, ebx
0x180093cd4  mov     ecx, 2
0x180093cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093cde  jmp     loc_180093E56
0x180093ce3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180093cea  jz      loc_180093E56
0x180093cf0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093cf7  jz      loc_180093E56
0x180093cfd  lea     rdx, aFailedToFindMa; "Failed to find machine information with"...
0x180093d04  mov     r8d, ebx
0x180093d07  mov     ecx, 2; unsigned int
0x180093d0c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093d11  jmp     loc_180093E56
0x180093d16  mov     rax, [r15]
0x180093d19  lea     rdx, [rbp+arg_0]
0x180093d1d  mov     rcx, r15
0x180093d20  mov     rax, [rax+18h]
0x180093d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d29  mov     ebx, eax
0x180093d2b  test    eax, eax
0x180093d2d  jz      short loc_180093D74
0x180093d2f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180093d36  jz      loc_180093E56
0x180093d3c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093d43  test    rax, rax
0x180093d46  jz      short loc_180093D51
0x180093d48  lea     rdx, aFailedToDuplic_0; "failed to duplicate token with 0x%x."
0x180093d4f  jmp     short loc_180093CD1
0x180093d51  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180093d58  jz      loc_180093E56
0x180093d5e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093d65  jz      loc_180093E56
0x180093d6b  lea     rdx, aFailedToDuplic_0; "failed to duplicate token with 0x%x."
0x180093d72  jmp     short loc_180093D04
0x180093d74  mov     rax, [rbp+arg_0]
0x180093d78  mov     [rdi], rax
0x180093d7b  lea     r8, [rbp+phModule]; phModule
0x180093d7f  lea     rdx, ?NotifyThread@CGPNotification@@CAKPEAU_POLICYCHANGEDINFO@@@Z; lpModuleName
0x180093d86  mov     ebx, 4
0x180093d8b  mov     ecx, ebx; dwFlags
0x180093d8d  call    cs:__imp_GetModuleHandleExW
0x180093d93  test    eax, eax
0x180093d95  jnz     short loc_180093DE6
0x180093d97  call    cs:__imp_GetLastError
0x180093d9d  mov     ebx, eax
0x180093d9f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180093da6  jz      loc_180093E56
0x180093dac  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093db3  test    rax, rax
0x180093db6  jz      short loc_180093DC4
0x180093db8  lea     rdx, aFailedToGetMod; "Failed to get module handle with 0x%x."
0x180093dbf  jmp     loc_180093CD1
0x180093dc4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180093dcb  jz      loc_180093E56
0x180093dd1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093dd8  jz      short loc_180093E56
0x180093dda  lea     rdx, aFailedToGetMod; "Failed to get module handle with 0x%x."
0x180093de1  jmp     loc_180093D04
0x180093de6  mov     rax, [rbp+phModule]
0x180093dea  mov     [rdi+20h], rax
0x180093dee  mov     [rbp+ThreadId], r12d
0x180093df2  lea     rax, [rbp+ThreadId]
0x180093df6  mov     [rsp+50h+lpThreadId], rax; lpThreadId
0x180093dfb  mov     [rsp+50h+dwCreationFlags], ebx; dwCreationFlags
0x180093dff  mov     r9, rdi; lpParameter
0x180093e02  lea     r8, ?NotifyThread@CGPNotification@@CAKPEAU_POLICYCHANGEDINFO@@@Z; lpStartAddress
0x180093e09  xor     edx, edx; dwStackSize
0x180093e0b  xor     ecx, ecx; lpThreadAttributes
0x180093e0d  call    cs:__imp_CreateThread
0x180093e13  mov     rbx, rax
0x180093e16  test    rax, rax
0x180093e19  jz      short loc_180093E49
0x180093e1b  mov     [rbp+var_20], r12
0x180093e1f  mov     [rbp+arg_0], r12
0x180093e23  mov     [rbp+var_18], r12
0x180093e27  mov     edx, 0FFFFFFF1h; nPriority
0x180093e2c  mov     rcx, rax; hThread
0x180093e2f  call    cs:__imp_SetThreadPriority
0x180093e35  mov     rcx, rbx; hThread
0x180093e38  call    cs:__imp_ResumeThread
0x180093e3e  mov     rcx, rbx; hObject
0x180093e41  call    cs:__imp_CloseHandle
0x180093e47  jmp     short loc_180093E53
0x180093e49  mov     rcx, [rbp+phModule]; hLibModule
0x180093e4d  call    cs:__imp_FreeLibrary
0x180093e53  mov     ebx, r12d
0x180093e56  lea     rcx, [rbp+arg_0]; this
0x180093e5a  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180093e5f  nop
0x180093e60  lea     rcx, [rbp+var_20]
0x180093e64  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180093e69  nop
0x180093e6a  lea     rcx, [rbp+var_18]
0x180093e6e  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180093e73  mov     eax, ebx
0x180093e75  add     rsp, 50h
0x180093e79  pop     r15
0x180093e7b  pop     r14
0x180093e7d  pop     r12
0x180093e7f  pop     rdi
0x180093e80  pop     rsi
0x180093e81  pop     rbx
0x180093e82  pop     rbp
0x180093e83  retn
```
