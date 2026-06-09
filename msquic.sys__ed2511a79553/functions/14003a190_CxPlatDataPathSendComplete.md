# CxPlatDataPathSendComplete

- ea: `0x14003a190`
- end: `0x14003a1eb`
- name: `CxPlatDataPathSendComplete`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14003a190`
- `0x14003b77c`
- `0x14003fdf8`

## import_xrefs

- `ntoskrnl!IoCleanupIrp` at `0x14003a1cb`
- `ntoskrnl!IoCleanupIrp` at `0x14003a1cb`

## string_xrefs

- `0x14003a1af`: `WskSendMessages completion`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathSendComplete(int a1, __int64 a2, __int64 a3)
{
  int v3; // r9d

  v3 = *(_DWORD *)(a2 + 48);
  if ( v3 < 0 && (byte_14005C48E & 4) != 0 )
    McTemplateU0pqs_EtwWriteTransfer(
      a1,
      (unsigned int)QuicDatapathErrorStatus,
      *(_QWORD *)(a3 + 16),
      v3,
      (__int64)"WskSendMessages completion");
  IoCleanupIrp(a3 + 32);
  SendDataFree(a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14003a190  push    rbx
0x14003a192  sub     rsp, 30h
0x14003a196  mov     r9d, [rdx+30h]
0x14003a19a  mov     rbx, r8
0x14003a19d  test    r9d, r9d
0x14003a1a0  jns     short loc_14003A1C7
0x14003a1a2  test    cs:byte_14005C48E, 4
0x14003a1a9  jz      short loc_14003A1C7
0x14003a1ab  mov     r8, [r8+10h]
0x14003a1af  lea     rax, aWsksendmessage; "WskSendMessages completion"
0x14003a1b6  lea     rdx, QuicDatapathErrorStatus
0x14003a1bd  mov     [rsp+38h+var_18], rax
0x14003a1c2  call    McTemplateU0pqs_EtwWriteTransfer
0x14003a1c7  lea     rcx, [rbx+20h]
0x14003a1cb  call    cs:__imp_IoCleanupIrp
0x14003a1d2  nop     dword ptr [rax+rax+00h]
0x14003a1d7  mov     rcx, rbx
0x14003a1da  call    SendDataFree
0x14003a1df  mov     eax, 0C0000016h
0x14003a1e4  add     rsp, 30h
0x14003a1e8  pop     rbx
0x14003a1e9  retn
```
