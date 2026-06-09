# SendWnfNotificationToProcess

- ea: `0x14011e358`
- end: `0x14011e4ce`
- name: `SendWnfNotificationToProcess`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14011e234`

## callees

- `0x140004268`
- `0x14003aeb4`
- `0x14011e358`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x14011e3fe`
- `ntoskrnl!ZwOpenProcess` at `0x14011e3fe`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14011e490`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14011e490`
- `ntoskrnl!ZwClose` at `0x14011e4aa`
- `ntoskrnl!ZwClose` at `0x14011e4aa`
- `watchdog!WdLogSingleEntry1` at `0x14011e419`
- `watchdog!WdLogSingleEntry1` at `0x14011e419`

## string_xrefs

- `0x14011e429`: `Failed to open process handle for process id 0x%I64x`

## pseudocode

```c
__int64 __fastcall SendWnfNotificationToProcess(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  NTSTATUS v7; // ebx
  int v8; // r8d
  NTSTATUS updated; // eax
  struct _CLIENT_ID ClientId; // [rsp+58h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp+27h] BYREF
  void *ProcessHandle; // [rsp+B0h] [rbp+6Fh] BYREF

  ProcessHandle = 0;
  v4 = *(_QWORD *)(a1 + 80);
  if ( (*(_DWORD *)(v4 + 408) & 0x100) != 0 )
    return SendWnfNotificationToVmProcess(v4, a1, a3, a3);
  ClientId = 0;
  if ( (*(_BYTE *)(v4 + 408) & 1) != 0 )
    ClientId.UniqueProcess = (HANDLE)*((_QWORD *)g_pVidMmSystemProcess + 3);
  else
    ClientId.UniqueProcess = *(HANDLE *)(a1 + 24);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenProcess(&ProcessHandle, 0x2000000u, &ObjectAttributes, &ClientId);
  if ( v7 >= 0 )
  {
    updated = ZwUpdateWnfStateData(&WNF_DX_VIDMM_TRIM_NOTIFICATION, a3, 24);
    v7 = 0;
    if ( updated != -1073741431 )
      v7 = updated;
    ZwClose(ProcessHandle);
  }
  else
  {
    WdLogSingleEntry1(1, ClientId.UniqueProcess);
    WdLogGlobalForLineNumber = 27902;
    DxgkLogInternalTriageEvent(
      ClientId.UniqueProcess,
      0x40000,
      v8,
      (unsigned int)L"Failed to open process handle for process id 0x%I64x",
      (__int64)ClientId.UniqueProcess,
      0,
      0,
      0);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14011e358  mov     rax, rsp
0x14011e35b  mov     [rax+8], rbx
0x14011e35f  mov     [rax+18h], rdi
0x14011e363  mov     [rax+10h], rdx
0x14011e367  push    rbp
0x14011e368  lea     rbp, [rax-5Fh]
0x14011e36c  sub     rsp, 90h
0x14011e373  mov     rdx, rcx
0x14011e376  mov     [rbp+57h+ProcessHandle], 0
0x14011e37e  mov     rcx, [rcx+50h]
0x14011e382  mov     rdi, r8
0x14011e385  mov     eax, [rcx+198h]
0x14011e38b  shr     eax, 8
0x14011e38e  test    al, 1
0x14011e390  jz      short loc_14011E39F
0x14011e392  mov     r9, r8
0x14011e395  call    SendWnfNotificationToVmProcess
0x14011e39a  jmp     loc_14011E4B8
0x14011e39f  xorps   xmm0, xmm0
0x14011e3a2  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x14011e3a6  test    byte ptr [rcx+198h], 1
0x14011e3ad  jz      short loc_14011E3C0
0x14011e3af  mov     rax, cs:?g_pVidMmSystemProcess@@3PEAVVIDMM_PROCESS@@EA; VIDMM_PROCESS * g_pVidMmSystemProcess
0x14011e3b6  mov     rcx, [rax+18h]
0x14011e3ba  mov     [rbp+57h+ClientId.UniqueProcess], rcx
0x14011e3be  jmp     short loc_14011E3C8
0x14011e3c0  mov     rax, [rdx+18h]
0x14011e3c4  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x14011e3c8  lea     r9, [rbp+57h+ClientId]; ClientId
0x14011e3cc  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14011e3d4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14011e3d8  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14011e3e0  mov     edx, 2000000h; DesiredAccess
0x14011e3e5  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14011e3ed  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14011e3f1  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x14011e3f9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14011e3fe  call    cs:__imp_ZwOpenProcess
0x14011e405  nop     dword ptr [rax+rax+00h]
0x14011e40a  mov     ebx, eax
0x14011e40c  test    eax, eax
0x14011e40e  jns     short loc_14011E466
0x14011e410  mov     rdx, [rbp+57h+ClientId.UniqueProcess]
0x14011e414  mov     ecx, 1
0x14011e419  call    cs:__imp_WdLogSingleEntry1
0x14011e420  nop     dword ptr [rax+rax+00h]
0x14011e425  mov     rcx, [rbp+57h+ClientId.UniqueProcess]
0x14011e429  lea     r9, aFailedToOpenPr; "Failed to open process handle for proce"...
0x14011e430  mov     [rsp+90h+var_58], 0
0x14011e439  mov     edx, 40000h
0x14011e43e  mov     [rsp+90h+var_60], 0
0x14011e447  mov     [rsp+90h+var_68], 0
0x14011e450  mov     [rsp+90h+var_70], rcx
0x14011e455  mov     cs:WdLogGlobalForLineNumber, 6CFEh
0x14011e45f  call    DxgkLogInternalTriageEvent
0x14011e464  jmp     short loc_14011E4B6
0x14011e466  mov     rax, [rbp+57h+ProcessHandle]
0x14011e46a  lea     rcx, WNF_DX_VIDMM_TRIM_NOTIFICATION
0x14011e471  xor     r9d, r9d
0x14011e474  mov     dword ptr [rsp+90h+var_60], 0
0x14011e47c  mov     dword ptr [rsp+90h+var_68], 0
0x14011e484  mov     rdx, rdi
0x14011e487  mov     [rsp+90h+var_70], rax
0x14011e48c  lea     r8d, [r9+18h]
0x14011e490  call    cs:__imp_ZwUpdateWnfStateData
0x14011e497  nop     dword ptr [rax+rax+00h]
0x14011e49c  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14011e4a0  xor     ebx, ebx
0x14011e4a2  cmp     eax, 0C0000189h
0x14011e4a7  cmovnz  ebx, eax
0x14011e4aa  call    cs:__imp_ZwClose
0x14011e4b1  nop     dword ptr [rax+rax+00h]
0x14011e4b6  mov     eax, ebx
0x14011e4b8  lea     r11, [rsp+90h+var_s0]
0x14011e4c0  mov     rbx, [r11+10h]
0x14011e4c4  mov     rdi, [r11+20h]
0x14011e4c8  mov     rsp, r11
0x14011e4cb  pop     rbp
0x14011e4cc  retn
```
