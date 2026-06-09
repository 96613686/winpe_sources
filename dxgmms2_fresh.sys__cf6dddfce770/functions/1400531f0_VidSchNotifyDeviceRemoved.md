# VidSchNotifyDeviceRemoved

- ea: `0x1400531f0`
- end: `0x140053351`
- name: `VidSchNotifyDeviceRemoved`
- size: `353`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140056544`

## callees

- `0x140004268`
- `0x1400531f0`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x140053246`
- `ntoskrnl!ZwOpenProcess` at `0x140053246`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400532be`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400532be`
- `ntoskrnl!ZwClose` at `0x14005331d`
- `ntoskrnl!ZwClose` at `0x14005331d`
- `ntoskrnl!IoFreeWorkItem` at `0x140053331`
- `ntoskrnl!IoFreeWorkItem` at `0x140053331`
- `watchdog!WdLogSingleEntry1` at `0x14005325d`
- `watchdog!WdLogSingleEntry1` at `0x1400532d9`
- `watchdog!WdLogSingleEntry1` at `0x14005325d`
- `watchdog!WdLogSingleEntry1` at `0x1400532d9`

## string_xrefs

- `0x14005326d`: `Failed to open process handle for process id 0x%I64x`
- `0x1400532ea`: `UpdateWnfStateData failed in VidSchNotifyDeviceRemoved: 0x%x`

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
0x1400531f0  mov     [rsp-8+arg_0], rbx
0x1400531f5  push    rbp
0x1400531f6  push    rsi
0x1400531f7  push    rdi
0x1400531f8  lea     rbp, [rsp-47h]
0x1400531fd  sub     rsp, 90h
0x140053204  xor     esi, esi
0x140053206  mov     [rbp+57h+ClientId.UniqueProcess], rdx
0x14005320a  mov     rdi, r8
0x14005320d  mov     [rbp+57h+ProcessHandle], rsi
0x140053211  xorps   xmm0, xmm0
0x140053214  mov     [rbp+57h+ClientId.UniqueThread], rsi
0x140053218  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005321c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x140053220  mov     edx, 2000000h; DesiredAccess
0x140053225  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x140053229  lea     r9, [rbp+57h+ClientId]; ClientId
0x14005322d  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140053235  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140053239  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140053241  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140053246  call    cs:__imp_ZwOpenProcess
0x14005324d  nop     dword ptr [rax+rax+00h]
0x140053252  test    eax, eax
0x140053254  jns     short loc_140053294
0x140053256  mov     rdx, [rbp+57h+ClientId.UniqueProcess]
0x14005325a  lea     ecx, [rsi+1]
0x14005325d  call    cs:__imp_WdLogSingleEntry1
0x140053264  nop     dword ptr [rax+rax+00h]
0x140053269  mov     rax, [rbp+57h+ClientId.UniqueProcess]
0x14005326d  lea     r9, aFailedToOpenPr; "Failed to open process handle for proce"...
0x140053274  mov     [rsp+0A0h+var_68], rsi
0x140053279  mov     [rsp+0A0h+var_70], rsi
0x14005327e  mov     [rsp+0A0h+var_78], rsi
0x140053283  mov     [rsp+0A0h+var_80], rax
0x140053288  mov     cs:WdLogGlobalForLineNumber, 1277h
0x140053292  jmp     short loc_14005330A
0x140053294  mov     rax, [rbp+57h+ProcessHandle]
0x140053298  lea     rdx, [rbp+57h+arg_8]
0x14005329c  xor     r9d, r9d
0x14005329f  mov     dword ptr [rsp+0A0h+var_70], esi
0x1400532a3  mov     dword ptr [rsp+0A0h+var_78], esi
0x1400532a7  lea     rcx, WNF_DX_DEVICE_REMOVAL
0x1400532ae  mov     [rbp+57h+arg_8], 1
0x1400532b5  mov     [rsp+0A0h+var_80], rax
0x1400532ba  lea     r8d, [r9+4]
0x1400532be  call    cs:__imp_ZwUpdateWnfStateData
0x1400532c5  nop     dword ptr [rax+rax+00h]
0x1400532ca  test    eax, eax
0x1400532cc  jns     short loc_140053314
0x1400532ce  movsxd  rbx, eax
0x1400532d1  mov     ecx, 1
0x1400532d6  mov     rdx, rbx
0x1400532d9  call    cs:__imp_WdLogSingleEntry1
0x1400532e0  nop     dword ptr [rax+rax+00h]
0x1400532e5  mov     [rsp+0A0h+var_68], rsi
0x1400532ea  lea     r9, aUpdatewnfstate; "UpdateWnfStateData failed in VidSchNoti"...
0x1400532f1  mov     [rsp+0A0h+var_70], rsi
0x1400532f6  mov     [rsp+0A0h+var_78], rsi
0x1400532fb  mov     [rsp+0A0h+var_80], rbx
0x140053300  mov     cs:WdLogGlobalForLineNumber, 1288h
0x14005330a  mov     edx, 40000h
0x14005330f  call    DxgkLogInternalTriageEvent
0x140053314  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140053318  test    rcx, rcx
0x14005331b  jz      short loc_140053329
0x14005331d  call    cs:__imp_ZwClose
0x140053324  nop     dword ptr [rax+rax+00h]
0x140053329  test    rdi, rdi
0x14005332c  jz      short loc_14005333D
0x14005332e  mov     rcx, rdi; IoWorkItem
0x140053331  call    cs:__imp_IoFreeWorkItem
0x140053338  nop     dword ptr [rax+rax+00h]
0x14005333d  mov     rbx, [rsp+0A0h+arg_0]
0x140053345  add     rsp, 90h
0x14005334c  pop     rdi
0x14005334d  pop     rsi
0x14005334e  pop     rbp
0x14005334f  retn
```
