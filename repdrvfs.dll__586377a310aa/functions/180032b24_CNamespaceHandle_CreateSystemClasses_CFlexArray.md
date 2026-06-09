# CNamespaceHandle::CreateSystemClasses(CFlexArray &)

- ea: `0x180032b24`
- end: `0x180032f01`
- name: `?CreateSystemClasses@CNamespaceHandle@@QEAAJAEAVCFlexArray@@@Z`
- size: `989`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, struct CFlexArray *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b064`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180006000`
- `0x18001b578`
- `0x18001d334`
- `0x18001e134`
- `0x1800240ac`
- `0x180027504`
- `0x180027580`
- `0x180027e8c`
- `0x180031128`
- `0x180032b24`
- `0x1800443df`
- `0x180044420`
- `0x180048010`

## import_xrefs

- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180032cdd`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180032cea`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180032cdd`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180032cea`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180032cf9`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180032cf9`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x180032e6a`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x180032e6a`
- `wbemcomn!GetMemLogObject` at `0x180032c14`
- `wbemcomn!GetMemLogObject` at `0x180032c6e`
- `wbemcomn!GetMemLogObject` at `0x180032dfa`
- `wbemcomn!GetMemLogObject` at `0x180032e94`
- `wbemcomn!GetMemLogObject` at `0x180032c14`
- `wbemcomn!GetMemLogObject` at `0x180032c6e`
- `wbemcomn!GetMemLogObject` at `0x180032dfa`
- `wbemcomn!GetMemLogObject` at `0x180032e94`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032c1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032c79`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032e06`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032e9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032c1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032c79`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032e06`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032e9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNamespaceHandle::CreateSystemClasses(CNamespaceHandle *this, struct CFlexArray *a2)
{
  CFlexArray *v2; // rsi
  CNamespaceHandle *v3; // r15
  int ClassDirect; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int CoreSvcs; // edi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v10; // rax
  _BYTE *v12; // r14
  struct _IWmiCoreServices *v13; // rbx
  unsigned int v14; // ebx
  struct _GUID *v15; // rdx
  CMemoryLog *v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  CMemoryLog *v20; // rax
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  struct _IWmiCoreServices *v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-A8h] BYREF
  struct CFlexArray *v24; // [rsp+60h] [rbp-A0h]
  _BYTE v25[144]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[2048]; // [rsp+100h] [rbp+0h] BYREF

  v2 = a2;
  v24 = a2;
  v3 = g_pSystemClassNamespace;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 535, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v22 = 0;
  ClassDirect = CNamespaceHandle::GetClassDirect(v3, L"CIM_Error", &IID__IWmiObject, (void **)&v22, 0, 0, 0, 0, 0);
  if ( ClassDirect >= 0 )
  {
    (*(void (__fastcall **)(struct _IWmiCoreServices *))(*(_QWORD *)v22 + 16LL))(v22);
    goto LABEL_7;
  }
  if ( ClassDirect == -2147217406 )
  {
LABEL_7:
    v5 = CFileCache::BeginTransaction((CFileCache *)byte_180058AF8);
    CoreSvcs = A51TranslateErrorCode(v5, v6, v7);
    if ( CoreSvcs < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, CoreSvcs);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          537,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)CoreSvcs);
      }
      return (unsigned int)CoreSvcs;
    }
    CEventCollector::CEventCollector((CEventCollector *)v25);
    memset_0(v26, 0, sizeof(v26));
    v23 = 256;
    if ( CFlexArray::Size(v2) )
    {
      v23 = CFlexArray::Size(v2);
      v12 = (_BYTE *)CFlexArray::operator[](v2, 0);
    }
    else
    {
      v22 = 0;
      CoreSvcs = CGlobals::GetCoreSvcs((CGlobals *)&g_Glob, &v22);
      if ( CoreSvcs < 0 )
        goto LABEL_35;
      v13 = v22;
      CoreSvcs = (*(__int64 (__fastcall **)(struct _IWmiCoreServices *, __int64, unsigned int *, _BYTE *))(*(_QWORD *)v22 + 128LL))(
                   v22,
                   1,
                   &v23,
                   v26);
      if ( v13 )
        (*(void (__fastcall **)(struct _IWmiCoreServices *))(*(_QWORD *)v13 + 16LL))(v13);
      if ( CoreSvcs < 0 )
      {
LABEL_35:
        CFlexArray::Empty(v2);
        if ( CoreSvcs >= 0 )
        {
          v17 = CFileCache::CommitTransaction((CFileCache *)byte_180058AF8);
          CoreSvcs = A51TranslateErrorCode(v17, v18, v19);
          if ( CoreSvcs >= 0 )
            goto LABEL_39;
        }
        else
        {
          CFileCache::AbortTransaction((CFileCache *)byte_180058AF8);
        }
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, CoreSvcs);
LABEL_39:
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            539,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)CoreSvcs);
        }
        CEventCollector::~CEventCollector((CEventCollector *)v25);
        return (unsigned int)CoreSvcs;
      }
      v12 = v26;
    }
    v14 = 0;
    if ( v23 )
    {
      do
      {
        v22 = 0;
        if ( CoreSvcs >= 0 )
        {
          CoreSvcs = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct _IWmiCoreServices **))&v12[8 * v14])(
                       *(_QWORD *)&v12[8 * v14],
                       &IID_IWbemClassObject,
                       &v22);
          if ( CoreSvcs >= 0 )
          {
            CoreSvcs = CNamespaceHandle::PutObject(
                         v3,
                         v15,
                         (__int64 (__fastcall ***)(_QWORD, GUID *, struct _IWmiObject **))v22,
                         0x1000u,
                         v21,
                         0,
                         (struct CEventCollector *)v25);
            (*(void (__fastcall **)(struct _IWmiCoreServices *))(*(_QWORD *)v22 + 16LL))(v22);
            if ( CoreSvcs < 0 )
            {
              v16 = GetMemLogObject();
              CMemoryLog::Write(v16, -1);
              if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  538,
                  WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                  (unsigned int)CoreSvcs);
              }
            }
          }
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v12[8 * v14] + 16LL))(*(_QWORD *)&v12[8 * v14]);
        ++v14;
      }
      while ( v14 < v23 );
      v2 = v24;
    }
    goto LABEL_35;
  }
  v10 = GetMemLogObject();
  CMemoryLog::Write(v10, ClassDirect);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      536,
      WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
      (unsigned int)ClassDirect);
  }
  return (unsigned int)ClassDirect;
}

```

## disassembly

```asm
0x180032b24  push    rbp
0x180032b26  push    rbx
0x180032b27  push    rsi
0x180032b28  push    rdi
0x180032b29  push    r14
0x180032b2b  push    r15
0x180032b2d  lea     rbp, [rsp-818h]
0x180032b35  sub     rsp, 918h
0x180032b3c  mov     rax, cs:__security_cookie
0x180032b43  xor     rax, rsp
0x180032b46  mov     [rbp+840h+var_40], rax
0x180032b4d  mov     rsi, rdx
0x180032b50  mov     [rsp+940h+var_8E0], rdx
0x180032b55  mov     r15, cs:?g_pSystemClassNamespace@@3PEAVCNamespaceHandle@@EA; CNamespaceHandle * g_pSystemClassNamespace
0x180032b5c  lea     r14, WPP_GLOBAL_Control
0x180032b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b6a  cmp     rcx, r14
0x180032b6d  jz      short loc_180032B90
0x180032b6f  test    byte ptr [rcx+1Ch], 1
0x180032b73  jz      short loc_180032B90
0x180032b75  cmp     byte ptr [rcx+19h], 5
0x180032b79  jb      short loc_180032B90
0x180032b7b  mov     edx, 217h
0x180032b80  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032b87  mov     rcx, [rcx+10h]
0x180032b8b  call    WPP_SF_
0x180032b90  mov     [rsp+940h+var_8F0], 0
0x180032b99  mov     [rsp+940h+var_900], 0; unsigned int
0x180032ba1  mov     [rsp+940h+var_908], 0; bool *
0x180032baa  mov     [rsp+940h+var_910], 0; bool *
0x180032bb3  mov     [rsp+940h+var_918], 0; __int64 *
0x180032bbc  mov     [rsp+940h+var_920], 0; unsigned int
0x180032bc1  lea     r9, [rsp+940h+var_8F0]; void **
0x180032bc6  lea     r8, IID__IWmiObject; struct _GUID *
0x180032bcd  lea     rdx, aCimError; "CIM_Error"
0x180032bd4  mov     rcx, r15; this
0x180032bd7  call    ?GetClassDirect@CNamespaceHandle@@IEAAJPEBGAEBU_GUID@@PEAPEAX_NPEA_JPEA_N5K@Z; CNamespaceHandle::GetClassDirect(ushort const *,_GUID const &,void * *,bool,__int64 *,bool *,bool *,ulong)
0x180032bdc  mov     ebx, eax
0x180032bde  test    eax, eax
0x180032be0  js      loc_180032C66
0x180032be6  mov     rcx, [rsp+940h+var_8F0]
0x180032beb  mov     rax, [rcx]
0x180032bee  mov     rax, [rax+10h]
0x180032bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bf7  lea     rcx, byte_180058AF8; this
0x180032bfe  call    ?BeginTransaction@CFileCache@@QEAAJXZ; CFileCache::BeginTransaction(void)
0x180032c03  mov     ecx, eax; int
0x180032c05  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x180032c0a  mov     edi, eax
0x180032c0c  test    eax, eax
0x180032c0e  jns     loc_180032CB6
0x180032c14  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180032c1a  mov     edx, edi
0x180032c1c  mov     rcx, rax
0x180032c1f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c2c  cmp     rcx, r14
0x180032c2f  jz      loc_180032EE0
0x180032c35  test    byte ptr [rcx+1Ch], 1
0x180032c39  jz      loc_180032EE0
0x180032c3f  cmp     byte ptr [rcx+19h], 2
0x180032c43  jb      loc_180032EE0
0x180032c49  mov     edx, 219h
0x180032c4e  mov     r9d, edi
0x180032c51  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032c58  mov     rcx, [rcx+10h]
0x180032c5c  call    WPP_SF_d
0x180032c61  jmp     loc_180032EE0
0x180032c66  cmp     ebx, 80041002h
0x180032c6c  jz      short loc_180032BF7
0x180032c6e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180032c74  mov     edx, ebx
0x180032c76  mov     rcx, rax
0x180032c79  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c86  cmp     rcx, r14
0x180032c89  jz      short loc_180032CAF
0x180032c8b  test    byte ptr [rcx+1Ch], 1
0x180032c8f  jz      short loc_180032CAF
0x180032c91  cmp     byte ptr [rcx+19h], 2
0x180032c95  jb      short loc_180032CAF
0x180032c97  mov     edx, 218h
0x180032c9c  mov     r9d, ebx
0x180032c9f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032ca6  mov     rcx, [rcx+10h]
0x180032caa  call    WPP_SF_d
0x180032caf  mov     eax, ebx
0x180032cb1  jmp     loc_180032EE2
0x180032cb6  lea     rcx, [rsp+940h+var_8D0]; this
0x180032cbb  call    ??0CEventCollector@@QEAA@XZ; CEventCollector::CEventCollector(void)
0x180032cc0  nop
0x180032cc1  xor     edx, edx; Val
0x180032cc3  mov     r8d, 800h; Size
0x180032cc9  lea     rcx, [rbp+840h+var_840]; void *
0x180032ccd  call    memset_0
0x180032cd2  mov     [rsp+940h+var_8E8], 100h
0x180032cda  mov     rcx, rsi
0x180032cdd  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180032ce3  test    eax, eax
0x180032ce5  jz      short loc_180032D04
0x180032ce7  mov     rcx, rsi
0x180032cea  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180032cf0  mov     [rsp+940h+var_8E8], eax
0x180032cf4  xor     edx, edx
0x180032cf6  mov     rcx, rsi
0x180032cf9  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180032cff  mov     r14, rax
0x180032d02  jmp     short loc_180032D75
0x180032d04  mov     [rsp+940h+var_8F0], 0
0x180032d0d  lea     rdx, [rsp+940h+var_8F0]; struct _IWmiCoreServices **
0x180032d12  lea     rcx, ?g_Glob@@3VCGlobals@@A; this
0x180032d19  call    ?GetCoreSvcs@CGlobals@@QEAAJPEAPEAU_IWmiCoreServices@@@Z; CGlobals::GetCoreSvcs(_IWmiCoreServices * *)
0x180032d1e  mov     edi, eax
0x180032d20  test    eax, eax
0x180032d22  js      loc_180032E67
0x180032d28  mov     rbx, [rsp+940h+var_8F0]
0x180032d2d  mov     [rsp+940h+var_8F0], rbx
0x180032d32  mov     rax, [rbx]
0x180032d35  lea     r9, [rbp+840h+var_840]
0x180032d39  lea     r8, [rsp+940h+var_8E8]
0x180032d3e  mov     edx, 1
0x180032d43  mov     rcx, rbx
0x180032d46  mov     rax, [rax+80h]
0x180032d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d52  mov     edi, eax
0x180032d54  test    rbx, rbx
0x180032d57  jz      short loc_180032D69
0x180032d59  mov     rax, [rbx]
0x180032d5c  mov     rcx, rbx
0x180032d5f  mov     rax, [rax+10h]
0x180032d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d68  nop
0x180032d69  test    edi, edi
0x180032d6b  js      loc_180032E67
0x180032d71  lea     r14, [rbp+840h+var_840]
0x180032d75  xor     ebx, ebx
0x180032d77  cmp     [rsp+940h+var_8E8], ebx
0x180032d7b  jbe     loc_180032E60
0x180032d81  lea     rsi, WPP_GLOBAL_Control
0x180032d88  mov     [rsp+940h+var_8F0], 0
0x180032d91  test    edi, edi
0x180032d93  js      loc_180032E3C
0x180032d99  movsxd  rax, ebx
0x180032d9c  mov     rcx, [r14+rax*8]
0x180032da0  mov     rax, [rcx]
0x180032da3  lea     r8, [rsp+940h+var_8F0]
0x180032da8  lea     rdx, IID_IWbemClassObject
0x180032daf  mov     rax, [rax]
0x180032db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032db7  mov     edi, eax
0x180032db9  test    eax, eax
0x180032dbb  js      short loc_180032E3C
0x180032dbd  lea     rax, [rsp+940h+var_8D0]
0x180032dc2  mov     [rsp+940h+var_910], rax; struct CEventCollector *
0x180032dc7  mov     [rsp+940h+var_918], 0; struct IWmiDbHandle **
0x180032dd0  mov     r9d, 1000h; unsigned int
0x180032dd6  mov     r8, [rsp+940h+var_8F0]; void *
0x180032ddb  mov     rcx, r15; this
0x180032dde  call    ?PutObject@CNamespaceHandle@@QEAAJAEBU_GUID@@PEAXKKPEAPEAUIWmiDbHandle@@AEAVCEventCollector@@@Z; CNamespaceHandle::PutObject(_GUID const &,void *,ulong,ulong,IWmiDbHandle * *,CEventCollector &)
0x180032de3  mov     edi, eax
0x180032de5  mov     rcx, [rsp+940h+var_8F0]
0x180032dea  mov     rax, [rcx]
0x180032ded  mov     rax, [rax+10h]
0x180032df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032df6  test    edi, edi
0x180032df8  jns     short loc_180032E3C
0x180032dfa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180032e00  or      edx, 0FFFFFFFFh
0x180032e03  mov     rcx, rax
0x180032e06  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e13  cmp     rcx, rsi
0x180032e16  jz      short loc_180032E3C
0x180032e18  test    byte ptr [rcx+1Ch], 1
0x180032e1c  jz      short loc_180032E3C
0x180032e1e  cmp     byte ptr [rcx+19h], 2
0x180032e22  jb      short loc_180032E3C
0x180032e24  mov     edx, 21Ah
0x180032e29  mov     r9d, edi
0x180032e2c  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032e33  mov     rcx, [rcx+10h]
0x180032e37  call    WPP_SF_d
0x180032e3c  movsxd  rax, ebx
0x180032e3f  mov     rcx, [r14+rax*8]
0x180032e43  mov     rax, [rcx]
0x180032e46  mov     rax, [rax+10h]
0x180032e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e4f  inc     ebx
0x180032e51  cmp     ebx, [rsp+940h+var_8E8]
0x180032e55  jb      loc_180032D88
0x180032e5b  mov     rsi, [rsp+940h+var_8E0]
0x180032e60  lea     r14, WPP_GLOBAL_Control
0x180032e67  mov     rcx, rsi
0x180032e6a  call    cs:__imp_?Empty@CFlexArray@@QEAAXXZ; CFlexArray::Empty(void)
0x180032e70  lea     rcx, byte_180058AF8; this
0x180032e77  test    edi, edi
0x180032e79  jns     short loc_180032E82
0x180032e7b  call    ?AbortTransaction@CFileCache@@QEAAJXZ; CFileCache::AbortTransaction(void)
0x180032e80  jmp     short loc_180032E94
0x180032e82  call    ?CommitTransaction@CFileCache@@QEAAJXZ; CFileCache::CommitTransaction(void)
0x180032e87  mov     ecx, eax; int
0x180032e89  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x180032e8e  mov     edi, eax
0x180032e90  test    eax, eax
0x180032e92  jns     short loc_180032EA5
0x180032e94  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180032e9a  mov     edx, edi
0x180032e9c  mov     rcx, rax
0x180032e9f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180032eac  cmp     rcx, r14
0x180032eaf  jz      short loc_180032ED6
0x180032eb1  test    byte ptr [rcx+1Ch], 1
0x180032eb5  jz      short loc_180032ED6
0x180032eb7  cmp     byte ptr [rcx+19h], 2
0x180032ebb  jb      short loc_180032ED6
0x180032ebd  mov     edx, 21Bh
0x180032ec2  mov     r9d, edi
0x180032ec5  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032ecc  mov     rcx, [rcx+10h]
0x180032ed0  call    WPP_SF_d
0x180032ed5  nop
0x180032ed6  lea     rcx, [rsp+940h+var_8D0]; this
0x180032edb  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x180032ee0  mov     eax, edi
0x180032ee2  mov     rcx, [rbp+840h+var_40]
0x180032ee9  xor     rcx, rsp; StackCookie
0x180032eec  call    __security_check_cookie
0x180032ef1  add     rsp, 918h
0x180032ef8  pop     r15
0x180032efa  pop     r14
0x180032efc  pop     rdi
0x180032efd  pop     rsi
0x180032efe  pop     rbx
0x180032eff  pop     rbp
0x180032f00  retn
```
