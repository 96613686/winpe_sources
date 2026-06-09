# QuicStreamCompleteSendRequest

- ea: `0x140026d9c`
- end: `0x140026f16`
- name: `QuicStreamCompleteSendRequest`
- size: `378`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000b3f4`
- `0x14000d0b0`
- `0x14002e82c`

## callees

- `0x14000a08c`
- `0x14000b27c`
- `0x140026cb4`
- `0x140026d9c`
- `0x140029104`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140026e78`
- `ntoskrnl!_snprintf_s` at `0x140026e78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026eb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026eb6`

## string_xrefs

- `0x140026e4d`: `Indicating QUIC_STREAM_EVENT_SEND_COMPLETE [%p] (Canceled)`
- `0x140026e5f`: `Indicating QUIC_STREAM_EVENT_SEND_COMPLETE [%p]`

## pseudocode

```c
__int64 __fastcall QuicStreamCompleteSendRequest(__int64 a1, __int64 a2, char a3, char a4)
{
  __int64 v5; // rsi
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdi
  _OWORD v13[2]; // [rsp+30h] [rbp-89h] BYREF
  int v14; // [rsp+50h] [rbp-69h]
  char DstBuf[128]; // [rsp+60h] [rbp-59h] BYREF

  v5 = *(_QWORD *)(a1 + 72);
  if ( *(_QWORD *)(a1 + 144) == a2 )
    *(_QWORD *)(a1 + 144) = *(_QWORD *)a2;
  if ( *(_QWORD *)(a1 + 152) == a2 )
    *(_QWORD *)(a1 + 152) = *(_QWORD *)a2;
  if ( (*(_DWORD *)(a2 + 20) & 2) != 0 && (*(_BYTE *)(a1 + 88) & 4) == 0 )
    QuicStreamIndicateStartComplete(a1, 3221225760LL);
  if ( *(int *)(a2 + 20) >= 0 )
  {
    v14 = 0;
    v9 = *(_QWORD *)(a2 + 56);
    v13[0] = 0;
    LODWORD(v13[0]) = 2;
    BYTE8(v13[0]) = a3;
    v13[1] = v9;
    if ( a3 )
    {
      if ( (byte_14005C48D & 1) != 0 )
      {
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Indicating QUIC_STREAM_EVENT_SEND_COMPLETE [%p] (Canceled)",
          a2);
LABEL_14:
        McTemplateU0ps_EtwWriteTransfer(v10, QuicStreamLogVerbose, a1, DstBuf);
      }
    }
    else if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Indicating QUIC_STREAM_EVENT_SEND_COMPLETE [%p]", a2);
      goto LABEL_14;
    }
    QuicStreamIndicateEvent(a1, v13);
    goto LABEL_18;
  }
  v11 = *(unsigned int *)(a2 + 40);
  if ( (_DWORD)v11 )
  {
    ExFreePoolWithTag(*(PVOID *)(a2 + 48), 0x32316351u);
    *(_QWORD *)(v5 + 3536) -= v11;
  }
LABEL_18:
  if ( a4 )
  {
    *(_QWORD *)(v5 + 3528) -= *(_QWORD *)(a2 + 32);
    if ( (*(_BYTE *)(v5 + 235) & 1) != 0 )
      QuicSendBufferFill(v5);
  }
  return CxPlatPoolFree(a2);
}

```

## disassembly

```asm
0x140026d9c  mov     [rsp-8+arg_18], rbx
0x140026da1  push    rbp
0x140026da2  push    rsi
0x140026da3  push    rdi
0x140026da4  push    r14
0x140026da6  push    r15
0x140026da8  lea     rbp, [rsp-37h]
0x140026dad  sub     rsp, 0F0h
0x140026db4  mov     rax, cs:__security_cookie
0x140026dbb  xor     rax, rsp
0x140026dbe  mov     [rbp+57h+var_30], rax
0x140026dc2  mov     r15b, r9b
0x140026dc5  mov     rsi, [rcx+48h]
0x140026dc9  mov     r14b, r8b
0x140026dcc  mov     rbx, rdx
0x140026dcf  mov     rdi, rcx
0x140026dd2  cmp     [rcx+90h], rdx
0x140026dd9  jnz     short loc_140026DE5
0x140026ddb  mov     rax, [rdx]
0x140026dde  mov     [rcx+90h], rax
0x140026de5  cmp     [rcx+98h], rbx
0x140026dec  jnz     short loc_140026DF8
0x140026dee  mov     rax, [rdx]
0x140026df1  mov     [rcx+98h], rax
0x140026df8  mov     eax, [rdx+14h]
0x140026dfb  test    al, 2
0x140026dfd  jz      short loc_140026E0F
0x140026dff  test    byte ptr [rcx+58h], 4
0x140026e03  jnz     short loc_140026E0F
0x140026e05  mov     edx, 0C0000120h
0x140026e0a  call    QuicStreamIndicateStartComplete
0x140026e0f  cmp     dword ptr [rbx+14h], 0
0x140026e13  jl      loc_140026EA6
0x140026e19  xor     eax, eax
0x140026e1b  xorps   xmm0, xmm0
0x140026e1e  mov     [rbp+57h+var_C0], eax
0x140026e21  mov     rax, [rbx+38h]
0x140026e25  movups  [rsp+110h+var_E0], xmm0
0x140026e2a  mov     dword ptr [rsp+110h+var_E0], 2
0x140026e32  mov     byte ptr [rsp+110h+var_E0+8], r14b
0x140026e37  movups  [rbp+57h+var_D0], xmm0
0x140026e3b  mov     qword ptr [rbp+57h+var_D0], rax
0x140026e3f  test    r14b, r14b
0x140026e42  jz      short loc_140026E56
0x140026e44  test    cs:byte_14005C48D, 1
0x140026e4b  jz      short loc_140026E97
0x140026e4d  lea     r9, aIndicatingQuic_9; "Indicating QUIC_STREAM_EVENT_SEND_COMPL"...
0x140026e54  jmp     short loc_140026E66
0x140026e56  test    cs:byte_14005C48D, 1
0x140026e5d  jz      short loc_140026E97
0x140026e5f  lea     r9, aIndicatingQuic_23; "Indicating QUIC_STREAM_EVENT_SEND_COMPL"...
0x140026e66  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140026e6a  mov     [rsp+110h+var_F0], rbx
0x140026e6f  mov     edx, 80h; SizeInBytes
0x140026e74  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x140026e78  call    cs:__imp__snprintf_s
0x140026e7f  nop     dword ptr [rax+rax+00h]
0x140026e84  lea     r9, [rbp+57h+DstBuf]
0x140026e88  mov     r8, rdi
0x140026e8b  lea     rdx, QuicStreamLogVerbose
0x140026e92  call    McTemplateU0ps_EtwWriteTransfer
0x140026e97  lea     rdx, [rsp+110h+var_E0]
0x140026e9c  mov     rcx, rdi
0x140026e9f  call    QuicStreamIndicateEvent
0x140026ea4  jmp     short loc_140026EC9
0x140026ea6  mov     edi, [rbx+28h]
0x140026ea9  test    edi, edi
0x140026eab  jz      short loc_140026EC9
0x140026ead  mov     rcx, [rbx+30h]; P
0x140026eb1  mov     edx, 32316351h; Tag
0x140026eb6  call    cs:__imp_ExFreePoolWithTag
0x140026ebd  nop     dword ptr [rax+rax+00h]
0x140026ec2  sub     [rsi+0DD0h], rdi
0x140026ec9  test    r15b, r15b
0x140026ecc  jz      short loc_140026EEA
0x140026ece  mov     rax, [rbx+20h]
0x140026ed2  sub     [rsi+0DC8h], rax
0x140026ed9  test    byte ptr [rsi+0EBh], 1
0x140026ee0  jz      short loc_140026EEA
0x140026ee2  mov     rcx, rsi
0x140026ee5  call    QuicSendBufferFill
0x140026eea  mov     rcx, rbx
0x140026eed  call    CxPlatPoolFree
0x140026ef2  mov     rcx, [rbp+57h+var_30]
0x140026ef6  xor     rcx, rsp; StackCookie
0x140026ef9  call    __security_check_cookie
0x140026efe  mov     rbx, [rsp+110h+arg_18]
0x140026f06  add     rsp, 0F0h
0x140026f0d  pop     r15
0x140026f0f  pop     r14
0x140026f11  pop     rdi
0x140026f12  pop     rsi
0x140026f13  pop     rbp
0x140026f14  retn
```
