# GetExternalSchannelAlgorithmsDeferred

- ea: `0x140003e30`
- end: `0x140003e9d`
- name: `GetExternalSchannelAlgorithmsDeferred`
- size: `109`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140021960`
- `0x1400219b0`
- `0x140021bb0`
- `0x140021c10`
- `0x1400230a0`
- `0x140023430`
- `0x140028eb0`
- `0x14002f880`
- `0x14002fd60`
- `0x14002fdf0`
- `0x140031100`
- `0x1400311e0`

## callees

- `0x140003e30`
- `0x14000bff0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140003e43`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003e43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003e8f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003e8f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003e58`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003e58`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003e83`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003e83`

## pseudocode

```c
void GetExternalSchannelAlgorithmsDeferred()
{
  if ( !dword_140019534 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_140019534 )
    {
      GetExternalSchannelAlgorithms();
      dword_140019534 = 1;
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140003e30  sub     rsp, 28h
0x140003e34  cmp     cs:dword_140019534, 0
0x140003e3b  jz      short loc_140003E43
0x140003e3d  add     rsp, 28h
0x140003e41  retn
0x140003e43  call    cs:__imp_KeEnterCriticalRegion
0x140003e4a  nop     dword ptr [rax+rax+00h]
0x140003e4f  mov     dl, 1; Wait
0x140003e51  lea     rcx, Resource; Resource
0x140003e58  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140003e5f  nop     dword ptr [rax+rax+00h]
0x140003e64  cmp     cs:dword_140019534, 0
0x140003e6b  jnz     short loc_140003E7C
0x140003e6d  call    GetExternalSchannelAlgorithms
0x140003e72  mov     cs:dword_140019534, 1
0x140003e7c  lea     rcx, Resource; Resource
0x140003e83  call    cs:__imp_ExReleaseResourceLite
0x140003e8a  nop     dword ptr [rax+rax+00h]
0x140003e8f  call    cs:__imp_KeLeaveCriticalRegion
0x140003e96  nop     dword ptr [rax+rax+00h]
0x140003e9b  jmp     short loc_140003E3D
```
