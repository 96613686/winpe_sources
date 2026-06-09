# PrjfFreeCommandBuffer

- ea: `0x14003a5cc`
- end: `0x14003a617`
- name: `PrjfFreeCommandBuffer`
- size: `75`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004640`
- `0x1400047cc`
- `0x1400339a8`
- `0x140034428`
- `0x1400346f0`
- `0x1400349fc`
- `0x140034c70`
- `0x140034e88`
- `0x140035060`

## callees

- `0x14000b1d0`
- `0x14003a5cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003a605`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a605`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003a5f2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003a5f2`

## pseudocode

```c
void __fastcall PrjfFreeCommandBuffer(PVOID Entry, __int64 a2, __int64 a3, __int64 a4)
{
  if ( Entry )
  {
    if ( (unsigned int)a2 > 0x790 )
      ExFreePoolWithTag(Entry, 0x62634A50u);
    else
      ExFreeToPagedLookasideList(&stru_14001AAC0, Entry);
  }
  else if ( (_DWORD)a2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(0, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x14003a5cc  sub     rsp, 28h
0x14003a5d0  test    rcx, rcx
0x14003a5d3  jnz     short loc_14003A5E0
0x14003a5d5  test    edx, edx
0x14003a5d7  jz      short loc_14003A611
0x14003a5d9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003a5de  jmp     short loc_14003A611
0x14003a5e0  cmp     edx, 790h
0x14003a5e6  ja      short loc_14003A600
0x14003a5e8  mov     rdx, rcx; Entry
0x14003a5eb  lea     rcx, stru_14001AAC0; Lookaside
0x14003a5f2  call    cs:__imp_ExFreeToPagedLookasideList
0x14003a5f9  nop     dword ptr [rax+rax+00h]
0x14003a5fe  jmp     short loc_14003A611
0x14003a600  mov     edx, 62634A50h; Tag
0x14003a605  call    cs:__imp_ExFreePoolWithTag
0x14003a60c  nop     dword ptr [rax+rax+00h]
0x14003a611  add     rsp, 28h
0x14003a615  retn
```
