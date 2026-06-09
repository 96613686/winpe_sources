# McGenEventWrite_EtwWriteTransfer

- ea: `0x14001fa00`
- end: `0x14001fa60`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x14001fa68`

## callees

- `0x14001fa00`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001fa4e`
- `ntoskrnl!EtwWriteTransfer` at `0x14001fa4e`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  unsigned int v6; // edx

  v5 = (unsigned __int16 *)qword_14002D018;
  if ( qword_14002D018 )
  {
    UserData->Ptr = qword_14002D018;
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
  return EtwWriteTransfer(BTH_POLICY_PROVIDER_Context, &PolicyServiceBlockAudit, 0, 0, 6u, UserData);
}

```

## disassembly

```asm
0x14001fa00  sub     rsp, 38h
0x14001fa04  mov     rcx, cs:qword_14002D018
0x14001fa0b  mov     rax, [rsp+38h+arg_20]
0x14001fa10  test    rcx, rcx
0x14001fa13  jnz     short loc_14001FA1C
0x14001fa15  mov     [rax], rcx
0x14001fa18  xor     edx, edx
0x14001fa1a  jmp     short loc_14001FA27
0x14001fa1c  mov     [rax], rcx
0x14001fa1f  mov     edx, 2
0x14001fa24  movzx   ecx, word ptr [rcx]
0x14001fa27  mov     [rax+8], ecx
0x14001fa2a  xor     r9d, r9d; RelatedActivityId
0x14001fa2d  mov     [rax+0Ch], edx
0x14001fa30  xor     r8d, r8d; ActivityId
0x14001fa33  mov     rcx, cs:BTH_POLICY_PROVIDER_Context; RegHandle
0x14001fa3a  lea     rdx, _PolicyServiceBlockAudit; EventDescriptor
0x14001fa41  mov     [rsp+38h+UserData], rax; UserData
0x14001fa46  mov     [rsp+38h+UserDataCount], 6; UserDataCount
0x14001fa4e  call    cs:__imp_EtwWriteTransfer
0x14001fa55  nop     dword ptr [rax+rax+00h]
0x14001fa5a  add     rsp, 38h
0x14001fa5e  retn
```
