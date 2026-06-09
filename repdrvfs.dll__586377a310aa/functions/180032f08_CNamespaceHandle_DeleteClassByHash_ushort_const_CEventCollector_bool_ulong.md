# CNamespaceHandle::DeleteClassByHash(ushort const *,CEventCollector &,bool,ulong)

- ea: `0x180032f08`
- end: `0x1800332d6`
- name: `?DeleteClassByHash@CNamespaceHandle@@IEAAJPEBGAEAVCEventCollector@@_NK@Z`
- size: `974`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, struct CEventCollector *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180033a0c`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000a350`
- `0x180013f14`
- `0x180023bf0`
- `0x1800253d4`
- `0x180032f08`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800331a8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180033233`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180033290`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800331a8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180033233`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180033290`
- `wbemcomn!GetMemLogObject` at `0x180032fb7`
- `wbemcomn!GetMemLogObject` at `0x18003305c`
- `wbemcomn!GetMemLogObject` at `0x1800330ce`
- `wbemcomn!GetMemLogObject` at `0x180033155`
- `wbemcomn!GetMemLogObject` at `0x1800331e6`
- `wbemcomn!GetMemLogObject` at `0x180032fb7`
- `wbemcomn!GetMemLogObject` at `0x18003305c`
- `wbemcomn!GetMemLogObject` at `0x1800330ce`
- `wbemcomn!GetMemLogObject` at `0x180033155`
- `wbemcomn!GetMemLogObject` at `0x1800331e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032fc2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033067`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800330de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033165`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800331f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180032fc2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033067`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800330de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180033165`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800331f1`
- `OLEAUT32!__imp_VariantClear` at `0x180033123`
- `OLEAUT32!__imp_VariantClear` at `0x1800331b3`
- `OLEAUT32!__imp_VariantClear` at `0x18003323e`
- `OLEAUT32!__imp_VariantClear` at `0x18003329b`
- `OLEAUT32!__imp_VariantClear` at `0x180033123`
- `OLEAUT32!__imp_VariantClear` at `0x1800331b3`
- `OLEAUT32!__imp_VariantClear` at `0x18003323e`
- `OLEAUT32!__imp_VariantClear` at `0x18003329b`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::DeleteClassByHash(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        struct CEventCollector *a3,
        bool a4,
        unsigned int a5)
{
  int ClassByHash; // edi
  struct _IWmiObject *v9; // rbx
  CMemoryLog *v10; // rax
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  CNamespaceHandle *v13; // rcx
  CMemoryLog *v14; // rax
  CMemoryLog *MemLogObject; // rax
  bool v17; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v18; // [rsp+48h] [rbp-38h] BYREF
  struct _IWmiObject *v19[3]; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 370, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v19[0] = 0;
  v17 = 0;
  ClassByHash = CNamespaceHandle::GetClassByHash(this, a2, 0, v19, 0, 0, &v17, a5);
  v9 = v19[0];
  v19[1] = v19[0];
  if ( ClassByHash >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    ClassByHash = (*(__int64 (__fastcall **)(struct _IWmiObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v19[0] + 32LL))(
                    v19[0],
                    L"__CLASS",
                    0,
                    &pvarg,
                    0,
                    0);
    if ( ClassByHash >= 0 )
    {
      v19[2] = (struct _IWmiObject *)&pvarg;
      if ( pvarg.vt == 8 )
      {
        CFileName::CFileName((CFileName *)&v18);
        if ( v18 )
        {
          ClassByHash = CNamespaceHandle::ConstructClassDefFileNameFromHash(v13, a2, (struct CFileName *)&v18);
          if ( ClassByHash >= 0 )
          {
            ClassByHash = CNamespaceHandle::DeleteClassInternal(this, pvarg.bstrVal, v19[0], v18, a3, v17, a4, a5);
            CWin32DefaultArena::WbemMemFree(v18);
            VariantClear(&pvarg);
            if ( v9 )
              (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v9 + 16LL))(v9);
          }
          else
          {
            MemLogObject = GetMemLogObject();
            CMemoryLog::Write(MemLogObject, ClassByHash);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                375,
                WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
                (unsigned int)ClassByHash);
            }
            CWin32DefaultArena::WbemMemFree(v18);
            VariantClear(&pvarg);
            if ( v9 )
              (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v9 + 16LL))(v9);
          }
        }
        else
        {
          v14 = GetMemLogObject();
          ClassByHash = -2147217402;
          CMemoryLog::Write(v14, -2147217402);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              374,
              WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
              2147749894LL);
          }
          CWin32DefaultArena::WbemMemFree(0);
          VariantClear(&pvarg);
          if ( v9 )
            (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
      else
      {
        v12 = GetMemLogObject();
        ClassByHash = -2147217392;
        CMemoryLog::Write(v12, -2147217392);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            373,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749904LL);
        }
        VariantClear(&pvarg);
        if ( v9 )
          (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    else
    {
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, ClassByHash);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          372,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)ClassByHash);
      }
      if ( v9 )
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  else
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, ClassByHash);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        371,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)ClassByHash);
    }
    if ( v9 )
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)ClassByHash;
}

```

## disassembly

```asm
0x180032f08  mov     [rsp-28h+arg_0], rbx
0x180032f0d  mov     [rsp-28h+arg_8], rdi
0x180032f12  mov     [rsp-28h+arg_10], r8
0x180032f17  push    rbp
0x180032f18  push    r12
0x180032f1a  push    r13
0x180032f1c  push    r14
0x180032f1e  push    r15
0x180032f20  mov     rbp, rsp
0x180032f23  sub     rsp, 80h
0x180032f2a  mov     r13b, r9b
0x180032f2d  mov     r14, rdx
0x180032f30  mov     r15, rcx
0x180032f33  lea     rax, WPP_GLOBAL_Control
0x180032f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f41  cmp     rcx, rax
0x180032f44  jz      short loc_180032F67
0x180032f46  test    byte ptr [rcx+1Ch], 1
0x180032f4a  jz      short loc_180032F67
0x180032f4c  cmp     byte ptr [rcx+19h], 5
0x180032f50  jb      short loc_180032F67
0x180032f52  mov     edx, 172h
0x180032f57  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032f5e  mov     rcx, [rcx+10h]
0x180032f62  call    WPP_SF_
0x180032f67  mov     [rbp+var_30], 0
0x180032f6f  mov     [rbp+var_40], 0
0x180032f73  mov     r12d, [rbp+arg_20]
0x180032f77  mov     [rsp+80h+var_48], r12d; unsigned int
0x180032f7c  lea     rax, [rbp+var_40]
0x180032f80  mov     [rsp+80h+var_50], rax; bool *
0x180032f85  mov     [rsp+80h+var_58], 0; bool *
0x180032f8e  mov     [rsp+80h+var_60], 0; __int64 *
0x180032f97  lea     r9, [rbp+var_30]; struct _IWmiObject **
0x180032f9b  xor     r8d, r8d; bool
0x180032f9e  mov     rdx, r14; unsigned __int16 *
0x180032fa1  mov     rcx, r15; this
0x180032fa4  call    ?GetClassByHash@CNamespaceHandle@@IEAAJPEBG_NPEAPEAU_IWmiObject@@PEA_JPEA_N4K@Z; CNamespaceHandle::GetClassByHash(ushort const *,bool,_IWmiObject * *,__int64 *,bool *,bool *,ulong)
0x180032fa9  mov     edi, eax
0x180032fab  mov     rbx, [rbp+var_30]
0x180032faf  mov     [rbp+var_28], rbx
0x180032fb3  test    eax, eax
0x180032fb5  jns     short loc_18003301A
0x180032fb7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180032fbd  mov     edx, edi
0x180032fbf  mov     rcx, rax
0x180032fc2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180032fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fcf  lea     rax, WPP_GLOBAL_Control
0x180032fd6  cmp     rcx, rax
0x180032fd9  jz      short loc_180033000
0x180032fdb  test    byte ptr [rcx+1Ch], 1
0x180032fdf  jz      short loc_180033000
0x180032fe1  cmp     byte ptr [rcx+19h], 2
0x180032fe5  jb      short loc_180033000
0x180032fe7  mov     edx, 173h
0x180032fec  mov     r9d, edi
0x180032fef  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180032ff6  mov     rcx, [rcx+10h]
0x180032ffa  call    WPP_SF_d
0x180032fff  nop
0x180033000  test    rbx, rbx
0x180033003  jz      short loc_180033015
0x180033005  mov     rax, [rbx]
0x180033008  mov     rcx, rbx
0x18003300b  mov     rax, [rax+10h]
0x18003300f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033014  nop
0x180033015  jmp     loc_1800332B7
0x18003301a  xorps   xmm0, xmm0
0x18003301d  xor     eax, eax
0x18003301f  movups  xmmword ptr [rbp+pvarg], xmm0
0x180033023  mov     qword ptr [rbp+pvarg+10h], rax
0x180033027  mov     rax, [rbx]
0x18003302a  mov     [rsp+80h+var_58], 0
0x180033033  mov     [rsp+80h+var_60], 0
0x18003303c  lea     r9, [rbp+pvarg]
0x180033040  xor     r8d, r8d
0x180033043  lea     rdx, aClass; "__CLASS"
0x18003304a  mov     rcx, rbx
0x18003304d  mov     rax, [rax+20h]
0x180033051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033056  mov     edi, eax
0x180033058  test    eax, eax
0x18003305a  jns     short loc_1800330BF
0x18003305c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180033062  mov     edx, edi
0x180033064  mov     rcx, rax
0x180033067  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003306d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033074  lea     rax, WPP_GLOBAL_Control
0x18003307b  cmp     rcx, rax
0x18003307e  jz      short loc_1800330A5
0x180033080  test    byte ptr [rcx+1Ch], 1
0x180033084  jz      short loc_1800330A5
0x180033086  cmp     byte ptr [rcx+19h], 2
0x18003308a  jb      short loc_1800330A5
0x18003308c  mov     edx, 174h
0x180033091  mov     r9d, edi
0x180033094  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003309b  mov     rcx, [rcx+10h]
0x18003309f  call    WPP_SF_d
0x1800330a4  nop
0x1800330a5  test    rbx, rbx
0x1800330a8  jz      short loc_1800330BA
0x1800330aa  mov     rax, [rbx]
0x1800330ad  mov     rcx, rbx
0x1800330b0  mov     rax, [rax+10h]
0x1800330b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330b9  nop
0x1800330ba  jmp     loc_1800332B7
0x1800330bf  lea     rax, [rbp+pvarg]
0x1800330c3  mov     [rbp+var_20], rax
0x1800330c7  cmp     word ptr [rbp+pvarg], 8
0x1800330cc  jz      short loc_180033144
0x1800330ce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800330d4  mov     edi, 80041010h
0x1800330d9  mov     edx, edi
0x1800330db  mov     rcx, rax
0x1800330de  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800330e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800330eb  lea     rax, WPP_GLOBAL_Control
0x1800330f2  cmp     rcx, rax
0x1800330f5  jz      short loc_18003311F
0x1800330f7  test    byte ptr [rcx+1Ch], 1
0x1800330fb  jz      short loc_18003311F
0x1800330fd  cmp     byte ptr [rcx+19h], 2
0x180033101  jb      short loc_18003311F
0x180033103  mov     edx, 175h
0x180033108  mov     r9d, 80041010h
0x18003310e  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180033115  mov     rcx, [rcx+10h]
0x180033119  call    WPP_SF_d
0x18003311e  nop
0x18003311f  lea     rcx, [rbp+pvarg]; pvarg
0x180033123  call    cs:__imp_VariantClear
0x180033129  nop
0x18003312a  test    rbx, rbx
0x18003312d  jz      short loc_18003313F
0x18003312f  mov     rcx, [rbx]
0x180033132  mov     rax, [rcx+10h]
0x180033136  mov     rcx, rbx
0x180033139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003313e  nop
0x18003313f  jmp     loc_1800332B7
0x180033144  lea     rcx, [rbp+var_38]; this
0x180033148  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003314d  nop
0x18003314e  cmp     [rbp+var_38], 0
0x180033153  jnz     short loc_1800331D4
0x180033155  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003315b  mov     edi, 80041006h
0x180033160  mov     edx, edi
0x180033162  mov     rcx, rax
0x180033165  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003316b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033172  lea     rax, WPP_GLOBAL_Control
0x180033179  cmp     rcx, rax
0x18003317c  jz      short loc_1800331A6
0x18003317e  test    byte ptr [rcx+1Ch], 1
0x180033182  jz      short loc_1800331A6
0x180033184  cmp     byte ptr [rcx+19h], 2
0x180033188  jb      short loc_1800331A6
0x18003318a  mov     edx, 176h
0x18003318f  mov     r9d, 80041006h
0x180033195  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003319c  mov     rcx, [rcx+10h]
0x1800331a0  call    WPP_SF_d
0x1800331a5  nop
0x1800331a6  xor     ecx, ecx
0x1800331a8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800331ae  nop
0x1800331af  lea     rcx, [rbp+pvarg]; pvarg
0x1800331b3  call    cs:__imp_VariantClear
0x1800331b9  nop
0x1800331ba  test    rbx, rbx
0x1800331bd  jz      short loc_1800331CF
0x1800331bf  mov     rcx, [rbx]
0x1800331c2  mov     rax, [rcx+10h]
0x1800331c6  mov     rcx, rbx
0x1800331c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331ce  nop
0x1800331cf  jmp     loc_1800332B7
0x1800331d4  lea     r8, [rbp+var_38]; struct CFileName *
0x1800331d8  mov     rdx, r14; unsigned __int16 *
0x1800331db  call    ?ConstructClassDefFileNameFromHash@CNamespaceHandle@@IEAAJPEBGAEAVCFileName@@@Z; CNamespaceHandle::ConstructClassDefFileNameFromHash(ushort const *,CFileName &)
0x1800331e0  mov     edi, eax
0x1800331e2  test    eax, eax
0x1800331e4  jns     short loc_18003325C
0x1800331e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800331ec  mov     edx, edi
0x1800331ee  mov     rcx, rax
0x1800331f1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800331f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331fe  lea     rax, WPP_GLOBAL_Control
0x180033205  cmp     rcx, rax
0x180033208  jz      short loc_18003322F
0x18003320a  test    byte ptr [rcx+1Ch], 1
0x18003320e  jz      short loc_18003322F
0x180033210  cmp     byte ptr [rcx+19h], 2
0x180033214  jb      short loc_18003322F
0x180033216  mov     edx, 177h
0x18003321b  mov     r9d, edi
0x18003321e  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180033225  mov     rcx, [rcx+10h]
0x180033229  call    WPP_SF_d
0x18003322e  nop
0x18003322f  mov     rcx, [rbp+var_38]
0x180033233  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180033239  nop
0x18003323a  lea     rcx, [rbp+pvarg]; pvarg
0x18003323e  call    cs:__imp_VariantClear
0x180033244  nop
0x180033245  test    rbx, rbx
0x180033248  jz      short loc_18003325A
0x18003324a  mov     rax, [rbx]
0x18003324d  mov     rcx, rbx
0x180033250  mov     rax, [rax+10h]
0x180033254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033259  nop
0x18003325a  jmp     short loc_1800332B7
0x18003325c  mov     al, [rbp+var_40]
0x18003325f  mov     [rsp+80h+var_48], r12d; unsigned int
0x180033264  mov     byte ptr [rsp+80h+var_50], r13b; bool
0x180033269  mov     byte ptr [rsp+80h+var_58], al; bool
0x18003326d  mov     rax, [rbp+arg_10]
0x180033271  mov     [rsp+80h+var_60], rax; struct CEventCollector *
0x180033276  mov     r9, [rbp+var_38]; unsigned __int16 *
0x18003327a  mov     r8, [rbp+var_30]; struct _IWmiObject *
0x18003327e  mov     rdx, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x180033282  mov     rcx, r15; this
0x180033285  call    ?DeleteClassInternal@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@0AEAVCEventCollector@@_N3K@Z; CNamespaceHandle::DeleteClassInternal(ushort const *,_IWmiObject *,ushort const *,CEventCollector &,bool,bool,ulong)
0x18003328a  mov     edi, eax
0x18003328c  mov     rcx, [rbp+var_38]
0x180033290  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180033296  nop
0x180033297  lea     rcx, [rbp+pvarg]; pvarg
0x18003329b  call    cs:__imp_VariantClear
0x1800332a1  nop
0x1800332a2  test    rbx, rbx
0x1800332a5  jz      short loc_1800332B7
0x1800332a7  mov     rax, [rbx]
0x1800332aa  mov     rcx, rbx
0x1800332ad  mov     rax, [rax+10h]
0x1800332b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332b6  nop
0x1800332b7  mov     eax, edi
0x1800332b9  lea     r11, [rsp+80h+var_s0]
0x1800332c1  mov     rbx, [r11+30h]
0x1800332c5  mov     rdi, [r11+38h]
0x1800332c9  mov     rsp, r11
0x1800332cc  pop     r15
0x1800332ce  pop     r14
0x1800332d0  pop     r13
0x1800332d2  pop     r12
0x1800332d4  pop     rbp
0x1800332d5  retn
```
