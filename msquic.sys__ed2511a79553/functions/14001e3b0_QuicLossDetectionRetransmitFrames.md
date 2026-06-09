# QuicLossDetectionRetransmitFrames

- ea: `0x14001e3b0`
- end: `0x14001e786`
- name: `QuicLossDetectionRetransmitFrames`
- size: `982`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: ``

## callers

- `0x14001e1b8`
- `0x14001e790`
- `0x140026f1c`
- `0x1400492d4`
- `0x140049440`

## callees

- `0x14000d230`
- `0x14000d490`
- `0x140010820`
- `0x140013a40`
- `0x14001e3b0`
- `0x14001ec28`
- `0x14001ec64`
- `0x14001eee0`
- `0x14001ef7c`
- `0x14003c8e0`
- `0x14003ec10`
- `0x14004572c`
- `0x140048c38`
- `0x140048c78`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001e679`
- `ntoskrnl!_snprintf_s` at `0x14001e679`
- `HAL!KeQueryPerformanceCounter` at `0x14001e600`
- `HAL!KeQueryPerformanceCounter` at `0x14001e600`

## string_xrefs

- `0x14001e660`: `Path[%hhu] validation timed out`

## pseudocode

```c
char __fastcall QuicLossDetectionRetransmitFrames(__int64 a1, _BYTE *a2, char a3)
{
  char v3; // bl
  __int64 v4; // rdi
  unsigned __int8 i; // r14
  __int64 v9; // rdx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  bool v15; // zf
  unsigned int v16; // ecx
  char v17; // al
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  __int64 v24; // rdx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  __int64 DestCidFromSeq; // rax
  __int64 SourceCidFromSeq; // rax
  char v32; // cl
  __int64 PathByID; // rax
  unsigned __int8 *v34; // rbp
  LARGE_INTEGER PerformanceCounter; // rax
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // r8
  __int64 v38; // rcx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned __int8 v44; // [rsp+30h] [rbp-C8h] BYREF
  char v45[15]; // [rsp+31h] [rbp-C7h] BYREF
  char DstBuf[128]; // [rsp+40h] [rbp-B8h] BYREF

  v3 = 0;
  v4 = a1 - 2632;
  for ( i = 0; i < a2[90]; ++i )
  {
    v9 = 3LL * i;
    v10 = *(unsigned __int16 *)&a2[24 * i + 114];
    if ( v10 > 0x10 )
    {
      if ( v10 <= 0x1A )
      {
        if ( v10 != 26 )
        {
          v25 = v10 - 17;
          if ( !v25 )
          {
            v18 = 3LL * i;
            v19 = 2;
            goto LABEL_16;
          }
          v26 = v25 - 1;
          if ( v26 )
          {
            v27 = v26 - 1;
            if ( v27 )
            {
              v28 = v27 - 2;
              if ( v28 )
              {
                v29 = v28 - 3;
                if ( v29 )
                {
                  if ( v29 != 1 )
                    continue;
                  DestCidFromSeq = QuicConnGetDestCidFromSeq(v4, *(_QWORD *)&a2[24 * i + 96], 0);
                  if ( !DestCidFromSeq )
                    continue;
                  *(_BYTE *)(DestCidFromSeq + 32) |= 2u;
                  v24 = 512;
                }
                else
                {
                  v45[0] = 0;
                  SourceCidFromSeq = QuicConnGetSourceCidFromSeq(v4, *(_QWORD *)&a2[24 * i + 96], 0, v45);
                  if ( !SourceCidFromSeq )
                    continue;
                  v32 = *(_BYTE *)(SourceCidFromSeq + 40);
                  if ( (v32 & 4) != 0 )
                    continue;
                  v24 = 256;
                  *(_BYTE *)(SourceCidFromSeq + 40) = v32 | 2;
                }
                goto LABEL_63;
              }
              v18 = 3LL * i;
              v19 = 1;
LABEL_16:
              v17 = QuicSendSetStreamSendFlag(v4 + 3416, *(_QWORD *)&a2[8 * v18 + 96], v19);
              goto LABEL_64;
            }
            v24 = 128;
          }
          else
          {
            v24 = 64;
          }
LABEL_63:
          v17 = QuicSendSetSendFlag(v4 + 3416, v24);
          goto LABEL_64;
        }
        LOBYTE(v9) = a2[42];
        v44 = 0;
        PathByID = QuicConnGetPathByID(v4, v9, &v44);
        v34 = (unsigned __int8 *)PathByID;
        if ( !PathByID || (*(_BYTE *)(PathByID + 1) & 0x20) != 0 )
          continue;
        PerformanceCounter = KeQueryPerformanceCounter(0);
        v36 = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart)
            - *((_QWORD *)v34 + 29);
        v37 = 3 * (*((_QWORD *)v34 + 19) + 4 * (*((_QWORD *)v34 + 23) + 250LL * *(_QWORD *)(a1 - 928)));
        if ( v37 <= (unsigned int)(6000 * *(_DWORD *)(v4 + 192)) )
          v37 = (unsigned int)(6000 * *(_DWORD *)(v4 + 192));
        if ( v36 > v37 )
        {
          if ( byte_14005C48B < 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Path[%hhu] validation timed out", *v34);
            McTemplateU0ps_EtwWriteTransfer(v38, QuicConnLogInfo, v4, DstBuf);
          }
          _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v4 + 72) + 2432LL));
          QuicPathRemove(v4, v44);
          continue;
        }
        v34[2] |= 1u;
        v20 = 1024;
        goto LABEL_20;
      }
      v39 = v10 - 30;
      if ( !v39 )
      {
        v24 = 0x2000;
        goto LABEL_63;
      }
      v40 = v39 - 3;
      if ( !v40 )
      {
        v18 = 3LL * i;
        v19 = 128;
        goto LABEL_16;
      }
      v41 = v40 - 15;
      if ( !v41 || (v42 = v41 - 1) == 0 )
      {
        if ( (a2[88] & 0x20) == 0 )
          QuicDatagramIndicateSendStateChange(v4, &a2[8 * v9 + 96], 2);
        continue;
      }
      if ( v42 == 126 && *(_QWORD *)&a2[24 * i + 96] == *(_QWORD *)(v4 + 288) )
      {
        v24 = 0x8000;
        goto LABEL_63;
      }
    }
    else
    {
      if ( v10 == 16 )
      {
        v24 = 32;
        goto LABEL_63;
      }
      if ( v10 > 0xA )
      {
        v21 = v10 - 11;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              v16 = v23 - 1;
              v15 = v16 == 0;
LABEL_11:
              if ( !v15 && v16 != 1 )
                continue;
            }
          }
        }
LABEL_13:
        v17 = QuicStreamOnLoss(*(_QWORD *)&a2[24 * i + 96], &a2[8 * v9 + 96]);
LABEL_64:
        v3 |= v17;
        continue;
      }
      if ( v10 == 10 )
        goto LABEL_13;
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 3;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              v16 = v14 - 2;
              v15 = v16 == 0;
              goto LABEL_11;
            }
            v17 = QuicCryptoOnLoss(v4 + 2784, &a2[8 * v9 + 96]);
            goto LABEL_64;
          }
          v18 = 3LL * i;
          v19 = 8;
        }
        else
        {
          v18 = 3LL * i;
          v19 = 4;
        }
        goto LABEL_16;
      }
      if ( (a2[88] & 8) == 0 )
      {
        v20 = 4096;
LABEL_20:
        QuicSendSetSendFlag(v4 + 3416, v20);
      }
    }
  }
  a2[88] |= 0x20u;
  if ( a3 )
    QuicSentPacketPoolReturnPacketMetadata(a2, v4);
  return v3;
}

```

## disassembly

```asm
0x14001e3b0  mov     [rsp+arg_10], rbx
0x14001e3b5  mov     [rsp+arg_18], rbp
0x14001e3ba  push    rsi
0x14001e3bb  push    rdi
0x14001e3bc  push    r12
0x14001e3be  push    r14
0x14001e3c0  push    r15
0x14001e3c2  sub     rsp, 0D0h
0x14001e3c9  mov     rax, cs:__security_cookie
0x14001e3d0  xor     rax, rsp
0x14001e3d3  mov     [rsp+0F8h+var_38], rax
0x14001e3db  xor     bl, bl
0x14001e3dd  lea     rdi, [rcx-0A48h]
0x14001e3e4  xor     r14b, r14b
0x14001e3e7  mov     r12b, r8b
0x14001e3ea  mov     rsi, rdx
0x14001e3ed  mov     r15, rcx
0x14001e3f0  cmp     [rdx+5Ah], bl
0x14001e3f3  jbe     loc_14001E743
0x14001e3f9  movzx   r8d, r14b
0x14001e3fd  lea     rdx, [r8+r8*2]
0x14001e401  movzx   ecx, word ptr [rsi+rdx*8+72h]
0x14001e406  cmp     ecx, 10h
0x14001e409  ja      loc_14001E4F6
0x14001e40f  jz      loc_14001E4EC
0x14001e415  cmp     ecx, 0Ah
0x14001e418  ja      loc_14001E4C9
0x14001e41e  jz      short loc_14001E446
0x14001e420  sub     ecx, 1
0x14001e423  jz      loc_14001E4A9
0x14001e429  sub     ecx, 3
0x14001e42c  jz      short loc_14001E49D
0x14001e42e  sub     ecx, 1
0x14001e431  jz      short loc_14001E47A
0x14001e433  sub     ecx, 1
0x14001e436  jz      short loc_14001E461
0x14001e438  sub     ecx, 2
0x14001e43b  jz      short loc_14001E446
0x14001e43d  cmp     ecx, 1
0x14001e440  jnz     loc_14001E736
0x14001e446  add     rdx, 0Ch
0x14001e44a  lea     rcx, [r8+r8*2]
0x14001e44e  mov     rcx, [rsi+rcx*8+60h]
0x14001e453  lea     rdx, [rsi+rdx*8]
0x14001e457  call    QuicStreamOnLoss
0x14001e45c  jmp     loc_14001E734
0x14001e461  add     rdx, 0Ch
0x14001e465  lea     rcx, [rdi+0AE0h]
0x14001e46c  lea     rdx, [rsi+rdx*8]
0x14001e470  call    QuicCryptoOnLoss
0x14001e475  jmp     loc_14001E734
0x14001e47a  lea     rdx, [r8+r8*2]
0x14001e47e  mov     r8d, 8
0x14001e484  mov     rdx, [rsi+rdx*8+60h]
0x14001e489  lea     rcx, [rdi+0D58h]
0x14001e490  xor     r9d, r9d
0x14001e493  call    QuicSendSetStreamSendFlag
0x14001e498  jmp     loc_14001E734
0x14001e49d  lea     rdx, [r8+r8*2]
0x14001e4a1  mov     r8d, 4
0x14001e4a7  jmp     short loc_14001E484
0x14001e4a9  test    byte ptr [rsi+58h], 8
0x14001e4ad  jnz     loc_14001E736
0x14001e4b3  mov     edx, 1000h
0x14001e4b8  lea     rcx, [rdi+0D58h]
0x14001e4bf  call    QuicSendSetSendFlag
0x14001e4c4  jmp     loc_14001E736
0x14001e4c9  sub     ecx, 0Bh
0x14001e4cc  jz      loc_14001E446
0x14001e4d2  sub     ecx, 1
0x14001e4d5  jz      loc_14001E446
0x14001e4db  sub     ecx, 1
0x14001e4de  jz      loc_14001E446
0x14001e4e4  sub     ecx, 1
0x14001e4e7  jmp     loc_14001E43B
0x14001e4ec  mov     edx, 20h ; ' '
0x14001e4f1  jmp     loc_14001E728
0x14001e4f6  cmp     ecx, 1Ah
0x14001e4f9  ja      loc_14001E6C4
0x14001e4ff  jz      loc_14001E5D3
0x14001e505  sub     ecx, 11h
0x14001e508  jz      loc_14001E5C4
0x14001e50e  sub     ecx, 1
0x14001e511  jz      loc_14001E5BA
0x14001e517  sub     ecx, 1
0x14001e51a  jz      loc_14001E5B0
0x14001e520  sub     ecx, 2
0x14001e523  jz      short loc_14001E5A1
0x14001e525  sub     ecx, 3
0x14001e528  jz      short loc_14001E55E
0x14001e52a  cmp     ecx, 1
0x14001e52d  jnz     loc_14001E736
0x14001e533  lea     rdx, [r8+r8*2]
0x14001e537  mov     rcx, rdi
0x14001e53a  mov     rdx, [rsi+rdx*8+60h]
0x14001e53f  xor     r8d, r8d
0x14001e542  call    QuicConnGetDestCidFromSeq
0x14001e547  test    rax, rax
0x14001e54a  jz      loc_14001E736
0x14001e550  or      byte ptr [rax+20h], 2
0x14001e554  mov     edx, 200h
0x14001e559  jmp     loc_14001E728
0x14001e55e  lea     rdx, [r8+r8*2]
0x14001e562  mov     [rsp+0F8h+var_C7], 0
0x14001e567  mov     rdx, [rsi+rdx*8+60h]
0x14001e56c  lea     r9, [rsp+0F8h+var_C7]
0x14001e571  xor     r8d, r8d
0x14001e574  mov     rcx, rdi
0x14001e577  call    QuicConnGetSourceCidFromSeq
0x14001e57c  test    rax, rax
0x14001e57f  jz      loc_14001E736
0x14001e585  mov     cl, [rax+28h]
0x14001e588  test    cl, 4
0x14001e58b  jnz     loc_14001E736
0x14001e591  or      cl, 2
0x14001e594  mov     edx, 100h
0x14001e599  mov     [rax+28h], cl
0x14001e59c  jmp     loc_14001E728
0x14001e5a1  lea     rdx, [r8+r8*2]
0x14001e5a5  mov     r8d, 1
0x14001e5ab  jmp     loc_14001E484
0x14001e5b0  mov     edx, 80h
0x14001e5b5  jmp     loc_14001E728
0x14001e5ba  mov     edx, 40h ; '@'
0x14001e5bf  jmp     loc_14001E728
0x14001e5c4  lea     rdx, [r8+r8*2]
0x14001e5c8  mov     r8d, 2
0x14001e5ce  jmp     loc_14001E484
0x14001e5d3  mov     dl, [rsi+2Ah]
0x14001e5d6  lea     r8, [rsp+0F8h+var_C8]
0x14001e5db  mov     rcx, rdi
0x14001e5de  mov     [rsp+0F8h+var_C8], 0
0x14001e5e3  call    QuicConnGetPathByID
0x14001e5e8  mov     rbp, rax
0x14001e5eb  test    rax, rax
0x14001e5ee  jz      loc_14001E736
0x14001e5f4  test    byte ptr [rax+1], 20h
0x14001e5f8  jnz     loc_14001E736
0x14001e5fe  xor     ecx, ecx; PerformanceFrequency
0x14001e600  call    cs:__imp_KeQueryPerformanceCounter
0x14001e607  nop     dword ptr [rax+rax+00h]
0x14001e60c  mov     rcx, rax
0x14001e60f  call    QuicTimePlatToUs64
0x14001e614  imul    rdx, [r15-3A0h], 0FAh
0x14001e61f  sub     rax, [rbp+0E8h]
0x14001e626  add     rdx, [rbp+0B8h]
0x14001e62d  mov     rcx, [rbp+98h]
0x14001e634  lea     rdx, [rcx+rdx*4]
0x14001e638  lea     r8, [rdx+rdx*2]
0x14001e63c  imul    edx, [rdi+0C0h], 1770h
0x14001e646  cmp     r8, rdx
0x14001e649  cmovbe  r8, rdx
0x14001e64d  cmp     rax, r8
0x14001e650  jbe     short loc_14001E6B6
0x14001e652  mov     al, cs:byte_14005C48B
0x14001e658  test    al, al
0x14001e65a  jns     short loc_14001E699
0x14001e65c  movzx   eax, byte ptr [rbp+0]
0x14001e660  lea     r9, aPathHhuValidat_0; "Path[%hhu] validation timed out"
0x14001e667  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001e66b  mov     [rsp+0F8h+var_D8], eax
0x14001e66f  mov     edx, 80h; SizeInBytes
0x14001e674  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x14001e679  call    cs:__imp__snprintf_s
0x14001e680  nop     dword ptr [rax+rax+00h]
0x14001e685  lea     r9, [rsp+0F8h+DstBuf]
0x14001e68a  mov     r8, rdi
0x14001e68d  lea     rdx, QuicConnLogInfo
0x14001e694  call    McTemplateU0ps_EtwWriteTransfer
0x14001e699  mov     rax, [rdi+48h]
0x14001e69d  lock inc qword ptr [rax+980h]
0x14001e6a5  mov     dl, [rsp+0F8h+var_C8]
0x14001e6a9  mov     rcx, rdi
0x14001e6ac  call    QuicPathRemove
0x14001e6b1  jmp     loc_14001E736
0x14001e6b6  or      byte ptr [rbp+2], 1
0x14001e6ba  mov     edx, 400h
0x14001e6bf  jmp     loc_14001E4B8
0x14001e6c4  sub     ecx, 1Eh
0x14001e6c7  jz      short loc_14001E723
0x14001e6c9  sub     ecx, 3
0x14001e6cc  jz      short loc_14001E714
0x14001e6ce  sub     ecx, 0Fh
0x14001e6d1  jz      short loc_14001E6F6
0x14001e6d3  sub     ecx, 1
0x14001e6d6  jz      short loc_14001E6F6
0x14001e6d8  cmp     ecx, 7Eh ; '~'
0x14001e6db  jnz     short loc_14001E736
0x14001e6dd  mov     rax, [rdi+120h]
0x14001e6e4  lea     rcx, [r8+r8*2]
0x14001e6e8  cmp     [rsi+rcx*8+60h], rax
0x14001e6ed  jnz     short loc_14001E736
0x14001e6ef  mov     edx, 8000h
0x14001e6f4  jmp     short loc_14001E728
0x14001e6f6  test    byte ptr [rsi+58h], 20h
0x14001e6fa  jnz     short loc_14001E736
0x14001e6fc  add     rdx, 0Ch
0x14001e700  mov     r8d, 2
0x14001e706  mov     rcx, rdi
0x14001e709  lea     rdx, [rsi+rdx*8]
0x14001e70d  call    QuicDatagramIndicateSendStateChange
0x14001e712  jmp     short loc_14001E736
0x14001e714  lea     rdx, [r8+r8*2]
0x14001e718  mov     r8d, 80h
0x14001e71e  jmp     loc_14001E484
0x14001e723  mov     edx, 2000h
0x14001e728  lea     rcx, [rdi+0D58h]
0x14001e72f  call    QuicSendSetSendFlag
0x14001e734  or      bl, al
0x14001e736  inc     r14b
0x14001e739  cmp     r14b, [rsi+5Ah]
0x14001e73d  jb      loc_14001E3F9
0x14001e743  or      byte ptr [rsi+58h], 20h
0x14001e747  test    r12b, r12b
0x14001e74a  jz      short loc_14001E757
0x14001e74c  mov     rdx, rdi
0x14001e74f  mov     rcx, rsi
0x14001e752  call    QuicSentPacketPoolReturnPacketMetadata
0x14001e757  mov     al, bl
0x14001e759  mov     rcx, [rsp+0F8h+var_38]
0x14001e761  xor     rcx, rsp; StackCookie
0x14001e764  call    __security_check_cookie
0x14001e769  lea     r11, [rsp+0F8h+var_28]
0x14001e771  mov     rbx, [r11+40h]
0x14001e775  mov     rbp, [r11+48h]
0x14001e779  mov     rsp, r11
0x14001e77c  pop     r15
0x14001e77e  pop     r14
0x14001e780  pop     r12
0x14001e782  pop     rdi
0x14001e783  pop     rsi
0x14001e784  retn
```
