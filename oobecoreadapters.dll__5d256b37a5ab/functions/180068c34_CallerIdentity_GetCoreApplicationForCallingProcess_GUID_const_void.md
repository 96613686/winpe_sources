# CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)

- ea: `0x180068c34`
- end: `0x180068cd6`
- name: `?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `162`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180068cdc`

## callees

- `0x180068c34`
- `0x180068dec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180068c6e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180068c6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068cbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068cbe`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180068c9e`
- `twinapi.appcore!__imp_CoreQueryApplicationService` at `0x180068c9e`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180068c7f`
- `twinapi.appcore!__imp_CoreIsApplicationServiceSupported` at `0x180068c7f`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreApplicationForCallingProcess(
        CallerIdentity *this,
        const struct _GUID *a2,
        void **a3)
{
  int CallingProcessHandle; // ebx
  __int64 ProcessId; // rsi
  char *v6; // rcx
  HANDLE Process; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)&a2->Data1 = 0;
  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, (unsigned int)&Process, a3);
  if ( CallingProcessHandle >= 0 )
  {
    ProcessId = GetProcessId(Process);
    CallingProcessHandle = CoreIsApplicationServiceSupported(ProcessId, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1);
    if ( CallingProcessHandle >= 0 )
      CallingProcessHandle = CoreQueryApplicationService(
                               (unsigned int)ProcessId,
                               &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1,
                               &GUID_17b0e613_942a_422d_904c_f90dc71a7dae,
                               a2);
  }
  v6 = (char *)Process;
  Process = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x180068c34  mov     rax, rsp
0x180068c37  mov     [rax+10h], rbx
0x180068c3b  mov     [rax+18h], rsi
0x180068c3f  mov     [rax+8], rcx
0x180068c43  push    rdi
0x180068c44  sub     rsp, 20h
0x180068c48  mov     rdi, rdx
0x180068c4b  mov     qword ptr [rdx], 0
0x180068c52  lea     rdx, [rax+8]; unsigned int
0x180068c56  mov     qword ptr [rax+8], 0
0x180068c5e  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x180068c63  mov     ebx, eax
0x180068c65  test    eax, eax
0x180068c67  js      short loc_180068CA6
0x180068c69  mov     rcx, [rsp+28h+Process]; Process
0x180068c6e  call    cs:__imp_GetProcessId
0x180068c74  mov     ecx, eax
0x180068c76  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180068c7d  mov     esi, eax
0x180068c7f  call    cs:__imp_CoreIsApplicationServiceSupported
0x180068c85  mov     ebx, eax
0x180068c87  test    eax, eax
0x180068c89  js      short loc_180068CA6
0x180068c8b  mov     r9, rdi
0x180068c8e  lea     r8, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180068c95  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180068c9c  mov     ecx, esi
0x180068c9e  call    cs:__imp_CoreQueryApplicationService
0x180068ca4  mov     ebx, eax
0x180068ca6  mov     rcx, [rsp+28h+Process]; hObject
0x180068cab  mov     [rsp+28h+Process], 0
0x180068cb4  lea     rax, [rcx-1]
0x180068cb8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180068cbc  ja      short loc_180068CC4
0x180068cbe  call    cs:__imp_CloseHandle
0x180068cc4  mov     rsi, [rsp+28h+arg_10]
0x180068cc9  mov     eax, ebx
0x180068ccb  mov     rbx, [rsp+28h+arg_8]
0x180068cd0  add     rsp, 20h
0x180068cd4  pop     rdi
0x180068cd5  retn
```
