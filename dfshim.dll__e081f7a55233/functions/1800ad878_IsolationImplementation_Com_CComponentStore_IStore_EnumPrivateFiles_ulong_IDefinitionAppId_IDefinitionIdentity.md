# IsolationImplementation::Com::CComponentStore::IStore_EnumPrivateFiles(ulong,IDefinitionAppId *,IDefinitionIdentity *,_GUID const &,IUnknown * *)

- ea: `0x1800ad878`
- end: `0x1800adc4f`
- name: `?IStore_EnumPrivateFiles@CComponentStore@Com@IsolationImplementation@@IEAAJKPEAUIDefinitionAppId@@PEAUIDefinitionIdentity@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `983`
- prototype: `int(IsolationImplementation::Com::CComponentStore *__hidden this, unsigned int, struct IDefinitionAppId *, struct IDefinitionIdentity *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800aa0c0`

## callees

- `0x180006991`
- `0x180012acc`
- `0x180012b1c`
- `0x180012b38`
- `0x180016698`
- `0x180017514`
- `0x180017530`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x18001a8d8`
- `0x180030508`
- `0x180030674`
- `0x180039c1c`
- `0x18003eb10`
- `0x180043644`
- `0x18004f2dc`
- `0x1800ad878`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad93e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad9a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ada82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800adc1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad93e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ad9a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800ada82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800adc1a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ad8dc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800adaf2`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ad8dc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800adaf2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800adb74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800adb74`

## string_xrefs

- `0x1800adb2d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800ad895`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800ada3e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800adafb`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800adbbd`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`
- `0x1800adbe0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\store.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CComponentStore::IStore_EnumPrivateFiles(
        IsolationImplementation::Com::CComponentStore *this,
        int a2,
        struct IDefinitionAppId *a3,
        struct IDefinitionIdentity *a4,
        const struct _GUID *a5,
        struct IUnknown **a6)
{
  int v9; // eax
  struct Windows::Isolation::Rtl::_DEFINITION_IDENTITY *v10; // r8
  int v11; // r9d
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // edi
  HANDLE v15; // rbx
  HANDLE v16; // rbx
  int v17; // r13d
  int v18; // eax
  struct Windows::Isolation::Rtl::_DEFINITION_APPID *v19; // r8
  int v20; // r9d
  __int64 v21; // rdx
  __int64 v22; // rcx
  HANDLE v23; // rbx
  __int64 v24; // rbx
  int v25; // eax
  unsigned int v26; // edi
  int v27; // edx
  __int64 v28; // r10
  unsigned int *v29; // r11
  signed int v30; // ecx
  int v31; // eax
  int v32; // r9d
  HANDLE v33; // rbx
  unsigned int v35; // [rsp+20h] [rbp-99h]
  unsigned int v36; // [rsp+20h] [rbp-99h]
  __int64 v37; // [rsp+30h] [rbp-89h] BYREF
  const char *v38; // [rsp+38h] [rbp-81h] BYREF
  int v39; // [rsp+40h] [rbp-79h]
  unsigned int v40; // [rsp+48h] [rbp-71h]
  unsigned int v41[2]; // [rsp+50h] [rbp-69h] BYREF
  HANDLE hMutex; // [rsp+60h] [rbp-59h] BYREF
  __int16 v43; // [rsp+68h] [rbp-51h]
  _BYTE v44[64]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v45[10]; // [rsp+B0h] [rbp-9h] BYREF

  v40 = -2147023537;
  v38 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp";
  BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v44);
  hMutex = 0;
  v43 = 0;
  v9 = StoreLock::Lock((StoreLock *)&hMutex);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)0x302,
      v12,
      v35);
    v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v12, v13);
LABEL_62:
    v33 = hMutex;
    if ( hMutex )
    {
      if ( (_BYTE)v43 )
      {
        ReleaseMutex(hMutex);
        LOBYTE(v43) = 0;
      }
      CloseHandle_0(v33);
      hMutex = 0;
    }
LABEL_66:
    BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v44);
    return v14;
  }
  v37 = 0;
  v45[0] = 0;
  if ( a6 )
    *a6 = 0;
  if ( (a2 & 0xFFFFFFFC) == 0 )
  {
    if ( !a4 )
    {
      v39 = 783;
LABEL_15:
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v38);
      if ( v37 )
      {
        RtlCloseDefinitionAppIdHandle();
        v37 = 0;
      }
      v16 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v43 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v43) = 0;
        }
        CloseHandle_0(v16);
        hMutex = 0;
      }
      BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v44);
      return v40;
    }
    if ( !a3 )
    {
      v39 = 784;
      goto LABEL_15;
    }
    if ( !a6 )
    {
      v39 = 785;
      goto LABEL_15;
    }
    if ( *(_QWORD *)&a5->Data1 != *(_QWORD *)&GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f.Data1
      || *(_QWORD *)a5->Data4 != *(_QWORD *)GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f.Data4 )
    {
      v14 = -2147467262;
      Windows::ErrorHandling::COM::ReportErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
        (const char *)0x314,
        -2147467262,
        v11);
      if ( v37 )
      {
        RtlCloseDefinitionAppIdHandle();
        v37 = 0;
      }
      goto LABEL_62;
    }
    v17 = a2 & 1 | 2;
    if ( (a2 & 2) == 0 )
      v17 = a2 & 1;
    v18 = IsolationImplementation::Com::ConvertIn(a4, (struct IDefinitionIdentity *)v45, v10);
    v14 = v18;
    if ( v18 >= 0 )
    {
      v18 = IsolationImplementation::Com::ConvertIn(a3, (struct IDefinitionAppId *)&v37, v19);
      v14 = v18;
      if ( v18 >= 0 )
      {
        v24 = v45[0];
        *(_QWORD *)v41 = 0;
        v25 = RtlEnumerateComponentStoreApplicationPrivateComponentFiles(
                v17,
                *((_QWORD *)this + 2),
                v37,
                v45[0],
                (__int64)v41);
        v26 = v25;
        if ( v25 >= 0 )
        {
          v31 = IsolationImplementation::Com::CopyOut(*(_QWORD *)v41, a5, a6);
          v14 = v31;
          if ( v31 >= 0 )
            v14 = 0;
          else
            Windows::ErrorHandling::COM::ReportErrorPropagation(
              (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
              (const char *)0x329,
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
            (const char *)0x327,
            v26,
            v36);
          v14 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v26, v27);
        }
        if ( *(_QWORD *)v41 )
        {
          v40 = -1073741595;
          v38 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(*(_QWORD *)v41) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v29 + 4))(*v29, v28);
            v30 = 0;
          }
          else
          {
            v39 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v38);
            v30 = v40;
          }
          if ( v30 < 0 )
            RaiseException(v30, 1u, 0, 0);
          *(_QWORD *)v41 = 0;
        }
        if ( !v24 )
          goto LABEL_35;
        v22 = v24;
        goto LABEL_34;
      }
      v21 = 797;
    }
    else
    {
      v21 = 796;
    }
    Windows::ErrorHandling::COM::ReportErrorPropagation(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\store.cpp",
      (const char *)v21,
      v18,
      v20);
    v22 = v45[0];
    if ( !v45[0] )
    {
LABEL_35:
      if ( v37 )
      {
        RtlCloseDefinitionAppIdHandle();
        v37 = 0;
      }
      v23 = hMutex;
      if ( hMutex )
      {
        if ( (_BYTE)v43 )
        {
          ReleaseMutex(hMutex);
          LOBYTE(v43) = 0;
        }
        CloseHandle_0(v23);
        hMutex = 0;
      }
      goto LABEL_66;
    }
LABEL_34:
    RtlCloseDefinitionIdentityHandle(v22);
    goto LABEL_35;
  }
  v15 = hMutex;
  v39 = 782;
  if ( hMutex )
  {
    if ( (_BYTE)v43 )
    {
      ReleaseMutex(hMutex);
      LOBYTE(v43) = 0;
    }
    CloseHandle_0(v15);
    hMutex = 0;
  }
  BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer((BCL::Nt::CUnicodeStringBuffer *)v44);
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v38);
  return v40;
}

```

## disassembly

```asm
0x1800ad878  mov     [rsp-8+arg_0], rcx
0x1800ad87d  push    rbp
0x1800ad87e  push    rbx
0x1800ad87f  push    rsi
0x1800ad880  push    rdi
0x1800ad881  push    r12
0x1800ad883  push    r13
0x1800ad885  push    r14
0x1800ad887  push    r15
0x1800ad889  lea     rbp, [rsp-0Fh]
0x1800ad88e  sub     rsp, 0C8h
0x1800ad895  lea     rsi, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ad89c  mov     [rbp+47h+var_B8], 8007054Fh
0x1800ad8a3  lea     rcx, [rbp+47h+var_90]; this
0x1800ad8a7  mov     [rsp+100h+var_C8], rsi
0x1800ad8ac  mov     r12, r9
0x1800ad8af  mov     r15, r8
0x1800ad8b2  mov     edi, edx
0x1800ad8b4  call    ??0CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::CUnicodeStringBuffer(void)
0x1800ad8b9  xor     r13d, r13d
0x1800ad8bc  lea     rcx, [rbp+47h+hMutex]; this
0x1800ad8c0  mov     [rbp+47h+hMutex], r13
0x1800ad8c4  mov     [rbp+47h+var_98], r13w
0x1800ad8c9  call    ?Lock@StoreLock@@QEAAJXZ; StoreLock::Lock(void)
0x1800ad8ce  mov     ebx, eax
0x1800ad8d0  test    eax, eax
0x1800ad8d2  jns     short loc_1800AD908
0x1800ad8d4  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800ad8da  jnz     short loc_1800AD8E2
0x1800ad8dc  call    cs:__imp_DebugBreak
0x1800ad8e2  mov     r9d, ebx; int
0x1800ad8e5  lea     rcx, aStatusPropagat; "Status propagated"
0x1800ad8ec  mov     r8d, 302h; char *
0x1800ad8f2  mov     rdx, rsi; char *
0x1800ad8f5  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800ad8fa  mov     ecx, ebx; this
0x1800ad8fc  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800ad901  mov     edi, eax
0x1800ad903  jmp     loc_1800ADC08
0x1800ad908  mov     rsi, [rbp+47h+arg_28]
0x1800ad90c  mov     [rsp+100h+var_D0], r13
0x1800ad911  mov     [rbp+47h+var_50], r13
0x1800ad915  test    rsi, rsi
0x1800ad918  jz      short loc_1800AD91D
0x1800ad91a  mov     [rsi], r13
0x1800ad91d  test    edi, 0FFFFFFFCh
0x1800ad923  jz      short loc_1800AD969
0x1800ad925  mov     rbx, [rbp+47h+hMutex]
0x1800ad929  mov     [rbp+47h+var_C0], 30Eh
0x1800ad930  test    rbx, rbx
0x1800ad933  jz      short loc_1800AD954
0x1800ad935  cmp     byte ptr [rbp+47h+var_98], r13b
0x1800ad939  jz      short loc_1800AD948
0x1800ad93b  mov     rcx, rbx; hMutex
0x1800ad93e  call    cs:__imp_ReleaseMutex
0x1800ad944  mov     byte ptr [rbp+47h+var_98], r13b
0x1800ad948  mov     rcx, rbx; hObject
0x1800ad94b  call    CloseHandle_0
0x1800ad950  mov     [rbp+47h+hMutex], r13
0x1800ad954  lea     rcx, [rbp+47h+var_90]; this
0x1800ad958  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ad95d  lea     rcx, [rsp+100h+var_C8]
0x1800ad962  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x1800ad967  jmp     short loc_1800AD9C4
0x1800ad969  test    r12, r12
0x1800ad96c  jnz     short loc_1800AD9CC
0x1800ad96e  mov     [rbp+47h+var_C0], 30Fh
0x1800ad975  lea     rcx, [rsp+100h+var_C8]
0x1800ad97a  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800ad97f  mov     rcx, [rsp+100h+var_D0]
0x1800ad984  test    rcx, rcx
0x1800ad987  jz      short loc_1800AD993
0x1800ad989  call    RtlCloseDefinitionAppIdHandle
0x1800ad98e  mov     [rsp+100h+var_D0], r13
0x1800ad993  mov     rbx, [rbp+47h+hMutex]
0x1800ad997  test    rbx, rbx
0x1800ad99a  jz      short loc_1800AD9BB
0x1800ad99c  cmp     byte ptr [rbp+47h+var_98], r13b
0x1800ad9a0  jz      short loc_1800AD9AF
0x1800ad9a2  mov     rcx, rbx; hMutex
0x1800ad9a5  call    cs:__imp_ReleaseMutex
0x1800ad9ab  mov     byte ptr [rbp+47h+var_98], r13b
0x1800ad9af  mov     rcx, rbx; hObject
0x1800ad9b2  call    CloseHandle_0
0x1800ad9b7  mov     [rbp+47h+hMutex], r13
0x1800ad9bb  lea     rcx, [rbp+47h+var_90]; this
0x1800ad9bf  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800ad9c4  mov     edi, [rbp+47h+var_B8]
0x1800ad9c7  jmp     loc_1800ADC39
0x1800ad9cc  test    r15, r15
0x1800ad9cf  jnz     short loc_1800AD9DA
0x1800ad9d1  mov     [rbp+47h+var_C0], 310h
0x1800ad9d8  jmp     short loc_1800AD975
0x1800ad9da  test    rsi, rsi
0x1800ad9dd  jnz     short loc_1800AD9E8
0x1800ad9df  mov     [rbp+47h+var_C0], 311h
0x1800ad9e6  jmp     short loc_1800AD975
0x1800ad9e8  mov     r14, [rbp+47h+arg_20]
0x1800ad9ec  mov     rax, [r14]
0x1800ad9ef  cmp     rax, qword ptr cs:_GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f.Data1
0x1800ad9f6  jnz     loc_1800ADBDB
0x1800ad9fc  mov     rax, [r14+8]
0x1800ada00  cmp     rax, qword ptr cs:_GUID_a5c6aaa3_03e4_478d_b9f5_2e45908d5e4f.Data4
0x1800ada07  jnz     loc_1800ADBDB
0x1800ada0d  mov     eax, edi
0x1800ada0f  lea     rdx, [rbp+47h+var_50]; struct IDefinitionIdentity *
0x1800ada13  and     eax, 1
0x1800ada16  mov     rcx, r12; this
0x1800ada19  mov     r13d, eax
0x1800ada1c  or      r13d, 2
0x1800ada20  test    dil, 2
0x1800ada24  cmovz   r13d, eax
0x1800ada28  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800ada2d  xor     r12d, r12d
0x1800ada30  mov     edi, eax
0x1800ada32  test    eax, eax
0x1800ada34  jns     short loc_1800ADA9D
0x1800ada36  mov     edx, 31Ch; char *
0x1800ada3b  mov     r8d, eax; int
0x1800ada3e  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800ada45  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800ada4a  mov     rcx, [rbp+47h+var_50]
0x1800ada4e  test    rcx, rcx
0x1800ada51  jz      short loc_1800ADA58
0x1800ada53  call    RtlCloseDefinitionIdentityHandle
0x1800ada58  mov     rcx, [rsp+100h+var_D0]
0x1800ada5d  test    rcx, rcx
0x1800ada60  jz      short loc_1800ADA6C
0x1800ada62  call    RtlCloseDefinitionAppIdHandle
0x1800ada67  mov     [rsp+100h+var_D0], r12
0x1800ada6c  mov     rbx, [rbp+47h+hMutex]
0x1800ada70  test    rbx, rbx
0x1800ada73  jz      loc_1800ADC30
0x1800ada79  cmp     byte ptr [rbp+47h+var_98], r12b
0x1800ada7d  jz      short loc_1800ADA8C
0x1800ada7f  mov     rcx, rbx; hMutex
0x1800ada82  call    cs:__imp_ReleaseMutex
0x1800ada88  mov     byte ptr [rbp+47h+var_98], r12b
0x1800ada8c  mov     rcx, rbx; hObject
0x1800ada8f  call    CloseHandle_0
0x1800ada94  mov     [rbp+47h+hMutex], r12
0x1800ada98  jmp     loc_1800ADC30
0x1800ada9d  lea     rdx, [rsp+100h+var_D0]; struct IDefinitionAppId *
0x1800adaa2  mov     rcx, r15; this
0x1800adaa5  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionAppId@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionAppId *,Windows::Isolation::Rtl::_DEFINITION_APPID *)
0x1800adaaa  mov     edi, eax
0x1800adaac  test    eax, eax
0x1800adaae  jns     short loc_1800ADAB7
0x1800adab0  mov     edx, 31Dh
0x1800adab5  jmp     short loc_1800ADA3B
0x1800adab7  mov     rdx, [rbp+47h+arg_0]
0x1800adabb  lea     rax, [rbp+47h+var_B0]
0x1800adabf  mov     rbx, [rbp+47h+var_50]
0x1800adac3  mov     ecx, r13d
0x1800adac6  mov     r8, [rsp+100h+var_D0]
0x1800adacb  mov     r9, rbx
0x1800adace  mov     qword ptr [rbp+47h+var_B0], r12
0x1800adad2  mov     rdx, [rdx+10h]
0x1800adad6  mov     qword ptr [rsp+100h+var_E0], rax; unsigned int
0x1800adadb  call    RtlEnumerateComponentStoreApplicationPrivateComponentFiles
0x1800adae0  mov     edi, eax
0x1800adae2  test    eax, eax
0x1800adae4  jns     loc_1800ADBA5
0x1800adaea  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800adaf0  jnz     short loc_1800ADAF8
0x1800adaf2  call    cs:__imp_DebugBreak
0x1800adaf8  mov     r9d, edi; int
0x1800adafb  lea     rdx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adb02  mov     r8d, 327h; char *
0x1800adb08  lea     rcx, aStatusPropagat; "Status propagated"
0x1800adb0f  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800adb14  mov     ecx, edi; this
0x1800adb16  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800adb1b  mov     edi, eax
0x1800adb1d  mov     r10, qword ptr [rbp+47h+var_B0]
0x1800adb21  test    r10, r10
0x1800adb24  jz      short loc_1800ADB7E
0x1800adb26  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@VCFileEnumerator@@VCFileEnumeratorCD@@VCFileEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,CFileEnumerator,CFileEnumeratorCD,CFileEnumeratorTraits>::ms_ptti
0x1800adb2d  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adb34  mov     [rbp+47h+var_B8], 0C00000E5h
0x1800adb3b  mov     [rsp+100h+var_C8], rax
0x1800adb40  test    r11, r11
0x1800adb43  jz      short loc_1800ADB8F
0x1800adb45  mov     rdx, r11
0x1800adb48  mov     rcx, r10
0x1800adb4b  call    RtlIsTypeSafeHandleValid
0x1800adb50  test    al, al
0x1800adb52  jz      short loc_1800ADB8F
0x1800adb54  mov     ecx, [r11]
0x1800adb57  mov     rdx, r10
0x1800adb5a  mov     rax, [r11+20h]
0x1800adb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb63  mov     ecx, r12d; dwExceptionCode
0x1800adb66  test    ecx, ecx
0x1800adb68  jns     short loc_1800ADB7A
0x1800adb6a  xor     r9d, r9d; lpArguments
0x1800adb6d  xor     r8d, r8d; nNumberOfArguments
0x1800adb70  lea     edx, [r9+1]; dwExceptionFlags
0x1800adb74  call    cs:__imp_RaiseException
0x1800adb7a  mov     qword ptr [rbp+47h+var_B0], r12
0x1800adb7e  test    rbx, rbx
0x1800adb81  jz      loc_1800ADA58
0x1800adb87  mov     rcx, rbx
0x1800adb8a  jmp     loc_1800ADA53
0x1800adb8f  mov     [rbp+47h+var_C0], 124h
0x1800adb96  lea     rcx, [rsp+100h+var_C8]
0x1800adb9b  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800adba0  mov     ecx, [rbp+47h+var_B8]
0x1800adba3  jmp     short loc_1800ADB66
0x1800adba5  mov     rcx, qword ptr [rbp+47h+var_B0]
0x1800adba9  mov     r8, rsi
0x1800adbac  mov     rdx, r14
0x1800adbaf  call    ?CopyOut@Com@IsolationImplementation@@YAJU_COMPONENT_STORE_FILE_ENUMERATOR@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_COMPONENT_STORE_FILE_ENUMERATOR,_GUID const &,IUnknown * *)
0x1800adbb4  mov     edi, eax
0x1800adbb6  test    eax, eax
0x1800adbb8  jns     short loc_1800ADBD3
0x1800adbba  mov     r8d, eax; int
0x1800adbbd  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adbc4  mov     edx, 329h; char *
0x1800adbc9  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800adbce  jmp     loc_1800ADB1D
0x1800adbd3  mov     edi, r12d
0x1800adbd6  jmp     loc_1800ADB1D
0x1800adbdb  mov     edi, 80004002h
0x1800adbe0  lea     rcx, aOnecoreComNetf_88; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800adbe7  mov     r8d, edi; int
0x1800adbea  mov     edx, 314h; char *
0x1800adbef  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x1800adbf4  mov     rcx, [rsp+100h+var_D0]
0x1800adbf9  test    rcx, rcx
0x1800adbfc  jz      short loc_1800ADC08
0x1800adbfe  call    RtlCloseDefinitionAppIdHandle
0x1800adc03  mov     [rsp+100h+var_D0], r13
0x1800adc08  mov     rbx, [rbp+47h+hMutex]
0x1800adc0c  test    rbx, rbx
0x1800adc0f  jz      short loc_1800ADC30
0x1800adc11  cmp     byte ptr [rbp+47h+var_98], r13b
0x1800adc15  jz      short loc_1800ADC24
0x1800adc17  mov     rcx, rbx; hMutex
0x1800adc1a  call    cs:__imp_ReleaseMutex
0x1800adc20  mov     byte ptr [rbp+47h+var_98], r13b
0x1800adc24  mov     rcx, rbx; hObject
0x1800adc27  call    CloseHandle_0
0x1800adc2c  mov     [rbp+47h+hMutex], r13
0x1800adc30  lea     rcx, [rbp+47h+var_90]; this
0x1800adc34  call    ??1CUnicodeStringBuffer@Nt@BCL@@QEAA@XZ; BCL::Nt::CUnicodeStringBuffer::~CUnicodeStringBuffer(void)
0x1800adc39  mov     eax, edi
0x1800adc3b  add     rsp, 0C8h
0x1800adc42  pop     r15
0x1800adc44  pop     r14
0x1800adc46  pop     r13
0x1800adc48  pop     r12
0x1800adc4a  pop     rdi
0x1800adc4b  pop     rsi
0x1800adc4c  pop     rbx
0x1800adc4d  pop     rbp
0x1800adc4e  retn
```
