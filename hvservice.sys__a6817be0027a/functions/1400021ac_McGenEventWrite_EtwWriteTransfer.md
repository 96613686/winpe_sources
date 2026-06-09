# McGenEventWrite_EtwWriteTransfer

- ea: `0x1400021ac`
- end: `0x140002205`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: `NTSTATUS __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000220c`
- `0x140002254`
- `0x1400022b4`
- `0x14000234c`

## callees

- `0x1400021ac`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400021f3`
- `ntoskrnl!EtwWriteTransfer` at `0x1400021f3`

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

  v5 = (unsigned __int16 *)qword_140009008;
  if ( qword_140009008 )
  {
    UserData->Ptr = qword_140009008;
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
  return EtwWriteTransfer(HvBootDriverControlGuid_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400021ac  sub     rsp, 38h
0x1400021b0  mov     rcx, cs:qword_140009008
0x1400021b7  mov     rax, [rsp+38h+arg_20]
0x1400021bc  test    rcx, rcx
0x1400021bf  jnz     short loc_1400021C9
0x1400021c1  mov     [rax], rcx
0x1400021c4  xor     r8d, r8d
0x1400021c7  jmp     short loc_1400021D5
0x1400021c9  mov     [rax], rcx
0x1400021cc  mov     r8d, 2
0x1400021d2  movzx   ecx, word ptr [rcx]
0x1400021d5  mov     [rax+8], ecx
0x1400021d8  mov     [rax+0Ch], r8d
0x1400021dc  xor     r8d, r8d; ActivityId
0x1400021df  mov     rcx, cs:HvBootDriverControlGuid_Context; RegHandle
0x1400021e6  mov     [rsp+38h+UserData], rax; UserData
0x1400021eb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1400021f0  xor     r9d, r9d; RelatedActivityId
0x1400021f3  call    cs:__imp_EtwWriteTransfer
0x1400021fa  nop     dword ptr [rax+rax+00h]
0x1400021ff  add     rsp, 38h
0x140002203  retn
```
