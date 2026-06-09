# CUniversalRefresher::CNonHiPerf::AddEnumRequest(CClientLoadableHiPerfEnum *,ushort const *,IWbemHiPerfEnum * *,long *,CLifeControl *)

- ea: `0x180086d1c`
- end: `0x180086ee7`
- name: `?AddEnumRequest@CNonHiPerf@CUniversalRefresher@@QEAAJPEAVCClientLoadableHiPerfEnum@@PEBGPEAPEAUIWbemHiPerfEnum@@PEAJPEAVCLifeControl@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(CUniversalRefresher::CNonHiPerf *this, struct CClientLoadableHiPerfEnum *, const unsigned __int16 *, struct IWbemHiPerfEnum **, int *, struct CLifeControl *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180087178`

## callees

- `0x180037120`
- `0x180046a38`
- `0x1800700c8`
- `0x18007212c`
- `0x180085c50`
- `0x1800864e0`
- `0x180086d1c`
- `0x180088b24`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180086d76`
- `wbemcomn!GetMemLogObject` at `0x180086de9`
- `wbemcomn!GetMemLogObject` at `0x180086e7e`
- `wbemcomn!GetMemLogObject` at `0x180086d76`
- `wbemcomn!GetMemLogObject` at `0x180086de9`
- `wbemcomn!GetMemLogObject` at `0x180086e7e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086d86`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086df9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086e89`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086d86`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086df9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086e89`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180086d37`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180086d37`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUniversalRefresher::CNonHiPerf::AddEnumRequest(
        CUniversalRefresher::CNonHiPerf *this,
        struct CClientLoadableHiPerfEnum *a2,
        const unsigned __int16 *a3,
        struct IWbemHiPerfEnum **a4,
        int *a5,
        struct CLifeControl *a6)
{
  CUniversalRefresher::CNonHiPerf::CEnumRequest *v10; // rax
  CUniversalRefresher::CNonHiPerf::CEnumRequest *v11; // rbx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  int ClientInfo; // ebx
  CMemoryLog *v16; // rax
  CUniversalRefresher::CNonHiPerf::CEnumRequest *v17; // [rsp+20h] [rbp-48h] BYREF
  int v18; // [rsp+28h] [rbp-40h]

  v10 = (CUniversalRefresher::CNonHiPerf::CEnumRequest *)CWin32DefaultArena::WbemMemAlloc(0x38u);
  v17 = v10;
  if ( v10 )
    v10 = CUniversalRefresher::CNonHiPerf::CEnumRequest::CEnumRequest(v10, a2, a3, a6);
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v17, (__int64)v10);
  v11 = v17;
  if ( !v17 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
LABEL_8:
    std::unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>::~unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>(&v17);
    return 2147749894LL;
  }
  if ( (unsigned int)CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(
                       (char *)this + 16,
                       v17) == -1 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
    goto LABEL_8;
  }
  ClientInfo = CUniversalRefresher::CNonHiPerf::CEnumRequest::GetClientInfo(v11, a4, a5);
  v18 = ClientInfo;
  std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v17);
  std::unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>::~unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>(&v17);
  if ( ClientInfo < 0 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, ClientInfo);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      121,
      WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
      (unsigned int)ClientInfo);
  }
  return (unsigned int)ClientInfo;
}

```

## disassembly

```asm
0x180086d1c  push    rbx
0x180086d1e  push    rsi
0x180086d1f  push    rdi
0x180086d20  push    r14
0x180086d22  sub     rsp, 48h
0x180086d26  mov     r14, r9
0x180086d29  mov     rbx, r8
0x180086d2c  mov     rsi, rdx
0x180086d2f  mov     rdi, rcx
0x180086d32  mov     ecx, 38h ; '8'
0x180086d37  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180086d3d  mov     [rsp+68h+var_48], rax
0x180086d42  test    rax, rax
0x180086d45  jz      short loc_180086D5E
0x180086d47  mov     r9, [rsp+68h+arg_28]; struct CLifeControl *
0x180086d4f  mov     r8, rbx; unsigned __int16 *
0x180086d52  mov     rdx, rsi; struct CClientLoadableHiPerfEnum *
0x180086d55  mov     rcx, rax; this
0x180086d58  call    ??0CEnumRequest@CNonHiPerf@CUniversalRefresher@@QEAA@PEAVCClientLoadableHiPerfEnum@@PEBGPEAVCLifeControl@@@Z; CUniversalRefresher::CNonHiPerf::CEnumRequest::CEnumRequest(CClientLoadableHiPerfEnum *,ushort const *,CLifeControl *)
0x180086d5d  nop
0x180086d5e  mov     rdx, rax
0x180086d61  lea     rcx, [rsp+68h+var_48]
0x180086d66  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180086d6b  nop
0x180086d6c  mov     rbx, [rsp+68h+var_48]
0x180086d71  test    rbx, rbx
0x180086d74  jnz     short loc_180086DD8
0x180086d76  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180086d7c  mov     ebx, 80041006h
0x180086d81  mov     edx, ebx
0x180086d83  mov     rcx, rax
0x180086d86  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180086d8c  lea     rax, WPP_GLOBAL_Control
0x180086d93  mov     rcx, cs:WPP_GLOBAL_Control
0x180086d9a  cmp     rcx, rax
0x180086d9d  jz      short loc_180086DC7
0x180086d9f  test    byte ptr [rcx+1Ch], 1
0x180086da3  jz      short loc_180086DC7
0x180086da5  cmp     byte ptr [rcx+19h], 2
0x180086da9  jb      short loc_180086DC7
0x180086dab  mov     edx, 75h ; 'u'
0x180086db0  mov     r9d, 80041006h
0x180086db6  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180086dbd  mov     rcx, [rcx+10h]
0x180086dc1  call    WPP_SF_d
0x180086dc6  nop
0x180086dc7  lea     rcx, [rsp+68h+var_48]
0x180086dcc  call    ??1?$unique_ptr@VCEnumRequest@CNonHiPerf@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>::~unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>(void)
0x180086dd1  mov     eax, ebx
0x180086dd3  jmp     loc_180086EDC
0x180086dd8  lea     rcx, [rdi+10h]
0x180086ddc  mov     rdx, rbx
0x180086ddf  call    ?Add@?$CPointerArray@VCObjectRequest@CRemote@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CRemote@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CRemote@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CRemote::CObjectRequest *)
0x180086de4  cmp     eax, 0FFFFFFFFh
0x180086de7  jnz     short loc_180086E4B
0x180086de9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180086def  mov     ebx, 80041006h
0x180086df4  mov     edx, ebx
0x180086df6  mov     rcx, rax
0x180086df9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180086dff  lea     rax, WPP_GLOBAL_Control
0x180086e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e0d  cmp     rcx, rax
0x180086e10  jz      short loc_180086E3A
0x180086e12  test    byte ptr [rcx+1Ch], 1
0x180086e16  jz      short loc_180086E3A
0x180086e18  cmp     byte ptr [rcx+19h], 2
0x180086e1c  jb      short loc_180086E3A
0x180086e1e  mov     edx, 76h ; 'v'
0x180086e23  mov     r9d, 80041006h
0x180086e29  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180086e30  mov     rcx, [rcx+10h]
0x180086e34  call    WPP_SF_d
0x180086e39  nop
0x180086e3a  lea     rcx, [rsp+68h+var_48]
0x180086e3f  call    ??1?$unique_ptr@VCEnumRequest@CNonHiPerf@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>::~unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>(void)
0x180086e44  mov     eax, ebx
0x180086e46  jmp     loc_180086EDC
0x180086e4b  mov     r8, [rsp+68h+arg_20]; int *
0x180086e53  mov     rdx, r14; struct IWbemHiPerfEnum **
0x180086e56  mov     rcx, rbx; this
0x180086e59  call    ?GetClientInfo@CEnumRequest@CNonHiPerf@CUniversalRefresher@@QEAAJPEAPEAUIWbemHiPerfEnum@@PEAJ@Z; CUniversalRefresher::CNonHiPerf::CEnumRequest::GetClientInfo(IWbemHiPerfEnum * *,long *)
0x180086e5e  mov     ebx, eax
0x180086e60  mov     [rsp+68h+var_40], eax
0x180086e64  lea     rcx, [rsp+68h+var_48]
0x180086e69  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180086e6e  nop
0x180086e6f  lea     rcx, [rsp+68h+var_48]
0x180086e74  call    ??1?$unique_ptr@VCEnumRequest@CNonHiPerf@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CNonHiPerf@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>::~unique_ptr<CUniversalRefresher::CNonHiPerf::CEnumRequest>(void)
0x180086e79  nop
0x180086e7a  test    ebx, ebx
0x180086e7c  jns     short loc_180086E8F
0x180086e7e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180086e84  mov     edx, ebx
0x180086e86  mov     rcx, rax
0x180086e89  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180086e8f  lea     rax, WPP_GLOBAL_Control
0x180086e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e9d  cmp     rcx, rax
0x180086ea0  jz      short loc_180086EC6
0x180086ea2  test    byte ptr [rcx+1Ch], 1
0x180086ea6  jz      short loc_180086EC6
0x180086ea8  cmp     byte ptr [rcx+19h], 2
0x180086eac  jb      short loc_180086EC6
0x180086eae  mov     edx, 79h ; 'y'
0x180086eb3  mov     r9d, ebx
0x180086eb6  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180086ebd  mov     rcx, [rcx+10h]
0x180086ec1  call    WPP_SF_d
0x180086ec6  mov     eax, ebx
0x180086ec8  jmp     short loc_180086EDC
0x180086eca  mov     eax, 80041006h
0x180086ecf  jmp     short loc_180086ED5
0x180086ed1  mov     eax, dword ptr [rsp+68h+var_48]
0x180086ed5  jmp     short loc_180086EDC
0x180086ed7  mov     eax, 80041001h
0x180086edc  add     rsp, 48h
0x180086ee0  pop     r14
0x180086ee2  pop     rdi
0x180086ee3  pop     rsi
0x180086ee4  pop     rbx
0x180086ee5  retn
```
