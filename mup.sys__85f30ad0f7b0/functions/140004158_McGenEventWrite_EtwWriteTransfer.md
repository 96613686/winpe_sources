# McGenEventWrite_EtwWriteTransfer

- ea: `0x140004158`
- end: `0x1400041b1`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400041b8`
- `0x14000426c`
- `0x140004304`
- `0x1400043ec`
- `0x1400044bc`
- `0x14000458c`

## callees

- `0x140004158`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000419f`
- `ntoskrnl!EtwWriteTransfer` at `0x14000419f`

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

  v5 = (unsigned __int16 *)qword_14000A028;
  if ( qword_14000A028 )
  {
    UserData->Ptr = qword_14000A028;
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
  return EtwWriteTransfer(REMOTEFS_MUP_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140004158  sub     rsp, 38h
0x14000415c  mov     rcx, cs:qword_14000A028
0x140004163  mov     rax, [rsp+38h+arg_20]
0x140004168  test    rcx, rcx
0x14000416b  jnz     short loc_140004175
0x14000416d  mov     [rax], rcx
0x140004170  xor     r8d, r8d
0x140004173  jmp     short loc_140004181
0x140004175  mov     [rax], rcx
0x140004178  mov     r8d, 2
0x14000417e  movzx   ecx, word ptr [rcx]
0x140004181  mov     [rax+8], ecx
0x140004184  mov     [rax+0Ch], r8d
0x140004188  xor     r8d, r8d; ActivityId
0x14000418b  mov     rcx, cs:REMOTEFS_MUP_Context; RegHandle
0x140004192  mov     [rsp+38h+UserData], rax; UserData
0x140004197  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000419c  xor     r9d, r9d; RelatedActivityId
0x14000419f  call    cs:__imp_EtwWriteTransfer
0x1400041a6  nop     dword ptr [rax+rax+00h]
0x1400041ab  add     rsp, 38h
0x1400041af  retn
```
