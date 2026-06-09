# CertDiagPrvInitProcessInfo(void)

- ea: `0x180082228`
- end: `0x1800823b9`
- name: `?CertDiagPrvInitProcessInfo@@YAXXZ`
- size: `401`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x180081fc8`

## callees

- `0x180082228`
- `0x1800823c0`
- `0x180082450`
- `0x1800824ac`
- `0x180082530`
- `0x180082b58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180082359`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180082359`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800822bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800822bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082339`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082339`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082247`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082247`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800822eb`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800822eb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800823aa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800823aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180082294`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180082294`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180082316`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180082316`

## string_xrefs

- `0x180082286`: `SYSTEM\CurrentControlSet\Services\crypt32`
- `0x180082378`: `SYSTEM\CurrentControlSet\Services\crypt32`

## pseudocode

```c
void CertDiagPrvInitProcessInfo(void)
{
  void *v0; // rdi
  LSTATUS v1; // eax
  int v2; // ebx
  HANDLE EventA; // rax
  LSTATUS v4; // eax
  DWORD v5; // ecx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF

  v0 = CertDiagPrvRevertImpersonateToken();
  EnterCriticalSection(&g_CertDiagCriticalSection);
  if ( !g_fCertDiagInitProcessInfo )
  {
    CertDiagPrvInitEtwInfo();
    g_pCertDiagProcessInfo = CertDiagPrvCreateProcessInfo(dword_180157D58);
    v1 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\crypt32",
           0,
           0x20019u,
           &g_CertDiagRegKey);
    v2 = 2;
    if ( v1 == 2 )
    {
      dwDisposition = 0;
      v1 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\crypt32",
             0,
             0,
             0,
             0x2001Fu,
             0,
             &g_CertDiagRegKey,
             &dwDisposition);
    }
    else
    {
      v2 = v1;
    }
    if ( v1 )
    {
      v5 = v2;
    }
    else
    {
      EventA = CreateEventA(0, 0, 0, 0);
      g_hCertDiagRegChangeEvent = EventA;
      if ( !EventA )
        goto LABEL_12;
      v4 = RegNotifyChangeKeyValue(g_CertDiagRegKey, 0, 0x10000004u, EventA, 1);
      if ( !v4 )
      {
        g_hCertDiagRegWaitFor = (HANDLE)RegisterWaitForSingleObjectEx(
                                          g_hCertDiagRegChangeEvent,
                                          CertDiagPrvRegChangeCallback,
                                          0,
                                          0xFFFFFFFFLL,
                                          128);
        if ( g_hCertDiagRegWaitFor )
        {
LABEL_8:
          g_fCertDiagInitProcessInfo = 1;
          goto LABEL_9;
        }
LABEL_12:
        CertDiagPrvUnregisterRegChange();
        goto LABEL_8;
      }
      v5 = v4;
    }
    SetLastError(v5);
    goto LABEL_12;
  }
LABEL_9:
  LeaveCriticalSection(&g_CertDiagCriticalSection);
  CertDiagPrvRestoreImpersonateToken(v0);
}

```

## disassembly

```asm
0x180082228  mov     [rsp+arg_8], rbx
0x18008222d  mov     [rsp+arg_10], rdi
0x180082232  push    r15
0x180082234  sub     rsp, 50h
0x180082238  call    ?CertDiagPrvRevertImpersonateToken@@YAPEAXXZ; CertDiagPrvRevertImpersonateToken(void)
0x18008223d  lea     rcx, ?g_CertDiagCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180082244  mov     rdi, rax
0x180082247  call    cs:__imp_EnterCriticalSection
0x18008224d  cmp     cs:?g_fCertDiagInitProcessInfo@@3HA, 0; int g_fCertDiagInitProcessInfo
0x180082254  jnz     loc_180082332
0x18008225a  call    ?CertDiagPrvInitEtwInfo@@YAXXZ; CertDiagPrvInitEtwInfo(void)
0x18008225f  mov     ecx, cs:dword_180157D58; int
0x180082265  call    ?CertDiagPrvCreateProcessInfo@@YAPEAU_CERT_DIAG_PROCESS_INFO@@H@Z; CertDiagPrvCreateProcessInfo(int)
0x18008226a  lea     r15, ?g_CertDiagRegKey@@3PEAUHKEY__@@EA; HKEY__ * g_CertDiagRegKey
0x180082271  mov     cs:?g_pCertDiagProcessInfo@@3PEAU_CERT_DIAG_PROCESS_INFO@@EA, rax; _CERT_DIAG_PROCESS_INFO * g_pCertDiagProcessInfo
0x180082278  mov     r9d, 20019h; samDesired
0x18008227e  mov     [rsp+58h+phkResult], r15; phkResult
0x180082283  xor     r8d, r8d; ulOptions
0x180082286  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\cr"...
0x18008228d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180082294  call    cs:__imp_RegOpenKeyExW
0x18008229a  mov     ebx, 2
0x18008229f  cmp     eax, ebx
0x1800822a1  jz      loc_180082366
0x1800822a7  mov     ebx, eax
0x1800822a9  test    eax, eax
0x1800822ab  jnz     loc_180082357
0x1800822b1  xor     r9d, r9d; lpName
0x1800822b4  xor     r8d, r8d; bInitialState
0x1800822b7  xor     edx, edx; bManualReset
0x1800822b9  xor     ecx, ecx; lpEventAttributes
0x1800822bb  call    cs:__imp_CreateEventA
0x1800822c1  mov     cs:?g_hCertDiagRegChangeEvent@@3PEAXEA, rax; void * g_hCertDiagRegChangeEvent
0x1800822c8  test    rax, rax
0x1800822cb  jz      loc_18008235F
0x1800822d1  mov     rcx, cs:?g_CertDiagRegKey@@3PEAUHKEY__@@EA; hKey
0x1800822d8  mov     r9, rax; hEvent
0x1800822db  xor     edx, edx; bWatchSubtree
0x1800822dd  mov     dword ptr [rsp+58h+phkResult], 1; fAsynchronous
0x1800822e5  mov     r8d, 10000004h; dwNotifyFilter
0x1800822eb  call    cs:__imp_RegNotifyChangeKeyValue
0x1800822f1  test    eax, eax
0x1800822f3  jnz     loc_1800823B5
0x1800822f9  mov     rcx, cs:?g_hCertDiagRegChangeEvent@@3PEAXEA; void * g_hCertDiagRegChangeEvent
0x180082300  lea     rdx, ?CertDiagPrvRegChangeCallback@@YAXPEAXE@Z; CertDiagPrvRegChangeCallback(void *,uchar)
0x180082307  or      r9d, 0FFFFFFFFh
0x18008230b  mov     dword ptr [rsp+58h+phkResult], 80h
0x180082313  xor     r8d, r8d
0x180082316  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18008231c  mov     cs:?g_hCertDiagRegWaitFor@@3PEAXEA, rax; void * g_hCertDiagRegWaitFor
0x180082323  test    rax, rax
0x180082326  jz      short loc_18008235F
0x180082328  mov     cs:?g_fCertDiagInitProcessInfo@@3HA, 1; int g_fCertDiagInitProcessInfo
0x180082332  lea     rcx, ?g_CertDiagCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180082339  call    cs:__imp_LeaveCriticalSection
0x18008233f  mov     rcx, rdi; hObject
0x180082342  mov     rbx, [rsp+58h+arg_8]
0x180082347  mov     rdi, [rsp+58h+arg_10]
0x18008234c  add     rsp, 50h
0x180082350  pop     r15
0x180082352  jmp     ?CertDiagPrvRestoreImpersonateToken@@YAXPEAX@Z; CertDiagPrvRestoreImpersonateToken(void *)
0x180082357  mov     ecx, ebx; dwErrCode
0x180082359  call    cs:__imp_SetLastError
0x18008235f  call    ?CertDiagPrvUnregisterRegChange@@YAXXZ; CertDiagPrvUnregisterRegChange(void)
0x180082364  jmp     short loc_180082328
0x180082366  lea     rax, [rsp+58h+dwDisposition]
0x18008236b  mov     [rsp+58h+dwDisposition], 0
0x180082373  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180082378  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\cr"...
0x18008237f  mov     [rsp+58h+var_20], r15; phkResult
0x180082384  xor     r9d, r9d; lpClass
0x180082387  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180082390  xor     r8d, r8d; Reserved
0x180082393  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18008239b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800823a2  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x1800823aa  call    cs:__imp_RegCreateKeyExW
0x1800823b0  jmp     loc_1800822A9
0x1800823b5  mov     ecx, eax
0x1800823b7  jmp     short loc_180082359
```
