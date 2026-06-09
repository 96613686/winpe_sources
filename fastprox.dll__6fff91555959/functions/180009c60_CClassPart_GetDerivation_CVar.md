# CClassPart::GetDerivation(CVar *)

- ea: `0x180009c60`
- end: `0x180009fbe`
- name: `?GetDerivation@CClassPart@@QEAAJPEAVCVar@@@Z`
- size: `862`
- prototype: `__int64 __fastcall(CClassPart *__hidden this, struct CVar *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006030`
- `0x180059a80`

## callees

- `0x180009c60`
- `0x18000b360`
- `0x18001e1b0`
- `0x180037120`
- `0x1800700c8`
- `0x18007212c`
- `0x1800728c8`
- `0x1800728f8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180009e07`
- `wbemcomn!GetMemLogObject` at `0x180009e75`
- `wbemcomn!GetMemLogObject` at `0x180009ee3`
- `wbemcomn!GetMemLogObject` at `0x180009f51`
- `wbemcomn!GetMemLogObject` at `0x180009e07`
- `wbemcomn!GetMemLogObject` at `0x180009e75`
- `wbemcomn!GetMemLogObject` at `0x180009ee3`
- `wbemcomn!GetMemLogObject` at `0x180009f51`
- `wbemcomn!?SetVarVector@CVar@@QEAAXPEAVCVarVector@@H@Z` at `0x180009dd4`
- `wbemcomn!?SetVarVector@CVar@@QEAAXPEAVCVarVector@@H@Z` at `0x180009dd4`
- `wbemcomn!??0CVarVector@@QEAA@HHH@Z` at `0x180009c9a`
- `wbemcomn!??0CVarVector@@QEAA@HHH@Z` at `0x180009c9a`
- `wbemcomn!?Add@CVarVector@@QEAAHPEAVCVar@@@Z` at `0x180009d50`
- `wbemcomn!?Add@CVarVector@@QEAAHPEAVCVar@@@Z` at `0x180009d50`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180009ced`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180009ced`
- `wbemcomn!?SetBSTR@CVar@@QEAAHVauto_bstr@@@Z` at `0x180009d38`
- `wbemcomn!?SetBSTR@CVar@@QEAAHVauto_bstr@@@Z` at `0x180009d38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009e15`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009e83`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009ef1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009f5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009e15`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009e83`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009ef1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009f5f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009c7b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009cda`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009c7b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009cda`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CClassPart::GetDerivation(CClassPart *this, struct CVar *a2)
{
  CVar *v4; // rax
  _DWORD *v5; // rax
  _DWORD *v6; // rsi
  CVarVector *v7; // rax
  unsigned __int16 *BSTRCopy; // rax
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // r8
  unsigned int v12; // edx
  __int64 result; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned int v17; // edx
  CMemoryLog *v18; // rax
  unsigned int v19; // edx
  CMemoryLog *v20; // rax
  CVarVector *v21[5]; // [rsp+20h] [rbp-28h] BYREF
  CVar *v22; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v23; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    v4 = (CVar *)CWin32DefaultArena::WbemMemAlloc(0x78u);
    v22 = v4;
    if ( v4 )
      v4 = CVarVector::CVarVector(v4, 8, 32, 32);
    std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(v21, (__int64)v4);
    if ( v21[0] )
    {
      v5 = (_DWORD *)*((_QWORD *)this + 7);
      v6 = 0;
      if ( *v5 != 4 )
        v6 = v5 + 1;
      while ( 1 )
      {
        if ( !v6 )
        {
          CVar::SetVarVector(a2, v21[0], 1);
          std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(v21);
          std::unique_ptr<CVarVector>::~unique_ptr<CVarVector>(v21, v12);
          return 0;
        }
        v7 = (CVarVector *)CWin32DefaultArena::WbemMemAlloc(0x20u);
        v21[1] = v7;
        if ( v7 )
          v7 = CVar::CVar(v7);
        std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v22, (__int64)v7);
        if ( !v22 )
          break;
        BSTRCopy = CCompressedString::CreateBSTRCopy((CCompressedString *)v6);
        if ( !BSTRCopy || (v21[2] = (CVarVector *)&v23, v23 = BSTRCopy, !(unsigned int)CVar::SetBSTR(v22, &v23)) )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749894LL);
          }
          goto LABEL_37;
        }
        if ( CVarVector::Add(v21[0], v22) )
        {
          v15 = GetMemLogObject();
          CMemoryLog::Write(v15, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              45,
              WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
              2147749894LL);
          }
          goto LABEL_37;
        }
        std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v22);
        if ( *(_BYTE *)v6 == 1 )
        {
          LODWORD(v9) = CCompressedString::fast_wcslen((const unsigned __int16 *)((char *)v6 + 1));
          v10 = 2;
        }
        else
        {
          v9 = -1;
          do
            ++v9;
          while ( *((_BYTE *)v6 + v9 + 1) );
          v10 = 1;
        }
        v11 = (__int64)v6 + v10 * ((int)v9 + 1) + 5;
        v6 = 0;
        if ( v11 - *((_QWORD *)this + 7) < **((int **)this + 7) )
          v6 = (_DWORD *)v11;
        std::unique_ptr<CVar>::~unique_ptr<CVar>(&v22);
      }
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
      }
LABEL_37:
      std::unique_ptr<CVar>::~unique_ptr<CVar>(&v22);
      std::unique_ptr<CVarVector>::~unique_ptr<CVarVector>(v21, v17);
      result = 2147749894LL;
    }
    else
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
      }
      std::unique_ptr<CVarVector>::~unique_ptr<CVarVector>(v21, v19);
      result = 2147749894LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x180009c60  mov     [rsp+arg_0], rsi
0x180009c65  mov     [rsp+arg_8], r12
0x180009c6a  push    r15
0x180009c6c  sub     rsp, 40h
0x180009c70  mov     r12, rdx
0x180009c73  mov     r15, rcx
0x180009c76  mov     ecx, 78h ; 'x'
0x180009c7b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009c81  mov     [rsp+48h+arg_10], rax
0x180009c86  test    rax, rax
0x180009c89  jz      short loc_180009CA1
0x180009c8b  mov     edx, 8
0x180009c90  lea     r9d, [rdx+18h]
0x180009c94  mov     r8d, r9d
0x180009c97  mov     rcx, rax
0x180009c9a  call    cs:__imp_??0CVarVector@@QEAA@HHH@Z; CVarVector::CVarVector(int,int,int)
0x180009ca0  nop
0x180009ca1  mov     rdx, rax
0x180009ca4  lea     rcx, [rsp+48h+var_28]
0x180009ca9  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180009cae  nop
0x180009caf  cmp     [rsp+48h+var_28], 0
0x180009cb5  jz      loc_180009F51
0x180009cbb  mov     rax, [r15+38h]
0x180009cbf  lea     rcx, [rax+4]
0x180009cc3  xor     esi, esi
0x180009cc5  cmp     dword ptr [rax], 4
0x180009cc8  cmovnz  rsi, rcx
0x180009ccc  test    rsi, rsi
0x180009ccf  jz      loc_180009DC6
0x180009cd5  mov     ecx, 20h ; ' '
0x180009cda  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009ce0  mov     [rsp+48h+var_20], rax
0x180009ce5  test    rax, rax
0x180009ce8  jz      short loc_180009CF4
0x180009cea  mov     rcx, rax
0x180009ced  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180009cf3  nop
0x180009cf4  mov     rdx, rax
0x180009cf7  lea     rcx, [rsp+48h+arg_10]
0x180009cfc  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180009d01  nop
0x180009d02  cmp     [rsp+48h+arg_10], 0
0x180009d08  jz      loc_180009E07
0x180009d0e  mov     rcx, rsi; this
0x180009d11  call    ?CreateBSTRCopy@CCompressedString@@QEBAPEAGXZ; CCompressedString::CreateBSTRCopy(void)
0x180009d16  test    rax, rax
0x180009d19  jz      loc_180009EE3
0x180009d1f  lea     rcx, [rsp+48h+arg_18]
0x180009d24  mov     [rsp+48h+var_18], rcx
0x180009d29  mov     [rsp+48h+arg_18], rax
0x180009d2e  lea     rdx, [rsp+48h+arg_18]
0x180009d33  mov     rcx, [rsp+48h+arg_10]
0x180009d38  call    cs:__imp_?SetBSTR@CVar@@QEAAHVauto_bstr@@@Z; CVar::SetBSTR(auto_bstr)
0x180009d3e  test    eax, eax
0x180009d40  jz      loc_180009EE3
0x180009d46  mov     rdx, [rsp+48h+arg_10]
0x180009d4b  mov     rcx, [rsp+48h+var_28]
0x180009d50  call    cs:__imp_?Add@CVarVector@@QEAAHPEAVCVar@@@Z; CVarVector::Add(CVar *)
0x180009d56  test    eax, eax
0x180009d58  jnz     loc_180009E75
0x180009d5e  lea     rcx, [rsp+48h+arg_10]
0x180009d63  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180009d68  cmp     byte ptr [rsi], 1
0x180009d6b  jz      short loc_180009DB6
0x180009d6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009d71  inc     rax
0x180009d74  cmp     byte ptr [rsi+rax+1], 0
0x180009d79  jnz     short loc_180009D71
0x180009d7b  mov     ecx, 1
0x180009d80  inc     eax
0x180009d82  imul    eax, ecx
0x180009d85  inc     eax
0x180009d87  movsxd  r8, eax
0x180009d8a  add     rsi, 4
0x180009d8e  add     r8, rsi
0x180009d91  mov     rax, [r15+38h]
0x180009d95  mov     rdx, r8
0x180009d98  sub     rdx, rax
0x180009d9b  movsxd  rcx, dword ptr [rax]
0x180009d9e  xor     esi, esi
0x180009da0  cmp     rdx, rcx
0x180009da3  cmovl   rsi, r8
0x180009da7  lea     rcx, [rsp+48h+arg_10]
0x180009dac  call    ??1?$unique_ptr@VCVar@@U?$default_delete@VCVar@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVar>::~unique_ptr<CVar>(void)
0x180009db1  jmp     loc_180009CCC
0x180009db6  lea     rcx, [rsi+1]; unsigned __int16 *
0x180009dba  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x180009dbf  mov     ecx, 2
0x180009dc4  jmp     short loc_180009D80
0x180009dc6  mov     r8d, 1
0x180009dcc  mov     rdx, [rsp+48h+var_28]
0x180009dd1  mov     rcx, r12
0x180009dd4  call    cs:__imp_?SetVarVector@CVar@@QEAAXPEAVCVarVector@@H@Z; CVar::SetVarVector(CVarVector *,int)
0x180009dda  lea     rcx, [rsp+48h+var_28]
0x180009ddf  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180009de4  nop
0x180009de5  lea     rcx, [rsp+48h+var_28]
0x180009dea  call    ??1?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVarVector>::~unique_ptr<CVarVector>(void)
0x180009def  xor     eax, eax
0x180009df1  mov     rsi, [rsp+48h+arg_0]
0x180009df6  mov     r12, [rsp+48h+arg_8]
0x180009dfb  add     rsp, 40h
0x180009dff  pop     r15
0x180009e01  retn
0x180009e02  jmp     loc_180009CA1
0x180009e07  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009e0d  mov     edx, 80041006h
0x180009e12  mov     rcx, rax
0x180009e15  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009e1b  lea     rax, WPP_GLOBAL_Control
0x180009e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e29  cmp     rcx, rax
0x180009e2c  jz      short loc_180009E56
0x180009e2e  test    byte ptr [rcx+1Ch], 1
0x180009e32  jz      short loc_180009E56
0x180009e34  cmp     byte ptr [rcx+19h], 2
0x180009e38  jb      short loc_180009E56
0x180009e3a  mov     edx, 2Bh ; '+'
0x180009e3f  mov     r9d, 80041006h
0x180009e45  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180009e4c  mov     rcx, [rcx+10h]
0x180009e50  call    WPP_SF_d
0x180009e55  nop
0x180009e56  lea     rcx, [rsp+48h+arg_10]
0x180009e5b  call    ??1?$unique_ptr@VCVar@@U?$default_delete@VCVar@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVar>::~unique_ptr<CVar>(void)
0x180009e60  nop
0x180009e61  lea     rcx, [rsp+48h+var_28]
0x180009e66  call    ??1?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVarVector>::~unique_ptr<CVarVector>(void)
0x180009e6b  mov     eax, 80041006h
0x180009e70  jmp     loc_180009DF1
0x180009e75  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009e7b  mov     edx, 80041006h
0x180009e80  mov     rcx, rax
0x180009e83  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009e89  lea     rax, WPP_GLOBAL_Control
0x180009e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e97  cmp     rcx, rax
0x180009e9a  jz      short loc_180009EC4
0x180009e9c  test    byte ptr [rcx+1Ch], 1
0x180009ea0  jz      short loc_180009EC4
0x180009ea2  cmp     byte ptr [rcx+19h], 2
0x180009ea6  jb      short loc_180009EC4
0x180009ea8  mov     edx, 2Dh ; '-'
0x180009ead  mov     r9d, 80041006h
0x180009eb3  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180009eba  mov     rcx, [rcx+10h]
0x180009ebe  call    WPP_SF_d
0x180009ec3  nop
0x180009ec4  lea     rcx, [rsp+48h+arg_10]
0x180009ec9  call    ??1?$unique_ptr@VCVar@@U?$default_delete@VCVar@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVar>::~unique_ptr<CVar>(void)
0x180009ece  nop
0x180009ecf  lea     rcx, [rsp+48h+var_28]
0x180009ed4  call    ??1?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVarVector>::~unique_ptr<CVarVector>(void)
0x180009ed9  mov     eax, 80041006h
0x180009ede  jmp     loc_180009DF1
0x180009ee3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009ee9  mov     edx, 80041006h
0x180009eee  mov     rcx, rax
0x180009ef1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009ef7  lea     rax, WPP_GLOBAL_Control
0x180009efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f05  cmp     rcx, rax
0x180009f08  jz      short loc_180009F32
0x180009f0a  test    byte ptr [rcx+1Ch], 1
0x180009f0e  jz      short loc_180009F32
0x180009f10  cmp     byte ptr [rcx+19h], 2
0x180009f14  jb      short loc_180009F32
0x180009f16  mov     edx, 2Ch ; ','
0x180009f1b  mov     r9d, 80041006h
0x180009f21  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180009f28  mov     rcx, [rcx+10h]
0x180009f2c  call    WPP_SF_d
0x180009f31  nop
0x180009f32  lea     rcx, [rsp+48h+arg_10]
0x180009f37  call    ??1?$unique_ptr@VCVar@@U?$default_delete@VCVar@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVar>::~unique_ptr<CVar>(void)
0x180009f3c  nop
0x180009f3d  lea     rcx, [rsp+48h+var_28]
0x180009f42  call    ??1?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVarVector>::~unique_ptr<CVarVector>(void)
0x180009f47  mov     eax, 80041006h
0x180009f4c  jmp     loc_180009DF1
0x180009f51  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009f57  mov     edx, 80041006h
0x180009f5c  mov     rcx, rax
0x180009f5f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009f65  lea     rax, WPP_GLOBAL_Control
0x180009f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f73  cmp     rcx, rax
0x180009f76  jz      short loc_180009FA0
0x180009f78  test    byte ptr [rcx+1Ch], 1
0x180009f7c  jz      short loc_180009FA0
0x180009f7e  cmp     byte ptr [rcx+19h], 2
0x180009f82  jb      short loc_180009FA0
0x180009f84  mov     edx, 2Eh ; '.'
0x180009f89  mov     r9d, 80041006h
0x180009f8f  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180009f96  mov     rcx, [rcx+10h]
0x180009f9a  call    WPP_SF_d
0x180009f9f  nop
0x180009fa0  lea     rcx, [rsp+48h+var_28]
0x180009fa5  call    ??1?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<CVarVector>::~unique_ptr<CVarVector>(void)
0x180009faa  mov     eax, 80041006h
0x180009faf  jmp     loc_180009DF1
0x180009fb4  mov     eax, 80041006h
0x180009fb9  jmp     loc_180009DF1
```
