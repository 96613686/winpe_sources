# NfsRdrpShutdownRedirector

- ea: `0x1400232dc`
- end: `0x140023382`
- name: `NfsRdrpShutdownRedirector`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, installer_update`

## callers

- `0x1400231c0`

## callees

- `0x1400232dc`
- `0x140023388`
- `0x140023454`
- `0x14002edd4`
- `0x1400393f8`
- `0x140039b40`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140023370`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140023370`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002335f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002335f`

## pseudocode

```c
void NfsRdrpShutdownRedirector()
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( StartContext )
  {
    _InterlockedOr((volatile signed __int32 *)&StartContext[1].DispatcherContext.pTearDownEvent + 1, 8u);
    NfsRdrpSpindownUpcallOperations(StartContext);
    NfsUpCallShutdownRequestQueue(*(_QWORD *)&StartContext[1].DeviceName.Length);
    NfsUpCallDestroyRequestQueue(&StartContext[1].DeviceName);
    NfsRdrpSpindownOperations(StartContext);
    UnInitNfsRedir((__int64)StartContext);
    if ( byte_1400416C0 )
    {
      RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\NfsRdr");
      IoDeleteSymbolicLink(&DestinationString);
    }
  }
}

```

## disassembly

```asm
0x1400232dc  sub     rsp, 38h
0x1400232e0  mov     rax, cs:StartContext
0x1400232e7  xorps   xmm0, xmm0
0x1400232ea  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400232ef  test    rax, rax
0x1400232f2  jz      loc_14002337C
0x1400232f8  lock or dword ptr [rax+90Ch], 8
0x140023300  mov     rcx, cs:StartContext
0x140023307  call    NfsRdrpSpindownUpcallOperations
0x14002330c  mov     rcx, cs:StartContext
0x140023313  mov     rcx, [rcx+7E0h]
0x14002331a  call    NfsUpCallShutdownRequestQueue
0x14002331f  mov     rcx, cs:StartContext
0x140023326  add     rcx, 7E0h
0x14002332d  call    NfsUpCallDestroyRequestQueue
0x140023332  mov     rcx, cs:StartContext
0x140023339  call    NfsRdrpSpindownOperations
0x14002333e  mov     rcx, cs:StartContext
0x140023345  call    UnInitNfsRedir
0x14002334a  cmp     cs:byte_1400416C0, 0
0x140023351  jz      short loc_14002337C
0x140023353  lea     rdx, aDosdevicesNfsr; "\\DosDevices\\NfsRdr"
0x14002335a  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14002335f  call    cs:__imp_RtlInitUnicodeString
0x140023366  nop     dword ptr [rax+rax+00h]
0x14002336b  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x140023370  call    cs:__imp_IoDeleteSymbolicLink
0x140023377  nop     dword ptr [rax+rax+00h]
0x14002337c  add     rsp, 38h
0x140023380  retn
```
