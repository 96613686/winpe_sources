# FxDriverEntryWorker

- ea: `0x140005144`
- end: `0x1400052ac`
- name: `FxDriverEntryWorker`
- size: `360`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x1400050cc`
- `0x140005144`
- `0x1400052f4`
- `0x140005550`
- `0x140006670`
- `0x140013350`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140005185`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140005185`
- `ntoskrnl!DbgPrintEx` at `0x140005200`
- `ntoskrnl!DbgPrintEx` at `0x140005200`
- `WDFLDR!WdfVersionBind` at `0x1400051a5`
- `WDFLDR!WdfVersionBind` at `0x1400051a5`
- `WDFLDR!WdfLdrQueryInterface` at `0x140005246`
- `WDFLDR!WdfLdrQueryInterface` at `0x140005246`

## pseudocode

```c
NTSTATUS __fastcall FxDriverEntryWorker(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  struct _WDF_BIND_INFO *v5; // rcx
  int inited; // ebx
  NTSTATUS v7; // eax
  GUID *v8; // [rsp+30h] [rbp-48h] BYREF
  int v9; // [rsp+38h] [rbp-40h]
  _QWORD v10[7]; // [rsp+3Ch] [rbp-3Ch] BYREF

  if ( !DriverObject )
    return DriverEntry(0, RegistryPath);
  *(_DWORD *)&DestinationString.Length = 34078720;
  DestinationString.Buffer = (wchar_t *)qword_14000B260;
  RtlCopyUnicodeString(&DestinationString, RegistryPath);
  result = WdfVersionBind(DriverObject, &DestinationString, &WdfBindInfo, &WdfDriverGlobals);
  if ( result >= 0 )
  {
    inited = FxStubBindClasses(v5);
    if ( inited < 0 || (inited = FxStubInitTypes(), inited < 0) )
    {
LABEL_10:
      FxStubDriverUnloadCommon();
      return inited;
    }
    v7 = DriverEntry(DriverObject, RegistryPath);
    inited = v7;
    if ( v7 < 0 )
    {
      DbgPrintEx(0x4Du, 0, "DriverEntry failed 0x%x for driver %wZ\n", (unsigned int)v7, &DestinationString);
      if ( off_14000B1D8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
      {
        memset(v10, 0, 12);
        v8 = &GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE;
        v9 = 24;
        if ( (int)WdfLdrQueryInterface(&v8) >= 0 )
          (*(void (__fastcall **)(__int64 *, PWDF_DRIVER_GLOBALS))((char *)v10 + 4))(&WdfBindInfo, WdfDriverGlobals);
      }
      goto LABEL_10;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      if ( DriverObject->DriverUnload )
        qword_14000B468 = (__int64)DriverObject->DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005144  push    rbx
0x140005146  push    rsi
0x140005147  push    rdi
0x140005148  push    r14
0x14000514a  sub     rsp, 58h
0x14000514e  mov     rsi, rdx
0x140005151  mov     rdi, rcx
0x140005154  test    rcx, rcx
0x140005157  jnz     short loc_140005163
0x140005159  call    DriverEntry
0x14000515e  jmp     loc_140005275
0x140005163  lea     rax, qword_14000B260
0x14000516a  mov     dword ptr cs:DestinationString.Length, 2080000h
0x140005174  lea     r14, DestinationString
0x14000517b  mov     cs:DestinationString.Buffer, rax
0x140005182  mov     rcx, r14; DestinationString
0x140005185  call    cs:__imp_RtlCopyUnicodeString
0x14000518c  nop     dword ptr [rax+rax+00h]
0x140005191  lea     r9, WdfDriverGlobals
0x140005198  mov     rdx, r14
0x14000519b  lea     r8, WdfBindInfo
0x1400051a2  mov     rcx, rdi
0x1400051a5  call    cs:__imp_WdfVersionBind
0x1400051ac  nop     dword ptr [rax+rax+00h]
0x1400051b1  test    eax, eax
0x1400051b3  js      loc_140005275
0x1400051b9  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x1400051be  mov     ebx, eax
0x1400051c0  test    eax, eax
0x1400051c2  js      loc_14000526E
0x1400051c8  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x1400051cd  mov     ebx, eax
0x1400051cf  test    eax, eax
0x1400051d1  js      loc_14000526E
0x1400051d7  mov     rdx, rsi; RegistryPath
0x1400051da  mov     rcx, rdi; DriverObject
0x1400051dd  call    DriverEntry
0x1400051e2  mov     ebx, eax
0x1400051e4  test    eax, eax
0x1400051e6  jns     loc_140005280
0x1400051ec  xor     edx, edx; Level
0x1400051ee  mov     [rsp+78h+var_58], r14
0x1400051f3  mov     r9d, eax
0x1400051f6  lea     r8, Format; "DriverEntry failed 0x%x for driver %wZ"...
0x1400051fd  lea     ecx, [rdx+4Dh]; ComponentId
0x140005200  call    cs:__imp_DbgPrintEx
0x140005207  nop     dword ptr [rax+rax+00h]
0x14000520c  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140005213  cmp     cs:off_14000B1D8, rax
0x14000521a  jz      short loc_14000526E
0x14000521c  lea     rax, GUID_WDF_LOADER_INTERFACE_DRIVER_ENTRY_FAILURE
0x140005223  mov     [rsp+78h+var_3C], 0
0x14000522c  lea     rcx, [rsp+78h+var_48]
0x140005231  mov     [rsp+78h+var_48], rax
0x140005236  mov     [rsp+78h+var_34], 0
0x14000523e  mov     [rsp+78h+var_40], 18h
0x140005246  call    cs:__imp_WdfLdrQueryInterface
0x14000524d  nop     dword ptr [rax+rax+00h]
0x140005252  test    eax, eax
0x140005254  js      short loc_14000526E
0x140005256  mov     rdx, cs:WdfDriverGlobals
0x14000525d  lea     rcx, WdfBindInfo
0x140005264  mov     rax, [rsp+78h+var_3C+4]
0x140005269  call    _guard_dispatch_icall
0x14000526e  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x140005273  mov     eax, ebx
0x140005275  add     rsp, 58h
0x140005279  pop     r14
0x14000527b  pop     rdi
0x14000527c  pop     rsi
0x14000527d  pop     rbx
0x14000527e  retn
0x140005280  mov     rax, cs:WdfDriverGlobals
0x140005287  cmp     byte ptr [rax+30h], 0
0x14000528b  jz      short loc_1400052A8
0x14000528d  mov     rax, [rdi+68h]
0x140005291  test    rax, rax
0x140005294  jz      short loc_14000529D
0x140005296  mov     cs:qword_14000B468, rax
0x14000529d  lea     rax, FxStubDriverUnload
0x1400052a4  mov     [rdi+68h], rax
0x1400052a8  xor     eax, eax
0x1400052aa  jmp     short loc_140005275
```
