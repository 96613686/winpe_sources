# CNamespaceHandle::WriteParentChildRelationship(ushort const *,ushort const *)

- ea: `0x180036e68`
- end: `0x180036f4e`
- name: `?WriteParentChildRelationship@CNamespaceHandle@@IEAAJPEBG0@Z`
- size: `230`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180036780`

## callees

- `0x1800012b8`
- `0x18001e134`
- `0x180023bf0`
- `0x180032798`
- `0x180036dd8`
- `0x180036e68`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036ee6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036f27`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036f35`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036ee6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036f27`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036f35`
- `wbemcomn!GetMemLogObject` at `0x180036e93`
- `wbemcomn!GetMemLogObject` at `0x180036e93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036ea3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036ea3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::WriteParentChildRelationship(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v7; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned __int16 *v12; // [rsp+48h] [rbp+20h] BYREF

  CFileName::CFileName((CFileName *)&v12);
  if ( !v12 )
  {
    MemLogObject = GetMemLogObject();
    v7 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 301, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return v7;
  }
  CNamespaceHandle::ConstructParentChildFileName(this, a2, a3, (struct CFileName *)&v12);
  v9 = CFileCache::WriteLink((CFileCache *)byte_180058AF8, v12);
  if ( v9 )
  {
    v7 = A51TranslateErrorCode(v9, v10, v11);
    CWin32DefaultArena::WbemMemFree(v12);
    return v7;
  }
  CWin32DefaultArena::WbemMemFree(v12);
  return 0;
}

```

## disassembly

```asm
0x180036e68  mov     [rsp+arg_0], rbx
0x180036e6d  mov     [rsp+arg_8], rbp
0x180036e72  push    rsi
0x180036e73  sub     rsp, 20h
0x180036e77  mov     rbx, r8
0x180036e7a  mov     rsi, rdx
0x180036e7d  mov     rbp, rcx
0x180036e80  lea     rcx, [rsp+28h+arg_18]; this
0x180036e85  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x180036e8a  nop
0x180036e8b  cmp     [rsp+28h+arg_18], 0
0x180036e91  jnz     short loc_180036EF1
0x180036e93  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036e99  mov     ebx, 80041006h
0x180036e9e  mov     edx, ebx
0x180036ea0  mov     rcx, rax
0x180036ea3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036ea9  lea     rax, WPP_GLOBAL_Control
0x180036eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180036eb7  cmp     rcx, rax
0x180036eba  jz      short loc_180036EE4
0x180036ebc  test    byte ptr [rcx+1Ch], 1
0x180036ec0  jz      short loc_180036EE4
0x180036ec2  cmp     byte ptr [rcx+19h], 2
0x180036ec6  jb      short loc_180036EE4
0x180036ec8  mov     edx, 12Dh
0x180036ecd  mov     r9d, 80041006h
0x180036ed3  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180036eda  mov     rcx, [rcx+10h]
0x180036ede  call    WPP_SF_d
0x180036ee3  nop
0x180036ee4  xor     ecx, ecx
0x180036ee6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036eec  nop
0x180036eed  mov     eax, ebx
0x180036eef  jmp     short loc_180036F3E
0x180036ef1  lea     r9, [rsp+28h+arg_18]; struct CFileName *
0x180036ef6  mov     r8, rbx; unsigned __int16 *
0x180036ef9  mov     rdx, rsi; unsigned __int16 *
0x180036efc  mov     rcx, rbp; this
0x180036eff  call    ?ConstructParentChildFileName@CNamespaceHandle@@IEAAJPEBG0AEAVCFileName@@@Z; CNamespaceHandle::ConstructParentChildFileName(ushort const *,ushort const *,CFileName &)
0x180036f04  mov     rdx, [rsp+28h+arg_18]; unsigned __int16 *
0x180036f09  lea     rcx, byte_180058AF8; this
0x180036f10  call    ?WriteLink@CFileCache@@QEAAJPEBG@Z; CFileCache::WriteLink(ushort const *)
0x180036f15  test    eax, eax
0x180036f17  jz      short loc_180036F30
0x180036f19  mov     ecx, eax; int
0x180036f1b  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x180036f20  mov     ebx, eax
0x180036f22  mov     rcx, [rsp+28h+arg_18]
0x180036f27  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036f2d  nop
0x180036f2e  jmp     short loc_180036EED
0x180036f30  mov     rcx, [rsp+28h+arg_18]
0x180036f35  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036f3b  nop
0x180036f3c  xor     eax, eax
0x180036f3e  mov     rbx, [rsp+28h+arg_0]
0x180036f43  mov     rbp, [rsp+28h+arg_8]
0x180036f48  add     rsp, 20h
0x180036f4c  pop     rsi
0x180036f4d  retn
```
