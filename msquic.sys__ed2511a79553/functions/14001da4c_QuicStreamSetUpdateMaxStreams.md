# QuicStreamSetUpdateMaxStreams

- ea: `0x14001da4c`
- end: `0x14001dbe7`
- name: `QuicStreamSetUpdateMaxStreams`
- size: `411`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1400108c0`

## callees

- `0x14000b2e8`
- `0x14000d638`
- `0x14000d6d0`
- `0x14001da4c`
- `0x14001dbf0`
- `0x14002f598`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001dae2`
- `ntoskrnl!_snprintf_s` at `0x14001dae2`

## string_xrefs

- `0x14001dac4`: `Peer updated max stream count (%hhu, %llu).`

## pseudocode

```c
__int64 __fastcall QuicStreamSetUpdateMaxStreams(__int64 a1, unsigned __int8 a2, unsigned __int64 a3)
{
  __int64 v3; // r13
  unsigned __int64 v6; // rbx
  __int64 result; // rax
  __int64 v8; // rcx
  char v9; // r12
  __int64 *v10; // rsi
  __int64 *v11; // r15
  unsigned __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 *v14; // rax
  __int64 *v15; // [rsp+30h] [rbp-D8h]
  char DstBuf[128]; // [rsp+40h] [rbp-C8h] BYREF

  v3 = a1 - 2032;
  if ( *(_DWORD *)(a1 - 2032) == 4 )
    v6 = (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 3;
  else
    v6 = a2 == 0 ? 2 : 0;
  result = 3 * v6;
  if ( a3 > *(_QWORD *)(a1 + 24 * v6) )
  {
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Peer updated max stream count (%hhu, %llu).", a2, a3);
      McTemplateU0ps_EtwWriteTransfer(v8, QuicConnLogVerbose, v3, DstBuf);
    }
    v9 = 0;
    v10 = *(__int64 **)(a1 + 104);
    while ( v10 != (__int64 *)(a1 + 104) )
    {
      v11 = v10 - 4;
      v15 = v10;
      v12 = v10[6];
      v10 = (__int64 *)*v10;
      if ( v12 >> 2 >= a3 )
        break;
      if ( (v12 & 3) == v6 )
      {
        QuicStreamRemoveOutFlowBlockedReason(v11, 32);
        v13 = *v15;
        v14 = (__int64 *)v15[1];
        *v14 = *v15;
        *(_QWORD *)(v13 + 8) = v14;
        *((_BYTE *)v11 + 93) &= ~1u;
        if ( !(unsigned __int8)QuicStreamSetInsertStream(a1, v11) )
        {
          CxPlatLogAssert(
            "C:\\__w\\1\\s\\msquic\\src\\core\\stream_set.c",
            515,
            "QuicStreamSetInsertStream(StreamSet, Stream)");
          __int2c();
        }
        QuicStreamIndicatePeerAccepted(v11);
        v9 = 1;
      }
    }
    *(_QWORD *)(a1 + 24 * v6) = a3;
    result = QuicStreamSetIndicateStreamsAvailable(a1);
    if ( v9 )
      return QuicSendQueueFlush(v3 + 3416, 10);
  }
  return result;
}

```

## disassembly

```asm
0x14001da4c  mov     [rsp+arg_18], rbx
0x14001da51  push    rbp
0x14001da52  push    rsi
0x14001da53  push    rdi
0x14001da54  push    r12
0x14001da56  push    r13
0x14001da58  push    r14
0x14001da5a  push    r15
0x14001da5c  sub     rsp, 0D0h
0x14001da63  mov     rax, cs:__security_cookie
0x14001da6a  xor     rax, rsp
0x14001da6d  mov     [rsp+108h+var_48], rax
0x14001da75  lea     r13, [rcx-7F0h]
0x14001da7c  mov     rbp, r8
0x14001da7f  cmp     dword ptr [r13+0], 4
0x14001da84  mov     rdi, rcx
0x14001da87  mov     al, dl
0x14001da89  jnz     short loc_14001DA9A
0x14001da8b  neg     al
0x14001da8d  sbb     rbx, rbx
0x14001da90  and     rbx, 0FFFFFFFFFFFFFFFEh
0x14001da94  add     rbx, 3
0x14001da98  jmp     short loc_14001DAA5
0x14001da9a  neg     al
0x14001da9c  sbb     rbx, rbx
0x14001da9f  not     rbx
0x14001daa2  and     ebx, 2
0x14001daa5  lea     rax, [rbx+rbx*2]
0x14001daa9  mov     [rsp+108h+var_D0], rax
0x14001daae  cmp     rbp, [rcx+rax*8]
0x14001dab2  jbe     loc_14001DBBB
0x14001dab8  test    cs:byte_14005C48C, 1
0x14001dabf  jz      short loc_14001DB02
0x14001dac1  movzx   eax, dl
0x14001dac4  lea     r9, aPeerUpdatedMax; "Peer updated max stream count (%hhu, %l"...
0x14001dacb  mov     edx, 80h; SizeInBytes
0x14001dad0  mov     [rsp+108h+var_E0], rbp
0x14001dad5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001dad9  mov     [rsp+108h+var_E8], eax
0x14001dadd  lea     rcx, [rsp+108h+DstBuf]; DstBuf
0x14001dae2  call    cs:__imp__snprintf_s
0x14001dae9  nop     dword ptr [rax+rax+00h]
0x14001daee  lea     r9, [rsp+108h+DstBuf]
0x14001daf3  mov     r8, r13
0x14001daf6  lea     rdx, QuicConnLogVerbose
0x14001dafd  call    McTemplateU0ps_EtwWriteTransfer
0x14001db02  lea     r14, [rdi+68h]
0x14001db06  xor     r12b, r12b
0x14001db09  mov     rsi, [r14]
0x14001db0c  jmp     short loc_14001DB8B
0x14001db0e  lea     r15, [rsi-20h]
0x14001db12  mov     [rsp+108h+var_D8], rsi
0x14001db17  mov     rcx, [r15+50h]
0x14001db1b  mov     rsi, [rsi]
0x14001db1e  mov     rax, rcx
0x14001db21  shr     rax, 2
0x14001db25  cmp     rax, rbp
0x14001db28  jnb     short loc_14001DB94
0x14001db2a  and     ecx, 3
0x14001db2d  cmp     rcx, rbx
0x14001db30  jnz     short loc_14001DB8B
0x14001db32  mov     edx, 20h ; ' '
0x14001db37  mov     rcx, r15
0x14001db3a  call    QuicStreamRemoveOutFlowBlockedReason
0x14001db3f  mov     rax, [rsp+108h+var_D8]
0x14001db44  mov     rdx, r15
0x14001db47  mov     rcx, [rax]
0x14001db4a  mov     rax, [rax+8]
0x14001db4e  mov     [rax], rcx
0x14001db51  mov     [rcx+8], rax
0x14001db55  mov     rcx, rdi
0x14001db58  and     byte ptr [r15+5Dh], 0FEh
0x14001db5d  call    QuicStreamSetInsertStream
0x14001db62  test    al, al
0x14001db64  jnz     short loc_14001DB80
0x14001db66  lea     r8, aQuicstreamseti; "QuicStreamSetInsertStream(StreamSet, St"...
0x14001db6d  mov     edx, 203h
0x14001db72  lea     rcx, aCW1SMsquicSrcC_17; "C:\\__w\\1\\s\\msquic\\src\\core\\strea"...
0x14001db79  call    CxPlatLogAssert
0x14001db7e  int     2Ch; Windows NT - assertion failure
0x14001db80  mov     rcx, r15
0x14001db83  call    QuicStreamIndicatePeerAccepted
0x14001db88  mov     r12b, 1
0x14001db8b  cmp     rsi, r14
0x14001db8e  jnz     loc_14001DB0E
0x14001db94  mov     rax, [rsp+108h+var_D0]
0x14001db99  mov     rcx, rdi
0x14001db9c  mov     [rdi+rax*8], rbp
0x14001dba0  call    QuicStreamSetIndicateStreamsAvailable
0x14001dba5  test    r12b, r12b
0x14001dba8  jz      short loc_14001DBBB
0x14001dbaa  lea     rcx, [r13+0D58h]
0x14001dbb1  mov     edx, 0Ah
0x14001dbb6  call    QuicSendQueueFlush
0x14001dbbb  mov     rcx, [rsp+108h+var_48]
0x14001dbc3  xor     rcx, rsp; StackCookie
0x14001dbc6  call    __security_check_cookie
0x14001dbcb  mov     rbx, [rsp+108h+arg_18]
0x14001dbd3  add     rsp, 0D0h
0x14001dbda  pop     r15
0x14001dbdc  pop     r14
0x14001dbde  pop     r13
0x14001dbe0  pop     r12
0x14001dbe2  pop     rdi
0x14001dbe3  pop     rsi
0x14001dbe4  pop     rbp
0x14001dbe5  retn
```
