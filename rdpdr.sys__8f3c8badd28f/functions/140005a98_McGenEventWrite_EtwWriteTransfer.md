# McGenEventWrite_EtwWriteTransfer

- ea: `0x140005a98`
- end: `0x140005af9`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `97`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005b00`

## callees

- `0x140005a98`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140005ae7`
- `ntoskrnl!EtwWriteTransfer` at `0x140005ae7`

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
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_14000C048;
  if ( qword_14000C048 )
  {
    UserData->Ptr = qword_14000C048;
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
  return EtwWriteTransfer(RDPDR_PROVIDER_Context, &TRIGGER_SCDEVICEENUM, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x140005a98  sub     rsp, 38h
0x140005a9c  mov     rcx, cs:qword_14000C048
0x140005aa3  mov     r8d, 2
0x140005aa9  mov     rax, [rsp+38h+arg_20]
0x140005aae  test    rcx, rcx
0x140005ab1  jnz     short loc_140005ABA
0x140005ab3  mov     [rax], rcx
0x140005ab6  xor     edx, edx
0x140005ab8  jmp     short loc_140005AC3
0x140005aba  mov     [rax], rcx
0x140005abd  mov     edx, r8d
0x140005ac0  movzx   ecx, word ptr [rcx]
0x140005ac3  mov     [rax+8], ecx
0x140005ac6  xor     r9d, r9d; RelatedActivityId
0x140005ac9  mov     [rax+0Ch], edx
0x140005acc  lea     rdx, TRIGGER_SCDEVICEENUM; EventDescriptor
0x140005ad3  mov     rcx, cs:RDPDR_PROVIDER_Context; RegHandle
0x140005ada  mov     [rsp+38h+UserData], rax; UserData
0x140005adf  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x140005ae4  xor     r8d, r8d; ActivityId
0x140005ae7  call    cs:__imp_EtwWriteTransfer
0x140005aee  nop     dword ptr [rax+rax+00h]
0x140005af3  add     rsp, 38h
0x140005af7  retn
```
