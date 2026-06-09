# AdvertisingIdHelpers::GetAppcontainerSidFromProcessHandle(void *,ushort *,ulong)

- ea: `0x180003350`
- end: `0x180003588`
- name: `?GetAppcontainerSidFromProcessHandle@AdvertisingIdHelpers@@YAJPEAXPEAGK@Z`
- size: `568`
- prototype: `__int64 __fastcall(AdvertisingIdHelpers *__hidden this, void *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001920`

## callees

- `0x180003350`
- `0x180005d90`
- `0x180006324`
- `0x180009dd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003393`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003393`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800033bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800033bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003451`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000355c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003451`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000355c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003571`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800033e8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800033e8`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::GetAppcontainerSidFromProcessHandle(
        AdvertisingIdHelpers *this,
        _WORD *a2,
        unsigned __int16 *a3)
{
  _WORD *v3; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int v8; // r8d
  const char *v9; // r9
  LPWSTR v10; // r9
  __int64 v11; // rax
  LPWSTR v12; // rdx
  __int64 v13; // r8
  _WORD *v14; // rcx
  unsigned int v15; // edi
  unsigned int LastError; // ebx
  unsigned int v18; // ebx
  int ReturnLength; // [rsp+20h] [rbp-98h]
  LPWSTR StringSid; // [rsp+30h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  DWORD TokenInformationLength[4]; // [rsp+40h] [rbp-78h] BYREF
  PSID TokenInformation[10]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  TokenInformationLength[0] = 76;
  *a2 = 0;
  v3 = a2;
  TokenHandle = 0;
  StringSid = 0;
  if ( !OpenProcessToken(this, 8u, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xE2, v4, v5);
LABEL_22:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastError;
  }
  if ( !GetTokenInformation(
          TokenHandle,
          TokenAppContainerSid,
          TokenInformation,
          TokenInformationLength[0],
          TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xE8, v6, v7);
    goto LABEL_22;
  }
  if ( !TokenInformation[0] )
  {
    v10 = StringSid;
LABEL_12:
    if ( v10 )
      LocalFree(v10);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return 0;
  }
  if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
  {
    v10 = StringSid;
    v11 = 2147483646;
    v12 = StringSid;
    v13 = 128;
    do
    {
      if ( !v11 )
        break;
      if ( !*v12 )
        break;
      *v3++ = *v12++;
      --v11;
      --v13;
    }
    while ( v13 );
    v14 = v3 - 1;
    v15 = -2147024774;
    if ( v13 )
    {
      v14 = v3;
      v15 = 0;
    }
    *v14 = 0;
    if ( v13 )
      goto LABEL_12;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)v15,
      ReturnLength);
    if ( StringSid )
      LocalFree(StringSid);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v15;
  }
  else
  {
    v18 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xF0, v8, v9);
    if ( StringSid )
      LocalFree(StringSid);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v18;
  }
}

```

## disassembly

```asm
0x180003350  mov     [rsp+arg_18], rbx
0x180003355  push    rsi
0x180003356  sub     rsp, 0B0h
0x18000335d  mov     rax, cs:__security_cookie
0x180003364  xor     rax, rsp
0x180003367  mov     [rsp+0B8h+var_18], rax
0x18000336f  xor     esi, esi
0x180003371  mov     [rsp+0B8h+TokenInformationLength], 4Ch ; 'L'
0x180003379  mov     [rdx], si
0x18000337c  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x180003381  mov     rbx, rdx
0x180003384  mov     [rsp+0B8h+TokenHandle], rsi
0x180003389  mov     edx, 8; DesiredAccess
0x18000338e  mov     [rsp+0B8h+StringSid], rsi
0x180003393  call    cs:__imp_OpenProcessToken
0x180003399  test    eax, eax
0x18000339b  jz      loc_1800034FE
0x1800033a1  mov     r9d, [rsp+0B8h+TokenInformationLength]; TokenInformationLength
0x1800033a6  lea     rax, [rsp+0B8h+TokenInformationLength]
0x1800033ab  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800033b0  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800033b5  mov     edx, 1Fh; TokenInformationClass
0x1800033ba  mov     qword ptr [rsp+0B8h+ReturnLength], rax; int
0x1800033bf  call    cs:__imp_GetTokenInformation
0x1800033c5  test    eax, eax
0x1800033c7  jz      loc_18000351E
0x1800033cd  mov     rcx, [rsp+0B8h+TokenInformation]; Sid
0x1800033d2  mov     [rsp+0B8h+arg_10], rdi
0x1800033da  test    rcx, rcx
0x1800033dd  jz      loc_18000357E
0x1800033e3  lea     rdx, [rsp+0B8h+StringSid]; StringSid
0x1800033e8  call    cs:__imp_ConvertSidToStringSidW
0x1800033ee  test    eax, eax
0x1800033f0  jz      loc_18000353E
0x1800033f6  mov     r9, [rsp+0B8h+StringSid]
0x1800033fb  mov     eax, 7FFFFFFEh
0x180003400  mov     rdx, r9
0x180003403  mov     r8d, 80h
0x180003409  nop     dword ptr [rax+00000000h]
0x180003410  test    rax, rax
0x180003413  jz      short loc_180003431
0x180003415  movzx   ecx, word ptr [rdx]
0x180003418  test    cx, cx
0x18000341b  jz      short loc_180003431
0x18000341d  mov     [rbx], cx
0x180003420  add     rdx, 2
0x180003424  add     rbx, 2
0x180003428  dec     rax
0x18000342b  sub     r8, 1
0x18000342f  jnz     short loc_180003410
0x180003431  test    r8, r8
0x180003434  lea     rcx, [rbx-2]
0x180003438  mov     edi, 8007007Ah
0x18000343d  cmovnz  rcx, rbx
0x180003441  cmovnz  edi, esi
0x180003444  mov     [rcx], si
0x180003447  jz      short loc_180003497
0x180003449  test    r9, r9
0x18000344c  jz      short loc_180003457
0x18000344e  mov     rcx, r9; hMem
0x180003451  call    cs:__imp_LocalFree
0x180003457  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18000345c  lea     rax, [rcx-1]
0x180003460  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003464  ja      short loc_18000346C
0x180003466  call    cs:__imp_CloseHandle
0x18000346c  xor     eax, eax
0x18000346e  mov     rdi, [rsp+0B8h+arg_10]
0x180003476  mov     rcx, [rsp+0B8h+var_18]
0x18000347e  xor     rcx, rsp; StackCookie
0x180003481  call    __security_check_cookie
0x180003486  mov     rbx, [rsp+0B8h+arg_18]
0x18000348e  add     rsp, 0B0h
0x180003495  pop     rsi
0x180003496  retn
0x180003497  mov     rcx, [rsp+0B8h]; this
0x18000349f  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800034a6  mov     r9d, edi; char *
0x1800034a9  mov     edx, 0F5h; void *
0x1800034ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800034b3  mov     rcx, [rsp+0B8h+StringSid]; hMem
0x1800034b8  test    rcx, rcx
0x1800034bb  jz      short loc_1800034C3
0x1800034bd  call    cs:__imp_LocalFree
0x1800034c3  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x1800034c8  lea     rdx, [rcx-1]
0x1800034cc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800034d0  ja      short loc_1800034D8
0x1800034d2  call    cs:__imp_CloseHandle
0x1800034d8  mov     eax, edi
0x1800034da  jmp     short loc_18000346E
0x1800034dc  call    cs:__imp_LocalFree
0x1800034e2  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x1800034e7  lea     rdx, [rcx-1]
0x1800034eb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800034ef  ja      short loc_1800034F7
0x1800034f1  call    cs:__imp_CloseHandle
0x1800034f7  mov     eax, ebx
0x1800034f9  jmp     loc_180003476
0x1800034fe  mov     rcx, [rsp+0B8h]; this
0x180003506  mov     edx, 0E2h; void *
0x18000350b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003510  mov     rcx, [rsp+0B8h+StringSid]; hMem
0x180003515  mov     ebx, eax
0x180003517  test    rcx, rcx
0x18000351a  jz      short loc_1800034E2
0x18000351c  jmp     short loc_1800034DC
0x18000351e  mov     rcx, [rsp+0B8h]; this
0x180003526  mov     edx, 0E8h; void *
0x18000352b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003530  mov     rcx, [rsp+0B8h+StringSid]
0x180003535  mov     ebx, eax
0x180003537  test    rcx, rcx
0x18000353a  jz      short loc_1800034E2
0x18000353c  jmp     short loc_1800034DC
0x18000353e  mov     rcx, [rsp+0B8h]; this
0x180003546  mov     edx, 0F0h; void *
0x18000354b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003550  mov     rcx, [rsp+0B8h+StringSid]; hMem
0x180003555  mov     ebx, eax
0x180003557  test    rcx, rcx
0x18000355a  jz      short loc_180003562
0x18000355c  call    cs:__imp_LocalFree
0x180003562  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180003567  lea     rdx, [rcx-1]
0x18000356b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000356f  ja      short loc_180003577
0x180003571  call    cs:__imp_CloseHandle
0x180003577  mov     eax, ebx
0x180003579  jmp     loc_18000346E
0x18000357e  mov     r9, [rsp+0B8h+StringSid]
0x180003583  jmp     loc_180003449
```
