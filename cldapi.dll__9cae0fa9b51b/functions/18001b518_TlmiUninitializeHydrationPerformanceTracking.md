# TlmiUninitializeHydrationPerformanceTracking

- ea: `0x18001b518`
- end: `0x18001b5b6`
- name: `TlmiUninitializeHydrationPerformanceTracking`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011ccc`
- `0x180019a6c`

## callees

- `0x18001b518`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b523`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b523`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b5aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b53b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b55e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b53b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b55e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b581`

## pseudocode

```c
__int64 TlmiUninitializeHydrationPerformanceTracking()
{
  RtlAcquireSRWLockExclusive(&qword_18002AA60);
  if ( hEvent )
  {
    CloseHandle(hEvent);
    hEvent = 0;
  }
  if ( qword_18002AB50 )
  {
    CloseHandle(qword_18002AB50);
    qword_18002AB50 = 0;
  }
  if ( qword_18002AB58 )
  {
    CloseHandle(qword_18002AB58);
    qword_18002AB58 = 0;
  }
  byte_18002AA58 = 0;
  return RtlReleaseSRWLockExclusive(&qword_18002AA60);
}

```

## disassembly

```asm
0x18001b518  sub     rsp, 28h
0x18001b51c  lea     rcx, qword_18002AA60
0x18001b523  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b52a  nop     dword ptr [rax+rax+00h]
0x18001b52f  mov     rcx, cs:hEvent; hObject
0x18001b536  test    rcx, rcx
0x18001b539  jz      short loc_18001B552
0x18001b53b  call    cs:__imp_CloseHandle
0x18001b542  nop     dword ptr [rax+rax+00h]
0x18001b547  mov     cs:hEvent, 0
0x18001b552  mov     rcx, cs:qword_18002AB50; hObject
0x18001b559  test    rcx, rcx
0x18001b55c  jz      short loc_18001B575
0x18001b55e  call    cs:__imp_CloseHandle
0x18001b565  nop     dword ptr [rax+rax+00h]
0x18001b56a  mov     cs:qword_18002AB50, 0
0x18001b575  mov     rcx, cs:qword_18002AB58; hObject
0x18001b57c  test    rcx, rcx
0x18001b57f  jz      short loc_18001B598
0x18001b581  call    cs:__imp_CloseHandle
0x18001b588  nop     dword ptr [rax+rax+00h]
0x18001b58d  mov     cs:qword_18002AB58, 0
0x18001b598  lea     rcx, qword_18002AA60
0x18001b59f  mov     cs:byte_18002AA58, 0
0x18001b5a6  add     rsp, 28h
0x18001b5aa  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
