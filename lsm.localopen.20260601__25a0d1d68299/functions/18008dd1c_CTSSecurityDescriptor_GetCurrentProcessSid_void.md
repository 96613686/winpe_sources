# CTSSecurityDescriptor::GetCurrentProcessSid(void * *)

- ea: `0x18008dd1c`
- end: `0x18008de35`
- name: `?GetCurrentProcessSid@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18008db9c`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x180011440`
- `0x180012650`
- `0x18008dd1c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008dd6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008dd6c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008dd5c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008dd5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008dd43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008dd43`

## string_xrefs

- `0x18008dd8e`: `OpenProcessToken failed: 0x%x in %s`
- `0x18008ddfd`: `CTSSecurityDescriptor::GetCurrentProcessSid`
- `0x18008ddf3`: `IUserName->GetUserSid failed: 0x%x in %s`

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
  if ( OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_6:
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
    goto LABEL_13;
  }
  _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x in %s", v5, "CTSSecurityDescriptor::GetCurrentProcessSid");
LABEL_13:
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v10);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18008dd1c  mov     rax, rsp
0x18008dd1f  mov     [rax+10h], rbx
0x18008dd23  mov     [rax+20h], rsi
0x18008dd27  mov     [rax+8], rcx
0x18008dd2b  push    rdi
0x18008dd2c  sub     rsp, 20h
0x18008dd30  mov     rsi, rdx
0x18008dd33  mov     qword ptr [rax+18h], 0
0x18008dd3b  mov     qword ptr [rax+8], 0
0x18008dd43  call    cs:__imp_GetCurrentProcess
0x18008dd4a  nop     dword ptr [rax+rax+00h]
0x18008dd4f  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18008dd54  mov     edx, 0Eh; DesiredAccess
0x18008dd59  mov     rcx, rax; ProcessHandle
0x18008dd5c  call    cs:__imp_OpenProcessToken
0x18008dd63  nop     dword ptr [rax+rax+00h]
0x18008dd68  test    eax, eax
0x18008dd6a  jnz     short loc_18008DD97
0x18008dd6c  call    cs:__imp_GetLastError
0x18008dd73  nop     dword ptr [rax+rax+00h]
0x18008dd78  mov     ebx, eax
0x18008dd7a  test    eax, eax
0x18008dd7c  jle     short loc_18008DD87
0x18008dd7e  movzx   ebx, ax
0x18008dd81  or      ebx, 80070000h
0x18008dd87  test    ebx, ebx
0x18008dd89  jns     short loc_18008DD97
0x18008dd8b  mov     r8d, ebx
0x18008dd8e  lea     rdx, aOpenprocesstok; "OpenProcessToken failed: 0x%x in %s"
0x18008dd95  jmp     short loc_18008DDFD
0x18008dd97  lea     rcx, [rsp+28h+arg_0]; struct IUserName **
0x18008dd9c  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18008dda1  mov     ebx, eax
0x18008dda3  test    eax, eax
0x18008dda5  jns     short loc_18008DDB0
0x18008dda7  lea     rdx, aGetinstanceofu; "GetInstanceOfUserName failed: 0x%x in %"...
0x18008ddae  jmp     short loc_18008DDFA
0x18008ddb0  mov     rdi, [rsp+28h+arg_0]
0x18008ddb5  xor     r8d, r8d
0x18008ddb8  mov     rdx, [rsp+28h+TokenHandle]
0x18008ddbd  mov     rcx, rdi
0x18008ddc0  mov     rax, [rdi]
0x18008ddc3  mov     rax, [rax+18h]
0x18008ddc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ddcc  mov     ebx, eax
0x18008ddce  test    eax, eax
0x18008ddd0  jns     short loc_18008DDDB
0x18008ddd2  lea     rdx, aIusernameIniti; "IUserName->Initialize failed: 0x%x in %"...
0x18008ddd9  jmp     short loc_18008DDFA
0x18008dddb  mov     rax, [rdi]
0x18008ddde  mov     rdx, rsi
0x18008dde1  mov     rcx, rdi
0x18008dde4  mov     rax, [rax+48h]
0x18008dde8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dded  mov     ebx, eax
0x18008ddef  test    eax, eax
0x18008ddf1  jns     short loc_18008DE0E
0x18008ddf3  lea     rdx, aIusernameGetus; "IUserName->GetUserSid failed: 0x%x in %"...
0x18008ddfa  mov     r8d, eax
0x18008ddfd  lea     r9, aCtssecuritydes_0; "CTSSecurityDescriptor::GetCurrentProces"...
0x18008de04  mov     ecx, 8; int
0x18008de09  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008de0e  lea     rcx, [rsp+28h+arg_0]
0x18008de13  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18008de18  lea     rcx, [rsp+28h+TokenHandle]; this
0x18008de1d  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18008de22  mov     rsi, [rsp+28h+arg_18]
0x18008de27  mov     eax, ebx
0x18008de29  mov     rbx, [rsp+28h+arg_8]
0x18008de2e  add     rsp, 20h
0x18008de32  pop     rdi
0x18008de33  retn
```
