# CUniversalRefresher::CRemote::CRemote(IWbemRemoteRefresher *,_COAUTHINFO *,_GUID const *,ushort const *,ushort const *,CUniversalRefresher *)

- ea: `0x1800860e4`
- end: `0x1800863d6`
- name: `??0CRemote@CUniversalRefresher@@QEAA@PEAUIWbemRemoteRefresher@@PEAU_COAUTHINFO@@PEBU_GUID@@PEBG3PEAV1@@Z`
- size: `754`
- prototype: `CUniversalRefresher::CRemote *__fastcall(CUniversalRefresher::CRemote *this, struct IWbemRemoteRefresher *, struct _COAUTHINFO *, const struct _GUID *, OLECHAR *psz, OLECHAR *, SIZE_T cb)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180088674`

## callees

- `0x180017860`
- `0x180028604`
- `0x180035b08`
- `0x18004f9a0`
- `0x18006fa4c`
- `0x1800860e4`
- `0x180086410`
- `0x180086450`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800861f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800861f2`
- `wbemcomn!GetMemLogObject` at `0x180086200`
- `wbemcomn!GetMemLogObject` at `0x18008628f`
- `wbemcomn!GetMemLogObject` at `0x18008630c`
- `wbemcomn!GetMemLogObject` at `0x180086200`
- `wbemcomn!GetMemLogObject` at `0x18008628f`
- `wbemcomn!GetMemLogObject` at `0x18008630c`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18008615d`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18008615d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008620c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008629b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008631a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008620c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008629b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008631a`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18008612f`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x180086144`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18008612f`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x180086144`
- `OLEAUT32!__imp_SysAllocString` at `0x180086281`
- `OLEAUT32!__imp_SysAllocString` at `0x180086301`
- `OLEAUT32!__imp_SysAllocString` at `0x180086281`
- `OLEAUT32!__imp_SysAllocString` at `0x180086301`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CUniversalRefresher::CRemote *__fastcall CUniversalRefresher::CRemote::CRemote(
        CUniversalRefresher::CRemote *this,
        struct IWbemRemoteRefresher *a2,
        struct _COAUTHINFO *a3,
        const struct _GUID *a4,
        OLECHAR *psz,
        OLECHAR *a6,
        SIZE_T cb)
{
  unsigned __int16 *v10; // rsi
  LPWSTR pwszServerPrincName; // rax
  __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  CMemoryLog *MemLogObject; // rax
  BSTR v15; // rbx
  CMemoryLog *v16; // rax
  BSTR v17; // rax
  CMemoryLog *v18; // rax
  BSTR v20; // [rsp+20h] [rbp-30h] BYREF
  char v21; // [rsp+28h] [rbp-28h]
  BSTR v22; // [rsp+30h] [rbp-20h] BYREF
  char v23; // [rsp+38h] [rbp-18h]
  unsigned __int16 *v24; // [rsp+40h] [rbp-10h] BYREF
  char v25; // [rsp+48h] [rbp-8h]

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 1;
  CFlexArray::CFlexArray((CUniversalRefresher::CRemote *)((char *)this + 88), 8, 100);
  CFlexArray::CFlexArray((CUniversalRefresher::CRemote *)((char *)this + 184), 8, 100);
  *((_QWORD *)this + 34) = cb;
  CCritSec::CCritSec((CUniversalRefresher::CRemote *)((char *)this + 280));
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 88) = 1;
  *((_OWORD *)this + 21) = 0;
  *(struct _GUID *)((char *)this + 8) = *a4;
  *(struct _COAUTHINFO *)((char *)this + 24) = *a3;
  v10 = 0;
  pwszServerPrincName = a3->pwszServerPrincName;
  if ( pwszServerPrincName )
  {
    v12 = -1;
    do
      ++v12;
    while ( pwszServerPrincName[v12] );
    if ( (_DWORD)v12 )
    {
      LODWORD(cb) = v12;
      SafeInt<unsigned long>::operator+=<int>(&cb, 1);
      SafeInt<unsigned long>::operator*=<unsigned __int64>(&cb, 2);
      v13 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
      v10 = v13;
      if ( !v13 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            133,
            WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
            "CX_MemoryException()");
        }
        throw (CX_MemoryException *)&cb;
      }
      StringCchCopyW(v13, (unsigned int)(v12 + 1), a3->pwszServerPrincName);
    }
  }
  v24 = v10;
  v25 = 0;
  v15 = 0;
  if ( psz )
  {
    v15 = SysAllocString(psz);
    if ( !v15 )
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&cb;
    }
  }
  v22 = v15;
  v23 = 0;
  v17 = 0;
  if ( a6 )
  {
    v17 = SysAllocString(a6);
    if ( !v17 )
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&cb;
    }
  }
  v20 = v17;
  v25 = 1;
  *((_QWORD *)this + 4) = v10;
  v23 = 1;
  *((_QWORD *)this + 8) = v15;
  v21 = 1;
  *((_QWORD *)this + 9) = v17;
  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
  OnDeleteIf<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *)>::~OnDeleteIf<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *)>(&v20);
  OnDeleteIf<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *)>::~OnDeleteIf<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *)>(&v22);
  OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>(&v24);
  return this;
}

```

## disassembly

```asm
0x1800860e4  mov     [rsp-28h+arg_10], rbx
0x1800860e9  mov     [rsp-28h+arg_0], rcx
0x1800860ee  push    rbp
0x1800860ef  push    rsi
0x1800860f0  push    rdi
0x1800860f1  push    r12
0x1800860f3  push    r14
0x1800860f5  mov     rbp, rsp
0x1800860f8  sub     rsp, 50h
0x1800860fc  mov     rbx, r9
0x1800860ff  mov     r14, r8
0x180086102  mov     rdi, rcx
0x180086105  mov     [rcx], rdx
0x180086108  xor     r12d, r12d
0x18008610b  mov     [rcx+40h], r12
0x18008610f  mov     [rcx+48h], r12
0x180086113  mov     qword ptr [rcx+50h], 1
0x18008611b  add     rcx, 58h ; 'X'
0x18008611f  mov     [rbp+arg_8], rcx
0x180086123  lea     esi, [r12+8]
0x180086128  lea     r8d, [r12+64h]
0x18008612d  mov     edx, esi
0x18008612f  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x180086135  nop
0x180086136  lea     rcx, [rdi+0B8h]
0x18008613d  lea     r8d, [r12+64h]
0x180086142  mov     edx, esi
0x180086144  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18008614a  nop
0x18008614b  mov     rax, [rbp+cb]
0x18008614f  mov     [rdi+110h], rax
0x180086156  lea     rcx, [rdi+118h]
0x18008615d  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x180086163  nop
0x180086164  mov     [rdi+140h], r12
0x18008616b  mov     [rdi+148h], r12
0x180086172  mov     dword ptr [rdi+160h], 1
0x18008617c  xorps   xmm0, xmm0
0x18008617f  movups  xmmword ptr [rdi+150h], xmm0
0x180086186  movups  xmm1, xmmword ptr [rbx]
0x180086189  movdqu  xmmword ptr [rdi+8], xmm1
0x18008618e  movups  xmm0, xmmword ptr [r14]
0x180086192  movups  xmmword ptr [rdi+18h], xmm0
0x180086196  movups  xmm1, xmmword ptr [r14+10h]
0x18008619b  movups  xmmword ptr [rdi+28h], xmm1
0x18008619f  movsd   xmm0, qword ptr [r14+20h]
0x1800861a5  movsd   qword ptr [rdi+38h], xmm0
0x1800861aa  mov     esi, r12d
0x1800861ad  mov     rax, [r14+8]
0x1800861b1  test    rax, rax
0x1800861b4  jz      loc_18008626D
0x1800861ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800861be  inc     rbx
0x1800861c1  cmp     [rax+rbx*2], r12w
0x1800861c6  jnz     short loc_1800861BE
0x1800861c8  test    ebx, ebx
0x1800861ca  jz      loc_18008626D
0x1800861d0  mov     dword ptr [rbp+cb], ebx
0x1800861d3  mov     edx, 1
0x1800861d8  lea     rcx, [rbp+cb]
0x1800861dc  call    ??$?YH@?$SafeInt@K@@QEAAAEAV0@H@Z; SafeInt<ulong>::operator+=<int>(int)
0x1800861e1  mov     edx, 2
0x1800861e6  lea     rcx, [rbp+cb]
0x1800861ea  call    ??$?X_K@?$SafeInt@K@@QEAAAEAV0@_K@Z; SafeInt<ulong>::operator*=<unsigned __int64>(unsigned __int64)
0x1800861ef  mov     ecx, dword ptr [rbp+cb]; cb
0x1800861f2  call    cs:__imp_CoTaskMemAlloc
0x1800861f8  mov     rsi, rax
0x1800861fb  test    rax, rax
0x1800861fe  jnz     short loc_18008625E
0x180086200  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180086206  lea     edx, [rsi-2]
0x180086209  mov     rcx, rax
0x18008620c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180086212  lea     rax, WPP_GLOBAL_Control
0x180086219  mov     rcx, cs:WPP_GLOBAL_Control
0x180086220  cmp     rcx, rax
0x180086223  jz      short loc_18008624D
0x180086225  test    byte ptr [rcx+1Ch], 1
0x180086229  jz      short loc_18008624D
0x18008622b  cmp     byte ptr [rcx+19h], 2
0x18008622f  jb      short loc_18008624D
0x180086231  mov     edx, 85h
0x180086236  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18008623d  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180086244  mov     rcx, [rcx+10h]
0x180086248  call    WPP_SF_s
0x18008624d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180086254  lea     rcx, [rbp+cb]; pExceptionObject
0x180086258  call    _CxxThrowException_0
0x18008625e  lea     edx, [rbx+1]; unsigned __int64
0x180086261  mov     r8, [r14+8]; unsigned __int16 *
0x180086265  mov     rcx, rax; unsigned __int16 *
0x180086268  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008626d  mov     [rbp+var_10], rsi
0x180086271  mov     [rbp+var_8], r12b
0x180086275  mov     rbx, r12
0x180086278  mov     rcx, [rbp+psz]; psz
0x18008627c  test    rcx, rcx
0x18008627f  jz      short loc_1800862ED
0x180086281  call    cs:__imp_SysAllocString
0x180086287  mov     rbx, rax
0x18008628a  test    rax, rax
0x18008628d  jnz     short loc_1800862ED
0x18008628f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180086295  lea     edx, [rbx-2]
0x180086298  mov     rcx, rax
0x18008629b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800862a1  lea     rax, WPP_GLOBAL_Control
0x1800862a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800862af  cmp     rcx, rax
0x1800862b2  jz      short loc_1800862DC
0x1800862b4  test    byte ptr [rcx+1Ch], 1
0x1800862b8  jz      short loc_1800862DC
0x1800862ba  cmp     byte ptr [rcx+19h], 2
0x1800862be  jb      short loc_1800862DC
0x1800862c0  mov     edx, 86h
0x1800862c5  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800862cc  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800862d3  mov     rcx, [rcx+10h]
0x1800862d7  call    WPP_SF_s
0x1800862dc  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800862e3  lea     rcx, [rbp+cb]; pExceptionObject
0x1800862e7  call    _CxxThrowException_0
0x1800862ed  mov     [rbp+var_20], rbx
0x1800862f1  mov     [rbp+var_18], r12b
0x1800862f5  mov     rax, r12
0x1800862f8  mov     rcx, [rbp+arg_28]; psz
0x1800862fc  test    rcx, rcx
0x1800862ff  jz      short loc_18008636C
0x180086301  call    cs:__imp_SysAllocString
0x180086307  test    rax, rax
0x18008630a  jnz     short loc_18008636C
0x18008630c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180086312  mov     edx, 0FFFFFFFEh
0x180086317  mov     rcx, rax
0x18008631a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180086320  lea     rax, WPP_GLOBAL_Control
0x180086327  mov     rcx, cs:WPP_GLOBAL_Control
0x18008632e  cmp     rcx, rax
0x180086331  jz      short loc_18008635B
0x180086333  test    byte ptr [rcx+1Ch], 1
0x180086337  jz      short loc_18008635B
0x180086339  cmp     byte ptr [rcx+19h], 2
0x18008633d  jb      short loc_18008635B
0x18008633f  mov     edx, 87h
0x180086344  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18008634b  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180086352  mov     rcx, [rcx+10h]
0x180086356  call    WPP_SF_s
0x18008635b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180086362  lea     rcx, [rbp+cb]; pExceptionObject
0x180086366  call    _CxxThrowException_0
0x18008636c  mov     [rbp+var_30], rax
0x180086370  mov     [rbp+var_28], r12b
0x180086374  mov     [rbp+var_8], 1
0x180086378  mov     [rdi+20h], rsi
0x18008637c  mov     [rbp+var_18], 1
0x180086380  mov     [rdi+40h], rbx
0x180086384  mov     [rbp+var_28], 1
0x180086388  mov     [rdi+48h], rax
0x18008638c  mov     rcx, [rdi]
0x18008638f  test    rcx, rcx
0x180086392  jz      short loc_1800863A1
0x180086394  mov     rax, [rcx]
0x180086397  mov     rax, [rax+8]
0x18008639b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800863a0  nop
0x1800863a1  lea     rcx, [rbp+var_30]
0x1800863a5  call    ??1?$OnDeleteIf@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z@@QEAA@XZ; OnDeleteIf<ushort *,void (*)(ushort *),&SysFreeString(ushort *)>::~OnDeleteIf<ushort *,void (*)(ushort *),&SysFreeString(ushort *)>(void)
0x1800863aa  nop
0x1800863ab  lea     rcx, [rbp+var_20]
0x1800863af  call    ??1?$OnDeleteIf@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z@@QEAA@XZ; OnDeleteIf<ushort *,void (*)(ushort *),&SysFreeString(ushort *)>::~OnDeleteIf<ushort *,void (*)(ushort *),&SysFreeString(ushort *)>(void)
0x1800863b4  nop
0x1800863b5  lea     rcx, [rbp+var_10]
0x1800863b9  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x1800863be  nop
0x1800863bf  mov     rax, rdi
0x1800863c2  mov     rbx, [rsp+50h+arg_10]
0x1800863ca  add     rsp, 50h
0x1800863ce  pop     r14
0x1800863d0  pop     r12
0x1800863d2  pop     rdi
0x1800863d3  pop     rsi
0x1800863d4  pop     rbp
0x1800863d5  retn
```
