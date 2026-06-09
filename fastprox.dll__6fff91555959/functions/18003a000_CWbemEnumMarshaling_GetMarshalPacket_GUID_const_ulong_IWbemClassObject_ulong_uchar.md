# CWbemEnumMarshaling::GetMarshalPacket(_GUID const &,ulong,IWbemClassObject * *,ulong *,uchar * *)

- ea: `0x18003a000`
- end: `0x18003a4af`
- name: `?GetMarshalPacket@CWbemEnumMarshaling@@QEAAJAEBU_GUID@@KPEAPEAUIWbemClassObject@@PEAKPEAPEAE@Z`
- size: `1199`
- prototype: `__int64 __fastcall(CWbemEnumMarshaling *this, const struct _GUID *, unsigned int, struct IWbemClassObject **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039ff0`

## callees

- `0x180035b08`
- `0x180037120`
- `0x18003a000`
- `0x18003a4c0`
- `0x18003a690`
- `0x18003b8f0`
- `0x18006fa4c`
- `0x180091966`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a26a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003a26a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a3b9`
- `wbemcomn!GetMemLogObject` at `0x18003a34a`
- `wbemcomn!GetMemLogObject` at `0x18003a3eb`
- `wbemcomn!GetMemLogObject` at `0x18003a44c`
- `wbemcomn!GetMemLogObject` at `0x18003a34a`
- `wbemcomn!GetMemLogObject` at `0x18003a3eb`
- `wbemcomn!GetMemLogObject` at `0x18003a44c`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003a121`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003a310`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003a121`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003a310`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003a033`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003a066`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003a033`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003a066`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a355`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a3f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a457`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a355`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a3f9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a457`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003a465`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003a473`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003a465`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003a473`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a17b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a191`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a17b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003a191`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemEnumMarshaling::GetMarshalPacket(
        CWbemEnumMarshaling *this,
        const struct _GUID *a2,
        unsigned int a3,
        struct IWbemClassObject **a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  unsigned __int64 v6; // r13
  __int64 *v9; // rdi
  __int64 *v10; // rsi
  __int64 *v11; // rsi
  int v12; // ebx
  unsigned int v13; // r12d
  struct _GUID *v14; // r15
  int *v15; // rax
  int *v16; // r14
  char *v17; // rax
  char *v18; // rsi
  char *v19; // rax
  __int64 result; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v24; // rax
  unsigned int v25[2]; // [rsp+48h] [rbp-E0h] BYREF
  int v26; // [rsp+50h] [rbp-D8h]
  unsigned int v27; // [rsp+54h] [rbp-D4h]
  int pExceptionObject; // [rsp+58h] [rbp-D0h] BYREF
  struct CWbemClassToIdMap *v29; // [rsp+60h] [rbp-C8h] BYREF
  __int64 *v30; // [rsp+68h] [rbp-C0h]
  char *v31; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int v32; // [rsp+78h] [rbp-B0h]
  char *v33; // [rsp+80h] [rbp-A8h]
  __int64 *v34; // [rsp+88h] [rbp-A0h]
  char v35[8]; // [rsp+90h] [rbp-98h] BYREF
  char v36[8]; // [rsp+98h] [rbp-90h] BYREF
  __int128 Buf2; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-78h] BYREF
  int v39; // [rsp+B8h] [rbp-70h]
  __int64 *v40; // [rsp+C0h] [rbp-68h]
  __int64 *v41; // [rsp+C8h] [rbp-60h]
  __int64 *v42; // [rsp+D0h] [rbp-58h]
  struct _GUID *v43; // [rsp+D8h] [rbp-50h]
  __int64 v44; // [rsp+E0h] [rbp-48h]
  int *v45; // [rsp+E8h] [rbp-40h]
  __int64 v46; // [rsp+F0h] [rbp-38h]

  v6 = a3;
  try
  {
    CInCritSec::CInCritSec((CInCritSec *)v36, (struct _RTL_CRITICAL_SECTION *)((char *)this + 88));
    v29 = 0;
    Buf2 = (__int128)*a2;
    v12 = 0;
    v26 = 0;
    *(_QWORD *)v25 = 0;
    CInCritSec::CInCritSec((CInCritSec *)v35, (struct _RTL_CRITICAL_SECTION *)((char *)this + 32));
    v9 = (__int64 *)*((_QWORD *)this + 9);
    v10 = (__int64 *)v9[1];
    v30 = v10;
    v34 = v9;
    while ( !*((_BYTE *)v10 + 25) )
    {
      if ( memcmp_0(v10 + 4, &Buf2, 0x10u) < 0 )
      {
        v10 = (__int64 *)v10[2];
      }
      else
      {
        v9 = v10;
        v34 = v10;
        v10 = (__int64 *)*v10;
      }
      v30 = v10;
    }
    *(_QWORD *)v25 = v9;
    v11 = (__int64 *)*((_QWORD *)this + 9);
    *(_QWORD *)v25 = v11;
    if ( v9 == v11 || memcmp_0(&Buf2, v9 + 4, 0x10u) < 0 )
    {
      v41 = v11;
      v9 = v11;
    }
    else
    {
      v40 = v9;
    }
    *(_QWORD *)v25 = v9;
    v42 = v11;
    if ( v9 == v11 )
    {
      v12 = -2147217407;
      v26 = -2147217407;
    }
    else
    {
      v29 = (struct CWbemClassToIdMap *)v9[6];
    }
    CInCritSec::~CInCritSec((CInCritSec *)v35);
    if ( v12 < 0 )
    {
      v12 = CWbemGuidToClassMap::AddMap((CWbemEnumMarshaling *)((char *)this + 32), (struct CGUID *)&Buf2, &v29);
      if ( v12 < 0 )
        goto LABEL_34;
    }
    if ( (_DWORD)v6 )
    {
      v13 = 0;
      v27 = 0;
      v14 = (struct _GUID *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v6, 0x10u));
      v15 = (int *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v6, 4u));
      v16 = v15;
      v33 = 0;
      v31 = 0;
      v32 = 0;
      v43 = v14;
      v44 = 0;
      v45 = v15;
      v46 = 0;
      if ( !v14 )
        goto LABEL_35;
      if ( v15 )
      {
        v25[0] = 0;
        v38 = 0;
        v39 = 0;
        v12 = CWbemObjectArrayPacket::CalculateLength(
                (CWbemObjectArrayPacket *)&v38,
                v6,
                a4,
                v25,
                (struct _RTL_CRITICAL_SECTION *)v29,
                v14,
                v15);
        if ( v12 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v12);
        }
        else
        {
          v13 = v25[0] + 34;
          v27 = v25[0] + 34;
        }
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids,
            (unsigned int)v12);
        }
      }
      else
      {
LABEL_35:
        v12 = -2147217402;
      }
      if ( v12 >= 0 )
      {
        v17 = (char *)CoTaskMemAlloc(v13);
        v18 = v17;
        if ( v17 )
        {
          v19 = v17 + 26;
          if ( v19 <= v18 )
          {
            v22 = GetMemLogObject();
            CMemoryLog::Write(v22, -2);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids,
                "SafeIntException(ERROR_INVALID_PARAMETER)");
            }
            pExceptionObject = 87;
            throw (SafeIntException *)&pExceptionObject;
          }
          v33 = v19;
          v31 = v18;
          v32 = v13;
          v12 = CWbemSmartEnumNextPacket::MarshalPacket((CWbemSmartEnumNextPacket *)&v31, v6, a4, v14, v16);
          if ( v12 < 0 )
          {
            CoTaskMemFree(v18);
          }
          else
          {
            *a5 = v13;
            *a6 = (unsigned __int8 *)v18;
          }
        }
        else
        {
          v12 = -2147217402;
        }
      }
      if ( v16 )
        CWin32DefaultArena::WbemMemFree(v16);
      if ( v14 )
        CWin32DefaultArena::WbemMemFree(v14);
    }
    else
    {
      *a5 = 0;
      *a6 = 0;
    }
    if ( v12 < 0 )
    {
LABEL_34:
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, v12);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_a1e93598a87c305fa984e7f84ff5bb03_Traceguids,
        (unsigned int)v12);
    }
    CInCritSec::~CInCritSec((CInCritSec *)v36);
    result = (unsigned int)v12;
  }
  catch ( CX_MemoryException )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a1e93598a87c305fa984e7f84ff5bb03_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  CInCritSec::CInCritSec((CInCritSec *)v36, (struct _RTL_CRITICAL_SECTION *)((char *)this + 88));
}

```

## disassembly

```asm
0x18003a000  mov     rax, rsp
0x18003a003  mov     [rax+8], rbx
0x18003a007  mov     [rax+10h], rsi
0x18003a00b  mov     [rax+20h], r9
0x18003a00f  push    rdi
0x18003a010  push    r12
0x18003a012  push    r13
0x18003a014  push    r14
0x18003a016  push    r15
0x18003a018  sub     rsp, 100h
0x18003a01f  mov     r13d, r8d
0x18003a022  mov     rbx, rdx
0x18003a025  mov     r14, rcx
0x18003a028  lea     rdx, [rcx+58h]
0x18003a02c  lea     rcx, [rax-90h]
0x18003a033  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003a039  nop
0x18003a03a  xor     r15d, r15d
0x18003a03d  mov     [rsp+128h+var_C8], r15
0x18003a042  movups  xmm0, xmmword ptr [rbx]
0x18003a045  movdqu  [rsp+128h+Buf2], xmm0
0x18003a04e  mov     ebx, r15d
0x18003a051  mov     [rsp+128h+var_D8], ebx
0x18003a055  mov     qword ptr [rsp+128h+var_E0], r15
0x18003a05a  lea     rdx, [r14+20h]
0x18003a05e  lea     rcx, [rsp+128h+var_98]
0x18003a066  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003a06c  nop
0x18003a06d  mov     rdi, [r14+48h]
0x18003a071  mov     rsi, [rdi+8]
0x18003a075  mov     [rsp+128h+var_C0], rsi
0x18003a07a  mov     [rsp+128h+var_A0], rdi
0x18003a082  cmp     [rsi+19h], r15b
0x18003a086  jnz     short loc_18003A0BC
0x18003a088  lea     rcx, [rsi+20h]; Buf1
0x18003a08c  mov     r8d, 10h; Size
0x18003a092  lea     rdx, [rsp+128h+Buf2]; Buf2
0x18003a09a  call    memcmp_0
0x18003a09f  test    eax, eax
0x18003a0a1  js      loc_18003A39F
0x18003a0a7  mov     rdi, rsi
0x18003a0aa  mov     [rsp+128h+var_A0], rsi
0x18003a0b2  mov     rsi, [rsi]
0x18003a0b5  mov     [rsp+128h+var_C0], rsi
0x18003a0ba  jmp     short loc_18003A082
0x18003a0bc  mov     qword ptr [rsp+128h+var_E0], rdi
0x18003a0c1  mov     rsi, [r14+48h]
0x18003a0c5  mov     qword ptr [rsp+128h+var_E0], rsi
0x18003a0ca  cmp     rdi, rsi
0x18003a0cd  jz      loc_18003A36E
0x18003a0d3  lea     rdx, [rdi+20h]; Buf2
0x18003a0d7  mov     r8d, 10h; Size
0x18003a0dd  lea     rcx, [rsp+128h+Buf2]; Buf1
0x18003a0e5  call    memcmp_0
0x18003a0ea  test    eax, eax
0x18003a0ec  js      loc_18003A36E
0x18003a0f2  mov     [rsp+128h+var_68], rdi
0x18003a0fa  mov     qword ptr [rsp+128h+var_E0], rdi
0x18003a0ff  mov     [rsp+128h+var_58], rsi
0x18003a107  cmp     rdi, rsi
0x18003a10a  jz      loc_18003A335
0x18003a110  mov     rax, [rdi+30h]
0x18003a114  mov     [rsp+128h+var_C8], rax
0x18003a119  lea     rcx, [rsp+128h+var_98]
0x18003a121  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003a127  mov     [rsp+128h+var_E8], ebx
0x18003a12b  xor     esi, esi
0x18003a12d  test    ebx, ebx
0x18003a12f  jns     short loc_18003A155
0x18003a131  lea     r8, [rsp+128h+var_C8]; struct CWbemClassToIdMap **
0x18003a136  lea     rdx, [rsp+128h+Buf2]; struct CGUID *
0x18003a13e  lea     rcx, [r14+20h]; this
0x18003a142  call    ?AddMap@CWbemGuidToClassMap@@QEAAJAEAVCGUID@@PEAPEAVCWbemClassToIdMap@@@Z; CWbemGuidToClassMap::AddMap(CGUID &,CWbemClassToIdMap * *)
0x18003a147  mov     ebx, eax
0x18003a149  mov     [rsp+128h+var_E8], eax
0x18003a14d  test    eax, eax
0x18003a14f  js      loc_18003A343
0x18003a155  test    r13d, r13d
0x18003a158  jz      loc_18003A37E
0x18003a15e  mov     r12d, esi
0x18003a161  mov     [rsp+128h+var_D4], esi
0x18003a165  mov     eax, 10h
0x18003a16a  mul     r13
0x18003a16d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18003a174  cmovb   rax, rdi
0x18003a178  mov     rcx, rax
0x18003a17b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003a181  mov     r15, rax
0x18003a184  lea     eax, [rdi+5]
0x18003a187  mul     r13
0x18003a18a  cmovb   rax, rdi
0x18003a18e  mov     rcx, rax
0x18003a191  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003a197  mov     r14, rax
0x18003a19a  mov     [rsp+128h+var_B8], rsi
0x18003a19f  mov     [rsp+128h+var_B0], esi
0x18003a1a3  mov     [rsp+128h+var_A8], rsi
0x18003a1ab  mov     [rsp+128h+var_B8], rsi
0x18003a1b0  mov     [rsp+128h+var_B0], esi
0x18003a1b4  mov     [rsp+128h+var_50], r15
0x18003a1bc  mov     [rsp+128h+var_48], rsi
0x18003a1c4  mov     [rsp+128h+var_40], rax
0x18003a1cc  mov     [rsp+128h+var_38], rsi
0x18003a1d4  test    r15, r15
0x18003a1d7  jz      loc_18003A35D
0x18003a1dd  test    rax, rax
0x18003a1e0  jz      loc_18003A35D
0x18003a1e6  mov     rax, [rsp+128h+var_C8]
0x18003a1eb  mov     [rsp+128h+var_E0], esi
0x18003a1ef  mov     [rsp+128h+var_78], rsi
0x18003a1f7  mov     [rsp+128h+var_70], esi
0x18003a1fe  mov     [rsp+128h+var_F8], r14; int *
0x18003a203  mov     [rsp+128h+var_100], r15; struct _GUID *
0x18003a208  mov     [rsp+128h+var_108], rax; struct CWbemClassToIdMap *
0x18003a20d  lea     r9, [rsp+128h+var_E0]; unsigned int *
0x18003a212  mov     r8, [rsp+128h+arg_18]; struct IWbemClassObject **
0x18003a21a  mov     edx, r13d; int
0x18003a21d  lea     rcx, [rsp+128h+var_78]; this
0x18003a225  call    ?CalculateLength@CWbemObjectArrayPacket@@QEAAJJPEAPEAUIWbemClassObject@@PEAKAEAVCWbemClassToIdMap@@PEAU_GUID@@PEAH@Z; CWbemObjectArrayPacket::CalculateLength(long,IWbemClassObject * *,ulong *,CWbemClassToIdMap &,_GUID *,int *)
0x18003a22a  mov     ebx, eax
0x18003a22c  test    eax, eax
0x18003a22e  js      loc_18003A44C
0x18003a234  mov     r12d, [rsp+128h+var_E0]
0x18003a239  add     r12d, 22h ; '"'
0x18003a23d  mov     [rsp+128h+var_D4], r12d
0x18003a242  lea     rdi, WPP_GLOBAL_Control
0x18003a249  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a250  cmp     rcx, rdi
0x18003a253  jz      short loc_18003A25F
0x18003a255  test    byte ptr [rcx+1Ch], 1
0x18003a259  jnz     loc_18003A3C4
0x18003a25f  mov     [rsp+128h+var_E8], ebx
0x18003a263  test    ebx, ebx
0x18003a265  js      short loc_18003A2DC
0x18003a267  mov     ecx, r12d; cb
0x18003a26a  call    cs:__imp_CoTaskMemAlloc
0x18003a270  mov     rsi, rax
0x18003a273  test    rax, rax
0x18003a276  jz      loc_18003A3A8
0x18003a27c  add     rax, 1Ah
0x18003a280  cmp     rax, rsi
0x18003a283  jbe     loc_18003A3EB
0x18003a289  mov     [rsp+128h+var_A8], rax
0x18003a291  mov     [rsp+128h+var_B8], rsi
0x18003a296  mov     [rsp+128h+var_B0], r12d
0x18003a29b  mov     [rsp+128h+var_108], r14; int *
0x18003a2a0  mov     r9, r15; struct _GUID *
0x18003a2a3  mov     r8, [rsp+128h+arg_18]; struct IWbemClassObject **
0x18003a2ab  mov     edx, r13d; int
0x18003a2ae  lea     rcx, [rsp+128h+var_B8]; this
0x18003a2b3  call    ?MarshalPacket@CWbemSmartEnumNextPacket@@QEAAJJPEAPEAUIWbemClassObject@@PEAU_GUID@@PEAH@Z; CWbemSmartEnumNextPacket::MarshalPacket(long,IWbemClassObject * *,_GUID *,int *)
0x18003a2b8  mov     ebx, eax
0x18003a2ba  mov     [rsp+128h+var_E8], eax
0x18003a2be  test    eax, eax
0x18003a2c0  js      loc_18003A3B6
0x18003a2c6  mov     rax, [rsp+128h+arg_20]
0x18003a2ce  mov     [rax], r12d
0x18003a2d1  mov     rax, [rsp+128h+arg_28]
0x18003a2d9  mov     [rax], rsi
0x18003a2dc  test    r14, r14
0x18003a2df  jnz     loc_18003A462
0x18003a2e5  test    r15, r15
0x18003a2e8  jnz     loc_18003A470
0x18003a2ee  test    ebx, ebx
0x18003a2f0  js      short loc_18003A34A
0x18003a2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a2f9  cmp     rcx, rdi
0x18003a2fc  jz      short loc_18003A308
0x18003a2fe  test    byte ptr [rcx+1Ch], 1
0x18003a302  jnz     loc_18003A47E
0x18003a308  lea     rcx, [rsp+128h+var_90]
0x18003a310  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003a316  mov     eax, ebx
0x18003a318  lea     r11, [rsp+128h+var_28]
0x18003a320  mov     rbx, [r11+30h]
0x18003a324  mov     rsi, [r11+38h]
0x18003a328  mov     rsp, r11
0x18003a32b  pop     r15
0x18003a32d  pop     r14
0x18003a32f  pop     r13
0x18003a331  pop     r12
0x18003a333  pop     rdi
0x18003a334  retn
0x18003a335  mov     ebx, 80041001h
0x18003a33a  mov     [rsp+128h+var_D8], ebx
0x18003a33e  jmp     loc_18003A119
0x18003a343  lea     rdi, WPP_GLOBAL_Control
0x18003a34a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a350  mov     edx, ebx
0x18003a352  mov     rcx, rax
0x18003a355  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a35b  jmp     short loc_18003A2F2
0x18003a35d  mov     ebx, 80041006h
0x18003a362  lea     rdi, WPP_GLOBAL_Control
0x18003a369  jmp     loc_18003A25F
0x18003a36e  mov     [rsp+128h+var_60], rsi
0x18003a376  mov     rdi, rsi
0x18003a379  jmp     loc_18003A0FA
0x18003a37e  mov     rax, [rsp+128h+arg_20]
0x18003a386  mov     [rax], esi
0x18003a388  mov     rax, [rsp+128h+arg_28]
0x18003a390  mov     [rax], rsi
0x18003a393  lea     rdi, WPP_GLOBAL_Control
0x18003a39a  jmp     loc_18003A2EE
0x18003a39f  mov     rsi, [rsi+10h]
0x18003a3a3  jmp     loc_18003A0B5
0x18003a3a8  mov     ebx, 80041006h
0x18003a3ad  mov     [rsp+128h+var_E8], ebx
0x18003a3b1  jmp     loc_18003A2DC
0x18003a3b6  mov     rcx, rsi; pv
0x18003a3b9  call    cs:__imp_CoTaskMemFree
0x18003a3bf  jmp     loc_18003A2DC
0x18003a3c4  cmp     byte ptr [rcx+19h], 2
0x18003a3c8  jb      loc_18003A25F
0x18003a3ce  mov     edx, 0Ah
0x18003a3d3  mov     r9d, ebx
0x18003a3d6  lea     r8, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids
0x18003a3dd  mov     rcx, [rcx+10h]
0x18003a3e1  call    WPP_SF_d
0x18003a3e6  jmp     loc_18003A25F
0x18003a3eb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a3f1  mov     edx, 0FFFFFFFEh
0x18003a3f6  mov     rcx, rax
0x18003a3f9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a406  cmp     rcx, rdi
0x18003a409  jz      short loc_18003A433
0x18003a40b  test    byte ptr [rcx+1Ch], 1
0x18003a40f  jz      short loc_18003A433
0x18003a411  cmp     byte ptr [rcx+19h], 2
0x18003a415  jb      short loc_18003A433
0x18003a417  mov     edx, 11h
0x18003a41c  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18003a423  lea     r8, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids
0x18003a42a  mov     rcx, [rcx+10h]
0x18003a42e  call    WPP_SF_s
0x18003a433  mov     [rsp+128h+pExceptionObject], 57h ; 'W'
0x18003a43b  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18003a442  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18003a447  call    _CxxThrowException_0
0x18003a44c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a452  mov     edx, ebx
0x18003a454  mov     rcx, rax
0x18003a457  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a45d  jmp     loc_18003A242
0x18003a462  mov     rcx, r14
0x18003a465  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003a46b  jmp     loc_18003A2E5
0x18003a470  mov     rcx, r15
0x18003a473  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003a479  jmp     loc_18003A2EE
0x18003a47e  cmp     byte ptr [rcx+19h], 2
0x18003a482  jb      loc_18003A308
0x18003a488  mov     edx, 0Ah
0x18003a48d  mov     r9d, ebx
0x18003a490  lea     r8, WPP_a1e93598a87c305fa984e7f84ff5bb03_Traceguids
0x18003a497  mov     rcx, [rcx+10h]
0x18003a49b  call    WPP_SF_d
0x18003a4a0  jmp     loc_18003A308
0x18003a4a5  mov     eax, 80041006h
0x18003a4aa  jmp     loc_18003A318
```
