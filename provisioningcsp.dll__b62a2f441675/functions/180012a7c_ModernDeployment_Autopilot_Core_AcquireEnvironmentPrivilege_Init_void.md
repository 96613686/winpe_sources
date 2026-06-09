# ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)

- ea: `0x180012a7c`
- end: `0x180012b11`
- name: `?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ`
- size: `149`
- prototype: `__int64 __fastcall(PVOID *ReturnedState)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001279c`
- `0x1800128d0`
- `0x180012be0`

## callees

- `0x180012a7c`
- `0x180012bb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ab5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ab5`
- `ntdll!RtlAcquirePrivilege` at `0x180012adf`
- `ntdll!RtlAcquirePrivilege` at `0x180012adf`
- `ntdll!RtlReleasePrivilege` at `0x180012aa7`
- `ntdll!RtlReleasePrivilege` at `0x180012aa7`

## pseudocode

```c
int __fastcall ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(PVOID *ReturnedState)
{
  PVOID v1; // rsi
  DWORD LastError; // ebx
  NTSTATUS v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ULONG Privilege; // [rsp+30h] [rbp+8h] BYREF

  v1 = *ReturnedState;
  if ( *ReturnedState )
  {
    LastError = GetLastError();
    RtlReleasePrivilege(v1);
    SetLastError(LastError);
  }
  Privilege = 22;
  *ReturnedState = 0;
  v4 = RtlAcquirePrivilege(&Privilege, 1u, 0, ReturnedState);
  if ( v4 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(retaddr, v5, v6, (const char *)(unsigned int)v4, v8);
}

```

## disassembly

```asm
0x180012a7c  mov     [rsp+arg_8], rbx
0x180012a81  mov     [rsp+arg_10], rsi
0x180012a86  push    rdi; int
0x180012a87  sub     rsp, 20h
0x180012a8b  mov     rsi, [rcx]
0x180012a8e  mov     rdi, rcx
0x180012a91  test    rsi, rsi
0x180012a94  jz      short loc_180012AC1
0x180012a96  call    cs:__imp_GetLastError
0x180012a9d  nop     dword ptr [rax+rax+00h]
0x180012aa2  mov     rcx, rsi; ReturnedState
0x180012aa5  mov     ebx, eax
0x180012aa7  call    cs:__imp_RtlReleasePrivilege
0x180012aae  nop     dword ptr [rax+rax+00h]
0x180012ab3  mov     ecx, ebx; dwErrCode
0x180012ab5  call    cs:__imp_SetLastError
0x180012abc  nop     dword ptr [rax+rax+00h]
0x180012ac1  xor     r8d, r8d; Flags
0x180012ac4  mov     [rsp+28h+Privilege], 16h
0x180012acc  mov     r9, rdi; ReturnedState
0x180012acf  mov     qword ptr [rdi], 0
0x180012ad6  lea     rcx, [rsp+28h+Privilege]; Privilege
0x180012adb  lea     edx, [r8+1]; NumPriv
0x180012adf  call    cs:__imp_RtlAcquirePrivilege
0x180012ae6  nop     dword ptr [rax+rax+00h]
0x180012aeb  test    eax, eax
0x180012aed  jns     short loc_180012AFE
0x180012aef  mov     rcx, [rsp+28h]; this
0x180012af4  mov     r9d, eax; char *
0x180012af7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180012afc  jmp     short loc_180012B00
0x180012afe  xor     eax, eax
0x180012b00  mov     rbx, [rsp+28h+arg_8]
0x180012b05  mov     rsi, [rsp+28h+arg_10]
0x180012b0a  add     rsp, 20h
0x180012b0e  pop     rdi
0x180012b0f  retn
```
