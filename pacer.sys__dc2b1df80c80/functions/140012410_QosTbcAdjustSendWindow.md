# QosTbcAdjustSendWindow

- ea: `0x140012410`
- end: `0x14001264b`
- name: `QosTbcAdjustSendWindow`
- size: `571`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003ab0`
- `0x140005c10`
- `0x140007f90`
- `0x1400085c0`
- `0x14000cce0`

## callees

- `0x14000b404`
- `0x14000c42c`
- `0x140012410`
- `0x140012654`
- `0x140013110`
- `0x140013600`

## pseudocode

```c
__int64 __fastcall QosTbcAdjustSendWindow(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  unsigned int v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rsi
  unsigned int v11; // r8d
  __int64 v12; // rax
  int v13; // eax
  __int64 result; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  __m128i v20; // xmm1
  __m128i v21; // xmm0
  _QWORD v22[10]; // [rsp+20h] [rbp-60h] BYREF

  memset(v22, 0, sizeof(v22));
  *(_DWORD *)(a1 + 416) &= ~1u;
  v4 = *(unsigned int *)(a1 + 320);
  v5 = *(_DWORD *)(a2 + 12);
  v6 = *(_DWORD *)(a2 + 20);
  if ( v5 <= (unsigned int)v4 )
    v5 = *(_DWORD *)(a1 + 320);
  if ( *(_DWORD *)(a1 + 336) != v6 )
  {
    if ( v6 < 0x64 )
      v6 = 100;
    *(_DWORD *)(a1 + 336) = v6;
    *(_QWORD *)(a1 + 288) = v4 * *(unsigned int *)(a2 + 8) / v5;
    QosTbcTuneParameters(a1);
  }
  if ( *(_DWORD *)(a1 + 324) != v5 )
  {
    *(_DWORD *)(a1 + 324) = v5;
    QosTbcTuneParameters(a1);
  }
  v7 = *(_DWORD *)(a2 + 16);
  if ( *(_DWORD *)(a1 + 328) != v7 )
  {
    v8 = *(_DWORD *)(a1 + 320);
    if ( v8 <= v7 )
      v8 = *(_DWORD *)(a2 + 16);
    *(_DWORD *)(a1 + 328) = v8;
    QosTbcTuneParameters(a1);
  }
  v9 = *(_QWORD *)(a2 + 24);
  if ( v9 == 0x7FFFFFFFFFFFFFFFLL )
  {
    *(_DWORD *)(a1 + 320) = 0;
    v10 = 0;
    v11 = 0;
  }
  else
  {
    v11 = *(_DWORD *)(a1 + 320);
    v10 = v9 * v11 / v5;
    v12 = *(_QWORD *)(a2 + 32);
    if ( v12 > 0 && v10 >= v12 )
      v10 = *(_QWORD *)(a2 + 32);
    v13 = *(_DWORD *)(a1 + 372);
    if ( v13 )
      *(_DWORD *)(a1 + 372) = v13 - 1;
  }
  result = QosgEtwDispatchTable;
  if ( **(_DWORD **)QosgEtwDispatchTable == 1 )
  {
    v15 = *(_QWORD *)(a1 + 272) - *(unsigned int *)(a1 + 336);
    v22[2] = a1;
    v22[3] = *(_QWORD *)(a1 + 296);
    v16 = *(_DWORD *)(a2 + 8) * v11;
    v22[0] = v15;
    LODWORD(v22[4]) = v10;
    LODWORD(v22[5]) = v11;
    HIDWORD(v22[4]) = v16 / v5;
    v22[6] = *(unsigned int *)(a1 + 344);
    v17 = QosTbcComputeDropRate(a1);
    v18 = *(_DWORD *)(a1 + 412);
    LODWORD(v22[7]) = v17;
    v22[1] = *(_QWORD *)(a1 + 384);
    v19 = *(_DWORD *)(a1 + 416);
    HIDWORD(v22[8]) = v18;
    if ( (v19 & 8) != 0 )
    {
      HIDWORD(v22[7]) = *(_DWORD *)(a1 + 392);
      LODWORD(v22[8]) = *(_DWORD *)(a1 + 404);
      LODWORD(v22[9]) = *(_DWORD *)(a1 + 400);
    }
    else
    {
      *(_QWORD *)((char *)&v22[7] + 4) = 0;
      LODWORD(v22[9]) = 0;
    }
    HIDWORD(v22[9]) = *(_DWORD *)(a1 + 348);
    result = QosTraceEvent(0, v22);
  }
  v20 = _mm_unpacklo_epi32(_mm_loadl_epi64((const __m128i *)(a1 + 296)), (__m128i)0LL);
  v21 = _mm_loadu_si128((const __m128i *)(a1 + 304));
  *(_QWORD *)(a1 + 296) = 0;
  *(_QWORD *)(a1 + 280) = v10;
  *(__m128i *)(a1 + 304) = _mm_add_epi64(v20, v21);
  return result;
}

```

## disassembly

```asm
0x140012410  mov     [rsp-28h+arg_10], rbx
0x140012415  push    rbp
0x140012416  push    rsi
0x140012417  push    rdi
0x140012418  push    r14
0x14001241a  push    r15
0x14001241c  mov     rbp, rsp
0x14001241f  sub     rsp, 80h
0x140012426  mov     rax, cs:__security_cookie
0x14001242d  xor     rax, rsp
0x140012430  mov     [rbp+var_10], rax
0x140012434  mov     r14, rdx
0x140012437  mov     rbx, rcx
0x14001243a  xor     edx, edx; Val
0x14001243c  lea     rcx, [rbp+var_60]; void *
0x140012440  lea     r8d, [rdx+50h]; Size
0x140012444  call    memset
0x140012449  and     dword ptr [rbx+1A0h], 0FFFFFFFEh
0x140012450  mov     ecx, [rbx+140h]
0x140012456  mov     edi, [r14+0Ch]
0x14001245a  cmp     edi, ecx
0x14001245c  mov     eax, [r14+14h]
0x140012460  cmovbe  edi, ecx
0x140012463  mov     r15d, edi
0x140012466  cmp     [rbx+150h], eax
0x14001246c  jz      short loc_14001249A
0x14001246e  mov     edx, 64h ; 'd'
0x140012473  cmp     eax, edx
0x140012475  cmovb   eax, edx
0x140012478  mov     [rbx+150h], eax
0x14001247e  mov     eax, [r14+8]
0x140012482  imul    rax, rcx
0x140012486  mov     rcx, rbx
0x140012489  cqo
0x14001248b  idiv    r15
0x14001248e  mov     [rbx+120h], rax
0x140012495  call    QosTbcTuneParameters
0x14001249a  cmp     [rbx+144h], edi
0x1400124a0  jz      short loc_1400124B0
0x1400124a2  mov     rcx, rbx
0x1400124a5  mov     [rbx+144h], edi
0x1400124ab  call    QosTbcTuneParameters
0x1400124b0  mov     ecx, [r14+10h]
0x1400124b4  cmp     [rbx+148h], ecx
0x1400124ba  jz      short loc_1400124D5
0x1400124bc  mov     eax, [rbx+140h]
0x1400124c2  cmp     eax, ecx
0x1400124c4  cmovbe  eax, ecx
0x1400124c7  mov     rcx, rbx
0x1400124ca  mov     [rbx+148h], eax
0x1400124d0  call    QosTbcTuneParameters
0x1400124d5  mov     rcx, [r14+18h]
0x1400124d9  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400124e3  xor     edi, edi
0x1400124e5  cmp     rcx, rax
0x1400124e8  jnz     short loc_1400124F7
0x1400124ea  mov     [rbx+140h], edi
0x1400124f0  mov     esi, edi
0x1400124f2  mov     r8d, edi
0x1400124f5  jmp     short loc_14001252F
0x1400124f7  mov     r8d, [rbx+140h]
0x1400124fe  mov     eax, r8d
0x140012501  imul    rax, rcx
0x140012505  cqo
0x140012507  idiv    r15
0x14001250a  mov     rsi, rax
0x14001250d  mov     rax, [r14+20h]
0x140012511  test    rax, rax
0x140012514  jle     short loc_14001251D
0x140012516  cmp     rsi, rax
0x140012519  cmovge  rsi, rax
0x14001251d  mov     eax, [rbx+174h]
0x140012523  test    eax, eax
0x140012525  jz      short loc_14001252F
0x140012527  dec     eax
0x140012529  mov     [rbx+174h], eax
0x14001252f  mov     rax, cs:QosgEtwDispatchTable
0x140012536  mov     rcx, [rax]
0x140012539  cmp     dword ptr [rcx], 1
0x14001253c  jnz     loc_1400125F2
0x140012542  mov     eax, [rbx+150h]
0x140012548  xor     edx, edx
0x14001254a  mov     rcx, [rbx+110h]
0x140012551  sub     rcx, rax
0x140012554  mov     [rbp+var_50], rbx
0x140012558  mov     eax, [rbx+128h]
0x14001255e  mov     [rbp+var_48], eax
0x140012561  mov     eax, [rbx+12Ch]
0x140012567  mov     [rbp+var_44], eax
0x14001256a  mov     eax, r8d
0x14001256d  imul    eax, [r14+8]
0x140012572  mov     [rbp+var_60], rcx
0x140012576  mov     rcx, rbx
0x140012579  mov     [rbp+var_40], esi
0x14001257c  mov     [rbp+var_38], r8d
0x140012580  div     r15
0x140012583  mov     [rbp+var_3C], eax
0x140012586  mov     eax, [rbx+158h]
0x14001258c  mov     [rbp+var_30], rax
0x140012590  call    QosTbcComputeDropRate
0x140012595  mov     ecx, [rbx+19Ch]
0x14001259b  mov     [rbp+var_28], eax
0x14001259e  mov     rax, [rbx+180h]
0x1400125a5  mov     [rbp+var_58], rax
0x1400125a9  mov     eax, [rbx+1A0h]
0x1400125af  mov     [rbp+var_1C], ecx
0x1400125b2  test    al, 8
0x1400125b4  jz      short loc_1400125D3
0x1400125b6  mov     eax, [rbx+188h]
0x1400125bc  mov     dword ptr [rbp+var_24], eax
0x1400125bf  mov     eax, [rbx+194h]
0x1400125c5  mov     dword ptr [rbp+var_24+4], eax
0x1400125c8  mov     eax, [rbx+190h]
0x1400125ce  mov     [rbp+var_18], eax
0x1400125d1  jmp     short loc_1400125DE
0x1400125d3  mov     [rbp+var_24], 0
0x1400125db  mov     [rbp+var_18], edi
0x1400125de  mov     eax, [rbx+15Ch]
0x1400125e4  lea     rdx, [rbp+var_60]
0x1400125e8  xor     ecx, ecx
0x1400125ea  mov     [rbp+var_14], eax
0x1400125ed  call    QosTraceEvent
0x1400125f2  movq    xmm1, qword ptr [rbx+128h]
0x1400125fa  xorps   xmm0, xmm0
0x1400125fd  punpckldq xmm1, xmm0
0x140012601  movdqu  xmm0, xmmword ptr [rbx+130h]
0x140012609  mov     qword ptr [rbx+128h], 0
0x140012614  mov     [rbx+118h], rsi
0x14001261b  paddq   xmm1, xmm0
0x14001261f  movdqu  xmmword ptr [rbx+130h], xmm1
0x140012627  mov     rcx, [rbp+var_10]
0x14001262b  xor     rcx, rsp; StackCookie
0x14001262e  call    __security_check_cookie
0x140012633  mov     rbx, [rsp+80h+arg_10]
0x14001263b  add     rsp, 80h
0x140012642  pop     r15
0x140012644  pop     r14
0x140012646  pop     rdi
0x140012647  pop     rsi
0x140012648  pop     rbp
0x140012649  retn
```
