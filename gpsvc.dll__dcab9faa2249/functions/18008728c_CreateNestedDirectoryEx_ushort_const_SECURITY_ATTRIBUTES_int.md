# CreateNestedDirectoryEx(ushort const *,_SECURITY_ATTRIBUTES *,int)

- ea: `0x18008728c`
- end: `0x18008767b`
- name: `?CreateNestedDirectoryEx@@YAIPEBGPEAU_SECURITY_ATTRIBUTES@@H@Z`
- size: `1007`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037470`

## callees

- `0x18002c690`
- `0x180075ec0`
- `0x18007d320`
- `0x18008728c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008730a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008730a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800874e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008751b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800874e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008751b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800875e0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008731a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800874b2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008757d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008731a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800874b2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008757d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800872f1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800874a1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800872f1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800874a1`

## string_xrefs

- `0x180087618`: `CreateNestedDirectory:  Received a NULL pointer.`
- `0x18008763d`: `CreateNestedDirectory:  Received a NULL pointer.`
- `0x18008735a`: `CreateNestedDirectoryEx:  Failed to copy Directory Name. StringCchCopy failed with 0x%x.`
- `0x18008738d`: `CreateNestedDirectoryEx:  Failed to copy Directory Name. StringCchCopy failed with 0x%x.`
- `0x1800874ea`: `CreateNestedDirectory:  CreateDirectory failed with %d.`
- `0x180087521`: `CreateNestedDirectory:  CreateDirectory failed with %d.`
- `0x1800875bd`: `CreateNestedDirectory:  Failed to create the directory with error %d.`
- `0x1800875e6`: `CreateNestedDirectory:  Failed to create the directory with error %d.`
- `0x180087546`: `CreateNestedDirectory:  Parsing problem`
- `0x18008756c`: `CreateNestedDirectory:  Parsing problem`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateNestedDirectoryEx(const unsigned __int16 *a1, struct _SECURITY_ATTRIBUTES *a2)
{
  DWORD v3; // eax
  const unsigned __int16 *v4; // rdx
  unsigned int v5; // ecx
  __int64 v6; // rax
  int v7; // edi
  WCHAR *p_FileName; // rbx
  int v9; // edi
  __int16 v10; // ax
  __int16 *v11; // rbx
  WCHAR v12; // ax
  WCHAR v13; // ax
  void (*v14)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  const wchar_t *v16; // rdx
  __int64 v17; // rcx
  void (*v18)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v19; // rdx
  _OWORD FileInformation[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+40h] [rbp-C0h]
  WCHAR FileName; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v24; // [rsp+52h] [rbp-AEh] BYREF
  __int16 v25; // [rsp+54h] [rbp-ACh] BYREF
  char v26; // [rsp+56h] [rbp-AAh] BYREF

  v22 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !a1 || !*a1 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      return 0;
    v18 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"CreateNestedDirectory:  Received a NULL pointer.");
      return 0;
    }
    v19 = L"CreateNestedDirectory:  Received a NULL pointer.";
    goto LABEL_75;
  }
  if ( !GetFileAttributesExW(a1, GetFileExInfoStandard, FileInformation) )
  {
    if ( CreateDirectoryW(a1, 0) )
      return 1;
    v3 = StringCchCopyW(&FileName, 0x208u, a1);
    if ( (v3 & 0x80000000) != 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"CreateNestedDirectoryEx:  Failed to copy Directory Name. StringCchCopy failed with 0x%x.",
            v3);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v4 = L"CreateNestedDirectoryEx:  Failed to copy Directory Name. StringCchCopy failed with 0x%x.";
LABEL_15:
          v5 = 2;
LABEL_70:
          RedirectDebugMsg(v5, v4, v3);
        }
      }
      return 0;
    }
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    v7 = v6 + 1;
    if ( v24 == 58 )
    {
      v7 = v6 - 2;
      if ( (_DWORD)v6 != 2 )
      {
        p_FileName = (WCHAR *)&v26;
        goto LABEL_38;
      }
    }
    else if ( v24 == 92 )
    {
      v9 = v6 - 1;
      if ( (_DWORD)v6 != 1 )
      {
        v10 = v25;
        v11 = &v25;
        while ( v10 && v10 != 92 )
        {
          ++v11;
          --v9;
          v10 = *v11;
        }
        if ( *v11 )
        {
          p_FileName = (WCHAR *)(v11 + 1);
          v12 = *p_FileName;
          if ( *p_FileName )
          {
            v7 = v9 - 1;
            do
            {
              if ( v12 == 92 )
                break;
              ++p_FileName;
              --v7;
              v12 = *p_FileName;
            }
            while ( *p_FileName );
            if ( *p_FileName )
              goto LABEL_46;
          }
        }
        return 0;
      }
    }
    else
    {
      if ( FileName != 92 )
      {
        p_FileName = &FileName;
LABEL_38:
        while ( 1 )
        {
          v13 = *p_FileName;
          if ( !*p_FileName )
            break;
          do
          {
            if ( v13 == 92 )
              break;
            ++p_FileName;
            --v7;
            v13 = *p_FileName;
          }
          while ( *p_FileName );
          if ( !v7 )
            goto LABEL_55;
          if ( *p_FileName == 92 )
          {
            *p_FileName = 0;
            if ( !GetFileAttributesExW(&FileName, GetFileExInfoStandard, FileInformation)
              && !CreateDirectoryW(&FileName, 0) )
            {
              if ( !*(_DWORD *)&g_dwDebugLevel )
                return 0;
              v14 = g_lpDebugMsg;
              if ( g_lpDebugMsg )
              {
                LastError = GetLastError();
                v16 = L"CreateNestedDirectory:  CreateDirectory failed with %d.";
                v17 = 2;
LABEL_51:
                v14(v17, v16, LastError);
                return 0;
              }
              if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                v3 = GetLastError();
                v4 = L"CreateNestedDirectory:  CreateDirectory failed with %d.";
                goto LABEL_15;
              }
              return 0;
            }
            *p_FileName = 92;
LABEL_46:
            if ( !--v7 )
              goto LABEL_55;
            ++p_FileName;
          }
        }
        if ( CreateDirectoryW(a1, 0) )
          return 1;
        if ( GetLastError() != 183 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v14 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              LastError = GetLastError();
              v16 = L"CreateNestedDirectory:  Failed to create the directory with error %d.";
              v17 = 4;
              goto LABEL_51;
            }
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v3 = GetLastError();
              v4 = L"CreateNestedDirectory:  Failed to create the directory with error %d.";
              v5 = 4;
              goto LABEL_70;
            }
          }
          return 0;
        }
        return 183;
      }
      if ( (_DWORD)v6 )
      {
        v7 = v6;
        p_FileName = (WCHAR *)&v24;
        goto LABEL_38;
      }
    }
LABEL_55:
    if ( !*(_DWORD *)&g_dwDebugLevel )
      return 0;
    v18 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"CreateNestedDirectory:  Parsing problem");
      return 0;
    }
    v19 = L"CreateNestedDirectory:  Parsing problem";
LABEL_75:
    v18(2u, v19);
    return 0;
  }
  if ( (FileInformation[0] & 0x10) != 0 )
    return 183;
  SetLastError(5u);
  return 0;
}

```

## disassembly

```asm
0x18008728c  mov     [rsp-8+arg_8], rbx
0x180087291  mov     [rsp-8+arg_10], rsi
0x180087296  push    rbp
0x180087297  push    rdi
0x180087298  push    r12
0x18008729a  push    r14
0x18008729c  push    r15
0x18008729e  lea     rbp, [rsp-370h]
0x1800872a6  sub     rsp, 470h
0x1800872ad  mov     rax, cs:__security_cookie
0x1800872b4  xor     rax, rsp
0x1800872b7  mov     [rbp+390h+var_30], rax
0x1800872be  xor     eax, eax
0x1800872c0  xorps   xmm0, xmm0
0x1800872c3  xor     r14d, r14d
0x1800872c6  mov     [rsp+490h+var_450], eax
0x1800872ca  mov     rsi, rcx
0x1800872cd  movups  [rsp+490h+FileInformation], xmm0
0x1800872d2  movups  [rsp+490h+var_460], xmm0
0x1800872d7  test    rcx, rcx
0x1800872da  jz      loc_180087603
0x1800872e0  cmp     [rcx], r14w
0x1800872e4  jz      loc_180087603
0x1800872ea  lea     r8, [rsp+490h+FileInformation]; lpFileInformation
0x1800872ef  xor     edx, edx; fInfoLevelId
0x1800872f1  call    cs:__imp_GetFileAttributesExW
0x1800872f7  test    eax, eax
0x1800872f9  jz      short loc_180087315
0x1800872fb  test    byte ptr [rsp+490h+FileInformation], 10h
0x180087300  jnz     loc_180087594
0x180087306  lea     ecx, [r14+5]; dwErrCode
0x18008730a  call    cs:__imp_SetLastError
0x180087310  jmp     loc_18008764E
0x180087315  xor     edx, edx; lpSecurityAttributes
0x180087317  mov     rcx, rsi; lpPathName
0x18008731a  call    cs:__imp_CreateDirectoryW
0x180087320  test    eax, eax
0x180087322  jnz     loc_1800875FC
0x180087328  mov     r8, rsi; unsigned __int16 *
0x18008732b  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x180087330  mov     edx, 208h; unsigned __int64
0x180087335  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008733a  test    eax, eax
0x18008733c  jns     short loc_18008739E
0x18008733e  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180087345  jz      loc_18008764E
0x18008734b  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087352  test    r9, r9
0x180087355  jz      short loc_180087373
0x180087357  mov     r8d, eax
0x18008735a  lea     rdx, aCreatenesteddi_1; "CreateNestedDirectoryEx:  Failed to cop"...
0x180087361  mov     rax, r9
0x180087364  mov     ecx, 2
0x180087369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008736e  jmp     loc_18008764E
0x180087373  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18008737a  jz      loc_18008764E
0x180087380  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087387  jz      loc_18008764E
0x18008738d  lea     rdx, aCreatenesteddi_1; "CreateNestedDirectoryEx:  Failed to cop"...
0x180087394  mov     ecx, 2
0x180087399  jmp     loc_1800875F2
0x18008739e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800873a2  inc     rax
0x1800873a5  cmp     [rsi+rax*2], r14w
0x1800873aa  jnz     short loc_1800873A2
0x1800873ac  or      r12d, 0FFFFFFFFh
0x1800873b0  lea     edi, [rax+1]
0x1800873b3  cmp     [rsp+490h+var_43E], 3Ah ; ':'
0x1800873b9  mov     r15d, 5Ch ; '\'
0x1800873bf  jnz     short loc_1800873D4
0x1800873c1  add     edi, 0FFFFFFFDh
0x1800873c4  jz      loc_18008752D
0x1800873ca  lea     rbx, [rsp+490h+var_43A]
0x1800873cf  jmp     loc_180087462
0x1800873d4  cmp     [rsp+490h+var_43E], r15w
0x1800873da  jnz     short loc_180087444
0x1800873dc  add     edi, 0FFFFFFFEh
0x1800873df  jz      loc_18008752D
0x1800873e5  movzx   eax, [rsp+490h+var_43C]
0x1800873ea  lea     rbx, [rsp+490h+var_43C]
0x1800873ef  jmp     short loc_180087401
0x1800873f1  cmp     ax, r15w
0x1800873f5  jz      short loc_180087406
0x1800873f7  add     rbx, 2
0x1800873fb  add     edi, r12d
0x1800873fe  movzx   eax, word ptr [rbx]
0x180087401  test    ax, ax
0x180087404  jnz     short loc_1800873F1
0x180087406  cmp     [rbx], r14w
0x18008740a  jz      loc_18008764E
0x180087410  add     rbx, 2
0x180087414  movzx   eax, word ptr [rbx]
0x180087417  test    ax, ax
0x18008741a  jz      loc_18008764E
0x180087420  add     edi, r12d
0x180087423  cmp     ax, r15w
0x180087427  jz      short loc_180087438
0x180087429  add     rbx, 2
0x18008742d  add     edi, r12d
0x180087430  movzx   eax, word ptr [rbx]
0x180087433  test    ax, ax
0x180087436  jnz     short loc_180087423
0x180087438  cmp     [rbx], r14w
0x18008743c  jz      loc_18008764E
0x180087442  jmp     short loc_1800874C0
0x180087444  cmp     [rsp+490h+FileName], r15w
0x18008744a  jnz     short loc_18008745D
0x18008744c  test    eax, eax
0x18008744e  jz      loc_18008752D
0x180087454  mov     edi, eax
0x180087456  lea     rbx, [rsp+490h+var_43E]
0x18008745b  jmp     short loc_180087462
0x18008745d  lea     rbx, [rsp+490h+FileName]
0x180087462  movzx   eax, word ptr [rbx]
0x180087465  test    ax, ax
0x180087468  jz      loc_180087578
0x18008746e  cmp     ax, r15w
0x180087472  jz      short loc_180087483
0x180087474  add     rbx, 2
0x180087478  add     edi, r12d
0x18008747b  movzx   eax, word ptr [rbx]
0x18008747e  test    ax, ax
0x180087481  jnz     short loc_18008746E
0x180087483  test    edi, edi
0x180087485  jz      loc_18008752D
0x18008748b  cmp     [rbx], r15w
0x18008748f  jnz     short loc_180087462
0x180087491  lea     r8, [rsp+490h+FileInformation]; lpFileInformation
0x180087496  mov     [rbx], r14w
0x18008749a  xor     edx, edx; fInfoLevelId
0x18008749c  lea     rcx, [rsp+490h+FileName]; lpFileName
0x1800874a1  call    cs:__imp_GetFileAttributesExW
0x1800874a7  test    eax, eax
0x1800874a9  jnz     short loc_1800874BC
0x1800874ab  xor     edx, edx; lpSecurityAttributes
0x1800874ad  lea     rcx, [rsp+490h+FileName]; lpPathName
0x1800874b2  call    cs:__imp_CreateDirectoryW
0x1800874b8  test    eax, eax
0x1800874ba  jz      short loc_1800874CB
0x1800874bc  mov     [rbx], r15w
0x1800874c0  sub     edi, 1
0x1800874c3  jz      short loc_18008752D
0x1800874c5  add     rbx, 2
0x1800874c9  jmp     short loc_180087462
0x1800874cb  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800874d2  jz      loc_18008764E
0x1800874d8  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800874df  test    rbx, rbx
0x1800874e2  jz      short loc_180087501
0x1800874e4  call    cs:__imp_GetLastError
0x1800874ea  lea     rdx, aCreatenesteddi_0; "CreateNestedDirectory:  CreateDirectory"...
0x1800874f1  mov     ecx, 2
0x1800874f6  mov     r8d, eax
0x1800874f9  mov     rax, rbx
0x1800874fc  jmp     loc_180087369
0x180087501  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180087508  jz      loc_18008764E
0x18008750e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087515  jz      loc_18008764E
0x18008751b  call    cs:__imp_GetLastError
0x180087521  lea     rdx, aCreatenesteddi_0; "CreateNestedDirectory:  CreateDirectory"...
0x180087528  jmp     loc_180087394
0x18008752d  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180087534  jz      loc_18008764E
0x18008753a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087541  test    rax, rax
0x180087544  jz      short loc_180087552
0x180087546  lea     rdx, aCreatenesteddi_2; "CreateNestedDirectory:  Parsing problem"
0x18008754d  jmp     loc_18008761F
0x180087552  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180087559  jz      loc_18008764E
0x18008755f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180087566  jz      loc_18008764E
0x18008756c  lea     rdx, aCreatenesteddi_2; "CreateNestedDirectory:  Parsing problem"
0x180087573  jmp     loc_180087644
0x180087578  xor     edx, edx; lpSecurityAttributes
0x18008757a  mov     rcx, rsi; lpPathName
0x18008757d  call    cs:__imp_CreateDirectoryW
0x180087583  test    eax, eax
0x180087585  jnz     short loc_1800875FC
0x180087587  call    cs:__imp_GetLastError
0x18008758d  cmp     eax, 0B7h
0x180087592  jnz     short loc_18008759E
0x180087594  mov     eax, 0B7h
0x180087599  jmp     loc_180087650
0x18008759e  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800875a5  jz      loc_18008764E
0x1800875ab  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800875b2  test    rbx, rbx
0x1800875b5  jz      short loc_1800875CE
0x1800875b7  call    cs:__imp_GetLastError
0x1800875bd  lea     rdx, aCreatenesteddi_3; "CreateNestedDirectory:  Failed to creat"...
0x1800875c4  mov     ecx, 4
0x1800875c9  jmp     loc_1800874F6
0x1800875ce  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800875d5  jz      short loc_18008764E
0x1800875d7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800875de  jz      short loc_18008764E
0x1800875e0  call    cs:__imp_GetLastError
0x1800875e6  lea     rdx, aCreatenesteddi_3; "CreateNestedDirectory:  Failed to creat"...
0x1800875ed  mov     ecx, 4; unsigned int
0x1800875f2  mov     r8d, eax
0x1800875f5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800875fa  jmp     short loc_18008764E
0x1800875fc  mov     eax, 1
0x180087601  jmp     short loc_180087650
0x180087603  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18008760a  jz      short loc_18008764E
0x18008760c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180087613  test    rax, rax
0x180087616  jz      short loc_18008762B
0x180087618  lea     rdx, aCreatenesteddi; "CreateNestedDirectory:  Received a NULL"...
0x18008761f  mov     ecx, 2
0x180087624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087629  jmp     short loc_18008764E
0x18008762b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180087632  jz      short loc_18008764E
0x180087634  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008763b  jz      short loc_18008764E
0x18008763d  lea     rdx, aCreatenesteddi; "CreateNestedDirectory:  Received a NULL"...
0x180087644  mov     ecx, 2; unsigned int
0x180087649  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008764e  xor     eax, eax
0x180087650  mov     rcx, [rbp+390h+var_30]
0x180087657  xor     rcx, rsp; StackCookie
0x18008765a  call    __security_check_cookie
0x18008765f  lea     r11, [rsp+490h+var_20]
0x180087667  mov     rbx, [r11+38h]
0x18008766b  mov     rsi, [r11+40h]
0x18008766f  mov     rsp, r11
0x180087672  pop     r15
0x180087674  pop     r14
0x180087676  pop     r12
0x180087678  pop     rdi
0x180087679  pop     rbp
0x18008767a  retn
```
