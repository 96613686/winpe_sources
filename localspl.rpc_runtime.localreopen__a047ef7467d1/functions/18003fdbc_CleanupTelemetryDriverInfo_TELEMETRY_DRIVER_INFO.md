# CleanupTelemetryDriverInfo(_TELEMETRY_DRIVER_INFO *)

- ea: `0x18003fdbc`
- end: `0x18003fe83`
- name: `?CleanupTelemetryDriverInfo@@YAXPEAU_TELEMETRY_DRIVER_INFO@@@Z`
- size: `199`
- prototype: `void __fastcall(struct _TELEMETRY_DRIVER_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800685e4`
- `0x1800705a0`

## callees

- `0x18003fdbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fdc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fdc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fe7c`
- `SPOOLSS!DllFreeSplStr` at `0x18003fdd9`
- `SPOOLSS!DllFreeSplStr` at `0x18003fdef`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe06`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe1d`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe34`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe4b`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe62`
- `SPOOLSS!DllFreeSplStr` at `0x18003fdd9`
- `SPOOLSS!DllFreeSplStr` at `0x18003fdef`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe06`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe1d`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe34`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe4b`
- `SPOOLSS!DllFreeSplStr` at `0x18003fe62`

## pseudocode

```c
void __fastcall CleanupTelemetryDriverInfo(struct _TELEMETRY_DRIVER_INFO *a1)
{
  DWORD LastError; // edi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

  LastError = GetLastError();
  if ( *(_QWORD *)a1 )
  {
    DllFreeSplStr(*(_QWORD *)a1);
    *(_QWORD *)a1 = 0;
  }
  v3 = *((_QWORD *)a1 + 1);
  if ( v3 )
  {
    DllFreeSplStr(v3);
    *((_QWORD *)a1 + 1) = 0;
  }
  v4 = *((_QWORD *)a1 + 4);
  if ( v4 )
  {
    DllFreeSplStr(v4);
    *((_QWORD *)a1 + 4) = 0;
  }
  v5 = *((_QWORD *)a1 + 5);
  if ( v5 )
  {
    DllFreeSplStr(v5);
    *((_QWORD *)a1 + 5) = 0;
  }
  v6 = *((_QWORD *)a1 + 8);
  if ( v6 )
  {
    DllFreeSplStr(v6);
    *((_QWORD *)a1 + 8) = 0;
  }
  v7 = *((_QWORD *)a1 + 9);
  if ( v7 )
  {
    DllFreeSplStr(v7);
    *((_QWORD *)a1 + 9) = 0;
  }
  v8 = *((_QWORD *)a1 + 10);
  if ( v8 )
  {
    DllFreeSplStr(v8);
    *((_QWORD *)a1 + 10) = 0;
  }
  SetLastError(LastError);
}

```

## disassembly

```asm
0x18003fdbc  mov     [rsp+arg_0], rbx
0x18003fdc1  push    rdi
0x18003fdc2  sub     rsp, 20h
0x18003fdc6  mov     rbx, rcx
0x18003fdc9  call    cs:__imp_GetLastError
0x18003fdcf  mov     rcx, [rbx]
0x18003fdd2  mov     edi, eax
0x18003fdd4  test    rcx, rcx
0x18003fdd7  jz      short loc_18003FDE6
0x18003fdd9  call    cs:__imp_DllFreeSplStr
0x18003fddf  mov     qword ptr [rbx], 0
0x18003fde6  mov     rcx, [rbx+8]
0x18003fdea  test    rcx, rcx
0x18003fded  jz      short loc_18003FDFD
0x18003fdef  call    cs:__imp_DllFreeSplStr
0x18003fdf5  mov     qword ptr [rbx+8], 0
0x18003fdfd  mov     rcx, [rbx+20h]
0x18003fe01  test    rcx, rcx
0x18003fe04  jz      short loc_18003FE14
0x18003fe06  call    cs:__imp_DllFreeSplStr
0x18003fe0c  mov     qword ptr [rbx+20h], 0
0x18003fe14  mov     rcx, [rbx+28h]
0x18003fe18  test    rcx, rcx
0x18003fe1b  jz      short loc_18003FE2B
0x18003fe1d  call    cs:__imp_DllFreeSplStr
0x18003fe23  mov     qword ptr [rbx+28h], 0
0x18003fe2b  mov     rcx, [rbx+40h]
0x18003fe2f  test    rcx, rcx
0x18003fe32  jz      short loc_18003FE42
0x18003fe34  call    cs:__imp_DllFreeSplStr
0x18003fe3a  mov     qword ptr [rbx+40h], 0
0x18003fe42  mov     rcx, [rbx+48h]
0x18003fe46  test    rcx, rcx
0x18003fe49  jz      short loc_18003FE59
0x18003fe4b  call    cs:__imp_DllFreeSplStr
0x18003fe51  mov     qword ptr [rbx+48h], 0
0x18003fe59  mov     rcx, [rbx+50h]
0x18003fe5d  test    rcx, rcx
0x18003fe60  jz      short loc_18003FE70
0x18003fe62  call    cs:__imp_DllFreeSplStr
0x18003fe68  mov     qword ptr [rbx+50h], 0
0x18003fe70  mov     ecx, edi
0x18003fe72  mov     rbx, [rsp+28h+arg_0]
0x18003fe77  add     rsp, 20h
0x18003fe7b  pop     rdi
0x18003fe7c  jmp     cs:__imp_SetLastError
```
