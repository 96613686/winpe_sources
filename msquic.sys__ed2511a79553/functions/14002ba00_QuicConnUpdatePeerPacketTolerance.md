# QuicConnUpdatePeerPacketTolerance

- ea: `0x14002ba00`
- end: `0x14002babc`
- name: `QuicConnUpdatePeerPacketTolerance`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140016210`
- `0x14001e790`

## callees

- `0x14000d490`
- `0x14002ba00`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14002ba5b`
- `ntoskrnl!_snprintf_s` at `0x14002ba5b`

## pseudocode

```c
_BOOL8 __fastcall QuicConnUpdatePeerPacketTolerance(__int64 a1, unsigned __int8 a2)
{
  __int64 v4; // rcx
  _BOOL8 result; // rax
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  if ( (*(_DWORD *)(a1 + 1624) & 0x100000) != 0 && *(_BYTE *)(a1 + 281) != a2 )
  {
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Updating peer packet tolerance to %hhu", a2);
      McTemplateU0ps_EtwWriteTransfer(v4, (const EVENT_DESCRIPTOR *)QuicConnLogInfo, a1, DstBuf);
    }
    ++*(_QWORD *)(a1 + 288);
    *(_BYTE *)(a1 + 281) = a2;
    return QuicSendSetSendFlag(a1 + 3416, 0x8000);
  }
  return result;
}

```

## disassembly

```asm
0x14002ba00  mov     [rsp+arg_10], rbx
0x14002ba05  push    rdi
0x14002ba06  sub     rsp, 0C0h
0x14002ba0d  mov     rax, cs:__security_cookie
0x14002ba14  xor     rax, rsp
0x14002ba17  mov     [rsp+0C8h+var_18], rax
0x14002ba1f  test    dword ptr [rcx+658h], 100000h
0x14002ba29  mov     rbx, rcx
0x14002ba2c  movzx   edi, dl
0x14002ba2f  jz      short loc_14002BA9A
0x14002ba31  cmp     [rcx+119h], dil
0x14002ba38  jz      short loc_14002BA9A
0x14002ba3a  mov     edx, 80h; SizeInBytes
0x14002ba3f  test    cs:byte_14005C48B, dl
0x14002ba45  jz      short loc_14002BA7B
0x14002ba47  lea     r9, aUpdatingPeerPa; "Updating peer packet tolerance to %hhu"
0x14002ba4e  mov     [rsp+0C8h+var_A8], edi
0x14002ba52  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002ba56  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x14002ba5b  call    cs:__imp__snprintf_s
0x14002ba62  nop     dword ptr [rax+rax+00h]
0x14002ba67  lea     r9, [rsp+0C8h+DstBuf]
0x14002ba6c  mov     r8, rbx
0x14002ba6f  lea     rdx, QuicConnLogInfo
0x14002ba76  call    McTemplateU0ps_EtwWriteTransfer
0x14002ba7b  inc     qword ptr [rbx+120h]
0x14002ba82  lea     rcx, [rbx+0D58h]
0x14002ba89  mov     edx, 8000h
0x14002ba8e  mov     [rbx+119h], dil
0x14002ba95  call    QuicSendSetSendFlag
0x14002ba9a  mov     rcx, [rsp+0C8h+var_18]
0x14002baa2  xor     rcx, rsp; StackCookie
0x14002baa5  call    __security_check_cookie
0x14002baaa  mov     rbx, [rsp+0C8h+arg_10]
0x14002bab2  add     rsp, 0C0h
0x14002bab9  pop     rdi
0x14002baba  retn
```
