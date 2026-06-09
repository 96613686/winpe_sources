# container_runtime::CreateContainerObject(void *,Schema::Containers::Definition::Container const &,bool)

- ea: `0x1800063f0`
- end: `0x1800065d2`
- name: `?CreateContainerObject@container_runtime@@YAXPEAXAEBUContainer@Definition@Containers@Schema@@_N@Z`
- size: `482`
- prototype: `void __fastcall(container_runtime *this, char *, const struct Schema::Containers::Definition::Container *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000db40`

## callees

- `0x180001008`
- `0x1800063f0`
- `0x18000895c`
- `0x180009984`
- `0x180009a58`
- `0x18000b4bc`
- `0x180024a84`
- `0x1800252d0`
- `0x180025aa8`
- `0x18002605c`
- `0x1800263f4`
- `0x180026e7c`
- `0x180029a1c`

## import_xrefs

- `ntdll!NtAssignProcessToJobObject` at `0x180006498`
- `ntdll!NtAssignProcessToJobObject` at `0x180006498`

## pseudocode

```c
void __fastcall container_runtime::CreateContainerObject(
        container_runtime *this,
        char *a2,
        const struct Schema::Containers::Definition::Container *a3)
{
  char v3; // bl
  void *v5; // rdx
  void *v6; // r8
  void *v7; // r9
  void *v8; // rdx
  const struct _tlgProvider_t *v9; // rax
  const wchar_t *v10; // rcx
  char *v11; // rdx
  _BYTE *v12; // rbx
  NTSTATUS v13; // eax
  const struct _tlgProvider_t *v14; // rax
  int v15; // [rsp+20h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  const wchar_t *v18; // [rsp+A8h] [rbp+28h] BYREF
  int v19; // [rsp+B0h] [rbp+30h] BYREF

  v3 = (char)a3;
  container::JobProvider::Setup(a2, this);
  if ( v3 )
  {
    if ( container_runtime::RegisterWithDam(this, v5) )
    {
      v9 = ContainerProvider::Provider();
      if ( *(_DWORD *)v9 > 5u )
      {
        v10 = L"DAM";
        v11 = (char *)&unk_18003AA28;
LABEL_7:
        v18 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v9,
          (_DWORD)v11,
          (_DWORD)v6,
          (_DWORD)v7,
          (__int64)&v18);
      }
    }
    else
    {
      container_runtime::RegisterWithSm(this, v8);
      v9 = ContainerProvider::Provider();
      if ( *(_DWORD *)v9 > 5u )
      {
        v10 = L"SMSS";
        v11 = byte_18003ADC3;
        goto LABEL_7;
      }
    }
    v12 = a2 + 312;
    goto LABEL_13;
  }
  v12 = a2 + 312;
  if ( !a2[312] )
    goto LABEL_15;
  v13 = NtAssignProcessToJobObject(this, (HANDLE)0xFFFFFFFFFFFFFFF9LL);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x1C8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime.cpp",
      (const char *)(unsigned int)v13,
      v15);
  v14 = ContainerProvider::Provider();
  if ( *(_DWORD *)v14 > 5u )
  {
    v18 = L"Self";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v14,
      (unsigned int)byte_18003ADC3,
      (_DWORD)v6,
      (_DWORD)v7,
      (__int64)&v18);
  }
LABEL_13:
  if ( *v12 )
    container::ObjectManagerProvider::Setup((container::ObjectManagerProvider *)(a2 + 256), this, v6);
LABEL_15:
  if ( a2[184] )
  {
    v19 = 0;
    container::FilesystemProvider::Setup(
      (container::FilesystemProvider *)(a2 + 96),
      (const struct Schema::Containers::Definition::FilesystemNamespace *)&v19,
      this,
      v7);
  }
  if ( a2[392] )
    container::RegistryProvider::Setup((container::RegistryProvider *)(a2 + 320), this, v6);
  if ( a2[432] && *((_QWORD *)a2 + 52) )
    container::NetworkProvider::SetupCompartment(a2 + 400, this);
  if ( a2[216] )
    container::MountManagerProvider::Setup((container::MountManagerProvider *)(a2 + 192), this, v6);
  if ( a2[248] )
    container::NamedPipeProvider::Setup((container::NamedPipeProvider *)(a2 + 224), this, v6);
}

```

## disassembly

```asm
0x1800063f0  mov     [rsp-18h+JobHandle], rcx
0x1800063f5  push    rbp
0x1800063f6  push    rbx
0x1800063f7  push    rdi
0x1800063f8  mov     rbp, rsp
0x1800063fb  sub     rsp, 80h
0x180006402  mov     bl, r8b
0x180006405  mov     rdi, rdx
0x180006408  mov     rdx, rcx
0x18000640b  mov     rcx, rdi
0x18000640e  call    ?Setup@JobProvider@container@@YAXAEBU?$optional@UJobNamespace@Definition@Containers@Schema@@@vmstd@@PEAX@Z; container::JobProvider::Setup(vmstd::optional<Schema::Containers::Definition::JobNamespace> const &,void *)
0x180006413  test    bl, bl
0x180006415  jz      short loc_180006481
0x180006417  mov     rcx, [rbp+JobHandle]; this
0x18000641b  call    ?RegisterWithDam@container_runtime@@YA_NPEAX@Z; container_runtime::RegisterWithDam(void *)
0x180006420  test    al, al
0x180006422  jz      short loc_180006440
0x180006424  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180006429  mov     ecx, [rax]
0x18000642b  cmp     ecx, 5
0x18000642e  jbe     short loc_180006478
0x180006430  lea     rcx, aDam; "DAM"
0x180006437  lea     rdx, unk_18003AA28
0x18000643e  jmp     short loc_180006463
0x180006440  mov     rcx, [rbp+JobHandle]; this
0x180006444  call    ?RegisterWithSm@container_runtime@@YAXPEAX@Z; container_runtime::RegisterWithSm(void *)
0x180006449  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000644e  mov     ecx, [rax]
0x180006450  cmp     ecx, 5
0x180006453  jbe     short loc_180006478
0x180006455  lea     rcx, aSmss; "SMSS"
0x18000645c  lea     rdx, byte_18003ADC3
0x180006463  mov     [rbp+arg_8], rcx
0x180006467  lea     rcx, [rbp+arg_8]
0x18000646b  mov     qword ptr [rsp+80h+var_60], rcx
0x180006470  mov     rcx, rax
0x180006473  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180006478  lea     rbx, [rdi+138h]
0x18000647f  jmp     short loc_1800064DF
0x180006481  lea     rbx, [rdi+138h]
0x180006488  cmp     byte ptr [rbx], 0
0x18000648b  jz      short loc_1800064F4
0x18000648d  mov     rdx, 0FFFFFFFFFFFFFFF9h; ProcessHandle
0x180006494  mov     rcx, [rbp+JobHandle]; JobHandle
0x180006498  call    cs:__imp_NtAssignProcessToJobObject
0x18000649f  nop     dword ptr [rax+rax+00h]
0x1800064a4  mov     rcx, [rbp+18h]; this
0x1800064a8  test    eax, eax
0x1800064aa  js      loc_1800065BD
0x1800064b0  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x1800064b5  mov     ecx, [rax]
0x1800064b7  cmp     ecx, 5
0x1800064ba  jbe     short loc_1800064DF
0x1800064bc  lea     rcx, aSelf; "Self"
0x1800064c3  mov     [rbp+arg_8], rcx
0x1800064c7  lea     rcx, [rbp+arg_8]
0x1800064cb  mov     qword ptr [rsp+80h+var_60], rcx
0x1800064d0  lea     rdx, byte_18003ADC3
0x1800064d7  mov     rcx, rax
0x1800064da  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800064df  cmp     byte ptr [rbx], 0
0x1800064e2  jz      short loc_1800064F4
0x1800064e4  lea     rcx, [rdi+100h]; this
0x1800064eb  mov     rdx, [rbp+JobHandle]; struct Schema::Containers::Definition::ObjectNamespace *
0x1800064ef  call    ?Setup@ObjectManagerProvider@container@@YAXAEBUObjectNamespace@Definition@Containers@Schema@@PEAX@Z; container::ObjectManagerProvider::Setup(Schema::Containers::Definition::ObjectNamespace const &,void *)
0x1800064f4  cmp     byte ptr [rdi+0B8h], 0
0x1800064fb  jz      short loc_180006515
0x1800064fd  mov     [rbp+arg_10], 0
0x180006504  lea     rcx, [rdi+60h]; this
0x180006508  mov     r8, [rbp+JobHandle]; enum _WC_FILESYSTEM_PROVIDER *
0x18000650c  lea     rdx, [rbp+arg_10]; struct Schema::Containers::Definition::FilesystemNamespace *
0x180006510  call    ?Setup@FilesystemProvider@container@@YAXAEBUFilesystemNamespace@Definition@Containers@Schema@@AEBW4_WC_FILESYSTEM_PROVIDER@@PEAX@Z; container::FilesystemProvider::Setup(Schema::Containers::Definition::FilesystemNamespace const &,_WC_FILESYSTEM_PROVIDER const &,void *)
0x180006515  mov     [rbp+var_50], rdi
0x180006519  lea     rax, [rbp+JobHandle]
0x18000651d  mov     [rbp+var_48], rax
0x180006521  mov     [rbp+var_40], 1
0x180006525  cmp     byte ptr [rdi+188h], 0
0x18000652c  jz      short loc_18000653E
0x18000652e  lea     rcx, [rdi+140h]; this
0x180006535  mov     rdx, [rbp+JobHandle]; struct Schema::Containers::Definition::RegistryNamespace *
0x180006539  call    ?Setup@RegistryProvider@container@@YAXAEBURegistryNamespace@Definition@Containers@Schema@@PEAX@Z; container::RegistryProvider::Setup(Schema::Containers::Definition::RegistryNamespace const &,void *)
0x18000653e  mov     [rbp+var_38], rdi
0x180006542  lea     rax, [rbp+JobHandle]
0x180006546  mov     [rbp+var_30], rax
0x18000654a  mov     [rbp+var_28], 1
0x18000654e  cmp     byte ptr [rdi+1B0h], 0
0x180006555  jz      short loc_18000656E
0x180006557  lea     rcx, [rdi+190h]
0x18000655e  cmp     qword ptr [rcx+10h], 0
0x180006563  jz      short loc_18000656E
0x180006565  mov     rdx, [rbp+JobHandle]
0x180006569  call    ?SetupCompartment@NetworkProvider@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; container::NetworkProvider::SetupCompartment(std::wstring const &,void *)
0x18000656e  mov     [rbp+var_20], rdi
0x180006572  lea     rax, [rbp+JobHandle]
0x180006576  mov     [rbp+var_18], rax
0x18000657a  mov     [rbp+var_10], 1
0x18000657e  cmp     byte ptr [rdi+0D8h], 0
0x180006585  jz      short loc_180006597
0x180006587  lea     rcx, [rdi+0C0h]; this
0x18000658e  mov     rdx, [rbp+JobHandle]; struct Schema::Containers::Definition::MountManagerNamespace *
0x180006592  call    ?Setup@MountManagerProvider@container@@YAXAEBUMountManagerNamespace@Definition@Containers@Schema@@PEAX@Z; container::MountManagerProvider::Setup(Schema::Containers::Definition::MountManagerNamespace const &,void *)
0x180006597  cmp     byte ptr [rdi+0F8h], 0
0x18000659e  jz      short loc_1800065B1
0x1800065a0  lea     rcx, [rdi+0E0h]; this
0x1800065a7  mov     rdx, [rbp+JobHandle]; struct Schema::Containers::Definition::NamedPipeNamespace *
0x1800065ab  call    ?Setup@NamedPipeProvider@container@@YAXAEBUNamedPipeNamespace@Definition@Containers@Schema@@PEAX@Z; container::NamedPipeProvider::Setup(Schema::Containers::Definition::NamedPipeNamespace const &,void *)
0x1800065b0  nop
0x1800065b1  add     rsp, 80h
0x1800065b8  pop     rdi
0x1800065b9  pop     rbx
0x1800065ba  pop     rbp
0x1800065bb  retn
0x1800065bd  mov     r9d, eax; char *
0x1800065c0  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\container"...
0x1800065c7  mov     edx, 1C8h; void *
0x1800065cc  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
