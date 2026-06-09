# QuicStreamSetGetStreamForPeer

- ea: `0x140010440`
- end: `0x140010819`
- name: `QuicStreamSetGetStreamForPeer`
- size: `985`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400108c0`

## callees

- `0x14000b2e8`
- `0x14000bad0`
- `0x14000ca70`
- `0x140010440`
- `0x1400145c0`
- `0x14001dcd0`
- `0x140026bd4`
- `0x14002974c`
- `0x1400337e4`
- `0x140038b04`
- `0x140038b78`
- `0x14003c8e0`
- `0x14003ec10`
- `0x140040c0c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001064a`
- `ntoskrnl!_snprintf_s` at `0x1400106a6`
- `ntoskrnl!_snprintf_s` at `0x140010735`
- `ntoskrnl!_snprintf_s` at `0x14001064a`
- `ntoskrnl!_snprintf_s` at `0x1400106a6`
- `ntoskrnl!_snprintf_s` at `0x140010735`

## string_xrefs

- `0x14001071e`: `Configured for delayed ID FC updates`
- `0x1400107b7`: `Remote tried to open stream it wasn't allowed to open.`

## pseudocode

```c
__int64 __fastcall QuicStreamSetGetStreamForPeer(__int64 a1, unsigned __int64 a2, char a3, char a4, _BYTE *a5)
{
  __int64 v5; // r14
  __int64 result; // rax
  unsigned __int64 v9; // rdx
  __int64 v10; // r13
  _BOOL8 v11; // rcx
  unsigned int v12; // r12d
  __int64 v13; // rbx
  unsigned __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rdi
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v25; // [rsp+38h] [rbp-C8h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  _QWORD v27[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h]
  char DstBuf[128]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a1 - 2032;
  v25 = a5;
  *a5 = 0;
  if ( (*(_BYTE *)(a1 - 2032 + 248) & 0x30) != 0 )
    return 0;
  v9 = (a2 >> 2) + 1;
  v26 = a2 & 3;
  v10 = a1 + 24 * v26;
  v11 = (a2 & 2) != 0;
  v12 = ((a2 & 2) != 0) + 2;
  if ( !a3 )
    v12 = (a2 & 2) != 0;
  if ( v9 <= *(_QWORD *)v10 )
  {
    v13 = 0;
    v14 = *(_QWORD *)(v10 + 8);
    v24 = 0;
    if ( v9 > v14 )
    {
      if ( !a4 )
      {
        if ( (byte_14005C48B & 4) != 0 )
          McTemplateU0ps_EtwWriteTransfer(
            v11,
            QuicConnError,
            v5,
            "Remote tried to open stream it wasn't allowed to open.");
        QuicConnTransportError(v5, 10);
        *v25 = 1;
        return v13;
      }
      v17 = v9;
      while ( 1 )
      {
        LOBYTE(v9) = 1;
        if ( (int)QuicStreamInitialize(v5, v9, v12, &v24) < 0 )
          break;
        v13 = v24;
        LOBYTE(v18) = 1;
        v19 = v24;
        *(_QWORD *)(v24 + 80) = v26 + 4 * v14;
        if ( (int)QuicStreamStart(v19, 0, v18) < 0 || !(unsigned __int8)QuicStreamSetInsertStream(a1, v13) )
        {
          *v25 = 1;
          QuicConnTransportError(v5, 1);
          QuicStreamRelease(v13);
          return 0;
        }
        ++*(_WORD *)(v10 + 18);
        ++*(_QWORD *)(v10 + 8);
        CxPlatRefIncrement(v13 + 16);
        v27[0] = 6;
        v30 = 0;
        v28 = 0;
        LODWORD(v28) = v12;
        v29 = 0;
        v27[1] = v13;
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(
            DstBuf,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "Indicating QUIC_CONNECTION_EVENT_PEER_STREAM_STARTED [%p, 0x%x]",
            (const void *)v13,
            v12);
          McTemplateU0ps_EtwWriteTransfer(v20, QuicConnLogVerbose, v5, DstBuf);
        }
        *(_BYTE *)(v13 + 88) |= 0x10u;
        v21 = QuicConnIndicateEvent(v5, v27);
        *(_BYTE *)(v13 + 88) &= ~0x10u;
        if ( v21 >= 0 )
        {
          if ( (*(_BYTE *)(v13 + 92) & 8) != 0 )
          {
            v13 = 0;
            v24 = 0;
          }
          else
          {
            if ( !*(_QWORD *)(v13 + 712) )
            {
              CxPlatLogAssert(
                "C:\\__w\\1\\s\\msquic\\src\\core\\stream_set.c",
                847,
                "Stream->ClientCallbackHandler != ((void *)0)");
              __int2c();
            }
            if ( (v28 & 4) != 0 )
            {
              *(_BYTE *)(v13 + 93) |= 2u;
              if ( (byte_14005C48D & 1) != 0 )
              {
                _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Configured for delayed ID FC updates");
                McTemplateU0ps_EtwWriteTransfer(v23, QuicStreamLogVerbose, v13, DstBuf);
              }
            }
          }
        }
        else
        {
          if ( (byte_14005C48C & 0x40) != 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "New stream wasn't accepted, 0x%x", v21);
            McTemplateU0ps_EtwWriteTransfer(v22, QuicStreamLogWarning, v13, DstBuf);
          }
          QuicStreamClose(v13);
          v13 = 0;
          v24 = 0;
        }
        v14 = *(_QWORD *)(v10 + 8);
        if ( v14 == v17 )
          goto LABEL_37;
      }
      *v25 = 1;
      QuicConnTransportError(v5, 1);
      v13 = v24;
    }
    else
    {
      v15 = *(_QWORD *)(a1 + 96);
      if ( v15 )
      {
        v31 = 0;
        v32 = 0;
        v16 = CxPlatHashtableLookup(v15, (unsigned int)a2, &v31);
        if ( v16 )
        {
          while ( 1 )
          {
            v13 = v16 - 32;
            if ( *(_QWORD *)(v16 + 48) == a2 )
              break;
            v16 = CxPlatHashtableLookupNext(*(_QWORD *)(a1 + 96), &v31);
            if ( !v16 )
              goto LABEL_14;
          }
        }
        else
        {
LABEL_14:
          v13 = 0;
        }
      }
    }
LABEL_37:
    if ( v13 )
      CxPlatRefIncrement(v13 + 16);
    return v13;
  }
  if ( (byte_14005C48B & 4) != 0 )
    McTemplateU0ps_EtwWriteTransfer(v11, QuicConnError, v5, "Peer used more streams than allowed");
  QuicConnTransportError(v5, 4);
  result = 0;
  *a5 = 1;
  return result;
}

```

## disassembly

```asm
0x140010440  push    rbp
0x140010442  push    rbx
0x140010443  push    rdi
0x140010444  push    r14
0x140010446  push    r15
0x140010448  lea     rbp, [rsp-40h]
0x14001044d  sub     rsp, 140h
0x140010454  mov     rax, cs:__security_cookie
0x14001045b  xor     rax, rsp
0x14001045e  mov     [rbp+60h+var_40], rax
0x140010462  mov     rbx, [rbp+60h+arg_20]
0x140010469  lea     r14, [rcx-7F0h]
0x140010470  mov     rdi, rdx
0x140010473  mov     [rsp+160h+var_128], rbx
0x140010478  mov     r15, rcx
0x14001047b  mov     byte ptr [rbx], 0
0x14001047e  test    byte ptr [r14+0F8h], 30h
0x140010486  jz      short loc_14001048F
0x140010488  xor     eax, eax
0x14001048a  jmp     loc_1400107FD
0x14001048f  mov     [rsp+160h+var_28], r12
0x140010497  mov     rax, rdi
0x14001049a  and     eax, 3
0x14001049d  shr     rdx, 2
0x1400104a1  inc     rdx
0x1400104a4  mov     [rsp+160h+var_118], rax
0x1400104a9  mov     [rsp+160h+var_30], r13
0x1400104b1  lea     rax, [rax+rax*2]
0x1400104b5  lea     r13, [rcx+rax*8]
0x1400104b9  mov     rax, rdi
0x1400104bc  and     eax, 2
0x1400104bf  mov     ecx, 0
0x1400104c4  setnz   cl
0x1400104c7  xor     r12d, r12d
0x1400104ca  test    rax, rax
0x1400104cd  setnz   r12b
0x1400104d1  add     r12d, 2
0x1400104d5  test    r8b, r8b
0x1400104d8  cmovz   r12d, ecx
0x1400104dc  cmp     rdx, [r13+0]
0x1400104e0  jbe     short loc_140010518
0x1400104e2  test    cs:byte_14005C48B, 4
0x1400104e9  jz      short loc_140010501
0x1400104eb  lea     r9, aPeerUsedMoreSt; "Peer used more streams than allowed"
0x1400104f2  mov     r8, r14
0x1400104f5  lea     rdx, QuicConnError
0x1400104fc  call    McTemplateU0ps_EtwWriteTransfer
0x140010501  mov     edx, 4
0x140010506  mov     rcx, r14
0x140010509  call    QuicConnTransportError
0x14001050e  xor     eax, eax
0x140010510  mov     byte ptr [rbx], 1
0x140010513  jmp     loc_1400107ED
0x140010518  xor     ebx, ebx
0x14001051a  mov     [rsp+160h+arg_10], rsi
0x140010522  mov     rsi, [r13+8]
0x140010526  mov     [rsp+160h+var_130], rbx
0x14001052b  cmp     rdx, rsi
0x14001052e  ja      short loc_140010587
0x140010530  mov     rcx, [r15+60h]
0x140010534  test    rcx, rcx
0x140010537  jz      loc_14001079E
0x14001053d  xorps   xmm0, xmm0
0x140010540  mov     edx, edi
0x140010542  xor     eax, eax
0x140010544  lea     r8, [rbp+60h+var_D8]
0x140010548  movups  [rbp+60h+var_D8], xmm0
0x14001054c  mov     [rbp+60h+var_C8], rax
0x140010550  call    CxPlatHashtableLookup
0x140010555  test    rax, rax
0x140010558  jz      short loc_140010580
0x14001055a  nop     word ptr [rax+rax+00h]
0x140010560  cmp     [rax+30h], rdi
0x140010564  lea     rbx, [rax-20h]
0x140010568  jz      loc_14001079E
0x14001056e  mov     rcx, [r15+60h]
0x140010572  lea     rdx, [rbp+60h+var_D8]
0x140010576  call    CxPlatHashtableLookupNext
0x14001057b  test    rax, rax
0x14001057e  jnz     short loc_140010560
0x140010580  xor     ebx, ebx
0x140010582  jmp     loc_14001079E
0x140010587  test    r9b, r9b
0x14001058a  jz      loc_1400107AE
0x140010590  mov     rdi, rdx
0x140010593  lea     r9, [rsp+160h+var_130]
0x140010598  mov     r8d, r12d
0x14001059b  mov     dl, 1
0x14001059d  mov     rcx, r14
0x1400105a0  call    QuicStreamInitialize
0x1400105a5  test    eax, eax
0x1400105a7  js      loc_140010784
0x1400105ad  mov     rbx, [rsp+160h+var_130]
0x1400105b2  mov     r8b, 1
0x1400105b5  mov     rax, [rsp+160h+var_118]
0x1400105ba  xor     edx, edx
0x1400105bc  mov     rcx, rbx
0x1400105bf  lea     rax, [rax+rsi*4]
0x1400105c3  mov     [rbx+50h], rax
0x1400105c7  call    QuicStreamStart
0x1400105cc  test    eax, eax
0x1400105ce  js      loc_140010763
0x1400105d4  mov     rdx, rbx
0x1400105d7  mov     rcx, r15
0x1400105da  call    QuicStreamSetInsertStream
0x1400105df  test    al, al
0x1400105e1  jz      loc_140010763
0x1400105e7  inc     word ptr [r13+12h]
0x1400105ec  lea     rcx, [rbx+10h]
0x1400105f0  inc     qword ptr [r13+8]
0x1400105f4  call    CxPlatRefIncrement
0x1400105f9  xor     esi, esi
0x1400105fb  mov     [rsp+160h+var_110], 6
0x140010604  test    cs:byte_14005C48C, 1
0x14001060b  xorps   xmm0, xmm0
0x14001060e  xorps   xmm1, xmm1
0x140010611  mov     [rbp+60h+var_E0], esi
0x140010614  movdqu  [rsp+160h+var_100], xmm0
0x14001061a  mov     dword ptr [rsp+160h+var_100], r12d
0x14001061f  movdqu  [rsp+160h+var_F0], xmm1
0x140010625  mov     [rsp+160h+var_108], rbx
0x14001062a  jz      short loc_140010669
0x14001062c  mov     [rsp+160h+var_138], r12d
0x140010631  lea     r9, aIndicatingQuic_25; "Indicating QUIC_CONNECTION_EVENT_PEER_S"...
0x140010638  mov     edx, 80h; SizeInBytes
0x14001063d  mov     [rsp+160h+var_140], rbx
0x140010642  lea     r8, [rsi-1]; MaxCount
0x140010646  lea     rcx, [rbp+60h+DstBuf]; DstBuf
0x14001064a  call    cs:__imp__snprintf_s
0x140010651  nop     dword ptr [rax+rax+00h]
0x140010656  lea     r9, [rbp+60h+DstBuf]
0x14001065a  mov     r8, r14
0x14001065d  lea     rdx, QuicConnLogVerbose
0x140010664  call    McTemplateU0ps_EtwWriteTransfer
0x140010669  or      byte ptr [rbx+58h], 10h
0x14001066d  lea     rdx, [rsp+160h+var_110]
0x140010672  mov     rcx, r14
0x140010675  call    QuicConnIndicateEvent
0x14001067a  and     byte ptr [rbx+58h], 0EFh
0x14001067e  test    eax, eax
0x140010680  jns     short loc_1400106D7
0x140010682  test    cs:byte_14005C48C, 40h
0x140010689  jz      short loc_1400106C5
0x14001068b  lea     r9, aNewStreamWasnT; "New stream wasn't accepted, 0x%x"
0x140010692  mov     dword ptr [rsp+160h+var_140], eax
0x140010696  mov     edx, 80h; SizeInBytes
0x14001069b  lea     rcx, [rbp+60h+DstBuf]; DstBuf
0x14001069f  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400106a6  call    cs:__imp__snprintf_s
0x1400106ad  nop     dword ptr [rax+rax+00h]
0x1400106b2  lea     r9, [rbp+60h+DstBuf]
0x1400106b6  mov     r8, rbx
0x1400106b9  lea     rdx, QuicStreamLogWarning
0x1400106c0  call    McTemplateU0ps_EtwWriteTransfer
0x1400106c5  mov     rcx, rbx
0x1400106c8  call    QuicStreamClose
0x1400106cd  mov     rbx, rsi
0x1400106d0  mov     [rsp+160h+var_130], rbx
0x1400106d5  jmp     short loc_140010754
0x1400106d7  test    byte ptr [rbx+5Ch], 8
0x1400106db  jz      short loc_1400106E7
0x1400106dd  mov     rbx, rsi
0x1400106e0  mov     [rsp+160h+var_130], rbx
0x1400106e5  jmp     short loc_140010754
0x1400106e7  cmp     [rbx+2C8h], rsi
0x1400106ee  jnz     short loc_14001070A
0x1400106f0  lea     r8, aStreamClientca; "Stream->ClientCallbackHandler != ((void"...
0x1400106f7  mov     edx, 34Fh
0x1400106fc  lea     rcx, aCW1SMsquicSrcC_17; "C:\\__w\\1\\s\\msquic\\src\\core\\strea"...
0x140010703  call    CxPlatLogAssert
0x140010708  int     2Ch; Windows NT - assertion failure
0x14001070a  test    byte ptr [rsp+160h+var_100], 4
0x14001070f  jz      short loc_140010754
0x140010711  or      byte ptr [rbx+5Dh], 2
0x140010715  test    cs:byte_14005C48D, 1
0x14001071c  jz      short loc_140010754
0x14001071e  lea     r9, aConfiguredForD; "Configured for delayed ID FC updates"
0x140010725  mov     edx, 80h; SizeInBytes
0x14001072a  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140010731  lea     rcx, [rbp+60h+DstBuf]; DstBuf
0x140010735  call    cs:__imp__snprintf_s
0x14001073c  nop     dword ptr [rax+rax+00h]
0x140010741  lea     r9, [rbp+60h+DstBuf]
0x140010745  mov     r8, rbx
0x140010748  lea     rdx, QuicStreamLogVerbose
0x14001074f  call    McTemplateU0ps_EtwWriteTransfer
0x140010754  mov     rsi, [r13+8]
0x140010758  cmp     rsi, rdi
0x14001075b  jnz     loc_140010593
0x140010761  jmp     short loc_14001079E
0x140010763  mov     rax, [rsp+160h+var_128]
0x140010768  mov     edx, 1
0x14001076d  mov     rcx, r14
0x140010770  mov     byte ptr [rax], 1
0x140010773  call    QuicConnTransportError
0x140010778  mov     rcx, rbx
0x14001077b  call    QuicStreamRelease
0x140010780  xor     ebx, ebx
0x140010782  jmp     short loc_1400107E2
0x140010784  mov     rax, [rsp+160h+var_128]
0x140010789  mov     edx, 1
0x14001078e  mov     rcx, r14
0x140010791  mov     byte ptr [rax], 1
0x140010794  call    QuicConnTransportError
0x140010799  mov     rbx, [rsp+160h+var_130]
0x14001079e  test    rbx, rbx
0x1400107a1  jz      short loc_1400107E2
0x1400107a3  lea     rcx, [rbx+10h]
0x1400107a7  call    CxPlatRefIncrement
0x1400107ac  jmp     short loc_1400107E2
0x1400107ae  test    cs:byte_14005C48B, 4
0x1400107b5  jz      short loc_1400107CD
0x1400107b7  lea     r9, aRemoteTriedToO; "Remote tried to open stream it wasn't a"...
0x1400107be  mov     r8, r14
0x1400107c1  lea     rdx, QuicConnError
0x1400107c8  call    McTemplateU0ps_EtwWriteTransfer
0x1400107cd  mov     edx, 0Ah
0x1400107d2  mov     rcx, r14
0x1400107d5  call    QuicConnTransportError
0x1400107da  mov     rax, [rsp+160h+var_128]
0x1400107df  mov     byte ptr [rax], 1
0x1400107e2  mov     rsi, [rsp+160h+arg_10]
0x1400107ea  mov     rax, rbx
0x1400107ed  mov     r12, [rsp+160h+var_28]
0x1400107f5  mov     r13, [rsp+160h+var_30]
0x1400107fd  mov     rcx, [rbp+60h+var_40]
0x140010801  xor     rcx, rsp; StackCookie
0x140010804  call    __security_check_cookie
0x140010809  add     rsp, 140h
0x140010810  pop     r15
0x140010812  pop     r14
0x140010814  pop     rdi
0x140010815  pop     rbx
0x140010816  pop     rbp
0x140010817  retn
```
