# McGenControlCallbackV2

- ea: `0x14000d770`
- end: `0x14000d8fc`
- name: `McGenControlCallbackV2`
- size: `396`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000d3b8`
- `0x14000d660`
- `0x14000d770`
- `0x14000da84`
- `0x140016700`

## import_xrefs

- `NDIS!NdisAllocateRWLock` at `0x14000d875`
- `NDIS!NdisAllocateRWLock` at `0x14000d875`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // bl
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          v10 = 0;
          if ( *(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8 )
          {
            v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
            if ( !v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
            {
              v10 = 1;
            }
          }
          v11 = 1 << v7;
          v12 = (int *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
          v13 = *v12;
          if ( v10 )
            v14 = v11 | v13;
          else
            v14 = ~v11 & v13;
          *v12 = v14;
        }
      }
      else if ( ControlCode - 1 >= 2 )
      {
        return;
      }
      if ( CallbackContext == &MICROSOFT_RAS_NDISWAN_PACKETCAPTURE_PROVIDER_Context )
      {
        gbEnablePacketCapture = 1;
        if ( !_InterlockedExchange(&NdisWanPacketCapFilterLockInitialized, 1) )
          NdisWanPacketCapFilterLock = NdisAllocateRWLock(NdisMiniportDriverHandle);
        if ( FilterData )
          ProcessFilterData((__int64)FilterData);
        else
          CleanupFilterData();
        EvaluateFilterRulesForAllConnections();
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
      CleanupFilterData();
      gbEnablePacketCapture = 0;
    }
  }
}

```

## disassembly

```asm
0x14000d770  mov     [rsp+arg_0], rbx
0x14000d775  push    rdi
0x14000d776  sub     rsp, 20h
0x14000d77a  mov     r10, [rsp+28h+CallbackContext]
0x14000d77f  xor     edi, edi
0x14000d781  test    r10, r10
0x14000d784  jz      loc_14000D8F0
0x14000d78a  mov     eax, edx
0x14000d78c  test    edx, edx
0x14000d78e  jz      loc_14000D8A5
0x14000d794  lea     r11d, [rdi+1]
0x14000d798  cmp     eax, r11d
0x14000d79b  jz      short loc_14000D7BC
0x14000d79d  test    edx, edx
0x14000d79f  jz      loc_14000D8E4
0x14000d7a5  sub     edx, r11d
0x14000d7a8  jz      loc_14000D84B
0x14000d7ae  cmp     edx, r11d
0x14000d7b1  jz      loc_14000D84B
0x14000d7b7  jmp     loc_14000D8F0
0x14000d7bc  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000d7c1  mov     [r10+28h], r8b
0x14000d7c5  mov     r8d, edi
0x14000d7c8  mov     [r10+18h], rax
0x14000d7cc  mov     [r10+10h], r9
0x14000d7d0  mov     [r10+24h], r11d
0x14000d7d4  cmp     di, [r10+2Ah]
0x14000d7d9  jnb     short loc_14000D84B
0x14000d7db  mov     rax, [r10+40h]
0x14000d7df  mov     cl, [r10+28h]
0x14000d7e3  mov     r9d, r8d
0x14000d7e6  cmp     [r9+rax], cl
0x14000d7ea  jbe     short loc_14000D7F0
0x14000d7ec  test    cl, cl
0x14000d7ee  jnz     short loc_14000D812
0x14000d7f0  mov     rax, [r10+38h]
0x14000d7f4  mov     rdx, [rax+r9*8]
0x14000d7f8  test    rdx, rdx
0x14000d7fb  jz      short loc_14000D817
0x14000d7fd  test    [r10+10h], rdx
0x14000d801  jz      short loc_14000D812
0x14000d803  mov     rcx, [r10+18h]
0x14000d807  mov     rax, rcx
0x14000d80a  and     rax, rdx
0x14000d80d  cmp     rax, rcx
0x14000d810  jz      short loc_14000D817
0x14000d812  mov     bl, dil
0x14000d815  jmp     short loc_14000D81A
0x14000d817  mov     bl, r11b
0x14000d81a  mov     rax, [r10+30h]
0x14000d81e  mov     ecx, r8d
0x14000d821  shr     r9, 5
0x14000d825  mov     edx, r11d
0x14000d828  shl     edx, cl
0x14000d82a  lea     rcx, [rax+r9*4]
0x14000d82e  mov     eax, [rcx]
0x14000d830  test    bl, bl
0x14000d832  jz      short loc_14000D838
0x14000d834  or      eax, edx
0x14000d836  jmp     short loc_14000D83C
0x14000d838  not     edx
0x14000d83a  and     eax, edx
0x14000d83c  mov     [rcx], eax
0x14000d83e  add     r8d, r11d
0x14000d841  movzx   eax, word ptr [r10+2Ah]
0x14000d846  cmp     r8d, eax
0x14000d849  jb      short loc_14000D7DB
0x14000d84b  lea     rax, MICROSOFT_RAS_NDISWAN_PACKETCAPTURE_PROVIDER_Context
0x14000d852  cmp     r10, rax
0x14000d855  jnz     loc_14000D8F0
0x14000d85b  mov     cs:gbEnablePacketCapture, r11b
0x14000d862  xchg    r11d, cs:NdisWanPacketCapFilterLockInitialized
0x14000d869  test    r11d, r11d
0x14000d86c  jnz     short loc_14000D888
0x14000d86e  mov     rcx, cs:NdisMiniportDriverHandle; NdisHandle
0x14000d875  call    cs:__imp_NdisAllocateRWLock
0x14000d87c  nop     dword ptr [rax+rax+00h]
0x14000d881  mov     cs:NdisWanPacketCapFilterLock, rax
0x14000d888  mov     rcx, [rsp+28h+FilterData]
0x14000d88d  test    rcx, rcx
0x14000d890  jz      short loc_14000D899
0x14000d892  call    ProcessFilterData
0x14000d897  jmp     short loc_14000D89E
0x14000d899  call    CleanupFilterData
0x14000d89e  call    EvaluateFilterRulesForAllConnections
0x14000d8a3  jmp     short loc_14000D8F0
0x14000d8a5  movzx   eax, word ptr [r10+2Ah]
0x14000d8aa  mov     [r10+24h], edi
0x14000d8ae  mov     [r10+28h], dil
0x14000d8b2  mov     [r10+10h], rdi
0x14000d8b6  mov     [r10+18h], rdi
0x14000d8ba  test    ax, ax
0x14000d8bd  jz      short loc_14000D8E4
0x14000d8bf  mov     r11d, 1
0x14000d8c5  sub     eax, r11d
0x14000d8c8  cdq
0x14000d8c9  lea     ecx, [r11+1Fh]
0x14000d8cd  idiv    ecx
0x14000d8cf  mov     rcx, [r10+30h]; void *
0x14000d8d3  xor     edx, edx; Val
0x14000d8d5  add     eax, r11d
0x14000d8d8  movsxd  r8, eax
0x14000d8db  shl     r8, 2; Size
0x14000d8df  call    memset
0x14000d8e4  call    CleanupFilterData
0x14000d8e9  mov     cs:gbEnablePacketCapture, dil
0x14000d8f0  mov     rbx, [rsp+28h+arg_0]
0x14000d8f5  add     rsp, 20h
0x14000d8f9  pop     rdi
0x14000d8fa  retn
```
