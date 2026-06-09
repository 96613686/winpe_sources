# CNamespaceHandle::UpdateClassCompatible(_IWmiObject *,ushort const *,_IWmiObject *,_IWmiObject *,__int64)

- ea: `0x180027000`
- end: `0x180027148`
- name: `?UpdateClassCompatible@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG00_J@Z`
- size: `328`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct _IWmiObject *, const unsigned __int16 *, struct _IWmiObject *, struct _IWmiObject *, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800262cc`
- `0x180035f1c`
- `0x180036248`

## callees

- `0x1800012b8`
- `0x180006960`
- `0x180027000`
- `0x180027150`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002701c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002701c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002708c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800270fb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027134`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002708c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800270fb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027134`
- `wbemcomn!GetMemLogObject` at `0x180027039`
- `wbemcomn!GetMemLogObject` at `0x1800270a7`
- `wbemcomn!GetMemLogObject` at `0x180027039`
- `wbemcomn!GetMemLogObject` at `0x1800270a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027049`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800270b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027049`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800270b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CNamespaceHandle::UpdateClassCompatible(
        CNamespaceHandle *this,
        struct _IWmiObject *a2,
        const unsigned __int16 *a3,
        struct _IWmiObject *a4,
        struct _IWmiObject *a5,
        __int64 a6)
{
  unsigned __int16 *v10; // rbx
  CMemoryLog *v11; // rax
  unsigned int updated; // edi
  CMemoryLog *MemLogObject; // rax

  v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  if ( v10 )
  {
    *v10 = 0;
    if ( A51Hash(a3, v10) )
    {
      updated = CNamespaceHandle::UpdateClassCompatibleHash(this, a2, v10, a4, a5, a6);
      CWin32DefaultArena::WbemMemFree(v10);
    }
    else
    {
      MemLogObject = GetMemLogObject();
      updated = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          255,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      CWin32DefaultArena::WbemMemFree(v10);
    }
  }
  else
  {
    v11 = GetMemLogObject();
    updated = -2147217402;
    CMemoryLog::Write(v11, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
  }
  return updated;
}

```

## disassembly

```asm
0x180027000  push    rbx
0x180027002  push    rbp
0x180027003  push    rsi
0x180027004  push    rdi
0x180027005  push    r14
0x180027007  sub     rsp, 40h
0x18002700b  mov     rsi, r9
0x18002700e  mov     rdi, r8
0x180027011  mov     rbp, rdx
0x180027014  mov     r14, rcx
0x180027017  mov     ecx, 2E6h
0x18002701c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180027022  mov     rbx, rax
0x180027025  mov     [rsp+68h+var_38], rax
0x18002702a  test    rax, rax
0x18002702d  jz      short loc_180027034
0x18002702f  xor     eax, eax
0x180027031  mov     [rbx], ax
0x180027034  test    rbx, rbx
0x180027037  jnz     short loc_180027098
0x180027039  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002703f  mov     edi, 80041006h
0x180027044  mov     edx, edi
0x180027046  mov     rcx, rax
0x180027049  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002704f  lea     rax, WPP_GLOBAL_Control
0x180027056  mov     rcx, cs:WPP_GLOBAL_Control
0x18002705d  cmp     rcx, rax
0x180027060  jz      short loc_18002708A
0x180027062  test    byte ptr [rcx+1Ch], 1
0x180027066  jz      short loc_18002708A
0x180027068  cmp     byte ptr [rcx+19h], 2
0x18002706c  jb      short loc_18002708A
0x18002706e  mov     edx, 0FEh
0x180027073  mov     r9d, 80041006h
0x180027079  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180027080  mov     rcx, [rcx+10h]
0x180027084  call    WPP_SF_d
0x180027089  nop
0x18002708a  xor     ecx, ecx
0x18002708c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180027092  nop
0x180027093  jmp     loc_18002713B
0x180027098  mov     rdx, rbx; unsigned __int16 *
0x18002709b  mov     rcx, rdi; unsigned __int16 *
0x18002709e  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x1800270a3  test    al, al
0x1800270a5  jnz     short loc_180027104
0x1800270a7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800270ad  mov     edi, 80041006h
0x1800270b2  mov     edx, edi
0x1800270b4  mov     rcx, rax
0x1800270b7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800270bd  lea     rax, WPP_GLOBAL_Control
0x1800270c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270cb  cmp     rcx, rax
0x1800270ce  jz      short loc_1800270F8
0x1800270d0  test    byte ptr [rcx+1Ch], 1
0x1800270d4  jz      short loc_1800270F8
0x1800270d6  cmp     byte ptr [rcx+19h], 2
0x1800270da  jb      short loc_1800270F8
0x1800270dc  mov     edx, 0FFh
0x1800270e1  mov     r9d, 80041006h
0x1800270e7  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800270ee  mov     rcx, [rcx+10h]
0x1800270f2  call    WPP_SF_d
0x1800270f7  nop
0x1800270f8  mov     rcx, rbx
0x1800270fb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180027101  nop
0x180027102  jmp     short loc_18002713B
0x180027104  mov     rax, [rsp+68h+arg_28]
0x18002710c  mov     [rsp+68h+var_40], rax; __int64
0x180027111  mov     rax, [rsp+68h+arg_20]
0x180027119  mov     [rsp+68h+var_48], rax; struct _IWmiObject *
0x18002711e  mov     r9, rsi; struct _IWmiObject *
0x180027121  mov     r8, rbx; unsigned __int16 *
0x180027124  mov     rdx, rbp; struct _IWmiObject *
0x180027127  mov     rcx, r14; this
0x18002712a  call    ?UpdateClassCompatibleHash@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG00_J@Z; CNamespaceHandle::UpdateClassCompatibleHash(_IWmiObject *,ushort const *,_IWmiObject *,_IWmiObject *,__int64)
0x18002712f  mov     edi, eax
0x180027131  mov     rcx, rbx
0x180027134  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002713a  nop
0x18002713b  mov     eax, edi
0x18002713d  add     rsp, 40h
0x180027141  pop     r14
0x180027143  pop     rdi
0x180027144  pop     rsi
0x180027145  pop     rbp
0x180027146  pop     rbx
0x180027147  retn
```
