# CUniversalRefresher::AddInProcEnum(CHiPerfProviderRecord *,IWbemObjectAccess *,IWbemServices *,ushort const *,IWbemContext *,IWbemHiPerfEnum * *,long *)

- ea: `0x18004a270`
- end: `0x18004a7bf`
- name: `?AddInProcEnum@CUniversalRefresher@@IEAAJPEAVCHiPerfProviderRecord@@PEAUIWbemObjectAccess@@PEAUIWbemServices@@PEBGPEAUIWbemContext@@PEAPEAUIWbemHiPerfEnum@@PEAJ@Z`
- size: `1359`
- prototype: `__int64 __fastcall(struct CLifeControl **this, struct CHiPerfProviderRecord *, struct IWbemObjectAccess *, struct IWbemServices *, const unsigned __int16 *, struct IWbemContext *, struct IWbemHiPerfEnum **, int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049900`
- `0x1800868d8`

## callees

- `0x180037120`
- `0x18004a270`
- `0x18004a7c8`
- `0x18004a8b4`
- `0x18004adb4`
- `0x18004b370`
- `0x18004b3a0`
- `0x1800700c8`
- `0x18007212c`
- `0x1800864a0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18004a2b8`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18004a2b8`
- `wbemcomn!GetMemLogObject` at `0x18004a394`
- `wbemcomn!GetMemLogObject` at `0x18004a417`
- `wbemcomn!GetMemLogObject` at `0x18004a4cb`
- `wbemcomn!GetMemLogObject` at `0x18004a66f`
- `wbemcomn!GetMemLogObject` at `0x18004a6ce`
- `wbemcomn!GetMemLogObject` at `0x18004a72d`
- `wbemcomn!GetMemLogObject` at `0x18004a7a8`
- `wbemcomn!GetMemLogObject` at `0x18004a394`
- `wbemcomn!GetMemLogObject` at `0x18004a417`
- `wbemcomn!GetMemLogObject` at `0x18004a4cb`
- `wbemcomn!GetMemLogObject` at `0x18004a66f`
- `wbemcomn!GetMemLogObject` at `0x18004a6ce`
- `wbemcomn!GetMemLogObject` at `0x18004a72d`
- `wbemcomn!GetMemLogObject` at `0x18004a7a8`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004a2a5`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004a2a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a39f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a422`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a4d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a67d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a6dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a73b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a7b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a39f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a422`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a4d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a67d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a6dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a73b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004a7b3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004a2d4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004a53f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004a2d4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004a53f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUniversalRefresher::AddInProcEnum(
        struct CLifeControl **this,
        struct CHiPerfProviderRecord *a2,
        struct IWbemObjectAccess *a3,
        struct IWbemServices *a4,
        const unsigned __int16 *a5,
        struct IWbemContext *a6,
        struct IWbemHiPerfEnum **a7,
        int *a8)
{
  struct IWbemServices *v8; // r15
  struct CHiPerfProviderRecord *v9; // r14
  int v10; // ebx
  CFlexArray *v11; // rdi
  CUniversalRefresher::CDirect *v12; // rax
  CUniversalRefresher::CDirect *v13; // rsi
  CClientLoadableHiPerfEnum *v14; // rax
  CUniversalRefresher::CDirect *v15; // rbx
  int v16; // edi
  CMemoryLog *v17; // rax
  CWbemRefreshingSvc *v18; // rcx
  __int64 result; // rax
  int v20; // ebx
  CMemoryLog *v21; // rax
  __int64 v22; // rdx
  CMemoryLog *v23; // rax
  struct IWbemRefresher *v24; // rbx
  CUniversalRefresher::CDirect *v25; // rax
  unsigned int v26; // edx
  CMemoryLog *v27; // rax
  unsigned int v28; // edx
  CMemoryLog *v29; // rax
  unsigned int v30; // edx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v32; // rax
  int v33; // [rsp+54h] [rbp-64h] BYREF
  CUniversalRefresher::CDirect *v34; // [rsp+58h] [rbp-60h] BYREF
  struct IWbemRefresher *v35; // [rsp+60h] [rbp-58h] BYREF
  CUniversalRefresher::CDirect *v36; // [rsp+68h] [rbp-50h]
  struct IWbemRefresher *v37; // [rsp+70h] [rbp-48h]
  ComException *v38; // [rsp+78h] [rbp-40h] BYREF
  ComException *v39; // [rsp+80h] [rbp-38h] BYREF

  v8 = a4;
  v9 = a2;
  v10 = 0;
  v11 = (CFlexArray *)(this + 4);
  v37 = (struct IWbemRefresher *)(this + 4);
  while ( v10 < CFlexArray::Size(v11) )
  {
    v12 = (CUniversalRefresher::CDirect *)CFlexArray::GetAt(v11, v10);
    v13 = v12;
    if ( *(struct CHiPerfProviderRecord **)v12 == v9 )
    {
      v36 = v12;
      goto LABEL_5;
    }
    ++v10;
  }
  v35 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v20 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, _QWORD, struct IWbemRefresher **))(**((_QWORD **)v9 + 4) + 32LL))(
            *((_QWORD *)v9 + 4),
            v8,
            0,
            &v35);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ComException `RTTI Type Descriptor', &v38) )
    {
      v11 = (CFlexArray *)v37;
      v20 = *((_DWORD *)v38 + 2);
      v9 = a2;
      v8 = a4;
      __eh34_try_continuation(0, &ComException `RTTI Type Descriptor', &loc_18004A615);
      goto LABEL_15;
    }
    if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
    {
      v20 = -2147217402;
      __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_18004A617);
LABEL_16:
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, v20);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
          (unsigned int)v20);
      }
      result = (unsigned int)v20;
LABEL_80:
      ;
    }
    if ( __eh34_catch_type(0, &CX_Exception `RTTI Type Descriptor', 0) )
    {
      v11 = (CFlexArray *)v37;
      v20 = -2147217404;
      v9 = a2;
      v8 = a4;
      __eh34_try_continuation(0, &CX_Exception `RTTI Type Descriptor', &loc_18004A620);
    }
  }
LABEL_15:
  if ( v20 < 0 )
    goto LABEL_16;
  v24 = v35;
  v37 = v35;
  v25 = (CUniversalRefresher::CDirect *)CWin32DefaultArena::WbemMemAlloc(0x70u);
  v36 = v25;
  if ( v25 )
    v25 = (CUniversalRefresher::CDirect *)CUniversalRefresher::CDirect::CDirect(v25, v9, v35);
  std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v34, (__int64)v25);
  if ( v34 )
  {
    if ( (unsigned int)CPointerArray<CUniversalRefresher::CDirect::CObjectRequest,CUniqueManager<CUniversalRefresher::CDirect::CObjectRequest>,CFlexArray>::Add(
                         v11,
                         v34) != -1 )
    {
      v13 = (CUniversalRefresher::CDirect *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v34);
      v36 = v13;
      std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(&v34, v26);
      if ( v24 )
        ((void (__fastcall *)(struct IWbemRefresher *))v24->lpVtbl->Release)(v24);
      v37 = 0;
LABEL_5:
      v14 = (CClientLoadableHiPerfEnum *)CWin32DefaultArena::WbemMemAlloc(0x188u);
      v37 = (struct IWbemRefresher *)v14;
      if ( v14 )
        v15 = CClientLoadableHiPerfEnum::CClientLoadableHiPerfEnum(v14, this[2]);
      else
        v15 = 0;
      v34 = v15;
      if ( !v15 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids,
            2147749894LL);
        }
        result = 2147749894LL;
        goto LABEL_80;
      }
      (*(void (__fastcall **)(CUniversalRefresher::CDirect *))(*(_QWORD *)v15 + 8LL))(v15);
      v37 = (struct IWbemRefresher *)v15;
      v33 = 0;
      v16 = CHiPerfEnum::SetInstanceTemplate(v15, (struct CWbemInstance *)a3);
      if ( v16 < 0 )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, v16);
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_12;
        }
        v22 = 51;
        goto LABEL_24;
      }
      if ( __eh34_try(-1, 2) )
      {
        __eh34_scope_strut(2);
        v16 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemServices *, const unsigned __int16 *, _QWORD, _DWORD, struct IWbemContext *, CUniversalRefresher::CDirect *, int *))(**((_QWORD **)v9 + 4) + 56LL))(
                *((_QWORD *)v9 + 4),
                v8,
                a5,
                *((_QWORD *)v13 + 1),
                0,
                a6,
                v15,
                &v33);
      }
      if ( __eh34_catch(2) )
      {
        if ( __eh34_catch_type(2, &ComException `RTTI Type Descriptor', &v39) )
        {
          v15 = v34;
          v13 = v36;
          v16 = *((_DWORD *)v39 + 2);
          __eh34_try_continuation(2, &ComException `RTTI Type Descriptor', &loc_18004A785);
          goto LABEL_10;
        }
        if ( __eh34_catch_type(2, &CX_MemoryException `RTTI Type Descriptor', 0) )
        {
          v16 = -2147217402;
          v15 = v34;
          __eh34_try_continuation(2, &CX_MemoryException `RTTI Type Descriptor', &loc_18004A787);
          goto LABEL_11;
        }
        if ( __eh34_catch_type(2, &CX_Exception `RTTI Type Descriptor', 0) )
        {
          v15 = v34;
          v13 = v36;
          v16 = -2147217404;
          __eh34_try_continuation(2, &CX_Exception `RTTI Type Descriptor', &loc_18004A795);
        }
      }
LABEL_10:
      if ( v16 >= 0 )
      {
        v16 = CUniversalRefresher::CDirect::AddEnumRequest(v13, v15, v33, a7, a8, this[2]);
        if ( v16 < 0 )
        {
          v32 = GetMemLogObject();
          CMemoryLog::Write(v32, v16);
        }
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_12;
        }
        v22 = 53;
        goto LABEL_24;
      }
LABEL_11:
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, v16);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_12;
      }
      v22 = 52;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v18 + 2), v22, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, (unsigned int)v16);
LABEL_12:
      (*(void (__fastcall **)(CUniversalRefresher::CDirect *))(*(_QWORD *)v15 + 16LL))(v15);
      result = (unsigned int)v16;
LABEL_13:
      v37 = 0;
      goto LABEL_80;
    }
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
    std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(&v34, v30);
    if ( !v24 )
    {
LABEL_42:
      result = 2147749894LL;
      goto LABEL_13;
    }
  }
  else
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    }
    std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(&v34, v28);
    if ( !v24 )
      goto LABEL_42;
  }
  ((void (__fastcall *)(struct IWbemRefresher *))v24->lpVtbl->Release)(v24);
  goto LABEL_42;
}

```

## disassembly

```asm
0x18004a270  mov     rax, rsp
0x18004a273  mov     [rax+20h], r9
0x18004a277  mov     [rax+18h], r8
0x18004a27b  mov     [rax+10h], rdx
0x18004a27f  mov     [rax+8], rcx
0x18004a283  push    rbx
0x18004a284  push    rsi
0x18004a285  push    rdi
0x18004a286  push    r14
0x18004a288  push    r15
0x18004a28a  sub     rsp, 90h
0x18004a291  mov     r15, r9
0x18004a294  mov     r14, rdx
0x18004a297  xor     ebx, ebx
0x18004a299  lea     rdi, [rcx+20h]
0x18004a29d  mov     [rsp+0B8h+var_48], rdi
0x18004a2a2  mov     rcx, rdi
0x18004a2a5  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004a2ab  cmp     ebx, eax
0x18004a2ad  jge     loc_18004A3E5
0x18004a2b3  mov     edx, ebx
0x18004a2b5  mov     rcx, rdi
0x18004a2b8  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18004a2be  mov     rsi, rax
0x18004a2c1  cmp     [rax], r14
0x18004a2c4  jnz     loc_18004A60E
0x18004a2ca  mov     [rsp+0B8h+var_50], rax
0x18004a2cf  mov     ecx, 188h
0x18004a2d4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004a2da  mov     [rsp+0B8h+var_48], rax
0x18004a2df  test    rax, rax
0x18004a2e2  jz      loc_18004A50E
0x18004a2e8  mov     rdx, [rsp+0B8h+arg_0]
0x18004a2f0  mov     rdx, [rdx+10h]; struct CLifeControl *
0x18004a2f4  mov     rcx, rax; this
0x18004a2f7  call    ??0CClientLoadableHiPerfEnum@@QEAA@PEAVCLifeControl@@@Z; CClientLoadableHiPerfEnum::CClientLoadableHiPerfEnum(CLifeControl *)
0x18004a2fc  mov     rbx, rax
0x18004a2ff  mov     [rsp+0B8h+var_60], rbx
0x18004a304  test    rbx, rbx
0x18004a307  jz      loc_18004A72D
0x18004a30d  mov     rax, [rbx]
0x18004a310  mov     rcx, rbx
0x18004a313  mov     rax, [rax+8]
0x18004a317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a31c  mov     [rsp+0B8h+var_48], rbx
0x18004a321  mov     [rsp+0B8h+var_64], 0
0x18004a329  mov     rdx, [rsp+0B8h+arg_10]; struct CWbemInstance *
0x18004a331  mov     rcx, rbx; this
0x18004a334  call    ?SetInstanceTemplate@CHiPerfEnum@@QEAAJPEAVCWbemInstance@@@Z; CHiPerfEnum::SetInstanceTemplate(CWbemInstance *)
0x18004a339  mov     edi, eax
0x18004a33b  test    eax, eax
0x18004a33d  js      loc_18004A4CB
0x18004a343  mov     rcx, [r14+20h]
0x18004a347  mov     rax, [rcx]
0x18004a34a  lea     rdx, [rsp+0B8h+var_64]
0x18004a34f  mov     [rsp+0B8h+var_80], rdx
0x18004a354  mov     [rsp+0B8h+var_88], rbx
0x18004a359  mov     rdx, [rsp+0B8h+arg_28]
0x18004a361  mov     [rsp+0B8h+var_90], rdx
0x18004a366  mov     dword ptr [rsp+0B8h+var_98], 0
0x18004a36e  mov     r9, [rsi+8]
0x18004a372  mov     r8, [rsp+0B8h+arg_20]
0x18004a37a  mov     rdx, r15
0x18004a37d  mov     rax, [rax+38h]
0x18004a381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a386  mov     edi, eax
0x18004a388  mov     [rsp+0B8h+var_68], eax
0x18004a38c  test    edi, edi
0x18004a38e  jns     loc_18004A443
0x18004a394  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004a39a  mov     edx, edi
0x18004a39c  mov     rcx, rax
0x18004a39f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004a3a5  lea     rax, WPP_GLOBAL_Control
0x18004a3ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3b3  cmp     rcx, rax
0x18004a3b6  jnz     loc_18004A515
0x18004a3bc  mov     rax, [rbx]
0x18004a3bf  mov     rcx, rbx
0x18004a3c2  mov     rax, [rax+10h]
0x18004a3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3cb  mov     eax, edi
0x18004a3cd  mov     [rsp+0B8h+var_48], 0
0x18004a3d6  add     rsp, 90h
0x18004a3dd  pop     r15
0x18004a3df  pop     r14
0x18004a3e1  pop     rdi
0x18004a3e2  pop     rsi
0x18004a3e3  pop     rbx
0x18004a3e4  retn
0x18004a3e5  mov     [rsp+0B8h+var_58], 0
0x18004a3ee  mov     rcx, [r14+20h]
0x18004a3f2  mov     rax, [rcx]
0x18004a3f5  lea     r9, [rsp+0B8h+var_58]
0x18004a3fa  xor     r8d, r8d
0x18004a3fd  mov     rdx, r15
0x18004a400  mov     rax, [rax+20h]
0x18004a404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a409  mov     ebx, eax
0x18004a40b  mov     [rsp+0B8h+var_68], eax
0x18004a40f  test    ebx, ebx
0x18004a411  jns     loc_18004A530
0x18004a417  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004a41d  mov     edx, ebx
0x18004a41f  mov     rcx, rax
0x18004a422  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004a428  lea     rax, WPP_GLOBAL_Control
0x18004a42f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a436  cmp     rcx, rax
0x18004a439  jnz     loc_18004A63E
0x18004a43f  mov     eax, ebx
0x18004a441  jmp     short loc_18004A3D6
0x18004a443  mov     rax, [rsp+0B8h+arg_0]
0x18004a44b  mov     rcx, [rax+10h]
0x18004a44f  mov     [rsp+0B8h+var_90], rcx; struct CLifeControl *
0x18004a454  mov     rax, [rsp+0B8h+arg_38]
0x18004a45c  mov     [rsp+0B8h+var_98], rax; int *
0x18004a461  mov     r9, [rsp+0B8h+arg_30]; struct IWbemHiPerfEnum **
0x18004a469  mov     r8d, [rsp+0B8h+var_64]; int
0x18004a46e  mov     rdx, rbx; struct CClientLoadableHiPerfEnum *
0x18004a471  mov     rcx, rsi; this
0x18004a474  call    ?AddEnumRequest@CDirect@CUniversalRefresher@@QEAAJPEAVCClientLoadableHiPerfEnum@@JPEAPEAUIWbemHiPerfEnum@@PEAJPEAVCLifeControl@@@Z; CUniversalRefresher::CDirect::AddEnumRequest(CClientLoadableHiPerfEnum *,long,IWbemHiPerfEnum * *,long *,CLifeControl *)
0x18004a479  mov     edi, eax
0x18004a47b  test    eax, eax
0x18004a47d  js      loc_18004A7A8
0x18004a483  lea     rax, WPP_GLOBAL_Control
0x18004a48a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a491  cmp     rcx, rax
0x18004a494  jz      loc_18004A3BC
0x18004a49a  test    byte ptr [rcx+1Ch], 1
0x18004a49e  jz      loc_18004A3BC
0x18004a4a4  cmp     byte ptr [rcx+19h], 2
0x18004a4a8  jb      loc_18004A3BC
0x18004a4ae  mov     edx, 35h ; '5'
0x18004a4b3  mov     r9d, edi
0x18004a4b6  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004a4bd  mov     rcx, [rcx+10h]
0x18004a4c1  call    WPP_SF_d
0x18004a4c6  jmp     loc_18004A3BC
0x18004a4cb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004a4d1  mov     edx, edi
0x18004a4d3  mov     rcx, rax
0x18004a4d6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004a4dc  lea     rax, WPP_GLOBAL_Control
0x18004a4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4ea  cmp     rcx, rax
0x18004a4ed  jz      loc_18004A3BC
0x18004a4f3  test    byte ptr [rcx+1Ch], 1
0x18004a4f7  jz      loc_18004A3BC
0x18004a4fd  cmp     byte ptr [rcx+19h], 2
0x18004a501  jb      loc_18004A3BC
0x18004a507  mov     edx, 33h ; '3'
0x18004a50c  jmp     short loc_18004A4B3
0x18004a50e  xor     ebx, ebx
0x18004a510  jmp     loc_18004A2FF
0x18004a515  test    byte ptr [rcx+1Ch], 1
0x18004a519  jz      loc_18004A3BC
0x18004a51f  cmp     byte ptr [rcx+19h], 2
0x18004a523  jb      loc_18004A3BC
0x18004a529  mov     edx, 34h ; '4'
0x18004a52e  jmp     short loc_18004A4B3
0x18004a530  mov     rbx, [rsp+0B8h+var_58]
0x18004a535  mov     [rsp+0B8h+var_48], rbx
0x18004a53a  mov     ecx, 70h ; 'p'
0x18004a53f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004a545  mov     [rsp+0B8h+var_50], rax
0x18004a54a  test    rax, rax
0x18004a54d  jz      short loc_18004A560
0x18004a54f  mov     r8, [rsp+0B8h+var_58]; struct IWbemRefresher *
0x18004a554  mov     rdx, r14; struct CHiPerfProviderRecord *
0x18004a557  mov     rcx, rax; this
0x18004a55a  call    ??0CDirect@CUniversalRefresher@@QEAA@PEAVCHiPerfProviderRecord@@PEAUIWbemRefresher@@@Z; CUniversalRefresher::CDirect::CDirect(CHiPerfProviderRecord *,IWbemRefresher *)
0x18004a55f  nop
0x18004a560  mov     rdx, rax
0x18004a563  lea     rcx, [rsp+0B8h+var_60]
0x18004a568  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x18004a56d  nop
0x18004a56e  mov     rdx, [rsp+0B8h+var_60]
0x18004a573  test    rdx, rdx
0x18004a576  jz      loc_18004A66F
0x18004a57c  mov     rcx, rdi
0x18004a57f  call    ?Add@?$CPointerArray@VCObjectRequest@CDirect@CUniversalRefresher@@V?$CUniqueManager@VCObjectRequest@CDirect@CUniversalRefresher@@@@VCFlexArray@@@@QEAAHPEAVCObjectRequest@CDirect@CUniversalRefresher@@@Z; CPointerArray<CUniversalRefresher::CDirect::CObjectRequest,CUniqueManager<CUniversalRefresher::CDirect::CObjectRequest>,CFlexArray>::Add(CUniversalRefresher::CDirect::CObjectRequest *)
0x18004a584  cmp     eax, 0FFFFFFFFh
0x18004a587  jz      loc_18004A6CE
0x18004a58d  lea     rcx, [rsp+0B8h+var_60]
0x18004a592  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x18004a597  mov     rsi, rax
0x18004a59a  mov     [rsp+0B8h+var_50], rax
0x18004a59f  lea     rcx, [rsp+0B8h+var_60]
0x18004a5a4  call    ??1?$unique_ptr@VCDirect@CUniversalRefresher@@U?$default_delete@VCDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(void)
0x18004a5a9  nop
0x18004a5aa  test    rbx, rbx
0x18004a5ad  jz      short loc_18004A5BE
0x18004a5af  mov     rcx, [rbx]
0x18004a5b2  mov     rax, [rcx+10h]
0x18004a5b6  mov     rcx, rbx
0x18004a5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5be  mov     [rsp+0B8h+var_48], 0
0x18004a5c7  jmp     loc_18004A2CF
0x18004a5cc  lea     rcx, [rsp+0B8h+var_60]
0x18004a5d1  call    ??1?$unique_ptr@VCDirect@CUniversalRefresher@@U?$default_delete@VCDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(void)
0x18004a5d6  nop
0x18004a5d7  test    rbx, rbx
0x18004a5da  jz      short loc_18004A5EB
0x18004a5dc  mov     rax, [rbx]
0x18004a5df  mov     rax, [rax+10h]
0x18004a5e3  mov     rcx, rbx
0x18004a5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5eb  mov     eax, 80041006h
0x18004a5f0  jmp     loc_18004A3CD
0x18004a5f5  lea     rcx, [rsp+0B8h+var_60]
0x18004a5fa  call    ??1?$unique_ptr@VCDirect@CUniversalRefresher@@U?$default_delete@VCDirect@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CDirect>::~unique_ptr<CUniversalRefresher::CDirect>(void)
0x18004a5ff  nop
0x18004a600  test    rbx, rbx
0x18004a603  jz      short loc_18004A5EB
0x18004a605  mov     rcx, [rbx]
0x18004a608  mov     rax, [rcx+10h]
0x18004a60c  jmp     short loc_18004A5E3
0x18004a60e  inc     ebx
0x18004a610  jmp     loc_18004A2A2
0x18004a615  jmp     short loc_18004A620
0x18004a617  mov     ebx, [rsp+0B8h+var_68]
0x18004a61b  jmp     loc_18004A417
0x18004a620  mov     rdi, [rsp+0B8h+var_48]
0x18004a625  mov     ebx, [rsp+0B8h+var_68]
0x18004a629  mov     r14, [rsp+0B8h+arg_8]
0x18004a631  mov     r15, [rsp+0B8h+arg_18]
0x18004a639  jmp     loc_18004A40F
0x18004a63e  test    byte ptr [rcx+1Ch], 1
0x18004a642  jz      loc_18004A43F
0x18004a648  cmp     byte ptr [rcx+19h], 2
0x18004a64c  jb      loc_18004A43F
0x18004a652  mov     edx, 2Fh ; '/'
0x18004a657  mov     r9d, ebx
0x18004a65a  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004a661  mov     rcx, [rcx+10h]
0x18004a665  call    WPP_SF_d
0x18004a66a  jmp     loc_18004A43F
0x18004a66f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004a675  mov     edx, 80041006h
0x18004a67a  mov     rcx, rax
0x18004a67d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004a683  lea     rax, WPP_GLOBAL_Control
0x18004a68a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a691  cmp     rcx, rax
0x18004a694  jz      loc_18004A5CC
0x18004a69a  test    byte ptr [rcx+1Ch], 1
0x18004a69e  jz      loc_18004A5CC
0x18004a6a4  cmp     byte ptr [rcx+19h], 2
0x18004a6a8  jb      loc_18004A5CC
0x18004a6ae  mov     edx, 30h ; '0'
0x18004a6b3  mov     r9d, 80041006h
0x18004a6b9  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004a6c0  mov     rcx, [rcx+10h]
0x18004a6c4  call    WPP_SF_d
0x18004a6c9  jmp     loc_18004A5CC
0x18004a6ce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004a6d4  mov     edx, 80041006h
0x18004a6d9  mov     rcx, rax
0x18004a6dc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004a6e2  lea     rax, WPP_GLOBAL_Control
0x18004a6e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a6f0  cmp     rcx, rax
0x18004a6f3  jz      loc_18004A5F5
0x18004a6f9  test    byte ptr [rcx+1Ch], 1
0x18004a6fd  jz      loc_18004A5F5
0x18004a703  cmp     byte ptr [rcx+19h], 2
0x18004a707  jb      loc_18004A5F5
0x18004a70d  mov     edx, 31h ; '1'
0x18004a712  mov     r9d, 80041006h
0x18004a718  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004a71f  mov     rcx, [rcx+10h]
0x18004a723  call    WPP_SF_d
0x18004a728  jmp     loc_18004A5F5
0x18004a72d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004a733  mov     edx, 80041006h
0x18004a738  mov     rcx, rax
0x18004a73b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004a741  lea     rax, WPP_GLOBAL_Control
0x18004a748  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a74f  cmp     rcx, rax
0x18004a752  jz      short loc_18004A77B
0x18004a754  test    byte ptr [rcx+1Ch], 1
0x18004a758  jz      short loc_18004A77B
0x18004a75a  cmp     byte ptr [rcx+19h], 2
0x18004a75e  jb      short loc_18004A77B
0x18004a760  mov     edx, 32h ; '2'
0x18004a765  mov     r9d, 80041006h
0x18004a76b  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x18004a772  mov     rcx, [rcx+10h]
0x18004a776  call    WPP_SF_d
0x18004a77b  mov     eax, 80041006h
0x18004a780  jmp     loc_18004A3D6
0x18004a785  jmp     short loc_18004A795
0x18004a787  mov     edi, [rsp+0B8h+var_68]
0x18004a78b  mov     rbx, [rsp+0B8h+var_60]
0x18004a790  jmp     loc_18004A394
0x18004a795  mov     rbx, [rsp+0B8h+var_60]
0x18004a79a  mov     rsi, [rsp+0B8h+var_50]
0x18004a79f  mov     edi, [rsp+0B8h+var_68]
  ... truncated ...
```
