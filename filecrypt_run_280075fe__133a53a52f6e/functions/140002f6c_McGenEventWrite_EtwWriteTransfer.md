# McGenEventWrite_EtwWriteTransfer

- ea: `0x140002f6c`
- end: `0x140002fc9`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `93`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002fd0`
- `0x140003028`
- `0x140003098`
- `0x140003134`

## callees

- `0x140002f6c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140002fb7`
- `ntoskrnl!EtwWriteTransfer` at `0x140002fb7`

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

  v5 = (unsigned __int16 *)qword_140009078;
  if ( qword_140009078 )
  {
    UserData->Ptr = qword_140009078;
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
  return EtwWriteTransfer(FileCryptGuid_Context, a2, &FileCryptGuid, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140002f6c  sub     rsp, 38h
0x140002f70  mov     rcx, cs:qword_140009078
0x140002f77  mov     rax, [rsp+38h+arg_20]
0x140002f7c  test    rcx, rcx
0x140002f7f  jnz     short loc_140002F89
0x140002f81  mov     [rax], rcx
0x140002f84  xor     r8d, r8d
0x140002f87  jmp     short loc_140002F95
0x140002f89  mov     [rax], rcx
0x140002f8c  mov     r8d, 2
0x140002f92  movzx   ecx, word ptr [rcx]
0x140002f95  mov     [rax+8], ecx
0x140002f98  mov     [rax+0Ch], r8d
0x140002f9c  lea     r8, FileCryptGuid; ActivityId
0x140002fa3  mov     rcx, cs:FileCryptGuid_Context; RegHandle
0x140002faa  mov     [rsp+38h+UserData], rax; UserData
0x140002faf  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140002fb4  xor     r9d, r9d; RelatedActivityId
0x140002fb7  call    cs:__imp_EtwWriteTransfer
0x140002fbe  nop     dword ptr [rax+rax+00h]
0x140002fc3  add     rsp, 38h
0x140002fc7  retn
```
