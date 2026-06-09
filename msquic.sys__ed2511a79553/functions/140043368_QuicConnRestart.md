# QuicConnRestart

- ea: `0x140043368`
- end: `0x1400435b7`
- name: `QuicConnRestart`
- size: `591`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140042e10`
- `0x1400430f0`

## callees

- `0x14000554c`
- `0x14000577c`
- `0x14000d490`
- `0x14000d7a0`
- `0x140030338`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003ce00`
- `0x14003ec10`
- `0x140042bbc`
- `0x140043368`
- `0x140049440`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400433d4`
- `ntoskrnl!_snprintf_s` at `0x1400433d4`

## string_xrefs

- `0x1400433c0`: `Restart (CompleteReset=%hhu)`

## pseudocode

```c
__int64 __fastcall QuicConnRestart(__int64 a1, unsigned __int8 a2)
{
  int v3; // edi
  __int64 v4; // rcx
  unsigned __int64 v5; // rcx
  __int64 *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  bool v9; // zf
  int v10; // eax
  char DstBuf[256]; // [rsp+30h] [rbp-118h] BYREF

  v3 = a2;
  if ( (*(_BYTE *)(a1 + 248) & 4) == 0 )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 2002, "Connection->State.Started");
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Restart (CompleteReset=%hhu)", v3);
    McTemplateU0ps_EtwWriteTransfer(v4, QuicConnLogInfo, a1, DstBuf);
  }
  if ( (_BYTE)v3 )
  {
    *(_BYTE *)(a1 + 321) &= ~8u;
    v5 = (unsigned int)(1000 * *(_DWORD *)(a1 + 192));
    *(_QWORD *)(a1 + 472) = v5;
    *(_QWORD *)(a1 + 504) = v5 >> 1;
  }
  v6 = (__int64 *)(a1 + 2760);
  v7 = 3;
  do
  {
    v8 = *v6++;
    *(_BYTE *)(v8 + 394) &= 0xFCu;
    *(_WORD *)(v8 + 392) = 0;
    *(_QWORD *)(v8 + 376) = 0;
    *(_QWORD *)(v8 + 384) = 0;
    *(_OWORD *)(v8 + 352) = 0;
    *(_QWORD *)(v8 + 368) = 0;
    *(_DWORD *)(v8 + 208) = 0;
    *(_DWORD *)(v8 + 56) = 0;
    --v7;
  }
  while ( v7 );
  (*(void (__fastcall **)(__int64, __int64))(a1 + 2192))(a1 + 2168, 1);
  v9 = (*(_BYTE *)(a1 + 3416) & 2) == 0;
  *(_DWORD *)(a1 + 3488) = 0;
  *(_QWORD *)(a1 + 3432) = 0;
  if ( !v9 )
  {
    QuicConnTimerCancel(a1, 1);
    *(_BYTE *)(a1 + 3416) &= ~2u;
  }
  QuicConnTimerCancel(a1, 0);
  QuicLossDetectionReset(a1 + 2632);
  QuicCryptoTlsCleanupTransportParameters(a1 + 1624);
  if ( (_BYTE)v3 )
  {
    memset(DstBuf, 0, sizeof(DstBuf));
    if ( (int)QuicConnGenerateLocalTransportParameters(a1, (__int64)DstBuf) < 0 )
    {
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 2036, "(((NTSTATUS)(Status)) >= 0)");
      __int2c();
    }
    v10 = QuicCryptoInitializeTls(a1 + 2784, *(_QWORD *)(*(_QWORD *)(a1 + 88) + 48LL), DstBuf);
    if ( v10 < 0 )
      QuicConnFatalError(a1, (unsigned int)v10, 0);
    return QuicCryptoTlsCleanupTransportParameters(DstBuf);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 3160) )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c", 368, "Crypto->RecvTotalConsumed == 0");
    *(_BYTE *)(a1 + 2784) &= ~2u;
    *(_QWORD *)(a1 + 2988) = 0;
    *(_QWORD *)(a1 + 2996) = 0;
    *(_DWORD *)(a1 + 3004) = 0;
    return QuicSendSetSendFlag(a1 + 3416, 2);
  }
}

```

## disassembly

```asm
0x140043368  mov     [rsp+arg_10], rbx
0x14004336d  mov     [rsp+arg_18], rsi
0x140043372  push    rdi
0x140043373  sub     rsp, 140h
0x14004337a  mov     rax, cs:__security_cookie
0x140043381  xor     rax, rsp
0x140043384  mov     [rsp+148h+var_18], rax
0x14004338c  test    byte ptr [rcx+0F8h], 4
0x140043393  mov     rbx, rcx
0x140043396  movzx   edi, dl
0x140043399  jnz     short loc_1400433B3
0x14004339b  lea     r8, aConnectionStat_4; "Connection->State.Started"
0x1400433a2  mov     edx, 7D2h
0x1400433a7  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x1400433ae  call    CxPlatLogAssert
0x1400433b3  mov     edx, 80h; SizeInBytes
0x1400433b8  test    cs:byte_14005C48B, dl
0x1400433be  jz      short loc_1400433F4
0x1400433c0  lea     r9, aRestartComplet; "Restart (CompleteReset=%hhu)"
0x1400433c7  mov     [rsp+148h+var_128], edi
0x1400433cb  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400433cf  lea     rcx, [rsp+148h+DstBuf]; DstBuf
0x1400433d4  call    cs:__imp__snprintf_s
0x1400433db  nop     dword ptr [rax+rax+00h]
0x1400433e0  lea     r9, [rsp+148h+DstBuf]
0x1400433e5  mov     r8, rbx
0x1400433e8  lea     rdx, QuicConnLogInfo
0x1400433ef  call    McTemplateU0ps_EtwWriteTransfer
0x1400433f4  xor     esi, esi
0x1400433f6  test    dil, dil
0x1400433f9  jz      short loc_14004341D
0x1400433fb  and     byte ptr [rbx+141h], 0F7h
0x140043402  imul    ecx, [rbx+0C0h], 3E8h
0x14004340c  mov     [rbx+1D8h], rcx
0x140043413  shr     rcx, 1
0x140043416  mov     [rbx+1F8h], rcx
0x14004341d  lea     rcx, [rbx+0AC8h]
0x140043424  mov     edx, 3
0x140043429  mov     rax, [rcx]
0x14004342c  xor     r8d, r8d
0x14004342f  xorps   xmm0, xmm0
0x140043432  lea     rcx, [rcx+8]
0x140043436  and     byte ptr [rax+18Ah], 0FCh
0x14004343d  mov     [rax+188h], si
0x140043444  mov     [rax+178h], rsi
0x14004344b  mov     [rax+180h], rsi
0x140043452  movups  xmmword ptr [rax+160h], xmm0
0x140043459  mov     [rax+170h], r8
0x140043460  mov     [rax+0D0h], esi
0x140043466  mov     [rax+38h], esi
0x140043469  sub     rdx, 1
0x14004346d  jnz     short loc_140043429
0x14004346f  lea     rcx, [rbx+878h]
0x140043476  mov     dl, 1
0x140043478  mov     rax, [rcx+18h]
0x14004347c  call    _guard_dispatch_icall
0x140043481  test    byte ptr [rbx+0D58h], 2
0x140043488  mov     [rbx+0DA0h], esi
0x14004348e  mov     [rbx+0D68h], rsi
0x140043495  jz      short loc_1400434AB
0x140043497  mov     edx, 1
0x14004349c  mov     rcx, rbx
0x14004349f  call    QuicConnTimerCancel
0x1400434a4  and     byte ptr [rbx+0D58h], 0FDh
0x1400434ab  xor     edx, edx
0x1400434ad  mov     rcx, rbx
0x1400434b0  call    QuicConnTimerCancel
0x1400434b5  lea     rcx, [rbx+0A48h]
0x1400434bc  call    QuicLossDetectionReset
0x1400434c1  lea     rcx, [rbx+658h]
0x1400434c8  call    QuicCryptoTlsCleanupTransportParameters
0x1400434cd  test    dil, dil
0x1400434d0  jz      short loc_140043545
0x1400434d2  xor     edx, edx; Val
0x1400434d4  lea     rcx, [rsp+148h+DstBuf]; void *
0x1400434d9  mov     r8d, 100h; Size
0x1400434df  call    memset
0x1400434e4  lea     rdx, [rsp+148h+DstBuf]
0x1400434e9  mov     rcx, rbx
0x1400434ec  call    QuicConnGenerateLocalTransportParameters
0x1400434f1  test    eax, eax
0x1400434f3  jns     short loc_14004350F
0x1400434f5  lea     r8, aNtstatusStatus; "(((NTSTATUS)(Status)) >= 0)"
0x1400434fc  mov     edx, 7F4h
0x140043501  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x140043508  call    CxPlatLogAssert
0x14004350d  int     2Ch; Windows NT - assertion failure
0x14004350f  mov     rdx, [rbx+58h]
0x140043513  lea     rcx, [rbx+0AE0h]
0x14004351a  lea     r8, [rsp+148h+DstBuf]
0x14004351f  mov     rdx, [rdx+30h]
0x140043523  call    QuicCryptoInitializeTls
0x140043528  test    eax, eax
0x14004352a  jns     short loc_140043539
0x14004352c  xor     r8d, r8d
0x14004352f  mov     edx, eax
0x140043531  mov     rcx, rbx
0x140043534  call    QuicConnFatalError
0x140043539  lea     rcx, [rsp+148h+DstBuf]
0x14004353e  call    QuicCryptoTlsCleanupTransportParameters
0x140043543  jmp     short loc_140043591
0x140043545  cmp     [rbx+0C58h], esi
0x14004354b  jz      short loc_140043565
0x14004354d  lea     r8, aCryptoRecvtota; "Crypto->RecvTotalConsumed == 0"
0x140043554  mov     edx, 170h
0x140043559  lea     rcx, aCW1SMsquicSrcC_15; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x140043560  call    CxPlatLogAssert
0x140043565  and     byte ptr [rbx+0AE0h], 0FDh
0x14004356c  lea     rcx, [rbx+0D58h]
0x140043573  mov     edx, 2
0x140043578  mov     [rbx+0BACh], rsi
0x14004357f  mov     [rbx+0BB4h], rsi
0x140043586  mov     [rbx+0BBCh], esi
0x14004358c  call    QuicSendSetSendFlag
0x140043591  mov     rcx, [rsp+148h+var_18]
0x140043599  xor     rcx, rsp; StackCookie
0x14004359c  call    __security_check_cookie
0x1400435a1  lea     r11, [rsp+148h+var_8]
0x1400435a9  mov     rbx, [r11+20h]
0x1400435ad  mov     rsi, [r11+28h]
0x1400435b1  mov     rsp, r11
0x1400435b4  pop     rdi
0x1400435b5  retn
```
