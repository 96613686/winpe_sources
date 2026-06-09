# DropClientContext

- ea: `0x18001d530`
- end: `0x18001db06`
- name: `DropClientContext`
- size: `1494`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800084bc`
- `0x18001c358`
- `0x18001d530`
- `0x18001dc00`
- `0x18001dee0`
- `0x18001e690`
- `0x18002df48`
- `0x180030ad0`
- `0x18003c870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001d78a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001d78a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d674`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d830`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d674`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d830`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d65d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d6ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001daa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d65d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d6ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001daa0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d5c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d61b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d5c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d61b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d5a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d5fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d5a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d5fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d9eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dacf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001daf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d9eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dacf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001daf5`
- `RPCRT4!RpcRevertToSelf` at `0x18001d634`
- `RPCRT4!RpcRevertToSelf` at `0x18001d74d`
- `RPCRT4!RpcRevertToSelf` at `0x18001d7cb`
- `RPCRT4!RpcRevertToSelf` at `0x18001d634`
- `RPCRT4!RpcRevertToSelf` at `0x18001d74d`
- `RPCRT4!RpcRevertToSelf` at `0x18001d7cb`
- `RPCRT4!RpcImpersonateClient` at `0x18001d580`
- `RPCRT4!RpcImpersonateClient` at `0x18001d580`

## string_xrefs

- `0x18001d722`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001d7df`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001d908`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001d94f`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001d97d`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001d9b6`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001da00`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001d70a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18001d80c`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall DropClientContext(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  int v5; // r15d
  RPC_STATUS v6; // eax
  signed int LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  HANDLE v10; // rax
  const char *v11; // r9
  struct _PROFILEINFOW *v12; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROFILEINFOW *v14; // rax
  WCHAR *v15; // rsi
  HANDLE v16; // rcx
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // r12
  unsigned int v19; // r14d
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  _QWORD *v23; // rcx
  const char *v24; // r9
  HANDLE v25; // rax
  WCHAR *v26; // rax
  int v27; // ecx
  WCHAR *v28; // rdx
  unsigned __int64 v29; // rcx
  __int64 v30; // r9
  unsigned __int64 v31; // r12
  _WORD *v32; // rdi
  _WORD *v33; // rdi
  __int64 v34; // rdx
  unsigned int v35; // ebx
  unsigned int v36; // edi
  HANDLE v37; // rax
  __int64 v38; // rdx
  int v39; // eax
  HANDLE v40; // rax
  __int64 v41; // rdx
  void *TokenHandle; // [rsp+20h] [rbp-60h] BYREF
  int v43; // [rsp+28h] [rbp-58h] BYREF
  __int64 v44; // [rsp+30h] [rbp-50h]
  __int64 v45; // [rsp+38h] [rbp-48h]
  int v46; // [rsp+40h] [rbp-40h]
  __int128 v47; // [rsp+48h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  HANDLE hObject; // [rsp+B8h] [rbp+38h] BYREF

  v3 = a3;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)0x80070057LL,
      (int)TokenHandle);
    return 2147942487LL;
  }
  v43 = 0;
  v5 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v6 = RpcImpersonateClient(0);
  LastError = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      LastError = (unsigned __int16)v6 | 0x80070000;
    if ( LastError < 0 )
    {
      v34 = 275;
      goto LABEL_55;
    }
  }
  else
  {
    v5 = 1;
    HIDWORD(v45) = 1;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    if ( (unsigned int)IsUserAnAdminMember(TokenHandle) )
    {
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      goto LABEL_8;
    }
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)0x80070005LL,
      (int)TokenHandle);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_50;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x31,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                v9);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( LastError < 0 )
  {
LABEL_50:
    v34 = 277;
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
      (const char *)(unsigned int)LastError,
      (int)TokenHandle);
    CThreadContext::~CThreadContext((CThreadContext *)&v43);
    return (unsigned int)LastError;
  }
LABEL_8:
  hObject = 0;
  v10 = GetCurrentThread();
  if ( OpenThreadToken(v10, 0xF01FFu, 1, &hObject) )
  {
    if ( v5 )
    {
      RpcRevertToSelf();
      HIDWORD(v45) = 0;
    }
    v12 = 0;
    if ( !a2 )
    {
LABEL_24:
      v23 = malloc(0x10u);
      if ( v23 )
      {
        v25 = hObject;
        hObject = 0;
        *v23 = v25;
        v23[1] = v12;
        *v3 = v23;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        return 0;
      }
      else
      {
        v36 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x12A,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                v24);
        if ( v12 )
          DeleteProfileInfo(v12);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        CThreadContext::~CThreadContext((CThreadContext *)&v43);
        return v36;
      }
    }
    ProcessHeap = GetProcessHeap();
    v14 = (struct _PROFILEINFOW *)HeapAlloc(ProcessHeap, 0, 0x38u);
    v12 = v14;
    if ( !v14 )
    {
      v19 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x276,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)0x8007000ELL,
        (int)TokenHandle);
      goto LABEL_21;
    }
    *(_OWORD *)&v14->dwSize = 0;
    *(_OWORD *)&v14->lpProfilePath = 0;
    *(_OWORD *)&v14->lpServerName = 0;
    v14->hProfile = 0;
    v14->dwSize = *(_DWORD *)a2;
    v14->dwFlags = *(_DWORD *)(a2 + 4);
    v15 = *(WCHAR **)(a2 + 8);
    if ( v15 )
    {
      v16 = GetProcessHeap();
      v17 = -1;
      do
        ++v17;
      while ( v15[v17] );
      v18 = v17 + 1;
      v12->lpUserName = 0;
      if ( v17 + 1 < v17 || !is_mul_ok(v18, 2u) )
      {
        v19 = -2147024362;
LABEL_19:
        v20 = v19;
        v21 = 646;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)v20,
          (int)TokenHandle);
        DeleteProfileInfo(v12);
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x125,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
          (const char *)v19,
          (int)TokenHandle);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        return v19;
      }
      v26 = (WCHAR *)HeapAlloc(v16, 0, 2 * v18);
      v27 = 0;
      v12->lpUserName = v26;
      v28 = v26;
      if ( !v26 )
        v27 = -2147024882;
      v19 = v27;
      if ( !v26 )
        goto LABEL_19;
      if ( v18 > 0x7FFFFFFF )
        goto LABEL_64;
      if ( v17 < 0x7FFFFFFF )
      {
        v29 = v17 + 1;
        v30 = 0;
        while ( v17 )
        {
          if ( !*v15 )
          {
            if ( !v29 )
            {
LABEL_39:
              *(v28 - 1) = 0;
              goto LABEL_44;
            }
            break;
          }
          *v28++ = *v15++;
          --v17;
          ++v30;
          if ( !--v29 )
            goto LABEL_39;
        }
        v31 = v18 - v30;
        *v28 = 0;
        if ( v31 > 1 && 2 * v31 > 2 )
          memset_0(&v26[v30 + 1], 0, 2 * v31 - 2);
        goto LABEL_44;
      }
      if ( v17 != -1 )
LABEL_64:
        *v26 = 0;
    }
LABEL_44:
    v32 = *(_WORD **)(a2 + 16);
    if ( v32 )
    {
      if ( *v32 )
      {
        v37 = GetProcessHeap();
        v39 = _AllocString<CTHeapAllocPolicy>(v37, v38, v32, &v12->lpProfilePath);
        v19 = v39;
        if ( v39 < 0 )
        {
          v21 = 652;
LABEL_72:
          v20 = (unsigned int)v39;
          goto LABEL_20;
        }
      }
    }
    v33 = *(_WORD **)(a2 + 24);
    if ( v33 )
    {
      if ( *v33 )
      {
        v40 = GetProcessHeap();
        v39 = _AllocString<CTHeapAllocPolicy>(v40, v41, v33, &v12->lpDefaultPath);
        v19 = v39;
        if ( v39 < 0 )
        {
          v21 = 657;
          goto LABEL_72;
        }
      }
    }
    v3 = a3;
    goto LABEL_24;
  }
  v35 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x11D,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
          v11);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  CThreadContext::~CThreadContext((CThreadContext *)&v43);
  return v35;
}

```

## disassembly

```asm
0x18001d530  mov     rax, rsp
0x18001d533  mov     [rax+18h], r8
0x18001d537  push    rbp
0x18001d538  push    rdi
0x18001d539  push    r13
0x18001d53b  mov     rbp, rsp
0x18001d53e  sub     rsp, 80h
0x18001d545  mov     rdi, r8
0x18001d548  mov     r13, rdx
0x18001d54b  test    r8, r8
0x18001d54e  jz      loc_18001D7DB
0x18001d554  mov     [rax+8], rbx
0x18001d558  xorps   xmm0, xmm0
0x18001d55b  mov     [rax-30h], r14
0x18001d55f  xor     ecx, ecx; BindingHandle
0x18001d561  xor     r14d, r14d
0x18001d564  mov     [rax-38h], r15
0x18001d568  mov     [rbp+var_58], r14d
0x18001d56c  mov     r15d, r14d
0x18001d56f  mov     [rbp+var_50], r14
0x18001d573  mov     [rbp+var_48], r14
0x18001d577  mov     [rbp+var_40], r14d
0x18001d57b  movdqu  [rbp+var_38], xmm0
0x18001d580  call    cs:__imp_RpcImpersonateClient
0x18001d587  nop     dword ptr [rax+rax+00h]
0x18001d58c  mov     ebx, eax
0x18001d58e  test    eax, eax
0x18001d590  jnz     loc_18001D93C
0x18001d596  mov     r15d, 1
0x18001d59c  mov     dword ptr [rbp+var_48+4], r15d
0x18001d5a0  mov     [rbp+TokenHandle], r14
0x18001d5a4  call    cs:__imp_GetCurrentThread
0x18001d5ab  nop     dword ptr [rax+rax+00h]
0x18001d5b0  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001d5b4  mov     edx, 2000Eh; DesiredAccess
0x18001d5b9  mov     rcx, rax; ThreadHandle
0x18001d5bc  mov     r8d, 1; OpenAsSelf
0x18001d5c2  call    cs:__imp_OpenThreadToken
0x18001d5c9  nop     dword ptr [rax+rax+00h]
0x18001d5ce  test    eax, eax
0x18001d5d0  jz      loc_18001D904
0x18001d5d6  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18001d5da  call    ?IsUserAnAdminMember@@YAHPEAX@Z; IsUserAnAdminMember(void *)
0x18001d5df  test    eax, eax
0x18001d5e1  jz      loc_18001D9FC
0x18001d5e7  mov     rcx, [rbp+TokenHandle]; hObject
0x18001d5eb  lea     rax, [rcx-1]
0x18001d5ef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d5f3  jbe     loc_18001DA27
0x18001d5f9  mov     [rbp+hObject], r14
0x18001d5fd  call    cs:__imp_GetCurrentThread
0x18001d604  nop     dword ptr [rax+rax+00h]
0x18001d609  lea     r9, [rbp+hObject]; TokenHandle
0x18001d60d  mov     edx, 0F01FFh; DesiredAccess
0x18001d612  mov     rcx, rax; ThreadHandle
0x18001d615  mov     r8d, 1; OpenAsSelf
0x18001d61b  call    cs:__imp_OpenThreadToken
0x18001d622  nop     dword ptr [rax+rax+00h]
0x18001d627  test    eax, eax
0x18001d629  jz      loc_18001D979
0x18001d62f  test    r15d, r15d
0x18001d632  jz      short loc_18001D647
0x18001d634  call    cs:__imp_RpcRevertToSelf
0x18001d63b  nop     dword ptr [rax+rax+00h]
0x18001d640  mov     r15d, r14d
0x18001d643  mov     dword ptr [rbp+var_48+4], r14d
0x18001d647  mov     [rsp+80h+var_8], rsi
0x18001d64c  mov     rbx, r14
0x18001d64f  mov     [rsp+80h+var_10], r12
0x18001d654  test    r13, r13
0x18001d657  jz      loc_18001D785
0x18001d65d  call    cs:__imp_GetProcessHeap
0x18001d664  nop     dword ptr [rax+rax+00h]
0x18001d669  xor     edx, edx; dwFlags
0x18001d66b  mov     r8d, 38h ; '8'; dwBytes
0x18001d671  mov     rcx, rax; hHeap
0x18001d674  call    cs:__imp_HeapAlloc
0x18001d67b  nop     dword ptr [rax+rax+00h]
0x18001d680  mov     rbx, rax
0x18001d683  test    rax, rax
0x18001d686  jz      loc_18001D808
0x18001d68c  xor     eax, eax
0x18001d68e  xorps   xmm0, xmm0
0x18001d691  movups  xmmword ptr [rbx], xmm0
0x18001d694  movups  xmmword ptr [rbx+10h], xmm0
0x18001d698  movups  xmmword ptr [rbx+20h], xmm0
0x18001d69c  mov     [rbx+30h], rax
0x18001d6a0  mov     eax, [r13+0]
0x18001d6a4  mov     [rbx], eax
0x18001d6a6  mov     eax, [r13+4]
0x18001d6aa  mov     [rbx+4], eax
0x18001d6ad  mov     rsi, [r13+8]
0x18001d6b1  test    rsi, rsi
0x18001d6b4  jz      loc_18001D8E1
0x18001d6ba  call    cs:__imp_GetProcessHeap
0x18001d6c1  nop     dword ptr [rax+rax+00h]
0x18001d6c6  mov     rcx, rax; hHeap
0x18001d6c9  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001d6d0  inc     rdi
0x18001d6d3  cmp     [rsi+rdi*2], r14w
0x18001d6d8  jnz     short loc_18001D6D0
0x18001d6da  lea     r12, [rdi+1]
0x18001d6de  mov     [rbx+8], r14
0x18001d6e2  cmp     r12, rdi
0x18001d6e5  jb      short loc_18001D6F8
0x18001d6e7  mov     eax, 2
0x18001d6ec  mul     r12
0x18001d6ef  test    rdx, rdx
0x18001d6f2  jz      loc_18001D82B
0x18001d6f8  mov     r14d, 80070216h
0x18001d6fe  mov     r9d, r14d; char *
0x18001d701  mov     edx, 286h; void *
0x18001d706  mov     rcx, [rbp+18h]; this
0x18001d70a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d711  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d716  mov     rcx, rbx; lpMem
0x18001d719  call    ?DeleteProfileInfo@@YAXPEAU_PROFILEINFOW@@@Z; DeleteProfileInfo(_PROFILEINFOW *)
0x18001d71e  mov     rcx, [rbp+18h]; this
0x18001d722  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d729  mov     r9d, r14d; char *
0x18001d72c  mov     edx, 125h; void *
0x18001d731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d736  mov     rcx, [rbp+hObject]; hObject
0x18001d73a  lea     rdx, [rcx-1]
0x18001d73e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001d742  jbe     loc_18001DACF
0x18001d748  test    r15d, r15d
0x18001d74b  jz      short loc_18001D759
0x18001d74d  call    cs:__imp_RpcRevertToSelf
0x18001d754  nop     dword ptr [rax+rax+00h]
0x18001d759  mov     eax, r14d
0x18001d75c  mov     r12, [rsp+80h+var_10]
0x18001d761  mov     rsi, [rsp+80h+var_8]
0x18001d766  mov     r14, [rsp+80h+var_18]
0x18001d76b  mov     rbx, [rsp+80h+arg_0]
0x18001d773  mov     r15, [rsp+80h+var_20]
0x18001d778  add     rsp, 80h
0x18001d77f  pop     r13
0x18001d781  pop     rdi
0x18001d782  pop     rbp
0x18001d783  retn
0x18001d785  mov     ecx, 10h; Size
0x18001d78a  call    cs:__imp_malloc
0x18001d791  nop     dword ptr [rax+rax+00h]
0x18001d796  mov     rcx, rax
0x18001d799  test    rax, rax
0x18001d79c  jz      loc_18001D9B2
0x18001d7a2  mov     rax, [rbp+hObject]
0x18001d7a6  mov     [rbp+hObject], r14
0x18001d7aa  mov     [rcx], rax
0x18001d7ad  mov     [rcx+8], rbx
0x18001d7b1  mov     [rdi], rcx
0x18001d7b4  mov     rcx, [rbp+hObject]; hObject
0x18001d7b8  lea     rax, [rcx-1]
0x18001d7bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d7c0  jbe     loc_18001DAF5
0x18001d7c6  test    r15d, r15d
0x18001d7c9  jz      short loc_18001D7D7
0x18001d7cb  call    cs:__imp_RpcRevertToSelf
0x18001d7d2  nop     dword ptr [rax+rax+00h]
0x18001d7d7  xor     eax, eax
0x18001d7d9  jmp     short loc_18001D75C
0x18001d7db  mov     rcx, [rbp+18h]; this
0x18001d7df  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d7e6  mov     r9d, 80070057h; char *
0x18001d7ec  mov     edx, 10Fh; void *
0x18001d7f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7f6  mov     eax, 80070057h
0x18001d7fb  add     rsp, 80h
0x18001d802  pop     r13
0x18001d804  pop     rdi
0x18001d805  pop     rbp
0x18001d806  retn
0x18001d808  mov     rcx, [rbp+18h]; this
0x18001d80c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d813  mov     r14d, 8007000Eh
0x18001d819  mov     edx, 276h; void *
0x18001d81e  mov     r9d, r14d; char *
0x18001d821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d826  jmp     loc_18001D71E
0x18001d82b  mov     r8, rax; dwBytes
0x18001d82e  xor     edx, edx; dwFlags
0x18001d830  call    cs:__imp_HeapAlloc
0x18001d837  nop     dword ptr [rax+rax+00h]
0x18001d83c  mov     ecx, r14d
0x18001d83f  mov     r14d, 8007000Eh
0x18001d845  test    rax, rax
0x18001d848  mov     [rbx+8], rax
0x18001d84c  mov     rdx, rax
0x18001d84f  cmovz   ecx, r14d
0x18001d853  mov     r14d, ecx
0x18001d856  jz      loc_18001D6FE
0x18001d85c  xor     r14d, r14d
0x18001d85f  cmp     r12, 7FFFFFFFh
0x18001d866  ja      loc_18001DA52
0x18001d86c  cmp     rdi, 7FFFFFFFh
0x18001d873  jnb     loc_18001DA49
0x18001d879  test    r12, r12
0x18001d87c  jz      short loc_18001D8E1
0x18001d87e  mov     rcx, r12
0x18001d881  mov     r9d, r14d
0x18001d884  mov     r10, rax
0x18001d887  test    rdi, rdi
0x18001d88a  jz      short loc_18001D8B7
0x18001d88c  movzx   eax, word ptr [rsi]
0x18001d88f  test    ax, ax
0x18001d892  jz      short loc_18001D8B2
0x18001d894  mov     [rdx], ax
0x18001d897  add     rsi, 2
0x18001d89b  add     rdx, 2
0x18001d89f  dec     rdi
0x18001d8a2  inc     r9
0x18001d8a5  sub     rcx, 1
0x18001d8a9  jnz     short loc_18001D887
0x18001d8ab  mov     [rdx-2], r14w
0x18001d8b0  jmp     short loc_18001D8E1
0x18001d8b2  test    rcx, rcx
0x18001d8b5  jz      short loc_18001D8AB
0x18001d8b7  sub     r12, r9
0x18001d8ba  mov     [rdx], r14w
0x18001d8be  cmp     r12, 1
0x18001d8c2  jbe     short loc_18001D8E1
0x18001d8c4  lea     r8, [r12+r12]
0x18001d8c8  cmp     r8, 2
0x18001d8cc  jbe     short loc_18001D8E1
0x18001d8ce  add     r10, 2
0x18001d8d2  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001d8d6  xor     edx, edx; Val
0x18001d8d8  lea     rcx, [r10+r9*2]; void *
0x18001d8dc  call    memset_0
0x18001d8e1  mov     rdi, [r13+10h]
0x18001d8e5  test    rdi, rdi
0x18001d8e8  jnz     loc_18001DA5B
0x18001d8ee  mov     rdi, [r13+18h]
0x18001d8f2  test    rdi, rdi
0x18001d8f5  jnz     loc_18001DA96
0x18001d8fb  mov     rdi, [rbp+arg_10]
0x18001d8ff  jmp     loc_18001D785
0x18001d904  mov     rcx, [rbp+18h]; this
0x18001d908  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d90f  mov     edx, 31h ; '1'; void *
0x18001d914  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d919  mov     rcx, [rbp+TokenHandle]; hObject
0x18001d91d  mov     ebx, eax
0x18001d91f  lea     rax, [rcx-1]
0x18001d923  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d927  jbe     loc_18001D9EB
0x18001d92d  test    ebx, ebx
0x18001d92f  jns     loc_18001D5F9
0x18001d935  mov     edx, 115h
0x18001d93a  jmp     short loc_18001D94B
0x18001d93c  jg      short loc_18001D96E
0x18001d93e  test    ebx, ebx
0x18001d940  jns     loc_18001D5A0
0x18001d946  mov     edx, 113h; void *
0x18001d94b  mov     rcx, [rbp+18h]; this
0x18001d94f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d956  mov     r9d, ebx; char *
0x18001d959  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d95e  lea     rcx, [rbp+var_58]; this
0x18001d962  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001d967  mov     eax, ebx
0x18001d969  jmp     loc_18001D766
0x18001d96e  movzx   ebx, ax
0x18001d971  or      ebx, 80070000h
0x18001d977  jmp     short loc_18001D93E
0x18001d979  mov     rcx, [rbp+18h]; this
0x18001d97d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d984  mov     edx, 11Dh; void *
0x18001d989  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d98e  mov     rcx, [rbp+hObject]; hObject
0x18001d992  mov     ebx, eax
0x18001d994  lea     rdx, [rcx-1]
0x18001d998  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001d99c  jbe     loc_18001DA38
0x18001d9a2  lea     rcx, [rbp+var_58]; this
0x18001d9a6  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001d9ab  mov     eax, ebx
0x18001d9ad  jmp     loc_18001D766
0x18001d9b2  mov     rcx, [rbp+18h]; this
0x18001d9b6  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d9bd  mov     edx, 12Ah; void *
0x18001d9c2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d9c7  mov     edi, eax
0x18001d9c9  test    rbx, rbx
0x18001d9cc  jnz     loc_18001DAE8
0x18001d9d2  lea     rcx, [rbp+hObject]
0x18001d9d6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001d9db  lea     rcx, [rbp+var_58]; this
0x18001d9df  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001d9e4  mov     eax, edi
0x18001d9e6  jmp     loc_18001D75C
0x18001d9eb  call    cs:__imp_CloseHandle
0x18001d9f2  nop     dword ptr [rax+rax+00h]
0x18001d9f7  jmp     loc_18001D92D
0x18001d9fc  mov     rcx, [rbp+18h]; this
0x18001da00  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001da07  mov     ebx, 80070005h
0x18001da0c  mov     edx, 33h ; '3'; void *
0x18001da11  mov     r9d, ebx; char *
  ... truncated ...
```
