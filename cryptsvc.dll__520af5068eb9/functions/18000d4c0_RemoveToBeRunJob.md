# RemoveToBeRunJob

- ea: `0x18000d4c0`
- end: `0x18000d519`
- name: `RemoveToBeRunJob`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b60`
- `0x180004998`
- `0x18000b918`
- `0x18000d134`

## callees

- `0x18000d4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d512`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4d0`

## pseudocode

```c
void __fastcall RemoveToBeRunJob(__int64 a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rcx

  EnterCriticalSection(&JobsCriticalSection);
  v2 = *(_QWORD **)a1;
  v3 = *(_QWORD **)(a1 + 8);
  if ( *(_QWORD *)a1 )
  {
    v2[1] = v3;
    *(_QWORD *)a1 = 0;
  }
  if ( v3 )
  {
    *v3 = v2;
    *(_QWORD *)(a1 + 8) = 0;
  }
  else
  {
    pToBeRunJobHead = v2;
  }
  LeaveCriticalSection(&JobsCriticalSection);
}

```

## disassembly

```asm
0x18000d4c0  push    rbx
0x18000d4c2  sub     rsp, 20h
0x18000d4c6  mov     rbx, rcx
0x18000d4c9  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d4d0  call    cs:__imp_EnterCriticalSection
0x18000d4d6  mov     rax, [rbx]
0x18000d4d9  mov     rcx, [rbx+8]
0x18000d4dd  test    rax, rax
0x18000d4e0  jz      short loc_18000D4ED
0x18000d4e2  mov     [rax+8], rcx
0x18000d4e6  mov     qword ptr [rbx], 0
0x18000d4ed  test    rcx, rcx
0x18000d4f0  jz      short loc_18000D4FF
0x18000d4f2  mov     [rcx], rax
0x18000d4f5  mov     qword ptr [rbx+8], 0
0x18000d4fd  jmp     short loc_18000D506
0x18000d4ff  mov     cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA, rax; _CUCS_JOB_HEADER * pToBeRunJobHead
0x18000d506  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION JobsCriticalSection
0x18000d50d  add     rsp, 20h
0x18000d511  pop     rbx
0x18000d512  jmp     cs:__imp_LeaveCriticalSection
```
