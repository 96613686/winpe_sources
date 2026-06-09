# CNamespaceHandle::EraseParentChildRelationship(ushort const *,ushort const *)

- ea: `0x18003543c`
- end: `0x1800355a0`
- name: `?EraseParentChildRelationship@CNamespaceHandle@@IEAAJPEBG0@Z`
- size: `356`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180035178`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001e134`
- `0x180023bf0`
- `0x180027780`
- `0x180032798`
- `0x18003543c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800354e2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035550`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003557c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003558d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800354e2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035550`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003557c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003558d`
- `wbemcomn!GetMemLogObject` at `0x180035496`
- `wbemcomn!GetMemLogObject` at `0x180035509`
- `wbemcomn!GetMemLogObject` at `0x180035496`
- `wbemcomn!GetMemLogObject` at `0x180035509`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800354a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035514`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800354a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035514`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::EraseParentChildRelationship(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v7; // ebx
  CMemoryLog *v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int16 *v13; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 416, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  CFileName::CFileName((CFileName *)&v13);
  if ( !v13 )
  {
    MemLogObject = GetMemLogObject();
    v7 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 417, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return v7;
  }
  v7 = CNamespaceHandle::ConstructParentChildFileName(this, a2, a3, (struct CFileName *)&v13);
  if ( (v7 & 0x80000000) != 0 )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, v7);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 418, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v7);
    }
    CWin32DefaultArena::WbemMemFree(v13);
    return v7;
  }
  v10 = CFileCache::DeleteLink((CFileCache *)byte_180058AF8, v13);
  if ( v10 )
  {
    v7 = A51TranslateErrorCode(v10, v11, v12);
    CWin32DefaultArena::WbemMemFree(v13);
    return v7;
  }
  CWin32DefaultArena::WbemMemFree(v13);
  return 0;
}

```

## disassembly

```asm
0x18003543c  push    rbx
0x18003543e  push    rbp
0x18003543f  push    rsi
0x180035440  push    r12
0x180035442  sub     rsp, 28h
0x180035446  mov     rbx, r8
0x180035449  mov     rsi, rdx
0x18003544c  mov     rbp, rcx
0x18003544f  lea     r12, WPP_GLOBAL_Control
0x180035456  mov     rcx, cs:WPP_GLOBAL_Control
0x18003545d  cmp     rcx, r12
0x180035460  jz      short loc_180035483
0x180035462  test    byte ptr [rcx+1Ch], 1
0x180035466  jz      short loc_180035483
0x180035468  cmp     byte ptr [rcx+19h], 5
0x18003546c  jb      short loc_180035483
0x18003546e  mov     edx, 1A0h
0x180035473  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003547a  mov     rcx, [rcx+10h]
0x18003547e  call    WPP_SF_
0x180035483  lea     rcx, [rsp+48h+arg_18]; this
0x180035488  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003548d  nop
0x18003548e  cmp     [rsp+48h+arg_18], 0
0x180035494  jnz     short loc_1800354F0
0x180035496  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003549c  mov     ebx, 80041006h
0x1800354a1  mov     edx, ebx
0x1800354a3  mov     rcx, rax
0x1800354a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800354ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800354b3  cmp     rcx, r12
0x1800354b6  jz      short loc_1800354E0
0x1800354b8  test    byte ptr [rcx+1Ch], 1
0x1800354bc  jz      short loc_1800354E0
0x1800354be  cmp     byte ptr [rcx+19h], 2
0x1800354c2  jb      short loc_1800354E0
0x1800354c4  mov     edx, 1A1h
0x1800354c9  mov     r9d, 80041006h
0x1800354cf  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800354d6  mov     rcx, [rcx+10h]
0x1800354da  call    WPP_SF_d
0x1800354df  nop
0x1800354e0  xor     ecx, ecx
0x1800354e2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800354e8  nop
0x1800354e9  mov     eax, ebx
0x1800354eb  jmp     loc_180035596
0x1800354f0  lea     r9, [rsp+48h+arg_18]; struct CFileName *
0x1800354f5  mov     r8, rbx; unsigned __int16 *
0x1800354f8  mov     rdx, rsi; unsigned __int16 *
0x1800354fb  mov     rcx, rbp; this
0x1800354fe  call    ?ConstructParentChildFileName@CNamespaceHandle@@IEAAJPEBG0AEAVCFileName@@@Z; CNamespaceHandle::ConstructParentChildFileName(ushort const *,ushort const *,CFileName &)
0x180035503  mov     ebx, eax
0x180035505  test    eax, eax
0x180035507  jns     short loc_180035559
0x180035509  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003550f  mov     edx, ebx
0x180035511  mov     rcx, rax
0x180035514  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003551a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035521  cmp     rcx, r12
0x180035524  jz      short loc_18003554B
0x180035526  test    byte ptr [rcx+1Ch], 1
0x18003552a  jz      short loc_18003554B
0x18003552c  cmp     byte ptr [rcx+19h], 2
0x180035530  jb      short loc_18003554B
0x180035532  mov     edx, 1A2h
0x180035537  mov     r9d, ebx
0x18003553a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035541  mov     rcx, [rcx+10h]
0x180035545  call    WPP_SF_d
0x18003554a  nop
0x18003554b  mov     rcx, [rsp+48h+arg_18]
0x180035550  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180035556  nop
0x180035557  jmp     short loc_1800354E9
0x180035559  mov     rdx, [rsp+48h+arg_18]; unsigned __int16 *
0x18003555e  lea     rcx, byte_180058AF8; this
0x180035565  call    ?DeleteLink@CFileCache@@QEAAJPEBG@Z; CFileCache::DeleteLink(ushort const *)
0x18003556a  test    eax, eax
0x18003556c  jz      short loc_180035588
0x18003556e  mov     ecx, eax; int
0x180035570  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x180035575  mov     ebx, eax
0x180035577  mov     rcx, [rsp+48h+arg_18]
0x18003557c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180035582  nop
0x180035583  jmp     loc_1800354E9
0x180035588  mov     rcx, [rsp+48h+arg_18]
0x18003558d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180035593  nop
0x180035594  xor     eax, eax
0x180035596  add     rsp, 28h
0x18003559a  pop     r12
0x18003559c  pop     rsi
0x18003559d  pop     rbp
0x18003559e  pop     rbx
0x18003559f  retn
```
