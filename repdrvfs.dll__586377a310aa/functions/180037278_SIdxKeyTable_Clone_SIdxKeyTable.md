# SIdxKeyTable::Clone(SIdxKeyTable * *)

- ea: `0x180037278`
- end: `0x180037597`
- name: `?Clone@SIdxKeyTable@@QEAAKPEAPEAV1@@Z`
- size: `799`
- prototype: `__int64 __fastcall(SIdxKeyTable *this, struct SIdxStringPool ***)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011904`

## callees

- `0x1800012b8`
- `0x18000fb3c`
- `0x18000fcf0`
- `0x18002b7b6`
- `0x180037278`
- `0x1800375a0`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003728d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003728d`
- `wbemcomn!GetMemLogObject` at `0x180037309`
- `wbemcomn!GetMemLogObject` at `0x180037386`
- `wbemcomn!GetMemLogObject` at `0x180037405`
- `wbemcomn!GetMemLogObject` at `0x180037484`
- `wbemcomn!GetMemLogObject` at `0x1800374ff`
- `wbemcomn!GetMemLogObject` at `0x180037540`
- `wbemcomn!GetMemLogObject` at `0x180037309`
- `wbemcomn!GetMemLogObject` at `0x180037386`
- `wbemcomn!GetMemLogObject` at `0x180037405`
- `wbemcomn!GetMemLogObject` at `0x180037484`
- `wbemcomn!GetMemLogObject` at `0x1800374ff`
- `wbemcomn!GetMemLogObject` at `0x180037540`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037317`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037396`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037415`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037494`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003750f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037550`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037317`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037396`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037415`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037494`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003750f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037550`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SIdxKeyTable::Clone(SIdxKeyTable *this, struct SIdxStringPool ***a2)
{
  struct SIdxStringPool **v4; // rax
  struct SIdxStringPool **v5; // rbx
  struct SIdxStringPool *v6; // rax
  CMemoryLog *v7; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  struct SIdxStringPool *v10; // rax
  CMemoryLog *v11; // rax
  struct SIdxStringPool *v12; // rax
  CMemoryLog *v13; // rax
  struct SIdxStringPool *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax

  v4 = (struct SIdxStringPool **)CWin32DefaultArena::WbemMemAlloc(0x50u);
  v5 = v4;
  if ( !v4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 8);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v9 = 63;
    goto LABEL_32;
  }
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  *((_DWORD *)v4 + 6) = 0;
  v4[6] = 0;
  v4[7] = 0;
  v4[8] = 0;
  v4[4] = 0;
  v4[5] = 0;
  v4[9] = 0;
  *(_DWORD *)v4 = 1;
  *((_DWORD *)v4 + 1) = *((_DWORD *)this + 1);
  *((_DWORD *)v4 + 2) = *((_DWORD *)this + 2);
  *((_DWORD *)v4 + 3) = *((_DWORD *)this + 3);
  v6 = (struct SIdxStringPool *)_BtrMemAlloc(2LL * *((unsigned int *)this + 6));
  v5[2] = v6;
  if ( !v6 )
  {
    SIdxKeyTable::`scalar deleting destructor'((SIdxKeyTable *)v5);
    v7 = GetMemLogObject();
    CMemoryLog::Write(v7, 8);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v9 = 64;
    goto LABEL_32;
  }
  memcpy_0(v6, *((const void **)this + 2), 2LL * *((unsigned int *)this + 6));
  *((_DWORD *)v5 + 6) = *((_DWORD *)this + 6);
  v10 = (struct SIdxStringPool *)_BtrMemAlloc(4LL * *((unsigned int *)this + 6));
  v5[4] = v10;
  if ( !v10 )
  {
    SIdxKeyTable::`scalar deleting destructor'((SIdxKeyTable *)v5);
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, 8);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v9 = 65;
    goto LABEL_32;
  }
  memcpy_0(v10, *((const void **)this + 4), 4LL * *((unsigned int *)this + 6));
  v12 = (struct SIdxStringPool *)_BtrMemAlloc(4LL * (unsigned int)(*((_DWORD *)this + 6) + 1));
  v5[5] = v12;
  if ( !v12 )
  {
    SIdxKeyTable::`scalar deleting destructor'((SIdxKeyTable *)v5);
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, 8);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v9 = 66;
    goto LABEL_32;
  }
  memcpy_0(v12, *((const void **)this + 5), 4LL * (unsigned int)(*((_DWORD *)this + 6) + 1));
  *((_DWORD *)v5 + 14) = *((_DWORD *)this + 14);
  v14 = (struct SIdxStringPool *)_BtrMemAlloc(2LL * *((unsigned int *)this + 14));
  v5[6] = v14;
  if ( !v14 )
  {
    SIdxKeyTable::`scalar deleting destructor'((SIdxKeyTable *)v5);
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, 8);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v9 = 67;
    goto LABEL_32;
  }
  memcpy_0(v14, *((const void **)this + 6), 2LL * *((unsigned int *)this + 14));
  *((_DWORD *)v5 + 15) = *((_DWORD *)this + 15);
  if ( !SIdxStringPool::Clone(*((SIdxStringPool **)this + 8), v5 + 8) )
  {
    *a2 = v5;
    return 0;
  }
  SIdxKeyTable::`scalar deleting destructor'((SIdxKeyTable *)v5);
  v16 = GetMemLogObject();
  CMemoryLog::Write(v16, 8);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 68;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 8);
  }
  return 8;
}

```

## disassembly

```asm
0x180037278  push    rbx
0x18003727a  push    rbp
0x18003727b  push    rsi
0x18003727c  push    r14
0x18003727e  sub     rsp, 28h
0x180037282  mov     rsi, rcx
0x180037285  mov     r14, rdx
0x180037288  mov     ecx, 50h ; 'P'
0x18003728d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180037293  xor     ebp, ebp
0x180037295  mov     [rsp+48h+arg_10], rax
0x18003729a  mov     rbx, rax
0x18003729d  test    rax, rax
0x1800372a0  jz      loc_180037540
0x1800372a6  mov     [rax], rbp
0x1800372a9  mov     [rax+8], rbp
0x1800372ad  mov     [rax+10h], rbp
0x1800372b1  mov     [rax+18h], ebp
0x1800372b4  mov     [rax+30h], rbp
0x1800372b8  mov     [rax+38h], rbp
0x1800372bc  mov     [rax+40h], rbp
0x1800372c0  mov     [rax+20h], rbp
0x1800372c4  mov     [rax+28h], rbp
0x1800372c8  mov     [rax+48h], rbp
0x1800372cc  test    rax, rax
0x1800372cf  jz      loc_180037540
0x1800372d5  mov     dword ptr [rax], 1
0x1800372db  mov     eax, [rsi+4]
0x1800372de  mov     [rbx+4], eax
0x1800372e1  mov     eax, [rsi+8]
0x1800372e4  mov     [rbx+8], eax
0x1800372e7  mov     eax, [rsi+0Ch]
0x1800372ea  mov     [rbx+0Ch], eax
0x1800372ed  mov     ecx, [rsi+18h]
0x1800372f0  add     rcx, rcx; unsigned __int64
0x1800372f3  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x1800372f8  mov     [rbx+10h], rax
0x1800372fc  test    rax, rax
0x1800372ff  jnz     short loc_180037350
0x180037301  mov     rcx, rbx; this
0x180037304  call    ??_GSIdxKeyTable@@AEAAPEAXI@Z; SIdxKeyTable::`scalar deleting destructor'(uint)
0x180037309  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003730f  lea     ebx, [rbp+8]
0x180037312  mov     rcx, rax
0x180037315  mov     edx, ebx
0x180037317  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003731d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037324  lea     rax, WPP_GLOBAL_Control
0x18003732b  cmp     rcx, rax
0x18003732e  jz      loc_18003758B
0x180037334  test    byte ptr [rcx+1Ch], 1
0x180037338  jz      loc_18003758B
0x18003733e  cmp     byte ptr [rcx+19h], 2
0x180037342  jb      loc_18003758B
0x180037348  lea     edx, [rbp+40h]
0x18003734b  jmp     loc_180037578
0x180037350  mov     r8d, [rsi+18h]
0x180037354  mov     rcx, rax; void *
0x180037357  mov     rdx, [rsi+10h]; Src
0x18003735b  add     r8, r8; Size
0x18003735e  call    memcpy_0
0x180037363  mov     eax, [rsi+18h]
0x180037366  mov     [rbx+18h], eax
0x180037369  mov     ecx, [rsi+18h]
0x18003736c  shl     rcx, 2; unsigned __int64
0x180037370  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x180037375  mov     [rbx+20h], rax
0x180037379  test    rax, rax
0x18003737c  jnz     short loc_1800373CF
0x18003737e  mov     rcx, rbx; this
0x180037381  call    ??_GSIdxKeyTable@@AEAAPEAXI@Z; SIdxKeyTable::`scalar deleting destructor'(uint)
0x180037386  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003738c  mov     ebx, 8
0x180037391  mov     rcx, rax
0x180037394  mov     edx, ebx
0x180037396  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003739c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373a3  lea     rax, WPP_GLOBAL_Control
0x1800373aa  cmp     rcx, rax
0x1800373ad  jz      loc_18003758B
0x1800373b3  test    byte ptr [rcx+1Ch], 1
0x1800373b7  jz      loc_18003758B
0x1800373bd  cmp     byte ptr [rcx+19h], 2
0x1800373c1  jb      loc_18003758B
0x1800373c7  lea     edx, [rbx+39h]
0x1800373ca  jmp     loc_180037578
0x1800373cf  mov     r8d, [rsi+18h]
0x1800373d3  mov     rcx, rax; void *
0x1800373d6  mov     rdx, [rsi+20h]; Src
0x1800373da  shl     r8, 2; Size
0x1800373de  call    memcpy_0
0x1800373e3  mov     ecx, [rsi+18h]
0x1800373e6  inc     ecx
0x1800373e8  shl     rcx, 2; unsigned __int64
0x1800373ec  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x1800373f1  mov     [rbx+28h], rax
0x1800373f5  mov     rcx, rax; void *
0x1800373f8  test    rax, rax
0x1800373fb  jnz     short loc_18003744E
0x1800373fd  mov     rcx, rbx; this
0x180037400  call    ??_GSIdxKeyTable@@AEAAPEAXI@Z; SIdxKeyTable::`scalar deleting destructor'(uint)
0x180037405  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003740b  mov     ebx, 8
0x180037410  mov     rcx, rax
0x180037413  mov     edx, ebx
0x180037415  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003741b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037422  lea     rax, WPP_GLOBAL_Control
0x180037429  cmp     rcx, rax
0x18003742c  jz      loc_18003758B
0x180037432  test    byte ptr [rcx+1Ch], 1
0x180037436  jz      loc_18003758B
0x18003743c  cmp     byte ptr [rcx+19h], 2
0x180037440  jb      loc_18003758B
0x180037446  lea     edx, [rbx+3Ah]
0x180037449  jmp     loc_180037578
0x18003744e  mov     r8d, [rsi+18h]
0x180037452  mov     rdx, [rsi+28h]; Src
0x180037456  inc     r8d
0x180037459  shl     r8, 2; Size
0x18003745d  call    memcpy_0
0x180037462  mov     eax, [rsi+38h]
0x180037465  mov     [rbx+38h], eax
0x180037468  mov     ecx, [rsi+38h]
0x18003746b  add     rcx, rcx; unsigned __int64
0x18003746e  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x180037473  mov     [rbx+30h], rax
0x180037477  test    rax, rax
0x18003747a  jnz     short loc_1800374CD
0x18003747c  mov     rcx, rbx; this
0x18003747f  call    ??_GSIdxKeyTable@@AEAAPEAXI@Z; SIdxKeyTable::`scalar deleting destructor'(uint)
0x180037484  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003748a  mov     ebx, 8
0x18003748f  mov     rcx, rax
0x180037492  mov     edx, ebx
0x180037494  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003749a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800374a1  lea     rax, WPP_GLOBAL_Control
0x1800374a8  cmp     rcx, rax
0x1800374ab  jz      loc_18003758B
0x1800374b1  test    byte ptr [rcx+1Ch], 1
0x1800374b5  jz      loc_18003758B
0x1800374bb  cmp     byte ptr [rcx+19h], 2
0x1800374bf  jb      loc_18003758B
0x1800374c5  lea     edx, [rbx+3Bh]
0x1800374c8  jmp     loc_180037578
0x1800374cd  mov     r8d, [rsi+38h]
0x1800374d1  mov     rcx, rax; void *
0x1800374d4  mov     rdx, [rsi+30h]; Src
0x1800374d8  add     r8, r8; Size
0x1800374db  call    memcpy_0
0x1800374e0  mov     eax, [rsi+3Ch]
0x1800374e3  lea     rdx, [rbx+40h]; struct SIdxStringPool **
0x1800374e7  mov     [rbx+3Ch], eax
0x1800374ea  mov     rcx, [rsi+40h]; this
0x1800374ee  call    ?Clone@SIdxStringPool@@QEAAKPEAPEAU1@@Z; SIdxStringPool::Clone(SIdxStringPool * *)
0x1800374f3  test    eax, eax
0x1800374f5  jz      short loc_180037539
0x1800374f7  mov     rcx, rbx; this
0x1800374fa  call    ??_GSIdxKeyTable@@AEAAPEAXI@Z; SIdxKeyTable::`scalar deleting destructor'(uint)
0x1800374ff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037505  mov     ebx, 8
0x18003750a  mov     rcx, rax
0x18003750d  mov     edx, ebx
0x18003750f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037515  mov     rcx, cs:WPP_GLOBAL_Control
0x18003751c  lea     rax, WPP_GLOBAL_Control
0x180037523  cmp     rcx, rax
0x180037526  jz      short loc_18003758B
0x180037528  test    byte ptr [rcx+1Ch], 1
0x18003752c  jz      short loc_18003758B
0x18003752e  cmp     byte ptr [rcx+19h], 2
0x180037532  jb      short loc_18003758B
0x180037534  lea     edx, [rbx+3Ch]
0x180037537  jmp     short loc_180037578
0x180037539  mov     [r14], rbx
0x18003753c  xor     eax, eax
0x18003753e  jmp     short loc_18003758D
0x180037540  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037546  mov     ebx, 8
0x18003754b  mov     rcx, rax
0x18003754e  mov     edx, ebx
0x180037550  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037556  mov     rcx, cs:WPP_GLOBAL_Control
0x18003755d  lea     rax, WPP_GLOBAL_Control
0x180037564  cmp     rcx, rax
0x180037567  jz      short loc_18003758B
0x180037569  test    byte ptr [rcx+1Ch], 1
0x18003756d  jz      short loc_18003758B
0x18003756f  cmp     byte ptr [rcx+19h], 2
0x180037573  jb      short loc_18003758B
0x180037575  lea     edx, [rbx+37h]
0x180037578  mov     rcx, [rcx+10h]
0x18003757c  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180037583  mov     r9d, ebx
0x180037586  call    WPP_SF_d
0x18003758b  mov     eax, ebx
0x18003758d  add     rsp, 28h
0x180037591  pop     r14
0x180037593  pop     rsi
0x180037594  pop     rbp
0x180037595  pop     rbx
0x180037596  retn
```
