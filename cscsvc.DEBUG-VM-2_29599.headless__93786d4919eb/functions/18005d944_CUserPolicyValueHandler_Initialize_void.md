# CUserPolicyValueHandler::Initialize(void *)

- ea: `0x18005d944`
- end: `0x18005da27`
- name: `?Initialize@CUserPolicyValueHandler@@QEAAJPEAX@Z`
- size: `227`
- prototype: `__int64 __fastcall(CUserPolicyValueHandler *__hidden this, PSID pSourceSid)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18005ebec`

## callees

- `0x18001b150`
- `0x18002f10c`
- `0x18003443c`
- `0x180036394`
- `0x18005d6ac`
- `0x18005d944`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005da0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005da0b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005d9bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005d9bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005d95d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005d95d`

## pseudocode

```c
__int64 __fastcall CUserPolicyValueHandler::Initialize(CUserPolicyValueHandler *this, PSID pSourceSid)
{
  int SidCopy; // ebx
  HANDLE Thread; // rax

  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 232), 0) )
  {
    *((_DWORD *)this + 68) = 1;
    SidCopy = CscSec_CreateSidCopy(pSourceSid, (void **)this + 27);
    if ( SidCopy >= 0 )
    {
      SidCopy = CPolicyValueHandler::Initialize(this);
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      Thread = CreateThread(0, 0, SettingsChgMon_RefreshUserPolicyThreadProc, this, 0, 0);
      if ( Thread )
      {
        CloseHandle(Thread);
      }
      else
      {
        SidCopy = ResultFromLastError();
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids,
            (unsigned int)SidCopy);
        }
        CRefCounted::ReleaseReference(this);
      }
    }
  }
  else
  {
    return (unsigned int)ResultFromLastError();
  }
  return (unsigned int)SidCopy;
}

```

## disassembly

```asm
0x18005d944  mov     [rsp+arg_0], rbx
0x18005d949  push    rdi
0x18005d94a  sub     rsp, 30h
0x18005d94e  mov     rbx, rdx
0x18005d951  mov     rdi, rcx
0x18005d954  add     rcx, 0E8h; lpCriticalSection
0x18005d95b  xor     edx, edx; dwSpinCount
0x18005d95d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005d963  test    eax, eax
0x18005d965  jz      loc_18005DA13
0x18005d96b  lea     rdx, [rdi+0D8h]; void **
0x18005d972  mov     dword ptr [rdi+110h], 1
0x18005d97c  mov     rcx, rbx; pSourceSid
0x18005d97f  call    ?CscSec_CreateSidCopy@@YAJPEAXPEAPEAX@Z; CscSec_CreateSidCopy(void *,void * *)
0x18005d984  mov     ebx, eax
0x18005d986  test    eax, eax
0x18005d988  js      loc_18005DA1A
0x18005d98e  mov     rcx, rdi; pv
0x18005d991  call    ?Initialize@CPolicyValueHandler@@QEAAJXZ; CPolicyValueHandler::Initialize(void)
0x18005d996  mov     ebx, eax
0x18005d998  lock inc dword ptr [rdi+8]
0x18005d99c  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18005d9a5  lea     r8, ?SettingsChgMon_RefreshUserPolicyThreadProc@@YAKPEAX@Z; lpStartAddress
0x18005d9ac  mov     r9, rdi; lpParameter
0x18005d9af  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18005d9b7  xor     edx, edx; dwStackSize
0x18005d9b9  xor     ecx, ecx; lpThreadAttributes
0x18005d9bb  call    cs:__imp_CreateThread
0x18005d9c1  test    rax, rax
0x18005d9c4  jnz     short loc_18005DA08
0x18005d9c6  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005d9cb  mov     ebx, eax
0x18005d9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d9d4  lea     rax, WPP_GLOBAL_Control
0x18005d9db  cmp     rcx, rax
0x18005d9de  jz      short loc_18005D9FE
0x18005d9e0  test    byte ptr [rcx+1Ch], 2
0x18005d9e4  jz      short loc_18005D9FE
0x18005d9e6  mov     rcx, [rcx+10h]
0x18005d9ea  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005d9f1  mov     edx, 19h
0x18005d9f6  mov     r9d, ebx
0x18005d9f9  call    WPP_SF_d
0x18005d9fe  mov     rcx, rdi; this
0x18005da01  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18005da06  jmp     short loc_18005DA1A
0x18005da08  mov     rcx, rax; hObject
0x18005da0b  call    cs:__imp_CloseHandle
0x18005da11  jmp     short loc_18005DA1A
0x18005da13  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005da18  mov     ebx, eax
0x18005da1a  mov     eax, ebx
0x18005da1c  mov     rbx, [rsp+38h+arg_0]
0x18005da21  add     rsp, 30h
0x18005da25  pop     rdi
0x18005da26  retn
```
