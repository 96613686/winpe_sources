# CxPlatDataPathCloseSocketIoCompletion

- ea: `0x1400391c0`
- end: `0x140039210`
- name: `CxPlatDataPathCloseSocketIoCompletion`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400391c0`
- `0x14003ae64`
- `0x14003fdf8`

## string_xrefs

- `0x1400391e4`: `WskCloseSocket completion`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathCloseSocketIoCompletion(int a1, __int64 a2, _DWORD *a3)
{
  int v4; // r9d

  if ( *(_BYTE *)(a2 + 65) )
  {
    v4 = a3[44];
    if ( v4 < 0 && (byte_14005C48E & 4) != 0 )
      McTemplateU0pqs_EtwWriteTransfer(
        a1,
        (unsigned int)QuicDatapathErrorStatus,
        (_DWORD)a3,
        v4,
        (__int64)"WskCloseSocket completion");
    CxPlatSocketDeleteComplete(a3);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400391c0  push    rbx
0x1400391c2  sub     rsp, 30h
0x1400391c6  cmp     byte ptr [rdx+41h], 0
0x1400391ca  mov     rbx, r8
0x1400391cd  jz      short loc_140039204
0x1400391cf  mov     r9d, [r8+0B0h]
0x1400391d6  test    r9d, r9d
0x1400391d9  jns     short loc_1400391FC
0x1400391db  test    cs:byte_14005C48E, 4
0x1400391e2  jz      short loc_1400391FC
0x1400391e4  lea     rax, aWskclosesocket; "WskCloseSocket completion"
0x1400391eb  lea     rdx, QuicDatapathErrorStatus
0x1400391f2  mov     [rsp+38h+var_18], rax
0x1400391f7  call    McTemplateU0pqs_EtwWriteTransfer
0x1400391fc  mov     rcx, rbx; P
0x1400391ff  call    CxPlatSocketDeleteComplete
0x140039204  mov     eax, 0C0000016h
0x140039209  add     rsp, 30h
0x14003920d  pop     rbx
0x14003920e  retn
```
