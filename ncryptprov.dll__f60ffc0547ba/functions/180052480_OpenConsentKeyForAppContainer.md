# OpenConsentKeyForAppContainer

- ea: `0x180052480`
- end: `0x1800526ef`
- name: `OpenConsentKeyForAppContainer`
- size: `623`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b340`
- `0x180014160`
- `0x180014558`
- `0x180014c60`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x18001235c`
- `0x18002529c`
- `0x180052480`
- `0x1800526f8`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18005260a`
- `ntdll!NtSetInformationThread` at `0x18005268c`
- `ntdll!NtSetInformationThread` at `0x18005260a`
- `ntdll!NtSetInformationThread` at `0x18005268c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800524d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800524d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800524bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800524bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052652`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052652`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800526c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800526c7`

## string_xrefs

- `0x18005259f`: `onecore\ds\security\cryptoapi\ncrypt\storage\appcontainer.c`
- `0x1800525da`: `onecore\ds\security\cryptoapi\ncrypt\storage\appcontainer.c`
- `0x1800526ab`: `onecore\ds\security\cryptoapi\ncrypt\storage\appcontainer.c`

## pseudocode

```c
__int64 __fastcall OpenConsentKeyForAppContainer(__int64 a1, __int64 a2, int a3)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int AppKeyAccessConsentRegKey; // ebx
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned int UserTextualSidW; // eax
  wchar_t *v11; // rax
  __int64 v12; // r14
  int v13; // r15d
  unsigned int v14; // eax
  unsigned int AppContainerSidAsString; // eax
  __int64 v16; // r9
  __int64 v18; // [rsp+28h] [rbp-18h]
  __int64 ThreadInformation; // [rsp+30h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+48h] BYREF

  v18 = 0;
  ThreadInformation = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    AppKeyAccessConsentRegKey = LastError;
    if ( LastError > 0 )
      AppKeyAccessConsentRegKey = (unsigned __int16)LastError | 0x80070000;
    v8 = 298;
    v9 = AppKeyAccessConsentRegKey;
    goto LABEL_27;
  }
  if ( (*(_BYTE *)(a2 + 428) & 0x20) == 0 && *(_DWORD *)(*(_QWORD *)(a2 + 416) + 4LL) )
  {
    AppKeyAccessConsentRegKey = -2146893792;
    v8 = 315;
    v9 = 2148073504LL;
LABEL_27:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c", v8);
    goto LABEL_28;
  }
  UserTextualSidW = GetUserTextualSidW(0, 0);
  AppKeyAccessConsentRegKey = UserTextualSidW;
  if ( UserTextualSidW )
  {
    v8 = 330;
LABEL_26:
    v9 = UserTextualSidW;
    goto LABEL_27;
  }
  v11 = (wchar_t *)SafeAllocaAllocateFromHeap(2);
  v12 = (__int64)v11;
  if ( !v11 )
  {
    AppKeyAccessConsentRegKey = -2146893810;
    v8 = 338;
    v9 = 2148073486LL;
    goto LABEL_27;
  }
  v13 = 0;
  v14 = GetUserTextualSidW(v11, 0);
  AppKeyAccessConsentRegKey = v14;
  if ( v14 )
  {
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c", 349);
  }
  else
  {
    AppContainerSidAsString = GetAppContainerSidAsString(TokenHandle);
    AppKeyAccessConsentRegKey = AppContainerSidAsString;
    if ( AppContainerSidAsString )
    {
      v16 = 363;
    }
    else
    {
      AppContainerSidAsString = NtSetInformationThread(
                                  (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                  ThreadImpersonationToken,
                                  &ThreadInformation,
                                  8u);
      AppKeyAccessConsentRegKey = AppContainerSidAsString;
      if ( !AppContainerSidAsString )
      {
        v13 = 1;
        AppKeyAccessConsentRegKey = OpenOrCreateAppKeyAccessConsentRegKey(v12, 0, *(_QWORD *)(a2 + 16), a3);
        goto LABEL_20;
      }
      v16 = 380;
    }
    DebugTraceError(
      AppContainerSidAsString,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c",
      v16);
  }
LABEL_20:
  MSCryptFree(v12);
  if ( v13 )
  {
    if ( !TokenHandle )
      return AppKeyAccessConsentRegKey;
    UserTextualSidW = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    if ( UserTextualSidW )
    {
      v8 = 429;
      if ( AppKeyAccessConsentRegKey )
        UserTextualSidW = AppKeyAccessConsentRegKey;
      AppKeyAccessConsentRegKey = UserTextualSidW;
      goto LABEL_26;
    }
  }
LABEL_28:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return AppKeyAccessConsentRegKey;
}

```

## disassembly

```asm
0x180052480  mov     [rsp-28h+arg_8], rbx
0x180052485  mov     [rsp-28h+arg_10], rsi
0x18005248a  mov     [rsp-28h+cchDest], rcx
0x18005248f  push    rbp
0x180052490  push    rdi
0x180052491  push    r12
0x180052493  push    r14
0x180052495  push    r15
0x180052497  mov     rbp, rsp
0x18005249a  sub     rsp, 40h
0x18005249e  xor     edi, edi
0x1800524a0  mov     [rbp+var_18], 0
0x1800524a8  mov     [rbp+var_20], rdi
0x1800524ac  mov     r12d, r8d
0x1800524af  mov     dword ptr [rbp+cchDest], edi
0x1800524b2  mov     rsi, rdx
0x1800524b5  mov     [rbp+ThreadInformation], rdi
0x1800524b9  mov     [rbp+TokenHandle], rdi
0x1800524bd  call    cs:__imp_GetCurrentThread
0x1800524c4  nop     dword ptr [rax+rax+00h]
0x1800524c9  mov     rcx, rax; ThreadHandle
0x1800524cc  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800524d0  lea     edx, [rdi+0Ch]; DesiredAccess
0x1800524d3  lea     r8d, [rdi+1]; OpenAsSelf
0x1800524d7  call    cs:__imp_OpenThreadToken
0x1800524de  nop     dword ptr [rax+rax+00h]
0x1800524e3  test    eax, eax
0x1800524e5  jnz     short loc_18005250F
0x1800524e7  call    cs:__imp_GetLastError
0x1800524ee  nop     dword ptr [rax+rax+00h]
0x1800524f3  mov     ebx, eax
0x1800524f5  test    eax, eax
0x1800524f7  jle     short loc_180052502
0x1800524f9  movzx   ebx, ax
0x1800524fc  or      ebx, 80070000h
0x180052502  mov     r9d, 12Ah
0x180052508  mov     ecx, ebx
0x18005250a  jmp     loc_1800526AB
0x18005250f  test    byte ptr [rsi+1ACh], 20h
0x180052516  jnz     short loc_180052539
0x180052518  mov     rax, [rsi+1A0h]
0x18005251f  cmp     [rax+4], edi
0x180052522  jz      short loc_180052539
0x180052524  mov     ebx, 80090020h
0x180052529  mov     r9d, 13Bh
0x18005252f  mov     ecx, 80090020h
0x180052534  jmp     loc_1800526AB
0x180052539  lea     r8, [rbp+cchDest]
0x18005253d  xor     edx, edx; cchDest
0x18005253f  xor     ecx, ecx; pszDest
0x180052541  call    GetUserTextualSidW
0x180052546  mov     ebx, eax
0x180052548  test    eax, eax
0x18005254a  jz      short loc_180052557
0x18005254c  mov     r9d, 14Ah
0x180052552  jmp     loc_1800526A9
0x180052557  mov     ebx, dword ptr [rbp+cchDest]
0x18005255a  lea     ecx, [rbx+1]
0x18005255d  add     rcx, rcx
0x180052560  call    SafeAllocaAllocateFromHeap
0x180052565  mov     r14, rax
0x180052568  test    rax, rax
0x18005256b  jnz     short loc_180052582
0x18005256d  mov     ebx, 8009000Eh
0x180052572  mov     r9d, 152h
0x180052578  mov     ecx, 8009000Eh
0x18005257d  jmp     loc_1800526AB
0x180052582  lea     r8, [rbp+cchDest]
0x180052586  mov     edx, ebx; cchDest
0x180052588  mov     rcx, r14; pszDest
0x18005258b  xor     r15d, r15d
0x18005258e  call    GetUserTextualSidW
0x180052593  mov     ebx, eax
0x180052595  test    eax, eax
0x180052597  jz      short loc_1800525B9
0x180052599  mov     r9d, 15Dh
0x18005259f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800525a6  lea     rdx, aStatus; "Status"
0x1800525ad  mov     ecx, eax
0x1800525af  call    DebugTraceError
0x1800525b4  jmp     loc_180052642
0x1800525b9  mov     rcx, [rbp+var_18]
0x1800525bd  lea     rdx, [rbp+var_20]
0x1800525c1  test    rcx, rcx
0x1800525c4  cmovz   rcx, [rbp+TokenHandle]; TokenHandle
0x1800525c9  call    GetAppContainerSidAsString
0x1800525ce  mov     ebx, eax
0x1800525d0  test    eax, eax
0x1800525d2  jz      short loc_1800525F5
0x1800525d4  mov     r9d, 16Bh
0x1800525da  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800525e1  mov     ecx, eax
0x1800525e3  lea     rdx, aStatus; "Status"
0x1800525ea  call    DebugTraceError
0x1800525ef  mov     rdi, [rbp+var_20]
0x1800525f3  jmp     short loc_180052642
0x1800525f5  mov     r9d, 8; ThreadInformationLength
0x1800525fb  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x1800525ff  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180052606  lea     edx, [r9-3]; ThreadInformationClass
0x18005260a  call    cs:__imp_NtSetInformationThread
0x180052611  nop     dword ptr [rax+rax+00h]
0x180052616  mov     ebx, eax
0x180052618  test    eax, eax
0x18005261a  jz      short loc_180052624
0x18005261c  mov     r9d, 17Ch
0x180052622  jmp     short loc_1800525DA
0x180052624  mov     rdi, [rbp+var_20]
0x180052628  mov     r9d, r12d
0x18005262b  mov     r8, [rsi+10h]
0x18005262f  mov     rdx, rdi
0x180052632  mov     rcx, r14
0x180052635  mov     r15d, 1
0x18005263b  call    OpenOrCreateAppKeyAccessConsentRegKey
0x180052640  mov     ebx, eax
0x180052642  mov     rcx, r14
0x180052645  call    MSCryptFree
0x18005264a  test    rdi, rdi
0x18005264d  jz      short loc_18005265E
0x18005264f  mov     rcx, rdi; hMem
0x180052652  call    cs:__imp_LocalFree
0x180052659  nop     dword ptr [rax+rax+00h]
0x18005265e  test    r15d, r15d
0x180052661  jz      short loc_1800526BE
0x180052663  cmp     [rbp+var_18], 0
0x180052668  jz      short loc_180052670
0x18005266a  lea     r8, [rbp+var_18]
0x18005266e  jmp     short loc_18005267B
0x180052670  cmp     [rbp+TokenHandle], 0
0x180052675  jz      short loc_1800526D3
0x180052677  lea     r8, [rbp+TokenHandle]; ThreadInformation
0x18005267b  mov     r9d, 8; ThreadInformationLength
0x180052681  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180052688  lea     edx, [r9-3]; ThreadInformationClass
0x18005268c  call    cs:__imp_NtSetInformationThread
0x180052693  nop     dword ptr [rax+rax+00h]
0x180052698  test    eax, eax
0x18005269a  jz      short loc_1800526BE
0x18005269c  test    ebx, ebx
0x18005269e  mov     r9d, 1ADh
0x1800526a4  cmovnz  eax, ebx
0x1800526a7  mov     ebx, eax
0x1800526a9  mov     ecx, eax
0x1800526ab  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800526b2  lea     rdx, aStatus; "Status"
0x1800526b9  call    DebugTraceError
0x1800526be  mov     rcx, [rbp+TokenHandle]; hObject
0x1800526c2  test    rcx, rcx
0x1800526c5  jz      short loc_1800526D3
0x1800526c7  call    cs:__imp_CloseHandle
0x1800526ce  nop     dword ptr [rax+rax+00h]
0x1800526d3  lea     r11, [rsp+40h+var_s0]
0x1800526d8  mov     eax, ebx
0x1800526da  mov     rbx, [r11+38h]
0x1800526de  mov     rsi, [r11+40h]
0x1800526e2  mov     rsp, r11
0x1800526e5  pop     r15
0x1800526e7  pop     r14
0x1800526e9  pop     r12
0x1800526eb  pop     rdi
0x1800526ec  pop     rbp
0x1800526ed  retn
```
