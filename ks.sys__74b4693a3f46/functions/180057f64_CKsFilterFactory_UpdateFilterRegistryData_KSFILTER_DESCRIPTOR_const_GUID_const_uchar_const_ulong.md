# CKsFilterFactory::UpdateFilterRegistryData(_KSFILTER_DESCRIPTOR const *,_GUID const *,uchar * const,ulong)

- ea: `0x180057f64`
- end: `0x18005824c`
- name: `?UpdateFilterRegistryData@CKsFilterFactory@@QEAAJPEBU_KSFILTER_DESCRIPTOR@@PEBU_GUID@@QEAEK@Z`
- size: `744`
- prototype: `int(CKsFilterFactory *__hidden this, const struct _KSFILTER_DESCRIPTOR *, const struct _GUID *, unsigned __int8 *const, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180057d0c`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c630`
- `0x180057f64`
- `0x180058254`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180058043`
- `ntoskrnl!RtlInitUnicodeString` at `0x180058043`
- `ntoskrnl!ZwClose` at `0x180058094`
- `ntoskrnl!ZwClose` at `0x180058094`
- `ntoskrnl!ZwSetValueKey` at `0x18005806e`
- `ntoskrnl!ZwSetValueKey` at `0x18005806e`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x180058019`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x180058019`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::UpdateFilterRegistryData(
        CKsFilterFactory *this,
        const struct _KSFILTER_DESCRIPTOR *a2,
        const struct _GUID *a3,
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
      if ( (unsigned int)IsEqualGUIDAligned(i[1].Flink, a3) )
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
0x180057f64  push    rbx
0x180057f66  push    rbp
0x180057f67  push    rsi
0x180057f68  push    rdi
0x180057f69  push    r12
0x180057f6b  push    r13
0x180057f6d  push    r14
0x180057f6f  push    r15
0x180057f71  sub     rsp, 48h
0x180057f75  mov     r14, r9
0x180057f78  mov     rbx, r8
0x180057f7b  mov     rbp, rdx
0x180057f7e  mov     rdi, rcx
0x180057f81  xor     r15d, r15d
0x180057f84  lea     r12, WPP_RECORDER_INITIALIZED
0x180057f8b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180057f92  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180057f99  lea     r13d, [r15+1]
0x180057f9d  jnz     loc_18005811E
0x180057fa3  test    rbp, rbp
0x180057fa6  jz      loc_1800581E1
0x180057fac  test    rbx, rbx
0x180057faf  jz      loc_1800581E1
0x180057fb5  test    r14, r14
0x180057fb8  jz      loc_1800581E1
0x180057fbe  mov     esi, [rsp+88h+arg_20]
0x180057fc5  test    esi, esi
0x180057fc7  jz      loc_1800581DA
0x180057fcd  lea     r9, [rdi+158h]
0x180057fd4  mov     r8, [r9]
0x180057fd7  cmp     r8, r9
0x180057fda  jz      loc_1800581A0
0x180057fe0  mov     rcx, [r8+10h]
0x180057fe4  mov     rdx, rbx
0x180057fe7  call    IsEqualGUIDAligned
0x180057fec  test    eax, eax
0x180057fee  jz      loc_18005814E
0x180057ff4  test    r8, r8
0x180057ff7  jz      loc_1800581A0
0x180057ffd  lea     rdi, [r8+18h]
0x180058001  mov     [rsp+88h+DeviceInterfaceRegKey], r15
0x180058009  mov     rcx, rdi; SymbolicLinkName
0x18005800c  lea     r8, [rsp+88h+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x180058014  mov     edx, 1F0000h; DesiredAccess
0x180058019  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x180058020  nop     dword ptr [rax+rax+00h]
0x180058025  mov     ebx, eax
0x180058027  test    eax, eax
0x180058029  js      loc_180058178
0x18005802f  xorps   xmm0, xmm0
0x180058032  lea     rdx, aFilterdata; "FilterData"
0x180058039  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18005803e  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x180058043  call    cs:__imp_RtlInitUnicodeString
0x18005804a  nop     dword ptr [rax+rax+00h]
0x18005804f  mov     rcx, [rsp+88h+DeviceInterfaceRegKey]; KeyHandle
0x180058057  lea     rdx, [rsp+88h+DestinationString]; ValueName
0x18005805c  mov     r9d, 3; Type
0x180058062  mov     dword ptr [rsp+88h+DataSize], esi; DataSize
0x180058066  xor     r8d, r8d; TitleIndex
0x180058069  mov     [rsp+88h+Data], r14; Data
0x18005806e  call    cs:__imp_ZwSetValueKey
0x180058075  nop     dword ptr [rax+rax+00h]
0x18005807a  mov     ebx, eax
0x18005807c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180058083  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18005808a  jnz     short loc_1800580C5
0x18005808c  mov     rcx, [rsp+88h+DeviceInterfaceRegKey]; Handle
0x180058094  call    cs:__imp_ZwClose
0x18005809b  nop     dword ptr [rax+rax+00h]
0x1800580a0  test    ebx, ebx
0x1800580a2  jns     short loc_1800580F2
0x1800580a4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800580ab  jnz     loc_180058218
0x1800580b1  mov     eax, ebx
0x1800580b3  add     rsp, 48h
0x1800580b7  pop     r15
0x1800580b9  pop     r14
0x1800580bb  pop     r13
0x1800580bd  pop     r12
0x1800580bf  pop     rdi
0x1800580c0  pop     rsi
0x1800580c1  pop     rbp
0x1800580c2  pop     rbx
0x1800580c3  retn
0x1800580c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580cc  cmp     [rcx+48h], r15w
0x1800580d1  jz      short loc_18005808C
0x1800580d3  mov     rcx, [rcx+40h]
0x1800580d7  mov     r9d, 27h ; '''
0x1800580dd  mov     dword ptr [rsp+88h+DataSize], ebx
0x1800580e1  mov     r8d, r13d
0x1800580e4  mov     dl, 5
0x1800580e6  mov     [rsp+88h+Data], rsi
0x1800580eb  call    WPP_RECORDER_SF_D
0x1800580f0  jmp     short loc_18005808C
0x1800580f2  mov     rdx, rbp
0x1800580f5  mov     rcx, rdi; SymbolicLink
0x1800580f8  call    KspCacheAllFilterPinMediums
0x1800580fd  mov     ebx, eax
0x1800580ff  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180058106  jz      short loc_1800580B1
0x180058108  mov     rcx, cs:WPP_GLOBAL_Control
0x18005810f  cmp     [rcx+48h], r15w
0x180058114  jz      short loc_1800580A4
0x180058116  mov     r9d, 29h ; ')'
0x18005811c  jmp     short loc_18005815C
0x18005811e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058125  cmp     [rcx+48h], r15w
0x18005812a  jz      loc_180057FA3
0x180058130  mov     rcx, [rcx+40h]
0x180058134  mov     r9d, 24h ; '$'
0x18005813a  mov     r8d, r13d
0x18005813d  mov     [rsp+88h+Data], rsi
0x180058142  mov     dl, 5
0x180058144  call    WPP_RECORDER_SF_
0x180058149  jmp     loc_180057FA3
0x18005814e  mov     r8, [r8]
0x180058151  jmp     loc_180057FD7
0x180058156  mov     r9d, 28h ; '('
0x18005815c  mov     rcx, [rcx+40h]
0x180058160  mov     r8d, r13d
0x180058163  mov     dword ptr [rsp+88h+DataSize], eax
0x180058167  mov     dl, 5
0x180058169  mov     [rsp+88h+Data], rsi
0x18005816e  call    WPP_RECORDER_SF_D
0x180058173  jmp     loc_1800580A4
0x180058178  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005817f  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x180058186  jz      loc_1800580B1
0x18005818c  mov     rcx, cs:WPP_GLOBAL_Control
0x180058193  cmp     [rcx+48h], r15w
0x180058198  jz      loc_1800580A4
0x18005819e  jmp     short loc_180058156
0x1800581a0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800581a7  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x1800581ae  jz      short loc_1800581D0
0x1800581b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800581b7  mov     r9d, 26h ; '&'
0x1800581bd  mov     r8d, r13d
0x1800581c0  mov     [rsp+88h+Data], rsi
0x1800581c5  mov     dl, 4
0x1800581c7  mov     rcx, [rcx+40h]
0x1800581cb  call    WPP_RECORDER_SF_
0x1800581d0  mov     ebx, 0C000000Dh
0x1800581d5  jmp     loc_1800580A4
0x1800581da  lea     rsi, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x1800581e1  mov     ebx, 0C000000Dh
0x1800581e6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800581ed  jz      loc_1800580B1
0x1800581f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800581fa  mov     r9d, 25h ; '%'
0x180058200  mov     r8d, r13d
0x180058203  mov     [rsp+88h+Data], rsi
0x180058208  mov     dl, 4
0x18005820a  mov     rcx, [rcx+40h]
0x18005820e  call    WPP_RECORDER_SF_
0x180058213  jmp     loc_1800580A4
0x180058218  mov     rcx, cs:WPP_GLOBAL_Control
0x18005821f  cmp     [rcx+48h], r15w
0x180058224  jz      loc_1800580B1
0x18005822a  mov     rcx, [rcx+40h]
0x18005822e  mov     r9d, 2Ah ; '*'
0x180058234  mov     dword ptr [rsp+88h+DataSize], ebx
0x180058238  mov     r8d, r13d
0x18005823b  mov     dl, 5
0x18005823d  mov     [rsp+88h+Data], rsi
0x180058242  call    WPP_RECORDER_SF_D
0x180058247  jmp     loc_1800580B1
```
