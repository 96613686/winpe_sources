# VidSchNotifyDeviceRemoved

- ea: `0x140052ae0`
- end: `0x140052c41`
- name: `VidSchNotifyDeviceRemoved`
- size: `353`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140055c74`

## callees

- `0x1400045ec`
- `0x140052ae0`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x140052b36`
- `ntoskrnl!ZwOpenProcess` at `0x140052b36`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140052bae`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140052bae`
- `ntoskrnl!ZwClose` at `0x140052c0d`
- `ntoskrnl!ZwClose` at `0x140052c0d`
- `ntoskrnl!IoFreeWorkItem` at `0x140052c21`
- `ntoskrnl!IoFreeWorkItem` at `0x140052c21`
- `watchdog!WdLogSingleEntry1` at `0x140052b4d`
- `watchdog!WdLogSingleEntry1` at `0x140052bc9`
- `watchdog!WdLogSingleEntry1` at `0x140052b4d`
- `watchdog!WdLogSingleEntry1` at `0x140052bc9`

## string_xrefs

- `0x140052b5d`: `Failed to open process handle for process id 0x%I64x`
- `0x140052bda`: `UpdateWnfStateData failed in VidSchNotifyDeviceRemoved: 0x%x`

## pseudocode

```c
void __fastcall VidSchNotifyDeviceRemoved(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  int v4; // ecx
  int v5; // r8d
  int updated; // eax
  __int64 v7; // rbx
  int v8; // ecx
  int v9; // r8d
  _CLIENT_ID ClientId; // [rsp+50h] [rbp+7h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  int v12; // [rsp+B8h] [rbp+6Fh] BYREF
  void *ProcessHandle; // [rsp+C0h] [rbp+77h] BYREF

  ClientId.UniqueProcess = Context;
  ProcessHandle = 0;
  ClientId.UniqueThread = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenProcess(&ProcessHandle, 0x2000000u, &ObjectAttributes, &ClientId) >= 0 )
  {
    v12 = 1;
    updated = ZwUpdateWnfStateData(&WNF_DX_DEVICE_REMOVAL, &v12, 4);
    if ( updated < 0 )
    {
      v7 = updated;
      WdLogSingleEntry1(1, updated);
      WdLogGlobalForLineNumber = 4744;
      DxgkLogInternalTriageEvent(
        v8,
        0x40000,
        v9,
        (unsigned int)L"UpdateWnfStateData failed in VidSchNotifyDeviceRemoved: 0x%x",
        v7,
        0,
        0,
        0);
    }
  }
  else
  {
    WdLogSingleEntry1(1, ClientId.UniqueProcess);
    WdLogGlobalForLineNumber = 4727;
    DxgkLogInternalTriageEvent(
      v4,
      0x40000,
      v5,
      (unsigned int)L"Failed to open process handle for process id 0x%I64x",
      (__int64)ClientId.UniqueProcess,
      0,
      0,
      0);
  }
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( IoWorkItem )
    IoFreeWorkItem(IoWorkItem);
}

```

## disassembly

```asm
0x140052ae0  mov     [rsp-8+arg_0], rbx
0x140052ae5  push    rbp
0x140052ae6  push    rsi
0x140052ae7  push    rdi
0x140052ae8  lea     rbp, [rsp-47h]
0x140052aed  sub     rsp, 90h
0x140052af4  xor     esi, esi
0x140052af6  mov     [rbp+57h+ClientId.UniqueProcess], rdx
0x140052afa  mov     rdi, r8
0x140052afd  mov     [rbp+57h+ProcessHandle], rsi
0x140052b01  xorps   xmm0, xmm0
0x140052b04  mov     [rbp+57h+ClientId.UniqueThread], rsi
0x140052b08  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140052b0c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x140052b10  mov     edx, 2000000h; DesiredAccess
0x140052b15  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x140052b19  lea     r9, [rbp+57h+ClientId]; ClientId
0x140052b1d  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140052b25  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140052b29  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140052b31  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140052b36  call    cs:__imp_ZwOpenProcess
0x140052b3d  nop     dword ptr [rax+rax+00h]
0x140052b42  test    eax, eax
0x140052b44  jns     short loc_140052B84
0x140052b46  mov     rdx, [rbp+57h+ClientId.UniqueProcess]
0x140052b4a  lea     ecx, [rsi+1]
0x140052b4d  call    cs:__imp_WdLogSingleEntry1
0x140052b54  nop     dword ptr [rax+rax+00h]
0x140052b59  mov     rax, [rbp+57h+ClientId.UniqueProcess]
0x140052b5d  lea     r9, aFailedToOpenPr; "Failed to open process handle for proce"...
0x140052b64  mov     [rsp+0A0h+var_68], rsi
0x140052b69  mov     [rsp+0A0h+var_70], rsi
0x140052b6e  mov     [rsp+0A0h+var_78], rsi
0x140052b73  mov     [rsp+0A0h+var_80], rax
0x140052b78  mov     cs:WdLogGlobalForLineNumber, 1277h
0x140052b82  jmp     short loc_140052BFA
0x140052b84  mov     rax, [rbp+57h+ProcessHandle]
0x140052b88  lea     rdx, [rbp+57h+arg_8]
0x140052b8c  xor     r9d, r9d
0x140052b8f  mov     dword ptr [rsp+0A0h+var_70], esi
0x140052b93  mov     dword ptr [rsp+0A0h+var_78], esi
0x140052b97  lea     rcx, WNF_DX_DEVICE_REMOVAL
0x140052b9e  mov     [rbp+57h+arg_8], 1
0x140052ba5  mov     [rsp+0A0h+var_80], rax
0x140052baa  lea     r8d, [r9+4]
0x140052bae  call    cs:__imp_ZwUpdateWnfStateData
0x140052bb5  nop     dword ptr [rax+rax+00h]
0x140052bba  test    eax, eax
0x140052bbc  jns     short loc_140052C04
0x140052bbe  movsxd  rbx, eax
0x140052bc1  mov     ecx, 1
0x140052bc6  mov     rdx, rbx
0x140052bc9  call    cs:__imp_WdLogSingleEntry1
0x140052bd0  nop     dword ptr [rax+rax+00h]
0x140052bd5  mov     [rsp+0A0h+var_68], rsi
0x140052bda  lea     r9, aUpdatewnfstate; "UpdateWnfStateData failed in VidSchNoti"...
0x140052be1  mov     [rsp+0A0h+var_70], rsi
0x140052be6  mov     [rsp+0A0h+var_78], rsi
0x140052beb  mov     [rsp+0A0h+var_80], rbx
0x140052bf0  mov     cs:WdLogGlobalForLineNumber, 1288h
0x140052bfa  mov     edx, 40000h
0x140052bff  call    DxgkLogInternalTriageEvent
0x140052c04  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140052c08  test    rcx, rcx
0x140052c0b  jz      short loc_140052C19
0x140052c0d  call    cs:__imp_ZwClose
0x140052c14  nop     dword ptr [rax+rax+00h]
0x140052c19  test    rdi, rdi
0x140052c1c  jz      short loc_140052C2D
0x140052c1e  mov     rcx, rdi; IoWorkItem
0x140052c21  call    cs:__imp_IoFreeWorkItem
0x140052c28  nop     dword ptr [rax+rax+00h]
0x140052c2d  mov     rbx, [rsp+0A0h+arg_0]
0x140052c35  add     rsp, 90h
0x140052c3c  pop     rdi
0x140052c3d  pop     rsi
0x140052c3e  pop     rbp
0x140052c3f  retn
```
