# DiskInitializeFailurePrediction

- ea: `0x14000e510`
- end: `0x14000e5f1`
- name: `DiskInitializeFailurePrediction`
- size: `225`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004258`
- `0x14000e510`
- `0x14001016c`
- `0x140011ee0`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14000e56d`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000e56d`
- `ntoskrnl!IoFreeWorkItem` at `0x14000e5d9`
- `ntoskrnl!IoFreeWorkItem` at `0x14000e5d9`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x14000e5ca`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x14000e5ca`
- `CLASSPNP!ClassAcquireRemoveLockEx` at `0x14000e536`
- `CLASSPNP!ClassAcquireRemoveLockEx` at `0x14000e536`

## pseudocode

```c
void __fastcall DiskInitializeFailurePrediction(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // r14
  _BYTE *DriverData; // rbp
  int v6; // eax
  __int64 v7; // r8

  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  DriverData = DeviceExtension->CommonExtension.DriverData;
  if ( !ClassAcquireRemoveLockEx(DeviceObject, Context, "minkernel\\storage\\disk\\disk.c", 0xA4Au) )
  {
    DiskDetectFailurePrediction((int)DeviceExtension);
    if ( *((_DWORD *)DriverData + 4) )
    {
      IoWMIRegistrationControl(DeviceObject, 4u);
      DriverData[20] = 1;
      v6 = DiskEnableDisableFailurePredictPolling(DeviceExtension);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_dqL(
          WPP_GLOBAL_Control->AttachedDevice,
          &WPP_GLOBAL_Control,
          v7,
          *((unsigned int *)DriverData + 4),
          DeviceObject,
          v6);
      }
    }
    ClassReleaseRemoveLock(DeviceObject, Context);
  }
  IoFreeWorkItem((PIO_WORKITEM)Context);
}

```

## disassembly

```asm
0x14000e510  push    rbx
0x14000e512  push    rbp
0x14000e513  push    rsi
0x14000e514  push    rdi
0x14000e515  push    r14
0x14000e517  sub     rsp, 30h
0x14000e51b  mov     r14, [rcx+40h]
0x14000e51f  lea     r8, File; "minkernel\\storage\\disk\\disk.c"
0x14000e526  mov     r9d, 0A4Ah; Line
0x14000e52c  mov     rdi, rdx
0x14000e52f  mov     rbx, rcx
0x14000e532  mov     rbp, [r14+60h]
0x14000e536  call    cs:__imp_ClassAcquireRemoveLockEx
0x14000e53d  nop     dword ptr [rax+rax+00h]
0x14000e542  test    eax, eax
0x14000e544  jnz     loc_14000E5D6
0x14000e54a  cmp     [rbp+8], eax
0x14000e54d  lea     rsi, [rbp+10h]
0x14000e551  mov     rdx, rsi
0x14000e554  mov     rcx, r14; int
0x14000e557  setnz   r8b
0x14000e55b  call    DiskDetectFailurePrediction
0x14000e560  cmp     dword ptr [rsi], 0
0x14000e563  jz      short loc_14000E5C4
0x14000e565  mov     edx, 4; Action
0x14000e56a  mov     rcx, rbx; DeviceObject
0x14000e56d  call    cs:__imp_IoWMIRegistrationControl
0x14000e574  nop     dword ptr [rax+rax+00h]
0x14000e579  mov     r8d, 0E10h
0x14000e57f  mov     byte ptr [rbp+14h], 1
0x14000e583  mov     dl, 1
0x14000e585  mov     rcx, r14; FdoExtension
0x14000e588  call    DiskEnableDisableFailurePredictPolling
0x14000e58d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e594  lea     rdx, WPP_GLOBAL_Control
0x14000e59b  cmp     rcx, rdx
0x14000e59e  jz      short loc_14000E5C4
0x14000e5a0  test    dword ptr [rcx+2Ch], 100h
0x14000e5a7  jz      short loc_14000E5C4
0x14000e5a9  cmp     byte ptr [rcx+29h], 4
0x14000e5ad  jb      short loc_14000E5C4
0x14000e5af  mov     r9d, [rsi]
0x14000e5b2  mov     rcx, [rcx+18h]
0x14000e5b6  mov     [rsp+58h+var_30], eax
0x14000e5ba  mov     [rsp+58h+var_38], rbx
0x14000e5bf  call    WPP_SF_dqL
0x14000e5c4  mov     rdx, rdi; Tag
0x14000e5c7  mov     rcx, rbx; DeviceObject
0x14000e5ca  call    cs:__imp_ClassReleaseRemoveLock
0x14000e5d1  nop     dword ptr [rax+rax+00h]
0x14000e5d6  mov     rcx, rdi; IoWorkItem
0x14000e5d9  call    cs:__imp_IoFreeWorkItem
0x14000e5e0  nop     dword ptr [rax+rax+00h]
0x14000e5e5  add     rsp, 30h
0x14000e5e9  pop     r14
0x14000e5eb  pop     rdi
0x14000e5ec  pop     rsi
0x14000e5ed  pop     rbp
0x14000e5ee  pop     rbx
0x14000e5ef  retn
```
