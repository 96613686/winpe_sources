# CWbemContext::GetNames(long,tagSAFEARRAY * *)

- ea: `0x180066ed0`
- end: `0x1800670b5`
- name: `?GetNames@CWbemContext@@UEAAJJPEAPEAUtagSAFEARRAY@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(CWbemContext *__hidden this, int, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x180066ed0`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180066f48`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180066f48`
- `wbemcomn!GetMemLogObject` at `0x180066f91`
- `wbemcomn!GetMemLogObject` at `0x180066fca`
- `wbemcomn!GetMemLogObject` at `0x180067021`
- `wbemcomn!GetMemLogObject` at `0x180066f91`
- `wbemcomn!GetMemLogObject` at `0x180066fca`
- `wbemcomn!GetMemLogObject` at `0x180067021`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180066f16`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180066f6c`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180066f16`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180066f6c`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180066f80`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180066fbd`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180066ffb`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180066f80`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180066fbd`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180066ffb`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180066eef`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180066eef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066fa0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066fda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006702f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066fa0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180066fda`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006702f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180066f2c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180066f2c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18006701b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18006701b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180066f58`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180066f58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemContext::GetNames(CWbemContext *this, int a2, struct tagSAFEARRAY **a3)
{
  CFlexArray *v6; // rdi
  SAFEARRAY *v7; // rbx
  void **v8; // rax
  LONG v9; // eax
  CMemoryLog *v11; // rax
  CWbemRefreshingSvc *v12; // rcx
  CMemoryLog *v13; // rax
  __int64 v14; // rdx
  CMemoryLog *MemLogObject; // rax
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-18h] BYREF
  _BYTE v17[16]; // [rsp+28h] [rbp-10h] BYREF
  LONG rgIndices; // [rsp+68h] [rbp+30h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v17, (struct _RTL_CRITICAL_SECTION *)((char *)this + 168));
  rgsabound = 0;
  if ( !a2 && a3 )
  {
    v6 = (CWbemContext *)((char *)this + 40);
    rgsabound.cElements = CFlexArray::Size(v6);
    rgsabound.lLbound = 0;
    v7 = SafeArrayCreate(8u, 1u, &rgsabound);
    if ( v7 )
    {
      for ( rgIndices = 0; ; ++rgIndices )
      {
        v9 = CFlexArray::Size(v6);
        if ( rgIndices >= v9 )
        {
          *a3 = v7;
          CInCritSec::~CInCritSec((CInCritSec *)v17);
          return 0;
        }
        v8 = (void **)CFlexArray::GetAt(v6, rgIndices);
        if ( SafeArrayPutElement(v7, &rgIndices, *v8) < 0 )
          break;
      }
      SafeArrayDestroy(v7);
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217402);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_10;
      }
      v14 = 61;
    }
    else
    {
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, -2147217402);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_10;
      }
      v14 = 60;
    }
    WPP_SF_d(*((_QWORD *)v12 + 2), v14, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, 2147749894LL);
LABEL_10:
    CInCritSec::~CInCritSec((CInCritSec *)v17);
    return 2147749894LL;
  }
  v13 = GetMemLogObject();
  CMemoryLog::Write(v13, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, 2147749896LL);
  }
  CInCritSec::~CInCritSec((CInCritSec *)v17);
  return 2147749896LL;
}

```

## disassembly

```asm
0x180066ed0  push    rbp
0x180066ed2  push    rbx
0x180066ed3  push    rsi
0x180066ed4  push    rdi
0x180066ed5  mov     rbp, rsp
0x180066ed8  sub     rsp, 38h
0x180066edc  mov     rsi, r8
0x180066edf  mov     ebx, edx
0x180066ee1  mov     rdi, rcx
0x180066ee4  lea     rdx, [rcx+0A8h]
0x180066eeb  lea     rcx, [rbp+var_10]
0x180066eef  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180066ef5  nop
0x180066ef6  mov     qword ptr [rbp+rgsabound.cElements], 0
0x180066efe  test    ebx, ebx
0x180066f00  jnz     loc_180066FCA
0x180066f06  test    rsi, rsi
0x180066f09  jz      loc_180066FCA
0x180066f0f  add     rdi, 28h ; '('
0x180066f13  mov     rcx, rdi
0x180066f16  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180066f1c  mov     [rbp+rgsabound.cElements], eax
0x180066f1f  mov     [rbp+rgsabound.lLbound], ebx
0x180066f22  lea     ecx, [rbx+8]; vt
0x180066f25  lea     r8, [rbp+rgsabound]; rgsabound
0x180066f29  lea     edx, [rbx+1]; cDims
0x180066f2c  call    cs:__imp_SafeArrayCreate
0x180066f32  mov     rbx, rax
0x180066f35  test    rax, rax
0x180066f38  jz      short loc_180066F91
0x180066f3a  mov     [rbp+rgIndices], 0
0x180066f41  jmp     short loc_180066F69
0x180066f43  mov     edx, ecx
0x180066f45  mov     rcx, rdi
0x180066f48  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180066f4e  mov     r8, [rax]; pv
0x180066f51  lea     rdx, [rbp+rgIndices]; rgIndices
0x180066f55  mov     rcx, rbx; psa
0x180066f58  call    cs:__imp_SafeArrayPutElement
0x180066f5e  test    eax, eax
0x180066f60  js      loc_180067018
0x180066f66  inc     [rbp+rgIndices]
0x180066f69  mov     rcx, rdi
0x180066f6c  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180066f72  mov     ecx, [rbp+rgIndices]
0x180066f75  cmp     ecx, eax
0x180066f77  jl      short loc_180066F43
0x180066f79  mov     [rsi], rbx
0x180066f7c  lea     rcx, [rbp+var_10]
0x180066f80  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180066f86  xor     eax, eax
0x180066f88  add     rsp, 38h
0x180066f8c  pop     rdi
0x180066f8d  pop     rsi
0x180066f8e  pop     rbx
0x180066f8f  pop     rbp
0x180066f90  retn
0x180066f91  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066f97  nop
0x180066f98  mov     edx, 80041006h
0x180066f9d  mov     rcx, rax
0x180066fa0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066fa6  lea     rax, WPP_GLOBAL_Control
0x180066fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fb4  cmp     rcx, rax
0x180066fb7  jnz     short loc_180067005
0x180066fb9  lea     rcx, [rbp+var_10]
0x180066fbd  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180066fc3  mov     eax, 80041006h
0x180066fc8  jmp     short loc_180066F88
0x180066fca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180066fd0  mov     ebx, 80041008h
0x180066fd5  mov     edx, ebx
0x180066fd7  mov     rcx, rax
0x180066fda  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180066fe0  lea     rax, WPP_GLOBAL_Control
0x180066fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fee  cmp     rcx, rax
0x180066ff1  jnz     loc_180067080
0x180066ff7  lea     rcx, [rbp+var_10]
0x180066ffb  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180067001  mov     eax, ebx
0x180067003  jmp     short loc_180066F88
0x180067005  test    byte ptr [rcx+1Ch], 1
0x180067009  jz      short loc_180066FB9
0x18006700b  cmp     byte ptr [rcx+19h], 2
0x18006700f  jb      short loc_180066FB9
0x180067011  mov     edx, 3Ch ; '<'
0x180067016  jmp     short loc_180067065
0x180067018  mov     rcx, rbx; psa
0x18006701b  call    cs:__imp_SafeArrayDestroy
0x180067021  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067027  mov     edx, 80041006h
0x18006702c  mov     rcx, rax
0x18006702f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067035  lea     rax, WPP_GLOBAL_Control
0x18006703c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067043  cmp     rcx, rax
0x180067046  jz      loc_180066FB9
0x18006704c  test    byte ptr [rcx+1Ch], 1
0x180067050  jz      loc_180066FB9
0x180067056  cmp     byte ptr [rcx+19h], 2
0x18006705a  jb      loc_180066FB9
0x180067060  mov     edx, 3Dh ; '='
0x180067065  mov     r9d, 80041006h
0x18006706b  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180067072  mov     rcx, [rcx+10h]
0x180067076  call    WPP_SF_d
0x18006707b  jmp     loc_180066FB9
0x180067080  test    byte ptr [rcx+1Ch], 1
0x180067084  jz      loc_180066FF7
0x18006708a  cmp     byte ptr [rcx+19h], 2
0x18006708e  jb      loc_180066FF7
0x180067094  mov     edx, 3Bh ; ';'
0x180067099  mov     r9d, 80041008h
0x18006709f  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x1800670a6  mov     rcx, [rcx+10h]
0x1800670aa  call    WPP_SF_d
0x1800670af  jmp     loc_180066FF7
```
