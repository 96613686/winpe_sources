# MRxSmb2ShouldRestartExchange

- ea: `0x14000c410`
- end: `0x14000cde5`
- name: `MRxSmb2ShouldRestartExchange`
- size: `2517`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x14000c410`
- `0x140028450`
- `0x140028a50`
- `0x14002a648`
- `0x14002f8c4`
- `0x140037120`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000c8d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c8d0`
- `mrxsmb!SmbCeGetExchangeHistory` at `0x140039858`
- `mrxsmb!SmbCeGetExchangeHistory` at `0x14003995c`
- `mrxsmb!SmbCeGetExchangeHistory` at `0x140039858`
- `mrxsmb!SmbCeGetExchangeHistory` at `0x14003995c`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000c636`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000c9da`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000ca1b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000cb8f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000cbc3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000cc54`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000c636`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000c9da`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000ca1b`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000cb8f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000cbc3`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000cc54`

## pseudocode

```c
__int64 __fastcall MRxSmb2ShouldRestartExchange(__int64 a1)
{
  int v1; // r14d
  int v3; // r15d
  __int64 v4; // rdi
  __int64 v5; // rbp
  __int64 v6; // r12
  __int64 v7; // r13
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // r10
  __int64 v13; // rdx
  int v14; // ecx
  int v15; // r8d
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // esi
  __int64 v20; // rcx
  __int64 ConfigurationBlock; // rax
  __int64 v22; // rdx
  __int64 v23; // r9
  unsigned int v24; // edi
  unsigned int v25; // edi
  unsigned __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbp
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // r8
  __int64 v44; // rax
  __int64 v45; // r8
  char v46; // r9
  int v47; // r10d
  __int64 v48; // r9
  __int64 v49; // r11
  __int64 v50; // rcx
  int ExchangeHistory; // r10d
  __int64 v52; // r9
  unsigned int v53; // [rsp+70h] [rbp-88h]
  int v54; // [rsp+74h] [rbp-84h]
  __int64 v55; // [rsp+78h] [rbp-80h]
  _BYTE v56[64]; // [rsp+80h] [rbp-78h] BYREF

  v1 = *(_DWORD *)(a1 + 16);
  v3 = 0;
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 232) + 56LL) )
  {
    v19 = 1773;
    goto LABEL_52;
  }
  v4 = *(_QWORD *)(a1 + 88);
  v5 = *(_QWORD *)(a1 + 80);
  v6 = *(_QWORD *)(a1 + 48);
  v7 = *(_QWORD *)(a1 + 72);
  v54 = *(_DWORD *)(a1 + 20);
  v55 = v4;
  v8 = *(unsigned int *)(*(_QWORD *)(v7 + 24) + 2344LL);
  v53 = *(_DWORD *)(*(_QWORD *)(v7 + 24) + 2344LL);
  if ( (*(_DWORD *)(a1 + 68) & 0x100) != 0 )
  {
    v19 = 1783;
    goto LABEL_52;
  }
  v9 = a1 + 160;
  v10 = *(_QWORD *)(a1 + 160);
  v11 = 0x4208040000000601LL;
  v12 = 0x900281000001LL;
  v13 = v10 - 8;
  if ( v10 == v9 )
    v13 = 0;
  if ( v13 )
  {
    do
    {
      v14 = *(_DWORD *)(v13 + 48);
      if ( v14 < 0 || (*(_DWORD *)(v13 + 4) & 0x400) != 0 )
      {
        v15 = *(_DWORD *)(v13 + 52);
      }
      else
      {
        v14 = *(_DWORD *)(a1 + 16);
        v15 = *(_DWORD *)(a1 + 20);
      }
      if ( (unsigned int)(v14 + 1073741667) <= 0x2F && _bittest64(&v12, v14 + 1073741667)
        || v14 == -1069481983
        || v14 == -1073740964
        || v14 == -1073740672
        || v14 == -1073741202
        || (v16 = (unsigned int)(v14 + 1073741309), (unsigned int)v16 <= 0x3E) && _bittest64(&v11, v16)
        || v14 == -1073741507
        || v14 == -1073741073
        || (unsigned int)(v14 + 1073740698) <= 1
        || v14 == -1073741810
        || v14 == -2146893022
        || v14 == -2147483631 )
      {
        *(_DWORD *)(v13 + 4) &= ~0x400u;
        if ( v1 >= 0 )
        {
          v1 = v14;
          v54 = v15;
        }
      }
      v17 = *(_QWORD *)(v13 + 8);
      v13 = 0;
      if ( v17 != v9 )
        v13 = v17 - 8;
    }
    while ( v13 );
    v8 = v53;
  }
  if ( dbgExchangeRestartThreshold && *(_DWORD *)(a1 + 44) >= (unsigned int)dbgExchangeRestartThreshold )
    __debugbreak();
  if ( v1 == -1073741507 || (*(_QWORD *)(a1 + 328) = 0, v1 == -1073740964) )
  {
    v19 = 1858;
    v3 = -1069481983;
    goto LABEL_52;
  }
  if ( (*(_DWORD *)(a1 + 68) & 0x2000) != 0 )
  {
    v19 = 1865;
    goto LABEL_52;
  }
  v18 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL);
  if ( v18 && *(_BYTE *)(v18 + 188) == 1 )
  {
    v19 = 1876;
    goto LABEL_52;
  }
  v19 = 0;
  if ( ((unsigned int)(v1 + 1073741667) > 0x2F || !_bittest64(&v12, v1 + 1073741667))
    && v1 != -1069481983
    && v1 != -1073741073
    && v1 != -1073741202 )
  {
    v27 = (unsigned int)(v1 + 1073741309);
    if ( (unsigned int)v27 > 0x3E || (v28 = 0x4208040000000601LL, !_bittest64(&v28, v27)) )
    {
      if ( (unsigned int)(v1 + 1073740698) > 1
        && v1 != -1073740672
        && v1 != -1073741810
        && v1 != -2146893022
        && v1 != -2147483631 )
      {
        goto LABEL_52;
      }
    }
  }
  v20 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL);
  if ( *(_BYTE *)(v20 + 1313) )
  {
    if ( v1 == -2147483631 || v1 == -1073741810 || v1 == -1073741202 || v1 == -1073741667 )
      goto LABEL_52;
  }
  if ( v6 )
  {
    _m_prefetchw((const void *)(v6 + 128));
    v20 = *(unsigned int *)(v6 + 128);
    if ( (_InterlockedXor((volatile signed __int32 *)(v6 + 128), 0) & 3) != 0 )
    {
      v19 = 1902;
      goto LABEL_52;
    }
    v30 = *(_QWORD *)(v6 + 40);
    if ( v30 && *(_BYTE *)(v30 + 68) )
    {
      v19 = 1909;
      goto LABEL_52;
    }
  }
  if ( (unsigned int)(v1 + 1073741643) > 9 || (v20 = 641, !_bittest((const int *)&v20, v1 + 1073741643)) )
  {
    if ( v1 != -1073740697 )
    {
      v29 = (unsigned int)(v1 + 1073741300);
      if ( (unsigned int)v29 > 0x35 || (v20 = 0x21040000000003LL, !_bittest64(&v20, v29)) )
      {
        if ( v4 )
        {
LABEL_47:
          v24 = *(_DWORD *)(v4 + 264);
          goto LABEL_48;
        }
        if ( !v5 )
        {
          v24 = *(_DWORD *)(v7 + 392);
          goto LABEL_48;
        }
        goto LABEL_136;
      }
    }
  }
  if ( (_DWORD)v8 )
  {
    v20 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL);
    v22 = *(unsigned int *)(v20 + 2344);
  }
  else
  {
    ConfigurationBlock = MRxSmbGetConfigurationBlock(v20);
    v8 = v53;
    v22 = *(unsigned int *)(ConfigurationBlock + 240);
  }
  if ( v4 )
  {
    if ( !*(_DWORD *)(v4 + 12) && *(_DWORD *)(v4 + 264) == *(_DWORD *)(a1 + 112) )
    {
      v23 = 10000000LL * (unsigned int)v22;
      if ( MEMORY[0xFFFFF78000000008] >= (unsigned __int64)(v23 + *(_QWORD *)(a1 + 200)) )
      {
        if ( dbgBreakOnRetryTimeout )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_iii(
              WPP_GLOBAL_Control->AttachedDevice,
              38,
              WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids,
              *(_QWORD *)(a1 + 200),
              v23,
              MEMORY[0xFFFFF78000000008]);
          }
          __debugbreak();
        }
        v19 = 1946;
      }
      else if ( v1 == -1073740697 || *(_DWORD *)(v7 + 700) <= *(_DWORD *)(a1 + 224) )
      {
        v19 = 1963;
        v3 = -1069481983;
      }
      else
      {
        v19 = 1958;
      }
      goto LABEL_52;
    }
    goto LABEL_47;
  }
  if ( v5 )
  {
    if ( !*(_DWORD *)(v5 + 12) && *(_DWORD *)(v5 + 264) == *(_DWORD *)(a1 + 108) )
    {
      if ( (unsigned __int8)MRxSmb2IsIoTimedOut(a1, v22, v8) )
      {
        v19 = 1975;
      }
      else
      {
        v19 = 1979;
        v3 = -1069481983;
      }
      goto LABEL_52;
    }
LABEL_136:
    v24 = *(_DWORD *)(v5 + 264);
    goto LABEL_48;
  }
  if ( !*(_DWORD *)(v7 + 12) && *(_DWORD *)(v7 + 392) == *(_DWORD *)(a1 + 104) )
  {
    if ( (unsigned __int8)MRxSmb2IsIoTimedOut(a1, v22, v8) )
    {
      v19 = 1991;
    }
    else
    {
      v19 = 1995;
      v3 = -1069481983;
    }
    goto LABEL_52;
  }
  v24 = *(_DWORD *)(v7 + 392);
LABEL_48:
  if ( !v6 )
    goto LABEL_50;
  if ( v1 == -1073740698 && !*(_BYTE *)(v6 + 32) )
  {
    if ( (_DWORD)v8 )
      v41 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL) + 2344LL);
    else
      v41 = *(unsigned int *)(MRxSmbGetConfigurationBlock(v20) + 240);
    v19 = 2032;
    v3 = -1069481983;
    if ( (unsigned __int8)MRxSmb2IsIoTimedOut(a1, v41, v8) )
      v3 = 0;
    goto LABEL_52;
  }
  if ( !*(_QWORD *)(v6 + 72) )
  {
LABEL_50:
    if ( *(_DWORD *)(a1 + 44) >= 3u
      && (v1 == -1073741667
       || v1 == -2147483631
       || v1 == -1073741810
       || v1 == -1073741202
       || v24 >= *(_DWORD *)(a1 + 220))
      || (_DWORD)v8 )
    {
      if ( !*(_BYTE *)(MRxSmbGetConfigurationBlock(v20) + 235) || (*(_BYTE *)(v7 + 737) & 3) == 3 )
      {
        if ( (*(_BYTE *)(v7 + 737) & 3) != 2 && (*(_DWORD *)(v7 + 716) & 0x2000) != 0 )
        {
          v19 = 2081;
          v38 = MRxSmbGetConfigurationBlock(v37);
          v3 = -1069481983;
          if ( (unsigned __int8)MRxSmb2IsIoTimedOut(a1, *(_DWORD *)(v38 + 12) >> 1, v39) )
            v3 = 0;
        }
      }
      else
      {
        v19 = 2065;
      }
    }
    else
    {
      v3 = -1069481983;
      v19 = 2053;
    }
    goto LABEL_52;
  }
  if ( KeGetCurrentIrql() )
  {
    v19 = 2093;
    v3 = -1069481983;
  }
  else
  {
    v31 = *(_QWORD *)(v6 + 72);
    if ( v31 )
    {
      v32 = *(_QWORD *)(v6 + 64);
      v33 = *(_QWORD *)(v31 + 48);
      v34 = v32 ? *(_QWORD *)(v32 + 56) : 0LL;
      if ( v33 )
      {
        v35 = *(_DWORD *)(v33 + 8);
        if ( (v35 & 0x20) != 0 || (v35 & 0x40) != 0 )
        {
          if ( *(int *)(v33 + 4) < 6 || *(_BYTE *)(v6 + 32) == 2 )
          {
            v46 = *(_BYTE *)(v6 + 32);
            if ( v46 == 13 && *(_DWORD *)(v6 + 540) == 1311180 )
            {
              v19 = 2164;
              v3 = -1069481983;
            }
            else
            {
              v49 = *(_QWORD *)(a1 + 200);
              if ( MEMORY[0xFFFFF78000000008] >= (unsigned __int64)(v49 + *(_QWORD *)(v33 + 256))
                || v34
                && (v50 = *(_QWORD *)(v34 + 40)) != 0
                && (MEMORY[0xFFFFF78000000008] >= (unsigned __int64)(v50 + v49)
                 || v46 == 2 && MEMORY[0xFFFFF78000000008] >= (unsigned __int64)(*(_QWORD *)(v33 + 248) + v50)) )
              {
                if ( *(_QWORD *)(v6 + 40) )
                {
                  ExchangeHistory = SmbCeGetExchangeHistory(a1, 4, v56);
                  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
                  {
                    v52 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v31 + 32) + 120LL) + 88LL);
                    McTemplateK0uqhzr2hzr4qqqNR8_EtwWriteTransfer(
                      v54,
                      **(_WORD **)(v31 + 80) >> 1,
                      *(_WORD *)v52 >> 1,
                      *(unsigned __int8 *)(v6 + 32),
                      *(_DWORD *)(a1 + 44),
                      *(_WORD *)v52 >> 1,
                      *(_QWORD *)(v52 + 8),
                      **(_WORD **)(v31 + 80) >> 1,
                      *(_QWORD *)(*(_QWORD *)(v31 + 80) + 8LL),
                      v1,
                      v54,
                      ExchangeHistory,
                      16 * ExchangeHistory,
                      (__int64)v56);
                  }
                }
                v19 = 2199;
              }
              else
              {
                v19 = 2207;
                v3 = -1069481983;
              }
            }
          }
          else
          {
            if ( *(_QWORD *)(v6 + 40) )
            {
              v47 = SmbCeGetExchangeHistory(a1, 4, v56);
              if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
              {
                v48 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v31 + 32) + 120LL) + 88LL);
                McTemplateK0uqhzr2hzr4qqqNR8_EtwWriteTransfer(
                  v54,
                  **(_WORD **)(v31 + 80) >> 1,
                  *(_WORD *)v48 >> 1,
                  *(unsigned __int8 *)(v6 + 32),
                  *(_DWORD *)(a1 + 44),
                  *(_WORD *)v48 >> 1,
                  *(_QWORD *)(v48 + 8),
                  **(_WORD **)(v31 + 80) >> 1,
                  *(_QWORD *)(*(_QWORD *)(v31 + 80) + 8LL),
                  v1,
                  v54,
                  v47,
                  16 * v47,
                  (__int64)v56);
              }
            }
            v19 = 2152;
          }
        }
        else if ( v34
               && (v40 = *(_QWORD *)(v34 + 40)) != 0
               && (MEMORY[0xFFFFF78000000008] >= (unsigned __int64)(v40 + *(_QWORD *)(a1 + 200))
                || *(_BYTE *)(v6 + 32) == 2
                && MEMORY[0xFFFFF78000000008] >= (unsigned __int64)(v40 + *(_QWORD *)(v33 + 248))) )
        {
          v19 = 2227;
        }
        else
        {
          v36 = *(unsigned int *)(*(_QWORD *)(v55 + 424) + 176LL);
          if ( (v36 & 0x80u) != 0LL )
          {
            v42 = MRxSmbGetConfigurationBlock(v36);
            v3 = -1069481983;
            v19 = 2241;
            if ( (unsigned __int8)MRxSmb2IsIoTimedOut(a1, *(unsigned int *)(v42 + 240), v43) )
            {
              v3 = 0;
              v19 = 0;
            }
          }
          else if ( v53 )
          {
            if ( (*(_DWORD *)(a1 + 44) < 3u
               || v1 != -2147483631
               && v1 != -1073741810
               && v1 != -1073741202
               && v1 != -1073741667
               && v24 < *(_DWORD *)(a1 + 220))
              && !(unsigned __int8)MRxSmb2IsIoTimedOut(
                                     a1,
                                     *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL) + 2344LL),
                                     v34) )
            {
              v3 = -1069481983;
            }
            v19 = 2261;
          }
          else if ( (*(_BYTE *)(v7 + 737) & 3) == 2 || (*(_DWORD *)(v7 + 716) & 0x2000) == 0 )
          {
            if ( *(_DWORD *)(a1 + 44) < 3u
              || v1 != -2147483631
              && v1 != -1073741810
              && v1 != -1073741202
              && v1 != -1073741667
              && v24 < *(_DWORD *)(a1 + 220) )
            {
              v19 = 2276;
              v3 = -1069481983;
            }
          }
          else
          {
            v44 = MRxSmbGetConfigurationBlock(v36);
            if ( !(unsigned __int8)MRxSmb2IsIoTimedOut(a1, *(unsigned int *)(v44 + 240), v45) )
            {
              v19 = 2286;
              v3 = -1069481983;
            }
          }
        }
      }
    }
  }
LABEL_52:
  v25 = 0;
  if ( !dbgDisableExchangeRestart )
    v25 = v3;
  if ( (v19
     || v25 == -1069481983
     || *(_DWORD *)(a1 + 44) && v1 < 0
     || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qddddd(
      WPP_GLOBAL_Control->AttachedDevice,
      3225485313LL,
      &WPP_GLOBAL_Control,
      a1,
      *(_DWORD *)(a1 + 44),
      v19,
      *(_DWORD *)(a1 + 16),
      v1,
      v25);
  }
  return v25;
}

```

## disassembly

```asm
0x14000c410  push    rbx
0x14000c412  push    rsi
0x14000c413  push    rdi
0x14000c414  push    r14
0x14000c416  sub     rsp, 0D8h
0x14000c41d  mov     rax, cs:__security_cookie
0x14000c424  xor     rax, rsp
0x14000c427  mov     [rsp+0F8h+var_38], rax
0x14000c42f  mov     rax, [rcx+0E8h]
0x14000c436  lea     r8, WPP_GLOBAL_Control
0x14000c43d  mov     r14d, [rcx+10h]
0x14000c441  mov     rbx, rcx
0x14000c444  mov     [rsp+0F8h+var_28], r15
0x14000c44c  mov     r11d, 0C0410001h
0x14000c452  xor     r15d, r15d
0x14000c455  cmp     [rax+38h], r15
0x14000c459  jz      loc_14000C6C8
0x14000c45f  mov     rdi, [rcx+58h]
0x14000c463  mov     r10d, [rcx+14h]
0x14000c467  mov     [rsp+0F8h+arg_8], rbp
0x14000c46f  mov     rbp, [rcx+50h]
0x14000c473  mov     [rsp+0F8h+arg_10], r12
0x14000c47b  mov     r12, [rcx+30h]
0x14000c47f  mov     [rsp+0F8h+arg_18], r13
0x14000c487  mov     r13, [rcx+48h]
0x14000c48b  mov     [rsp+0F8h+var_84], r10d
0x14000c490  mov     [rsp+0F8h+var_80], rdi
0x14000c495  mov     rax, [r13+18h]
0x14000c499  mov     r8d, [rax+928h]
0x14000c4a0  mov     eax, [rcx+44h]
0x14000c4a3  mov     [rsp+0F8h+var_88], r8d
0x14000c4a8  bt      eax, 8
0x14000c4ac  jb      loc_14000CA74
0x14000c4b2  xor     eax, eax
0x14000c4b4  lea     r9, [rcx+0A0h]
0x14000c4bb  mov     rcx, [r9]
0x14000c4be  mov     rsi, 4208040000000601h
0x14000c4c8  cmp     rcx, r9
0x14000c4cb  mov     r10, 900281000001h
0x14000c4d5  lea     rdx, [rcx-8]
0x14000c4d9  cmovz   rdx, rax
0x14000c4dd  test    rdx, rdx
0x14000c4e0  jz      loc_14000C57A
0x14000c4e6  mov     ecx, [rdx+30h]
0x14000c4e9  test    ecx, ecx
0x14000c4eb  js      short loc_14000C4FA
0x14000c4ed  test    dword ptr [rdx+4], 400h
0x14000c4f4  jz      loc_14000C6BC
0x14000c4fa  mov     r8d, [rdx+34h]
0x14000c4fe  lea     eax, [rcx+3FFFFF63h]
0x14000c504  cmp     eax, 2Fh ; '/'
0x14000c507  ja      short loc_14000C511
0x14000c509  cdqe
0x14000c50b  bt      r10, rax
0x14000c50f  jb      short loc_14000C547
0x14000c511  cmp     ecx, r11d
0x14000c514  jz      short loc_14000C547
0x14000c516  cmp     ecx, 0C000035Ch
0x14000c51c  jz      short loc_14000C547
0x14000c51e  cmp     ecx, 0C0000480h
0x14000c524  jz      short loc_14000C547
0x14000c526  cmp     ecx, 0C000026Eh
0x14000c52c  jz      short loc_14000C547
0x14000c52e  lea     eax, [rcx+3FFFFDFDh]
0x14000c534  cmp     eax, 3Eh ; '>'
0x14000c537  ja      loc_140039746
0x14000c53d  bt      rsi, rax
0x14000c541  jnb     loc_140039746
0x14000c547  and     dword ptr [rdx+4], 0FFFFFBFFh
0x14000c54e  test    r14d, r14d
0x14000c551  js      short loc_14000C55B
0x14000c553  mov     r14d, ecx
0x14000c556  mov     [rsp+0F8h+var_84], r8d
0x14000c55b  mov     rcx, [rdx+8]
0x14000c55f  xor     edx, edx
0x14000c561  cmp     rcx, r9
0x14000c564  lea     rax, [rcx-8]
0x14000c568  cmovnz  rdx, rax
0x14000c56c  test    rdx, rdx
0x14000c56f  jnz     loc_14000C4E6
0x14000c575  mov     r8d, [rsp+0F8h+var_88]
0x14000c57a  mov     eax, cs:dbgExchangeRestartThreshold
0x14000c580  test    eax, eax
0x14000c582  jnz     loc_14000CAF0
0x14000c588  cmp     r14d, 0C000013Dh
0x14000c58f  jz      loc_14000C824
0x14000c595  mov     [rbx+148h], r15
0x14000c59c  cmp     r14d, 0C000035Ch
0x14000c5a3  jz      loc_14000C824
0x14000c5a9  mov     eax, [rbx+44h]
0x14000c5ac  bt      eax, 0Dh
0x14000c5b0  jb      loc_14000C99D
0x14000c5b6  mov     rax, [rbx+58h]
0x14000c5ba  mov     rcx, [rax+1A8h]
0x14000c5c1  test    rcx, rcx
0x14000c5c4  jz      short loc_14000C5D3
0x14000c5c6  cmp     byte ptr [rcx+0BCh], 1
0x14000c5cd  jz      loc_14000C817
0x14000c5d3  xor     esi, esi
0x14000c5d5  lea     eax, [r14+3FFFFF63h]
0x14000c5dc  cmp     eax, 2Fh ; '/'
0x14000c5df  ja      loc_14000C7CB
0x14000c5e5  cdqe
0x14000c5e7  bt      r10, rax
0x14000c5eb  jnb     loc_14000C7CB
0x14000c5f1  mov     rax, [rbx+48h]
0x14000c5f5  mov     rcx, [rax+18h]
0x14000c5f9  cmp     [rcx+521h], sil
0x14000c600  jnz     loc_14000CB07
0x14000c606  test    r12, r12
0x14000c609  jnz     loc_14000C86A
0x14000c60f  lea     eax, [r14+3FFFFF4Bh]
0x14000c616  cmp     eax, 9
0x14000c619  ja      loc_14000C834
0x14000c61f  mov     ecx, 281h
0x14000c624  bt      ecx, eax
0x14000c627  jnb     loc_14000C834
0x14000c62d  test    r8d, r8d
0x14000c630  jnz     loc_14000CADD
0x14000c636  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14000c63d  nop     dword ptr [rax+rax+00h]
0x14000c642  mov     r8d, [rsp+0F8h+var_88]
0x14000c647  mov     r11d, 0C0410001h
0x14000c64d  mov     edx, [rax+0F0h]
0x14000c653  test    rdi, rdi
0x14000c656  jz      loc_14000CB5E
0x14000c65c  cmp     [rdi+0Ch], esi
0x14000c65f  jnz     short loc_14000C6DB
0x14000c661  mov     eax, [rbx+70h]
0x14000c664  cmp     [rdi+108h], eax
0x14000c66a  jnz     short loc_14000C6DB
0x14000c66c  mov     rax, 0FFFFF78000000008h
0x14000c676  mov     r8, [rax]
0x14000c679  mov     rcx, [rbx+0C8h]
0x14000c680  mov     eax, edx
0x14000c682  imul    r9, rax, 989680h
0x14000c689  add     rcx, r9
0x14000c68c  cmp     r8, rcx
0x14000c68f  jnb     loc_1400397DF
0x14000c695  cmp     r14d, 0C0000467h
0x14000c69c  jz      loc_14000CD60
0x14000c6a2  mov     eax, [rbx+0E0h]
0x14000c6a8  cmp     [r13+2BCh], eax
0x14000c6af  jbe     loc_14000CD60
0x14000c6b5  mov     esi, 7A6h
0x14000c6ba  jmp     short loc_14000C705
0x14000c6bc  mov     ecx, [rbx+10h]
0x14000c6bf  mov     r8d, [rbx+14h]
0x14000c6c3  jmp     loc_14000C4FE
0x14000c6c8  mov     esi, 6EDh
0x14000c6cd  mov     edx, r11d
0x14000c6d0  jmp     short loc_14000C729
0x14000c6d2  test    rdi, rdi
0x14000c6d5  jz      loc_14000CB4D
0x14000c6db  mov     edi, [rdi+108h]
0x14000c6e1  test    r12, r12
0x14000c6e4  jnz     loc_14000C8B8
0x14000c6ea  cmp     dword ptr [rbx+2Ch], 3
0x14000c6ee  jnb     loc_14000C9AA
0x14000c6f4  test    r8d, r8d
0x14000c6f7  jnz     loc_14000C9DA
0x14000c6fd  mov     r15d, r11d
0x14000c700  mov     esi, 805h
0x14000c705  mov     edx, 0C0410001h
0x14000c70a  lea     r8, WPP_GLOBAL_Control
0x14000c711  mov     r12, [rsp+0F8h+arg_10]
0x14000c719  mov     rbp, [rsp+0F8h+arg_8]
0x14000c721  mov     r13, [rsp+0F8h+arg_18]
0x14000c729  movzx   eax, cs:dbgDisableExchangeRestart
0x14000c730  xor     edi, edi
0x14000c732  test    al, al
0x14000c734  cmovz   edi, r15d
0x14000c738  mov     r15, [rsp+0F8h+var_28]
0x14000c740  test    esi, esi
0x14000c742  jz      short loc_14000C770
0x14000c744  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c74b  cmp     rcx, r8
0x14000c74e  jnz     short loc_14000C795
0x14000c750  mov     eax, edi
0x14000c752  mov     rcx, [rsp+0F8h+var_38]
0x14000c75a  xor     rcx, rsp; StackCookie
0x14000c75d  call    __security_check_cookie
0x14000c762  add     rsp, 0D8h
0x14000c769  pop     r14
0x14000c76b  pop     rdi
0x14000c76c  pop     rsi
0x14000c76d  pop     rbx
0x14000c76e  retn
0x14000c770  cmp     edi, edx
0x14000c772  jz      short loc_14000C744
0x14000c774  cmp     dword ptr [rbx+2Ch], 0
0x14000c778  ja      loc_14000CA81
0x14000c77e  mov     rax, cs:WPP_GLOBAL_Control
0x14000c785  mov     ecx, [rax+2Ch]
0x14000c788  test    cl, 10h
0x14000c78b  jz      short loc_14000C750
0x14000c78d  cmp     byte ptr [rax+29h], 4
0x14000c791  jb      short loc_14000C750
0x14000c793  jmp     short loc_14000C744
0x14000c795  mov     eax, [rcx+2Ch]
0x14000c798  test    al, 10h
0x14000c79a  jz      short loc_14000C750
0x14000c79c  cmp     byte ptr [rcx+29h], 2
0x14000c7a0  jb      short loc_14000C750
0x14000c7a2  mov     eax, [rbx+10h]
0x14000c7a5  mov     r9, rbx
0x14000c7a8  mov     rcx, [rcx+18h]
0x14000c7ac  mov     dword ptr [rsp+0F8h+var_B8], edi
0x14000c7b0  mov     [rsp+0F8h+var_C0], r14d
0x14000c7b5  mov     dword ptr [rsp+0F8h+var_C8], eax
0x14000c7b9  mov     eax, [rbx+2Ch]
0x14000c7bc  mov     dword ptr [rsp+0F8h+var_D0], esi
0x14000c7c0  mov     dword ptr [rsp+0F8h+var_D8], eax
0x14000c7c4  call    WPP_SF_qddddd
0x14000c7c9  jmp     short loc_14000C750
0x14000c7cb  cmp     r14d, r11d
0x14000c7ce  jz      loc_14000C5F1
0x14000c7d4  cmp     r14d, 0C00002EFh
0x14000c7db  jz      loc_14000C5F1
0x14000c7e1  cmp     r14d, 0C000026Eh
0x14000c7e8  jz      loc_14000C5F1
0x14000c7ee  lea     eax, [r14+3FFFFDFDh]
0x14000c7f5  cmp     eax, 3Eh ; '>'
0x14000c7f8  ja      loc_140039796
0x14000c7fe  mov     rcx, 4208040000000601h
0x14000c808  bt      rcx, rax
0x14000c80c  jb      loc_14000C5F1
0x14000c812  jmp     loc_140039796
0x14000c817  mov     esi, 754h
0x14000c81c  mov     edx, r11d
0x14000c81f  jmp     loc_14000C70A
0x14000c824  mov     esi, 742h
0x14000c829  mov     r15d, r11d
0x14000c82c  mov     edx, r11d
0x14000c82f  jmp     loc_14000C70A
0x14000c834  cmp     r14d, 0C0000467h
0x14000c83b  jz      loc_14000C62D
0x14000c841  lea     eax, [r14+3FFFFDF4h]
0x14000c848  cmp     eax, 35h ; '5'
0x14000c84b  ja      loc_14000C6D2
0x14000c851  mov     rcx, 21040000000003h
0x14000c85b  bt      rcx, rax
0x14000c85f  jnb     loc_14000C6D2
0x14000c865  jmp     loc_14000C62D
0x14000c86a  prefetchw byte ptr [r12+80h]
0x14000c873  mov     eax, [r12+80h]
0x14000c87b  mov     ecx, eax
0x14000c87d  xor     ecx, esi
0x14000c87f  lock cmpxchg [r12+80h], ecx
0x14000c889  jnz     short loc_14000C87B
0x14000c88b  test    al, 3
0x14000c88d  jnz     loc_14000CB40
0x14000c893  mov     rax, [r12+28h]
0x14000c898  test    rax, rax
0x14000c89b  jz      loc_14000C60F
0x14000c8a1  cmp     [rax+44h], sil
0x14000c8a5  jz      loc_14000C60F
0x14000c8ab  mov     esi, 775h
0x14000c8b0  mov     edx, r11d
0x14000c8b3  jmp     loc_14000C70A
0x14000c8b8  cmp     r14d, 0C0000466h
0x14000c8bf  jz      loc_14000CB7B
0x14000c8c5  cmp     [r12+48h], rsi
0x14000c8ca  jz      loc_14000C6EA
0x14000c8d0  call    cs:__imp_KeGetCurrentIrql
0x14000c8d7  nop     dword ptr [rax+rax+00h]
0x14000c8dc  test    al, al
0x14000c8de  jnz     loc_14000C98B
0x14000c8e4  mov     rbp, [r12+48h]
0x14000c8e9  test    rbp, rbp
0x14000c8ec  jz      loc_14000C705
0x14000c8f2  mov     rax, 0FFFFF78000000008h
0x14000c8fc  mov     r10, [rax]
0x14000c8ff  mov     rax, [r12+40h]
0x14000c904  mov     rdx, [rbp+30h]
0x14000c908  test    rax, rax
0x14000c90b  jnz     loc_14000CAD4
0x14000c911  xor     r8d, r8d
0x14000c914  test    rdx, rdx
0x14000c917  jz      loc_14000C705
0x14000c91d  mov     eax, [rdx+8]
0x14000c920  test    al, 20h
0x14000c922  jnz     loc_14000CA49
0x14000c928  test    al, 40h
0x14000c92a  jnz     loc_14000CA49
0x14000c930  test    r8, r8
0x14000c933  jnz     loc_14000CA8F
0x14000c939  mov     rax, [rsp+0F8h+var_80]
0x14000c93e  mov     rax, [rax+1A8h]
0x14000c945  mov     ecx, [rax+0B0h]
0x14000c94b  test    cl, cl
0x14000c94d  js      loc_14000CBC3
0x14000c953  cmp     [rsp+0F8h+var_88], esi
0x14000c957  jnz     loc_14000CBFA
0x14000c95d  movzx   eax, byte ptr [r13+2E1h]
0x14000c965  and     al, 3
0x14000c967  cmp     al, 2
0x14000c969  jnz     loc_14000CC43
0x14000c96f  cmp     dword ptr [rbx+2Ch], 3
0x14000c973  jnb     loc_14000CC88
  ... truncated ...
```
