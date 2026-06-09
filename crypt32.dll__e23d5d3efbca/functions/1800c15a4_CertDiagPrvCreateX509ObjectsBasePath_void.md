# CertDiagPrvCreateX509ObjectsBasePath(void)

- ea: `0x1800c15a4`
- end: `0x1800c1655`
- name: `?CertDiagPrvCreateX509ObjectsBasePath@@YAPEAGXZ`
- size: `177`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180095fd8`

## callees

- `0x180028d60`
- `0x1800823c0`
- `0x180082450`
- `0x1800c15a4`
- `0x180110fbc`
- `0x1801111b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c15e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c15e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c15fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c15fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c15de`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c15de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c15c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c15c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c163b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c163b`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800c15bf`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800c15bf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c15ee`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c15ee`

## pseudocode

```c
unsigned __int16 *CertDiagPrvCreateX509ObjectsBasePath(void)
{
  WCHAR *v0; // rdi
  void *v1; // rsi
  HANDLE CurrentThread; // rax
  BOOL v3; // ebx
  DWORD LastError; // ebp
  const WCHAR *LowIntegrityUserPath; // rax
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  TokenHandle = 0;
  v1 = CertDiagPrvRevertImpersonateToken();
  if ( ImpersonateSelf(SecurityImpersonation) )
  {
    CurrentThread = GetCurrentThread();
    v3 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
    LastError = GetLastError();
    RevertToSelf();
    if ( v3 )
    {
      LowIntegrityUserPath = (const WCHAR *)I_CryptGetLowIntegrityUserPath(TokenHandle, L"\\Microsoft\\X509Objects");
      v0 = (WCHAR *)LowIntegrityUserPath;
      if ( LowIntegrityUserPath && !(unsigned int)I_CryptRecursiveCreateLowIntegrityDirectory(LowIntegrityUserPath) )
      {
        PkiDefaultCryptFree(v0);
        v0 = 0;
      }
    }
    else
    {
      SetLastError(LastError);
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  CertDiagPrvRestoreImpersonateToken(v1);
  return v0;
}

```

## disassembly

```asm
0x1800c15a4  push    rbx
0x1800c15a6  push    rbp
0x1800c15a7  push    rsi
0x1800c15a8  push    rdi
0x1800c15a9  sub     rsp, 28h
0x1800c15ad  xor     edi, edi
0x1800c15af  mov     [rsp+48h+TokenHandle], rdi
0x1800c15b4  call    ?CertDiagPrvRevertImpersonateToken@@YAPEAXXZ; CertDiagPrvRevertImpersonateToken(void)
0x1800c15b9  lea     ecx, [rdi+2]; ImpersonationLevel
0x1800c15bc  mov     rsi, rax
0x1800c15bf  call    cs:__imp_ImpersonateSelf
0x1800c15c5  test    eax, eax
0x1800c15c7  jz      short loc_1800C1631
0x1800c15c9  call    cs:__imp_GetCurrentThread
0x1800c15cf  mov     rcx, rax; ThreadHandle
0x1800c15d2  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800c15d7  lea     edx, [rdi+0Ch]; DesiredAccess
0x1800c15da  lea     r8d, [rdi+1]; OpenAsSelf
0x1800c15de  call    cs:__imp_OpenThreadToken
0x1800c15e4  mov     ebx, eax
0x1800c15e6  call    cs:__imp_GetLastError
0x1800c15ec  mov     ebp, eax
0x1800c15ee  call    cs:__imp_RevertToSelf
0x1800c15f4  test    ebx, ebx
0x1800c15f6  jnz     short loc_1800C1602
0x1800c15f8  mov     ecx, ebp; dwErrCode
0x1800c15fa  call    cs:__imp_SetLastError
0x1800c1600  jmp     short loc_1800C1631
0x1800c1602  mov     rcx, [rsp+48h+TokenHandle]
0x1800c1607  lea     rdx, aMicrosoftX509o; "\\Microsoft\\X509Objects"
0x1800c160e  call    I_CryptGetLowIntegrityUserPath
0x1800c1613  mov     rdi, rax
0x1800c1616  test    rax, rax
0x1800c1619  jz      short loc_1800C1631
0x1800c161b  mov     rcx, rax; lpFileName
0x1800c161e  call    I_CryptRecursiveCreateLowIntegrityDirectory
0x1800c1623  test    eax, eax
0x1800c1625  jnz     short loc_1800C1631
0x1800c1627  mov     rcx, rdi; hMem
0x1800c162a  call    PkiDefaultCryptFree
0x1800c162f  xor     edi, edi
0x1800c1631  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800c1636  test    rcx, rcx
0x1800c1639  jz      short loc_1800C1641
0x1800c163b  call    cs:__imp_CloseHandle
0x1800c1641  mov     rcx, rsi; hObject
0x1800c1644  call    ?CertDiagPrvRestoreImpersonateToken@@YAXPEAX@Z; CertDiagPrvRestoreImpersonateToken(void *)
0x1800c1649  mov     rax, rdi
0x1800c164c  add     rsp, 28h
0x1800c1650  pop     rdi
0x1800c1651  pop     rsi
0x1800c1652  pop     rbp
0x1800c1653  pop     rbx
0x1800c1654  retn
```
