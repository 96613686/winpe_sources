# QuicConnRecvPostProcessing

- ea: `0x140013200`
- end: `0x14001354a`
- name: `QuicConnRecvPostProcessing`
- size: `842`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x140012c80`

## callees

- `0x14000d490`
- `0x140010820`
- `0x140013200`
- `0x14001dcd0`
- `0x1400228b8`
- `0x140022a9c`
- `0x140033810`
- `0x14003c8e0`
- `0x14003c9e0`
- `0x14003ec10`
- `0x14003fea4`
- `0x140040b80`
- `0x140048d98`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400132c5`
- `ntoskrnl!_snprintf_s` at `0x1400134fb`
- `ntoskrnl!_snprintf_s` at `0x1400132c5`
- `ntoskrnl!_snprintf_s` at `0x1400134fb`
- `HAL!KeQueryPerformanceCounter` at `0x1400133b0`
- `HAL!KeQueryPerformanceCounter` at `0x1400133fe`
- `HAL!KeQueryPerformanceCounter` at `0x1400133b0`
- `HAL!KeQueryPerformanceCounter` at `0x1400133fe`

## string_xrefs

- `0x140013364`: `No unused CID for new path`

## pseudocode

```c
char __fastcall QuicConnRecvPostProcessing(__int64 a1, __int64 *a2, __int64 a3)
{
  bool v3; // r14
  size_t v4; // rbp
  __int64 *v8; // rbx
  const void *v9; // r15
  __int64 v10; // r9
  const char *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char v14; // al
  __int64 v15; // rax
  __int64 UnusedDestCid; // rax
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  char v21; // al
  LARGE_INTEGER v22; // rax
  int v23; // ecx
  int v24; // r9d
  __int64 v25; // rax
  __int64 v26; // rcx
  _QWORD v28[2]; // [rsp+30h] [rbp-308h] BYREF
  __int128 v29; // [rsp+40h] [rbp-2F8h]
  __int128 v30; // [rsp+50h] [rbp-2E8h]
  int v31; // [rsp+60h] [rbp-2D8h]
  _BYTE v32[520]; // [rsp+68h] [rbp-2D0h] BYREF
  char DstBuf[128]; // [rsp+270h] [rbp-C8h] BYREF

  v3 = 0;
  v4 = *(unsigned __int8 *)(a3 + 86);
  if ( (_BYTE)v4 )
  {
    v8 = *(__int64 **)(a1 + 1280);
    v9 = *(const void **)(a3 + 64);
    if ( v8 )
    {
      while ( (_BYTE)v4 != *((_BYTE *)v8 + 17) || memcmp(v9, v8 + 4, v4) )
      {
        v8 = (__int64 *)*v8;
        if ( !v8 )
          goto LABEL_11;
      }
      if ( (v8[2] & 0x10) == 0 )
      {
        if ( byte_14005C48B < 0 )
        {
          v11 = (const char *)QuicCidBufToStr(v32, v9, (unsigned __int8)v4, v10);
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "First usage of SrcCid: %s", v11);
          McTemplateU0ps_EtwWriteTransfer(v12, QuicConnLogInfo, a1, DstBuf);
        }
        *((_BYTE *)v8 + 16) |= 0x10u;
        v3 = (v8[2] & 1) == 0;
      }
    }
  }
LABEL_11:
  v13 = *a2;
  v14 = *(_BYTE *)(*a2 + 1);
  if ( (v14 & 0x10) != 0 )
  {
    if ( v3 )
    {
      if ( (v14 & 4) != 0 )
        *(_BYTE *)(v13 + 1) = v14 & 0xFB;
      else
        QuicConnRetireCurrentDestCid(a1, *a2);
    }
  }
  else
  {
    *(_BYTE *)(v13 + 1) = v14 | 0x10;
    if ( (*(_BYTE *)(*a2 + 1) & 2) == 0 )
    {
      v15 = *(_QWORD *)(*a2 + 144);
      if ( !v15 || v3 && *(_BYTE *)(v15 + 33) )
      {
        UnusedDestCid = QuicConnGetUnusedDestCid(a1);
        if ( !UnusedDestCid )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0ps_EtwWriteTransfer(v17, QuicConnError, a1, "No unused CID for new path");
          *(_BYTE *)(*a2 + 1) &= ~0x10u;
          v19 = *a2;
          *(_QWORD *)(*a2 + 144) = 0;
          return v19;
        }
        *(_QWORD *)(v18 + 144) = UnusedDestCid;
        *(_BYTE *)(*(_QWORD *)(*a2 + 144) + 32LL) |= 8u;
      }
      *(_BYTE *)(*a2 + 2) |= 1u;
      PerformanceCounter = KeQueryPerformanceCounter(0);
      *(_QWORD *)(*a2 + 232) = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart);
      CxPlatRandom(8u);
      v21 = *(_BYTE *)(a1 + 321);
      if ( (v21 & 0x20) != 0 )
      {
        *(_BYTE *)(a1 + 322) |= 1u;
        *(_BYTE *)(a1 + 321) = v21 & 0xDF;
        v22 = KeQueryPerformanceCounter(0);
        *(_QWORD *)(a1 + 552) = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)v22.QuadPart);
        CxPlatRandom(8u);
      }
      QuicSendSetSendFlag(a1 + 3416, 1024);
    }
  }
  LOBYTE(v19) = *(_BYTE *)(a3 + 93) & 0xC;
  if ( (_BYTE)v19 == 12 && (*(_BYTE *)(*a2 + 1) & 2) == 0 )
  {
    QuicPathSetActive(a1, *a2);
    *a2 = a1 + 320;
    if ( (byte_14005C489 & 0x40) != 0 )
    {
      LOBYTE(v24) = 28;
      McTemplateU0pubr1_EtwWriteTransfer(v23, (unsigned int)QuicConnRemoteAddrAdded, a1, v24, a1 + 376);
    }
    v25 = *a2 + 56;
    v28[0] = 5;
    v31 = 0;
    v29 = 0;
    v28[1] = v25;
    v30 = 0;
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Indicating QUIC_CONNECTION_EVENT_PEER_ADDRESS_CHANGED");
      McTemplateU0ps_EtwWriteTransfer(v26, QuicConnLogVerbose, a1, DstBuf);
    }
    LOBYTE(v19) = QuicConnIndicateEvent(a1, (__int64)v28);
  }
  return v19;
}

```

## disassembly

```asm
0x140013200  mov     r11, rsp
0x140013203  push    rsi
0x140013204  push    rdi
0x140013205  push    r13
0x140013207  push    r14
0x140013209  sub     rsp, 318h
0x140013210  mov     rax, cs:__security_cookie
0x140013217  xor     rax, rsp
0x14001321a  mov     [rsp+338h+var_48], rax
0x140013222  mov     [r11-30h], rbp
0x140013226  xor     r14b, r14b
0x140013229  movzx   ebp, byte ptr [r8+56h]
0x14001322e  mov     r13, r8
0x140013231  mov     rsi, rdx
0x140013234  mov     rdi, rcx
0x140013237  test    bpl, bpl
0x14001323a  jz      loc_14001330D
0x140013240  mov     [r11-28h], rbx
0x140013244  mov     rbx, [rcx+500h]
0x14001324b  mov     [r11-38h], r15
0x14001324f  mov     r15, [r8+40h]
0x140013253  test    rbx, rbx
0x140013256  jz      loc_1400132FD
0x14001325c  nop     dword ptr [rax+00h]
0x140013260  cmp     bpl, [rbx+11h]
0x140013264  jnz     short loc_140013279
0x140013266  mov     r8, rbp; Size
0x140013269  lea     rdx, [rbx+20h]; Buf2
0x14001326d  mov     rcx, r15; Buf1
0x140013270  call    memcmp
0x140013275  test    eax, eax
0x140013277  jz      short loc_140013283
0x140013279  mov     rbx, [rbx]
0x14001327c  test    rbx, rbx
0x14001327f  jnz     short loc_140013260
0x140013281  jmp     short loc_1400132FD
0x140013283  test    byte ptr [rbx+10h], 10h
0x140013287  jnz     short loc_1400132FD
0x140013289  movzx   eax, cs:byte_14005C48B
0x140013290  test    al, al
0x140013292  jns     short loc_1400132E8
0x140013294  movzx   r8d, bpl
0x140013298  lea     rcx, [rsp+338h+var_2D0]
0x14001329d  mov     rdx, r15
0x1400132a0  call    QuicCidBufToStr
0x1400132a5  lea     r9, aFirstUsageOfSr; "First usage of SrcCid: %s"
0x1400132ac  mov     [rsp+338h+var_318], rax
0x1400132b1  mov     edx, 80h; SizeInBytes
0x1400132b6  lea     rcx, [rsp+338h+DstBuf]; DstBuf
0x1400132be  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400132c5  call    cs:__imp__snprintf_s
0x1400132cc  nop     dword ptr [rax+rax+00h]
0x1400132d1  lea     r9, [rsp+338h+DstBuf]
0x1400132d9  mov     r8, rdi
0x1400132dc  lea     rdx, QuicConnLogInfo
0x1400132e3  call    McTemplateU0ps_EtwWriteTransfer
0x1400132e8  or      byte ptr [rbx+10h], 10h
0x1400132ec  mov     eax, 1
0x1400132f1  test    byte ptr [rbx+10h], 1
0x1400132f5  movzx   r14d, r14b
0x1400132f9  cmovz   r14d, eax
0x1400132fd  mov     rbx, [rsp+338h+var_28]
0x140013305  mov     r15, [rsp+338h+var_38]
0x14001330d  mov     rcx, [rsi]
0x140013310  mov     rbp, [rsp+338h+var_30]
0x140013318  movzx   eax, byte ptr [rcx+1]
0x14001331c  test    al, 10h
0x14001331e  jnz     loc_14001343D
0x140013324  or      al, 10h
0x140013326  mov     [rcx+1], al
0x140013329  mov     r9, [rsi]
0x14001332c  test    byte ptr [r9+1], 2
0x140013331  jnz     loc_140013458
0x140013337  mov     rax, [r9+90h]
0x14001333e  test    rax, rax
0x140013341  jz      short loc_14001334E
0x140013343  test    r14b, r14b
0x140013346  jz      short loc_1400133A7
0x140013348  cmp     byte ptr [rax+21h], 0
0x14001334c  jz      short loc_1400133A7
0x14001334e  mov     rcx, rdi
0x140013351  call    QuicConnGetUnusedDestCid
0x140013356  test    rax, rax
0x140013359  jnz     short loc_140013392
0x14001335b  test    cs:byte_14005C48B, 4
0x140013362  jz      short loc_14001337A
0x140013364  lea     r9, aNoUnusedCidFor; "No unused CID for new path"
0x14001336b  mov     r8, rdi
0x14001336e  lea     rdx, QuicConnError
0x140013375  call    McTemplateU0ps_EtwWriteTransfer
0x14001337a  mov     rax, [rsi]
0x14001337d  and     byte ptr [rax+1], 0EFh
0x140013381  mov     rax, [rsi]
0x140013384  xor     ecx, ecx
0x140013386  mov     [rax+90h], rcx
0x14001338d  jmp     loc_14001352B
0x140013392  mov     [r9+90h], rax
0x140013399  mov     rax, [rsi]
0x14001339c  mov     rcx, [rax+90h]
0x1400133a3  or      byte ptr [rcx+20h], 8
0x1400133a7  mov     rax, [rsi]
0x1400133aa  xor     ecx, ecx; PerformanceFrequency
0x1400133ac  or      byte ptr [rax+2], 1
0x1400133b0  call    cs:__imp_KeQueryPerformanceCounter
0x1400133b7  nop     dword ptr [rax+rax+00h]
0x1400133bc  mov     rcx, rax
0x1400133bf  call    QuicTimePlatToUs64
0x1400133c4  mov     rcx, [rsi]
0x1400133c7  mov     [rcx+0E8h], rax
0x1400133ce  mov     ecx, 8; cbBuffer
0x1400133d3  mov     rdx, [rsi]
0x1400133d6  add     rdx, 0DCh
0x1400133dd  call    CxPlatRandom
0x1400133e2  movzx   eax, byte ptr [rdi+141h]
0x1400133e9  test    al, 20h
0x1400133eb  jz      short loc_14001342A
0x1400133ed  or      byte ptr [rdi+142h], 1
0x1400133f4  and     al, 0DFh
0x1400133f6  xor     ecx, ecx; PerformanceFrequency
0x1400133f8  mov     [rdi+141h], al
0x1400133fe  call    cs:__imp_KeQueryPerformanceCounter
0x140013405  nop     dword ptr [rax+rax+00h]
0x14001340a  mov     rcx, rax
0x14001340d  call    QuicTimePlatToUs64
0x140013412  lea     rdx, [rdi+21Ch]
0x140013419  mov     [rdi+228h], rax
0x140013420  mov     ecx, 8; cbBuffer
0x140013425  call    CxPlatRandom
0x14001342a  lea     rcx, [rdi+0D58h]
0x140013431  mov     edx, 400h
0x140013436  call    QuicSendSetSendFlag
0x14001343b  jmp     short loc_140013458
0x14001343d  test    r14b, r14b
0x140013440  jz      short loc_140013458
0x140013442  test    al, 4
0x140013444  jnz     short loc_140013453
0x140013446  mov     rdx, rcx
0x140013449  mov     rcx, rdi
0x14001344c  call    QuicConnRetireCurrentDestCid
0x140013451  jmp     short loc_140013458
0x140013453  and     al, 0FBh
0x140013455  mov     [rcx+1], al
0x140013458  movzx   eax, byte ptr [r13+5Dh]
0x14001345d  and     al, 0Ch
0x14001345f  cmp     al, 0Ch
0x140013461  jnz     loc_14001352B
0x140013467  mov     rdx, [rsi]
0x14001346a  test    byte ptr [rdx+1], 2
0x14001346e  jnz     loc_14001352B
0x140013474  mov     rcx, rdi
0x140013477  call    QuicPathSetActive
0x14001347c  lea     rax, [rdi+140h]
0x140013483  mov     [rsi], rax
0x140013486  test    cs:byte_14005C489, 40h
0x14001348d  jz      short loc_1400134AD
0x14001348f  lea     rax, [rdi+178h]
0x140013496  mov     r9b, 1Ch
0x140013499  mov     r8, rdi
0x14001349c  mov     [rsp+338h+var_318], rax
0x1400134a1  lea     rdx, QuicConnRemoteAddrAdded
0x1400134a8  call    McTemplateU0pubr1_EtwWriteTransfer
0x1400134ad  mov     rax, [rsi]
0x1400134b0  xor     ecx, ecx
0x1400134b2  add     rax, 38h ; '8'
0x1400134b6  mov     [rsp+338h+var_308], 5
0x1400134bf  test    cs:byte_14005C48C, 1
0x1400134c6  xorps   xmm0, xmm0
0x1400134c9  xorps   xmm1, xmm1
0x1400134cc  mov     [rsp+338h+var_2D8], ecx
0x1400134d0  movdqu  [rsp+338h+var_2F8], xmm0
0x1400134d6  mov     [rsp+338h+var_300], rax
0x1400134db  movdqu  [rsp+338h+var_2E8], xmm1
0x1400134e1  jz      short loc_14001351E
0x1400134e3  lea     r8, [rcx-1]; MaxCount
0x1400134e7  mov     edx, 80h; SizeInBytes
0x1400134ec  lea     rcx, [rsp+338h+DstBuf]; DstBuf
0x1400134f4  lea     r9, aIndicatingQuic_15; "Indicating QUIC_CONNECTION_EVENT_PEER_A"...
0x1400134fb  call    cs:__imp__snprintf_s
0x140013502  nop     dword ptr [rax+rax+00h]
0x140013507  lea     r9, [rsp+338h+DstBuf]
0x14001350f  mov     r8, rdi
0x140013512  lea     rdx, QuicConnLogVerbose
0x140013519  call    McTemplateU0ps_EtwWriteTransfer
0x14001351e  lea     rdx, [rsp+338h+var_308]
0x140013523  mov     rcx, rdi
0x140013526  call    QuicConnIndicateEvent
0x14001352b  mov     rcx, [rsp+338h+var_48]
0x140013533  xor     rcx, rsp; StackCookie
0x140013536  call    __security_check_cookie
0x14001353b  add     rsp, 318h
0x140013542  pop     r14
0x140013544  pop     r13
0x140013546  pop     rdi
0x140013547  pop     rsi
0x140013548  retn
```
