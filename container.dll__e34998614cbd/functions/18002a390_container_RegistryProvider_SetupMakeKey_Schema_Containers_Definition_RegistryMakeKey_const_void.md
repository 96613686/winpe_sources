# container::RegistryProvider::SetupMakeKey(Schema::Containers::Definition::RegistryMakeKey const &,void *)

- ea: `0x18002a390`
- end: `0x18002a784`
- name: `?SetupMakeKey@RegistryProvider@container@@YAXAEBURegistryMakeKey@Definition@Containers@Schema@@PEAX@Z`
- size: `1012`
- prototype: `void __fastcall(container::RegistryProvider *__hidden this, const struct Schema::Containers::Definition::RegistryMakeKey *, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029bc0`
- `0x18002a390`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000b4bc`
- `0x180011fe8`
- `0x180012b30`
- `0x1800215cc`
- `0x180026830`
- `0x18002759c`
- `0x180029888`
- `0x18002a390`
- `0x18002c444`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002a67b`
- `ntdll!RtlInitUnicodeString` at `0x18002a67b`
- `ntdll!NtCreateKey` at `0x18002a4a3`
- `ntdll!NtCreateKey` at `0x18002a4a3`
- `ntdll!NtSetValueKey` at `0x18002a69d`
- `ntdll!NtSetValueKey` at `0x18002a69d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a453`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a472`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a472`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a6e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a6e4`

## string_xrefs

- `0x18002a507`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002a74d`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002a525`: `Invalid registry definition. Cannot create a stable key underneath a volatile one.`
- `0x18002a741`: `CreateKey(%ws) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall container::RegistryProvider::SetupMakeKey(
        container::RegistryProvider *this,
        const struct Schema::Containers::Definition::RegistryMakeKey *a2,
        void *a3)
{
  int v3; // esi
  void *v5; // r14
  char *v6; // rcx
  char *v7; // rbx
  struct SecurityDescriptor *v8; // r8
  ULONG CreateOptions; // r15d
  NTSTATUS v10; // r9d
  const struct Schema::Containers::Definition::RegistryMakeKey *v11; // r13
  unsigned __int64 v12; // rdx
  container::RegistryProvider *v13; // r15
  container::RegistryProvider *i; // rbx
  char v15; // al
  void *v16; // r8
  __int64 v17; // rbx
  HANDLE *p_hObject; // r15
  unsigned __int64 v19; // rdi
  ULONG v20; // r12d
  __int64 v21; // rax
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  __int64 v24; // r9
  const WCHAR *v25; // rdx
  NTSTATUS v26; // eax
  const char *v27; // rax
  const char *v28; // r9
  int Class; // [rsp+20h] [rbp-A9h]
  const char *Disposition; // [rsp+30h] [rbp-99h]
  HANDLE hObject; // [rsp+40h] [rbp-89h] BYREF
  void *v32; // [rsp+48h] [rbp-81h] BYREF
  const struct Schema::Containers::Definition::RegistryMakeKey *v33; // [rsp+50h] [rbp-79h]
  __int64 j; // [rsp+58h] [rbp-71h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-59h] BYREF
  char v37[32]; // [rsp+B0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v3 = (int)a2;
  v33 = 0;
  v5 = 0;
  v32 = 0;
  v6 = (char *)this + 32;
  if ( *((_QWORD *)v6 + 2) )
  {
    v7 = (char *)container::Registry::OpenKey(v6, 16908313);
    hObject = v7;
    windows_wrappers::GetSecurityDescriptor(v7, &v32, v8);
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v7);
    v5 = v32;
  }
  CreateOptions = *((_BYTE *)this + 112) != 0;
  windows_wrappers::ObjectAttributes::ObjectAttributes(
    (unsigned int)&ObjectAttributes,
    (_DWORD)this,
    64,
    v3,
    (__int64)v5);
  hObject = 0;
  v10 = NtCreateKey(&hObject, 0xF003Fu, &ObjectAttributes, 0, 0, CreateOptions, 0);
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -1073741771 )
  {
    v27 = (const char *)std::wstring::c_str(this);
    wil::details::in1diag3::Throw_NtStatusMsg(
      retaddr,
      (void *)0x3EC,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v28,
      (int)"CreateKey(%ws) failed",
      v27);
  }
  v11 = (const struct Schema::Containers::Definition::RegistryMakeKey *)hObject;
  hObject = 0;
  std::wstring::~wstring(v37);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  v33 = v11;
  v13 = (container::RegistryProvider *)*((_QWORD *)this + 9);
  for ( i = (container::RegistryProvider *)*((_QWORD *)this + 8);
        i != v13;
        i = (container::RegistryProvider *)((char *)i + 120) )
  {
    if ( !*((_BYTE *)this + 112) || (v15 = 1, *((_BYTE *)i + 112)) )
      v15 = 0;
    LOBYTE(Class) = v15;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x2AE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      (const char *)0x80070057LL,
      Class,
      (bool)"Invalid registry definition. Cannot create a stable key underneath a volatile one.",
      Disposition);
    container::RegistryProvider::SetupMakeKey(i, v11, v16);
  }
  v17 = *((_QWORD *)this + 11);
  for ( j = *((_QWORD *)this + 12); v17 != j; v17 += 152 )
  {
    LODWORD(hObject) = 0;
    if ( *(_BYTE *)(v17 + 144) )
    {
      p_hObject = *(HANDLE **)(v17 + 120);
      v19 = *(_QWORD *)(v17 + 128) - (_QWORD)p_hObject;
      if ( v19 > 0xFFFFFFFF )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2CA,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
          (const char *)0x80070216LL,
          Class);
      v20 = 3;
    }
    else if ( *(_BYTE *)(v17 + 76) )
    {
      LODWORD(hObject) = *(_DWORD *)(v17 + 72);
      p_hObject = &hObject;
      LODWORD(v19) = 4;
      v20 = 4;
    }
    else
    {
      if ( *(_BYTE *)(v17 + 64) )
      {
        v21 = 32;
        v20 = 7;
      }
      else
      {
        if ( !*(_BYTE *)(v17 + 112) )
          __fastfail(5u);
        v21 = 80;
        v20 = 1;
      }
      v22 = v21 + v17;
      if ( *(_QWORD *)(v21 + v17 + 24) <= 7u )
        p_hObject = (HANDLE *)(v21 + v17);
      else
        p_hObject = *(HANDLE **)v22;
      v23 = *(_QWORD *)(v22 + 16);
      if ( v23 + 1 < v23 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x2E0,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
          v23 + 1 < v23 ? (const char *)0xC0000095LL : 0,
          Class);
      *(_QWORD *)&DestinationString.Length = 0;
      LODWORD(v19) = 2 * (v23 + 1);
      if ( is_mul_ok(v23 + 1, 2u) )
      {
        v24 = 0;
      }
      else
      {
        LODWORD(v19) = -1;
        v24 = 3221225621LL;
      }
      if ( (int)v24 < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x2E3,
          (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
          (const char *)v24,
          Class);
    }
    DestinationString = 0;
    if ( *(_QWORD *)(v17 + 24) <= 7u )
      v25 = (const WCHAR *)v17;
    else
      v25 = *(const WCHAR **)v17;
    RtlInitUnicodeString(&DestinationString, v25);
    v26 = NtSetValueKey(v11, &DestinationString, 0, v20, p_hObject, v19);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x405,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
        (const char *)(unsigned int)v26,
        Class);
  }
  if ( v5 )
    operator delete(v5, v12);
  if ( (unsigned __int64)v11 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
}

```

## disassembly

```asm
0x18002a390  push    rbp
0x18002a392  push    rbx
0x18002a393  push    rsi
0x18002a394  push    rdi
0x18002a395  push    r12
0x18002a397  push    r13
0x18002a399  push    r14
0x18002a39b  push    r15
0x18002a39d  lea     rbp, [rsp-1Fh]
0x18002a3a2  sub     rsp, 0E8h
0x18002a3a9  mov     rax, cs:__security_cookie
0x18002a3b0  xor     rax, rsp
0x18002a3b3  mov     [rbp+57h+var_50], rax
0x18002a3b7  mov     rsi, rdx
0x18002a3ba  mov     rdi, rcx
0x18002a3bd  xor     r12d, r12d
0x18002a3c0  mov     [rbp+57h+var_D0], r12
0x18002a3c4  mov     r14d, r12d
0x18002a3c7  mov     [rsp+120h+var_D8], r12
0x18002a3cc  add     rcx, 20h ; ' '
0x18002a3d0  cmp     [rcx+10h], r12
0x18002a3d4  jz      short loc_18002A419
0x18002a3d6  mov     [rsp+120h+hObject], r12
0x18002a3db  mov     edx, 1020019h
0x18002a3e0  call    ?OpenKey@Registry@container@@YAPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; container::Registry::OpenKey(std::wstring const &,ulong)
0x18002a3e5  mov     rbx, rax
0x18002a3e8  mov     [rsp+120h+hObject], rax
0x18002a3ed  lea     rdx, [rsp+120h+var_D8]; void *
0x18002a3f2  mov     rcx, rax; Handle
0x18002a3f5  call    ?GetSecurityDescriptor@windows_wrappers@@YAXPEAXAEAVSecurityDescriptor@1@@Z; windows_wrappers::GetSecurityDescriptor(void *,windows_wrappers::SecurityDescriptor &)
0x18002a3fa  nop
0x18002a3fb  lea     rcx, [rbx-1]
0x18002a3ff  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002a403  ja      short loc_18002A414
0x18002a405  mov     rcx, rbx; hObject
0x18002a408  call    cs:__imp_CloseHandle
0x18002a40f  nop     dword ptr [rax+rax+00h]
0x18002a414  mov     r14, [rsp+120h+var_D8]
0x18002a419  mov     r15d, r12d
0x18002a41c  cmp     [rdi+70h], r12b
0x18002a420  setnz   r15b
0x18002a424  mov     [rsp+120h+hObject], r12
0x18002a429  mov     [rsp+120h+Class], r14
0x18002a42e  mov     r9, rsi
0x18002a431  mov     r8d, 40h ; '@'
0x18002a437  mov     rdx, rdi
0x18002a43a  lea     rcx, [rbp+57h+ObjectAttributes]
0x18002a43e  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x18002a443  nop
0x18002a444  mov     rsi, [rsp+120h+hObject]
0x18002a449  lea     rax, [rsi-1]
0x18002a44d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a451  ja      short loc_18002A47E
0x18002a453  call    cs:__imp_GetLastError
0x18002a45a  nop     dword ptr [rax+rax+00h]
0x18002a45f  mov     ebx, eax
0x18002a461  mov     rcx, rsi; hObject
0x18002a464  call    cs:__imp_CloseHandle
0x18002a46b  nop     dword ptr [rax+rax+00h]
0x18002a470  mov     ecx, ebx; dwErrCode
0x18002a472  call    cs:__imp_SetLastError
0x18002a479  nop     dword ptr [rax+rax+00h]
0x18002a47e  mov     [rsp+120h+hObject], r12
0x18002a483  mov     [rsp+120h+Disposition], r12; Disposition
0x18002a488  mov     [rsp+120h+CreateOptions], r15d; CreateOptions
0x18002a48d  mov     [rsp+120h+Class], r12; Class
0x18002a492  xor     r9d, r9d; TitleIndex
0x18002a495  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002a499  mov     edx, 0F003Fh; DesiredAccess
0x18002a49e  lea     rcx, [rsp+120h+hObject]; KeyHandle
0x18002a4a3  call    cs:__imp_NtCreateKey
0x18002a4aa  nop     dword ptr [rax+rax+00h]
0x18002a4af  mov     r9d, eax
0x18002a4b2  mov     eax, 80000000h
0x18002a4b7  lea     edx, [r9+rax]
0x18002a4bb  test    eax, edx
0x18002a4bd  jnz     short loc_18002A4CC
0x18002a4bf  cmp     r9d, 0C0000035h
0x18002a4c6  jnz     loc_18002A730
0x18002a4cc  mov     r13, [rsp+120h+hObject]
0x18002a4d1  mov     [rsp+120h+hObject], r12
0x18002a4d6  lea     rcx, [rbp+57h+var_70]
0x18002a4da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a4df  nop
0x18002a4e0  mov     rcx, [rsp+120h+hObject]; hObject
0x18002a4e5  lea     rax, [rcx-1]
0x18002a4e9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a4ed  ja      short loc_18002A4FB
0x18002a4ef  call    cs:__imp_CloseHandle
0x18002a4f6  nop     dword ptr [rax+rax+00h]
0x18002a4fb  mov     [rbp+57h+var_D0], r13
0x18002a4ff  mov     r15, [rdi+48h]
0x18002a503  mov     rbx, [rdi+40h]
0x18002a507  lea     rsi, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002a50e  jmp     short loc_18002A557
0x18002a510  cmp     [rdi+70h], r12b
0x18002a514  jz      short loc_18002A51E
0x18002a516  cmp     [rbx+70h], r12b
0x18002a51a  mov     al, 1
0x18002a51c  jz      short loc_18002A521
0x18002a51e  mov     al, r12b
0x18002a521  mov     rcx, [rbp+5Fh]; this
0x18002a525  lea     rdx, aInvalidRegistr; "Invalid registry definition. Cannot cre"...
0x18002a52c  mov     qword ptr [rsp+120h+CreateOptions], rdx; bool
0x18002a531  mov     byte ptr [rsp+120h+Class], al; int
0x18002a535  mov     r9d, 80070057h; char *
0x18002a53b  mov     r8, rsi; unsigned int
0x18002a53e  mov     edx, 2AEh; void *
0x18002a543  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002a548  mov     rdx, r13; struct Schema::Containers::Definition::RegistryMakeKey *
0x18002a54b  mov     rcx, rbx; this
0x18002a54e  call    ?SetupMakeKey@RegistryProvider@container@@YAXAEBURegistryMakeKey@Definition@Containers@Schema@@PEAX@Z; container::RegistryProvider::SetupMakeKey(Schema::Containers::Definition::RegistryMakeKey const &,void *)
0x18002a553  add     rbx, 78h ; 'x'
0x18002a557  cmp     rbx, r15
0x18002a55a  jnz     short loc_18002A510
0x18002a55c  mov     rbx, [rdi+58h]
0x18002a560  mov     rax, [rdi+60h]
0x18002a564  mov     [rbp+57h+var_C8], rax
0x18002a568  cmp     rbx, rax
0x18002a56b  jz      loc_18002A6C9
0x18002a571  mov     dword ptr [rsp+120h+hObject], r12d
0x18002a576  cmp     [rbx+90h], r12b
0x18002a57d  jz      short loc_18002A5AA
0x18002a57f  mov     r15, [rbx+78h]
0x18002a583  mov     rdi, [rbx+80h]
0x18002a58a  sub     rdi, r15
0x18002a58d  mov     rcx, [rbp+5Fh]; this
0x18002a591  mov     eax, 0FFFFFFFFh
0x18002a596  cmp     rdi, rax
0x18002a599  ja      loc_18002A75F
0x18002a59f  mov     r12d, 3
0x18002a5a5  jmp     loc_18002A661
0x18002a5aa  cmp     [rbx+4Ch], r12b
0x18002a5ae  jz      short loc_18002A5C9
0x18002a5b0  mov     eax, [rbx+48h]
0x18002a5b3  mov     dword ptr [rsp+120h+hObject], eax
0x18002a5b7  lea     r15, [rsp+120h+hObject]
0x18002a5bc  mov     edi, 4
0x18002a5c1  mov     r12d, edi
0x18002a5c4  jmp     loc_18002A661
0x18002a5c9  cmp     [rbx+40h], r12b
0x18002a5cd  jz      short loc_18002A5DA
0x18002a5cf  mov     eax, 20h ; ' '
0x18002a5d4  lea     r12d, [rax-19h]
0x18002a5d8  jmp     short loc_18002A5F0
0x18002a5da  cmp     [rbx+70h], r12b
0x18002a5de  jnz     short loc_18002A5E7
0x18002a5e0  mov     ecx, 5
0x18002a5e5  int     29h; Win8: RtlFailFast(ecx)
0x18002a5e7  mov     eax, 50h ; 'P'
0x18002a5ec  lea     r12d, [rax-4Fh]
0x18002a5f0  lea     rcx, [rax+rbx]
0x18002a5f4  cmp     qword ptr [rcx+18h], 7
0x18002a5f9  jbe     short loc_18002A600
0x18002a5fb  mov     r15, [rcx]
0x18002a5fe  jmp     short loc_18002A603
0x18002a600  mov     r15, rcx
0x18002a603  mov     rcx, [rcx+10h]
0x18002a607  lea     rax, [rcx+1]
0x18002a60b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a60f  cmp     rax, rcx
0x18002a612  cmovnb  rdx, rax
0x18002a616  sbb     r9d, r9d
0x18002a619  and     r9d, 0C0000095h; char *
0x18002a620  mov     r10, [rbp+5Fh]
0x18002a624  cmp     rax, rcx
0x18002a627  jb      loc_18002A71F
0x18002a62d  mov     qword ptr [rbp+57h+DestinationString.Length], 0
0x18002a635  mov     eax, 2
0x18002a63a  mul     rdx
0x18002a63d  mov     rdi, rax
0x18002a640  test    rdx, rdx
0x18002a643  jnz     short loc_18002A64A
0x18002a645  xor     r9d, r9d
0x18002a648  jmp     short loc_18002A654
0x18002a64a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002a64e  mov     r9d, 0C0000095h; char *
0x18002a654  mov     rcx, [rbp+5Fh]; this
0x18002a658  test    r9d, r9d
0x18002a65b  js      loc_18002A711
0x18002a661  xorps   xmm0, xmm0
0x18002a664  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002a668  cmp     qword ptr [rbx+18h], 7
0x18002a66d  jbe     short loc_18002A674
0x18002a66f  mov     rdx, [rbx]
0x18002a672  jmp     short loc_18002A677
0x18002a674  mov     rdx, rbx; SourceString
0x18002a677  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002a67b  call    cs:__imp_RtlInitUnicodeString
0x18002a682  nop     dword ptr [rax+rax+00h]
0x18002a687  mov     [rsp+120h+CreateOptions], edi; DataSize
0x18002a68b  mov     [rsp+120h+Class], r15; int
0x18002a690  mov     r9d, r12d; Type
0x18002a693  xor     r8d, r8d; TitleIndex
0x18002a696  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18002a69a  mov     rcx, r13; KeyHandle
0x18002a69d  call    cs:__imp_NtSetValueKey
0x18002a6a4  nop     dword ptr [rax+rax+00h]
0x18002a6a9  mov     rcx, [rbp+5Fh]; this
0x18002a6ad  xor     r12d, r12d
0x18002a6b0  test    eax, eax
0x18002a6b2  js      loc_18002A773
0x18002a6b8  add     rbx, 98h
0x18002a6bf  cmp     rbx, [rbp+57h+var_C8]
0x18002a6c3  jnz     loc_18002A571
0x18002a6c9  test    r14, r14
0x18002a6cc  jz      short loc_18002A6D7
0x18002a6ce  mov     rcx, r14; void *
0x18002a6d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a6d6  nop
0x18002a6d7  lea     rax, [r13-1]
0x18002a6db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a6df  ja      short loc_18002A6F0
0x18002a6e1  mov     rcx, r13; hObject
0x18002a6e4  call    cs:__imp_CloseHandle
0x18002a6eb  nop     dword ptr [rax+rax+00h]
0x18002a6f0  mov     rcx, [rbp+57h+var_50]
0x18002a6f4  xor     rcx, rsp; StackCookie
0x18002a6f7  call    __security_check_cookie
0x18002a6fc  add     rsp, 0E8h
0x18002a703  pop     r15
0x18002a705  pop     r14
0x18002a707  pop     r13
0x18002a709  pop     r12
0x18002a70b  pop     rdi
0x18002a70c  pop     rsi
0x18002a70d  pop     rbx
0x18002a70e  pop     rbp
0x18002a70f  retn
0x18002a711  mov     r8, rsi; unsigned int
0x18002a714  mov     edx, 2E3h; void *
0x18002a719  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002a71f  mov     r8, rsi; unsigned int
0x18002a722  mov     edx, 2E0h; void *
0x18002a727  mov     rcx, r10; this
0x18002a72a  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002a730  mov     rcx, rdi
0x18002a733  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002a738  mov     rcx, [rbp+5Fh]; this
0x18002a73c  mov     qword ptr [rsp+120h+CreateOptions], rax; char *
0x18002a741  lea     rax, aCreatekeyWsFai; "CreateKey(%ws) failed"
0x18002a748  mov     [rsp+120h+Class], rax; int
0x18002a74d  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002a754  mov     edx, 3ECh; void *
0x18002a759  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18002a75f  mov     r9d, 80070216h; char *
0x18002a765  mov     r8, rsi; unsigned int
0x18002a768  mov     edx, 2CAh; void *
0x18002a76d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002a773  mov     r9d, eax; char *
0x18002a776  mov     r8, rsi; unsigned int
0x18002a779  mov     edx, 405h; void *
0x18002a77e  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
