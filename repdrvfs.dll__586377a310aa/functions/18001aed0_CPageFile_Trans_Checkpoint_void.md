# CPageFile::Trans_Checkpoint(void *)

- ea: `0x18001aed0`
- end: `0x18001b129`
- name: `?Trans_Checkpoint@CPageFile@@QEAAKPEAX@Z`
- size: `601`
- prototype: `unsigned int __fastcall(CPageFile *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ad80`

## callees

- `0x1800012b8`
- `0x18001abc0`
- `0x18001aed0`
- `0x18001b130`
- `0x18001b270`
- `0x18001be18`
- `0x1800293b0`
- `0x180029a58`
- `0x18002a6f8`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001b0ff`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001b0ff`
- `wbemcomn!GetMemLogObject` at `0x18001aeeb`
- `wbemcomn!GetMemLogObject` at `0x18001af57`
- `wbemcomn!GetMemLogObject` at `0x18001b066`
- `wbemcomn!GetMemLogObject` at `0x18001aeeb`
- `wbemcomn!GetMemLogObject` at `0x18001af57`
- `wbemcomn!GetMemLogObject` at `0x18001b066`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001aefb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001af62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b071`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001aefb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001af62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b071`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b049`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b049`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPageFile::Trans_Checkpoint(CPageFile *this, void *a2)
{
  CMemoryLog *MemLogObject; // rax
  DWORD v4; // ebx
  CVarObjHeap *v5; // rcx
  __int64 v6; // rdx
  CMemoryLog *v8; // rax
  __int64 *v9; // rbx
  unsigned __int64 v10; // rdx
  __int64 v11; // r11
  int v12; // edx
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // esi
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  __int128 v18; // [rsp+20h] [rbp-28h] BYREF
  __int64 v19; // [rsp+30h] [rbp-18h]

  if ( *((_DWORD *)this + 49) )
  {
    MemLogObject = GetMemLogObject();
    v4 = 4317;
    CMemoryLog::Write(MemLogObject, 4317);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v4;
    }
    v6 = 62;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v4);
    return v4;
  }
  if ( CPageSource::m_writeBit )
  {
    v4 = CPageCache::Flush((CPageFile *)((char *)this + 64));
    if ( v4 )
    {
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, v4);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v4;
      }
      v6 = 63;
      goto LABEL_6;
    }
  }
  v18 = 0;
  v19 = 0;
  try
  {
    v9 = (__int64 *)((char *)this + 272);
    v10 = (__int64)(*((_QWORD *)this + 35) - *((_QWORD *)this + 34)) >> 2;
    if ( v10 )
    {
      if ( v10 > 0x3FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector<T> too long");
      std::vector<unsigned long,wbem_allocator<unsigned long>>::_Reallocate(&v18);
    }
  }
  catch ( CX_MemoryException )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 14);
    }
    std::vector<unsigned int,wbem_allocator<bool>>::_Tidy((__int64)&v18);
    return 14;
  }
  std::vector<unsigned long,wbem_allocator<unsigned long>>::operator=(&v18, v9);
  StripHiBits((char *)this + 224);
  v11 = *v9;
  if ( (v9[1] - *v9) >> 2 )
  {
    v12 = 0;
    v13 = 0;
    do
    {
      v14 = *(_DWORD *)(v11 + 4 * v13);
      if ( v14 )
        *(_DWORD *)(v11 + 4 * v13) = v14 - 1;
      ++v12;
      v11 = *v9;
      v13 = v12;
    }
    while ( v12 < (unsigned __int64)((v9[1] - *v9) >> 2) );
  }
  *((_DWORD *)this + 54) = 0;
  v15 = CPageFile::ResyncMaps(this, 0);
  *((_DWORD *)this + 50) = GetTickCount();
  if ( v15 )
  {
    std::vector<unsigned long,wbem_allocator<unsigned long>>::operator=(v9, &v18);
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, v15);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v15);
    }
    std::vector<unsigned int,wbem_allocator<bool>>::_Tidy((__int64)&v18);
    return v15;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 0);
    }
    if ( (_QWORD)v18 )
      CWin32DefaultArena::WbemMemFree((void *)v18);
    return 0;
  }
}

```

## disassembly

```asm
0x18001aed0  mov     [rsp+arg_0], rbx
0x18001aed5  mov     [rsp+arg_8], rsi
0x18001aeda  push    rdi
0x18001aedb  sub     rsp, 40h
0x18001aedf  mov     rdi, rcx
0x18001aee2  cmp     dword ptr [rcx+0C4h], 0
0x18001aee9  jz      short loc_18001AF3F
0x18001aeeb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001aef1  mov     ebx, 10DDh
0x18001aef6  mov     edx, ebx
0x18001aef8  mov     rcx, rax
0x18001aefb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001af01  lea     rax, WPP_GLOBAL_Control
0x18001af08  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af0f  cmp     rcx, rax
0x18001af12  jz      short loc_18001AF38
0x18001af14  test    byte ptr [rcx+1Ch], 1
0x18001af18  jz      short loc_18001AF38
0x18001af1a  cmp     byte ptr [rcx+19h], 2
0x18001af1e  jb      short loc_18001AF38
0x18001af20  mov     edx, 3Eh ; '>'
0x18001af25  mov     r9d, ebx
0x18001af28  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001af2f  mov     rcx, [rcx+10h]
0x18001af33  call    WPP_SF_d
0x18001af38  mov     eax, ebx
0x18001af3a  jmp     loc_18001B119
0x18001af3f  cmp     cs:?m_writeBit@CPageSource@@0KA, 0; ulong CPageSource::m_writeBit
0x18001af46  jz      short loc_18001AF8E
0x18001af48  add     rcx, 40h ; '@'; this
0x18001af4c  call    ?Flush@CPageCache@@QEAAKXZ; CPageCache::Flush(void)
0x18001af51  mov     ebx, eax
0x18001af53  test    eax, eax
0x18001af55  jz      short loc_18001AF8E
0x18001af57  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001af5d  mov     edx, ebx
0x18001af5f  mov     rcx, rax
0x18001af62  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001af68  lea     rax, WPP_GLOBAL_Control
0x18001af6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af76  cmp     rcx, rax
0x18001af79  jz      short loc_18001AF38
0x18001af7b  test    byte ptr [rcx+1Ch], 1
0x18001af7f  jz      short loc_18001AF38
0x18001af81  cmp     byte ptr [rcx+19h], 2
0x18001af85  jb      short loc_18001AF38
0x18001af87  mov     edx, 3Fh ; '?'
0x18001af8c  jmp     short loc_18001AF25
0x18001af8e  xorps   xmm0, xmm0
0x18001af91  movdqu  [rsp+48h+var_28], xmm0
0x18001af97  mov     [rsp+48h+var_18], 0
0x18001afa0  lea     rbx, [rdi+110h]
0x18001afa7  mov     rdx, [rbx+8]
0x18001afab  sub     rdx, [rbx]
0x18001afae  sar     rdx, 2
0x18001afb2  test    rdx, rdx
0x18001afb5  jz      short loc_18001AFDD
0x18001afb7  mov     rax, 3FFFFFFFFFFFFFFFh
0x18001afc1  cmp     rdx, rax
0x18001afc4  jbe     short loc_18001AFD2
0x18001afc6  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x18001afcd  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001afd2  lea     rcx, [rsp+48h+var_28]
0x18001afd7  call    ?_Reallocate@?$vector@KV?$wbem_allocator@K@@@std@@IEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::_Reallocate(unsigned __int64)
0x18001afdc  nop
0x18001afdd  mov     rdx, rbx
0x18001afe0  lea     rcx, [rsp+48h+var_28]
0x18001afe5  call    ??4?$vector@KV?$wbem_allocator@K@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<ulong,wbem_allocator<ulong>>::operator=(std::vector<ulong,wbem_allocator<ulong>> const &)
0x18001afea  lea     rcx, [rdi+0E0h]
0x18001aff1  call    ?StripHiBits@@YAXAEAV?$vector@UPageMapEntry@@V?$wbem_allocator@UPageMapEntry@@@@@std@@@Z; StripHiBits(std::vector<PageMapEntry,wbem_allocator<PageMapEntry>> &)
0x18001aff6  mov     r11, [rbx]
0x18001aff9  mov     rax, [rbx+8]
0x18001affd  sub     rax, r11
0x18001b000  sar     rax, 2
0x18001b004  test    rax, rax
0x18001b007  jz      short loc_18001B033
0x18001b009  xor     edx, edx
0x18001b00b  xor     ecx, ecx
0x18001b00d  mov     eax, [r11+rcx*4]
0x18001b011  test    eax, eax
0x18001b013  jz      short loc_18001B01B
0x18001b015  dec     eax
0x18001b017  mov     [r11+rcx*4], eax
0x18001b01b  inc     edx
0x18001b01d  mov     r11, [rbx]
0x18001b020  movsxd  rcx, edx
0x18001b023  mov     rax, [rbx+8]
0x18001b027  sub     rax, r11
0x18001b02a  sar     rax, 2
0x18001b02e  cmp     rcx, rax
0x18001b031  jb      short loc_18001B00D
0x18001b033  mov     dword ptr [rdi+0D8h], 0
0x18001b03d  xor     edx, edx; bool
0x18001b03f  mov     rcx, rdi; this
0x18001b042  call    ?ResyncMaps@CPageFile@@QEAAK_N@Z; CPageFile::ResyncMaps(bool)
0x18001b047  mov     esi, eax
0x18001b049  call    cs:__imp_GetTickCount
0x18001b04f  mov     [rdi+0C8h], eax
0x18001b055  test    esi, esi
0x18001b057  jz      short loc_18001B0BD
0x18001b059  lea     rdx, [rsp+48h+var_28]
0x18001b05e  mov     rcx, rbx
0x18001b061  call    ??4?$vector@KV?$wbem_allocator@K@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<ulong,wbem_allocator<ulong>>::operator=(std::vector<ulong,wbem_allocator<ulong>> const &)
0x18001b066  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b06c  mov     edx, esi
0x18001b06e  mov     rcx, rax
0x18001b071  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b077  lea     rax, WPP_GLOBAL_Control
0x18001b07e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b085  cmp     rcx, rax
0x18001b088  jz      short loc_18001B0AF
0x18001b08a  test    byte ptr [rcx+1Ch], 1
0x18001b08e  jz      short loc_18001B0AF
0x18001b090  cmp     byte ptr [rcx+19h], 2
0x18001b094  jb      short loc_18001B0AF
0x18001b096  mov     edx, 41h ; 'A'
0x18001b09b  mov     r9d, esi
0x18001b09e  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001b0a5  mov     rcx, [rcx+10h]
0x18001b0a9  call    WPP_SF_d
0x18001b0ae  nop
0x18001b0af  lea     rcx, [rsp+48h+var_28]
0x18001b0b4  call    ?_Tidy@?$vector@IV?$wbem_allocator@_N@@@std@@IEAAXXZ; std::vector<uint,wbem_allocator<bool>>::_Tidy(void)
0x18001b0b9  mov     eax, esi
0x18001b0bb  jmp     short loc_18001B119
0x18001b0bd  lea     rax, WPP_GLOBAL_Control
0x18001b0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0cb  cmp     rcx, rax
0x18001b0ce  jz      short loc_18001B0F5
0x18001b0d0  test    byte ptr [rcx+1Ch], 1
0x18001b0d4  jz      short loc_18001B0F5
0x18001b0d6  cmp     byte ptr [rcx+19h], 2
0x18001b0da  jb      short loc_18001B0F5
0x18001b0dc  mov     edx, 42h ; 'B'
0x18001b0e1  xor     r9d, r9d
0x18001b0e4  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001b0eb  mov     rcx, [rcx+10h]
0x18001b0ef  call    WPP_SF_d
0x18001b0f4  nop
0x18001b0f5  mov     rcx, qword ptr [rsp+48h+var_28]
0x18001b0fa  test    rcx, rcx
0x18001b0fd  jz      short loc_18001B106
0x18001b0ff  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001b105  nop
0x18001b106  xor     eax, eax
0x18001b108  jmp     short loc_18001B119
0x18001b10a  lea     rcx, [rsp+48h+var_28]
0x18001b10f  call    ?_Tidy@?$vector@IV?$wbem_allocator@_N@@@std@@IEAAXXZ; std::vector<uint,wbem_allocator<bool>>::_Tidy(void)
0x18001b114  mov     eax, 0Eh
0x18001b119  mov     rbx, [rsp+48h+arg_0]
0x18001b11e  mov     rsi, [rsp+48h+arg_8]
0x18001b123  add     rsp, 40h
0x18001b127  pop     rdi
0x18001b128  retn
```
