# CNamespaceHandle::UpdateClassAggressively(_IWmiObject *,ulong,ushort const *,_IWmiObject *,_IWmiObject *,CEventCollector &,ulong)

- ea: `0x180035f1c`
- end: `0x180036241`
- name: `?UpdateClassAggressively@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@KPEBG00AEAVCEventCollector@@K@Z`
- size: `805`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct _IWmiObject *, unsigned int, const unsigned __int16 *, struct _IWmiObject *, struct _IWmiObject *, struct CEventCollector *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180036248`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180020f2c`
- `0x180027000`
- `0x180031ae8`
- `0x1800332dc`
- `0x1800355a8`
- `0x180035908`
- `0x180035f1c`

## import_xrefs

- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18003611c`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18003611c`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18003610b`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18003610b`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x180036097`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x180036097`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180036225`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180036225`
- `wbemcomn!GetMemLogObject` at `0x180035f9f`
- `wbemcomn!GetMemLogObject` at `0x180035ff5`
- `wbemcomn!GetMemLogObject` at `0x18003604d`
- `wbemcomn!GetMemLogObject` at `0x1800360ba`
- `wbemcomn!GetMemLogObject` at `0x180036142`
- `wbemcomn!GetMemLogObject` at `0x1800361af`
- `wbemcomn!GetMemLogObject` at `0x180035f9f`
- `wbemcomn!GetMemLogObject` at `0x180035ff5`
- `wbemcomn!GetMemLogObject` at `0x18003604d`
- `wbemcomn!GetMemLogObject` at `0x1800360ba`
- `wbemcomn!GetMemLogObject` at `0x180036142`
- `wbemcomn!GetMemLogObject` at `0x1800361af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035faa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036005`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036058`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800360c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003614d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800361ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035faa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036005`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036058`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800360c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003614d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800361ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CNamespaceHandle::UpdateClassAggressively(
        CNamespaceHandle *this,
        struct _IWmiObject *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        struct _IWmiObject *a5,
        struct _IWmiObject *a6,
        struct CEventCollector *a7)
{
  int HasInstances; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  CVarObjHeap *v18; // rcx
  __int64 v19; // rdx
  unsigned int i; // esi
  const unsigned __int16 *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  unsigned int v25; // [rsp+28h] [rbp-B0h]
  _BYTE v26[168]; // [rsp+30h] [rbp-A8h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  if ( (a3 & 0x40) == 0 )
  {
    HasInstances = CNamespaceHandle::ClassHasInstances(this, a4, a3);
    if ( HasInstances < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, HasInstances);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 265;
LABEL_11:
        v14 = (unsigned int)HasInstances;
LABEL_12:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v14);
        return (unsigned int)HasInstances;
      }
      return (unsigned int)HasInstances;
    }
    if ( !HasInstances )
    {
      v15 = GetMemLogObject();
      HasInstances = -2147217370;
      CMemoryLog::Write(v15, -2147217370);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 266;
        v14 = 2147749926LL;
        goto LABEL_12;
      }
      return (unsigned int)HasInstances;
    }
LABEL_23:
    CWStringArray::CWStringArray((CWStringArray *)v26, 0, 100);
    HasInstances = CNamespaceHandle::GetChildHashes(this, a4, (struct CWStringArray *)v26, 2u);
    if ( HasInstances >= 0 )
    {
      for ( i = 0; i != CWStringArray::Size((CWStringArray *)v26); ++i )
      {
        v21 = (const unsigned __int16 *)CWStringArray::operator[](v26, i);
        HasInstances = CNamespaceHandle::UpdateChildClassAggressively(this, a3, v21, a5, a7, v25);
        if ( HasInstances < 0 )
        {
          v22 = GetMemLogObject();
          CMemoryLog::Write(v22, HasInstances);
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = 269;
            goto LABEL_41;
          }
          goto LABEL_45;
        }
      }
      HasInstances = CNamespaceHandle::UpdateClassCompatible(this, a2, a4, a5, a6, 0);
      if ( HasInstances >= 0 )
      {
        if ( (a3 & 0x1000) == 0 )
          CNamespaceHandle::FireEvent(this, a7, 0xCu, a4, a5, a6);
        HasInstances = 0;
      }
      else
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, HasInstances);
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = 270;
          goto LABEL_41;
        }
      }
    }
    else
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, HasInstances);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 268;
LABEL_41:
        WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)HasInstances);
      }
    }
LABEL_45:
    CWStringArray::~CWStringArray((CWStringArray *)v26);
    return (unsigned int)HasInstances;
  }
  HasInstances = CNamespaceHandle::DeleteClassInstances(this, a4, a6, a7);
  if ( HasInstances >= 0 )
    goto LABEL_23;
  v16 = GetMemLogObject();
  CMemoryLog::Write(v16, HasInstances);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 267;
    goto LABEL_11;
  }
  return (unsigned int)HasInstances;
}

```

## disassembly

```asm
0x180035f1c  mov     [rsp+arg_8], rdx
0x180035f21  push    rbx
0x180035f22  push    rbp
0x180035f23  push    rsi
0x180035f24  push    rdi
0x180035f25  push    r12
0x180035f27  push    r13
0x180035f29  push    r14
0x180035f2b  push    r15
0x180035f2d  sub     rsp, 98h
0x180035f34  mov     rbp, r9
0x180035f37  mov     r12d, r8d
0x180035f3a  mov     rdi, rcx
0x180035f3d  lea     r14, WPP_GLOBAL_Control
0x180035f44  lea     rsi, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f52  cmp     rcx, r14
0x180035f55  jz      short loc_180035F74
0x180035f57  test    byte ptr [rcx+1Ch], 1
0x180035f5b  jz      short loc_180035F74
0x180035f5d  cmp     byte ptr [rcx+19h], 5
0x180035f61  jb      short loc_180035F74
0x180035f63  mov     edx, 108h
0x180035f68  mov     r8, rsi
0x180035f6b  mov     rcx, [rcx+10h]
0x180035f6f  call    WPP_SF_
0x180035f74  mov     r13, [rsp+0D8h+arg_30]
0x180035f7c  mov     r15, [rsp+0D8h+arg_28]
0x180035f84  mov     rdx, rbp; unsigned __int16 *
0x180035f87  mov     rcx, rdi; this
0x180035f8a  test    r12b, 40h
0x180035f8e  jnz     loc_18003603C
0x180035f94  call    ?ClassHasInstances@CNamespaceHandle@@IEAAJPEBGK@Z; CNamespaceHandle::ClassHasInstances(ushort const *,ulong)
0x180035f99  mov     ebx, eax
0x180035f9b  test    eax, eax
0x180035f9d  jns     short loc_180035FED
0x180035f9f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035fa5  mov     edx, ebx
0x180035fa7  mov     rcx, rax
0x180035faa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180035fb7  cmp     rcx, r14
0x180035fba  jz      loc_18003622B
0x180035fc0  test    byte ptr [rcx+1Ch], 1
0x180035fc4  jz      loc_18003622B
0x180035fca  cmp     byte ptr [rcx+19h], 2
0x180035fce  jb      loc_18003622B
0x180035fd4  mov     edx, 109h
0x180035fd9  mov     r9d, ebx
0x180035fdc  mov     r8, rsi
0x180035fdf  mov     rcx, [rcx+10h]
0x180035fe3  call    WPP_SF_d
0x180035fe8  jmp     loc_18003622B
0x180035fed  test    ebx, ebx
0x180035fef  jnz     loc_18003608C
0x180035ff5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035ffb  mov     ebx, 80041026h
0x180036000  mov     edx, ebx
0x180036002  mov     rcx, rax
0x180036005  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003600b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036012  cmp     rcx, r14
0x180036015  jz      loc_18003622B
0x18003601b  test    byte ptr [rcx+1Ch], 1
0x18003601f  jz      loc_18003622B
0x180036025  cmp     byte ptr [rcx+19h], 2
0x180036029  jb      loc_18003622B
0x18003602f  mov     edx, 10Ah
0x180036034  mov     r9d, 80041026h
0x18003603a  jmp     short loc_180035FDC
0x18003603c  mov     r9, r13; struct CEventCollector *
0x18003603f  mov     r8, r15; struct _IWmiObject *
0x180036042  call    ?DeleteClassInstances@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@AEAVCEventCollector@@@Z; CNamespaceHandle::DeleteClassInstances(ushort const *,_IWmiObject *,CEventCollector &)
0x180036047  mov     ebx, eax
0x180036049  test    eax, eax
0x18003604b  jns     short loc_18003608C
0x18003604d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036053  mov     edx, ebx
0x180036055  mov     rcx, rax
0x180036058  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003605e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036065  cmp     rcx, r14
0x180036068  jz      loc_18003622B
0x18003606e  test    byte ptr [rcx+1Ch], 1
0x180036072  jz      loc_18003622B
0x180036078  cmp     byte ptr [rcx+19h], 2
0x18003607c  jb      loc_18003622B
0x180036082  mov     edx, 10Bh
0x180036087  jmp     loc_180035FD9
0x18003608c  xor     edx, edx
0x18003608e  lea     r8d, [rdx+64h]
0x180036092  lea     rcx, [rsp+0D8h+var_A8]
0x180036097  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x18003609d  nop
0x18003609e  mov     r9d, 2; unsigned int
0x1800360a4  lea     r8, [rsp+0D8h+var_A8]; struct CWStringArray *
0x1800360a9  mov     rdx, rbp; unsigned __int16 *
0x1800360ac  mov     rcx, rdi; this
0x1800360af  call    ?GetChildHashes@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z; CNamespaceHandle::GetChildHashes(ushort const *,CWStringArray &,ulong)
0x1800360b4  mov     ebx, eax
0x1800360b6  test    eax, eax
0x1800360b8  jns     short loc_1800360FC
0x1800360ba  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800360c0  mov     edx, ebx
0x1800360c2  mov     rcx, rax
0x1800360c5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800360cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360d2  cmp     rcx, r14
0x1800360d5  jz      loc_180036220
0x1800360db  test    byte ptr [rcx+1Ch], 1
0x1800360df  jz      loc_180036220
0x1800360e5  cmp     byte ptr [rcx+19h], 2
0x1800360e9  jb      loc_180036220
0x1800360ef  mov     edx, 10Ch
0x1800360f4  mov     r8, rsi
0x1800360f7  jmp     loc_1800361EB
0x1800360fc  xor     esi, esi
0x1800360fe  mov     r14, [rsp+0D8h+arg_20]
0x180036106  lea     rcx, [rsp+0D8h+var_A8]
0x18003610b  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x180036111  cmp     esi, eax
0x180036113  jz      short loc_180036185
0x180036115  mov     edx, esi
0x180036117  lea     rcx, [rsp+0D8h+var_A8]
0x18003611c  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180036122  mov     r8, rax; unsigned __int16 *
0x180036125  mov     [rsp+0D8h+var_B8], r13; struct CEventCollector *
0x18003612a  mov     r9, r14; struct _IWmiObject *
0x18003612d  mov     edx, r12d; unsigned int
0x180036130  mov     rcx, rdi; this
0x180036133  call    ?UpdateChildClassAggressively@CNamespaceHandle@@IEAAJKPEBGPEAU_IWmiObject@@AEAVCEventCollector@@K@Z; CNamespaceHandle::UpdateChildClassAggressively(ulong,ushort const *,_IWmiObject *,CEventCollector &,ulong)
0x180036138  mov     ebx, eax
0x18003613a  test    eax, eax
0x18003613c  js      short loc_180036142
0x18003613e  inc     esi
0x180036140  jmp     short loc_180036106
0x180036142  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036148  mov     edx, ebx
0x18003614a  mov     rcx, rax
0x18003614d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036153  mov     rcx, cs:WPP_GLOBAL_Control
0x18003615a  lea     rax, WPP_GLOBAL_Control
0x180036161  cmp     rcx, rax
0x180036164  jz      loc_180036220
0x18003616a  test    byte ptr [rcx+1Ch], 1
0x18003616e  jz      loc_180036220
0x180036174  cmp     byte ptr [rcx+19h], 2
0x180036178  jb      loc_180036220
0x18003617e  mov     edx, 10Dh
0x180036183  jmp     short loc_1800361E4
0x180036185  mov     [rsp+0D8h+var_B0], 0; __int64
0x18003618e  mov     [rsp+0D8h+var_B8], r15; struct _IWmiObject *
0x180036193  mov     r9, r14; struct _IWmiObject *
0x180036196  mov     r8, rbp; unsigned __int16 *
0x180036199  mov     rdx, [rsp+0D8h+arg_8]; struct _IWmiObject *
0x1800361a1  mov     rcx, rdi; this
0x1800361a4  call    ?UpdateClassCompatible@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG00_J@Z; CNamespaceHandle::UpdateClassCompatible(_IWmiObject *,ushort const *,_IWmiObject *,_IWmiObject *,__int64)
0x1800361a9  mov     ebx, eax
0x1800361ab  test    eax, eax
0x1800361ad  jns     short loc_1800361F9
0x1800361af  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800361b5  mov     edx, ebx
0x1800361b7  mov     rcx, rax
0x1800361ba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800361c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361c7  lea     rax, WPP_GLOBAL_Control
0x1800361ce  cmp     rcx, rax
0x1800361d1  jz      short loc_180036220
0x1800361d3  test    byte ptr [rcx+1Ch], 1
0x1800361d7  jz      short loc_180036220
0x1800361d9  cmp     byte ptr [rcx+19h], 2
0x1800361dd  jb      short loc_180036220
0x1800361df  mov     edx, 10Eh
0x1800361e4  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800361eb  mov     r9d, ebx
0x1800361ee  mov     rcx, [rcx+10h]
0x1800361f2  call    WPP_SF_d
0x1800361f7  jmp     short loc_180036220
0x1800361f9  bt      r12d, 0Ch
0x1800361fe  jb      short loc_18003621E
0x180036200  mov     [rsp+0D8h+var_B0], r15; struct _IWmiObject *
0x180036205  mov     [rsp+0D8h+var_B8], r14; struct _IWmiObject *
0x18003620a  mov     r9, rbp; unsigned __int16 *
0x18003620d  mov     r8d, 0Ch; unsigned int
0x180036213  mov     rdx, r13; struct CEventCollector *
0x180036216  mov     rcx, rdi; this
0x180036219  call    ?FireEvent@CNamespaceHandle@@IEAAJAEAVCEventCollector@@KPEBGPEAU_IWmiObject@@2@Z; CNamespaceHandle::FireEvent(CEventCollector &,ulong,ushort const *,_IWmiObject *,_IWmiObject *)
0x18003621e  xor     ebx, ebx
0x180036220  lea     rcx, [rsp+0D8h+var_A8]
0x180036225  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x18003622b  mov     eax, ebx
0x18003622d  add     rsp, 98h
0x180036234  pop     r15
0x180036236  pop     r14
0x180036238  pop     r13
0x18003623a  pop     r12
0x18003623c  pop     rdi
0x18003623d  pop     rsi
0x18003623e  pop     rbp
0x18003623f  pop     rbx
0x180036240  retn
```
