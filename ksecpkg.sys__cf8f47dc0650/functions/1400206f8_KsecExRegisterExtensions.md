# KsecExRegisterExtensions

- ea: `0x1400206f8`
- end: `0x1400207e5`
- name: `KsecExRegisterExtensions`
- size: `237`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140032078`

## callees

- `0x140007008`
- `0x1400206f8`
- `0x1400207ec`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400207cb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400207cb`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14002074b`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14002074b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002072e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002072e`

## string_xrefs

- `0x140020769`: `KsecExRegisterExtensions: IoGetDeviceObjectPointer failed: 0x%lx\n`

## pseudocode

```c
__int64 KsecExRegisterExtensions()
{
  NTSTATUS DeviceObjectPointer; // eax
  int v1; // ebx
  __int128 InputBuffer; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp+10h] BYREF
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp+18h] BYREF

  DeviceObject = 0;
  FileObject = 0;
  DestinationString = 0;
  InputBuffer = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\KsecDD");
  DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x1F01FFu, &FileObject, &DeviceObject);
  v1 = DeviceObjectPointer;
  if ( DeviceObjectPointer >= 0 )
  {
    *((_QWORD *)&InputBuffer + 1) = &gKsecExBuiltinPackages;
    LODWORD(InputBuffer) = 2;
    v1 = KsecExRegisterOneExtension(DeviceObject, &InputBuffer);
    if ( v1 >= 0 )
    {
      *((_QWORD *)&InputBuffer + 1) = &gKsecExMiscExtension;
      LODWORD(InputBuffer) = 4;
      v1 = KsecExRegisterOneExtension(DeviceObject, &InputBuffer);
    }
  }
  else if ( KsecInfoLevel )
  {
    KsecDebugOut(1, "KsecExRegisterExtensions: IoGetDeviceObjectPointer failed: 0x%lx\n", DeviceObjectPointer);
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1400206f8  mov     [rsp-8+arg_10], rbx
0x1400206fd  push    rbp
0x1400206fe  mov     rbp, rsp
0x140020701  sub     rsp, 40h
0x140020705  xorps   xmm0, xmm0
0x140020708  mov     [rbp+DeviceObject], 0
0x140020710  xorps   xmm1, xmm1
0x140020713  mov     [rbp+FileObject], 0
0x14002071b  lea     rdx, aDeviceKsecdd; "\\Device\\KsecDD"
0x140020722  lea     rcx, [rbp+DestinationString]; DestinationString
0x140020726  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002072a  movups  [rbp+InputBuffer], xmm1
0x14002072e  call    cs:__imp_RtlInitUnicodeString
0x140020735  nop     dword ptr [rax+rax+00h]
0x14002073a  lea     r9, [rbp+DeviceObject]; DeviceObject
0x14002073e  mov     edx, 1F01FFh; DesiredAccess
0x140020743  lea     r8, [rbp+FileObject]; FileObject
0x140020747  lea     rcx, [rbp+DestinationString]; ObjectName
0x14002074b  call    cs:__imp_IoGetDeviceObjectPointer
0x140020752  nop     dword ptr [rax+rax+00h]
0x140020757  mov     ebx, eax
0x140020759  test    eax, eax
0x14002075b  jns     short loc_14002077C
0x14002075d  cmp     cs:KsecInfoLevel, 0
0x140020764  jz      short loc_1400207C2
0x140020766  mov     r8d, eax
0x140020769  lea     rdx, aKsecexregister_0; "KsecExRegisterExtensions: IoGetDeviceOb"...
0x140020770  mov     ecx, 1
0x140020775  call    KsecDebugOut
0x14002077a  jmp     short loc_1400207C2
0x14002077c  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x140020780  lea     rax, ?gKsecExBuiltinPackages@@3PAU_SEC_BUILTIN_KPACKAGE@@A; _SEC_BUILTIN_KPACKAGE near * gKsecExBuiltinPackages
0x140020787  lea     rdx, [rbp+InputBuffer]; InputBuffer
0x14002078b  mov     qword ptr [rbp+InputBuffer+8], rax
0x14002078f  mov     dword ptr [rbp+InputBuffer], 2
0x140020796  call    KsecExRegisterOneExtension
0x14002079b  mov     ebx, eax
0x14002079d  test    eax, eax
0x14002079f  js      short loc_1400207C2
0x1400207a1  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x1400207a5  lea     rax, ?gKsecExMiscExtension@@3U_KSEC_MISC_EX_FUNCTIONS@@A; _KSEC_MISC_EX_FUNCTIONS gKsecExMiscExtension
0x1400207ac  lea     rdx, [rbp+InputBuffer]; InputBuffer
0x1400207b0  mov     qword ptr [rbp+InputBuffer+8], rax
0x1400207b4  mov     dword ptr [rbp+InputBuffer], 4
0x1400207bb  call    KsecExRegisterOneExtension
0x1400207c0  mov     ebx, eax
0x1400207c2  mov     rcx, [rbp+FileObject]; Object
0x1400207c6  test    rcx, rcx
0x1400207c9  jz      short loc_1400207D7
0x1400207cb  call    cs:__imp_ObfDereferenceObject
0x1400207d2  nop     dword ptr [rax+rax+00h]
0x1400207d7  mov     eax, ebx
0x1400207d9  mov     rbx, [rsp+40h+arg_10]
0x1400207de  add     rsp, 40h
0x1400207e2  pop     rbp
0x1400207e3  retn
```
