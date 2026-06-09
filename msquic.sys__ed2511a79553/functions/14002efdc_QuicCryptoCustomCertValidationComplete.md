# QuicCryptoCustomCertValidationComplete

- ea: `0x14002efdc`
- end: `0x14002f0e6`
- name: `QuicCryptoCustomCertValidationComplete`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001d6c`
- `0x14000c774`

## callees

- `0x140008778`
- `0x140009534`
- `0x1400098e8`
- `0x14001c638`
- `0x14002efdc`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14002f030`
- `ntoskrnl!_snprintf_s` at `0x14002f030`

## pseudocode

```c
char __fastcall QuicCryptoCustomCertValidationComplete(__int64 a1, char a2, unsigned __int8 a3)
{
  char result; // al
  __int64 v6; // rcx
  char DstBuf[128]; // [rsp+20h] [rbp-98h] BYREF

  result = *(_BYTE *)a1;
  if ( (*(_BYTE *)a1 & 4) != 0 )
  {
    *(_BYTE *)a1 = result & 0xFB;
    if ( a2 )
    {
      if ( byte_14005C48B < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Custom cert validation succeeded");
        McTemplateU0ps_EtwWriteTransfer(v6, (const EVENT_DESCRIPTOR *)QuicConnLogInfo, a1 - 2784, DstBuf);
      }
      QuicCryptoProcessDataComplete(a1, *(unsigned int *)(a1 + 384));
      result = QuicRecvBufferHasUnreadData(a1 + 392);
      if ( result )
        result = QuicCryptoProcessData(a1, 0);
    }
    else
    {
      if ( (byte_14005C48B & 4) != 0 )
        McTemplateU0ps_EtwWriteTransfer(
          a1,
          (const EVENT_DESCRIPTOR *)QuicConnError,
          a1 - 2784,
          "Custom cert validation failed.");
      result = QuicConnCloseLocally(a1 - 2784, 2, a3 | 0x100LL);
    }
    *(_DWORD *)(a1 + 384) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002efdc  mov     [rsp+arg_8], rbx
0x14002efe1  push    rdi
0x14002efe2  sub     rsp, 0B0h
0x14002efe9  mov     rax, cs:__security_cookie
0x14002eff0  xor     rax, rsp
0x14002eff3  mov     [rsp+0B8h+var_18], rax
0x14002effb  mov     al, [rcx]
0x14002effd  mov     rbx, rcx
0x14002f000  mov     edi, r8d
0x14002f003  test    al, 4
0x14002f005  jz      loc_14002F0C4
0x14002f00b  and     al, 0FBh
0x14002f00d  mov     [rcx], al
0x14002f00f  test    dl, dl
0x14002f011  jz      short loc_14002F07E
0x14002f013  mov     edx, 80h; SizeInBytes
0x14002f018  test    cs:byte_14005C48B, dl
0x14002f01e  jz      short loc_14002F054
0x14002f020  lea     r9, aCustomCertVali_1; "Custom cert validation succeeded"
0x14002f027  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002f02b  lea     rcx, [rsp+0B8h+DstBuf]; DstBuf
0x14002f030  call    cs:__imp__snprintf_s
0x14002f037  nop     dword ptr [rax+rax+00h]
0x14002f03c  lea     r8, [rbx-0AE0h]
0x14002f043  lea     r9, [rsp+0B8h+DstBuf]
0x14002f048  lea     rdx, QuicConnLogInfo
0x14002f04f  call    McTemplateU0ps_EtwWriteTransfer
0x14002f054  mov     edx, [rbx+180h]
0x14002f05a  mov     rcx, rbx
0x14002f05d  call    QuicCryptoProcessDataComplete
0x14002f062  lea     rcx, [rbx+188h]
0x14002f069  call    QuicRecvBufferHasUnreadData
0x14002f06e  test    al, al
0x14002f070  jz      short loc_14002F0BD
0x14002f072  xor     edx, edx
0x14002f074  mov     rcx, rbx
0x14002f077  call    QuicCryptoProcessData
0x14002f07c  jmp     short loc_14002F0BD
0x14002f07e  test    cs:byte_14005C48B, 4
0x14002f085  jz      short loc_14002F0A1
0x14002f087  lea     r8, [rcx-0AE0h]
0x14002f08e  lea     r9, aCustomCertVali; "Custom cert validation failed."
0x14002f095  lea     rdx, QuicConnError
0x14002f09c  call    McTemplateU0ps_EtwWriteTransfer
0x14002f0a1  xor     r9d, r9d
0x14002f0a4  movzx   r8d, dil
0x14002f0a8  bts     r8, 8
0x14002f0ad  lea     rcx, [rbx-0AE0h]
0x14002f0b4  lea     edx, [r9+2]
0x14002f0b8  call    QuicConnCloseLocally
0x14002f0bd  and     dword ptr [rbx+180h], 0
0x14002f0c4  mov     rcx, [rsp+0B8h+var_18]
0x14002f0cc  xor     rcx, rsp; StackCookie
0x14002f0cf  call    __security_check_cookie
0x14002f0d4  mov     rbx, [rsp+0B8h+arg_8]
0x14002f0dc  add     rsp, 0B0h
0x14002f0e3  pop     rdi
0x14002f0e4  retn
```
