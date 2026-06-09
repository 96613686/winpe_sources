# PlaiCreateStoreEntry(__MIDL_Registration_0002 *,_COLLECTORSET_STORE * *,void * *)

- ea: `0x18008cc94`
- end: `0x18008d6a8`
- name: `?PlaiCreateStoreEntry@@YAJPEAU__MIDL_Registration_0002@@PEAPEAU_COLLECTORSET_STORE@@PEAPEAX@Z`
- size: `2580`
- prototype: `__int64 __fastcall(struct __MIDL_Registration_0002 *, struct _COLLECTORSET_STORE **, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c7430`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x18002b3a0`
- `0x18008cc94`
- `0x18008d6b0`
- `0x1800d05a8`
- `0x180113c60`
- `0x18013ae9a`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18008ce0c`
- `msvcrt!_wcsnicmp` at `0x18008ce0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cfd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d12d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cfd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d12d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d4aa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008d326`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008d3e1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008d49c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008d326`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008d3e1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008d49c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008d66e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008d66e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008d300`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008d3bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008d476`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008d300`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008d3bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008d476`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18008cfc8`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18008d11f`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18008cfc8`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18008d11f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18008d1d7`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18008d1d7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008d26b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008d26b`

## string_xrefs

- `0x18008cd9a`: `PlaiCreateStoreEntry`
- `0x18008cee6`: `PlaiCreateStoreEntry`

## pseudocode

```c
__int64 __fastcall PlaiCreateStoreEntry(
        struct __MIDL_Registration_0002 *a1,
        struct _COLLECTORSET_STORE **a2,
        void **a3)
{
  void *v6; // rax
  void *v7; // rsi
  int v8; // ebx
  __int64 v9; // rax
  HANDLE v10; // r12
  int v11; // eax
  bool v12; // zf
  const wchar_t *v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  int CollectorSetPath; // eax
  __int64 v17; // rax
  DWORD v18; // eax
  __int64 v19; // rax
  void *v20; // rax
  __int64 v21; // rax
  DWORD LastError; // eax
  int v23; // eax
  __int64 v24; // rax
  RPC_STATUS v25; // eax
  int v26; // eax
  __int64 v27; // rax
  DWORD v28; // r8d
  DWORD v29; // eax
  __int64 v30; // rax
  HANDLE CurrentProcess; // rax
  DWORD v32; // eax
  int v33; // eax
  __int64 v34; // rax
  HANDLE v35; // rax
  DWORD v36; // eax
  int v37; // eax
  __int64 v38; // rax
  HANDLE v39; // rax
  DWORD v40; // eax
  int v41; // eax
  __int64 v42; // rax
  int UserToken; // eax
  const char *v44; // rdx
  int v45; // r8d
  __int64 v46; // rax
  unsigned __int16 *v47; // rax
  __int64 v48; // rax
  int lpnLengthNeeded; // [rsp+20h] [rbp-E0h]
  int lpnLengthNeededa; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+70h] [rbp-90h] BYREF
  int v53; // [rsp+78h] [rbp-88h] BYREF
  DWORD nLengthNeeded; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp-78h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v57[56]; // [rsp+98h] [rbp-68h] BYREF
  DWORD dwProcessId; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v59[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v60[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v61[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v62[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v63[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v64[64]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v65[64]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v66[64]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v67[64]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v68[64]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v69[64]; // [rsp+600h] [rbp+500h] BYREF
  unsigned __int16 v70[64]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 v71[64]; // [rsp+700h] [rbp+600h] BYREF

  nLengthNeeded = 0;
  memset_0(RpcCallAttributes, 0, 0x70u);
  lpFileName = 0;
  v6 = PlaiAlloc(0x68u, 1, 0, qword_180147320, lpnLengthNeeded);
  v7 = v6;
  if ( !v6 )
  {
    v8 = -2147024882;
    v53 = -2147024882;
    v52 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v59, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v59[v9] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v53,
        4,
        qword_180147320,
        1,
        &v52,
        4,
        "PlaiCreateStoreEntry",
        21);
    }
LABEL_106:
    PlaiDeleteStoreEntry((struct _COLLECTORSET_STORE *)v7);
    return (unsigned int)v8;
  }
  v10 = 0;
  memset_0(v6, 0, 0x68u);
  *((_DWORD *)v7 + 6) = 554113408;
  v11 = _wcsnicmp(L"system\\", *(const wchar_t **)a1, 7u);
  v12 = !g_isTaskSchedulerUseXMLStoreEnabled;
  *((_DWORD *)v7 + 22) = v11 == 0;
  if ( v12 )
    goto LABEL_48;
  v13 = *(const wchar_t **)a1;
  if ( v11 )
  {
    CollectorSetPath = PlaiCreateCollectorSetPath(v13, 0, (unsigned __int16 **)&lpFileName);
    v8 = CollectorSetPath;
    if ( CollectorSetPath < 0 )
    {
      v53 = 0;
      v52 = CollectorSetPath;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v61, 0x4000000000000800uLL);
        v17 = -1;
        do
          ++v17;
        while ( v61[v17] );
        goto LABEL_16;
      }
      goto LABEL_101;
    }
  }
  else
  {
    v14 = PlaiCreateCollectorSetPath(v13 + 7, 1, (unsigned __int16 **)&lpFileName);
    v8 = v14;
    if ( v14 < 0 )
    {
      v53 = 0;
      v52 = v14;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v60, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v60[v15] );
LABEL_16:
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v52,
          4,
          qword_180147320,
          1,
          &v53,
          4,
          "PlaiCreateStoreEntry",
          21);
        goto LABEL_101;
      }
      goto LABEL_101;
    }
  }
  if ( GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded)
    || (v18 = GetLastError(), v8 = PlaiHResultFromWin32(v18), (int)(v8 + 0x80000000) < 0)
    || v8 == -2147024774 )
  {
    v20 = PlaiAlloc(nLengthNeeded, 1, 0, qword_180147320, lpnLengthNeededa);
    *((_QWORD *)v7 + 10) = v20;
    if ( !v20 )
    {
      v8 = -2147024882;
      v52 = -2147024882;
      v53 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v63, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v63[v21] );
        goto LABEL_16;
      }
      goto LABEL_101;
    }
    if ( !GetFileSecurityW(lpFileName, 7u, v20, nLengthNeeded, &nLengthNeeded) )
    {
      LastError = GetLastError();
      v23 = PlaiHResultFromWin32(LastError);
      v8 = v23;
      if ( v23 < 0 )
      {
        v53 = 0;
        v52 = v23;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v64, 0x4000000000000800uLL);
          v24 = -1;
          do
            ++v24;
          while ( v64[v24] );
          goto LABEL_16;
        }
        goto LABEL_101;
      }
    }
LABEL_48:
    memset_0(v57, 0, 0x68u);
    RpcCallAttributes[0] = 3;
    RpcCallAttributes[1] = 16;
    v25 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
    v26 = PlaiHResultFromWin32(v25);
    v8 = v26;
    if ( v26 >= 0 )
    {
      v28 = dwProcessId;
      *((_DWORD *)v7 + 16) = dwProcessId;
      v10 = OpenProcess(0x40u, 0, v28);
      if ( v10 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( DuplicateHandle(v10, *((HANDLE *)a1 + 1), CurrentProcess, (LPHANDLE)v7 + 4, 0, 0, 2u)
          || (v32 = GetLastError(), v33 = PlaiHResultFromWin32(v32), v8 = v33, v33 >= 0) )
        {
          v35 = GetCurrentProcess();
          if ( DuplicateHandle(v10, *((HANDLE *)a1 + 2), v35, (LPHANDLE)v7 + 5, 0, 0, 2u)
            || (v36 = GetLastError(), v37 = PlaiHResultFromWin32(v36), v8 = v37, v37 >= 0) )
          {
            v39 = GetCurrentProcess();
            if ( DuplicateHandle(v10, *((HANDLE *)a1 + 3), v39, (LPHANDLE)v7 + 6, 0, 0, 2u)
              || (v40 = GetLastError(), v41 = PlaiHResultFromWin32(v40), v8 = v41, v41 >= 0) )
            {
              UserToken = PlaiGetUserToken((PHANDLE)v7 + 7);
              v8 = UserToken;
              if ( UserToken >= 0 )
              {
                v47 = PlaiAllocStringEx(*(const unsigned __int16 **)a1, v44, v45);
                *((_QWORD *)v7 + 2) = v47;
                if ( v47 )
                {
                  *((_QWORD *)v7 + 12) = (char *)v47 + (*((_DWORD *)v7 + 22) != 0 ? 0xE : 0);
                  *a2 = (struct _COLLECTORSET_STORE *)v7;
                  *a3 = v10;
                }
                else
                {
                  v8 = -2147024882;
                  v52 = -2147024882;
                  v53 = 0;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v71, 0x4000000000000800uLL);
                    v48 = -1;
                    do
                      ++v48;
                    while ( v71[v48] );
                    goto LABEL_16;
                  }
                }
              }
              else
              {
                v53 = 0;
                v52 = UserToken;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v70, 0x4000000000000800uLL);
                  v46 = -1;
                  do
                    ++v46;
                  while ( v70[v46] );
                  goto LABEL_16;
                }
              }
            }
            else
            {
              v53 = 0;
              v52 = v41;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v69, 0x4000000000000800uLL);
                v42 = -1;
                do
                  ++v42;
                while ( v69[v42] );
                goto LABEL_16;
              }
            }
          }
          else
          {
            v53 = 0;
            v52 = v37;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v68, 0x4000000000000800uLL);
              v38 = -1;
              do
                ++v38;
              while ( v68[v38] );
              goto LABEL_16;
            }
          }
        }
        else
        {
          v53 = 0;
          v52 = v33;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v67, 0x4000000000000800uLL);
            v34 = -1;
            do
              ++v34;
            while ( v67[v34] );
            goto LABEL_16;
          }
        }
      }
      else
      {
        v29 = GetLastError();
        v8 = PlaiHResultFromWin32(v29);
        v53 = 0;
        v52 = v8;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v66, 0x4000000000000800uLL);
          v30 = -1;
          do
            ++v30;
          while ( v66[v30] );
          goto LABEL_16;
        }
      }
    }
    else
    {
      v53 = 0;
      v52 = v26;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v65, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v65[v27] );
        goto LABEL_16;
      }
    }
    goto LABEL_101;
  }
  v53 = 0;
  v52 = v8;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v62, 0x4000000000000800uLL);
    v19 = -1;
    do
      ++v19;
    while ( v62[v19] );
    goto LABEL_16;
  }
LABEL_101:
  if ( lpFileName )
    PlaiFree(lpFileName, 1);
  if ( v8 < 0 )
  {
    if ( v10 )
      CloseHandle(v10);
    goto LABEL_106;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008cc94  mov     [rsp-8+arg_18], rbx
0x18008cc99  push    rbp
0x18008cc9a  push    rsi
0x18008cc9b  push    rdi
0x18008cc9c  push    r12
0x18008cc9e  push    r13
0x18008cca0  push    r14
0x18008cca2  push    r15
0x18008cca4  lea     rbp, [rsp-690h]
0x18008ccac  sub     rsp, 790h
0x18008ccb3  mov     rax, cs:__security_cookie
0x18008ccba  xor     rax, rsp
0x18008ccbd  mov     [rbp+6C0h+var_40], rax
0x18008ccc4  xor     r13d, r13d
0x18008ccc7  mov     r15, r8
0x18008ccca  mov     r14, rdx
0x18008cccd  mov     [rbp+6C0h+nLengthNeeded], r13d
0x18008ccd1  mov     rdi, rcx
0x18008ccd4  xor     edx, edx; Val
0x18008ccd6  lea     rcx, [rbp+6C0h+RpcCallAttributes]; void *
0x18008ccda  lea     r8d, [r13+70h]; Size
0x18008ccde  call    memset_0
0x18008cce3  lea     edx, [r13+1]; int
0x18008cce7  mov     [rbp+6C0h+lpFileName], r13
0x18008cceb  lea     r12, qword_180147320
0x18008ccf2  xor     r8d, r8d; int
0x18008ccf5  mov     r9, r12; char *
0x18008ccf8  lea     ecx, [rdx+67h]; dwBytes
0x18008ccfb  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18008cd00  mov     rsi, rax
0x18008cd03  test    rax, rax
0x18008cd06  jnz     loc_18008CDE4
0x18008cd0c  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008cd13  mov     ecx, 8007000Eh
0x18008cd18  mov     ebx, ecx
0x18008cd1a  mov     [rsp+7C0h+var_748], ecx
0x18008cd1e  mov     [rsp+7C0h+var_750], r13d
0x18008cd23  jz      loc_18008D674
0x18008cd29  mov     rdx, 4000000000000800h; unsigned __int64
0x18008cd33  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008cd3a  jz      loc_18008D674
0x18008cd40  mov     rax, cs:qword_180169748
0x18008cd47  and     rax, rdx
0x18008cd4a  cmp     cs:qword_180169748, rax
0x18008cd51  jnz     loc_18008D674
0x18008cd57  lea     rcx, [rbp+6C0h+var_6C0]; unsigned __int16 *
0x18008cd5b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008cd60  lea     rcx, [rbp+6C0h+var_6C0]
0x18008cd64  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008cd68  inc     rax
0x18008cd6b  cmp     [rcx+rax*2], r13w
0x18008cd70  jnz     short loc_18008CD68
0x18008cd72  lea     ecx, [rax+rax]
0x18008cd75  add     rcx, 2
0x18008cd79  lea     rax, [rbp+6C0h+var_6C0]
0x18008cd7d  mov     [rsp+7C0h+var_760], rcx
0x18008cd82  lea     r9, [rsp+7C0h+var_748]
0x18008cd87  mov     [rsp+7C0h+var_768], rax
0x18008cd8c  lea     rcx, [rsp+7C0h+var_750]
0x18008cd91  mov     [rsp+7C0h+var_770], 15h
0x18008cd9a  lea     rax, aPlaicreatestor; "PlaiCreateStoreEntry"
0x18008cda1  mov     [rsp+7C0h+var_778], rax
0x18008cda6  lea     rdx, PLA_EVENT_ERROR
0x18008cdad  mov     eax, 4
0x18008cdb2  mov     [rsp+7C0h+var_780], rax
0x18008cdb7  mov     [rsp+7C0h+var_788], rcx
0x18008cdbc  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18008cdc3  mov     qword ptr [rsp+7C0h+dwOptions], 1
0x18008cdcc  mov     qword ptr [rsp+7C0h+bInheritHandle], r12
0x18008cdd1  lea     r8d, [rax+1]
0x18008cdd5  mov     [rsp+7C0h+lpnLengthNeeded], rax
0x18008cdda  call    EventingWriteEvent
0x18008cddf  jmp     loc_18008D674
0x18008cde4  xor     edx, edx; Val
0x18008cde6  mov     rcx, rsi; void *
0x18008cde9  mov     r12, r13
0x18008cdec  lea     r8d, [rdx+68h]; Size
0x18008cdf0  call    memset_0
0x18008cdf5  mov     dword ptr [rsi+18h], 21071980h
0x18008cdfc  lea     rcx, aSystem; "system\\"
0x18008ce03  mov     rdx, [rdi]; String2
0x18008ce06  mov     r8d, 7; MaxCount
0x18008ce0c  call    cs:__imp__wcsnicmp
0x18008ce12  test    eax, eax
0x18008ce14  mov     ecx, r13d
0x18008ce17  setz    cl
0x18008ce1a  cmp     cs:?g_isTaskSchedulerUseXMLStoreEnabled@@3_NA, r13b; bool g_isTaskSchedulerUseXMLStoreEnabled
0x18008ce21  mov     [rsi+58h], ecx
0x18008ce24  jz      loc_18008D1B4
0x18008ce2a  mov     rcx, [rdi]; unsigned __int16 *
0x18008ce2d  lea     r8, [rbp+6C0h+lpFileName]; unsigned __int16 **
0x18008ce31  test    eax, eax
0x18008ce33  jnz     loc_18008CF30
0x18008ce39  add     rcx, 0Eh; unsigned __int16 *
0x18008ce3d  lea     edx, [rax+1]; int
0x18008ce40  call    ?PlaiCreateCollectorSetPath@@YAJPEBGHPEAPEAG@Z; PlaiCreateCollectorSetPath(ushort const *,int,ushort * *)
0x18008ce45  mov     ebx, eax
0x18008ce47  test    eax, eax
0x18008ce49  jns     loc_18008CFB1
0x18008ce4f  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008ce56  mov     [rsp+7C0h+var_748], r13d
0x18008ce5b  mov     [rsp+7C0h+var_750], eax
0x18008ce5f  jz      loc_18008D64F
0x18008ce65  mov     rdx, 4000000000000800h; unsigned __int64
0x18008ce6f  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008ce76  jz      loc_18008D64F
0x18008ce7c  mov     rax, cs:qword_180169748
0x18008ce83  and     rax, rdx
0x18008ce86  cmp     cs:qword_180169748, rax
0x18008ce8d  jnz     loc_18008D64F
0x18008ce93  lea     rcx, [rbp+6C0h+var_640]; unsigned __int16 *
0x18008ce9a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008ce9f  lea     rcx, [rbp+6C0h+var_640]
0x18008cea6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008ceaa  inc     rax
0x18008cead  cmp     [rcx+rax*2], r13w
0x18008ceb2  jnz     short loc_18008CEAA
0x18008ceb4  lea     ecx, [rax+rax]
0x18008ceb7  lea     rax, [rbp+6C0h+var_640]
0x18008cebe  add     rcx, 2
0x18008cec2  lea     r9, [rsp+7C0h+var_750]
0x18008cec7  mov     [rsp+7C0h+var_760], rcx
0x18008cecc  lea     rdx, PLA_EVENT_ERROR
0x18008ced3  mov     [rsp+7C0h+var_768], rax
0x18008ced8  lea     rcx, [rsp+7C0h+var_748]
0x18008cedd  mov     [rsp+7C0h+var_770], 15h
0x18008cee6  lea     rax, aPlaicreatestor; "PlaiCreateStoreEntry"
0x18008ceed  mov     [rsp+7C0h+var_778], rax
0x18008cef2  mov     eax, 4
0x18008cef7  mov     [rsp+7C0h+var_780], rax
0x18008cefc  mov     [rsp+7C0h+var_788], rcx
0x18008cf01  lea     rcx, qword_180147320
0x18008cf08  mov     qword ptr [rsp+7C0h+dwOptions], 1
0x18008cf11  mov     qword ptr [rsp+7C0h+bInheritHandle], rcx
0x18008cf16  lea     r8d, [rax+1]
0x18008cf1a  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18008cf21  mov     [rsp+7C0h+lpnLengthNeeded], rax
0x18008cf26  call    EventingWriteEvent
0x18008cf2b  jmp     loc_18008D64F
0x18008cf30  xor     edx, edx; int
0x18008cf32  call    ?PlaiCreateCollectorSetPath@@YAJPEBGHPEAPEAG@Z; PlaiCreateCollectorSetPath(ushort const *,int,ushort * *)
0x18008cf37  mov     ebx, eax
0x18008cf39  test    eax, eax
0x18008cf3b  jns     short loc_18008CFB1
0x18008cf3d  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008cf44  mov     [rsp+7C0h+var_748], r13d
0x18008cf49  mov     [rsp+7C0h+var_750], eax
0x18008cf4d  jz      loc_18008D64F
0x18008cf53  mov     rdx, 4000000000000800h; unsigned __int64
0x18008cf5d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008cf64  jz      loc_18008D64F
0x18008cf6a  mov     rax, cs:qword_180169748
0x18008cf71  and     rax, rdx
0x18008cf74  cmp     cs:qword_180169748, rax
0x18008cf7b  jnz     loc_18008D64F
0x18008cf81  lea     rcx, [rbp+6C0h+var_5C0]; unsigned __int16 *
0x18008cf88  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008cf8d  lea     rcx, [rbp+6C0h+var_5C0]
0x18008cf94  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008cf98  inc     rax
0x18008cf9b  cmp     [rcx+rax*2], r13w
0x18008cfa0  jnz     short loc_18008CF98
0x18008cfa2  lea     ecx, [rax+rax]
0x18008cfa5  lea     rax, [rbp+6C0h+var_5C0]
0x18008cfac  jmp     loc_18008CEBE
0x18008cfb1  mov     rcx, [rbp+6C0h+lpFileName]; lpFileName
0x18008cfb5  lea     rax, [rbp+6C0h+nLengthNeeded]
0x18008cfb9  xor     r9d, r9d; nLength
0x18008cfbc  mov     [rsp+7C0h+lpnLengthNeeded], rax; int
0x18008cfc1  xor     r8d, r8d; pSecurityDescriptor
0x18008cfc4  lea     edx, [r9+7]; RequestedInformation
0x18008cfc8  call    cs:__imp_GetFileSecurityW
0x18008cfce  test    eax, eax
0x18008cfd0  jnz     loc_18008D06C
0x18008cfd6  call    cs:__imp_GetLastError
0x18008cfdc  mov     ecx, eax; unsigned int
0x18008cfde  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18008cfe3  mov     ecx, 80000000h
0x18008cfe8  mov     ebx, eax
0x18008cfea  add     eax, ecx
0x18008cfec  test    ecx, eax
0x18008cfee  jnz     short loc_18008D06C
0x18008cff0  cmp     ebx, 8007007Ah
0x18008cff6  jz      short loc_18008D06C
0x18008cff8  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008cfff  mov     [rsp+7C0h+var_748], r13d
0x18008d004  mov     [rsp+7C0h+var_750], ebx
0x18008d008  jz      loc_18008D64F
0x18008d00e  mov     rdx, 4000000000000800h; unsigned __int64
0x18008d018  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008d01f  jz      loc_18008D64F
0x18008d025  mov     rax, cs:qword_180169748
0x18008d02c  and     rax, rdx
0x18008d02f  cmp     cs:qword_180169748, rax
0x18008d036  jnz     loc_18008D64F
0x18008d03c  lea     rcx, [rbp+6C0h+var_540]; unsigned __int16 *
0x18008d043  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008d048  lea     rcx, [rbp+6C0h+var_540]
0x18008d04f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008d053  inc     rax
0x18008d056  cmp     [rcx+rax*2], r13w
0x18008d05b  jnz     short loc_18008D053
0x18008d05d  lea     ecx, [rax+rax]
0x18008d060  lea     rax, [rbp+6C0h+var_540]
0x18008d067  jmp     loc_18008CEBE
0x18008d06c  mov     ecx, [rbp+6C0h+nLengthNeeded]; dwBytes
0x18008d06f  lea     r9, qword_180147320; char *
0x18008d076  xor     r8d, r8d; int
0x18008d079  lea     edx, [r8+1]; int
0x18008d07d  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18008d082  mov     [rsi+50h], rax
0x18008d086  test    rax, rax
0x18008d089  jnz     short loc_18008D106
0x18008d08b  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008d092  mov     ecx, 8007000Eh
0x18008d097  mov     ebx, ecx
0x18008d099  mov     [rsp+7C0h+var_750], ecx
0x18008d09d  mov     [rsp+7C0h+var_748], r13d
0x18008d0a2  jz      loc_18008D64F
0x18008d0a8  mov     rdx, 4000000000000800h; unsigned __int64
0x18008d0b2  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008d0b9  jz      loc_18008D64F
0x18008d0bf  mov     rax, cs:qword_180169748
0x18008d0c6  and     rax, rdx
0x18008d0c9  cmp     cs:qword_180169748, rax
0x18008d0d0  jnz     loc_18008D64F
0x18008d0d6  lea     rcx, [rbp+6C0h+var_4C0]; unsigned __int16 *
0x18008d0dd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008d0e2  lea     rcx, [rbp+6C0h+var_4C0]
0x18008d0e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008d0ed  inc     rax
0x18008d0f0  cmp     [rcx+rax*2], r13w
0x18008d0f5  jnz     short loc_18008D0ED
0x18008d0f7  lea     ecx, [rax+rax]
0x18008d0fa  lea     rax, [rbp+6C0h+var_4C0]
0x18008d101  jmp     loc_18008CEBE
0x18008d106  mov     r9d, [rbp+6C0h+nLengthNeeded]; nLength
0x18008d10a  lea     rcx, [rbp+6C0h+nLengthNeeded]
0x18008d10e  mov     [rsp+7C0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18008d113  mov     r8, rax; pSecurityDescriptor
0x18008d116  mov     rcx, [rbp+6C0h+lpFileName]; lpFileName
0x18008d11a  mov     edx, 7; RequestedInformation
0x18008d11f  call    cs:__imp_GetFileSecurityW
0x18008d125  test    eax, eax
0x18008d127  jnz     loc_18008D1B4
0x18008d12d  call    cs:__imp_GetLastError
0x18008d133  mov     ecx, eax; unsigned int
0x18008d135  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18008d13a  mov     ebx, eax
0x18008d13c  test    eax, eax
0x18008d13e  jns     short loc_18008D1B4
0x18008d140  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008d147  mov     [rsp+7C0h+var_748], r13d
0x18008d14c  mov     [rsp+7C0h+var_750], eax
0x18008d150  jz      loc_18008D64F
0x18008d156  mov     rdx, 4000000000000800h; unsigned __int64
0x18008d160  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008d167  jz      loc_18008D64F
0x18008d16d  mov     rax, cs:qword_180169748
0x18008d174  and     rax, rdx
0x18008d177  cmp     cs:qword_180169748, rax
0x18008d17e  jnz     loc_18008D64F
0x18008d184  lea     rcx, [rbp+6C0h+var_440]; unsigned __int16 *
0x18008d18b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008d190  lea     rcx, [rbp+6C0h+var_440]
0x18008d197  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008d19b  inc     rax
0x18008d19e  cmp     [rcx+rax*2], r13w
0x18008d1a3  jnz     short loc_18008D19B
0x18008d1a5  lea     ecx, [rax+rax]
0x18008d1a8  lea     rax, [rbp+6C0h+var_440]
0x18008d1af  jmp     loc_18008CEBE
0x18008d1b4  xor     edx, edx; Val
0x18008d1b6  lea     rcx, [rbp+6C0h+var_728]; void *
0x18008d1ba  lea     r8d, [rdx+68h]; Size
0x18008d1be  call    memset_0
0x18008d1c3  lea     rdx, [rbp+6C0h+RpcCallAttributes]; RpcCallAttributes
0x18008d1c7  mov     [rbp+6C0h+RpcCallAttributes], 3
0x18008d1ce  xor     ecx, ecx; ClientBinding
0x18008d1d0  mov     [rbp+6C0h+var_72C], 10h
0x18008d1d7  call    cs:__imp_RpcServerInqCallAttributesW
0x18008d1dd  mov     ecx, eax; unsigned int
0x18008d1df  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18008d1e4  mov     ebx, eax
0x18008d1e6  test    eax, eax
0x18008d1e8  jns     short loc_18008D25E
0x18008d1ea  cmp     dword ptr cs:xmmword_180169738, r13d
0x18008d1f1  mov     [rsp+7C0h+var_748], r13d
0x18008d1f6  mov     [rsp+7C0h+var_750], eax
0x18008d1fa  jz      loc_18008D64F
0x18008d200  mov     rdx, 4000000000000800h; unsigned __int64
0x18008d20a  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008d211  jz      loc_18008D64F
0x18008d217  mov     rax, cs:qword_180169748
0x18008d21e  and     rax, rdx
0x18008d221  cmp     cs:qword_180169748, rax
0x18008d228  jnz     loc_18008D64F
0x18008d22e  lea     rcx, [rbp+6C0h+var_3C0]; unsigned __int16 *
0x18008d235  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008d23a  lea     rcx, [rbp+6C0h+var_3C0]
  ... truncated ...
```
