# MountMgrMountedDeviceNotification

- ea: `0x140019980`
- end: `0x140019aea`
- name: `MountMgrMountedDeviceNotification`
- size: `362`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001ae0`
- `0x14000a050`
- `0x140014fc0`
- `0x140019980`

## import_xrefs

- `ntoskrnl!PsGetThreadHardErrorsAreDisabled` at `0x14001999e`
- `ntoskrnl!PsGetThreadHardErrorsAreDisabled` at `0x14001999e`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x1400199b8`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x140019acb`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x1400199b8`
- `ntoskrnl!PsSetThreadHardErrorsAreDisabled` at `0x140019acb`

## pseudocode

```c
__int64 __fastcall MountMgrMountedDeviceNotification(char *NotificationStructure, struct _KMUTANT *Context)
{
  unsigned __int8 ThreadHardErrorsAreDisabled; // al
  __int64 v5; // rdx
  unsigned __int8 v6; // di
  __int64 v7; // r8
  int v8; // eax
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // eax

  ThreadHardErrorsAreDisabled = PsGetThreadHardErrorsAreDisabled(KeGetCurrentThread());
  LOBYTE(v5) = 1;
  v6 = ThreadHardErrorsAreDisabled;
  PsSetThreadHardErrorsAreDisabled(KeGetCurrentThread(), v5);
  v7 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_DEVICE_INTERFACE_ARRIVAL.Data1;
  if ( !v7 )
    v7 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_DEVICE_INTERFACE_ARRIVAL.Data4;
  if ( v7 )
  {
    v12 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_DEVICE_INTERFACE_REMOVAL.Data1;
    if ( !v12 )
      v12 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_DEVICE_INTERFACE_REMOVAL.Data4;
    if ( v12 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v10 = 200;
        v11 = 3221225485LL;
        goto LABEL_21;
      }
    }
    else
    {
      v13 = MountMgrMountedDeviceRemoval(Context, *((const UNICODE_STRING **)NotificationStructure + 5), 0);
      if ( v13 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v10 = 199;
          v11 = (unsigned int)v13;
          goto LABEL_21;
        }
      }
    }
  }
  else
  {
    v8 = MountMgrMountedDeviceArrival(Context, *((_QWORD *)NotificationStructure + 5), 0);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v10 = 198;
        v11 = (unsigned int)v8;
LABEL_21:
        WPP_SF_L(v9->AttachedDevice, v10, v7, v11);
      }
    }
  }
  PsSetThreadHardErrorsAreDisabled(KeGetCurrentThread(), v6);
  return 0;
}

```

## disassembly

```asm
0x140019980  mov     [rsp+arg_0], rbx
0x140019985  mov     [rsp+arg_8], rsi
0x14001998a  push    rdi
0x14001998b  sub     rsp, 20h
0x14001998f  mov     rbx, rcx
0x140019992  mov     rsi, rdx
0x140019995  mov     rcx, gs:188h
0x14001999e  call    cs:__imp_PsGetThreadHardErrorsAreDisabled
0x1400199a5  nop     dword ptr [rax+rax+00h]
0x1400199aa  mov     rcx, gs:188h
0x1400199b3  mov     dl, 1
0x1400199b5  movzx   edi, al
0x1400199b8  call    cs:__imp_PsSetThreadHardErrorsAreDisabled
0x1400199bf  nop     dword ptr [rax+rax+00h]
0x1400199c4  mov     r8, [rbx+4]
0x1400199c8  sub     r8, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data1
0x1400199cf  jnz     short loc_1400199DC
0x1400199d1  mov     r8, [rbx+0Ch]
0x1400199d5  sub     r8, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data4
0x1400199dc  test    r8, r8
0x1400199df  jnz     short loc_140019A2F
0x1400199e1  mov     rdx, [rbx+28h]
0x1400199e5  mov     rcx, rsi
0x1400199e8  call    MountMgrMountedDeviceArrival
0x1400199ed  test    eax, eax
0x1400199ef  jns     loc_140019ABE
0x1400199f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400199fc  lea     rdx, WPP_GLOBAL_Control
0x140019a03  cmp     rcx, rdx
0x140019a06  jz      loc_140019ABE
0x140019a0c  mov     edx, [rcx+2Ch]
0x140019a0f  test    dl, 1
0x140019a12  jz      loc_140019ABE
0x140019a18  cmp     byte ptr [rcx+29h], 2
0x140019a1c  jb      loc_140019ABE
0x140019a22  mov     edx, 0C6h
0x140019a27  mov     r9d, eax
0x140019a2a  jmp     loc_140019AB5
0x140019a2f  mov     rax, [rbx+4]
0x140019a33  sub     rax, qword ptr cs:GUID_DEVICE_INTERFACE_REMOVAL.Data1
0x140019a3a  jnz     short loc_140019A47
0x140019a3c  mov     rax, [rbx+0Ch]
0x140019a40  sub     rax, qword ptr cs:GUID_DEVICE_INTERFACE_REMOVAL.Data4
0x140019a47  test    rax, rax
0x140019a4a  jnz     short loc_140019A8A
0x140019a4c  mov     rdx, [rbx+28h]
0x140019a50  xor     r8d, r8d
0x140019a53  mov     rcx, rsi
0x140019a56  call    MountMgrMountedDeviceRemoval
0x140019a5b  test    eax, eax
0x140019a5d  jns     short loc_140019ABE
0x140019a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a66  lea     rdx, WPP_GLOBAL_Control
0x140019a6d  cmp     rcx, rdx
0x140019a70  jz      short loc_140019ABE
0x140019a72  mov     edx, [rcx+2Ch]
0x140019a75  test    dl, 1
0x140019a78  jz      short loc_140019ABE
0x140019a7a  cmp     byte ptr [rcx+29h], 2
0x140019a7e  jb      short loc_140019ABE
0x140019a80  mov     edx, 0C7h
0x140019a85  mov     r9d, eax
0x140019a88  jmp     short loc_140019AB5
0x140019a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a91  lea     rdx, WPP_GLOBAL_Control
0x140019a98  cmp     rcx, rdx
0x140019a9b  jz      short loc_140019ABE
0x140019a9d  mov     eax, [rcx+2Ch]
0x140019aa0  test    al, 1
0x140019aa2  jz      short loc_140019ABE
0x140019aa4  cmp     byte ptr [rcx+29h], 2
0x140019aa8  jb      short loc_140019ABE
0x140019aaa  mov     edx, 0C8h
0x140019aaf  mov     r9d, 0C000000Dh
0x140019ab5  mov     rcx, [rcx+18h]
0x140019ab9  call    WPP_SF_L
0x140019abe  mov     rcx, gs:188h
0x140019ac7  movzx   edx, dil
0x140019acb  call    cs:__imp_PsSetThreadHardErrorsAreDisabled
0x140019ad2  nop     dword ptr [rax+rax+00h]
0x140019ad7  mov     rbx, [rsp+28h+arg_0]
0x140019adc  xor     eax, eax
0x140019ade  mov     rsi, [rsp+28h+arg_8]
0x140019ae3  add     rsp, 20h
0x140019ae7  pop     rdi
0x140019ae8  retn
```
