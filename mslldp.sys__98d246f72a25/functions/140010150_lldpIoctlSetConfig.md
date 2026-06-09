# lldpIoctlSetConfig

- ea: `0x140010150`
- end: `0x140010526`
- name: `lldpIoctlSetConfig`
- size: `982`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x14000fdd0`

## callees

- `0x140002180`
- `0x140003500`
- `0x140003d80`
- `0x140004a60`
- `0x140004b00`
- `0x140006720`
- `0x14000f3b8`
- `0x140010150`
- `0x140010aec`
- `0x140011a40`
- `0x140011cac`

## pseudocode

```c
__int64 __fastcall lldpIoctlSetConfig(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int v3; // ebp
  __int64 i; // rax
  unsigned int v6; // r8d
  char v7; // r12
  __int64 j; // rbx
  unsigned int v9; // r15d
  __int64 v10; // r14
  unsigned int v11; // r11d
  unsigned int v12; // r10d
  int v13; // eax
  int v14; // r15d
  int v15; // r13d
  int v16; // ecx
  int v17; // r8d
  int v18; // r12d
  int v19; // edx
  int v20; // r9d
  char v21; // bl
  char v22; // r8
  char v23; // dl
  int v24; // r15d
  char v25; // cl
  int v26; // r12d
  char v27; // al
  int v28; // eax
  __int64 v29; // r9
  __int128 v30; // xmm1

  v2 = lldpFindAndReferencePort();
  if ( !v2 )
    return 3221226021LL;
  if ( *(_DWORD *)(a1 + 16) == 1 && *(_QWORD *)(a1 + 24) >= 0x2Cu )
  {
    for ( i = 0; (unsigned int)i < 7; i = (unsigned int)(i + 1) )
    {
      v6 = *(_DWORD *)(*((unsigned int *)&lldpParameterRules + 6 * i + 5) + a1 + 16);
      if ( v6 != -1
        && (v6 < *((_DWORD *)&lldpParameterRules + 6 * i + 2) || v6 > LODWORD((&lldpParameterRules)[3 * i + 1])) )
      {
        v3 = -1073740757;
        goto LABEL_5;
      }
    }
    v3 = 0;
    v7 = 0;
    for ( j = 0; (unsigned int)j < 7; j = (unsigned int)(j + 1) )
    {
      v9 = *(_DWORD *)(*((unsigned int *)&lldpParameterRules + 6 * j + 5) + a1 + 16);
      if ( v9 != -1 )
      {
        if ( *(_BYTE *)(a1 + 60) )
          v7 = 1;
        v10 = v2 + 4LL * (int)j;
        if ( *(_DWORD *)(v10 + 248) == v9 )
        {
          v3 = 0;
        }
        else
        {
          if ( v9 < *((_DWORD *)&lldpParameterRules + 6 * (int)j + 2)
            || v9 > LODWORD((&lldpParameterRules)[3 * (int)j + 1]) )
          {
            v3 = -1073740757;
            v29 = 3221226539LL;
LABEL_61:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7c33d10fb468381898e2799524a08bcc_Traceguids, v29);
            break;
          }
          v3 = 0;
          if ( v7 && (v28 = lldpWriteConfigToRegistry(v2, j, v9), (v3 = v28) != 0) )
          {
            v29 = (unsigned int)v28;
            if ( v28 < 0 )
              goto LABEL_61;
          }
          else
          {
            *(_DWORD *)(v10 + 248) = v9;
          }
        }
      }
    }
    v11 = *(_DWORD *)(v2 + 264);
    v12 = *(_DWORD *)(v2 + 292);
    v13 = *(_DWORD *)(v2 + 296);
    v14 = *(_DWORD *)(v2 + 248);
    v15 = *(_DWORD *)(v2 + 268);
    v16 = *(_DWORD *)(v2 + 256);
    v17 = *(_DWORD *)(v2 + 252);
    v18 = *(_DWORD *)(v2 + 276);
    v19 = *(_DWORD *)(v2 + 284);
    v20 = *(_DWORD *)(v2 + 280);
    if ( v11 != v12 )
    {
      if ( v11 <= v12 )
      {
        if ( v11 < v12 )
        {
          if ( (signed int)v12 >= *(_DWORD *)(v2 + 872) )
            v12 = *(_DWORD *)(v2 + 872);
          *(_DWORD *)(v2 + 872) = v12;
        }
      }
      else
      {
        *(_DWORD *)(v2 + 872) += v11 - v12;
      }
    }
    if ( (v16 != v19 || (v21 = 0, v15 != v13)) && (v21 = 1, v16 != v19) || v17 != v20 )
      lldpUpdateTxTtl(v2);
    if ( v14 != v18 )
    {
      v22 = v14 && (v14 == 1 || v14 == 3);
      v23 = v18 && (v18 == 1 || v18 == 3);
      v25 = 0;
      if ( v14 )
      {
        v24 = v14 - 1;
        if ( v24 )
        {
          if ( (unsigned int)(v24 - 1) < 2 )
            v25 = 1;
        }
      }
      v27 = 0;
      if ( v18 )
      {
        v26 = v18 - 1;
        if ( v26 )
        {
          if ( (unsigned int)(v26 - 1) < 2 )
            v27 = 1;
        }
      }
      if ( v22 != v23 )
        v21 = 1;
      if ( v25 != v27 )
        lldpAdjustRxPacketFilters(v2);
    }
    if ( v21 )
      lldpEnableTxFastMode(v2);
    if ( memcmp((const void *)(v2 + 248), (const void *)(v2 + 276), 0x1Cu) )
    {
      v30 = *(_OWORD *)(v2 + 260);
      *(_OWORD *)(v2 + 276) = *(_OWORD *)(v2 + 248);
      *(_OWORD *)(v2 + 288) = v30;
      lldpQueueChangeNotificationEx((PVOID)v2);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7c33d10fb468381898e2799524a08bcc_Traceguids);
    v3 = -1073741736;
  }
LABEL_5:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 48), 0xFFFFFFFF) == 1 )
    lldpDeletePort((PVOID)v2);
  return v3;
}

```

## disassembly

```asm
0x140010150  push    rsi
0x140010152  push    rdi
0x140010153  sub     rsp, 38h
0x140010157  mov     rsi, rcx
0x14001015a  call    lldpFindAndReferencePort
0x14001015f  mov     rdi, rax
0x140010162  test    rax, rax
0x140010165  jz      loc_140010303
0x14001016b  cmp     dword ptr [rsi+10h], 1
0x14001016f  mov     [rsp+48h+arg_10], rbp
0x140010174  mov     [rsp+48h+var_18], r13
0x140010179  jz      short loc_1400101BE
0x14001017b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010182  lea     rax, WPP_GLOBAL_Control
0x140010189  cmp     rcx, rax
0x14001018c  jnz     loc_140010502
0x140010192  mov     ebp, 0C0000058h
0x140010197  mov     ecx, 0FFFFFFFFh
0x14001019c  lock xadd [rdi+30h], ecx
0x1400101a1  mov     r13, [rsp+48h+var_18]
0x1400101a6  cmp     ecx, 1
0x1400101a9  jz      loc_140010310
0x1400101af  mov     eax, ebp
0x1400101b1  mov     rbp, [rsp+48h+arg_10]
0x1400101b6  add     rsp, 38h
0x1400101ba  pop     rdi
0x1400101bb  pop     rsi
0x1400101bc  retn
0x1400101be  cmp     qword ptr [rsi+18h], 2Ch ; ','
0x1400101c3  jb      short loc_14001017B
0x1400101c5  xor     eax, eax
0x1400101c7  lea     r13, lldpParameterRules
0x1400101ce  xchg    ax, ax
0x1400101d0  cmp     eax, 7
0x1400101d3  jnb     short loc_140010203
0x1400101d5  lea     rdx, [rax+rax*2]
0x1400101d9  mov     ecx, [r13+rdx*8+14h]
0x1400101de  mov     r8d, [rcx+rsi+10h]
0x1400101e3  cmp     r8d, 0FFFFFFFFh
0x1400101e7  jz      short loc_1400101FF
0x1400101e9  cmp     r8d, [r13+rdx*8+8]
0x1400101ee  jb      loc_1400103B7
0x1400101f4  cmp     r8d, [r13+rdx*8+10h]
0x1400101f9  ja      loc_1400103B7
0x1400101ff  inc     eax
0x140010201  jmp     short loc_1400101D0
0x140010203  mov     [rsp+48h+arg_8], rbx
0x140010208  xor     ebp, ebp
0x14001020a  mov     [rsp+48h+arg_18], r12
0x14001020f  xor     r12b, r12b
0x140010212  mov     [rsp+48h+var_20], r14
0x140010217  xor     ebx, ebx
0x140010219  mov     [rsp+48h+var_28], r15
0x14001021e  xchg    ax, ax
0x140010220  cmp     ebx, 7
0x140010223  jnb     short loc_14001025C
0x140010225  lea     rcx, [rbx+rbx*2]
0x140010229  mov     eax, [r13+rcx*8+14h]
0x14001022e  mov     r15d, [rax+rsi+10h]
0x140010233  cmp     r15d, 0FFFFFFFFh
0x140010237  jz      short loc_140010258
0x140010239  cmp     byte ptr [rsi+3Ch], 0
0x14001023d  jz      short loc_140010242
0x14001023f  mov     r12b, 1
0x140010242  movsxd  rax, ebx
0x140010245  lea     r14, [rdi+rax*4]
0x140010249  cmp     [r14+0F8h], r15d
0x140010250  jnz     loc_1400103C1
0x140010256  xor     ebp, ebp
0x140010258  inc     ebx
0x14001025a  jmp     short loc_140010220
0x14001025c  mov     r11d, [rdi+108h]
0x140010263  mov     r10d, [rdi+124h]
0x14001026a  mov     eax, [rdi+128h]
0x140010270  mov     r15d, [rdi+0F8h]
0x140010277  mov     r13d, [rdi+10Ch]
0x14001027e  mov     ecx, [rdi+100h]
0x140010284  mov     r8d, [rdi+0FCh]
0x14001028b  mov     r12d, [rdi+114h]
0x140010292  mov     edx, [rdi+11Ch]
0x140010298  mov     r9d, [rdi+118h]
0x14001029f  mov     [rsp+48h+arg_0], eax
0x1400102a3  cmp     r11d, r10d
0x1400102a6  jnz     loc_140010448
0x1400102ac  cmp     ecx, edx
0x1400102ae  jnz     short loc_14001031D
0x1400102b0  xor     bl, bl
0x1400102b2  cmp     r13d, eax
0x1400102b5  jnz     short loc_14001031D
0x1400102b7  cmp     r8d, r9d
0x1400102ba  jnz     short loc_140010323
0x1400102bc  cmp     r15d, r12d
0x1400102bf  jnz     short loc_14001032D
0x1400102c1  mov     r15, [rsp+48h+var_28]
0x1400102c6  test    bl, bl
0x1400102c8  mov     rbx, [rsp+48h+arg_8]
0x1400102cd  mov     r12, [rsp+48h+arg_18]
0x1400102d2  jnz     loc_1400104C4
0x1400102d8  mov     r8d, 1Ch; Size
0x1400102de  lea     rdx, [rdi+114h]; Buf2
0x1400102e5  lea     rcx, [rdi+0F8h]; Buf1
0x1400102ec  call    memcmp
0x1400102f1  test    eax, eax
0x1400102f3  jnz     loc_1400104D1
0x1400102f9  mov     r14, [rsp+48h+var_20]
0x1400102fe  jmp     loc_140010197
0x140010303  mov     eax, 0C0000225h
0x140010308  add     rsp, 38h
0x14001030c  pop     rdi
0x14001030d  pop     rsi
0x14001030e  retn
0x140010310  mov     rcx, rdi; Context
0x140010313  call    lldpDeletePort
0x140010318  jmp     loc_1400101AF
0x14001031d  mov     bl, 1
0x14001031f  cmp     ecx, edx
0x140010321  jz      short loc_1400102B7
0x140010323  mov     rcx, rdi
0x140010326  call    lldpUpdateTxTtl
0x14001032b  jmp     short loc_1400102BC
0x14001032d  mov     ecx, r15d
0x140010330  test    r15d, r15d
0x140010333  jz      short loc_14001034C
0x140010335  sub     ecx, 1
0x140010338  jz      loc_140010487
0x14001033e  sub     ecx, 1
0x140010341  jz      short loc_14001034C
0x140010343  cmp     ecx, 1
0x140010346  jz      loc_140010487
0x14001034c  xor     r8b, r8b
0x14001034f  mov     ecx, r12d
0x140010352  test    r12d, r12d
0x140010355  jz      short loc_14001036E
0x140010357  sub     ecx, 1
0x14001035a  jz      loc_14001048F
0x140010360  sub     ecx, 1
0x140010363  jz      short loc_14001036E
0x140010365  cmp     ecx, 1
0x140010368  jz      loc_14001048F
0x14001036e  xor     dl, dl
0x140010370  test    r15d, r15d
0x140010373  jz      short loc_14001038F
0x140010375  sub     r15d, 1
0x140010379  jz      short loc_14001038F
0x14001037b  sub     r15d, 1
0x14001037f  jz      loc_140010496
0x140010385  cmp     r15d, 1
0x140010389  jz      loc_140010496
0x14001038f  xor     cl, cl
0x140010391  test    r12d, r12d
0x140010394  jz      short loc_1400103B0
0x140010396  sub     r12d, 1
0x14001039a  jz      short loc_1400103B0
0x14001039c  sub     r12d, 1
0x1400103a0  jz      loc_14001049D
0x1400103a6  cmp     r12d, 1
0x1400103aa  jz      loc_14001049D
0x1400103b0  xor     al, al
0x1400103b2  jmp     loc_14001049F
0x1400103b7  mov     ebp, 0C000042Bh
0x1400103bc  jmp     loc_140010197
0x1400103c1  lea     rax, [rax+rax*2]
0x1400103c5  cmp     r15d, [r13+rax*8+8]
0x1400103ca  jb      short loc_140010405
0x1400103cc  cmp     r15d, [r13+rax*8+10h]
0x1400103d1  ja      short loc_140010405
0x1400103d3  xor     ebp, ebp
0x1400103d5  test    r12b, r12b
0x1400103d8  jz      short loc_1400103F9
0x1400103da  mov     r8d, r15d
0x1400103dd  mov     edx, ebx
0x1400103df  mov     rcx, rdi
0x1400103e2  call    lldpWriteConfigToRegistry
0x1400103e7  mov     ebp, eax
0x1400103e9  test    eax, eax
0x1400103eb  jz      short loc_1400103F9
0x1400103ed  mov     r9d, eax
0x1400103f0  test    eax, eax
0x1400103f2  js      short loc_14001040D
0x1400103f4  jmp     loc_140010258
0x1400103f9  mov     [r14+0F8h], r15d
0x140010400  jmp     loc_140010258
0x140010405  mov     ebp, 0C000042Bh
0x14001040a  mov     r9d, ebp
0x14001040d  mov     rcx, cs:WPP_GLOBAL_Control
0x140010414  lea     rax, WPP_GLOBAL_Control
0x14001041b  cmp     rcx, rax
0x14001041e  jz      loc_14001025C
0x140010424  cmp     byte ptr [rcx+29h], 2
0x140010428  jb      loc_14001025C
0x14001042e  mov     rcx, [rcx+18h]
0x140010432  lea     r8, WPP_7c33d10fb468381898e2799524a08bcc_Traceguids
0x140010439  mov     edx, 0Bh
0x14001043e  call    WPP_SF_d
0x140010443  jmp     loc_14001025C
0x140010448  jbe     short loc_14001045F
0x14001044a  mov     eax, [rdi+368h]
0x140010450  sub     r11d, r10d
0x140010453  add     r11d, eax
0x140010456  mov     [rdi+368h], r11d
0x14001045d  jmp     short loc_14001047E
0x14001045f  jnb     loc_1400102AC
0x140010465  mov     eax, [rdi+368h]
0x14001046b  cmp     r10d, eax
0x14001046e  jl      short loc_140010477
0x140010470  mov     r10d, [rdi+368h]
0x140010477  mov     [rdi+368h], r10d
0x14001047e  mov     eax, [rsp+48h+arg_0]
0x140010482  jmp     loc_1400102AC
0x140010487  mov     r8b, 1
0x14001048a  jmp     loc_14001034F
0x14001048f  mov     dl, 1
0x140010491  jmp     loc_140010370
0x140010496  mov     cl, 1
0x140010498  jmp     loc_140010391
0x14001049d  mov     al, 1
0x14001049f  cmp     r8b, dl
0x1400104a2  movzx   ebx, bl
0x1400104a5  mov     r9d, 1
0x1400104ab  cmovnz  ebx, r9d
0x1400104af  cmp     cl, al
0x1400104b1  jz      loc_1400102C1
0x1400104b7  mov     rcx, rdi
0x1400104ba  call    lldpAdjustRxPacketFilters
0x1400104bf  jmp     loc_1400102C1
0x1400104c4  mov     rcx, rdi
0x1400104c7  call    lldpEnableTxFastMode
0x1400104cc  jmp     loc_1400102D8
0x1400104d1  movups  xmm0, xmmword ptr [rdi+0F8h]
0x1400104d8  xor     edx, edx
0x1400104da  mov     r8d, 4
0x1400104e0  movups  xmm1, xmmword ptr [rdi+104h]
0x1400104e7  mov     rcx, rdi; Context
0x1400104ea  movups  xmmword ptr [rdi+114h], xmm0
0x1400104f1  movups  xmmword ptr [rdi+120h], xmm1
0x1400104f8  call    lldpQueueChangeNotificationEx
0x1400104fd  jmp     loc_1400102F9
0x140010502  cmp     byte ptr [rcx+29h], 2
0x140010506  jb      loc_140010192
0x14001050c  mov     rcx, [rcx+18h]
0x140010510  lea     r8, WPP_7c33d10fb468381898e2799524a08bcc_Traceguids
0x140010517  mov     edx, 0Ah
0x14001051c  call    WPP_SF_
0x140010521  jmp     loc_140010192
```
