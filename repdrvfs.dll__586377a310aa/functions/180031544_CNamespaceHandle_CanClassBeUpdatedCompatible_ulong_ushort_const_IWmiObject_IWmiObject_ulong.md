# CNamespaceHandle::CanClassBeUpdatedCompatible(ulong,ushort const *,_IWmiObject *,_IWmiObject *,ulong)

- ea: `0x180031544`
- end: `0x1800316bf`
- name: `?CanClassBeUpdatedCompatible@CNamespaceHandle@@IEAAJKPEBGPEAU_IWmiObject@@1K@Z`
- size: `379`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, __int64, const unsigned __int16 *, struct _IWmiObject *, struct _IWmiObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800262cc`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180031544`
- `0x1800316e0`
- `0x180031ae8`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800315a4`
- `wbemcomn!GetMemLogObject` at `0x180031608`
- `wbemcomn!GetMemLogObject` at `0x180031672`
- `wbemcomn!GetMemLogObject` at `0x1800315a4`
- `wbemcomn!GetMemLogObject` at `0x180031608`
- `wbemcomn!GetMemLogObject` at `0x180031672`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800315af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031613`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003167d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800315af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180031613`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003167d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::CanClassBeUpdatedCompatible(
        CNamespaceHandle *this,
        __int64 a2,
        const unsigned __int16 *a3,
        struct _IWmiObject *a4,
        struct _IWmiObject *a5)
{
  unsigned int HasChildren; // ebx
  unsigned int v9; // r8d
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v11; // rcx
  __int64 v12; // rdx
  unsigned int v14; // edi
  CMemoryLog *v15; // rax
  int v16; // eax
  CMemoryLog *v17; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  HasChildren = CNamespaceHandle::ClassHasChildren(this, a3, 2u);
  if ( (HasChildren & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, HasChildren);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return HasChildren;
    }
    v12 = 282;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, HasChildren);
    return HasChildren;
  }
  if ( HasChildren )
  {
    HasChildren = CNamespaceHandle::ClassHasInstances(this, a3, v9);
    if ( (HasChildren & 0x80000000) != 0 )
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, HasChildren);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return HasChildren;
      }
      v12 = 283;
      goto LABEL_10;
    }
    if ( HasChildren )
      return 0;
    v14 = -2147217370;
  }
  else
  {
    v14 = -2147217371;
  }
  v16 = (*(__int64 (__fastcall **)(struct _IWmiObject *, __int64, struct _IWmiObject *))(*(_QWORD *)a4 + 672LL))(
          a4,
          1,
          a5);
  HasChildren = v16;
  if ( !v16 )
    return 0;
  if ( v16 != -2147217407 )
  {
    if ( v16 < 0 )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, HasChildren);
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return HasChildren;
    }
    v12 = 284;
    goto LABEL_10;
  }
  return v14;
}

```

## disassembly

```asm
0x180031544  push    rbx
0x180031546  push    rsi
0x180031547  push    rdi
0x180031548  push    r13
0x18003154a  push    r14
0x18003154c  sub     rsp, 20h
0x180031550  mov     r14, r9
0x180031553  mov     rdi, r8
0x180031556  mov     rsi, rcx
0x180031559  mov     rcx, cs:WPP_GLOBAL_Control
0x180031560  lea     r13, WPP_GLOBAL_Control
0x180031567  cmp     rcx, r13
0x18003156a  jz      short loc_18003158D
0x18003156c  test    byte ptr [rcx+1Ch], 1
0x180031570  jz      short loc_18003158D
0x180031572  cmp     byte ptr [rcx+19h], 5
0x180031576  jb      short loc_18003158D
0x180031578  mov     rcx, [rcx+10h]
0x18003157c  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180031583  mov     edx, 119h
0x180031588  call    WPP_SF_
0x18003158d  mov     r8d, 2; unsigned int
0x180031593  mov     rdx, rdi; unsigned __int16 *
0x180031596  mov     rcx, rsi; this
0x180031599  call    ?ClassHasChildren@CNamespaceHandle@@IEAAJPEBGK@Z; CNamespaceHandle::ClassHasChildren(ushort const *,ulong)
0x18003159e  mov     ebx, eax
0x1800315a0  test    eax, eax
0x1800315a2  jns     short loc_1800315EC
0x1800315a4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800315aa  mov     rcx, rax
0x1800315ad  mov     edx, ebx
0x1800315af  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800315b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800315bc  cmp     rcx, r13
0x1800315bf  jz      short loc_1800315E5
0x1800315c1  test    byte ptr [rcx+1Ch], 1
0x1800315c5  jz      short loc_1800315E5
0x1800315c7  cmp     byte ptr [rcx+19h], 2
0x1800315cb  jb      short loc_1800315E5
0x1800315cd  mov     edx, 11Ah
0x1800315d2  mov     rcx, [rcx+10h]
0x1800315d6  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800315dd  mov     r9d, ebx
0x1800315e0  call    WPP_SF_d
0x1800315e5  mov     eax, ebx
0x1800315e7  jmp     loc_1800316B3
0x1800315ec  test    ebx, ebx
0x1800315ee  jnz     short loc_1800315F7
0x1800315f0  mov     edi, 80041025h
0x1800315f5  jmp     short loc_180031641
0x1800315f7  mov     rdx, rdi; unsigned __int16 *
0x1800315fa  mov     rcx, rsi; this
0x1800315fd  call    ?ClassHasInstances@CNamespaceHandle@@IEAAJPEBGK@Z; CNamespaceHandle::ClassHasInstances(ushort const *,ulong)
0x180031602  mov     ebx, eax
0x180031604  test    eax, eax
0x180031606  jns     short loc_180031638
0x180031608  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003160e  mov     rcx, rax
0x180031611  mov     edx, ebx
0x180031613  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180031619  mov     rcx, cs:WPP_GLOBAL_Control
0x180031620  cmp     rcx, r13
0x180031623  jz      short loc_1800315E5
0x180031625  test    byte ptr [rcx+1Ch], 1
0x180031629  jz      short loc_1800315E5
0x18003162b  cmp     byte ptr [rcx+19h], 2
0x18003162f  jb      short loc_1800315E5
0x180031631  mov     edx, 11Bh
0x180031636  jmp     short loc_1800315D2
0x180031638  test    ebx, ebx
0x18003163a  jnz     short loc_1800316B1
0x18003163c  mov     edi, 80041026h
0x180031641  mov     rcx, [r14]
0x180031644  mov     edx, 1
0x180031649  mov     r8, [rsp+48h+arg_20]
0x18003164e  mov     rax, [rcx+2A0h]
0x180031655  mov     rcx, r14
0x180031658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003165d  mov     ebx, eax
0x18003165f  test    eax, eax
0x180031661  jz      short loc_1800316B1
0x180031663  cmp     eax, 80041001h
0x180031668  jnz     short loc_18003166E
0x18003166a  mov     eax, edi
0x18003166c  jmp     short loc_1800316B3
0x18003166e  test    ebx, ebx
0x180031670  jns     short loc_180031683
0x180031672  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180031678  mov     rcx, rax
0x18003167b  mov     edx, ebx
0x18003167d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180031683  mov     rcx, cs:WPP_GLOBAL_Control
0x18003168a  cmp     rcx, r13
0x18003168d  jz      loc_1800315E5
0x180031693  test    byte ptr [rcx+1Ch], 1
0x180031697  jz      loc_1800315E5
0x18003169d  cmp     byte ptr [rcx+19h], 2
0x1800316a1  jb      loc_1800315E5
0x1800316a7  mov     edx, 11Ch
0x1800316ac  jmp     loc_1800315D2
0x1800316b1  xor     eax, eax
0x1800316b3  add     rsp, 20h
0x1800316b7  pop     r14
0x1800316b9  pop     r13
0x1800316bb  pop     rdi
0x1800316bc  pop     rsi
0x1800316bd  pop     rbx
0x1800316be  retn
```
