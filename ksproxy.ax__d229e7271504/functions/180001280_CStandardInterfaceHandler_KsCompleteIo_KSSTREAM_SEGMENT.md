# CStandardInterfaceHandler::KsCompleteIo(_KSSTREAM_SEGMENT *)

- ea: `0x180001280`
- end: `0x1800019a1`
- name: `?KsCompleteIo@CStandardInterfaceHandler@@UEAAJPEAU_KSSTREAM_SEGMENT@@@Z`
- size: `1825`
- prototype: `__int64 __fastcall(CStandardInterfaceHandler *this, struct _KSSTREAM_SEGMENT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001280`
- `0x1800019b0`
- `0x180002b58`
- `0x18001f1c4`
- `0x18001ffb0`
- `0x180025a74`
- `0x180040180`
- `0x1800401fc`
- `0x180040268`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001588`
- `KERNEL32!GetLastError` at `0x180001588`
- `KERNEL32!GetOverlappedResult` at `0x1800012c6`
- `KERNEL32!GetOverlappedResult` at `0x1800012c6`

## pseudocode

```c
__int64 __fastcall CStandardInterfaceHandler::KsCompleteIo(
        CStandardInterfaceHandler *this,
        struct _KSSTREAM_SEGMENT *a2)
{
  void *v4; // rcx
  IKsDataTypeHandler *KsDataTypeHandler; // r14
  unsigned __int64 v6; // rdx
  BOOL OverlappedResult; // ebp
  signed int LastError; // r15d
  int i; // esi
  unsigned __int64 v10; // r12
  _GUID *v11; // r12
  IKsInterfaceHandler *v12; // rcx
  IKsInterfaceHandler *v13; // rcx
  IKsInterfaceHandler *v14; // rcx
  IKsInterfaceHandler_vtbl *v15; // rax
  __int64 v16; // rdx
  IKsInterfaceHandler *v18; // rcx
  IKsInterfaceHandler *v19; // rcx
  IKsInterfaceHandler *v20; // rcx
  int v21; // eax
  IKsDataTypeHandler_vtbl *v22; // rcx
  IKsInterfaceHandler *v23; // rcx
  PVOID *v24; // rcx
  signed int v25; // eax
  signed int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // edx
  unsigned int v29; // edx
  signed int v30; // eax
  IKsInterfaceHandler *v31; // rcx
  IKsInterfaceHandler *v32; // rcx
  IKsDataTypeHandler *v33; // rcx
  IKsInterfaceHandler *v34; // rcx
  unsigned int *v35; // rdx
  __int64 v36; // rdx
  int v37; // eax
  int v38; // r12d
  __int64 v39; // [rsp+20h] [rbp-A8h]
  char *v40; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v41[2]; // [rsp+40h] [rbp-88h] BYREF
  int v42; // [rsp+48h] [rbp-80h]
  int v43; // [rsp+D0h] [rbp+8h]
  DWORD v44; // [rsp+D8h] [rbp+10h] BYREF
  void *v45; // [rsp+E0h] [rbp+18h] BYREF
  IKsDataTypeHandler_vtbl *v46; // [rsp+E8h] [rbp+20h] BYREF

  v4 = *(void **)&this->m_ClsID.Data1;
  KsDataTypeHandler = a2[17].KsDataTypeHandler;
  v44 = 0;
  OverlappedResult = GetOverlappedResult(v4, (LPOVERLAPPED)&a2[17].IoOperation, &v44, 0);
  if ( OverlappedResult )
  {
    LastError = 0;
    v43 = 0;
  }
  else
  {
    LastError = GetLastError();
    v43 = LastError;
  }
  for ( i = 0; i < SLODWORD(a2[17].KsInterfaceHandler); ++i )
  {
    if ( OverlappedResult )
      goto LABEL_5;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids, a2);
    if ( (unsigned int)IsD3DMediaSample((struct IMediaSample *)(&a2[1].KsInterfaceHandler)[i]) )
    {
      v45 = KsDataTypeHandler[5].__vftable;
      if ( v45 )
      {
        v31 = (&a2[1].KsInterfaceHandler)[i];
        ((void (__fastcall *)(IKsInterfaceHandler *, _QWORD))v31->__vftable[2].QueryInterface)(v31, 0);
        memset_0(v45, 0, 0xA8u);
        KsDataTypeHandler[5].__vftable = 0;
      }
      v24 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( LastError <= 0 )
          v26 = LastError;
        else
          v26 = (unsigned __int16)LastError | 0x80070000;
        WPP_SF_PP(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          *(_QWORD *)&a2[17].IoOperation,
          v26,
          *(_QWORD *)&a2[17].IoOperation);
        v24 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *(_QWORD *)&a2[17].IoOperation != -1073741811 )
      {
        v27 = (unsigned __int16)LastError | 0x80070000;
        v28 = LastError <= 0 ? LastError : (unsigned __int16)LastError | 0x80070000;
        if ( v28 != -2147024865 )
        {
          v29 = LastError <= 0 ? LastError : (unsigned __int16)LastError | 0x80070000;
          if ( v29 != -2147024809 )
          {
            if ( LastError <= 0 )
              v27 = LastError;
            if ( v27 != -2147023112 )
              goto LABEL_32;
          }
        }
      }
      if ( this->m_ClsID.Data4[0] )
        goto LABEL_5;
      if ( (int)RestartGraph((struct IMediaSample *)(&a2[1].KsInterfaceHandler)[i]) >= 0 )
        this->m_ClsID.Data4[0] = 1;
    }
    v24 = (PVOID *)WPP_GLOBAL_Control;
LABEL_32:
    if ( !this->m_ClsID.Data4[0] )
    {
      if ( v24 != &WPP_GLOBAL_Control )
      {
        if ( LastError <= 0 )
          v25 = LastError;
        else
          v25 = (unsigned __int16)LastError | 0x80070000;
        WPP_SF_PP(v24[2], 15, *(_QWORD *)&a2[17].IoOperation, v25, *(_QWORD *)&a2[17].IoOperation);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      (*((void (__fastcall **)(IKsInterfaceHandler_vtbl *, IKsInterfaceHandler *, _QWORD))this->QueryInterface + 16))(
        this->IKsInterfaceHandler::IUnknown::__vftable,
        (&a2[1].KsInterfaceHandler)[i],
        (unsigned int)LastError);
    }
LABEL_5:
    v10 = 7LL * i;
    if ( HIDWORD(a2[17].KsDataTypeHandler[v10].__vftable) )
    {
      v32 = (&a2[1].KsInterfaceHandler)[i];
      v45 = 0;
      if ( v32->QueryInterface(v32, &GUID_36b73884_c2c8_11cf_8b46_00805f6cef60, &v45) >= 0 )
      {
        memset_0(v41, 0, 0x40u);
        (*(void (__fastcall **)(void *, __int64, _DWORD *))(*(_QWORD *)v45 + 152LL))(v45, 12, v41);
        v33 = a2[17].KsDataTypeHandler;
        v41[0] = 12;
        v41[1] = HIDWORD(v33[v10].__vftable);
        v42 |= (__int64)v33[v10 + 6].__vftable & 0x40;
        (*(void (__fastcall **)(void *, __int64, _DWORD *))(*(_QWORD *)v45 + 160LL))(v45, 12, v41);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 16LL))(v45);
      }
    }
    if ( HIDWORD(a2[17].KsInterfaceHandler) )
    {
      LODWORD(v39) = !OverlappedResult;
      a2->KsDataTypeHandler->KsCompleteIoOperation(
        a2->KsDataTypeHandler,
        (IMediaSample *)(&a2[1].KsInterfaceHandler)[i],
        KsDataTypeHandler,
        a2->IoOperation,
        v39);
    }
    if ( a2->IoOperation != KsIoOperation_Read )
    {
LABEL_24:
      v23 = (&a2[1].KsInterfaceHandler)[i];
      v23->Release(v23);
      goto LABEL_17;
    }
    v46 = 0;
    v11 = 0;
    v40 = 0;
    v45 = 0;
    if ( OverlappedResult )
    {
      v18 = (&a2[1].KsInterfaceHandler)[i];
      ((void (__fastcall *)(IKsInterfaceHandler *, _QWORD))v18->__vftable[2].KsProcessMediaSamples)(
        v18,
        (__int64)KsDataTypeHandler[6].__vftable & 4);
      v19 = (&a2[1].KsInterfaceHandler)[i];
      ((void (__fastcall *)(IKsInterfaceHandler *, _QWORD))v19->__vftable[1].KsProcessMediaSamples)(
        v19,
        (__int64)KsDataTypeHandler[6].__vftable & 2);
      v20 = (&a2[1].KsInterfaceHandler)[i];
      ((void (__fastcall *)(IKsInterfaceHandler *, _QWORD))v20->__vftable[1].Release)(
        v20,
        (__int64)KsDataTypeHandler[6].__vftable & 1);
      v21 = (int)KsDataTypeHandler[6].__vftable;
      if ( (v21 & 0x10) != 0 )
      {
        v22 = KsDataTypeHandler[1].__vftable;
        v11 = (_GUID *)&v46;
        v46 = v22;
        if ( (v21 & 0x100) != 0 )
        {
          v40 = (char *)KsDataTypeHandler[3].__vftable + (unsigned __int64)v22;
          v45 = &v40;
        }
      }
    }
    v12 = (&a2[1].KsInterfaceHandler)[i];
    if ( v12->__vftable[1].QueryInterface(v12, v11, (void **)v45) < 0 && !v45 )
    {
      v34 = (&a2[1].KsInterfaceHandler)[i];
      v34->__vftable[1].QueryInterface(v34, v11, (void **)v11);
    }
    v13 = (&a2[1].KsInterfaceHandler)[i];
    v45 = 0;
    if ( v13->QueryInterface(v13, &GUID_68961e68_832b_41ea_bc91_63593f3e70e3, &v45) < 0 )
    {
      v14 = (&a2[1].KsInterfaceHandler)[i];
      v15 = v14->__vftable;
      if ( OverlappedResult )
        v16 = HIDWORD(KsDataTypeHandler[4].__vftable);
      else
LABEL_26:
        v16 = 0;
      ((void (__fastcall *)(IKsInterfaceHandler *, __int64))v15[2].QueryInterface)(v14, v16);
      goto LABEL_15;
    }
    if ( v45 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 16LL))(v45);
    v35 = (unsigned int *)KsDataTypeHandler[5].__vftable;
    v14 = (&a2[1].KsInterfaceHandler)[i];
    v45 = v35;
    v15 = v14->__vftable;
    if ( !v35 )
      goto LABEL_26;
    if ( OverlappedResult )
      v36 = v35[4];
    else
      v36 = 0;
    ((void (__fastcall *)(IKsInterfaceHandler *, __int64))v15[2].QueryInterface)(v14, v36);
    v37 = VidmemToSysmemBlit((struct IMediaSample *)(&a2[1].KsInterfaceHandler)[i]);
    v38 = v37;
    if ( v37 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids,
          (unsigned int)v37);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v30 = v43;
          if ( v43 > 0 )
            v30 = (unsigned __int16)v43 | 0x80070000;
          WPP_SF_PP(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            *(_QWORD *)&a2[17].IoOperation,
            v30,
            *(_QWORD *)&a2[17].IoOperation);
        }
      }
      OverlappedResult = 0;
      if ( v38 == -2005530520 || v38 == -2005530508 )
        RestartGraph((struct IMediaSample *)(&a2[1].KsInterfaceHandler)[i]);
    }
    memset_0(v45, 0, 0xA8u);
    KsDataTypeHandler[5].__vftable = 0;
LABEL_15:
    if ( !OverlappedResult )
      goto LABEL_24;
    (*((void (__fastcall **)(IKsInterfaceHandler_vtbl *, IKsInterfaceHandler *, _QWORD))this->QueryInterface + 8))(
      this->IKsInterfaceHandler::IUnknown::__vftable,
      (&a2[1].KsInterfaceHandler)[i],
      LODWORD(KsDataTypeHandler[6].__vftable));
LABEL_17:
    LastError = v43;
    KsDataTypeHandler = (IKsDataTypeHandler *)((char *)KsDataTypeHandler + HIDWORD(a2[17].KsInterfaceHandler) + 56);
  }
  operator delete(a2[17].KsDataTypeHandler, v6);
  if ( HIDWORD(a2[17].KsInterfaceHandler) )
    a2->KsDataTypeHandler->Release(a2->KsDataTypeHandler);
  (*((void (__fastcall **)(IKsInterfaceHandler_vtbl *))this->QueryInterface + 14))(this->IKsInterfaceHandler::IUnknown::__vftable);
  (*((void (__fastcall **)(IKsInterfaceHandler_vtbl *, struct _KSSTREAM_SEGMENT *))this->QueryInterface + 9))(
    this->IKsInterfaceHandler::IUnknown::__vftable,
    a2);
  operator delete(a2, 0x250u);
  this->NonDelegatingRelease(this);
  return 0;
}

```

## disassembly

```asm
0x180001280  mov     rax, rsp
0x180001283  push    rbx
0x180001284  push    rdi
0x180001285  sub     rsp, 0B8h
0x18000128c  mov     [rax-18h], rbp
0x180001290  lea     r8, [rax+10h]; lpNumberOfBytesTransferred
0x180001294  mov     [rax-20h], rsi
0x180001298  mov     rbx, rdx
0x18000129b  mov     [rax-30h], r13
0x18000129f  mov     rdi, rcx
0x1800012a2  mov     rcx, [rcx+20h]; hFile
0x1800012a6  xor     r9d, r9d; bWait
0x1800012a9  mov     [rax-38h], r14
0x1800012ad  mov     r14, [rdx+228h]
0x1800012b4  add     rdx, 230h; lpOverlapped
0x1800012bb  mov     [rax-40h], r15
0x1800012bf  mov     dword ptr [rax+10h], 0
0x1800012c6  call    cs:__imp_GetOverlappedResult
0x1800012cd  nop     dword ptr [rax+rax+00h]
0x1800012d2  mov     ebp, eax
0x1800012d4  test    eax, eax
0x1800012d6  jz      loc_180001588
0x1800012dc  xor     r15d, r15d
0x1800012df  mov     [rsp+0C8h+arg_0], r15d
0x1800012e7  xor     esi, esi
0x1800012e9  cmp     [rbx+220h], esi
0x1800012ef  jle     loc_180001449
0x1800012f5  mov     [rsp+0C8h+var_28], r12
0x1800012fd  lea     rax, WPP_GLOBAL_Control
0x180001304  test    ebp, ebp
0x180001306  jz      loc_1800015AA
0x18000130c  mov     rax, [rbx+228h]
0x180001313  movsxd  r15, esi
0x180001316  imul    r12, r15, 38h ; '8'
0x18000131a  cmp     dword ptr [r12+rax+4], 0
0x180001320  jnz     loc_1800017DC
0x180001326  cmp     dword ptr [rbx+224h], 0
0x18000132d  jz      short loc_180001356
0x18000132f  mov     rcx, [rbx+8]
0x180001333  xor     edx, edx
0x180001335  mov     r9d, [rbx+10h]
0x180001339  test    ebp, ebp
0x18000133b  mov     r8, r14
0x18000133e  setz    dl
0x180001341  mov     rax, [rcx]
0x180001344  mov     dword ptr [rsp+0C8h+var_A8], edx
0x180001348  mov     rdx, [rbx+r15*8+20h]
0x18000134d  mov     rax, [rax+18h]
0x180001351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001356  cmp     dword ptr [rbx+10h], 1
0x18000135a  jnz     loc_180001572
0x180001360  xor     eax, eax
0x180001362  mov     [rsp+0C8h+arg_18], rax
0x18000136a  mov     r12d, eax
0x18000136d  mov     [rsp+0C8h+var_98], rax
0x180001372  mov     [rsp+0C8h+arg_10], rax
0x18000137a  test    ebp, ebp
0x18000137c  jnz     loc_1800014E2
0x180001382  mov     rcx, [rbx+r15*8+20h]
0x180001387  mov     rdx, r12
0x18000138a  mov     r8, [rsp+0C8h+arg_10]
0x180001392  mov     rax, [rcx]
0x180001395  mov     rax, [rax+30h]
0x180001399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000139e  test    eax, eax
0x1800013a0  js      loc_1800018A0
0x1800013a6  mov     rcx, [rbx+r15*8+20h]
0x1800013ab  lea     r8, [rsp+0C8h+arg_10]
0x1800013b3  lea     rdx, _GUID_68961e68_832b_41ea_bc91_63593f3e70e3
0x1800013ba  mov     [rsp+0C8h+arg_10], 0
0x1800013c6  mov     rax, [rcx]
0x1800013c9  mov     rax, [rax]
0x1800013cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013d1  test    eax, eax
0x1800013d3  jns     loc_1800018CB
0x1800013d9  mov     rcx, [rbx+r15*8+20h]
0x1800013de  mov     rax, [rcx]
0x1800013e1  test    ebp, ebp
0x1800013e3  jz      loc_1800015A3
0x1800013e9  mov     edx, [r14+24h]
0x1800013ed  mov     rax, [rax+60h]
0x1800013f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013f6  test    ebp, ebp
0x1800013f8  jz      loc_180001572
0x1800013fe  mov     rcx, [rdi+18h]
0x180001402  mov     r8d, [r14+30h]
0x180001406  mov     rdx, [rbx+r15*8+20h]
0x18000140b  mov     rax, [rcx]
0x18000140e  mov     rax, [rax+40h]
0x180001412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001417  mov     eax, [rbx+224h]
0x18000141d  inc     esi
0x18000141f  mov     r15d, [rsp+0C8h+arg_0]
0x180001427  add     rax, 38h ; '8'
0x18000142b  add     r14, rax
0x18000142e  lea     rax, WPP_GLOBAL_Control
0x180001435  cmp     esi, [rbx+220h]
0x18000143b  jl      loc_180001304
0x180001441  mov     r12, [rsp+0C8h+var_28]
0x180001449  mov     rcx, [rbx+228h]; void *
0x180001450  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001455  cmp     dword ptr [rbx+224h], 0
0x18000145c  mov     r15, [rsp+0C8h+var_40]
0x180001464  mov     r14, [rsp+0C8h+var_38]
0x18000146c  mov     r13, [rsp+0C8h+var_30]
0x180001474  mov     rsi, [rsp+0C8h+var_20]
0x18000147c  mov     rbp, [rsp+0C8h+var_18]
0x180001484  jz      short loc_180001496
0x180001486  mov     rcx, [rbx+8]
0x18000148a  mov     rax, [rcx]
0x18000148d  mov     rax, [rax+10h]
0x180001491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001496  mov     rcx, [rdi+18h]
0x18000149a  mov     rax, [rcx]
0x18000149d  mov     rax, [rax+70h]
0x1800014a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014a6  mov     rcx, [rdi+18h]
0x1800014aa  mov     rdx, rbx
0x1800014ad  mov     rax, [rcx]
0x1800014b0  mov     rax, [rax+48h]
0x1800014b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014b9  mov     edx, 250h; unsigned __int64
0x1800014be  mov     rcx, rbx; void *
0x1800014c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800014c6  mov     rax, [rdi]
0x1800014c9  mov     rcx, rdi
0x1800014cc  mov     rax, [rax+10h]
0x1800014d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014d5  xor     eax, eax
0x1800014d7  add     rsp, 0B8h
0x1800014de  pop     rdi
0x1800014df  pop     rbx
0x1800014e0  retn
0x1800014e2  mov     rcx, [rbx+r15*8+20h]
0x1800014e7  mov     edx, [r14+30h]
0x1800014eb  and     edx, 4
0x1800014ee  mov     rax, [rcx]
0x1800014f1  mov     rax, [rax+80h]
0x1800014f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014fd  mov     rcx, [rbx+r15*8+20h]
0x180001502  mov     edx, [r14+30h]
0x180001506  and     edx, 2
0x180001509  mov     rax, [rcx]
0x18000150c  mov     rax, [rax+50h]
0x180001510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001515  mov     rcx, [rbx+r15*8+20h]
0x18000151a  mov     edx, [r14+30h]
0x18000151e  and     edx, 1
0x180001521  mov     rax, [rcx]
0x180001524  mov     rax, [rax+40h]
0x180001528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000152d  mov     eax, [r14+30h]
0x180001531  test    al, 10h
0x180001533  jz      loc_180001382
0x180001539  mov     rcx, [r14+8]
0x18000153d  lea     r12, [rsp+0C8h+arg_18]
0x180001545  mov     [rsp+0C8h+arg_18], rcx
0x18000154d  bt      eax, 8
0x180001551  jnb     loc_180001382
0x180001557  add     rcx, [r14+18h]
0x18000155b  lea     rax, [rsp+0C8h+var_98]
0x180001560  mov     [rsp+0C8h+var_98], rcx
0x180001565  mov     [rsp+0C8h+arg_10], rax
0x18000156d  jmp     loc_180001382
0x180001572  mov     rcx, [rbx+r15*8+20h]
0x180001577  mov     rax, [rcx]
0x18000157a  mov     rax, [rax+10h]
0x18000157e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001583  jmp     loc_180001417
0x180001588  call    cs:__imp_GetLastError
0x18000158f  nop     dword ptr [rax+rax+00h]
0x180001594  mov     r15d, eax
0x180001597  mov     [rsp+0C8h+arg_0], eax
0x18000159e  jmp     loc_1800012E7
0x1800015a3  xor     edx, edx
0x1800015a5  jmp     loc_1800013ED
0x1800015aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015b1  cmp     rcx, rax
0x1800015b4  jz      short loc_1800015C0
0x1800015b6  cmp     byte ptr [rcx+19h], 1
0x1800015ba  jnb     loc_18000172A
0x1800015c0  movsxd  r12, esi
0x1800015c3  mov     rcx, [rbx+r12*8+20h]; struct IMediaSample *
0x1800015c8  call    ?IsD3DMediaSample@@YAHPEAUIMediaSample@@@Z; IsD3DMediaSample(IMediaSample *)
0x1800015cd  test    eax, eax
0x1800015cf  jnz     loc_180001747
0x1800015d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015dc  cmp     byte ptr [rdi+28h], 0
0x1800015e0  jnz     loc_18000130C
0x1800015e6  lea     rax, WPP_GLOBAL_Control
0x1800015ed  cmp     rcx, rax
0x1800015f0  jz      short loc_180001621
0x1800015f2  mov     r8, [rbx+230h]
0x1800015f9  test    r15d, r15d
0x1800015fc  jle     loc_1800017D4
0x180001602  movzx   eax, r15w
0x180001606  or      eax, 80070000h
0x18000160b  mov     rcx, [rcx+10h]
0x18000160f  mov     edx, 0Fh
0x180001614  movsxd  r9, eax
0x180001617  mov     [rsp+0C8h+var_A8], r8
0x18000161c  call    WPP_SF_PP
0x180001621  mov     rcx, [rdi+18h]
0x180001625  mov     rax, [rcx]
0x180001628  test    r15d, r15d
0x18000162b  jle     short loc_180001638
0x18000162d  movzx   r15d, r15w
0x180001631  or      r15d, 80070000h
0x180001638  mov     rdx, [rbx+r12*8+20h]
0x18000163d  mov     r8d, r15d
0x180001640  mov     rax, [rax+80h]
0x180001647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000164c  jmp     loc_18000130C
0x180001651  mov     r8, [rbx+230h]
0x180001658  test    r15d, r15d
0x18000165b  jle     loc_1800017A4
0x180001661  movzx   eax, r15w
0x180001665  or      eax, 80070000h
0x18000166a  mov     rcx, [rcx+10h]
0x18000166e  mov     edx, 0Eh
0x180001673  movsxd  r9, eax
0x180001676  mov     [rsp+0C8h+var_A8], r8
0x18000167b  call    WPP_SF_PP
0x180001680  mov     rcx, cs:WPP_GLOBAL_Control
0x180001687  cmp     qword ptr [rbx+230h], 0FFFFFFFFC000000Dh
0x180001692  jz      short loc_1800016D0
0x180001694  movzx   eax, r15w
0x180001698  or      eax, 80070000h
0x18000169d  test    r15d, r15d
0x1800016a0  jle     loc_1800017AC
0x1800016a6  mov     edx, eax
0x1800016a8  jmp     loc_1800017AF
0x1800016ad  test    r15d, r15d
0x1800016b0  jle     loc_1800017C0
0x1800016b6  mov     edx, eax
0x1800016b8  jmp     loc_1800017C3
0x1800016bd  test    r15d, r15d
0x1800016c0  jg      short loc_1800016C5
0x1800016c2  mov     eax, r15d
0x1800016c5  cmp     eax, 800706F8h
0x1800016ca  jnz     loc_1800015DC
0x1800016d0  cmp     byte ptr [rdi+28h], 0
0x1800016d4  jnz     loc_18000130C
0x1800016da  mov     rcx, [rbx+r12*8+20h]; struct IMediaSample *
0x1800016df  call    ?RestartGraph@@YAJPEAUIMediaSample@@@Z; RestartGraph(IMediaSample *)
0x1800016e4  test    eax, eax
0x1800016e6  js      loc_1800015D5
0x1800016ec  mov     byte ptr [rdi+28h], 1
0x1800016f0  jmp     loc_1800015D5
0x1800016f5  mov     eax, [rsp+0C8h+arg_0]
0x1800016fc  mov     r8, [rbx+230h]
0x180001703  test    eax, eax
0x180001705  jle     short loc_18000170F
0x180001707  movzx   eax, ax
0x18000170a  or      eax, 80070000h
0x18000170f  mov     rcx, [rcx+10h]
0x180001713  mov     edx, 11h
0x180001718  movsxd  r9, eax
0x18000171b  mov     [rsp+0C8h+var_A8], r8
0x180001720  call    WPP_SF_PP
0x180001725  jmp     loc_180001961
0x18000172a  mov     rcx, [rcx+10h]
0x18000172e  lea     r8, WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids
0x180001735  mov     edx, 0Dh
0x18000173a  mov     r9, rbx
0x18000173d  call    WPP_SF_q
0x180001742  jmp     loc_1800015C0
0x180001747  mov     rax, [r14+28h]
0x18000174b  mov     [rsp+0C8h+arg_10], rax
0x180001753  test    rax, rax
0x180001756  jz      short loc_180001788
0x180001758  mov     rcx, [rbx+r12*8+20h]
0x18000175d  xor     edx, edx
0x18000175f  mov     rax, [rcx]
0x180001762  mov     rax, [rax+60h]
0x180001766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000176b  mov     rcx, [rsp+0C8h+arg_10]; void *
0x180001773  xor     edx, edx; Val
0x180001775  mov     r8d, 0A8h; Size
0x18000177b  call    memset_0
0x180001780  mov     qword ptr [r14+28h], 0
0x180001788  mov     rcx, cs:WPP_GLOBAL_Control
0x18000178f  lea     rax, WPP_GLOBAL_Control
0x180001796  cmp     rcx, rax
0x180001799  jz      loc_180001687
0x18000179f  jmp     loc_180001651
0x1800017a4  mov     eax, r15d
0x1800017a7  jmp     loc_18000166A
0x1800017ac  mov     edx, r15d
0x1800017af  cmp     edx, 8007001Fh
0x1800017b5  jz      loc_1800016D0
0x1800017bb  jmp     loc_1800016AD
0x1800017c0  mov     edx, r15d
0x1800017c3  cmp     edx, 80070057h
0x1800017c9  jz      loc_1800016D0
0x1800017cf  jmp     loc_1800016BD
0x1800017d4  mov     eax, r15d
0x1800017d7  jmp     loc_18000160B
0x1800017dc  mov     rcx, [rbx+r15*8+20h]
0x1800017e1  lea     r8, [rsp+0C8h+arg_10]
  ... truncated ...
```
