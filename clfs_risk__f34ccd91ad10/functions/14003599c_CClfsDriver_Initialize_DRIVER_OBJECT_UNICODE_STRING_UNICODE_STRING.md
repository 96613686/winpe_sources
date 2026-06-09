# CClfsDriver::Initialize(_DRIVER_OBJECT *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14003599c`
- end: `0x140035abb`
- name: `?Initialize@CClfsDriver@@QEAAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@1@Z`
- size: `287`
- prototype: `__int64 __fastcall(CClfsDriver *__hidden this, struct _DRIVER_OBJECT *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x140035cc4`

## callees

- `0x140010e08`
- `0x140017a2c`
- `0x140035590`
- `0x14003599c`
- `0x140035ac4`
- `0x140035b94`
- `0x14004c5a0`
- `0x14004fc18`
- `0x1400508d0`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x140035a63`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140035a63`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007cfbd`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14007cfbd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035a4f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035a4f`

## pseudocode

```c
__int64 __fastcall CClfsDriver::Initialize(
        CClfsDriver *this,
        struct _DRIVER_OBJECT *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  NTSTATUS Registry; // ebx
  UNICODE_STRING DestinationString; // [rsp+28h] [rbp-30h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *((_QWORD *)this + 1) = 0;
  ClfsTelemetryInit(a2->DeviceObject);
  if ( (unsigned int)Feature_CLFS_EventLog__private_IsEnabledDeviceUsageNoInline(v8, v7, v9)
    && (int)McGenEventRegister_EtwRegister(
              v11,
              v10,
              &ClfsEtwProvider_Context,
              &ClfsEtwProvider_Context,
              0,
              *(_QWORD *)&DestinationString.Length,
              DestinationString.Buffer) < 0 )
  {
    ClfsEtwProvider_Context = 0;
  }
  Registry = ClfsInitialize();
  if ( Registry >= 0 )
  {
    *((_QWORD *)this + 1) = a2;
    Registry = CClfsDriver::ReadRegistry(this, (unsigned int *)a2->DeviceObject->DeviceExtension + 36);
    if ( Registry >= 0 )
    {
      Registry = CClfsDriver::SetIrpFunctions(this);
      if ( Registry >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"\\??\\LOG:");
        Registry = IoCreateSymbolicLink(&DestinationString, a4);
        if ( Registry >= 0 )
          *(_DWORD *)this |= 8u;
      }
    }
  }
  if ( Registry >= 0 )
    Registry = ClfsMgmtInitialize();
  if ( Registry < 0 )
    CClfsDriver::Finalize(this);
  return (unsigned int)Registry;
}

```

## disassembly

```asm
0x14003599c  mov     rax, rsp
0x14003599f  mov     [rax+10h], rbx
0x1400359a3  mov     [rax+18h], rsi
0x1400359a7  mov     [rax+8], rcx
0x1400359ab  push    rdi
0x1400359ac  push    r14
0x1400359ae  push    r15
0x1400359b0  sub     rsp, 40h
0x1400359b4  mov     r15, r9
0x1400359b7  mov     r14, rdx
0x1400359ba  mov     rsi, rcx
0x1400359bd  xor     edi, edi
0x1400359bf  mov     [rax-38h], edi
0x1400359c2  mov     [rax-30h], rdi
0x1400359c6  xor     eax, eax
0x1400359c8  mov     [rsp+58h+DestinationString.Buffer], rdi
0x1400359cd  mov     [rcx+8], rdi
0x1400359d1  mov     rcx, [rdx+8]; DeviceObject
0x1400359d5  call    ClfsTelemetryInit
0x1400359da  call    Feature_CLFS_EventLog__private_IsEnabledDeviceUsageNoInline
0x1400359df  test    eax, eax
0x1400359e1  jz      short loc_1400359FD
0x1400359e3  lea     r8, ClfsEtwProvider_Context
0x1400359ea  mov     r9, r8
0x1400359ed  call    McGenEventRegister_EtwRegister
0x1400359f2  test    eax, eax
0x1400359f4  jns     short loc_1400359FD
0x1400359f6  mov     cs:ClfsEtwProvider_Context, rdi
0x1400359fd  call    ClfsInitialize
0x140035a02  mov     ebx, eax
0x140035a04  mov     [rsp+58h+var_38], eax
0x140035a08  test    eax, eax
0x140035a0a  js      short loc_140035A7C
0x140035a0c  mov     [rsi+8], r14
0x140035a10  mov     rax, [r14+8]
0x140035a14  mov     rdx, [rax+40h]
0x140035a18  add     rdx, 90h; unsigned int *
0x140035a1f  mov     rcx, rsi; this
0x140035a22  call    ?ReadRegistry@CClfsDriver@@AEAAJAEAK@Z; CClfsDriver::ReadRegistry(ulong &)
0x140035a27  mov     ebx, eax
0x140035a29  mov     [rsp+58h+var_38], eax
0x140035a2d  test    eax, eax
0x140035a2f  js      short loc_140035A7C
0x140035a31  mov     rcx, rsi; this
0x140035a34  call    ?SetIrpFunctions@CClfsDriver@@AEAAJXZ; CClfsDriver::SetIrpFunctions(void)
0x140035a39  mov     ebx, eax
0x140035a3b  mov     [rsp+58h+var_38], eax
0x140035a3f  test    eax, eax
0x140035a41  js      short loc_140035A7C
0x140035a43  lea     rdx, aLog; "\\??\\LOG:"
0x140035a4a  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140035a4f  call    cs:__imp_RtlInitUnicodeString
0x140035a56  nop     dword ptr [rax+rax+00h]
0x140035a5b  mov     rdx, r15; DeviceName
0x140035a5e  lea     rcx, [rsp+58h+DestinationString]; SymbolicLinkName
0x140035a63  call    cs:__imp_IoCreateSymbolicLink
0x140035a6a  nop     dword ptr [rax+rax+00h]
0x140035a6f  mov     ebx, eax
0x140035a71  mov     [rsp+58h+var_38], eax
0x140035a75  test    eax, eax
0x140035a77  js      short loc_140035A7C
0x140035a79  or      dword ptr [rsi], 8
0x140035a7c  jmp     short loc_140035A89
0x140035a7e  mov     ebx, eax
0x140035a80  mov     [rsp+58h+var_38], eax
0x140035a84  mov     rsi, [rsp+58h+arg_0]
0x140035a89  test    ebx, ebx
0x140035a8b  js      short loc_140035A98
0x140035a8d  call    ?ClfsMgmtInitialize@@YAJXZ; ClfsMgmtInitialize(void)
0x140035a92  mov     ebx, eax
0x140035a94  mov     [rsp+58h+var_38], eax
0x140035a98  test    ebx, ebx
0x140035a9a  jns     short loc_140035AA4
0x140035a9c  mov     rcx, rsi; this
0x140035a9f  call    ?Finalize@CClfsDriver@@QEAAJXZ; CClfsDriver::Finalize(void)
0x140035aa4  mov     eax, ebx
0x140035aa6  mov     rbx, [rsp+58h+arg_8]
0x140035aab  mov     rsi, [rsp+58h+arg_10]
0x140035ab0  add     rsp, 40h
0x140035ab4  pop     r15
0x140035ab6  pop     r14
0x140035ab8  pop     rdi
0x140035ab9  retn
0x14007cfaf  push    rbp
0x14007cfb1  sub     rsp, 20h
0x14007cfb5  mov     rbp, rdx
0x14007cfb8  mov     rcx, [rcx]
0x14007cfbb  mov     ecx, [rcx]; Exception
0x14007cfbd  call    cs:__imp_FsRtlIsNtstatusExpected
0x14007cfc4  nop     dword ptr [rax+rax+00h]
0x14007cfc9  xor     ecx, ecx
0x14007cfcb  test    al, al
0x14007cfcd  setnz   cl
0x14007cfd0  mov     eax, ecx
0x14007cfd2  add     rsp, 20h
0x14007cfd6  pop     rbp
0x14007cfd7  retn
0x14007cfd9  push    rbp
0x14007cfdb  sub     rsp, 20h
0x14007cfdf  mov     rbp, rdx
0x14007cfe2  cmp     dword ptr [rbp+20h], 0
0x14007cfe6  jge     short loc_14007CFF2
0x14007cfe8  mov     rcx, [rbp+60h]; this
0x14007cfec  call    ?Finalize@CClfsDriver@@QEAAJXZ; CClfsDriver::Finalize(void)
0x14007cff1  nop
0x14007cff2  add     rsp, 20h
0x14007cff6  pop     rbp
0x14007cff7  retn
```
