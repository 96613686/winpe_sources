# CWbemContext::CContextObj::CContextObj(IStream *,ulong &)

- ea: `0x180016edc`
- end: `0x1800172c1`
- name: `??0CContextObj@CWbemContext@@QEAA@PEAUIStream@@AEAK@Z`
- size: `997`
- prototype: `CWbemContext::CContextObj *__fastcall(OLECHAR *this, struct IStream *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800168d0`

## callees

- `0x180016edc`
- `0x1800172c8`
- `0x1800175f4`
- `0x180035b08`
- `0x180038ad4`
- `0x18006182c`
- `0x18006fa4c`
- `0x180091972`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800170d2`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x1800170d2`
- `wbemcomn!GetMemLogObject` at `0x18001713b`
- `wbemcomn!GetMemLogObject` at `0x18001719b`
- `wbemcomn!GetMemLogObject` at `0x180017201`
- `wbemcomn!GetMemLogObject` at `0x180017261`
- `wbemcomn!GetMemLogObject` at `0x18001713b`
- `wbemcomn!GetMemLogObject` at `0x18001719b`
- `wbemcomn!GetMemLogObject` at `0x180017201`
- `wbemcomn!GetMemLogObject` at `0x180017261`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017149`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800171a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001720f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001726f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017149`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800171a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001720f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001726f`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f47`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f52`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f47`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f52`
- `OLEAUT32!__imp_VariantInit` at `0x180016f18`
- `OLEAUT32!__imp_VariantInit` at `0x180016f18`
- `OLEAUT32!__imp_VariantClear` at `0x180017044`
- `OLEAUT32!__imp_VariantClear` at `0x180017044`

## pseudocode

```c
CWbemContext::CContextObj *__fastcall CWbemContext::CContextObj::CContextObj(
        OLECHAR *this,
        struct IStream *a2,
        unsigned int *a3)
{
  VARIANTARG *v6; // rsi
  BSTR *v7; // rax
  BSTR v8; // rdx
  OLECHAR *v9; // rcx
  int v10; // eax
  struct IErrorInfo *v11; // rdx
  int v12; // eax
  struct IErrorInfo *v13; // rdx
  struct IErrorInfo *v14; // rdx
  HRESULT v15; // ecx
  HRESULT v16; // eax
  struct IErrorInfo *v17; // rdx
  HRESULT v19; // eax
  int v20; // eax
  struct IErrorInfo *v21; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  _BYTE pExceptionObject[4]; // [rsp+30h] [rbp-69h] BYREF
  int v27; // [rsp+34h] [rbp-65h] BYREF
  OLECHAR *v28; // [rsp+38h] [rbp-61h] BYREF
  LPVOID ppv[2]; // [rsp+40h] [rbp-59h] BYREF
  IRecordInfo *v30; // [rsp+50h] [rbp-49h]
  BSTR bstrString[3]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v32[16]; // [rsp+70h] [rbp-29h] BYREF
  int v33; // [rsp+80h] [rbp-19h]

  bstrString[1] = this;
  *(_QWORD *)this = 0;
  v6 = (VARIANTARG *)(this + 8);
  VariantInit((VARIANTARG *)(this + 8));
  v7 = UnmarshalBSTR(bstrString, (__int64)a2, a3);
  v8 = *v7;
  *v7 = 0;
  v28 = v8;
  v9 = *(OLECHAR **)this;
  *(_QWORD *)this = v8;
  v28 = v9;
  SysFreeString(v9);
  SysFreeString(bstrString[0]);
  *((_DWORD *)this + 2) = 0;
  v27 = 0;
  v10 = ((__int64 (__fastcall *)(struct IStream *, OLECHAR *, __int64, int *))a2->lpVtbl->Read)(a2, this + 4, 4, &v27);
  if ( v10 < 0 )
    _com_raise_error(v10, v11);
  if ( v27 != 4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)pExceptionObject;
  }
  *a3 -= 4;
  *(_OWORD *)ppv = 0;
  v30 = 0;
  v12 = ((__int64 (__fastcall *)(struct IStream *, LPVOID *, __int64, int *))a2->lpVtbl->Read)(a2, ppv, 2, &v27);
  if ( v12 < 0 )
    _com_raise_error(v12, v13);
  if ( v27 != 2 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)pExceptionObject;
  }
  *a3 -= 2;
  if ( LOWORD(ppv[0]) != 1 )
  {
    if ( LOWORD(ppv[0]) == 8 )
    {
      v19 = UnmarshalBSTR(a2, (unsigned __int16 **)&ppv[1], a3);
    }
    else
    {
      if ( LOWORD(ppv[0]) == 13 )
      {
        v15 = CoUnmarshalInterface(a2, &IID_IWbemClassObject, &ppv[1]);
        if ( v15 < 0 )
          goto LABEL_19;
        memset_0(v32, 0, 0x50u);
        v20 = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, _QWORD))a2->lpVtbl->Stat)(a2, v32, 0);
        if ( v20 < 0 )
          _com_raise_error(v20, v21);
        v28 = 0;
        v15 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, __int64, OLECHAR **))a2->lpVtbl->Seek)(a2, 0, 1, &v28);
        *a3 = v33 - (_DWORD)v28;
LABEL_12:
        if ( v15 >= 0 )
          goto LABEL_13;
LABEL_19:
        _com_raise_error(v15, v14);
      }
      if ( ((__int64)ppv[0] & 0xDFFF) == 9 )
      {
        LOWORD(ppv[0]) = 0;
        v24 = GetMemLogObject();
        CMemoryLog::Write(v24, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
            "CX_ContextMarshalException()");
        }
        throw (CX_ContextMarshalException *)pExceptionObject;
      }
      if ( ((__int64)ppv[0] & 0x2000) == 0 )
      {
        v15 = ((__int64 (__fastcall *)(struct IStream *, LPVOID *, __int64, int *))a2->lpVtbl->Read)(
                a2,
                &ppv[1],
                8,
                &v27);
        if ( v27 != 8 )
        {
          v25 = GetMemLogObject();
          CMemoryLog::Write(v25, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              42,
              WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
              "CX_Exception()");
          }
          throw (CX_Exception *)pExceptionObject;
        }
        *a3 -= 8;
        goto LABEL_12;
      }
      v19 = UnmarshalSafeArray(a2, (__int64)ppv[0] & 0xDFFF, (struct tagSAFEARRAY **)&ppv[1], a3);
    }
    v15 = v19;
    goto LABEL_12;
  }
LABEL_13:
  v16 = VariantClear(v6);
  if ( v16 < 0 )
    _com_raise_error(v16, v17);
  *(_OWORD *)&v6->vt = *(_OWORD *)ppv;
  v6->pRecInfo = v30;
  return (CWbemContext::CContextObj *)this;
}

```

## disassembly

```asm
0x180016edc  push    rbp
0x180016ede  push    rbx
0x180016edf  push    rsi
0x180016ee0  push    rdi
0x180016ee1  push    r14
0x180016ee3  lea     rbp, [rsp-37h]
0x180016ee8  sub     rsp, 0D0h
0x180016eef  mov     rax, cs:__security_cookie
0x180016ef6  xor     rax, rsp
0x180016ef9  mov     [rbp+57h+var_30], rax
0x180016efd  mov     rdi, r8
0x180016f00  mov     rbx, rdx
0x180016f03  mov     r14, rcx
0x180016f06  mov     [rbp+57h+var_90], rcx
0x180016f0a  mov     qword ptr [rcx], 0
0x180016f11  lea     rsi, [rcx+10h]
0x180016f15  mov     rcx, rsi; pvarg
0x180016f18  call    cs:__imp_VariantInit
0x180016f1e  nop
0x180016f1f  mov     r8, rdi
0x180016f22  mov     rdx, rbx
0x180016f25  lea     rcx, [rbp+57h+bstrString]
0x180016f29  call    ?UnmarshalBSTR@@YA?AVauto_bstr@@PEAUIStream@@AEAK@Z; UnmarshalBSTR(IStream *,ulong &)
0x180016f2e  nop
0x180016f2f  mov     rdx, [rax]
0x180016f32  mov     qword ptr [rax], 0
0x180016f39  mov     [rbp+57h+var_B8], rdx
0x180016f3d  mov     rcx, [r14]; bstrString
0x180016f40  mov     [r14], rdx
0x180016f43  mov     [rbp+57h+var_B8], rcx
0x180016f47  call    cs:__imp_SysFreeString
0x180016f4d  nop
0x180016f4e  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180016f52  call    cs:__imp_SysFreeString
0x180016f58  lea     rdx, [r14+8]
0x180016f5c  mov     dword ptr [rdx], 0
0x180016f62  mov     [rbp+57h+var_BC], 0
0x180016f69  mov     rax, [rbx]
0x180016f6c  lea     r9, [rbp+57h+var_BC]
0x180016f70  mov     r8d, 4
0x180016f76  mov     rcx, rbx
0x180016f79  mov     rax, [rax+18h]
0x180016f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f82  test    eax, eax
0x180016f84  js      loc_18001708F
0x180016f8a  cmp     [rbp+57h+var_BC], 4
0x180016f8e  jnz     loc_18001713B
0x180016f94  add     dword ptr [rdi], 0FFFFFFFCh
0x180016f97  xorps   xmm0, xmm0
0x180016f9a  xor     eax, eax
0x180016f9c  movups  xmmword ptr [rbp+57h+ppv], xmm0
0x180016fa0  mov     [rbp+57h+var_A0], rax
0x180016fa4  mov     rax, [rbx]
0x180016fa7  lea     r9, [rbp+57h+var_BC]
0x180016fab  mov     r8d, 2
0x180016fb1  lea     rdx, [rbp+57h+ppv]
0x180016fb5  mov     rcx, rbx
0x180016fb8  mov     rax, [rax+18h]
0x180016fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc1  test    eax, eax
0x180016fc3  js      loc_180017097
0x180016fc9  cmp     [rbp+57h+var_BC], 2
0x180016fcd  jnz     loc_18001719B
0x180016fd3  add     dword ptr [rdi], 0FFFFFFFEh
0x180016fd6  movzx   r10d, word ptr [rbp+57h+ppv]
0x180016fdb  mov     edx, r10d
0x180016fde  mov     ecx, r10d
0x180016fe1  sub     ecx, 1
0x180016fe4  jz      short loc_180017041
0x180016fe6  sub     ecx, 7
0x180016fe9  jz      loc_18001707C
0x180016fef  cmp     ecx, 5
0x180016ff2  jz      loc_1800170C4
0x180016ff8  btr     edx, 0Dh
0x180016ffc  cmp     edx, 9
0x180016fff  jz      loc_1800171FB
0x180017005  mov     rcx, rbx; struct IStream *
0x180017008  bt      r10w, 0Dh
0x18001700e  jb      loc_1800170AD
0x180017014  mov     rax, [rbx]
0x180017017  lea     r9, [rbp+57h+var_BC]
0x18001701b  mov     r8d, 8
0x180017021  lea     rdx, [rbp+57h+ppv+8]
0x180017025  mov     rax, [rax+18h]
0x180017029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001702e  mov     ecx, eax; int
0x180017030  cmp     [rbp+57h+var_BC], 8
0x180017034  jnz     loc_180017261
0x18001703a  add     dword ptr [rdi], 0FFFFFFF8h
0x18001703d  test    ecx, ecx
0x18001703f  js      short loc_18001709F
0x180017041  mov     rcx, rsi; pvarg
0x180017044  call    cs:__imp_VariantClear
0x18001704a  test    eax, eax
0x18001704c  js      short loc_1800170A5
0x18001704e  movups  xmm0, xmmword ptr [rbp+57h+ppv]
0x180017052  movups  xmmword ptr [rsi], xmm0
0x180017055  movsd   xmm1, [rbp+57h+var_A0]
0x18001705a  movsd   qword ptr [rsi+10h], xmm1
0x18001705f  mov     rax, r14
0x180017062  mov     rcx, [rbp+57h+var_30]
0x180017066  xor     rcx, rsp; StackCookie
0x180017069  call    __security_check_cookie
0x18001706e  add     rsp, 0D0h
0x180017075  pop     r14
0x180017077  pop     rdi
0x180017078  pop     rsi
0x180017079  pop     rbx
0x18001707a  pop     rbp
0x18001707b  retn
0x18001707c  mov     r8, rdi; unsigned int *
0x18001707f  lea     rdx, [rbp+57h+ppv+8]; unsigned __int16 **
0x180017083  mov     rcx, rbx; struct IStream *
0x180017086  call    ?UnmarshalBSTR@@YAJPEAUIStream@@AEAPEAGAEAK@Z; UnmarshalBSTR(IStream *,ushort * &,ulong &)
0x18001708b  mov     ecx, eax
0x18001708d  jmp     short loc_18001703D
0x18001708f  mov     ecx, eax; int
0x180017091  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180017097  mov     ecx, eax; int
0x180017099  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001709f  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800170a5  mov     ecx, eax; int
0x1800170a7  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800170ad  mov     edx, 0DFFFh
0x1800170b2  and     dx, r10w; unsigned __int16
0x1800170b6  mov     r9, rdi; unsigned int *
0x1800170b9  lea     r8, [rbp+57h+ppv+8]; struct tagSAFEARRAY **
0x1800170bd  call    ?UnmarshalSafeArray@@YAJPEAUIStream@@GAEAPEAUtagSAFEARRAY@@AEAK@Z; UnmarshalSafeArray(IStream *,ushort,tagSAFEARRAY * &,ulong &)
0x1800170c2  jmp     short loc_18001708B
0x1800170c4  lea     r8, [rbp+57h+ppv+8]; ppv
0x1800170c8  lea     rdx, IID_IWbemClassObject; riid
0x1800170cf  mov     rcx, rbx; pStm
0x1800170d2  call    cs:__imp_CoUnmarshalInterface
0x1800170d8  mov     ecx, eax
0x1800170da  test    eax, eax
0x1800170dc  js      short loc_18001709F
0x1800170de  xor     edx, edx; Val
0x1800170e0  lea     r8d, [rdx+50h]; Size
0x1800170e4  lea     rcx, [rbp+57h+var_80]; void *
0x1800170e8  call    memset_0
0x1800170ed  mov     rax, [rbx]
0x1800170f0  xor     r8d, r8d
0x1800170f3  lea     rdx, [rbp+57h+var_80]
0x1800170f7  mov     rcx, rbx
0x1800170fa  mov     rax, [rax+60h]
0x1800170fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017103  test    eax, eax
0x180017105  js      short loc_180017133
0x180017107  xor     edx, edx
0x180017109  mov     [rbp+57h+var_B8], rdx
0x18001710d  mov     rax, [rbx]
0x180017110  lea     r9, [rbp+57h+var_B8]
0x180017114  lea     r8d, [rdx+1]
0x180017118  mov     rcx, rbx
0x18001711b  mov     rax, [rax+28h]
0x18001711f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017124  mov     ecx, eax
0x180017126  mov     eax, [rbp+57h+var_70]
0x180017129  sub     eax, dword ptr [rbp+57h+var_B8]
0x18001712c  mov     [rdi], eax
0x18001712e  jmp     loc_18001703D
0x180017133  mov     ecx, eax; int
0x180017135  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001713b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017141  mov     edx, 0FFFFFFFEh
0x180017146  mov     rcx, rax
0x180017149  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001714f  lea     rax, WPP_GLOBAL_Control
0x180017156  mov     rcx, cs:WPP_GLOBAL_Control
0x18001715d  cmp     rcx, rax
0x180017160  jz      short loc_18001718A
0x180017162  test    byte ptr [rcx+1Ch], 1
0x180017166  jz      short loc_18001718A
0x180017168  cmp     byte ptr [rcx+19h], 2
0x18001716c  jb      short loc_18001718A
0x18001716e  mov     edx, 27h ; '''
0x180017173  lea     r9, aCxException; "CX_Exception()"
0x18001717a  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180017181  mov     rcx, [rcx+10h]
0x180017185  call    WPP_SF_s
0x18001718a  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180017191  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180017195  call    _CxxThrowException_0
0x18001719b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800171a1  mov     edx, 0FFFFFFFEh
0x1800171a6  mov     rcx, rax
0x1800171a9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800171af  lea     rax, WPP_GLOBAL_Control
0x1800171b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171bd  cmp     rcx, rax
0x1800171c0  jz      short loc_1800171EA
0x1800171c2  test    byte ptr [rcx+1Ch], 1
0x1800171c6  jz      short loc_1800171EA
0x1800171c8  cmp     byte ptr [rcx+19h], 2
0x1800171cc  jb      short loc_1800171EA
0x1800171ce  mov     edx, 28h ; '('
0x1800171d3  lea     r9, aCxException; "CX_Exception()"
0x1800171da  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x1800171e1  mov     rcx, [rcx+10h]
0x1800171e5  call    WPP_SF_s
0x1800171ea  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x1800171f1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800171f5  call    _CxxThrowException_0
0x1800171fb  xor     eax, eax
0x1800171fd  mov     word ptr [rbp+57h+ppv], ax
0x180017201  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017207  mov     edx, 0FFFFFFFEh
0x18001720c  mov     rcx, rax
0x18001720f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017215  lea     rax, WPP_GLOBAL_Control
0x18001721c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017223  cmp     rcx, rax
0x180017226  jz      short loc_180017250
0x180017228  test    byte ptr [rcx+1Ch], 1
0x18001722c  jz      short loc_180017250
0x18001722e  cmp     byte ptr [rcx+19h], 2
0x180017232  jb      short loc_180017250
0x180017234  mov     edx, 29h ; ')'
0x180017239  lea     r9, aCxContextmarsh; "CX_ContextMarshalException()"
0x180017240  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180017247  mov     rcx, [rcx+10h]
0x18001724b  call    WPP_SF_s
0x180017250  lea     rdx, _TI2?AVCX_ContextMarshalException@@; pThrowInfo
0x180017257  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001725b  call    _CxxThrowException_0
0x180017261  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017267  mov     edx, 0FFFFFFFEh
0x18001726c  mov     rcx, rax
0x18001726f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017275  lea     rax, WPP_GLOBAL_Control
0x18001727c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017283  cmp     rcx, rax
0x180017286  jz      short loc_1800172B0
0x180017288  test    byte ptr [rcx+1Ch], 1
0x18001728c  jz      short loc_1800172B0
0x18001728e  cmp     byte ptr [rcx+19h], 2
0x180017292  jb      short loc_1800172B0
0x180017294  mov     edx, 2Ah ; '*'
0x180017299  lea     r9, aCxException; "CX_Exception()"
0x1800172a0  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x1800172a7  mov     rcx, [rcx+10h]
0x1800172ab  call    WPP_SF_s
0x1800172b0  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x1800172b7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800172bb  call    _CxxThrowException_0
```
