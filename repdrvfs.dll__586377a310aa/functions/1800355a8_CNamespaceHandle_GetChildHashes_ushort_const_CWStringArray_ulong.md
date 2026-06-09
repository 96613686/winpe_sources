# CNamespaceHandle::GetChildHashes(ushort const *,CWStringArray &,ulong)

- ea: `0x1800355a8`
- end: `0x1800356cd`
- name: `?GetChildHashes@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z`
- size: `293`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, const unsigned __int16 *, struct CWStringArray *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180033a0c`
- `0x180035f1c`

## callees

- `0x1800012b8`
- `0x180006960`
- `0x18001dba8`
- `0x180023bf0`
- `0x1800355a8`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035624`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035697`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800356ba`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035624`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035697`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800356ba`
- `wbemcomn!GetMemLogObject` at `0x1800355d1`
- `wbemcomn!GetMemLogObject` at `0x180035641`
- `wbemcomn!GetMemLogObject` at `0x1800355d1`
- `wbemcomn!GetMemLogObject` at `0x180035641`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800355e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035651`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800355e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035651`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::GetChildHashes(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        struct CWStringArray *a3,
        unsigned int a4)
{
  CMemoryLog *v8; // rax
  unsigned int ChildHashesByHash; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 *v12; // [rsp+20h] [rbp-38h] BYREF

  CFileName::CFileName((CFileName *)&v12);
  if ( v12 )
  {
    if ( A51Hash(a2, v12) )
    {
      ChildHashesByHash = CNamespaceHandle::GetChildHashesByHash(this, v12, a3, a4);
      CWin32DefaultArena::WbemMemFree(v12);
    }
    else
    {
      MemLogObject = GetMemLogObject();
      ChildHashesByHash = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          396,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      CWin32DefaultArena::WbemMemFree(v12);
    }
  }
  else
  {
    v8 = GetMemLogObject();
    ChildHashesByHash = -2147217402;
    CMemoryLog::Write(v8, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 395, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
  }
  return ChildHashesByHash;
}

```

## disassembly

```asm
0x1800355a8  push    rbx
0x1800355aa  push    rbp
0x1800355ab  push    rsi
0x1800355ac  push    r14
0x1800355ae  sub     rsp, 38h
0x1800355b2  mov     esi, r9d
0x1800355b5  mov     rbp, r8
0x1800355b8  mov     rbx, rdx
0x1800355bb  mov     r14, rcx
0x1800355be  lea     rcx, [rsp+58h+var_38]; this
0x1800355c3  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x1800355c8  nop
0x1800355c9  cmp     [rsp+58h+var_38], 0
0x1800355cf  jnz     short loc_180035630
0x1800355d1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800355d7  mov     ebx, 80041006h
0x1800355dc  mov     edx, ebx
0x1800355de  mov     rcx, rax
0x1800355e1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800355e7  lea     rax, WPP_GLOBAL_Control
0x1800355ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355f5  cmp     rcx, rax
0x1800355f8  jz      short loc_180035622
0x1800355fa  test    byte ptr [rcx+1Ch], 1
0x1800355fe  jz      short loc_180035622
0x180035600  cmp     byte ptr [rcx+19h], 2
0x180035604  jb      short loc_180035622
0x180035606  mov     edx, 18Bh
0x18003560b  mov     r9d, 80041006h
0x180035611  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035618  mov     rcx, [rcx+10h]
0x18003561c  call    WPP_SF_d
0x180035621  nop
0x180035622  xor     ecx, ecx
0x180035624  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003562a  nop
0x18003562b  jmp     loc_1800356C1
0x180035630  mov     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x180035635  mov     rcx, rbx; unsigned __int16 *
0x180035638  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x18003563d  test    al, al
0x18003563f  jnz     short loc_1800356A0
0x180035641  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035647  mov     ebx, 80041006h
0x18003564c  mov     edx, ebx
0x18003564e  mov     rcx, rax
0x180035651  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035657  lea     rax, WPP_GLOBAL_Control
0x18003565e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035665  cmp     rcx, rax
0x180035668  jz      short loc_180035692
0x18003566a  test    byte ptr [rcx+1Ch], 1
0x18003566e  jz      short loc_180035692
0x180035670  cmp     byte ptr [rcx+19h], 2
0x180035674  jb      short loc_180035692
0x180035676  mov     edx, 18Ch
0x18003567b  mov     r9d, 80041006h
0x180035681  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035688  mov     rcx, [rcx+10h]
0x18003568c  call    WPP_SF_d
0x180035691  nop
0x180035692  mov     rcx, [rsp+58h+var_38]
0x180035697  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003569d  nop
0x18003569e  jmp     short loc_1800356C1
0x1800356a0  mov     r9d, esi; unsigned int
0x1800356a3  mov     r8, rbp; struct CWStringArray *
0x1800356a6  mov     rdx, [rsp+58h+var_38]; unsigned __int16 *
0x1800356ab  mov     rcx, r14; this
0x1800356ae  call    ?GetChildHashesByHash@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z; CNamespaceHandle::GetChildHashesByHash(ushort const *,CWStringArray &,ulong)
0x1800356b3  mov     ebx, eax
0x1800356b5  mov     rcx, [rsp+58h+var_38]
0x1800356ba  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800356c0  nop
0x1800356c1  mov     eax, ebx
0x1800356c3  add     rsp, 38h
0x1800356c7  pop     r14
0x1800356c9  pop     rsi
0x1800356ca  pop     rbp
0x1800356cb  pop     rbx
0x1800356cc  retn
```
