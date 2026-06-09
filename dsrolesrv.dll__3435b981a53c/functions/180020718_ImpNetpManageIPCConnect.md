# ImpNetpManageIPCConnect

- ea: `0x180020718`
- end: `0x18002082f`
- name: `ImpNetpManageIPCConnect`
- size: `279`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800100c0`
- `0x180011240`
- `0x180012460`
- `0x1800202c0`
- `0x180022898`

## callees

- `0x180020718`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207e5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002081b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002081b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020734`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020734`
- `netjoin!NetpManageIPCConnect` at `0x180020755`
- `netjoin!NetpManageIPCConnect` at `0x18002079b`
- `netjoin!NetpManageIPCConnect` at `0x1800207c3`
- `netjoin!NetpManageIPCConnect` at `0x180020755`
- `netjoin!NetpManageIPCConnect` at `0x18002079b`
- `netjoin!NetpManageIPCConnect` at `0x1800207c3`

## string_xrefs

- `0x1800207eb`: `Failed to impersonate caller, error %lu\n`
- `0x18002077b`: `ImpNetpManageIPCConnect: Initial open attempt failed(0x%lx), retrying\n`
- `0x1800207a1`: `ImpNetpManageIPCConnect: forcible connection attempt returned: 0x%lx\n`
- `0x1800207d2`: `ImpNetpManageIPCConnect: Failed to reopen connection 0x%lx\n`
- `0x180020806`: `ImpNetpManageIPCConnect: Successfully reopened connection\n`

## pseudocode

```c
__int64 __fastcall ImpNetpManageIPCConnect(void *a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  int v5; // edi
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  DWORD LastError; // eax

  v5 = 0;
  if ( a1 )
  {
    if ( !ImpersonateLoggedOnUser(a1) )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(4, "Failed to impersonate caller, error %lu\n", LastError);
      return 5;
    }
    v5 = 1;
  }
  v9 = NetpManageIPCConnect(a2, a3, a4, a5);
  v10 = v9;
  if ( (v9 == 1219 || v9 == 53) && (a5 & 1) != 0 )
  {
    DsRolepLogPrintRoutine(4, "ImpNetpManageIPCConnect: Initial open attempt failed(0x%lx), retrying\n", v9);
    v11 = NetpManageIPCConnect(a2, a3, a4, 34);
    DsRolepLogPrintRoutine(1, "ImpNetpManageIPCConnect: forcible connection attempt returned: 0x%lx\n", v11);
    v12 = NetpManageIPCConnect(a2, a3, a4, a5);
    v10 = v12;
    if ( v12 )
      DsRolepLogPrintRoutine(1, "ImpNetpManageIPCConnect: Failed to reopen connection 0x%lx\n", v12);
    else
      DsRolepLogPrintRoutine(4, "ImpNetpManageIPCConnect: Successfully reopened connection\n");
  }
  if ( v5 )
    RevertToSelf();
  return v10;
}

```

## disassembly

```asm
0x180020718  push    rbx
0x18002071a  push    rbp
0x18002071b  push    rdi
0x18002071c  push    r14
0x18002071e  push    r15
0x180020720  sub     rsp, 20h
0x180020724  xor     edi, edi
0x180020726  mov     rbp, r9
0x180020729  mov     r14, r8
0x18002072c  mov     r15, rdx
0x18002072f  test    rcx, rcx
0x180020732  jz      short loc_180020747
0x180020734  call    cs:__imp_ImpersonateLoggedOnUser
0x18002073a  test    eax, eax
0x18002073c  jz      loc_1800207E5
0x180020742  mov     edi, 1
0x180020747  mov     r9d, [rsp+48h+arg_20]
0x18002074c  mov     r8, rbp
0x18002074f  mov     rdx, r14
0x180020752  mov     rcx, r15
0x180020755  call    cs:__imp_NetpManageIPCConnect
0x18002075b  mov     ebx, eax
0x18002075d  cmp     eax, 4C3h
0x180020762  jz      short loc_18002076D
0x180020764  cmp     eax, 35h ; '5'
0x180020767  jnz     loc_180020817
0x18002076d  test    byte ptr [rsp+48h+arg_20], 1
0x180020772  jz      loc_180020817
0x180020778  mov     r8d, eax
0x18002077b  lea     rdx, aImpnetpmanagei; "ImpNetpManageIPCConnect: Initial open a"...
0x180020782  mov     ecx, 4
0x180020787  call    DsRolepLogPrintRoutine
0x18002078c  mov     r9d, 22h ; '"'
0x180020792  mov     r8, rbp
0x180020795  mov     rdx, r14
0x180020798  mov     rcx, r15
0x18002079b  call    cs:__imp_NetpManageIPCConnect
0x1800207a1  lea     rdx, aImpnetpmanagei_0; "ImpNetpManageIPCConnect: forcible conne"...
0x1800207a8  mov     ecx, 1
0x1800207ad  mov     r8d, eax
0x1800207b0  call    DsRolepLogPrintRoutine
0x1800207b5  mov     r9d, [rsp+48h+arg_20]
0x1800207ba  mov     r8, rbp
0x1800207bd  mov     rdx, r14
0x1800207c0  mov     rcx, r15
0x1800207c3  call    cs:__imp_NetpManageIPCConnect
0x1800207c9  mov     ebx, eax
0x1800207cb  test    eax, eax
0x1800207cd  jz      short loc_180020806
0x1800207cf  mov     r8d, eax
0x1800207d2  lea     rdx, aImpnetpmanagei_2; "ImpNetpManageIPCConnect: Failed to reop"...
0x1800207d9  mov     ecx, 1
0x1800207de  call    DsRolepLogPrintRoutine
0x1800207e3  jmp     short loc_180020817
0x1800207e5  call    cs:__imp_GetLastError
0x1800207eb  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x1800207f2  mov     ecx, 4
0x1800207f7  mov     r8d, eax
0x1800207fa  call    DsRolepLogPrintRoutine
0x1800207ff  mov     ebx, 5
0x180020804  jmp     short loc_180020821
0x180020806  lea     rdx, aImpnetpmanagei_1; "ImpNetpManageIPCConnect: Successfully r"...
0x18002080d  mov     ecx, 4
0x180020812  call    DsRolepLogPrintRoutine
0x180020817  test    edi, edi
0x180020819  jz      short loc_180020821
0x18002081b  call    cs:__imp_RevertToSelf
0x180020821  mov     eax, ebx
0x180020823  add     rsp, 20h
0x180020827  pop     r15
0x180020829  pop     r14
0x18002082b  pop     rdi
0x18002082c  pop     rbp
0x18002082d  pop     rbx
0x18002082e  retn
```
