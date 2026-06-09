# CUniversalRefresher::AddInProcObject(CHiPerfProviderRecord *,IWbemObjectAccess *,IWbemServices *,IWbemContext *,IWbemClassObject * *,long *)

- ea: `0x180067234`
- end: `0x1800677a2`
- name: `?AddInProcObject@CUniversalRefresher@@IEAAJPEAVCHiPerfProviderRecord@@PEAUIWbemObjectAccess@@PEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAJ@Z`
- size: `1390`
- prototype: `__int64 __fastcall(CUniversalRefresher *this, struct CHiPerfProviderRecord *, struct IWbemObjectAccess *, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject **, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046d48`
- `0x180086af8`

## callees

- `0x180037120`
- `0x18004b370`
- `0x18004b3a0`
- `0x180067234`
- `0x1800677a8`
- `0x1800700c8`
- `0x18007212c`
- `0x1800864a0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180067279`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180067279`
- `wbemcomn!GetMemLogObject` at `0x1800672f4`
- `wbemcomn!GetMemLogObject` at `0x180067391`
- `wbemcomn!GetMemLogObject` at `0x18006740e`
- `wbemcomn!GetMemLogObject` at `0x180067500`
- `wbemcomn!GetMemLogObject` at `0x1800675bd`
- `wbemcomn!GetMemLogObject` at `0x18006764f`
- `wbemcomn!GetMemLogObject` at `0x18006770c`
- `wbemcomn!GetMemLogObject` at `0x1800672f4`
- `wbemcomn!GetMemLogObject` at `0x180067391`
- `wbemcomn!GetMemLogObject` at `0x18006740e`
- `wbemcomn!GetMemLogObject` at `0x180067500`
- `wbemcomn!GetMemLogObject` at `0x1800675bd`
- `wbemcomn!GetMemLogObject` at `0x18006764f`
- `wbemcomn!GetMemLogObject` at `0x18006770c`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18006726a`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18006726a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800672ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006739f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006741c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006750b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800675c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006765b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067717`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800672ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006739f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006741c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006750b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800675c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006765b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180067717`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180067355`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180067355`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUniversalRefresher::AddInProcObject(
        CUniversalRefresher *this,
        struct CHiPerfProviderRecord *a2,
        struct IWbemObjectAccess *a3,
        struct IWbemServices *a4,
        struct IWbemContext *a5,
        struct IWbemClassObject **a6,
        int *a7)
{
  struct IWbemServices *v7; // r12
  struct IWbemObjectAccess *v8; // r15
  struct CHiPerfProviderRecord *v9; // r14
  int v10; // ebx
  CFlexArray *v11; // rdi
  CUniversalRefresher::CDirect *v12; // rax
  CUniversalRefresher::CDirect *v13; // rsi
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v15; // rcx
  __int64 v16; // rdx
  __int64 result; // rax
  struct IWbemRefresher *v18; // rbx
  CUniversalRefresher::CDirect *v19; // rax
  CMemoryLog *v20; // rax
  unsigned int v21; // edx
  CMemoryLog *v22; // rax
  unsigned int v23; // edx
  unsigned int v24; // edx
  int v25; // ebx
  CMemoryLog *v26; // rax
  struct CWbemObject *v27; // rbx
  int v28; // edi
  CMemoryLog *v29; // rax
  struct CWbemObject *v30; // rdi
  int v31; // r14d
  CMemoryLog *v32; // rax
  int v33; // esi
  CMemoryLog *v34; // rax
  CUniversalRefresher::CDirect *v35; // [rsp+58h] [rbp-80h] BYREF
  CFlexArray *v36; // [rsp+60h] [rbp-78h]
  void *v37; // [rsp+68h] [rbp-70h]
  struct CWbemObject *v38; // [rsp+70h] [rbp-68h] BYREF
  struct CWbemObject *v39; // [rsp+78h] [rbp-60h] BYREF
  struct IWbemRefresher *v40; // [rsp+80h] [rbp-58h] BYREF
  ComException *v41; // [rsp+88h] [rbp-50h] BYREF
  ComException *v42; // [rsp+90h] [rbp-48h] BYREF
  int v43; // [rsp+E0h] [rbp+8h] BYREF
  struct CHiPerfProviderRecord *v44; // [rsp+E8h] [rbp+10h]
  struct IWbemObjectAccess *v45; // [rsp+F0h] [rbp+18h]
  struct IWbemServices *v46; // [rsp+F8h] [rbp+20h]

  v46 = a4;
  v45 = a3;
  v44 = a2;
  v7 = a4;
  v8 = a3;
  v9 = a2;
  v10 = 0;
  v11 = (CUniversalRefresher *)((char *)this + 32);
  v36 = (CUniversalRefresher *)((char *)this + 32);
  while ( v10 < CFlexArray::Size(v11) )
  {
    v12 = (CUniversalRefresher::CDirect *)CFlexArray::GetAt(v11, v10);
    v13 = v12;
    if ( *(struct CHiPerfProviderRecord **)v12 == v9 )
    {
      v36 = v12;
      goto LABEL_34;
    }
    ++v10;
  }
  v40 = 0;
  try
  {
    v25 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, _QWORD, struct IWbemRefresher **))(**((_QWORD **)v9 + 4) + 32LL))(
            *((_QWORD *)v9 + 4),
            v7,
            0,
            &v40);
  }
  catch ( ComException *v41 )
  {
    v11 = v36;
    v25 = *((_DWORD *)v41 + 2);
    v9 = v44;
    v8 = v45;
    v7 = v46;
  }
  catch ( CX_MemoryException )
  {
    v25 = -2147217402;
    goto LABEL_8;
  }
  catch ( CX_Exception )
  {
    v11 = v36;
    v25 = -2147217404;
    v9 = v44;
    v8 = v45;
    v7 = v46;
  }
  if ( v25 < 0 )
  {
LABEL_8:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v25);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v25;
    }
    v16 = 40;
    goto LABEL_12;
  }
  v18 = v40;
  v37 = v40;
  v19 = (CUniversalRefresher::CDirect *)CWin32DefaultArena::WbemMemAlloc(0x70u);
  v36 = v19;
  if ( v19 )
    v19 = (CUniversalRefresher::CDirect *)CUniversalRefresher::CDirect::CDirect(v19, v9, v40);
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v35, (__int64)v19);
  if ( !v35 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
    std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(&v35, v21);
    if ( !v18 )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( (unsigned int)CPointerArray<CUniversalRefresher::CDirect::CObjectRequest,CUniqueManager<CUniversalRefresher::CDirect::CObjectRequest>,CFlexArray>::Add(
                       v11,
                       v35) == -1 )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
    std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(&v35, v23);
    if ( !v18 )
      goto LABEL_30;
LABEL_29:
    ((void (__fastcall *)(struct IWbemRefresher *))v18->lpVtbl->Release)(v18);
LABEL_30:
    v37 = 0;
    return 2147749894LL;
  }
  v13 = (CUniversalRefresher::CDirect *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v35);
  v36 = v13;
  std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(&v35, v24);
  if ( v18 )
    ((void (__fastcall *)(struct IWbemRefresher *))v18->lpVtbl->Release)(v18);
  v37 = 0;
LABEL_34:
  v39 = 0;
  v43 = 0;
  v38 = 0;
  v25 = ((__int64 (__fastcall *)(struct IWbemObjectAccess *, struct CWbemObject **))v8->lpVtbl->Clone)(v8, &v38);
  if ( v25 < 0 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, v25);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v25;
    }
    v16 = 43;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, (unsigned int)v25);
    return (unsigned int)v25;
  }
  v27 = v38;
  v35 = v38;
  try
  {
    v28 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, struct IWbemObjectAccess *, _QWORD, _DWORD, struct IWbemContext *, struct CWbemObject **, int *))(**((_QWORD **)v9 + 4) + 40LL))(
            *((_QWORD *)v9 + 4),
            v7,
            v8,
            *((_QWORD *)v13 + 1),
            0,
            a5,
            &v39,
            &v43);
  }
  catch ( ComException *v42 )
  {
    v27 = v35;
    v13 = v36;
    v28 = *((_DWORD *)v42 + 2);
  }
  catch ( CX_MemoryException )
  {
    v28 = -2147217402;
    v27 = v35;
    goto LABEL_41;
  }
  catch ( CX_Exception )
  {
    v27 = v35;
    v13 = v36;
    v28 = -2147217404;
  }
  if ( v28 >= 0 )
  {
    v30 = v39;
    v37 = v39;
    v31 = (*(__int64 (__fastcall **)(struct CWbemObject *, struct CWbemObject *))(*(_QWORD *)v38 + 1136LL))(v38, v39);
    if ( v31 >= 0 )
    {
      v33 = ((int (__stdcall *)(CUniversalRefresher::CDirect *, struct CWbemObject *, struct CWbemObject *, int, struct IWbemClassObject **, int *))CUniversalRefresher::CDirect::AddObjectRequest)(
              v13,
              v39,
              v38,
              v43,
              a6,
              a7);
      if ( v33 < 0 )
      {
        v34 = GetMemLogObject();
        CMemoryLog::Write(v34, v33);
      }
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          (unsigned int)v33);
      }
      if ( v30 )
        (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v30 + 16LL))(v30);
      v37 = 0;
      if ( v27 )
        (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v27 + 16LL))(v27);
      result = (unsigned int)v33;
    }
    else
    {
      v32 = GetMemLogObject();
      CMemoryLog::Write(v32, v31);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          (unsigned int)v31);
      }
      if ( v30 )
        (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v30 + 16LL))(v30);
      v37 = 0;
      if ( v27 )
        (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v27 + 16LL))(v27);
      result = (unsigned int)v31;
    }
  }
  else
  {
LABEL_41:
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, v28);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
        (unsigned int)v28);
    }
    if ( v27 )
      (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v27 + 16LL))(v27);
    result = (unsigned int)v28;
  }
  v35 = 0;
  return result;
}

```

## disassembly

```asm
0x180067234  mov     [rsp+arg_18], r9
0x180067239  mov     [rsp+arg_10], r8
0x18006723e  mov     [rsp+arg_8], rdx
0x180067243  push    rbx
0x180067244  push    rsi
0x180067245  push    rdi
0x180067246  push    r12
0x180067248  push    r14
0x18006724a  push    r15
0x18006724c  sub     rsp, 0A8h
0x180067253  mov     r12, r9
0x180067256  mov     r15, r8
0x180067259  mov     r14, rdx
0x18006725c  xor     ebx, ebx
0x18006725e  lea     rdi, [rcx+20h]
0x180067262  mov     [rsp+0D8h+var_78], rdi
0x180067267  mov     rcx, rdi
0x18006726a  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180067270  cmp     ebx, eax
0x180067272  jge     short loc_180067295
0x180067274  mov     edx, ebx
0x180067276  mov     rcx, rdi
0x180067279  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18006727f  mov     rsi, rax
0x180067282  cmp     [rax], r14
0x180067285  jz      short loc_18006728B
0x180067287  inc     ebx
0x180067289  jmp     short loc_180067267
0x18006728b  mov     [rsp+0D8h+var_78], rax
0x180067290  jmp     loc_1800674C9
0x180067295  mov     [rsp+0D8h+var_58], 0
0x1800672a1  mov     rcx, [r14+20h]
0x1800672a5  mov     rax, [rcx]
0x1800672a8  lea     r9, [rsp+0D8h+var_58]
0x1800672b0  xor     r8d, r8d
0x1800672b3  mov     rdx, r12
0x1800672b6  mov     rax, [rax+20h]
0x1800672ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672bf  mov     ebx, eax
0x1800672c1  mov     [rsp+0D8h+var_88], eax
0x1800672c5  jmp     short loc_1800672F0
0x1800672c7  jmp     short loc_1800672CF
0x1800672c9  mov     ebx, [rsp+0D8h+var_88]
0x1800672cd  jmp     short loc_1800672F4
0x1800672cf  mov     rdi, [rsp+0D8h+var_78]
0x1800672d4  mov     ebx, [rsp+0D8h+var_88]
0x1800672d8  mov     r14, [rsp+0D8h+arg_8]
0x1800672e0  mov     r15, [rsp+0D8h+arg_10]
0x1800672e8  mov     r12, [rsp+0D8h+arg_18]
0x1800672f0  test    ebx, ebx
0x1800672f2  jns     short loc_180067343
0x1800672f4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800672fa  mov     edx, ebx
0x1800672fc  mov     rcx, rax
0x1800672ff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067305  lea     rax, WPP_GLOBAL_Control
0x18006730c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067313  cmp     rcx, rax
0x180067316  jz      short loc_18006733C
0x180067318  test    byte ptr [rcx+1Ch], 1
0x18006731c  jz      short loc_18006733C
0x18006731e  cmp     byte ptr [rcx+19h], 2
0x180067322  jb      short loc_18006733C
0x180067324  mov     edx, 28h ; '('
0x180067329  mov     r9d, ebx
0x18006732c  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180067333  mov     rcx, [rcx+10h]
0x180067337  call    WPP_SF_d
0x18006733c  mov     eax, ebx
0x18006733e  jmp     loc_180067791
0x180067343  mov     rbx, [rsp+0D8h+var_58]
0x18006734b  mov     [rsp+0D8h+var_70], rbx
0x180067350  mov     ecx, 70h ; 'p'
0x180067355  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18006735b  mov     [rsp+0D8h+var_78], rax
0x180067360  test    rax, rax
0x180067363  jz      short loc_180067379
0x180067365  mov     r8, [rsp+0D8h+var_58]; struct IWbemRefresher *
0x18006736d  mov     rdx, r14; struct CHiPerfProviderRecord *
0x180067370  mov     rcx, rax; this
0x180067373  call    ??0CDirect@CUniversalRefresher@@QEAA@PEAVCHiPerfProviderRecord@@PEAUIWbemRefresher@@@Z; CUniversalRefresher::CDirect::CDirect(CHiPerfProviderRecord *,IWbemRefresher *)
0x180067378  nop
0x180067379  mov     rdx, rax
0x18006737c  lea     rcx, [rsp+0D8h+var_80]
0x180067381  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180067386  nop
0x180067387  mov     rdx, [rsp+0D8h+var_80]
0x18006738c  test    rdx, rdx
0x18006738f  jnz     short loc_1800673FD
0x180067391  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067397  mov     edx, 80041006h
0x18006739c  mov     rcx, rax
0x18006739f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800673a5  lea     rax, WPP_GLOBAL_Control
0x1800673ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800673b3  cmp     rcx, rax
0x1800673b6  jz      short loc_1800673E0
0x1800673b8  test    byte ptr [rcx+1Ch], 1
0x1800673bc  jz      short loc_1800673E0
0x1800673be  cmp     byte ptr [rcx+19h], 2
0x1800673c2  jb      short loc_1800673E0
0x1800673c4  mov     edx, 29h ; ')'
0x1800673c9  mov     r9d, 80041006h
0x1800673cf  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800673d6  mov     rcx, [rcx+10h]
0x1800673da  call    WPP_SF_d
0x1800673df  nop
0x1800673e0  lea     rcx, [rsp+0D8h+var_80]
0x1800673e5  call    ??1?$unique_ptr@VCDirect@CUniversalRefresher@@U?$default_delete@VCDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(void)
0x1800673ea  nop
0x1800673eb  test    rbx, rbx
0x1800673ee  jz      loc_18006747C
0x1800673f4  mov     rax, [rbx]
0x1800673f7  mov     rax, [rax+10h]
0x1800673fb  jmp     short loc_180067474
0x1800673fd  mov     rcx, rdi
0x180067400  call    ?Add@?$CPointerArray@VCObjectRequest@CDirect@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CDirect@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CDirect@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CDirect::CObjectRequest,CUniqueManager<CUniversalRefresher::CDirect::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CDirect::CObjectRequest *)
0x180067405  cmp     eax, 0FFFFFFFFh
0x180067408  jnz     loc_18006748F
0x18006740e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067414  mov     edx, 80041006h
0x180067419  mov     rcx, rax
0x18006741c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067422  lea     rax, WPP_GLOBAL_Control
0x180067429  mov     rcx, cs:WPP_GLOBAL_Control
0x180067430  cmp     rcx, rax
0x180067433  jz      short loc_18006745D
0x180067435  test    byte ptr [rcx+1Ch], 1
0x180067439  jz      short loc_18006745D
0x18006743b  cmp     byte ptr [rcx+19h], 2
0x18006743f  jb      short loc_18006745D
0x180067441  mov     edx, 2Ah ; '*'
0x180067446  mov     r9d, 80041006h
0x18006744c  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180067453  mov     rcx, [rcx+10h]
0x180067457  call    WPP_SF_d
0x18006745c  nop
0x18006745d  lea     rcx, [rsp+0D8h+var_80]
0x180067462  call    ??1?$unique_ptr@VCDirect@CUniversalRefresher@@U?$default_delete@VCDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(void)
0x180067467  nop
0x180067468  test    rbx, rbx
0x18006746b  jz      short loc_18006747C
0x18006746d  mov     rcx, [rbx]
0x180067470  mov     rax, [rcx+10h]
0x180067474  mov     rcx, rbx
0x180067477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006747c  mov     [rsp+0D8h+var_70], 0
0x180067485  mov     eax, 80041006h
0x18006748a  jmp     loc_180067791
0x18006748f  lea     rcx, [rsp+0D8h+var_80]
0x180067494  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180067499  mov     rsi, rax
0x18006749c  mov     [rsp+0D8h+var_78], rax
0x1800674a1  lea     rcx, [rsp+0D8h+var_80]
0x1800674a6  call    ??1?$unique_ptr@VCDirect@CUniversalRefresher@@U?$default_delete@VCDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(void)
0x1800674ab  nop
0x1800674ac  test    rbx, rbx
0x1800674af  jz      short loc_1800674C0
0x1800674b1  mov     rcx, [rbx]
0x1800674b4  mov     rax, [rcx+10h]
0x1800674b8  mov     rcx, rbx
0x1800674bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674c0  mov     [rsp+0D8h+var_70], 0
0x1800674c9  mov     [rsp+0D8h+var_60], 0
0x1800674d2  mov     [rsp+0D8h+arg_0], 0
0x1800674dd  mov     [rsp+0D8h+var_68], 0
0x1800674e6  mov     rax, [r15]
0x1800674e9  lea     rdx, [rsp+0D8h+var_68]
0x1800674ee  mov     rcx, r15
0x1800674f1  mov     rax, [rax+60h]
0x1800674f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674fa  mov     ebx, eax
0x1800674fc  test    eax, eax
0x1800674fe  jns     short loc_180067546
0x180067500  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067506  mov     edx, ebx
0x180067508  mov     rcx, rax
0x18006750b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067511  lea     rax, WPP_GLOBAL_Control
0x180067518  mov     rcx, cs:WPP_GLOBAL_Control
0x18006751f  cmp     rcx, rax
0x180067522  jz      loc_18006733C
0x180067528  test    byte ptr [rcx+1Ch], 1
0x18006752c  jz      loc_18006733C
0x180067532  cmp     byte ptr [rcx+19h], 2
0x180067536  jb      loc_18006733C
0x18006753c  mov     edx, 2Bh ; '+'
0x180067541  jmp     loc_180067329
0x180067546  mov     rbx, [rsp+0D8h+var_68]
0x18006754b  mov     [rsp+0D8h+var_80], rbx
0x180067550  mov     rcx, [r14+20h]
0x180067554  mov     rax, [rcx]
0x180067557  lea     rdx, [rsp+0D8h+arg_0]
0x18006755f  mov     [rsp+0D8h+var_A0], rdx
0x180067564  lea     rdx, [rsp+0D8h+var_60]
0x180067569  mov     [rsp+0D8h+var_A8], rdx
0x18006756e  mov     rdx, [rsp+0D8h+arg_20]
0x180067576  mov     [rsp+0D8h+var_B0], rdx
0x18006757b  mov     dword ptr [rsp+0D8h+var_B8], 0
0x180067583  mov     r9, [rsi+8]
0x180067587  mov     r8, r15
0x18006758a  mov     rdx, r12
0x18006758d  mov     rax, [rax+28h]
0x180067591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067596  mov     edi, eax
0x180067598  mov     [rsp+0D8h+var_88], eax
0x18006759c  jmp     short loc_1800675B9
0x18006759e  jmp     short loc_1800675AB
0x1800675a0  mov     edi, [rsp+0D8h+var_88]
0x1800675a4  mov     rbx, [rsp+0D8h+var_80]
0x1800675a9  jmp     short loc_1800675BD
0x1800675ab  mov     rbx, [rsp+0D8h+var_80]
0x1800675b0  mov     rsi, [rsp+0D8h+var_78]
0x1800675b5  mov     edi, [rsp+0D8h+var_88]
0x1800675b9  test    edi, edi
0x1800675bb  jns     short loc_180067621
0x1800675bd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800675c3  mov     edx, edi
0x1800675c5  mov     rcx, rax
0x1800675c8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800675ce  lea     rax, WPP_GLOBAL_Control
0x1800675d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800675dc  cmp     rcx, rax
0x1800675df  jz      short loc_180067606
0x1800675e1  test    byte ptr [rcx+1Ch], 1
0x1800675e5  jz      short loc_180067606
0x1800675e7  cmp     byte ptr [rcx+19h], 2
0x1800675eb  jb      short loc_180067606
0x1800675ed  mov     edx, 2Ch ; ','
0x1800675f2  mov     r9d, edi
0x1800675f5  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x1800675fc  mov     rcx, [rcx+10h]
0x180067600  call    WPP_SF_d
0x180067605  nop
0x180067606  test    rbx, rbx
0x180067609  jz      short loc_18006761A
0x18006760b  mov     rax, [rbx]
0x18006760e  mov     rcx, rbx
0x180067611  mov     rax, [rax+10h]
0x180067615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006761a  mov     eax, edi
0x18006761c  jmp     loc_180067788
0x180067621  mov     rdi, [rsp+0D8h+var_60]
0x180067626  mov     [rsp+0D8h+var_70], rdi
0x18006762b  mov     rcx, [rsp+0D8h+var_68]
0x180067630  mov     rax, [rcx]
0x180067633  mov     rdx, [rsp+0D8h+var_60]
0x180067638  mov     rax, [rax+470h]
0x18006763f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067644  mov     r14d, eax
0x180067647  test    eax, eax
0x180067649  jns     loc_1800676D2
0x18006764f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067655  mov     edx, r14d
0x180067658  mov     rcx, rax
0x18006765b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180067661  lea     rax, WPP_GLOBAL_Control
0x180067668  mov     rcx, cs:WPP_GLOBAL_Control
0x18006766f  cmp     rcx, rax
0x180067672  jz      short loc_180067699
0x180067674  test    byte ptr [rcx+1Ch], 1
0x180067678  jz      short loc_180067699
0x18006767a  cmp     byte ptr [rcx+19h], 2
0x18006767e  jb      short loc_180067699
0x180067680  mov     edx, 2Dh ; '-'
0x180067685  mov     r9d, r14d
0x180067688  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18006768f  mov     rcx, [rcx+10h]
0x180067693  call    WPP_SF_d
0x180067698  nop
0x180067699  test    rdi, rdi
0x18006769c  jz      short loc_1800676AD
0x18006769e  mov     rax, [rdi]
0x1800676a1  mov     rcx, rdi
0x1800676a4  mov     rax, [rax+10h]
0x1800676a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676ad  mov     [rsp+0D8h+var_70], 0
0x1800676b6  test    rbx, rbx
0x1800676b9  jz      short loc_1800676CA
0x1800676bb  mov     rax, [rbx]
0x1800676be  mov     rcx, rbx
0x1800676c1  mov     rax, [rax+10h]
0x1800676c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676ca  mov     eax, r14d
0x1800676cd  jmp     loc_180067788
0x1800676d2  mov     rax, [rsp+0D8h+arg_30]
0x1800676da  mov     [rsp+0D8h+var_B0], rax; int *
0x1800676df  mov     rax, [rsp+0D8h+arg_28]
0x1800676e7  mov     [rsp+0D8h+var_B8], rax; struct IWbemClassObject **
0x1800676ec  mov     r9d, [rsp+0D8h+arg_0]; int
0x1800676f4  mov     r8, [rsp+0D8h+var_68]; struct CWbemObject *
0x1800676f9  mov     rdx, [rsp+0D8h+var_60]; struct CWbemObject *
0x1800676fe  mov     rcx, rsi; this
0x180067701  call    ?AddObjectRequest@CDirect@CUniversalRefresher@@QEAAJPEAVCWbemObject@@0JPEAPEAUIWbemClassObject@@PEAJ@Z; CUniversalRefresher::CDirect::AddObjectRequest(CWbemObject *,CWbemObject *,long,IWbemClassObject * *,long *)
0x180067706  mov     esi, eax
0x180067708  test    eax, eax
0x18006770a  jns     short loc_18006771D
0x18006770c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180067712  mov     edx, esi
0x180067714  mov     rcx, rax
  ... truncated ...
```
