# CCrashReport::OnWerUICallback(_WER_UI_CALLBACK_INPUT * const)

- ea: `0x1800144d4`
- end: `0x180014591`
- name: `?OnWerUICallback@CCrashReport@@AEAAHQEAU_WER_UI_CALLBACK_INPUT@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(CCrashReport *__hidden this, struct _WER_UI_CALLBACK_INPUT *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001611c`

## callees

- `0x1800144d4`
- `0x1800149b0`
- `0x1800199f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001455a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001455a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180014580`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180014580`
- `wer!WerpAddTerminationReason` at `0x180014571`
- `wer!WerpAddTerminationReason` at `0x180014571`

## pseudocode

```c
__int64 __fastcall CCrashReport::OnWerUICallback(CCrashReport *this, struct _WER_UI_CALLBACK_INPUT *const a2)
{
  void *v3; // rdx
  DWORD ProcessId; // eax

  *(_DWORD *)(*((_QWORD *)this + 5) + 176LL) = -2145681408;
  if ( *(_DWORD *)a2 == 3 )
  {
    v3 = (void *)*((_QWORD *)this + 6);
    if ( (unsigned __int64)v3 + 1 > 1 )
    {
      CLocalDumpGenerator::GenerateDump(
        (__int64)this + 3616,
        v3,
        *((_DWORD *)this + 185),
        (char *)this + 824,
        (__int64)this + 976);
      if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0 && (*((_BYTE *)this + 4272) & 1) == 0 )
      {
        ProcessId = GetProcessId(*((HANDLE *)this + 6));
        WerpAddTerminationReason(ProcessId, 0, L"WerCrashReportWerUI");
        TerminateProcess(*((HANDLE *)this + 6), 0xFFu);
      }
    }
  }
  else if ( *(_DWORD *)a2 == 24 )
  {
    CCrashReport::ProcessRelease(this);
  }
  return 1;
}

```

## disassembly

```asm
0x1800144d4  push    rbx
0x1800144d6  sub     rsp, 30h
0x1800144da  mov     rax, [rcx+28h]
0x1800144de  mov     rbx, rcx
0x1800144e1  mov     dword ptr [rax+0B0h], 801B8000h
0x1800144eb  cmp     dword ptr [rdx], 3
0x1800144ee  jz      short loc_180014503
0x1800144f0  cmp     dword ptr [rdx], 18h
0x1800144f3  jnz     loc_180014586
0x1800144f9  call    ?ProcessRelease@CCrashReport@@AEAAHXZ; CCrashReport::ProcessRelease(void)
0x1800144fe  jmp     loc_180014586
0x180014503  mov     rdx, [rcx+30h]
0x180014507  lea     rax, [rdx+1]
0x18001450b  cmp     rax, 1
0x18001450f  jbe     short loc_180014586
0x180014511  mov     r8d, [rbx+2E4h]
0x180014518  lea     rax, [rcx+3D0h]
0x18001451f  lea     r9, [rcx+338h]
0x180014526  mov     [rsp+38h+var_10], 0
0x18001452f  add     rcx, 0E20h
0x180014536  mov     [rsp+38h+var_18], rax
0x18001453b  call    ?GenerateDump@CLocalDumpGenerator@@QEAAJPEAXKPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CLocalDumpGenerator::GenerateDump(void *,ulong,_EXCEPTION_RECORD *,_CONTEXT *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180014540  mov     rax, [rbx+28h]
0x180014544  test    byte ptr [rax+0ECh], 4
0x18001454b  jnz     short loc_180014586
0x18001454d  test    byte ptr [rbx+10B0h], 1
0x180014554  jnz     short loc_180014586
0x180014556  mov     rcx, [rbx+30h]; Process
0x18001455a  call    cs:__imp_GetProcessId
0x180014560  mov     r9d, 1
0x180014566  lea     r8, aWercrashreport_1; "WerCrashReportWerUI"
0x18001456d  mov     ecx, eax
0x18001456f  xor     edx, edx
0x180014571  call    cs:__imp_WerpAddTerminationReason
0x180014577  mov     rcx, [rbx+30h]; hProcess
0x18001457b  mov     edx, 0FFh; uExitCode
0x180014580  call    cs:__imp_TerminateProcess
0x180014586  mov     eax, 1
0x18001458b  add     rsp, 30h
0x18001458f  pop     rbx
0x180014590  retn
```
