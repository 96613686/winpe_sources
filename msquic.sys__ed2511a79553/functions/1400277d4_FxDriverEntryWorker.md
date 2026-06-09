# FxDriverEntryWorker

- ea: `0x1400277d4`
- end: `0x14002792d`
- name: `FxDriverEntryWorker`
- size: `345`
- prototype: `__int64 __fastcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400277a0`

## callees

- `0x140027700`
- `0x140027760`
- `0x1400277d4`
- `0x140027994`
- `0x140027a5c`
- `0x140027ce6`
- `0x14006503c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002782d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002782d`
- `ntoskrnl!DbgPrintEx` at `0x1400278ad`
- `ntoskrnl!DbgPrintEx` at `0x1400278ad`

## pseudocode

```c
NTSTATUS __fastcall FxDriverEntryWorker(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS result; // eax
  int inited; // ebx
  NTSTATUS v6; // eax
  PDRIVER_UNLOAD DriverUnload; // rax

  if ( !DriverObject )
    return DriverEntry(0, RegistryPath);
  qword_14005C3B8 = (__int64)DriverObject;
  *(_DWORD *)&DestinationString.Length = 34078720;
  DestinationString.Buffer = (PWSTR)qword_14005C180;
  RtlCopyUnicodeString(&DestinationString, RegistryPath);
  result = WdfVersionBind_0(DriverObject, &DestinationString, &WdfBindInfo, &WdfDriverGlobals);
  if ( result >= 0 )
  {
    WdfDriverMiniportUnloadOverride = *(_QWORD *)(WdfFunctions_01015 + 1608);
    inited = FxStubBindClasses((struct _WDF_BIND_INFO *)&WdfBindInfo);
    if ( inited < 0 )
      goto LABEL_8;
    inited = FxStubInitTypes();
    if ( inited < 0 )
      goto LABEL_8;
    v6 = DriverEntry(DriverObject, RegistryPath);
    inited = v6;
    if ( v6 < 0 )
    {
      DbgPrintEx(0x4Du, 0, "DriverEntry failed 0x%x for driver %wZ\n", (unsigned int)v6, &DestinationString);
      FxStubDriverEntryFailure();
LABEL_8:
      FxStubDriverUnloadCommon();
      return inited;
    }
    if ( WdfDriverGlobals->DisplaceDriverUnload )
    {
      DriverUnload = (PDRIVER_UNLOAD)qword_14005C3C0;
      if ( DriverObject->DriverUnload )
        DriverUnload = DriverObject->DriverUnload;
      qword_14005C3C0 = (__int64)DriverUnload;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)FxStubDriverUnload;
    }
    else if ( (WdfDriverGlobals->DriverFlags & 2) != 0 )
    {
      WdfDriverMiniportUnloadOverride = (__int64)FxStubDriverMiniportUnload;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400277d4  mov     rax, rsp
0x1400277d7  mov     [rax+8], rbx
0x1400277db  mov     [rax+10h], rbp
0x1400277df  mov     [rax+18h], rsi
0x1400277e3  mov     [rax+20h], rdi
0x1400277e7  push    r14
0x1400277e9  sub     rsp, 30h
0x1400277ed  xor     ebp, ebp
0x1400277ef  mov     rsi, rdx
0x1400277f2  mov     rdi, rcx
0x1400277f5  test    rcx, rcx
0x1400277f8  jnz     short loc_140027804
0x1400277fa  call    DriverEntry
0x1400277ff  jmp     loc_1400278C5
0x140027804  lea     rax, qword_14005C180
0x14002780b  mov     cs:qword_14005C3B8, rdi
0x140027812  lea     r14, DestinationString
0x140027819  mov     dword ptr cs:DestinationString.Length, 2080000h
0x140027823  mov     rcx, r14; DestinationString
0x140027826  mov     cs:DestinationString.Buffer, rax
0x14002782d  call    cs:__imp_RtlCopyUnicodeString
0x140027834  nop     dword ptr [rax+rax+00h]
0x140027839  lea     r9, WdfDriverGlobals
0x140027840  mov     rdx, r14
0x140027843  lea     r8, WdfBindInfo
0x14002784a  mov     rcx, rdi
0x14002784d  call    WdfVersionBind_0
0x140027852  test    eax, eax
0x140027854  js      short loc_1400278C5
0x140027856  mov     rax, cs:WdfFunctions_01015
0x14002785d  lea     rcx, WdfBindInfo; struct _WDF_BIND_INFO *
0x140027864  mov     rdx, [rax+648h]
0x14002786b  mov     cs:WdfDriverMiniportUnloadOverride, rdx
0x140027872  call    ?FxStubBindClasses@@YAJPEAU_WDF_BIND_INFO@@@Z; FxStubBindClasses(_WDF_BIND_INFO *)
0x140027877  mov     ebx, eax
0x140027879  test    eax, eax
0x14002787b  js      short loc_1400278BE
0x14002787d  call    ?FxStubInitTypes@@YAJXZ; FxStubInitTypes(void)
0x140027882  mov     ebx, eax
0x140027884  test    eax, eax
0x140027886  js      short loc_1400278BE
0x140027888  mov     rdx, rsi; RegistryPath
0x14002788b  mov     rcx, rdi; DriverObject
0x14002788e  call    DriverEntry
0x140027893  mov     ebx, eax
0x140027895  test    eax, eax
0x140027897  jns     short loc_1400278E1
0x140027899  xor     edx, edx; Level
0x14002789b  mov     [rsp+38h+var_18], r14
0x1400278a0  mov     r9d, eax
0x1400278a3  lea     r8, aDriverentryFai; "DriverEntry failed 0x%x for driver %wZ"...
0x1400278aa  lea     ecx, [rdx+4Dh]; ComponentId
0x1400278ad  call    cs:__imp_DbgPrintEx
0x1400278b4  nop     dword ptr [rax+rax+00h]
0x1400278b9  call    ?FxStubDriverEntryFailure@@YAXXZ; FxStubDriverEntryFailure(void)
0x1400278be  call    ?FxStubDriverUnloadCommon@@YAXXZ; FxStubDriverUnloadCommon(void)
0x1400278c3  mov     eax, ebx
0x1400278c5  mov     rbx, [rsp+38h+arg_0]
0x1400278ca  mov     rbp, [rsp+38h+arg_8]
0x1400278cf  mov     rsi, [rsp+38h+arg_10]
0x1400278d4  mov     rdi, [rsp+38h+arg_18]
0x1400278d9  add     rsp, 30h
0x1400278dd  pop     r14
0x1400278df  retn
0x1400278e1  mov     rax, cs:WdfDriverGlobals
0x1400278e8  cmp     [rax+30h], bpl
0x1400278ec  jz      short loc_140027914
0x1400278ee  mov     rcx, [rdi+68h]
0x1400278f2  mov     rax, cs:qword_14005C3C0
0x1400278f9  test    rcx, rcx
0x1400278fc  cmovnz  rax, rcx
0x140027900  mov     cs:qword_14005C3C0, rax
0x140027907  lea     rax, FxStubDriverUnload
0x14002790e  mov     [rdi+68h], rax
0x140027912  jmp     short loc_140027929
0x140027914  mov     eax, [rax+8]
0x140027917  test    al, 2
0x140027919  jz      short loc_140027929
0x14002791b  lea     rax, FxStubDriverMiniportUnload
0x140027922  mov     cs:WdfDriverMiniportUnloadOverride, rax
0x140027929  xor     eax, eax
0x14002792b  jmp     short loc_1400278C5
```
