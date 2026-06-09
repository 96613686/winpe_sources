# SendWnfNotificationToProcess

- ea: `0x14011aca0`
- end: `0x14011ae16`
- name: `SendWnfNotificationToProcess`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400e3334`

## callees

- `0x1400045ec`
- `0x14003c1a4`
- `0x14011aca0`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x14011ad46`
- `ntoskrnl!ZwOpenProcess` at `0x14011ad46`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14011add8`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14011add8`
- `ntoskrnl!ZwClose` at `0x14011adf2`
- `ntoskrnl!ZwClose` at `0x14011adf2`
- `watchdog!WdLogSingleEntry1` at `0x14011ad61`
- `watchdog!WdLogSingleEntry1` at `0x14011ad61`

## string_xrefs

- `0x14011ad71`: `Failed to open process handle for process id 0x%I64x`

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
  v4 = *(_QWORD *)(a1 + 72);
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
    WdLogGlobalForLineNumber = 27640;
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
0x14011aca0  mov     rax, rsp
0x14011aca3  mov     [rax+8], rbx
0x14011aca7  mov     [rax+18h], rdi
0x14011acab  mov     [rax+10h], rdx
0x14011acaf  push    rbp
0x14011acb0  lea     rbp, [rax-5Fh]
0x14011acb4  sub     rsp, 90h
0x14011acbb  mov     rdx, rcx
0x14011acbe  mov     [rbp+57h+ProcessHandle], 0
0x14011acc6  mov     rcx, [rcx+48h]
0x14011acca  mov     rdi, r8
0x14011accd  mov     eax, [rcx+198h]
0x14011acd3  shr     eax, 8
0x14011acd6  test    al, 1
0x14011acd8  jz      short loc_14011ACE7
0x14011acda  mov     r9, r8
0x14011acdd  call    SendWnfNotificationToVmProcess
0x14011ace2  jmp     loc_14011AE00
0x14011ace7  xorps   xmm0, xmm0
0x14011acea  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x14011acee  test    byte ptr [rcx+198h], 1
0x14011acf5  jz      short loc_14011AD08
0x14011acf7  mov     rax, cs:?g_pVidMmSystemProcess@@3PEAVVIDMM_PROCESS@@EA; VIDMM_PROCESS * g_pVidMmSystemProcess
0x14011acfe  mov     rcx, [rax+18h]
0x14011ad02  mov     [rbp+57h+ClientId.UniqueProcess], rcx
0x14011ad06  jmp     short loc_14011AD10
0x14011ad08  mov     rax, [rdx+18h]
0x14011ad0c  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x14011ad10  lea     r9, [rbp+57h+ClientId]; ClientId
0x14011ad14  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14011ad1c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14011ad20  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14011ad28  mov     edx, 2000000h; DesiredAccess
0x14011ad2d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14011ad35  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14011ad39  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x14011ad41  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14011ad46  call    cs:__imp_ZwOpenProcess
0x14011ad4d  nop     dword ptr [rax+rax+00h]
0x14011ad52  mov     ebx, eax
0x14011ad54  test    eax, eax
0x14011ad56  jns     short loc_14011ADAE
0x14011ad58  mov     rdx, [rbp+57h+ClientId.UniqueProcess]
0x14011ad5c  mov     ecx, 1
0x14011ad61  call    cs:__imp_WdLogSingleEntry1
0x14011ad68  nop     dword ptr [rax+rax+00h]
0x14011ad6d  mov     rcx, [rbp+57h+ClientId.UniqueProcess]
0x14011ad71  lea     r9, aFailedToOpenPr; "Failed to open process handle for proce"...
0x14011ad78  mov     [rsp+90h+var_58], 0
0x14011ad81  mov     edx, 40000h
0x14011ad86  mov     [rsp+90h+var_60], 0
0x14011ad8f  mov     [rsp+90h+var_68], 0
0x14011ad98  mov     [rsp+90h+var_70], rcx
0x14011ad9d  mov     cs:WdLogGlobalForLineNumber, 6BF8h
0x14011ada7  call    DxgkLogInternalTriageEvent
0x14011adac  jmp     short loc_14011ADFE
0x14011adae  mov     rax, [rbp+57h+ProcessHandle]
0x14011adb2  lea     rcx, WNF_DX_VIDMM_TRIM_NOTIFICATION
0x14011adb9  xor     r9d, r9d
0x14011adbc  mov     dword ptr [rsp+90h+var_60], 0
0x14011adc4  mov     dword ptr [rsp+90h+var_68], 0
0x14011adcc  mov     rdx, rdi
0x14011adcf  mov     [rsp+90h+var_70], rax
0x14011add4  lea     r8d, [r9+18h]
0x14011add8  call    cs:__imp_ZwUpdateWnfStateData
0x14011addf  nop     dword ptr [rax+rax+00h]
0x14011ade4  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14011ade8  xor     ebx, ebx
0x14011adea  cmp     eax, 0C0000189h
0x14011adef  cmovnz  ebx, eax
0x14011adf2  call    cs:__imp_ZwClose
0x14011adf9  nop     dword ptr [rax+rax+00h]
0x14011adfe  mov     eax, ebx
0x14011ae00  lea     r11, [rsp+90h+var_s0]
0x14011ae08  mov     rbx, [r11+10h]
0x14011ae0c  mov     rdi, [r11+20h]
0x14011ae10  mov     rsp, r11
0x14011ae13  pop     rbp
0x14011ae14  retn
```
