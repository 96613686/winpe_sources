# CUniversalRefresher::CRemote::AddEnumRequest(CWbemObject *,ushort const *,long,IWbemHiPerfEnum * *,long *,CLifeControl *)

- ea: `0x180086ef0`
- end: `0x180087170`
- name: `?AddEnumRequest@CRemote@CUniversalRefresher@@QEAAJPEAVCWbemObject@@PEBGJPEAPEAUIWbemHiPerfEnum@@PEAJPEAVCLifeControl@@@Z`
- size: `640`
- prototype: `__int64 __fastcall(CUniversalRefresher::CRemote *this, struct CWbemObject *, const unsigned __int16 *, int, struct IWbemHiPerfEnum **, int *, struct CLifeControl *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180087d0c`

## callees

- `0x180037120`
- `0x180046a38`
- `0x18004b9e0`
- `0x18006a9c4`
- `0x1800700c8`
- `0x18007212c`
- `0x180085eac`
- `0x180086504`
- `0x180086ef0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180086f52`
- `wbemcomn!GetMemLogObject` at `0x180086fbb`
- `wbemcomn!GetMemLogObject` at `0x18008702b`
- `wbemcomn!GetMemLogObject` at `0x180087107`
- `wbemcomn!GetMemLogObject` at `0x180086f52`
- `wbemcomn!GetMemLogObject` at `0x180086fbb`
- `wbemcomn!GetMemLogObject` at `0x18008702b`
- `wbemcomn!GetMemLogObject` at `0x180087107`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086f62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086fcb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008703b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087112`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086f62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180086fcb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008703b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087112`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180086f0b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180086f0b`

## pseudocode

```c
__int64 __fastcall CUniversalRefresher::CRemote::AddEnumRequest(
        CUniversalRefresher::CRemote *this,
        struct CWbemObject *a2,
        const unsigned __int16 *a3,
        int a4,
        struct IWbemHiPerfEnum **a5,
        int *a6,
        struct CLifeControl *a7)
{
  CUniversalRefresher::CRemote::CEnumRequest *v11; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CUniversalRefresher::CClientRequest *v16; // rbx
  CHiPerfEnum *v17; // rcx
  int Interface; // ebx
  CMemoryLog *v19; // rax
  CUniversalRefresher::CRemote::CEnumRequest *v20; // [rsp+30h] [rbp-48h] BYREF
  int v21; // [rsp+38h] [rbp-40h]
  struct IWbemClassObject *v22; // [rsp+40h] [rbp-38h] BYREF

  v11 = (CUniversalRefresher::CRemote::CEnumRequest *)CWin32DefaultArena::WbemMemAlloc(0x38u);
  v22 = (struct IWbemClassObject *)v11;
  if ( v11 )
    v11 = CUniversalRefresher::CRemote::CEnumRequest::CEnumRequest((volatile signed __int32 **)v11, a2, a4, a3, a7);
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v20, (__int64)v11);
  if ( !v20 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
LABEL_8:
    std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::~unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>(&v20);
    return 2147749894LL;
  }
  if ( *((_QWORD *)v20 + 6) )
  {
    if ( (unsigned int)CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(
                         (char *)this + 88,
                         v20) == -1 )
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          145,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          2147749894LL);
      }
      goto LABEL_8;
    }
    v16 = (CUniversalRefresher::CClientRequest *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v20);
    v22 = 0;
    CUniversalRefresher::CClientRequest::GetClientInfo(v16, &v22, a6);
    if ( v22 )
      ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
    v17 = (CHiPerfEnum *)*((_QWORD *)v16 + 6);
    if ( v17 )
      Interface = CHiPerfEnum::QueryInterface(v17, &IID_IWbemHiPerfEnum, (void **)a5);
    else
      Interface = -2147217407;
    v21 = Interface;
    std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::~unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>(&v20);
    if ( Interface < 0 )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, Interface);
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        (unsigned int)Interface);
    }
    return (unsigned int)Interface;
  }
  else
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, -2147217407);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749889LL);
    }
    std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::~unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>(&v20);
    return 2147749889LL;
  }
}

```

## disassembly

```asm
0x180086ef0  push    rbx
0x180086ef2  push    rsi
0x180086ef3  push    rdi
0x180086ef4  push    r14
0x180086ef6  sub     rsp, 58h
0x180086efa  mov     edi, r9d
0x180086efd  mov     rsi, r8
0x180086f00  mov     r14, rdx
0x180086f03  mov     rbx, rcx
0x180086f06  mov     ecx, 38h ; '8'
0x180086f0b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180086f11  mov     [rsp+78h+var_38], rax
0x180086f16  test    rax, rax
0x180086f19  jz      short loc_180086F3A
0x180086f1b  mov     rcx, [rsp+78h+arg_30]
0x180086f23  mov     [rsp+78h+var_58], rcx; struct CLifeControl *
0x180086f28  mov     r9, rsi; unsigned __int16 *
0x180086f2b  mov     r8d, edi; int
0x180086f2e  mov     rdx, r14; struct CWbemObject *
0x180086f31  mov     rcx, rax; this
0x180086f34  call    ??0CEnumRequest@CRemote@CUniversalRefresher@@QEAA@PEAVCWbemObject@@JPEBGPEAVCLifeControl@@@Z; CUniversalRefresher::CRemote::CEnumRequest::CEnumRequest(CWbemObject *,long,ushort const *,CLifeControl *)
0x180086f39  nop
0x180086f3a  mov     rdx, rax
0x180086f3d  lea     rcx, [rsp+78h+var_48]
0x180086f42  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180086f47  nop
0x180086f48  mov     rdx, [rsp+78h+var_48]
0x180086f4d  test    rdx, rdx
0x180086f50  jnz     short loc_180086FB4
0x180086f52  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180086f58  mov     ebx, 80041006h
0x180086f5d  mov     edx, ebx
0x180086f5f  mov     rcx, rax
0x180086f62  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180086f68  lea     rax, WPP_GLOBAL_Control
0x180086f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180086f76  cmp     rcx, rax
0x180086f79  jz      short loc_180086FA3
0x180086f7b  test    byte ptr [rcx+1Ch], 1
0x180086f7f  jz      short loc_180086FA3
0x180086f81  cmp     byte ptr [rcx+19h], 2
0x180086f85  jb      short loc_180086FA3
0x180086f87  mov     edx, 8Fh
0x180086f8c  mov     r9d, 80041006h
0x180086f92  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180086f99  mov     rcx, [rcx+10h]
0x180086f9d  call    WPP_SF_d
0x180086fa2  nop
0x180086fa3  lea     rcx, [rsp+78h+var_48]
0x180086fa8  call    ??1?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::~unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>(void)
0x180086fad  mov     eax, ebx
0x180086faf  jmp     loc_180087165
0x180086fb4  cmp     qword ptr [rdx+30h], 0
0x180086fb9  jnz     short loc_18008701D
0x180086fbb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180086fc1  mov     ebx, 80041001h
0x180086fc6  mov     edx, ebx
0x180086fc8  mov     rcx, rax
0x180086fcb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180086fd1  lea     rax, WPP_GLOBAL_Control
0x180086fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180086fdf  cmp     rcx, rax
0x180086fe2  jz      short loc_18008700C
0x180086fe4  test    byte ptr [rcx+1Ch], 1
0x180086fe8  jz      short loc_18008700C
0x180086fea  cmp     byte ptr [rcx+19h], 2
0x180086fee  jb      short loc_18008700C
0x180086ff0  mov     edx, 90h
0x180086ff5  mov     r9d, 80041001h
0x180086ffb  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180087002  mov     rcx, [rcx+10h]
0x180087006  call    WPP_SF_d
0x18008700b  nop
0x18008700c  lea     rcx, [rsp+78h+var_48]
0x180087011  call    ??1?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::~unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>(void)
0x180087016  mov     eax, ebx
0x180087018  jmp     loc_180087165
0x18008701d  lea     rcx, [rbx+58h]
0x180087021  call    ?Add@?$CPointerArray@VCObjectRequest@CRemote@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CRemote@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CRemote@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CRemote::CObjectRequest,CUniqueManager<CUniversalRefresher::CRemote::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CRemote::CObjectRequest *)
0x180087026  cmp     eax, 0FFFFFFFFh
0x180087029  jnz     short loc_18008708D
0x18008702b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180087031  mov     ebx, 80041006h
0x180087036  mov     edx, ebx
0x180087038  mov     rcx, rax
0x18008703b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180087041  lea     rax, WPP_GLOBAL_Control
0x180087048  mov     rcx, cs:WPP_GLOBAL_Control
0x18008704f  cmp     rcx, rax
0x180087052  jz      short loc_18008707C
0x180087054  test    byte ptr [rcx+1Ch], 1
0x180087058  jz      short loc_18008707C
0x18008705a  cmp     byte ptr [rcx+19h], 2
0x18008705e  jb      short loc_18008707C
0x180087060  mov     edx, 91h
0x180087065  mov     r9d, 80041006h
0x18008706b  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180087072  mov     rcx, [rcx+10h]
0x180087076  call    WPP_SF_d
0x18008707b  nop
0x18008707c  lea     rcx, [rsp+78h+var_48]
0x180087081  call    ??1?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::~unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>(void)
0x180087086  mov     eax, ebx
0x180087088  jmp     loc_180087165
0x18008708d  lea     rcx, [rsp+78h+var_48]
0x180087092  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180087097  mov     rbx, rax
0x18008709a  mov     [rsp+78h+var_38], 0
0x1800870a3  mov     r8, [rsp+78h+arg_28]; int *
0x1800870ab  lea     rdx, [rsp+78h+var_38]; struct IWbemClassObject **
0x1800870b0  mov     rcx, rax; this
0x1800870b3  call    ?GetClientInfo@CClientRequest@CUniversalRefresher@@QEAAXPEAPEAUIWbemClassObject@@PEAJ@Z; CUniversalRefresher::CClientRequest::GetClientInfo(IWbemClassObject * *,long *)
0x1800870b8  mov     rcx, [rsp+78h+var_38]
0x1800870bd  test    rcx, rcx
0x1800870c0  jz      short loc_1800870CE
0x1800870c2  mov     rdx, [rcx]
0x1800870c5  mov     rax, [rdx+10h]
0x1800870c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800870ce  mov     rcx, [rbx+30h]; this
0x1800870d2  test    rcx, rcx
0x1800870d5  jz      short loc_1800870EF
0x1800870d7  mov     r8, [rsp+78h+arg_20]; void **
0x1800870df  lea     rdx, IID_IWbemHiPerfEnum; struct _GUID *
0x1800870e6  call    ?QueryInterface@CHiPerfEnum@@UEAAJAEBU_GUID@@PEAPEAX@Z; CHiPerfEnum::QueryInterface(_GUID const &,void * *)
0x1800870eb  mov     ebx, eax
0x1800870ed  jmp     short loc_1800870F4
0x1800870ef  mov     ebx, 80041001h
0x1800870f4  mov     [rsp+78h+var_40], ebx
0x1800870f8  lea     rcx, [rsp+78h+var_48]
0x1800870fd  call    ??1?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::~unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>(void)
0x180087102  nop
0x180087103  test    ebx, ebx
0x180087105  jns     short loc_180087118
0x180087107  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008710d  mov     edx, ebx
0x18008710f  mov     rcx, rax
0x180087112  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180087118  lea     rax, WPP_GLOBAL_Control
0x18008711f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087126  cmp     rcx, rax
0x180087129  jz      short loc_18008714F
0x18008712b  test    byte ptr [rcx+1Ch], 1
0x18008712f  jz      short loc_18008714F
0x180087131  cmp     byte ptr [rcx+19h], 2
0x180087135  jb      short loc_18008714F
0x180087137  mov     edx, 94h
0x18008713c  mov     r9d, ebx
0x18008713f  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180087146  mov     rcx, [rcx+10h]
0x18008714a  call    WPP_SF_d
0x18008714f  mov     eax, ebx
0x180087151  jmp     short loc_180087165
0x180087153  mov     eax, 80041006h
0x180087158  jmp     short loc_18008715E
0x18008715a  mov     eax, dword ptr [rsp+78h+var_48]
0x18008715e  jmp     short loc_180087165
0x180087160  mov     eax, 80041001h
0x180087165  add     rsp, 58h
0x180087169  pop     r14
0x18008716b  pop     rdi
0x18008716c  pop     rsi
0x18008716d  pop     rbx
0x18008716e  retn
```
