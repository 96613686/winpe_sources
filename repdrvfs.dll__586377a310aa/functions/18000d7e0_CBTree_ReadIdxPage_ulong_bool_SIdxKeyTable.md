# CBTree::ReadIdxPage(ulong,bool,SIdxKeyTable * *)

- ea: `0x18000d7e0`
- end: `0x18000dbf3`
- name: `?ReadIdxPage@CBTree@@AEAAKK_NPEAPEAVSIdxKeyTable@@@Z`
- size: `1043`
- prototype: `unsigned int(CBTree *__hidden this, unsigned int, bool, struct SIdxKeyTable **)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d220`
- `0x18000dc00`
- `0x180010fe4`
- `0x180011904`
- `0x180012590`
- `0x18002822c`
- `0x180029d4c`
- `0x180037d18`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000d7e0`
- `0x18000e000`
- `0x18000e920`
- `0x18000f8f0`
- `0x18000fb3c`
- `0x1800129a0`
- `0x18003d184`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000d87e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000d87e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000dae9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000dae9`
- `wbemcomn!GetMemLogObject` at `0x18000d9a1`
- `wbemcomn!GetMemLogObject` at `0x18000da16`
- `wbemcomn!GetMemLogObject` at `0x18000da57`
- `wbemcomn!GetMemLogObject` at `0x18000daa7`
- `wbemcomn!GetMemLogObject` at `0x18000db0c`
- `wbemcomn!GetMemLogObject` at `0x18000db5d`
- `wbemcomn!GetMemLogObject` at `0x18000dbab`
- `wbemcomn!GetMemLogObject` at `0x18000d9a1`
- `wbemcomn!GetMemLogObject` at `0x18000da16`
- `wbemcomn!GetMemLogObject` at `0x18000da57`
- `wbemcomn!GetMemLogObject` at `0x18000daa7`
- `wbemcomn!GetMemLogObject` at `0x18000db0c`
- `wbemcomn!GetMemLogObject` at `0x18000db5d`
- `wbemcomn!GetMemLogObject` at `0x18000dbab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d9af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000da21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000da62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dab2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000db1a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000db6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dbb6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d9af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000da21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000da62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dab2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000db1a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000db6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dbb6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d8e6`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d8e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBTree::ReadIdxPage(CBTree *this, unsigned int a2, __int64 a3, struct SIdxKeyTable **a4)
{
  char v5; // r15
  __int64 v8; // rbx
  unsigned int Page; // ebx
  volatile signed __int32 *v10; // rdi
  struct MemoryPage *v11; // rbp
  void *v12; // r15
  MemoryPage *v13; // rax
  MemoryPage *v14; // rbx
  unsigned int v15; // ebp
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CVarObjHeap *v21; // rcx
  __int64 v22; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  MemoryPage *v26; // [rsp+88h] [rbp+20h] BYREF

  v5 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  if ( a4 )
  {
    *a4 = 0;
    v8 = *(_QWORD *)this;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
    }
    v26 = 0;
    Page = CPageFile::GetPage(*(CPageFile **)(v8 + 8), a2, a3, &v26);
    if ( !Page )
    {
      v10 = (volatile signed __int32 *)v26;
      v11 = v26;
      if ( !v5 )
        v11 = 0;
      v12 = (void *)*((_QWORD *)v26 + 2);
      v13 = (MemoryPage *)CWin32DefaultArena::WbemMemAlloc(0x50u);
      v14 = v13;
      v26 = v13;
      if ( v13 )
      {
        *(_QWORD *)v13 = 0;
        *((_QWORD *)v13 + 1) = 0;
        *((_QWORD *)v13 + 2) = 0;
        *((_DWORD *)v13 + 6) = 0;
        *((_QWORD *)v13 + 6) = 0;
        *((_QWORD *)v13 + 7) = 0;
        *((_QWORD *)v13 + 8) = 0;
        *((_QWORD *)v13 + 4) = 0;
        *((_QWORD *)v13 + 5) = 0;
        *((_QWORD *)v13 + 9) = 0;
        v15 = SIdxKeyTable::MapFromPage(v13, v12, v11);
        if ( !v15 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v14);
          if ( *v10 != 1313820496
            || *((_DWORD *)v10 + 1) != 1347374926
            || (unsigned int)(*((_DWORD *)v10 + 2) - 1) > 0xFFF )
          {
            DebugBreak();
          }
          if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
            CWin32DefaultArena::WbemMemFree((void *)v10);
          if ( a2 == *((_DWORD *)v14 + 1) )
          {
            *a4 = v14;
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 0);
            }
            return 0;
          }
          else
          {
            SIdxKeyTable::Release(v14);
            CRepositoryCorruption::SetRepositoryCorrupted(1, 0, 0);
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, 1358);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 1358);
            }
            return 1358;
          }
        }
        SIdxKeyTable::`scalar deleting destructor'(v14);
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, v15);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_56;
        }
        v22 = 90;
      }
      else
      {
        v24 = GetMemLogObject();
        v15 = 8;
        CMemoryLog::Write(v24, 8);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_56;
        }
        v22 = 89;
      }
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v15);
LABEL_56:
      MemoryPage::Release((MemoryPage *)v10);
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, v15);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v15);
      }
      return v15;
    }
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, Page);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, Page);
    }
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, Page);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, Page);
    }
    return Page;
  }
  else
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x18000d7e0  push    rbx
0x18000d7e2  push    rbp
0x18000d7e3  push    rsi
0x18000d7e4  push    rdi
0x18000d7e5  push    r12
0x18000d7e7  push    r13
0x18000d7e9  push    r14
0x18000d7eb  push    r15
0x18000d7ed  sub     rsp, 28h
0x18000d7f1  mov     rsi, r9
0x18000d7f4  movzx   r15d, r8b
0x18000d7f8  mov     r14d, edx
0x18000d7fb  mov     rbx, rcx
0x18000d7fe  lea     r13, WPP_GLOBAL_Control
0x18000d805  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d80c  cmp     rcx, r13
0x18000d80f  jnz     loc_18000D92B
0x18000d815  test    rsi, rsi
0x18000d818  jz      loc_18000D9A1
0x18000d81e  xor     r12d, r12d
0x18000d821  mov     [rsi], r12
0x18000d824  mov     rbx, [rbx]
0x18000d827  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d82e  cmp     rcx, r13
0x18000d831  jz      short loc_18000D83D
0x18000d833  test    byte ptr [rcx+1Ch], 1
0x18000d837  jnz     loc_18000D9F2
0x18000d83d  mov     [rsp+68h+arg_18], r12
0x18000d845  lea     r9, [rsp+68h+arg_18]; struct MemoryPage **
0x18000d84d  mov     edx, r14d; unsigned int
0x18000d850  mov     rcx, [rbx+8]; this
0x18000d854  call    ?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z; CPageFile::GetPage(ulong,ulong,MemoryPage * *)
0x18000d859  mov     ebx, eax
0x18000d85b  test    eax, eax
0x18000d85d  jnz     loc_18000DA16
0x18000d863  mov     rdi, [rsp+68h+arg_18]
0x18000d86b  mov     rbp, rdi
0x18000d86e  test    r15b, r15b
0x18000d871  cmovz   rbp, r12
0x18000d875  mov     r15, [rdi+10h]
0x18000d879  mov     ecx, 50h ; 'P'
0x18000d87e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000d884  mov     rbx, rax
0x18000d887  mov     [rsp+68h+arg_18], rax
0x18000d88f  test    rax, rax
0x18000d892  jz      loc_18000DB5D
0x18000d898  mov     [rax], r12
0x18000d89b  mov     [rax+8], r12
0x18000d89f  mov     [rax+10h], r12
0x18000d8a3  mov     [rax+18h], r12d
0x18000d8a7  mov     [rax+30h], r12
0x18000d8ab  mov     [rax+38h], r12
0x18000d8af  mov     [rax+40h], r12
0x18000d8b3  mov     [rax+20h], r12
0x18000d8b7  mov     [rax+28h], r12
0x18000d8bb  mov     [rax+48h], r12
0x18000d8bf  mov     r8, rbp; struct MemoryPage *
0x18000d8c2  mov     rdx, r15; void *
0x18000d8c5  mov     rcx, rax; this
0x18000d8c8  call    ?MapFromPage@SIdxKeyTable@@QEAAKPEAXPEAVMemoryPage@@@Z; SIdxKeyTable::MapFromPage(void *,MemoryPage *)
0x18000d8cd  mov     ebp, eax
0x18000d8cf  test    eax, eax
0x18000d8d1  jnz     loc_18000DA9F
0x18000d8d7  lock inc dword ptr [rbx]
0x18000d8da  cmp     dword ptr [rdi], 4E4F4F50h
0x18000d8e0  jz      loc_18000D97F
0x18000d8e6  call    cs:__imp_DebugBreak
0x18000d8ec  mov     eax, 0FFFFFFFFh
0x18000d8f1  lock xadd [rdi+8], eax
0x18000d8f6  cmp     eax, 1
0x18000d8f9  jz      loc_18000DAE6
0x18000d8ff  cmp     r14d, [rbx+4]
0x18000d903  jnz     loc_18000DAF5
0x18000d909  mov     [rsi], rbx
0x18000d90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d913  cmp     rcx, r13
0x18000d916  jnz     short loc_18000D959
0x18000d918  xor     eax, eax
0x18000d91a  add     rsp, 28h
0x18000d91e  pop     r15
0x18000d920  pop     r14
0x18000d922  pop     r13
0x18000d924  pop     r12
0x18000d926  pop     rdi
0x18000d927  pop     rsi
0x18000d928  pop     rbp
0x18000d929  pop     rbx
0x18000d92a  retn
0x18000d92b  test    byte ptr [rcx+1Ch], 1
0x18000d92f  jz      loc_18000D815
0x18000d935  cmp     byte ptr [rcx+19h], 5
0x18000d939  jb      loc_18000D815
0x18000d93f  mov     edx, 7Dh ; '}'
0x18000d944  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000d94b  mov     rcx, [rcx+10h]
0x18000d94f  call    WPP_SF_
0x18000d954  jmp     loc_18000D815
0x18000d959  test    byte ptr [rcx+1Ch], 1
0x18000d95d  jz      short loc_18000D918
0x18000d95f  cmp     byte ptr [rcx+19h], 2
0x18000d963  jb      short loc_18000D918
0x18000d965  mov     edx, 83h
0x18000d96a  xor     r9d, r9d
0x18000d96d  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000d974  mov     rcx, [rcx+10h]
0x18000d978  call    WPP_SF_d
0x18000d97d  jmp     short loc_18000D918
0x18000d97f  cmp     dword ptr [rdi+4], 504F4F4Eh
0x18000d986  jnz     loc_18000D8E6
0x18000d98c  mov     eax, [rdi+8]
0x18000d98f  dec     eax
0x18000d991  cmp     eax, 0FFFh
0x18000d996  jbe     loc_18000D8EC
0x18000d99c  jmp     loc_18000D8E6
0x18000d9a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000d9a7  mov     edx, 57h ; 'W'
0x18000d9ac  mov     rcx, rax
0x18000d9af  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000d9b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9bc  cmp     rcx, r13
0x18000d9bf  jz      short loc_18000D9E8
0x18000d9c1  test    byte ptr [rcx+1Ch], 1
0x18000d9c5  jz      short loc_18000D9E8
0x18000d9c7  cmp     byte ptr [rcx+19h], 2
0x18000d9cb  jb      short loc_18000D9E8
0x18000d9cd  mov     edx, 7Eh ; '~'
0x18000d9d2  mov     r9d, 57h ; 'W'
0x18000d9d8  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000d9df  mov     rcx, [rcx+10h]
0x18000d9e3  call    WPP_SF_d
0x18000d9e8  mov     eax, 57h ; 'W'
0x18000d9ed  jmp     loc_18000D91A
0x18000d9f2  cmp     byte ptr [rcx+19h], 5
0x18000d9f6  jb      loc_18000D83D
0x18000d9fc  mov     edx, 12h
0x18000da01  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000da08  mov     rcx, [rcx+10h]
0x18000da0c  call    WPP_SF_
0x18000da11  jmp     loc_18000D83D
0x18000da16  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000da1c  mov     edx, ebx
0x18000da1e  mov     rcx, rax
0x18000da21  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000da27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da2e  cmp     rcx, r13
0x18000da31  jz      short loc_18000DA57
0x18000da33  test    byte ptr [rcx+1Ch], 1
0x18000da37  jz      short loc_18000DA57
0x18000da39  cmp     byte ptr [rcx+19h], 2
0x18000da3d  jb      short loc_18000DA57
0x18000da3f  mov     edx, 14h
0x18000da44  mov     r9d, ebx
0x18000da47  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000da4e  mov     rcx, [rcx+10h]
0x18000da52  call    WPP_SF_d
0x18000da57  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000da5d  mov     edx, ebx
0x18000da5f  mov     rcx, rax
0x18000da62  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000da68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da6f  cmp     rcx, r13
0x18000da72  jz      short loc_18000DA98
0x18000da74  test    byte ptr [rcx+1Ch], 1
0x18000da78  jz      short loc_18000DA98
0x18000da7a  cmp     byte ptr [rcx+19h], 2
0x18000da7e  jb      short loc_18000DA98
0x18000da80  mov     edx, 7Fh
0x18000da85  mov     r9d, ebx
0x18000da88  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000da8f  mov     rcx, [rcx+10h]
0x18000da93  call    WPP_SF_d
0x18000da98  mov     eax, ebx
0x18000da9a  jmp     loc_18000D91A
0x18000da9f  mov     rcx, rbx; this
0x18000daa2  call    ??_GSIdxKeyTable@@AEAAPEAXI@Z; SIdxKeyTable::`scalar deleting destructor'(uint)
0x18000daa7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000daad  mov     edx, ebp
0x18000daaf  mov     rcx, rax
0x18000dab2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000dab8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dabf  cmp     rcx, r13
0x18000dac2  jz      loc_18000DBA3
0x18000dac8  test    byte ptr [rcx+1Ch], 1
0x18000dacc  jz      loc_18000DBA3
0x18000dad2  cmp     byte ptr [rcx+19h], 2
0x18000dad6  jb      loc_18000DBA3
0x18000dadc  mov     edx, 5Ah ; 'Z'
0x18000dae1  jmp     loc_18000DB90
0x18000dae6  mov     rcx, rdi
0x18000dae9  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000daef  nop
0x18000daf0  jmp     loc_18000D8FF
0x18000daf5  mov     rcx, rbx; this
0x18000daf8  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x18000dafd  xor     r8d, r8d; unsigned int
0x18000db00  xor     edx, edx; bool
0x18000db02  mov     ecx, 1; int
0x18000db07  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18000db0c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000db12  mov     edx, 54Eh
0x18000db17  mov     rcx, rax
0x18000db1a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000db20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db27  cmp     rcx, r13
0x18000db2a  jz      short loc_18000DB53
0x18000db2c  test    byte ptr [rcx+1Ch], 1
0x18000db30  jz      short loc_18000DB53
0x18000db32  cmp     byte ptr [rcx+19h], 2
0x18000db36  jb      short loc_18000DB53
0x18000db38  mov     edx, 82h
0x18000db3d  mov     r9d, 54Eh
0x18000db43  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000db4a  mov     rcx, [rcx+10h]
0x18000db4e  call    WPP_SF_d
0x18000db53  mov     eax, 54Eh
0x18000db58  jmp     loc_18000D91A
0x18000db5d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000db63  mov     ebp, 8
0x18000db68  mov     edx, ebp
0x18000db6a  mov     rcx, rax
0x18000db6d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000db73  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db7a  cmp     rcx, r13
0x18000db7d  jz      short loc_18000DBA3
0x18000db7f  test    byte ptr [rcx+1Ch], 1
0x18000db83  jz      short loc_18000DBA3
0x18000db85  cmp     byte ptr [rcx+19h], 2
0x18000db89  jb      short loc_18000DBA3
0x18000db8b  mov     edx, 59h ; 'Y'
0x18000db90  mov     r9d, ebp
0x18000db93  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000db9a  mov     rcx, [rcx+10h]
0x18000db9e  call    WPP_SF_d
0x18000dba3  mov     rcx, rdi; this
0x18000dba6  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18000dbab  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000dbb1  mov     edx, ebp
0x18000dbb3  mov     rcx, rax
0x18000dbb6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000dbbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbc3  cmp     rcx, r13
0x18000dbc6  jz      short loc_18000DBEC
0x18000dbc8  test    byte ptr [rcx+1Ch], 1
0x18000dbcc  jz      short loc_18000DBEC
0x18000dbce  cmp     byte ptr [rcx+19h], 2
0x18000dbd2  jb      short loc_18000DBEC
0x18000dbd4  mov     edx, 80h
0x18000dbd9  mov     r9d, ebp
0x18000dbdc  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000dbe3  mov     rcx, [rcx+10h]
0x18000dbe7  call    WPP_SF_d
0x18000dbec  mov     eax, ebp
0x18000dbee  jmp     loc_18000D91A
```
