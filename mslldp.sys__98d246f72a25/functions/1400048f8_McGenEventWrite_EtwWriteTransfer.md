# McGenEventWrite_EtwWriteTransfer

- ea: `0x1400048f8`
- end: `0x140004951`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140004860`
- `0x1400059ac`
- `0x140005d78`
- `0x140005dd0`
- `0x140005e4c`
- `0x140005ef8`

## callees

- `0x1400048f8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000493f`
- `ntoskrnl!EtwWriteTransfer` at `0x14000493f`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_14000B008;
  if ( qword_14000B008 )
  {
    UserData->Ptr = qword_14000B008;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EtwWriteTransfer(LLDP_ETW_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400048f8  sub     rsp, 38h
0x1400048fc  mov     rcx, cs:qword_14000B008
0x140004903  mov     rax, [rsp+38h+arg_20]
0x140004908  test    rcx, rcx
0x14000490b  jnz     short loc_140004915
0x14000490d  mov     [rax], rcx
0x140004910  xor     r8d, r8d
0x140004913  jmp     short loc_140004921
0x140004915  mov     [rax], rcx
0x140004918  mov     r8d, 2
0x14000491e  movzx   ecx, word ptr [rcx]
0x140004921  mov     [rax+8], ecx
0x140004924  mov     [rax+0Ch], r8d
0x140004928  xor     r8d, r8d; ActivityId
0x14000492b  mov     rcx, cs:LLDP_ETW_PROVIDER_Context; RegHandle
0x140004932  mov     [rsp+38h+UserData], rax; UserData
0x140004937  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000493c  xor     r9d, r9d; RelatedActivityId
0x14000493f  call    cs:__imp_EtwWriteTransfer
0x140004946  nop     dword ptr [rax+rax+00h]
0x14000494b  add     rsp, 38h
0x14000494f  retn
```
