# ValidateGpuMmuCaps

- ea: `0x1400cc588`
- end: `0x1400cc9a5`
- name: `ValidateGpuMmuCaps`
- size: `1053`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400cbd1c`

## callees

- `0x1400045ec`
- `0x1400cc588`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x1400cc5cf`
- `watchdog!WdLogSingleEntry2` at `0x1400cc916`
- `watchdog!WdLogSingleEntry2` at `0x1400cc959`
- `watchdog!WdLogSingleEntry2` at `0x1400cc5cf`
- `watchdog!WdLogSingleEntry2` at `0x1400cc916`
- `watchdog!WdLogSingleEntry2` at `0x1400cc959`
- `watchdog!WdLogSingleEntry0` at `0x1400cc7ad`
- `watchdog!WdLogSingleEntry0` at `0x1400cc7ad`
- `watchdog!WdLogSingleEntry1` at `0x1400cc61f`
- `watchdog!WdLogSingleEntry1` at `0x1400cc65d`
- `watchdog!WdLogSingleEntry1` at `0x1400cc6a5`
- `watchdog!WdLogSingleEntry1` at `0x1400cc6ea`
- `watchdog!WdLogSingleEntry1` at `0x1400cc72f`
- `watchdog!WdLogSingleEntry1` at `0x1400cc774`
- `watchdog!WdLogSingleEntry1` at `0x1400cc80a`
- `watchdog!WdLogSingleEntry1` at `0x1400cc891`
- `watchdog!WdLogSingleEntry1` at `0x1400cc8d2`
- `watchdog!WdLogSingleEntry1` at `0x1400cc61f`
- `watchdog!WdLogSingleEntry1` at `0x1400cc65d`
- `watchdog!WdLogSingleEntry1` at `0x1400cc6a5`
- `watchdog!WdLogSingleEntry1` at `0x1400cc6ea`
- `watchdog!WdLogSingleEntry1` at `0x1400cc72f`
- `watchdog!WdLogSingleEntry1` at `0x1400cc774`
- `watchdog!WdLogSingleEntry1` at `0x1400cc80a`
- `watchdog!WdLogSingleEntry1` at `0x1400cc891`
- `watchdog!WdLogSingleEntry1` at `0x1400cc8d2`

## string_xrefs

- `0x1400cc7be`: `CachedPageTables can only be used with DXGK_PAGETABLEUPDATE_CPU_VIRTUAL update mode`
- `0x1400cc81b`: `GpuMmu.PageTableUpdateMode is invalid`
- `0x1400cc8e3`: `The number of bits in page directory levels is inconsistent with virtual address bit count`
- `0x1400cc927`: `VirtualAddressBitCount from the caps is different from computed using PageDirectoryIndexBitCount`

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
  v5 = *(_DWORD *)(a1 + 1076);
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
  v16 = *(_DWORD *)(a1 + 668);
  if ( a2[7] > v16 )
  {
    WdLogSingleEntry1(1, *(unsigned int *)(a1 + 680));
    v14 = L"PageTableSegmentId, specified by the driver, is invalid";
    WdLogGlobalForLineNumber = 185;
    v15 = *(unsigned int *)(a1 + 680);
    v33 = 0;
    goto LABEL_42;
  }
  if ( a2[12] > v16 )
  {
    WdLogSingleEntry1(1, *(unsigned int *)(a1 + 696));
    v14 = L"PageTableSegmentId, specified by the driver is invalid";
    WdLogGlobalForLineNumber = 193;
    v15 = *(unsigned int *)(a1 + 696);
    v33 = 0;
    goto LABEL_42;
  }
  if ( a2[8] > v16 )
  {
    WdLogSingleEntry1(1, *(unsigned int *)(a1 + 688));
    WdLogGlobalForLineNumber = 201;
    v15 = *(unsigned int *)(a1 + 688);
LABEL_18:
    v14 = L"PagingProcessPageTableSegmentId, specified by the driver, is invalid";
    v33 = 0;
    goto LABEL_42;
  }
  if ( a2[13] > v16 )
  {
    WdLogSingleEntry1(1, *(unsigned int *)(a1 + 704));
    WdLogGlobalForLineNumber = 209;
    v15 = *(unsigned int *)(a1 + 704);
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
  v20 = *(unsigned int *)(a1 + 740);
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
    v23 = 6LL * i;
    if ( !*(_DWORD *)(a1 + 48LL * i + 744) )
    {
      WdLogSingleEntry1(1, 0);
      v14 = L"Invalid page table size";
      WdLogGlobalForLineNumber = 271;
      v15 = *(unsigned int *)(a1 + 8 * v23 + 744);
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
0x1400cc588  push    rbx
0x1400cc58a  push    rbp
0x1400cc58b  push    rsi
0x1400cc58c  push    rdi
0x1400cc58d  push    r14
0x1400cc58f  sub     rsp, 50h
0x1400cc593  mov     rbx, rcx
0x1400cc596  xor     ebp, ebp
0x1400cc598  mov     rdi, rdx
0x1400cc59b  mov     ecx, ebp
0x1400cc59d  mov     r11d, [rbx+434h]
0x1400cc5a4  lea     r14d, [rbp+1]
0x1400cc5a8  cmp     ecx, r11d
0x1400cc5ab  ja      short loc_1400CC605
0x1400cc5ad  mov     esi, ecx
0x1400cc5af  lea     rax, [rsi+rsi*4]
0x1400cc5b3  mov     edx, [rdi+rax*4+28h]
0x1400cc5b7  lea     eax, [rdx-1]
0x1400cc5ba  test    edx, eax
0x1400cc5bc  jnz     short loc_1400CC5C3
0x1400cc5be  add     ecx, r14d
0x1400cc5c1  jmp     short loc_1400CC5A8
0x1400cc5c3  mov     rbx, rdx
0x1400cc5c6  mov     r8, rdx
0x1400cc5c9  mov     rdx, rsi
0x1400cc5cc  mov     ecx, r14d
0x1400cc5cf  call    cs:__imp_WdLogSingleEntry2
0x1400cc5d6  nop     dword ptr [rax+rax+00h]
0x1400cc5db  mov     [rsp+78h+var_40], rbp
0x1400cc5e0  lea     r9, aPagetablelevel; "PageTableLevelDesc[%u].PageTableAlignme"...
0x1400cc5e7  mov     [rsp+78h+var_48], rbp
0x1400cc5ec  mov     [rsp+78h+var_50], rbx
0x1400cc5f1  mov     [rsp+78h+var_58], rsi
0x1400cc5f6  mov     cs:WdLogGlobalForLineNumber, 9Ch
0x1400cc600  jmp     loc_1400CC98D
0x1400cc605  mov     edx, [rdi]
0x1400cc607  test    dl, dl
0x1400cc609  jns     short loc_1400CC653
0x1400cc60b  mov     eax, [rdi+0Ch]
0x1400cc60e  test    eax, eax
0x1400cc610  jz      short loc_1400CC619
0x1400cc612  test    eax, 0FFFh
0x1400cc617  jz      short loc_1400CC653
0x1400cc619  mov     rdx, rax
0x1400cc61c  mov     ecx, r14d
0x1400cc61f  call    cs:__imp_WdLogSingleEntry1
0x1400cc626  nop     dword ptr [rax+rax+00h]
0x1400cc62b  mov     [rsp+78h+var_40], rbp
0x1400cc630  lea     r9, aGpummucapsLeaf; "GpuMmuCaps.LeafPageTableSizeFor64KPages"...
0x1400cc637  mov     [rsp+78h+var_48], rbp
0x1400cc63c  mov     cs:WdLogGlobalForLineNumber, 0A8h
0x1400cc646  mov     eax, [rdi+0Ch]
0x1400cc649  mov     [rsp+78h+var_50], rbp
0x1400cc64e  jmp     loc_1400CC988
0x1400cc653  cmp     [rdi+24h], ebp
0x1400cc656  jnz     short loc_1400CC691
0x1400cc658  xor     edx, edx
0x1400cc65a  mov     ecx, r14d
0x1400cc65d  call    cs:__imp_WdLogSingleEntry1
0x1400cc664  nop     dword ptr [rax+rax+00h]
0x1400cc669  mov     [rsp+78h+var_40], rbp
0x1400cc66e  lea     r9, aPageTableSizeC; "Page table size cannot be zero"
0x1400cc675  mov     [rsp+78h+var_48], rbp
0x1400cc67a  mov     cs:WdLogGlobalForLineNumber, 0B1h
0x1400cc684  mov     eax, [rdi+24h]
0x1400cc687  mov     [rsp+78h+var_50], rbp
0x1400cc68c  jmp     loc_1400CC988
0x1400cc691  mov     eax, [rbx+29Ch]
0x1400cc697  cmp     [rdi+1Ch], eax
0x1400cc69a  jbe     short loc_1400CC6DC
0x1400cc69c  mov     edx, [rbx+2A8h]
0x1400cc6a2  mov     ecx, r14d
0x1400cc6a5  call    cs:__imp_WdLogSingleEntry1
0x1400cc6ac  nop     dword ptr [rax+rax+00h]
0x1400cc6b1  mov     [rsp+78h+var_40], rbp
0x1400cc6b6  lea     r9, aPagetablesegme_0; "PageTableSegmentId, specified by the dr"...
0x1400cc6bd  mov     [rsp+78h+var_48], rbp
0x1400cc6c2  mov     cs:WdLogGlobalForLineNumber, 0B9h
0x1400cc6cc  mov     eax, [rbx+2A8h]
0x1400cc6d2  mov     [rsp+78h+var_50], rbp
0x1400cc6d7  jmp     loc_1400CC988
0x1400cc6dc  cmp     [rdi+30h], eax
0x1400cc6df  jbe     short loc_1400CC721
0x1400cc6e1  mov     edx, [rbx+2B8h]
0x1400cc6e7  mov     ecx, r14d
0x1400cc6ea  call    cs:__imp_WdLogSingleEntry1
0x1400cc6f1  nop     dword ptr [rax+rax+00h]
0x1400cc6f6  mov     [rsp+78h+var_40], rbp
0x1400cc6fb  lea     r9, aPagetablesegme; "PageTableSegmentId, specified by the dr"...
0x1400cc702  mov     [rsp+78h+var_48], rbp
0x1400cc707  mov     cs:WdLogGlobalForLineNumber, 0C1h
0x1400cc711  mov     eax, [rbx+2B8h]
0x1400cc717  mov     [rsp+78h+var_50], rbp
0x1400cc71c  jmp     loc_1400CC988
0x1400cc721  cmp     [rdi+20h], eax
0x1400cc724  jbe     short loc_1400CC766
0x1400cc726  mov     edx, [rbx+2B0h]
0x1400cc72c  mov     ecx, r14d
0x1400cc72f  call    cs:__imp_WdLogSingleEntry1
0x1400cc736  nop     dword ptr [rax+rax+00h]
0x1400cc73b  mov     cs:WdLogGlobalForLineNumber, 0C9h
0x1400cc745  mov     eax, [rbx+2B0h]
0x1400cc74b  mov     [rsp+78h+var_40], rbp
0x1400cc750  lea     r9, aPagingprocessp; "PagingProcessPageTableSegmentId, specif"...
0x1400cc757  mov     [rsp+78h+var_48], rbp
0x1400cc75c  mov     [rsp+78h+var_50], rbp
0x1400cc761  jmp     loc_1400CC988
0x1400cc766  cmp     [rdi+34h], eax
0x1400cc769  jbe     short loc_1400CC792
0x1400cc76b  mov     edx, [rbx+2C0h]
0x1400cc771  mov     ecx, r14d
0x1400cc774  call    cs:__imp_WdLogSingleEntry1
0x1400cc77b  nop     dword ptr [rax+rax+00h]
0x1400cc780  mov     cs:WdLogGlobalForLineNumber, 0D1h
0x1400cc78a  mov     eax, [rbx+2C0h]
0x1400cc790  jmp     short loc_1400CC74B
0x1400cc792  mov     rcx, [rbx+38h]
0x1400cc796  cmp     dword ptr [rcx+28h], 10002h
0x1400cc79d  jb      short loc_1400CC7DF
0x1400cc79f  bt      edx, 0Ch
0x1400cc7a3  jnb     short loc_1400CC7DF
0x1400cc7a5  cmp     [rdi+4], ebp
0x1400cc7a8  jz      short loc_1400CC7DF
0x1400cc7aa  mov     ecx, r14d
0x1400cc7ad  call    cs:__imp_WdLogSingleEntry0
0x1400cc7b4  nop     dword ptr [rax+rax+00h]
0x1400cc7b9  mov     [rsp+78h+var_40], rbp
0x1400cc7be  lea     r9, aCachedpagetabl; "CachedPageTables can only be used with "...
0x1400cc7c5  mov     eax, 0DBh
0x1400cc7ca  mov     [rsp+78h+var_48], rbp
0x1400cc7cf  mov     cs:WdLogGlobalForLineNumber, eax
0x1400cc7d5  mov     [rsp+78h+var_50], rbp
0x1400cc7da  jmp     loc_1400CC988
0x1400cc7df  mov     ecx, [rcx+9160h]
0x1400cc7e5  mov     eax, [rdi+18h]
0x1400cc7e8  sub     ecx, 0Ch
0x1400cc7eb  test    eax, eax
0x1400cc7ed  jz      loc_1400CC94E
0x1400cc7f3  cmp     eax, ecx
0x1400cc7f5  jnb     loc_1400CC94E
0x1400cc7fb  movsxd  rax, dword ptr [rdi+4]
0x1400cc7ff  cmp     eax, 2
0x1400cc802  jbe     short loc_1400CC83F
0x1400cc804  mov     rdx, rax
0x1400cc807  mov     ecx, r14d
0x1400cc80a  call    cs:__imp_WdLogSingleEntry1
0x1400cc811  nop     dword ptr [rax+rax+00h]
0x1400cc816  mov     [rsp+78h+var_40], rbp
0x1400cc81b  lea     r9, aGpummuPagetabl; "GpuMmu.PageTableUpdateMode is invalid"
0x1400cc822  mov     [rsp+78h+var_48], rbp
0x1400cc827  mov     cs:WdLogGlobalForLineNumber, 0F2h
0x1400cc831  movsxd  rax, dword ptr [rdi+4]
0x1400cc835  mov     [rsp+78h+var_50], rbp
0x1400cc83a  jmp     loc_1400CC988
0x1400cc83f  cmp     r11d, r14d
0x1400cc842  jbe     loc_1400CC949
0x1400cc848  mov     edx, [rbx+2E4h]
0x1400cc84e  mov     r8d, r14d
0x1400cc851  cmp     r8d, r11d
0x1400cc854  ja      loc_1400CC908
0x1400cc85a  mov     r10d, r8d
0x1400cc85d  lea     rax, [r10+r10*4]
0x1400cc861  mov     r9d, [rdi+rax*4+18h]
0x1400cc866  test    r9d, r9d
0x1400cc869  jz      short loc_1400CC8C9
0x1400cc86b  mov     eax, ecx
0x1400cc86d  sub     eax, edx
0x1400cc86f  cmp     r9d, eax
0x1400cc872  ja      short loc_1400CC8C9
0x1400cc874  lea     rsi, [r10+r10*2]
0x1400cc878  add     rsi, rsi
0x1400cc87b  cmp     [rbx+rsi*8+2E8h], ebp
0x1400cc882  jz      short loc_1400CC88C
0x1400cc884  add     edx, r9d
0x1400cc887  add     r8d, r14d
0x1400cc88a  jmp     short loc_1400CC851
0x1400cc88c  xor     edx, edx
0x1400cc88e  mov     ecx, r14d
0x1400cc891  call    cs:__imp_WdLogSingleEntry1
0x1400cc898  nop     dword ptr [rax+rax+00h]
0x1400cc89d  mov     [rsp+78h+var_40], rbp
0x1400cc8a2  lea     r9, aInvalidPageTab; "Invalid page table size"
0x1400cc8a9  mov     [rsp+78h+var_48], rbp
0x1400cc8ae  mov     cs:WdLogGlobalForLineNumber, 10Fh
0x1400cc8b8  mov     eax, [rbx+rsi*8+2E8h]
0x1400cc8bf  mov     [rsp+78h+var_50], rbp
0x1400cc8c4  jmp     loc_1400CC988
0x1400cc8c9  mov     rdx, r9
0x1400cc8cc  mov     ecx, r14d
0x1400cc8cf  mov     rbx, r9
0x1400cc8d2  call    cs:__imp_WdLogSingleEntry1
0x1400cc8d9  nop     dword ptr [rax+rax+00h]
0x1400cc8de  mov     [rsp+78h+var_40], rbp
0x1400cc8e3  lea     r9, aTheNumberOfBit; "The number of bits in page directory le"...
0x1400cc8ea  mov     [rsp+78h+var_48], rbp
0x1400cc8ef  mov     [rsp+78h+var_50], rbp
0x1400cc8f4  mov     [rsp+78h+var_58], rbx
0x1400cc8f9  mov     cs:WdLogGlobalForLineNumber, 105h
0x1400cc903  jmp     loc_1400CC98D
0x1400cc908  cmp     edx, ecx
0x1400cc90a  jz      short loc_1400CC949
0x1400cc90c  mov     ebx, ecx
0x1400cc90e  mov     r8d, ecx
0x1400cc911  mov     ecx, r14d
0x1400cc914  mov     edi, edx
0x1400cc916  call    cs:__imp_WdLogSingleEntry2
0x1400cc91d  nop     dword ptr [rax+rax+00h]
0x1400cc922  mov     [rsp+78h+var_40], rbp
0x1400cc927  lea     r9, aVirtualaddress; "VirtualAddressBitCount from the caps is"...
0x1400cc92e  mov     [rsp+78h+var_48], rbp
0x1400cc933  mov     [rsp+78h+var_50], rbx
0x1400cc938  mov     [rsp+78h+var_58], rdi
0x1400cc93d  mov     cs:WdLogGlobalForLineNumber, 119h
0x1400cc947  jmp     short loc_1400CC98D
0x1400cc949  mov     al, r14b
0x1400cc94c  jmp     short loc_1400CC999
0x1400cc94e  mov     ebx, ecx
0x1400cc950  mov     rdx, rax
0x1400cc953  mov     r8d, ecx
0x1400cc956  mov     ecx, r14d
0x1400cc959  call    cs:__imp_WdLogSingleEntry2
0x1400cc960  nop     dword ptr [rax+rax+00h]
0x1400cc965  mov     [rsp+78h+var_40], rbp
0x1400cc96a  lea     r9, aGpummucapsPage; "GpuMmuCaps.PageTableIndexBitCount is in"...
0x1400cc971  mov     [rsp+78h+var_48], rbp
0x1400cc976  mov     cs:WdLogGlobalForLineNumber, 0E8h
0x1400cc980  mov     eax, [rdi+18h]
0x1400cc983  mov     [rsp+78h+var_50], rbx
0x1400cc988  mov     [rsp+78h+var_58], rax
0x1400cc98d  mov     edx, 40000h
0x1400cc992  call    DxgkLogInternalTriageEvent
0x1400cc997  xor     al, al
0x1400cc999  add     rsp, 50h
0x1400cc99d  pop     r14
0x1400cc99f  pop     rdi
0x1400cc9a0  pop     rsi
0x1400cc9a1  pop     rbp
0x1400cc9a2  pop     rbx
0x1400cc9a3  retn
```
