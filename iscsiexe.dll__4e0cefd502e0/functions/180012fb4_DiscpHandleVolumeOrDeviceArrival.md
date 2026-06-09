# DiscpHandleVolumeOrDeviceArrival

- ea: `0x180012fb4`
- end: `0x180013024`
- name: `DiscpHandleVolumeOrDeviceArrival`
- size: `112`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012a18`
- `0x180012bfc`

## callees

- `0x180012fb4`

## import_xrefs

- `ISCSIUM!DiscpRemoveStringFromMultiSzList` at `0x180012fea`
- `ISCSIUM!DiscpRemoveStringFromMultiSzList` at `0x180012fea`
- `ntdll!RtlLeaveCriticalSection` at `0x180013001`
- `ntdll!RtlLeaveCriticalSection` at `0x180013001`
- `ntdll!RtlEnterCriticalSection` at `0x180012fd3`
- `ntdll!RtlEnterCriticalSection` at `0x180012fd3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013013`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013013`

## pseudocode

```c
NTSTATUS __fastcall DiscpHandleVolumeOrDeviceArrival(__int64 a1)
{
  __int16 v2; // bx
  NTSTATUS result; // eax

  if ( DiscpPersistentVolumeList )
  {
    RtlEnterCriticalSection(&DiscpCritSection);
    DiscpRemoveStringFromMultiSzList(&DiscpPersistentVolumeList, &DiscpPersistentVolumeListSize, a1);
    v2 = *(_WORD *)DiscpPersistentVolumeList;
    result = RtlLeaveCriticalSection(&DiscpCritSection);
    if ( !v2 )
      return SetEvent(DiscpVolumeArrivalEventHandle);
  }
  return result;
}

```

## disassembly

```asm
0x180012fb4  mov     [rsp+arg_0], rbx
0x180012fb9  push    rdi
0x180012fba  sub     rsp, 20h
0x180012fbe  xor     edi, edi
0x180012fc0  mov     rbx, rcx
0x180012fc3  cmp     cs:DiscpPersistentVolumeList, rdi
0x180012fca  jz      short loc_180013019
0x180012fcc  lea     rcx, DiscpCritSection; CriticalSection
0x180012fd3  call    cs:__imp_RtlEnterCriticalSection
0x180012fd9  mov     r8, rbx
0x180012fdc  lea     rdx, DiscpPersistentVolumeListSize
0x180012fe3  lea     rcx, DiscpPersistentVolumeList
0x180012fea  call    cs:__imp_DiscpRemoveStringFromMultiSzList
0x180012ff0  mov     rax, cs:DiscpPersistentVolumeList
0x180012ff7  lea     rcx, DiscpCritSection; CriticalSection
0x180012ffe  movzx   ebx, word ptr [rax]
0x180013001  call    cs:__imp_RtlLeaveCriticalSection
0x180013007  test    bx, bx
0x18001300a  jnz     short loc_180013019
0x18001300c  mov     rcx, cs:DiscpVolumeArrivalEventHandle; hEvent
0x180013013  call    cs:__imp_SetEvent
0x180013019  mov     rbx, [rsp+28h+arg_0]
0x18001301e  add     rsp, 20h
0x180013022  pop     rdi
0x180013023  retn
```
