# CertDiagPrvCreateProcessInfo(int)

- ea: `0x180082530`
- end: `0x180082709`
- name: `?CertDiagPrvCreateProcessInfo@@YAPEAU_CERT_DIAG_PROCESS_INFO@@H@Z`
- size: `473`
- prototype: `struct _CERT_DIAG_PROCESS_INFO *__fastcall(int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180081f5c`
- `0x180082228`

## callees

- `0x180028d60`
- `0x180046e10`
- `0x18004d730`
- `0x180082530`
- `0x180082710`
- `0x180082784`
- `0x1800827f8`
- `0x180082848`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800825d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800825d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180082575`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180082575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180082608`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180082608`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008261a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008261a`
- `ntdll!wcsrchr` at `0x180082630`
- `ntdll!wcsrchr` at `0x1800826f6`
- `ntdll!wcsrchr` at `0x180082630`
- `ntdll!wcsrchr` at `0x1800826f6`

## string_xrefs

- `0x18008256e`: `SYSTEM\CurrentControlSet\Services\crypt32`
- `0x1800826a6`: `DiagXmlFileName`

## pseudocode

```c
struct _CERT_DIAG_PROCESS_INFO *__fastcall CertDiagPrvCreateProcessInfo(int a1)
{
  __int64 v2; // rdi
  const unsigned __int16 *v3; // rdx
  HKEY v4; // rcx
  char DWORDRegValue; // r15
  const unsigned __int16 *v6; // rdx
  unsigned __int64 QWORDRegValue; // rax
  __int64 v8; // r14
  wchar_t *v9; // rbx
  HANDLE CurrentProcess; // rax
  wchar_t *v12; // rcx
  wchar_t *v13; // rsi
  __int64 v14; // rax
  DWORD dwSize; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  v2 = 0;
  hKey = 0;
  dwSize = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\crypt32", 0, 0x20019u, &hKey) )
  {
    v4 = 0;
    hKey = 0;
  }
  else
  {
    v4 = hKey;
  }
  DWORDRegValue = CertDiagPrvGetDWORDRegValue(v4, v3);
  QWORDRegValue = CertDiagPrvGetQWORDRegValue(hKey, v6);
  v8 = QWORDRegValue;
  if ( (unsigned __int8)DWORDRegValue < 2u || !QWORDRegValue )
  {
    v9 = 0;
    if ( !a1 )
      goto LABEL_7;
    DWORDRegValue = 4;
    v8 = 0xFFFFFFFFLL;
  }
  v9 = (wchar_t *)PkiAlloc(0x2000u);
  if ( v9 )
  {
    dwSize = 4096;
    CurrentProcess = GetCurrentProcess();
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, v9, &dwSize) )
    {
      v12 = wcsrchr(v9, 0x5Cu);
      if ( v12 || (v12 = wcsrchr(v9, 0x3Au)) != 0 )
      {
        dwSize += -1 - (v12 - v9);
        v13 = v12 + 1;
LABEL_15:
        if ( CertDiagPrvIsLoggingEnabledForCurrentProcess(hKey, v13) )
        {
          v14 = PkiZeroAlloc(2LL * (dwSize + 1) + 32);
          v2 = v14;
          if ( v14 )
          {
            *(_QWORD *)(v14 + 24) = v14 + 32;
            memcpy_0((void *)(v14 + 32), v13, 2LL * (dwSize + 1));
            *(_DWORD *)v2 = 1;
            *(_BYTE *)(v2 + 4) = DWORDRegValue;
            *(_QWORD *)(v2 + 8) = v8;
            *(_QWORD *)(v2 + 16) = CertDiagPrvGetStringRegValue(hKey, L"DiagXmlFileName");
          }
        }
        goto LABEL_7;
      }
    }
    else
    {
      dwSize = 0;
      *v9 = 0;
    }
    v13 = v9;
    goto LABEL_15;
  }
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    PkiDefaultCryptFree(v9);
  return (struct _CERT_DIAG_PROCESS_INFO *)v2;
}

```

## disassembly

```asm
0x180082530  mov     [rsp-28h+arg_0], rbx
0x180082535  mov     [rsp-28h+arg_18], rsi
0x18008253a  push    rbp
0x18008253b  push    rdi
0x18008253c  push    r12
0x18008253e  push    r14
0x180082540  push    r15
0x180082542  mov     rbp, rsp
0x180082545  sub     rsp, 30h
0x180082549  mov     r12d, ecx
0x18008254c  lea     rax, [rbp+hKey]
0x180082550  xor     edi, edi
0x180082552  mov     [rsp+30h+phkResult], rax; phkResult
0x180082557  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008255e  mov     [rbp+hKey], rdi
0x180082562  mov     r9d, 20019h; samDesired
0x180082568  mov     [rbp+dwSize], edi
0x18008256b  xor     r8d, r8d; ulOptions
0x18008256e  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\cr"...
0x180082575  call    cs:__imp_RegOpenKeyExW
0x18008257b  test    eax, eax
0x18008257d  jz      loc_1800826C7
0x180082583  xor     ecx, ecx; HKEY
0x180082585  mov     [rbp+hKey], rcx
0x180082589  call    ?CertDiagPrvGetDWORDRegValue@@YAKPEAUHKEY__@@PEBG@Z; CertDiagPrvGetDWORDRegValue(HKEY__ *,ushort const *)
0x18008258e  mov     rcx, [rbp+hKey]; HKEY
0x180082592  mov     r15d, eax
0x180082595  call    ?CertDiagPrvGetQWORDRegValue@@YA_KPEAUHKEY__@@PEBG@Z; CertDiagPrvGetQWORDRegValue(HKEY__ *,ushort const *)
0x18008259a  mov     r14, rax
0x18008259d  mov     esi, 0FFFFFFFFh
0x1800825a2  cmp     r15b, 2
0x1800825a6  jnb     loc_1800826E0
0x1800825ac  xor     ebx, ebx
0x1800825ae  test    r12d, r12d
0x1800825b1  jz      short loc_1800825CB
0x1800825b3  mov     r15b, 4
0x1800825b6  mov     r14, rsi
0x1800825b9  mov     ecx, 2000h; uBytes
0x1800825be  call    PkiAlloc
0x1800825c3  mov     rbx, rax
0x1800825c6  test    rax, rax
0x1800825c9  jnz     short loc_180082601
0x1800825cb  mov     rcx, [rbp+hKey]; hKey
0x1800825cf  test    rcx, rcx
0x1800825d2  jz      short loc_1800825DA
0x1800825d4  call    cs:__imp_RegCloseKey
0x1800825da  test    rbx, rbx
0x1800825dd  jz      short loc_1800825E7
0x1800825df  mov     rcx, rbx; hMem
0x1800825e2  call    PkiDefaultCryptFree
0x1800825e7  mov     rbx, [rsp+30h+arg_0]
0x1800825ec  mov     rax, rdi
0x1800825ef  mov     rsi, [rsp+30h+arg_18]
0x1800825f4  add     rsp, 30h
0x1800825f8  pop     r15
0x1800825fa  pop     r14
0x1800825fc  pop     r12
0x1800825fe  pop     rdi
0x1800825ff  pop     rbp
0x180082600  retn
0x180082601  mov     [rbp+dwSize], 1000h
0x180082608  call    cs:__imp_GetCurrentProcess
0x18008260e  lea     r9, [rbp+dwSize]; lpdwSize
0x180082612  mov     r8, rbx; lpExeName
0x180082615  mov     rcx, rax; hProcess
0x180082618  xor     edx, edx; dwFlags
0x18008261a  call    cs:__imp_QueryFullProcessImageNameW
0x180082620  test    eax, eax
0x180082622  jz      loc_1800826D0
0x180082628  mov     edx, 5Ch ; '\'; Ch
0x18008262d  mov     rcx, rbx; Str
0x180082630  call    cs:__imp_wcsrchr
0x180082636  mov     rcx, rax
0x180082639  test    rax, rax
0x18008263c  jz      loc_1800826EE
0x180082642  mov     rax, rcx
0x180082645  sub     rax, rbx
0x180082648  sar     rax, 1
0x18008264b  sub     esi, eax
0x18008264d  add     [rbp+dwSize], esi
0x180082650  lea     rsi, [rcx+2]
0x180082654  mov     rcx, [rbp+hKey]; HKEY
0x180082658  mov     rdx, rsi; unsigned __int16 *
0x18008265b  call    ?CertDiagPrvIsLoggingEnabledForCurrentProcess@@YAHPEAUHKEY__@@PEBG@Z; CertDiagPrvIsLoggingEnabledForCurrentProcess(HKEY__ *,ushort const *)
0x180082660  test    eax, eax
0x180082662  jz      loc_1800825CB
0x180082668  mov     eax, [rbp+dwSize]
0x18008266b  inc     eax
0x18008266d  lea     rcx, ds:20h[rax*2]; uBytes
0x180082675  call    PkiZeroAlloc
0x18008267a  mov     rdi, rax
0x18008267d  test    rax, rax
0x180082680  jz      loc_1800825CB
0x180082686  lea     rcx, [rax+20h]; void *
0x18008268a  mov     rdx, rsi; Src
0x18008268d  mov     [rax+18h], rcx
0x180082691  mov     r8d, [rbp+dwSize]
0x180082695  inc     r8d
0x180082698  add     r8, r8; Size
0x18008269b  call    memcpy_0
0x1800826a0  mov     dword ptr [rdi], 1
0x1800826a6  lea     rdx, aDiagxmlfilenam; "DiagXmlFileName"
0x1800826ad  mov     [rdi+4], r15b
0x1800826b1  mov     [rdi+8], r14
0x1800826b5  mov     rcx, [rbp+hKey]; hKey
0x1800826b9  call    ?CertDiagPrvGetStringRegValue@@YAPEAGPEAUHKEY__@@PEBG@Z; CertDiagPrvGetStringRegValue(HKEY__ *,ushort const *)
0x1800826be  mov     [rdi+10h], rax
0x1800826c2  jmp     loc_1800825CB
0x1800826c7  mov     rcx, [rbp+hKey]
0x1800826cb  jmp     loc_180082589
0x1800826d0  xor     eax, eax
0x1800826d2  mov     [rbp+dwSize], edi
0x1800826d5  mov     [rbx], ax
0x1800826d8  mov     rsi, rbx
0x1800826db  jmp     loc_180082654
0x1800826e0  test    rax, rax
0x1800826e3  jnz     loc_1800825B9
0x1800826e9  jmp     loc_1800825AC
0x1800826ee  mov     edx, 3Ah ; ':'; Ch
0x1800826f3  mov     rcx, rbx; Str
0x1800826f6  call    cs:__imp_wcsrchr
0x1800826fc  mov     rcx, rax
0x1800826ff  test    rax, rax
0x180082702  jz      short loc_1800826D8
0x180082704  jmp     loc_180082642
```
