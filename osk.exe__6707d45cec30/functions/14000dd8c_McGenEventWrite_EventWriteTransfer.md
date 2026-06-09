# McGenEventWrite_EventWriteTransfer

- ea: `0x14000dd8c`
- end: `0x14000ddde`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140007f54`
- `0x14000e16c`
- `0x140011178`
- `0x140013b1c`
- `0x140013eac`
- `0x1400154b8`
- `0x140018db0`
- `0x1400192a4`
- `0x140019ae8`
- `0x14001acc0`

## callees

- `0x14000dd8c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x14000ddd3`
- `ADVAPI32!EventWriteTransfer` at `0x14000ddd3`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_140036008;
  if ( qword_140036008 )
  {
    UserData->Ptr = qword_140036008;
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
  return EventWriteTransfer(MS_OSK_Provider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000dd8c  sub     rsp, 38h
0x14000dd90  mov     rcx, cs:qword_140036008
0x14000dd97  mov     rax, [rsp+38h+arg_20]
0x14000dd9c  test    rcx, rcx
0x14000dd9f  jnz     short loc_14000DDA9
0x14000dda1  mov     [rax], rcx
0x14000dda4  xor     r8d, r8d
0x14000dda7  jmp     short loc_14000DDB5
0x14000dda9  mov     [rax], rcx
0x14000ddac  mov     r8d, 2
0x14000ddb2  movzx   ecx, word ptr [rcx]
0x14000ddb5  mov     [rax+8], ecx
0x14000ddb8  mov     [rax+0Ch], r8d
0x14000ddbc  xor     r8d, r8d; ActivityId
0x14000ddbf  mov     rcx, cs:MS_OSK_Provider_Context; RegHandle
0x14000ddc6  mov     [rsp+38h+UserData], rax; UserData
0x14000ddcb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000ddd0  xor     r9d, r9d; RelatedActivityId
0x14000ddd3  call    cs:__imp_EventWriteTransfer
0x14000ddd9  add     rsp, 38h
0x14000dddd  retn
```
