# SetRsopTargetName(_GPOINFO *)

- ea: `0x180019fb4`
- end: `0x18001a5d7`
- name: `?SetRsopTargetName@@YAHPEAU_GPOINFO@@@Z`
- size: `1571`
- prototype: `__int64 __fastcall(struct _GPOINFO *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005ce5c`
- `0x18009b60c`

## callees

- `0x18000a504`
- `0x180019fb4`
- `0x18001ae40`
- `0x18001ae60`
- `0x18001ee6c`
- `0x180075ec0`
- `0x18007d320`
- `0x1800b30a0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a38a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a22c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a22c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a3c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a406`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a0c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a0c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a0ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a0ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a142`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a05c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a21e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a46e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a05c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a21e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a46e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001a31d`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001a31d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a00d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a022`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a371`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a47f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a55a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a00d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a022`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a371`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a47f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a55a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a12a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001a12a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a351`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a351`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001a085`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001a085`
- `SspiCli!GetUserNameExW` at `0x18001a2e6`
- `SspiCli!GetUserNameExW` at `0x18001a2e6`

## string_xrefs

- `0x18001a0fb`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x18001a11e`: `ImpersonateUser: Failed to open thread token with %d.`
- `0x18001a16c`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x18001a19d`: `ImpersonateUser: Failed to impersonate user with %d.`
- `0x18001a1ca`: `SetRsopTargetName: Failed to impersonate user`
- `0x18001a1fb`: `SetRsopTargetName: Failed to impersonate user`
- `0x18001a3d2`: `Computer`
- `0x18001a417`: `Computer`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetRsopTargetName(struct _GPOINFO *a1)
{
  void *v2; // rcx
  HLOCAL *v3; // r15
  unsigned __int16 *ComputerName; // rdx
  HLOCAL v5; // rax
  WCHAR *v6; // rbx
  void *v7; // rbx
  HANDLE CurrentThread; // rax
  DWORD v9; // eax
  void (*v10)(unsigned int, const unsigned __int16 *, ...); // rbx
  const wchar_t *v11; // rdx
  DWORD v12; // eax
  DWORD LastError; // edi
  int v14; // esi
  WCHAR *v15; // rax
  void (*v16)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v17; // eax
  const unsigned __int16 *v18; // r8
  DWORD v19; // eax
  const unsigned __int16 *v20; // r8
  __int64 v22; // rsi
  __int64 v23; // rdi
  unsigned __int64 v24; // rdi
  WCHAR *v25; // rdx
  WCHAR *v26; // rcx
  WCHAR i; // ax
  bool v28; // zf
  __int64 v29; // rax
  __int16 *v30; // rcx
  WCHAR *v31; // r8
  WCHAR v32; // r9
  signed int v33; // ecx
  __int64 v34; // rax
  WCHAR *v35; // rcx
  WCHAR v36; // r9
  WCHAR *v37; // rcx
  LPWSTR lpBuffer; // [rsp+30h] [rbp-99h] BYREF
  DWORD nSize; // [rsp+38h] [rbp-91h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-89h] BYREF
  void *v41[2]; // [rsp+48h] [rbp-81h] BYREF
  void *v42[5]; // [rsp+58h] [rbp-71h] BYREF
  int v43; // [rsp+84h] [rbp-45h]
  int v44; // [rsp+88h] [rbp-41h]
  int v45; // [rsp+A8h] [rbp-21h]
  __int64 v46; // [rsp+C8h] [rbp-1h]

  lpBuffer = 0;
  v41[0] = 0;
  TokenHandle = 0;
  v2 = (void *)*((_QWORD *)a1 + 25);
  v3 = (HLOCAL *)((char *)a1 + 208);
  if ( v2 )
  {
    if ( *v3 )
      return 1;
    LocalFree(v2);
    *((_QWORD *)a1 + 25) = 0;
  }
  if ( *v3 )
  {
    LocalFree(*v3);
    *v3 = 0;
  }
  if ( (*(_BYTE *)a1 & 1) == 0 )
  {
    v7 = (void *)*((_QWORD *)a1 + 1);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) || (TokenHandle = 0, v9 = GetLastError(), v9 == 1008) )
    {
      if ( ImpersonateLoggedOnUser(v7) )
      {
        nSize = 75;
        v6 = (WCHAR *)LocalAlloc(0x40u, 0x96u);
        if ( v6 )
        {
          v14 = 0;
          while ( 1 )
          {
            v42[0] = 0;
            v42[1] = 0;
            v42[2] = API_CALL_TRACING_END_SUCCESS;
            v42[3] = 0;
            v42[4] = "i\x1B";
            v41[1] = &CAPICallScenarioEvent::`vftable';
            v43 = 0;
            v44 = 4117;
            v45 = 4118;
            v46 = 0;
            if ( GetUserNameExW(NameSamCompatible, v6, &nSize) )
              break;
            LastError = GetLastError();
            if ( nSize && (LastError == 122 || LastError == 234) )
            {
              v15 = (WCHAR *)LocalReAlloc(v6, 2LL * nSize, 2u);
              if ( !v15 )
              {
                LastError = GetLastError();
LABEL_58:
                LocalFree(v6);
                v6 = 0;
                goto LABEL_60;
              }
              v6 = v15;
            }
            else
            {
              switch ( LastError )
              {
                case 0x534u:
                  goto LABEL_58;
                case 0x4CFu:
                  goto LABEL_58;
                case 0x54Bu:
                  goto LABEL_58;
              }
              if ( (unsigned int)++v14 > 3 )
                goto LABEL_58;
              Sleep(0x1F4u);
            }
            CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(v42);
          }
          LastError = 0;
LABEL_60:
          CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(v42);
        }
        else
        {
          LastError = GetLastError();
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"MyGetUserName:  Failed to allocate memory with %d", LastError);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"MyGetUserName:  Failed to allocate memory with %d", LastError);
            }
          }
        }
        SetLastError(LastError);
        lpBuffer = v6;
        RevertToUser(&TokenHandle);
        goto LABEL_62;
      }
      if ( TokenHandle )
      {
        CloseHandle(TokenHandle);
        TokenHandle = 0;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_73;
      v10 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v12 = GetLastError();
          RedirectDebugMsg(4u, L"ImpersonateUser: Failed to impersonate user with %d.", v12);
        }
        goto LABEL_31;
      }
      v9 = GetLastError();
      v11 = L"ImpersonateUser: Failed to impersonate user with %d.";
    }
    else
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
      {
LABEL_73:
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(v41);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpBuffer);
        return 0;
      }
      v10 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContext && g_lpDebugMsgContextInstance )
          RedirectDebugMsg(4u, L"ImpersonateUser: Failed to open thread token with %d.", v9);
        goto LABEL_31;
      }
      v11 = L"ImpersonateUser: Failed to open thread token with %d.";
    }
    v10(4u, v11, v9);
LABEL_31:
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"SetRsopTargetName: Failed to impersonate user");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"SetRsopTargetName: Failed to impersonate user");
      }
    }
    goto LABEL_73;
  }
  if ( (*(_BYTE *)a1 & 4) != 0 )
  {
    ComputerName = MyGetComputerName(NameSamCompatible);
  }
  else
  {
    nSize = 16;
    v5 = LocalAlloc(0x40u, 0x20u);
    XPtrLF<unsigned short>::operator=((void **)&lpBuffer, v5);
    v6 = lpBuffer;
    if ( !lpBuffer )
      goto LABEL_63;
    if ( GetComputerNameW(lpBuffer, &nSize) )
      goto LABEL_62;
    ComputerName = 0;
  }
  XPtrLF<unsigned short>::operator=((void **)&lpBuffer, ComputerName);
  v6 = lpBuffer;
LABEL_62:
  if ( !v6 )
  {
LABEL_63:
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v16 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v17 = GetLastError();
        v18 = L"Computer";
        if ( (*(_BYTE *)a1 & 1) == 0 )
          v18 = L"User";
        v16(2u, L"SetRsopTargetName: Failed to get the %s name, error = %d", v18, v17);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v19 = GetLastError();
        v20 = L"Computer";
        if ( (*(_BYTE *)a1 & 1) == 0 )
          v20 = L"User";
        RedirectDebugMsg(2u, L"SetRsopTargetName: Failed to get the %s name, error = %d", v20, v19);
      }
    }
    goto LABEL_73;
  }
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( v6[v23] );
  v24 = v23 + 1;
  v25 = (WCHAR *)LocalAlloc(0x40u, 2 * v24);
  if ( !v25 )
  {
LABEL_78:
    LocalFree(v6);
    return 0;
  }
  v26 = v6;
  for ( i = *v6; i && i != 92; i = *v26 )
    ++v26;
  if ( *v26 == 92 )
  {
    v28 = v24 == 0;
    if ( v24 )
    {
      if ( v24 <= 0x7FFFFFFF )
      {
        v29 = 2147483646;
        v30 = (__int16 *)(v26 + 1);
        v31 = v25;
        do
        {
          if ( !v29 )
            break;
          v32 = *v30;
          if ( !*v30 )
            break;
          ++v30;
          *v31++ = v32;
          --v29;
          --v24;
        }
        while ( v24 );
LABEL_98:
        v37 = v31 - 1;
        if ( v24 )
          v37 = v31;
        *v37 = 0;
        v33 = v24 == 0 ? 0x8007007A : 0;
        goto LABEL_103;
      }
LABEL_93:
      v33 = -2147024809;
LABEL_102:
      *v25 = 0;
      goto LABEL_103;
    }
  }
  else
  {
    v28 = v24 == 0;
    if ( v24 )
    {
      if ( v24 <= 0x7FFFFFFF )
      {
        v34 = 2147483646;
        v35 = v6;
        v31 = v25;
        do
        {
          if ( !v34 )
            break;
          v36 = *v35;
          if ( !*v35 )
            break;
          ++v35;
          *v31++ = v36;
          --v34;
          --v24;
        }
        while ( v24 );
        goto LABEL_98;
      }
      goto LABEL_93;
    }
  }
  v33 = -2147024809;
  if ( !v28 )
    goto LABEL_102;
LABEL_103:
  if ( v33 < 0 )
  {
    LocalFree(v25);
    goto LABEL_78;
  }
  if ( (*(_BYTE *)a1 & 1) != 0 && *v25 )
  {
    do
      ++v22;
    while ( v25[v22] );
    if ( v25[v22 - 1] == 36 )
      v25[v22 - 1] = 0;
  }
  v41[0] = 0;
  *v3 = v25;
  lpBuffer = 0;
  *((_QWORD *)a1 + 25) = v6;
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(v41);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpBuffer);
  return 1;
}

```

## disassembly

```asm
0x180019fb4  push    rbp
0x180019fb6  push    rbx
0x180019fb7  push    rsi
0x180019fb8  push    rdi
0x180019fb9  push    r12
0x180019fbb  push    r13
0x180019fbd  push    r14
0x180019fbf  push    r15
0x180019fc1  lea     rbp, [rsp-1Fh]
0x180019fc6  sub     rsp, 0E8h
0x180019fcd  mov     rax, cs:__security_cookie
0x180019fd4  xor     rax, rsp
0x180019fd7  mov     [rbp+57h+var_50], rax
0x180019fdb  mov     r14, rcx
0x180019fde  xor     r12d, r12d
0x180019fe1  mov     [rsp+120h+lpBuffer], r12
0x180019fe6  mov     [rsp+120h+var_D8], r12
0x180019feb  mov     [rsp+120h+TokenHandle], r12
0x180019ff0  mov     rcx, [rcx+0C8h]; hMem
0x180019ff7  lea     r15, [r14+0D0h]
0x180019ffe  test    rcx, rcx
0x18001a001  jz      short loc_18001A01A
0x18001a003  cmp     [r15], r12
0x18001a006  jz      short loc_18001A00D
0x18001a008  jmp     loc_18001A5B2
0x18001a00d  call    cs:__imp_LocalFree
0x18001a013  mov     [r14+0C8h], r12
0x18001a01a  mov     rcx, [r15]; hMem
0x18001a01d  test    rcx, rcx
0x18001a020  jz      short loc_18001A02B
0x18001a022  call    cs:__imp_LocalFree
0x18001a028  mov     [r15], r12
0x18001a02b  mov     edi, 40h ; '@'
0x18001a030  lea     r13d, [rdi-3Eh]
0x18001a034  test    byte ptr [r14], 1
0x18001a038  jz      short loc_18001A0A9
0x18001a03a  test    byte ptr [r14], 4
0x18001a03e  jz      short loc_18001A04D
0x18001a040  mov     ecx, r13d; NameFormat
0x18001a043  call    ?MyGetComputerName@@YAPEAGW4EXTENDED_NAME_FORMAT@@@Z; MyGetComputerName(EXTENDED_NAME_FORMAT)
0x18001a048  mov     rdx, rax
0x18001a04b  jmp     short loc_18001A095
0x18001a04d  mov     [rsp+120h+nSize], 10h
0x18001a055  mov     edx, 20h ; ' '; uBytes
0x18001a05a  mov     ecx, edi; uFlags
0x18001a05c  call    cs:__imp_LocalAlloc
0x18001a062  mov     rdx, rax
0x18001a065  lea     rcx, [rsp+120h+lpBuffer]
0x18001a06a  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18001a06f  mov     rbx, [rsp+120h+lpBuffer]
0x18001a074  test    rbx, rbx
0x18001a077  jz      loc_18001A3A8
0x18001a07d  lea     rdx, [rsp+120h+nSize]; nSize
0x18001a082  mov     rcx, rbx; lpBuffer
0x18001a085  call    cs:__imp_GetComputerNameW
0x18001a08b  test    eax, eax
0x18001a08d  jnz     loc_18001A39F
0x18001a093  xor     edx, edx
0x18001a095  lea     rcx, [rsp+120h+lpBuffer]
0x18001a09a  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18001a09f  mov     rbx, [rsp+120h+lpBuffer]
0x18001a0a4  jmp     loc_18001A39F
0x18001a0a9  mov     rbx, [r14+8]
0x18001a0ad  call    cs:__imp_GetCurrentThread
0x18001a0b3  mov     rcx, rax; ThreadHandle
0x18001a0b6  lea     r9, [rsp+120h+TokenHandle]; TokenHandle
0x18001a0bb  mov     edx, 2000Ch; DesiredAccess
0x18001a0c0  mov     r8d, 1; OpenAsSelf
0x18001a0c6  call    cs:__imp_OpenThreadToken
0x18001a0cc  test    eax, eax
0x18001a0ce  jnz     short loc_18001A127
0x18001a0d0  mov     [rsp+120h+TokenHandle], r12
0x18001a0d5  call    cs:__imp_GetLastError
0x18001a0db  cmp     eax, 3F0h
0x18001a0e0  jz      short loc_18001A127
0x18001a0e2  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001a0e9  jz      loc_18001A435
0x18001a0ef  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a0f6  test    rbx, rbx
0x18001a0f9  jz      short loc_18001A104
0x18001a0fb  lea     rdx, aImpersonateuse; "ImpersonateUser: Failed to open thread "...
0x18001a102  jmp     short loc_18001A173
0x18001a104  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a10b  jz      loc_18001A1B1
0x18001a111  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001a118  jz      loc_18001A1B1
0x18001a11e  lea     rdx, aImpersonateuse; "ImpersonateUser: Failed to open thread "...
0x18001a125  jmp     short loc_18001A1A4
0x18001a127  mov     rcx, rbx; hToken
0x18001a12a  call    cs:__imp_ImpersonateLoggedOnUser
0x18001a130  test    eax, eax
0x18001a132  jnz     loc_18001A20F
0x18001a138  mov     rcx, [rsp+120h+TokenHandle]; hObject
0x18001a13d  test    rcx, rcx
0x18001a140  jz      short loc_18001A14D
0x18001a142  call    cs:__imp_CloseHandle
0x18001a148  mov     [rsp+120h+TokenHandle], r12
0x18001a14d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001a154  jz      loc_18001A435
0x18001a15a  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a161  test    rbx, rbx
0x18001a164  jz      short loc_18001A185
0x18001a166  call    cs:__imp_GetLastError
0x18001a16c  lea     rdx, aImpersonateuse_0; "ImpersonateUser: Failed to impersonate "...
0x18001a173  mov     r8d, eax
0x18001a176  mov     ecx, 4
0x18001a17b  mov     rax, rbx
0x18001a17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a183  jmp     short loc_18001A1B1
0x18001a185  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001a18c  jz      short loc_18001A1B1
0x18001a18e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a195  jz      short loc_18001A1B1
0x18001a197  call    cs:__imp_GetLastError
0x18001a19d  lea     rdx, aImpersonateuse_0; "ImpersonateUser: Failed to impersonate "...
0x18001a1a4  mov     r8d, eax
0x18001a1a7  mov     ecx, 4; unsigned int
0x18001a1ac  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001a1b1  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001a1b8  jz      loc_18001A435
0x18001a1be  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a1c5  test    rbx, rbx
0x18001a1c8  jz      short loc_18001A1E1
0x18001a1ca  lea     rdx, aSetrsoptargetn_0; "SetRsopTargetName: Failed to impersonat"...
0x18001a1d1  mov     ecx, r13d
0x18001a1d4  mov     rax, rbx
0x18001a1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1dc  jmp     loc_18001A435
0x18001a1e1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001a1e8  jz      loc_18001A435
0x18001a1ee  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a1f5  jz      loc_18001A435
0x18001a1fb  lea     rdx, aSetrsoptargetn_0; "SetRsopTargetName: Failed to impersonat"...
0x18001a202  mov     ecx, r13d; unsigned int
0x18001a205  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001a20a  jmp     loc_18001A435
0x18001a20f  mov     [rsp+120h+nSize], 4Bh ; 'K'
0x18001a217  mov     edx, 96h; uBytes
0x18001a21c  mov     ecx, edi; uFlags
0x18001a21e  call    cs:__imp_LocalAlloc
0x18001a224  mov     rbx, rax
0x18001a227  test    rax, rax
0x18001a22a  jnz     short loc_18001A295
0x18001a22c  call    cs:__imp_GetLastError
0x18001a232  mov     edi, eax
0x18001a234  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001a23b  jz      loc_18001A388
0x18001a241  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a248  test    rax, rax
0x18001a24b  jz      short loc_18001A264
0x18001a24d  mov     r8d, edi
0x18001a250  lea     rdx, aMygetusernameF; "MyGetUserName:  Failed to allocate memo"...
0x18001a257  mov     ecx, r13d
0x18001a25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a25f  jmp     loc_18001A388
0x18001a264  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001a26b  jz      loc_18001A388
0x18001a271  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a278  jz      loc_18001A388
0x18001a27e  mov     r8d, edi
0x18001a281  lea     rdx, aMygetusernameF; "MyGetUserName:  Failed to allocate memo"...
0x18001a288  mov     ecx, r13d; unsigned int
0x18001a28b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001a290  jmp     loc_18001A388
0x18001a295  mov     esi, r12d
0x18001a298  mov     [rbp+57h+var_C8], r12
0x18001a29c  mov     [rbp+57h+var_C0], r12
0x18001a2a0  lea     rax, API_CALL_TRACING_END_SUCCESS
0x18001a2a7  mov     [rbp+57h+var_B8], rax
0x18001a2ab  mov     [rbp+57h+var_B0], r12
0x18001a2af  lea     rax, API_CALL_TRACING_END_FAILURE; "i\x1B"
0x18001a2b6  mov     [rbp+57h+var_A8], rax
0x18001a2ba  lea     rax, ??_7CAPICallScenarioEvent@@6B@; const CAPICallScenarioEvent::`vftable'
0x18001a2c1  mov     [rbp+57h+var_D0], rax
0x18001a2c5  mov     [rbp+57h+var_9C], r12d
0x18001a2c9  mov     [rbp+57h+var_98], 1015h
0x18001a2d0  mov     [rbp+57h+var_78], 1016h
0x18001a2d7  mov     [rbp+57h+var_58], r12
0x18001a2db  lea     r8, [rsp+120h+nSize]; nSize
0x18001a2e0  mov     rdx, rbx; lpNameBuffer
0x18001a2e3  mov     ecx, r13d; NameFormat
0x18001a2e6  call    cs:__imp_GetUserNameExW
0x18001a2ec  test    al, al
0x18001a2ee  jnz     loc_18001A37C
0x18001a2f4  call    cs:__imp_GetLastError
0x18001a2fa  mov     edi, eax
0x18001a2fc  mov     eax, [rsp+120h+nSize]
0x18001a300  test    eax, eax
0x18001a302  jz      short loc_18001A32D
0x18001a304  cmp     edi, 7Ah ; 'z'
0x18001a307  jz      short loc_18001A311
0x18001a309  cmp     edi, 0EAh
0x18001a30f  jnz     short loc_18001A32D
0x18001a311  mov     rdx, rax
0x18001a314  add     rdx, rdx; uBytes
0x18001a317  mov     r8d, r13d; uFlags
0x18001a31a  mov     rcx, rbx; hMem
0x18001a31d  call    cs:__imp_LocalReAlloc
0x18001a323  test    rax, rax
0x18001a326  jz      short loc_18001A366
0x18001a328  mov     rbx, rax
0x18001a32b  jmp     short loc_18001A358
0x18001a32d  cmp     edi, 534h
0x18001a333  jz      short loc_18001A36E
0x18001a335  cmp     edi, 4CFh
0x18001a33b  jz      short loc_18001A36E
0x18001a33d  cmp     edi, 54Bh
0x18001a343  jz      short loc_18001A36E
0x18001a345  inc     esi
0x18001a347  cmp     esi, 3
0x18001a34a  ja      short loc_18001A36E
0x18001a34c  mov     ecx, 1F4h; dwMilliseconds
0x18001a351  call    cs:__imp_Sleep
0x18001a357  nop
0x18001a358  lea     rcx, [rbp+57h+var_C8]; this
0x18001a35c  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x18001a361  jmp     loc_18001A298
0x18001a366  call    cs:__imp_GetLastError
0x18001a36c  mov     edi, eax
0x18001a36e  mov     rcx, rbx; hMem
0x18001a371  call    cs:__imp_LocalFree
0x18001a377  mov     rbx, r12
0x18001a37a  jmp     short loc_18001A37F
0x18001a37c  mov     edi, r12d
0x18001a37f  lea     rcx, [rbp+57h+var_C8]; this
0x18001a383  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x18001a388  mov     ecx, edi; dwErrCode
0x18001a38a  call    cs:__imp_SetLastError
0x18001a390  mov     [rsp+120h+lpBuffer], rbx
0x18001a395  lea     rcx, [rsp+120h+TokenHandle]; void **
0x18001a39a  call    ?RevertToUser@@YAHPEAPEAX@Z; RevertToUser(void * *)
0x18001a39f  test    rbx, rbx
0x18001a3a2  jnz     loc_18001A451
0x18001a3a8  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18001a3af  jz      loc_18001A435
0x18001a3b5  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001a3bc  test    rbx, rbx
0x18001a3bf  jz      short loc_18001A3F4
0x18001a3c1  call    cs:__imp_GetLastError
0x18001a3c7  test    byte ptr [r14], 1
0x18001a3cb  lea     rcx, aUser; "User"
0x18001a3d2  lea     r8, aComputer; "Computer"
0x18001a3d9  cmovz   r8, rcx
0x18001a3dd  mov     r9d, eax
0x18001a3e0  lea     rdx, aSetrsoptargetn; "SetRsopTargetName: Failed to get the %s"...
0x18001a3e7  mov     ecx, r13d
0x18001a3ea  mov     rax, rbx
0x18001a3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3f2  jmp     short loc_18001A435
0x18001a3f4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18001a3fb  jz      short loc_18001A435
0x18001a3fd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18001a404  jz      short loc_18001A435
0x18001a406  call    cs:__imp_GetLastError
0x18001a40c  test    byte ptr [r14], 1
0x18001a410  lea     rcx, aUser; "User"
0x18001a417  lea     r8, aComputer; "Computer"
0x18001a41e  cmovz   r8, rcx
0x18001a422  mov     r9d, eax
0x18001a425  lea     rdx, aSetrsoptargetn; "SetRsopTargetName: Failed to get the %s"...
0x18001a42c  mov     ecx, r13d; unsigned int
0x18001a42f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18001a434  nop
0x18001a435  lea     rcx, [rsp+120h+var_D8]
0x18001a43a  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001a43f  nop
0x18001a440  lea     rcx, [rsp+120h+lpBuffer]
0x18001a445  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18001a44a  xor     eax, eax
0x18001a44c  jmp     loc_18001A5B7
0x18001a451  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001a455  mov     rdi, rsi
0x18001a458  inc     rdi
0x18001a45b  cmp     [rbx+rdi*2], r12w
0x18001a460  jnz     short loc_18001A458
0x18001a462  inc     rdi
0x18001a465  lea     rdx, [rdi+rdi]; uBytes
0x18001a469  mov     ecx, 40h ; '@'; uFlags
0x18001a46e  call    cs:__imp_LocalAlloc
0x18001a474  mov     rdx, rax
0x18001a477  test    rax, rax
0x18001a47a  jnz     short loc_18001A487
0x18001a47c  mov     rcx, rbx; hMem
0x18001a47f  call    cs:__imp_LocalFree
0x18001a485  jmp     short loc_18001A44A
0x18001a487  mov     rcx, rbx
0x18001a48a  movzx   eax, word ptr [rbx]
0x18001a48d  jmp     short loc_18001A49B
0x18001a48f  cmp     ax, 5Ch ; '\'
0x18001a493  jz      short loc_18001A4A0
0x18001a495  add     rcx, r13
0x18001a498  movzx   eax, word ptr [rcx]
0x18001a49b  test    ax, ax
0x18001a49e  jnz     short loc_18001A48F
0x18001a4a0  cmp     word ptr [rcx], 5Ch ; '\'
0x18001a4a4  jnz     short loc_18001A4E8
0x18001a4a6  test    rdi, rdi
0x18001a4a9  jz      loc_18001A548
0x18001a4af  cmp     rdi, 7FFFFFFFh
0x18001a4b6  ja      short loc_18001A4F6
  ... truncated ...
```
