# McGenEventWrite_EtwWriteTransfer

- ea: `0x1400062a0`
- end: `0x1400062f6`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: ``

## callers

- `0x140004ed0`
- `0x1400050a0`
- `0x140005c30`
- `0x1400061e0`
- `0x140006f60`
- `0x140007000`
- `0x140007230`
- `0x14000740c`
- `0x14002249c`
- `0x140022514`
- `0x14002675c`
- `0x140026804`
- `0x14002689c`
- `0x14002693c`
- `0x140029ff4`
- `0x140036ea0`
- `0x140036fb4`
- `0x14003708c`
- `0x1400371a0`
- `0x140037258`
- `0x14003c578`
- `0x14003c64c`
- `0x14003c7d4`
- `0x14003c914`
- `0x14003ca70`
- `0x14003cbc8`
- `0x14003cd58`
- `0x14003ceec`
- `0x14003d06c`
- `0x14003d258`
- `0x14003d460`
- `0x14003d5e0`
- `0x14003d72c`
- `0x14003d8ac`
- `0x14003d954`
- `0x14003da0c`
- `0x14003dac8`

## callees

- `0x1400062a0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400062d6`
- `ntoskrnl!EtwWriteTransfer` at `0x1400062d6`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r10d

  v5 = (unsigned __int16 *)qword_14004D008;
  if ( qword_14004D008 )
  {
    UserData->Ptr = qword_14004D008;
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
  return EtwWriteTransfer(StorDiagProvider_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400062a0  sub     rsp, 38h
0x1400062a4  mov     rcx, cs:qword_14004D008
0x1400062ab  mov     rax, [rsp+38h+arg_20]
0x1400062b0  test    rcx, rcx
0x1400062b3  jnz     short loc_1400062E8
0x1400062b5  mov     [rax], rcx
0x1400062b8  xor     r10d, r10d
0x1400062bb  mov     [rax+8], ecx
0x1400062be  mov     [rsp+38h+UserData], rax; UserData
0x1400062c3  mov     [rax+0Ch], r10d
0x1400062c7  mov     rcx, cs:StorDiagProvider_Context; RegHandle
0x1400062ce  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1400062d3  xor     r9d, r9d; RelatedActivityId
0x1400062d6  call    cs:__imp_EtwWriteTransfer
0x1400062dd  nop     dword ptr [rax+rax+00h]
0x1400062e2  add     rsp, 38h
0x1400062e6  retn
0x1400062e8  mov     [rax], rcx
0x1400062eb  mov     r10d, 2
0x1400062f1  movzx   ecx, word ptr [rcx]
0x1400062f4  jmp     short loc_1400062BB
```
