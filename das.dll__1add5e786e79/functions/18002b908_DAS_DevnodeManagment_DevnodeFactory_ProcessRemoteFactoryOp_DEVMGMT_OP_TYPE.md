# DAS::DevnodeManagment::DevnodeFactory::ProcessRemoteFactoryOp(DEVMGMT_OP_TYPE)

- ea: `0x18002b908`
- end: `0x18002bcc7`
- name: `?ProcessRemoteFactoryOp@DevnodeFactory@DevnodeManagment@DAS@@AEAAJW4DEVMGMT_OP_TYPE@@@Z`
- size: `959`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x1800278a0`

## callees

- `0x1800074c0`
- `0x180015de8`
- `0x1800166b8`
- `0x18001dfe0`
- `0x18001eae0`
- `0x18002a948`
- `0x18002b908`
- `0x18005c168`
- `0x18005c6e4`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b9a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002ba3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002ba78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b9a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002ba3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002ba78`

## string_xrefs

- `0x18002b98c`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002ba21`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002ba98`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002bb1f`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002bb7f`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002bc34`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DAS::DevnodeManagment::DevnodeFactory::ProcessRemoteFactoryOp(unsigned __int64 a1, int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  int DasHostFactoryOp; // eax
  __int64 v7; // rcx
  int v8; // esi
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v18; // [rsp+20h] [rbp-89h]
  int v19; // [rsp+20h] [rbp-89h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-79h] BYREF
  struct _DAS_SW_DEVICE_CREATE_INFO *v21; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v22[2]; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v23[2]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v24[6]; // [rsp+50h] [rbp-59h] BYREF
  char v25; // [rsp+80h] [rbp-29h]
  _OWORD v26[4]; // [rsp+90h] [rbp-19h] BYREF
  PVOID Ptr; // [rsp+D0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  int v29; // [rsp+110h] [rbp+67h] BYREF
  struct _DAS_SW_DEVICE_CREATE_INFO *v30; // [rsp+120h] [rbp+77h] BYREF
  __int64 v31; // [rsp+128h] [rbp+7Fh] BYREF

  *(_QWORD *)v23 = 0;
  v21 = 0;
  LODWORD(v30) = 0;
  *(_QWORD *)v22 = 0;
  v31 = 0;
  v29 = 0;
  v24[0] = &v21;
  v24[1] = v22;
  v24[2] = &v30;
  v24[3] = &v29;
  v24[4] = &v31;
  v24[5] = a1;
  wil::AcquireSRWLockShared(&SRWLock, (RTL_SRWLOCK *)(a1 + 224));
  if ( !*(_BYTE *)(a1 + 232) )
  {
    v4 = -2140930029;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E7,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
      (const char *)0x80640013LL,
      v18);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    v25 = 0;
    lambda_e254b81f94a478849e6697b204f20e3b_::operator()(v24);
    v5 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    goto LABEL_36;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v23,
    0);
  DasHostFactoryOp = DAS::DevnodeManagment::GetDasHostFactoryOp(
                       (DAS::DevnodeManagment *)(a1 + 192),
                       (void **)*(unsigned int *)(a1 + 216),
                       (unsigned int)v23,
                       (unsigned __int16 **)&v21,
                       &v30,
                       v22,
                       (struct _DEVPROPERTY **)SRWLock);
  v4 = DasHostFactoryOp;
  v29 = DasHostFactoryOp;
  if ( DasHostFactoryOp < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
      (const char *)(unsigned int)DasHostFactoryOp,
      v19);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    v25 = 0;
    lambda_e254b81f94a478849e6697b204f20e3b_::operator()(v24);
    v7 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    goto LABEL_36;
  }
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v8 = a2 - 16;
  if ( v8 )
  {
    if ( v8 != 1 )
    {
      v4 = -2147467263;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30D,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)0x80004001LL,
        v19);
      v25 = 0;
      lambda_e254b81f94a478849e6697b204f20e3b_::operator()(v24);
      v9 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      goto LABEL_36;
    }
    v10 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 32LL))(
            a1,
            *((_QWORD *)v21 + 1),
            (unsigned int)v30,
            *(_QWORD *)v22);
    v4 = v10;
    v29 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x307,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)(unsigned int)v10,
        (a1 + 16) & ((unsigned __int128)-(__int128)a1 >> 64));
      v25 = 0;
      lambda_e254b81f94a478849e6697b204f20e3b_::operator()(v24);
      v11 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      goto LABEL_36;
    }
    goto LABEL_33;
  }
  SRWLock = 0;
  v12 = MidlDasDeviceCreationInfoToSwDeviceCreationInfo(v21, (struct _SW_DEVICE_CREATE_INFO **)&SRWLock);
  v4 = v12;
  v29 = v12;
  if ( v12 >= 0 )
  {
    v26[0] = *(_OWORD *)&SRWLock->Ptr;
    v26[1] = *(_OWORD *)&SRWLock[2].Ptr;
    v26[2] = *(_OWORD *)&SRWLock[4].Ptr;
    v26[3] = *(_OWORD *)&SRWLock[6].Ptr;
    Ptr = SRWLock[8].Ptr;
    v14 = (*(__int64 (__fastcall **)(unsigned __int64, _OWORD *, _QWORD, _QWORD))(*(_QWORD *)a1 + 24LL))(
            a1,
            v26,
            (unsigned int)v30,
            *(_QWORD *)v22);
    v4 = v14;
    v29 = v14;
    if ( v14 >= 0 )
    {
      MidlFreeSwDeviceCreationInfo((struct _SW_DEVICE_CREATE_INFO *)SRWLock);
LABEL_33:
      v25 = 0;
      lambda_e254b81f94a478849e6697b204f20e3b_::operator()(v24);
      v16 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v4 = 0;
      goto LABEL_36;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FE,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
      (const char *)(unsigned int)v14,
      (a1 + 16) & ((unsigned __int128)-(__int128)a1 >> 64));
    MidlFreeSwDeviceCreationInfo((struct _SW_DEVICE_CREATE_INFO *)SRWLock);
    v25 = 0;
    lambda_e254b81f94a478849e6697b204f20e3b_::operator()(v24);
    v15 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F9,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
      (const char *)(unsigned int)v12,
      v19);
    MidlFreeSwDeviceCreationInfo((struct _SW_DEVICE_CREATE_INFO *)SRWLock);
    v25 = 0;
    lambda_e254b81f94a478849e6697b204f20e3b_::operator()(v24);
    v13 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)v23);
  return v4;
}

```

## disassembly

```asm
0x18002b908  push    rbp
0x18002b90a  push    rbx
0x18002b90b  push    rsi
0x18002b90c  push    rdi
0x18002b90d  push    r14
0x18002b90f  lea     rbp, [rsp-37h]
0x18002b914  sub     rsp, 0E0h
0x18002b91b  mov     esi, edx
0x18002b91d  mov     rdi, rcx
0x18002b920  xor     r14d, r14d
0x18002b923  mov     qword ptr [rbp+57h+var_B8], r14
0x18002b927  mov     [rbp+57h+var_C8], r14
0x18002b92b  mov     dword ptr [rbp+57h+arg_10], r14d
0x18002b92f  mov     qword ptr [rbp+57h+var_C0], r14
0x18002b933  mov     [rbp+57h+arg_18], r14
0x18002b937  mov     [rbp+57h+arg_0], r14d
0x18002b93b  lea     rax, [rbp+57h+var_C8]
0x18002b93f  mov     [rbp+57h+var_B0], rax
0x18002b943  lea     rax, [rbp+57h+var_C0]
0x18002b947  mov     [rbp+57h+var_A8], rax
0x18002b94b  lea     rax, [rbp+57h+arg_10]
0x18002b94f  mov     [rbp+57h+var_A0], rax
0x18002b953  lea     rax, [rbp+57h+arg_0]
0x18002b957  mov     [rbp+57h+var_98], rax
0x18002b95b  lea     rax, [rbp+57h+arg_18]
0x18002b95f  mov     [rbp+57h+var_90], rax
0x18002b963  mov     [rbp+57h+var_88], rcx
0x18002b967  lea     rdx, [rcx+0E0h]
0x18002b96e  lea     rcx, [rbp+57h+SRWLock]
0x18002b972  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18002b977  cmp     [rdi+0E8h], r14b
0x18002b97e  jnz     short loc_18002B9DA
0x18002b980  mov     rcx, [rbp+5Fh]; this
0x18002b984  mov     ebx, 80640013h
0x18002b989  mov     r9d, ebx; char *
0x18002b98c  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002b993  mov     edx, 2E7h; void *
0x18002b998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b99d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002b9a1  test    rcx, rcx
0x18002b9a4  jz      short loc_18002B9AD
0x18002b9a6  call    cs:__imp_ReleaseSRWLockShared
0x18002b9ac  nop
0x18002b9ad  mov     [rbp+57h+var_80], r14b
0x18002b9b1  lea     rcx, [rbp+57h+var_B0]
0x18002b9b5  call    _lambda_e254b81f94a478849e6697b204f20e3b___operator__
0x18002b9ba  nop
0x18002b9bb  mov     rcx, [rbp+57h+arg_18]
0x18002b9bf  test    rcx, rcx
0x18002b9c2  jz      short loc_18002B9D5
0x18002b9c4  mov     [rbp+57h+arg_18], r14
0x18002b9c8  mov     rax, [rcx]
0x18002b9cb  mov     rax, [rax+10h]
0x18002b9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9d4  nop
0x18002b9d5  jmp     loc_18002BCAE
0x18002b9da  xor     edx, edx
0x18002b9dc  lea     rcx, [rbp+57h+var_B8]
0x18002b9e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b9e5  lea     rcx, [rdi+0C0h]; this
0x18002b9ec  lea     rax, [rbp+57h+var_C0]
0x18002b9f0  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18002b9f5  lea     rax, [rbp+57h+arg_10]
0x18002b9f9  mov     [rsp+100h+var_E0], rax; int
0x18002b9fe  lea     r9, [rbp+57h+var_C8]; unsigned __int16 **
0x18002ba02  lea     r8, [rbp+57h+var_B8]; unsigned int
0x18002ba06  mov     edx, [rdi+0D8h]; void **
0x18002ba0c  call    ?GetDasHostFactoryOp@DevnodeManagment@DAS@@YAJPEAPEAXKPEAPEAGPEAPEAU_DAS_SW_DEVICE_CREATE_INFO@@PEAKPEAPEAU_DEVPROPERTY@@@Z; DAS::DevnodeManagment::GetDasHostFactoryOp(void * *,ulong,ushort * *,_DAS_SW_DEVICE_CREATE_INFO * *,ulong *,_DEVPROPERTY * *)
0x18002ba11  mov     ebx, eax
0x18002ba13  mov     [rbp+57h+arg_0], eax
0x18002ba16  test    eax, eax
0x18002ba18  jns     short loc_18002BA6F
0x18002ba1a  mov     rcx, [rbp+5Fh]; this
0x18002ba1e  mov     r9d, eax; char *
0x18002ba21  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002ba28  mov     edx, 2F0h; void *
0x18002ba2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba32  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002ba36  test    rcx, rcx
0x18002ba39  jz      short loc_18002BA42
0x18002ba3b  call    cs:__imp_ReleaseSRWLockShared
0x18002ba41  nop
0x18002ba42  mov     [rbp+57h+var_80], r14b
0x18002ba46  lea     rcx, [rbp+57h+var_B0]
0x18002ba4a  call    _lambda_e254b81f94a478849e6697b204f20e3b___operator__
0x18002ba4f  nop
0x18002ba50  mov     rcx, [rbp+57h+arg_18]
0x18002ba54  test    rcx, rcx
0x18002ba57  jz      short loc_18002BA6A
0x18002ba59  mov     [rbp+57h+arg_18], r14
0x18002ba5d  mov     rax, [rcx]
0x18002ba60  mov     rax, [rax+10h]
0x18002ba64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba69  nop
0x18002ba6a  jmp     loc_18002BCAE
0x18002ba6f  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002ba73  test    rcx, rcx
0x18002ba76  jz      short loc_18002BA7E
0x18002ba78  call    cs:__imp_ReleaseSRWLockShared
0x18002ba7e  sub     esi, 10h
0x18002ba81  jz      loc_18002BB5E
0x18002ba87  cmp     esi, 1
0x18002ba8a  jz      short loc_18002BAD7
0x18002ba8c  mov     rcx, [rbp+5Fh]; this
0x18002ba90  mov     ebx, 80004001h
0x18002ba95  mov     r9d, ebx; char *
0x18002ba98  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002ba9f  mov     edx, 30Dh; void *
0x18002baa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002baa9  nop
0x18002baaa  mov     [rbp+57h+var_80], r14b
0x18002baae  lea     rcx, [rbp+57h+var_B0]
0x18002bab2  call    _lambda_e254b81f94a478849e6697b204f20e3b___operator__
0x18002bab7  nop
0x18002bab8  mov     rcx, [rbp+57h+arg_18]
0x18002babc  test    rcx, rcx
0x18002babf  jz      short loc_18002BAD2
0x18002bac1  mov     [rbp+57h+arg_18], r14
0x18002bac5  mov     rax, [rcx]
0x18002bac8  mov     rax, [rax+10h]
0x18002bacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bad1  nop
0x18002bad2  jmp     loc_18002BCAE
0x18002bad7  mov     r8, [rdi]
0x18002bada  mov     rax, rdi
0x18002badd  lea     rcx, [rdi+10h]
0x18002bae1  neg     rax
0x18002bae4  sbb     rdx, rdx
0x18002bae7  and     rdx, rcx
0x18002baea  mov     rax, [r8+20h]
0x18002baee  mov     [rsp+100h+var_E0], rdx; int
0x18002baf3  mov     r9, qword ptr [rbp+57h+var_C0]
0x18002baf7  mov     r8d, dword ptr [rbp+57h+arg_10]
0x18002bafb  mov     rdx, [rbp+57h+var_C8]
0x18002baff  mov     rdx, [rdx+8]
0x18002bb03  mov     rcx, rdi
0x18002bb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb0b  mov     ebx, eax
0x18002bb0d  mov     [rbp+57h+arg_0], eax
0x18002bb10  test    eax, eax
0x18002bb12  jns     loc_18002BC83
0x18002bb18  mov     rcx, [rbp+5Fh]; this
0x18002bb1c  mov     r9d, eax; char *
0x18002bb1f  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002bb26  mov     edx, 307h; void *
0x18002bb2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bb30  nop
0x18002bb31  mov     [rbp+57h+var_80], r14b
0x18002bb35  lea     rcx, [rbp+57h+var_B0]
0x18002bb39  call    _lambda_e254b81f94a478849e6697b204f20e3b___operator__
0x18002bb3e  nop
0x18002bb3f  mov     rcx, [rbp+57h+arg_18]
0x18002bb43  test    rcx, rcx
0x18002bb46  jz      short loc_18002BB59
0x18002bb48  mov     [rbp+57h+arg_18], r14
0x18002bb4c  mov     rax, [rcx]
0x18002bb4f  mov     rax, [rax+10h]
0x18002bb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb58  nop
0x18002bb59  jmp     loc_18002BCAE
0x18002bb5e  mov     [rbp+57h+SRWLock], r14
0x18002bb62  lea     rdx, [rbp+57h+SRWLock]; struct _SW_DEVICE_CREATE_INFO **
0x18002bb66  mov     rcx, [rbp+57h+var_C8]; struct _DAS_SW_DEVICE_CREATE_INFO *
0x18002bb6a  call    ?MidlDasDeviceCreationInfoToSwDeviceCreationInfo@@YAJPEAU_DAS_SW_DEVICE_CREATE_INFO@@PEAPEAU_SW_DEVICE_CREATE_INFO@@@Z; MidlDasDeviceCreationInfoToSwDeviceCreationInfo(_DAS_SW_DEVICE_CREATE_INFO *,_SW_DEVICE_CREATE_INFO * *)
0x18002bb6f  mov     ebx, eax
0x18002bb71  mov     [rbp+57h+arg_0], eax
0x18002bb74  test    eax, eax
0x18002bb76  jns     short loc_18002BBC7
0x18002bb78  mov     rcx, [rbp+5Fh]; this
0x18002bb7c  mov     r9d, eax; char *
0x18002bb7f  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002bb86  mov     edx, 2F9h; void *
0x18002bb8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bb90  mov     rcx, [rbp+57h+SRWLock]; lpMem
0x18002bb94  call    ?MidlFreeSwDeviceCreationInfo@@YAXPEAU_SW_DEVICE_CREATE_INFO@@@Z; MidlFreeSwDeviceCreationInfo(_SW_DEVICE_CREATE_INFO *)
0x18002bb99  nop
0x18002bb9a  mov     [rbp+57h+var_80], r14b
0x18002bb9e  lea     rcx, [rbp+57h+var_B0]
0x18002bba2  call    _lambda_e254b81f94a478849e6697b204f20e3b___operator__
0x18002bba7  nop
0x18002bba8  mov     rcx, [rbp+57h+arg_18]
0x18002bbac  test    rcx, rcx
0x18002bbaf  jz      short loc_18002BBC2
0x18002bbb1  mov     [rbp+57h+arg_18], r14
0x18002bbb5  mov     rax, [rcx]
0x18002bbb8  mov     rax, [rax+10h]
0x18002bbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbc1  nop
0x18002bbc2  jmp     loc_18002BCAE
0x18002bbc7  mov     rax, [rbp+57h+SRWLock]
0x18002bbcb  movups  xmm0, xmmword ptr [rax]
0x18002bbce  movaps  [rbp+57h+var_70], xmm0
0x18002bbd2  movups  xmm1, xmmword ptr [rax+10h]
0x18002bbd6  movaps  [rbp+57h+var_60], xmm1
0x18002bbda  movups  xmm0, xmmword ptr [rax+20h]
0x18002bbde  movaps  [rbp+57h+var_50], xmm0
0x18002bbe2  movups  xmm1, xmmword ptr [rax+30h]
0x18002bbe6  movaps  [rbp+57h+var_40], xmm1
0x18002bbea  movsd   xmm0, qword ptr [rax+40h]
0x18002bbef  movsd   [rbp+57h+var_30], xmm0
0x18002bbf4  mov     r8, [rdi]
0x18002bbf7  mov     rax, rdi
0x18002bbfa  lea     rcx, [rdi+10h]
0x18002bbfe  neg     rax
0x18002bc01  sbb     rdx, rdx
0x18002bc04  and     rdx, rcx
0x18002bc07  mov     rax, [r8+18h]
0x18002bc0b  mov     [rsp+100h+var_E0], rdx; int
0x18002bc10  mov     r9, qword ptr [rbp+57h+var_C0]
0x18002bc14  mov     r8d, dword ptr [rbp+57h+arg_10]
0x18002bc18  lea     rdx, [rbp+57h+var_70]
0x18002bc1c  mov     rcx, rdi
0x18002bc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc24  mov     ebx, eax
0x18002bc26  mov     [rbp+57h+arg_0], eax
0x18002bc29  test    eax, eax
0x18002bc2b  jns     short loc_18002BC79
0x18002bc2d  mov     rcx, [rbp+5Fh]; this
0x18002bc31  mov     r9d, eax; char *
0x18002bc34  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002bc3b  mov     edx, 2FEh; void *
0x18002bc40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bc45  mov     rcx, [rbp+57h+SRWLock]; lpMem
0x18002bc49  call    ?MidlFreeSwDeviceCreationInfo@@YAXPEAU_SW_DEVICE_CREATE_INFO@@@Z; MidlFreeSwDeviceCreationInfo(_SW_DEVICE_CREATE_INFO *)
0x18002bc4e  nop
0x18002bc4f  mov     [rbp+57h+var_80], r14b
0x18002bc53  lea     rcx, [rbp+57h+var_B0]
0x18002bc57  call    _lambda_e254b81f94a478849e6697b204f20e3b___operator__
0x18002bc5c  nop
0x18002bc5d  mov     rcx, [rbp+57h+arg_18]
0x18002bc61  test    rcx, rcx
0x18002bc64  jz      short loc_18002BC77
0x18002bc66  mov     [rbp+57h+arg_18], r14
0x18002bc6a  mov     rax, [rcx]
0x18002bc6d  mov     rax, [rax+10h]
0x18002bc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc76  nop
0x18002bc77  jmp     short loc_18002BCAE
0x18002bc79  mov     rcx, [rbp+57h+SRWLock]; lpMem
0x18002bc7d  call    ?MidlFreeSwDeviceCreationInfo@@YAXPEAU_SW_DEVICE_CREATE_INFO@@@Z; MidlFreeSwDeviceCreationInfo(_SW_DEVICE_CREATE_INFO *)
0x18002bc82  nop
0x18002bc83  mov     [rbp+57h+var_80], r14b
0x18002bc87  lea     rcx, [rbp+57h+var_B0]
0x18002bc8b  call    _lambda_e254b81f94a478849e6697b204f20e3b___operator__
0x18002bc90  nop
0x18002bc91  mov     rcx, [rbp+57h+arg_18]
0x18002bc95  test    rcx, rcx
0x18002bc98  jz      short loc_18002BCAB
0x18002bc9a  mov     [rbp+57h+arg_18], r14
0x18002bc9e  mov     rax, [rcx]
0x18002bca1  mov     rax, [rax+10h]
0x18002bca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcaa  nop
0x18002bcab  mov     ebx, r14d
0x18002bcae  lea     rcx, [rbp+57h+var_B8]
0x18002bcb2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bcb7  mov     eax, ebx
0x18002bcb9  add     rsp, 0E0h
0x18002bcc0  pop     r14
0x18002bcc2  pop     rdi
0x18002bcc3  pop     rsi
0x18002bcc4  pop     rbx
0x18002bcc5  pop     rbp
0x18002bcc6  retn
```
