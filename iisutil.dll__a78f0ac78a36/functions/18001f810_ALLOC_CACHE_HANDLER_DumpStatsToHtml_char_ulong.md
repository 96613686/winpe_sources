# ALLOC_CACHE_HANDLER::DumpStatsToHtml(char *,ulong *)

- ea: `0x18001f810`
- end: `0x18001f9df`
- name: `?DumpStatsToHtml@ALLOC_CACHE_HANDLER@@SAHPEADPEAK@Z`
- size: `463`
- prototype: `__int64 __fastcall(char *Buffer, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180015120`
- `0x18001f810`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18001f875`
- `msvcrt!sprintf_s` at `0x18001f945`
- `msvcrt!sprintf_s` at `0x18001f9a6`
- `msvcrt!sprintf_s` at `0x18001f875`
- `msvcrt!sprintf_s` at `0x18001f945`
- `msvcrt!sprintf_s` at `0x18001f9a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f837`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f9bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f837`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f9bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f984`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f984`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f85a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f85a`

## string_xrefs

- `0x18001f86b`: `\nAllocCacheTable Data <br>\n<TABLE BORDER> <TR> <TH> Item Name </TH> <TH> Config(concurr, threshold, size) </TH> <TH> # Total Items </TH> <TH> # Alloc Calls </TH> <TH> # Free Calls </TH> <TH> # Free Entries </TH> <TH> # Total Size (bytes) </TH> <TH> Fill Pattern </TH> <TH> Heap </TH>  </TR>\n`

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
0x18001f810  mov     [rsp+arg_10], rbx
0x18001f815  mov     [rsp+arg_0], rcx
0x18001f81a  push    rbp
0x18001f81b  push    rsi
0x18001f81c  push    rdi
0x18001f81d  push    r12
0x18001f81f  push    r13
0x18001f821  push    r14
0x18001f823  push    r15
0x18001f825  sub     rsp, 70h
0x18001f829  mov     rsi, rdx
0x18001f82c  mov     rbx, rcx
0x18001f82f  test    rdx, rdx
0x18001f832  jnz     short loc_18001F844
0x18001f834  lea     ecx, [rdx+57h]; dwErrCode
0x18001f837  call    cs:__imp_SetLastError
0x18001f83d  xor     eax, eax
0x18001f83f  jmp     loc_18001F9C7
0x18001f844  xor     r15d, r15d
0x18001f847  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f84e  mov     [rsp+0A8h+arg_8], r15d
0x18001f856  lea     ebp, [r15+1]
0x18001f85a  call    cs:__imp_EnterCriticalSection
0x18001f860  mov     edi, 12Ch
0x18001f865  cmp     [rsi], edi
0x18001f867  jbe     short loc_18001F87D
0x18001f869  mov     edx, [rsi]; BufferCount
0x18001f86b  lea     r8, aAlloccachetabl; "\r\nAllocCacheTable Data <br>\r\n<TABLE"...
0x18001f872  mov     rcx, rbx; Buffer
0x18001f875  call    cs:__imp_sprintf_s
0x18001f87b  mov     edi, eax
0x18001f87d  mov     r14, cs:?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18001f884  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18001f88b  xor     r12d, r12d
0x18001f88e  cmp     r14, rax
0x18001f891  jz      loc_18001F97D
0x18001f897  lea     r15, [r14-0D0h]
0x18001f89e  mov     r13d, [r15+40h]
0x18001f8a2  imul    r13d, [r15+10h]
0x18001f8a7  mov     rax, [r15+0C8h]
0x18001f8ae  add     [rsp+0A8h+arg_8], r13d
0x18001f8b6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001f8ba  inc     rdx
0x18001f8bd  cmp     byte ptr [rax+rdx], 0
0x18001f8c1  jnz     short loc_18001F8BA
0x18001f8c3  mov     eax, [rsi]
0x18001f8c5  lea     ecx, [rdi+0A0h]
0x18001f8cb  add     rcx, rdx
0x18001f8ce  cmp     rcx, rax
0x18001f8d1  jnb     short loc_18001F94F
0x18001f8d3  mov     ebx, [r15+0C4h]
0x18001f8da  mov     rcx, r15; this
0x18001f8dd  call    ?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ; ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)
0x18001f8e2  mov     edx, [rsi]
0x18001f8e4  lea     r8, aTrTdDSTdTdDDDT; " <TR> <TD> [%d] %s </TD> <TD> (%d, %d, "...
0x18001f8eb  mov     [rsp+0A8h+var_40], ebx
0x18001f8ef  sub     edx, edi; BufferCount
0x18001f8f1  mov     [rsp+0A8h+var_48], r13d
0x18001f8f6  mov     r9d, r12d
0x18001f8f9  mov     [rsp+0A8h+var_50], eax
0x18001f8fd  mov     eax, [r15+0C0h]
0x18001f904  mov     [rsp+0A8h+var_58], eax
0x18001f908  mov     eax, [r15+80h]
0x18001f90f  mov     [rsp+0A8h+var_60], eax
0x18001f913  mov     eax, [r15+40h]
0x18001f917  mov     [rsp+0A8h+var_68], eax
0x18001f91b  mov     eax, [r15+10h]
0x18001f91f  mov     [rsp+0A8h+var_70], eax
0x18001f923  mov     eax, [r15+0Ch]
0x18001f927  mov     [rsp+0A8h+var_78], eax
0x18001f92b  mov     rax, [r15+0C8h]
0x18001f932  mov     ecx, edi
0x18001f934  add     rcx, [rsp+0A8h+arg_0]; Buffer
0x18001f93c  mov     [rsp+0A8h+var_80], ebp
0x18001f940  mov     [rsp+0A8h+var_88], rax
0x18001f945  call    cs:__imp_sprintf_s
0x18001f94b  add     edi, eax
0x18001f94d  jmp     short loc_18001F957
0x18001f94f  add     edi, 0A0h
0x18001f955  add     edi, edx
0x18001f957  mov     r14, [r14]
0x18001f95a  lea     rax, ?sm_lItemsHead@ALLOC_CACHE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ALLOC_CACHE_HANDLER::sm_lItemsHead
0x18001f961  add     r12d, ebp
0x18001f964  cmp     r14, rax
0x18001f967  jnz     loc_18001F897
0x18001f96d  mov     rbx, [rsp+0A8h+arg_0]
0x18001f975  mov     r15d, [rsp+0A8h+arg_8]
0x18001f97d  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001f984  call    cs:__imp_LeaveCriticalSection
0x18001f98a  mov     eax, [rsi]
0x18001f98c  lea     ecx, [rdi+64h]
0x18001f98f  cmp     ecx, eax
0x18001f991  jnb     short loc_18001F9B0
0x18001f993  sub     eax, edi
0x18001f995  mov     ecx, edi
0x18001f997  mov     edx, eax; BufferCount
0x18001f999  lea     r8, aBTrTrTrTdTotal; " <b> <TR> </TR> <TR> <TD> Total </TD> <"...
0x18001f9a0  add     rcx, rbx; Buffer
0x18001f9a3  mov     r9d, r15d
0x18001f9a6  call    cs:__imp_sprintf_s
0x18001f9ac  add     edi, eax
0x18001f9ae  jmp     short loc_18001F9B2
0x18001f9b0  mov     edi, ecx
0x18001f9b2  cmp     [rsi], edi
0x18001f9b4  jnb     short loc_18001F9C3
0x18001f9b6  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18001f9bb  call    cs:__imp_SetLastError
0x18001f9c1  xor     ebp, ebp
0x18001f9c3  mov     [rsi], edi
0x18001f9c5  mov     eax, ebp
0x18001f9c7  mov     rbx, [rsp+0A8h+arg_10]
0x18001f9cf  add     rsp, 70h
0x18001f9d3  pop     r15
0x18001f9d5  pop     r14
0x18001f9d7  pop     r13
0x18001f9d9  pop     r12
0x18001f9db  pop     rdi
0x18001f9dc  pop     rsi
0x18001f9dd  pop     rbp
0x18001f9de  retn
```
