# KspFindNextKeyFile

- ea: `0x180052f84`
- end: `0x18005318a`
- name: `KspFindNextKeyFile`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180053500`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x180011548`
- `0x180038970`
- `0x180051e8c`
- `0x18005283c`
- `0x180052f84`
- `0x1800532a4`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005314d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005314d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180053061`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180053061`

## string_xrefs

- `0x18005301f`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x1800530c3`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`
- `0x180053116`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`

## pseudocode

```c
__int64 __fastcall KspFindNextKeyFile(
        __int64 a1,
        void *a2,
        _WORD *a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6,
        _QWORD *a7)
{
  _QWORD *v7; // rbx
  __int64 v9; // rdi
  void *v10; // rsi
  void *v11; // r15
  unsigned int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdi
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // r14d
  void *v20; // [rsp+20h] [rbp-E0h] BYREF
  void *v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h]
  HANDLE hFindFile; // [rsp+48h] [rbp-B8h]
  _WORD *v26; // [rsp+50h] [rbp-B0h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF

  v7 = a7;
  v26 = a3;
  hFindFile = a2;
  v24 = a1;
  v23 = (__int64)a7;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  if ( a5 )
  {
    v12 = ChangeThreadILToMedium(&v20, &v21);
    v13 = v12;
    if ( v12 )
    {
      DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1770);
      v10 = v20;
      v11 = v21;
LABEL_17:
      v17 = RevertBackToCallerToken((__int64)v10);
      v18 = v17;
      if ( v17 )
      {
        DebugTraceError(v17, "RevertStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1840);
        if ( !v13 )
          v13 = v18;
      }
      goto LABEL_20;
    }
    v10 = v20;
    v11 = v21;
    v7 = (_QWORD *)v23;
  }
  v14 = v24;
  while ( 1 )
  {
    do
    {
      if ( !FindNextFileW(hFindFile, &FindFileData) && GetLastError() == 18 )
      {
        v9 = v22;
        v13 = -2146893782;
        goto LABEL_16;
      }
      if ( a4 )
        v15 = 0;
      else
        v15 = *(unsigned int *)(v14 + 48);
    }
    while ( !(unsigned int)IsValidKeyFileName(&FindFileData, v15, a5) );
    v16 = ReadKeyNameFromFile(v26, FindFileData.cFileName, a4, &v22);
    if ( !v16 )
      break;
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", 1812);
  }
  ++*a6;
  v9 = 0;
  *v7 = v22;
  v13 = 0;
LABEL_16:
  if ( a5 )
    goto LABEL_17;
LABEL_20:
  if ( v11 )
    CloseHandle(v11);
  if ( v10 )
    CloseHandle(v10);
  if ( v9 )
    MSCryptFree(v9);
  return v13;
}

```

## disassembly

```asm
0x180052f84  push    rbp
0x180052f86  push    rbx
0x180052f87  push    rsi
0x180052f88  push    rdi
0x180052f89  push    r13
0x180052f8b  push    r14
0x180052f8d  push    r15
0x180052f8f  lea     rbp, [rsp-1C0h]
0x180052f97  sub     rsp, 2C0h
0x180052f9e  mov     rax, cs:__security_cookie
0x180052fa5  xor     rax, rsp
0x180052fa8  mov     [rbp+1F0h+var_40], rax
0x180052faf  mov     rbx, [rbp+1F0h+arg_30]
0x180052fb6  mov     r13d, r9d
0x180052fb9  mov     r14, [rbp+1F0h+arg_28]
0x180052fc0  mov     [rsp+2F0h+var_2A0], r8
0x180052fc5  mov     r8d, 250h; Size
0x180052fcb  mov     [rsp+2F0h+hFindFile], rdx
0x180052fd0  xor     edx, edx; Val
0x180052fd2  mov     [rsp+2F0h+var_2B0], rcx
0x180052fd7  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x180052fdc  mov     [rsp+2F0h+var_2B8], rbx
0x180052fe1  call    memset_0
0x180052fe6  xor     edi, edi
0x180052fe8  xor     esi, esi
0x180052fea  xor     r15d, r15d
0x180052fed  mov     [rsp+2F0h+var_2C0], rdi
0x180052ff2  mov     [rsp+2F0h+var_2D0], rsi
0x180052ff7  mov     [rsp+2F0h+var_2C8], r15
0x180052ffc  cmp     [rbp+1F0h+arg_20], esi
0x180053002  jz      short loc_180053052
0x180053004  lea     rdx, [rsp+2F0h+var_2C8]
0x180053009  lea     rcx, [rsp+2F0h+var_2D0]
0x18005300e  call    ChangeThreadILToMedium
0x180053013  mov     ebx, eax
0x180053015  test    eax, eax
0x180053017  jz      short loc_180053043
0x180053019  mov     r9d, 6EAh
0x18005301f  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180053026  lea     rdx, aStatus; "Status"
0x18005302d  mov     ecx, eax
0x18005302f  call    DebugTraceError
0x180053034  mov     rsi, [rsp+2F0h+var_2D0]
0x180053039  mov     r15, [rsp+2F0h+var_2C8]
0x18005303e  jmp     loc_180053101
0x180053043  mov     rsi, [rsp+2F0h+var_2D0]
0x180053048  mov     r15, [rsp+2F0h+var_2C8]
0x18005304d  mov     rbx, [rsp+2F0h+var_2B8]
0x180053052  mov     rdi, [rsp+2F0h+var_2B0]
0x180053057  mov     rcx, [rsp+2F0h+hFindFile]; hFindFile
0x18005305c  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180053061  call    cs:__imp_FindNextFileW
0x180053068  nop     dword ptr [rax+rax+00h]
0x18005306d  test    eax, eax
0x18005306f  jnz     short loc_180053082
0x180053071  call    cs:__imp_GetLastError
0x180053078  nop     dword ptr [rax+rax+00h]
0x18005307d  cmp     eax, 12h
0x180053080  jz      short loc_1800530DD
0x180053082  test    r13d, r13d
0x180053085  jz      short loc_18005308B
0x180053087  xor     edx, edx
0x180053089  jmp     short loc_18005308E
0x18005308b  mov     edx, [rdi+30h]
0x18005308e  mov     r8d, [rbp+1F0h+arg_20]
0x180053095  lea     rcx, [rsp+2F0h+FindFileData]
0x18005309a  call    IsValidKeyFileName
0x18005309f  test    eax, eax
0x1800530a1  jz      short loc_180053057
0x1800530a3  mov     rcx, [rsp+2F0h+var_2A0]
0x1800530a8  lea     r9, [rsp+2F0h+var_2C0]
0x1800530ad  mov     r8d, r13d
0x1800530b0  lea     rdx, [rbp+1F0h+FindFileData.cFileName]
0x1800530b4  call    ReadKeyNameFromFile
0x1800530b9  test    eax, eax
0x1800530bb  jz      short loc_1800530E9
0x1800530bd  mov     r9d, 714h
0x1800530c3  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800530ca  lea     rdx, aStatus; "Status"
0x1800530d1  mov     ecx, eax
0x1800530d3  call    DebugTraceError
0x1800530d8  jmp     loc_180053057
0x1800530dd  mov     rdi, [rsp+2F0h+var_2C0]
0x1800530e2  mov     ebx, 8009002Ah
0x1800530e7  jmp     short loc_1800530F8
0x1800530e9  inc     dword ptr [r14]
0x1800530ec  xor     edi, edi
0x1800530ee  mov     rax, [rsp+2F0h+var_2C0]
0x1800530f3  mov     [rbx], rax
0x1800530f6  xor     ebx, ebx
0x1800530f8  cmp     [rbp+1F0h+arg_20], 0
0x1800530ff  jz      short loc_180053131
0x180053101  mov     rcx, rsi
0x180053104  call    RevertBackToCallerToken
0x180053109  mov     r14d, eax
0x18005310c  test    eax, eax
0x18005310e  jz      short loc_180053131
0x180053110  mov     r9d, 730h
0x180053116  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005311d  lea     rdx, aRevertstatus; "RevertStatus"
0x180053124  mov     ecx, eax
0x180053126  call    DebugTraceError
0x18005312b  test    ebx, ebx
0x18005312d  cmovz   ebx, r14d
0x180053131  test    r15, r15
0x180053134  jz      short loc_180053145
0x180053136  mov     rcx, r15; hObject
0x180053139  call    cs:__imp_CloseHandle
0x180053140  nop     dword ptr [rax+rax+00h]
0x180053145  test    rsi, rsi
0x180053148  jz      short loc_180053159
0x18005314a  mov     rcx, rsi; hObject
0x18005314d  call    cs:__imp_CloseHandle
0x180053154  nop     dword ptr [rax+rax+00h]
0x180053159  test    rdi, rdi
0x18005315c  jz      short loc_180053166
0x18005315e  mov     rcx, rdi
0x180053161  call    MSCryptFree
0x180053166  mov     eax, ebx
0x180053168  mov     rcx, [rbp+1F0h+var_40]
0x18005316f  xor     rcx, rsp; StackCookie
0x180053172  call    __security_check_cookie
0x180053177  add     rsp, 2C0h
0x18005317e  pop     r15
0x180053180  pop     r14
0x180053182  pop     r13
0x180053184  pop     rdi
0x180053185  pop     rsi
0x180053186  pop     rbx
0x180053187  pop     rbp
0x180053188  retn
```
