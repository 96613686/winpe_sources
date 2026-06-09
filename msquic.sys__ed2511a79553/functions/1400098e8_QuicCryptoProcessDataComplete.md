# QuicCryptoProcessDataComplete

- ea: `0x1400098e8`
- end: `0x1400099ab`
- name: `QuicCryptoProcessDataComplete`
- size: `195`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140009534`
- `0x14002efdc`
- `0x14002f0ec`
- `0x14004670c`

## callees

- `0x1400098e8`
- `0x1400099b4`
- `0x14000ac50`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140009946`
- `ntoskrnl!_snprintf_s` at `0x140009946`

## pseudocode

```c
__int64 __fastcall QuicCryptoProcessDataComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 result; // rax
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  v5 = (unsigned int)a2;
  if ( (*(_BYTE *)(a1 + 380) & 1) != 0 || (*(_BYTE *)a1 & 4) != 0 )
  {
    *(_DWORD *)(a1 + 384) = a2;
  }
  else
  {
    if ( (_DWORD)a2 )
    {
      *(_DWORD *)(a1 + 376) += a2;
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Draining %u crypto bytes", a2);
        McTemplateU0ps_EtwWriteTransfer(v6, (const EVENT_DESCRIPTOR *)QuicConnLogVerbose, a1 - 2784, DstBuf);
      }
      QuicRecvBufferDrain(a1 + 392, v5);
    }
    return QuicCryptoProcessTlsCompletion(a1, a2, a3, a4);
  }
  return result;
}

```

## disassembly

```asm
0x1400098e8  mov     [rsp+arg_10], rbx
0x1400098ed  push    rdi
0x1400098ee  sub     rsp, 0C0h
0x1400098f5  mov     rax, cs:__security_cookie
0x1400098fc  xor     rax, rsp
0x1400098ff  mov     [rsp+0C8h+var_18], rax
0x140009907  test    byte ptr [rcx+17Ch], 1
0x14000990e  mov     rbx, rcx
0x140009911  mov     edi, edx
0x140009913  jnz     short loc_140009983
0x140009915  test    byte ptr [rcx], 4
0x140009918  jnz     short loc_140009983
0x14000991a  test    edx, edx
0x14000991c  jz      short loc_140009979
0x14000991e  add     [rcx+178h], edi
0x140009924  test    cs:byte_14005C48C, 1
0x14000992b  jz      short loc_14000996A
0x14000992d  lea     r9, aDrainingUCrypt; "Draining %u crypto bytes"
0x140009934  mov     [rsp+0C8h+var_A8], edi
0x140009938  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000993c  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140009941  mov     edx, 80h; SizeInBytes
0x140009946  call    cs:__imp__snprintf_s
0x14000994d  nop     dword ptr [rax+rax+00h]
0x140009952  lea     r8, [rbx-0AE0h]
0x140009959  lea     r9, [rsp+0C8h+DstBuf]
0x14000995e  lea     rdx, QuicConnLogVerbose
0x140009965  call    McTemplateU0ps_EtwWriteTransfer
0x14000996a  mov     rdx, rdi
0x14000996d  lea     rcx, [rbx+188h]
0x140009974  call    QuicRecvBufferDrain
0x140009979  mov     rcx, rbx
0x14000997c  call    QuicCryptoProcessTlsCompletion
0x140009981  jmp     short loc_140009989
0x140009983  mov     [rcx+180h], edi
0x140009989  mov     rcx, [rsp+0C8h+var_18]
0x140009991  xor     rcx, rsp; StackCookie
0x140009994  call    __security_check_cookie
0x140009999  mov     rbx, [rsp+0C8h+arg_10]
0x1400099a1  add     rsp, 0C0h
0x1400099a8  pop     rdi
0x1400099a9  retn
```
