# LoadGPExtension(_GPEXT *,int)

- ea: `0x18009a4b8`
- end: `0x18009a790`
- name: `?LoadGPExtension@@YAHPEAU_GPEXT@@H@Z`
- size: `728`
- prototype: `__int64 __fastcall(struct _GPEXT *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18006a2e0`
- `0x18009819c`

## callees

- `0x180075ec0`
- `0x18009a4b8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a50f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a5a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a61f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a50f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a5a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a61f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009a4ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009a4ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a77f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009a77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a4c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a4c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a756`

## string_xrefs

- `0x18009a548`: `LoadGPExtension: Failed to query ProcessGroupPolicyEx function entry point in dll <%s> with %d`
- `0x18009a57d`: `LoadGPExtension: Failed to query ProcessGroupPolicyEx function entry point in dll <%s> with %d`
- `0x18009a5da`: `LoadGPExtension: Failed to query ProcessGroupPolicy function entry point in dll <%s> with %d`
- `0x18009a5fe`: `LoadGPExtension: Failed to query ProcessGroupPolicy function entry point in dll <%s> with %d`
- `0x18009a65c`: `LoadGPExtension: Failed to query GenerateGroupPolicy function entry point in dll <%s> with %d`
- `0x18009a688`: `LoadGPExtension: Failed to query GenerateGroupPolicy function entry point in dll <%s> with %d`
- `0x18009a6b9`: `LoadGPExtension: Failed to find Rsop entry point in dll <%s>`
- `0x18009a6eb`: `LoadGPExtension: Failed to find Rsop entry point in dll <%s>`
- `0x18009a72e`: `LoadGPExtension: Failed to load dll <%s> with %d`
- `0x18009a763`: `LoadGPExtension: Failed to load dll <%s> with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LoadGPExtension(struct _GPEXT *a1, int a2)
{
  DWORD LastError; // ebx
  HMODULE Library; // rax
  const CHAR *v6; // rdx
  FARPROC ProcAddress; // rax
  DWORD v8; // ebx
  void (*v9)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v10; // eax
  const wchar_t *v11; // rdx
  DWORD v12; // eax
  FARPROC v14; // rax
  DWORD v15; // eax
  const CHAR *v16; // rdx
  FARPROC v17; // rax
  DWORD v18; // eax
  void (*v19)(unsigned int, const unsigned __int16 *, ...); // rsi
  DWORD v20; // eax
  DWORD v21; // eax
  unsigned int v22; // edi

  LastError = GetLastError();
  if ( !*((_DWORD *)a1 + 29) && !*((_QWORD *)a1 + 5) )
  {
    Library = LoadLibraryExW(*((LPCWSTR *)a1 + 2), 0, 0);
    *((_QWORD *)a1 + 5) = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v19 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v20 = GetLastError();
          v19(2u, L"LoadGPExtension: Failed to load dll <%s> with %d", *((_QWORD *)a1 + 2), v20);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v21 = GetLastError();
          RedirectDebugMsg(2u, L"LoadGPExtension: Failed to load dll <%s> with %d", *((_QWORD *)a1 + 2), v21);
        }
      }
      v22 = 0;
      goto LABEL_44;
    }
    v6 = (const CHAR *)*((_QWORD *)a1 + 3);
    if ( *((_DWORD *)a1 + 18) )
    {
      ProcAddress = GetProcAddress(Library, v6);
      *((_QWORD *)a1 + 7) = ProcAddress;
      if ( !ProcAddress )
      {
        v8 = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
        {
LABEL_13:
          SetLastError(v8);
          return 0;
        }
        v9 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance )
          {
            if ( g_lpDebugMsgContext )
            {
              v12 = GetLastError();
              RedirectDebugMsg(
                2u,
                L"LoadGPExtension: Failed to query ProcessGroupPolicyEx function entry point in dll <%s> with %d",
                *((_QWORD *)a1 + 2),
                v12);
            }
          }
          goto LABEL_13;
        }
        v10 = GetLastError();
        v11 = L"LoadGPExtension: Failed to query ProcessGroupPolicyEx function entry point in dll <%s> with %d";
LABEL_9:
        v9(2u, v11, *((_QWORD *)a1 + 2), v10);
        goto LABEL_13;
      }
    }
    else
    {
      v14 = GetProcAddress(Library, v6);
      *((_QWORD *)a1 + 6) = v14;
      if ( !v14 )
      {
        v8 = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_13;
        v9 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v15 = GetLastError();
            RedirectDebugMsg(
              2u,
              L"LoadGPExtension: Failed to query ProcessGroupPolicy function entry point in dll <%s> with %d",
              *((_QWORD *)a1 + 2),
              v15);
          }
          goto LABEL_13;
        }
        v10 = GetLastError();
        v11 = L"LoadGPExtension: Failed to query ProcessGroupPolicy function entry point in dll <%s> with %d";
        goto LABEL_9;
      }
    }
    if ( a2 )
    {
      v16 = (const CHAR *)*((_QWORD *)a1 + 4);
      if ( !v16 )
      {
        v8 = 127;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"LoadGPExtension: Failed to find Rsop entry point in dll <%s>", *((_QWORD *)a1 + 2));
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"LoadGPExtension: Failed to find Rsop entry point in dll <%s>", *((_QWORD *)a1 + 2));
          }
        }
        goto LABEL_13;
      }
      v17 = GetProcAddress(*((HMODULE *)a1 + 5), v16);
      *((_QWORD *)a1 + 8) = v17;
      if ( !v17 )
      {
        v8 = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_13;
        v9 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v18 = GetLastError();
            RedirectDebugMsg(
              2u,
              L"LoadGPExtension: Failed to query GenerateGroupPolicy function entry point in dll <%s> with %d",
              *((_QWORD *)a1 + 2),
              v18);
          }
          goto LABEL_13;
        }
        v10 = GetLastError();
        v11 = L"LoadGPExtension: Failed to query GenerateGroupPolicy function entry point in dll <%s> with %d";
        goto LABEL_9;
      }
    }
  }
  v22 = 1;
LABEL_44:
  SetLastError(LastError);
  return v22;
}

```

## disassembly

```asm
0x18009a4b8  push    rbx
0x18009a4ba  push    rbp
0x18009a4bb  push    rsi
0x18009a4bc  push    rdi
0x18009a4bd  sub     rsp, 38h
0x18009a4c1  mov     esi, edx
0x18009a4c3  mov     rdi, rcx
0x18009a4c6  call    cs:__imp_GetLastError
0x18009a4cc  mov     ebx, eax
0x18009a4ce  xor     ebp, ebp
0x18009a4d0  cmp     [rdi+74h], ebp
0x18009a4d3  jnz     loc_18009A778
0x18009a4d9  cmp     [rdi+28h], rbp
0x18009a4dd  jnz     loc_18009A778
0x18009a4e3  xor     r8d, r8d; dwFlags
0x18009a4e6  xor     edx, edx; hFile
0x18009a4e8  mov     rcx, [rdi+10h]; lpLibFileName
0x18009a4ec  call    cs:__imp_LoadLibraryExW
0x18009a4f2  mov     [rdi+28h], rax
0x18009a4f6  test    rax, rax
0x18009a4f9  jz      loc_18009A701
0x18009a4ff  mov     rdx, [rdi+18h]; lpProcName
0x18009a503  mov     rcx, rax; hModule
0x18009a506  cmp     [rdi+48h], ebp
0x18009a509  jz      loc_18009A5A5
0x18009a50f  call    cs:__imp_GetProcAddress
0x18009a515  mov     [rdi+38h], rax
0x18009a519  test    rax, rax
0x18009a51c  jnz     loc_18009A60A
0x18009a522  call    cs:__imp_GetLastError
0x18009a528  mov     ebx, eax
0x18009a52a  mov     [rsp+58h+arg_0], eax
0x18009a52e  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18009a534  jz      short loc_18009A596
0x18009a536  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a53d  test    rsi, rsi
0x18009a540  jz      short loc_18009A565
0x18009a542  call    cs:__imp_GetLastError
0x18009a548  lea     rdx, aLoadgpextensio_2; "LoadGPExtension: Failed to query Proces"...
0x18009a54f  mov     r9d, eax
0x18009a552  mov     r8, [rdi+10h]
0x18009a556  mov     ecx, 2
0x18009a55b  mov     rax, rsi
0x18009a55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a563  jmp     short loc_18009A596
0x18009a565  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18009a56c  jz      short loc_18009A596
0x18009a56e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a575  jz      short loc_18009A596
0x18009a577  call    cs:__imp_GetLastError
0x18009a57d  lea     rdx, aLoadgpextensio_2; "LoadGPExtension: Failed to query Proces"...
0x18009a584  mov     r9d, eax
0x18009a587  mov     r8, [rdi+10h]
0x18009a58b  mov     ecx, 2; unsigned int
0x18009a590  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a595  nop
0x18009a596  mov     ecx, ebx; dwErrCode
0x18009a598  call    cs:__imp_SetLastError
0x18009a59e  xor     eax, eax
0x18009a5a0  jmp     loc_18009A787
0x18009a5a5  call    cs:__imp_GetProcAddress
0x18009a5ab  mov     [rdi+30h], rax
0x18009a5af  test    rax, rax
0x18009a5b2  jnz     short loc_18009A60A
0x18009a5b4  call    cs:__imp_GetLastError
0x18009a5ba  mov     ebx, eax
0x18009a5bc  mov     [rsp+58h+arg_0], eax
0x18009a5c0  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18009a5c6  jz      short loc_18009A596
0x18009a5c8  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a5cf  test    rsi, rsi
0x18009a5d2  jz      short loc_18009A5E6
0x18009a5d4  call    cs:__imp_GetLastError
0x18009a5da  lea     rdx, aLoadgpextensio; "LoadGPExtension: Failed to query Proces"...
0x18009a5e1  jmp     loc_18009A54F
0x18009a5e6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18009a5ed  jz      short loc_18009A596
0x18009a5ef  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a5f6  jz      short loc_18009A596
0x18009a5f8  call    cs:__imp_GetLastError
0x18009a5fe  lea     rdx, aLoadgpextensio; "LoadGPExtension: Failed to query Proces"...
0x18009a605  jmp     loc_18009A584
0x18009a60a  test    esi, esi
0x18009a60c  jz      loc_18009A778
0x18009a612  mov     rdx, [rdi+20h]; lpProcName
0x18009a616  test    rdx, rdx
0x18009a619  jz      short loc_18009A694
0x18009a61b  mov     rcx, [rdi+28h]; hModule
0x18009a61f  call    cs:__imp_GetProcAddress
0x18009a625  mov     [rdi+40h], rax
0x18009a629  test    rax, rax
0x18009a62c  jnz     loc_18009A778
0x18009a632  call    cs:__imp_GetLastError
0x18009a638  mov     ebx, eax
0x18009a63a  mov     [rsp+58h+arg_0], eax
0x18009a63e  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18009a644  jz      loc_18009A596
0x18009a64a  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a651  test    rsi, rsi
0x18009a654  jz      short loc_18009A668
0x18009a656  call    cs:__imp_GetLastError
0x18009a65c  lea     rdx, aLoadgpextensio_1; "LoadGPExtension: Failed to query Genera"...
0x18009a663  jmp     loc_18009A54F
0x18009a668  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18009a66f  jz      loc_18009A596
0x18009a675  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a67c  jz      loc_18009A596
0x18009a682  call    cs:__imp_GetLastError
0x18009a688  lea     rdx, aLoadgpextensio_1; "LoadGPExtension: Failed to query Genera"...
0x18009a68f  jmp     loc_18009A584
0x18009a694  mov     ebx, 7Fh
0x18009a699  mov     [rsp+58h+arg_0], ebx
0x18009a69d  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18009a6a3  jz      loc_18009A596
0x18009a6a9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a6b0  test    rax, rax
0x18009a6b3  jz      short loc_18009A6CD
0x18009a6b5  mov     r8, [rdi+10h]
0x18009a6b9  lea     rdx, aLoadgpextensio_0; "LoadGPExtension: Failed to find Rsop en"...
0x18009a6c0  lea     ecx, [rbx-7Dh]
0x18009a6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a6c8  jmp     loc_18009A596
0x18009a6cd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18009a6d4  jz      loc_18009A596
0x18009a6da  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a6e1  jz      loc_18009A596
0x18009a6e7  mov     r8, [rdi+10h]
0x18009a6eb  lea     rdx, aLoadgpextensio_0; "LoadGPExtension: Failed to find Rsop en"...
0x18009a6f2  mov     ecx, 2; unsigned int
0x18009a6f7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a6fc  jmp     loc_18009A596
0x18009a701  call    cs:__imp_GetLastError
0x18009a707  mov     ebx, eax
0x18009a709  mov     [rsp+58h+arg_0], eax
0x18009a70d  cmp     cs:?g_dwDebugLevel@@3KA, ebp; ulong g_dwDebugLevel
0x18009a713  jz      short loc_18009A774
0x18009a715  mov     rsi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009a71c  test    rsi, rsi
0x18009a71f  jz      short loc_18009A744
0x18009a721  call    cs:__imp_GetLastError
0x18009a727  mov     r9d, eax
0x18009a72a  mov     r8, [rdi+10h]
0x18009a72e  lea     rdx, aLoadgpextensio_3; "LoadGPExtension: Failed to load dll <%s"...
0x18009a735  mov     ecx, 2
0x18009a73a  mov     rax, rsi
0x18009a73d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a742  jmp     short loc_18009A774
0x18009a744  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbp; void * g_lpDebugMsgContextInstance
0x18009a74b  jz      short loc_18009A774
0x18009a74d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbp; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009a754  jz      short loc_18009A774
0x18009a756  call    cs:__imp_GetLastError
0x18009a75c  mov     r9d, eax
0x18009a75f  mov     r8, [rdi+10h]
0x18009a763  lea     rdx, aLoadgpextensio_3; "LoadGPExtension: Failed to load dll <%s"...
0x18009a76a  mov     ecx, 2; unsigned int
0x18009a76f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009a774  mov     edi, ebp
0x18009a776  jmp     short loc_18009A77D
0x18009a778  mov     edi, 1
0x18009a77d  mov     ecx, ebx; dwErrCode
0x18009a77f  call    cs:__imp_SetLastError
0x18009a785  mov     eax, edi
0x18009a787  add     rsp, 38h
0x18009a78b  pop     rdi
0x18009a78c  pop     rsi
0x18009a78d  pop     rbp
0x18009a78e  pop     rbx
0x18009a78f  retn
```
