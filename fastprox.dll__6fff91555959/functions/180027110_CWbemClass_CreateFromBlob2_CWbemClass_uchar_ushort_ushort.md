# CWbemClass::CreateFromBlob2(CWbemClass *,uchar *,ushort *,ushort *)

- ea: `0x180027110`
- end: `0x180027466`
- name: `?CreateFromBlob2@CWbemClass@@SAPEAV1@PEAV1@PEAEPEAG2@Z`
- size: `854`
- prototype: `struct CWbemClass *__fastcall(struct CWbemClass *this, unsigned __int8 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180026930`

## callees

- `0x18001a4e0`
- `0x180020000`
- `0x180020440`
- `0x180026880`
- `0x180027110`
- `0x1800276c0`
- `0x180027730`
- `0x180028860`
- `0x180035b08`
- `0x18006d1b0`
- `0x18006fa4c`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180027315`
- `wbemcomn!GetMemLogObject` at `0x18002738a`
- `wbemcomn!GetMemLogObject` at `0x1800273f5`
- `wbemcomn!GetMemLogObject` at `0x180027315`
- `wbemcomn!GetMemLogObject` at `0x18002738a`
- `wbemcomn!GetMemLogObject` at `0x1800273f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027323`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027398`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027403`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027323`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027398`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027403`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180027153`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180027153`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct CWbemClass *__fastcall CWbemClass::CreateFromBlob2(
        struct CWbemClass *this,
        unsigned __int8 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  CWbemClass *v8; // rax
  struct CWbemClass *v9; // rdi
  __int64 v10; // r15
  unsigned __int8 *v11; // r14
  struct CWbemClass *result; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  _BYTE pExceptionObject[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  int v18; // [rsp+38h] [rbp-C8h] BYREF
  CWbemClass *v19; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+48h] [rbp-B8h]
  int v21; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 *v22; // [rsp+50h] [rbp-B0h]
  _QWORD v23[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v24; // [rsp+68h] [rbp-98h]
  _BYTE v25[864]; // [rsp+70h] [rbp-90h] BYREF

  v22 = a4;
  v8 = (CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
  v19 = v8;
  if ( v8 )
    v9 = CWbemClass::CWbemClass(v8);
  else
    v9 = 0;
  if ( !v9 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        178,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)pExceptionObject;
  }
  v19 = v9;
  CWbemClass::CWbemClass((CWbemClass *)v25);
  if ( !this )
  {
    if ( (int)CWbemClass::InitEmpty((CWbemClass *)v25, 0, 1) < 0 )
    {
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          179,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)pExceptionObject;
    }
    this = (struct CWbemClass *)v25;
  }
  v17 = 0;
  v20 = CCompressedString::ComputeNecessarySpace(a3, &v17);
  v18 = 0;
  v21 = v20 + 1 + CCompressedString::ComputeNecessarySpace(a4, &v18);
  v10 = CWbemClass::EstimateMergeSpace(this, a2, v21);
  v11 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v9 + 15) + 8LL))(
                             *((_QWORD *)v9 + 15),
                             v10);
  if ( !v11 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        180,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)pExceptionObject;
  }
  v23[0] = *((_QWORD *)v9 + 15);
  v23[1] = v11;
  v24 = 0;
  *v11 = 4;
  CCompressedString::SetFromUnicode((CCompressedString *)(v11 + 1), v17, a3);
  CCompressedString::SetFromUnicode((CCompressedString *)&v11[v20 + 1], v18, v22);
  if ( !CWbemClass::Merge(this, a2, v11, v10, v21) )
  {
    OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<unsigned char *,CBlobControl,void (CBlobControl::*)(unsigned char *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>((__int64)v23);
    goto LABEL_10;
  }
  v24 = 1;
  (*(void (__fastcall **)(struct CWbemClass *, unsigned __int8 *, _QWORD))(*(_QWORD *)v9 + 1152LL))(
    v9,
    v11,
    (unsigned int)v10);
  if ( (*(int (__fastcall **)(struct CWbemClass *, _QWORD))(*(_QWORD *)v9 + 744LL))(v9, 0) < 0 )
  {
LABEL_10:
    CWbemClass::~CWbemClass((CWbemClass *)v25);
    (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v9 + 16LL))(v9);
    result = 0;
    goto LABEL_9;
  }
  (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v9 + 8LL))(v9);
  CWbemClass::~CWbemClass((CWbemClass *)v25);
  (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v9 + 16LL))(v9);
  result = v9;
LABEL_9:
  v19 = 0;
  return result;
}

```

## disassembly

```asm
0x180027110  push    rbp
0x180027112  push    rbx
0x180027113  push    rsi
0x180027114  push    rdi
0x180027115  push    r12
0x180027117  push    r13
0x180027119  push    r14
0x18002711b  push    r15
0x18002711d  lea     rbp, [rsp-2E8h]
0x180027125  sub     rsp, 3E8h
0x18002712c  mov     rax, cs:__security_cookie
0x180027133  xor     rax, rsp
0x180027136  mov     [rbp+320h+var_50], rax
0x18002713d  mov     rbx, r9
0x180027140  mov     [rsp+420h+var_3D0], rbx
0x180027145  mov     r13, r8
0x180027148  mov     r12, rdx
0x18002714b  mov     rsi, rcx
0x18002714e  mov     ecx, 360h
0x180027153  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180027159  mov     [rsp+420h+var_3E0], rax
0x18002715e  test    rax, rax
0x180027161  jz      loc_18002730E
0x180027167  mov     rcx, rax; this
0x18002716a  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x18002716f  mov     rdi, rax
0x180027172  test    rdi, rdi
0x180027175  jz      loc_180027315
0x18002717b  mov     [rsp+420h+var_3E0], rdi
0x180027180  lea     rcx, [rsp+420h+var_3B0]; this
0x180027185  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x18002718a  nop
0x18002718b  test    rsi, rsi
0x18002718e  jz      loc_180027376
0x180027194  mov     [rsp+420h+var_3EC], 0
0x18002719c  lea     rdx, [rsp+420h+var_3EC]; int *
0x1800271a1  mov     rcx, r13; unsigned __int16 *
0x1800271a4  call    ?ComputeNecessarySpace@CCompressedString@@SAHPEBGAEAH@Z; CCompressedString::ComputeNecessarySpace(ushort const *,int &)
0x1800271a9  mov     r14d, eax
0x1800271ac  mov     [rsp+420h+var_3D8], eax
0x1800271b0  mov     [rsp+420h+var_3E8], 0
0x1800271b8  lea     rdx, [rsp+420h+var_3E8]; int *
0x1800271bd  mov     rcx, rbx; unsigned __int16 *
0x1800271c0  call    ?ComputeNecessarySpace@CCompressedString@@SAHPEBGAEAH@Z; CCompressedString::ComputeNecessarySpace(ushort const *,int &)
0x1800271c5  inc     r14d
0x1800271c8  add     eax, r14d
0x1800271cb  mov     [rsp+420h+var_3D4], eax
0x1800271cf  mov     r8d, eax; int
0x1800271d2  mov     rdx, r12; unsigned __int8 *
0x1800271d5  mov     rcx, rsi; this
0x1800271d8  call    ?EstimateMergeSpace@CWbemClass@@QEAAKPEAEJ@Z; CWbemClass::EstimateMergeSpace(uchar *,long)
0x1800271dd  mov     r15d, eax
0x1800271e0  mov     r8, [rdi+78h]
0x1800271e4  mov     rcx, [r8]
0x1800271e7  mov     rax, [rcx+8]
0x1800271eb  mov     edx, r15d
0x1800271ee  mov     rcx, r8
0x1800271f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271f6  mov     r14, rax
0x1800271f9  test    rax, rax
0x1800271fc  jz      loc_1800273F5
0x180027202  mov     rax, [rdi+78h]
0x180027206  mov     [rsp+420h+var_3C8], rax
0x18002720b  mov     [rsp+420h+var_3C0], r14
0x180027210  mov     [rsp+420h+var_3B8], 0
0x180027215  mov     byte ptr [r14], 4
0x180027219  lea     rbx, [r14+1]
0x18002721d  mov     r8, r13; unsigned __int16 *
0x180027220  mov     edx, [rsp+420h+var_3EC]; int
0x180027224  mov     rcx, rbx; this
0x180027227  call    ?SetFromUnicode@CCompressedString@@QEAAXHPEBG@Z; CCompressedString::SetFromUnicode(int,ushort const *)
0x18002722c  movsxd  rcx, [rsp+420h+var_3D8]
0x180027231  add     rcx, rbx; this
0x180027234  mov     r8, [rsp+420h+var_3D0]; unsigned __int16 *
0x180027239  mov     edx, [rsp+420h+var_3E8]; int
0x18002723d  call    ?SetFromUnicode@CCompressedString@@QEAAXHPEBG@Z; CCompressedString::SetFromUnicode(int,ushort const *)
0x180027242  mov     eax, [rsp+420h+var_3D4]
0x180027246  mov     [rsp+420h+var_400], eax; int
0x18002724a  mov     r9d, r15d; int
0x18002724d  mov     r8, r14; unsigned __int8 *
0x180027250  mov     rdx, r12; unsigned __int8 *
0x180027253  mov     rcx, rsi; this
0x180027256  call    ?Merge@CWbemClass@@QEAAPEAEPEAE0HH@Z; CWbemClass::Merge(uchar *,uchar *,int,int)
0x18002725b  xor     ebx, ebx
0x18002725d  test    rax, rax
0x180027260  jz      loc_180027456
0x180027266  mov     [rsp+420h+var_3B8], 1
0x18002726b  mov     rax, [rdi]
0x18002726e  mov     r8d, r15d
0x180027271  mov     rdx, r14
0x180027274  mov     rcx, rdi
0x180027277  mov     rax, [rax+480h]
0x18002727e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027283  mov     rax, [rdi]
0x180027286  xor     edx, edx
0x180027288  mov     rcx, rdi
0x18002728b  mov     rax, [rax+2E8h]
0x180027292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027297  test    eax, eax
0x180027299  js      short loc_1800272F0
0x18002729b  mov     rax, [rdi]
0x18002729e  mov     rcx, rdi
0x1800272a1  mov     rax, [rax+8]
0x1800272a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272aa  nop
0x1800272ab  lea     rcx, [rsp+420h+var_3B0]; this
0x1800272b0  call    ??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x1800272b5  nop
0x1800272b6  mov     rax, [rdi]
0x1800272b9  mov     rcx, rdi
0x1800272bc  mov     rax, [rax+10h]
0x1800272c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272c5  mov     rax, rdi
0x1800272c8  mov     [rsp+420h+var_3E0], rbx
0x1800272cd  mov     rcx, [rbp+320h+var_50]
0x1800272d4  xor     rcx, rsp; StackCookie
0x1800272d7  call    __security_check_cookie
0x1800272dc  add     rsp, 3E8h
0x1800272e3  pop     r15
0x1800272e5  pop     r14
0x1800272e7  pop     r13
0x1800272e9  pop     r12
0x1800272eb  pop     rdi
0x1800272ec  pop     rsi
0x1800272ed  pop     rbx
0x1800272ee  pop     rbp
0x1800272ef  retn
0x1800272f0  lea     rcx, [rsp+420h+var_3B0]; this
0x1800272f5  call    ??1CWbemClass@@UEAA@XZ; CWbemClass::~CWbemClass(void)
0x1800272fa  nop
0x1800272fb  mov     rax, [rdi]
0x1800272fe  mov     rcx, rdi
0x180027301  mov     rax, [rax+10h]
0x180027305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002730a  xor     eax, eax
0x18002730c  jmp     short loc_1800272C8
0x18002730e  xor     edi, edi
0x180027310  jmp     loc_180027172
0x180027315  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002731b  mov     edx, 0FFFFFFFEh
0x180027320  mov     rcx, rax
0x180027323  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180027329  lea     rax, WPP_GLOBAL_Control
0x180027330  mov     rcx, cs:WPP_GLOBAL_Control
0x180027337  cmp     rcx, rax
0x18002733a  jz      short loc_180027364
0x18002733c  test    byte ptr [rcx+1Ch], 1
0x180027340  jz      short loc_180027364
0x180027342  cmp     byte ptr [rcx+19h], 2
0x180027346  jb      short loc_180027364
0x180027348  mov     edx, 0B2h
0x18002734d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180027354  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18002735b  mov     rcx, [rcx+10h]
0x18002735f  call    WPP_SF_s
0x180027364  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18002736b  lea     rcx, [rsp+420h+pExceptionObject]; pExceptionObject
0x180027370  call    _CxxThrowException_0
0x180027376  xor     edx, edx; int
0x180027378  lea     r8d, [rdx+1]; int
0x18002737c  lea     rcx, [rsp+420h+var_3B0]; this
0x180027381  call    ?InitEmpty@CWbemClass@@QEAAJHH@Z; CWbemClass::InitEmpty(int,int)
0x180027386  test    eax, eax
0x180027388  jns     short loc_1800273EB
0x18002738a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180027390  mov     edx, 0FFFFFFFEh
0x180027395  mov     rcx, rax
0x180027398  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002739e  lea     rax, WPP_GLOBAL_Control
0x1800273a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273ac  cmp     rcx, rax
0x1800273af  jz      short loc_1800273D9
0x1800273b1  test    byte ptr [rcx+1Ch], 1
0x1800273b5  jz      short loc_1800273D9
0x1800273b7  cmp     byte ptr [rcx+19h], 2
0x1800273bb  jb      short loc_1800273D9
0x1800273bd  mov     edx, 0B3h
0x1800273c2  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800273c9  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800273d0  mov     rcx, [rcx+10h]
0x1800273d4  call    WPP_SF_s
0x1800273d9  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800273e0  lea     rcx, [rsp+420h+pExceptionObject]; pExceptionObject
0x1800273e5  call    _CxxThrowException_0
0x1800273eb  lea     rsi, [rsp+420h+var_3B0]
0x1800273f0  jmp     loc_180027194
0x1800273f5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800273fb  mov     edx, 0FFFFFFFEh
0x180027400  mov     rcx, rax
0x180027403  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180027409  lea     rax, WPP_GLOBAL_Control
0x180027410  mov     rcx, cs:WPP_GLOBAL_Control
0x180027417  cmp     rcx, rax
0x18002741a  jz      short loc_180027444
0x18002741c  test    byte ptr [rcx+1Ch], 1
0x180027420  jz      short loc_180027444
0x180027422  cmp     byte ptr [rcx+19h], 2
0x180027426  jb      short loc_180027444
0x180027428  mov     edx, 0B4h
0x18002742d  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180027434  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18002743b  mov     rcx, [rcx+10h]
0x18002743f  call    WPP_SF_s
0x180027444  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18002744b  lea     rcx, [rsp+420h+pExceptionObject]; pExceptionObject
0x180027450  call    _CxxThrowException_0
0x180027456  lea     rcx, [rsp+420h+var_3C8]
0x18002745b  call    ??1?$OnDeleteObjIf@PEAEVCBlobControl@@P81@EAAXPEAE@Z$1??_91@$BBI@AA@@QEAA@XZ; OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>::~OnDeleteObjIf<uchar *,CBlobControl,void (CBlobControl::*)(uchar *),&[thunk]: CBlobControl::`vcall'{24,{flat}}>(void)
0x180027460  jmp     loc_1800272F0
```
