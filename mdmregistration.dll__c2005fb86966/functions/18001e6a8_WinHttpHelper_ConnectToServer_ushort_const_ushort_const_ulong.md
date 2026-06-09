# WinHttpHelper::ConnectToServer(ushort const *,ushort const *,ulong)

- ea: `0x18001e6a8`
- end: `0x18001e983`
- name: `?ConnectToServer@WinHttpHelper@@QEAAJPEBG0K@Z`
- size: `731`
- prototype: `int(WinHttpHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ffc0`
- `0x180021458`

## callees

- `0x1800141b0`
- `0x180019ec0`
- `0x18001e6a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e7ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e8bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e7ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e8bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e846`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e846`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001e913`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001e92e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001e942`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001e913`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001e92e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001e942`
- `DMCmnUtils!DmImpersonate` at `0x18001e73f`
- `DMCmnUtils!DmImpersonate` at `0x18001e73f`
- `WINHTTP!WinHttpCloseHandle` at `0x18001e79f`
- `WINHTTP!WinHttpCloseHandle` at `0x18001e8b1`
- `WINHTTP!WinHttpCloseHandle` at `0x18001e79f`
- `WINHTTP!WinHttpCloseHandle` at `0x18001e8b1`
- `WINHTTP!WinHttpOpen` at `0x18001e777`
- `WINHTTP!WinHttpOpen` at `0x18001e777`
- `WINHTTP!WinHttpSetTimeouts` at `0x18001e867`
- `WINHTTP!WinHttpSetTimeouts` at `0x18001e867`
- `WINHTTP!WinHttpConnect` at `0x18001e888`
- `WINHTTP!WinHttpConnect` at `0x18001e888`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinHttpHelper::ConnectToServer(
        WinHttpHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        INTERNET_PORT a4)
{
  void *v8; // rsi
  HINTERNET v9; // rsi
  void *v10; // r14
  DWORD LastError; // ebx
  unsigned int v12; // eax
  HINTERNET v13; // rsi
  void *v14; // r14
  DWORD v15; // ebx
  void *v16; // rcx
  void *v17; // rcx
  unsigned int v18; // ebx
  int nSendTimeout; // [rsp+48h] [rbp-29h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-25h] BYREF
  DWORD pdwType; // [rsp+50h] [rbp-21h] BYREF
  void *v23; // [rsp+58h] [rbp-19h]
  _QWORD v24[2]; // [rsp+60h] [rbp-11h] BYREF
  __int128 v25; // [rsp+70h] [rbp-1h]
  unsigned int v26; // [rsp+E8h] [rbp+77h] BYREF

  v26 = 0;
  v25 = 0;
  v8 = 0;
  v23 = 0;
  v24[0] = "WinHttpHelper::ConnectToServer";
  v24[1] = &v26;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, ConnectingToServerEvent, a3);
  if ( !a3 )
  {
    v26 = -2147024809;
    goto LABEL_25;
  }
  if ( a2 )
  {
    if ( !*((_BYTE *)this + 40) && (int)DmImpersonate(a2) >= 0 )
    {
      *((_BYTE *)this + 40) = 1;
      *((_BYTE *)this + 42) = 1;
    }
    v26 = 0;
  }
  v9 = WinHttpOpen(L"ENROLLClient", 4u, 0, 0, 0);
  v10 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    WinHttpCloseHandle(v10);
    SetLastError(LastError);
  }
  *(_QWORD *)this = v9;
  if ( v9
    && ((nSendTimeout = 0,
         pcbData = 4,
         pdwType = 0,
         RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Enrollments",
           L"HTTPTimeout",
           0x10u,
           &pdwType,
           &nSendTimeout,
           &pcbData))
     || WinHttpSetTimeouts(*(HINTERNET *)this, 0, nSendTimeout, nSendTimeout, nSendTimeout)) )
  {
    v13 = WinHttpConnect(*(HINTERNET *)this, a3, a4, 0);
    v14 = (void *)*((_QWORD *)this + 1);
    if ( v14 )
    {
      v15 = GetLastError();
      WinHttpCloseHandle(v14);
      SetLastError(v15);
    }
    *((_QWORD *)this + 1) = v13;
    if ( v13 )
      goto LABEL_24;
    if ( (int)GetLastError() > 0 )
    {
      v26 = (unsigned __int16)GetLastError() | 0x80190000;
      goto LABEL_24;
    }
  }
  else if ( (int)GetLastError() > 0 )
  {
    v12 = (unsigned __int16)GetLastError() | 0x80190000;
    goto LABEL_16;
  }
  v12 = GetLastError();
LABEL_16:
  v26 = v12;
LABEL_24:
  v8 = v23;
LABEL_25:
  v16 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v16 )
    GlobalFree(v16);
  v17 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v17 )
    GlobalFree(v17);
  if ( v8 )
    GlobalFree(v8);
  v18 = v26;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v24);
  return v18;
}

```

## disassembly

```asm
0x18001e6a8  mov     rax, rsp
0x18001e6ab  mov     [rax+8], rbx
0x18001e6af  mov     [rax+10h], rsi
0x18001e6b3  push    rbp
0x18001e6b4  push    rdi
0x18001e6b5  push    r12
0x18001e6b7  push    r14
0x18001e6b9  push    r15
0x18001e6bb  lea     rbp, [rax-5Fh]
0x18001e6bf  sub     rsp, 0A0h
0x18001e6c6  movaps  xmmword ptr [rax-38h], xmm6
0x18001e6ca  movaps  xmmword ptr [rax-48h], xmm7
0x18001e6ce  mov     r12d, r9d
0x18001e6d1  mov     r15, r8
0x18001e6d4  mov     rbx, rdx
0x18001e6d7  mov     rdi, rcx
0x18001e6da  mov     [rbp+57h+arg_10], 0
0x18001e6e1  xorps   xmm6, xmm6
0x18001e6e4  movups  [rbp+57h+var_58], xmm6
0x18001e6e8  xorps   xmm7, xmm7
0x18001e6eb  xor     esi, esi
0x18001e6ed  mov     [rbp+57h+var_70], rsi
0x18001e6f1  lea     rax, aWinhttphelperC; "WinHttpHelper::ConnectToServer"
0x18001e6f8  mov     [rbp+57h+var_68], rax
0x18001e6fc  lea     rax, [rbp+57h+arg_10]
0x18001e700  mov     [rbp+57h+var_60], rax
0x18001e704  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x18001e70b  jz      short loc_18001E720
0x18001e70d  lea     rdx, ConnectingToServerEvent
0x18001e714  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18001e71b  call    McTemplateU0z_EventWriteTransfer
0x18001e720  test    r15, r15
0x18001e723  jnz     short loc_18001E731
0x18001e725  mov     [rbp+57h+arg_10], 80070057h
0x18001e72c  jmp     loc_18001E904
0x18001e731  test    rbx, rbx
0x18001e734  jz      short loc_18001E75E
0x18001e736  cmp     byte ptr [rdi+28h], 0
0x18001e73a  jnz     short loc_18001E757
0x18001e73c  mov     rcx, rbx
0x18001e73f  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18001e746  nop     dword ptr [rax+rax+00h]
0x18001e74b  test    eax, eax
0x18001e74d  js      short loc_18001E757
0x18001e74f  mov     byte ptr [rdi+28h], 1
0x18001e753  mov     byte ptr [rdi+2Ah], 1
0x18001e757  mov     [rbp+57h+arg_10], 0
0x18001e75e  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x18001e766  xor     r9d, r9d; pszProxyBypassW
0x18001e769  xor     r8d, r8d; pszProxyW
0x18001e76c  lea     edx, [r9+4]; dwAccessType
0x18001e770  lea     rcx, pszAgentW; "ENROLLClient"
0x18001e777  call    cs:__imp_WinHttpOpen
0x18001e77e  nop     dword ptr [rax+rax+00h]
0x18001e783  mov     rsi, rax
0x18001e786  mov     r14, [rdi]
0x18001e789  test    r14, r14
0x18001e78c  jz      short loc_18001E7B9
0x18001e78e  call    cs:__imp_GetLastError
0x18001e795  nop     dword ptr [rax+rax+00h]
0x18001e79a  mov     ebx, eax
0x18001e79c  mov     rcx, r14; hInternet
0x18001e79f  call    cs:__imp_WinHttpCloseHandle
0x18001e7a6  nop     dword ptr [rax+rax+00h]
0x18001e7ab  mov     ecx, ebx; dwErrCode
0x18001e7ad  call    cs:__imp_SetLastError
0x18001e7b4  nop     dword ptr [rax+rax+00h]
0x18001e7b9  mov     [rdi], rsi
0x18001e7bc  test    rsi, rsi
0x18001e7bf  jnz     short loc_18001E7FB
0x18001e7c1  call    cs:__imp_GetLastError
0x18001e7c8  nop     dword ptr [rax+rax+00h]
0x18001e7cd  test    eax, eax
0x18001e7cf  jg      short loc_18001E7DF
0x18001e7d1  call    cs:__imp_GetLastError
0x18001e7d8  nop     dword ptr [rax+rax+00h]
0x18001e7dd  jmp     short loc_18001E7F3
0x18001e7df  call    cs:__imp_GetLastError
0x18001e7e6  nop     dword ptr [rax+rax+00h]
0x18001e7eb  movzx   eax, ax
0x18001e7ee  or      eax, 80190000h
0x18001e7f3  mov     [rbp+57h+arg_10], eax
0x18001e7f6  jmp     loc_18001E900
0x18001e7fb  mov     [rbp+57h+nSendTimeout], 0
0x18001e802  mov     [rbp+57h+var_7C], 4
0x18001e809  mov     [rbp+57h+pdwType], 0
0x18001e810  lea     rax, [rbp+57h+var_7C]
0x18001e814  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18001e819  lea     rax, [rbp+57h+nSendTimeout]
0x18001e81d  mov     [rsp+0C0h+pvData], rax; pvData
0x18001e822  lea     rax, [rbp+57h+pdwType]
0x18001e826  mov     qword ptr [rsp+0C0h+dwFlags], rax; pdwType
0x18001e82b  mov     r9d, 10h; dwFlags
0x18001e831  lea     r8, Value; "HTTPTimeout"
0x18001e838  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Enrollments"
0x18001e83f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001e846  call    cs:__imp_RegGetValueW
0x18001e84d  nop     dword ptr [rax+rax+00h]
0x18001e852  test    eax, eax
0x18001e854  jnz     short loc_18001E87B
0x18001e856  mov     r8d, [rbp+57h+nSendTimeout]; nConnectTimeout
0x18001e85a  mov     [rsp+0C0h+dwFlags], r8d; nReceiveTimeout
0x18001e85f  mov     r9d, r8d; nSendTimeout
0x18001e862  xor     edx, edx; nResolveTimeout
0x18001e864  mov     rcx, [rdi]; hInternet
0x18001e867  call    cs:__imp_WinHttpSetTimeouts
0x18001e86e  nop     dword ptr [rax+rax+00h]
0x18001e873  test    eax, eax
0x18001e875  jz      loc_18001E7C1
0x18001e87b  movzx   r8d, r12w; nServerPort
0x18001e87f  xor     r9d, r9d; dwReserved
0x18001e882  mov     rdx, r15; pswzServerName
0x18001e885  mov     rcx, [rdi]; hSession
0x18001e888  call    cs:__imp_WinHttpConnect
0x18001e88f  nop     dword ptr [rax+rax+00h]
0x18001e894  mov     rsi, rax
0x18001e897  mov     r14, [rdi+8]
0x18001e89b  test    r14, r14
0x18001e89e  jz      short loc_18001E8CB
0x18001e8a0  call    cs:__imp_GetLastError
0x18001e8a7  nop     dword ptr [rax+rax+00h]
0x18001e8ac  mov     ebx, eax
0x18001e8ae  mov     rcx, r14; hInternet
0x18001e8b1  call    cs:__imp_WinHttpCloseHandle
0x18001e8b8  nop     dword ptr [rax+rax+00h]
0x18001e8bd  mov     ecx, ebx; dwErrCode
0x18001e8bf  call    cs:__imp_SetLastError
0x18001e8c6  nop     dword ptr [rax+rax+00h]
0x18001e8cb  mov     [rdi+8], rsi
0x18001e8cf  test    rsi, rsi
0x18001e8d2  jnz     short loc_18001E900
0x18001e8d4  call    cs:__imp_GetLastError
0x18001e8db  nop     dword ptr [rax+rax+00h]
0x18001e8e0  test    eax, eax
0x18001e8e2  jle     loc_18001E7D1
0x18001e8e8  call    cs:__imp_GetLastError
0x18001e8ef  nop     dword ptr [rax+rax+00h]
0x18001e8f4  movzx   ecx, ax
0x18001e8f7  or      ecx, 80190000h
0x18001e8fd  mov     [rbp+57h+arg_10], ecx
0x18001e900  mov     rsi, [rbp+57h+var_70]
0x18001e904  psrldq  xmm6, 8
0x18001e909  movq    rcx, xmm6; hMem
0x18001e90e  test    rcx, rcx
0x18001e911  jz      short loc_18001E91F
0x18001e913  call    cs:__imp_GlobalFree
0x18001e91a  nop     dword ptr [rax+rax+00h]
0x18001e91f  psrldq  xmm7, 8
0x18001e924  movq    rcx, xmm7; hMem
0x18001e929  test    rcx, rcx
0x18001e92c  jz      short loc_18001E93A
0x18001e92e  call    cs:__imp_GlobalFree
0x18001e935  nop     dword ptr [rax+rax+00h]
0x18001e93a  test    rsi, rsi
0x18001e93d  jz      short loc_18001E94E
0x18001e93f  mov     rcx, rsi; hMem
0x18001e942  call    cs:__imp_GlobalFree
0x18001e949  nop     dword ptr [rax+rax+00h]
0x18001e94e  mov     ebx, [rbp+57h+arg_10]
0x18001e951  lea     rcx, [rbp+57h+var_68]; this
0x18001e955  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001e95a  mov     eax, ebx
0x18001e95c  lea     r11, [rsp+0C0h+var_20]
0x18001e964  mov     rbx, [r11+30h]
0x18001e968  mov     rsi, [r11+38h]
0x18001e96c  movaps  xmm6, xmmword ptr [r11-10h]
0x18001e971  movaps  xmm7, xmmword ptr [r11-20h]
0x18001e976  mov     rsp, r11
0x18001e979  pop     r15
0x18001e97b  pop     r14
0x18001e97d  pop     r12
0x18001e97f  pop     rdi
0x18001e980  pop     rbp
0x18001e981  retn
```
