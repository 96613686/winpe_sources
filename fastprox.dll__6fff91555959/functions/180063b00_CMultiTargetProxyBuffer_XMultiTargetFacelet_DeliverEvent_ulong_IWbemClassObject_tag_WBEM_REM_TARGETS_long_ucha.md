# CMultiTargetProxyBuffer::XMultiTargetFacelet::DeliverEvent(ulong,IWbemClassObject * *,tag_WBEM_REM_TARGETS *,long,uchar *)

- ea: `0x180063b00`
- end: `0x180063de1`
- name: `?DeliverEvent@XMultiTargetFacelet@CMultiTargetProxyBuffer@@UEAAJKPEAPEAUIWbemClassObject@@PEAUtag_WBEM_REM_TARGETS@@JPEAE@Z`
- size: `737`
- prototype: `int(CMultiTargetProxyBuffer::XMultiTargetFacelet *__hidden this, unsigned int, struct IWbemClassObject **, struct tag_WBEM_REM_TARGETS *, int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180037120`
- `0x18005f8cc`
- `0x180063b00`
- `0x180063de8`
- `0x180082e00`
- `0x180083220`
- `0x180083250`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180063cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063d8c`
- `wbemcomn!GetMemLogObject` at `0x180063dcb`
- `wbemcomn!GetMemLogObject` at `0x180063dcb`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180063dc0`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180063dc0`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180063c18`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180063c18`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180063dd6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180063dd6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180063c40`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180063c5d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180063c40`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180063c5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMultiTargetProxyBuffer::XMultiTargetFacelet::DeliverEvent(
        CMultiTargetProxyBuffer **this,
        unsigned int a2,
        struct IWbemClassObject **a3,
        struct tag_WBEM_REM_TARGETS *a4,
        int a5,
        unsigned __int8 *a6)
{
  unsigned __int64 v8; // r15
  CMultiTargetProxyBuffer *v10; // rcx
  int v11; // ebx
  struct _GUID *v13; // r14
  int *v14; // rax
  int *v15; // r12
  unsigned int v16; // r14d
  struct IWbemClassObject **v17; // rsi
  CMemoryLog *MemLogObject; // rax
  int v20; // [rsp+50h] [rbp-78h]
  int v21; // [rsp+50h] [rbp-78h]
  struct _GUID *v22; // [rsp+58h] [rbp-70h]
  _BYTE v23[8]; // [rsp+60h] [rbp-68h] BYREF
  void *v24[2]; // [rsp+68h] [rbp-60h] BYREF
  void *v25[2]; // [rsp+78h] [rbp-50h] BYREF
  _BYTE v26[64]; // [rsp+88h] [rbp-40h] BYREF
  SIZE_T cb; // [rsp+D0h] [rbp+8h] BYREF
  struct IWbemClassObject **v28; // [rsp+E0h] [rbp+18h]
  struct tag_WBEM_REM_TARGETS *v29; // [rsp+E8h] [rbp+20h]

  v29 = a4;
  v28 = a3;
  v8 = a2;
  CMultiTargetProxyBuffer::InitSmartMultiTarget(this[2], 0, 0xFFFFFFFF, 0, 0, 0, 3u, 0, 0);
  v10 = this[2];
  if ( !*((_DWORD *)v10 + 7) || !*((_QWORD *)v10 + 6) )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWbemClassObject **, struct tag_WBEM_REM_TARGETS *, int, unsigned __int8 *))(**((_QWORD **)v10 + 2) + 24LL))(
            *((_QWORD *)v10 + 2),
            (unsigned int)v8,
            a3,
            a4,
            a5,
            a6);
    goto LABEL_3;
  }
  CInCritSec::CInCritSec((CInCritSec *)v23, (struct _RTL_CRITICAL_SECTION *)((char *)v10 + 56));
  LODWORD(cb) = 0;
  try
  {
    v13 = (struct _GUID *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v8, 0x10u));
    v22 = v13;
    v14 = (int *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v8, 4u));
    v15 = v14;
    v25[0] = v13;
    v25[1] = 0;
    v24[0] = v14;
    v24[1] = 0;
    if ( v13 && v14 )
    {
      CWbemMtgtDeliverEventPacket::CWbemMtgtDeliverEventPacket((CWbemMtgtDeliverEventPacket *)v26, 0, 0, 0);
      v11 = CWbemMtgtDeliverEventPacket::CalculateLength(
              (CWbemMtgtDeliverEventPacket *)v26,
              v8,
              a3,
              (unsigned int *)&cb,
              (struct CWbemClassToIdMap *)(this + 3),
              v13,
              v15);
      if ( v11 < 0 )
      {
LABEL_20:
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v24);
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v25);
        goto LABEL_25;
      }
      v16 = cb;
      v17 = (struct IWbemClassObject **)CoTaskMemAlloc((unsigned int)cb);
      if ( v17 )
      {
        v11 = CWbemMtgtDeliverEventPacket::MarshalPacket(
                (CWbemMtgtDeliverEventPacket *)v26,
                v17,
                (struct _GUID *)v16,
                (int *)(unsigned int)v8,
                v28,
                v22,
                v15);
        if ( v11 >= 0 )
          v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IWbemClassObject **, struct tag_WBEM_REM_TARGETS *, int, unsigned __int8 *))(**((_QWORD **)this[2] + 6) + 24LL))(
                  *((_QWORD *)this[2] + 6),
                  (unsigned int)v8,
                  v16,
                  v17,
                  v29,
                  a5,
                  a6);
        CoTaskMemFree(v17);
        goto LABEL_20;
      }
    }
    v11 = -2147217402;
    goto LABEL_20;
  }
  catch ( CX_MemoryException )
  {
    v20 = -2147217402;
    v11 = v20;
  }
  catch ( SafeIntException )
  {
    v21 = -2147217407;
    v11 = v21;
  }
LABEL_25:
  CInCritSec::~CInCritSec((CInCritSec *)v23);
LABEL_3:
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_33ee673b1d663441998393d79c86ae5d_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180063b00  mov     [rsp+arg_8], rbx
0x180063b05  mov     [rsp+arg_18], r9
0x180063b0a  mov     [rsp+arg_10], r8
0x180063b0f  push    rsi
0x180063b10  push    r12
0x180063b12  push    r13
0x180063b14  push    r14
0x180063b16  push    r15
0x180063b18  sub     rsp, 0A0h
0x180063b1f  mov     rbx, r9
0x180063b22  mov     rsi, r8
0x180063b25  mov     r15d, edx
0x180063b28  mov     r13, rcx
0x180063b2b  mov     [rsp+0C8h+var_88], 0; unsigned int
0x180063b33  mov     [rsp+0C8h+var_90], 0; void *
0x180063b3c  mov     dword ptr [rsp+0C8h+var_98], 3; unsigned int
0x180063b44  mov     dword ptr [rsp+0C8h+var_A0], 0; unsigned int
0x180063b4c  mov     [rsp+0C8h+var_A8], 0; unsigned __int16 *
0x180063b55  xor     r9d, r9d; unsigned int
0x180063b58  or      r8d, 0FFFFFFFFh; unsigned int
0x180063b5c  xor     edx, edx; int
0x180063b5e  mov     rcx, [rcx+10h]; this
0x180063b62  call    ?InitSmartMultiTarget@CMultiTargetProxyBuffer@@IEAAJHKKPEAGKKPEAXK@Z; CMultiTargetProxyBuffer::InitSmartMultiTarget(int,ulong,ulong,ushort *,ulong,ulong,void *,ulong)
0x180063b67  mov     rcx, [r13+10h]
0x180063b6b  cmp     dword ptr [rcx+1Ch], 0
0x180063b6f  jnz     loc_180063C04
0x180063b75  mov     rcx, [rcx+10h]
0x180063b79  mov     rax, [rcx]
0x180063b7c  mov     rdx, [rsp+0C8h+arg_28]
0x180063b84  mov     [rsp+0C8h+var_A0], rdx
0x180063b89  mov     edx, [rsp+0C8h+arg_20]
0x180063b90  mov     dword ptr [rsp+0C8h+var_A8], edx
0x180063b94  mov     r9, rbx
0x180063b97  mov     r8, rsi
0x180063b9a  mov     edx, r15d
0x180063b9d  mov     rax, [rax+18h]
0x180063ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063ba6  mov     ebx, eax
0x180063ba8  test    ebx, ebx
0x180063baa  js      loc_180063DCB
0x180063bb0  lea     rax, WPP_GLOBAL_Control
0x180063bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180063bbe  cmp     rcx, rax
0x180063bc1  jnz     short loc_180063BDE
0x180063bc3  mov     eax, ebx
0x180063bc5  mov     rbx, [rsp+0C8h+arg_8]
0x180063bcd  add     rsp, 0A0h
0x180063bd4  pop     r15
0x180063bd6  pop     r14
0x180063bd8  pop     r13
0x180063bda  pop     r12
0x180063bdc  pop     rsi
0x180063bdd  retn
0x180063bde  test    byte ptr [rcx+1Ch], 1
0x180063be2  jz      short loc_180063BC3
0x180063be4  cmp     byte ptr [rcx+19h], 2
0x180063be8  jb      short loc_180063BC3
0x180063bea  mov     edx, 0Fh
0x180063bef  mov     r9d, ebx
0x180063bf2  lea     r8, WPP_33ee673b1d663441998393d79c86ae5d_Traceguids
0x180063bf9  mov     rcx, [rcx+10h]
0x180063bfd  call    WPP_SF_d
0x180063c02  jmp     short loc_180063BC3
0x180063c04  cmp     qword ptr [rcx+30h], 0
0x180063c09  jz      loc_180063B75
0x180063c0f  lea     rdx, [rcx+38h]
0x180063c13  lea     rcx, [rsp+0C8h+var_68]
0x180063c18  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180063c1e  nop
0x180063c1f  mov     dword ptr [rsp+0C8h+cb], 0
0x180063c2a  mov     eax, 10h
0x180063c2f  mul     r15
0x180063c32  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180063c39  cmovb   rax, r12
0x180063c3d  mov     rcx, rax
0x180063c40  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180063c46  mov     r14, rax
0x180063c49  mov     [rsp+0C8h+var_70], rax
0x180063c4e  lea     eax, [r12+5]
0x180063c53  mul     r15
0x180063c56  cmovb   rax, r12
0x180063c5a  mov     rcx, rax
0x180063c5d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180063c63  mov     r12, rax
0x180063c66  mov     [rsp+0C8h+var_50], r14
0x180063c6b  mov     [rsp+0C8h+var_48], 0
0x180063c77  mov     [rsp+0C8h+var_60], rax
0x180063c7c  mov     [rsp+0C8h+var_58], 0
0x180063c85  test    r14, r14
0x180063c88  jz      loc_180063D94
0x180063c8e  test    rax, rax
0x180063c91  jz      loc_180063D94
0x180063c97  xor     r9d, r9d; bool
0x180063c9a  xor     r8d, r8d; unsigned int
0x180063c9d  xor     edx, edx; unsigned __int8 *
0x180063c9f  lea     rcx, [rsp+0C8h+var_40]; this
0x180063ca7  call    ??0CWbemMtgtDeliverEventPacket@@QEAA@PEAEK_N@Z; CWbemMtgtDeliverEventPacket::CWbemMtgtDeliverEventPacket(uchar *,ulong,bool)
0x180063cac  lea     rax, [r13+18h]
0x180063cb0  mov     [rsp+0C8h+var_98], r12; int *
0x180063cb5  mov     [rsp+0C8h+var_A0], r14; struct _GUID *
0x180063cba  mov     [rsp+0C8h+var_A8], rax; struct CWbemClassToIdMap *
0x180063cbf  lea     r9, [rsp+0C8h+cb]; unsigned int *
0x180063cc7  mov     r8, rsi; struct IWbemClassObject **
0x180063cca  mov     edx, r15d; int
0x180063ccd  lea     rcx, [rsp+0C8h+var_40]; this
0x180063cd5  call    ?CalculateLength@CWbemMtgtDeliverEventPacket@@QEAAJJPEAPEAUIWbemClassObject@@PEAKAEAVCWbemClassToIdMap@@PEAU_GUID@@PEAH@Z; CWbemMtgtDeliverEventPacket::CalculateLength(long,IWbemClassObject * *,ulong *,CWbemClassToIdMap &,_GUID *,int *)
0x180063cda  mov     ebx, eax
0x180063cdc  mov     [rsp+0C8h+var_78], eax
0x180063ce0  test    eax, eax
0x180063ce2  js      loc_180063D9D
0x180063ce8  mov     r14d, dword ptr [rsp+0C8h+cb]
0x180063cf0  mov     ecx, r14d; cb
0x180063cf3  call    cs:__imp_CoTaskMemAlloc
0x180063cf9  mov     rsi, rax
0x180063cfc  test    rax, rax
0x180063cff  jz      loc_180063D94
0x180063d05  mov     [rsp+0C8h+var_98], r12; int *
0x180063d0a  mov     rax, [rsp+0C8h+var_70]
0x180063d0f  mov     [rsp+0C8h+var_A0], rax; struct _GUID *
0x180063d14  mov     rax, [rsp+0C8h+arg_10]
0x180063d1c  mov     [rsp+0C8h+var_A8], rax; struct IWbemClassObject **
0x180063d21  mov     r9d, r15d; int *
0x180063d24  mov     r8d, r14d; struct _GUID *
0x180063d27  mov     rdx, rsi; struct IWbemClassObject **
0x180063d2a  lea     rcx, [rsp+0C8h+var_40]; this
0x180063d32  call    ?MarshalPacket@CWbemMtgtDeliverEventPacket@@QEAAJPEAEKJPEAPEAUIWbemClassObject@@PEAU_GUID@@PEAH@Z; CWbemMtgtDeliverEventPacket::MarshalPacket(uchar *,ulong,long,IWbemClassObject * *,_GUID *,int *)
0x180063d37  mov     ebx, eax
0x180063d39  mov     [rsp+0C8h+var_78], eax
0x180063d3d  test    eax, eax
0x180063d3f  js      short loc_180063D89
0x180063d41  mov     rax, [r13+10h]
0x180063d45  mov     rcx, [rax+30h]
0x180063d49  mov     rax, [rcx]
0x180063d4c  mov     rdx, [rsp+0C8h+arg_28]
0x180063d54  mov     [rsp+0C8h+var_98], rdx
0x180063d59  mov     edx, [rsp+0C8h+arg_20]
0x180063d60  mov     dword ptr [rsp+0C8h+var_A0], edx
0x180063d64  mov     rdx, [rsp+0C8h+arg_18]
0x180063d6c  mov     [rsp+0C8h+var_A8], rdx
0x180063d71  mov     r9, rsi
0x180063d74  mov     r8d, r14d
0x180063d77  mov     edx, r15d
0x180063d7a  mov     rax, [rax+18h]
0x180063d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d83  mov     ebx, eax
0x180063d85  mov     [rsp+0C8h+var_78], eax
0x180063d89  mov     rcx, rsi; pv
0x180063d8c  call    cs:__imp_CoTaskMemFree
0x180063d92  jmp     short loc_180063D9D
0x180063d94  mov     ebx, 80041006h
0x180063d99  mov     [rsp+0C8h+var_78], ebx
0x180063d9d  lea     rcx, [rsp+0C8h+var_60]
0x180063da2  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180063da7  nop
0x180063da8  lea     rcx, [rsp+0C8h+var_50]
0x180063dad  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180063db2  nop
0x180063db3  jmp     short loc_180063DBB
0x180063db5  jmp     short $+2
0x180063db7  mov     ebx, [rsp+0C8h+var_78]
0x180063dbb  lea     rcx, [rsp+0C8h+var_68]
0x180063dc0  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180063dc6  jmp     loc_180063BA8
0x180063dcb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180063dd1  mov     edx, ebx
0x180063dd3  mov     rcx, rax
0x180063dd6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180063ddc  jmp     loc_180063BB0
```
