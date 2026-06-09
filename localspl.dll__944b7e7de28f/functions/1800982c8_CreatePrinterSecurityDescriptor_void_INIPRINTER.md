# CreatePrinterSecurityDescriptor(void *,_INIPRINTER *)

- ea: `0x1800982c8`
- end: `0x1800984ca`
- name: `?CreatePrinterSecurityDescriptor@@YAPEAXPEAXPEAU_INIPRINTER@@@Z`
- size: `514`
- prototype: `void *__fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, struct _INIPRINTER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800984d0`

## callees

- `0x18003ea2c`
- `0x1800982c8`
- `0x180098ccc`
- `0x18009964c`
- `0x1800c7748`
- `0x1800ca63c`
- `0x1800cceec`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18009841a`
- `ntdll!RtlEqualSid` at `0x18009842e`
- `ntdll!RtlEqualSid` at `0x18009841a`
- `ntdll!RtlEqualSid` at `0x18009842e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009837a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009837a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800983ea`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800983ea`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800983bf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800983bf`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurity` at `0x180098365`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurity` at `0x180098365`
- `SPOOLSS!DllFreeSplMem` at `0x18009848a`
- `SPOOLSS!DllFreeSplMem` at `0x18009848a`
- `SPOOLSS!RevertToPrinterSelf` at `0x180098329`
- `SPOOLSS!RevertToPrinterSelf` at `0x180098329`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180098370`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180098370`

## string_xrefs

- `0x180098449`: `CreatePrinterSecurityDescriptor, GetActiveSessionSidViaBroker`
- `0x18009838d`: `CreatePrivateObjectSecurity failed.  Error %d`
- `0x180098394`: `CreatePrinterSecurityDescriptor`

## pseudocode

```c
PSECURITY_DESCRIPTOR __fastcall CreatePrinterSecurityDescriptor(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        struct _INIPRINTER *a2)
{
  HANDLE v4; // rdi
  BOOL v5; // ebx
  DWORD LastError; // eax
  PSECURITY_DESCRIPTOR v8; // rbx
  int v9; // edi
  PSID *v10; // r14
  int ActiveSessionSidViaBroker; // eax
  WINBOOL bDaclDefaulted; // [rsp+30h] [rbp-30h] BYREF
  WINBOOL bDaclPresent; // [rsp+34h] [rbp-2Ch] BYREF
  void *v14; // [rsp+38h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-20h] BYREF
  void *v16; // [rsp+48h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+50h] [rbp-10h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-8h] BYREF
  WORD pControl; // [rsp+A0h] [rbp+40h] BYREF
  DWORD dwRevision; // [rsp+A8h] [rbp+48h] BYREF

  hObject = 0;
  pControl = 0;
  dwRevision = 0;
  NewDescriptor = 0;
  bDaclPresent = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  v16 = 0;
  if ( !(unsigned int)GetTokenHandle(&hObject) )
    return 0;
  v4 = RevertToPrinterSelf();
  v5 = CreatePrivateObjectSecurity(
         *(PSECURITY_DESCRIPTOR *)(*((_QWORD *)a2 + 35) + 352LL),
         pSecurityDescriptor,
         &NewDescriptor,
         1,
         hObject,
         &stru_18013DDE8);
  ImpersonatePrinterClient(v4);
  CloseHandle(hObject);
  if ( !v5 )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreatePrinterSecurityDescriptor",
      L"CreatePrivateObjectSecurity failed.  Error %d",
      LastError);
    return 0;
  }
  v8 = NewDescriptor;
  v14 = NewDescriptor;
  if ( pSecurityDescriptor
    && GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision)
    && (pControl & 8) == 0 )
  {
    v9 = 0;
  }
  else
  {
    v9 = 1;
    if ( !pSecurityDescriptor )
    {
      GetSecurityDescriptorDacl(v8, &bDaclPresent, &pDacl, &bDaclDefaulted);
      RemoveDummyAceFromPrinter(pDacl);
    }
  }
  v10 = (PSID *)((char *)a2 + 472);
  if ( (*((_DWORD *)a2 + 38) & 0x8000) != 0
    || !RtlEqualSid(*v10, pLocalSystemSid) && !RtlEqualSid(*v10, gRestrictedSpoolerServiceSid) )
  {
    FixPrinterSecurityDescriptor(&v14, (void **)a2 + 59, 1u, 0xF000Cu, v9);
    return v14;
  }
  ActiveSessionSidViaBroker = GetActiveSessionSidViaBroker(&v16);
  if ( ActiveSessionSidViaBroker >= 0 )
  {
    FixPrinterSecurityDescriptor(&v14, &v16, 1u, 0xF000Cu, v9);
    DllFreeSplMem(v16);
    return v14;
  }
  SplLogPrinterEvent(
    &LOCAL_ADDPRN_FAILED,
    L"CreatePrinterSecurityDescriptor, GetActiveSessionSidViaBroker",
    (unsigned __int16)ActiveSessionSidViaBroker,
    *((const unsigned __int16 **)a2 + 3),
    *((_DWORD *)a2 + 34));
  return v8;
}

```

## disassembly

```asm
0x1800982c8  mov     [rsp-28h+arg_0], rbx
0x1800982cd  push    rbp
0x1800982ce  push    rsi
0x1800982cf  push    rdi
0x1800982d0  push    r12
0x1800982d2  push    r14
0x1800982d4  mov     rbp, rsp
0x1800982d7  sub     rsp, 60h
0x1800982db  xor     eax, eax
0x1800982dd  mov     [rbp+hObject], 0
0x1800982e5  mov     r14, rcx
0x1800982e8  mov     [rbp+pControl], ax
0x1800982ec  lea     rcx, [rbp+hObject]; TokenHandle
0x1800982f0  mov     [rbp+dwRevision], eax
0x1800982f3  mov     rsi, rdx
0x1800982f6  mov     [rbp+NewDescriptor], 0
0x1800982fe  mov     [rbp+bDaclPresent], 0
0x180098305  mov     [rbp+pDacl], 0
0x18009830d  mov     [rbp+bDaclDefaulted], 0
0x180098314  mov     [rbp+var_18], 0
0x18009831c  call    GetTokenHandle
0x180098321  test    eax, eax
0x180098323  jz      loc_1800984B1
0x180098329  call    cs:__imp_RevertToPrinterSelf
0x18009832f  mov     rdx, [rbp+hObject]
0x180098333  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x180098337  mov     rcx, [rsi+118h]
0x18009833e  mov     rdi, rax
0x180098341  lea     rax, stru_18013DDE8
0x180098348  mov     r12d, 1
0x18009834e  mov     [rsp+60h+GenericMapping], rax; GenericMapping
0x180098353  mov     r9d, r12d; IsDirectoryObject
0x180098356  mov     [rsp+60h+Token], rdx; Token
0x18009835b  mov     rdx, r14; CreatorDescriptor
0x18009835e  mov     rcx, [rcx+160h]; ParentDescriptor
0x180098365  call    cs:__imp_CreatePrivateObjectSecurity
0x18009836b  mov     rcx, rdi; hToken
0x18009836e  mov     ebx, eax
0x180098370  call    cs:__imp_ImpersonatePrinterClient
0x180098376  mov     rcx, [rbp+hObject]; hObject
0x18009837a  call    cs:__imp_CloseHandle
0x180098380  test    ebx, ebx
0x180098382  jnz     short loc_1800983A7
0x180098384  call    cs:__imp_GetLastError
0x18009838a  mov     r8d, eax
0x18009838d  lea     rdx, aCreateprivateo; "CreatePrivateObjectSecurity failed.  Er"...
0x180098394  lea     rcx, aCreateprinters_1; "CreatePrinterSecurityDescriptor"
0x18009839b  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800983a0  xor     eax, eax
0x1800983a2  jmp     loc_1800984B6
0x1800983a7  mov     rbx, [rbp+NewDescriptor]
0x1800983ab  mov     [rbp+var_28], rbx
0x1800983af  test    r14, r14
0x1800983b2  jz      short loc_1800983D3
0x1800983b4  lea     r8, [rbp+dwRevision]; lpdwRevision
0x1800983b8  mov     rcx, r14; pSecurityDescriptor
0x1800983bb  lea     rdx, [rbp+pControl]; pControl
0x1800983bf  call    cs:__imp_GetSecurityDescriptorControl
0x1800983c5  test    eax, eax
0x1800983c7  jz      short loc_1800983D3
0x1800983c9  test    byte ptr [rbp+pControl], 8
0x1800983cd  jnz     short loc_1800983D3
0x1800983cf  xor     edi, edi
0x1800983d1  jmp     short loc_1800983F9
0x1800983d3  mov     edi, r12d
0x1800983d6  test    r14, r14
0x1800983d9  jnz     short loc_1800983F9
0x1800983db  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800983df  mov     rcx, rbx; pSecurityDescriptor
0x1800983e2  lea     r8, [rbp+pDacl]; pDacl
0x1800983e6  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800983ea  call    cs:__imp_GetSecurityDescriptorDacl
0x1800983f0  mov     rcx, [rbp+pDacl]; pAcl
0x1800983f4  call    ?RemoveDummyAceFromPrinter@@YAXPEAU_ACL@@@Z; RemoveDummyAceFromPrinter(_ACL *)
0x1800983f9  test    dword ptr [rsi+98h], 8000h
0x180098403  lea     r14, [rsi+1D8h]
0x18009840a  jnz     loc_180098492
0x180098410  mov     rdx, cs:?pLocalSystemSid@@3PEAXEA; Sid2
0x180098417  mov     rcx, [r14]; Sid1
0x18009841a  call    cs:__imp_RtlEqualSid
0x180098420  test    al, al
0x180098422  jnz     short loc_180098438
0x180098424  mov     rdx, cs:?gRestrictedSpoolerServiceSid@@3PEAXEA; Sid2
0x18009842b  mov     rcx, [r14]; Sid1
0x18009842e  call    cs:__imp_RtlEqualSid
0x180098434  test    al, al
0x180098436  jz      short loc_180098492
0x180098438  lea     rcx, [rbp+var_18]; void **
0x18009843c  call    ?GetActiveSessionSidViaBroker@@YAJPEAPEAX@Z; GetActiveSessionSidViaBroker(void * *)
0x180098441  test    eax, eax
0x180098443  jns     short loc_18009846C
0x180098445  mov     r9, [rsi+18h]; unsigned __int16 *
0x180098449  lea     rdx, aCreateprinters; "CreatePrinterSecurityDescriptor, GetAct"...
0x180098450  movzx   r8d, ax; unsigned int
0x180098454  lea     rcx, LOCAL_ADDPRN_FAILED; struct _EVENT_DESCRIPTOR *
0x18009845b  mov     eax, [rsi+88h]
0x180098461  mov     dword ptr [rsp+60h+Token], eax; unsigned int
0x180098465  call    ?SplLogPrinterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBGK1K@Z; SplLogPrinterEvent(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ushort const *,ulong)
0x18009846a  jmp     short loc_1800984B3
0x18009846c  mov     r9d, 0F000Ch; unsigned int
0x180098472  mov     dword ptr [rsp+60h+Token], edi; int
0x180098476  mov     r8d, r12d; unsigned int
0x180098479  lea     rdx, [rbp+var_18]; void **
0x18009847d  lea     rcx, [rbp+var_28]; void **
0x180098481  call    ?FixPrinterSecurityDescriptor@@YAKPEAPEAX0KKH@Z; FixPrinterSecurityDescriptor(void * *,void * *,ulong,ulong,int)
0x180098486  mov     rcx, [rbp+var_18]
0x18009848a  call    cs:__imp_DllFreeSplMem
0x180098490  jmp     short loc_1800984AB
0x180098492  mov     r9d, 0F000Ch; unsigned int
0x180098498  mov     dword ptr [rsp+60h+Token], edi; int
0x18009849c  mov     r8d, r12d; unsigned int
0x18009849f  lea     rcx, [rbp+var_28]; void **
0x1800984a3  mov     rdx, r14; void **
0x1800984a6  call    ?FixPrinterSecurityDescriptor@@YAKPEAPEAX0KKH@Z; FixPrinterSecurityDescriptor(void * *,void * *,ulong,ulong,int)
0x1800984ab  mov     rbx, [rbp+var_28]
0x1800984af  jmp     short loc_1800984B3
0x1800984b1  xor     ebx, ebx
0x1800984b3  mov     rax, rbx
0x1800984b6  mov     rbx, [rsp+60h+arg_0]
0x1800984be  add     rsp, 60h
0x1800984c2  pop     r14
0x1800984c4  pop     r12
0x1800984c6  pop     rdi
0x1800984c7  pop     rsi
0x1800984c8  pop     rbp
0x1800984c9  retn
```
