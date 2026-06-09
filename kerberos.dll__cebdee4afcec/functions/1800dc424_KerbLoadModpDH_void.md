# KerbLoadModpDH(void)

- ea: `0x1800dc424`
- end: `0x1800dc5d9`
- name: `?KerbLoadModpDH@@YAHXZ`
- size: `437`
- prototype: `int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800dc3a8`

## callees

- `0x180034c58`
- `0x18006ccec`
- `0x18006d73c`
- `0x1800dc11c`
- `0x1800dc424`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc542`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc50c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc5c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc5c1`
- `ntdll!NtOpenThreadToken` at `0x1800dc46e`
- `ntdll!NtOpenThreadToken` at `0x1800dc46e`
- `ntdll!RtlInitializeCriticalSection` at `0x1800dc551`
- `ntdll!RtlInitializeCriticalSection` at `0x1800dc551`
- `ntdll!NtSetInformationThread` at `0x1800dc4ba`
- `ntdll!NtSetInformationThread` at `0x1800dc5b6`
- `ntdll!NtSetInformationThread` at `0x1800dc4ba`
- `ntdll!NtSetInformationThread` at `0x1800dc5b6`
- `CRYPTSP!CryptAcquireContextW` at `0x1800dc4e2`
- `CRYPTSP!CryptAcquireContextW` at `0x1800dc4e2`

## pseudocode

```c
__int64 KerbLoadModpDH(void)
{
  BOOL v1; // edi
  NTSTATUS v2; // ecx
  void *v3; // rax
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF
  __int64 ThreadInformation; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  ThreadInformation = 0;
  if ( KerbGlobalWellknownDomainParamtersLockInitialized )
    return 1;
  v1 = 0;
  v2 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -1073741700 )
  {
    if ( v2 == -1073741700 )
    {
      v3 = 0;
      TokenHandle = 0;
    }
    else
    {
      v3 = TokenHandle;
    }
    if ( !v3
      || NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) >= 0 )
    {
      if ( !CryptAcquireContextW(&KerbGlobalCSPProvider, 0, 0, 0xDu, 0xF0000040) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4256176c45563d9365687fae28cf9cb4_Traceguids, LastError);
        }
        goto LABEL_21;
      }
      if ( KerbGetGlobalEphemeralDHAlg() )
      {
        if ( RtlInitializeCriticalSection(&KerbGlobalWellknownDomainParamtersLock) >= 0 )
        {
          KerbGlobalWellknownDomainParamtersLockInitialized = 1;
          v1 = KerbInitDHWellknowDomainParametersDefaults() != 0;
          goto LABEL_21;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4256176c45563d9365687fae28cf9cb4_Traceguids);
      }
      SetLastError(0x5AAu);
    }
  }
LABEL_21:
  if ( TokenHandle )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    CloseHandle(TokenHandle);
  }
  return v1;
}

```

## disassembly

```asm
0x1800dc424  mov     rax, rsp
0x1800dc427  mov     [rax+18h], rbx
0x1800dc42b  mov     [rax+20h], rbp
0x1800dc42f  push    rdi
0x1800dc430  sub     rsp, 30h
0x1800dc434  cmp     cs:?KerbGlobalWellknownDomainParamtersLockInitialized@@3HA, 0; int KerbGlobalWellknownDomainParamtersLockInitialized
0x1800dc43b  mov     qword ptr [rax+8], 0
0x1800dc443  mov     qword ptr [rax+10h], 0
0x1800dc44b  jz      short loc_1800DC457
0x1800dc44d  mov     eax, 1
0x1800dc452  jmp     loc_1800DC5C9
0x1800dc457  xor     edi, edi
0x1800dc459  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800dc45e  lea     ebx, [rdi+1]
0x1800dc461  lea     rbp, [rdi-2]
0x1800dc465  mov     r8b, bl; OpenAsSelf
0x1800dc468  mov     rcx, rbp; ThreadHandle
0x1800dc46b  lea     edx, [rdi+0Ch]; DesiredAccess
0x1800dc46e  call    cs:__imp_NtOpenThreadToken
0x1800dc474  mov     edx, 80000000h
0x1800dc479  mov     r8d, 0C000007Ch
0x1800dc47f  mov     ecx, eax
0x1800dc481  add     eax, edx
0x1800dc483  test    edx, eax
0x1800dc485  jnz     short loc_1800DC490
0x1800dc487  cmp     ecx, r8d
0x1800dc48a  jnz     loc_1800DC59C
0x1800dc490  cmp     ecx, r8d
0x1800dc493  jnz     short loc_1800DC49E
0x1800dc495  xor     eax, eax
0x1800dc497  mov     [rsp+38h+TokenHandle], rax
0x1800dc49c  jmp     short loc_1800DC4A3
0x1800dc49e  mov     rax, [rsp+38h+TokenHandle]
0x1800dc4a3  test    rax, rax
0x1800dc4a6  jz      short loc_1800DC4C8
0x1800dc4a8  mov     r9d, 8; ThreadInformationLength
0x1800dc4ae  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800dc4b3  mov     rcx, rbp; ThreadHandle
0x1800dc4b6  lea     edx, [r9-3]; ThreadInformationClass
0x1800dc4ba  call    cs:__imp_NtSetInformationThread
0x1800dc4c0  test    eax, eax
0x1800dc4c2  js      loc_1800DC59C
0x1800dc4c8  mov     r9d, 0Dh; dwProvType
0x1800dc4ce  mov     [rsp+38h+dwFlags], 0F0000040h; dwFlags
0x1800dc4d6  xor     r8d, r8d; szProvider
0x1800dc4d9  lea     rcx, ?KerbGlobalCSPProvider@@3_KA; phProv
0x1800dc4e0  xor     edx, edx; szContainer
0x1800dc4e2  call    cs:__imp_CryptAcquireContextW
0x1800dc4e8  test    eax, eax
0x1800dc4ea  jnz     short loc_1800DC533
0x1800dc4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc4f3  lea     rax, WPP_GLOBAL_Control
0x1800dc4fa  cmp     rcx, rax
0x1800dc4fd  jz      loc_1800DC59C
0x1800dc503  test    [rcx+1Ch], bl
0x1800dc506  jz      loc_1800DC59C
0x1800dc50c  call    cs:__imp_GetLastError
0x1800dc512  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc519  lea     r8, WPP_4256176c45563d9365687fae28cf9cb4_Traceguids
0x1800dc520  mov     edx, 0Ah
0x1800dc525  mov     r9d, eax
0x1800dc528  mov     rcx, [rcx+10h]
0x1800dc52c  call    WPP_SF_D
0x1800dc531  jmp     short loc_1800DC59C
0x1800dc533  call    ?KerbGetGlobalEphemeralDHAlg@@YAPEAUKERB_ALGORITHM_IDENTIFIER@@XZ; KerbGetGlobalEphemeralDHAlg(void)
0x1800dc538  test    rax, rax
0x1800dc53b  jnz     short loc_1800DC54A
0x1800dc53d  mov     ecx, 5AAh; dwErrCode
0x1800dc542  call    cs:__imp_SetLastError
0x1800dc548  jmp     short loc_1800DC59C
0x1800dc54a  lea     rcx, ?KerbGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800dc551  call    cs:__imp_RtlInitializeCriticalSection
0x1800dc557  test    eax, eax
0x1800dc559  jns     short loc_1800DC58A
0x1800dc55b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc562  lea     rax, WPP_GLOBAL_Control
0x1800dc569  cmp     rcx, rax
0x1800dc56c  jz      short loc_1800DC53D
0x1800dc56e  test    [rcx+1Ch], bl
0x1800dc571  jz      short loc_1800DC53D
0x1800dc573  mov     rcx, [rcx+10h]
0x1800dc577  lea     r8, WPP_4256176c45563d9365687fae28cf9cb4_Traceguids
0x1800dc57e  mov     edx, 0Bh
0x1800dc583  call    WPP_SF_
0x1800dc588  jmp     short loc_1800DC53D
0x1800dc58a  mov     cs:?KerbGlobalWellknownDomainParamtersLockInitialized@@3HA, ebx; int KerbGlobalWellknownDomainParamtersLockInitialized
0x1800dc590  call    ?KerbInitDHWellknowDomainParametersDefaults@@YAHXZ; KerbInitDHWellknowDomainParametersDefaults(void)
0x1800dc595  test    eax, eax
0x1800dc597  mov     edi, eax
0x1800dc599  cmovnz  edi, ebx
0x1800dc59c  cmp     [rsp+38h+TokenHandle], 0
0x1800dc5a2  jz      short loc_1800DC5C7
0x1800dc5a4  mov     r9d, 8; ThreadInformationLength
0x1800dc5aa  lea     r8, [rsp+38h+TokenHandle]; ThreadInformation
0x1800dc5af  mov     rcx, rbp; ThreadHandle
0x1800dc5b2  lea     edx, [r9-3]; ThreadInformationClass
0x1800dc5b6  call    cs:__imp_NtSetInformationThread
0x1800dc5bc  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800dc5c1  call    cs:__imp_CloseHandle
0x1800dc5c7  mov     eax, edi
0x1800dc5c9  mov     rbx, [rsp+38h+arg_10]
0x1800dc5ce  mov     rbp, [rsp+38h+arg_18]
0x1800dc5d3  add     rsp, 30h
0x1800dc5d7  pop     rdi
0x1800dc5d8  retn
```
