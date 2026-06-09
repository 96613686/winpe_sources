# QuicCryptoProcessData

- ea: `0x140009534`
- end: `0x140009800`
- name: `QuicCryptoProcessData`
- size: `716`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000554c`
- `0x1400093e4`
- `0x14002efdc`
- `0x14002f0ec`

## callees

- `0x1400033e0`
- `0x140009534`
- `0x140009808`
- `0x1400098e8`
- `0x14000ac50`
- `0x14001c638`
- `0x14001cd20`
- `0x140020c50`
- `0x14002eb78`
- `0x14002ec10`
- `0x14002ee5c`
- `0x14003047c`
- `0x140035f3c`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140009611`
- `ntoskrnl!_snprintf_s` at `0x140009611`

## string_xrefs

- `0x1400095fd`: `No complete TLS messages to process`

## pseudocode

```c
__int64 __fastcall QuicCryptoProcessData(__int64 a1, char a2)
{
  int v2; // r14d
  bool v3; // zf
  char v5; // al
  __int64 **v6; // rbx
  _BYTE *v7; // r15
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rcx
  int Initial; // eax
  __int64 *v12; // rax
  __int64 *v13; // rdx
  __int64 **v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  char v17; // al
  __int64 v18; // rax
  __int128 v19; // xmm1
  int v21; // eax
  __int64 v22; // rdx
  __int128 v23; // [rsp+30h] [rbp-79h] BYREF
  __int64 v24; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-61h] BYREF
  char DstBuf[128]; // [rsp+50h] [rbp-59h] BYREF

  LODWORD(v24) = 1;
  v2 = 0;
  *(_QWORD *)((char *)&v23 + 4) = 0;
  v3 = (*(_BYTE *)a1 & 4) == 0;
  *(_QWORD *)&v23 = 0;
  if ( v3 )
  {
    v5 = *(_BYTE *)(a1 + 380);
    if ( (v5 & 1) == 0 || (v5 & 2) != 0 )
    {
      v6 = (__int64 **)(a1 + 392);
      if ( a2 )
      {
        v7 = 0;
        *((_QWORD *)&v23 + 1) = 0;
      }
      else
      {
        QuicRecvBufferRead(a1 + 392, v25, &v24, &v23);
        v7 = (_BYTE *)*((_QWORD *)&v23 + 1);
        v9 = a1 - 2784;
        LODWORD(v23) = QuicCryptoTlsGetCompleteTlsMessagesLength(*((_QWORD *)&v23 + 1), (unsigned int)v23);
        if ( !(_DWORD)v23 )
        {
          if ( (byte_14005C48C & 1) != 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "No complete TLS messages to process");
            McTemplateU0ps_EtwWriteTransfer(v10, QuicConnLogVerbose, a1 - 2784, DstBuf);
          }
          goto LABEL_7;
        }
        if ( *(_DWORD *)v9 == 4 && (*(_BYTE *)(v9 + 250) & 4) == 0 )
        {
          memset(DstBuf, 0, 0x48u);
          Initial = QuicCryptoTlsReadInitial(a1 - 2784, v7, v23, (__int64)DstBuf);
          v2 = Initial;
          if ( Initial >= 0 )
          {
            if ( Initial != 259 )
            {
              v2 = QuicConnProcessPeerTransportParameters(a1 - 2784, 0);
              if ( v2 >= 0 )
              {
                v24 = 0;
                if ( *((_DWORD *)v6 + 54) == 2 )
                  v12 = v6[23];
                else
                  v12 = 0;
                v6[23] = v12;
                v13 = v6[2];
                if ( v13 )
                {
                  QuicRecvChunkFree(v6, v13);
                  v6[2] = 0;
                }
                QuicRecvBufferDrainFullChunks(v6, &v24);
                if ( *v6 != (__int64 *)v6 )
                {
                  QuicRecvBufferDrainFirstChunk(v6, v24);
                  v14 = (__int64 **)*v6;
                  if ( *((_DWORD *)v6 + 54) == 2 )
                  {
                    *((_BYTE *)v14 + 20) = *((_BYTE *)v14 + 20) & 0xFE | (v6[23] != 0);
                  }
                  else
                  {
                    while ( v14 != v6 )
                    {
                      *((_BYTE *)v14 + 20) &= ~1u;
                      v14 = (__int64 **)*v14;
                    }
                  }
                }
                v15 = *(_QWORD *)(v9 + 360);
                *(_DWORD *)DstBuf = *(_DWORD *)(v9 + 3636);
                *(_QWORD *)&DstBuf[8] = v9 + 404;
                *(_QWORD *)&DstBuf[16] = v9 + 376;
                *(_DWORD *)&DstBuf[24] = v23;
                *(_QWORD *)&DstBuf[40] = *((_QWORD *)&v23 + 1);
                QuicBindingAcceptConnection(v15, a1 - 2784, DstBuf);
                v16 = *(_QWORD *)(v9 + 3872);
                if ( v16 )
                {
                  v17 = *(_BYTE *)(v9 + 249);
                  if ( (v17 & 2) == 0 && (v17 & 0x20) != 0 )
                  {
                    v18 = *((_QWORD *)&v23 + 1);
                    *(_OWORD *)(v16 + 2) = *(_OWORD *)(*((_QWORD *)&v23 + 1) + 6LL);
                    v19 = *(_OWORD *)(v18 + 22);
                    *(_BYTE *)(v16 + 1) |= 1u;
                    *(_OWORD *)(v16 + 18) = v19;
                  }
                }
                return (unsigned int)v2;
              }
            }
          }
          else
          {
            QuicConnCloseLocally(a1 - 2784, 2, 296);
          }
LABEL_7:
          QuicRecvBufferDrain(v6, 0);
          return (unsigned int)v2;
        }
      }
      v8 = *(_QWORD *)(a1 + 8);
      if ( !v8 )
        goto LABEL_7;
      v21 = CxPlatTlsProcessData(v8, 0, (__int64)v7, &v23, a1 + 16);
      v22 = (unsigned int)v23;
      *(_DWORD *)(a1 + 200) = v21;
      QuicCryptoProcessDataComplete(a1, v22);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140009534  mov     [rsp-8+arg_8], rbx
0x140009539  mov     [rsp-8+arg_10], rsi
0x14000953e  push    rbp
0x14000953f  push    rdi
0x140009540  push    r12
0x140009542  push    r14
0x140009544  push    r15
0x140009546  lea     rbp, [rsp-37h]
0x14000954b  sub     rsp, 0E0h
0x140009552  mov     rax, cs:__security_cookie
0x140009559  xor     rax, rsp
0x14000955c  mov     [rbp+57h+var_30], rax
0x140009560  xor     eax, eax
0x140009562  mov     dword ptr [rbp+57h+var_C0], 1
0x140009569  xor     r14d, r14d
0x14000956c  mov     qword ptr [rbp+57h+var_D0+4], rax
0x140009570  test    byte ptr [rcx], 4
0x140009573  mov     rsi, rcx
0x140009576  mov     qword ptr [rbp+57h+var_D0], rax
0x14000957a  jnz     loc_1400097D5
0x140009580  mov     al, [rcx+17Ch]
0x140009586  test    al, 1
0x140009588  jz      short loc_140009592
0x14000958a  test    al, 2
0x14000958c  jz      loc_1400097D5
0x140009592  lea     rbx, [rcx+188h]
0x140009599  test    dl, dl
0x14000959b  jz      short loc_1400095C0
0x14000959d  xor     r15d, r15d
0x1400095a0  mov     qword ptr [rbp+57h+var_D0+8], r15
0x1400095a4  mov     rcx, [rsi+8]
0x1400095a8  test    rcx, rcx
0x1400095ab  jnz     loc_1400097AD
0x1400095b1  xor     edx, edx
0x1400095b3  mov     rcx, rbx
0x1400095b6  call    QuicRecvBufferDrain
0x1400095bb  jmp     loc_140009797
0x1400095c0  lea     r9, [rbp+57h+var_D0]
0x1400095c4  mov     rcx, rbx
0x1400095c7  lea     r8, [rbp+57h+var_C0]
0x1400095cb  lea     rdx, [rbp+57h+var_B8]
0x1400095cf  call    QuicRecvBufferRead
0x1400095d4  mov     r15, qword ptr [rbp+57h+var_D0+8]
0x1400095d8  lea     rdi, [rsi-0AE0h]
0x1400095df  mov     edx, dword ptr [rbp+57h+var_D0]
0x1400095e2  mov     rcx, r15
0x1400095e5  call    QuicCryptoTlsGetCompleteTlsMessagesLength
0x1400095ea  mov     dword ptr [rbp+57h+var_D0], eax
0x1400095ed  mov     r12d, eax
0x1400095f0  test    eax, eax
0x1400095f2  jnz     short loc_140009635
0x1400095f4  test    cs:byte_14005C48C, 1
0x1400095fb  jz      short loc_1400095B1
0x1400095fd  lea     r9, aNoCompleteTlsM; "No complete TLS messages to process"
0x140009604  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140009608  mov     edx, 80h; SizeInBytes
0x14000960d  lea     rcx, [rbp+57h+DstBuf]; DstBuf
0x140009611  call    cs:__imp__snprintf_s
0x140009618  nop     dword ptr [rax+rax+00h]
0x14000961d  lea     r9, [rbp+57h+DstBuf]
0x140009621  mov     r8, rdi
0x140009624  lea     rdx, QuicConnLogVerbose
0x14000962b  call    McTemplateU0ps_EtwWriteTransfer
0x140009630  jmp     loc_1400095B1
0x140009635  cmp     dword ptr [rdi], 4
0x140009638  jnz     loc_1400095A4
0x14000963e  test    byte ptr [rdi+0FAh], 4
0x140009645  jnz     loc_1400095A4
0x14000964b  xor     edx, edx; Val
0x14000964d  lea     rcx, [rbp+57h+DstBuf]; void *
0x140009651  lea     r8d, [rdx+48h]; Size
0x140009655  call    memset
0x14000965a  lea     r9, [rbp+57h+DstBuf]
0x14000965e  mov     r8d, r12d
0x140009661  mov     rdx, r15
0x140009664  mov     rcx, rdi; int
0x140009667  call    QuicCryptoTlsReadInitial
0x14000966c  mov     r14d, eax
0x14000966f  test    eax, eax
0x140009671  jns     short loc_14000968D
0x140009673  xor     r9d, r9d
0x140009676  mov     r8d, 128h
0x14000967c  mov     rcx, rdi
0x14000967f  lea     edx, [r9+2]
0x140009683  call    QuicConnCloseLocally
0x140009688  jmp     loc_1400095B1
0x14000968d  cmp     eax, 103h
0x140009692  jz      loc_1400095B1
0x140009698  xor     edx, edx
0x14000969a  mov     rcx, rdi
0x14000969d  call    QuicConnProcessPeerTransportParameters
0x1400096a2  mov     r14d, eax
0x1400096a5  test    eax, eax
0x1400096a7  js      loc_1400095B1
0x1400096ad  and     [rbp+57h+var_C0], 0
0x1400096b2  cmp     dword ptr [rbx+0D8h], 2
0x1400096b9  jnz     short loc_1400096C4
0x1400096bb  mov     rax, [rbx+0B8h]
0x1400096c2  jmp     short loc_1400096C6
0x1400096c4  xor     eax, eax
0x1400096c6  mov     [rbx+0B8h], rax
0x1400096cd  mov     rdx, [rbx+10h]
0x1400096d1  test    rdx, rdx
0x1400096d4  jz      short loc_1400096E3
0x1400096d6  mov     rcx, rbx
0x1400096d9  call    QuicRecvChunkFree
0x1400096de  and     qword ptr [rbx+10h], 0
0x1400096e3  lea     rdx, [rbp+57h+var_C0]
0x1400096e7  mov     rcx, rbx
0x1400096ea  call    QuicRecvBufferDrainFullChunks
0x1400096ef  cmp     [rbx], rbx
0x1400096f2  jz      short loc_140009725
0x1400096f4  mov     rdx, [rbp+57h+var_C0]
0x1400096f8  mov     rcx, rbx
0x1400096fb  call    QuicRecvBufferDrainFirstChunk
0x140009700  cmp     dword ptr [rbx+0D8h], 2
0x140009707  mov     rdx, [rbx]
0x14000970a  jnz     loc_1400097A3
0x140009710  cmp     qword ptr [rbx+0B8h], 0
0x140009718  mov     al, [rdx+14h]
0x14000971b  setnz   cl
0x14000971e  and     al, 0FEh
0x140009720  or      cl, al
0x140009722  mov     [rdx+14h], cl
0x140009725  mov     eax, [rdi+0E34h]
0x14000972b  lea     r8, [rbp+57h+DstBuf]
0x14000972f  mov     rcx, [rdi+168h]
0x140009736  mov     rdx, rdi
0x140009739  mov     dword ptr [rbp+57h+DstBuf], eax
0x14000973c  lea     rax, [rdi+194h]
0x140009743  mov     [rbp+57h+var_A8], rax
0x140009747  lea     rax, [rdi+178h]
0x14000974e  mov     [rbp+57h+var_A0], rax
0x140009752  mov     eax, dword ptr [rbp+57h+var_D0]
0x140009755  mov     [rbp+57h+var_98], eax
0x140009758  mov     rax, qword ptr [rbp+57h+var_D0+8]
0x14000975c  mov     [rbp+57h+var_88], rax
0x140009760  call    QuicBindingAcceptConnection
0x140009765  mov     rcx, [rdi+0F20h]
0x14000976c  test    rcx, rcx
0x14000976f  jz      short loc_140009797
0x140009771  mov     al, [rdi+0F9h]
0x140009777  test    al, 2
0x140009779  jnz     short loc_140009797
0x14000977b  test    al, 20h
0x14000977d  jz      short loc_140009797
0x14000977f  mov     rax, qword ptr [rbp+57h+var_D0+8]
0x140009783  movups  xmm0, xmmword ptr [rax+6]
0x140009787  movups  xmmword ptr [rcx+2], xmm0
0x14000978b  movups  xmm1, xmmword ptr [rax+16h]
0x14000978f  or      byte ptr [rcx+1], 1
0x140009793  movups  xmmword ptr [rcx+12h], xmm1
0x140009797  mov     eax, r14d
0x14000979a  jmp     short loc_1400097D7
0x14000979c  and     byte ptr [rdx+14h], 0FEh
0x1400097a0  mov     rdx, [rdx]
0x1400097a3  cmp     rdx, rbx
0x1400097a6  jnz     short loc_14000979C
0x1400097a8  jmp     loc_140009725
0x1400097ad  lea     rax, [rsi+10h]
0x1400097b1  mov     r8, r15
0x1400097b4  lea     r9, [rbp+57h+var_D0]
0x1400097b8  mov     [rsp+100h+var_E0], rax
0x1400097bd  xor     edx, edx
0x1400097bf  call    CxPlatTlsProcessData
0x1400097c4  mov     edx, dword ptr [rbp+57h+var_D0]
0x1400097c7  mov     rcx, rsi
0x1400097ca  mov     [rsi+0C8h], eax
0x1400097d0  call    QuicCryptoProcessDataComplete
0x1400097d5  xor     eax, eax
0x1400097d7  mov     rcx, [rbp+57h+var_30]
0x1400097db  xor     rcx, rsp; StackCookie
0x1400097de  call    __security_check_cookie
0x1400097e3  lea     r11, [rsp+100h+var_20]
0x1400097eb  mov     rbx, [r11+38h]
0x1400097ef  mov     rsi, [r11+40h]
0x1400097f3  mov     rsp, r11
0x1400097f6  pop     r15
0x1400097f8  pop     r14
0x1400097fa  pop     r12
0x1400097fc  pop     rdi
0x1400097fd  pop     rbp
0x1400097fe  retn
```
