# DriverEntry

- ea: `0x140014300`
- end: `0x1400145ce`
- name: `DriverEntry`
- size: `718`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400145e0`

## callees

- `0x1400013c0`
- `0x140002fd0`
- `0x140003580`
- `0x14000d4c8`
- `0x14000d604`
- `0x140014010`
- `0x140014300`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400143f4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400143f4`
- `ntoskrnl!FsRtlIsMobileOS` at `0x1400144b8`
- `ntoskrnl!FsRtlIsMobileOS` at `0x1400144b8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001454d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140014560`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140014573`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001454d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140014560`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140014573`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001443d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140014473`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400144ac`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001443d`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140014473`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400144ac`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001433e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001433e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014590`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014590`
- `ntoskrnl!ExAllocatePool2` at `0x1400143c1`
- `ntoskrnl!ExAllocatePool2` at `0x1400143c1`
- `FLTMGR!FltStartFiltering` at `0x14001450f`
- `FLTMGR!FltStartFiltering` at `0x14001450f`
- `FLTMGR!FltRegisterFilter` at `0x1400144e7`
- `FLTMGR!FltRegisterFilter` at `0x1400144e7`
- `FLTMGR!FltUnregisterFilter` at `0x1400145b2`
- `FLTMGR!FltUnregisterFilter` at `0x1400145b2`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v3; // si
  char v5; // r14
  char v6; // bp
  int (__fastcall *SystemRoutineAddress)(__int64, char *, __int64, _QWORD); // rax
  __int64 v8; // rcx
  int v9; // ebx
  __int64 v10; // r8
  USHORT v11; // bx
  __int64 v12; // rcx
  NTSTATUS result; // eax
  struct _UNICODE_STRING SystemRoutineName; // [rsp+40h] [rbp-48h] BYREF
  char v15; // [rsp+A0h] [rbp+18h] BYREF

  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  v3 = 0;
  v15 = 0;
  SystemRoutineName.Buffer = L"ZwQuerySystemInformation";
  v5 = 0;
  v6 = 0;
  SystemRoutineAddress = (int (__fastcall *)(__int64, char *, __int64, _QWORD))MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress && SystemRoutineAddress(227, &v15, 1, 0) >= 0 && v15 )
    ExPoolZeroingNativelySupported = 1;
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  McGenEventRegister_EtwRegister();
  v9 = FCReadDriverParameters(RegistryPath);
  if ( v9 >= 0 )
  {
    v11 = RegistryPath->Length + 2;
    gRegistryPath.Buffer = (PWSTR)ExAllocatePool2(64, v11, 1852392262);
    if ( gRegistryPath.Buffer )
    {
      gRegistryPath.MaximumLength = v11;
      RtlCopyUnicodeString(&gRegistryPath, RegistryPath);
      gRegistryPath.Buffer[(unsigned __int64)RegistryPath->Length >> 1] = 0;
      ExInitializeNPagedLookasideList(&gPre2PostIoContextList, 0, 0, 0x200u, 0x20u, 0x70704346u, 0);
      ExInitializeNPagedLookasideList(&gPre2PostCreateContextList, 0, 0, 0x200u, 0x10u, 0x70704346u, 0);
      v5 = 1;
      ExInitializeNPagedLookasideList(&gShadowBufferList, 0, 0, 0x200u, 0x10000u, 0x62734346u, 0);
      if ( (unsigned __int8)FsRtlIsMobileOS(v12) )
        FilterRegistration.OperationRegistration = (const FLT_OPERATION_REGISTRATION *)&CallbacksMobile;
      v9 = FltRegisterFilter(DriverObject, &FilterRegistration, &gFilterHandle);
      if ( v9 >= 0 )
      {
        v6 = 1;
        v9 = StSecInitialize();
        if ( v9 >= 0 )
        {
          result = FltStartFiltering(gFilterHandle);
          v9 = result;
          if ( result >= 0 )
            return result;
          v3 = 1;
        }
      }
    }
    else
    {
      v9 = -1073741670;
    }
  }
  if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
    McTemplateK0d_EtwWriteTransfer(v8, &DriverEntryFailure, v10, (unsigned int)v9);
  if ( v5 )
  {
    ExDeleteNPagedLookasideList(&gPre2PostIoContextList);
    ExDeleteNPagedLookasideList(&gPre2PostCreateContextList);
    ExDeleteNPagedLookasideList(&gShadowBufferList);
  }
  if ( gRegistryPath.Buffer )
    ExFreePoolWithTag(gRegistryPath.Buffer, 0x6E694346u);
  if ( v3 )
    StSecDeinitialize();
  if ( v6 )
    FltUnregisterFilter(gFilterHandle);
  return v9;
}

```

## disassembly

```asm
0x140014300  push    rbx
0x140014302  push    rbp
0x140014303  push    rsi
0x140014304  push    rdi
0x140014305  push    r14
0x140014307  push    r15
0x140014309  sub     rsp, 58h
0x14001430d  mov     r15, rcx
0x140014310  mov     qword ptr [rsp+88h+SystemRoutineName.Length], 320030h
0x140014319  lea     rax, aZwquerysystemi; "ZwQuerySystemInformation"
0x140014320  xor     sil, sil
0x140014323  lea     rcx, [rsp+88h+SystemRoutineName]; SystemRoutineName
0x140014328  mov     [rsp+88h+arg_10], sil
0x140014330  mov     [rsp+88h+SystemRoutineName.Buffer], rax
0x140014335  mov     rdi, rdx
0x140014338  xor     r14b, r14b
0x14001433b  xor     bpl, bpl
0x14001433e  call    cs:__imp_MmGetSystemRoutineAddress
0x140014345  nop     dword ptr [rax+rax+00h]
0x14001434a  test    rax, rax
0x14001434d  jz      short loc_14001437F
0x14001434f  xor     r9d, r9d
0x140014352  lea     rdx, [rsp+88h+arg_10]
0x14001435a  mov     r8d, 1
0x140014360  mov     ecx, 0E3h
0x140014365  call    _guard_dispatch_icall
0x14001436a  test    eax, eax
0x14001436c  js      short loc_14001437F
0x14001436e  cmp     [rsp+88h+arg_10], sil
0x140014376  jz      short loc_14001437F
0x140014378  mov     cs:ExPoolZeroingNativelySupported, 1
0x14001437f  mov     cs:ExDefaultNonPagedPoolType, 200h
0x140014389  mov     cs:ExDefaultMdlProtection, 40000000h
0x140014393  call    McGenEventRegister_EtwRegister
0x140014398  mov     rcx, rdi
0x14001439b  call    FCReadDriverParameters
0x1400143a0  mov     ebx, eax
0x1400143a2  test    eax, eax
0x1400143a4  js      loc_140014529
0x1400143aa  movzx   eax, word ptr [rdi]
0x1400143ad  mov     ecx, 40h ; '@'
0x1400143b2  add     ax, 2
0x1400143b6  mov     r8d, 6E694346h
0x1400143bc  movzx   ebx, ax
0x1400143bf  mov     edx, ebx
0x1400143c1  call    cs:__imp_ExAllocatePool2
0x1400143c8  nop     dword ptr [rax+rax+00h]
0x1400143cd  mov     cs:gRegistryPath.Buffer, rax
0x1400143d4  test    rax, rax
0x1400143d7  jnz     short loc_1400143E3
0x1400143d9  mov     ebx, 0C000009Ah
0x1400143de  jmp     loc_140014529
0x1400143e3  mov     rdx, rdi; SourceString
0x1400143e6  mov     cs:gRegistryPath.MaximumLength, bx
0x1400143ed  lea     rcx, gRegistryPath; DestinationString
0x1400143f4  call    cs:__imp_RtlCopyUnicodeString
0x1400143fb  nop     dword ptr [rax+rax+00h]
0x140014400  movzx   edx, word ptr [rdi]
0x140014403  xor     ecx, ecx
0x140014405  mov     rax, cs:gRegistryPath.Buffer
0x14001440c  mov     r9d, 200h; Flags
0x140014412  shr     rdx, 1
0x140014415  xor     r8d, r8d; Free
0x140014418  mov     [rax+rdx*2], cx
0x14001441c  xor     eax, eax
0x14001441e  mov     [rsp+88h+Depth], ax; Depth
0x140014423  lea     rcx, gPre2PostIoContextList; Lookaside
0x14001442a  mov     [rsp+88h+Tag], 70704346h; Tag
0x140014432  xor     edx, edx; Allocate
0x140014434  mov     [rsp+88h+Size], 20h ; ' '; Size
0x14001443d  call    cs:__imp_ExInitializeNPagedLookasideList
0x140014444  nop     dword ptr [rax+rax+00h]
0x140014449  xor     eax, eax
0x14001444b  lea     rcx, gPre2PostCreateContextList; Lookaside
0x140014452  mov     [rsp+88h+Depth], ax; Depth
0x140014457  mov     r9d, 200h; Flags
0x14001445d  mov     [rsp+88h+Tag], 70704346h; Tag
0x140014465  xor     r8d, r8d; Free
0x140014468  xor     edx, edx; Allocate
0x14001446a  mov     [rsp+88h+Size], 10h; Size
0x140014473  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001447a  nop     dword ptr [rax+rax+00h]
0x14001447f  xor     eax, eax
0x140014481  lea     rcx, gShadowBufferList; Lookaside
0x140014488  mov     [rsp+88h+Depth], ax; Depth
0x14001448d  mov     r9d, 200h; Flags
0x140014493  mov     [rsp+88h+Tag], 62734346h; Tag
0x14001449b  xor     r8d, r8d; Free
0x14001449e  xor     edx, edx; Allocate
0x1400144a0  mov     [rsp+88h+Size], 10000h; Size
0x1400144a9  mov     r14b, 1
0x1400144ac  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400144b3  nop     dword ptr [rax+rax+00h]
0x1400144b8  call    cs:__imp_FsRtlIsMobileOS
0x1400144bf  nop     dword ptr [rax+rax+00h]
0x1400144c4  test    al, al
0x1400144c6  jz      short loc_1400144D6
0x1400144c8  lea     rax, CallbacksMobile
0x1400144cf  mov     cs:FilterRegistration.OperationRegistration, rax
0x1400144d6  lea     r8, gFilterHandle; RetFilter
0x1400144dd  mov     rcx, r15; Driver
0x1400144e0  lea     rdx, FilterRegistration; Registration
0x1400144e7  call    cs:__imp_FltRegisterFilter
0x1400144ee  nop     dword ptr [rax+rax+00h]
0x1400144f3  mov     ebx, eax
0x1400144f5  test    eax, eax
0x1400144f7  js      short loc_140014529
0x1400144f9  movzx   ebp, r14b
0x1400144fd  call    StSecInitialize
0x140014502  mov     ebx, eax
0x140014504  test    eax, eax
0x140014506  js      short loc_140014529
0x140014508  mov     rcx, cs:gFilterHandle; Filter
0x14001450f  call    cs:__imp_FltStartFiltering
0x140014516  nop     dword ptr [rax+rax+00h]
0x14001451b  mov     ebx, eax
0x14001451d  test    eax, eax
0x14001451f  jns     loc_1400145C0
0x140014525  movzx   esi, r14b
0x140014529  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 1
0x140014530  jz      short loc_140014541
0x140014532  mov     r9d, ebx
0x140014535  lea     rdx, DriverEntryFailure
0x14001453c  call    McTemplateK0d_EtwWriteTransfer
0x140014541  test    r14b, r14b
0x140014544  jz      short loc_14001457F
0x140014546  lea     rcx, gPre2PostIoContextList; Lookaside
0x14001454d  call    cs:__imp_ExDeleteNPagedLookasideList
0x140014554  nop     dword ptr [rax+rax+00h]
0x140014559  lea     rcx, gPre2PostCreateContextList; Lookaside
0x140014560  call    cs:__imp_ExDeleteNPagedLookasideList
0x140014567  nop     dword ptr [rax+rax+00h]
0x14001456c  lea     rcx, gShadowBufferList; Lookaside
0x140014573  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001457a  nop     dword ptr [rax+rax+00h]
0x14001457f  mov     rcx, cs:gRegistryPath.Buffer; P
0x140014586  test    rcx, rcx
0x140014589  jz      short loc_14001459C
0x14001458b  mov     edx, 6E694346h; Tag
0x140014590  call    cs:__imp_ExFreePoolWithTag
0x140014597  nop     dword ptr [rax+rax+00h]
0x14001459c  test    sil, sil
0x14001459f  jz      short loc_1400145A6
0x1400145a1  call    StSecDeinitialize
0x1400145a6  test    bpl, bpl
0x1400145a9  jz      short loc_1400145BE
0x1400145ab  mov     rcx, cs:gFilterHandle; Filter
0x1400145b2  call    cs:__imp_FltUnregisterFilter
0x1400145b9  nop     dword ptr [rax+rax+00h]
0x1400145be  mov     eax, ebx
0x1400145c0  add     rsp, 58h
0x1400145c4  pop     r15
0x1400145c6  pop     r14
0x1400145c8  pop     rdi
0x1400145c9  pop     rsi
0x1400145ca  pop     rbp
0x1400145cb  pop     rbx
0x1400145cc  retn
```
