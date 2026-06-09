# CUniversalRefresher::CDirect::CEnumRequest::CEnumRequest(CClientLoadableHiPerfEnum *,long,CLifeControl *)

- ea: `0x18004afc4`
- end: `0x18004b26e`
- name: `??0CEnumRequest@CDirect@CUniversalRefresher@@QEAA@PEAVCClientLoadableHiPerfEnum@@JPEAVCLifeControl@@@Z`
- size: `682`
- prototype: `CUniversalRefresher::CDirect::CEnumRequest *__fastcall(CUniversalRefresher::CDirect::CEnumRequest *this, struct CClientLoadableHiPerfEnum *, int, struct CLifeControl *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004adb4`

## callees

- `0x180035b08`
- `0x18004a7c8`
- `0x18004afc4`
- `0x18004b274`
- `0x18004b31c`
- `0x18006fa4c`
- `0x1800700c8`
- `0x18007212c`
- `0x180086588`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004b0eb`
- `wbemcomn!GetMemLogObject` at `0x18004b14c`
- `wbemcomn!GetMemLogObject` at `0x18004b1ac`
- `wbemcomn!GetMemLogObject` at `0x18004b0eb`
- `wbemcomn!GetMemLogObject` at `0x18004b14c`
- `wbemcomn!GetMemLogObject` at `0x18004b1ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b0fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b15a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b1ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b0fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b15a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004b1ba`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004b062`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004b062`

## string_xrefs

- `0x18004b238`: `ComException(hr)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CUniversalRefresher::CDirect::CEnumRequest *__fastcall CUniversalRefresher::CDirect::CEnumRequest::CEnumRequest(
        CUniversalRefresher::CDirect::CEnumRequest *this,
        struct CClientLoadableHiPerfEnum *a2,
        int a3,
        struct CLifeControl *a4)
{
  struct CWbemInstance *InstanceTemplate; // rdi
  CHiPerfEnum *v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  void **v15; // [rsp+28h] [rbp-18h] BYREF
  int v16; // [rsp+30h] [rbp-10h]
  CHiPerfEnum *v17; // [rsp+78h] [rbp+38h] BYREF
  char pExceptionObject; // [rsp+80h] [rbp+40h] BYREF

  *(_QWORD *)this = &CUniversalRefresher::CClientRequest::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 4) = _InterlockedIncrement(&CUniversalRefresher::mstatic_lLastId);
  *(_QWORD *)this = &CUniversalRefresher::CDirect::CObjectRequest::`vftable';
  *((_DWORD *)this + 6) = a3;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &CUniversalRefresher::CDirect::CEnumRequest::`vftable';
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = 0;
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
        108,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v8 = (CHiPerfEnum *)CWin32DefaultArena::WbemMemAlloc(0x188u);
  v17 = v8;
  if ( v8 )
    v8 = CReadOnlyHiPerfEnum::CReadOnlyHiPerfEnum(v8, a4);
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v17, (__int64)v8);
  if ( !v17 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  v9 = CHiPerfEnum::SetInstanceTemplate(v17, InstanceTemplate);
  if ( v9 < 0 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, -2);
    if ( v9 == -2147217402 )
    {
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          110,
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
        111,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        "ComException(hr)");
    }
    v15 = &ComException::`vftable';
    v16 = v9;
    throw (ComException *)&v15;
  }
  v10 = std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v17);
  *((_QWORD *)this + 6) = v10;
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  std::unique_ptr<CReadOnlyHiPerfEnum>::~unique_ptr<CReadOnlyHiPerfEnum>(&v17);
  (*(void (__fastcall **)(struct CWbemInstance *))(*(_QWORD *)InstanceTemplate + 16LL))(InstanceTemplate);
  return this;
}

```

## disassembly

```asm
0x18004afc4  mov     [rsp-28h+arg_0], rcx
0x18004afc9  push    rbp
0x18004afca  push    rbx
0x18004afcb  push    rsi
0x18004afcc  push    rdi
0x18004afcd  push    r14
0x18004afcf  mov     rbp, rsp
0x18004afd2  sub     rsp, 40h
0x18004afd6  mov     r14, r9
0x18004afd9  mov     rbx, rdx
0x18004afdc  mov     rsi, rcx
0x18004afdf  lea     rax, ??_7CClientRequest@CUniversalRefresher@@6B@; const CUniversalRefresher::CClientRequest::`vftable'
0x18004afe6  mov     [rcx], rax
0x18004afe9  mov     qword ptr [rcx+8], 0
0x18004aff1  mov     dword ptr [rcx+10h], 0
0x18004aff8  mov     eax, 1
0x18004affd  lock xadd cs:?mstatic_lLastId@CUniversalRefresher@@1JA, eax; long CUniversalRefresher::mstatic_lLastId
0x18004b005  inc     eax
0x18004b007  mov     [rcx+10h], eax
0x18004b00a  lea     rax, ??_7CObjectRequest@CDirect@CUniversalRefresher@@6B@; const CUniversalRefresher::CDirect::CObjectRequest::`vftable'
0x18004b011  mov     [rcx], rax
0x18004b014  mov     [rcx+18h], r8d
0x18004b018  mov     qword ptr [rcx+20h], 0
0x18004b020  lea     rax, ??_7CEnumRequest@CDirect@CUniversalRefresher@@6B@; const CUniversalRefresher::CDirect::CEnumRequest::`vftable'
0x18004b027  mov     [rcx], rax
0x18004b02a  mov     [rcx+28h], rdx
0x18004b02e  mov     qword ptr [rcx+30h], 0
0x18004b036  mov     rax, [rdx]
0x18004b039  mov     rcx, rdx
0x18004b03c  mov     rax, [rax+8]
0x18004b040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b045  mov     rcx, rbx; this
0x18004b048  call    ?GetInstanceTemplate@CHiPerfEnum@@QEAAPEAVCWbemInstance@@XZ; CHiPerfEnum::GetInstanceTemplate(void)
0x18004b04d  mov     rdi, rax
0x18004b050  test    rax, rax
0x18004b053  jz      loc_18004B0EB
0x18004b059  mov     [rbp+var_20], rax
0x18004b05d  mov     ecx, 188h
0x18004b062  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004b068  mov     [rbp+arg_8], rax
0x18004b06c  test    rax, rax
0x18004b06f  jz      short loc_18004B07D
0x18004b071  mov     rdx, r14; struct CLifeControl *
0x18004b074  mov     rcx, rax; this
0x18004b077  call    ??0CReadOnlyHiPerfEnum@@QEAA@PEAVCLifeControl@@@Z; CReadOnlyHiPerfEnum::CReadOnlyHiPerfEnum(CLifeControl *)
0x18004b07c  nop
0x18004b07d  mov     rdx, rax
0x18004b080  lea     rcx, [rbp+arg_8]
0x18004b084  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x18004b089  nop
0x18004b08a  mov     rcx, [rbp+arg_8]; this
0x18004b08e  test    rcx, rcx
0x18004b091  jz      loc_18004B14C
0x18004b097  mov     rdx, rdi; struct CWbemInstance *
0x18004b09a  call    ?SetInstanceTemplate@CHiPerfEnum@@QEAAJPEAVCWbemInstance@@@Z; CHiPerfEnum::SetInstanceTemplate(CWbemInstance *)
0x18004b09f  mov     ebx, eax
0x18004b0a1  test    eax, eax
0x18004b0a3  js      loc_18004B1AC
0x18004b0a9  lea     rcx, [rbp+arg_8]
0x18004b0ad  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x18004b0b2  mov     [rsi+30h], rax
0x18004b0b6  lock inc dword ptr [rax+8]
0x18004b0ba  lea     rcx, [rbp+arg_8]
0x18004b0be  call    ??1?$unique_ptr@VCReadOnlyHiPerfEnum@@U?$default_delete@VCReadOnlyHiPerfEnum@@@std@@@std@@QEAA@XZ; std::unique_ptr<CReadOnlyHiPerfEnum>::~unique_ptr<CReadOnlyHiPerfEnum>(void)
0x18004b0c3  nop
0x18004b0c4  mov     rax, [rdi]
0x18004b0c7  mov     rcx, rdi
0x18004b0ca  mov     rax, [rax+10h]
0x18004b0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0d3  mov     [rbp+var_20], 0
0x18004b0db  mov     rax, rsi
0x18004b0de  add     rsp, 40h
0x18004b0e2  pop     r14
0x18004b0e4  pop     rdi
0x18004b0e5  pop     rsi
0x18004b0e6  pop     rbx
0x18004b0e7  pop     rbp
0x18004b0e8  retn
0x18004b0e9  jmp     short loc_18004B07D
0x18004b0eb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004b0f1  nop
0x18004b0f2  mov     edx, 0FFFFFFFEh
0x18004b0f7  mov     rcx, rax
0x18004b0fa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004b100  lea     rax, WPP_GLOBAL_Control
0x18004b107  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b10e  cmp     rcx, rax
0x18004b111  jz      short loc_18004B13B
0x18004b113  test    byte ptr [rcx+1Ch], 1
0x18004b117  jz      short loc_18004B13B
0x18004b119  cmp     byte ptr [rcx+19h], 2
0x18004b11d  jb      short loc_18004B13B
0x18004b11f  mov     edx, 6Ch ; 'l'
0x18004b124  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18004b12b  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004b132  mov     rcx, [rcx+10h]
0x18004b136  call    WPP_SF_s
0x18004b13b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18004b142  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004b146  call    _CxxThrowException_0
0x18004b14c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004b152  mov     edx, 0FFFFFFFEh
0x18004b157  mov     rcx, rax
0x18004b15a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004b160  lea     rax, WPP_GLOBAL_Control
0x18004b167  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b16e  cmp     rcx, rax
0x18004b171  jz      short loc_18004B19B
0x18004b173  test    byte ptr [rcx+1Ch], 1
0x18004b177  jz      short loc_18004B19B
0x18004b179  cmp     byte ptr [rcx+19h], 2
0x18004b17d  jb      short loc_18004B19B
0x18004b17f  mov     edx, 6Dh ; 'm'
0x18004b184  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18004b18b  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004b192  mov     rcx, [rcx+10h]
0x18004b196  call    WPP_SF_s
0x18004b19b  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18004b1a2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004b1a6  call    _CxxThrowException_0
0x18004b1ac  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004b1b2  mov     edx, 0FFFFFFFEh
0x18004b1b7  mov     rcx, rax
0x18004b1ba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004b1c0  cmp     ebx, 80041006h
0x18004b1c6  jnz     short loc_18004B214
0x18004b1c8  lea     rax, WPP_GLOBAL_Control
0x18004b1cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b1d6  cmp     rcx, rax
0x18004b1d9  jz      short loc_18004B203
0x18004b1db  test    byte ptr [rcx+1Ch], 1
0x18004b1df  jz      short loc_18004B203
0x18004b1e1  cmp     byte ptr [rcx+19h], 2
0x18004b1e5  jb      short loc_18004B203
0x18004b1e7  mov     edx, 6Eh ; 'n'
0x18004b1ec  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18004b1f3  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004b1fa  mov     rcx, [rcx+10h]
0x18004b1fe  call    WPP_SF_s
0x18004b203  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18004b20a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004b20e  call    _CxxThrowException_0
0x18004b214  lea     rax, WPP_GLOBAL_Control
0x18004b21b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b222  cmp     rcx, rax
0x18004b225  jz      short loc_18004B24F
0x18004b227  test    byte ptr [rcx+1Ch], 1
0x18004b22b  jz      short loc_18004B24F
0x18004b22d  cmp     byte ptr [rcx+19h], 2
0x18004b231  jb      short loc_18004B24F
0x18004b233  mov     edx, 6Fh ; 'o'
0x18004b238  lea     r9, aComexceptionHr; "ComException(hr)"
0x18004b23f  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004b246  mov     rcx, [rcx+10h]
0x18004b24a  call    WPP_SF_s
0x18004b24f  lea     rax, ??_7ComException@@6B@; const ComException::`vftable'
0x18004b256  mov     [rbp+var_18], rax
0x18004b25a  mov     [rbp+var_10], ebx
0x18004b25d  lea     rdx, _TI2?AVComException@@; pThrowInfo
0x18004b264  lea     rcx, [rbp+var_18]; pExceptionObject
0x18004b268  call    _CxxThrowException_0
```
