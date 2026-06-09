# CPageFile::PutPage(ulong,ulong,MemoryPage *)

- ea: `0x18000fd30`
- end: `0x18001041a`
- name: `?PutPage@CPageFile@@QEAAKKKPEAVMemoryPage@@@Z`
- size: `1770`
- prototype: `unsigned int __fastcall(CPageFile *__hidden this, unsigned int, unsigned int, struct MemoryPage *)`
- caller_count: `4`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180012e84`
- `0x1800136b8`
- `0x180020b38`
- `0x180025818`

## callees

- `0x1800012b8`
- `0x18000f2ac`
- `0x18000f8f0`
- `0x18000fd30`
- `0x180010420`
- `0x1800112a0`
- `0x18001a4d8`
- `0x18001b434`
- `0x180024854`
- `0x180029f3c`
- `0x18002a6f8`
- `0x1800305a8`
- `0x18003d184`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18000ff10`
- `wbemcomn!GetMemLogObject` at `0x18000ffae`
- `wbemcomn!GetMemLogObject` at `0x18001013b`
- `wbemcomn!GetMemLogObject` at `0x1800101d7`
- `wbemcomn!GetMemLogObject` at `0x180010247`
- `wbemcomn!GetMemLogObject` at `0x1800102a8`
- `wbemcomn!GetMemLogObject` at `0x1800102fd`
- `wbemcomn!GetMemLogObject` at `0x18000ff10`
- `wbemcomn!GetMemLogObject` at `0x18000ffae`
- `wbemcomn!GetMemLogObject` at `0x18001013b`
- `wbemcomn!GetMemLogObject` at `0x1800101d7`
- `wbemcomn!GetMemLogObject` at `0x180010247`
- `wbemcomn!GetMemLogObject` at `0x1800102a8`
- `wbemcomn!GetMemLogObject` at `0x1800102fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ff1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ffba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010149`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800101e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010255`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800102b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010309`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ff1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ffba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010149`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800101e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010255`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800102b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180010309`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CPageFile::PutPage(CPageFile *this, unsigned int a2, __int64 a3, struct MemoryPage *a4)
{
  unsigned __int64 v5; // r14
  __int64 v7; // rdx
  int v8; // esi
  unsigned int v9; // edi
  unsigned int v11; // r12d
  unsigned int v12; // edx
  unsigned int v13; // r14d
  CMemoryLog *v14; // rax
  __int64 *v15; // r14
  unsigned __int64 v16; // rax
  CMemoryLog *v17; // rax
  _QWORD *v18; // r12
  unsigned __int64 v19; // rdx
  _QWORD *v20; // r13
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  CMemoryLog *v23; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  __int64 v28; // r12
  CMemoryLog *v29; // rax
  int v30; // [rsp+20h] [rbp-58h] BYREF
  struct MemoryPage *v31; // [rsp+28h] [rbp-50h]
  __int128 v32; // [rsp+30h] [rbp-48h] BYREF
  __int64 v33; // [rsp+40h] [rbp-38h]
  unsigned int v34; // [rsp+90h] [rbp+18h] BYREF
  MemoryPage *v35; // [rsp+98h] [rbp+20h]

  v35 = a4;
  v5 = a2;
  v31 = a4;
  v34 = -1;
  if ( a4 )
  {
    if ( *((_DWORD *)this + 49) )
    {
      v7 = *((_QWORD *)this + 41);
      if ( v5 >= 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 42) - v7) >> 3) )
      {
        CRepositoryCorruption::SetRepositoryCorrupted(3, 0, 0);
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, 87);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 87);
        }
        MemoryPage::Release(a4);
        return 87;
      }
      else
      {
        v32 = *(_OWORD *)(24 * v5 + v7);
        v8 = v32;
        v33 = *(_QWORD *)(24 * v5 + v7 + 16);
        if ( (_DWORD)v32 == -1 )
        {
          CRepositoryCorruption::SetRepositoryCorrupted(3, 0, 0);
          v25 = GetMemLogObject();
          CMemoryLog::Write(v25, 31);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 31);
          }
          MemoryPage::Release(a4);
          return 31;
        }
        else
        {
          if ( (_DWORD)v32 != -2 )
          {
            if ( (int)v32 < 0 )
            {
              v9 = CPageCache::Write((CPageFile *)((char *)this + 64), v32 & 0x3FFFFFFF, a4, v5);
              if ( v9 )
              {
                v26 = GetMemLogObject();
                CMemoryLog::Write(v26, v9);
              }
              if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v9);
              }
              MemoryPage::Release(a4);
              return v9;
            }
            try
            {
              v18 = (_QWORD *)((char *)this + 432);
              if ( (v32 & 0x40000000) != 0 )
              {
                v19 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3) + 1;
                if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 56) - *((_QWORD *)this + 54)) >> 3) < v19 )
                {
                  if ( v19 > 0xAAAAAAAAAAAAAAALL )
                    std::_Xlength_error("vector<T> too long");
                  std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::_Reallocate((char *)this + 432);
                }
              }
              else
              {
                v20 = (_QWORD *)((char *)this + 352);
                std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve(
                  (char *)this + 352,
                  0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 55) - *((_QWORD *)this + 54)) >> 3)
                + ((__int64)(*((_QWORD *)this + 45) - *((_QWORD *)this + 44)) >> 2)
                + 1);
                std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve(
                  (char *)this + 376,
                  0xAAAAAAAAAAAAAAABuLL * ((__int64)(v18[1] - *v18) >> 3) + ((__int64)(v20[1] - *v20) >> 2) + 1);
                v21 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v18[1] - *v18) >> 3) + ((__int64)(v20[1] - *v20) >> 2) + 1;
                if ( (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2 > v21 )
                  v21 = (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2;
                std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve((char *)this + 248, v21);
                v22 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v18[1] - *v18) >> 3) + ((__int64)(v20[1] - *v20) >> 2) + 1;
                if ( (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2 > v22 )
                  v22 = (__int64)(*((_QWORD *)this + 32) - *((_QWORD *)this + 31)) >> 2;
                std::vector<unsigned long,wbem_allocator<unsigned long>>::reserve((char *)this + 272, v22);
              }
            }
            catch ( CX_MemoryException )
            {
              v29 = GetMemLogObject();
              CMemoryLog::Write(v29, 14);
              if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 14);
              }
              MemoryPage::Release(v35);
              return 14;
            }
          }
          v11 = CPageFile::AllocPhysPage(this, &v34);
          if ( v11 )
          {
            v27 = GetMemLogObject();
            CMemoryLog::Write(v27, v11);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v11);
            }
            MemoryPage::Release(a4);
            return v11;
          }
          else
          {
            v12 = v34;
            *(_DWORD *)(24 * v5 + *((_QWORD *)this + 41)) = v34 | 0x80000000;
            v13 = CPageCache::Write((CPageFile *)((char *)this + 64), v12 & 0x3FFFFFFF, a4, v5);
            if ( v13 )
            {
              v17 = GetMemLogObject();
              CMemoryLog::Write(v17, v13);
              if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v13);
              }
              MemoryPage::Release(a4);
              return v13;
            }
            else
            {
              if ( v8 != -2 )
              {
                if ( (v8 & 0x40000000) != 0 )
                {
                  std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::push_back((char *)this + 432, &v32);
                }
                else
                {
                  v15 = (__int64 *)((char *)this + 352);
                  v30 = v8 & 0x3FFFFFFF;
                  v16 = *((_QWORD *)this + 45);
                  if ( (unsigned __int64)&v30 >= v16 || *v15 > (unsigned __int64)&v30 )
                  {
                    if ( v16 == *((_QWORD *)this + 46) )
                      std::vector<unsigned long,wbem_allocator<unsigned long>>::_Reserve((char *)this + 352, 1);
                    **((_DWORD **)this + 45) = v8 & 0x3FFFFFFF;
                  }
                  else
                  {
                    v28 = *v15;
                    if ( v16 == *((_QWORD *)this + 46) )
                      std::vector<unsigned long,wbem_allocator<unsigned long>>::_Reserve((char *)this + 352, 1);
                    **((_DWORD **)this + 45) = *(_DWORD *)(*v15 + 4 * (((__int64)&v30 - v28) >> 2));
                  }
                  *((_QWORD *)this + 45) += 4LL;
                  std::vector<unsigned long,wbem_allocator<unsigned long>>::push_back(
                    (char *)this + 376,
                    &FREE_PAGE_AGE_INIT_VALUE);
                  CPageCache::Discard((CPageFile *)((char *)this + 64), v8);
                }
              }
              if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 0);
              }
              MemoryPage::Release(a4);
              return 0;
            }
          }
        }
      }
    }
    else
    {
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, 4317);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 4317);
      }
      MemoryPage::Release(a4);
      return 4317;
    }
  }
  else
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x18000fd30  mov     rax, rsp
0x18000fd33  mov     [rax+8], rbx
0x18000fd37  mov     [rax+10h], rsi
0x18000fd3b  mov     [rax+20h], r9
0x18000fd3f  mov     [rax+18h], r8d
0x18000fd43  push    rdi
0x18000fd44  push    r12
0x18000fd46  push    r13
0x18000fd48  push    r14
0x18000fd4a  push    r15
0x18000fd4c  sub     rsp, 50h
0x18000fd50  mov     rbx, r9
0x18000fd53  mov     r14d, edx
0x18000fd56  mov     rdi, rcx
0x18000fd59  mov     [rax-50h], rbx
0x18000fd5d  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x18000fd64  test    r9, r9
0x18000fd67  jz      loc_18001013B
0x18000fd6d  cmp     dword ptr [rcx+0C4h], 0
0x18000fd74  jz      loc_18000FF10
0x18000fd7a  mov     rdx, [rcx+148h]
0x18000fd81  mov     rax, [rcx+150h]
0x18000fd88  sub     rax, rdx
0x18000fd8b  sar     rax, 3
0x18000fd8f  mov     r8, 0AAAAAAAAAAAAAAABh
0x18000fd99  imul    rax, r8
0x18000fd9d  cmp     r14, rax
0x18000fda0  jnb     loc_1800101C8
0x18000fda6  lea     rax, [r14+r14*2]
0x18000fdaa  lea     r15, ds:0[rax*8]
0x18000fdb2  mov     esi, [r15+rdx]
0x18000fdb6  movups  xmm0, xmmword ptr [r15+rdx]
0x18000fdbb  movups  [rsp+78h+var_48], xmm0
0x18000fdc0  movsd   xmm1, qword ptr [r15+rdx+10h]
0x18000fdc7  movsd   [rsp+78h+var_38], xmm1
0x18000fdcd  cmp     esi, 0FFFFFFFFh
0x18000fdd0  jz      loc_180010238
0x18000fdd6  cmp     esi, 0FFFFFFFEh
0x18000fdd9  jz      short loc_18000FE3F
0x18000fddb  test    esi, esi
0x18000fddd  jns     loc_18000FFE7
0x18000fde3  and     esi, 3FFFFFFFh
0x18000fde9  add     rcx, 40h ; '@'; this
0x18000fded  mov     r9d, r14d; unsigned int
0x18000fdf0  mov     r8, rbx; struct MemoryPage *
0x18000fdf3  mov     edx, esi; unsigned int
0x18000fdf5  call    ?Write@CPageCache@@QEAAKKPEAVMemoryPage@@K@Z; CPageCache::Write(ulong,MemoryPage *,ulong)
0x18000fdfa  mov     edi, eax
0x18000fdfc  test    eax, eax
0x18000fdfe  jnz     loc_1800102A8
0x18000fe04  lea     rax, WPP_GLOBAL_Control
0x18000fe0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe12  cmp     rcx, rax
0x18000fe15  jnz     loc_18000FEDF
0x18000fe1b  mov     rcx, rbx; this
0x18000fe1e  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000fe23  mov     eax, edi
0x18000fe25  lea     r11, [rsp+78h+var_28]
0x18000fe2a  mov     rbx, [r11+30h]
0x18000fe2e  mov     rsi, [r11+38h]
0x18000fe32  mov     rsp, r11
0x18000fe35  pop     r15
0x18000fe37  pop     r14
0x18000fe39  pop     r13
0x18000fe3b  pop     r12
0x18000fe3d  pop     rdi
0x18000fe3e  retn
0x18000fe3f  lea     rdx, [rsp+78h+arg_10]; unsigned int *
0x18000fe47  mov     rcx, rdi; this
0x18000fe4a  call    ?AllocPhysPage@CPageFile@@QEAAKPEAK@Z; CPageFile::AllocPhysPage(ulong *)
0x18000fe4f  mov     r12d, eax
0x18000fe52  test    eax, eax
0x18000fe54  jnz     loc_1800102FD
0x18000fe5a  mov     edx, [rsp+78h+arg_10]
0x18000fe61  mov     ecx, edx
0x18000fe63  bts     ecx, 1Fh
0x18000fe67  mov     rax, [rdi+148h]
0x18000fe6e  mov     [r15+rax], ecx
0x18000fe72  and     edx, 3FFFFFFFh; unsigned int
0x18000fe78  mov     r9d, r14d; unsigned int
0x18000fe7b  mov     r8, rbx; struct MemoryPage *
0x18000fe7e  lea     rcx, [rdi+40h]; this
0x18000fe82  call    ?Write@CPageCache@@QEAAKKPEAVMemoryPage@@K@Z; CPageCache::Write(ulong,MemoryPage *,ulong)
0x18000fe87  mov     r14d, eax
0x18000fe8a  test    eax, eax
0x18000fe8c  jnz     loc_18000FFAE
0x18000fe92  cmp     esi, 0FFFFFFFEh
0x18000fe95  jz      short loc_18000FEB3
0x18000fe97  bt      esi, 1Eh
0x18000fe9b  jnb     loc_18000FF4D
0x18000fea1  lea     rcx, [rdi+1B0h]
0x18000fea8  lea     rdx, [rsp+78h+var_48]
0x18000fead  call    ?push_back@?$vector@UPageMapEntry@@V?$wbem_allocator@UPageMapEntry@@@@@std@@QEAAXAEBUPageMapEntry@@@Z; std::vector<PageMapEntry,wbem_allocator<PageMapEntry>>::push_back(PageMapEntry const &)
0x18000feb2  nop
0x18000feb3  lea     rax, WPP_GLOBAL_Control
0x18000feba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fec1  cmp     rcx, rax
0x18000fec4  jz      short loc_18000FED0
0x18000fec6  test    byte ptr [rcx+1Ch], 1
0x18000feca  jnz     loc_1800103F2
0x18000fed0  mov     rcx, rbx; this
0x18000fed3  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000fed8  xor     eax, eax
0x18000feda  jmp     loc_18000FE25
0x18000fedf  test    byte ptr [rcx+1Ch], 1
0x18000fee3  jz      loc_18000FE1B
0x18000fee9  cmp     byte ptr [rcx+19h], 2
0x18000feed  jb      loc_18000FE1B
0x18000fef3  mov     edx, 53h ; 'S'
0x18000fef8  mov     r9d, edi
0x18000fefb  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18000ff02  mov     rcx, [rcx+10h]
0x18000ff06  call    WPP_SF_d
0x18000ff0b  jmp     loc_18000FE1B
0x18000ff10  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ff16  mov     edx, 10DDh
0x18000ff1b  mov     rcx, rax
0x18000ff1e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ff24  lea     rax, WPP_GLOBAL_Control
0x18000ff2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff32  cmp     rcx, rax
0x18000ff35  jnz     loc_180010194
0x18000ff3b  mov     rcx, rbx; this
0x18000ff3e  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000ff43  mov     eax, 10DDh
0x18000ff48  jmp     loc_18000FE25
0x18000ff4d  lea     r14, [rdi+160h]
0x18000ff54  mov     r12d, esi
0x18000ff57  and     r12d, 3FFFFFFFh
0x18000ff5e  mov     [rsp+78h+var_58], r12d
0x18000ff63  mov     rax, [r14+8]
0x18000ff67  lea     rcx, [rsp+78h+var_58]
0x18000ff6c  cmp     rcx, rax
0x18000ff6f  jb      loc_180010388
0x18000ff75  cmp     rax, [r14+10h]
0x18000ff79  jz      loc_1800103C9
0x18000ff7f  mov     rax, [r14+8]
0x18000ff83  mov     [rax], r12d
0x18000ff86  add     qword ptr [r14+8], 4
0x18000ff8b  lea     rcx, [rdi+178h]
0x18000ff92  lea     rdx, ?FREE_PAGE_AGE_INIT_VALUE@@3KA; ulong FREE_PAGE_AGE_INIT_VALUE
0x18000ff99  call    ?push_back@?$vector@KV?$wbem_allocator@K@@@std@@QEAAXAEBK@Z; std::vector<ulong,wbem_allocator<ulong>>::push_back(ulong const &)
0x18000ff9e  mov     edx, esi; unsigned int
0x18000ffa0  lea     rcx, [rdi+40h]; this
0x18000ffa4  call    ?Discard@CPageCache@@QEAAKK@Z; CPageCache::Discard(ulong)
0x18000ffa9  jmp     loc_18000FEB3
0x18000ffae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ffb4  mov     edx, r14d
0x18000ffb7  mov     rcx, rax
0x18000ffba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ffc0  lea     rax, WPP_GLOBAL_Control
0x18000ffc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffce  cmp     rcx, rax
0x18000ffd1  jnz     loc_180010357
0x18000ffd7  mov     rcx, rbx; this
0x18000ffda  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000ffdf  mov     eax, r14d
0x18000ffe2  jmp     loc_18000FE25
0x18000ffe7  lea     r12, [rcx+1B0h]
0x18000ffee  bt      esi, 1Eh
0x18000fff2  jnb     short loc_180010027
0x18000fff4  mov     rdx, [r12+8]
0x18000fff9  sub     rdx, [r12]
0x18000fffd  sar     rdx, 3
0x180010001  imul    rdx, r8
0x180010005  inc     rdx
0x180010008  mov     rax, [r12+10h]
0x18001000d  sub     rax, [r12]
0x180010011  sar     rax, 3
0x180010015  imul    rax, r8
0x180010019  cmp     rax, rdx
0x18001001c  jb      loc_1800102BE
0x180010022  jmp     loc_18000FE3F
0x180010027  lea     r13, [rcx+160h]
0x18001002e  mov     rcx, [r12+8]
0x180010033  sub     rcx, [r12]
0x180010037  sar     rcx, 3
0x18001003b  imul    rcx, r8
0x18001003f  mov     rdx, [r13+8]
0x180010043  sub     rdx, [r13+0]
0x180010047  sar     rdx, 2
0x18001004b  inc     rdx
0x18001004e  add     rdx, rcx
0x180010051  mov     rcx, r13
0x180010054  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x180010059  mov     rcx, [r12+8]
0x18001005e  sub     rcx, [r12]
0x180010062  sar     rcx, 3
0x180010066  mov     rax, 0AAAAAAAAAAAAAAABh
0x180010070  imul    rcx, rax
0x180010074  mov     rdx, [r13+8]
0x180010078  sub     rdx, [r13+0]
0x18001007c  sar     rdx, 2
0x180010080  inc     rdx
0x180010083  add     rdx, rcx
0x180010086  lea     rcx, [rdi+178h]
0x18001008d  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x180010092  mov     rcx, [r12+8]
0x180010097  sub     rcx, [r12]
0x18001009b  sar     rcx, 3
0x18001009f  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800100a9  imul    rcx, rax
0x1800100ad  mov     rdx, [r13+8]
0x1800100b1  sub     rdx, [r13+0]
0x1800100b5  sar     rdx, 2
0x1800100b9  inc     rdx
0x1800100bc  add     rdx, rcx
0x1800100bf  mov     rax, [rdi+100h]
0x1800100c6  sub     rax, [rdi+0F8h]
0x1800100cd  sar     rax, 2
0x1800100d1  cmp     rax, rdx
0x1800100d4  cmova   rdx, rax
0x1800100d8  lea     rcx, [rdi+0F8h]
0x1800100df  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x1800100e4  mov     rcx, [r12+8]
0x1800100e9  sub     rcx, [r12]
0x1800100ed  sar     rcx, 3
0x1800100f1  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800100fb  imul    rcx, rax
0x1800100ff  mov     rdx, [r13+8]
0x180010103  sub     rdx, [r13+0]
0x180010107  sar     rdx, 2
0x18001010b  inc     rdx
0x18001010e  add     rdx, rcx
0x180010111  mov     rax, [rdi+100h]
0x180010118  sub     rax, [rdi+0F8h]
0x18001011f  sar     rax, 2
0x180010123  cmp     rax, rdx
0x180010126  cmova   rdx, rax
0x18001012a  lea     rcx, [rdi+110h]
0x180010131  call    ?reserve@?$vector@KV?$wbem_allocator@K@@@std@@QEAAX_K@Z; std::vector<ulong,wbem_allocator<ulong>>::reserve(unsigned __int64)
0x180010136  jmp     loc_180010022
0x18001013b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180010141  mov     edx, 57h ; 'W'
0x180010146  mov     rcx, rax
0x180010149  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001014f  lea     rax, WPP_GLOBAL_Control
0x180010156  mov     rcx, cs:WPP_GLOBAL_Control
0x18001015d  cmp     rcx, rax
0x180010160  jz      short loc_18001018A
0x180010162  test    byte ptr [rcx+1Ch], 1
0x180010166  jz      short loc_18001018A
0x180010168  cmp     byte ptr [rcx+19h], 2
0x18001016c  jb      short loc_18001018A
0x18001016e  mov     edx, 4Fh ; 'O'
0x180010173  mov     r9d, 57h ; 'W'
0x180010179  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x180010180  mov     rcx, [rcx+10h]
0x180010184  call    WPP_SF_d
0x180010189  nop
0x18001018a  mov     eax, 57h ; 'W'
0x18001018f  jmp     loc_18000FE25
0x180010194  test    byte ptr [rcx+1Ch], 1
0x180010198  jz      loc_18000FF3B
0x18001019e  cmp     byte ptr [rcx+19h], 2
0x1800101a2  jb      loc_18000FF3B
0x1800101a8  mov     edx, 50h ; 'P'
0x1800101ad  mov     r9d, 10DDh
0x1800101b3  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x1800101ba  mov     rcx, [rcx+10h]
0x1800101be  call    WPP_SF_d
0x1800101c3  jmp     loc_18000FF3B
0x1800101c8  xor     r8d, r8d; unsigned int
0x1800101cb  xor     edx, edx; bool
0x1800101cd  mov     ecx, 3; int
0x1800101d2  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x1800101d7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800101dd  mov     edx, 57h ; 'W'
0x1800101e2  mov     rcx, rax
0x1800101e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800101eb  lea     rax, WPP_GLOBAL_Control
0x1800101f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101f9  cmp     rcx, rax
0x1800101fc  jz      short loc_180010226
0x1800101fe  test    byte ptr [rcx+1Ch], 1
0x180010202  jz      short loc_180010226
0x180010204  cmp     byte ptr [rcx+19h], 2
0x180010208  jb      short loc_180010226
0x18001020a  mov     edx, 51h ; 'Q'
0x18001020f  mov     r9d, 57h ; 'W'
0x180010215  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001021c  mov     rcx, [rcx+10h]
0x180010220  call    WPP_SF_d
0x180010225  nop
0x180010226  mov     rcx, rbx; this
0x180010229  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18001022e  mov     eax, 57h ; 'W'
0x180010233  jmp     loc_18000FE25
0x180010238  xor     r8d, r8d; unsigned int
0x18001023b  xor     edx, edx; bool
0x18001023d  mov     ecx, 3; int
0x180010242  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x180010247  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001024d  mov     edx, 1Fh
0x180010252  mov     rcx, rax
0x180010255  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001025b  lea     rax, WPP_GLOBAL_Control
0x180010262  mov     rcx, cs:WPP_GLOBAL_Control
0x180010269  cmp     rcx, rax
0x18001026c  jz      short loc_180010296
  ... truncated ...
```
