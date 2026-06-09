# CHostContext::GetHostPids(std::vector<ulong,std::allocator<ulong>> &)

- ea: `0x18004c204`
- end: `0x18004c288`
- name: `?GetHostPids@CHostContext@@SAJAEAV?$vector@KV?$allocator@K@std@@@std@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001958c`
- `0x180047e74`

## callees

- `0x18004baa4`
- `0x18004c204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c218`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c218`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c26e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c26e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004c238`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004c238`

## pseudocode

```c
__int64 __fastcall CHostContext::GetHostPids(__int64 a1)
{
  __int64 *i; // rcx
  __int64 v3; // rdi
  DWORD ProcessId; // eax
  DWORD *v5; // rdx
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD v9; // [rsp+38h] [rbp+10h] BYREF

  EnterCriticalSection(&HostList);
  for ( i = (__int64 *)qword_1800A4618; i != &qword_1800A4618; i = (__int64 *)v3 )
  {
    v3 = *i;
    ProcessId = GetProcessId((HANDLE)*(i - 2));
    v9 = ProcessId;
    v5 = *(DWORD **)(a1 + 8);
    if ( v5 == *(DWORD **)(a1 + 16) )
    {
      try
      {
        std::vector<unsigned long>::_Emplace_reallocate<unsigned long>(a1, v5, &v9);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x139,
                               (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\hostcontext.cpp",
                               v6);
      }
    }
    else
    {
      *v5 = ProcessId;
      *(_QWORD *)(a1 + 8) += 4LL;
    }
  }
  LeaveCriticalSection(&HostList);
  return 0;
}

```

## disassembly

```asm
0x18004c204  mov     [rsp+arg_0], rbx
0x18004c209  push    rdi
0x18004c20a  sub     rsp, 20h
0x18004c20e  mov     rbx, rcx
0x18004c211  lea     rcx, ?HostList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004c218  call    cs:__imp_EnterCriticalSection
0x18004c21e  mov     rcx, cs:qword_1800A4618
0x18004c225  lea     rax, qword_1800A4618
0x18004c22c  cmp     rcx, rax
0x18004c22f  jz      short loc_18004C267
0x18004c231  mov     rdi, [rcx]
0x18004c234  mov     rcx, [rcx-10h]; Process
0x18004c238  call    cs:__imp_GetProcessId
0x18004c23e  mov     [rsp+28h+arg_8], eax
0x18004c242  mov     rdx, [rbx+8]
0x18004c246  cmp     rdx, [rbx+10h]
0x18004c24a  jz      short loc_18004C255
0x18004c24c  mov     [rdx], eax
0x18004c24e  add     qword ptr [rbx+8], 4
0x18004c253  jmp     short loc_18004C262
0x18004c255  lea     r8, [rsp+28h+arg_8]
0x18004c25a  mov     rcx, rbx
0x18004c25d  call    ??$_Emplace_reallocate@K@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAK$$QEAK@Z; std::vector<ulong>::_Emplace_reallocate<ulong>(ulong * const,ulong &&)
0x18004c262  mov     rcx, rdi
0x18004c265  jmp     short loc_18004C225
0x18004c267  lea     rcx, ?HostList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004c26e  call    cs:__imp_LeaveCriticalSection
0x18004c274  xor     eax, eax
0x18004c276  jmp     short loc_18004C27C
0x18004c278  mov     eax, [rsp+28h+arg_8]
0x18004c27c  mov     rbx, [rsp+28h+arg_0]
0x18004c281  add     rsp, 20h
0x18004c285  pop     rdi
0x18004c286  retn
```
