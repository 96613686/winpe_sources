# CNamespaceHandle::DeleteInstanceSelf(ushort const *,_IWmiObject *,bool)

- ea: `0x18001404c`
- end: `0x1800141ea`
- name: `?DeleteInstanceSelf@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@_N@Z`
- size: `414`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, struct _IWmiObject *, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014bb4`
- `0x18001e370`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180013048`
- `0x180013bc4`
- `0x18001404c`
- `0x1800149cc`
- `0x18001e134`
- `0x180033b84`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800140e5`
- `wbemcomn!GetMemLogObject` at `0x180014152`
- `wbemcomn!GetMemLogObject` at `0x18001419c`
- `wbemcomn!GetMemLogObject` at `0x1800140e5`
- `wbemcomn!GetMemLogObject` at `0x180014152`
- `wbemcomn!GetMemLogObject` at `0x18001419c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800140f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001415d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800141a7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800140f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001415d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800141a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::DeleteInstanceSelf(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        struct _IWmiObject *a3,
        char a4)
{
  unsigned int v8; // eax
  unsigned int v10; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  CNamespaceHandle *v15; // rcx
  CMemoryLog *v16; // rax
  unsigned int v17; // eax
  CMemoryLog *v18; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  if ( !dword_180058AFC || g_bShuttingDown )
  {
    v8 = 1255;
    return A51TranslateErrorCode(v8, (__int64)a2, (__int64)a3);
  }
  v8 = CObjectHeap::DeleteObject((CObjectHeap *)&qword_180058EF8, a2);
  if ( v8 )
    return A51TranslateErrorCode(v8, (__int64)a2, (__int64)a3);
  v10 = CNamespaceHandle::DeleteInstanceLink(this, a3, a2);
  if ( (v10 & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v10);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v13 = 325;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v10);
    return v10;
  }
  v14 = CNamespaceHandle::DeleteInstanceReferences((CRepository **)this, a3, a2);
  v10 = v14;
  v15 = (CNamespaceHandle *)(v14 + 0x80000000);
  if ( (int)v15 >= 0 && v14 != -2147217406 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, v10);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v13 = 326;
    goto LABEL_15;
  }
  if ( a4 )
  {
    v17 = CNamespaceHandle::DeleteInstanceBackReferences(v15, a2);
    v10 = v17;
    if ( ((v17 + 0x80000000) & 0x80000000) == 0 && v17 != -2147217406 )
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, v10);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v10;
      }
      v13 = 327;
      goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001404c  push    rbx
0x18001404e  push    rbp
0x18001404f  push    rsi
0x180014050  push    rdi
0x180014051  push    r13
0x180014053  push    r14
0x180014055  sub     rsp, 28h
0x180014059  mov     r14b, r9b
0x18001405c  mov     rsi, r8
0x18001405f  mov     rdi, rdx
0x180014062  mov     rbp, rcx
0x180014065  mov     rcx, cs:WPP_GLOBAL_Control
0x18001406c  lea     r13, WPP_GLOBAL_Control
0x180014073  cmp     rcx, r13
0x180014076  jz      short loc_180014099
0x180014078  test    byte ptr [rcx+1Ch], 1
0x18001407c  jz      short loc_180014099
0x18001407e  cmp     byte ptr [rcx+19h], 5
0x180014082  jb      short loc_180014099
0x180014084  mov     rcx, [rcx+10h]
0x180014088  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001408f  mov     edx, 144h
0x180014094  call    WPP_SF_
0x180014099  cmp     cs:dword_180058AFC, 0
0x1800140a0  jnz     short loc_1800140A9
0x1800140a2  mov     eax, 4E7h
0x1800140a7  jmp     short loc_1800140C5
0x1800140a9  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x1800140b0  jnz     short loc_1800140A2
0x1800140b2  mov     rdx, rdi; unsigned __int16 *
0x1800140b5  lea     rcx, qword_180058EF8; this
0x1800140bc  call    ?DeleteObject@CObjectHeap@@QEAAJPEBG@Z; CObjectHeap::DeleteObject(ushort const *)
0x1800140c1  test    eax, eax
0x1800140c3  jz      short loc_1800140D1
0x1800140c5  mov     ecx, eax; int
0x1800140c7  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x1800140cc  jmp     loc_1800141DD
0x1800140d1  mov     r8, rdi; unsigned __int16 *
0x1800140d4  mov     rdx, rsi; struct _IWmiObject *
0x1800140d7  mov     rcx, rbp; this
0x1800140da  call    ?DeleteInstanceLink@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG@Z; CNamespaceHandle::DeleteInstanceLink(_IWmiObject *,ushort const *)
0x1800140df  mov     ebx, eax
0x1800140e1  test    eax, eax
0x1800140e3  jns     short loc_18001412D
0x1800140e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800140eb  mov     rcx, rax
0x1800140ee  mov     edx, ebx
0x1800140f0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800140f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140fd  cmp     rcx, r13
0x180014100  jz      short loc_180014126
0x180014102  test    byte ptr [rcx+1Ch], 1
0x180014106  jz      short loc_180014126
0x180014108  cmp     byte ptr [rcx+19h], 2
0x18001410c  jb      short loc_180014126
0x18001410e  mov     edx, 145h
0x180014113  mov     rcx, [rcx+10h]
0x180014117  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001411e  mov     r9d, ebx
0x180014121  call    WPP_SF_d
0x180014126  mov     eax, ebx
0x180014128  jmp     loc_1800141DD
0x18001412d  mov     r8, rdi; unsigned __int16 *
0x180014130  mov     rdx, rsi; struct _IWmiObject *
0x180014133  mov     rcx, rbp; this
0x180014136  call    ?DeleteInstanceReferences@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG@Z; CNamespaceHandle::DeleteInstanceReferences(_IWmiObject *,ushort const *)
0x18001413b  mov     esi, 80000000h
0x180014140  mov     ebx, eax
0x180014142  mov     ebp, 80041002h
0x180014147  lea     ecx, [rax+rsi]; this
0x18001414a  test    esi, ecx
0x18001414c  jnz     short loc_180014182
0x18001414e  cmp     eax, ebp
0x180014150  jz      short loc_180014182
0x180014152  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014158  mov     rcx, rax
0x18001415b  mov     edx, ebx
0x18001415d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014163  mov     rcx, cs:WPP_GLOBAL_Control
0x18001416a  cmp     rcx, r13
0x18001416d  jz      short loc_180014126
0x18001416f  test    byte ptr [rcx+1Ch], 1
0x180014173  jz      short loc_180014126
0x180014175  cmp     byte ptr [rcx+19h], 2
0x180014179  jb      short loc_180014126
0x18001417b  mov     edx, 146h
0x180014180  jmp     short loc_180014113
0x180014182  test    r14b, r14b
0x180014185  jz      short loc_1800141DB
0x180014187  mov     rdx, rdi; unsigned __int16 *
0x18001418a  call    ?DeleteInstanceBackReferences@CNamespaceHandle@@IEAAJPEBG@Z; CNamespaceHandle::DeleteInstanceBackReferences(ushort const *)
0x18001418f  mov     ebx, eax
0x180014191  lea     ecx, [rax+rsi]
0x180014194  test    esi, ecx
0x180014196  jnz     short loc_1800141DB
0x180014198  cmp     eax, ebp
0x18001419a  jz      short loc_1800141DB
0x18001419c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800141a2  mov     rcx, rax
0x1800141a5  mov     edx, ebx
0x1800141a7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800141ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141b4  cmp     rcx, r13
0x1800141b7  jz      loc_180014126
0x1800141bd  test    byte ptr [rcx+1Ch], 1
0x1800141c1  jz      loc_180014126
0x1800141c7  cmp     byte ptr [rcx+19h], 2
0x1800141cb  jb      loc_180014126
0x1800141d1  mov     edx, 147h
0x1800141d6  jmp     loc_180014113
0x1800141db  xor     eax, eax
0x1800141dd  add     rsp, 28h
0x1800141e1  pop     r14
0x1800141e3  pop     r13
0x1800141e5  pop     rdi
0x1800141e6  pop     rsi
0x1800141e7  pop     rbp
0x1800141e8  pop     rbx
0x1800141e9  retn
```
