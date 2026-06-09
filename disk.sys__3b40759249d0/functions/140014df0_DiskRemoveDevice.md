# DiskRemoveDevice

- ea: `0x140014df0`
- end: `0x140014ef0`
- name: `DiskRemoveDevice`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140014df0`
- `0x140014f00`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140014e3c`
- `ntoskrnl!ZwClose` at `0x140014e3c`
- `ntoskrnl!IoFreeIrp` at `0x140014e97`
- `ntoskrnl!IoFreeIrp` at `0x140014e97`
- `ntoskrnl!IoGetConfigurationInformation` at `0x140014e7d`
- `ntoskrnl!IoGetConfigurationInformation` at `0x140014e7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e66`
- `ntoskrnl!ZwMakeTemporaryObject` at `0x140014e29`
- `ntoskrnl!ZwMakeTemporaryObject` at `0x140014e29`
- `CLASSPNP!ClassDeleteSrbLookasideList` at `0x140014ec8`
- `CLASSPNP!ClassDeleteSrbLookasideList` at `0x140014ec8`

## pseudocode

```c
__int64 __fastcall DiskRemoveDevice(__int64 a1, char a2)
{
  struct _COMMON_DEVICE_EXTENSION *v4; // rdi
  struct _LIST_ENTRY *Flink; // rcx
  PVOID DriverData; // rbp
  struct _LIST_ENTRY *Blink; // rcx
  PCONFIGURATION_INFORMATION ConfigurationInformation; // rax
  IRP *v9; // rcx

  if ( ((a2 - 1) & 0xFD) != 0 )
  {
    v4 = *(struct _COMMON_DEVICE_EXTENSION **)(a1 + 64);
    Flink = v4[1].PathCountEvent.Header.WaitListHead.Flink;
    DriverData = v4->DriverData;
    if ( Flink )
    {
      ZwMakeTemporaryObject(Flink);
      ZwClose(v4[1].PathCountEvent.Header.WaitListHead.Flink);
      v4[1].PathCountEvent.Header.WaitListHead.Flink = 0;
    }
    if ( a2 != 2 )
      goto LABEL_9;
    Blink = v4[1].RemoveEvent.Header.WaitListHead.Blink;
    if ( Blink )
    {
      ExFreePoolWithTag(Blink, 0);
      v4[1].RemoveEvent.Header.WaitListHead.Blink = 0;
    }
    ConfigurationInformation = IoGetConfigurationInformation();
    --ConfigurationInformation->DiskCount;
    v9 = (IRP *)*((_QWORD *)DriverData + 63);
    if ( v9 )
    {
      IoFreeIrp(v9);
      *((_QWORD *)DriverData + 63) = 0;
      DiskDeleteSymbolicLinks(a1);
    }
    else
    {
LABEL_9:
      DiskDeleteSymbolicLinks(a1);
      if ( a2 != 2 )
        return 0;
    }
    ClassDeleteSrbLookasideList(v4);
    return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140014df0  mov     [rsp+arg_10], rbx
0x140014df5  push    rsi
0x140014df6  sub     rsp, 20h
0x140014dfa  movzx   ebx, dl
0x140014dfd  mov     rsi, rcx
0x140014e00  lea     eax, [rbx-1]
0x140014e03  test    al, 0FDh
0x140014e05  jz      loc_140014EEC
0x140014e0b  mov     [rsp+28h+arg_0], rbp
0x140014e10  mov     [rsp+28h+arg_8], rdi
0x140014e15  mov     rdi, [rcx+40h]
0x140014e19  mov     rcx, [rdi+2C0h]; Handle
0x140014e20  mov     rbp, [rdi+60h]
0x140014e24  test    rcx, rcx
0x140014e27  jz      short loc_140014E53
0x140014e29  call    cs:__imp_ZwMakeTemporaryObject
0x140014e30  nop     dword ptr [rax+rax+00h]
0x140014e35  mov     rcx, [rdi+2C0h]; Handle
0x140014e3c  call    cs:__imp_ZwClose
0x140014e43  nop     dword ptr [rax+rax+00h]
0x140014e48  mov     qword ptr [rdi+2C0h], 0
0x140014e53  cmp     bl, 2
0x140014e56  jnz     short loc_140014EB8
0x140014e58  mov     rcx, [rdi+240h]; P
0x140014e5f  test    rcx, rcx
0x140014e62  jz      short loc_140014E7D
0x140014e64  xor     edx, edx; Tag
0x140014e66  call    cs:__imp_ExFreePoolWithTag
0x140014e6d  nop     dword ptr [rax+rax+00h]
0x140014e72  mov     qword ptr [rdi+240h], 0
0x140014e7d  call    cs:__imp_IoGetConfigurationInformation
0x140014e84  nop     dword ptr [rax+rax+00h]
0x140014e89  dec     dword ptr [rax]
0x140014e8b  mov     rcx, [rbp+1F8h]; Irp
0x140014e92  test    rcx, rcx
0x140014e95  jz      short loc_140014EB8
0x140014e97  call    cs:__imp_IoFreeIrp
0x140014e9e  nop     dword ptr [rax+rax+00h]
0x140014ea3  mov     rcx, rsi
0x140014ea6  mov     qword ptr [rbp+1F8h], 0
0x140014eb1  call    DiskDeleteSymbolicLinks
0x140014eb6  jmp     short loc_140014EC5
0x140014eb8  mov     rcx, rsi
0x140014ebb  call    DiskDeleteSymbolicLinks
0x140014ec0  cmp     bl, 2
0x140014ec3  jnz     short loc_140014ED4
0x140014ec5  mov     rcx, rdi; CommonExtension
0x140014ec8  call    cs:__imp_ClassDeleteSrbLookasideList
0x140014ecf  nop     dword ptr [rax+rax+00h]
0x140014ed4  mov     rbp, [rsp+28h+arg_0]
0x140014ed9  xor     eax, eax
0x140014edb  mov     rdi, [rsp+28h+arg_8]
0x140014ee0  mov     rbx, [rsp+28h+arg_10]
0x140014ee5  add     rsp, 20h
0x140014ee9  pop     rsi
0x140014eea  retn
0x140014eec  xor     eax, eax
0x140014eee  jmp     short loc_140014EE0
```
