# CPageFile::NewPage(ulong,ulong,ulong *)

- ea: `0x1800259c0`
- end: `0x180025b52`
- name: `?NewPage@CPageFile@@QEAAKKKPEAK@Z`
- size: `402`
- prototype: `unsigned int(CPageFile *__hidden this, unsigned int, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180025818`
- `0x18002be34`
- `0x180037da8`

## callees

- `0x1800012b8`
- `0x18001a51c`
- `0x180024854`
- `0x1800259c0`
- `0x180025b58`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800259e0`
- `wbemcomn!GetMemLogObject` at `0x180025a53`
- `wbemcomn!GetMemLogObject` at `0x1800259e0`
- `wbemcomn!GetMemLogObject` at `0x180025a53`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800259f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025a5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800259f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025a5e`

## pseudocode

```c
__int64 __fastcall CPageFile::NewPage(CPageFile *this, __int64 a2, unsigned int a3, unsigned int *a4)
{
  __int64 v5; // rsi
  CMemoryLog *MemLogObject; // rax
  unsigned int v8; // ebx
  CVarObjHeap *v9; // rcx
  __int64 v10; // rdx
  CMemoryLog *v12; // rax
  _QWORD *v13; // rdi
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  unsigned int i; // r14d
  CMemoryLog *v17; // rax
  int v18; // [rsp+20h] [rbp-58h] BYREF
  __int64 v19; // [rsp+24h] [rbp-54h]
  int v20; // [rsp+2Ch] [rbp-4Ch]
  __int64 v21; // [rsp+30h] [rbp-48h]

  v5 = a3;
  if ( !*((_DWORD *)this + 49) )
  {
    MemLogObject = GetMemLogObject();
    v8 = 4317;
    CMemoryLog::Write(MemLogObject, 4317);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v10 = 93;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v8);
    return v8;
  }
  v8 = CPageFile::ReclaimLogicalPages(this, a3, a4);
  if ( v8 )
  {
    if ( v8 != 1168 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, v8);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v8;
      }
      v10 = 94;
      goto LABEL_6;
    }
    try
    {
      v13 = (_QWORD *)((char *)this + 328);
      std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::reserve(
        (char *)this + 328,
        v5 - 0x5555555555555555LL * ((__int64)(*((_QWORD *)this + 42) - *((_QWORD *)this + 41)) >> 3));
      v14 = v5 - 0x5555555555555555LL * ((__int64)(*((_QWORD *)this + 42) - *((_QWORD *)this + 41)) >> 3);
      if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 29) - *((_QWORD *)this + 28)) >> 3) > v14 )
        v14 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 29) - *((_QWORD *)this + 28)) >> 3);
      std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::reserve((char *)this + 224, v14);
    }
    catch ( CX_MemoryException )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, 14);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 14);
      }
      return 14;
    }
    v15 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v13[1] - *v13) >> 3);
    for ( i = 0; i < (unsigned int)v5; ++i )
    {
      v18 = -2;
      v19 = 0;
      v21 = 0;
      v20 = 0;
      std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::push_back(v13, &v18);
    }
    *a4 = v15;
  }
  return 0;
}

```

## disassembly

```asm
0x1800259c0  push    rbx
0x1800259c2  push    rsi
0x1800259c3  push    rdi
0x1800259c4  push    r13
0x1800259c6  push    r14
0x1800259c8  push    r15
0x1800259ca  sub     rsp, 48h
0x1800259ce  mov     r15, r9
0x1800259d1  mov     esi, r8d
0x1800259d4  mov     r14, rcx
0x1800259d7  cmp     dword ptr [rcx+0C4h], 0
0x1800259de  jnz     short loc_180025A34
0x1800259e0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800259e6  mov     ebx, 10DDh
0x1800259eb  mov     edx, ebx
0x1800259ed  mov     rcx, rax
0x1800259f0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800259f6  lea     rax, WPP_GLOBAL_Control
0x1800259fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a04  cmp     rcx, rax
0x180025a07  jz      short loc_180025A2D
0x180025a09  test    byte ptr [rcx+1Ch], 1
0x180025a0d  jz      short loc_180025A2D
0x180025a0f  cmp     byte ptr [rcx+19h], 2
0x180025a13  jb      short loc_180025A2D
0x180025a15  mov     edx, 5Dh ; ']'
0x180025a1a  mov     r9d, ebx
0x180025a1d  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x180025a24  mov     rcx, [rcx+10h]
0x180025a28  call    WPP_SF_d
0x180025a2d  mov     eax, ebx
0x180025a2f  jmp     loc_180025B44
0x180025a34  mov     r8, r15; unsigned int *
0x180025a37  mov     edx, esi; unsigned int
0x180025a39  call    ?ReclaimLogicalPages@CPageFile@@QEAAKKPEAK@Z; CPageFile::ReclaimLogicalPages(ulong,ulong *)
0x180025a3e  mov     ebx, eax
0x180025a40  test    eax, eax
0x180025a42  jnz     short loc_180025A4B
0x180025a44  xor     eax, eax
0x180025a46  jmp     loc_180025B44
0x180025a4b  cmp     ebx, 490h
0x180025a51  jz      short loc_180025A8A
0x180025a53  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025a59  mov     edx, ebx
0x180025a5b  mov     rcx, rax
0x180025a5e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025a64  lea     rax, WPP_GLOBAL_Control
0x180025a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a72  cmp     rcx, rax
0x180025a75  jz      short loc_180025A2D
0x180025a77  test    byte ptr [rcx+1Ch], 1
0x180025a7b  jz      short loc_180025A2D
0x180025a7d  cmp     byte ptr [rcx+19h], 2
0x180025a81  jb      short loc_180025A2D
0x180025a83  mov     edx, 5Eh ; '^'
0x180025a88  jmp     short loc_180025A1A
0x180025a8a  lea     rdi, [r14+148h]
0x180025a91  mov     rdx, [rdi+8]
0x180025a95  sub     rdx, [rdi]
0x180025a98  sar     rdx, 3
0x180025a9c  mov     r13, 0AAAAAAAAAAAAAAABh
0x180025aa6  imul    rdx, r13
0x180025aaa  add     rdx, rsi
0x180025aad  mov     rcx, rdi
0x180025ab0  call    ?reserve@?$vector@UPageMapEntry@@V?$wbem_allocator@UPageMapEntry@@@@@std@@QEAAX_K@Z; std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::reserve(unsigned __int64)
0x180025ab5  lea     rcx, [r14+0E0h]
0x180025abc  mov     rdx, [rdi+8]
0x180025ac0  sub     rdx, [rdi]
0x180025ac3  sar     rdx, 3
0x180025ac7  imul    rdx, r13
0x180025acb  add     rdx, rsi
0x180025ace  mov     rax, [rcx+8]
0x180025ad2  sub     rax, [rcx]
0x180025ad5  sar     rax, 3
0x180025ad9  imul    rax, r13
0x180025add  cmp     rax, rdx
0x180025ae0  cmova   rdx, rax
0x180025ae4  call    ?reserve@?$vector@UPageMapEntry@@V?$wbem_allocator@UPageMapEntry@@@@@std@@QEAAX_K@Z; std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::reserve(unsigned __int64)
0x180025ae9  nop
0x180025aea  mov     rbx, [rdi+8]
0x180025aee  sub     rbx, [rdi]
0x180025af1  sar     rbx, 3
0x180025af5  imul    rbx, r13
0x180025af9  xor     r14d, r14d
0x180025afc  test    esi, esi
0x180025afe  jz      short loc_180025B37
0x180025b00  mov     [rsp+78h+var_58], 0FFFFFFFEh
0x180025b08  mov     [rsp+78h+var_54], 0
0x180025b11  mov     [rsp+78h+var_48], 0
0x180025b1a  mov     [rsp+78h+var_4C], 0
0x180025b22  lea     rdx, [rsp+78h+var_58]
0x180025b27  mov     rcx, rdi
0x180025b2a  call    ?push_back@?$vector@UPageMapEntry@@V?$wbem_allocator@UPageMapEntry@@@@@std@@QEAAXAEBUPageMapEntry@@@Z; std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::push_back(PageMapEntry const &)
0x180025b2f  inc     r14d
0x180025b32  cmp     r14d, esi
0x180025b35  jb      short loc_180025B00
0x180025b37  mov     [r15], ebx
0x180025b3a  jmp     loc_180025A44
0x180025b3f  mov     eax, 0Eh
0x180025b44  add     rsp, 48h
0x180025b48  pop     r15
0x180025b4a  pop     r14
0x180025b4c  pop     r13
0x180025b4e  pop     rdi
0x180025b4f  pop     rsi
0x180025b50  pop     rbx
0x180025b51  retn
```
