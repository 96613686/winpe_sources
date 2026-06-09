# CuipWaitForDesktopToBeReady(void)

- ea: `0x14000f7dc`
- end: `0x14000f8b8`
- name: `?CuipWaitForDesktopToBeReady@@YAKXZ`
- size: `220`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14001adb0`

## callees

- `0x14000f7dc`
- `0x14000fbec`
- `0x140013928`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000f81c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000f81c`
- `WMsgAPI!WmsgSendMessage` at `0x14000f83e`
- `WMsgAPI!WmsgSendMessage` at `0x14000f83e`
- `ntdll!RtlNtStatusToDosError` at `0x14000f879`
- `ntdll!RtlNtStatusToDosError` at `0x14000f879`

## pseudocode

```c
__int64 CuipWaitForDesktopToBeReady(void)
{
  DWORD CurrentProcessId; // eax
  ULONG v1; // ebx
  NTSTATUS Status; // [rsp+30h] [rbp+8h] BYREF

  Status = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
  CurrentProcessId = GetCurrentProcessId();
  v1 = WmsgSendMessage(NtCurrentPeb()->SessionId, 1282, CurrentProcessId, &Status);
  if ( !v1 )
  {
    if ( Status >= 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 37, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
      return v1;
    }
    v1 = RtlNtStatusToDosError(Status);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x14000f7dc  mov     [rsp+arg_8], rbx
0x14000f7e1  push    rsi
0x14000f7e2  sub     rsp, 20h
0x14000f7e6  mov     [rsp+28h+Status], 0
0x14000f7ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7f5  lea     rsi, WPP_GLOBAL_Control
0x14000f7fc  cmp     rcx, rsi
0x14000f7ff  jz      short loc_14000F81C
0x14000f801  test    byte ptr [rcx+1Ch], 4
0x14000f805  jz      short loc_14000F81C
0x14000f807  mov     rcx, [rcx+10h]
0x14000f80b  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000f812  mov     edx, 23h ; '#'
0x14000f817  call    WPP_SF_
0x14000f81c  call    cs:__imp_GetCurrentProcessId
0x14000f822  mov     rcx, gs:60h
0x14000f82b  lea     r9, [rsp+28h+Status]
0x14000f830  mov     r8d, eax
0x14000f833  mov     edx, 502h
0x14000f838  mov     ecx, [rcx+2C0h]
0x14000f83e  call    cs:__imp_WmsgSendMessage
0x14000f844  mov     ebx, eax
0x14000f846  test    eax, eax
0x14000f848  jnz     short loc_14000F881
0x14000f84a  mov     ecx, [rsp+28h+Status]; Status
0x14000f84e  test    ecx, ecx
0x14000f850  js      short loc_14000F879
0x14000f852  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f859  cmp     rcx, rsi
0x14000f85c  jz      short loc_14000F8AB
0x14000f85e  test    byte ptr [rcx+1Ch], 4
0x14000f862  jz      short loc_14000F8AB
0x14000f864  mov     rcx, [rcx+10h]
0x14000f868  lea     edx, [rax+25h]
0x14000f86b  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000f872  call    WPP_SF_
0x14000f877  jmp     short loc_14000F8AB
0x14000f879  call    cs:__imp_RtlNtStatusToDosError
0x14000f87f  mov     ebx, eax
0x14000f881  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f888  cmp     rcx, rsi
0x14000f88b  jz      short loc_14000F8AB
0x14000f88d  test    byte ptr [rcx+1Ch], 4
0x14000f891  jz      short loc_14000F8AB
0x14000f893  mov     rcx, [rcx+10h]
0x14000f897  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000f89e  mov     edx, 24h ; '$'
0x14000f8a3  mov     r9d, ebx
0x14000f8a6  call    WPP_SF_D
0x14000f8ab  mov     eax, ebx
0x14000f8ad  mov     rbx, [rsp+28h+arg_8]
0x14000f8b2  add     rsp, 20h
0x14000f8b6  pop     rsi
0x14000f8b7  retn
```
