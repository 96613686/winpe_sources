# CreateIniTxFilter

- ea: `0x1800066a0`
- end: `0x180006a02`
- name: `CreateIniTxFilter`
- size: `866`
- prototype: `__int64 __fastcall(int *, __int128 *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001e9f0`

## callees

- `0x1800066a0`
- `0x180006f00`
- `0x18000b1d0`
- `0x18000e510`
- `0x180019e74`
- `0x18001e21c`
- `0x180042ef8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800066dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800066dd`

## pseudocode

```c
__int64 __fastcall CreateIniTxFilter(int *a1, __int128 *a2, _QWORD *a3)
{
  char *v6; // rbx
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // r12
  _QWORD *v11; // r13
  __int128 v12; // xmm0
  unsigned __int16 *v13; // r15
  __int64 v14; // rcx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // r11
  int v17; // ecx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  __int128 v29; // xmm0
  __int64 result; // rax
  unsigned __int64 v31; // [rsp+98h] [rbp+20h] BYREF

  if ( g_Mem_lModuleInitCount <= 0 )
  {
    v6 = 0;
    goto LABEL_4;
  }
  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 8u, 0xE0u);
  v6 = v8;
  if ( !v8 )
  {
LABEL_4:
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, 8);
      v9 = WPP_GLOBAL_Control;
    }
    v10 = (__int64)(a1 + 1);
    v11 = a1 + 6;
    goto LABEL_47;
  }
  *(_QWORD *)(v8 + 156) = 0;
  v10 = (__int64)(a1 + 1);
  *((_DWORD *)v8 + 41) = 0;
  v11 = a1 + 6;
  *(_DWORD *)v8 = *a1;
  v12 = *(_OWORD *)(a1 + 1);
  v31 = 0;
  *(_OWORD *)(v8 + 4) = v12;
  v13 = (unsigned __int16 *)*((_QWORD *)a1 + 3);
  if ( !v13 )
    goto LABEL_43;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  if ( (unsigned int)NsuSizeTMultiply(v14 + 1, 2, &v31)
    || (v15 = (unsigned __int16 *)IpsecAllocMem(v31), (v16 = v15) != 0)
    && (unsigned __int16)StringCchCopyW(v15, v31 >> 1, v13) )
  {
LABEL_43:
    *((_QWORD *)v6 + 3) = 0;
    goto LABEL_44;
  }
  *((_QWORD *)v6 + 3) = v16;
  if ( !v16 )
  {
LABEL_44:
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_50:
      if ( v6 )
        FreeIniTxFilter(v6);
      *a3 = 0;
      return 8;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, 8);
      v9 = WPP_GLOBAL_Control;
    }
LABEL_47:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
      WPP_SF_S_guid_D(v9[2], 45, (unsigned int)WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, *v11, v10, 8);
    goto LABEL_50;
  }
  *((_DWORD *)v6 + 8) = a1[8];
  *((_DWORD *)v6 + 9) = a1[9];
  *((_DWORD *)v6 + 10) = a1[10];
  v17 = *a1;
  *(_OWORD *)(v6 + 44) = 0;
  *(_OWORD *)(v6 + 60) = 0;
  *(_QWORD *)(v6 + 76) = 0;
  *((_DWORD *)v6 + 12) = v17;
  *((_DWORD *)v6 + 11) = a1[12];
  v18 = a1[12];
  if ( v17 == 1 )
  {
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        if ( v20 == 8 )
        {
          *(_OWORD *)(v6 + 52) = *(_OWORD *)(a1 + 14);
          *(_OWORD *)(v6 + 68) = *(_OWORD *)(a1 + 18);
        }
      }
      else
      {
        *(_OWORD *)(v6 + 52) = *(_OWORD *)(a1 + 14);
        v6[68] = *((_BYTE *)a1 + 72);
      }
    }
    else
    {
      *(_OWORD *)(v6 + 52) = *(_OWORD *)(a1 + 14);
    }
  }
  else
  {
    v21 = v18 - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( !v22 || v22 == 8 )
      {
        *((_DWORD *)v6 + 13) = a1[14];
        *((_DWORD *)v6 + 14) = a1[15];
      }
    }
    else
    {
      *((_DWORD *)v6 + 13) = a1[14];
    }
  }
  v23 = *a1;
  *(_OWORD *)(v6 + 84) = 0;
  *(_OWORD *)(v6 + 100) = 0;
  *(_QWORD *)(v6 + 116) = 0;
  *((_DWORD *)v6 + 22) = v23;
  *((_DWORD *)v6 + 21) = a1[22];
  v24 = a1[22];
  if ( v23 == 1 )
  {
    v25 = v24 - 1;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        if ( v26 == 8 )
        {
          *(_OWORD *)(v6 + 92) = *((_OWORD *)a1 + 6);
          *(_OWORD *)(v6 + 108) = *((_OWORD *)a1 + 7);
        }
      }
      else
      {
        *(_OWORD *)(v6 + 92) = *((_OWORD *)a1 + 6);
        v6[108] = *((_BYTE *)a1 + 112);
      }
    }
    else
    {
      *(_OWORD *)(v6 + 92) = *((_OWORD *)a1 + 6);
    }
  }
  else
  {
    v27 = v24 - 1;
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( !v28 || v28 == 8 )
      {
        *((_DWORD *)v6 + 23) = a1[24];
        *((_DWORD *)v6 + 24) = a1[25];
      }
    }
    else
    {
      *((_DWORD *)v6 + 23) = a1[24];
    }
  }
  *(_QWORD *)(v6 + 132) = *((_QWORD *)a1 + 17);
  *(_QWORD *)(v6 + 140) = *((_QWORD *)a1 + 18);
  *(_QWORD *)(v6 + 124) = *((_QWORD *)a1 + 16);
  *((_DWORD *)v6 + 37) = a1[38];
  *((_DWORD *)v6 + 38) = a1[39];
  if ( a2 )
    v29 = *a2;
  else
    v29 = *(_OWORD *)(a1 + 42);
  *(_OWORD *)(v6 + 168) = v29;
  *((_QWORD *)v6 + 23) = 0;
  result = 0;
  *((_DWORD *)v6 + 48) = 0;
  *((_QWORD *)v6 + 25) = 0;
  *((_QWORD *)v6 + 27) = 0;
  *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x1800066a0  push    rbx
0x1800066a2  push    rbp
0x1800066a3  push    rsi
0x1800066a4  push    rdi
0x1800066a5  push    r12
0x1800066a7  push    r13
0x1800066a9  push    r14
0x1800066ab  push    r15
0x1800066ad  sub     rsp, 38h
0x1800066b1  cmp     cs:?g_Mem_lModuleInitCount@@3JA, 0; long g_Mem_lModuleInitCount
0x1800066b8  mov     r14, r8
0x1800066bb  mov     rbp, rdx
0x1800066be  mov     rdi, rcx
0x1800066c1  jg      short loc_1800066C9
0x1800066c3  xor     esi, esi
0x1800066c5  mov     ebx, esi
0x1800066c7  jmp     short loc_1800066ED
0x1800066c9  call    cs:__imp_GetProcessHeap
0x1800066cf  mov     edx, 8; dwFlags
0x1800066d4  mov     r8d, 0E0h; dwBytes
0x1800066da  mov     rcx, rax; hHeap
0x1800066dd  call    cs:__imp_HeapAlloc
0x1800066e3  xor     esi, esi
0x1800066e5  mov     rbx, rax
0x1800066e8  test    rax, rax
0x1800066eb  jnz     short loc_180006735
0x1800066ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066f4  lea     rbp, WPP_GLOBAL_Control
0x1800066fb  cmp     rcx, rbp
0x1800066fe  jz      short loc_180006728
0x180006700  test    byte ptr [rcx+1Ch], 10h
0x180006704  jz      short loc_180006728
0x180006706  mov     rcx, [rcx+10h]
0x18000670a  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x180006711  mov     edx, 2Bh ; '+'
0x180006716  mov     r9d, 8
0x18000671c  call    WPP_SF_d
0x180006721  mov     rcx, cs:WPP_GLOBAL_Control
0x180006728  lea     r12, [rdi+4]
0x18000672c  lea     r13, [rdi+18h]
0x180006730  jmp     loc_1800069AB
0x180006735  mov     [rax+9Ch], rsi
0x18000673c  lea     r12, [rdi+4]
0x180006740  mov     [rax+0A4h], esi
0x180006746  lea     r13, [rdi+18h]
0x18000674a  mov     eax, [rdi]
0x18000674c  mov     [rbx], eax
0x18000674e  movups  xmm0, xmmword ptr [r12]
0x180006753  mov     [rsp+78h+arg_18], rsi
0x18000675b  movups  xmmword ptr [rbx+4], xmm0
0x18000675f  mov     r15, [r13+0]
0x180006763  test    r15, r15
0x180006766  jz      loc_18000696C
0x18000676c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006773  inc     rcx
0x180006776  cmp     [r15+rcx*2], si
0x18000677b  jnz     short loc_180006773
0x18000677d  inc     rcx
0x180006780  lea     r8, [rsp+78h+arg_18]
0x180006788  mov     edx, 2
0x18000678d  call    NsuSizeTMultiply
0x180006792  test    eax, eax
0x180006794  jnz     loc_18000696C
0x18000679a  mov     rcx, [rsp+78h+arg_18]
0x1800067a2  call    IpsecAllocMem
0x1800067a7  mov     r11, rax
0x1800067aa  test    rax, rax
0x1800067ad  jz      short loc_1800067CE
0x1800067af  mov     rdx, [rsp+78h+arg_18]
0x1800067b7  mov     r8, r15; unsigned __int16 *
0x1800067ba  shr     rdx, 1; unsigned __int64
0x1800067bd  mov     rcx, rax; unsigned __int16 *
0x1800067c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800067c5  test    ax, ax
0x1800067c8  jnz     loc_18000696C
0x1800067ce  mov     [rbx+18h], r11
0x1800067d2  test    r11, r11
0x1800067d5  jz      loc_180006970
0x1800067db  mov     eax, [rdi+20h]
0x1800067de  xorps   xmm0, xmm0
0x1800067e1  mov     [rbx+20h], eax
0x1800067e4  mov     eax, [rdi+24h]
0x1800067e7  mov     [rbx+24h], eax
0x1800067ea  mov     eax, [rdi+28h]
0x1800067ed  mov     [rbx+28h], eax
0x1800067f0  xor     eax, eax
0x1800067f2  mov     ecx, [rdi]
0x1800067f4  movups  xmmword ptr [rbx+2Ch], xmm0
0x1800067f8  movups  xmmword ptr [rbx+3Ch], xmm0
0x1800067fc  mov     [rbx+4Ch], rax
0x180006800  mov     [rbx+30h], ecx
0x180006803  mov     eax, [rdi+30h]
0x180006806  mov     [rbx+2Ch], eax
0x180006809  mov     edx, [rdi+30h]
0x18000680c  cmp     ecx, 1
0x18000680f  jnz     short loc_18000684B
0x180006811  sub     edx, ecx
0x180006813  jz      short loc_180006841
0x180006815  sub     edx, ecx
0x180006817  jz      short loc_180006830
0x180006819  cmp     edx, 8
0x18000681c  jnz     short loc_18000686E
0x18000681e  movups  xmm0, xmmword ptr [rdi+38h]
0x180006822  movups  xmmword ptr [rbx+34h], xmm0
0x180006826  movups  xmm0, xmmword ptr [rdi+48h]
0x18000682a  movups  xmmword ptr [rbx+44h], xmm0
0x18000682e  jmp     short loc_18000686E
0x180006830  movups  xmm0, xmmword ptr [rdi+38h]
0x180006834  movups  xmmword ptr [rbx+34h], xmm0
0x180006838  movzx   eax, byte ptr [rdi+48h]
0x18000683c  mov     [rbx+44h], al
0x18000683f  jmp     short loc_18000686E
0x180006841  movups  xmm0, xmmword ptr [rdi+38h]
0x180006845  movups  xmmword ptr [rbx+34h], xmm0
0x180006849  jmp     short loc_18000686E
0x18000684b  sub     edx, 1
0x18000684e  jz      short loc_180006868
0x180006850  sub     edx, 1
0x180006853  jz      short loc_18000685A
0x180006855  cmp     edx, 8
0x180006858  jnz     short loc_18000686E
0x18000685a  mov     eax, [rdi+38h]
0x18000685d  mov     [rbx+34h], eax
0x180006860  mov     eax, [rdi+3Ch]
0x180006863  mov     [rbx+38h], eax
0x180006866  jmp     short loc_18000686E
0x180006868  mov     eax, [rdi+38h]
0x18000686b  mov     [rbx+34h], eax
0x18000686e  mov     ecx, [rdi]
0x180006870  xor     eax, eax
0x180006872  xorps   xmm0, xmm0
0x180006875  movups  xmmword ptr [rbx+54h], xmm0
0x180006879  movups  xmmword ptr [rbx+64h], xmm0
0x18000687d  mov     [rbx+74h], rax
0x180006881  mov     [rbx+58h], ecx
0x180006884  mov     eax, [rdi+58h]
0x180006887  mov     [rbx+54h], eax
0x18000688a  mov     edx, [rdi+58h]
0x18000688d  cmp     ecx, 1
0x180006890  jnz     short loc_1800068CC
0x180006892  sub     edx, ecx
0x180006894  jz      short loc_1800068C2
0x180006896  sub     edx, ecx
0x180006898  jz      short loc_1800068B1
0x18000689a  cmp     edx, 8
0x18000689d  jnz     short loc_1800068EF
0x18000689f  movups  xmm0, xmmword ptr [rdi+60h]
0x1800068a3  movups  xmmword ptr [rbx+5Ch], xmm0
0x1800068a7  movups  xmm0, xmmword ptr [rdi+70h]
0x1800068ab  movups  xmmword ptr [rbx+6Ch], xmm0
0x1800068af  jmp     short loc_1800068EF
0x1800068b1  movups  xmm0, xmmword ptr [rdi+60h]
0x1800068b5  movups  xmmword ptr [rbx+5Ch], xmm0
0x1800068b9  movzx   eax, byte ptr [rdi+70h]
0x1800068bd  mov     [rbx+6Ch], al
0x1800068c0  jmp     short loc_1800068EF
0x1800068c2  movups  xmm0, xmmword ptr [rdi+60h]
0x1800068c6  movups  xmmword ptr [rbx+5Ch], xmm0
0x1800068ca  jmp     short loc_1800068EF
0x1800068cc  sub     edx, 1
0x1800068cf  jz      short loc_1800068E9
0x1800068d1  sub     edx, 1
0x1800068d4  jz      short loc_1800068DB
0x1800068d6  cmp     edx, 8
0x1800068d9  jnz     short loc_1800068EF
0x1800068db  mov     eax, [rdi+60h]
0x1800068de  mov     [rbx+5Ch], eax
0x1800068e1  mov     eax, [rdi+64h]
0x1800068e4  mov     [rbx+60h], eax
0x1800068e7  jmp     short loc_1800068EF
0x1800068e9  mov     eax, [rdi+60h]
0x1800068ec  mov     [rbx+5Ch], eax
0x1800068ef  mov     rax, [rdi+88h]
0x1800068f6  mov     [rbx+84h], rax
0x1800068fd  mov     rax, [rdi+90h]
0x180006904  mov     [rbx+8Ch], rax
0x18000690b  mov     rax, [rdi+80h]
0x180006912  mov     [rbx+7Ch], rax
0x180006916  mov     eax, [rdi+98h]
0x18000691c  mov     [rbx+94h], eax
0x180006922  mov     eax, [rdi+9Ch]
0x180006928  mov     [rbx+98h], eax
0x18000692e  test    rbp, rbp
0x180006931  jz      short loc_180006939
0x180006933  movups  xmm0, xmmword ptr [rbp+0]
0x180006937  jmp     short loc_180006940
0x180006939  movups  xmm0, xmmword ptr [rdi+0A8h]
0x180006940  movups  xmmword ptr [rbx+0A8h], xmm0
0x180006947  mov     [rbx+0B8h], rsi
0x18000694e  xor     eax, eax
0x180006950  mov     [rbx+0C0h], esi
0x180006956  mov     [rbx+0C8h], rsi
0x18000695d  mov     [rbx+0D8h], rsi
0x180006964  mov     [r14], rbx
0x180006967  jmp     loc_1800069F1
0x18000696c  mov     [rbx+18h], rsi
0x180006970  mov     rcx, cs:WPP_GLOBAL_Control
0x180006977  lea     rbp, WPP_GLOBAL_Control
0x18000697e  cmp     rcx, rbp
0x180006981  jz      short loc_1800069DC
0x180006983  test    byte ptr [rcx+1Ch], 10h
0x180006987  jz      short loc_1800069AB
0x180006989  mov     rcx, [rcx+10h]
0x18000698d  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x180006994  mov     edx, 2Ch ; ','
0x180006999  mov     r9d, 8
0x18000699f  call    WPP_SF_d
0x1800069a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069ab  cmp     rcx, rbp
0x1800069ae  jz      short loc_1800069DC
0x1800069b0  test    byte ptr [rcx+1Ch], 10h
0x1800069b4  jz      short loc_1800069DC
0x1800069b6  mov     r9, [r13+0]
0x1800069ba  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x1800069c1  mov     rcx, [rcx+10h]
0x1800069c5  mov     edx, 2Dh ; '-'
0x1800069ca  mov     [rsp+78h+var_50], 8
0x1800069d2  mov     [rsp+78h+var_58], r12
0x1800069d7  call    WPP_SF_S_guid_D
0x1800069dc  test    rbx, rbx
0x1800069df  jz      short loc_1800069E9
0x1800069e1  mov     rcx, rbx; lpMem
0x1800069e4  call    FreeIniTxFilter
0x1800069e9  mov     [r14], rsi
0x1800069ec  mov     eax, 8
0x1800069f1  add     rsp, 38h
0x1800069f5  pop     r15
0x1800069f7  pop     r14
0x1800069f9  pop     r13
0x1800069fb  pop     r12
0x1800069fd  pop     rdi
0x1800069fe  pop     rsi
0x1800069ff  pop     rbp
0x180006a00  pop     rbx
0x180006a01  retn
```
