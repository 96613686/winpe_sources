# CNamespaceHandle::DeleteInstanceByFile(ushort const *,_IWmiObject *,bool,CEventCollector &)

- ea: `0x180014bb4`
- end: `0x180014cbe`
- name: `?DeleteInstanceByFile@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@_NAEAVCEventCollector@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, const unsigned __int16 *, struct _IWmiObject *, bool, struct CEventCollector *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014290`
- `0x1800332dc`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001404c`
- `0x180014bb4`
- `0x180027814`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180014c16`
- `wbemcomn!GetMemLogObject` at `0x180014c81`
- `wbemcomn!GetMemLogObject` at `0x180014c16`
- `wbemcomn!GetMemLogObject` at `0x180014c81`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014c21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014c8c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014c21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014c8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CNamespaceHandle::DeleteInstanceByFile(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        struct _IWmiObject *a3,
        bool a4,
        struct CEventCollector *a5)
{
  unsigned int v9; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v11; // rcx
  __int64 v12; // rdx
  CMemoryLog *v14; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v9 = CNamespaceHandle::DeleteInstanceSelf(this, a2, a3, a4);
  if ( (v9 & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v9);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v12 = 322;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v9);
    return v9;
  }
  v9 = CNamespaceHandle::DeleteInstanceAsScope(this, a3, a5);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147217406 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, v9);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v12 = 323;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x180014bb4  push    rbx
0x180014bb6  push    rbp
0x180014bb7  push    rsi
0x180014bb8  push    rdi
0x180014bb9  push    r12
0x180014bbb  sub     rsp, 20h
0x180014bbf  mov     bl, r9b
0x180014bc2  mov     rdi, r8
0x180014bc5  mov     rbp, rdx
0x180014bc8  mov     rsi, rcx
0x180014bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bd2  lea     r12, WPP_GLOBAL_Control
0x180014bd9  cmp     rcx, r12
0x180014bdc  jz      short loc_180014BFF
0x180014bde  test    byte ptr [rcx+1Ch], 1
0x180014be2  jz      short loc_180014BFF
0x180014be4  cmp     byte ptr [rcx+19h], 5
0x180014be8  jb      short loc_180014BFF
0x180014bea  mov     rcx, [rcx+10h]
0x180014bee  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180014bf5  mov     edx, 141h
0x180014bfa  call    WPP_SF_
0x180014bff  mov     r9b, bl; bool
0x180014c02  mov     r8, rdi; struct _IWmiObject *
0x180014c05  mov     rdx, rbp; unsigned __int16 *
0x180014c08  mov     rcx, rsi; this
0x180014c0b  call    ?DeleteInstanceSelf@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@_N@Z; CNamespaceHandle::DeleteInstanceSelf(ushort const *,_IWmiObject *,bool)
0x180014c10  mov     ebx, eax
0x180014c12  test    eax, eax
0x180014c14  jns     short loc_180014C5B
0x180014c16  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014c1c  mov     rcx, rax
0x180014c1f  mov     edx, ebx
0x180014c21  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014c27  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c2e  cmp     rcx, r12
0x180014c31  jz      short loc_180014C57
0x180014c33  test    byte ptr [rcx+1Ch], 1
0x180014c37  jz      short loc_180014C57
0x180014c39  cmp     byte ptr [rcx+19h], 2
0x180014c3d  jb      short loc_180014C57
0x180014c3f  mov     edx, 142h
0x180014c44  mov     rcx, [rcx+10h]
0x180014c48  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180014c4f  mov     r9d, ebx
0x180014c52  call    WPP_SF_d
0x180014c57  mov     eax, ebx
0x180014c59  jmp     short loc_180014CB3
0x180014c5b  mov     r8, [rsp+48h+arg_20]; struct CEventCollector *
0x180014c60  mov     rdx, rdi; struct _IWmiObject *
0x180014c63  mov     rcx, rsi; this
0x180014c66  call    ?DeleteInstanceAsScope@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@AEAVCEventCollector@@@Z; CNamespaceHandle::DeleteInstanceAsScope(_IWmiObject *,CEventCollector &)
0x180014c6b  mov     ebx, eax
0x180014c6d  mov     eax, 80000000h
0x180014c72  lea     ecx, [rbx+rax]
0x180014c75  test    eax, ecx
0x180014c77  jnz     short loc_180014CB1
0x180014c79  cmp     ebx, 80041002h
0x180014c7f  jz      short loc_180014CB1
0x180014c81  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014c87  mov     rcx, rax
0x180014c8a  mov     edx, ebx
0x180014c8c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014c92  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c99  cmp     rcx, r12
0x180014c9c  jz      short loc_180014C57
0x180014c9e  test    byte ptr [rcx+1Ch], 1
0x180014ca2  jz      short loc_180014C57
0x180014ca4  cmp     byte ptr [rcx+19h], 2
0x180014ca8  jb      short loc_180014C57
0x180014caa  mov     edx, 143h
0x180014caf  jmp     short loc_180014C44
0x180014cb1  xor     eax, eax
0x180014cb3  add     rsp, 20h
0x180014cb7  pop     r12
0x180014cb9  pop     rdi
0x180014cba  pop     rsi
0x180014cbb  pop     rbp
0x180014cbc  pop     rbx
0x180014cbd  retn
```
