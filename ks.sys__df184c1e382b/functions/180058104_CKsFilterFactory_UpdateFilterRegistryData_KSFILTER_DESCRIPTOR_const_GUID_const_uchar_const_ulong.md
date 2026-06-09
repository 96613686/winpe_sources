# CKsFilterFactory::UpdateFilterRegistryData(_KSFILTER_DESCRIPTOR const *,_GUID const *,uchar * const,ulong)

- ea: `0x180058104`
- end: `0x1800583ec`
- name: `?UpdateFilterRegistryData@CKsFilterFactory@@QEAAJPEBU_KSFILTER_DESCRIPTOR@@PEBU_GUID@@QEAEK@Z`
- size: `744`
- prototype: `__int64 __fastcall(CKsFilterFactory *this, const struct _KSFILTER_DESCRIPTOR *, struct _GUID *, unsigned __int8 *const, ULONG)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180057eac`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c630`
- `0x180058104`
- `0x1800583f4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800581e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800581e3`
- `ntoskrnl!ZwClose` at `0x180058234`
- `ntoskrnl!ZwClose` at `0x180058234`
- `ntoskrnl!ZwSetValueKey` at `0x18005820e`
- `ntoskrnl!ZwSetValueKey` at `0x18005820e`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800581b9`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800581b9`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::UpdateFilterRegistryData(
        CKsFilterFactory *this,
        const struct _KSFILTER_DESCRIPTOR *a2,
        struct _GUID *a3,
        unsigned __int8 *const a4,
        ULONG a5)
{
  const struct _KSFILTER_DESCRIPTOR *v7; // rbp
  ULONG v9; // esi
  _LIST_ENTRY *p_m_DeviceClasses; // r9
  struct _LIST_ENTRY *i; // r8
  __int64 v12; // r8
  UNICODE_STRING *v13; // rdi
  NTSTATUS v14; // eax
  unsigned int v15; // ebx
  NTSTATUS v16; // eax
  int v17; // edx
  PDEVICE_OBJECT v19; // rcx
  int v20; // r9d
  __int64 DataSize; // [rsp+28h] [rbp-60h]
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF
  void *DeviceInterfaceRegKey; // [rsp+98h] [rbp+10h] BYREF

  v7 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      36,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids);
  }
  if ( v7 && a3 && a4 && (v9 = a5) != 0 )
  {
    p_m_DeviceClasses = &this->m_DeviceClasses;
    for ( i = this->m_DeviceClasses.Flink; ; i = *(struct _LIST_ENTRY **)v12 )
    {
      if ( i == p_m_DeviceClasses )
        goto LABEL_27;
      if ( IsEqualGUIDAligned(&i[1].Flink->Flink, a3) )
        break;
    }
    if ( v12 )
    {
      v13 = (UNICODE_STRING *)(v12 + 24);
      DeviceInterfaceRegKey = 0;
      v14 = IoOpenDeviceInterfaceRegistryKey((PUNICODE_STRING)(v12 + 24), 0x1F0000u, &DeviceInterfaceRegKey);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v15;
        v19 = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v20 = 40;
          goto LABEL_23;
        }
      }
      else
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"FilterData");
        v16 = ZwSetValueKey(DeviceInterfaceRegKey, &DestinationString, 0, 3u, a4, v9);
        v15 = v16;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LODWORD(DataSize) = v16;
          LOBYTE(v17) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            1,
            39,
            (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
            DataSize);
        }
        ZwClose(DeviceInterfaceRegKey);
        if ( (v15 & 0x80000000) == 0 )
        {
          v14 = KspCacheAllFilterPinMediums(v13);
          v15 = v14;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v15;
          v19 = WPP_GLOBAL_Control;
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            v20 = 41;
LABEL_23:
            LODWORD(DataSize) = v14;
            LOBYTE(a2) = 5;
            WPP_RECORDER_SF_D(
              v19->DeviceExtension,
              (_DWORD)a2,
              1,
              v20,
              (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
              DataSize);
          }
        }
      }
    }
    else
    {
LABEL_27:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          38,
          (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids);
      }
      v15 = -1073741811;
    }
  }
  else
  {
    v15 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v15;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      37,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(DataSize) = v15;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      42,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
      DataSize);
  }
  return v15;
}

```

## disassembly

```asm
0x180058104  push    rbx
0x180058106  push    rbp
0x180058107  push    rsi
0x180058108  push    rdi
0x180058109  push    r12
0x18005810b  push    r13
0x18005810d  push    r14
0x18005810f  push    r15
0x180058111  sub     rsp, 48h
0x180058115  mov     r14, r9
0x180058118  mov     rbx, r8
0x18005811b  mov     rbp, rdx
0x18005811e  mov     rdi, rcx
0x180058121  xor     r15d, r15d
0x180058124  lea     r12, WPP_RECORDER_INITIALIZED
0x18005812b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180058132  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180058139  lea     r13d, [r15+1]
0x18005813d  jnz     loc_1800582BE
0x180058143  test    rbp, rbp
0x180058146  jz      loc_180058381
0x18005814c  test    rbx, rbx
0x18005814f  jz      loc_180058381
0x180058155  test    r14, r14
0x180058158  jz      loc_180058381
0x18005815e  mov     esi, [rsp+88h+arg_20]
0x180058165  test    esi, esi
0x180058167  jz      loc_18005837A
0x18005816d  lea     r9, [rdi+158h]
0x180058174  mov     r8, [r9]
0x180058177  cmp     r8, r9
0x18005817a  jz      loc_180058340
0x180058180  mov     rcx, [r8+10h]
0x180058184  mov     rdx, rbx
0x180058187  call    IsEqualGUIDAligned
0x18005818c  test    eax, eax
0x18005818e  jz      loc_1800582EE
0x180058194  test    r8, r8
0x180058197  jz      loc_180058340
0x18005819d  lea     rdi, [r8+18h]
0x1800581a1  mov     [rsp+88h+DeviceInterfaceRegKey], r15
0x1800581a9  mov     rcx, rdi; SymbolicLinkName
0x1800581ac  lea     r8, [rsp+88h+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x1800581b4  mov     edx, 1F0000h; DesiredAccess
0x1800581b9  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x1800581c0  nop     dword ptr [rax+rax+00h]
0x1800581c5  mov     ebx, eax
0x1800581c7  test    eax, eax
0x1800581c9  js      loc_180058318
0x1800581cf  xorps   xmm0, xmm0
0x1800581d2  lea     rdx, aFilterdata; "FilterData"
0x1800581d9  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800581de  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x1800581e3  call    cs:__imp_RtlInitUnicodeString
0x1800581ea  nop     dword ptr [rax+rax+00h]
0x1800581ef  mov     rcx, [rsp+88h+DeviceInterfaceRegKey]; KeyHandle
0x1800581f7  lea     rdx, [rsp+88h+DestinationString]; ValueName
0x1800581fc  mov     r9d, 3; Type
0x180058202  mov     dword ptr [rsp+88h+DataSize], esi; DataSize
0x180058206  xor     r8d, r8d; TitleIndex
0x180058209  mov     [rsp+88h+Data], r14; Data
0x18005820e  call    cs:__imp_ZwSetValueKey
0x180058215  nop     dword ptr [rax+rax+00h]
0x18005821a  mov     ebx, eax
0x18005821c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180058223  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18005822a  jnz     short loc_180058265
0x18005822c  mov     rcx, [rsp+88h+DeviceInterfaceRegKey]; Handle
0x180058234  call    cs:__imp_ZwClose
0x18005823b  nop     dword ptr [rax+rax+00h]
0x180058240  test    ebx, ebx
0x180058242  jns     short loc_180058292
0x180058244  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005824b  jnz     loc_1800583B8
0x180058251  mov     eax, ebx
0x180058253  add     rsp, 48h
0x180058257  pop     r15
0x180058259  pop     r14
0x18005825b  pop     r13
0x18005825d  pop     r12
0x18005825f  pop     rdi
0x180058260  pop     rsi
0x180058261  pop     rbp
0x180058262  pop     rbx
0x180058263  retn
0x180058265  mov     rcx, cs:WPP_GLOBAL_Control
0x18005826c  cmp     [rcx+48h], r15w
0x180058271  jz      short loc_18005822C
0x180058273  mov     rcx, [rcx+40h]
0x180058277  mov     r9d, 27h ; '''
0x18005827d  mov     dword ptr [rsp+88h+DataSize], ebx
0x180058281  mov     r8d, r13d
0x180058284  mov     dl, 5
0x180058286  mov     [rsp+88h+Data], rsi
0x18005828b  call    WPP_RECORDER_SF_D
0x180058290  jmp     short loc_18005822C
0x180058292  mov     rdx, rbp
0x180058295  mov     rcx, rdi; SymbolicLink
0x180058298  call    KspCacheAllFilterPinMediums
0x18005829d  mov     ebx, eax
0x18005829f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800582a6  jz      short loc_180058251
0x1800582a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800582af  cmp     [rcx+48h], r15w
0x1800582b4  jz      short loc_180058244
0x1800582b6  mov     r9d, 29h ; ')'
0x1800582bc  jmp     short loc_1800582FC
0x1800582be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800582c5  cmp     [rcx+48h], r15w
0x1800582ca  jz      loc_180058143
0x1800582d0  mov     rcx, [rcx+40h]
0x1800582d4  mov     r9d, 24h ; '$'
0x1800582da  mov     r8d, r13d
0x1800582dd  mov     [rsp+88h+Data], rsi
0x1800582e2  mov     dl, 5
0x1800582e4  call    WPP_RECORDER_SF_
0x1800582e9  jmp     loc_180058143
0x1800582ee  mov     r8, [r8]
0x1800582f1  jmp     loc_180058177
0x1800582f6  mov     r9d, 28h ; '('
0x1800582fc  mov     rcx, [rcx+40h]
0x180058300  mov     r8d, r13d
0x180058303  mov     dword ptr [rsp+88h+DataSize], eax
0x180058307  mov     dl, 5
0x180058309  mov     [rsp+88h+Data], rsi
0x18005830e  call    WPP_RECORDER_SF_D
0x180058313  jmp     loc_180058244
0x180058318  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005831f  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180058326  jz      loc_180058251
0x18005832c  mov     rcx, cs:WPP_GLOBAL_Control
0x180058333  cmp     [rcx+48h], r15w
0x180058338  jz      loc_180058244
0x18005833e  jmp     short loc_1800582F6
0x180058340  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180058347  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18005834e  jz      short loc_180058370
0x180058350  mov     rcx, cs:WPP_GLOBAL_Control
0x180058357  mov     r9d, 26h ; '&'
0x18005835d  mov     r8d, r13d
0x180058360  mov     [rsp+88h+Data], rsi
0x180058365  mov     dl, 4
0x180058367  mov     rcx, [rcx+40h]
0x18005836b  call    WPP_RECORDER_SF_
0x180058370  mov     ebx, 0C000000Dh
0x180058375  jmp     loc_180058244
0x18005837a  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180058381  mov     ebx, 0C000000Dh
0x180058386  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005838d  jz      loc_180058251
0x180058393  mov     rcx, cs:WPP_GLOBAL_Control
0x18005839a  mov     r9d, 25h ; '%'
0x1800583a0  mov     r8d, r13d
0x1800583a3  mov     [rsp+88h+Data], rsi
0x1800583a8  mov     dl, 4
0x1800583aa  mov     rcx, [rcx+40h]
0x1800583ae  call    WPP_RECORDER_SF_
0x1800583b3  jmp     loc_180058244
0x1800583b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800583bf  cmp     [rcx+48h], r15w
0x1800583c4  jz      loc_180058251
0x1800583ca  mov     rcx, [rcx+40h]
0x1800583ce  mov     r9d, 2Ah ; '*'
0x1800583d4  mov     dword ptr [rsp+88h+DataSize], ebx
0x1800583d8  mov     r8d, r13d
0x1800583db  mov     dl, 5
0x1800583dd  mov     [rsp+88h+Data], rsi
0x1800583e2  call    WPP_RECORDER_SF_D
0x1800583e7  jmp     loc_180058251
```
