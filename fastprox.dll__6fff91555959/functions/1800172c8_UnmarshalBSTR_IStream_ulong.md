# UnmarshalBSTR(IStream *,ulong &)

- ea: `0x1800172c8`
- end: `0x18001752e`
- name: `?UnmarshalBSTR@@YA?AVauto_bstr@@PEAUIStream@@AEAK@Z`
- size: `614`
- prototype: `BSTR *__fastcall(BSTR *, __int64, UINT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016edc`

## callees

- `0x1800172c8`
- `0x180017534`
- `0x180035b08`
- `0x180038ad4`
- `0x18006fa4c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800173a4`
- `wbemcomn!GetMemLogObject` at `0x180017404`
- `wbemcomn!GetMemLogObject` at `0x18001746e`
- `wbemcomn!GetMemLogObject` at `0x1800174ce`
- `wbemcomn!GetMemLogObject` at `0x1800173a4`
- `wbemcomn!GetMemLogObject` at `0x180017404`
- `wbemcomn!GetMemLogObject` at `0x18001746e`
- `wbemcomn!GetMemLogObject` at `0x1800174ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800173b2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017412`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001747c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800174dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800173b2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017412`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001747c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800174dc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180017345`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180017345`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BSTR *__fastcall UnmarshalBSTR(BSTR *a1, __int64 a2, UINT *a3)
{
  int v6; // eax
  struct IErrorInfo *v7; // rdx
  UINT v8; // ebx
  int v9; // eax
  struct IErrorInfo *v10; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  int v16; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+34h] [rbp-Ch]
  UINT pExceptionObject; // [rsp+78h] [rbp+38h] BYREF
  UINT ui; // [rsp+88h] [rbp+48h] BYREF

  v17 = 0;
  ui = 0;
  v16 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, UINT *, __int64, int *))(*(_QWORD *)a2 + 24LL))(a2, &ui, 4, &v16);
  if ( v6 < 0 )
    _com_raise_error(v6, v7);
  if ( v16 != 4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  *a3 -= 4;
  pExceptionObject = ui;
  SafeInt<unsigned long>::operator*=<int>(&pExceptionObject);
  v8 = pExceptionObject;
  if ( pExceptionObject > *a3 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  *a1 = SysAllocStringLen(0, ui);
  v17 = 1;
  if ( !*a1 && ui )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, int *))(*(_QWORD *)a2 + 24LL))(a2, *a1, v8, &v16);
  if ( v9 < 0 )
    _com_raise_error(v9, v10);
  if ( v8 != v16 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  *a3 -= v8;
  return a1;
}

```

## disassembly

```asm
0x1800172c8  mov     [rsp-28h+arg_0], rcx
0x1800172cd  push    rbp
0x1800172ce  push    rbx
0x1800172cf  push    rsi
0x1800172d0  push    rdi
0x1800172d1  push    r14
0x1800172d3  mov     rbp, rsp
0x1800172d6  sub     rsp, 40h
0x1800172da  mov     rdi, r8
0x1800172dd  mov     r14, rdx
0x1800172e0  mov     rsi, rcx
0x1800172e3  mov     [rbp+var_C], 0
0x1800172ea  mov     [rbp+ui], 0
0x1800172f1  mov     [rbp+var_10], 0
0x1800172f8  mov     rax, [rdx]
0x1800172fb  lea     r9, [rbp+var_10]
0x1800172ff  mov     r8d, 4
0x180017305  lea     rdx, [rbp+ui]
0x180017309  mov     rcx, r14
0x18001730c  mov     rax, [rax+18h]
0x180017310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017315  test    eax, eax
0x180017317  js      short loc_180017394
0x180017319  cmp     [rbp+var_10], 4
0x18001731d  jnz     loc_1800173A4
0x180017323  add     dword ptr [rdi], 0FFFFFFFCh
0x180017326  mov     eax, [rbp+ui]
0x180017329  mov     [rbp+pExceptionObject], eax
0x18001732c  lea     rcx, [rbp+pExceptionObject]
0x180017330  call    ??$?XH@?$SafeInt@K@@QEAAAEAV0@H@Z; SafeInt<ulong>::operator*=<int>(int)
0x180017335  mov     ebx, [rbp+pExceptionObject]
0x180017338  cmp     ebx, [rdi]
0x18001733a  ja      loc_180017404
0x180017340  mov     edx, [rbp+ui]; ui
0x180017343  xor     ecx, ecx; strIn
0x180017345  call    cs:__imp_SysAllocStringLen
0x18001734b  mov     [rsi], rax
0x18001734e  mov     [rbp+var_C], 1
0x180017355  mov     rdx, [rsi]
0x180017358  test    rdx, rdx
0x18001735b  jz      loc_180017464
0x180017361  mov     rax, [r14]
0x180017364  lea     r9, [rbp+var_10]
0x180017368  mov     r8d, ebx
0x18001736b  mov     rcx, r14
0x18001736e  mov     rax, [rax+18h]
0x180017372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017377  test    eax, eax
0x180017379  js      short loc_18001739C
0x18001737b  cmp     ebx, [rbp+var_10]
0x18001737e  jnz     loc_1800174CE
0x180017384  sub     [rdi], ebx
0x180017386  mov     rax, rsi
0x180017389  add     rsp, 40h
0x18001738d  pop     r14
0x18001738f  pop     rdi
0x180017390  pop     rsi
0x180017391  pop     rbx
0x180017392  pop     rbp
0x180017393  retn
0x180017394  mov     ecx, eax; int
0x180017396  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18001739c  mov     ecx, eax; int
0x18001739e  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800173a4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800173aa  mov     edx, 0FFFFFFFEh
0x1800173af  mov     rcx, rax
0x1800173b2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800173b8  lea     rax, WPP_GLOBAL_Control
0x1800173bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173c6  cmp     rcx, rax
0x1800173c9  jz      short loc_1800173F3
0x1800173cb  test    byte ptr [rcx+1Ch], 1
0x1800173cf  jz      short loc_1800173F3
0x1800173d1  cmp     byte ptr [rcx+19h], 2
0x1800173d5  jb      short loc_1800173F3
0x1800173d7  mov     edx, 0Bh
0x1800173dc  lea     r9, aCxException; "CX_Exception()"
0x1800173e3  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x1800173ea  mov     rcx, [rcx+10h]
0x1800173ee  call    WPP_SF_s
0x1800173f3  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x1800173fa  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800173fe  call    _CxxThrowException_0
0x180017404  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001740a  mov     edx, 0FFFFFFFEh
0x18001740f  mov     rcx, rax
0x180017412  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017418  lea     rax, WPP_GLOBAL_Control
0x18001741f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017426  cmp     rcx, rax
0x180017429  jz      short loc_180017453
0x18001742b  test    byte ptr [rcx+1Ch], 1
0x18001742f  jz      short loc_180017453
0x180017431  cmp     byte ptr [rcx+19h], 2
0x180017435  jb      short loc_180017453
0x180017437  mov     edx, 0Ch
0x18001743c  lea     r9, aCxException; "CX_Exception()"
0x180017443  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x18001744a  mov     rcx, [rcx+10h]
0x18001744e  call    WPP_SF_s
0x180017453  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001745a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001745e  call    _CxxThrowException_0
0x180017464  cmp     [rbp+ui], 0
0x180017468  jz      loc_180017361
0x18001746e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017474  mov     edx, 0FFFFFFFEh
0x180017479  mov     rcx, rax
0x18001747c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017482  lea     rax, WPP_GLOBAL_Control
0x180017489  mov     rcx, cs:WPP_GLOBAL_Control
0x180017490  cmp     rcx, rax
0x180017493  jz      short loc_1800174BD
0x180017495  test    byte ptr [rcx+1Ch], 1
0x180017499  jz      short loc_1800174BD
0x18001749b  cmp     byte ptr [rcx+19h], 2
0x18001749f  jb      short loc_1800174BD
0x1800174a1  mov     edx, 0Dh
0x1800174a6  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800174ad  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x1800174b4  mov     rcx, [rcx+10h]
0x1800174b8  call    WPP_SF_s
0x1800174bd  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800174c4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800174c8  call    _CxxThrowException_0
0x1800174ce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800174d4  mov     edx, 0FFFFFFFEh
0x1800174d9  mov     rcx, rax
0x1800174dc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800174e2  lea     rax, WPP_GLOBAL_Control
0x1800174e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174f0  cmp     rcx, rax
0x1800174f3  jz      short loc_18001751D
0x1800174f5  test    byte ptr [rcx+1Ch], 1
0x1800174f9  jz      short loc_18001751D
0x1800174fb  cmp     byte ptr [rcx+19h], 2
0x1800174ff  jb      short loc_18001751D
0x180017501  mov     edx, 0Eh
0x180017506  lea     r9, aCxException; "CX_Exception()"
0x18001750d  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180017514  mov     rcx, [rcx+10h]
0x180017518  call    WPP_SF_s
0x18001751d  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180017524  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017528  call    _CxxThrowException_0
```
