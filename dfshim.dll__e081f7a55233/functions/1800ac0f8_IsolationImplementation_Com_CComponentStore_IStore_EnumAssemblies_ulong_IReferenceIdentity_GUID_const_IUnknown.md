# IsolationImplementation::Com::CComponentStore::IStore_EnumAssemblies(ulong,IReferenceIdentity *,_GUID const &,IUnknown * *)

- ea: `0x1800ac0f8`
- end: `0x1800ac457`
- name: `?IStore_EnumAssemblies@CComponentStore@Com@IsolationImplementation@@IEAAJKPEAUIReferenceIdentity@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `863`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, struct IReferenceIdentity *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800a9d30`

## callees

- `0x180006991`
- `0x180012acc`
- `0x180012b1c`
- `0x180012b38`
- `0x180016850`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x18001a750`
- `0x18003094c`
- `0x180039c1c`
- `0x180044708`
- `0x18004f2dc`
- `0x1800ac0f8`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac1b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac204`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac2c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac422`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac1b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac204`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac2c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ac422`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ac15a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ac30c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ac15a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ac30c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac38d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac38d`

## string_xrefs

- `0x1800ac347`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ac11b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ac28f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ac315`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ac3d9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ac3fc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_EnumAssemblies(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        struct IReferenceIdentity *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  int v9; // eax
  struct Windows::Isolation::Rtl::_REFERENCE_IDENTITY *v10; // r8
  int v11; // r9d
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // edi
  HANDLE v15; // rbx
  HANDLE v16; // rbx
  int v17; // edx
  unsigned int v18; // r15d
  __int64 v19; // rbx
  int v20; // eax
  int v21; // r9d
  __int64 v22; // rcx
  HANDLE v23; // rbx
  __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // edi
  int v27; // edx
  __int64 v28; // r10
  unsigned int *v29; // r11
  signed int v30; // ecx
  int v31; // eax
  int v32; // r9d
  HANDLE v33; // rbx
  struct IReferenceIdentity *v35; // [rsp+20h] [rbp-71h] BYREF
  const char *v36; // [rsp+28h] [rbp-69h] BYREF
  int v37; // [rsp+30h] [rbp-61h]
  unsigned int v38; // [rsp+38h] [rbp-59h]
  HANDLE hMutex; // [rsp+40h] [rbp-51h] BYREF
  __int16 v40; // [rsp+48h] [rbp-49h]
  _BYTE v41[64]; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v42[10]; // [rsp+90h] [rbp-1h] BYREF

  v38 = -2147023537;
  v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v41);
  hMutex = 0;
  v40 = 0;
  v9 = StoreLock::Lock((StoreLock *)&hMutex);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x29B,
      v12,
      (unsigned int)v35);
    v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v13);
    goto LABEL_53;
  }
  if ( a5 )
    *a5 = 0;
  if ( (a2 & 0xFFFFFFF8) == 0 )
  {
    if ( !a5 )
    {
      v37 = 677;
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v36);
      v16 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v40 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v40) = 0;
        }
        CloseHandle_0(v16);
        hMutex = 0;
      }
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v41);
      return v38;
    }
    if ( *(_QWORD *)&a4->Data1 != *(_QWORD *)&GUID_a5c637bf_6eaa_4e5f_b535_55299657e33e.Data1
      || *(_QWORD *)a4->Data4 != *(_QWORD *)GUID_a5c637bf_6eaa_4e5f_b535_55299657e33e.Data4 )
    {
      v14 = -2147467262;
      Windows::ErrorHandling::COM::ReportErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x2A8,
        -2147467262,
        v11);
LABEL_53:
      v33 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v40 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v40) = 0;
        }
        CloseHandle_0(v33);
        hMutex = 0;
      }
LABEL_57:
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v41);
      return v14;
    }
    v17 = a2 & 1 | 2;
    if ( (a2 & 2) == 0 )
      v17 = a2 & 1;
    v18 = v17 | 4;
    if ( (a2 & 4) == 0 )
      v18 = v17;
    v19 = 0;
    v42[0] = 0;
    if ( a3 )
    {
      v20 = IsolationImplementation::Com::ConvertIn(a3, (struct IReferenceIdentity *)v42, v10);
      a3 = 0;
      v14 = v20;
      if ( v20 < 0 )
      {
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x2B8,
          v20,
          v21);
        v22 = v42[0];
        if ( !v42[0] )
          goto LABEL_30;
        goto LABEL_29;
      }
      v19 = v42[0];
    }
    v24 = *((_QWORD *)this + 2);
    v35 = a3;
    v25 = RtlEnumerateComponentStoreComponents(v18, v24, v19, &v35);
    v26 = v25;
    if ( v25 >= 0 )
    {
      v31 = IsolationImplementation::Com::CopyOut(*((_QWORD *)this + 2), v35, a4, a5);
      v14 = v31;
      if ( v31 >= 0 )
        v14 = (unsigned int)a3;
      else
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
          (const char *)0x2C2,
          v31,
          v32);
    }
    else
    {
      if ( v25 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x2C0,
        v26,
        (unsigned int)v35);
      v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v26, v27);
    }
    if ( v35 )
    {
      v38 = -1073741595;
      v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,CComponentEnumerator,CComponentEnumeratorCD,CComponentEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v35) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v29 + 4))(*v29, v28);
        v30 = (int)a3;
      }
      else
      {
        v37 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
        v30 = v38;
      }
      if ( v30 < 0 )
        RaiseException(v30, 1u, 0, 0);
      v35 = a3;
    }
    if ( !v19 )
      goto LABEL_30;
    v22 = v19;
LABEL_29:
    RtlCloseReferenceIdentityHandle(v22);
LABEL_30:
    v23 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v40 != (_BYTE)a3 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v40) = (_BYTE)a3;
      }
      CloseHandle_0(v23);
      hMutex = a3;
    }
    goto LABEL_57;
  }
  v15 = hMutex;
  v37 = 675;
  if ( hMutex )
  {
    if ( (_BYTE)v40 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v40) = 0;
    }
    CloseHandle_0(v15);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v41);
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v36);
  return v38;
}

```

## disassembly

```asm
0x1800ac0f8  push    rbp
0x1800ac0fa  push    rbx
0x1800ac0fb  push    rsi
0x1800ac0fc  push    rdi
0x1800ac0fd  push    r12
0x1800ac0ff  push    r13
0x1800ac101  push    r14
0x1800ac103  push    r15
0x1800ac105  lea     rbp, [rsp-17h]
0x1800ac10a  sub     rsp, 0A8h
0x1800ac111  mov     r13, rcx
0x1800ac114  mov     [rbp+4Fh+var_A8], 8007054Fh
0x1800ac11b  lea     rsi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac122  mov     r14, r9
0x1800ac125  lea     rcx, [rbp+4Fh+var_90]; this
0x1800ac129  mov     [rbp+4Fh+var_B8], rsi
0x1800ac12d  mov     r12, r8
0x1800ac130  mov     edi, edx
0x1800ac132  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800ac137  xor     r15d, r15d
0x1800ac13a  lea     rcx, [rbp+4Fh+hMutex]; this
0x1800ac13e  mov     [rbp+4Fh+hMutex], r15
0x1800ac142  mov     [rbp+4Fh+var_98], r15w
0x1800ac147  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800ac14c  mov     ebx, eax
0x1800ac14e  test    eax, eax
0x1800ac150  jns     short loc_1800AC186
0x1800ac152  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ac158  jnz     short loc_1800AC160
0x1800ac15a  call    cs:__imp_DebugBreak
0x1800ac160  mov     r9d, ebx; int
0x1800ac163  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ac16a  mov     r8d, 29Bh; char *
0x1800ac170  mov     rdx, rsi; char *
0x1800ac173  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ac178  mov     ecx, ebx; this
0x1800ac17a  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ac17f  mov     edi, eax
0x1800ac181  jmp     loc_1800AC410
0x1800ac186  mov     rsi, [rbp+4Fh+arg_20]
0x1800ac18a  test    rsi, rsi
0x1800ac18d  jz      short loc_1800AC192
0x1800ac18f  mov     [rsi], r15
0x1800ac192  test    edi, 0FFFFFFF8h
0x1800ac198  jz      short loc_1800AC1DD
0x1800ac19a  mov     rbx, [rbp+4Fh+hMutex]
0x1800ac19e  mov     [rbp+4Fh+var_B0], 2A3h
0x1800ac1a5  test    rbx, rbx
0x1800ac1a8  jz      short loc_1800AC1C9
0x1800ac1aa  cmp     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac1ae  jz      short loc_1800AC1BD
0x1800ac1b0  mov     rcx, rbx; hMutex
0x1800ac1b3  call    cs:__imp_ReleaseMutex
0x1800ac1b9  mov     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac1bd  mov     rcx, rbx; hObject
0x1800ac1c0  call    CloseHandle_0
0x1800ac1c5  mov     [rbp+4Fh+hMutex], r15
0x1800ac1c9  lea     rcx, [rbp+4Fh+var_90]; this
0x1800ac1cd  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ac1d2  lea     rcx, [rbp+4Fh+var_B8]
0x1800ac1d6  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800ac1db  jmp     short loc_1800AC223
0x1800ac1dd  test    rsi, rsi
0x1800ac1e0  jnz     short loc_1800AC22B
0x1800ac1e2  lea     rcx, [rbp+4Fh+var_B8]
0x1800ac1e6  mov     [rbp+4Fh+var_B0], 2A5h
0x1800ac1ed  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800ac1f2  mov     rbx, [rbp+4Fh+hMutex]
0x1800ac1f6  test    rbx, rbx
0x1800ac1f9  jz      short loc_1800AC21A
0x1800ac1fb  cmp     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac1ff  jz      short loc_1800AC20E
0x1800ac201  mov     rcx, rbx; hMutex
0x1800ac204  call    cs:__imp_ReleaseMutex
0x1800ac20a  mov     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac20e  mov     rcx, rbx; hObject
0x1800ac211  call    CloseHandle_0
0x1800ac216  mov     [rbp+4Fh+hMutex], r15
0x1800ac21a  lea     rcx, [rbp+4Fh+var_90]; this
0x1800ac21e  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ac223  mov     edi, [rbp+4Fh+var_A8]
0x1800ac226  jmp     loc_1800AC441
0x1800ac22b  mov     rax, [r14]
0x1800ac22e  cmp     rax, qword ptr cs:_GUID_a5c637bf_6eaa_4e5f_b535_55299657e33e.Data1
0x1800ac235  jnz     loc_1800AC3F7
0x1800ac23b  mov     rax, [r14+8]
0x1800ac23f  cmp     rax, qword ptr cs:_GUID_a5c637bf_6eaa_4e5f_b535_55299657e33e.Data4
0x1800ac246  jnz     loc_1800AC3F7
0x1800ac24c  mov     ecx, edi
0x1800ac24e  and     ecx, 1
0x1800ac251  mov     edx, ecx
0x1800ac253  or      edx, 2
0x1800ac256  test    dil, 2
0x1800ac25a  cmovz   edx, ecx
0x1800ac25d  mov     r15d, edx
0x1800ac260  or      r15d, 4
0x1800ac264  test    dil, 4
0x1800ac268  cmovz   r15d, edx
0x1800ac26c  xor     ebx, ebx
0x1800ac26e  mov     [rbp+4Fh+var_50], rbx
0x1800ac272  test    r12, r12
0x1800ac275  jz      short loc_1800AC2E3
0x1800ac277  lea     rdx, [rbp+4Fh+var_50]; struct IReferenceIdentity *
0x1800ac27b  mov     rcx, r12; this
0x1800ac27e  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIReferenceIdentity@@PEAU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IReferenceIdentity *,Windows::Isolation::Rtl::_REFERENCE_IDENTITY *)
0x1800ac283  xor     r12d, r12d
0x1800ac286  mov     edi, eax
0x1800ac288  test    eax, eax
0x1800ac28a  jns     short loc_1800AC2DF
0x1800ac28c  mov     r8d, eax; int
0x1800ac28f  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac296  mov     edx, 2B8h; char *
0x1800ac29b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ac2a0  mov     rcx, [rbp+4Fh+var_50]
0x1800ac2a4  test    rcx, rcx
0x1800ac2a7  jz      short loc_1800AC2AE
0x1800ac2a9  call    RtlCloseReferenceIdentityHandle
0x1800ac2ae  mov     rbx, [rbp+4Fh+hMutex]
0x1800ac2b2  test    rbx, rbx
0x1800ac2b5  jz      loc_1800AC438
0x1800ac2bb  cmp     byte ptr [rbp+4Fh+var_98], r12b
0x1800ac2bf  jz      short loc_1800AC2CE
0x1800ac2c1  mov     rcx, rbx; hMutex
0x1800ac2c4  call    cs:__imp_ReleaseMutex
0x1800ac2ca  mov     byte ptr [rbp+4Fh+var_98], r12b
0x1800ac2ce  mov     rcx, rbx; hObject
0x1800ac2d1  call    CloseHandle_0
0x1800ac2d6  mov     [rbp+4Fh+hMutex], r12
0x1800ac2da  jmp     loc_1800AC438
0x1800ac2df  mov     rbx, [rbp+4Fh+var_50]
0x1800ac2e3  mov     rdx, [r13+10h]
0x1800ac2e7  lea     r9, [rbp+4Fh+var_C0]
0x1800ac2eb  mov     r8, rbx
0x1800ac2ee  mov     [rbp+4Fh+var_C0], r12
0x1800ac2f2  mov     ecx, r15d
0x1800ac2f5  call    RtlEnumerateComponentStoreComponents
0x1800ac2fa  mov     edi, eax
0x1800ac2fc  test    eax, eax
0x1800ac2fe  jns     loc_1800AC3BD
0x1800ac304  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ac30a  jnz     short loc_1800AC312
0x1800ac30c  call    cs:__imp_DebugBreak
0x1800ac312  mov     r9d, edi; int
0x1800ac315  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac31c  mov     r8d, 2C0h; char *
0x1800ac322  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ac329  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ac32e  mov     ecx, edi; this
0x1800ac330  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ac335  mov     edi, eax
0x1800ac337  mov     r10, [rbp+4Fh+var_C0]
0x1800ac33b  test    r10, r10
0x1800ac33e  jz      short loc_1800AC397
0x1800ac340  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_COMPONENT_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentEnumerator@@VCComponentEnumeratorCD@@VCComponentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,CComponentEnumerator,CComponentEnumeratorCD,CComponentEnumeratorTraits>::ms_ptti
0x1800ac347  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac34e  mov     [rbp+4Fh+var_A8], 0C00000E5h
0x1800ac355  mov     [rbp+4Fh+var_B8], rax
0x1800ac359  test    r11, r11
0x1800ac35c  jz      short loc_1800AC3A8
0x1800ac35e  mov     rdx, r11
0x1800ac361  mov     rcx, r10
0x1800ac364  call    RtlIsTypeSafeHandleValid
0x1800ac369  test    al, al
0x1800ac36b  jz      short loc_1800AC3A8
0x1800ac36d  mov     ecx, [r11]
0x1800ac370  mov     rdx, r10
0x1800ac373  mov     rax, [r11+20h]
0x1800ac377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac37c  mov     ecx, r12d; dwExceptionCode
0x1800ac37f  test    ecx, ecx
0x1800ac381  jns     short loc_1800AC393
0x1800ac383  xor     r9d, r9d; lpArguments
0x1800ac386  xor     r8d, r8d; nNumberOfArguments
0x1800ac389  lea     edx, [r9+1]; dwExceptionFlags
0x1800ac38d  call    cs:__imp_RaiseException
0x1800ac393  mov     [rbp+4Fh+var_C0], r12
0x1800ac397  test    rbx, rbx
0x1800ac39a  jz      loc_1800AC2AE
0x1800ac3a0  mov     rcx, rbx
0x1800ac3a3  jmp     loc_1800AC2A9
0x1800ac3a8  mov     [rbp+4Fh+var_B0], 124h
0x1800ac3af  lea     rcx, [rbp+4Fh+var_B8]
0x1800ac3b3  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800ac3b8  mov     ecx, [rbp+4Fh+var_A8]
0x1800ac3bb  jmp     short loc_1800AC37F
0x1800ac3bd  mov     rdx, [rbp+4Fh+var_C0]
0x1800ac3c1  mov     r9, rsi
0x1800ac3c4  mov     rcx, [r13+10h]
0x1800ac3c8  mov     r8, r14
0x1800ac3cb  call    ?CopyOut@Com@IsolationImplementation@@YAJU_COMPONENT_STORE@Rtl@Isolation@Windows@@U_COMPONENT_STORE_COMPONENT_ENUMERATOR@456@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_COMPONENT_STORE,Windows::Isolation::Rtl::_COMPONENT_STORE_COMPONENT_ENUMERATOR,_GUID const &,IUnknown * *)
0x1800ac3d0  mov     edi, eax
0x1800ac3d2  test    eax, eax
0x1800ac3d4  jns     short loc_1800AC3EF
0x1800ac3d6  mov     r8d, eax; int
0x1800ac3d9  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac3e0  mov     edx, 2C2h; char *
0x1800ac3e5  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ac3ea  jmp     loc_1800AC337
0x1800ac3ef  mov     edi, r12d
0x1800ac3f2  jmp     loc_1800AC337
0x1800ac3f7  mov     edi, 80004002h
0x1800ac3fc  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ac403  mov     r8d, edi; int
0x1800ac406  mov     edx, 2A8h; char *
0x1800ac40b  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x1800ac410  mov     rbx, [rbp+4Fh+hMutex]
0x1800ac414  test    rbx, rbx
0x1800ac417  jz      short loc_1800AC438
0x1800ac419  cmp     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac41d  jz      short loc_1800AC42C
0x1800ac41f  mov     rcx, rbx; hMutex
0x1800ac422  call    cs:__imp_ReleaseMutex
0x1800ac428  mov     byte ptr [rbp+4Fh+var_98], r15b
0x1800ac42c  mov     rcx, rbx; hObject
0x1800ac42f  call    CloseHandle_0
0x1800ac434  mov     [rbp+4Fh+hMutex], r15
0x1800ac438  lea     rcx, [rbp+4Fh+var_90]; this
0x1800ac43c  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ac441  mov     eax, edi
0x1800ac443  add     rsp, 0A8h
0x1800ac44a  pop     r15
0x1800ac44c  pop     r14
0x1800ac44e  pop     r13
0x1800ac450  pop     r12
0x1800ac452  pop     rdi
0x1800ac453  pop     rsi
0x1800ac454  pop     rbx
0x1800ac455  pop     rbp
0x1800ac456  retn
```
