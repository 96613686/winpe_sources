# WinHttpHelper::ConnectToServer(ushort const *,ushort const *,ulong)

- ea: `0x180052378`
- end: `0x180052570`
- name: `?ConnectToServer@WinHttpHelper@@QEAAJPEBG0K@Z`
- size: `504`
- prototype: `__int64 __fastcall(HINTERNET *this, const unsigned __int16 *, const unsigned __int16 *, INTERNET_PORT)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800533ec`
- `0x18005363c`

## callees

- `0x1800140d0`
- `0x18003b170`
- `0x1800424fc`
- `0x180052378`
- `0x180053d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005243d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005244f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005243d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005244f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052509`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005252a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005253f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005252a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005253f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800524ac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800524ac`
- `WINHTTP!WinHttpConnect` at `0x1800524e2`
- `WINHTTP!WinHttpConnect` at `0x1800524e2`
- `WINHTTP!WinHttpOpen` at `0x180052426`
- `WINHTTP!WinHttpOpen` at `0x180052426`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800524c7`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800524c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinHttpHelper::ConnectToServer(
        HINTERNET *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        INTERNET_PORT a4)
{
  HINTERNET v8; // rax
  unsigned int LastError; // eax
  HINTERNET v10; // rax
  void *v11; // rcx
  void *v12; // rcx
  unsigned int v13; // ebx
  int nSendTimeout; // [rsp+48h] [rbp-29h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-25h] BYREF
  DWORD pdwType; // [rsp+50h] [rbp-21h] BYREF
  _QWORD v18[2]; // [rsp+58h] [rbp-19h] BYREF
  __int128 v19; // [rsp+68h] [rbp-9h]
  unsigned int v20; // [rsp+E8h] [rbp+77h] BYREF

  v20 = 0;
  v19 = 0;
  v18[0] = "WinHttpHelper::ConnectToServer";
  v18[1] = &v20;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, ConnectingToServerEvent, a3);
  if ( !a3 )
  {
    v20 = -2147024809;
    goto LABEL_17;
  }
  if ( a2 )
  {
    AutoImpersonate::ImpersonateSID((AutoImpersonate *)(this + 5), a2);
    v20 = 0;
  }
  v8 = WinHttpOpen(L"ENROLLClient", 4u, 0, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    this,
    v8);
  if ( !*this
    || (nSendTimeout = 0,
        pcbData = 4,
        pdwType = 0,
        !RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Enrollments",
           L"HTTPTimeout",
           0x10u,
           &pdwType,
           &nSendTimeout,
           &pcbData))
    && !WinHttpSetTimeouts(*this, 0, nSendTimeout, nSendTimeout, nSendTimeout) )
  {
    if ( (int)GetLastError() > 0 )
    {
      LastError = (unsigned __int16)GetLastError() | 0x80190000;
      goto LABEL_11;
    }
LABEL_9:
    LastError = GetLastError();
LABEL_11:
    v20 = LastError;
    goto LABEL_17;
  }
  v10 = WinHttpConnect(*this, a3, a4, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    this + 1,
    v10);
  if ( this[1] )
    goto LABEL_17;
  if ( (int)GetLastError() <= 0 )
    goto LABEL_9;
  v20 = (unsigned __int16)GetLastError() | 0x80190000;
LABEL_17:
  v11 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v11 )
    GlobalFree(v11);
  v12 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v12 )
    GlobalFree(v12);
  v13 = v20;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v18, (__int64)a2);
  return v13;
}

```

## disassembly

```asm
0x180052378  mov     rax, rsp
0x18005237b  push    rbp
0x18005237c  push    rbx
0x18005237d  push    rsi
0x18005237e  push    rdi
0x18005237f  push    r12
0x180052381  push    r14
0x180052383  lea     rbp, [rax-5Fh]
0x180052387  sub     rsp, 98h
0x18005238e  movaps  xmmword ptr [rax-48h], xmm6
0x180052392  movaps  xmmword ptr [rax-58h], xmm7
0x180052396  mov     r14d, r9d
0x180052399  mov     rsi, r8
0x18005239c  mov     rbx, rdx
0x18005239f  mov     rdi, rcx
0x1800523a2  mov     [rbp+57h+arg_10], 0
0x1800523a9  xorps   xmm6, xmm6
0x1800523ac  movups  xmmword ptr [rbp-9], xmm6
0x1800523b0  xorps   xmm7, xmm7
0x1800523b3  lea     rax, aWinhttphelperC; "WinHttpHelper::ConnectToServer"
0x1800523ba  mov     [rbp+57h+var_70], rax
0x1800523be  lea     rax, [rbp+57h+arg_10]
0x1800523c2  mov     [rbp+57h+var_68], rax
0x1800523c6  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x1800523cd  jz      short loc_1800523E2
0x1800523cf  lea     rdx, ConnectingToServerEvent
0x1800523d6  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x1800523dd  call    McTemplateU0z_EventWriteTransfer
0x1800523e2  test    rsi, rsi
0x1800523e5  jnz     short loc_1800523F3
0x1800523e7  mov     [rbp+57h+arg_10], 80070057h
0x1800523ee  jmp     loc_18005251B
0x1800523f3  test    rbx, rbx
0x1800523f6  jz      short loc_18005240B
0x1800523f8  lea     rcx, [rdi+28h]; this
0x1800523fc  mov     rdx, rbx; unsigned __int16 *
0x1800523ff  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x180052404  mov     [rbp+57h+arg_10], 0
0x18005240b  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x180052413  xor     r9d, r9d; pszProxyBypassW
0x180052416  xor     r8d, r8d; pszProxyW
0x180052419  lea     ebx, [r9+4]
0x18005241d  mov     edx, ebx; dwAccessType
0x18005241f  lea     rcx, pszAgentW; "ENROLLClient"
0x180052426  call    cs:__imp_WinHttpOpen
0x18005242c  mov     rdx, rax
0x18005242f  mov     rcx, rdi
0x180052432  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180052437  cmp     qword ptr [rdi], 0
0x18005243b  jnz     short loc_180052465
0x18005243d  call    cs:__imp_GetLastError
0x180052443  test    eax, eax
0x180052445  jg      short loc_18005244F
0x180052447  call    cs:__imp_GetLastError
0x18005244d  jmp     short loc_18005245D
0x18005244f  call    cs:__imp_GetLastError
0x180052455  movzx   eax, ax
0x180052458  or      eax, 80190000h
0x18005245d  mov     [rbp+57h+arg_10], eax
0x180052460  jmp     loc_18005251B
0x180052465  mov     [rbp+57h+nSendTimeout], 0
0x18005246c  mov     [rbp+57h+pcbData], ebx
0x18005246f  mov     [rbp+57h+pdwType], 0
0x180052476  lea     rax, [rbp+57h+pcbData]
0x18005247a  mov     [rsp+30h], rax; pcbData
0x18005247f  lea     rax, [rbp+57h+nSendTimeout]
0x180052483  mov     [rsp+0C0h+pvData], rax; pvData
0x180052488  lea     rax, [rbp+57h+pdwType]
0x18005248c  mov     qword ptr [rsp+0C0h+dwFlags], rax; pdwType
0x180052491  mov     r9d, 10h; dwFlags
0x180052497  lea     r8, aHttptimeout; "HTTPTimeout"
0x18005249e  lea     rdx, SubKey; "Software\\Microsoft\\Enrollments"
0x1800524a5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800524ac  call    cs:__imp_RegGetValueW
0x1800524b2  test    eax, eax
0x1800524b4  jnz     short loc_1800524D5
0x1800524b6  mov     r8d, [rbp+57h+nSendTimeout]; nConnectTimeout
0x1800524ba  mov     [rsp+0C0h+dwFlags], r8d; nReceiveTimeout
0x1800524bf  mov     r9d, r8d; nSendTimeout
0x1800524c2  xor     edx, edx; nResolveTimeout
0x1800524c4  mov     rcx, [rdi]; hInternet
0x1800524c7  call    cs:__imp_WinHttpSetTimeouts
0x1800524cd  test    eax, eax
0x1800524cf  jz      loc_18005243D
0x1800524d5  movzx   r8d, r14w; nServerPort
0x1800524d9  xor     r9d, r9d; dwReserved
0x1800524dc  mov     rdx, rsi; pswzServerName
0x1800524df  mov     rcx, [rdi]; hSession
0x1800524e2  call    cs:__imp_WinHttpConnect
0x1800524e8  mov     rdx, rax
0x1800524eb  lea     rcx, [rdi+8]
0x1800524ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800524f4  cmp     qword ptr [rdi+8], 0
0x1800524f9  jnz     short loc_18005251B
0x1800524fb  call    cs:__imp_GetLastError
0x180052501  test    eax, eax
0x180052503  jle     loc_180052447
0x180052509  call    cs:__imp_GetLastError
0x18005250f  movzx   ecx, ax
0x180052512  or      ecx, 80190000h
0x180052518  mov     [rbp+57h+arg_10], ecx
0x18005251b  psrldq  xmm6, 8
0x180052520  movq    rcx, xmm6; hMem
0x180052525  test    rcx, rcx
0x180052528  jz      short loc_180052530
0x18005252a  call    cs:__imp_GlobalFree
0x180052530  psrldq  xmm7, 8
0x180052535  movq    rcx, xmm7; hMem
0x18005253a  test    rcx, rcx
0x18005253d  jz      short loc_180052545
0x18005253f  call    cs:__imp_GlobalFree
0x180052545  mov     ebx, [rbp+57h+arg_10]
0x180052548  lea     rcx, [rbp+57h+var_70]; this
0x18005254c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180052551  mov     eax, ebx
0x180052553  movaps  xmm6, [rsp+0C0h+var_48+8]
0x18005255b  movaps  xmm7, [rsp+0C0h+var_58+8]
0x180052560  add     rsp, 98h
0x180052567  pop     r14
0x180052569  pop     r12
0x18005256b  pop     rdi
0x18005256c  pop     rsi
0x18005256d  pop     rbx
0x18005256e  pop     rbp
0x18005256f  retn
```
