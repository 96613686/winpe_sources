# McGenEventWrite_EventWriteTransfer

- ea: `0x1800068b4`
- end: `0x180006906`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003740`
- `0x18000690c`
- `0x18000eb94`
- `0x18000f19c`
- `0x18000f254`
- `0x18000f670`
- `0x18000faf0`
- `0x180012d98`
- `0x180012e34`
- `0x180012ef0`

## callees

- `0x1800068b4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800068fb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800068fb`

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

  v5 = (unsigned __int16 *)qword_180035008;
  if ( qword_180035008 )
  {
    UserData->Ptr = qword_180035008;
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
  return EventWriteTransfer(Microsoft_Windows_GraphicsCapture_API_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800068b4  sub     rsp, 38h
0x1800068b8  mov     rcx, cs:qword_180035008
0x1800068bf  mov     rax, [rsp+38h+arg_20]
0x1800068c4  test    rcx, rcx
0x1800068c7  jnz     short loc_1800068D1
0x1800068c9  mov     [rax], rcx
0x1800068cc  xor     r8d, r8d
0x1800068cf  jmp     short loc_1800068DD
0x1800068d1  mov     [rax], rcx
0x1800068d4  mov     r8d, 2
0x1800068da  movzx   ecx, word ptr [rcx]
0x1800068dd  mov     [rax+8], ecx
0x1800068e0  mov     [rax+0Ch], r8d
0x1800068e4  xor     r8d, r8d; ActivityId
0x1800068e7  mov     rcx, cs:Microsoft_Windows_GraphicsCapture_API_Context; RegHandle
0x1800068ee  mov     [rsp+38h+UserData], rax; UserData
0x1800068f3  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800068f8  xor     r9d, r9d; RelatedActivityId
0x1800068fb  call    cs:__imp_EventWriteTransfer
0x180006901  add     rsp, 38h
0x180006905  retn
```
