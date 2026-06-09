# FCFilterUnload

- ea: `0x14000d0a0`
- end: `0x14000d11f`
- name: `FCFilterUnload`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140002f34`
- `0x14000d0a0`
- `0x14000d4c8`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0c3`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0d6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0e9`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0c3`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0d6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000d0e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d106`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d106`
- `FLTMGR!FltUnregisterFilter` at `0x14000d0b0`
- `FLTMGR!FltUnregisterFilter` at `0x14000d0b0`

## pseudocode

```c
__int64 FCFilterUnload()
{
  StSecDeinitialize();
  FltUnregisterFilter(gFilterHandle);
  ExDeleteNPagedLookasideList(&gPre2PostIoContextList);
  ExDeleteNPagedLookasideList(&gPre2PostCreateContextList);
  ExDeleteNPagedLookasideList(&gShadowBufferList);
  if ( gRegistryPath.Buffer )
    ExFreePoolWithTag(gRegistryPath.Buffer, 0x6E694346u);
  McGenEventUnregister_EtwUnregister();
  return 0;
}

```

## disassembly

```asm
0x14000d0a0  sub     rsp, 28h
0x14000d0a4  call    StSecDeinitialize
0x14000d0a9  mov     rcx, cs:gFilterHandle; Filter
0x14000d0b0  call    cs:__imp_FltUnregisterFilter
0x14000d0b7  nop     dword ptr [rax+rax+00h]
0x14000d0bc  lea     rcx, gPre2PostIoContextList; Lookaside
0x14000d0c3  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000d0ca  nop     dword ptr [rax+rax+00h]
0x14000d0cf  lea     rcx, gPre2PostCreateContextList; Lookaside
0x14000d0d6  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000d0dd  nop     dword ptr [rax+rax+00h]
0x14000d0e2  lea     rcx, gShadowBufferList; Lookaside
0x14000d0e9  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000d0f0  nop     dword ptr [rax+rax+00h]
0x14000d0f5  mov     rcx, cs:gRegistryPath.Buffer; P
0x14000d0fc  test    rcx, rcx
0x14000d0ff  jz      short loc_14000D112
0x14000d101  mov     edx, 6E694346h; Tag
0x14000d106  call    cs:__imp_ExFreePoolWithTag
0x14000d10d  nop     dword ptr [rax+rax+00h]
0x14000d112  call    McGenEventUnregister_EtwUnregister
0x14000d117  xor     eax, eax
0x14000d119  add     rsp, 28h
0x14000d11d  retn
```
