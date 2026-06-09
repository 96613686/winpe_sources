# CWbemClass::CreateFromBlob(CWbemClass *,uchar *,unsigned __int64)

- ea: `0x180073710`
- end: `0x1800739f6`
- name: `?CreateFromBlob@CWbemClass@@SAPEAV1@PEAV1@PEAE_K@Z`
- size: `742`
- prototype: `struct CWbemClass *__fastcall(struct CWbemClass *this, unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180074e90`

## callees

- `0x180017eb0`
- `0x18001a4e0`
- `0x180020440`
- `0x180026880`
- `0x180027730`
- `0x180028860`
- `0x180035b08`
- `0x18006d1b0`
- `0x18006fa4c`
- `0x180073710`
- `0x180091972`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180073776`
- `wbemcomn!GetMemLogObject` at `0x1800737fe`
- `wbemcomn!GetMemLogObject` at `0x180073894`
- `wbemcomn!GetMemLogObject` at `0x180073776`
- `wbemcomn!GetMemLogObject` at `0x1800737fe`
- `wbemcomn!GetMemLogObject` at `0x180073894`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073782`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007380a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800738a0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180073782`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007380a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800738a0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180073752`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180073752`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct CWbemClass *__fastcall CWbemClass::CreateFromBlob(
        struct CWbemClass *this,
        unsigned __int8 *a2,
        unsigned __int64 a3)
{
  CWbemClass *v5; // rax
  CWbemClass *v6; // rbx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v8; // rax
  unsigned int v9; // eax
  size_t v10; // r14
  void *v11; // rsi
  CMemoryLog *v12; // rax
  char pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  CWbemClass *v15; // [rsp+38h] [rbp-C8h]
  _QWORD v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v17; // [rsp+50h] [rbp-B0h]
  _BYTE v18[864]; // [rsp+60h] [rbp-A0h] BYREF

  CClassAndMethods::ValidateBuffer(a2, a3);
  v5 = (CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
  v15 = v5;
  if ( v5 )
    v6 = CWbemClass::CWbemClass(v5);
  else
    v6 = 0;
  if ( !v6 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        175,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v15 = v6;
  CWbemClass::CWbemClass((CWbemClass *)v18);
  if ( !this )
  {
    if ( (int)CWbemClass::InitEmpty((CWbemClass *)v18, 0, 1) < 0 )
    {
      v8 = GetMemLogObject();
      CMemoryLog::Write(v8, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          176,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    this = (struct CWbemClass *)v18;
  }
  v9 = CWbemClass::EstimateMergeSpace(this, a2, 1);
  v10 = (int)v9;
  v11 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v6 + 15) + 8LL))(*((_QWORD *)v6 + 15), v9);
  if ( !v11 )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        177,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v16[0] = *((_QWORD *)v6 + 15);
  v16[1] = v11;
  v17 = 0;
  memset_0(v11, 0, v10);
  if ( CWbemClass::Merge(this, a2, (unsigned __int8 *)v11, v10, 0)
    && (v17 = 1,
        (*(void (__fastcall **)(CWbemClass *, void *, _QWORD))(*(_QWORD *)v6 + 1152LL))(v6, v11, (unsigned int)v10),
        (*(int (__fastcall **)(CWbemClass *, _QWORD))(*(_QWORD *)v6 + 744LL))(v6, 0) >= 0) )
  {
    (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v6 + 8LL))(v6);
    OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>((__int64)v16);
    CWbemClass::~CWbemClass((CWbemClass *)v18);
    (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v6 + 16LL))(v6);
    return v6;
  }
  else
  {
    OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>((__int64)v16);
    CWbemClass::~CWbemClass((CWbemClass *)v18);
    (*(void (__fastcall **)(CWbemClass *))(*(_QWORD *)v6 + 16LL))(v6);
    return 0;
  }
}

```

## disassembly

```asm
0x180073710  mov     [rsp-8+arg_18], rbx
0x180073715  push    rbp
0x180073716  push    rsi
0x180073717  push    rdi
0x180073718  push    r14
0x18007371a  push    r15
0x18007371c  lea     rbp, [rsp-2D0h]
0x180073724  sub     rsp, 3D0h
0x18007372b  mov     rax, cs:__security_cookie
0x180073732  xor     rax, rsp
0x180073735  mov     [rbp+2F0h+var_30], rax
0x18007373c  mov     r15, rdx
0x18007373f  mov     rdi, rcx
0x180073742  mov     rdx, r8; unsigned __int64
0x180073745  mov     rcx, r15; unsigned __int8 *
0x180073748  call    ?ValidateBuffer@CClassAndMethods@@SA_KPEAE_K@Z; CClassAndMethods::ValidateBuffer(uchar *,unsigned __int64)
0x18007374d  mov     ecx, 360h
0x180073752  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180073758  mov     [rsp+3F0h+var_3B8], rax
0x18007375d  test    rax, rax
0x180073760  jz      short loc_18007376F
0x180073762  mov     rcx, rax; this
0x180073765  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x18007376a  mov     rbx, rax
0x18007376d  jmp     short loc_180073771
0x18007376f  xor     ebx, ebx
0x180073771  test    rbx, rbx
0x180073774  jnz     short loc_1800737D5
0x180073776  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007377c  lea     edx, [rbx-2]
0x18007377f  mov     rcx, rax
0x180073782  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073788  lea     rax, WPP_GLOBAL_Control
0x18007378f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073796  cmp     rcx, rax
0x180073799  jz      short loc_1800737C3
0x18007379b  test    byte ptr [rcx+1Ch], 1
0x18007379f  jz      short loc_1800737C3
0x1800737a1  cmp     byte ptr [rcx+19h], 2
0x1800737a5  jb      short loc_1800737C3
0x1800737a7  mov     edx, 0AFh
0x1800737ac  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800737b3  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800737ba  mov     rcx, [rcx+10h]
0x1800737be  call    WPP_SF_s
0x1800737c3  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800737ca  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x1800737cf  call    _CxxThrowException_0
0x1800737d5  mov     [rsp+3F0h+var_3B8], rbx
0x1800737da  lea     rcx, [rsp+3F0h+var_390]; this
0x1800737df  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x1800737e4  nop
0x1800737e5  test    rdi, rdi
0x1800737e8  jnz     short loc_180073862
0x1800737ea  xor     edx, edx; int
0x1800737ec  lea     r8d, [rdi+1]; int
0x1800737f0  lea     rcx, [rsp+3F0h+var_390]; this
0x1800737f5  call    ?InitEmpty@CWbemClass@@QEAAJHH@Z; CWbemClass::InitEmpty(int,int)
0x1800737fa  test    eax, eax
0x1800737fc  jns     short loc_18007385D
0x1800737fe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180073804  lea     edx, [rdi-2]
0x180073807  mov     rcx, rax
0x18007380a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180073810  lea     rax, WPP_GLOBAL_Control
0x180073817  mov     rcx, cs:WPP_GLOBAL_Control
0x18007381e  cmp     rcx, rax
0x180073821  jz      short loc_18007384B
0x180073823  test    byte ptr [rcx+1Ch], 1
0x180073827  jz      short loc_18007384B
0x180073829  cmp     byte ptr [rcx+19h], 2
0x18007382d  jb      short loc_18007384B
0x18007382f  mov     edx, 0B0h
0x180073834  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18007383b  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180073842  mov     rcx, [rcx+10h]
0x180073846  call    WPP_SF_s
0x18007384b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180073852  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x180073857  call    _CxxThrowException_0
0x18007385d  lea     rdi, [rsp+3F0h+var_390]
0x180073862  mov     r8d, 1; int
0x180073868  mov     rdx, r15; unsigned __int8 *
0x18007386b  mov     rcx, rdi; this
0x18007386e  call    ?EstimateMergeSpace@CWbemClass@@QEAAKPEAEJ@Z; CWbemClass::EstimateMergeSpace(uchar *,long)
0x180073873  movsxd  r14, eax
0x180073876  mov     r8, [rbx+78h]
0x18007387a  mov     rcx, [r8]
0x18007387d  mov     rax, [rcx+8]
0x180073881  mov     edx, r14d
0x180073884  mov     rcx, r8
0x180073887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007388c  mov     rsi, rax
0x18007388f  test    rax, rax
0x180073892  jnz     short loc_1800738F3
0x180073894  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007389a  lea     edx, [rsi-2]
0x18007389d  mov     rcx, rax
0x1800738a0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800738a6  lea     rax, WPP_GLOBAL_Control
0x1800738ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800738b4  cmp     rcx, rax
0x1800738b7  jz      short loc_1800738E1
0x1800738b9  test    byte ptr [rcx+1Ch], 1
0x1800738bd  jz      short loc_1800738E1
0x1800738bf  cmp     byte ptr [rcx+19h], 2
0x1800738c3  jb      short loc_1800738E1
0x1800738c5  mov     edx, 0B1h
0x1800738ca  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800738d1  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800738d8  mov     rcx, [rcx+10h]
0x1800738dc  call    WPP_SF_s
0x1800738e1  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800738e8  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x1800738ed  call    _CxxThrowException_0
0x1800738f3  mov     rax, [rbx+78h]
0x1800738f7  mov     [rsp+3F0h+var_3B0], rax
0x1800738fc  mov     [rsp+3F0h+var_3A8], rsi
0x180073901  mov     [rsp+3F0h+var_3A0], 0
0x180073906  mov     r8, r14; Size
0x180073909  xor     edx, edx; Val
0x18007390b  mov     rcx, rsi; void *
0x18007390e  call    memset_0
0x180073913  mov     [rsp+3F0h+var_3D0], 0; int
0x18007391b  mov     r9d, r14d; int
0x18007391e  mov     r8, rsi; unsigned __int8 *
0x180073921  mov     rdx, r15; unsigned __int8 *
0x180073924  mov     rcx, rdi; this
0x180073927  call    ?Merge@CWbemClass@@QEAAPEAEPEAE0HH@Z; CWbemClass::Merge(uchar *,uchar *,int,int)
0x18007392c  test    rax, rax
0x18007392f  jnz     short loc_18007395A
0x180073931  lea     rcx, [rsp+3F0h+var_3B0]
0x180073936  call    ??1?$OnDeleteObjIf@PEAEVCBlobControl@@P81@EAAXPEAE@Z$1??_91@$BBI@AA@@QEAA@XZ; OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>(void)
0x18007393b  nop
0x18007393c  lea     rcx, [rsp+3F0h+var_390]; this
0x180073941  call    ??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x180073946  nop
0x180073947  mov     rax, [rbx]
0x18007394a  mov     rcx, rbx
0x18007394d  mov     rax, [rax+10h]
0x180073951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073956  xor     eax, eax
0x180073958  jmp     short loc_1800739C7
0x18007395a  mov     [rsp+3F0h+var_3A0], 1
0x18007395f  mov     rax, [rbx]
0x180073962  mov     r8d, r14d
0x180073965  mov     rdx, rsi
0x180073968  mov     rcx, rbx
0x18007396b  mov     rax, [rax+480h]
0x180073972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073977  mov     rax, [rbx]
0x18007397a  xor     edx, edx
0x18007397c  mov     rcx, rbx
0x18007397f  mov     rax, [rax+2E8h]
0x180073986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007398b  test    eax, eax
0x18007398d  js      short loc_180073931
0x18007398f  mov     rax, [rbx]
0x180073992  mov     rcx, rbx
0x180073995  mov     rax, [rax+8]
0x180073999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007399e  nop
0x18007399f  lea     rcx, [rsp+3F0h+var_3B0]
0x1800739a4  call    ??1?$OnDeleteObjIf@PEAEVCBlobControl@@P81@EAAXPEAE@Z$1??_91@$BBI@AA@@QEAA@XZ; OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>(void)
0x1800739a9  nop
0x1800739aa  lea     rcx, [rsp+3F0h+var_390]; this
0x1800739af  call    ??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x1800739b4  nop
0x1800739b5  mov     rax, [rbx]
0x1800739b8  mov     rcx, rbx
0x1800739bb  mov     rax, [rax+10h]
0x1800739bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800739c4  mov     rax, rbx
0x1800739c7  mov     [rsp+3F0h+var_3B8], 0
0x1800739d0  mov     rcx, [rbp+2F0h+var_30]
0x1800739d7  xor     rcx, rsp; StackCookie
0x1800739da  call    __security_check_cookie
0x1800739df  mov     rbx, [rsp+3F0h+arg_18]
0x1800739e7  add     rsp, 3D0h
0x1800739ee  pop     r15
0x1800739f0  pop     r14
0x1800739f2  pop     rdi
0x1800739f3  pop     rsi
0x1800739f4  pop     rbp
0x1800739f5  retn
```
