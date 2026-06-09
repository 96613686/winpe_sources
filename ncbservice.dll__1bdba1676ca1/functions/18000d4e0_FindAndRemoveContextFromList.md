# FindAndRemoveContextFromList

- ea: `0x18000d4e0`
- end: `0x18000d644`
- name: `FindAndRemoveContextFromList`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000db60`
- `0x180021130`

## callees

- `0x18000ba08`
- `0x18000d4e0`
- `0x18001c500`
- `0x18001d09c`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x18000d53f`
- `ntdll!RtlLookupEntryHashTable` at `0x18000d53f`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000d61c`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000d61c`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000d5fb`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000d5fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d51a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d51a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d605`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d605`

## pseudocode

```c
__int64 __fastcall FindAndRemoveContextFromList(__int64 a1)
{
  unsigned int v2; // eax
  __int64 i; // rax
  __int64 v4; // rsi
  unsigned int v5; // edi
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+30h] [rbp-38h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  v8 = 0;
  EnterCriticalSection(&g_ControlChannelTriggerContextTableLock);
  v2 = NcbComputeContextKey(a1);
  v7 = 0;
  for ( i = RtlLookupEntryHashTable(g_ControlChannelTriggerContextTable, v2, &v7);
        ;
        i = RtlGetNextEntryHashTable(g_ControlChannelTriggerContextTable, &v7) )
  {
    v4 = i;
    if ( !i )
    {
      v5 = 1168;
      goto LABEL_5;
    }
    if ( i == a1 )
      break;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  RtlRemoveEntryHashTable(g_ControlChannelTriggerContextTable, v4, 0);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
LABEL_5:
  LeaveCriticalSection(&g_ControlChannelTriggerContextTableLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18000d4e0  push    rbx
0x18000d4e2  push    rsi
0x18000d4e3  push    rdi
0x18000d4e4  push    r14
0x18000d4e6  sub     rsp, 48h
0x18000d4ea  mov     rbx, rcx
0x18000d4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4f4  lea     r14, WPP_GLOBAL_Control
0x18000d4fb  cmp     rcx, r14
0x18000d4fe  jnz     loc_18000D59D
0x18000d504  xorps   xmm0, xmm0
0x18000d507  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x18000d50e  xor     eax, eax
0x18000d510  movups  [rsp+68h+var_48], xmm0
0x18000d515  mov     [rsp+68h+var_38], rax
0x18000d51a  call    cs:__imp_EnterCriticalSection
0x18000d520  mov     rcx, rbx
0x18000d523  call    NcbComputeContextKey
0x18000d528  xorps   xmm0, xmm0
0x18000d52b  mov     edx, eax
0x18000d52d  lea     r8, [rsp+68h+var_48]
0x18000d532  lea     rcx, g_ControlChannelTriggerContextTable
0x18000d539  movdqu  [rsp+68h+var_48], xmm0
0x18000d53f  call    cs:__imp_RtlLookupEntryHashTable
0x18000d545  mov     rsi, rax
0x18000d548  test    rax, rax
0x18000d54b  jnz     short loc_18000D5CB
0x18000d54d  mov     edi, 490h
0x18000d552  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x18000d559  call    cs:__imp_LeaveCriticalSection
0x18000d55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d566  cmp     rcx, r14
0x18000d569  jnz     short loc_18000D577
0x18000d56b  mov     eax, edi
0x18000d56d  add     rsp, 48h
0x18000d571  pop     r14
0x18000d573  pop     rdi
0x18000d574  pop     rsi
0x18000d575  pop     rbx
0x18000d576  retn
0x18000d577  test    byte ptr [rcx+1Ch], 1
0x18000d57b  jz      short loc_18000D56B
0x18000d57d  cmp     byte ptr [rcx+19h], 6
0x18000d581  jb      short loc_18000D56B
0x18000d583  mov     rcx, [rcx+10h]
0x18000d587  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000d58e  mov     edx, 7Ch ; '|'
0x18000d593  mov     r9d, edi
0x18000d596  call    WPP_SF_d
0x18000d59b  jmp     short loc_18000D56B
0x18000d59d  test    byte ptr [rcx+1Ch], 1
0x18000d5a1  jz      loc_18000D504
0x18000d5a7  cmp     byte ptr [rcx+19h], 6
0x18000d5ab  jb      loc_18000D504
0x18000d5b1  mov     rcx, [rcx+10h]
0x18000d5b5  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000d5bc  mov     edx, 7Ah ; 'z'
0x18000d5c1  call    WPP_SF_
0x18000d5c6  jmp     loc_18000D504
0x18000d5cb  cmp     rsi, rbx
0x18000d5ce  jnz     short loc_18000D610
0x18000d5d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5d7  cmp     rcx, r14
0x18000d5da  jz      short loc_18000D5E2
0x18000d5dc  test    byte ptr [rcx+1Ch], 1
0x18000d5e0  jnz     short loc_18000D627
0x18000d5e2  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000d5e6  xor     edi, edi
0x18000d5e8  call    cs:__imp_EnterCriticalSection
0x18000d5ee  xor     r8d, r8d
0x18000d5f1  lea     rcx, g_ControlChannelTriggerContextTable
0x18000d5f8  mov     rdx, rsi
0x18000d5fb  call    cs:__imp_RtlRemoveEntryHashTable
0x18000d601  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000d605  call    cs:__imp_LeaveCriticalSection
0x18000d60b  jmp     loc_18000D552
0x18000d610  lea     rdx, [rsp+68h+var_48]
0x18000d615  lea     rcx, g_ControlChannelTriggerContextTable
0x18000d61c  call    cs:__imp_RtlGetNextEntryHashTable
0x18000d622  jmp     loc_18000D545
0x18000d627  cmp     byte ptr [rcx+19h], 5
0x18000d62b  jb      short loc_18000D5E2
0x18000d62d  mov     rcx, [rcx+10h]
0x18000d631  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000d638  mov     edx, 7Bh ; '{'
0x18000d63d  call    WPP_SF_
0x18000d642  jmp     short loc_18000D5E2
```
