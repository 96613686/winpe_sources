# CTSSecurityDescriptor::GetCurrentProcessSid(void * *)

- ea: `0x18008900c`
- end: `0x180089118`
- name: `?GetCurrentProcessSid@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180088ea4`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180009dd0`
- `0x18008900c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089050`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180089046`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180089046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180089033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180089033`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089100`

## string_xrefs

- `0x18008906c`: `OpenProcessToken failed: 0x%x in %s`
- `0x1800890db`: `CTSSecurityDescriptor::GetCurrentProcessSid`
- `0x1800890d1`: `IUserName->GetUserSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::GetCurrentProcessSid(CTSSecurityDescriptor *this, void **a2)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  int InstanceOfUserName; // eax
  const char *v7; // rdx
  struct IUserName *v8; // rdi
  struct IUserName *v10; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  v10 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x in %s", v5, "CTSSecurityDescriptor::GetCurrentProcessSid");
      goto LABEL_13;
    }
  }
  InstanceOfUserName = CUtils::GetInstanceOfUserName(&v10);
  v5 = InstanceOfUserName;
  if ( InstanceOfUserName >= 0 )
  {
    v8 = v10;
    InstanceOfUserName = (*(__int64 (__fastcall **)(struct IUserName *, void *, _QWORD))(*(_QWORD *)v10 + 24LL))(
                           v10,
                           TokenHandle,
                           0);
    v5 = InstanceOfUserName;
    if ( InstanceOfUserName >= 0 )
    {
      InstanceOfUserName = (*(__int64 (__fastcall **)(struct IUserName *, void **))(*(_QWORD *)v8 + 72LL))(v8, a2);
      v5 = InstanceOfUserName;
      if ( InstanceOfUserName >= 0 )
        goto LABEL_13;
      v7 = "IUserName->GetUserSid failed: 0x%x in %s";
    }
    else
    {
      v7 = "IUserName->Initialize failed: 0x%x in %s";
    }
  }
  else
  {
    v7 = "GetInstanceOfUserName failed: 0x%x in %s";
  }
  _DbgPrintMessage(8, v7, (unsigned int)InstanceOfUserName, "CTSSecurityDescriptor::GetCurrentProcessSid");
LABEL_13:
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v10);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18008900c  mov     rax, rsp
0x18008900f  mov     [rax+10h], rbx
0x180089013  mov     [rax+20h], rsi
0x180089017  mov     [rax+8], rcx
0x18008901b  push    rdi
0x18008901c  sub     rsp, 20h
0x180089020  mov     rsi, rdx
0x180089023  mov     qword ptr [rax+18h], 0
0x18008902b  mov     qword ptr [rax+8], 0
0x180089033  call    cs:__imp_GetCurrentProcess
0x180089039  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18008903e  mov     edx, 0Eh; DesiredAccess
0x180089043  mov     rcx, rax; ProcessHandle
0x180089046  call    cs:__imp_OpenProcessToken
0x18008904c  test    eax, eax
0x18008904e  jnz     short loc_180089075
0x180089050  call    cs:__imp_GetLastError
0x180089056  mov     ebx, eax
0x180089058  test    eax, eax
0x18008905a  jle     short loc_180089065
0x18008905c  movzx   ebx, ax
0x18008905f  or      ebx, 80070000h
0x180089065  test    ebx, ebx
0x180089067  jns     short loc_180089075
0x180089069  mov     r8d, ebx
0x18008906c  lea     rdx, aOpenprocesstok; "OpenProcessToken failed: 0x%x in %s"
0x180089073  jmp     short loc_1800890DB
0x180089075  lea     rcx, [rsp+28h+arg_0]; struct IUserName **
0x18008907a  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18008907f  mov     ebx, eax
0x180089081  test    eax, eax
0x180089083  jns     short loc_18008908E
0x180089085  lea     rdx, aGetinstanceofu; "GetInstanceOfUserName failed: 0x%x in %"...
0x18008908c  jmp     short loc_1800890D8
0x18008908e  mov     rdi, [rsp+28h+arg_0]
0x180089093  xor     r8d, r8d
0x180089096  mov     rdx, [rsp+28h+TokenHandle]
0x18008909b  mov     rcx, rdi
0x18008909e  mov     rax, [rdi]
0x1800890a1  mov     rax, [rax+18h]
0x1800890a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800890aa  mov     ebx, eax
0x1800890ac  test    eax, eax
0x1800890ae  jns     short loc_1800890B9
0x1800890b0  lea     rdx, aIusernameIniti; "IUserName->Initialize failed: 0x%x in %"...
0x1800890b7  jmp     short loc_1800890D8
0x1800890b9  mov     rax, [rdi]
0x1800890bc  mov     rdx, rsi
0x1800890bf  mov     rcx, rdi
0x1800890c2  mov     rax, [rax+48h]
0x1800890c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800890cb  mov     ebx, eax
0x1800890cd  test    eax, eax
0x1800890cf  jns     short loc_1800890EC
0x1800890d1  lea     rdx, aIusernameGetus; "IUserName->GetUserSid failed: 0x%x in %"...
0x1800890d8  mov     r8d, eax
0x1800890db  lea     r9, aCtssecuritydes_0; "CTSSecurityDescriptor::GetCurrentProces"...
0x1800890e2  mov     ecx, 8; int
0x1800890e7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800890ec  lea     rcx, [rsp+28h+arg_0]
0x1800890f1  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800890f6  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800890fb  test    rcx, rcx
0x1800890fe  jz      short loc_180089106
0x180089100  call    cs:__imp_CloseHandle
0x180089106  mov     rsi, [rsp+28h+arg_18]
0x18008910b  mov     eax, ebx
0x18008910d  mov     rbx, [rsp+28h+arg_8]
0x180089112  add     rsp, 20h
0x180089116  pop     rdi
0x180089117  retn
```
