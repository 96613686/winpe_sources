# ValidateGpuMmuCaps

- ea: `0x1400d241c`
- end: `0x1400d2835`
- name: `ValidateGpuMmuCaps`
- size: `1049`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400d1c2c`

## callees

- `0x140004268`
- `0x1400d241c`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x1400d2463`
- `watchdog!WdLogSingleEntry2` at `0x1400d27a6`
- `watchdog!WdLogSingleEntry2` at `0x1400d27e9`
- `watchdog!WdLogSingleEntry2` at `0x1400d2463`
- `watchdog!WdLogSingleEntry2` at `0x1400d27a6`
- `watchdog!WdLogSingleEntry2` at `0x1400d27e9`
- `watchdog!WdLogSingleEntry0` at `0x1400d2641`
- `watchdog!WdLogSingleEntry0` at `0x1400d2641`
- `watchdog!WdLogSingleEntry1` at `0x1400d24b3`
- `watchdog!WdLogSingleEntry1` at `0x1400d24f1`
- `watchdog!WdLogSingleEntry1` at `0x1400d2539`
- `watchdog!WdLogSingleEntry1` at `0x1400d257e`
- `watchdog!WdLogSingleEntry1` at `0x1400d25c3`
- `watchdog!WdLogSingleEntry1` at `0x1400d2608`
- `watchdog!WdLogSingleEntry1` at `0x1400d269e`
- `watchdog!WdLogSingleEntry1` at `0x1400d2725`
- `watchdog!WdLogSingleEntry1` at `0x1400d2762`
- `watchdog!WdLogSingleEntry1` at `0x1400d24b3`
- `watchdog!WdLogSingleEntry1` at `0x1400d24f1`
- `watchdog!WdLogSingleEntry1` at `0x1400d2539`
- `watchdog!WdLogSingleEntry1` at `0x1400d257e`
- `watchdog!WdLogSingleEntry1` at `0x1400d25c3`
- `watchdog!WdLogSingleEntry1` at `0x1400d2608`
- `watchdog!WdLogSingleEntry1` at `0x1400d269e`
- `watchdog!WdLogSingleEntry1` at `0x1400d2725`
- `watchdog!WdLogSingleEntry1` at `0x1400d2762`

## string_xrefs

- `0x1400d2652`: `CachedPageTables can only be used with DXGK_PAGETABLEUPDATE_CPU_VIRTUAL update mode`
- `0x1400d26af`: `GpuMmu.PageTableUpdateMode is invalid`
- `0x1400d2773`: `The number of bits in page directory levels is inconsistent with virtual address bit count`
- `0x1400d27b7`: `VirtualAddressBitCount from the caps is different from computed using PageDirectoryIndexBitCount`

## pseudocode

```c
char __fastcall ValidateGpuMmuCaps(__int64 a1, _DWORD *a2)
{
  unsigned int v4; // ecx
  unsigned int v5; // r11d
  __int64 v6; // rsi
  int v7; // edx
  __int64 v8; // rbx
  int v9; // ecx
  int v10; // r8d
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  const wchar_t *v14; // r9
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // ecx
  __int64 v20; // rdx
  unsigned int i; // r8d
  unsigned int v22; // r9d
  __int64 v23; // rsi
  __int64 v24; // rbx
  int v25; // ecx
  int v26; // r8d
  __int64 v27; // rbx
  __int64 v28; // rdi
  int v29; // ecx
  int v30; // r8d
  __int64 v32; // rbx
  __int64 v33; // [rsp+28h] [rbp-50h]

  v4 = 0;
  v5 = *(_DWORD *)(a1 + 1340);
  while ( v4 <= v5 )
  {
    v6 = v4;
    v7 = a2[5 * v4 + 10];
    if ( ((v7 - 1) & v7) != 0 )
    {
      v8 = (unsigned int)a2[5 * v4 + 10];
      WdLogSingleEntry2(1, v4, v8);
      WdLogGlobalForLineNumber = 156;
      DxgkLogInternalTriageEvent(
        v9,
        0x40000,
        v10,
        (unsigned int)L"PageTableLevelDesc[%u].PageTableAlignmentInBytes must be aligned to a power of two. Value=%u",
        v6,
        v8,
        0,
        0);
      return 0;
    }
    ++v4;
  }
  if ( (*a2 & 0x80u) != 0 )
  {
    v11 = a2[3];
    if ( !v11 || (v11 & 0xFFF) != 0 )
    {
      WdLogSingleEntry1(1, (unsigned int)a2[3]);
      v14 = L"GpuMmuCaps.LeafPageTableSizeFor64KPagesInBytes must be multiple of 4 KB when dual PTE is supported.";
      WdLogGlobalForLineNumber = 168;
      v15 = (unsigned int)a2[3];
      v33 = 0;
LABEL_42:
      DxgkLogInternalTriageEvent(v12, 0x40000, v13, (_DWORD)v14, v15, v33, 0, 0);
      return 0;
    }
  }
  if ( !a2[9] )
  {
    WdLogSingleEntry1(1, 0);
    v14 = L"Page table size cannot be zero";
    WdLogGlobalForLineNumber = 177;
    v15 = (unsigned int)a2[9];
    v33 = 0;
    goto LABEL_42;
  }
  v16 = *(_DWORD *)(a1 + 932);
  if ( a2[7] > v16 )
  {
    WdLogSingleEntry1(1, *(unsigned int *)(a1 + 944));
    v14 = L"PageTableSegmentId, specified by the driver, is invalid";
    WdLogGlobalForLineNumber = 185;
    v15 = *(unsigned int *)(a1 + 944);
    v33 = 0;
    goto LABEL_42;
  }
  if ( a2[12] > v16 )
  {
    WdLogSingleEntry1(1, *(unsigned int *)(a1 + 960));
    v14 = L"PageTableSegmentId, specified by the driver is invalid";
    WdLogGlobalForLineNumber = 193;
    v15 = *(unsigned int *)(a1 + 960);
    v33 = 0;
    goto LABEL_42;
  }
  if ( a2[8] > v16 )
  {
    WdLogSingleEntry1(1, *(unsigned int *)(a1 + 952));
    WdLogGlobalForLineNumber = 201;
    v15 = *(unsigned int *)(a1 + 952);
LABEL_18:
    v14 = L"PagingProcessPageTableSegmentId, specified by the driver, is invalid";
    v33 = 0;
    goto LABEL_42;
  }
  if ( a2[13] > v16 )
  {
    WdLogSingleEntry1(1, *(unsigned int *)(a1 + 968));
    WdLogGlobalForLineNumber = 209;
    v15 = *(unsigned int *)(a1 + 968);
    goto LABEL_18;
  }
  v17 = *(_QWORD *)(a1 + 56);
  if ( *(_DWORD *)(v17 + 40) >= 0x10002u && (*a2 & 0x1000) != 0 && a2[1] )
  {
    WdLogSingleEntry0(1);
    v14 = L"CachedPageTables can only be used with DXGK_PAGETABLEUPDATE_CPU_VIRTUAL update mode";
    v15 = 219;
    WdLogGlobalForLineNumber = 219;
    v33 = 0;
    goto LABEL_42;
  }
  v18 = a2[6];
  v19 = *(_DWORD *)(v17 + 37216) - 12;
  if ( !v18 || v18 >= v19 )
  {
    v32 = v19;
    WdLogSingleEntry2(1, (unsigned int)a2[6], v19);
    v14 = L"GpuMmuCaps.PageTableIndexBitCount is invalid";
    WdLogGlobalForLineNumber = 232;
    v15 = (unsigned int)a2[6];
    v33 = v32;
    goto LABEL_42;
  }
  if ( a2[1] > 2u )
  {
    WdLogSingleEntry1(1, (int)a2[1]);
    v14 = L"GpuMmu.PageTableUpdateMode is invalid";
    WdLogGlobalForLineNumber = 242;
    v15 = (int)a2[1];
    v33 = 0;
    goto LABEL_42;
  }
  if ( v5 <= 1 )
    return 1;
  v20 = *(unsigned int *)(a1 + 1004);
  for ( i = 1; i <= v5; ++i )
  {
    v22 = a2[5 * i + 6];
    if ( !v22 || v22 > v19 - (unsigned int)v20 )
    {
      v24 = (unsigned int)a2[5 * i + 6];
      WdLogSingleEntry1(1, v24);
      WdLogGlobalForLineNumber = 261;
      DxgkLogInternalTriageEvent(
        v25,
        0x40000,
        v26,
        (unsigned int)L"The number of bits in page directory levels is inconsistent with virtual address bit count",
        v24,
        0,
        0,
        0);
      return 0;
    }
    v23 = 6 * (i + 21LL);
    if ( !*(_DWORD *)(a1 + 48 * (i + 21LL)) )
    {
      WdLogSingleEntry1(1, 0);
      v14 = L"Invalid page table size";
      WdLogGlobalForLineNumber = 271;
      v15 = *(unsigned int *)(a1 + 8 * v23);
      v33 = 0;
      goto LABEL_42;
    }
    v20 = v22 + (unsigned int)v20;
  }
  if ( (_DWORD)v20 == v19 )
    return 1;
  v27 = v19;
  v28 = (unsigned int)v20;
  WdLogSingleEntry2(1, v20, v19);
  WdLogGlobalForLineNumber = 281;
  DxgkLogInternalTriageEvent(
    v29,
    0x40000,
    v30,
    (unsigned int)L"VirtualAddressBitCount from the caps is different from computed using PageDirectoryIndexBitCount",
    v28,
    v27,
    0,
    0);
  return 0;
}

```

## disassembly

```asm
0x1400d241c  push    rbx
0x1400d241e  push    rbp
0x1400d241f  push    rsi
0x1400d2420  push    rdi
0x1400d2421  push    r14
0x1400d2423  sub     rsp, 50h
0x1400d2427  mov     rbx, rcx
0x1400d242a  xor     ebp, ebp
0x1400d242c  mov     rdi, rdx
0x1400d242f  mov     ecx, ebp
0x1400d2431  mov     r11d, [rbx+53Ch]
0x1400d2438  lea     r14d, [rbp+1]
0x1400d243c  cmp     ecx, r11d
0x1400d243f  ja      short loc_1400D2499
0x1400d2441  mov     esi, ecx
0x1400d2443  lea     rax, [rsi+rsi*4]
0x1400d2447  mov     edx, [rdi+rax*4+28h]
0x1400d244b  lea     eax, [rdx-1]
0x1400d244e  test    edx, eax
0x1400d2450  jnz     short loc_1400D2457
0x1400d2452  add     ecx, r14d
0x1400d2455  jmp     short loc_1400D243C
0x1400d2457  mov     rbx, rdx
0x1400d245a  mov     r8, rdx
0x1400d245d  mov     rdx, rsi
0x1400d2460  mov     ecx, r14d
0x1400d2463  call    cs:__imp_WdLogSingleEntry2
0x1400d246a  nop     dword ptr [rax+rax+00h]
0x1400d246f  mov     [rsp+78h+var_40], rbp
0x1400d2474  lea     r9, aPagetablelevel; "PageTableLevelDesc[%u].PageTableAlignme"...
0x1400d247b  mov     [rsp+78h+var_48], rbp
0x1400d2480  mov     [rsp+78h+var_50], rbx
0x1400d2485  mov     [rsp+78h+var_58], rsi
0x1400d248a  mov     cs:WdLogGlobalForLineNumber, 9Ch
0x1400d2494  jmp     loc_1400D281D
0x1400d2499  mov     edx, [rdi]
0x1400d249b  test    dl, dl
0x1400d249d  jns     short loc_1400D24E7
0x1400d249f  mov     eax, [rdi+0Ch]
0x1400d24a2  test    eax, eax
0x1400d24a4  jz      short loc_1400D24AD
0x1400d24a6  test    eax, 0FFFh
0x1400d24ab  jz      short loc_1400D24E7
0x1400d24ad  mov     rdx, rax
0x1400d24b0  mov     ecx, r14d
0x1400d24b3  call    cs:__imp_WdLogSingleEntry1
0x1400d24ba  nop     dword ptr [rax+rax+00h]
0x1400d24bf  mov     [rsp+78h+var_40], rbp
0x1400d24c4  lea     r9, aGpummucapsLeaf; "GpuMmuCaps.LeafPageTableSizeFor64KPages"...
0x1400d24cb  mov     [rsp+78h+var_48], rbp
0x1400d24d0  mov     cs:WdLogGlobalForLineNumber, 0A8h
0x1400d24da  mov     eax, [rdi+0Ch]
0x1400d24dd  mov     [rsp+78h+var_50], rbp
0x1400d24e2  jmp     loc_1400D2818
0x1400d24e7  cmp     [rdi+24h], ebp
0x1400d24ea  jnz     short loc_1400D2525
0x1400d24ec  xor     edx, edx
0x1400d24ee  mov     ecx, r14d
0x1400d24f1  call    cs:__imp_WdLogSingleEntry1
0x1400d24f8  nop     dword ptr [rax+rax+00h]
0x1400d24fd  mov     [rsp+78h+var_40], rbp
0x1400d2502  lea     r9, aPageTableSizeC; "Page table size cannot be zero"
0x1400d2509  mov     [rsp+78h+var_48], rbp
0x1400d250e  mov     cs:WdLogGlobalForLineNumber, 0B1h
0x1400d2518  mov     eax, [rdi+24h]
0x1400d251b  mov     [rsp+78h+var_50], rbp
0x1400d2520  jmp     loc_1400D2818
0x1400d2525  mov     eax, [rbx+3A4h]
0x1400d252b  cmp     [rdi+1Ch], eax
0x1400d252e  jbe     short loc_1400D2570
0x1400d2530  mov     edx, [rbx+3B0h]
0x1400d2536  mov     ecx, r14d
0x1400d2539  call    cs:__imp_WdLogSingleEntry1
0x1400d2540  nop     dword ptr [rax+rax+00h]
0x1400d2545  mov     [rsp+78h+var_40], rbp
0x1400d254a  lea     r9, aPagetablesegme_0; "PageTableSegmentId, specified by the dr"...
0x1400d2551  mov     [rsp+78h+var_48], rbp
0x1400d2556  mov     cs:WdLogGlobalForLineNumber, 0B9h
0x1400d2560  mov     eax, [rbx+3B0h]
0x1400d2566  mov     [rsp+78h+var_50], rbp
0x1400d256b  jmp     loc_1400D2818
0x1400d2570  cmp     [rdi+30h], eax
0x1400d2573  jbe     short loc_1400D25B5
0x1400d2575  mov     edx, [rbx+3C0h]
0x1400d257b  mov     ecx, r14d
0x1400d257e  call    cs:__imp_WdLogSingleEntry1
0x1400d2585  nop     dword ptr [rax+rax+00h]
0x1400d258a  mov     [rsp+78h+var_40], rbp
0x1400d258f  lea     r9, aPagetablesegme; "PageTableSegmentId, specified by the dr"...
0x1400d2596  mov     [rsp+78h+var_48], rbp
0x1400d259b  mov     cs:WdLogGlobalForLineNumber, 0C1h
0x1400d25a5  mov     eax, [rbx+3C0h]
0x1400d25ab  mov     [rsp+78h+var_50], rbp
0x1400d25b0  jmp     loc_1400D2818
0x1400d25b5  cmp     [rdi+20h], eax
0x1400d25b8  jbe     short loc_1400D25FA
0x1400d25ba  mov     edx, [rbx+3B8h]
0x1400d25c0  mov     ecx, r14d
0x1400d25c3  call    cs:__imp_WdLogSingleEntry1
0x1400d25ca  nop     dword ptr [rax+rax+00h]
0x1400d25cf  mov     cs:WdLogGlobalForLineNumber, 0C9h
0x1400d25d9  mov     eax, [rbx+3B8h]
0x1400d25df  mov     [rsp+78h+var_40], rbp
0x1400d25e4  lea     r9, aPagingprocessp; "PagingProcessPageTableSegmentId, specif"...
0x1400d25eb  mov     [rsp+78h+var_48], rbp
0x1400d25f0  mov     [rsp+78h+var_50], rbp
0x1400d25f5  jmp     loc_1400D2818
0x1400d25fa  cmp     [rdi+34h], eax
0x1400d25fd  jbe     short loc_1400D2626
0x1400d25ff  mov     edx, [rbx+3C8h]
0x1400d2605  mov     ecx, r14d
0x1400d2608  call    cs:__imp_WdLogSingleEntry1
0x1400d260f  nop     dword ptr [rax+rax+00h]
0x1400d2614  mov     cs:WdLogGlobalForLineNumber, 0D1h
0x1400d261e  mov     eax, [rbx+3C8h]
0x1400d2624  jmp     short loc_1400D25DF
0x1400d2626  mov     rcx, [rbx+38h]
0x1400d262a  cmp     dword ptr [rcx+28h], 10002h
0x1400d2631  jb      short loc_1400D2673
0x1400d2633  bt      edx, 0Ch
0x1400d2637  jnb     short loc_1400D2673
0x1400d2639  cmp     [rdi+4], ebp
0x1400d263c  jz      short loc_1400D2673
0x1400d263e  mov     ecx, r14d
0x1400d2641  call    cs:__imp_WdLogSingleEntry0
0x1400d2648  nop     dword ptr [rax+rax+00h]
0x1400d264d  mov     [rsp+78h+var_40], rbp
0x1400d2652  lea     r9, aCachedpagetabl; "CachedPageTables can only be used with "...
0x1400d2659  mov     eax, 0DBh
0x1400d265e  mov     [rsp+78h+var_48], rbp
0x1400d2663  mov     cs:WdLogGlobalForLineNumber, eax
0x1400d2669  mov     [rsp+78h+var_50], rbp
0x1400d266e  jmp     loc_1400D2818
0x1400d2673  mov     ecx, [rcx+9160h]
0x1400d2679  mov     eax, [rdi+18h]
0x1400d267c  sub     ecx, 0Ch
0x1400d267f  test    eax, eax
0x1400d2681  jz      loc_1400D27DE
0x1400d2687  cmp     eax, ecx
0x1400d2689  jnb     loc_1400D27DE
0x1400d268f  movsxd  rax, dword ptr [rdi+4]
0x1400d2693  cmp     eax, 2
0x1400d2696  jbe     short loc_1400D26D3
0x1400d2698  mov     rdx, rax
0x1400d269b  mov     ecx, r14d
0x1400d269e  call    cs:__imp_WdLogSingleEntry1
0x1400d26a5  nop     dword ptr [rax+rax+00h]
0x1400d26aa  mov     [rsp+78h+var_40], rbp
0x1400d26af  lea     r9, aGpummuPagetabl; "GpuMmu.PageTableUpdateMode is invalid"
0x1400d26b6  mov     [rsp+78h+var_48], rbp
0x1400d26bb  mov     cs:WdLogGlobalForLineNumber, 0F2h
0x1400d26c5  movsxd  rax, dword ptr [rdi+4]
0x1400d26c9  mov     [rsp+78h+var_50], rbp
0x1400d26ce  jmp     loc_1400D2818
0x1400d26d3  cmp     r11d, r14d
0x1400d26d6  jbe     loc_1400D27D9
0x1400d26dc  mov     edx, [rbx+3ECh]
0x1400d26e2  mov     r8d, r14d
0x1400d26e5  cmp     r8d, r11d
0x1400d26e8  ja      loc_1400D2798
0x1400d26ee  mov     r10d, r8d
0x1400d26f1  lea     rax, [r10+r10*4]
0x1400d26f5  mov     r9d, [rdi+rax*4+18h]
0x1400d26fa  test    r9d, r9d
0x1400d26fd  jz      short loc_1400D2759
0x1400d26ff  mov     eax, ecx
0x1400d2701  sub     eax, edx
0x1400d2703  cmp     r9d, eax
0x1400d2706  ja      short loc_1400D2759
0x1400d2708  lea     rsi, [r10+15h]
0x1400d270c  lea     rsi, [rsi+rsi*2]
0x1400d2710  add     rsi, rsi
0x1400d2713  cmp     [rbx+rsi*8], ebp
0x1400d2716  jz      short loc_1400D2720
0x1400d2718  add     edx, r9d
0x1400d271b  add     r8d, r14d
0x1400d271e  jmp     short loc_1400D26E5
0x1400d2720  xor     edx, edx
0x1400d2722  mov     ecx, r14d
0x1400d2725  call    cs:__imp_WdLogSingleEntry1
0x1400d272c  nop     dword ptr [rax+rax+00h]
0x1400d2731  mov     [rsp+78h+var_40], rbp
0x1400d2736  lea     r9, aInvalidPageTab; "Invalid page table size"
0x1400d273d  mov     [rsp+78h+var_48], rbp
0x1400d2742  mov     cs:WdLogGlobalForLineNumber, 10Fh
0x1400d274c  mov     eax, [rbx+rsi*8]
0x1400d274f  mov     [rsp+78h+var_50], rbp
0x1400d2754  jmp     loc_1400D2818
0x1400d2759  mov     rdx, r9
0x1400d275c  mov     ecx, r14d
0x1400d275f  mov     rbx, r9
0x1400d2762  call    cs:__imp_WdLogSingleEntry1
0x1400d2769  nop     dword ptr [rax+rax+00h]
0x1400d276e  mov     [rsp+78h+var_40], rbp
0x1400d2773  lea     r9, aTheNumberOfBit; "The number of bits in page directory le"...
0x1400d277a  mov     [rsp+78h+var_48], rbp
0x1400d277f  mov     [rsp+78h+var_50], rbp
0x1400d2784  mov     [rsp+78h+var_58], rbx
0x1400d2789  mov     cs:WdLogGlobalForLineNumber, 105h
0x1400d2793  jmp     loc_1400D281D
0x1400d2798  cmp     edx, ecx
0x1400d279a  jz      short loc_1400D27D9
0x1400d279c  mov     ebx, ecx
0x1400d279e  mov     r8d, ecx
0x1400d27a1  mov     ecx, r14d
0x1400d27a4  mov     edi, edx
0x1400d27a6  call    cs:__imp_WdLogSingleEntry2
0x1400d27ad  nop     dword ptr [rax+rax+00h]
0x1400d27b2  mov     [rsp+78h+var_40], rbp
0x1400d27b7  lea     r9, aVirtualaddress; "VirtualAddressBitCount from the caps is"...
0x1400d27be  mov     [rsp+78h+var_48], rbp
0x1400d27c3  mov     [rsp+78h+var_50], rbx
0x1400d27c8  mov     [rsp+78h+var_58], rdi
0x1400d27cd  mov     cs:WdLogGlobalForLineNumber, 119h
0x1400d27d7  jmp     short loc_1400D281D
0x1400d27d9  mov     al, r14b
0x1400d27dc  jmp     short loc_1400D2829
0x1400d27de  mov     ebx, ecx
0x1400d27e0  mov     rdx, rax
0x1400d27e3  mov     r8d, ecx
0x1400d27e6  mov     ecx, r14d
0x1400d27e9  call    cs:__imp_WdLogSingleEntry2
0x1400d27f0  nop     dword ptr [rax+rax+00h]
0x1400d27f5  mov     [rsp+78h+var_40], rbp
0x1400d27fa  lea     r9, aGpummucapsPage; "GpuMmuCaps.PageTableIndexBitCount is in"...
0x1400d2801  mov     [rsp+78h+var_48], rbp
0x1400d2806  mov     cs:WdLogGlobalForLineNumber, 0E8h
0x1400d2810  mov     eax, [rdi+18h]
0x1400d2813  mov     [rsp+78h+var_50], rbx
0x1400d2818  mov     [rsp+78h+var_58], rax
0x1400d281d  mov     edx, 40000h
0x1400d2822  call    DxgkLogInternalTriageEvent
0x1400d2827  xor     al, al
0x1400d2829  add     rsp, 50h
0x1400d282d  pop     r14
0x1400d282f  pop     rdi
0x1400d2830  pop     rsi
0x1400d2831  pop     rbp
0x1400d2832  pop     rbx
0x1400d2833  retn
```
