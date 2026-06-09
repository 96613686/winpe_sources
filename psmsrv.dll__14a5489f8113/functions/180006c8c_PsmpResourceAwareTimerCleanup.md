# PsmpResourceAwareTimerCleanup

- ea: `0x180006c8c`
- end: `0x180006cf2`
- name: `PsmpResourceAwareTimerCleanup`
- size: `102`
- prototype: `BOOLEAN __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800065a0`
- `0x180006750`
- `0x180007214`

## callees

- `0x180006c8c`
- `0x180006d00`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006cc3`
- `ntdll!RtlFreeHeap` at `0x180006cc3`
- `ntdll!TpReleaseTimer` at `0x180006ca5`
- `ntdll!TpReleaseTimer` at `0x180006ca5`
- `ntdll!NtDeleteWnfStateName` at `0x180006ce3`

## pseudocode

```c
BOOLEAN __fastcall PsmpResourceAwareTimerCleanup(__int64 a1)
{
  BOOLEAN result; // al
  __int64 v3; // rcx
  void *v4; // r8

  result = PsmpResourceAwareTimerReset(a1, 0);
  v3 = *(_QWORD *)(a1 + 40);
  if ( v3 )
    result = TpReleaseTimer(v3);
  v4 = *(void **)(a1 + 88);
  if ( v4 )
    result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( (*(_BYTE *)(a1 + 64) & 2) == 0 && (*(_DWORD *)(a1 + 48) || *(_DWORD *)(a1 + 52)) )
    return NtDeleteWnfStateName(a1 + 48);
  return result;
}

```

## disassembly

```asm
0x180006c8c  push    rbx
0x180006c8e  sub     rsp, 20h
0x180006c92  xor     edx, edx
0x180006c94  mov     rbx, rcx
0x180006c97  call    PsmpResourceAwareTimerReset
0x180006c9c  mov     rcx, [rbx+28h]
0x180006ca0  test    rcx, rcx
0x180006ca3  jz      short loc_180006CAB
0x180006ca5  call    cs:__imp_TpReleaseTimer
0x180006cab  mov     r8, [rbx+58h]; P
0x180006caf  test    r8, r8
0x180006cb2  jz      short loc_180006CC9
0x180006cb4  mov     rcx, gs:60h
0x180006cbd  xor     edx, edx; Flags
0x180006cbf  mov     rcx, [rcx+30h]; HeapHandle
0x180006cc3  call    cs:__imp_RtlFreeHeap
0x180006cc9  test    byte ptr [rbx+40h], 2
0x180006ccd  jz      short loc_180006CD5
0x180006ccf  add     rsp, 20h
0x180006cd3  pop     rbx
0x180006cd4  retn
0x180006cd5  lea     rcx, [rbx+30h]
0x180006cd9  cmp     dword ptr [rcx], 0
0x180006cdc  jz      short loc_180006CEA
0x180006cde  add     rsp, 20h
0x180006ce2  pop     rbx
0x180006ce3  jmp     cs:__imp_NtDeleteWnfStateName
0x180006cea  cmp     dword ptr [rbx+34h], 0
0x180006cee  jz      short loc_180006CCF
0x180006cf0  jmp     short loc_180006CDE
```
