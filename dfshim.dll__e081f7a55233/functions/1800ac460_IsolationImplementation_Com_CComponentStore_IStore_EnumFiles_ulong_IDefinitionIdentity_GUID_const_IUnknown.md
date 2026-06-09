# IsolationImplementation::Com::CComponentStore::IStore_EnumFiles(ulong,IDefinitionIdentity *,_GUID const &,IUnknown * *)

- ea: `0x1800ac460`
- end: `0x1800ac7b6`
- name: `?IStore_EnumFiles@CComponentStore@Com@IsolationImplementation@@IEAAJKPEAUIDefinitionIdentity@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `854`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, struct IDefinitionIdentity *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800aa080`

## callees

- `0x180006991`
- `0x180012acc`
- `0x180012b1c`
- `0x180012b38`
- `0x1800169c4`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x18001a8d8`
- `0x180030674`
- `0x180039c1c`
- `0x180043644`
- `0x18004f2dc`
- `0x1800ac460`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac51f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac570`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac627`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac781`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac51f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac570`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac627`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac781`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ac4c2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ac66f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ac4c2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ac66f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac6f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac6f0`

## string_xrefs

- `0x1800ac6aa`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ac483`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ac5f2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ac678`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ac738`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ac75b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_EnumFiles(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        struct IDefinitionIdentity *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  int v9; // eax
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v10; // r8
  int v11; // r9d
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // edi
  HANDLE v15; // rbx
  HANDLE v16; // rbx
  unsigned int v17; // r15d
  int v18; // eax
  int v19; // r9d
  __int64 v20; // rcx
  HANDLE v21; // rbx
  __int64 v22; // rbx
  __int64 v23; // rdx
  int v24; // eax
  unsigned int v25; // edi
  int v26; // edx
  __int64 v27; // r10
  unsigned int *v28; // r11
  signed int v29; // ecx
  int v30; // eax
  int v31; // r9d
  HANDLE v32; // rbx
  __int64 v34; // [rsp+20h] [rbp-71h] BYREF
  const char *v35; // [rsp+28h] [rbp-69h] BYREF
  int v36; // [rsp+30h] [rbp-61h]
  unsigned int v37; // [rsp+38h] [rbp-59h]
  HANDLE hMutex; // [rsp+40h] [rbp-51h] BYREF
  __int16 v39; // [rsp+48h] [rbp-49h]
  _BYTE v40[64]; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v41[10]; // [rsp+90h] [rbp-1h] BYREF

  v37 = -2147023537;
  v35 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v40);
  hMutex = 0;
  v39 = 0;
  v9 = StoreLock::Lock((StoreLock *)&hMutex);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x2D2,
      v12,
      v34);
    v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v13);
    goto LABEL_52;
  }
  v41[0] = 0;
  if ( a5 )
    *a5 = 0;
  if ( (a2 & 0xFFFFFFFC) == 0 )
  {
    if ( !a3 )
    {
      v36 = 731;
LABEL_15:
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v35);
      v16 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v39 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v39) = 0;
        }
        CloseHandle_0(v16);
        hMutex = 0;
      }
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v40);
      return v37;
    }
    if ( !a5 )
    {
      v36 = 732;
      goto LABEL_15;
    }
    if ( *(_QWORD *)&a4->Data1 != *(_QWORD *)&GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f.Data1
      || *(_QWORD *)a4->Data4 != *(_QWORD *)GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f.Data4 )
    {
      v14 = -2147467262;
      Windows::ErrorHandling::COM::ReportErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x2DF,
        -2147467262,
        v11);
LABEL_52:
      v32 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v39 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v39) = 0;
        }
        CloseHandle_0(v32);
        hMutex = 0;
      }
LABEL_56:
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v40);
      return v14;
    }
    v17 = a2 & 1 | 2;
    if ( (a2 & 2) == 0 )
      v17 = a2 & 1;
    v18 = IsolationImplementation::Com::ConvertIn(a3, (struct IDefinitionIdentity *)v41, v10);
    v14 = v18;
    if ( v18 >= 0 )
    {
      v22 = v41[0];
      v23 = *((_QWORD *)this + 2);
      v34 = 0;
      v24 = RtlEnumerateComponentStoreFiles(v17, v23, v41[0], &v34);
      v25 = v24;
      if ( v24 >= 0 )
      {
        v30 = IsolationImplementation::Com::CopyOut(v34, a4, a5);
        v14 = v30;
        if ( v30 >= 0 )
          v14 = 0;
        else
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
            (const char *)0x2F2,
            v30,
            v31);
      }
      else
      {
        if ( v24 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x2F0,
          v25,
          v34);
        v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v25, v26);
      }
      if ( v34 )
      {
        v37 = -1073741595;
        v35 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v34) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v28 + 4))(*v28, v27);
          v29 = 0;
        }
        else
        {
          v36 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v35);
          v29 = v37;
        }
        if ( v29 < 0 )
          RaiseException(v29, 1u, 0, 0);
        v34 = 0;
      }
      if ( !v22 )
        goto LABEL_30;
      v20 = v22;
    }
    else
    {
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x2E7,
        v18,
        v19);
      v20 = v41[0];
      if ( !v41[0] )
        goto LABEL_30;
    }
    RtlCloseDefinitionIdentityHandle(v20);
LABEL_30:
    v21 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v39 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v39) = 0;
      }
      CloseHandle_0(v21);
      hMutex = 0;
    }
    goto LABEL_56;
  }
  v15 = hMutex;
  v36 = 730;
  if ( hMutex )
  {
    if ( (_BYTE)v39 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v39) = 0;
    }
    CloseHandle_0(v15);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v40);
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v35);
  return v37;
}

```

## disassembly

```asm
0x1800ac460  push    rbp
0x1800ac462  push    rbx
0x1800ac463  push    rsi
0x1800ac464  push    rdi
0x1800ac465  push    r12
0x1800ac467  push    r13
0x1800ac469  push    r14
0x1800ac46b  push    r15
0x1800ac46d  lea     rbp, [rsp-17h]
0x1800ac472  sub     rsp, 0A8h
0x1800ac479  mov     r13, rcx
0x1800ac47c  mov     [rbp+4Fh+var_A8], 8007054Fh
0x1800ac483  lea     rsi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac48a  mov     r14, r9
0x1800ac48d  lea     rcx, [rbp+4Fh+var_90]; this
0x1800ac491  mov     [rbp+4Fh+var_B8], rsi
0x1800ac495  mov     r12, r8
0x1800ac498  mov     edi, edx
0x1800ac49a  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800ac49f  xor     r15d, r15d
0x1800ac4a2  lea     rcx, [rbp+4Fh+hMutex]; this
0x1800ac4a6  mov     [rbp+4Fh+hMutex], r15
0x1800ac4aa  mov     [rbp+4Fh+var_98], r15w
0x1800ac4af  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800ac4b4  mov     ebx, eax
0x1800ac4b6  test    eax, eax
0x1800ac4b8  jns     short loc_1800AC4EE
0x1800ac4ba  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ac4c0  jnz     short loc_1800AC4C8
0x1800ac4c2  call    cs:__imp_DebugBreak
0x1800ac4c8  mov     r9d, ebx; int
0x1800ac4cb  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ac4d2  mov     r8d, 2D2h; char *
0x1800ac4d8  mov     rdx, rsi; char *
0x1800ac4db  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ac4e0  mov     ecx, ebx; this
0x1800ac4e2  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ac4e7  mov     edi, eax
0x1800ac4e9  jmp     loc_1800AC76F
0x1800ac4ee  mov     rsi, [rbp+4Fh+arg_20]
0x1800ac4f2  mov     [rbp+4Fh+var_50], r15
0x1800ac4f6  test    rsi, rsi
0x1800ac4f9  jz      short loc_1800AC4FE
0x1800ac4fb  mov     [rsi], r15
0x1800ac4fe  test    edi, 0FFFFFFFCh
0x1800ac504  jz      short loc_1800AC549
0x1800ac506  mov     rbx, [rbp+4Fh+hMutex]
0x1800ac50a  mov     [rbp+4Fh+var_B0], 2DAh
0x1800ac511  test    rbx, rbx
0x1800ac514  jz      short loc_1800AC535
0x1800ac516  cmp     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac51a  jz      short loc_1800AC529
0x1800ac51c  mov     rcx, rbx; hMutex
0x1800ac51f  call    cs:__imp_ReleaseMutex
0x1800ac525  mov     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac529  mov     rcx, rbx; hObject
0x1800ac52c  call    CloseHandle_0
0x1800ac531  mov     [rbp+4Fh+hMutex], r15
0x1800ac535  lea     rcx, [rbp+4Fh+var_90]; this
0x1800ac539  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ac53e  lea     rcx, [rbp+4Fh+var_B8]
0x1800ac542  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800ac547  jmp     short loc_1800AC58F
0x1800ac549  test    r12, r12
0x1800ac54c  jnz     short loc_1800AC597
0x1800ac54e  mov     [rbp+4Fh+var_B0], 2DBh
0x1800ac555  lea     rcx, [rbp+4Fh+var_B8]
0x1800ac559  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800ac55e  mov     rbx, [rbp+4Fh+hMutex]
0x1800ac562  test    rbx, rbx
0x1800ac565  jz      short loc_1800AC586
0x1800ac567  cmp     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac56b  jz      short loc_1800AC57A
0x1800ac56d  mov     rcx, rbx; hMutex
0x1800ac570  call    cs:__imp_ReleaseMutex
0x1800ac576  mov     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac57a  mov     rcx, rbx; hObject
0x1800ac57d  call    CloseHandle_0
0x1800ac582  mov     [rbp+4Fh+hMutex], r15
0x1800ac586  lea     rcx, [rbp+4Fh+var_90]; this
0x1800ac58a  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ac58f  mov     edi, [rbp+4Fh+var_A8]
0x1800ac592  jmp     loc_1800AC7A0
0x1800ac597  test    rsi, rsi
0x1800ac59a  jnz     short loc_1800AC5A5
0x1800ac59c  mov     [rbp+4Fh+var_B0], 2DCh
0x1800ac5a3  jmp     short loc_1800AC555
0x1800ac5a5  mov     rax, [r14]
0x1800ac5a8  cmp     rax, qword ptr cs:_GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f.Data1
0x1800ac5af  jnz     loc_1800AC756
0x1800ac5b5  mov     rax, [r14+8]
0x1800ac5b9  cmp     rax, qword ptr cs:_GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f.Data4
0x1800ac5c0  jnz     loc_1800AC756
0x1800ac5c6  mov     eax, edi
0x1800ac5c8  lea     rdx, [rbp+4Fh+var_50]; struct IDefinitionIdentity *
0x1800ac5cc  and     eax, 1
0x1800ac5cf  mov     rcx, r12; this
0x1800ac5d2  mov     r15d, eax
0x1800ac5d5  or      r15d, 2
0x1800ac5d9  test    dil, 2
0x1800ac5dd  cmovz   r15d, eax
0x1800ac5e1  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800ac5e6  xor     r12d, r12d
0x1800ac5e9  mov     edi, eax
0x1800ac5eb  test    eax, eax
0x1800ac5ed  jns     short loc_1800AC642
0x1800ac5ef  mov     r8d, eax; int
0x1800ac5f2  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac5f9  mov     edx, 2E7h; char *
0x1800ac5fe  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ac603  mov     rcx, [rbp+4Fh+var_50]
0x1800ac607  test    rcx, rcx
0x1800ac60a  jz      short loc_1800AC611
0x1800ac60c  call    RtlCloseDefinitionIdentityHandle
0x1800ac611  mov     rbx, [rbp+4Fh+hMutex]
0x1800ac615  test    rbx, rbx
0x1800ac618  jz      loc_1800AC797
0x1800ac61e  cmp     byte ptr [rbp+4Fh+var_98], r12b
0x1800ac622  jz      short loc_1800AC631
0x1800ac624  mov     rcx, rbx; hMutex
0x1800ac627  call    cs:__imp_ReleaseMutex
0x1800ac62d  mov     byte ptr [rbp+4Fh+var_98], r12b
0x1800ac631  mov     rcx, rbx; hObject
0x1800ac634  call    CloseHandle_0
0x1800ac639  mov     [rbp+4Fh+hMutex], r12
0x1800ac63d  jmp     loc_1800AC797
0x1800ac642  mov     rbx, [rbp+4Fh+var_50]
0x1800ac646  lea     r9, [rbp+4Fh+var_C0]
0x1800ac64a  mov     rdx, [r13+10h]
0x1800ac64e  mov     r8, rbx
0x1800ac651  mov     ecx, r15d
0x1800ac654  mov     [rbp+4Fh+var_C0], r12
0x1800ac658  call    RtlEnumerateComponentStoreFiles
0x1800ac65d  mov     edi, eax
0x1800ac65f  test    eax, eax
0x1800ac661  jns     loc_1800AC720
0x1800ac667  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ac66d  jnz     short loc_1800AC675
0x1800ac66f  call    cs:__imp_DebugBreak
0x1800ac675  mov     r9d, edi; int
0x1800ac678  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac67f  mov     r8d, 2F0h; char *
0x1800ac685  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ac68c  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ac691  mov     ecx, edi; this
0x1800ac693  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ac698  mov     edi, eax
0x1800ac69a  mov     r10, [rbp+4Fh+var_C0]
0x1800ac69e  test    r10, r10
0x1800ac6a1  jz      short loc_1800AC6FA
0x1800ac6a3  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@VCFileEnumerator@@VCFileEnumeratorCD@@VCFileEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
0x1800ac6aa  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac6b1  mov     [rbp+4Fh+var_A8], 0C00000E5h
0x1800ac6b8  mov     [rbp+4Fh+var_B8], rax
0x1800ac6bc  test    r11, r11
0x1800ac6bf  jz      short loc_1800AC70B
0x1800ac6c1  mov     rdx, r11
0x1800ac6c4  mov     rcx, r10
0x1800ac6c7  call    RtlIsTypeSafeHandleValid
0x1800ac6cc  test    al, al
0x1800ac6ce  jz      short loc_1800AC70B
0x1800ac6d0  mov     ecx, [r11]
0x1800ac6d3  mov     rdx, r10
0x1800ac6d6  mov     rax, [r11+20h]
0x1800ac6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac6df  mov     ecx, r12d; dwExceptionCode
0x1800ac6e2  test    ecx, ecx
0x1800ac6e4  jns     short loc_1800AC6F6
0x1800ac6e6  xor     r9d, r9d; lpArguments
0x1800ac6e9  xor     r8d, r8d; nNumberOfArguments
0x1800ac6ec  lea     edx, [r9+1]; dwExceptionFlags
0x1800ac6f0  call    cs:__imp_RaiseException
0x1800ac6f6  mov     [rbp+4Fh+var_C0], r12
0x1800ac6fa  test    rbx, rbx
0x1800ac6fd  jz      loc_1800AC611
0x1800ac703  mov     rcx, rbx
0x1800ac706  jmp     loc_1800AC60C
0x1800ac70b  mov     [rbp+4Fh+var_B0], 124h
0x1800ac712  lea     rcx, [rbp+4Fh+var_B8]
0x1800ac716  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800ac71b  mov     ecx, [rbp+4Fh+var_A8]
0x1800ac71e  jmp     short loc_1800AC6E2
0x1800ac720  mov     rcx, [rbp+4Fh+var_C0]
0x1800ac724  mov     r8, rsi
0x1800ac727  mov     rdx, r14
0x1800ac72a  call    ?CopyOut@Com@IsolationImplementation@@YAJU_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,_GUID const &,IUnknown * *)
0x1800ac72f  mov     edi, eax
0x1800ac731  test    eax, eax
0x1800ac733  jns     short loc_1800AC74E
0x1800ac735  mov     r8d, eax; int
0x1800ac738  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac73f  mov     edx, 2F2h; char *
0x1800ac744  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ac749  jmp     loc_1800AC69A
0x1800ac74e  mov     edi, r12d
0x1800ac751  jmp     loc_1800AC69A
0x1800ac756  mov     edi, 80004002h
0x1800ac75b  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac762  mov     r8d, edi; int
0x1800ac765  mov     edx, 2DFh; char *
0x1800ac76a  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x1800ac76f  mov     rbx, [rbp+4Fh+hMutex]
0x1800ac773  test    rbx, rbx
0x1800ac776  jz      short loc_1800AC797
0x1800ac778  cmp     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac77c  jz      short loc_1800AC78B
0x1800ac77e  mov     rcx, rbx; hMutex
0x1800ac781  call    cs:__imp_ReleaseMutex
0x1800ac787  mov     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac78b  mov     rcx, rbx; hObject
0x1800ac78e  call    CloseHandle_0
0x1800ac793  mov     [rbp+4Fh+hMutex], r15
0x1800ac797  lea     rcx, [rbp+4Fh+var_90]; this
0x1800ac79b  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ac7a0  mov     eax, edi
0x1800ac7a2  add     rsp, 0A8h
0x1800ac7a9  pop     r15
0x1800ac7ab  pop     r14
0x1800ac7ad  pop     r13
0x1800ac7af  pop     r12
0x1800ac7b1  pop     rdi
0x1800ac7b2  pop     rsi
0x1800ac7b3  pop     rbx
0x1800ac7b4  pop     rbp
0x1800ac7b5  retn
```
