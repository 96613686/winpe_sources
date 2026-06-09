# McGenEventWrite_EtwWriteTransfer

- ea: `0x140013840`
- end: `0x140013896`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `86`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140013760`
- `0x1400166e0`
- `0x140016900`
- `0x140016ec0`
- `0x140017040`
- `0x140017220`
- `0x140017dcc`
- `0x14001820c`
- `0x14001cca0`
- `0x140020b68`

## callees

- `0x140013840`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140013884`
- `ntoskrnl!EtwWriteTransfer` at `0x140013884`

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

  v5 = (unsigned __int16 *)qword_140033008;
  if ( qword_140033008 )
  {
    UserData->Ptr = qword_140033008;
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
  return EtwWriteTransfer(REMOTEFS_RDBSS_Context, a2, a3, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140013840  sub     rsp, 38h
0x140013844  mov     rcx, cs:qword_140033008
0x14001384b  mov     rax, [rsp+38h+arg_20]
0x140013850  test    rcx, rcx
0x140013853  jnz     short loc_14001385D
0x140013855  mov     [rax], rcx
0x140013858  xor     r10d, r10d
0x14001385b  jmp     short loc_140013869
0x14001385d  mov     [rax], rcx
0x140013860  mov     r10d, 2
0x140013866  movzx   ecx, word ptr [rcx]
0x140013869  mov     [rax+8], ecx
0x14001386c  mov     [rsp+38h+UserData], rax; UserData
0x140013871  mov     [rax+0Ch], r10d
0x140013875  mov     rcx, cs:REMOTEFS_RDBSS_Context; RegHandle
0x14001387c  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140013881  xor     r9d, r9d; RelatedActivityId
0x140013884  call    cs:__imp_EtwWriteTransfer
0x14001388b  nop     dword ptr [rax+rax+00h]
0x140013890  add     rsp, 38h
0x140013894  retn
```
