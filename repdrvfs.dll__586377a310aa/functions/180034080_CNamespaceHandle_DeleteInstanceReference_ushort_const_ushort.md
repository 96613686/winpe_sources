# CNamespaceHandle::DeleteInstanceReference(ushort const *,ushort *)

- ea: `0x180034080`
- end: `0x180034233`
- name: `?DeleteInstanceReference@CNamespaceHandle@@IEAAJPEBGPEAG@Z`
- size: `435`
- prototype: `__int64 __fastcall(CRepository **this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800149cc`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180014024`
- `0x18001e134`
- `0x180023bf0`
- `0x1800329f4`
- `0x180034080`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180034126`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003418e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800341e1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180034211`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180034220`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180034126`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003418e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800341e1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180034211`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180034220`
- `wbemcomn!GetMemLogObject` at `0x1800340da`
- `wbemcomn!GetMemLogObject` at `0x18003419a`
- `wbemcomn!GetMemLogObject` at `0x1800340da`
- `wbemcomn!GetMemLogObject` at `0x18003419a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800340ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800341a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800340ea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800341a5`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::DeleteInstanceReference(
        CRepository **this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v7; // ebx
  int v9; // eax
  CMemoryLog *v10; // rax
  unsigned __int16 *v11; // rdi
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned __int16 *v15; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 366, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  CFileName::CFileName((CFileName *)&v15);
  if ( !v15 )
  {
    MemLogObject = GetMemLogObject();
    v7 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 367, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return v7;
  }
  v9 = CNamespaceHandle::ConstructReferenceFileName(this, a3, a2, (struct CFileName *)&v15);
  v7 = v9;
  if ( v9 >= 0 )
  {
    v11 = v15;
    v12 = CFileCache::DeleteObject((CFileCache *)byte_180058AF8, v15);
    if ( v12 )
    {
      v7 = A51TranslateErrorCode(v12, v13, v14);
      CWin32DefaultArena::WbemMemFree(v11);
      return v7;
    }
    CWin32DefaultArena::WbemMemFree(v11);
  }
  else
  {
    if ( v9 != -2147217406 )
    {
      v10 = GetMemLogObject();
      CMemoryLog::Write(v10, v7);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 369, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v7);
      }
      CWin32DefaultArena::WbemMemFree(v15);
      return v7;
    }
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 368, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 0);
    }
    CWin32DefaultArena::WbemMemFree(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180034080  push    rbx
0x180034082  push    rsi
0x180034083  push    rdi
0x180034084  push    r15
0x180034086  sub     rsp, 28h
0x18003408a  mov     rbx, r8
0x18003408d  mov     rdi, rdx
0x180034090  mov     rsi, rcx
0x180034093  lea     r15, WPP_GLOBAL_Control
0x18003409a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340a1  cmp     rcx, r15
0x1800340a4  jz      short loc_1800340C7
0x1800340a6  test    byte ptr [rcx+1Ch], 1
0x1800340aa  jz      short loc_1800340C7
0x1800340ac  cmp     byte ptr [rcx+19h], 5
0x1800340b0  jb      short loc_1800340C7
0x1800340b2  mov     edx, 16Eh
0x1800340b7  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800340be  mov     rcx, [rcx+10h]
0x1800340c2  call    WPP_SF_
0x1800340c7  lea     rcx, [rsp+48h+arg_18]; this
0x1800340cc  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x1800340d1  nop
0x1800340d2  cmp     [rsp+48h+arg_18], 0
0x1800340d8  jnz     short loc_180034134
0x1800340da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800340e0  mov     ebx, 80041006h
0x1800340e5  mov     edx, ebx
0x1800340e7  mov     rcx, rax
0x1800340ea  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800340f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340f7  cmp     rcx, r15
0x1800340fa  jz      short loc_180034124
0x1800340fc  test    byte ptr [rcx+1Ch], 1
0x180034100  jz      short loc_180034124
0x180034102  cmp     byte ptr [rcx+19h], 2
0x180034106  jb      short loc_180034124
0x180034108  mov     edx, 16Fh
0x18003410d  mov     r9d, 80041006h
0x180034113  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003411a  mov     rcx, [rcx+10h]
0x18003411e  call    WPP_SF_d
0x180034123  nop
0x180034124  xor     ecx, ecx
0x180034126  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003412c  nop
0x18003412d  mov     eax, ebx
0x18003412f  jmp     loc_180034229
0x180034134  lea     r9, [rsp+48h+arg_18]; struct CFileName *
0x180034139  mov     r8, rdi; unsigned __int16 *
0x18003413c  mov     rdx, rbx; unsigned __int16 *
0x18003413f  mov     rcx, rsi; this
0x180034142  call    ?ConstructReferenceFileName@CNamespaceHandle@@IEAAJPEBG0AEAVCFileName@@@Z; CNamespaceHandle::ConstructReferenceFileName(ushort const *,ushort const *,CFileName &)
0x180034147  mov     ebx, eax
0x180034149  test    eax, eax
0x18003414b  jns     loc_1800341ED
0x180034151  cmp     eax, 80041002h
0x180034156  jnz     short loc_18003419A
0x180034158  mov     rcx, cs:WPP_GLOBAL_Control
0x18003415f  cmp     rcx, r15
0x180034162  jz      short loc_180034189
0x180034164  test    byte ptr [rcx+1Ch], 1
0x180034168  jz      short loc_180034189
0x18003416a  cmp     byte ptr [rcx+19h], 2
0x18003416e  jb      short loc_180034189
0x180034170  mov     edx, 170h
0x180034175  xor     r9d, r9d
0x180034178  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003417f  mov     rcx, [rcx+10h]
0x180034183  call    WPP_SF_d
0x180034188  nop
0x180034189  mov     rcx, [rsp+48h+arg_18]
0x18003418e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180034194  nop
0x180034195  jmp     loc_180034227
0x18003419a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800341a0  mov     edx, ebx
0x1800341a2  mov     rcx, rax
0x1800341a5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800341ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800341b2  cmp     rcx, r15
0x1800341b5  jz      short loc_1800341DC
0x1800341b7  test    byte ptr [rcx+1Ch], 1
0x1800341bb  jz      short loc_1800341DC
0x1800341bd  cmp     byte ptr [rcx+19h], 2
0x1800341c1  jb      short loc_1800341DC
0x1800341c3  mov     edx, 171h
0x1800341c8  mov     r9d, ebx
0x1800341cb  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800341d2  mov     rcx, [rcx+10h]
0x1800341d6  call    WPP_SF_d
0x1800341db  nop
0x1800341dc  mov     rcx, [rsp+48h+arg_18]
0x1800341e1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800341e7  nop
0x1800341e8  jmp     loc_18003412D
0x1800341ed  mov     rdi, [rsp+48h+arg_18]
0x1800341f2  mov     rdx, rdi; unsigned __int16 *
0x1800341f5  lea     rcx, byte_180058AF8; this
0x1800341fc  call    ?DeleteObject@CFileCache@@QEAAJPEBG@Z; CFileCache::DeleteObject(ushort const *)
0x180034201  test    eax, eax
0x180034203  jz      short loc_18003421D
0x180034205  mov     ecx, eax; int
0x180034207  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x18003420c  mov     ebx, eax
0x18003420e  mov     rcx, rdi
0x180034211  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180034217  nop
0x180034218  jmp     loc_18003412D
0x18003421d  mov     rcx, rdi
0x180034220  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180034226  nop
0x180034227  xor     eax, eax
0x180034229  add     rsp, 28h
0x18003422d  pop     r15
0x18003422f  pop     rdi
0x180034230  pop     rsi
0x180034231  pop     rbx
0x180034232  retn
```
