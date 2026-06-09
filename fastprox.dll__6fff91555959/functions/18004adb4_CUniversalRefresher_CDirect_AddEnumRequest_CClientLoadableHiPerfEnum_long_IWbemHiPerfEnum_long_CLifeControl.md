# CUniversalRefresher::CDirect::AddEnumRequest(CClientLoadableHiPerfEnum *,long,IWbemHiPerfEnum * *,long *,CLifeControl *)

- ea: `0x18004adb4`
- end: `0x18004afbb`
- name: `?AddEnumRequest@CDirect@CUniversalRefresher@@QEAAJPEAVCClientLoadableHiPerfEnum@@JPEAPEAUIWbemHiPerfEnum@@PEAJPEAVCLifeControl@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(CUniversalRefresher::CDirect *this, struct CClientLoadableHiPerfEnum *, int, struct IWbemHiPerfEnum **, int *, struct CLifeControl *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004a270`

## callees

- `0x180037120`
- `0x18004adb4`
- `0x18004afc4`
- `0x18004b370`
- `0x18004b954`
- `0x1800700c8`
- `0x18007212c`
- `0x1800864bc`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004ae0e`
- `wbemcomn!GetMemLogObject` at `0x18004ae62`
- `wbemcomn!GetMemLogObject` at `0x18004af5a`
- `wbemcomn!GetMemLogObject` at `0x18004ae0e`
- `wbemcomn!GetMemLogObject` at `0x18004ae62`
- `wbemcomn!GetMemLogObject` at `0x18004af5a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ae1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ae72`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004af65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ae1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004ae72`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004af65`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004adcf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004adcf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUniversalRefresher::CDirect::AddEnumRequest(
        CUniversalRefresher::CDirect *this,
        struct CClientLoadableHiPerfEnum *a2,
        int a3,
        struct IWbemHiPerfEnum **a4,
        int *a5,
        struct CLifeControl *a6)
{
  CUniversalRefresher::CDirect::CEnumRequest *v10; // rax
  CUniversalRefresher::CDirect::CEnumRequest *v11; // rbx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  int ClientInfo; // ebx
  CMemoryLog *v16; // rax
  CUniversalRefresher::CDirect::CEnumRequest *v17; // [rsp+20h] [rbp-48h] BYREF
  int v18; // [rsp+28h] [rbp-40h]

  v10 = (CUniversalRefresher::CDirect::CEnumRequest *)CWin32DefaultArena::WbemMemAlloc(0x38u);
  v17 = v10;
  if ( v10 )
    v10 = CUniversalRefresher::CDirect::CEnumRequest::CEnumRequest(v10, a2, a3, a6);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
LABEL_5:
    std::unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>::~unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>(&v17);
    return 2147749894LL;
  }
  if ( (unsigned int)CPointerArray<CUniversalRefresher::CDirect::CObjectRequest,CUniqueManager<CUniversalRefresher::CDirect::CObjectRequest>,CFlexArray>::Add(
                       (char *)this + 16,
                       v17) == -1 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
    goto LABEL_5;
  }
  ClientInfo = CUniversalRefresher::CDirect::CEnumRequest::GetClientInfo(v11, a4, a5);
  v18 = ClientInfo;
  std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v17);
  std::unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>::~unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>(&v17);
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
      104,
      WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
      (unsigned int)ClientInfo);
  }
  return (unsigned int)ClientInfo;
}

```

## disassembly

```asm
0x18004adb4  push    rbx
0x18004adb6  push    rsi
0x18004adb7  push    rdi
0x18004adb8  push    r14
0x18004adba  sub     rsp, 48h
0x18004adbe  mov     r14, r9
0x18004adc1  mov     ebx, r8d
0x18004adc4  mov     rsi, rdx
0x18004adc7  mov     rdi, rcx
0x18004adca  mov     ecx, 38h ; '8'
0x18004adcf  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004add5  mov     [rsp+68h+var_48], rax
0x18004adda  test    rax, rax
0x18004addd  jz      short loc_18004ADF6
0x18004addf  mov     r9, [rsp+68h+arg_28]; struct CLifeControl *
0x18004ade7  mov     r8d, ebx; int
0x18004adea  mov     rdx, rsi; struct CClientLoadableHiPerfEnum *
0x18004aded  mov     rcx, rax; this
0x18004adf0  call    ??0CEnumRequest@CDirect@CUniversalRefresher@@QEAA@PEAVCClientLoadableHiPerfEnum@@JPEAVCLifeControl@@@Z; CUniversalRefresher::CDirect::CEnumRequest::CEnumRequest(CClientLoadableHiPerfEnum *,long,CLifeControl *)
0x18004adf5  nop
0x18004adf6  mov     rdx, rax
0x18004adf9  lea     rcx, [rsp+68h+var_48]
0x18004adfe  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x18004ae03  nop
0x18004ae04  mov     rbx, [rsp+68h+var_48]
0x18004ae09  test    rbx, rbx
0x18004ae0c  jnz     short loc_18004AE51
0x18004ae0e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004ae14  mov     ebx, 80041006h
0x18004ae19  mov     edx, ebx
0x18004ae1b  mov     rcx, rax
0x18004ae1e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004ae24  lea     rax, WPP_GLOBAL_Control
0x18004ae2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae32  cmp     rcx, rax
0x18004ae35  jnz     loc_18004AEF2
0x18004ae3b  lea     rcx, [rsp+68h+var_48]
0x18004ae40  call    ??1?$unique_ptr@VCEnumRequest@CDirect@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>::~unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>(void)
0x18004ae45  mov     eax, ebx
0x18004ae47  add     rsp, 48h
0x18004ae4b  pop     r14
0x18004ae4d  pop     rdi
0x18004ae4e  pop     rsi
0x18004ae4f  pop     rbx
0x18004ae50  retn
0x18004ae51  lea     rcx, [rdi+10h]
0x18004ae55  mov     rdx, rbx
0x18004ae58  call    ?Add@?$CPointerArray@VCObjectRequest@CDirect@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CDirect@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CDirect@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CDirect::CObjectRequest,CUniqueManager<CUniversalRefresher::CDirect::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CDirect::CObjectRequest *)
0x18004ae5d  cmp     eax, 0FFFFFFFFh
0x18004ae60  jnz     short loc_18004AE9D
0x18004ae62  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004ae68  mov     ebx, 80041006h
0x18004ae6d  mov     edx, ebx
0x18004ae6f  mov     rcx, rax
0x18004ae72  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004ae78  lea     rax, WPP_GLOBAL_Control
0x18004ae7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae86  cmp     rcx, rax
0x18004ae89  jnz     loc_18004AF26
0x18004ae8f  lea     rcx, [rsp+68h+var_48]
0x18004ae94  call    ??1?$unique_ptr@VCEnumRequest@CDirect@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>::~unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>(void)
0x18004ae99  mov     eax, ebx
0x18004ae9b  jmp     short loc_18004AE47
0x18004ae9d  mov     r8, [rsp+68h+arg_20]; int *
0x18004aea5  mov     rdx, r14; struct IWbemHiPerfEnum **
0x18004aea8  mov     rcx, rbx; this
0x18004aeab  call    ?GetClientInfo@CEnumRequest@CDirect@CUniversalRefresher@@QEAAJPEAPEAUIWbemHiPerfEnum@@PEAJ@Z; CUniversalRefresher::CDirect::CEnumRequest::GetClientInfo(IWbemHiPerfEnum * *,long *)
0x18004aeb0  mov     ebx, eax
0x18004aeb2  mov     [rsp+68h+var_40], eax
0x18004aeb6  lea     rcx, [rsp+68h+var_48]
0x18004aebb  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x18004aec0  nop
0x18004aec1  lea     rcx, [rsp+68h+var_48]
0x18004aec6  call    ??1?$unique_ptr@VCEnumRequest@CDirect@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>::~unique_ptr<CUniversalRefresher::CDirect::CEnumRequest>(void)
0x18004aecb  nop
0x18004aecc  test    ebx, ebx
0x18004aece  js      loc_18004AF5A
0x18004aed4  lea     rax, WPP_GLOBAL_Control
0x18004aedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aee2  cmp     rcx, rax
0x18004aee5  jnz     loc_18004AF70
0x18004aeeb  mov     eax, ebx
0x18004aeed  jmp     loc_18004AE47
0x18004aef2  test    byte ptr [rcx+1Ch], 1
0x18004aef6  jz      loc_18004AE3B
0x18004aefc  cmp     byte ptr [rcx+19h], 2
0x18004af00  jb      loc_18004AE3B
0x18004af06  mov     edx, 64h ; 'd'
0x18004af0b  mov     r9d, 80041006h
0x18004af11  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004af18  mov     rcx, [rcx+10h]
0x18004af1c  call    WPP_SF_d
0x18004af21  jmp     loc_18004AE3B
0x18004af26  test    byte ptr [rcx+1Ch], 1
0x18004af2a  jz      loc_18004AE8F
0x18004af30  cmp     byte ptr [rcx+19h], 2
0x18004af34  jb      loc_18004AE8F
0x18004af3a  mov     edx, 65h ; 'e'
0x18004af3f  mov     r9d, 80041006h
0x18004af45  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004af4c  mov     rcx, [rcx+10h]
0x18004af50  call    WPP_SF_d
0x18004af55  jmp     loc_18004AE8F
0x18004af5a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004af60  mov     edx, ebx
0x18004af62  mov     rcx, rax
0x18004af65  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004af6b  jmp     loc_18004AED4
0x18004af70  test    byte ptr [rcx+1Ch], 1
0x18004af74  jz      loc_18004AEEB
0x18004af7a  cmp     byte ptr [rcx+19h], 2
0x18004af7e  jb      loc_18004AEEB
0x18004af84  mov     edx, 68h ; 'h'
0x18004af89  mov     r9d, ebx
0x18004af8c  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004af93  mov     rcx, [rcx+10h]
0x18004af97  call    WPP_SF_d
0x18004af9c  jmp     loc_18004AEEB
0x18004afa1  mov     eax, 80041006h
0x18004afa6  jmp     short loc_18004AFAC
0x18004afa8  mov     eax, dword ptr [rsp+68h+var_48]
0x18004afac  jmp     loc_18004AE47
0x18004afb1  mov     eax, 80041001h
0x18004afb6  jmp     loc_18004AE47
```
