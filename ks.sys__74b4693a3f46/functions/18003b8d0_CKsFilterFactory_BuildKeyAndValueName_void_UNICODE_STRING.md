# CKsFilterFactory::BuildKeyAndValueName(void * *,_UNICODE_STRING *)

- ea: `0x18003b8d0`
- end: `0x18003bb96`
- name: `?BuildKeyAndValueName@CKsFilterFactory@@QEAAJPEAPEAXPEAU_UNICODE_STRING@@@Z`
- size: `710`
- prototype: `int(CKsFilterFactory *__hidden this, void **, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003bfe0`
- `0x18003c10c`

## callees

- `0x18000abec`
- `0x18000b7bc`
- `0x18000c630`
- `0x180019fc0`
- `0x18003b8d0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18003baa5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003baa5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b9c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b9c5`
- `ntoskrnl!ZwCreateKey` at `0x18003ba14`
- `ntoskrnl!ZwCreateKey` at `0x18003ba14`
- `ntoskrnl!RtlStringFromGUID` at `0x18003babd`
- `ntoskrnl!RtlStringFromGUID` at `0x18003babd`
- `ntoskrnl!ZwClose` at `0x18003ba8b`
- `ntoskrnl!ZwClose` at `0x18003ba8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003bb37`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003bb37`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003b97e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003b97e`

## string_xrefs

- `0x18003b965`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\DeviceClasses\{24e552d7-6523-47f7-a647-d3465bf1F5ca}\ReferenceGuids`
- `0x18003b948`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\DeviceClasses\{e5323777-f976-4f5b-9b55-b94699c46e44}\ReferenceGuids`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::BuildKeyAndValueName(
        CKsFilterFactory *this,
        void **a2,
        struct _UNICODE_STRING *a3)
{
  void **v4; // r14
  wchar_t *v6; // rsi
  __int64 v7; // rcx
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
  if ( (unsigned int)IsEqualGUIDAligned(&this->m_profileGUID, &GUID_e5323777_f976_4f5b_9b55_b94699c46e44) )
  {
    v8 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\DeviceClasses\\{e5323777-f976-4f5b-9b55-b94699c46e44}\\ReferenceGuids";
  }
  else
  {
    if ( !(unsigned int)IsEqualGUIDAligned(v7, &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca) )
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
0x18003b8d0  push    rbp
0x18003b8d2  push    rbx
0x18003b8d3  push    rsi
0x18003b8d4  push    rdi
0x18003b8d5  push    r12
0x18003b8d7  push    r13
0x18003b8d9  push    r14
0x18003b8db  push    r15
0x18003b8dd  lea     rbp, [rsp-1Fh]
0x18003b8e2  sub     rsp, 88h
0x18003b8e9  xorps   xmm0, xmm0
0x18003b8ec  lea     r10, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003b8f3  xor     r12d, r12d
0x18003b8f6  mov     r15, r8
0x18003b8f9  lea     r8, WPP_RECORDER_INITIALIZED
0x18003b900  mov     r14, rdx
0x18003b903  mov     r13, rcx
0x18003b906  mov     esi, r12d
0x18003b909  mov     edi, r12d
0x18003b90c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003b910  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003b914  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003b918  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003b91c  test    rdx, rdx
0x18003b91f  jz      loc_18003BB0C
0x18003b925  test    r15, r15
0x18003b928  jz      loc_18003BB0C
0x18003b92e  mov     [rdx], r12
0x18003b931  add     rcx, 1C8h
0x18003b938  lea     rdx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x18003b93f  call    IsEqualGUIDAligned
0x18003b944  test    eax, eax
0x18003b946  jz      short loc_18003B951
0x18003b948  lea     r12, aRegistryMachin_1; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18003b94f  jmp     short loc_18003B96C
0x18003b951  lea     rdx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca
0x18003b958  call    IsEqualGUIDAligned
0x18003b95d  test    eax, eax
0x18003b95f  jz      loc_18003BAD8
0x18003b965  lea     r12, aRegistryMachin_2; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18003b96c  mov     esi, 0F0h
0x18003b971  mov     r8d, 6670534Bh; Tag
0x18003b977  mov     edx, esi; NumberOfBytes
0x18003b979  mov     ecx, 401h; PoolType
0x18003b97e  call    cs:__imp_ExAllocatePoolWithTag
0x18003b985  nop     dword ptr [rax+rax+00h]
0x18003b98a  cmp     cs:ExPoolZeroingNativelySupported, dil
0x18003b991  mov     rbx, rax
0x18003b994  jnz     loc_18003BA68
0x18003b99a  test    rax, rax
0x18003b99d  jz      loc_18003BA68
0x18003b9a3  mov     r8d, esi; Size
0x18003b9a6  xor     edx, edx; Val
0x18003b9a8  mov     rcx, rax; void *
0x18003b9ab  call    memset
0x18003b9b0  mov     rsi, rbx
0x18003b9b3  mov     rdx, r12; SourceString
0x18003b9b6  mov     dword ptr [rbp+57h+DestinationString.Length], 0F00000h
0x18003b9bd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003b9c1  mov     [rbp+57h+DestinationString.Buffer], rbx
0x18003b9c5  call    cs:__imp_RtlInitUnicodeString
0x18003b9cc  nop     dword ptr [rax+rax+00h]
0x18003b9d1  xor     r12d, r12d
0x18003b9d4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003b9db  mov     [rsp+0C0h+Disposition], r12; Disposition
0x18003b9e0  lea     rax, [rbp+57h+DestinationString]
0x18003b9e4  xorps   xmm0, xmm0
0x18003b9e7  mov     dword ptr [rsp+0C0h+CreateOptions], r12d; CreateOptions
0x18003b9ec  xor     r9d, r9d; TitleIndex
0x18003b9ef  mov     [rsp+0C0h+Class], r12; Class
0x18003b9f4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003b9f8  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18003b9fc  mov     edx, 0F003Fh; DesiredAccess
0x18003ba01  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003ba08  mov     rcx, r14; KeyHandle
0x18003ba0b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003ba0f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ba14  call    cs:__imp_ZwCreateKey
0x18003ba1b  nop     dword ptr [rax+rax+00h]
0x18003ba20  mov     ebx, eax
0x18003ba22  test    eax, eax
0x18003ba24  jns     loc_18003BAB3
0x18003ba2a  lea     r13, WPP_RECORDER_INITIALIZED
0x18003ba31  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003ba38  jz      short loc_18003BA83
0x18003ba3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba41  lea     r9d, [r12+2Fh]
0x18003ba46  mov     dword ptr [rsp+0C0h+CreateOptions], eax
0x18003ba4a  lea     r8d, [r12+1]
0x18003ba4f  lea     rax, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003ba56  mov     dl, 2
0x18003ba58  mov     [rsp+0C0h+Class], rax
0x18003ba5d  mov     rcx, [rcx+40h]
0x18003ba61  call    WPP_RECORDER_SF_D
0x18003ba66  jmp     short loc_18003BA83
0x18003ba68  mov     rsi, rbx
0x18003ba6b  test    rbx, rbx
0x18003ba6e  jnz     loc_18003B9B3
0x18003ba74  mov     ebx, 0C000009Ah
0x18003ba79  xor     r12d, r12d
0x18003ba7c  lea     r13, WPP_RECORDER_INITIALIZED
0x18003ba83  mov     rcx, [r14]; Handle
0x18003ba86  test    rcx, rcx
0x18003ba89  jz      short loc_18003BA9A
0x18003ba8b  call    cs:__imp_ZwClose
0x18003ba92  nop     dword ptr [rax+rax+00h]
0x18003ba97  mov     [r14], r12
0x18003ba9a  test    edi, edi
0x18003ba9c  jz      loc_18003BB2D
0x18003baa2  mov     rcx, r15; UnicodeString
0x18003baa5  call    cs:__imp_RtlFreeUnicodeString
0x18003baac  nop     dword ptr [rax+rax+00h]
0x18003bab1  jmp     short loc_18003BB2D
0x18003bab3  lea     rcx, [r13+1ACh]; Guid
0x18003baba  mov     rdx, r15; GuidString
0x18003babd  call    cs:__imp_RtlStringFromGUID
0x18003bac4  nop     dword ptr [rax+rax+00h]
0x18003bac9  mov     edi, eax
0x18003bacb  mov     ebx, eax
0x18003bacd  test    eax, eax
0x18003bacf  jns     short loc_18003BB26
0x18003bad1  not     edi
0x18003bad3  shr     edi, 1Fh
0x18003bad6  jmp     short loc_18003BB11
0x18003bad8  mov     ebx, 0C00000BBh
0x18003badd  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18003bae4  jz      short loc_18003BA7C
0x18003bae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003baed  mov     r9d, 2Eh ; '.'
0x18003baf3  mov     dl, 2
0x18003baf5  mov     [rsp+0C0h+Class], r10
0x18003bafa  mov     rcx, [rcx+40h]
0x18003bafe  lea     r8d, [r9-2Dh]
0x18003bb02  call    WPP_RECORDER_SF_
0x18003bb07  jmp     loc_18003BA7C
0x18003bb0c  mov     ebx, 0C000000Dh
0x18003bb11  lea     r13, WPP_RECORDER_INITIALIZED
0x18003bb18  test    r14, r14
0x18003bb1b  jz      loc_18003BA9A
0x18003bb21  jmp     loc_18003BA83
0x18003bb26  lea     r13, WPP_RECORDER_INITIALIZED
0x18003bb2d  test    rsi, rsi
0x18003bb30  jz      short loc_18003BB43
0x18003bb32  xor     edx, edx; Tag
0x18003bb34  mov     rcx, rsi; P
0x18003bb37  call    cs:__imp_ExFreePoolWithTag
0x18003bb3e  nop     dword ptr [rax+rax+00h]
0x18003bb43  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003bb4a  jz      short loc_18003BB7F
0x18003bb4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb53  cmp     [rcx+48h], r12w
0x18003bb58  jz      short loc_18003BB7F
0x18003bb5a  mov     rcx, [rcx+40h]
0x18003bb5e  lea     rax, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003bb65  mov     r9d, 30h ; '0'
0x18003bb6b  mov     dword ptr [rsp+0C0h+CreateOptions], ebx
0x18003bb6f  mov     dl, 5
0x18003bb71  mov     [rsp+0C0h+Class], rax
0x18003bb76  lea     r8d, [r9-2Fh]
0x18003bb7a  call    WPP_RECORDER_SF_D
0x18003bb7f  mov     eax, ebx
0x18003bb81  add     rsp, 88h
0x18003bb88  pop     r15
0x18003bb8a  pop     r14
0x18003bb8c  pop     r13
0x18003bb8e  pop     r12
0x18003bb90  pop     rdi
0x18003bb91  pop     rsi
0x18003bb92  pop     rbx
0x18003bb93  pop     rbp
0x18003bb94  retn
```
