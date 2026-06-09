# McGenEventWrite_EtwWriteTransfer

- ea: `0x140006950`
- end: `0x1400069b1`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `97`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400069b8`

## callees

- `0x140006950`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000699f`
- `ntoskrnl!EtwWriteTransfer` at `0x14000699f`

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

  v5 = (unsigned __int16 *)qword_1400310E8;
  if ( qword_1400310E8 )
  {
    UserData->Ptr = qword_1400310E8;
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
  return EtwWriteTransfer(IPNAT_Context, &DebugTrace, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x140006950  sub     rsp, 38h
0x140006954  mov     rcx, cs:qword_1400310E8
0x14000695b  mov     r8d, 2
0x140006961  mov     rax, [rsp+38h+arg_20]
0x140006966  test    rcx, rcx
0x140006969  jnz     short loc_140006972
0x14000696b  mov     [rax], rcx
0x14000696e  xor     edx, edx
0x140006970  jmp     short loc_14000697B
0x140006972  mov     [rax], rcx
0x140006975  mov     edx, r8d
0x140006978  movzx   ecx, word ptr [rcx]
0x14000697b  mov     [rax+8], ecx
0x14000697e  xor     r9d, r9d; RelatedActivityId
0x140006981  mov     [rax+0Ch], edx
0x140006984  lea     rdx, DebugTrace; EventDescriptor
0x14000698b  mov     rcx, cs:IPNAT_Context; RegHandle
0x140006992  mov     [rsp+38h+UserData], rax; UserData
0x140006997  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x14000699c  xor     r8d, r8d; ActivityId
0x14000699f  call    cs:__imp_EtwWriteTransfer
0x1400069a6  nop     dword ptr [rax+rax+00h]
0x1400069ab  add     rsp, 38h
0x1400069af  retn
```
