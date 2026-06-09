# ALLOC_CACHE_HANDLER::DumpStatsToHtml(char *,ulong *)

- ea: `0x180020b00`
- end: `0x180020cfe`
- name: `?DumpStatsToHtml@ALLOC_CACHE_HANDLER@@SAHPEADPEAK@Z`
- size: `510`
- prototype: `__int64 __fastcall(char *Buffer, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800159e0`
- `0x180020b00`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180020b71`
- `msvcrt!sprintf_s` at `0x180020c4b`
- `msvcrt!sprintf_s` at `0x180020cb8`
- `msvcrt!sprintf_s` at `0x180020b71`
- `msvcrt!sprintf_s` at `0x180020c4b`
- `msvcrt!sprintf_s` at `0x180020cb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020b27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020cd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020b27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020cd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020b50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020b50`

## string_xrefs

- `0x180020b67`: `\nAllocCacheTable Data <br>\n<TABLE BORDER> <TR> <TH> Item Name </TH> <TH> Config(concurr, threshold, size) </TH> <TH> # Total Items </TH> <TH> # Alloc Calls </TH> <TH> # Free Calls </TH> <TH> # Free Entries </TH> <TH> # Total Size (bytes) </TH> <TH> Fill Pattern </TH> <TH> Heap </TH>  </TR>\n`

## pseudocode

```c
__int64 __fastcall ALLOC_CACHE_HANDLER::DumpStatsToHtml(char *Buffer, unsigned int *a2)
{
  char *v3; // rbx
  int v5; // r15d
  unsigned int v6; // ebp
  unsigned int v7; // edi
  struct _LIST_ENTRY *Flink; // r14
  int v9; // r12d
  struct _LIST_ENTRY *v10; // r15
  int v11; // r13d
  __int64 v12; // rdx
  int Flink_high; // ebx
  unsigned int DepthForAllSLists; // eax
  unsigned int v15; // edi
  int v17; // [rsp+B8h] [rbp+10h]

  v3 = Buffer;
  if ( a2 )
  {
    v5 = 0;
    v17 = 0;
    v6 = 1;
    EnterCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
    v7 = 300;
    if ( *a2 > 0x12C )
      v7 = sprintf_s(
             v3,
             *a2,
             "\r\n"
             "AllocCacheTable Data <br>\r\n"
             "<TABLE BORDER> <TR> <TH> Item Name </TH> <TH> Config(concurr, threshold, size) </TH> <TH> # Total Items </T"
             "H> <TH> # Alloc Calls </TH> <TH> # Free Calls </TH> <TH> # Free Entries </TH> <TH> # Total Size (bytes) </T"
             "H> <TH> Fill Pattern </TH> <TH> Heap </TH>  </TR>\r\n");
    Flink = ALLOC_CACHE_HANDLER::sm_lItemsHead.Flink;
    v9 = 0;
    if ( ALLOC_CACHE_HANDLER::sm_lItemsHead.Flink != &ALLOC_CACHE_HANDLER::sm_lItemsHead )
    {
      do
      {
        v10 = Flink - 13;
        v11 = LODWORD(Flink[-12].Flink) * LODWORD(Flink[-9].Flink);
        v17 += v11;
        v12 = -1;
        do
          ++v12;
        while ( *((_BYTE *)&Flink[-1].Blink->Flink + v12) );
        if ( v12 + (unsigned __int64)(v7 + 160) >= *a2 )
        {
          v7 += v12 + 160;
        }
        else
        {
          Flink_high = HIDWORD(v10[12].Flink);
          DepthForAllSLists = ALLOC_CACHE_HANDLER::QueryDepthForAllSLists((ALLOC_CACHE_HANDLER *)&Flink[-13]);
          v7 += sprintf_s(
                  &Buffer[v7],
                  *a2 - v7,
                  " <TR> <TD> [%d] %s </TD> <TD> (%d, %d, %d) </TD> <TD> %4d </TD> <TD> %4d </TD> <TD> %4d </TD> <TD> %4d"
                  " </TD> <TD> %4d </TD> <TD> 0x%08lX </TD> </TR>\r\n",
                  v9,
                  (const char *)v10[12].Blink,
                  1,
                  HIDWORD(v10->Blink),
                  LODWORD(v10[1].Flink),
                  LODWORD(v10[4].Flink),
                  LODWORD(v10[8].Flink),
                  LODWORD(v10[12].Flink),
                  DepthForAllSLists,
                  v11,
                  Flink_high);
        }
        Flink = Flink->Flink;
        ++v9;
      }
      while ( Flink != &ALLOC_CACHE_HANDLER::sm_lItemsHead );
      v3 = Buffer;
      v5 = v17;
    }
    LeaveCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
    if ( v7 + 100 >= *a2 )
      v15 = v7 + 100;
    else
      v15 = sprintf_s(
              &v3[v7],
              *a2 - v7,
              " <b> <TR> </TR> <TR> <TD> Total </TD> <TD> </TD> <TD> </TD> <TD> </TD> <TD> </TD> <TD> </TD> <TD> %4d </TD"
              "> </TR></b>\r\n"
              " </TABLE>\r\n"
              "\r\n",
              v5)
          + v7;
    if ( *a2 < v15 )
    {
      SetLastError(0x7Au);
      v6 = 0;
    }
    *a2 = v15;
    return v6;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180020b00  mov     [rsp+arg_10], rbx
0x180020b05  mov     [rsp+arg_0], rcx
0x180020b0a  push    rbp
0x180020b0b  push    rsi
0x180020b0c  push    rdi
0x180020b0d  push    r12
0x180020b0f  push    r13
0x180020b11  push    r14
0x180020b13  push    r15
0x180020b15  sub     rsp, 70h
0x180020b19  mov     rsi, rdx
0x180020b1c  mov     rbx, rcx
0x180020b1f  test    rdx, rdx
0x180020b22  jnz     short loc_180020B3A
0x180020b24  lea     ecx, [rdx+57h]; dwErrCode
0x180020b27  call    cs:__imp_SetLastError
0x180020b2e  nop     dword ptr [rax+rax+00h]
0x180020b33  xor     eax, eax
0x180020b35  jmp     loc_180020CE5
0x180020b3a  xor     r15d, r15d
0x180020b3d  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020b44  mov     [rsp+0A8h+arg_8], r15d
0x180020b4c  lea     ebp, [r15+1]
0x180020b50  call    cs:__imp_EnterCriticalSection
0x180020b57  nop     dword ptr [rax+rax+00h]
0x180020b5c  mov     edi, 12Ch
0x180020b61  cmp     [rsi], edi
0x180020b63  jbe     short loc_180020B7F
0x180020b65  mov     edx, [rsi]; BufferCount
0x180020b67  lea     r8, aAlloccachetabl; "\r\nAllocCacheTable Data <br>\r\n<TABLE"...
0x180020b6e  mov     rcx, rbx; Buffer
0x180020b71  call    cs:__imp_sprintf_s
0x180020b78  nop     dword ptr [rax+rax+00h]
0x180020b7d  mov     edi, eax
0x180020b7f  mov     r14, cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180020b86  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180020b8d  xor     r12d, r12d
0x180020b90  cmp     r14, rax
0x180020b93  jz      loc_180020C89
0x180020b99  lea     r15, [r14-0D0h]
0x180020ba0  mov     r13d, [r15+40h]
0x180020ba4  imul    r13d, [r15+10h]
0x180020ba9  mov     rax, [r15+0C8h]
0x180020bb0  add     [rsp+0A8h+arg_8], r13d
0x180020bb8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180020bbc  inc     rdx
0x180020bbf  cmp     byte ptr [rax+rdx], 0
0x180020bc3  jnz     short loc_180020BBC
0x180020bc5  mov     eax, [rsi]
0x180020bc7  lea     ecx, [rdi+0A0h]
0x180020bcd  add     rcx, rdx
0x180020bd0  cmp     rcx, rax
0x180020bd3  jnb     loc_180020C5B
0x180020bd9  mov     ebx, [r15+0C4h]
0x180020be0  mov     rcx, r15; this
0x180020be3  call    ?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ; ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)
0x180020be8  mov     edx, [rsi]
0x180020bea  lea     r8, aTrTdDSTdTdDDDT; " <TR> <TD> [%d] %s </TD> <TD> (%d, %d, "...
0x180020bf1  mov     [rsp+0A8h+var_40], ebx
0x180020bf5  sub     edx, edi; BufferCount
0x180020bf7  mov     [rsp+0A8h+var_48], r13d
0x180020bfc  mov     r9d, r12d
0x180020bff  mov     [rsp+0A8h+var_50], eax
0x180020c03  mov     eax, [r15+0C0h]
0x180020c0a  mov     [rsp+0A8h+var_58], eax
0x180020c0e  mov     eax, [r15+80h]
0x180020c15  mov     [rsp+0A8h+var_60], eax
0x180020c19  mov     eax, [r15+40h]
0x180020c1d  mov     [rsp+0A8h+var_68], eax
0x180020c21  mov     eax, [r15+10h]
0x180020c25  mov     [rsp+0A8h+var_70], eax
0x180020c29  mov     eax, [r15+0Ch]
0x180020c2d  mov     [rsp+0A8h+var_78], eax
0x180020c31  mov     rax, [r15+0C8h]
0x180020c38  mov     ecx, edi
0x180020c3a  add     rcx, [rsp+0A8h+arg_0]; Buffer
0x180020c42  mov     [rsp+0A8h+var_80], ebp
0x180020c46  mov     [rsp+0A8h+var_88], rax
0x180020c4b  call    cs:__imp_sprintf_s
0x180020c52  nop     dword ptr [rax+rax+00h]
0x180020c57  add     edi, eax
0x180020c59  jmp     short loc_180020C63
0x180020c5b  add     edi, 0A0h
0x180020c61  add     edi, edx
0x180020c63  mov     r14, [r14]
0x180020c66  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x180020c6d  add     r12d, ebp
0x180020c70  cmp     r14, rax
0x180020c73  jnz     loc_180020B99
0x180020c79  mov     rbx, [rsp+0A8h+arg_0]
0x180020c81  mov     r15d, [rsp+0A8h+arg_8]
0x180020c89  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020c90  call    cs:__imp_LeaveCriticalSection
0x180020c97  nop     dword ptr [rax+rax+00h]
0x180020c9c  mov     eax, [rsi]
0x180020c9e  lea     ecx, [rdi+64h]
0x180020ca1  cmp     ecx, eax
0x180020ca3  jnb     short loc_180020CC8
0x180020ca5  sub     eax, edi
0x180020ca7  mov     ecx, edi
0x180020ca9  mov     edx, eax; BufferCount
0x180020cab  lea     r8, aBTrTrTrTdTotal; " <b> <TR> </TR> <TR> <TD> Total </TD> <"...
0x180020cb2  add     rcx, rbx; Buffer
0x180020cb5  mov     r9d, r15d
0x180020cb8  call    cs:__imp_sprintf_s
0x180020cbf  nop     dword ptr [rax+rax+00h]
0x180020cc4  add     edi, eax
0x180020cc6  jmp     short loc_180020CCA
0x180020cc8  mov     edi, ecx
0x180020cca  cmp     [rsi], edi
0x180020ccc  jnb     short loc_180020CE1
0x180020cce  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180020cd3  call    cs:__imp_SetLastError
0x180020cda  nop     dword ptr [rax+rax+00h]
0x180020cdf  xor     ebp, ebp
0x180020ce1  mov     [rsi], edi
0x180020ce3  mov     eax, ebp
0x180020ce5  mov     rbx, [rsp+0A8h+arg_10]
0x180020ced  add     rsp, 70h
0x180020cf1  pop     r15
0x180020cf3  pop     r14
0x180020cf5  pop     r13
0x180020cf7  pop     r12
0x180020cf9  pop     rdi
0x180020cfa  pop     rsi
0x180020cfb  pop     rbp
0x180020cfc  retn
```
