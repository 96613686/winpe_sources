# CWbemObject::GetFullPath(void)

- ea: `0x180034a80`
- end: `0x180034cef`
- name: `?GetFullPath@CWbemObject@@QEAAPEAGXZ`
- size: `623`
- prototype: `unsigned __int16 *__fastcall(CWbemObject *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800060f0`

## callees

- `0x18000b360`
- `0x180034a80`
- `0x180034cf8`
- `0x180035b08`
- `0x18006d500`
- `0x18006fa4c`
- `0x1800700c8`
- `0x180076a78`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180034bc0`
- `wbemcomn!GetMemLogObject` at `0x180034bfa`
- `wbemcomn!GetMemLogObject` at `0x180034c8e`
- `wbemcomn!GetMemLogObject` at `0x180034bc0`
- `wbemcomn!GetMemLogObject` at `0x180034bfa`
- `wbemcomn!GetMemLogObject` at `0x180034c8e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034bcf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034c08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034c9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034bcf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034c08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034c9c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180034b50`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180034b50`
- `OLEAUT32!__imp_SysFreeString` at `0x180034b85`
- `OLEAUT32!__imp_SysFreeString` at `0x180034b8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180034b85`
- `OLEAUT32!__imp_SysFreeString` at `0x180034b8f`
- `OLEAUT32!__imp_SysStringLen` at `0x180034b27`
- `OLEAUT32!__imp_SysStringLen` at `0x180034b32`
- `OLEAUT32!__imp_SysStringLen` at `0x180034b27`
- `OLEAUT32!__imp_SysStringLen` at `0x180034b32`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
unsigned __int16 *__fastcall CWbemObject::GetFullPath(CWbemObject *this)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  OLECHAR *BSTRCopy; // rsi
  OLECHAR *v5; // rbp
  __int64 v6; // rax
  __int64 v7; // r14
  UINT v8; // edi
  unsigned __int64 v9; // r14
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *MemLogObject; // rax
  char pExceptionObject; // [rsp+70h] [rbp+8h] BYREF
  __int64 v17; // [rsp+78h] [rbp+10h] BYREF
  OLECHAR *v18; // [rsp+80h] [rbp+18h]
  OLECHAR *v19; // [rsp+88h] [rbp+20h]

  if ( (**((_BYTE **)this + 9) & 4) == 0 )
    return 0;
  v2 = (*(__int64 (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 1040LL))(this, 0);
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v17, v2);
  v3 = v17;
  if ( !v17 )
  {
    std::unique_ptr<_WBEM_RECONNECT_RESULTS [0]>::~unique_ptr<_WBEM_RECONNECT_RESULTS [0]>(&v17);
    return 0;
  }
  BSTRCopy = CCompressedString::CreateBSTRCopy(*((CCompressedString **)this + 10));
  v18 = BSTRCopy;
  if ( !BSTRCopy )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v5 = CCompressedString::CreateBSTRCopy(*((CCompressedString **)this + 11));
  v19 = v5;
  if ( !v5 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v6 = std::unique_ptr<CClassInfo>::operator->(&v17);
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v6 + 2 * v7) );
  v8 = SysStringLen(v5);
  v9 = v8 + SysStringLen(BSTRCopy) + 10LL + v7;
  v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v9, 2u));
  v11 = v10;
  if ( !v10 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  StringCchPrintfW(v10, v9, L"\\\\%s\\%s:%s", BSTRCopy, v5, v3);
  SysFreeString(v5);
  SysFreeString(BSTRCopy);
  std::unique_ptr<_WBEM_RECONNECT_RESULTS [0]>::~unique_ptr<_WBEM_RECONNECT_RESULTS [0]>(&v17);
  return v11;
}

```

## disassembly

```asm
0x180034a80  push    rbx
0x180034a82  push    rbp
0x180034a83  push    rsi
0x180034a84  push    rdi
0x180034a85  push    r12
0x180034a87  push    r14
0x180034a89  push    r15
0x180034a8b  sub     rsp, 30h
0x180034a8f  mov     rdi, rcx
0x180034a92  mov     rax, [rcx+48h]
0x180034a96  test    byte ptr [rax], 4
0x180034a99  jz      loc_180034BBC
0x180034a9f  mov     rax, [rcx]
0x180034aa2  xor     edx, edx
0x180034aa4  mov     rax, [rax+410h]
0x180034aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ab0  mov     rdx, rax
0x180034ab3  lea     rcx, [rsp+68h+arg_8]
0x180034ab8  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180034abd  nop
0x180034abe  mov     rbx, [rsp+68h+arg_8]
0x180034ac3  xor     r15d, r15d
0x180034ac6  test    rbx, rbx
0x180034ac9  jz      loc_180034BB2
0x180034acf  mov     rcx, [rdi+50h]; this
0x180034ad3  call    ?CreateBSTRCopy@CCompressedString@@QEBAPEAGXZ; CCompressedString::CreateBSTRCopy(void)
0x180034ad8  mov     rsi, rax
0x180034adb  mov     [rsp+68h+arg_10], rax
0x180034ae3  test    rax, rax
0x180034ae6  jz      loc_180034C8E
0x180034aec  mov     rcx, [rdi+58h]; this
0x180034af0  call    ?CreateBSTRCopy@CCompressedString@@QEBAPEAGXZ; CCompressedString::CreateBSTRCopy(void)
0x180034af5  mov     rbp, rax
0x180034af8  mov     [rsp+68h+arg_18], rax
0x180034b00  test    rax, rax
0x180034b03  jz      loc_180034BC0
0x180034b09  lea     rcx, [rsp+68h+arg_8]
0x180034b0e  call    ??C?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEBAPEAUCClassInfo@@XZ; std::unique_ptr<CClassInfo>::operator->(void)
0x180034b13  or      r12, 0FFFFFFFFFFFFFFFFh
0x180034b17  mov     r14, r12
0x180034b1a  inc     r14
0x180034b1d  cmp     [rax+r14*2], r15w
0x180034b22  jnz     short loc_180034B1A
0x180034b24  mov     rcx, rbp; pbstr
0x180034b27  call    cs:__imp_SysStringLen
0x180034b2d  mov     edi, eax
0x180034b2f  mov     rcx, rsi; pbstr
0x180034b32  call    cs:__imp_SysStringLen
0x180034b38  add     eax, edi
0x180034b3a  add     rax, 0Ah
0x180034b3e  add     r14, rax
0x180034b41  mov     eax, 2
0x180034b46  mul     r14
0x180034b49  cmovb   rax, r12
0x180034b4d  mov     rcx, rax
0x180034b50  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180034b56  mov     rdi, rax
0x180034b59  test    rax, rax
0x180034b5c  jz      loc_180034BFA
0x180034b62  mov     [rsp+68h+var_40], rbx
0x180034b67  mov     [rsp+68h+var_48], rbp
0x180034b6c  mov     r9, rsi
0x180034b6f  lea     r8, aSSS; "\\\\%s\\%s:%s"
0x180034b76  mov     rdx, r14; unsigned __int64
0x180034b79  mov     rcx, rax; unsigned __int16 *
0x180034b7c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034b81  nop
0x180034b82  mov     rcx, rbp; bstrString
0x180034b85  call    cs:__imp_SysFreeString
0x180034b8b  nop
0x180034b8c  mov     rcx, rsi; bstrString
0x180034b8f  call    cs:__imp_SysFreeString
0x180034b95  nop
0x180034b96  lea     rcx, [rsp+68h+arg_8]
0x180034b9b  call    ??1?$unique_ptr@$$BY0A@U_WBEM_RECONNECT_RESULTS@@U?$default_delete@$$BY0A@U_WBEM_RECONNECT_RESULTS@@@std@@@std@@QEAA@XZ; std::unique_ptr<_WBEM_RECONNECT_RESULTS [0]>::~unique_ptr<_WBEM_RECONNECT_RESULTS [0]>(void)
0x180034ba0  mov     rax, rdi
0x180034ba3  add     rsp, 30h
0x180034ba7  pop     r15
0x180034ba9  pop     r14
0x180034bab  pop     r12
0x180034bad  pop     rdi
0x180034bae  pop     rsi
0x180034baf  pop     rbp
0x180034bb0  pop     rbx
0x180034bb1  retn
0x180034bb2  lea     rcx, [rsp+68h+arg_8]
0x180034bb7  call    ??1?$unique_ptr@$$BY0A@U_WBEM_RECONNECT_RESULTS@@U?$default_delete@$$BY0A@U_WBEM_RECONNECT_RESULTS@@@std@@@std@@QEAA@XZ; std::unique_ptr<_WBEM_RECONNECT_RESULTS [0]>::~unique_ptr<_WBEM_RECONNECT_RESULTS [0]>(void)
0x180034bbc  xor     eax, eax
0x180034bbe  jmp     short loc_180034BA3
0x180034bc0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180034bc6  nop
0x180034bc7  mov     edx, 0FFFFFFFEh
0x180034bcc  mov     rcx, rax
0x180034bcf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034bd5  lea     rax, WPP_GLOBAL_Control
0x180034bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180034be3  cmp     rcx, rax
0x180034be6  jnz     short loc_180034C5D
0x180034be8  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180034bef  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180034bf4  call    _CxxThrowException_0
0x180034bfa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180034c00  mov     edx, 0FFFFFFFEh
0x180034c05  mov     rcx, rax
0x180034c08  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034c0e  lea     rax, WPP_GLOBAL_Control
0x180034c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180034c1c  cmp     rcx, rax
0x180034c1f  jnz     short loc_180034C33
0x180034c21  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180034c28  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180034c2d  call    _CxxThrowException_0
0x180034c33  test    byte ptr [rcx+1Ch], 1
0x180034c37  jz      short loc_180034C21
0x180034c39  cmp     byte ptr [rcx+19h], 2
0x180034c3d  jb      short loc_180034C21
0x180034c3f  mov     edx, 2Dh ; '-'
0x180034c44  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180034c4b  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x180034c52  mov     rcx, [rcx+10h]
0x180034c56  call    WPP_SF_s
0x180034c5b  jmp     short loc_180034C21
0x180034c5d  test    byte ptr [rcx+1Ch], 1
0x180034c61  jz      short loc_180034BE8
0x180034c63  cmp     byte ptr [rcx+19h], 2
0x180034c67  jb      loc_180034BE8
0x180034c6d  mov     edx, 2Eh ; '.'
0x180034c72  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180034c79  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x180034c80  mov     rcx, [rcx+10h]
0x180034c84  call    WPP_SF_s
0x180034c89  jmp     loc_180034BE8
0x180034c8e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180034c94  mov     edx, 0FFFFFFFEh
0x180034c99  mov     rcx, rax
0x180034c9c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034ca2  lea     rax, WPP_GLOBAL_Control
0x180034ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180034cb0  cmp     rcx, rax
0x180034cb3  jz      short loc_180034CDD
0x180034cb5  test    byte ptr [rcx+1Ch], 1
0x180034cb9  jz      short loc_180034CDD
0x180034cbb  cmp     byte ptr [rcx+19h], 2
0x180034cbf  jb      short loc_180034CDD
0x180034cc1  mov     edx, 2Fh ; '/'
0x180034cc6  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180034ccd  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x180034cd4  mov     rcx, [rcx+10h]
0x180034cd8  call    WPP_SF_s
0x180034cdd  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180034ce4  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180034ce9  call    _CxxThrowException_0
```
