# SIdxKeyTable::Create(void *,MemoryPage *,SIdxKeyTable * *)

- ea: `0x18000f130`
- end: `0x18000f26b`
- name: `?Create@SIdxKeyTable@@SAKPEAXPEAVMemoryPage@@PEAPEAV1@@Z`
- size: `315`
- prototype: `unsigned int __fastcall(void *, struct MemoryPage *, struct SIdxKeyTable **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037a98`

## callees

- `0x1800012b8`
- `0x18000e920`
- `0x18000f130`
- `0x18000fb3c`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f14a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000f14a`
- `wbemcomn!GetMemLogObject` at `0x18000f1c7`
- `wbemcomn!GetMemLogObject` at `0x18000f213`
- `wbemcomn!GetMemLogObject` at `0x18000f1c7`
- `wbemcomn!GetMemLogObject` at `0x18000f213`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f1d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f221`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f1d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000f221`

## pseudocode

```c
unsigned int __fastcall SIdxKeyTable::Create(void *a1, struct MemoryPage *a2, struct SIdxKeyTable **a3)
{
  SIdxKeyTable *v6; // rax
  SIdxKeyTable *v7; // rbx
  unsigned int result; // eax
  unsigned int v9; // esi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v11; // rax

  v6 = (SIdxKeyTable *)CWin32DefaultArena::WbemMemAlloc(0x50u);
  v7 = v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_DWORD *)v6 + 6) = 0;
    *((_QWORD *)v6 + 6) = 0;
    *((_QWORD *)v6 + 7) = 0;
    *((_QWORD *)v6 + 8) = 0;
    *((_QWORD *)v6 + 4) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *((_QWORD *)v6 + 9) = 0;
    result = SIdxKeyTable::MapFromPage(v6, a1, a2);
    v9 = result;
    if ( result )
    {
      *a3 = 0;
      SIdxKeyTable::`scalar deleting destructor'(v7);
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v9);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v9);
      }
      return v9;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)v7);
      *a3 = v7;
    }
  }
  else
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, 8);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 8);
    }
    return 8;
  }
  return result;
}

```

## disassembly

```asm
0x18000f130  mov     [rsp+arg_8], rbx
0x18000f135  push    rbp
0x18000f136  push    rsi
0x18000f137  push    rdi
0x18000f138  sub     rsp, 20h
0x18000f13c  mov     rbp, rcx
0x18000f13f  mov     rdi, r8
0x18000f142  mov     ecx, 50h ; 'P'
0x18000f147  mov     rsi, rdx
0x18000f14a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000f150  mov     [rsp+38h+arg_18], rax
0x18000f155  mov     rbx, rax
0x18000f158  test    rax, rax
0x18000f15b  jz      loc_18000F213
0x18000f161  mov     [rsp+38h+arg_0], r14
0x18000f166  mov     r8, rsi; struct MemoryPage *
0x18000f169  xor     r14d, r14d
0x18000f16c  mov     rdx, rbp; void *
0x18000f16f  mov     rcx, rax; this
0x18000f172  mov     [rax], r14
0x18000f175  mov     [rax+8], r14
0x18000f179  mov     [rax+10h], r14
0x18000f17d  mov     [rax+18h], r14d
0x18000f181  mov     [rax+30h], r14
0x18000f185  mov     [rax+38h], r14
0x18000f189  mov     [rax+40h], r14
0x18000f18d  mov     [rax+20h], r14
0x18000f191  mov     [rax+28h], r14
0x18000f195  mov     [rax+48h], r14
0x18000f199  call    ?MapFromPage@SIdxKeyTable@@QEAAKPEAXPEAVMemoryPage@@@Z; SIdxKeyTable::MapFromPage(void *,MemoryPage *)
0x18000f19e  mov     esi, eax
0x18000f1a0  test    eax, eax
0x18000f1a2  jnz     short loc_18000F1BC
0x18000f1a4  lock inc dword ptr [rbx]
0x18000f1a7  mov     [rdi], rbx
0x18000f1aa  mov     r14, [rsp+38h+arg_0]
0x18000f1af  mov     rbx, [rsp+38h+arg_8]
0x18000f1b4  add     rsp, 20h
0x18000f1b8  pop     rdi
0x18000f1b9  pop     rsi
0x18000f1ba  pop     rbp
0x18000f1bb  retn
0x18000f1bc  mov     rcx, rbx; this
0x18000f1bf  mov     [rdi], r14
0x18000f1c2  call    ??_GSIdxKeyTable@@AEAAPEAXI@Z; SIdxKeyTable::`scalar deleting destructor'(uint)
0x18000f1c7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f1cd  mov     rcx, rax
0x18000f1d0  mov     edx, esi
0x18000f1d2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1df  lea     rax, WPP_GLOBAL_Control
0x18000f1e6  cmp     rcx, rax
0x18000f1e9  jz      short loc_18000F20F
0x18000f1eb  test    byte ptr [rcx+1Ch], 1
0x18000f1ef  jz      short loc_18000F20F
0x18000f1f1  cmp     byte ptr [rcx+19h], 2
0x18000f1f5  jb      short loc_18000F20F
0x18000f1f7  mov     rcx, [rcx+10h]
0x18000f1fb  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000f202  mov     edx, 5Ah ; 'Z'
0x18000f207  mov     r9d, esi
0x18000f20a  call    WPP_SF_d
0x18000f20f  mov     eax, esi
0x18000f211  jmp     short loc_18000F1AA
0x18000f213  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000f219  mov     rcx, rax
0x18000f21c  mov     edx, 8
0x18000f221  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000f227  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f22e  lea     rax, WPP_GLOBAL_Control
0x18000f235  cmp     rcx, rax
0x18000f238  jz      short loc_18000F261
0x18000f23a  test    byte ptr [rcx+1Ch], 1
0x18000f23e  jz      short loc_18000F261
0x18000f240  cmp     byte ptr [rcx+19h], 2
0x18000f244  jb      short loc_18000F261
0x18000f246  mov     rcx, [rcx+10h]
0x18000f24a  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000f251  mov     edx, 59h ; 'Y'
0x18000f256  mov     r9d, 8
0x18000f25c  call    WPP_SF_d
0x18000f261  mov     eax, 8
0x18000f266  jmp     loc_18000F1AF
```
