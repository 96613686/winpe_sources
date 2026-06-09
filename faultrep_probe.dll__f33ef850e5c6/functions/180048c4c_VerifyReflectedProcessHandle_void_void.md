# VerifyReflectedProcessHandle(void *,void *)

- ea: `0x180048c4c`
- end: `0x180048d6e`
- name: `?VerifyReflectedProcessHandle@@YAHPEAX0@Z`
- size: `290`
- prototype: `__int64 __fastcall(HANDLE Process, HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180047adc`

## callees

- `0x180009ed8`
- `0x180048c4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180048c82`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180048cfd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180048c82`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180048cfd`
- `ntdll!NtQueryInformationProcess` at `0x180048cd0`
- `ntdll!NtQueryInformationProcess` at `0x180048cd0`

## pseudocode

```c
__int64 __fastcall VerifyReflectedProcessHandle(HANDLE Process, HANDLE ProcessHandle)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  DWORD ProcessId; // eax
  _BYTE ProcessInformation[32]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v9; // [rsp+50h] [rbp-18h]

  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v9 = 0;
  if ( !Process || !ProcessHandle )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v5 = 16;
    goto LABEL_19;
  }
  if ( !GetProcessId(ProcessHandle) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v5 = 17;
    goto LABEL_19;
  }
  if ( NtQueryInformationProcess(ProcessHandle, ProcessBasicInformation, ProcessInformation, 0x30u, 0) < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v5 = 18;
    goto LABEL_19;
  }
  ProcessId = GetProcessId(Process);
  if ( ProcessId == *((_QWORD *)&v9 + 1) )
    return 1;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 19;
LABEL_19:
    WPP_SF_(v4[2], v5, &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180048c4c  mov     rax, rsp
0x180048c4f  mov     [rax+8], rbx
0x180048c53  push    rdi
0x180048c54  sub     rsp, 60h
0x180048c58  xorps   xmm0, xmm0
0x180048c5b  mov     rbx, rdx
0x180048c5e  mov     rdi, rcx
0x180048c61  movups  xmmword ptr [rax-38h], xmm0
0x180048c65  movups  xmmword ptr [rax-28h], xmm0
0x180048c69  movups  xmmword ptr [rax-18h], xmm0
0x180048c6d  test    rcx, rcx
0x180048c70  jz      loc_180048D33
0x180048c76  test    rdx, rdx
0x180048c79  jz      loc_180048D33
0x180048c7f  mov     rcx, rdx; Process
0x180048c82  call    cs:__imp_GetProcessId
0x180048c88  test    eax, eax
0x180048c8a  jnz     short loc_180048CB7
0x180048c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c93  lea     rax, WPP_GLOBAL_Control
0x180048c9a  cmp     rcx, rax
0x180048c9d  jz      loc_180048D61
0x180048ca3  test    byte ptr [rcx+1Ch], 4
0x180048ca7  jz      loc_180048D61
0x180048cad  mov     edx, 11h
0x180048cb2  jmp     loc_180048D51
0x180048cb7  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180048cbd  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x180048cc6  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x180048ccb  xor     edx, edx; ProcessInformationClass
0x180048ccd  mov     rcx, rbx; ProcessHandle
0x180048cd0  call    cs:__imp_NtQueryInformationProcess
0x180048cd6  test    eax, eax
0x180048cd8  jns     short loc_180048CFA
0x180048cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180048ce1  lea     rax, WPP_GLOBAL_Control
0x180048ce8  cmp     rcx, rax
0x180048ceb  jz      short loc_180048D61
0x180048ced  test    byte ptr [rcx+1Ch], 1
0x180048cf1  jz      short loc_180048D61
0x180048cf3  mov     edx, 12h
0x180048cf8  jmp     short loc_180048D51
0x180048cfa  mov     rcx, rdi; Process
0x180048cfd  call    cs:__imp_GetProcessId
0x180048d03  mov     eax, eax
0x180048d05  cmp     rax, [rsp+68h+var_10]
0x180048d0a  jz      short loc_180048D2C
0x180048d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048d13  lea     rax, WPP_GLOBAL_Control
0x180048d1a  cmp     rcx, rax
0x180048d1d  jz      short loc_180048D61
0x180048d1f  test    byte ptr [rcx+1Ch], 1
0x180048d23  jz      short loc_180048D61
0x180048d25  mov     edx, 13h
0x180048d2a  jmp     short loc_180048D51
0x180048d2c  mov     eax, 1
0x180048d31  jmp     short loc_180048D63
0x180048d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180048d3a  lea     rax, WPP_GLOBAL_Control
0x180048d41  cmp     rcx, rax
0x180048d44  jz      short loc_180048D61
0x180048d46  test    byte ptr [rcx+1Ch], 4
0x180048d4a  jz      short loc_180048D61
0x180048d4c  mov     edx, 10h
0x180048d51  mov     rcx, [rcx+10h]
0x180048d55  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x180048d5c  call    WPP_SF_
0x180048d61  xor     eax, eax
0x180048d63  mov     rbx, [rsp+68h+arg_0]
0x180048d68  add     rsp, 60h
0x180048d6c  pop     rdi
0x180048d6d  retn
```
