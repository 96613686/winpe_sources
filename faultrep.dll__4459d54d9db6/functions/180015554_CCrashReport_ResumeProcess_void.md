# CCrashReport::ResumeProcess(void)

- ea: `0x180015554`
- end: `0x180015694`
- name: `?ResumeProcess@CCrashReport@@AEAAXXZ`
- size: `320`
- prototype: `void __fastcall(CCrashReport *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800143a8`
- `0x1800149b0`
- `0x180014c34`

## callees

- `0x180009f40`
- `0x180015554`
- `0x1800165e4`
- `0x180016964`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001560c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001560c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800155c4`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800155c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015662`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015662`
- `ntdll!NtResumeProcess` at `0x1800155ee`
- `ntdll!NtResumeProcess` at `0x1800155ee`
- `ntdll!NtSuspendThread` at `0x18001559a`
- `ntdll!NtSuspendThread` at `0x18001559a`

## pseudocode

```c
void __fastcall CCrashReport::ResumeProcess(CCrashReport *this)
{
  void *v2; // rcx
  unsigned int v3; // esi
  ULONG v4; // ebx
  DWORD ThreadId; // eax
  __int64 v6; // r8
  NTSTATUS v7; // ebx
  DWORD ProcessId; // eax
  unsigned int v9; // eax
  ULONG PreviousSuspendCount; // [rsp+60h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 5) && *((_QWORD *)this + 6) != -1 && *((_QWORD *)this + 6) != 0 )
  {
    if ( *((_DWORD *)this + 6) )
    {
      v2 = (void *)*((_QWORD *)this + 7);
      PreviousSuspendCount = 0;
      v3 = NtSuspendThread(v2, &PreviousSuspendCount);
      *((_DWORD *)this + 6) = v3 >> 31;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v4 = PreviousSuspendCount;
        ThreadId = GetThreadId(*((HANDLE *)this + 7));
        WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, v6, ThreadId, v3, v4);
      }
    }
    v7 = NtResumeProcess(*((HANDLE *)this + 6));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      ProcessId = GetProcessId(*((HANDLE *)this + 6));
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        120,
        WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        ProcessId,
        v7);
    }
    v9 = 0;
    if ( v7 != -1073741558 )
      v9 = v7;
    *((_DWORD *)this + 5) = v9 >> 31;
  }
  if ( *((_DWORD *)this + 1218)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    GetTickCount();
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
}

```

## disassembly

```asm
0x180015554  push    rbx
0x180015556  push    rsi
0x180015557  push    rdi
0x180015558  push    r15
0x18001555a  sub     rsp, 38h
0x18001555e  cmp     dword ptr [rcx+14h], 0
0x180015562  lea     r15, WPP_GLOBAL_Control
0x180015569  mov     rdi, rcx
0x18001556c  jz      loc_180015646
0x180015572  mov     rax, [rcx+30h]
0x180015576  inc     rax
0x180015579  cmp     rax, 1
0x18001557d  jbe     loc_180015646
0x180015583  cmp     dword ptr [rcx+18h], 0
0x180015587  jz      short loc_1800155EA
0x180015589  mov     rcx, [rcx+38h]; ThreadHandle
0x18001558d  lea     rdx, [rsp+58h+PreviousSuspendCount]; PreviousSuspendCount
0x180015592  mov     [rsp+58h+PreviousSuspendCount], 0
0x18001559a  call    cs:__imp_NtSuspendThread
0x1800155a0  mov     ecx, eax
0x1800155a2  mov     esi, eax
0x1800155a4  shr     ecx, 1Fh
0x1800155a7  mov     [rdi+18h], ecx
0x1800155aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155b1  cmp     rcx, r15
0x1800155b4  jz      short loc_1800155EA
0x1800155b6  test    byte ptr [rcx+1Ch], 4
0x1800155ba  jz      short loc_1800155EA
0x1800155bc  mov     rcx, [rdi+38h]; Thread
0x1800155c0  mov     ebx, [rsp+58h+PreviousSuspendCount]
0x1800155c4  call    cs:__imp_GetThreadId
0x1800155ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155d1  mov     edx, 77h ; 'w'
0x1800155d6  mov     [rsp+58h+var_30], ebx
0x1800155da  mov     r9d, eax
0x1800155dd  mov     [rsp+58h+var_38], esi
0x1800155e1  mov     rcx, [rcx+10h]
0x1800155e5  call    WPP_SF_DdD
0x1800155ea  mov     rcx, [rdi+30h]; ProcessHandle
0x1800155ee  call    cs:__imp_NtResumeProcess
0x1800155f4  mov     ebx, eax
0x1800155f6  mov     rax, cs:WPP_GLOBAL_Control
0x1800155fd  cmp     rax, r15
0x180015600  jz      short loc_180015635
0x180015602  test    byte ptr [rax+1Ch], 4
0x180015606  jz      short loc_180015635
0x180015608  mov     rcx, [rdi+30h]; Process
0x18001560c  call    cs:__imp_GetProcessId
0x180015612  mov     rcx, cs:WPP_GLOBAL_Control
0x180015619  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180015620  mov     edx, 78h ; 'x'
0x180015625  mov     [rsp+58h+var_38], ebx
0x180015629  mov     r9d, eax
0x18001562c  mov     rcx, [rcx+10h]
0x180015630  call    WPP_SF_Dd
0x180015635  xor     eax, eax
0x180015637  cmp     ebx, 0C000010Ah
0x18001563d  cmovnz  eax, ebx
0x180015640  shr     eax, 1Fh
0x180015643  mov     [rdi+14h], eax
0x180015646  mov     ebx, [rdi+1308h]
0x18001564c  test    ebx, ebx
0x18001564e  jz      short loc_18001568A
0x180015650  mov     rax, cs:WPP_GLOBAL_Control
0x180015657  cmp     rax, r15
0x18001565a  jz      short loc_18001568A
0x18001565c  test    byte ptr [rax+1Ch], 4
0x180015660  jz      short loc_18001568A
0x180015662  call    cs:__imp_GetTickCount
0x180015668  mov     rcx, cs:WPP_GLOBAL_Control
0x18001566f  sub     eax, ebx
0x180015671  mov     r9d, [rdi+2E0h]
0x180015678  mov     [rsp+58h+var_30], eax
0x18001567c  mov     [rsp+58h+var_38], r9d
0x180015681  mov     rcx, [rcx+10h]
0x180015685  call    WPP_SF_DDD
0x18001568a  add     rsp, 38h
0x18001568e  pop     r15
0x180015690  pop     rdi
0x180015691  pop     rsi
0x180015692  pop     rbx
0x180015693  retn
```
