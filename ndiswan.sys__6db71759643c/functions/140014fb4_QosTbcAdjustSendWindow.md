# QosTbcAdjustSendWindow

- ea: `0x140014fb4`
- end: `0x1400151ef`
- name: `QosTbcAdjustSendWindow`
- size: `571`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002974`
- `0x140012570`
- `0x140013080`
- `0x140013570`

## callees

- `0x14000a23c`
- `0x140014fb4`
- `0x1400151f8`
- `0x140015e90`
- `0x1400161f0`
- `0x140016700`

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
0x140014fb4  mov     [rsp-28h+arg_10], rbx
0x140014fb9  push    rbp
0x140014fba  push    rsi
0x140014fbb  push    rdi
0x140014fbc  push    r14
0x140014fbe  push    r15
0x140014fc0  mov     rbp, rsp
0x140014fc3  sub     rsp, 80h
0x140014fca  mov     rax, cs:__security_cookie
0x140014fd1  xor     rax, rsp
0x140014fd4  mov     [rbp+var_10], rax
0x140014fd8  mov     r14, rdx
0x140014fdb  mov     rbx, rcx
0x140014fde  xor     edx, edx; Val
0x140014fe0  lea     rcx, [rbp+var_60]; void *
0x140014fe4  lea     r8d, [rdx+50h]; Size
0x140014fe8  call    memset
0x140014fed  and     dword ptr [rbx+1A0h], 0FFFFFFFEh
0x140014ff4  mov     ecx, [rbx+140h]
0x140014ffa  mov     edi, [r14+0Ch]
0x140014ffe  cmp     edi, ecx
0x140015000  mov     eax, [r14+14h]
0x140015004  cmovbe  edi, ecx
0x140015007  mov     r15d, edi
0x14001500a  cmp     [rbx+150h], eax
0x140015010  jz      short loc_14001503E
0x140015012  mov     edx, 64h ; 'd'
0x140015017  cmp     eax, edx
0x140015019  cmovb   eax, edx
0x14001501c  mov     [rbx+150h], eax
0x140015022  mov     eax, [r14+8]
0x140015026  imul    rax, rcx
0x14001502a  mov     rcx, rbx
0x14001502d  cqo
0x14001502f  idiv    r15
0x140015032  mov     [rbx+120h], rax
0x140015039  call    QosTbcTuneParameters
0x14001503e  cmp     [rbx+144h], edi
0x140015044  jz      short loc_140015054
0x140015046  mov     rcx, rbx
0x140015049  mov     [rbx+144h], edi
0x14001504f  call    QosTbcTuneParameters
0x140015054  mov     ecx, [r14+10h]
0x140015058  cmp     [rbx+148h], ecx
0x14001505e  jz      short loc_140015079
0x140015060  mov     eax, [rbx+140h]
0x140015066  cmp     eax, ecx
0x140015068  cmovbe  eax, ecx
0x14001506b  mov     rcx, rbx
0x14001506e  mov     [rbx+148h], eax
0x140015074  call    QosTbcTuneParameters
0x140015079  mov     rcx, [r14+18h]
0x14001507d  mov     rax, 7FFFFFFFFFFFFFFFh
0x140015087  xor     edi, edi
0x140015089  cmp     rcx, rax
0x14001508c  jnz     short loc_14001509B
0x14001508e  mov     [rbx+140h], edi
0x140015094  mov     esi, edi
0x140015096  mov     r8d, edi
0x140015099  jmp     short loc_1400150D3
0x14001509b  mov     r8d, [rbx+140h]
0x1400150a2  mov     eax, r8d
0x1400150a5  imul    rax, rcx
0x1400150a9  cqo
0x1400150ab  idiv    r15
0x1400150ae  mov     rsi, rax
0x1400150b1  mov     rax, [r14+20h]
0x1400150b5  test    rax, rax
0x1400150b8  jle     short loc_1400150C1
0x1400150ba  cmp     rsi, rax
0x1400150bd  cmovge  rsi, rax
0x1400150c1  mov     eax, [rbx+174h]
0x1400150c7  test    eax, eax
0x1400150c9  jz      short loc_1400150D3
0x1400150cb  dec     eax
0x1400150cd  mov     [rbx+174h], eax
0x1400150d3  mov     rax, cs:QosgEtwDispatchTable
0x1400150da  mov     rcx, [rax]
0x1400150dd  cmp     dword ptr [rcx], 1
0x1400150e0  jnz     loc_140015196
0x1400150e6  mov     eax, [rbx+150h]
0x1400150ec  xor     edx, edx
0x1400150ee  mov     rcx, [rbx+110h]
0x1400150f5  sub     rcx, rax
0x1400150f8  mov     [rbp+var_50], rbx
0x1400150fc  mov     eax, [rbx+128h]
0x140015102  mov     [rbp+var_48], eax
0x140015105  mov     eax, [rbx+12Ch]
0x14001510b  mov     [rbp+var_44], eax
0x14001510e  mov     eax, r8d
0x140015111  imul    eax, [r14+8]
0x140015116  mov     [rbp+var_60], rcx
0x14001511a  mov     rcx, rbx
0x14001511d  mov     [rbp+var_40], esi
0x140015120  mov     [rbp+var_38], r8d
0x140015124  div     r15
0x140015127  mov     [rbp+var_3C], eax
0x14001512a  mov     eax, [rbx+158h]
0x140015130  mov     [rbp+var_30], rax
0x140015134  call    QosTbcComputeDropRate
0x140015139  mov     ecx, [rbx+19Ch]
0x14001513f  mov     [rbp+var_28], eax
0x140015142  mov     rax, [rbx+180h]
0x140015149  mov     [rbp+var_58], rax
0x14001514d  mov     eax, [rbx+1A0h]
0x140015153  mov     [rbp+var_1C], ecx
0x140015156  test    al, 8
0x140015158  jz      short loc_140015177
0x14001515a  mov     eax, [rbx+188h]
0x140015160  mov     dword ptr [rbp+var_24], eax
0x140015163  mov     eax, [rbx+194h]
0x140015169  mov     dword ptr [rbp+var_24+4], eax
0x14001516c  mov     eax, [rbx+190h]
0x140015172  mov     [rbp+var_18], eax
0x140015175  jmp     short loc_140015182
0x140015177  mov     [rbp+var_24], 0
0x14001517f  mov     [rbp+var_18], edi
0x140015182  mov     eax, [rbx+15Ch]
0x140015188  lea     rdx, [rbp+var_60]
0x14001518c  xor     ecx, ecx
0x14001518e  mov     [rbp+var_14], eax
0x140015191  call    QosTraceEvent
0x140015196  movq    xmm1, qword ptr [rbx+128h]
0x14001519e  xorps   xmm0, xmm0
0x1400151a1  punpckldq xmm1, xmm0
0x1400151a5  movdqu  xmm0, xmmword ptr [rbx+130h]
0x1400151ad  mov     qword ptr [rbx+128h], 0
0x1400151b8  mov     [rbx+118h], rsi
0x1400151bf  paddq   xmm1, xmm0
0x1400151c3  movdqu  xmmword ptr [rbx+130h], xmm1
0x1400151cb  mov     rcx, [rbp+var_10]
0x1400151cf  xor     rcx, rsp; StackCookie
0x1400151d2  call    __security_check_cookie
0x1400151d7  mov     rbx, [rsp+80h+arg_10]
0x1400151df  add     rsp, 80h
0x1400151e6  pop     r15
0x1400151e8  pop     r14
0x1400151ea  pop     rdi
0x1400151eb  pop     rsi
0x1400151ec  pop     rbp
0x1400151ed  retn
```
