# CNamespaceHandle::UpdateClassSafeForce(_IWmiObject *,ulong,ushort const *,_IWmiObject *,_IWmiObject *,CEventCollector &,ulong)

- ea: `0x180036248`
- end: `0x1800363e0`
- name: `?UpdateClassSafeForce@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@KPEBG00AEAVCEventCollector@@K@Z`
- size: `408`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct _IWmiObject *, unsigned int, const unsigned __int16 *, struct _IWmiObject *, struct _IWmiObject *, struct CEventCollector *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800262cc`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180025180`
- `0x180027000`
- `0x180035f1c`
- `0x180036248`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180036323`
- `wbemcomn!GetMemLogObject` at `0x180036387`
- `wbemcomn!GetMemLogObject` at `0x180036323`
- `wbemcomn!GetMemLogObject` at `0x180036387`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003632e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036392`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003632e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036392`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CNamespaceHandle::UpdateClassSafeForce(
        CNamespaceHandle *this,
        struct _IWmiObject *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        struct _IWmiObject *a5,
        struct _IWmiObject *a6,
        struct CEventCollector *a7)
{
  int updated; // eax
  int v12; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v14; // rcx
  __int64 v15; // rdx
  CMemoryLog *v16; // rax
  unsigned int v18; // [rsp+38h] [rbp-40h]

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 261, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  updated = CNamespaceHandle::UpdateClassAggressively(this, a2, a3, a4, a6, a5, a7, v18);
  v12 = updated;
  if ( updated < 0 )
  {
    if ( updated == -2147217402 || updated == -2147217337 || updated == -2147217326 || (a3 & 0x40) == 0 )
      goto LABEL_16;
    v12 = CNamespaceHandle::DeleteClass(this, a4, a7, 0, 2u);
    if ( v12 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v12);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 262;
LABEL_21:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)v12);
        return (unsigned int)v12;
      }
      return (unsigned int)v12;
    }
    v12 = CNamespaceHandle::UpdateClassCompatible(this, a2, a4, a6, 0, 0);
    if ( v12 < 0 )
    {
LABEL_16:
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, v12);
    }
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 263;
    goto LABEL_21;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180036248  push    rbx
0x18003624a  push    rbp
0x18003624b  push    rsi
0x18003624c  push    rdi
0x18003624d  push    r12
0x18003624f  push    r14
0x180036251  push    r15
0x180036253  sub     rsp, 40h
0x180036257  mov     rdi, r9
0x18003625a  mov     ebp, r8d
0x18003625d  mov     r15, rdx
0x180036260  mov     rsi, rcx
0x180036263  mov     rcx, cs:WPP_GLOBAL_Control
0x18003626a  lea     rax, WPP_GLOBAL_Control
0x180036271  cmp     rcx, rax
0x180036274  jz      short loc_180036297
0x180036276  test    byte ptr [rcx+1Ch], 1
0x18003627a  jz      short loc_180036297
0x18003627c  cmp     byte ptr [rcx+19h], 5
0x180036280  jb      short loc_180036297
0x180036282  mov     rcx, [rcx+10h]
0x180036286  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003628d  mov     edx, 105h
0x180036292  call    WPP_SF_
0x180036297  mov     rax, [rsp+78h+arg_20]
0x18003629f  mov     r9, rdi; unsigned __int16 *
0x1800362a2  mov     r14, [rsp+78h+arg_30]
0x1800362aa  mov     r8d, ebp; unsigned int
0x1800362ad  mov     r12, [rsp+78h+arg_28]
0x1800362b5  mov     rdx, r15; struct _IWmiObject *
0x1800362b8  mov     [rsp+78h+var_48], r14; struct CEventCollector *
0x1800362bd  mov     rcx, rsi; this
0x1800362c0  mov     [rsp+78h+var_50], rax; struct _IWmiObject *
0x1800362c5  mov     [rsp+78h+var_58], r12; struct _IWmiObject *
0x1800362ca  call    ?UpdateClassAggressively@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@KPEBG00AEAVCEventCollector@@K@Z; CNamespaceHandle::UpdateClassAggressively(_IWmiObject *,ulong,ushort const *,_IWmiObject *,_IWmiObject *,CEventCollector &,ulong)
0x1800362cf  mov     ebx, eax
0x1800362d1  test    eax, eax
0x1800362d3  jns     loc_180036398
0x1800362d9  cmp     eax, 80041006h
0x1800362de  jz      loc_180036387
0x1800362e4  cmp     eax, 80041047h
0x1800362e9  jz      loc_180036387
0x1800362ef  cmp     eax, 80041052h
0x1800362f4  jz      loc_180036387
0x1800362fa  test    bpl, 40h
0x1800362fe  jz      loc_180036387
0x180036304  xor     r9d, r9d; bool
0x180036307  mov     dword ptr [rsp+78h+var_58], 2; unsigned int
0x18003630f  mov     r8, r14; struct CEventCollector *
0x180036312  mov     rdx, rdi; unsigned __int16 *
0x180036315  mov     rcx, rsi; this
0x180036318  call    ?DeleteClass@CNamespaceHandle@@IEAAJPEBGAEAVCEventCollector@@_NK@Z; CNamespaceHandle::DeleteClass(ushort const *,CEventCollector &,bool,ulong)
0x18003631d  mov     ebx, eax
0x18003631f  test    eax, eax
0x180036321  jns     short loc_18003635E
0x180036323  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036329  mov     rcx, rax
0x18003632c  mov     edx, ebx
0x18003632e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036334  mov     rcx, cs:WPP_GLOBAL_Control
0x18003633b  lea     rax, WPP_GLOBAL_Control
0x180036342  cmp     rcx, rax
0x180036345  jz      loc_1800363CF
0x18003634b  test    byte ptr [rcx+1Ch], 1
0x18003634f  jz      short loc_1800363CF
0x180036351  cmp     byte ptr [rcx+19h], 2
0x180036355  jb      short loc_1800363CF
0x180036357  mov     edx, 106h
0x18003635c  jmp     short loc_1800363BC
0x18003635e  mov     [rsp+78h+var_50], 0; __int64
0x180036367  mov     r9, r12; struct _IWmiObject *
0x18003636a  mov     r8, rdi; unsigned __int16 *
0x18003636d  mov     [rsp+78h+var_58], 0; struct _IWmiObject *
0x180036376  mov     rdx, r15; struct _IWmiObject *
0x180036379  mov     rcx, rsi; this
0x18003637c  call    ?UpdateClassCompatible@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG00_J@Z; CNamespaceHandle::UpdateClassCompatible(_IWmiObject *,ushort const *,_IWmiObject *,_IWmiObject *,__int64)
0x180036381  mov     ebx, eax
0x180036383  test    eax, eax
0x180036385  jns     short loc_180036398
0x180036387  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003638d  mov     rcx, rax
0x180036390  mov     edx, ebx
0x180036392  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036398  mov     rcx, cs:WPP_GLOBAL_Control
0x18003639f  lea     rax, WPP_GLOBAL_Control
0x1800363a6  cmp     rcx, rax
0x1800363a9  jz      short loc_1800363CF
0x1800363ab  test    byte ptr [rcx+1Ch], 1
0x1800363af  jz      short loc_1800363CF
0x1800363b1  cmp     byte ptr [rcx+19h], 2
0x1800363b5  jb      short loc_1800363CF
0x1800363b7  mov     edx, 107h
0x1800363bc  mov     rcx, [rcx+10h]
0x1800363c0  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800363c7  mov     r9d, ebx
0x1800363ca  call    WPP_SF_d
0x1800363cf  mov     eax, ebx
0x1800363d1  add     rsp, 40h
0x1800363d5  pop     r15
0x1800363d7  pop     r14
0x1800363d9  pop     r12
0x1800363db  pop     rdi
0x1800363dc  pop     rsi
0x1800363dd  pop     rbp
0x1800363de  pop     rbx
0x1800363df  retn
```
