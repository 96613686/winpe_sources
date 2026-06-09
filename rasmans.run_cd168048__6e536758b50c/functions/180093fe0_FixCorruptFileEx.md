# FixCorruptFileEx

- ea: `0x180093fe0`
- end: `0x1800943a8`
- name: `FixCorruptFileEx`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180094c54`

## callees

- `0x180001fc4`
- `0x180001fdc`
- `0x18000eb54`
- `0x180093fe0`
- `0x18009452c`
- `0x180094650`
- `0x1800e8e7e`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!calloc` at `0x1800942d5`
- `msvcrt!calloc` at `0x1800942d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009403d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009403d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180094057`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180094057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009408a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800940bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800940ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800942b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009435b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009408a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800940bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800940ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800942b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009435b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094329`
- `RPCRT4!RpcImpersonateClient` at `0x18009402d`
- `RPCRT4!RpcImpersonateClient` at `0x1800940dc`
- `RPCRT4!RpcImpersonateClient` at `0x18009402d`
- `RPCRT4!RpcImpersonateClient` at `0x1800940dc`
- `RPCRT4!RpcRevertToSelf` at `0x180094096`
- `RPCRT4!RpcRevertToSelf` at `0x18009437b`
- `RPCRT4!RpcRevertToSelf` at `0x180094096`
- `RPCRT4!RpcRevertToSelf` at `0x18009437b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180094072`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180094072`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800941ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800941ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009436a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009436a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180094222`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009424f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180094222`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009424f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800942a6`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180094319`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800942a6`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180094319`

## pseudocode

```c
void __fastcall FixCorruptFileEx(__int64 a1)
{
  WCHAR *v1; // rbx
  HANDLE CurrentThread; // rax
  void *v3; // rdi
  BOOL v4; // r15d
  WCHAR *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rax
  WCHAR v9; // cx
  unsigned int v10; // r12d
  unsigned int v11; // edi
  unsigned __int16 *v12; // rsi
  HANDLE FileW; // r14
  __int64 v14; // rdi
  char *v15; // rax
  void *v16; // rbx
  void *v17; // r8
  char FileInformation[8]; // [rsp+40h] [rbp-29h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-19h] BYREF
  wchar_t v21; // [rsp+58h] [rbp-11h]
  __int64 v22; // [rsp+60h] [rbp-9h] BYREF
  wchar_t v23; // [rsp+68h] [rbp-1h]

  if ( a1 )
  {
    v1 = (WCHAR *)(a1 + 52);
    if ( a1 != -52 )
    {
      TokenHandle = (void *)-1LL;
      DuplicateTokenHandle = (void *)-1LL;
      if ( !RpcImpersonateClient(0) )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
        {
          if ( !DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
            DuplicateTokenHandle = (void *)-1LL;
          CloseHandle(TokenHandle);
        }
        RpcRevertToSelf();
      }
      v3 = DuplicateTokenHandle;
      if ( DuplicateTokenHandle == (void *)-1LL )
      {
        v4 = 0;
      }
      else
      {
        if ( !(unsigned int)IsPhoneBookPathValidEx(DuplicateTokenHandle, v1) )
        {
          CloseHandle(v3);
          return;
        }
        CloseHandle(v3);
        v4 = RpcImpersonateClient(0) == 0;
      }
      v5 = v1;
      v6 = 260;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v6;
      }
      while ( v6 );
      v7 = (260 - v6) & -(__int64)(v6 != 0);
      if ( !v6 || !v7 )
        goto LABEL_42;
      v23 = aBad[4];
      v22 = *(_QWORD *)L".bad";
      v21 = aPbk_0[4];
      v8 = (260 - v6) & -(__int64)(v6 != 0);
      TokenHandle = *(void **)L".pbk";
      while ( 1 )
      {
        v9 = v1[v8 - 1];
        if ( v9 == 46 )
          break;
        if ( v9 != 92 && v9 != 47 )
        {
          if ( --v8 )
            continue;
        }
        goto LABEL_42;
      }
      if ( !&v1[v8 - 1] )
        goto LABEL_42;
      if ( wcsicmp_0(&v1[v8 - 1], (const wchar_t *)&TokenHandle) )
        goto LABEL_42;
      v11 = v7 + 5;
      v10 = v11;
      DuplicateTokenHandle = (void *)(2LL * v11);
      v12 = (unsigned __int16 *)LocalAlloc(0x40u, (SIZE_T)DuplicateTokenHandle);
      if ( !v12 )
        goto LABEL_42;
      StringCchPrintfW(v12, v11, L"%s%s", v1, &v22);
      FileW = CreateFileW(v1, 0x10000u, 3u, 0, 3u, 0, 0);
      v14 = (__int64)CreateFileW(v12, 0x10000u, 3u, 0, 3u, 0, 0);
      if ( FileW != (HANDLE)-1LL && !(unsigned int)IsFileNotSymlink(FileW, v1) )
      {
        if ( v14 != -1 )
        {
          if ( (unsigned int)IsFileNotSymlink((HANDLE)v14, v12) )
          {
LABEL_38:
            CloseHandle((HANDLE)v14);
LABEL_39:
            if ( FileW == (HANDLE)-1LL )
            {
LABEL_41:
              LocalFree(v12);
LABEL_42:
              if ( v4 )
                RpcRevertToSelf();
              return;
            }
LABEL_40:
            CloseHandle(FileW);
            goto LABEL_41;
          }
          FileInformation[0] = 1;
          SetFileInformationByHandle((HANDLE)v14, FileDispositionInfo, FileInformation, 1u);
          CloseHandle((HANDLE)v14);
          v14 = -1;
        }
        v15 = (char *)calloc(1u, 2 * v10 + 22);
        v16 = v15;
        if ( !v15 )
          goto LABEL_40;
        v17 = DuplicateTokenHandle;
        *((_DWORD *)v15 + 4) = 2 * v10;
        *v15 = 0;
        *((_QWORD *)v15 + 1) = 0;
        memcpy_0(v15 + 20, v12, (size_t)v17);
        if ( !SetFileInformationByHandle(FileW, FileRenameInfo, v16, 2 * v10 + 22) )
          GetLastError();
        free_0(v16);
      }
      if ( v14 == -1 )
        goto LABEL_39;
      goto LABEL_38;
    }
  }
}

```

## disassembly

```asm
0x180093fe0  test    rcx, rcx
0x180093fe3  jz      locret_1800943A6
0x180093fe9  push    rbp
0x180093fea  push    rbx
0x180093feb  push    rsi
0x180093fec  push    rdi
0x180093fed  push    r12
0x180093fef  push    r13
0x180093ff1  push    r14
0x180093ff3  push    r15
0x180093ff5  lea     rbp, [rsp-1Fh]
0x180093ffa  sub     rsp, 88h
0x180094001  mov     rax, cs:__security_cookie
0x180094008  xor     rax, rsp
0x18009400b  mov     [rbp+57h+var_50], rax
0x18009400f  xor     r13d, r13d
0x180094012  lea     rbx, [rcx+34h]
0x180094016  test    rbx, rbx
0x180094019  jz      loc_180094387
0x18009401f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180094023  xor     ecx, ecx; BindingHandle
0x180094025  mov     [rbp+57h+TokenHandle], rsi
0x180094029  mov     [rbp+57h+DuplicateTokenHandle], rsi
0x18009402d  call    cs:__imp_RpcImpersonateClient
0x180094034  nop     dword ptr [rax+rax+00h]
0x180094039  test    eax, eax
0x18009403b  jnz     short loc_1800940A2
0x18009403d  call    cs:__imp_GetCurrentThread
0x180094044  nop     dword ptr [rax+rax+00h]
0x180094049  mov     rcx, rax; ThreadHandle
0x18009404c  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180094050  lea     edx, [rsi+0Fh]; DesiredAccess
0x180094053  lea     r8d, [r13+1]; OpenAsSelf
0x180094057  call    cs:__imp_OpenThreadToken
0x18009405e  nop     dword ptr [rax+rax+00h]
0x180094063  test    eax, eax
0x180094065  jz      short loc_180094096
0x180094067  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18009406b  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18009406f  lea     edx, [rsi+3]; ImpersonationLevel
0x180094072  call    cs:__imp_DuplicateToken
0x180094079  nop     dword ptr [rax+rax+00h]
0x18009407e  test    eax, eax
0x180094080  jnz     short loc_180094086
0x180094082  mov     [rbp+57h+DuplicateTokenHandle], rsi
0x180094086  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18009408a  call    cs:__imp_CloseHandle
0x180094091  nop     dword ptr [rax+rax+00h]
0x180094096  call    cs:__imp_RpcRevertToSelf
0x18009409d  nop     dword ptr [rax+rax+00h]
0x1800940a2  mov     rdi, [rbp+57h+DuplicateTokenHandle]
0x1800940a6  cmp     rdi, rsi
0x1800940a9  jz      short loc_1800940F3
0x1800940ab  mov     rdx, rbx; lpString2
0x1800940ae  mov     rcx, rdi; hToken
0x1800940b1  call    IsPhoneBookPathValidEx
0x1800940b6  mov     rcx, rdi; hObject
0x1800940b9  test    eax, eax
0x1800940bb  jnz     short loc_1800940CE
0x1800940bd  call    cs:__imp_CloseHandle
0x1800940c4  nop     dword ptr [rax+rax+00h]
0x1800940c9  jmp     loc_180094387
0x1800940ce  call    cs:__imp_CloseHandle
0x1800940d5  nop     dword ptr [rax+rax+00h]
0x1800940da  xor     ecx, ecx; BindingHandle
0x1800940dc  call    cs:__imp_RpcImpersonateClient
0x1800940e3  nop     dword ptr [rax+rax+00h]
0x1800940e8  test    eax, eax
0x1800940ea  mov     r15d, r13d
0x1800940ed  setz    r15b
0x1800940f1  jmp     short loc_1800940F6
0x1800940f3  mov     r15d, r13d
0x1800940f6  mov     edx, 104h
0x1800940fb  mov     rax, rbx
0x1800940fe  mov     ecx, edx
0x180094100  cmp     [rax], r13w
0x180094104  jz      short loc_180094110
0x180094106  add     rax, 2
0x18009410a  sub     rcx, 1
0x18009410e  jnz     short loc_180094100
0x180094110  sub     rdx, rcx
0x180094113  mov     rax, rcx
0x180094116  neg     rax
0x180094119  sbb     rdi, rdi
0x18009411c  and     rdi, rdx
0x18009411f  test    rcx, rcx
0x180094122  jz      loc_180094376
0x180094128  test    rdi, rdi
0x18009412b  jz      loc_180094376
0x180094131  movzx   eax, word ptr cs:aBad+8; ""
0x180094138  movsd   xmm0, qword ptr cs:aBad; ".bad"
0x180094140  mov     [rbp+57h+var_58], ax
0x180094144  movzx   eax, word ptr cs:aPbk_0+8; ""
0x18009414b  movsd   [rbp+57h+var_60], xmm0
0x180094150  movsd   xmm0, qword ptr cs:aPbk_0; ".pbk"
0x180094158  mov     [rbp+57h+var_68], ax
0x18009415c  mov     rax, rdi
0x18009415f  movsd   [rbp+57h+TokenHandle], xmm0
0x180094164  movzx   ecx, word ptr [rbx+rax*2-2]
0x180094169  lea     r8, [rbx-2]
0x18009416d  lea     r8, [r8+rax*2]
0x180094171  cmp     cx, 2Eh ; '.'
0x180094175  jz      short loc_180094196
0x180094177  cmp     cx, 5Ch ; '\'
0x18009417b  jz      loc_180094376
0x180094181  cmp     cx, 2Fh ; '/'
0x180094185  jz      loc_180094376
0x18009418b  sub     rax, 1
0x18009418f  jnz     short loc_180094164
0x180094191  jmp     loc_180094376
0x180094196  test    r8, r8
0x180094199  jz      loc_180094376
0x18009419f  lea     rdx, [rbp+57h+TokenHandle]; String2
0x1800941a3  mov     rcx, r8; String1
0x1800941a6  call    _wcsicmp_0
0x1800941ab  test    eax, eax
0x1800941ad  jnz     loc_180094376
0x1800941b3  lea     r12d, [rdi+5]
0x1800941b7  mov     ecx, 40h ; '@'; uFlags
0x1800941bc  lea     rax, [r12+r12]
0x1800941c0  mov     edi, r12d
0x1800941c3  mov     rdx, rax; uBytes
0x1800941c6  mov     [rbp+57h+DuplicateTokenHandle], rax
0x1800941ca  call    cs:__imp_LocalAlloc
0x1800941d1  nop     dword ptr [rax+rax+00h]
0x1800941d6  mov     rsi, rax
0x1800941d9  test    rax, rax
0x1800941dc  jz      loc_180094376
0x1800941e2  lea     rax, [rbp+57h+var_60]
0x1800941e6  mov     r9, rbx
0x1800941e9  lea     r8, aSS_3; "%s%s"
0x1800941f0  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800941f5  mov     edx, edi; unsigned __int64
0x1800941f7  mov     rcx, rsi; unsigned __int16 *
0x1800941fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800941ff  mov     eax, 3
0x180094204  mov     [rsp+0C0h+hTemplateFile], r13; hTemplateFile
0x180094209  mov     edi, 10000h
0x18009420e  mov     [rsp+0C0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180094213  mov     r8d, eax; dwShareMode
0x180094216  mov     [rsp+0C0h+dwCreationDisposition], eax; dwCreationDisposition
0x18009421a  xor     r9d, r9d; lpSecurityAttributes
0x18009421d  mov     edx, edi; dwDesiredAccess
0x18009421f  mov     rcx, rbx; lpFileName
0x180094222  call    cs:__imp_CreateFileW
0x180094229  nop     dword ptr [rax+rax+00h]
0x18009422e  mov     [rsp+0C0h+hTemplateFile], r13; hTemplateFile
0x180094233  xor     r9d, r9d; lpSecurityAttributes
0x180094236  mov     r14, rax
0x180094239  mov     [rsp+0C0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18009423e  mov     eax, 3
0x180094243  mov     edx, edi; dwDesiredAccess
0x180094245  mov     r8d, eax; dwShareMode
0x180094248  mov     [rsp+0C0h+dwCreationDisposition], eax; dwCreationDisposition
0x18009424c  mov     rcx, rsi; lpFileName
0x18009424f  call    cs:__imp_CreateFileW
0x180094256  nop     dword ptr [rax+rax+00h]
0x18009425b  mov     rdi, rax
0x18009425e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180094262  jz      loc_18009433D
0x180094268  mov     rdx, rbx; String1
0x18009426b  mov     rcx, r14; hFile
0x18009426e  call    IsFileNotSymlink
0x180094273  test    eax, eax
0x180094275  jnz     loc_18009433D
0x18009427b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18009427f  jz      short loc_1800942C5
0x180094281  mov     rdx, rsi; String1
0x180094284  mov     rcx, rdi; hFile
0x180094287  call    IsFileNotSymlink
0x18009428c  test    eax, eax
0x18009428e  jnz     loc_180094343
0x180094294  lea     r9d, [rax+1]; dwBufferSize
0x180094298  mov     [rbp+57h+FileInformation], 1
0x18009429c  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800942a0  mov     rcx, rdi; hFile
0x1800942a3  lea     edx, [rax+4]; FileInformationClass
0x1800942a6  call    cs:__imp_SetFileInformationByHandle
0x1800942ad  nop     dword ptr [rax+rax+00h]
0x1800942b2  mov     rcx, rdi; hObject
0x1800942b5  call    cs:__imp_CloseHandle
0x1800942bc  nop     dword ptr [rax+rax+00h]
0x1800942c1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800942c5  lea     r13d, ds:16h[r12*2]
0x1800942cd  mov     ecx, 1; Count
0x1800942d2  mov     edx, r13d; Size
0x1800942d5  call    cs:__imp_calloc
0x1800942dc  nop     dword ptr [rax+rax+00h]
0x1800942e1  mov     rbx, rax
0x1800942e4  test    rax, rax
0x1800942e7  jz      short loc_180094358
0x1800942e9  mov     r8, [rbp+57h+DuplicateTokenHandle]; Size
0x1800942ed  lea     ecx, [r12+r12]
0x1800942f1  mov     [rax+10h], ecx
0x1800942f4  mov     rdx, rsi; Src
0x1800942f7  lea     rcx, [rax+14h]; void *
0x1800942fb  mov     byte ptr [rax], 0
0x1800942fe  mov     qword ptr [rax+8], 0
0x180094306  call    memcpy_0
0x18009430b  mov     r9d, r13d; dwBufferSize
0x18009430e  mov     r8, rbx; lpFileInformation
0x180094311  mov     edx, 3; FileInformationClass
0x180094316  mov     rcx, r14; hFile
0x180094319  call    cs:__imp_SetFileInformationByHandle
0x180094320  nop     dword ptr [rax+rax+00h]
0x180094325  test    eax, eax
0x180094327  jnz     short loc_180094335
0x180094329  call    cs:__imp_GetLastError
0x180094330  nop     dword ptr [rax+rax+00h]
0x180094335  mov     rcx, rbx; Block
0x180094338  call    free_0
0x18009433d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180094341  jz      short loc_180094352
0x180094343  mov     rcx, rdi; hObject
0x180094346  call    cs:__imp_CloseHandle
0x18009434d  nop     dword ptr [rax+rax+00h]
0x180094352  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180094356  jz      short loc_180094367
0x180094358  mov     rcx, r14; hObject
0x18009435b  call    cs:__imp_CloseHandle
0x180094362  nop     dword ptr [rax+rax+00h]
0x180094367  mov     rcx, rsi; hMem
0x18009436a  call    cs:__imp_LocalFree
0x180094371  nop     dword ptr [rax+rax+00h]
0x180094376  test    r15d, r15d
0x180094379  jz      short loc_180094387
0x18009437b  call    cs:__imp_RpcRevertToSelf
0x180094382  nop     dword ptr [rax+rax+00h]
0x180094387  mov     rcx, [rbp+57h+var_50]
0x18009438b  xor     rcx, rsp; StackCookie
0x18009438e  call    __security_check_cookie
0x180094393  add     rsp, 88h
0x18009439a  pop     r15
0x18009439c  pop     r14
0x18009439e  pop     r13
0x1800943a0  pop     r12
0x1800943a2  pop     rdi
0x1800943a3  pop     rsi
0x1800943a4  pop     rbx
0x1800943a5  pop     rbp
0x1800943a6  retn
```
