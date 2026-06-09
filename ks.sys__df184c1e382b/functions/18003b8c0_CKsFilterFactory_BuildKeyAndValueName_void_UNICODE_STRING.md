# CKsFilterFactory::BuildKeyAndValueName(void * *,_UNICODE_STRING *)

- ea: `0x18003b8c0`
- end: `0x18003bb86`
- name: `?BuildKeyAndValueName@CKsFilterFactory@@QEAAJPEAPEAXPEAU_UNICODE_STRING@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(CKsFilterFactory *this, void **, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003bfd0`
- `0x18003c0fc`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c630`
- `0x18001a000`
- `0x18003b8c0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18003ba95`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003ba95`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b9b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b9b5`
- `ntoskrnl!ZwCreateKey` at `0x18003ba04`
- `ntoskrnl!ZwCreateKey` at `0x18003ba04`
- `ntoskrnl!RtlStringFromGUID` at `0x18003baad`
- `ntoskrnl!RtlStringFromGUID` at `0x18003baad`
- `ntoskrnl!ZwClose` at `0x18003ba7b`
- `ntoskrnl!ZwClose` at `0x18003ba7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003bb27`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003bb27`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003b96e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003b96e`

## string_xrefs

- `0x18003b955`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\DeviceClasses\{24e552d7-6523-47f7-a647-d3465bf1F5ca}\ReferenceGuids`
- `0x18003b938`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\DeviceClasses\{e5323777-f976-4f5b-9b55-b94699c46e44}\ReferenceGuids`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::BuildKeyAndValueName(
        CKsFilterFactory *this,
        void **a2,
        struct _UNICODE_STRING *a3)
{
  void **v4; // r14
  wchar_t *v6; // rsi
  _QWORD *v7; // rcx
  const WCHAR *v8; // r12
  void *v9; // r8
  __int64 v10; // r10
  wchar_t *PoolWithTag; // rax
  wchar_t *v12; // rbx
  NTSTATUS v13; // eax
  NTSTATUS v14; // ebx
  __int64 CreateOptions; // [rsp+28h] [rbp-41h]
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF

  v4 = a2;
  v6 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( !a2 || !a3 )
  {
    v14 = -1073741811;
    goto LABEL_23;
  }
  *a2 = 0;
  if ( IsEqualGUIDAligned(&this->m_profileGUID.Data1, &GUID_e5323777_f976_4f5b_9b55_b94699c46e44) )
  {
    v8 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\DeviceClasses\\{e5323777-f976-4f5b-9b55-b94699c46e44}\\ReferenceGuids";
  }
  else
  {
    if ( !IsEqualGUIDAligned(v7, &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca) )
    {
      v14 = -1073741637;
      if ( WPP_RECORDER_INITIALIZED != v9 )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)a2, 1, 46, v10);
      }
      goto LABEL_15;
    }
    v8 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\DeviceClasses\\{24e552d7-6523-47f7-a647-d3465bf1F5ca}\\ReferenceGuids";
  }
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0xF0u, 0x6670534Bu);
  v12 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
  {
    memset(PoolWithTag, 0, 0xF0u);
    v6 = v12;
LABEL_10:
    *(_DWORD *)&DestinationString.Length = 15728640;
    DestinationString.Buffer = v12;
    RtlInitUnicodeString(&DestinationString, v8);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v13 = ZwCreateKey(v4, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(CreateOptions) = v13;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          47,
          (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
          CreateOptions);
      }
      goto LABEL_15;
    }
    v14 = RtlStringFromGUID(&this->m_ReferenceGUID, a3);
    if ( v14 >= 0 )
      goto LABEL_25;
LABEL_23:
    if ( !v4 )
      goto LABEL_25;
    goto LABEL_15;
  }
  v6 = PoolWithTag;
  if ( PoolWithTag )
    goto LABEL_10;
  v14 = -1073741670;
LABEL_15:
  if ( *v4 )
  {
    ZwClose(*v4);
    *v4 = 0;
  }
LABEL_25:
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(CreateOptions) = v14;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      48,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
      CreateOptions);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003b8c0  push    rbp
0x18003b8c2  push    rbx
0x18003b8c3  push    rsi
0x18003b8c4  push    rdi
0x18003b8c5  push    r12
0x18003b8c7  push    r13
0x18003b8c9  push    r14
0x18003b8cb  push    r15
0x18003b8cd  lea     rbp, [rsp-1Fh]
0x18003b8d2  sub     rsp, 88h
0x18003b8d9  xorps   xmm0, xmm0
0x18003b8dc  lea     r10, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003b8e3  xor     r12d, r12d
0x18003b8e6  mov     r15, r8
0x18003b8e9  lea     r8, WPP_RECORDER_INITIALIZED
0x18003b8f0  mov     r14, rdx
0x18003b8f3  mov     r13, rcx
0x18003b8f6  mov     esi, r12d
0x18003b8f9  mov     edi, r12d
0x18003b8fc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003b900  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003b904  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003b908  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003b90c  test    rdx, rdx
0x18003b90f  jz      loc_18003BAFC
0x18003b915  test    r15, r15
0x18003b918  jz      loc_18003BAFC
0x18003b91e  mov     [rdx], r12
0x18003b921  add     rcx, 1C8h
0x18003b928  lea     rdx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x18003b92f  call    IsEqualGUIDAligned
0x18003b934  test    eax, eax
0x18003b936  jz      short loc_18003B941
0x18003b938  lea     r12, aRegistryMachin_1; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18003b93f  jmp     short loc_18003B95C
0x18003b941  lea     rdx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca
0x18003b948  call    IsEqualGUIDAligned
0x18003b94d  test    eax, eax
0x18003b94f  jz      loc_18003BAC8
0x18003b955  lea     r12, aRegistryMachin_2; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18003b95c  mov     esi, 0F0h
0x18003b961  mov     r8d, 6670534Bh; Tag
0x18003b967  mov     edx, esi; NumberOfBytes
0x18003b969  mov     ecx, 401h; PoolType
0x18003b96e  call    cs:__imp_ExAllocatePoolWithTag
0x18003b975  nop     dword ptr [rax+rax+00h]
0x18003b97a  cmp     cs:ExPoolZeroingNativelySupported, dil
0x18003b981  mov     rbx, rax
0x18003b984  jnz     loc_18003BA58
0x18003b98a  test    rax, rax
0x18003b98d  jz      loc_18003BA58
0x18003b993  mov     r8d, esi; Size
0x18003b996  xor     edx, edx; Val
0x18003b998  mov     rcx, rax; void *
0x18003b99b  call    memset
0x18003b9a0  mov     rsi, rbx
0x18003b9a3  mov     rdx, r12; SourceString
0x18003b9a6  mov     dword ptr [rbp+57h+DestinationString.Length], 0F00000h
0x18003b9ad  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003b9b1  mov     [rbp+57h+DestinationString.Buffer], rbx
0x18003b9b5  call    cs:__imp_RtlInitUnicodeString
0x18003b9bc  nop     dword ptr [rax+rax+00h]
0x18003b9c1  xor     r12d, r12d
0x18003b9c4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003b9cb  mov     [rsp+0C0h+Disposition], r12; Disposition
0x18003b9d0  lea     rax, [rbp+57h+DestinationString]
0x18003b9d4  xorps   xmm0, xmm0
0x18003b9d7  mov     dword ptr [rsp+0C0h+CreateOptions], r12d; CreateOptions
0x18003b9dc  xor     r9d, r9d; TitleIndex
0x18003b9df  mov     [rsp+0C0h+Class], r12; Class
0x18003b9e4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003b9e8  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18003b9ec  mov     edx, 0F003Fh; DesiredAccess
0x18003b9f1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003b9f8  mov     rcx, r14; KeyHandle
0x18003b9fb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003b9ff  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ba04  call    cs:__imp_ZwCreateKey
0x18003ba0b  nop     dword ptr [rax+rax+00h]
0x18003ba10  mov     ebx, eax
0x18003ba12  test    eax, eax
0x18003ba14  jns     loc_18003BAA3
0x18003ba1a  lea     r13, WPP_RECORDER_INITIALIZED
0x18003ba21  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003ba28  jz      short loc_18003BA73
0x18003ba2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba31  lea     r9d, [r12+2Fh]
0x18003ba36  mov     dword ptr [rsp+0C0h+CreateOptions], eax
0x18003ba3a  lea     r8d, [r12+1]
0x18003ba3f  lea     rax, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003ba46  mov     dl, 2
0x18003ba48  mov     [rsp+0C0h+Class], rax
0x18003ba4d  mov     rcx, [rcx+40h]
0x18003ba51  call    WPP_RECORDER_SF_D
0x18003ba56  jmp     short loc_18003BA73
0x18003ba58  mov     rsi, rbx
0x18003ba5b  test    rbx, rbx
0x18003ba5e  jnz     loc_18003B9A3
0x18003ba64  mov     ebx, 0C000009Ah
0x18003ba69  xor     r12d, r12d
0x18003ba6c  lea     r13, WPP_RECORDER_INITIALIZED
0x18003ba73  mov     rcx, [r14]; Handle
0x18003ba76  test    rcx, rcx
0x18003ba79  jz      short loc_18003BA8A
0x18003ba7b  call    cs:__imp_ZwClose
0x18003ba82  nop     dword ptr [rax+rax+00h]
0x18003ba87  mov     [r14], r12
0x18003ba8a  test    edi, edi
0x18003ba8c  jz      loc_18003BB1D
0x18003ba92  mov     rcx, r15; UnicodeString
0x18003ba95  call    cs:__imp_RtlFreeUnicodeString
0x18003ba9c  nop     dword ptr [rax+rax+00h]
0x18003baa1  jmp     short loc_18003BB1D
0x18003baa3  lea     rcx, [r13+1ACh]; Guid
0x18003baaa  mov     rdx, r15; GuidString
0x18003baad  call    cs:__imp_RtlStringFromGUID
0x18003bab4  nop     dword ptr [rax+rax+00h]
0x18003bab9  mov     edi, eax
0x18003babb  mov     ebx, eax
0x18003babd  test    eax, eax
0x18003babf  jns     short loc_18003BB16
0x18003bac1  not     edi
0x18003bac3  shr     edi, 1Fh
0x18003bac6  jmp     short loc_18003BB01
0x18003bac8  mov     ebx, 0C00000BBh
0x18003bacd  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18003bad4  jz      short loc_18003BA6C
0x18003bad6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003badd  mov     r9d, 2Eh ; '.'
0x18003bae3  mov     dl, 2
0x18003bae5  mov     [rsp+0C0h+Class], r10
0x18003baea  mov     rcx, [rcx+40h]
0x18003baee  lea     r8d, [r9-2Dh]
0x18003baf2  call    WPP_RECORDER_SF_
0x18003baf7  jmp     loc_18003BA6C
0x18003bafc  mov     ebx, 0C000000Dh
0x18003bb01  lea     r13, WPP_RECORDER_INITIALIZED
0x18003bb08  test    r14, r14
0x18003bb0b  jz      loc_18003BA8A
0x18003bb11  jmp     loc_18003BA73
0x18003bb16  lea     r13, WPP_RECORDER_INITIALIZED
0x18003bb1d  test    rsi, rsi
0x18003bb20  jz      short loc_18003BB33
0x18003bb22  xor     edx, edx; Tag
0x18003bb24  mov     rcx, rsi; P
0x18003bb27  call    cs:__imp_ExFreePoolWithTag
0x18003bb2e  nop     dword ptr [rax+rax+00h]
0x18003bb33  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003bb3a  jz      short loc_18003BB6F
0x18003bb3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb43  cmp     [rcx+48h], r12w
0x18003bb48  jz      short loc_18003BB6F
0x18003bb4a  mov     rcx, [rcx+40h]
0x18003bb4e  lea     rax, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003bb55  mov     r9d, 30h ; '0'
0x18003bb5b  mov     dword ptr [rsp+0C0h+CreateOptions], ebx
0x18003bb5f  mov     dl, 5
0x18003bb61  mov     [rsp+0C0h+Class], rax
0x18003bb66  lea     r8d, [r9-2Fh]
0x18003bb6a  call    WPP_RECORDER_SF_D
0x18003bb6f  mov     eax, ebx
0x18003bb71  add     rsp, 88h
0x18003bb78  pop     r15
0x18003bb7a  pop     r14
0x18003bb7c  pop     r13
0x18003bb7e  pop     r12
0x18003bb80  pop     rdi
0x18003bb81  pop     rsi
0x18003bb82  pop     rbx
0x18003bb83  pop     rbp
0x18003bb84  retn
```
