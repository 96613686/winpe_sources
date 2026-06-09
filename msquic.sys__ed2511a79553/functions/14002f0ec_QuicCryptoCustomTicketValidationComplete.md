# QuicCryptoCustomTicketValidationComplete

- ea: `0x14002f0ec`
- end: `0x14002f1fe`
- name: `QuicCryptoCustomTicketValidationComplete`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000c774`

## callees

- `0x14000554c`
- `0x140008778`
- `0x140008ef0`
- `0x140009534`
- `0x1400098e8`
- `0x14001c664`
- `0x14002f0ec`

## pseudocode

```c
char __fastcall QuicCryptoCustomTicketValidationComplete(__int64 a1, char a2)
{
  int v2; // eax
  __int64 v4; // rdx
  void **v5; // rdi
  __int64 v6; // rsi
  void *v7; // rcx

  LOBYTE(v2) = *(_BYTE *)(a1 + 380);
  if ( (v2 & 1) != 0 && (v2 & 2) == 0 )
  {
    if ( a2 )
    {
      v4 = *(unsigned int *)(a1 + 384);
      *(_BYTE *)(a1 + 380) = v2 & 0xFE;
      QuicCryptoProcessDataComplete(a1, v4);
      LOBYTE(v2) = QuicRecvBufferHasUnreadData(a1 + 392);
      if ( (_BYTE)v2 )
        LOBYTE(v2) = QuicCryptoProcessData(a1, 0);
    }
    else
    {
      *(_DWORD *)(a1 + 24) = 0;
      v5 = (void **)(a1 + 144);
      *(_DWORD *)(a1 + 28) = 0;
      *(_DWORD *)(a1 + 44) = 0;
      v6 = 5;
      *(_DWORD *)(a1 + 48) = 0;
      *(_BYTE *)(a1 + 380) = v2 | 2;
      do
      {
        QuicPacketKeyFree(*(v5 - 6));
        v7 = *v5;
        *(v5 - 6) = 0;
        QuicPacketKeyFree(v7);
        *v5++ = 0;
        --v6;
      }
      while ( v6 );
      *(_BYTE *)(*(_QWORD *)(a1 + 392) + 20LL) &= ~1u;
      *(_QWORD *)(a1 + 576) = 0;
      v2 = QuicCryptoInitializeTls(a1, *(_QWORD *)(*(_QWORD *)(a1 - 2784 + 88) + 48LL), *(_QWORD *)(a1 - 2784 + 3616));
      if ( v2 )
        LOBYTE(v2) = QuicConnTryClose(a1 - 2784, 18, v2, "Failed finalizing resumption ticket rejection", 0x2Du);
    }
    *(_DWORD *)(a1 + 384) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x14002f0ec  mov     [rsp+arg_0], rbx
0x14002f0f1  mov     [rsp+arg_8], rsi
0x14002f0f6  push    rdi
0x14002f0f7  sub     rsp, 30h
0x14002f0fb  mov     al, [rcx+17Ch]
0x14002f101  mov     rbx, rcx
0x14002f104  test    al, 1
0x14002f106  jz      loc_14002F1ED
0x14002f10c  test    al, 2
0x14002f10e  jnz     loc_14002F1ED
0x14002f114  test    dl, dl
0x14002f116  jz      short loc_14002F14E
0x14002f118  mov     edx, [rcx+180h]
0x14002f11e  and     al, 0FEh
0x14002f120  mov     [rcx+17Ch], al
0x14002f126  call    QuicCryptoProcessDataComplete
0x14002f12b  lea     rcx, [rbx+188h]
0x14002f132  call    QuicRecvBufferHasUnreadData
0x14002f137  test    al, al
0x14002f139  jz      loc_14002F1E6
0x14002f13f  xor     edx, edx
0x14002f141  mov     rcx, rbx
0x14002f144  call    QuicCryptoProcessData
0x14002f149  jmp     loc_14002F1E6
0x14002f14e  and     dword ptr [rcx+18h], 0
0x14002f152  lea     rdi, [rcx+90h]
0x14002f159  and     dword ptr [rcx+1Ch], 0
0x14002f15d  or      al, 2
0x14002f15f  and     dword ptr [rcx+2Ch], 0
0x14002f163  mov     esi, 5
0x14002f168  and     dword ptr [rcx+30h], 0
0x14002f16c  mov     [rcx+17Ch], al
0x14002f172  mov     rcx, [rdi-30h]; P
0x14002f176  call    QuicPacketKeyFree
0x14002f17b  mov     rcx, [rdi]; P
0x14002f17e  and     qword ptr [rdi-30h], 0
0x14002f183  call    QuicPacketKeyFree
0x14002f188  and     qword ptr [rdi], 0
0x14002f18c  lea     rdi, [rdi+8]
0x14002f190  sub     rsi, 1
0x14002f194  jnz     short loc_14002F172
0x14002f196  mov     rax, [rbx+188h]
0x14002f19d  lea     rdi, [rbx-0AE0h]
0x14002f1a4  mov     rcx, rbx
0x14002f1a7  and     byte ptr [rax+14h], 0FEh
0x14002f1ab  and     [rbx+240h], rsi
0x14002f1b2  mov     rdx, [rdi+58h]
0x14002f1b6  mov     r8, [rdi+0E20h]
0x14002f1bd  mov     rdx, [rdx+30h]
0x14002f1c1  call    QuicCryptoInitializeTls
0x14002f1c6  test    eax, eax
0x14002f1c8  jz      short loc_14002F1E6
0x14002f1ca  movsxd  r8, eax
0x14002f1cd  lea     r9, aFailedFinalizi; "Failed finalizing resumption ticket rej"...
0x14002f1d4  lea     edx, [rsi+12h]
0x14002f1d7  mov     [rsp+38h+var_18], 2Dh ; '-'
0x14002f1de  mov     rcx, rdi
0x14002f1e1  call    QuicConnTryClose
0x14002f1e6  and     dword ptr [rbx+180h], 0
0x14002f1ed  mov     rbx, [rsp+38h+arg_0]
0x14002f1f2  mov     rsi, [rsp+38h+arg_8]
0x14002f1f7  add     rsp, 30h
0x14002f1fb  pop     rdi
0x14002f1fc  retn
```
