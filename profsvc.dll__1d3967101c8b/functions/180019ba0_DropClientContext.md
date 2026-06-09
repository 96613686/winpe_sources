# DropClientContext

- ea: `0x180019ba0`
- end: `0x18001a105`
- name: `DropClientContext`
- size: `1381`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008360`
- `0x18000a9b8`
- `0x180018bcc`
- `0x180019ba0`
- `0x18001a1e0`
- `0x18001a3d0`
- `0x18002d2d8`
- `0x18002db38`
- `0x18003b310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180019dc3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180019dc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019cba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019e5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019cba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019e5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ca9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019cfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a07c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ca9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019cfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a07c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0b1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019c26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019c73`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019c26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019c73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019c5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a014`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a04a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a0da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a0fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a014`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a04a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a0da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a0fa`
- `RPCRT4!RpcRevertToSelf` at `0x180019c86`
- `RPCRT4!RpcRevertToSelf` at `0x180019d8d`
- `RPCRT4!RpcRevertToSelf` at `0x180019dfe`
- `RPCRT4!RpcRevertToSelf` at `0x180019c86`
- `RPCRT4!RpcRevertToSelf` at `0x180019d8d`
- `RPCRT4!RpcRevertToSelf` at `0x180019dfe`
- `RPCRT4!RpcImpersonateClient` at `0x180019bf0`
- `RPCRT4!RpcImpersonateClient` at `0x180019bf0`

## string_xrefs

- `0x180019d62`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180019e0c`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180019f31`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180019f78`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180019fa6`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180019fdf`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001a023`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x180019d4a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180019e38`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

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
  HANDLE v43[2]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v44; // [rsp+38h] [rbp-48h]
  int v45; // [rsp+40h] [rbp-40h]
  __int128 v46; // [rsp+48h] [rbp-38h]
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
  LODWORD(v43[0]) = 0;
  v5 = 0;
  v43[1] = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
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
    HIDWORD(v44) = 1;
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
    CThreadContext::~CThreadContext(v43);
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
      HIDWORD(v44) = 0;
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
        CThreadContext::~CThreadContext(v43);
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
  CThreadContext::~CThreadContext(v43);
  return v35;
}

```

## disassembly

```asm
0x180019ba0  mov     rax, rsp
0x180019ba3  mov     [rax+18h], r8
0x180019ba7  push    rbp
0x180019ba8  push    rdi
0x180019ba9  push    r13
0x180019bab  mov     rbp, rsp
0x180019bae  sub     rsp, 80h
0x180019bb5  mov     rdi, r8
0x180019bb8  mov     r13, rdx
0x180019bbb  test    r8, r8
0x180019bbe  jz      loc_180019E08
0x180019bc4  mov     [rax+8], rbx
0x180019bc8  xorps   xmm0, xmm0
0x180019bcb  mov     [rax-30h], r14
0x180019bcf  xor     ecx, ecx; BindingHandle
0x180019bd1  xor     r14d, r14d
0x180019bd4  mov     [rax-38h], r15
0x180019bd8  mov     [rbp+var_58], r14d
0x180019bdc  mov     r15d, r14d
0x180019bdf  mov     [rbp+var_50], r14
0x180019be3  mov     [rbp+var_48], r14
0x180019be7  mov     [rbp+var_40], r14d
0x180019beb  movdqu  [rbp+var_38], xmm0
0x180019bf0  call    cs:__imp_RpcImpersonateClient
0x180019bf6  mov     ebx, eax
0x180019bf8  test    eax, eax
0x180019bfa  jnz     loc_180019F65
0x180019c00  mov     r15d, 1
0x180019c06  mov     dword ptr [rbp+var_48+4], r15d
0x180019c0a  mov     [rbp+TokenHandle], r14
0x180019c0e  call    cs:__imp_GetCurrentThread
0x180019c14  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180019c18  mov     edx, 2000Eh; DesiredAccess
0x180019c1d  mov     rcx, rax; ThreadHandle
0x180019c20  mov     r8d, 1; OpenAsSelf
0x180019c26  call    cs:__imp_OpenThreadToken
0x180019c2c  test    eax, eax
0x180019c2e  jz      loc_180019F2D
0x180019c34  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180019c38  call    ?IsUserAnAdminMember@@YAHPEAX@Z; IsUserAnAdminMember(void *)
0x180019c3d  test    eax, eax
0x180019c3f  jz      loc_18001A01F
0x180019c45  mov     rcx, [rbp+TokenHandle]; hObject
0x180019c49  lea     rax, [rcx-1]
0x180019c4d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019c51  jbe     loc_18001A04A
0x180019c57  mov     [rbp+hObject], r14
0x180019c5b  call    cs:__imp_GetCurrentThread
0x180019c61  lea     r9, [rbp+hObject]; TokenHandle
0x180019c65  mov     edx, 0F01FFh; DesiredAccess
0x180019c6a  mov     rcx, rax; ThreadHandle
0x180019c6d  mov     r8d, 1; OpenAsSelf
0x180019c73  call    cs:__imp_OpenThreadToken
0x180019c79  test    eax, eax
0x180019c7b  jz      loc_180019FA2
0x180019c81  test    r15d, r15d
0x180019c84  jz      short loc_180019C93
0x180019c86  call    cs:__imp_RpcRevertToSelf
0x180019c8c  mov     r15d, r14d
0x180019c8f  mov     dword ptr [rbp+var_48+4], r14d
0x180019c93  mov     [rsp+80h+var_8], rsi
0x180019c98  mov     rbx, r14
0x180019c9b  mov     [rsp+80h+var_10], r12
0x180019ca0  test    r13, r13
0x180019ca3  jz      loc_180019DBE
0x180019ca9  call    cs:__imp_GetProcessHeap
0x180019caf  xor     edx, edx; dwFlags
0x180019cb1  mov     r8d, 38h ; '8'; dwBytes
0x180019cb7  mov     rcx, rax; hHeap
0x180019cba  call    cs:__imp_HeapAlloc
0x180019cc0  mov     rbx, rax
0x180019cc3  test    rax, rax
0x180019cc6  jz      loc_180019E34
0x180019ccc  xor     eax, eax
0x180019cce  xorps   xmm0, xmm0
0x180019cd1  movups  xmmword ptr [rbx], xmm0
0x180019cd4  movups  xmmword ptr [rbx+10h], xmm0
0x180019cd8  movups  xmmword ptr [rbx+20h], xmm0
0x180019cdc  mov     [rbx+30h], rax
0x180019ce0  mov     eax, [r13+0]
0x180019ce4  mov     [rbx], eax
0x180019ce6  mov     eax, [r13+4]
0x180019cea  mov     [rbx+4], eax
0x180019ced  mov     rsi, [r13+8]
0x180019cf1  test    rsi, rsi
0x180019cf4  jz      loc_180019F0A
0x180019cfa  call    cs:__imp_GetProcessHeap
0x180019d00  mov     rcx, rax; hHeap
0x180019d03  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180019d0a  nop     word ptr [rax+rax+00h]
0x180019d10  inc     rdi
0x180019d13  cmp     [rsi+rdi*2], r14w
0x180019d18  jnz     short loc_180019D10
0x180019d1a  lea     r12, [rdi+1]
0x180019d1e  mov     [rbx+8], r14
0x180019d22  cmp     r12, rdi
0x180019d25  jb      short loc_180019D38
0x180019d27  mov     eax, 2
0x180019d2c  mul     r12
0x180019d2f  test    rdx, rdx
0x180019d32  jz      loc_180019E57
0x180019d38  mov     r14d, 80070216h
0x180019d3e  mov     r9d, r14d; char *
0x180019d41  mov     edx, 286h; void *
0x180019d46  mov     rcx, [rbp+18h]; this
0x180019d4a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180019d51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d56  mov     rcx, rbx; lpMem
0x180019d59  call    ?DeleteProfileInfo@@YAXPEAU_PROFILEINFOW@@@Z; DeleteProfileInfo(_PROFILEINFOW *)
0x180019d5e  mov     rcx, [rbp+18h]; this
0x180019d62  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180019d69  mov     r9d, r14d; char *
0x180019d6c  mov     edx, 125h; void *
0x180019d71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d76  mov     rcx, [rbp+hObject]; hObject
0x180019d7a  lea     rdx, [rcx-1]
0x180019d7e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019d82  jbe     loc_18001A0DA
0x180019d88  test    r15d, r15d
0x180019d8b  jz      short loc_180019D93
0x180019d8d  call    cs:__imp_RpcRevertToSelf
0x180019d93  mov     eax, r14d
0x180019d96  mov     r12, [rsp+80h+var_10]
0x180019d9b  mov     rsi, [rsp+80h+var_8]
0x180019da0  mov     r14, [rsp+80h+var_18]
0x180019da5  mov     rbx, [rsp+80h+arg_0]
0x180019dad  mov     r15, [rsp+80h+var_20]
0x180019db2  add     rsp, 80h
0x180019db9  pop     r13
0x180019dbb  pop     rdi
0x180019dbc  pop     rbp
0x180019dbd  retn
0x180019dbe  mov     ecx, 10h; Size
0x180019dc3  call    cs:__imp_malloc
0x180019dc9  mov     rcx, rax
0x180019dcc  test    rax, rax
0x180019dcf  jz      loc_180019FDB
0x180019dd5  mov     rax, [rbp+hObject]
0x180019dd9  mov     [rbp+hObject], r14
0x180019ddd  mov     [rcx], rax
0x180019de0  mov     [rcx+8], rbx
0x180019de4  mov     [rdi], rcx
0x180019de7  mov     rcx, [rbp+hObject]; hObject
0x180019deb  lea     rax, [rcx-1]
0x180019def  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019df3  jbe     loc_18001A0FA
0x180019df9  test    r15d, r15d
0x180019dfc  jz      short loc_180019E04
0x180019dfe  call    cs:__imp_RpcRevertToSelf
0x180019e04  xor     eax, eax
0x180019e06  jmp     short loc_180019D96
0x180019e08  mov     rcx, [rbp+18h]; this
0x180019e0c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180019e13  mov     r9d, 80070057h; char *
0x180019e19  mov     edx, 10Fh; void *
0x180019e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e23  mov     eax, 80070057h
0x180019e28  add     rsp, 80h
0x180019e2f  pop     r13
0x180019e31  pop     rdi
0x180019e32  pop     rbp
0x180019e33  retn
0x180019e34  mov     rcx, [rbp+18h]; this
0x180019e38  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180019e3f  mov     r14d, 8007000Eh
0x180019e45  mov     edx, 276h; void *
0x180019e4a  mov     r9d, r14d; char *
0x180019e4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e52  jmp     loc_180019D5E
0x180019e57  mov     r8, rax; dwBytes
0x180019e5a  xor     edx, edx; dwFlags
0x180019e5c  call    cs:__imp_HeapAlloc
0x180019e62  mov     ecx, r14d
0x180019e65  mov     r14d, 8007000Eh
0x180019e6b  test    rax, rax
0x180019e6e  mov     [rbx+8], rax
0x180019e72  mov     rdx, rax
0x180019e75  cmovz   ecx, r14d
0x180019e79  mov     r14d, ecx
0x180019e7c  jz      loc_180019D3E
0x180019e82  xor     r14d, r14d
0x180019e85  cmp     r12, 7FFFFFFFh
0x180019e8c  ja      loc_18001A069
0x180019e92  cmp     rdi, 7FFFFFFFh
0x180019e99  jnb     loc_18001A060
0x180019e9f  test    r12, r12
0x180019ea2  jz      short loc_180019F0A
0x180019ea4  mov     rcx, r12
0x180019ea7  mov     r9d, r14d
0x180019eaa  mov     r10, rax
0x180019ead  nop     dword ptr [rax]
0x180019eb0  test    rdi, rdi
0x180019eb3  jz      short loc_180019EE0
0x180019eb5  movzx   eax, word ptr [rsi]
0x180019eb8  test    ax, ax
0x180019ebb  jz      short loc_180019EDB
0x180019ebd  mov     [rdx], ax
0x180019ec0  add     rsi, 2
0x180019ec4  add     rdx, 2
0x180019ec8  dec     rdi
0x180019ecb  inc     r9
0x180019ece  sub     rcx, 1
0x180019ed2  jnz     short loc_180019EB0
0x180019ed4  mov     [rdx-2], r14w
0x180019ed9  jmp     short loc_180019F0A
0x180019edb  test    rcx, rcx
0x180019ede  jz      short loc_180019ED4
0x180019ee0  sub     r12, r9
0x180019ee3  mov     [rdx], r14w
0x180019ee7  cmp     r12, 1
0x180019eeb  jbe     short loc_180019F0A
0x180019eed  lea     r8, [r12+r12]
0x180019ef1  cmp     r8, 2
0x180019ef5  jbe     short loc_180019F0A
0x180019ef7  add     r10, 2
0x180019efb  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180019eff  xor     edx, edx; Val
0x180019f01  lea     rcx, [r10+r9*2]; void *
0x180019f05  call    memset_0
0x180019f0a  mov     rdi, [r13+10h]
0x180019f0e  test    rdi, rdi
0x180019f11  jnz     loc_18001A072
0x180019f17  mov     rdi, [r13+18h]
0x180019f1b  test    rdi, rdi
0x180019f1e  jnz     loc_18001A0A7
0x180019f24  mov     rdi, [rbp+arg_10]
0x180019f28  jmp     loc_180019DBE
0x180019f2d  mov     rcx, [rbp+18h]; this
0x180019f31  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180019f38  mov     edx, 31h ; '1'; void *
0x180019f3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019f42  mov     rcx, [rbp+TokenHandle]; hObject
0x180019f46  mov     ebx, eax
0x180019f48  lea     rax, [rcx-1]
0x180019f4c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019f50  jbe     loc_18001A014
0x180019f56  test    ebx, ebx
0x180019f58  jns     loc_180019C57
0x180019f5e  mov     edx, 115h
0x180019f63  jmp     short loc_180019F74
0x180019f65  jg      short loc_180019F97
0x180019f67  test    ebx, ebx
0x180019f69  jns     loc_180019C0A
0x180019f6f  mov     edx, 113h; void *
0x180019f74  mov     rcx, [rbp+18h]; this
0x180019f78  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180019f7f  mov     r9d, ebx; char *
0x180019f82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f87  lea     rcx, [rbp+var_58]; this
0x180019f8b  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180019f90  mov     eax, ebx
0x180019f92  jmp     loc_180019DA0
0x180019f97  movzx   ebx, ax
0x180019f9a  or      ebx, 80070000h
0x180019fa0  jmp     short loc_180019F67
0x180019fa2  mov     rcx, [rbp+18h]; this
0x180019fa6  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180019fad  mov     edx, 11Dh; void *
0x180019fb2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019fb7  mov     rcx, [rbp+hObject]; hObject
0x180019fbb  mov     ebx, eax
0x180019fbd  lea     rdx, [rcx-1]
0x180019fc1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019fc5  jbe     loc_18001A055
0x180019fcb  lea     rcx, [rbp+var_58]; this
0x180019fcf  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180019fd4  mov     eax, ebx
0x180019fd6  jmp     loc_180019DA0
0x180019fdb  mov     rcx, [rbp+18h]; this
0x180019fdf  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x180019fe6  mov     edx, 12Ah; void *
0x180019feb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019ff0  mov     edi, eax
0x180019ff2  test    rbx, rbx
0x180019ff5  jnz     loc_18001A0ED
0x180019ffb  lea     rcx, [rbp+hObject]
0x180019fff  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a004  lea     rcx, [rbp+var_58]; this
0x18001a008  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001a00d  mov     eax, edi
0x18001a00f  jmp     loc_180019D96
0x18001a014  call    cs:__imp_CloseHandle
0x18001a01a  jmp     loc_180019F56
0x18001a01f  mov     rcx, [rbp+18h]; this
0x18001a023  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a02a  mov     ebx, 80070005h
0x18001a02f  mov     edx, 33h ; '3'; void *
0x18001a034  mov     r9d, ebx; char *
0x18001a037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a03c  lea     rcx, [rbp+TokenHandle]
0x18001a040  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a045  jmp     loc_180019F5E
0x18001a04a  call    cs:__imp_CloseHandle
0x18001a050  jmp     loc_180019C57
0x18001a055  call    cs:__imp_CloseHandle
0x18001a05b  jmp     loc_180019FCB
0x18001a060  test    r12, r12
0x18001a063  jz      loc_180019F0A
0x18001a069  mov     [rax], r14w
0x18001a06d  jmp     loc_180019F0A
  ... truncated ...
```
