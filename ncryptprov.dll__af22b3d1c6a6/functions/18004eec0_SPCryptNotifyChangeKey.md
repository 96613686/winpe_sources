# SPCryptNotifyChangeKey

- ea: `0x18004eec0`
- end: `0x18004f134`
- name: `SPCryptNotifyChangeKey`
- size: `628`
- prototype: `__int64 __fastcall(__int64, void **, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800060e0`
- `0x18000af80`
- `0x18000d3d0`
- `0x18000dab0`
- `0x180017a80`
- `0x18004eec0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18004f078`
- `ntdll!RtlReleaseResource` at `0x18004f078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f03c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f03c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f120`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x18004f0d5`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x18004f0d5`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x18004f02a`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x18004f02a`
- `api-ms-win-core-file-l1-1-0!FindNextChangeNotification` at `0x18004f10c`
- `api-ms-win-core-file-l1-1-0!FindNextChangeNotification` at `0x18004f10c`

## string_xrefs

- `0x18004ef03`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18004ef41`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18004f0bf`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall SPCryptNotifyChangeKey(__int64 a1, void **a2, int a3)
{
  char *v4; // rbp
  const WCHAR *v5; // rdi
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r14
  DWORD v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // r8d
  int v14; // eax
  BOOL v15; // r15d
  DWORD UserStorageArea; // eax
  DWORD UserDirectory; // eax
  __int64 v18; // rcx
  HANDLE v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r9
  void *v23; // rcx
  DWORD LastError; // eax
  LPCWSTR lpPathName[7]; // [rsp+30h] [rbp-38h] BYREF
  char *v26; // [rsp+88h] [rbp+20h] BYREF

  v26 = 0;
  v4 = 0;
  lpPathName[0] = 0;
  v5 = 0;
  v7 = KspValidateAndLockProvider(a1, 0);
  v9 = v7;
  if ( v7 )
  {
    if ( !a2 )
    {
      v10 = -2146893785;
      v11 = 8366;
      v12 = 2148073511LL;
LABEL_5:
      DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v11);
LABEL_26:
      RtlReleaseResource((PRTL_RESOURCE)(v9 + 64));
      return v10;
    }
    if ( (a3 & 0xFFFFFFDC) != 0 )
    {
      v10 = -2146893815;
      v11 = 8378;
      v12 = 2148073481LL;
      goto LABEL_5;
    }
    v13 = *(_DWORD *)(v7 + 48);
    v14 = a3 & 0x20;
    if ( v13 && (a3 & 0x20) != 0 )
    {
      v10 = -2146893808;
      v11 = 8387;
      v12 = 2148073488LL;
      goto LABEL_5;
    }
    if ( (a3 & 1) == 0 )
    {
      v23 = *a2;
      if ( (a3 & 2) != 0 )
      {
        if ( FindCloseChangeNotification(v23) )
        {
          *a2 = (void *)-1LL;
          goto LABEL_21;
        }
        LastError = GetLastError();
        v11 = 8491;
      }
      else
      {
        if ( FindNextChangeNotification(v23) )
          goto LABEL_21;
        LastError = GetLastError();
        v11 = 8501;
      }
      v10 = LastError;
      v12 = LastError;
      goto LABEL_5;
    }
    v15 = v14 != 0;
    UserStorageArea = GetUserStorageArea(v14 != 0, v8, v13, *(_WORD **)(v9 + 40), &v26);
    v4 = v26;
    v10 = UserStorageArea;
    if ( !UserStorageArea )
    {
      if ( v26 )
      {
        UserDirectory = GetUserDirectory(v15, *(_QWORD *)(v9 + 40) != 0, v26, lpPathName);
        v5 = lpPathName[0];
        v10 = UserDirectory;
        if ( !UserDirectory )
        {
          if ( lpPathName[0] )
          {
            v18 = -1;
            do
              ++v18;
            while ( lpPathName[0][v18] );
            lpPathName[0][v18 - 1] = 0;
            v19 = FindFirstChangeNotificationW(v5, 1, 0x11Du);
            if ( v19 == (HANDLE)-1LL )
            {
              v10 = GetLastError();
              v20 = v10;
              v21 = 8480;
LABEL_33:
              DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v21);
              goto LABEL_22;
            }
            *a2 = v19;
LABEL_21:
            v10 = 0;
LABEL_22:
            if ( v4 )
              MSCryptFree(v4);
            if ( v5 )
              MSCryptFree(v5);
            goto LABEL_26;
          }
          v10 = 3;
        }
        v21 = 8460;
LABEL_32:
        v20 = v10;
        goto LABEL_33;
      }
      v10 = 3;
    }
    v21 = 8447;
    goto LABEL_32;
  }
  v10 = -2146893786;
  DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 8359);
  return v10;
}

```

## disassembly

```asm
0x18004eec0  mov     rax, rsp
0x18004eec3  mov     [rax+8], rbx
0x18004eec7  mov     [rax+10h], rbp
0x18004eecb  push    rsi
0x18004eecc  push    rdi
0x18004eecd  push    r12
0x18004eecf  push    r14
0x18004eed1  push    r15
0x18004eed3  sub     rsp, 40h
0x18004eed7  xor     r12d, r12d
0x18004eeda  mov     rsi, rdx
0x18004eedd  xor     edx, edx
0x18004eedf  mov     [rax+20h], r12
0x18004eee3  mov     ebp, r12d
0x18004eee6  mov     [rax-38h], r12
0x18004eeea  mov     edi, r12d
0x18004eeed  mov     ebx, r8d
0x18004eef0  call    KspValidateAndLockProvider
0x18004eef5  mov     r14, rax
0x18004eef8  test    rax, rax
0x18004eefb  jnz     short loc_18004EF25
0x18004eefd  mov     r9d, 20A7h
0x18004ef03  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ef0a  lea     rdx, aStatus; "Status"
0x18004ef11  mov     ecx, 80090026h
0x18004ef16  mov     ebx, 80090026h
0x18004ef1b  call    DebugTraceError
0x18004ef20  jmp     loc_18004F084
0x18004ef25  test    rsi, rsi
0x18004ef28  jnz     short loc_18004EF52
0x18004ef2a  mov     ebx, 80090027h
0x18004ef2f  mov     r9d, 20AEh
0x18004ef35  mov     ecx, 80090027h
0x18004ef3a  lea     rdx, aStatus; "Status"
0x18004ef41  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ef48  call    DebugTraceError
0x18004ef4d  jmp     loc_18004F074
0x18004ef52  test    ebx, 0FFFFFFDCh
0x18004ef58  jz      short loc_18004EF6C
0x18004ef5a  mov     ebx, 80090009h
0x18004ef5f  mov     r9d, 20BAh
0x18004ef65  mov     ecx, 80090009h
0x18004ef6a  jmp     short loc_18004EF3A
0x18004ef6c  mov     r8d, [rax+30h]
0x18004ef70  mov     eax, ebx
0x18004ef72  and     eax, 20h
0x18004ef75  test    r8d, r8d
0x18004ef78  jz      short loc_18004EF90
0x18004ef7a  test    eax, eax
0x18004ef7c  jz      short loc_18004EF90
0x18004ef7e  mov     ebx, 80090010h
0x18004ef83  mov     r9d, 20C3h
0x18004ef89  mov     ecx, 80090010h
0x18004ef8e  jmp     short loc_18004EF3A
0x18004ef90  test    bl, 1
0x18004ef93  jz      loc_18004F0CD
0x18004ef99  mov     r9, [r14+28h]
0x18004ef9d  test    eax, eax
0x18004ef9f  mov     r15d, r12d
0x18004efa2  lea     rax, [rsp+68h+arg_18]
0x18004efaa  setnz   r15b
0x18004efae  mov     [rsp+68h+var_48], rax
0x18004efb3  mov     ecx, r15d
0x18004efb6  call    GetUserStorageArea
0x18004efbb  mov     rbp, [rsp+68h+arg_18]
0x18004efc3  mov     ebx, eax
0x18004efc5  test    eax, eax
0x18004efc7  jnz     loc_18004F0B0
0x18004efcd  test    rbp, rbp
0x18004efd0  jz      loc_18004F0AB
0x18004efd6  cmp     [r14+28h], r12
0x18004efda  lea     r9, [rsp+68h+lpPathName]
0x18004efdf  mov     edx, r12d
0x18004efe2  mov     r8, rbp
0x18004efe5  setnz   dl
0x18004efe8  mov     ecx, r15d
0x18004efeb  call    GetUserDirectory
0x18004eff0  mov     rdi, [rsp+68h+lpPathName]
0x18004eff5  mov     ebx, eax
0x18004eff7  test    eax, eax
0x18004eff9  jnz     loc_18004F0A3
0x18004efff  test    rdi, rdi
0x18004f002  jz      loc_18004F09E
0x18004f008  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004f00c  inc     rcx
0x18004f00f  cmp     [rdi+rcx*2], r12w
0x18004f014  jnz     short loc_18004F00C
0x18004f016  mov     [rdi+rcx*2-2], r12w
0x18004f01c  mov     edx, 1; bWatchSubtree
0x18004f021  mov     rcx, rdi; lpPathName
0x18004f024  mov     r8d, 11Dh; dwNotifyFilter
0x18004f02a  call    cs:__imp_FindFirstChangeNotificationW
0x18004f031  nop     dword ptr [rax+rax+00h]
0x18004f036  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f03a  jnz     short loc_18004F054
0x18004f03c  call    cs:__imp_GetLastError
0x18004f043  nop     dword ptr [rax+rax+00h]
0x18004f048  mov     ebx, eax
0x18004f04a  mov     ecx, eax
0x18004f04c  mov     r9d, 2120h
0x18004f052  jmp     short loc_18004F0B8
0x18004f054  mov     [rsi], rax
0x18004f057  mov     ebx, r12d
0x18004f05a  test    rbp, rbp
0x18004f05d  jz      short loc_18004F067
0x18004f05f  mov     rcx, rbp
0x18004f062  call    MSCryptFree
0x18004f067  test    rdi, rdi
0x18004f06a  jz      short loc_18004F074
0x18004f06c  mov     rcx, rdi
0x18004f06f  call    MSCryptFree
0x18004f074  lea     rcx, [r14+40h]; Resource
0x18004f078  call    cs:__imp_RtlReleaseResource
0x18004f07f  nop     dword ptr [rax+rax+00h]
0x18004f084  mov     rbp, [rsp+68h+arg_8]
0x18004f089  mov     eax, ebx
0x18004f08b  mov     rbx, [rsp+68h+arg_0]
0x18004f090  add     rsp, 40h
0x18004f094  pop     r15
0x18004f096  pop     r14
0x18004f098  pop     r12
0x18004f09a  pop     rdi
0x18004f09b  pop     rsi
0x18004f09c  retn
0x18004f09e  mov     ebx, 3
0x18004f0a3  mov     r9d, 210Ch
0x18004f0a9  jmp     short loc_18004F0B6
0x18004f0ab  mov     ebx, 3
0x18004f0b0  mov     r9d, 20FFh
0x18004f0b6  mov     ecx, ebx
0x18004f0b8  lea     rdx, aStatus; "Status"
0x18004f0bf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004f0c6  call    DebugTraceError
0x18004f0cb  jmp     short loc_18004F05A
0x18004f0cd  mov     rcx, [rsi]; hChangeHandle
0x18004f0d0  test    bl, 2
0x18004f0d3  jz      short loc_18004F10C
0x18004f0d5  call    cs:__imp_FindCloseChangeNotification
0x18004f0dc  nop     dword ptr [rax+rax+00h]
0x18004f0e1  test    eax, eax
0x18004f0e3  jnz     short loc_18004F100
0x18004f0e5  call    cs:__imp_GetLastError
0x18004f0ec  nop     dword ptr [rax+rax+00h]
0x18004f0f1  mov     r9d, 212Bh
0x18004f0f7  mov     ebx, eax
0x18004f0f9  mov     ecx, eax
0x18004f0fb  jmp     loc_18004EF3A
0x18004f100  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18004f107  jmp     loc_18004F057
0x18004f10c  call    cs:__imp_FindNextChangeNotification
0x18004f113  nop     dword ptr [rax+rax+00h]
0x18004f118  test    eax, eax
0x18004f11a  jnz     loc_18004F057
0x18004f120  call    cs:__imp_GetLastError
0x18004f127  nop     dword ptr [rax+rax+00h]
0x18004f12c  mov     r9d, 2135h
0x18004f132  jmp     short loc_18004F0F7
```
