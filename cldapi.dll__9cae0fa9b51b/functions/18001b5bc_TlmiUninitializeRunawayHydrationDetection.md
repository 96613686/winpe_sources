# TlmiUninitializeRunawayHydrationDetection

- ea: `0x18001b5bc`
- end: `0x18001b65a`
- name: `TlmiUninitializeRunawayHydrationDetection`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180011ccc`
- `0x180019d54`

## callees

- `0x18001b5bc`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b5c7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b5c7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b64e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b5df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b602`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b625`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b5df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b602`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b625`

## pseudocode

```c
__int64 TlmiUninitializeRunawayHydrationDetection()
{
  RtlAcquireSRWLockExclusive(&qword_18002A9B8);
  if ( qword_18002AA40 )
  {
    CloseHandle(qword_18002AA40);
    qword_18002AA40 = 0;
  }
  if ( qword_18002AA48 )
  {
    CloseHandle(qword_18002AA48);
    qword_18002AA48 = 0;
  }
  if ( qword_18002AA50 )
  {
    CloseHandle(qword_18002AA50);
    qword_18002AA50 = 0;
  }
  byte_18002A9B0 = 0;
  return RtlReleaseSRWLockExclusive(&qword_18002A9B8);
}

```

## disassembly

```asm
0x18001b5bc  sub     rsp, 28h
0x18001b5c0  lea     rcx, qword_18002A9B8
0x18001b5c7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b5ce  nop     dword ptr [rax+rax+00h]
0x18001b5d3  mov     rcx, cs:qword_18002AA40; hObject
0x18001b5da  test    rcx, rcx
0x18001b5dd  jz      short loc_18001B5F6
0x18001b5df  call    cs:__imp_CloseHandle
0x18001b5e6  nop     dword ptr [rax+rax+00h]
0x18001b5eb  mov     cs:qword_18002AA40, 0
0x18001b5f6  mov     rcx, cs:qword_18002AA48; hObject
0x18001b5fd  test    rcx, rcx
0x18001b600  jz      short loc_18001B619
0x18001b602  call    cs:__imp_CloseHandle
0x18001b609  nop     dword ptr [rax+rax+00h]
0x18001b60e  mov     cs:qword_18002AA48, 0
0x18001b619  mov     rcx, cs:qword_18002AA50; hObject
0x18001b620  test    rcx, rcx
0x18001b623  jz      short loc_18001B63C
0x18001b625  call    cs:__imp_CloseHandle
0x18001b62c  nop     dword ptr [rax+rax+00h]
0x18001b631  mov     cs:qword_18002AA50, 0
0x18001b63c  lea     rcx, qword_18002A9B8
0x18001b643  mov     cs:byte_18002A9B0, 0
0x18001b64a  add     rsp, 28h
0x18001b64e  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
