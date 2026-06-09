# OpenClassesRootKeyExW

- ea: `0x180012750`
- end: `0x1800128f3`
- name: `OpenClassesRootKeyExW`
- size: `419`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001186c`
- `0x180012020`
- `0x180015104`
- `0x180040d20`
- `0x1800572c0`
- `0x180072d10`
- `0x180085eec`

## callees

- `0x180011f84`
- `0x180012750`
- `0x18002f8dc`
- `0x1800304f0`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800127cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800127cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800127af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800127af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012799`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012799`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800127dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800127dd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800127bd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800127bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012872`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001286a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001286a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800128d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800128d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenUserClassesRoot` at `0x180012832`
- `api-ms-win-core-registry-l1-1-0!RegOpenUserClassesRoot` at `0x180012832`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001285e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001285e`

## pseudocode

```c
__int64 __fastcall OpenClassesRootKeyExW(LPCWSTR lpSubKey, int a2, HKEY *a3)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  int v8; // esi
  int LastError; // ebx
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned __int16 *v12; // [rsp+28h] [rbp-18h]
  unsigned __int16 *v13; // [rsp+28h] [rbp-18h]
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  int v15; // [rsp+78h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+40h] BYREF
  HANDLE hToken; // [rsp+88h] [rbp+48h] BYREF

  v15 = a2;
  hToken = 0;
  phkResult = 0;
  if ( !a3 )
    return 87;
  *a3 = 0;
  TokenHandle = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
      SetThreadToken(0, 0);
    else
      GetLastError();
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &hToken) )
  {
    LastError = GetLastError();
    goto LABEL_17;
  }
  v8 = 0;
  v15 = 0;
  LastError = CalculateHklmOnlyClassicCOMCatalogGlobalOptionStatus();
  if ( LastError >= 0 )
  {
    if ( dword_1800C2CC0 == 1 )
    {
LABEL_12:
      if ( !v8 || (LastError = RegOpenUserClassesRoot(hToken, 0, 0x2000000u, &phkResult)) != 0 )
        LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes", 0, 0x2000000u, &phkResult);
      goto LABEL_15;
    }
    LastError = IsUserHiveOK(hToken, &v15);
    if ( LastError >= 0 )
    {
      v8 = v15;
      goto LABEL_12;
    }
  }
LABEL_15:
  CloseHandle(hToken);
LABEL_17:
  ResumeImpersonate(TokenHandle);
  if ( !LastError )
  {
    if ( lpSubKey && *lpSubKey )
    {
      LastError = RegOpenOtherKeyExW(phkResult, lpSubKey, v10, 0x2000000u, a3, v12);
      if ( LastError == 2 )
        LastError = (unsigned int)RegOpenOtherKeyExW(phkResult, lpSubKey, v11, 0x2000200u, a3, v13) != 0 ? 2 : 0;
      RegCloseKey(phkResult);
    }
    else
    {
      *a3 = phkResult;
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180012750  mov     [rsp-28h+arg_0], rbx
0x180012755  mov     [rsp-28h+arg_8], edx
0x180012759  push    rbp
0x18001275a  push    rsi
0x18001275b  push    rdi
0x18001275c  push    r14
0x18001275e  push    r15
0x180012760  mov     rbp, rsp
0x180012763  sub     rsp, 40h
0x180012767  xor     r15d, r15d
0x18001276a  mov     rdi, r8
0x18001276d  mov     [rbp+hToken], r15
0x180012771  mov     r14, rcx
0x180012774  mov     [rbp+phkResult], r15
0x180012778  test    r8, r8
0x18001277b  jnz     short loc_180012786
0x18001277d  lea     eax, [r8+57h]
0x180012781  jmp     loc_1800128E2
0x180012786  mov     [r8], r15
0x180012789  mov     [rbp+TokenHandle], r15
0x18001278d  mov     eax, gs:179Ch
0x180012795  test    eax, eax
0x180012797  jz      short loc_1800127CB
0x180012799  call    cs:__imp_GetCurrentThread
0x18001279f  mov     edx, 4; DesiredAccess
0x1800127a4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800127a8  mov     rcx, rax; ThreadHandle
0x1800127ab  lea     r8d, [rdx-3]; OpenAsSelf
0x1800127af  call    cs:__imp_OpenThreadToken
0x1800127b5  test    eax, eax
0x1800127b7  jz      short loc_1800127C5
0x1800127b9  xor     edx, edx; Token
0x1800127bb  xor     ecx, ecx; Thread
0x1800127bd  call    cs:__imp_SetThreadToken
0x1800127c3  jmp     short loc_1800127CB
0x1800127c5  call    cs:__imp_GetLastError
0x1800127cb  call    cs:__imp_GetCurrentProcess
0x1800127d1  lea     r8, [rbp+hToken]; TokenHandle
0x1800127d5  mov     edx, 8; DesiredAccess
0x1800127da  mov     rcx, rax; ProcessHandle
0x1800127dd  call    cs:__imp_OpenProcessToken
0x1800127e3  test    eax, eax
0x1800127e5  jz      loc_180012872
0x1800127eb  mov     esi, r15d
0x1800127ee  mov     [rbp+arg_8], r15d
0x1800127f2  call    ?CalculateHklmOnlyClassicCOMCatalogGlobalOptionStatus@@YAJXZ; CalculateHklmOnlyClassicCOMCatalogGlobalOptionStatus(void)
0x1800127f7  mov     ebx, eax
0x1800127f9  test    eax, eax
0x1800127fb  js      short loc_180012866
0x1800127fd  mov     eax, cs:dword_1800C2CC0
0x180012803  cmp     eax, 1
0x180012806  jz      short loc_18001281E
0x180012808  mov     rcx, [rbp+hToken]; TokenHandle
0x18001280c  lea     rdx, [rbp+arg_8]; int *
0x180012810  call    ?IsUserHiveOK@@YAJPEAXPEAH@Z; IsUserHiveOK(void *,int *)
0x180012815  mov     ebx, eax
0x180012817  test    eax, eax
0x180012819  js      short loc_180012866
0x18001281b  mov     esi, [rbp+arg_8]
0x18001281e  test    esi, esi
0x180012820  jz      short loc_18001283E
0x180012822  mov     rcx, [rbp+hToken]; hToken
0x180012826  lea     r9, [rbp+phkResult]; phkResult
0x18001282a  xor     edx, edx; dwOptions
0x18001282c  mov     r8d, 2000000h; samDesired
0x180012832  call    cs:__imp_RegOpenUserClassesRoot
0x180012838  mov     ebx, eax
0x18001283a  test    eax, eax
0x18001283c  jz      short loc_180012866
0x18001283e  lea     rax, [rbp+phkResult]
0x180012842  mov     r9d, 2000000h; samDesired
0x180012848  xor     r8d, r8d; ulOptions
0x18001284b  mov     [rsp+40h+var_20], rax; phkResult
0x180012850  lea     rdx, aSoftwareClasse_0; "Software\\Classes"
0x180012857  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001285e  call    cs:__imp_RegOpenKeyExW
0x180012864  mov     ebx, eax
0x180012866  mov     rcx, [rbp+hToken]; hObject
0x18001286a  call    cs:__imp_CloseHandle
0x180012870  jmp     short loc_18001287A
0x180012872  call    cs:__imp_GetLastError
0x180012878  mov     ebx, eax
0x18001287a  mov     rcx, [rbp+TokenHandle]; Token
0x18001287e  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180012883  test    ebx, ebx
0x180012885  jnz     short loc_1800128E0
0x180012887  test    r14, r14
0x18001288a  jz      short loc_1800128D9
0x18001288c  cmp     [r14], r15w
0x180012890  jz      short loc_1800128D9
0x180012892  mov     rcx, [rbp+phkResult]; hKey
0x180012896  mov     r9d, 2000000h; unsigned int
0x18001289c  mov     rdx, r14; lpSubKey
0x18001289f  mov     [rsp+40h+var_20], rdi; HKEY *
0x1800128a4  call    ?RegOpenOtherKeyExW@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@PEAG@Z; RegOpenOtherKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *,ushort *)
0x1800128a9  mov     ebx, eax
0x1800128ab  cmp     eax, 2
0x1800128ae  jnz     short loc_1800128CD
0x1800128b0  mov     rcx, [rbp+phkResult]; hKey
0x1800128b4  mov     r9d, 2000200h; unsigned int
0x1800128ba  mov     rdx, r14; lpSubKey
0x1800128bd  mov     [rsp+40h+var_20], rdi; HKEY *
0x1800128c2  call    ?RegOpenOtherKeyExW@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@PEAG@Z; RegOpenOtherKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *,ushort *)
0x1800128c7  neg     eax
0x1800128c9  sbb     ecx, ecx
0x1800128cb  and     ebx, ecx
0x1800128cd  mov     rcx, [rbp+phkResult]; hKey
0x1800128d1  call    cs:__imp_RegCloseKey
0x1800128d7  jmp     short loc_1800128E0
0x1800128d9  mov     rax, [rbp+phkResult]
0x1800128dd  mov     [rdi], rax
0x1800128e0  mov     eax, ebx
0x1800128e2  mov     rbx, [rsp+40h+arg_0]
0x1800128e7  add     rsp, 40h
0x1800128eb  pop     r15
0x1800128ed  pop     r14
0x1800128ef  pop     rdi
0x1800128f0  pop     rsi
0x1800128f1  pop     rbp
0x1800128f2  retn
```
