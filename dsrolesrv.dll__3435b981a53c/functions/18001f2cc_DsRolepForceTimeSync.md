# DsRolepForceTimeSync

- ea: `0x18001f2cc`
- end: `0x18001f5a8`
- name: `DsRolepForceTimeSync`
- size: `732`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800202c0`

## callees

- `0x18000e4d0`
- `0x180016374`
- `0x18001f2cc`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f46e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f46e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f506`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f579`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f506`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f579`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001f45f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001f45f`
- `ntdll!NtSetSystemTime` at `0x18001f515`
- `ntdll!NtSetSystemTime` at `0x18001f515`
- `ntdll!RtlTimeFieldsToTime` at `0x18001f4f0`
- `ntdll!RtlTimeFieldsToTime` at `0x18001f4f0`
- `ntdll!NtOpenProcessToken` at `0x18001f3d5`
- `ntdll!NtOpenProcessToken` at `0x18001f3d5`
- `ntdll!NtAdjustPrivilegesToken` at `0x18001f419`
- `ntdll!NtAdjustPrivilegesToken` at `0x18001f419`
- `ntdll!NtOpenThreadToken` at `0x18001f3b9`
- `ntdll!NtOpenThreadToken` at `0x18001f3b9`
- `ntdll!RtlAllocateHeap` at `0x18001f359`
- `ntdll!RtlAllocateHeap` at `0x18001f359`
- `ntdll!RtlNtStatusToDosError` at `0x18001f432`
- `ntdll!RtlNtStatusToDosError` at `0x18001f534`
- `ntdll!RtlNtStatusToDosError` at `0x18001f432`
- `ntdll!RtlNtStatusToDosError` at `0x18001f534`
- `ntdll!NtClose` at `0x18001f42a`
- `ntdll!NtClose` at `0x18001f42a`
- `netutils!NetApiBufferFree` at `0x18001f540`
- `netutils!NetApiBufferFree` at `0x18001f540`
- `srvcli!NetRemoteTOD` at `0x18001f48f`
- `srvcli!NetRemoteTOD` at `0x18001f48f`

## string_xrefs

- `0x18001f474`: `Failed to impersonate caller, error %lu\n`
- `0x18001f370`: `Failed to open a NULL session with %ws for time sync.  Out of Memory. Failed with %d\n`
- `0x18001f43c`: `Failed to enable the SE_SYSTEMTIME_PRIVILEGE: %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepForceTimeSync(HANDLE hToken, const WCHAR *a2)
{
  ULONG v4; // ebx
  __int64 v5; // rax
  size_t v6; // rbx
  wchar_t *Heap; // rax
  const WCHAR *v8; // r15
  int v9; // r14d
  int v10; // ebx
  ULONG v11; // eax
  DWORD LastError; // eax
  DWORD v13; // eax
  NTSTATUS v14; // ebx
  NTSTATUS v15; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-31h] BYREF
  LPBYTE BufferPtr; // [rsp+40h] [rbp-29h] BYREF
  union _LARGE_INTEGER Time; // [rsp+48h] [rbp-21h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+50h] [rbp-19h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+60h] [rbp-9h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+70h] [rbp+7h] BYREF

  BufferPtr = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  Time.QuadPart = 0;
  NewState = 0;
  PreviousState = 0;
  TimeFields = 0;
  if ( !a2 )
    return 87;
  if ( *a2 == 92 )
  {
    v8 = a2;
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = v5 + 3;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * (v5 + 3));
    v8 = Heap;
    if ( !Heap )
    {
      v4 = 8;
      DsRolepLogPrintRoutine(
        1,
        "Failed to open a NULL session with %ws for time sync.  Out of Memory. Failed with %d\n",
        a2,
        8);
      return v4;
    }
    StringCchPrintfW(Heap, v6, L"\\\\%ws", a2);
  }
  v9 = 0;
  v10 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x200E8u, 1u, &TokenHandle);
  if ( v10 == -1073741700 )
    v10 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x200E8u, &TokenHandle);
  if ( v10 >= 0 )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)12LL;
    NewState.Privileges[0].Attributes = 2;
    ReturnLength = 16;
    v10 = NtAdjustPrivilegesToken(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  v11 = RtlNtStatusToDosError(v10);
  if ( v11 )
  {
    DsRolepLogPrintRoutine(1, "Failed to enable the SE_SYSTEMTIME_PRIVILEGE: %lu\n", v11);
  }
  else if ( hToken )
  {
    DsRolepSetCurrentOperationStatus(28723, a2, 0);
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v9 = 1;
    }
    else
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(4, "Failed to impersonate caller, error %lu\n", LastError);
    }
  }
  v13 = NetRemoteTOD(v8, &BufferPtr);
  v4 = v13;
  if ( v13 )
  {
    DsRolepLogPrintRoutine(1, "Failed to get the current time on %ws: %lu\n", a2, v13);
  }
  else
  {
    TimeFields.Hour = *((_WORD *)BufferPtr + 4);
    TimeFields.Minute = *((_WORD *)BufferPtr + 6);
    TimeFields.Second = *((_WORD *)BufferPtr + 8);
    TimeFields.Milliseconds = 10 * *((_WORD *)BufferPtr + 10);
    TimeFields.Day = *((_WORD *)BufferPtr + 16);
    TimeFields.Month = *((_WORD *)BufferPtr + 18);
    TimeFields.Year = *((_WORD *)BufferPtr + 20);
    if ( RtlTimeFieldsToTime(&TimeFields, &Time) )
    {
      if ( v9 )
      {
        RevertToSelf();
        v9 = 0;
      }
      v15 = NtSetSystemTime(&Time, 0);
      v14 = v15;
      if ( v15 < 0 )
        DsRolepLogPrintRoutine(1, "NtSetSystemTime failed with 0x%lx\n", v15);
    }
    else
    {
      v14 = -1073741811;
    }
    v4 = RtlNtStatusToDosError(v14);
    NetApiBufferFree(BufferPtr);
    if ( !v4 )
      goto LABEL_33;
  }
  DsRolepLogPrintRoutine(1, "NON-FATAL error forcing a time sync (%lu).  Ignoring\n", v4);
  v4 = 0;
LABEL_33:
  if ( v9 )
    RevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x18001f2cc  mov     [rsp-8+arg_10], rbx
0x18001f2d1  push    rbp
0x18001f2d2  push    rsi
0x18001f2d3  push    rdi
0x18001f2d4  push    r12
0x18001f2d6  push    r13
0x18001f2d8  push    r14
0x18001f2da  push    r15
0x18001f2dc  lea     rbp, [rsp-27h]
0x18001f2e1  sub     rsp, 90h
0x18001f2e8  mov     rax, cs:__security_cookie
0x18001f2ef  xor     rax, rsp
0x18001f2f2  mov     [rbp+57h+var_40], rax
0x18001f2f6  xor     r13d, r13d
0x18001f2f9  xorps   xmm0, xmm0
0x18001f2fc  mov     [rbp+57h+BufferPtr], r13
0x18001f300  xorps   xmm1, xmm1
0x18001f303  mov     [rbp+57h+TokenHandle], r13
0x18001f307  mov     rsi, rdx
0x18001f30a  mov     [rbp+57h+var_90], r13d
0x18001f30e  mov     r12, rcx
0x18001f311  mov     qword ptr [rbp+57h+Time], r13
0x18001f315  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18001f319  movups  xmmword ptr [rbp+57h+var_50.PrivilegeCount], xmm1
0x18001f31d  movups  xmmword ptr [rbp+57h+TimeFields.Year], xmm0
0x18001f321  test    rdx, rdx
0x18001f324  jnz     short loc_18001F32E
0x18001f326  lea     ebx, [rdx+57h]
0x18001f329  jmp     loc_18001F57F
0x18001f32e  cmp     word ptr [rdx], 5Ch ; '\'
0x18001f332  jz      short loc_18001F39B
0x18001f334  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f338  inc     rax
0x18001f33b  cmp     [rdx+rax*2], r13w
0x18001f340  jnz     short loc_18001F338
0x18001f342  mov     rcx, gs:60h
0x18001f34b  lea     rbx, [rax+3]
0x18001f34f  lea     r8, [rbx+rbx]; Size
0x18001f353  xor     edx, edx; Flags
0x18001f355  mov     rcx, [rcx+30h]; HeapHandle
0x18001f359  call    cs:__imp_RtlAllocateHeap
0x18001f35f  mov     r15, rax
0x18001f362  test    rax, rax
0x18001f365  jnz     short loc_18001F384
0x18001f367  lea     ebx, [rax+8]
0x18001f36a  mov     r8, rsi
0x18001f36d  mov     r9d, ebx
0x18001f370  lea     rdx, aFailedToOpenAN; "Failed to open a NULL session with %ws "...
0x18001f377  lea     ecx, [rax+1]
0x18001f37a  call    DsRolepLogPrintRoutine
0x18001f37f  jmp     loc_18001F57F
0x18001f384  mov     r9, rsi
0x18001f387  lea     r8, aWs; "\\\\%ws"
0x18001f38e  mov     rdx, rbx; cchDest
0x18001f391  mov     rcx, rax; pszDest
0x18001f394  call    StringCchPrintfW
0x18001f399  jmp     short loc_18001F39E
0x18001f39b  mov     r15, rsi
0x18001f39e  mov     edi, 1
0x18001f3a3  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001f3a7  mov     r8b, dil; OpenAsSelf
0x18001f3aa  mov     edx, 200E8h; DesiredAccess
0x18001f3af  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001f3b6  mov     r14d, r13d
0x18001f3b9  call    cs:__imp_NtOpenThreadToken
0x18001f3bf  mov     ebx, eax
0x18001f3c1  cmp     eax, 0C000007Ch
0x18001f3c6  jnz     short loc_18001F3DD
0x18001f3c8  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001f3cc  mov     edx, 200E8h; DesiredAccess
0x18001f3d1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001f3d5  call    cs:__imp_NtOpenProcessToken
0x18001f3db  mov     ebx, eax
0x18001f3dd  test    ebx, ebx
0x18001f3df  js      short loc_18001F421
0x18001f3e1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001f3e5  lea     rax, [rbp+57h+var_90]
0x18001f3e9  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18001f3ee  lea     r8, [rbp+57h+NewState]; NewState
0x18001f3f2  lea     rax, [rbp+57h+var_50]
0x18001f3f6  mov     [rbp+57h+NewState.PrivilegeCount], edi
0x18001f3f9  mov     r9d, 10h; BufferLength
0x18001f3ff  mov     [rsp+0C0h+PreviousState], rax; PreviousState
0x18001f404  xor     edx, edx; DisableAllPrivileges
0x18001f406  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], 0Ch
0x18001f40e  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x18001f415  mov     [rbp+57h+var_90], r9d
0x18001f419  call    cs:__imp_NtAdjustPrivilegesToken
0x18001f41f  mov     ebx, eax
0x18001f421  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18001f425  test    rcx, rcx
0x18001f428  jz      short loc_18001F430
0x18001f42a  call    cs:__imp_NtClose
0x18001f430  mov     ecx, ebx; Status
0x18001f432  call    cs:__imp_RtlNtStatusToDosError
0x18001f438  test    eax, eax
0x18001f43a  jz      short loc_18001F447
0x18001f43c  lea     rdx, aFailedToEnable; "Failed to enable the SE_SYSTEMTIME_PRIV"...
0x18001f443  mov     ecx, edi
0x18001f445  jmp     short loc_18001F480
0x18001f447  test    r12, r12
0x18001f44a  jz      short loc_18001F488
0x18001f44c  xor     r8d, r8d
0x18001f44f  mov     rdx, rsi
0x18001f452  mov     ecx, 7033h
0x18001f457  call    DsRolepSetCurrentOperationStatus
0x18001f45c  mov     rcx, r12; hToken
0x18001f45f  call    cs:__imp_ImpersonateLoggedOnUser
0x18001f465  test    eax, eax
0x18001f467  jz      short loc_18001F46E
0x18001f469  mov     r14d, edi
0x18001f46c  jmp     short loc_18001F488
0x18001f46e  call    cs:__imp_GetLastError
0x18001f474  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x18001f47b  mov     ecx, 4
0x18001f480  mov     r8d, eax
0x18001f483  call    DsRolepLogPrintRoutine
0x18001f488  lea     rdx, [rbp+57h+BufferPtr]; BufferPtr
0x18001f48c  mov     rcx, r15; UncServerName
0x18001f48f  call    cs:__imp_NetRemoteTOD
0x18001f495  mov     ebx, eax
0x18001f497  test    eax, eax
0x18001f499  jnz     loc_18001F54C
0x18001f49f  mov     rdx, [rbp+57h+BufferPtr]
0x18001f4a3  movzx   eax, word ptr [rdx+8]
0x18001f4a7  mov     [rbp+57h+TimeFields.Hour], ax
0x18001f4ab  movzx   eax, word ptr [rdx+0Ch]
0x18001f4af  mov     [rbp+57h+TimeFields.Minute], ax
0x18001f4b3  movzx   eax, word ptr [rdx+10h]
0x18001f4b7  mov     [rbp+57h+TimeFields.Second], ax
0x18001f4bb  movzx   ecx, word ptr [rdx+14h]
0x18001f4bf  movzx   eax, cx
0x18001f4c2  shl     ax, 2
0x18001f4c6  add     cx, ax
0x18001f4c9  add     cx, cx
0x18001f4cc  mov     [rbp+57h+TimeFields.Milliseconds], cx
0x18001f4d0  lea     rcx, [rbp+57h+TimeFields]; TimeFields
0x18001f4d4  movzx   eax, word ptr [rdx+20h]
0x18001f4d8  mov     [rbp+57h+TimeFields.Day], ax
0x18001f4dc  movzx   eax, word ptr [rdx+24h]
0x18001f4e0  mov     [rbp+57h+TimeFields.Month], ax
0x18001f4e4  movzx   eax, word ptr [rdx+28h]
0x18001f4e8  lea     rdx, [rbp+57h+Time]; Time
0x18001f4ec  mov     [rbp+57h+TimeFields.Year], ax
0x18001f4f0  call    cs:__imp_RtlTimeFieldsToTime
0x18001f4f6  test    al, al
0x18001f4f8  jnz     short loc_18001F501
0x18001f4fa  mov     ebx, 0C000000Dh
0x18001f4ff  jmp     short loc_18001F532
0x18001f501  test    r14d, r14d
0x18001f504  jz      short loc_18001F50F
0x18001f506  call    cs:__imp_RevertToSelf
0x18001f50c  mov     r14d, r13d
0x18001f50f  xor     edx, edx; NewSystemTime
0x18001f511  lea     rcx, [rbp+57h+Time]; SystemTime
0x18001f515  call    cs:__imp_NtSetSystemTime
0x18001f51b  mov     ebx, eax
0x18001f51d  test    eax, eax
0x18001f51f  jns     short loc_18001F532
0x18001f521  mov     r8d, eax
0x18001f524  lea     rdx, aNtsetsystemtim; "NtSetSystemTime failed with 0x%lx\n"
0x18001f52b  mov     ecx, edi
0x18001f52d  call    DsRolepLogPrintRoutine
0x18001f532  mov     ecx, ebx; Status
0x18001f534  call    cs:__imp_RtlNtStatusToDosError
0x18001f53a  mov     rcx, [rbp+57h+BufferPtr]; Buffer
0x18001f53e  mov     ebx, eax
0x18001f540  call    cs:__imp_NetApiBufferFree
0x18001f546  test    ebx, ebx
0x18001f548  jz      short loc_18001F574
0x18001f54a  jmp     short loc_18001F560
0x18001f54c  mov     r9d, eax
0x18001f54f  lea     rdx, aFailedToGetThe; "Failed to get the current time on %ws: "...
0x18001f556  mov     r8, rsi
0x18001f559  mov     ecx, edi
0x18001f55b  call    DsRolepLogPrintRoutine
0x18001f560  mov     r8d, ebx
0x18001f563  lea     rdx, aNonFatalErrorF; "NON-FATAL error forcing a time sync (%l"...
0x18001f56a  mov     ecx, edi
0x18001f56c  call    DsRolepLogPrintRoutine
0x18001f571  mov     ebx, r13d
0x18001f574  test    r14d, r14d
0x18001f577  jz      short loc_18001F57F
0x18001f579  call    cs:__imp_RevertToSelf
0x18001f57f  mov     eax, ebx
0x18001f581  mov     rcx, [rbp+57h+var_40]
0x18001f585  xor     rcx, rsp; StackCookie
0x18001f588  call    __security_check_cookie
0x18001f58d  mov     rbx, [rsp+0C0h+arg_10]
0x18001f595  add     rsp, 90h
0x18001f59c  pop     r15
0x18001f59e  pop     r14
0x18001f5a0  pop     r13
0x18001f5a2  pop     r12
0x18001f5a4  pop     rdi
0x18001f5a5  pop     rsi
0x18001f5a6  pop     rbp
0x18001f5a7  retn
```
