# QuicStreamSendBufferRequest

- ea: `0x14000a120`
- end: `0x14000a249`
- name: `QuicStreamSendBufferRequest`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000a08c`

## callees

- `0x14000a120`
- `0x14000a250`
- `0x14000b27c`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003d817`
- `ntoskrnl!_snprintf_s` at `0x14003d817`

## string_xrefs

- `0x14003d7fd`: `Indicating QUIC_STREAM_EVENT_SEND_COMPLETE [%p]`

## pseudocode

```c
__int64 __fastcall QuicStreamSendBufferRequest(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  unsigned int v6; // r14d
  char *v7; // r15
  __int64 v8; // rcx
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rax
  __int64 v13; // rcx
  _OWORD v14[2]; // [rsp+30h] [rbp-E8h] BYREF
  int v15; // [rsp+50h] [rbp-C8h]
  char DstBuf[128]; // [rsp+60h] [rbp-B8h] BYREF

  if ( a2[4] )
  {
    v4 = QuicSendBufferAlloc(*(_QWORD *)(a1 + 72) + 3528LL, *((unsigned int *)a2 + 8));
    v5 = v4;
    if ( !v4 )
      return 3221225495LL;
    v6 = 0;
    v7 = (char *)v4;
    if ( *((_DWORD *)a2 + 4) )
    {
      v8 = a2[1];
      do
      {
        v9 = 2LL * v6;
        memmove(v7, *(const void **)(v8 + 16LL * v6 + 8), *(unsigned int *)(v8 + 16LL * v6));
        v8 = a2[1];
        ++v6;
        v7 += *(unsigned int *)(v8 + 8 * v9);
      }
      while ( v6 < *((_DWORD *)a2 + 4) );
    }
  }
  else
  {
    v5 = 0;
  }
  a2[6] = v5;
  v10 = *((_DWORD *)a2 + 8);
  *((_DWORD *)a2 + 5) |= 0x80000000;
  *((_DWORD *)a2 + 10) = v10;
  v11 = *a2;
  *((_DWORD *)a2 + 4) = 1;
  a2[1] = a2 + 5;
  *(_QWORD *)(a1 + 152) = v11;
  v14[0] = 0;
  v15 = 0;
  BYTE8(v14[0]) = 0;
  v14[1] = (unsigned __int64)a2[7];
  LODWORD(v14[0]) = 2;
  if ( (byte_14005C48D & 1) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Indicating QUIC_STREAM_EVENT_SEND_COMPLETE [%p]", a2);
    McTemplateU0ps_EtwWriteTransfer(v13, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
  }
  QuicStreamIndicateEvent(a1, v14);
  a2[7] = 0;
  return 0;
}

```

## disassembly

```asm
0x14000a120  mov     [rsp+arg_10], rbx
0x14000a125  push    rbp
0x14000a126  push    rsi
0x14000a127  push    rdi
0x14000a128  push    r14
0x14000a12a  push    r15
0x14000a12c  sub     rsp, 0F0h
0x14000a133  mov     rax, cs:__security_cookie
0x14000a13a  xor     rax, rsp
0x14000a13d  mov     [rsp+118h+var_38], rax
0x14000a145  cmp     qword ptr [rdx+20h], 0
0x14000a14a  mov     rdi, rdx
0x14000a14d  mov     rbp, rcx
0x14000a150  jz      loc_14003D7F6
0x14000a156  mov     rcx, [rcx+48h]
0x14000a15a  mov     edx, [rdx+20h]
0x14000a15d  add     rcx, 0DC8h
0x14000a164  call    QuicSendBufferAlloc
0x14000a169  mov     rsi, rax
0x14000a16c  test    rax, rax
0x14000a16f  jz      loc_14003D7EC
0x14000a175  xor     r14d, r14d
0x14000a178  mov     r15, rax
0x14000a17b  cmp     [rdi+10h], r14d
0x14000a17f  jbe     short loc_14000A1AF
0x14000a181  mov     rcx, [rdi+8]
0x14000a185  mov     ebx, r14d
0x14000a188  add     rbx, rbx
0x14000a18b  mov     r8d, [rcx+rbx*8]; Size
0x14000a18f  mov     rdx, [rcx+rbx*8+8]; Src
0x14000a194  mov     rcx, r15; void *
0x14000a197  call    memmove
0x14000a19c  mov     rcx, [rdi+8]
0x14000a1a0  inc     r14d
0x14000a1a3  mov     eax, [rcx+rbx*8]
0x14000a1a6  add     r15, rax
0x14000a1a9  cmp     r14d, [rdi+10h]
0x14000a1ad  jb      short loc_14000A185
0x14000a1af  mov     [rdi+30h], rsi
0x14000a1b3  lea     rcx, [rdi+28h]
0x14000a1b7  mov     eax, [rdi+20h]
0x14000a1ba  xorps   xmm0, xmm0
0x14000a1bd  or      dword ptr [rdi+14h], 80000000h
0x14000a1c4  mov     [rcx], eax
0x14000a1c6  mov     rax, [rdi]
0x14000a1c9  mov     dword ptr [rdi+10h], 1
0x14000a1d0  mov     [rdi+8], rcx
0x14000a1d4  mov     [rbp+98h], rax
0x14000a1db  xor     eax, eax
0x14000a1dd  test    cs:byte_14005C48D, 1
0x14000a1e4  movups  [rsp+118h+var_E8], xmm0
0x14000a1e9  mov     [rsp+118h+var_C8], eax
0x14000a1ed  mov     byte ptr [rsp+118h+var_E8+8], al
0x14000a1f1  mov     rax, [rdi+38h]
0x14000a1f5  movups  [rsp+118h+var_D8], xmm0
0x14000a1fa  mov     qword ptr [rsp+118h+var_D8], rax
0x14000a1ff  mov     dword ptr [rsp+118h+var_E8], 2
0x14000a207  jnz     loc_14003D7FD
0x14000a20d  lea     rdx, [rsp+118h+var_E8]
0x14000a212  mov     rcx, rbp
0x14000a215  call    QuicStreamIndicateEvent
0x14000a21a  and     qword ptr [rdi+38h], 0
0x14000a21f  xor     eax, eax
0x14000a221  mov     rcx, [rsp+118h+var_38]
0x14000a229  xor     rcx, rsp; StackCookie
0x14000a22c  call    __security_check_cookie
0x14000a231  mov     rbx, [rsp+118h+arg_10]
0x14000a239  add     rsp, 0F0h
0x14000a240  pop     r15
0x14000a242  pop     r14
0x14000a244  pop     rdi
0x14000a245  pop     rsi
0x14000a246  pop     rbp
0x14000a247  retn
0x14003d7ec  mov     eax, 0C0000017h
0x14003d7f1  jmp     loc_14000A221
0x14003d7f6  xor     esi, esi
0x14003d7f8  jmp     loc_14000A1AF
0x14003d7fd  lea     r9, aIndicatingQuic_23; "Indicating QUIC_STREAM_EVENT_SEND_COMPL"...
0x14003d804  mov     [rsp+118h+var_F8], rdi
0x14003d809  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003d80d  lea     rcx, [rsp+118h+DstBuf]; DstBuf
0x14003d812  mov     edx, 80h; SizeInBytes
0x14003d817  call    cs:__imp__snprintf_s
0x14003d81e  nop     dword ptr [rax+rax+00h]
0x14003d823  lea     r9, [rsp+118h+DstBuf]
0x14003d828  mov     r8, rbp
0x14003d82b  lea     rdx, QuicStreamLogVerbose
0x14003d832  call    McTemplateU0ps_EtwWriteTransfer
0x14003d837  nop
0x14003d838  jmp     loc_14000A20D
```
