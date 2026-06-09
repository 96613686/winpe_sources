# HidpFdoSendIdleIrpWorker

- ea: `0x180009d00`
- end: `0x180009ef0`
- name: `HidpFdoSendIdleIrpWorker`
- size: `496`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009d00`
- `0x18000a020`
- `0x18000a15c`
- `0x18000ddc8`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x180009e50`
- `ntoskrnl!IoFreeWorkItem` at `0x180009e50`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180009e41`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x180009e41`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x180009d87`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x180009d87`

## pseudocode

```c
void __fastcall HidpFdoSendIdleIrpWorker(PDEVICE_OBJECT DeviceObject, struct _IO_WORKITEM *Context)
{
  struct _IO_REMOVE_LOCK *v2; // rbx
  char v4; // di
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rax
  NTSTATUS v8; // eax
  int v9; // edx
  int v10; // r8d
  char v11; // al
  int v12; // edx
  int v13; // r8d

  v2 = (struct _IO_REMOVE_LOCK *)((char *)DeviceObject->DeviceExtension + 32);
  v4 = 1;
  v5 = *((_QWORD *)DeviceObject->DeviceExtension + 58);
  v6 = *(_QWORD *)(v5 + 184);
  *(_BYTE *)(v6 - 72) = 15;
  *(_DWORD *)(v6 - 48) = 720939;
  *(_DWORD *)(v6 - 56) = 16;
  *(_QWORD *)(v6 - 40) = v2 + 13;
  v7 = *(_QWORD *)(v5 + 184);
  *(_QWORD *)(v7 - 16) = HidpIdleNotificationRequestComplete;
  *(_QWORD *)(v7 - 8) = v2;
  *(_BYTE *)(v7 - 69) = -32;
  v8 = IoAcquireRemoveLockEx(v2 + 20, "Idle Worker Tag", File, 1u, 0x20u);
  if ( v8 < 0 )
  {
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        *(_QWORD *)&v2[21].Common.Removed,
        2,
        9,
        10,
        (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
        *(_QWORD *)&v2->Common.Removed,
        v8);
    }
  }
  v11 = HidpCallDriver(*(_QWORD *)&v2->Common.Removed, v5);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v4 = 0;
  }
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = v4;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      v13,
      *(_QWORD *)&v2[21].Common.Removed,
      4,
      9,
      11,
      (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
      *(_QWORD *)&v2->Common.Removed,
      v5,
      v11);
  }
  IoReleaseRemoveLockEx(v2 + 20, "Idle Worker Tag", 0x20u);
  IoFreeWorkItem(Context);
}

```

## disassembly

```asm
0x180009d00  push    rbx
0x180009d02  push    rbp
0x180009d03  push    rsi
0x180009d04  push    rdi
0x180009d05  push    r12
0x180009d07  push    r13
0x180009d09  push    r14
0x180009d0b  sub     rsp, 60h
0x180009d0f  mov     rbx, [rcx+40h]
0x180009d13  lea     r8, File; File
0x180009d1a  add     rbx, 20h ; ' '
0x180009d1e  mov     [rsp+98h+RemlockSize], 20h ; ' '; RemlockSize
0x180009d26  mov     r14, rdx
0x180009d29  mov     edi, 1
0x180009d2e  mov     r9d, edi; Line
0x180009d31  lea     rdx, IdleWorkerTag; "Idle Worker Tag"
0x180009d38  mov     rsi, [rbx+1B0h]
0x180009d3f  lea     rax, [rbx+1A0h]
0x180009d46  lea     rbp, [rbx+280h]
0x180009d4d  mov     rcx, [rsi+0B8h]
0x180009d54  mov     byte ptr [rcx-48h], 0Fh
0x180009d58  mov     dword ptr [rcx-30h], 0B002Bh
0x180009d5f  mov     dword ptr [rcx-38h], 10h
0x180009d66  mov     [rcx-28h], rax
0x180009d6a  lea     rcx, HidpIdleNotificationRequestComplete
0x180009d71  mov     rax, [rsi+0B8h]
0x180009d78  mov     [rax-10h], rcx
0x180009d7c  mov     rcx, rbp; RemoveLock
0x180009d7f  mov     [rax-8], rbx
0x180009d83  mov     byte ptr [rax-45h], 0E0h
0x180009d87  call    cs:__imp_IoAcquireRemoveLockEx
0x180009d8e  nop     dword ptr [rax+rax+00h]
0x180009d93  lea     r12, WPP_GLOBAL_Control
0x180009d9a  lea     r13, WPP_RECORDER_INITIALIZED
0x180009da1  lea     r11, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x180009da8  test    eax, eax
0x180009daa  js      loc_180009E6C
0x180009db0  mov     rcx, [rbx]
0x180009db3  mov     rdx, rsi
0x180009db6  call    HidpCallDriver
0x180009dbb  mov     r10, cs:WPP_GLOBAL_Control
0x180009dc2  cmp     r10, r12
0x180009dc5  jz      short loc_180009DD5
0x180009dc7  test    dword ptr [r10+2Ch], 100h
0x180009dcf  jnz     loc_180009EE0
0x180009dd5  xor     dil, dil
0x180009dd8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180009ddf  setnz   r8b
0x180009de3  test    dil, dil
0x180009de6  jnz     short loc_180009DED
0x180009de8  test    r8b, r8b
0x180009deb  jz      short loc_180009E31
0x180009ded  mov     r9, [rbx+2A0h]
0x180009df4  mov     dl, dil
0x180009df7  mov     rcx, [r10+18h]
0x180009dfb  mov     [rsp+98h+var_48], eax
0x180009dff  mov     rax, [rbx]
0x180009e02  mov     [rsp+98h+var_50], rsi
0x180009e07  mov     [rsp+98h+var_58], rax
0x180009e0c  lea     rax, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x180009e13  mov     [rsp+98h+var_60], rax
0x180009e18  mov     [rsp+98h+var_68], 0Bh
0x180009e1f  mov     [rsp+98h+var_70], 9
0x180009e27  mov     byte ptr [rsp+98h+RemlockSize], 4
0x180009e2c  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180009e31  mov     r8d, 20h ; ' '; RemlockSize
0x180009e37  lea     rdx, IdleWorkerTag; "Idle Worker Tag"
0x180009e3e  mov     rcx, rbp; RemoveLock
0x180009e41  call    cs:__imp_IoReleaseRemoveLockEx
0x180009e48  nop     dword ptr [rax+rax+00h]
0x180009e4d  mov     rcx, r14; IoWorkItem
0x180009e50  call    cs:__imp_IoFreeWorkItem
0x180009e57  nop     dword ptr [rax+rax+00h]
0x180009e5c  add     rsp, 60h
0x180009e60  pop     r14
0x180009e62  pop     r13
0x180009e64  pop     r12
0x180009e66  pop     rdi
0x180009e67  pop     rsi
0x180009e68  pop     rbp
0x180009e69  pop     rbx
0x180009e6a  retn
0x180009e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e73  cmp     rcx, r12
0x180009e76  jz      short loc_180009E8C
0x180009e78  test    dword ptr [rcx+2Ch], 100h
0x180009e7f  jz      short loc_180009E8C
0x180009e81  cmp     byte ptr [rcx+29h], 2
0x180009e85  jb      short loc_180009E8C
0x180009e87  mov     dl, dil
0x180009e8a  jmp     short loc_180009E8E
0x180009e8c  xor     dl, dl
0x180009e8e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180009e95  setnz   r8b
0x180009e99  test    dl, dl
0x180009e9b  jnz     short loc_180009EA6
0x180009e9d  test    r8b, r8b
0x180009ea0  jz      loc_180009DB0
0x180009ea6  mov     r9, [rbx+2A0h]
0x180009ead  mov     rcx, [rcx+18h]
0x180009eb1  mov     dword ptr [rsp+98h+var_50], eax
0x180009eb5  mov     rax, [rbx]
0x180009eb8  mov     [rsp+98h+var_58], rax
0x180009ebd  mov     [rsp+98h+var_60], r11
0x180009ec2  mov     [rsp+98h+var_68], 0Ah
0x180009ec9  mov     [rsp+98h+var_70], 9
0x180009ed1  mov     byte ptr [rsp+98h+RemlockSize], 2
0x180009ed6  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180009edb  jmp     loc_180009DB0
0x180009ee0  cmp     byte ptr [r10+29h], 4
0x180009ee5  jnb     loc_180009DD8
0x180009eeb  jmp     loc_180009DD5
```
