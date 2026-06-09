# CWbemObjectArrayPacket::CalculateLength(long,IWbemClassObject * *,ulong *,CWbemClassToIdMap &,_GUID *,int *)

- ea: `0x18003b8f0`
- end: `0x18003bf37`
- name: `?CalculateLength@CWbemObjectArrayPacket@@QEAAJJPEAPEAUIWbemClassObject@@PEAKAEAVCWbemClassToIdMap@@PEAU_GUID@@PEAH@Z`
- size: `1607`
- prototype: `__int64 __fastcall(CWbemObjectArrayPacket *this, int, struct IWbemClassObject **, unsigned int *, struct _RTL_CRITICAL_SECTION *, struct _GUID *, int *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a000`
- `0x18003b020`
- `0x18003b0e0`
- `0x18005c460`
- `0x180083250`

## callees

- `0x180037120`
- `0x18003b8f0`
- `0x18003c128`
- `0x18003c534`
- `0x180091966`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003bc7e`
- `wbemcomn!GetMemLogObject` at `0x18003bd8f`
- `wbemcomn!GetMemLogObject` at `0x18003bde0`
- `wbemcomn!GetMemLogObject` at `0x18003be7d`
- `wbemcomn!GetMemLogObject` at `0x18003bed5`
- `wbemcomn!GetMemLogObject` at `0x18003bc7e`
- `wbemcomn!GetMemLogObject` at `0x18003bd8f`
- `wbemcomn!GetMemLogObject` at `0x18003bde0`
- `wbemcomn!GetMemLogObject` at `0x18003be7d`
- `wbemcomn!GetMemLogObject` at `0x18003bed5`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003bb0f`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003bb0f`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003ba84`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003ba84`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bc8a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bd9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bdec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003be89`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bee3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bc8a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bd9b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bdec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003be89`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003bee3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003bd57`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003bdd8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003bd57`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003bdd8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003ba0a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003ba0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWbemObjectArrayPacket::CalculateLength(
        CWbemObjectArrayPacket *this,
        int a2,
        struct IWbemClassObject **a3,
        unsigned int *a4,
        struct _RTL_CRITICAL_SECTION *a5,
        struct _GUID *a6,
        int *a7)
{
  int v7; // r14d
  unsigned int v8; // esi
  void *v9; // r15
  int v10; // r13d
  __int64 v11; // rdi
  struct IWbemClassObject **v12; // rax
  struct CWbemObject *v13; // r12
  struct _GUID *v14; // rbx
  unsigned __int64 v15; // rsi
  void *v16; // rax
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi
  unsigned int v19; // eax
  int v20; // ebx
  struct IWbemClassObject *v21; // rcx
  bool v22; // zf
  __int64 v23; // rax
  __int64 (__fastcall *v24)(struct _GUID *, _QWORD, _QWORD, __int64, struct IWbemClassObject ***); // rax
  int v25; // eax
  int v26; // ebx
  CMemoryLog *v27; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  int v33; // [rsp+30h] [rbp-51h]
  struct _GUID *v34; // [rsp+38h] [rbp-49h] BYREF
  void *v35; // [rsp+40h] [rbp-41h] BYREF
  __int64 v36; // [rsp+48h] [rbp-39h]
  void *v37; // [rsp+50h] [rbp-31h]
  __int64 v38; // [rsp+58h] [rbp-29h]
  unsigned int Size; // [rsp+60h] [rbp-21h] BYREF
  int Size_4; // [rsp+64h] [rbp-1Dh]
  struct IWbemClassObject **v41; // [rsp+68h] [rbp-19h] BYREF
  void *v42; // [rsp+70h] [rbp-11h]
  int v43; // [rsp+78h] [rbp-9h] BYREF
  _BYTE v44[64]; // [rsp+80h] [rbp-1h] BYREF
  int v45; // [rsp+D8h] [rbp+57h]
  struct IWbemClassObject **v46; // [rsp+E0h] [rbp+5Fh]

  v46 = a3;
  v45 = a2;
  v7 = 0;
  v8 = 12;
  Size_4 = 12;
  v33 = 0;
  v9 = 0;
  v42 = 0;
  v35 = 0;
  v36 = 0;
  v10 = 0;
  while ( 1 )
  {
    if ( v10 >= a2 )
    {
      if ( v7 < 0 )
      {
LABEL_73:
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v7);
      }
      else
      {
        *a4 = v8;
      }
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids,
          (unsigned int)v7);
      }
      if ( v9 && HIDWORD(v36) )
        CWin32DefaultArena::WbemMemFree(v9);
      v35 = 0;
      v36 = 0;
      return (unsigned int)v7;
    }
    if ( v7 < 0 )
      goto LABEL_73;
    v11 = v10;
    v12 = &a3[v10];
    v41 = v12;
    v13 = (struct CWbemObject *)*v12;
    if ( !*v12 )
      break;
    if ( (*(unsigned int (__fastcall **)(struct IWbemClassObject *))(*(_QWORD *)v13 + 600LL))(*v12) )
    {
      v20 = 1;
      a7[v10] = 1;
LABEL_33:
      v21 = *v41;
      if ( *v41 )
      {
        LODWORD(v41) = 0;
        v34 = 0;
        v7 = ((__int64 (__fastcall *)(struct IWbemClassObject *, GUID *, struct _GUID **))v21->lpVtbl->QueryInterface)(
               v21,
               &IID__IWmiObject,
               &v34);
        if ( v7 < 0 )
          goto LABEL_39;
        v22 = (*(unsigned int (__fastcall **)(struct _GUID *))(*(_QWORD *)&v34->Data1 + 600LL))(v34) == 0;
        v23 = *(_QWORD *)&v34->Data1;
        if ( v22 )
        {
          v33 = 33;
          v24 = *(__int64 (__fastcall **)(struct _GUID *, _QWORD, _QWORD, __int64, struct IWbemClassObject ***))(v23 + 568);
          v25 = v20 ? v24(v34, 0, 0, 7, &v41) : v24(v34, 0, 0, 3, &v41);
        }
        else
        {
          v33 = 17;
          v25 = (*(__int64 (__fastcall **)(struct _GUID *, _QWORD, _QWORD, struct IWbemClassObject ***))(v23 + 552))(
                  v34,
                  0,
                  0,
                  &v41);
        }
        v7 = v25;
        (*(void (__fastcall **)(struct _GUID *))(*(_QWORD *)&v34->Data1 + 16LL))(v34);
        if ( v7 < 0 )
        {
LABEL_39:
          if ( v7 == -2147217348 )
          {
            v26 = (_DWORD)v41 + v33;
            v33 += (int)v41;
            v7 = 0;
            goto LABEL_41;
          }
          v27 = GetMemLogObject();
          CMemoryLog::Write(v27, v7);
        }
        v26 = v33;
      }
      else
      {
        v7 = 0;
        v26 = 9;
        v33 = 9;
      }
LABEL_41:
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          (unsigned int)v7);
      }
      if ( v7 >= 0 )
        Size_4 = v26 + v8;
      goto LABEL_45;
    }
    v14 = &a6[v10];
    v34 = v14;
    if ( !v14 )
    {
      v7 = -2147217400;
LABEL_82:
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, v7);
LABEL_27:
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_f53bfe3cc5f131955f941a7dc61642fc_Traceguids,
          (unsigned int)v7);
      }
      goto LABEL_29;
    }
    Size = 0;
    v43 = 0;
    v7 = (*(__int64 (__fastcall **)(struct CWbemObject *, _QWORD, _QWORD, __int64, unsigned int *))(*(_QWORD *)v13
                                                                                                  + 568LL))(
           v13,
           0,
           0,
           4,
           &Size);
    if ( v7 != -2147217348 )
      goto LABEL_25;
    v37 = 0;
    v38 = 0;
    v15 = Size;
    if ( (unsigned int)v36 < Size )
    {
      CMemBuffer::Free((CMemBuffer *)&v35);
      v16 = CWin32DefaultArena::WbemMemAlloc(v15);
      v42 = v16;
      v35 = v16;
      if ( v16 )
        v36 = (unsigned int)v15 | 0x100000000LL;
      LODWORD(v15) = Size;
      v9 = v16;
      v37 = v16;
      v38 = Size;
      if ( !v16 )
      {
        v7 = -2147217402;
        goto LABEL_24;
      }
    }
    else
    {
      v37 = v9;
      v38 = Size;
    }
    v7 = (*(__int64 (__fastcall **)(struct CWbemObject *, void *, _QWORD, __int64, int *))(*(_QWORD *)v13 + 568LL))(
           v13,
           v9,
           (unsigned int)v15,
           4,
           &v43);
    if ( v7 < 0 )
      goto LABEL_24;
    CInCritSec::CInCritSec((CInCritSec *)v44, a5);
    CriticalSection = a5[1].DebugInfo->CriticalSection;
    DebugInfo = a5[1].DebugInfo;
    if ( BYTE1(CriticalSection->LockSemaphore) )
      goto LABEL_66;
    do
    {
      v19 = (unsigned int)CriticalSection[1].DebugInfo;
      if ( v19 == (_DWORD)v15 )
      {
        if ( memcmp_0((const void *)CriticalSection->SpinCount, v9, v19) >= 0 )
          goto LABEL_17;
      }
      else if ( v19 >= (unsigned int)v15 )
      {
LABEL_17:
        DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)CriticalSection;
        CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->DebugInfo;
        continue;
      }
      CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->OwningThread;
    }
    while ( !BYTE1(CriticalSection->LockSemaphore) );
    if ( DebugInfo == a5[1].DebugInfo )
      goto LABEL_66;
    if ( (_DWORD)v15 == DebugInfo->Flags )
    {
      if ( memcmp_0(v9, *(const void **)&DebugInfo->EntryCount, (unsigned int)v15) >= 0 )
        goto LABEL_22;
LABEL_66:
      v7 = -2147217407;
      v14 = v34;
    }
    else
    {
      if ( (unsigned int)v15 < DebugInfo->Flags )
        goto LABEL_66;
LABEL_22:
      v14 = v34;
      *v34 = *(struct _GUID *)&DebugInfo[1].Type;
    }
    CInCritSec::~CInCritSec((CInCritSec *)v44);
    v11 = v10;
LABEL_24:
    v37 = 0;
    v38 = 0;
    if ( v7 != -2147217348 )
    {
LABEL_25:
      if ( v7 != -2147217407 )
      {
        if ( v7 >= 0 )
          goto LABEL_27;
        goto LABEL_82;
      }
    }
LABEL_29:
    if ( v7 >= 0 )
    {
      v20 = 0;
      goto LABEL_31;
    }
    if ( v7 == -2147217402 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids, 2147749894LL);
      }
      if ( v42 && HIDWORD(v36) )
        CWin32DefaultArena::WbemMemFree(v42);
      v35 = 0;
      v36 = 0;
      return (unsigned int)v7;
    }
    v7 = CWbemClassToIdMap::AssignClassId((CWbemClassToIdMap *)a5, v13, v14, (struct CMemBuffer *)&v35);
    v20 = 1;
    v42 = v35;
LABEL_31:
    a7[v11] = v20;
    if ( v7 >= 0 )
    {
      v8 = Size_4;
      goto LABEL_33;
    }
LABEL_45:
    ++v10;
    a2 = v45;
    a3 = v46;
    v9 = v42;
    v8 = Size_4;
  }
  v32 = GetMemLogObject();
  CMemoryLog::Write(v32, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids, 2147749896LL);
  }
  CMemBuffer::Free((CMemBuffer *)&v35);
  return 2147749896LL;
}

```

## disassembly

```asm
0x18003b8f0  mov     [rsp-8+arg_0], rbx
0x18003b8f5  mov     [rsp-8+arg_18], r9
0x18003b8fa  mov     [rsp-8+arg_10], r8
0x18003b8ff  mov     [rsp-8+arg_8], edx
0x18003b903  push    rbp
0x18003b904  push    rsi
0x18003b905  push    rdi
0x18003b906  push    r12
0x18003b908  push    r13
0x18003b90a  push    r14
0x18003b90c  push    r15
0x18003b90e  lea     rbp, [rsp-0Fh]
0x18003b913  sub     rsp, 90h
0x18003b91a  xor     ebx, ebx
0x18003b91c  mov     r14d, ebx
0x18003b91f  mov     esi, 0Ch
0x18003b924  mov     dword ptr [rbp+3Fh+Size+4], esi
0x18003b927  mov     [rbp+3Fh+var_90], ebx
0x18003b92a  mov     r15d, ebx
0x18003b92d  mov     [rbp+3Fh+var_50], rbx
0x18003b931  mov     [rbp+3Fh+var_80], rbx
0x18003b935  mov     [rbp+3Fh+var_78], rbx
0x18003b939  mov     r13d, ebx
0x18003b93c  nop     dword ptr [rax+00h]
0x18003b940  cmp     r13d, edx
0x18003b943  jge     loc_18003BCB3
0x18003b949  test    r14d, r14d
0x18003b94c  js      loc_18003BDE0
0x18003b952  movsxd  rdi, r13d
0x18003b955  lea     rax, [r8+rdi*8]
0x18003b959  mov     [rbp+3Fh+var_58], rax
0x18003b95d  mov     r12, [rax]
0x18003b960  test    r12, r12
0x18003b963  jz      loc_18003BED5
0x18003b969  mov     rax, [r12]
0x18003b96d  mov     rcx, r12
0x18003b970  mov     rax, [rax+258h]
0x18003b977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b97c  test    eax, eax
0x18003b97e  jnz     loc_18003BC6D
0x18003b984  mov     rbx, rdi
0x18003b987  shl     rbx, 4
0x18003b98b  add     rbx, [rbp+3Fh+arg_28]
0x18003b98f  mov     [rbp+3Fh+var_88], rbx
0x18003b993  jz      loc_18003BE74
0x18003b999  xor     eax, eax
0x18003b99b  mov     dword ptr [rbp+3Fh+Size], eax
0x18003b99e  mov     [rbp+3Fh+var_48], eax
0x18003b9a1  mov     rax, [r12]
0x18003b9a5  lea     rcx, [rbp+3Fh+Size]
0x18003b9a9  mov     [rsp+0C0h+var_A0], rcx
0x18003b9ae  mov     r9d, 4
0x18003b9b4  xor     r8d, r8d
0x18003b9b7  xor     edx, edx
0x18003b9b9  mov     rcx, r12
0x18003b9bc  mov     rax, [rax+238h]
0x18003b9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9c8  mov     r14d, eax
0x18003b9cb  cmp     eax, 8004103Ch
0x18003b9d0  jnz     loc_18003BE6C
0x18003b9d6  xor     r14d, r14d
0x18003b9d9  mov     [rbp+3Fh+var_70], r14
0x18003b9dd  mov     [rbp+3Fh+var_68], r14
0x18003b9e1  mov     esi, dword ptr [rbp+3Fh+Size]
0x18003b9e4  cmp     dword ptr [rbp+3Fh+var_78], esi
0x18003b9e7  jb      short loc_18003B9FE
0x18003b9e9  mov     [rbp+3Fh+var_70], r14
0x18003b9ed  mov     [rbp+3Fh+var_68], r14
0x18003b9f1  mov     [rbp+3Fh+var_70], r15
0x18003b9f5  mov     dword ptr [rbp+3Fh+var_68], esi
0x18003b9f8  mov     dword ptr [rbp+3Fh+var_68+4], r14d
0x18003b9fc  jmp     short loc_18003BA49
0x18003b9fe  lea     rcx, [rbp+3Fh+var_80]; this
0x18003ba02  call    ?Free@CMemBuffer@@QEAAXXZ; CMemBuffer::Free(void)
0x18003ba07  mov     rcx, rsi
0x18003ba0a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003ba10  mov     [rbp+3Fh+var_50], rax
0x18003ba14  mov     [rbp+3Fh+var_80], rax
0x18003ba18  test    rax, rax
0x18003ba1b  jz      short loc_18003BA27
0x18003ba1d  mov     dword ptr [rbp+3Fh+var_78], esi
0x18003ba20  mov     dword ptr [rbp+3Fh+var_78+4], 1
0x18003ba27  mov     esi, dword ptr [rbp+3Fh+Size]
0x18003ba2a  mov     [rbp+3Fh+var_70], r14
0x18003ba2e  mov     [rbp+3Fh+var_68], r14
0x18003ba32  mov     r15, rax
0x18003ba35  mov     [rbp+3Fh+var_70], rax
0x18003ba39  mov     dword ptr [rbp+3Fh+var_68], esi
0x18003ba3c  mov     dword ptr [rbp+3Fh+var_68+4], r14d
0x18003ba40  test    rax, rax
0x18003ba43  jz      loc_18003BD84
0x18003ba49  mov     rax, [r12]
0x18003ba4d  lea     rcx, [rbp+3Fh+var_48]
0x18003ba51  mov     [rsp+0C0h+var_A0], rcx
0x18003ba56  mov     r9d, 4
0x18003ba5c  mov     r8d, esi
0x18003ba5f  mov     rdx, r15
0x18003ba62  mov     rcx, r12
0x18003ba65  mov     rax, [rax+238h]
0x18003ba6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba71  mov     r14d, eax
0x18003ba74  test    eax, eax
0x18003ba76  js      loc_18003BB18
0x18003ba7c  mov     rdx, [rbp+3Fh+arg_20]
0x18003ba80  lea     rcx, [rbp+3Fh+var_40]
0x18003ba84  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003ba8a  nop
0x18003ba8b  mov     rdx, [rbp+3Fh+arg_20]
0x18003ba8f  mov     rcx, [rdx+28h]
0x18003ba93  mov     rbx, [rcx+8]
0x18003ba97  mov     rdi, rcx
0x18003ba9a  cmp     byte ptr [rbx+19h], 0
0x18003ba9e  jnz     loc_18003BD75
0x18003baa4  mov     eax, [rbx+28h]
0x18003baa7  cmp     eax, esi
0x18003baa9  jnz     loc_18003BD15
0x18003baaf  mov     r8d, eax; Size
0x18003bab2  mov     rdx, r15; Buf2
0x18003bab5  mov     rcx, [rbx+20h]; Buf1
0x18003bab9  call    memcmp_0
0x18003babe  test    eax, eax
0x18003bac0  js      loc_18003BD0C
0x18003bac6  mov     rdi, rbx
0x18003bac9  mov     rbx, [rbx]
0x18003bacc  cmp     byte ptr [rbx+19h], 0
0x18003bad0  jz      short loc_18003BAA4
0x18003bad2  mov     rax, [rbp+3Fh+arg_20]
0x18003bad6  cmp     rdi, [rax+28h]
0x18003bada  jz      loc_18003BD75
0x18003bae0  cmp     esi, [rdi+28h]
0x18003bae3  jnz     loc_18003BD6F
0x18003bae9  mov     r8d, esi; Size
0x18003baec  mov     rdx, [rdi+20h]; Buf2
0x18003baf0  mov     rcx, r15; Buf1
0x18003baf3  call    memcmp_0
0x18003baf8  test    eax, eax
0x18003bafa  js      loc_18003BD75
0x18003bb00  movups  xmm0, xmmword ptr [rdi+30h]
0x18003bb04  mov     rbx, [rbp+3Fh+var_88]
0x18003bb08  movups  xmmword ptr [rbx], xmm0
0x18003bb0b  lea     rcx, [rbp+3Fh+var_40]
0x18003bb0f  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003bb15  movsxd  rdi, r13d
0x18003bb18  xor     r15d, r15d
0x18003bb1b  mov     [rbp+3Fh+var_70], r15
0x18003bb1f  mov     [rbp+3Fh+var_68], r15
0x18003bb23  cmp     r14d, 8004103Ch
0x18003bb2a  jz      short loc_18003BB5B
0x18003bb2c  cmp     r14d, 80041001h
0x18003bb33  jz      short loc_18003BB5B
0x18003bb35  test    r14d, r14d
0x18003bb38  js      loc_18003BE7D
0x18003bb3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb45  lea     rax, WPP_GLOBAL_Control
0x18003bb4c  cmp     rcx, rax
0x18003bb4f  jz      short loc_18003BB5B
0x18003bb51  test    byte ptr [rcx+1Ch], 1
0x18003bb55  jnz     loc_18003BDF7
0x18003bb5b  test    r14d, r14d
0x18003bb5e  js      loc_18003BD1D
0x18003bb64  mov     ebx, r15d
0x18003bb67  mov     rax, [rbp+3Fh+arg_30]
0x18003bb6b  mov     [rax+rdi*4], ebx
0x18003bb6e  test    r14d, r14d
0x18003bb71  js      loc_18003BC57
0x18003bb77  mov     esi, dword ptr [rbp+3Fh+Size+4]
0x18003bb7a  mov     rcx, [rbp+3Fh+var_58]
0x18003bb7e  mov     rcx, [rcx]
0x18003bb81  test    rcx, rcx
0x18003bb84  jz      loc_18003BE94
0x18003bb8a  xor     r15d, r15d
0x18003bb8d  mov     dword ptr [rbp+3Fh+var_58], r15d
0x18003bb91  mov     [rbp+3Fh+var_88], r15
0x18003bb95  mov     rax, [rcx]
0x18003bb98  lea     r8, [rbp+3Fh+var_88]
0x18003bb9c  lea     rdx, IID__IWmiObject
0x18003bba3  mov     rax, [rax]
0x18003bba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbab  mov     r14d, eax
0x18003bbae  test    eax, eax
0x18003bbb0  js      short loc_18003BC1B
0x18003bbb2  mov     rcx, [rbp+3Fh+var_88]
0x18003bbb6  mov     rax, [rcx]
0x18003bbb9  mov     rax, [rax+258h]
0x18003bbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbc5  mov     rcx, [rbp+3Fh+var_88]
0x18003bbc9  xor     r8d, r8d
0x18003bbcc  test    eax, eax
0x18003bbce  mov     rax, [rcx]
0x18003bbd1  jnz     loc_18003BC95
0x18003bbd7  mov     [rbp+3Fh+var_90], 21h ; '!'
0x18003bbde  lea     rdx, [rbp+3Fh+var_58]
0x18003bbe2  mov     [rsp+0C0h+var_A0], rdx
0x18003bbe7  mov     rax, [rax+238h]
0x18003bbee  xor     edx, edx
0x18003bbf0  test    ebx, ebx
0x18003bbf2  jnz     loc_18003BD5F
0x18003bbf8  mov     r9d, 3
0x18003bbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc03  mov     r14d, eax
0x18003bc06  mov     rcx, [rbp+3Fh+var_88]
0x18003bc0a  mov     rax, [rcx]
0x18003bc0d  mov     rax, [rax+10h]
0x18003bc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc16  test    r14d, r14d
0x18003bc19  jns     short loc_18003BC90
0x18003bc1b  cmp     r14d, 8004103Ch
0x18003bc22  jnz     short loc_18003BC7E
0x18003bc24  mov     ebx, [rbp+3Fh+var_90]
0x18003bc27  add     ebx, dword ptr [rbp+3Fh+var_58]
0x18003bc2a  mov     [rbp+3Fh+var_90], ebx
0x18003bc2d  mov     r14d, r15d
0x18003bc30  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bc37  lea     rax, WPP_GLOBAL_Control
0x18003bc3e  cmp     rcx, rax
0x18003bc41  jz      short loc_18003BC4D
0x18003bc43  test    byte ptr [rcx+1Ch], 1
0x18003bc47  jnz     loc_18003BE1E
0x18003bc4d  test    r14d, r14d
0x18003bc50  js      short loc_18003BC57
0x18003bc52  add     esi, ebx
0x18003bc54  mov     dword ptr [rbp+3Fh+Size+4], esi
0x18003bc57  inc     r13d
0x18003bc5a  mov     edx, [rbp+3Fh+arg_8]
0x18003bc5d  mov     r8, [rbp+3Fh+arg_10]
0x18003bc61  mov     r15, [rbp+3Fh+var_50]
0x18003bc65  mov     esi, dword ptr [rbp+3Fh+Size+4]
0x18003bc68  jmp     loc_18003B940
0x18003bc6d  mov     ebx, 1
0x18003bc72  mov     rax, [rbp+3Fh+arg_30]
0x18003bc76  mov     [rax+rdi*4], ebx
0x18003bc79  jmp     loc_18003BB7A
0x18003bc7e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003bc84  mov     edx, r14d
0x18003bc87  mov     rcx, rax
0x18003bc8a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003bc90  mov     ebx, [rbp+3Fh+var_90]
0x18003bc93  jmp     short loc_18003BC30
0x18003bc95  mov     [rbp+3Fh+var_90], 11h
0x18003bc9c  lea     r9, [rbp+3Fh+var_58]
0x18003bca0  xor     edx, edx
0x18003bca2  mov     rax, [rax+228h]
0x18003bca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcae  jmp     loc_18003BC03
0x18003bcb3  test    r14d, r14d
0x18003bcb6  js      loc_18003BDE0
0x18003bcbc  mov     rax, [rbp+3Fh+arg_18]
0x18003bcc0  mov     [rax], esi
0x18003bcc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcc9  lea     rax, WPP_GLOBAL_Control
0x18003bcd0  cmp     rcx, rax
0x18003bcd3  jz      short loc_18003BCDF
0x18003bcd5  test    byte ptr [rcx+1Ch], 1
0x18003bcd9  jnz     loc_18003BE45
0x18003bcdf  test    r15, r15
0x18003bce2  jnz     short loc_18003BD4E
0x18003bce4  xor     eax, eax
0x18003bce6  mov     [rbp+3Fh+var_80], rax
0x18003bcea  mov     [rbp+3Fh+var_78], rax
0x18003bcee  mov     eax, r14d
0x18003bcf1  mov     rbx, [rsp+0C0h+arg_0]
0x18003bcf9  add     rsp, 90h
0x18003bd00  pop     r15
0x18003bd02  pop     r14
0x18003bd04  pop     r13
0x18003bd06  pop     r12
0x18003bd08  pop     rdi
0x18003bd09  pop     rsi
0x18003bd0a  pop     rbp
0x18003bd0b  retn
0x18003bd0c  mov     rbx, [rbx+10h]
0x18003bd10  jmp     loc_18003BACC
0x18003bd15  jnb     loc_18003BAC6
0x18003bd1b  jmp     short loc_18003BD0C
0x18003bd1d  cmp     r14d, 80041006h
0x18003bd24  jz      short loc_18003BD8F
0x18003bd26  lea     r9, [rbp+3Fh+var_80]; struct CMemBuffer *
0x18003bd2a  mov     r8, rbx; struct _GUID *
0x18003bd2d  mov     rdx, r12; struct CWbemObject *
0x18003bd30  mov     rcx, [rbp+3Fh+arg_20]; this
0x18003bd34  call    ?AssignClassId@CWbemClassToIdMap@@QEAAJPEAVCWbemObject@@PEAU_GUID@@PEAVCMemBuffer@@@Z; CWbemClassToIdMap::AssignClassId(CWbemObject *,_GUID *,CMemBuffer *)
0x18003bd39  mov     r14d, eax
0x18003bd3c  mov     ebx, 1
0x18003bd41  mov     rcx, [rbp+3Fh+var_80]
0x18003bd45  mov     [rbp+3Fh+var_50], rcx
0x18003bd49  jmp     loc_18003BB67
0x18003bd4e  cmp     dword ptr [rbp+3Fh+var_78+4], 0
0x18003bd52  jz      short loc_18003BCE4
0x18003bd54  mov     rcx, r15
0x18003bd57  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003bd5d  jmp     short loc_18003BCE4
0x18003bd5f  mov     r9d, 7
0x18003bd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd6a  jmp     loc_18003BC03
0x18003bd6f  jnb     loc_18003BB00
0x18003bd75  mov     r14d, 80041001h
0x18003bd7b  mov     rbx, [rbp+3Fh+var_88]
0x18003bd7f  jmp     loc_18003BB0B
0x18003bd84  mov     r14d, 80041006h
0x18003bd8a  jmp     loc_18003BB18
  ... truncated ...
```
