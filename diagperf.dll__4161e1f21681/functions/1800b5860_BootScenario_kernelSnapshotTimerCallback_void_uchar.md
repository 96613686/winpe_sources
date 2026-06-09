# BootScenario::_kernelSnapshotTimerCallback(void *,uchar)

- ea: `0x1800b5860`
- end: `0x1800b5898`
- name: `?_kernelSnapshotTimerCallback@BootScenario@@CAXPEAXE@Z`
- size: `56`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800b5860`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800b588d`
- `ntdll!EtwEventWrite` at `0x1800b588d`

## pseudocode

```c
void __fastcall BootScenario::_kernelSnapshotTimerCallback(_DWORD *a1)
{
  int v1; // eax

  if ( a1 )
  {
    v1 = a1[6];
    *((_QWORD *)a1 + 5) = 0;
    if ( v1 == 2 )
      EtwEventWrite(PerfDiagOutput::StatusLog::g_RegHandle, PDEvt_Boot_Loopback_SnapshotKMScenario, 0, 0);
  }
}

```

## disassembly

```asm
0x1800b5860  sub     rsp, 28h
0x1800b5864  test    rcx, rcx
0x1800b5867  jz      short loc_1800B5893
0x1800b5869  mov     eax, [rcx+18h]
0x1800b586c  mov     qword ptr [rcx+28h], 0
0x1800b5874  cmp     eax, 2
0x1800b5877  jnz     short loc_1800B5893
0x1800b5879  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x1800b5880  lea     rdx, PDEvt_Boot_Loopback_SnapshotKMScenario
0x1800b5887  xor     r9d, r9d
0x1800b588a  xor     r8d, r8d
0x1800b588d  call    cs:__imp_EtwEventWrite
0x1800b5893  add     rsp, 28h
0x1800b5897  retn
```
