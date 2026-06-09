# container::RegistryProvider::SetupSymlink(Schema::Containers::Definition::RegistrySymlink const &)

- ea: `0x18002abc0`
- end: `0x18002af06`
- name: `?SetupSymlink@RegistryProvider@container@@YAXAEBURegistrySymlink@Definition@Containers@Schema@@@Z`
- size: `838`
- prototype: `void __fastcall(container::RegistryProvider *__hidden this, const struct Schema::Containers::Definition::RegistrySymlink *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, registry_config, loader_planting, installer_update`

## callers

- `0x180029a1c`

## callees

- `0x180001f4c`
- `0x180002ad0`
- `0x1800051b0`
- `0x18000895c`
- `0x18000b4bc`
- `0x180012b30`
- `0x1800215cc`
- `0x180026830`
- `0x180027f20`
- `0x18002805c`
- `0x180028100`
- `0x1800281e8`
- `0x18002abc0`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x18002acc3`
- `ntdll!NtDeleteKey` at `0x18002acc3`
- `ntdll!NtCreateKey` at `0x18002aca3`
- `ntdll!NtCreateKey` at `0x18002aca3`
- `ntdll!NtSetValueKey` at `0x18002adbf`
- `ntdll!NtSetValueKey` at `0x18002adbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ace7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ace7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002addf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002addf`

## string_xrefs

- `0x18002ae4d`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002aea3`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002aedc`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002aef4`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall container::RegistryProvider::SetupSymlink(
        container::RegistryProvider *this,
        const struct Schema::Containers::Definition::RegistrySymlink *a2)
{
  _QWORD *v3; // rdi
  char *v4; // rbx
  container::RegistryProvider *v5; // r14
  const struct _tlgProvider_t *v6; // rax
  int v7; // r8d
  int v8; // r9d
  int v9; // r15d
  char v10; // r14
  NTSTATUS v11; // ebx
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  void *v14; // r13
  DWORD LastError; // ebx
  _QWORD *v16; // rax
  container::RegistryProvider *v17; // rax
  void *v18; // rcx
  NTSTATUS v19; // eax
  unsigned int v20; // ebx
  int Class; // [rsp+20h] [rbp-89h]
  int Classa; // [rsp+20h] [rbp-89h]
  ULONG Disposition; // [rsp+40h] [rbp-69h] BYREF
  container::RegistryProvider *v24; // [rsp+48h] [rbp-61h] BYREF
  __int64 v25; // [rsp+50h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-51h] BYREF
  __int64 v27; // [rsp+60h] [rbp-49h] BYREF
  __int64 v28; // [rsp+68h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v30[32]; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  Disposition = 0;
  KeyHandle = 0;
  v3 = (_QWORD *)((char *)this + 32);
  if ( *((_QWORD *)this + 7) <= 7u )
    v4 = (char *)this + 32;
  else
    v4 = (char *)*v3;
  if ( *((_QWORD *)this + 3) <= 7u )
    v5 = this;
  else
    v5 = *(container::RegistryProvider **)this;
  v6 = ContainerProvider::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v25 = (__int64)v4;
    v24 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v6,
      (unsigned int)byte_18003CEA3,
      v7,
      v8,
      (__int64)&v24,
      (__int64)&v25);
  }
  v9 = 0;
  v10 = 1;
  while ( 1 )
  {
    windows_wrappers::ObjectAttributes::ObjectAttributes((unsigned int)&ObjectAttributes, (_DWORD)this, 64, 0, 0);
    v11 = NtCreateKey(&KeyHandle, 0x10022u, &ObjectAttributes, 0, 0, 3u, &Disposition);
    if ( v11 < 0 )
    {
      LODWORD(v24) = v9 + 1;
      LODWORD(v25) = v11 | 0x10000000;
      v27 = std::wstring::c_str(v3);
      v28 = std::wstring::c_str(this);
      ContainerProvider::RegistrySymlinkCreationFailure<unsigned short const *,unsigned short const *,long,int,unsigned short const (&)[43]>(
        &v28,
        &v27,
        &v25,
        &v24);
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x390,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        (const char *)(unsigned int)v11,
        Class);
    }
    if ( Disposition == 1 )
      break;
    v12 = NtDeleteKey(KeyHandle);
    v13 = v12;
    if ( v12 < 0 )
    {
      LODWORD(v24) = v12 | 0x10000000;
      v25 = std::wstring::c_str(this);
      ContainerProvider::RegistrySymlinkDeletionFailure<unsigned short const *,long,unsigned short const (&)[40]>(
        &v25,
        &v24);
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x3A1,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        (const char *)v13,
        Class);
    }
    v14 = KeyHandle;
    if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v14);
      SetLastError(LastError);
    }
    KeyHandle = 0;
    std::wstring::~wstring(v30);
    if ( ++v9 >= 2 )
      goto LABEL_18;
  }
  std::wstring::~wstring(v30);
LABEL_18:
  if ( Disposition == 1
    || (v3[3] <= 7u ? (v16 = v3) : (v16 = (_QWORD *)*v3),
        (v25 = (__int64)v16, *((_QWORD *)this + 3) <= 7u) ? (v17 = this) : (v17 = *(container::RegistryProvider **)this),
        v24 = v17,
        ContainerProvider::RegistrySymlinkCreationFailureWithDisposition<unsigned short const *,unsigned short const *,unsigned long &,unsigned short const (&)[41]>(
          &v24,
          &v25,
          &Disposition),
        Disposition == 1) )
  {
    v10 = 0;
  }
  if ( v10 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3B3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      (const char *)0x8007054FLL,
      Class);
  if ( v3[3] <= 7u )
    v18 = v3;
  else
    v18 = (void *)*v3;
  v19 = NtSetValueKey(KeyHandle, (PUNICODE_STRING)&ValueName, 0, 6u, v18, 2 * *((_DWORD *)this + 12));
  v20 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v24) = v19 | 0x10000000;
    v25 = std::wstring::c_str(v3);
    v27 = std::wstring::c_str(this);
    ContainerProvider::RegistrySymlinkValueFailure<unsigned short const *,unsigned short const *,long,unsigned short const (&)[44]>(
      &v27,
      &v25,
      &v24);
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x3C2,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      (const char *)v20,
      Classa);
  }
  if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(KeyHandle);
}

```

## disassembly

```asm
0x18002abc0  mov     [rsp-8+arg_8], rbx
0x18002abc5  mov     [rsp-8+arg_10], rsi
0x18002abca  push    rbp
0x18002abcb  push    rdi
0x18002abcc  push    r13
0x18002abce  push    r14
0x18002abd0  push    r15
0x18002abd2  lea     rbp, [rsp-37h]
0x18002abd7  sub     rsp, 0E0h
0x18002abde  mov     rax, cs:__security_cookie
0x18002abe5  xor     rax, rsp
0x18002abe8  mov     [rbp+57h+var_30], rax
0x18002abec  mov     rsi, rcx
0x18002abef  mov     [rbp+57h+var_C0], 0
0x18002abf6  mov     [rbp+57h+KeyHandle], 0
0x18002abfe  lea     rdi, [rcx+20h]
0x18002ac02  cmp     qword ptr [rdi+18h], 7
0x18002ac07  jbe     short loc_18002AC0E
0x18002ac09  mov     rbx, [rdi]
0x18002ac0c  jmp     short loc_18002AC11
0x18002ac0e  mov     rbx, rdi
0x18002ac11  cmp     qword ptr [rcx+18h], 7
0x18002ac16  jbe     short loc_18002AC1D
0x18002ac18  mov     r14, [rcx]
0x18002ac1b  jmp     short loc_18002AC20
0x18002ac1d  mov     r14, rsi
0x18002ac20  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18002ac25  mov     ecx, [rax]
0x18002ac27  cmp     ecx, 5
0x18002ac2a  jbe     short loc_18002AC55
0x18002ac2c  mov     [rbp+57h+var_B0], rbx
0x18002ac30  mov     [rbp+57h+var_B8], r14
0x18002ac34  lea     rcx, [rbp+57h+var_B0]
0x18002ac38  mov     qword ptr [rsp+100h+CreateOptions], rcx
0x18002ac3d  lea     rcx, [rbp+57h+var_B8]
0x18002ac41  mov     [rsp+100h+Class], rcx
0x18002ac46  lea     rdx, byte_18003CEA3
0x18002ac4d  mov     rcx, rax
0x18002ac50  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002ac55  xor     r15d, r15d
0x18002ac58  lea     r14d, [r15+1]
0x18002ac5c  mov     [rsp+100h+Class], 0
0x18002ac65  xor     r9d, r9d
0x18002ac68  lea     r8d, [r9+40h]
0x18002ac6c  mov     rdx, rsi
0x18002ac6f  lea     rcx, [rbp+57h+ObjectAttributes]
0x18002ac73  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x18002ac78  nop
0x18002ac79  lea     rax, [rbp+57h+var_C0]
0x18002ac7d  mov     [rsp+100h+Disposition], rax; Disposition
0x18002ac82  mov     [rsp+100h+CreateOptions], 3; CreateOptions
0x18002ac8a  mov     [rsp+100h+Class], 0; int
0x18002ac93  xor     r9d, r9d; TitleIndex
0x18002ac96  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002ac9a  mov     edx, 10022h; DesiredAccess
0x18002ac9f  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002aca3  call    cs:__imp_NtCreateKey
0x18002acaa  nop     dword ptr [rax+rax+00h]
0x18002acaf  mov     ebx, eax
0x18002acb1  test    eax, eax
0x18002acb3  js      loc_18002AE5F
0x18002acb9  cmp     [rbp+57h+var_C0], r14d
0x18002acbd  jz      short loc_18002AD32
0x18002acbf  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002acc3  call    cs:__imp_NtDeleteKey
0x18002acca  nop     dword ptr [rax+rax+00h]
0x18002accf  mov     ebx, eax
0x18002acd1  test    eax, eax
0x18002acd3  js      loc_18002AEB5
0x18002acd9  mov     r13, [rbp+57h+KeyHandle]
0x18002acdd  lea     rax, [r13-1]
0x18002ace1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ace5  ja      short loc_18002AD12
0x18002ace7  call    cs:__imp_GetLastError
0x18002acee  nop     dword ptr [rax+rax+00h]
0x18002acf3  mov     ebx, eax
0x18002acf5  mov     rcx, r13; hObject
0x18002acf8  call    cs:__imp_CloseHandle
0x18002acff  nop     dword ptr [rax+rax+00h]
0x18002ad04  mov     ecx, ebx; dwErrCode
0x18002ad06  call    cs:__imp_SetLastError
0x18002ad0d  nop     dword ptr [rax+rax+00h]
0x18002ad12  mov     [rbp+57h+KeyHandle], 0
0x18002ad1a  lea     rcx, [rbp+57h+var_50]
0x18002ad1e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ad23  add     r15d, r14d
0x18002ad26  cmp     r15d, 2
0x18002ad2a  jl      loc_18002AC5C
0x18002ad30  jmp     short loc_18002AD3B
0x18002ad32  lea     rcx, [rbp+57h+var_50]
0x18002ad36  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ad3b  cmp     [rbp+57h+var_C0], r14d
0x18002ad3f  jz      short loc_18002AD7E
0x18002ad41  cmp     qword ptr [rdi+18h], 7
0x18002ad46  jbe     short loc_18002AD4D
0x18002ad48  mov     rax, [rdi]
0x18002ad4b  jmp     short loc_18002AD50
0x18002ad4d  mov     rax, rdi
0x18002ad50  mov     [rbp+57h+var_B0], rax
0x18002ad54  cmp     qword ptr [rsi+18h], 7
0x18002ad59  jbe     short loc_18002AD60
0x18002ad5b  mov     rax, [rsi]
0x18002ad5e  jmp     short loc_18002AD63
0x18002ad60  mov     rax, rsi
0x18002ad63  mov     [rbp+57h+var_B8], rax
0x18002ad67  lea     r8, [rbp+57h+var_C0]
0x18002ad6b  lea     rdx, [rbp+57h+var_B0]
0x18002ad6f  lea     rcx, [rbp+57h+var_B8]
0x18002ad73  call    ??$RegistrySymlinkCreationFailureWithDisposition@PEBGPEBGAEAKAEAY0CJ@$$CBG@ContainerProvider@@SAX$$QEAPEBG0AEAKAEAY0CJ@$$CBG@Z; ContainerProvider::RegistrySymlinkCreationFailureWithDisposition<ushort const *,ushort const *,ulong &,ushort const (&)[41]>(ushort const * &&,ushort const * &&,ulong &,ushort const (&)[41])
0x18002ad78  cmp     [rbp+57h+var_C0], r14d
0x18002ad7c  jnz     short loc_18002AD81
0x18002ad7e  xor     r14b, r14b
0x18002ad81  mov     rcx, [rbp+5Fh]; this
0x18002ad85  test    r14b, r14b
0x18002ad88  jnz     loc_18002AEEE
0x18002ad8e  mov     eax, [rsi+30h]
0x18002ad91  add     eax, eax
0x18002ad93  cmp     qword ptr [rdi+18h], 7
0x18002ad98  jbe     short loc_18002AD9F
0x18002ad9a  mov     rcx, [rdi]
0x18002ad9d  jmp     short loc_18002ADA2
0x18002ad9f  mov     rcx, rdi
0x18002ada2  mov     [rsp+100h+CreateOptions], eax; DataSize
0x18002ada6  mov     [rsp+100h+Class], rcx; int
0x18002adab  mov     r9d, 6; Type
0x18002adb1  xor     r8d, r8d; TitleIndex
0x18002adb4  lea     rdx, ValueName; ValueName
0x18002adbb  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002adbf  call    cs:__imp_NtSetValueKey
0x18002adc6  nop     dword ptr [rax+rax+00h]
0x18002adcb  mov     ebx, eax
0x18002adcd  test    eax, eax
0x18002adcf  js      short loc_18002AE14
0x18002add1  mov     rcx, [rbp+57h+KeyHandle]; hObject
0x18002add5  lea     rax, [rcx-1]
0x18002add9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002addd  ja      short loc_18002ADEB
0x18002addf  call    cs:__imp_CloseHandle
0x18002ade6  nop     dword ptr [rax+rax+00h]
0x18002adeb  mov     rcx, [rbp+57h+var_30]
0x18002adef  xor     rcx, rsp; StackCookie
0x18002adf2  call    __security_check_cookie
0x18002adf7  lea     r11, [rsp+100h+var_20]
0x18002adff  mov     rbx, [r11+38h]
0x18002ae03  mov     rsi, [r11+40h]
0x18002ae07  mov     rsp, r11
0x18002ae0a  pop     r15
0x18002ae0c  pop     r14
0x18002ae0e  pop     r13
0x18002ae10  pop     rdi
0x18002ae11  pop     rbp
0x18002ae12  retn
0x18002ae14  mov     edx, ebx
0x18002ae16  bts     edx, 1Ch
0x18002ae1a  mov     dword ptr [rbp+57h+var_B8], edx
0x18002ae1d  mov     rcx, rdi
0x18002ae20  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002ae25  mov     [rbp+57h+var_B0], rax
0x18002ae29  mov     rcx, rsi
0x18002ae2c  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002ae31  mov     [rbp+57h+var_A0], rax
0x18002ae35  lea     r8, [rbp+57h+var_B8]
0x18002ae39  lea     rdx, [rbp+57h+var_B0]
0x18002ae3d  lea     rcx, [rbp+57h+var_A0]
0x18002ae41  call    ??$RegistrySymlinkValueFailure@PEBGPEBGJAEAY0CM@$$CBG@ContainerProvider@@SAX$$QEAPEBG0$$QEAJAEAY0CM@$$CBG@Z; ContainerProvider::RegistrySymlinkValueFailure<ushort const *,ushort const *,long,ushort const (&)[44]>(ushort const * &&,ushort const * &&,long &&,ushort const (&)[44])
0x18002ae46  mov     rcx, [rbp+5Fh]; this
0x18002ae4a  mov     r9d, ebx; char *
0x18002ae4d  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002ae54  mov     edx, 3C2h; void *
0x18002ae59  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002ae5f  lea     eax, [r15+1]
0x18002ae63  mov     dword ptr [rbp+57h+var_B8], eax
0x18002ae66  mov     eax, ebx
0x18002ae68  bts     eax, 1Ch
0x18002ae6c  mov     dword ptr [rbp+57h+var_B0], eax
0x18002ae6f  mov     rcx, rdi
0x18002ae72  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002ae77  mov     [rbp+57h+var_A0], rax
0x18002ae7b  mov     rcx, rsi
0x18002ae7e  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002ae83  mov     [rbp+57h+var_98], rax
0x18002ae87  lea     r9, [rbp+57h+var_B8]
0x18002ae8b  lea     r8, [rbp+57h+var_B0]
0x18002ae8f  lea     rdx, [rbp+57h+var_A0]
0x18002ae93  lea     rcx, [rbp+57h+var_98]
0x18002ae97  call    ??$RegistrySymlinkCreationFailure@PEBGPEBGJHAEAY0CL@$$CBG@ContainerProvider@@SAX$$QEAPEBG0$$QEAJ$$QEAHAEAY0CL@$$CBG@Z; ContainerProvider::RegistrySymlinkCreationFailure<ushort const *,ushort const *,long,int,ushort const (&)[43]>(ushort const * &&,ushort const * &&,long &&,int &&,ushort const (&)[43])
0x18002ae9c  mov     rcx, [rbp+5Fh]; this
0x18002aea0  mov     r9d, ebx; char *
0x18002aea3  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002aeaa  mov     edx, 390h; void *
0x18002aeaf  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002aeb5  bts     eax, 1Ch
0x18002aeb9  mov     dword ptr [rbp+57h+var_B8], eax
0x18002aebc  mov     rcx, rsi
0x18002aebf  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002aec4  mov     [rbp+57h+var_B0], rax
0x18002aec8  lea     rdx, [rbp+57h+var_B8]
0x18002aecc  lea     rcx, [rbp+57h+var_B0]
0x18002aed0  call    ??$RegistrySymlinkDeletionFailure@PEBGJAEAY0CI@$$CBG@ContainerProvider@@SAX$$QEAPEBG$$QEAJAEAY0CI@$$CBG@Z; ContainerProvider::RegistrySymlinkDeletionFailure<ushort const *,long,ushort const (&)[40]>(ushort const * &&,long &&,ushort const (&)[40])
0x18002aed5  mov     rcx, [rbp+5Fh]; this
0x18002aed9  mov     r9d, ebx; char *
0x18002aedc  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002aee3  mov     edx, 3A1h; void *
0x18002aee8  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002aeee  mov     r9d, 8007054Fh; char *
0x18002aef4  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002aefb  mov     edx, 3B3h; void *
0x18002af00  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
