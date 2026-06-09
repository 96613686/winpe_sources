# RtlLockComponentStoreComponent

- ea: `0x1800fa36c`
- end: `0x1800faa15`
- name: `RtlLockComponentStoreComponent`
- size: `1705`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800aed6c`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012b1c`
- `0x180016e64`
- `0x180016f8c`
- `0x18001ccac`
- `0x18002dde4`
- `0x18002decc`
- `0x180042f10`
- `0x180048470`
- `0x18004f2dc`
- `0x1800f9bec`
- `0x1800f9ed0`
- `0x1800fa2a4`
- `0x1800fa36c`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fa5a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fa6a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fa7b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fa870`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fa5a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fa6a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fa7b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fa870`

## string_xrefs

- `0x1800fa558`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800fa644`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800fa766`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800fa81f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800fa38d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\cs_clock.cpp`

## pseudocode

```c
__int64 __fastcall RtlLockComponentStoreComponent(
        __int64 a1,
        __int64 a2,
        Windows::Isolation::FsProv::Rtl *a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *v5; // r15
  __int64 i; // rbx
  int AllocationListArray; // esi
  Windows::Isolation::FsProv::Rtl *v10; // r12
  __int64 j; // rbx
  __int64 v12; // rcx
  Windows::Isolation::FsProv::Rtl *v13; // r14
  Windows::Isolation::FsProv::Rtl *v14; // rcx
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // r10
  unsigned int *v18; // r11
  signed int v19; // ecx
  void (__fastcall *v20)(LPVOID *); // rax
  HANDLE v21; // rax
  LPVOID *v22; // rbx
  Windows::Isolation::FsProv::Rtl *v23; // rbx
  unsigned int *v24; // r10
  signed int v25; // ecx
  void (__fastcall *v26)(LPVOID *); // rax
  HANDLE v27; // rax
  LPVOID *v28; // rbx
  __int64 v29; // r14
  __int64 v30; // rdx
  unsigned int *v31; // r10
  signed int v32; // ecx
  void (__fastcall *v33)(LPVOID *); // rax
  LPVOID *v34; // rcx
  LPVOID *v35; // rbx
  unsigned int *v36; // r10
  signed int v37; // ecx
  void (__fastcall *v38)(LPVOID *); // rax
  HANDLE v39; // rax
  LPVOID *v40; // rbx
  void (__fastcall *v41)(LPVOID *); // rax
  HANDLE v42; // rax
  LPVOID *v43; // rbx
  void (__fastcall *v44)(LPVOID *); // rax
  HANDLE v45; // rax
  LPVOID *v46; // rbx
  void (__fastcall *v47)(LPVOID *); // rax
  HANDLE v48; // rax
  LPVOID *v49; // rbx
  void (__fastcall *v50)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v52; // rbx
  struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *v54; // [rsp+20h] [rbp-69h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v56; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v57; // [rsp+48h] [rbp-41h]
  unsigned int v58; // [rsp+50h] [rbp-39h]
  const char *v59; // [rsp+58h] [rbp-31h] BYREF
  __int64 v60; // [rsp+60h] [rbp-29h]
  DWORD dwExceptionCode[2]; // [rsp+68h] [rbp-21h]
  const char *v62; // [rsp+70h] [rbp-19h] BYREF
  int v63; // [rsp+78h] [rbp-11h]
  int v64; // [rsp+80h] [rbp-9h]
  Windows::Isolation::FsProv::Rtl *v65; // [rsp+F0h] [rbp+67h] BYREF

  v65 = a3;
  v5 = a5;
  v58 = -1073741595;
  v56 = (__int64)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\cs_clock.cpp";
  if ( a5 )
    *a5 = 0;
  if ( !(unsigned __int8)RtlIsComponentStoreHandleValid(a2) )
  {
    LODWORD(v57) = 112;
LABEL_93:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v56);
    return v58;
  }
  if ( !a4 )
  {
    LODWORD(v57) = 114;
    goto LABEL_93;
  }
  if ( !v5 )
  {
    LODWORD(v57) = 115;
    goto LABEL_93;
  }
  for ( i = 0; i != 1; ++i )
  {
    if ( !qword_180166950 || !(unsigned __int8)RtlIsBaseIdentityHandleValidWithType(*(_QWORD *)qword_180166950) )
    {
      LODWORD(v57) = 118;
      goto LABEL_93;
    }
  }
  v56 = 1;
  lpMem[1] = lpMem;
  v57 = v5;
  lpMem[0] = lpMem;
  v65 = 0;
  AllocationListArray = RtlAllocateAllocationListArray(
                          (unsigned int)lpMem,
                          1,
                          16,
                          (unsigned int)Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
                          (__int64)&v65);
  if ( AllocationListArray < 0 )
  {
    while ( 1 )
    {
      v52 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v52 == lpMem )
        break;
      v50 = (void (__fastcall *)(LPVOID *))v52[2];
      if ( v50 )
        v50(v52 + 3);
      ProcessHeap_0 = GetProcessHeap_0();
      HeapFree_0(ProcessHeap_0, 0, v52);
    }
  }
  else
  {
    v10 = v65;
    for ( j = 0; j != 1; ++j )
    {
      v65 = 0;
      AllocationListArray = RtlAllocateAllocationListMemory(
                              lpMem,
                              32,
                              Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
                              &v65);
      if ( AllocationListArray < 0 )
      {
        while ( 1 )
        {
          v49 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v49 == lpMem )
            break;
          v47 = (void (__fastcall *)(LPVOID *))v49[2];
          if ( v47 )
            v47(v49 + 3);
          v48 = GetProcessHeap_0();
          HeapFree_0(v48, 0, v49);
        }
        goto LABEL_71;
      }
      v13 = v65;
      AllocationListArray = RtlGenerateComponentStoreLockIdentifier(v12, v65);
      if ( AllocationListArray < 0 )
      {
        while ( 1 )
        {
          v46 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v46 == lpMem )
            break;
          v44 = (void (__fastcall *)(LPVOID *))v46[2];
          if ( v44 )
            v44(v46 + 3);
          v45 = GetProcessHeap_0();
          HeapFree_0(v45, 0, v46);
        }
        goto LABEL_71;
      }
      v65 = 0;
      AllocationListArray = RtlAllocateAllocationListMemory(
                              lpMem,
                              40,
                              Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
                              &v65);
      if ( AllocationListArray < 0 )
      {
        while ( 1 )
        {
          v43 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v43 == lpMem )
            break;
          v41 = (void (__fastcall *)(LPVOID *))v43[2];
          if ( v41 )
            v41(v43 + 3);
          v42 = GetProcessHeap_0();
          HeapFree_0(v42, 0, v43);
        }
        goto LABEL_71;
      }
      v14 = v65;
      *((_QWORD *)v65 + 1) = *(_QWORD *)(a4 + 8 * j);
      *((_QWORD *)v14 + 2) = v13;
      v15 = 2 * j;
      *(_QWORD *)v14 = 40;
      *((_DWORD *)v10 + 2 * v15) = 9;
      *((_QWORD *)v10 + v15 + 1) = v14;
    }
    v65 = 0;
    AllocationListArray = Windows::Isolation::FsProv::Rtl::CreateIsolatedFilesystemFromProvider(
                            v14,
                            (unsigned int)&RtlpNullIsolatedFilesystem,
                            (struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *)&v65,
                            0,
                            v54);
    if ( AllocationListArray >= 0 )
    {
      v23 = v65;
      AllocationListArray = RtlTransactComponentStore(v16, (int)v65, a2, 1, (__int64)v10, 0);
      if ( AllocationListArray >= 0 )
      {
        v29 = 0;
        while ( 1 )
        {
          *(_QWORD *)dwExceptionCode = *(_QWORD *)(a4 + 8 * v29);
          v59 = 0;
          v60 = 0;
          v59 = *(const char **)(*((_QWORD *)v10 + 2 * v29 + 1) + 16LL);
          v60 = a2;
          AllocationListArray = Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_LOCK,CComponentStoreComponentLock,CComponentStoreComponentLockCD,CComponentStoreComponentLockTraits>::Allocate(
                                  &v59,
                                  &v5[v29]);
          if ( AllocationListArray < 0 )
            break;
          if ( ++v29 == 1 )
          {
            AllocationListArray = 0;
            v56 = 0;
            v57 = 0;
            if ( v23 )
            {
              ++g_nRtlCloseIsolatedFilesystemHandle;
              dwExceptionCode[0] = -1073741595;
              v59 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
              {
                (*((void (__fastcall **)(_QWORD, Windows::Isolation::FsProv::Rtl *))v31 + 4))(*v31, v23);
                v32 = 0;
              }
              else
              {
                LODWORD(v60) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v59);
                v32 = dwExceptionCode[0];
              }
              if ( v32 < 0 )
                RaiseException(v32, 1u, 0, 0);
            }
            while ( 1 )
            {
              v35 = (LPVOID *)lpMem[0];
              v34 = lpMem;
              lpMem[0] = *(LPVOID *)lpMem[0];
              *((_QWORD *)lpMem[0] + 1) = lpMem;
              if ( v35 == lpMem )
                break;
              v33 = (void (__fastcall *)(LPVOID *))v35[2];
              if ( v33 )
                v33(v35 + 3);
              RtlFreeHeap(v34, v30, v35);
            }
            goto LABEL_71;
          }
        }
        if ( v23 )
        {
          ++g_nRtlCloseIsolatedFilesystemHandle;
          v64 = -1073741595;
          v62 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
          {
            (*((void (__fastcall **)(_QWORD, Windows::Isolation::FsProv::Rtl *))v36 + 4))(*v36, v23);
            v37 = 0;
          }
          else
          {
            v63 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v62);
            v37 = v64;
          }
          if ( v37 < 0 )
            RaiseException(v37, 1u, 0, 0);
        }
        while ( 1 )
        {
          v40 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v40 == lpMem )
            break;
          v38 = (void (__fastcall *)(LPVOID *))v40[2];
          if ( v38 )
            v38(v40 + 3);
          v39 = GetProcessHeap_0();
          HeapFree_0(v39, 0, v40);
        }
      }
      else
      {
        if ( v23 )
        {
          ++g_nRtlCloseIsolatedFilesystemHandle;
          dwExceptionCode[0] = -1073741595;
          v59 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
          {
            (*((void (__fastcall **)(_QWORD, Windows::Isolation::FsProv::Rtl *))v24 + 4))(*v24, v23);
            v25 = 0;
          }
          else
          {
            LODWORD(v60) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v59);
            v25 = dwExceptionCode[0];
          }
          if ( v25 < 0 )
            RaiseException(v25, 1u, 0, 0);
        }
        while ( 1 )
        {
          v28 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v28 == lpMem )
            break;
          v26 = (void (__fastcall *)(LPVOID *))v28[2];
          if ( v26 )
            v26(v28 + 3);
          v27 = GetProcessHeap_0();
          HeapFree_0(v27, 0, v28);
        }
      }
    }
    else
    {
      if ( v65 )
      {
        ++g_nRtlCloseIsolatedFilesystemHandle;
        dwExceptionCode[0] = -1073741595;
        v59 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v65) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v18 + 4))(*v18, v17);
          v19 = 0;
        }
        else
        {
          LODWORD(v60) = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v59);
          v19 = dwExceptionCode[0];
        }
        if ( v19 < 0 )
          RaiseException(v19, 1u, 0, 0);
      }
      while ( 1 )
      {
        v22 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v22 == lpMem )
          break;
        v20 = (void (__fastcall *)(LPVOID *))v22[2];
        if ( v20 )
          v20(v22 + 3);
        v21 = GetProcessHeap_0();
        HeapFree_0(v21, 0, v22);
      }
    }
  }
LABEL_71:
  BCL::CArrayLifetimeManager<unsigned __int64,CBaseHandleObjectArrayTraits<Windows::Isolation::Rtl::CCOMPONENT_STORE_COMPONENT_LOCK_Traits>>::~CArrayLifetimeManager<unsigned __int64,CBaseHandleObjectArrayTraits<Windows::Isolation::Rtl::CCOMPONENT_STORE_COMPONENT_LOCK_Traits>>(&v56);
  return (unsigned int)AllocationListArray;
}

```

## disassembly

```asm
0x1800fa36c  mov     [rsp-8+arg_10], r8
0x1800fa371  push    rbp
0x1800fa372  push    rbx
0x1800fa373  push    rsi
0x1800fa374  push    rdi
0x1800fa375  push    r12
0x1800fa377  push    r13
0x1800fa379  push    r14
0x1800fa37b  push    r15
0x1800fa37d  lea     rbp, [rsp-0Fh]
0x1800fa382  sub     rsp, 98h
0x1800fa389  mov     r15, [rbp+47h+arg_20]
0x1800fa38d  lea     rax, aOnecoreComNetf_85; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800fa394  mov     [rbp+47h+var_80], 0C00000E5h
0x1800fa39b  mov     r13, r9
0x1800fa39e  mov     [rbp+47h+var_90], rax
0x1800fa3a2  mov     rdi, rdx
0x1800fa3a5  test    r15, r15
0x1800fa3a8  jz      short loc_1800FA3B1
0x1800fa3aa  mov     qword ptr [r15], 0
0x1800fa3b1  mov     rcx, rdi
0x1800fa3b4  call    RtlIsComponentStoreHandleValid
0x1800fa3b9  test    al, al
0x1800fa3bb  jnz     short loc_1800FA3C9
0x1800fa3bd  mov     dword ptr [rbp+47h+var_88], 70h ; 'p'
0x1800fa3c4  jmp     loc_1800FA9F3
0x1800fa3c9  test    r13, r13
0x1800fa3cc  jnz     short loc_1800FA3E3
0x1800fa3ce  mov     dword ptr [rbp+47h+var_88], 72h ; 'r'
0x1800fa3d5  lea     rcx, [rbp+47h+var_90]
0x1800fa3d9  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800fa3de  jmp     loc_1800FA9FC
0x1800fa3e3  test    r15, r15
0x1800fa3e6  jnz     short loc_1800FA3F1
0x1800fa3e8  mov     dword ptr [rbp+47h+var_88], 73h ; 's'
0x1800fa3ef  jmp     short loc_1800FA3D5
0x1800fa3f1  xor     ebx, ebx
0x1800fa3f3  lea     r14d, [rbx+1]
0x1800fa3f7  mov     rcx, cs:qword_180166950
0x1800fa3fe  test    rcx, rcx
0x1800fa401  jz      loc_1800FA9EC
0x1800fa407  mov     rdx, [r13+rbx*8+0]
0x1800fa40c  mov     rcx, [rcx]
0x1800fa40f  call    RtlIsBaseIdentityHandleValidWithType
0x1800fa414  test    al, al
0x1800fa416  jz      loc_1800FA9EC
0x1800fa41c  add     rbx, r14
0x1800fa41f  cmp     rbx, r14
0x1800fa422  jnz     short loc_1800FA3F7
0x1800fa424  lea     rax, [rbp+47h+lpMem]
0x1800fa428  mov     [rbp+47h+var_90], r14
0x1800fa42c  mov     [rbp+47h+var_98], rax
0x1800fa430  lea     r9, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800fa437  lea     rax, [rbp+47h+lpMem]
0x1800fa43b  mov     [rbp+47h+var_88], r15
0x1800fa43f  mov     [rbp+47h+lpMem], rax
0x1800fa443  lea     rcx, [rbp+47h+lpMem]
0x1800fa447  lea     rax, [rbp+47h+arg_10]
0x1800fa44b  mov     [rbp+47h+arg_10], 0
0x1800fa453  mov     r8d, 10h
0x1800fa459  mov     [rsp+0D0h+var_B0], rax; struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *
0x1800fa45e  mov     rdx, r14
0x1800fa461  call    RtlAllocateAllocationListArray
0x1800fa466  mov     esi, eax
0x1800fa468  test    eax, eax
0x1800fa46a  js      loc_1800FA9CB
0x1800fa470  mov     r12, [rbp+47h+arg_10]
0x1800fa474  xor     ebx, ebx
0x1800fa476  lea     r9, [rbp+47h+arg_10]
0x1800fa47a  mov     [rbp+47h+arg_10], 0
0x1800fa482  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800fa489  mov     edx, 20h ; ' '
0x1800fa48e  lea     rcx, [rbp+47h+lpMem]
0x1800fa492  call    RtlAllocateAllocationListMemory
0x1800fa497  mov     esi, eax
0x1800fa499  test    eax, eax
0x1800fa49b  js      loc_1800FA986
0x1800fa4a1  mov     r14, [rbp+47h+arg_10]
0x1800fa4a5  mov     rdx, r14
0x1800fa4a8  call    RtlGenerateComponentStoreLockIdentifier
0x1800fa4ad  lea     rcx, [rbp+47h+lpMem]
0x1800fa4b1  mov     esi, eax
0x1800fa4b3  test    eax, eax
0x1800fa4b5  js      loc_1800FA945
0x1800fa4bb  lea     r9, [rbp+47h+arg_10]
0x1800fa4bf  mov     [rbp+47h+arg_10], 0
0x1800fa4c7  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x1800fa4ce  mov     edx, 28h ; '('
0x1800fa4d3  call    RtlAllocateAllocationListMemory
0x1800fa4d8  mov     esi, eax
0x1800fa4da  test    eax, eax
0x1800fa4dc  js      loc_1800FA8FF
0x1800fa4e2  mov     rcx, [rbp+47h+arg_10]; this
0x1800fa4e6  mov     rax, [r13+rbx*8+0]
0x1800fa4eb  mov     [rcx+8], rax
0x1800fa4ef  mov     rax, rbx
0x1800fa4f2  mov     [rcx+10h], r14
0x1800fa4f6  add     rax, rax
0x1800fa4f9  mov     r14d, 1
0x1800fa4ff  mov     qword ptr [rcx], 28h ; '('
0x1800fa506  add     rbx, r14
0x1800fa509  mov     dword ptr [r12+rax*8], 9
0x1800fa511  mov     [r12+rax*8+8], rcx
0x1800fa516  cmp     rbx, r14
0x1800fa519  jnz     loc_1800FA476
0x1800fa51f  xor     r9d, r9d; struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *
0x1800fa522  mov     [rbp+47h+arg_10], 0
0x1800fa52a  lea     r8, [rbp+47h+arg_10]; struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *
0x1800fa52e  lea     rdx, ?RtlpNullIsolatedFilesystem@@3U_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@Rtl@FsProv@Isolation@Windows@@B; unsigned int
0x1800fa535  call    ?CreateIsolatedFilesystemFromProvider@Rtl@FsProv@Isolation@Windows@@YAJKPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1234@PEAU_ISOLATED_FILESYSTEM@134@PEAU_ISOLATED_FILESYSTEM_OBJECT@134@@Z; Windows::Isolation::FsProv::Rtl::CreateIsolatedFilesystemFromProvider(ulong,Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)
0x1800fa53a  mov     esi, eax
0x1800fa53c  test    eax, eax
0x1800fa53e  jns     loc_1800FA60A
0x1800fa544  mov     r10, [rbp+47h+arg_10]
0x1800fa548  test    r10, r10
0x1800fa54b  jz      loc_1800FA5E9
0x1800fa551  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r14; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800fa558  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800fa55f  mov     [rbp+47h+dwExceptionCode], 0C00000E5h
0x1800fa566  mov     [rbp+47h+var_78], rax
0x1800fa56a  test    r10, r10
0x1800fa56d  jz      short loc_1800FA599
0x1800fa56f  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800fa576  test    r11, r11
0x1800fa579  jz      short loc_1800FA5B0
0x1800fa57b  mov     rdx, r11
0x1800fa57e  mov     rcx, r10
0x1800fa581  call    RtlIsTypeSafeHandleValid
0x1800fa586  test    al, al
0x1800fa588  jz      short loc_1800FA5B0
0x1800fa58a  mov     ecx, [r11]
0x1800fa58d  mov     rdx, r10
0x1800fa590  mov     rax, [r11+20h]
0x1800fa594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa599  xor     ecx, ecx; dwExceptionCode
0x1800fa59b  test    ecx, ecx
0x1800fa59d  jns     short loc_1800FA5E9
0x1800fa59f  xor     r9d, r9d; lpArguments
0x1800fa5a2  xor     r8d, r8d; nNumberOfArguments
0x1800fa5a5  mov     edx, r14d; dwExceptionFlags
0x1800fa5a8  call    cs:__imp_RaiseException
0x1800fa5ae  jmp     short loc_1800FA5E9
0x1800fa5b0  mov     dword ptr [rbp+47h+var_70], 124h
0x1800fa5b7  lea     rcx, [rbp+47h+var_78]
0x1800fa5bb  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800fa5c0  mov     ecx, [rbp+47h+dwExceptionCode]
0x1800fa5c3  jmp     short loc_1800FA59B
0x1800fa5c5  mov     rax, [rbx+10h]
0x1800fa5c9  test    rax, rax
0x1800fa5cc  jz      short loc_1800FA5D7
0x1800fa5ce  lea     rcx, [rbx+18h]
0x1800fa5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa5d7  call    GetProcessHeap_0
0x1800fa5dc  mov     r8, rbx; lpMem
0x1800fa5df  xor     edx, edx; dwFlags
0x1800fa5e1  mov     rcx, rax; hHeap
0x1800fa5e4  call    HeapFree_0
0x1800fa5e9  mov     rbx, [rbp+47h+lpMem]
0x1800fa5ed  lea     rcx, [rbp+47h+lpMem]
0x1800fa5f1  mov     rax, [rbx]
0x1800fa5f4  mov     [rbp+47h+lpMem], rax
0x1800fa5f8  mov     [rax+8], rcx
0x1800fa5fc  lea     rax, [rbp+47h+lpMem]
0x1800fa600  cmp     rbx, rax
0x1800fa603  jnz     short loc_1800FA5C5
0x1800fa605  jmp     loc_1800FA8CD
0x1800fa60a  mov     rbx, [rbp+47h+arg_10]
0x1800fa60e  mov     r9, r14; int
0x1800fa611  mov     rdx, rbx; int
0x1800fa614  mov     [rsp+0D0h+var_A8], 0; void *
0x1800fa61d  mov     r8, rdi; int
0x1800fa620  mov     [rsp+0D0h+var_B0], r12; __int64
0x1800fa625  call    RtlTransactComponentStore
0x1800fa62a  mov     esi, eax
0x1800fa62c  test    eax, eax
0x1800fa62e  jns     loc_1800FA6F1
0x1800fa634  test    rbx, rbx
0x1800fa637  jz      loc_1800FA6D0
0x1800fa63d  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r14; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800fa644  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800fa64b  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800fa652  mov     [rbp+47h+dwExceptionCode], 0C00000E5h
0x1800fa659  mov     [rbp+47h+var_78], rax
0x1800fa65d  test    r10, r10
0x1800fa660  jz      short loc_1800FA684
0x1800fa662  mov     rdx, r10
0x1800fa665  mov     rcx, rbx
0x1800fa668  call    RtlIsTypeSafeHandleValid
0x1800fa66d  test    al, al
0x1800fa66f  jz      short loc_1800FA684
0x1800fa671  mov     ecx, [r10]
0x1800fa674  mov     rdx, rbx
0x1800fa677  mov     rax, [r10+20h]
0x1800fa67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa680  xor     ecx, ecx
0x1800fa682  jmp     short loc_1800FA697
0x1800fa684  mov     dword ptr [rbp+47h+var_70], 124h
0x1800fa68b  lea     rcx, [rbp+47h+var_78]
0x1800fa68f  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800fa694  mov     ecx, [rbp+47h+dwExceptionCode]; dwExceptionCode
0x1800fa697  test    ecx, ecx
0x1800fa699  jns     short loc_1800FA6D0
0x1800fa69b  xor     r9d, r9d; lpArguments
0x1800fa69e  xor     r8d, r8d; nNumberOfArguments
0x1800fa6a1  mov     edx, r14d; dwExceptionFlags
0x1800fa6a4  call    cs:__imp_RaiseException
0x1800fa6aa  jmp     short loc_1800FA6D0
0x1800fa6ac  mov     rax, [rbx+10h]
0x1800fa6b0  test    rax, rax
0x1800fa6b3  jz      short loc_1800FA6BE
0x1800fa6b5  lea     rcx, [rbx+18h]
0x1800fa6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa6be  call    GetProcessHeap_0
0x1800fa6c3  mov     r8, rbx; lpMem
0x1800fa6c6  xor     edx, edx; dwFlags
0x1800fa6c8  mov     rcx, rax; hHeap
0x1800fa6cb  call    HeapFree_0
0x1800fa6d0  mov     rbx, [rbp+47h+lpMem]
0x1800fa6d4  lea     rcx, [rbp+47h+lpMem]
0x1800fa6d8  mov     rax, [rbx]
0x1800fa6db  mov     [rbp+47h+lpMem], rax
0x1800fa6df  mov     [rax+8], rcx
0x1800fa6e3  lea     rax, [rbp+47h+lpMem]
0x1800fa6e7  cmp     rbx, rax
0x1800fa6ea  jnz     short loc_1800FA6AC
0x1800fa6ec  jmp     loc_1800FA8CD
0x1800fa6f1  xor     r14d, r14d
0x1800fa6f4  mov     rax, [r13+r14*8+0]
0x1800fa6f9  lea     rdx, [r15+r14*8]
0x1800fa6fd  mov     qword ptr [rbp+47h+dwExceptionCode], rax
0x1800fa701  mov     rax, r14
0x1800fa704  mov     [rbp+47h+var_78], 0
0x1800fa70c  add     rax, rax
0x1800fa70f  mov     [rbp+47h+var_70], 0
0x1800fa717  mov     rax, [r12+rax*8+8]
0x1800fa71c  mov     rcx, [rax+10h]
0x1800fa720  mov     [rbp+47h+var_78], rcx
0x1800fa724  lea     rcx, [rbp+47h+var_78]
0x1800fa728  mov     [rbp+47h+var_70], rdi
0x1800fa72c  call    ?Allocate@?$CTsObjectTraits@U_COMPONENT_STORE_COMPONENT_LOCK@Rtl@Isolation@Windows@@VCComponentStoreComponentLock@@VCComponentStoreComponentLockCD@@VCComponentStoreComponentLockTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@SAJAEAVCComponentStoreComponentLockCD@@AEAU_COMPONENT_STORE_COMPONENT_LOCK@2Isolation@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_LOCK,CComponentStoreComponentLock,CComponentStoreComponentLockCD,CComponentStoreComponentLockTraits>::Allocate(CComponentStoreComponentLockCD &,Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_LOCK &)
0x1800fa731  mov     esi, eax
0x1800fa733  test    eax, eax
0x1800fa735  js      loc_1800FA80F
0x1800fa73b  inc     r14
0x1800fa73e  cmp     r14, 1
0x1800fa742  jnz     short loc_1800FA6F4
0x1800fa744  xor     esi, esi
0x1800fa746  mov     [rbp+47h+var_90], 0
0x1800fa74e  mov     [rbp+47h+var_88], 0
0x1800fa756  test    rbx, rbx
0x1800fa759  jz      loc_1800FA7EE
0x1800fa75f  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800fa766  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800fa76d  mov     [rbp+47h+dwExceptionCode], 0C00000E5h
0x1800fa774  mov     [rbp+47h+var_78], rax
0x1800fa778  test    rbx, rbx
0x1800fa77b  jz      short loc_1800FA7A7
0x1800fa77d  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800fa784  test    r10, r10
0x1800fa787  jz      short loc_1800FA7BF
0x1800fa789  mov     rdx, r10
0x1800fa78c  mov     rcx, rbx
0x1800fa78f  call    RtlIsTypeSafeHandleValid
0x1800fa794  test    al, al
0x1800fa796  jz      short loc_1800FA7BF
0x1800fa798  mov     ecx, [r10]
0x1800fa79b  mov     rdx, rbx
0x1800fa79e  mov     rax, [r10+20h]
0x1800fa7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa7a7  xor     ecx, ecx; dwExceptionCode
0x1800fa7a9  test    ecx, ecx
0x1800fa7ab  jns     short loc_1800FA7EE
0x1800fa7ad  xor     r9d, r9d; lpArguments
0x1800fa7b0  xor     r8d, r8d; nNumberOfArguments
0x1800fa7b3  lea     edx, [r9+1]; dwExceptionFlags
0x1800fa7b7  call    cs:__imp_RaiseException
0x1800fa7bd  jmp     short loc_1800FA7EE
0x1800fa7bf  mov     dword ptr [rbp+47h+var_70], 124h
0x1800fa7c6  lea     rcx, [rbp+47h+var_78]
0x1800fa7ca  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800fa7cf  mov     ecx, [rbp+47h+dwExceptionCode]
0x1800fa7d2  jmp     short loc_1800FA7A9
0x1800fa7d4  mov     rax, [rbx+10h]
0x1800fa7d8  test    rax, rax
0x1800fa7db  jz      short loc_1800FA7E6
0x1800fa7dd  lea     rcx, [rbx+18h]
0x1800fa7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa7e6  mov     r8, rbx
0x1800fa7e9  call    RtlFreeHeap
0x1800fa7ee  mov     rbx, [rbp+47h+lpMem]
0x1800fa7f2  lea     rcx, [rbp+47h+lpMem]
0x1800fa7f6  mov     rax, [rbx]
0x1800fa7f9  mov     [rbp+47h+lpMem], rax
0x1800fa7fd  mov     [rax+8], rcx
0x1800fa801  lea     rax, [rbp+47h+lpMem]
0x1800fa805  cmp     rbx, rax
0x1800fa808  jnz     short loc_1800FA7D4
0x1800fa80a  jmp     loc_1800FA8CD
0x1800fa80f  test    rbx, rbx
0x1800fa812  jz      loc_1800FA8B1
  ... truncated ...
```
