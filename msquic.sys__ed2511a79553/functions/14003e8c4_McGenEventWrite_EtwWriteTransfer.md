# McGenEventWrite_EtwWriteTransfer

- ea: `0x14003e8c4`
- end: `0x14003e91f`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `91`
- prototype: ``
- caller_count: `45`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002808c`
- `0x140028128`
- `0x1400291f0`
- `0x140029624`
- `0x140029770`
- `0x14002a8dc`
- `0x14002a960`
- `0x14002a9ec`
- `0x14003020c`
- `0x140030e08`
- `0x140031e8c`
- `0x140031f28`
- `0x1400334d8`
- `0x14003b4d4`
- `0x14003e928`
- `0x14003ead8`
- `0x14003eb54`
- `0x14003eb98`
- `0x14003ec10`
- `0x14003eca4`
- `0x14003ed00`
- `0x14003fcc4`
- `0x14003fd84`
- `0x14003fdf8`
- `0x14003fea4`
- `0x140040c2c`
- `0x140040de8`
- `0x1400417e0`
- `0x1400418c0`
- `0x140042668`
- `0x1400426e8`
- `0x14004275c`
- `0x1400427e0`
- `0x140042878`
- `0x14004290c`
- `0x1400429a0`
- `0x140042a2c`
- `0x140044c28`
- `0x1400453d0`
- `0x14004545c`
- `0x140049238`
- `0x140049ec0`
- `0x14004a12c`
- `0x14004a32c`
- `0x14004a3f8`

## callees

- `0x14003e8c4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14003e90d`
- `ntoskrnl!EtwWriteTransfer` at `0x14003e90d`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // eax
  ULONG v7; // r8d

  v5 = (unsigned __int16 *)qword_14005C0C8;
  v6 = 0;
  if ( qword_14005C0C8 )
  {
    UserData->Ptr = qword_14005C0C8;
    v6 = 2;
    v7 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v7 = 0;
  }
  UserData->Size = v7;
  UserData->Reserved = v6;
  return EtwWriteTransfer(MICROSOFT_MSQUIC_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14003e8c4  sub     rsp, 38h
0x14003e8c8  mov     r8, cs:qword_14005C0C8
0x14003e8cf  xor     eax, eax
0x14003e8d1  mov     rcx, [rsp+38h+arg_20]
0x14003e8d6  test    r8, r8
0x14003e8d9  jnz     short loc_14003E8E3
0x14003e8db  mov     [rcx], rax
0x14003e8de  mov     r8d, eax
0x14003e8e1  jmp     short loc_14003E8EF
0x14003e8e3  mov     [rcx], r8
0x14003e8e6  mov     eax, 2
0x14003e8eb  movzx   r8d, word ptr [r8]
0x14003e8ef  mov     [rcx+8], r8d
0x14003e8f3  xor     r8d, r8d; ActivityId
0x14003e8f6  mov     [rsp+38h+UserData], rcx; UserData
0x14003e8fb  mov     [rcx+0Ch], eax
0x14003e8fe  mov     rcx, cs:MICROSOFT_MSQUIC_PROVIDER_Context; RegHandle
0x14003e905  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14003e90a  xor     r9d, r9d; RelatedActivityId
0x14003e90d  call    cs:__imp_EtwWriteTransfer
0x14003e914  nop     dword ptr [rax+rax+00h]
0x14003e919  add     rsp, 38h
0x14003e91d  retn
```
