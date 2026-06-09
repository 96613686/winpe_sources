# EdpCredSvcQuerySessionUserSid(ulong,ushort * *)

- ea: `0x1800853a4`
- end: `0x18008560d`
- name: `?EdpCredSvcQuerySessionUserSid@@YAJKPEAPEAG@Z`
- size: `617`
- prototype: `__int64 __fastcall(ULONG SessionId, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180084508`
- `0x1800857a8`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800853a4`
- `0x180085614`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800854db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800854db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800854ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800855e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800854ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800855e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800855f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800855f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008549f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008549f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800855d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800855d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800855c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800855c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008548a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008551c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008548a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008551c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008554f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008554f`

## pseudocode

```c
__int64 __fastcall EdpCredSvcQuerySessionUserSid(ULONG SessionId, unsigned __int16 **a2)
{
  PSID *v2; // rbx
  HANDLE v3; // rsi
  unsigned int v6; // edi
  int v7; // eax
  __int64 v8; // rcx
  signed int v9; // eax
  int v10; // r8d
  DWORD v11; // ebx
  HANDLE ProcessHeap; // rax
  signed int v13; // eax
  signed int LastError; // eax
  HANDLE v15; // rax
  char ReturnLength; // [rsp+20h] [rbp-30h]
  HANDLE TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+88h] [rbp+38h] BYREF
  DWORD v20; // [rsp+90h] [rbp+40h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  v3 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  v20 = 0;
  StringSid = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    ReturnLength = 102;
    v10 = -2147467261;
    goto LABEL_25;
  }
  *a2 = 0;
  fnEfsLogTrace1Strings(SessionId, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 108);
  v6 = EdpCredSvcQuerySessionUserToken(SessionId, &TokenHandle);
  v7 = fnEfsLogTrace1String1Dword(
         g_hPublisher,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
         (unsigned int)&sourceString,
         v6,
         38,
         108);
  v3 = TokenHandle;
  if ( v7 < 0 )
    goto LABEL_26;
  if ( TokenHandle )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
    {
      v11 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v2 = (PSID *)HeapAlloc(ProcessHeap, 8u, v11);
      if ( !v2 )
      {
        v6 = -2147024882;
        ReturnLength = -116;
        v10 = -2147024882;
        goto LABEL_25;
      }
      if ( GetTokenInformation(v3, TokenUser, v2, TokenInformationLength, &v20) )
      {
        if ( ConvertSidToStringSidW(*v2, &StringSid) )
        {
          *a2 = StringSid;
          StringSid = 0;
          goto LABEL_26;
        }
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        ReturnLength = -99;
      }
      else
      {
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
        ReturnLength = -108;
      }
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      ReturnLength = -122;
    }
    v10 = v6;
LABEL_25:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v10, 38, ReturnLength);
    goto LABEL_26;
  }
  if ( v6 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
  v6 = 1;
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 38, 118);
LABEL_26:
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( v3 )
    CloseHandle(v3);
  if ( v2 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v2);
  }
  return v6;
}

```

## disassembly

```asm
0x1800853a4  mov     [rsp-28h+arg_0], rbx
0x1800853a9  push    rbp
0x1800853aa  push    rsi
0x1800853ab  push    rdi
0x1800853ac  push    r12
0x1800853ae  push    r15
0x1800853b0  mov     rbp, rsp
0x1800853b3  sub     rsp, 50h
0x1800853b7  xor     ebx, ebx
0x1800853b9  xor     esi, esi
0x1800853bb  mov     [rbp+TokenHandle], rsi
0x1800853bf  mov     r12, rdx
0x1800853c2  mov     [rbp+TokenInformationLength], ebx
0x1800853c5  mov     edi, ecx
0x1800853c7  mov     [rbp+arg_10], ebx
0x1800853ca  mov     [rbp+StringSid], rbx
0x1800853ce  test    rdx, rdx
0x1800853d1  jz      loc_18008558D
0x1800853d7  xor     eax, eax
0x1800853d9  lea     r15d, [rbx+26h]
0x1800853dd  mov     [rdx], rax
0x1800853e0  lea     r8, sourceString
0x1800853e7  mov     esi, 96Ch
0x1800853ec  lea     rdx, EFS_TRACE_START_EVENT
0x1800853f3  mov     r9d, r15d
0x1800853f6  mov     dword ptr [rsp+50h+ReturnLength], esi
0x1800853fa  call    fnEfsLogTrace1Strings
0x1800853ff  lea     rdx, [rbp+TokenHandle]; void **
0x180085403  mov     ecx, edi; SessionId
0x180085405  call    ?EdpCredSvcQuerySessionUserToken@@YAJKPEAPEAX@Z; EdpCredSvcQuerySessionUserToken(ulong,void * *)
0x18008540a  mov     rcx, cs:g_hPublisher
0x180085411  lea     r9, sourceString
0x180085418  mov     [rsp+50h+var_20], esi
0x18008541c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180085423  mov     [rsp+50h+var_28], r15d
0x180085428  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008542f  mov     dword ptr [rsp+50h+ReturnLength], eax
0x180085433  mov     edi, eax
0x180085435  call    fnEfsLogTrace1String1Dword
0x18008543a  mov     rsi, [rbp+TokenHandle]
0x18008543e  test    eax, eax
0x180085440  js      loc_1800855B9
0x180085446  test    rsi, rsi
0x180085449  jnz     short loc_180085474
0x18008544b  cmp     edi, 1
0x18008544e  jz      short loc_180085455
0x180085450  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hr == S_FALSE")
0x180085455  mov     edi, 1
0x18008545a  mov     dword ptr [rsp+50h+ReturnLength], 976h
0x180085462  mov     r8d, edi
0x180085465  lea     rdx, EFS_TRACE_STATUS
0x18008546c  mov     r9d, r15d
0x18008546f  jmp     loc_1800855AD
0x180085474  xor     r9d, r9d; TokenInformationLength
0x180085477  lea     rax, [rbp+TokenInformationLength]
0x18008547b  xor     r8d, r8d; TokenInformation
0x18008547e  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180085483  mov     rcx, rsi; TokenHandle
0x180085486  lea     edx, [r9+1]; TokenInformationClass
0x18008548a  call    cs:__imp_GetTokenInformation
0x180085490  test    eax, eax
0x180085492  jnz     short loc_1800854C7
0x180085494  call    cs:__imp_GetLastError
0x18008549a  cmp     eax, 7Ah ; 'z'
0x18008549d  jz      short loc_1800854C7
0x18008549f  call    cs:__imp_GetLastError
0x1800854a5  mov     edi, eax
0x1800854a7  test    eax, eax
0x1800854a9  jle     short loc_1800854B4
0x1800854ab  movzx   edi, ax
0x1800854ae  or      edi, 80070000h
0x1800854b4  mov     dword ptr [rsp+50h+ReturnLength], 986h
0x1800854bc  mov     r9d, r15d
0x1800854bf  mov     r8d, edi
0x1800854c2  jmp     loc_1800855A6
0x1800854c7  mov     ebx, [rbp+TokenInformationLength]
0x1800854ca  call    cs:__imp_GetProcessHeap
0x1800854d0  mov     r8d, ebx; dwBytes
0x1800854d3  mov     edx, 8; dwFlags
0x1800854d8  mov     rcx, rax; hHeap
0x1800854db  call    cs:__imp_HeapAlloc
0x1800854e1  mov     rbx, rax
0x1800854e4  test    rax, rax
0x1800854e7  jnz     short loc_180085504
0x1800854e9  mov     edi, 8007000Eh
0x1800854ee  mov     dword ptr [rsp+50h+ReturnLength], 98Ch
0x1800854f6  mov     r9d, r15d
0x1800854f9  mov     r8d, 8007000Eh
0x1800854ff  jmp     loc_1800855A6
0x180085504  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180085508  lea     rax, [rbp+arg_10]
0x18008550c  mov     r8, rbx; TokenInformation
0x18008550f  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180085514  mov     edx, 1; TokenInformationClass
0x180085519  mov     rcx, rsi; TokenHandle
0x18008551c  call    cs:__imp_GetTokenInformation
0x180085522  test    eax, eax
0x180085524  jnz     short loc_180085548
0x180085526  call    cs:__imp_GetLastError
0x18008552c  mov     edi, eax
0x18008552e  test    eax, eax
0x180085530  jle     short loc_18008553B
0x180085532  movzx   edi, ax
0x180085535  or      edi, 80070000h
0x18008553b  mov     dword ptr [rsp+50h+ReturnLength], 994h
0x180085543  jmp     loc_1800854BC
0x180085548  mov     rcx, [rbx]; Sid
0x18008554b  lea     rdx, [rbp+StringSid]; StringSid
0x18008554f  call    cs:__imp_ConvertSidToStringSidW
0x180085555  test    eax, eax
0x180085557  jnz     short loc_18008557B
0x180085559  call    cs:__imp_GetLastError
0x18008555f  mov     edi, eax
0x180085561  test    eax, eax
0x180085563  jle     short loc_18008556E
0x180085565  movzx   edi, ax
0x180085568  or      edi, 80070000h
0x18008556e  mov     dword ptr [rsp+50h+ReturnLength], 99Dh
0x180085576  jmp     loc_1800854BC
0x18008557b  mov     rax, [rbp+StringSid]
0x18008557f  mov     [r12], rax
0x180085583  mov     [rbp+StringSid], 0
0x18008558b  jmp     short loc_1800855B9
0x18008558d  mov     edi, 80004003h
0x180085592  mov     dword ptr [rsp+50h+ReturnLength], 966h
0x18008559a  mov     r9d, 26h ; '&'
0x1800855a0  mov     r8d, 80004003h
0x1800855a6  lea     rdx, EFS_TRACE_ERROR
0x1800855ad  mov     rcx, cs:g_hPublisher
0x1800855b4  call    fnEfsLogTrace1
0x1800855b9  mov     rcx, [rbp+StringSid]; hMem
0x1800855bd  test    rcx, rcx
0x1800855c0  jz      short loc_1800855D0
0x1800855c2  call    cs:__imp_LocalFree
0x1800855c8  mov     [rbp+StringSid], 0
0x1800855d0  test    rsi, rsi
0x1800855d3  jz      short loc_1800855DE
0x1800855d5  mov     rcx, rsi; hObject
0x1800855d8  call    cs:__imp_CloseHandle
0x1800855de  test    rbx, rbx
0x1800855e1  jz      short loc_1800855F7
0x1800855e3  call    cs:__imp_GetProcessHeap
0x1800855e9  mov     r8, rbx; lpMem
0x1800855ec  xor     edx, edx; dwFlags
0x1800855ee  mov     rcx, rax; hHeap
0x1800855f1  call    cs:__imp_HeapFree
0x1800855f7  mov     rbx, [rsp+50h+arg_0]
0x1800855ff  mov     eax, edi
0x180085601  add     rsp, 50h
0x180085605  pop     r15
0x180085607  pop     r12
0x180085609  pop     rdi
0x18008560a  pop     rsi
0x18008560b  pop     rbp
0x18008560c  retn
```
