# DsRolepStopDs

- ea: `0x180017fb0`
- end: `0x180017ff8`
- name: `DsRolepStopDs`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x180017fb0`
- `0x180020dbc`

## import_xrefs

- `LSASRV!LsapDsUnitializeDsStateInfo` at `0x180017fbc`
- `LSASRV!LsapDsUnitializeDsStateInfo` at `0x180017fbc`
- `ntdll!RtlNtStatusToDosError` at `0x180017fd0`
- `ntdll!RtlNtStatusToDosError` at `0x180017fd0`
- `NTDSETUP!NtdsInstallShutdown` at `0x180017fc6`
- `NTDSETUP!NtdsInstallShutdown` at `0x180017fc6`

## pseudocode

```c
__int64 __fastcall DsRolepStopDs(char a1)
{
  ULONG v1; // ebx
  NTSTATUS v2; // eax
  ULONG v3; // eax

  v1 = 0;
  if ( a1 )
  {
    v2 = LsapDsUnitializeDsStateInfo();
    if ( v2 < 0 )
      v3 = RtlNtStatusToDosError(v2);
    else
      v3 = NtdsInstallShutdown();
    v1 = v3;
    if ( v3 )
      DsRolepLogPrintRoutine(4, "DsRolepStopDs failed with %lu\n", v3);
  }
  return v1;
}

```

## disassembly

```asm
0x180017fb0  push    rbx
0x180017fb2  sub     rsp, 20h
0x180017fb6  xor     ebx, ebx
0x180017fb8  test    cl, cl
0x180017fba  jz      short loc_180017FF0
0x180017fbc  call    cs:__imp_LsapDsUnitializeDsStateInfo
0x180017fc2  test    eax, eax
0x180017fc4  js      short loc_180017FCE
0x180017fc6  call    cs:__imp_NtdsInstallShutdown
0x180017fcc  jmp     short loc_180017FD6
0x180017fce  mov     ecx, eax; Status
0x180017fd0  call    cs:__imp_RtlNtStatusToDosError
0x180017fd6  mov     ebx, eax
0x180017fd8  test    eax, eax
0x180017fda  jz      short loc_180017FF0
0x180017fdc  mov     r8d, eax
0x180017fdf  lea     rdx, aDsrolepstopdsF; "DsRolepStopDs failed with %lu\n"
0x180017fe6  mov     ecx, 4
0x180017feb  call    DsRolepLogPrintRoutine
0x180017ff0  mov     eax, ebx
0x180017ff2  add     rsp, 20h
0x180017ff6  pop     rbx
0x180017ff7  retn
```
