# CUniversalRefresher::CNonHiPerf::CEnumRequest::CEnumRequest(CClientLoadableHiPerfEnum *,ushort const *,CLifeControl *)

- ea: `0x180085c50`
- end: `0x180085ea6`
- name: `??0CEnumRequest@CNonHiPerf@CUniversalRefresher@@QEAA@PEAVCClientLoadableHiPerfEnum@@PEBGPEAVCLifeControl@@@Z`
- size: `598`
- prototype: `CUniversalRefresher::CNonHiPerf::CEnumRequest *__fastcall(CUniversalRefresher::CNonHiPerf::CEnumRequest *this, struct CClientLoadableHiPerfEnum *, const unsigned __int16 *, struct CLifeControl *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180086d1c`

## callees

- `0x180035b08`
- `0x18004a7c8`
- `0x18004b274`
- `0x18004b31c`
- `0x18006fa4c`
- `0x1800700c8`
- `0x18007212c`
- `0x180085c50`
- `0x180085fa8`
- `0x180086588`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180085cb5`
- `wbemcomn!GetMemLogObject` at `0x180085d47`
- `wbemcomn!GetMemLogObject` at `0x180085db9`
- `wbemcomn!GetMemLogObject` at `0x180085cb5`
- `wbemcomn!GetMemLogObject` at `0x180085d47`
- `wbemcomn!GetMemLogObject` at `0x180085db9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085cc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085d55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085dc7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085cc1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085d55`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085dc7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180085d16`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180085d16`

## string_xrefs

- `0x180085e45`: `ComException(hr)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CUniversalRefresher::CNonHiPerf::CEnumRequest *__fastcall CUniversalRefresher::CNonHiPerf::CEnumRequest::CEnumRequest(
        CUniversalRefresher::CNonHiPerf::CEnumRequest *this,
        struct CClientLoadableHiPerfEnum *a2,
        const unsigned __int16 *a3,
        struct CLifeControl *a4)
{
  struct CWbemInstance *InstanceTemplate; // rbx
  CMemoryLog *MemLogObject; // rax
  CReadOnlyHiPerfEnum *v9; // rax
  CMemoryLog *v10; // rax
  int v11; // ebx
  CMemoryLog *v12; // rax
  __int64 v13; // rax
  CHiPerfEnum *v15; // [rsp+20h] [rbp-20h] BYREF
  void **v16; // [rsp+28h] [rbp-18h] BYREF
  int v17; // [rsp+30h] [rbp-10h]
  CReadOnlyHiPerfEnum *pExceptionObject; // [rsp+68h] [rbp+28h] BYREF

  CUniversalRefresher::CNonHiPerf::CObjectRequest::CObjectRequest(this, 0, 0, a3);
  *(_QWORD *)this = &CUniversalRefresher::CNonHiPerf::CEnumRequest::`vftable';
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = 0;
  if ( a2 )
    (*(void (__fastcall **)(struct CClientLoadableHiPerfEnum *))(*(_QWORD *)a2 + 8LL))(a2);
  InstanceTemplate = CHiPerfEnum::GetInstanceTemplate(a2);
  if ( !InstanceTemplate )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        125,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v9 = (CReadOnlyHiPerfEnum *)CWin32DefaultArena::WbemMemAlloc(0x188u);
  pExceptionObject = v9;
  if ( v9 )
    v9 = CReadOnlyHiPerfEnum::CReadOnlyHiPerfEnum(v9, a4);
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v15, (__int64)v9);
  if ( !v15 )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v11 = CHiPerfEnum::SetInstanceTemplate(v15, InstanceTemplate);
  if ( v11 < 0 )
  {
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, -2);
    if ( v11 == -2147217402 )
    {
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          127,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        128,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        "ComException(hr)");
    }
    v16 = &ComException::`vftable';
    v17 = v11;
    throw (ComException *)&v16;
  }
  v13 = std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v15);
  *((_QWORD *)this + 6) = v13;
  _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  std::unique_ptr<CReadOnlyHiPerfEnum>::~unique_ptr<CReadOnlyHiPerfEnum>(&v15);
  return this;
}

```

## disassembly

```asm
0x180085c50  mov     [rsp-18h+arg_10], rbx
0x180085c55  mov     [rsp-18h+arg_0], rcx
0x180085c5a  push    rbp
0x180085c5b  push    rsi
0x180085c5c  push    rdi
0x180085c5d  mov     rbp, rsp
0x180085c60  sub     rsp, 40h
0x180085c64  mov     rsi, r9
0x180085c67  mov     rbx, rdx
0x180085c6a  mov     rdi, rcx
0x180085c6d  mov     r9, r8; unsigned __int16 *
0x180085c70  xor     r8d, r8d; struct CWbemObject *
0x180085c73  xor     edx, edx; struct CWbemObject *
0x180085c75  call    ??0CObjectRequest@CNonHiPerf@CUniversalRefresher@@QEAA@PEAVCWbemObject@@0PEBG@Z; CUniversalRefresher::CNonHiPerf::CObjectRequest::CObjectRequest(CWbemObject *,CWbemObject *,ushort const *)
0x180085c7a  nop
0x180085c7b  lea     rax, ??_7CEnumRequest@CNonHiPerf@CUniversalRefresher@@6B@; const CUniversalRefresher::CNonHiPerf::CEnumRequest::`vftable'
0x180085c82  mov     [rdi], rax
0x180085c85  mov     [rdi+28h], rbx
0x180085c89  mov     qword ptr [rdi+30h], 0
0x180085c91  test    rbx, rbx
0x180085c94  jz      short loc_180085CA5
0x180085c96  mov     rax, [rbx]
0x180085c99  mov     rcx, rbx
0x180085c9c  mov     rax, [rax+8]
0x180085ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ca5  mov     rcx, rbx; this
0x180085ca8  call    ?GetInstanceTemplate@CHiPerfEnum@@QEAAPEAVCWbemInstance@@XZ; CHiPerfEnum::GetInstanceTemplate(void)
0x180085cad  mov     rbx, rax
0x180085cb0  test    rax, rax
0x180085cb3  jnz     short loc_180085D11
0x180085cb5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085cbb  lea     edx, [rbx-2]
0x180085cbe  mov     rcx, rax
0x180085cc1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085cc7  lea     rax, WPP_GLOBAL_Control
0x180085cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180085cd5  cmp     rcx, rax
0x180085cd8  jz      short loc_180085D00
0x180085cda  test    byte ptr [rcx+1Ch], 1
0x180085cde  jz      short loc_180085D00
0x180085ce0  cmp     byte ptr [rcx+19h], 2
0x180085ce4  jb      short loc_180085D00
0x180085ce6  lea     edx, [rbx+7Dh]
0x180085ce9  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180085cf0  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180085cf7  mov     rcx, [rcx+10h]
0x180085cfb  call    WPP_SF_s
0x180085d00  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180085d07  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180085d0b  call    _CxxThrowException_0
0x180085d11  mov     ecx, 188h
0x180085d16  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180085d1c  mov     [rbp+pExceptionObject], rax
0x180085d20  test    rax, rax
0x180085d23  jz      short loc_180085D31
0x180085d25  mov     rdx, rsi; struct CLifeControl *
0x180085d28  mov     rcx, rax; this
0x180085d2b  call    ??0CReadOnlyHiPerfEnum@@QEAA@PEAVCLifeControl@@@Z; CReadOnlyHiPerfEnum::CReadOnlyHiPerfEnum(CLifeControl *)
0x180085d30  nop
0x180085d31  mov     rdx, rax
0x180085d34  lea     rcx, [rbp+var_20]
0x180085d38  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180085d3d  nop
0x180085d3e  mov     rcx, [rbp+var_20]; this
0x180085d42  test    rcx, rcx
0x180085d45  jnz     short loc_180085DA7
0x180085d47  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085d4d  mov     edx, 0FFFFFFFEh
0x180085d52  mov     rcx, rax
0x180085d55  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085d5b  lea     rax, WPP_GLOBAL_Control
0x180085d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180085d69  cmp     rcx, rax
0x180085d6c  jz      short loc_180085D96
0x180085d6e  test    byte ptr [rcx+1Ch], 1
0x180085d72  jz      short loc_180085D96
0x180085d74  cmp     byte ptr [rcx+19h], 2
0x180085d78  jb      short loc_180085D96
0x180085d7a  mov     edx, 7Eh ; '~'
0x180085d7f  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180085d86  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180085d8d  mov     rcx, [rcx+10h]
0x180085d91  call    WPP_SF_s
0x180085d96  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180085d9d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180085da1  call    _CxxThrowException_0
0x180085da7  mov     rdx, rbx; struct CWbemInstance *
0x180085daa  call    ?SetInstanceTemplate@CHiPerfEnum@@QEAAJPEAVCWbemInstance@@@Z; CHiPerfEnum::SetInstanceTemplate(CWbemInstance *)
0x180085daf  mov     ebx, eax
0x180085db1  test    eax, eax
0x180085db3  jns     loc_180085E7B
0x180085db9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085dbf  mov     edx, 0FFFFFFFEh
0x180085dc4  mov     rcx, rax
0x180085dc7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085dcd  cmp     ebx, 80041006h
0x180085dd3  jnz     short loc_180085E21
0x180085dd5  lea     rax, WPP_GLOBAL_Control
0x180085ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180085de3  cmp     rcx, rax
0x180085de6  jz      short loc_180085E10
0x180085de8  test    byte ptr [rcx+1Ch], 1
0x180085dec  jz      short loc_180085E10
0x180085dee  cmp     byte ptr [rcx+19h], 2
0x180085df2  jb      short loc_180085E10
0x180085df4  mov     edx, 7Fh
0x180085df9  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180085e00  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180085e07  mov     rcx, [rcx+10h]
0x180085e0b  call    WPP_SF_s
0x180085e10  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180085e17  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180085e1b  call    _CxxThrowException_0
0x180085e21  lea     rax, WPP_GLOBAL_Control
0x180085e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180085e2f  cmp     rcx, rax
0x180085e32  jz      short loc_180085E5C
0x180085e34  test    byte ptr [rcx+1Ch], 1
0x180085e38  jz      short loc_180085E5C
0x180085e3a  cmp     byte ptr [rcx+19h], 2
0x180085e3e  jb      short loc_180085E5C
0x180085e40  mov     edx, 80h
0x180085e45  lea     r9, aComexceptionHr; "ComException(hr)"
0x180085e4c  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180085e53  mov     rcx, [rcx+10h]
0x180085e57  call    WPP_SF_s
0x180085e5c  lea     rax, ??_7ComException@@6B@; const ComException::`vftable'
0x180085e63  mov     [rbp+var_18], rax
0x180085e67  mov     [rbp+var_10], ebx
0x180085e6a  lea     rdx, _TI2?AVComException@@; pThrowInfo
0x180085e71  lea     rcx, [rbp+var_18]; pExceptionObject
0x180085e75  call    _CxxThrowException_0
0x180085e7b  lea     rcx, [rbp+var_20]
0x180085e7f  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180085e84  mov     [rdi+30h], rax
0x180085e88  lock inc dword ptr [rax+8]
0x180085e8c  lea     rcx, [rbp+var_20]
0x180085e90  call    ??1?$unique_ptr@VCReadOnlyHiPerfEnum@@U?$default_delete@VCReadOnlyHiPerfEnum@@@std@@@std@@QEAA@XZ; std::unique_ptr<CReadOnlyHiPerfEnum>::~unique_ptr<CReadOnlyHiPerfEnum>(void)
0x180085e95  nop
0x180085e96  mov     rax, rdi
0x180085e99  mov     rbx, [rsp+40h+arg_10]
0x180085e9e  add     rsp, 40h
0x180085ea2  pop     rdi
0x180085ea3  pop     rsi
0x180085ea4  pop     rbp
0x180085ea5  retn
```
