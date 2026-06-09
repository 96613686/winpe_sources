# CComServer::AddClassInfo(_GUID const &,CUnkInternal *,ushort *,int,int)

- ea: `0x1800427e8`
- end: `0x1800429de`
- name: `?AddClassInfo@CComServer@@IEAAJAEBU_GUID@@PEAVCUnkInternal@@PEAGHH@Z`
- size: `502`
- prototype: `__int64 __fastcall(CComServer *this, const struct _GUID *, struct CUnkInternal *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ea00`

## callees

- `0x1800013a0`
- `0x180013880`
- `0x1800427b0`
- `0x1800427e8`

## import_xrefs

- `wbemcomn!?InternalAddRef@CUnkInternal@@QEAAKXZ` at `0x1800428f7`
- `wbemcomn!?InternalAddRef@CUnkInternal@@QEAAKXZ` at `0x1800428f7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180042855`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180042911`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180042855`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180042911`
- `wbemcomn!GetMemLogObject` at `0x1800427ff`
- `wbemcomn!GetMemLogObject` at `0x1800428a6`
- `wbemcomn!GetMemLogObject` at `0x180042920`
- `wbemcomn!GetMemLogObject` at `0x1800427ff`
- `wbemcomn!GetMemLogObject` at `0x1800428a6`
- `wbemcomn!GetMemLogObject` at `0x180042920`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004280f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800428b6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042930`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004280f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800428b6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180042930`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CComServer::AddClassInfo(
        CComServer *this,
        const struct _GUID *a2,
        struct CUnkInternal *a3,
        unsigned __int16 *a4)
{
  CMemoryLog *MemLogObject; // rax
  char *v7; // rbx
  CMemoryLog *v8; // rax
  unsigned __int16 *v9; // rax
  CMemoryLog *v10; // rax
  struct _LIST_ENTRY *v11; // rcx

  if ( !a3 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147024882);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids);
    }
    return 2147942414LL;
  }
  v7 = (char *)CWin32DefaultArena::WbemMemAlloc(0x40u);
  if ( v7 )
  {
    *(_QWORD *)v7 = &CClassInfo::`vftable';
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 5) = 0;
    *((_DWORD *)v7 + 12) = 0;
    *((_DWORD *)v7 + 14) = 0;
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
  {
    v8 = GetMemLogObject();
    CMemoryLog::Write(v8, -2147024882);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids);
    }
    return 2147942414LL;
  }
  CUnkInternal::InternalAddRef(a3);
  *((_QWORD *)v7 + 4) = a3;
  *((_QWORD *)v7 + 3) = &CLSID_A51Repository;
  v9 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x1Eu);
  *((_QWORD *)v7 + 5) = v9;
  if ( !v9 )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, -2147024882);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids);
    }
    CClassInfo::`scalar deleting destructor'((CClassInfo *)v7, 1u);
    return 2147942414LL;
  }
  StringCchCopyW(v9, 0xFu, L"A51 Repository");
  *((_QWORD *)v7 + 6) = 1;
  v11 = off_180058078;
  if ( off_180058078->Flink != &g_ClassInfoHead )
    __fastfail(3u);
  *((_QWORD *)v7 + 1) = &g_ClassInfoHead;
  *((_QWORD *)v7 + 2) = v11;
  v11->Flink = (struct _LIST_ENTRY *)(v7 + 8);
  off_180058078 = (struct _LIST_ENTRY *)(v7 + 8);
  return 0;
}

```

## disassembly

```asm
0x1800427e8  mov     [rsp+arg_0], rbx
0x1800427ed  mov     [rsp+arg_18], r9
0x1800427f2  push    rdi
0x1800427f3  sub     rsp, 20h
0x1800427f7  mov     rdi, r8
0x1800427fa  test    r8, r8
0x1800427fd  jnz     short loc_180042850
0x1800427ff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042805  mov     edi, 8007000Eh
0x18004280a  mov     edx, edi
0x18004280c  mov     rcx, rax
0x18004280f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042815  lea     rax, WPP_GLOBAL_Control
0x18004281c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042823  cmp     rcx, rax
0x180042826  jz      short loc_180042849
0x180042828  test    byte ptr [rcx+1Ch], 1
0x18004282c  jz      short loc_180042849
0x18004282e  cmp     byte ptr [rcx+19h], 2
0x180042832  jb      short loc_180042849
0x180042834  mov     edx, 1Bh
0x180042839  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180042840  mov     rcx, [rcx+10h]
0x180042844  call    WPP_SF_
0x180042849  mov     eax, edi
0x18004284b  jmp     loc_1800429D3
0x180042850  mov     ecx, 40h ; '@'
0x180042855  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004285b  mov     rbx, rax
0x18004285e  mov     [rsp+28h+arg_18], rax
0x180042863  test    rax, rax
0x180042866  jz      short loc_18004289A
0x180042868  lea     rax, ??_7CClassInfo@@6B@; const CClassInfo::`vftable'
0x18004286f  mov     [rbx], rax
0x180042872  mov     qword ptr [rbx+18h], 0
0x18004287a  mov     qword ptr [rbx+20h], 0
0x180042882  mov     qword ptr [rbx+28h], 0
0x18004288a  mov     dword ptr [rbx+30h], 0
0x180042891  mov     dword ptr [rbx+38h], 0
0x180042898  jmp     short loc_18004289C
0x18004289a  xor     ebx, ebx
0x18004289c  mov     [rsp+28h+arg_18], rbx
0x1800428a1  test    rbx, rbx
0x1800428a4  jnz     short loc_1800428F4
0x1800428a6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800428ac  mov     edi, 8007000Eh
0x1800428b1  mov     edx, edi
0x1800428b3  mov     rcx, rax
0x1800428b6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800428bc  lea     rax, WPP_GLOBAL_Control
0x1800428c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800428ca  cmp     rcx, rax
0x1800428cd  jz      short loc_1800428EF
0x1800428cf  test    byte ptr [rcx+1Ch], 1
0x1800428d3  jz      short loc_1800428EF
0x1800428d5  cmp     byte ptr [rcx+19h], 2
0x1800428d9  jb      short loc_1800428EF
0x1800428db  lea     edx, [rbx+1Ch]
0x1800428de  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x1800428e5  mov     rcx, [rcx+10h]
0x1800428e9  call    WPP_SF_
0x1800428ee  nop
0x1800428ef  jmp     loc_180042849
0x1800428f4  mov     rcx, rdi
0x1800428f7  call    cs:__imp_?InternalAddRef@CUnkInternal@@QEAAKXZ; CUnkInternal::InternalAddRef(void)
0x1800428fd  mov     [rbx+20h], rdi
0x180042901  lea     rax, CLSID_A51Repository
0x180042908  mov     [rbx+18h], rax
0x18004290c  mov     ecx, 1Eh
0x180042911  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180042917  mov     [rbx+28h], rax
0x18004291b  test    rax, rax
0x18004291e  jnz     short loc_18004297D
0x180042920  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180042926  mov     edi, 8007000Eh
0x18004292b  mov     edx, edi
0x18004292d  mov     rcx, rax
0x180042930  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180042936  lea     rax, WPP_GLOBAL_Control
0x18004293d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042944  cmp     rcx, rax
0x180042947  jz      short loc_18004296B
0x180042949  test    byte ptr [rcx+1Ch], 1
0x18004294d  jz      short loc_18004296B
0x18004294f  cmp     byte ptr [rcx+19h], 2
0x180042953  jb      short loc_18004296B
0x180042955  mov     edx, 1Dh
0x18004295a  lea     r8, WPP_caca780cf7163dbe62a4352f30d6adcd_Traceguids
0x180042961  mov     rcx, [rcx+10h]
0x180042965  call    WPP_SF_
0x18004296a  nop
0x18004296b  mov     edx, 1; unsigned int
0x180042970  mov     rcx, rbx; this
0x180042973  call    ??_GCClassInfo@@UEAAPEAXI@Z; CClassInfo::`scalar deleting destructor'(uint)
0x180042978  jmp     loc_180042849
0x18004297d  lea     r8, aA51Repository; "A51 Repository"
0x180042984  mov     edx, 0Fh; unsigned __int64
0x180042989  mov     rcx, rax; unsigned __int16 *
0x18004298c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180042991  mov     qword ptr [rbx+30h], 1
0x180042999  mov     rcx, cs:off_180058078
0x1800429a0  lea     rdx, ?g_ClassInfoHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ClassInfoHead
0x1800429a7  cmp     [rcx], rdx
0x1800429aa  jz      short loc_1800429B3
0x1800429ac  mov     ecx, 3
0x1800429b1  int     29h; Win8: RtlFailFast(ecx)
0x1800429b3  lea     rax, [rbx+8]
0x1800429b7  mov     [rax], rdx
0x1800429ba  mov     [rax+8], rcx
0x1800429be  mov     [rcx], rax
0x1800429c1  mov     cs:off_180058078, rax
0x1800429c8  mov     [rsp+28h+arg_18], 0
0x1800429d1  xor     eax, eax
0x1800429d3  mov     rbx, [rsp+28h+arg_0]
0x1800429d8  add     rsp, 20h
0x1800429dc  pop     rdi
0x1800429dd  retn
```
