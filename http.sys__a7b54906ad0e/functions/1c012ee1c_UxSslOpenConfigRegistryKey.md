# UxSslOpenConfigRegistryKey

- ea: `0x1c012ee1c`
- end: `0x1c012f010`
- name: `UxSslOpenConfigRegistryKey`
- size: `500`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1c012bd64`
- `0x1c012c04c`
- `0x1c012f0b0`

## callees

- `0x1c001b610`
- `0x1c008f21c`
- `0x1c008f570`
- `0x1c008fd84`
- `0x1c012ee1c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1c012ef28`
- `ntoskrnl!ZwOpenKey` at `0x1c012ef28`
- `ntoskrnl!ZwCreateKey` at `0x1c012efc1`
- `ntoskrnl!ZwCreateKey` at `0x1c012efc1`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1c012eede`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1c012eede`
- `ntoskrnl!ZwClose` at `0x1c012ef60`
- `ntoskrnl!ZwClose` at `0x1c012ef60`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c012ee96`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c012ee96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c012ef4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c012ef4b`

## pseudocode

```c
__int64 __fastcall UxSslOpenConfigRegistryKey(__int64 a1, unsigned int a2, _QWORD *a3)
{
  WCHAR *PoolWithTagPriority; // rax
  WCHAR *v7; // r14
  NTSTATUS inited; // ebx
  void *v9; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Disposition; // [rsp+B0h] [rbp+30h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp+38h] BYREF

  KeyHandle = 0;
  Disposition = 0;
  *a3 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000) != 0 )
    WPP_SF_qdP(135, WPP_2d1f4381eaea39064c91b1a674619a5b_Traceguids, a1, a2);
  PoolWithTagPriority = (WCHAR *)ExAllocatePoolWithTagPriority(PagedPool, 0x208u, 0x53556C55u, LowPoolPriority);
  v7 = PoolWithTagPriority;
  if ( !PoolWithTagPriority )
  {
    inited = -1073741670;
    goto LABEL_11;
  }
  inited = (*(__int64 (__fastcall **)(__int64, WCHAR *, __int64))(*(_QWORD *)(a1 + 416) + 88LL))(
             a1,
             PoolWithTagPriority,
             520);
  if ( inited >= 0 )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, v7);
    if ( inited >= 0 )
    {
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( a2 )
      {
        inited = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( inited < 0 )
          goto LABEL_10;
        if ( a2 == 1 && Disposition != 1 )
        {
          if ( (WPP_MAIN_CB.DeviceType & 0x10000) != 0 )
            WPP_SF_(136, WPP_2d1f4381eaea39064c91b1a674619a5b_Traceguids);
          inited = -1073741771;
          goto LABEL_10;
        }
        goto LABEL_9;
      }
      inited = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
      if ( inited >= 0 )
      {
LABEL_9:
        v9 = KeyHandle;
        KeyHandle = 0;
        *a3 = v9;
      }
    }
  }
LABEL_10:
  ExFreePoolWithTag(v7, 0);
LABEL_11:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000) != 0 )
    WPP_SF_qD(137, WPP_2d1f4381eaea39064c91b1a674619a5b_Traceguids, a3, (unsigned int)inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1c012ee1c  mov     [rsp-18h+arg_0], rbx
0x1c012ee21  mov     [rsp-18h+arg_8], rsi
0x1c012ee26  push    rbp
0x1c012ee27  push    rdi
0x1c012ee28  push    r14
0x1c012ee2a  mov     rbp, rsp
0x1c012ee2d  sub     rsp, 80h
0x1c012ee34  and     [rbp+KeyHandle], 0
0x1c012ee39  xorps   xmm0, xmm0
0x1c012ee3c  and     [rbp+arg_10], 0
0x1c012ee40  mov     rdi, r8
0x1c012ee43  and     qword ptr [r8], 0
0x1c012ee47  mov     esi, edx
0x1c012ee49  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1c012ee4d  mov     rbx, rcx
0x1c012ee50  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1c012ee54  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1c012ee58  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1c012ee5c  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000h
0x1c012ee66  jz      short loc_1C012EE84
0x1c012ee68  mov     [rsp+80h+Class], r8; Class
0x1c012ee6d  mov     r9d, edx
0x1c012ee70  mov     r8, rbx
0x1c012ee73  lea     rdx, WPP_2d1f4381eaea39064c91b1a674619a5b_Traceguids
0x1c012ee7a  mov     ecx, 87h
0x1c012ee7f  call    WPP_SF_qdP
0x1c012ee84  xor     r9d, r9d; Priority
0x1c012ee87  mov     edx, 208h; NumberOfBytes
0x1c012ee8c  mov     r8d, 53556C55h; Tag
0x1c012ee92  lea     ecx, [r9+1]; PoolType
0x1c012ee96  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c012ee9d  nop     dword ptr [rax+rax+00h]
0x1c012eea2  mov     r14, rax
0x1c012eea5  test    rax, rax
0x1c012eea8  jnz     short loc_1C012EEB4
0x1c012eeaa  mov     ebx, 0C000009Ah
0x1c012eeaf  jmp     loc_1C012EF57
0x1c012eeb4  mov     rax, [rbx+1A0h]
0x1c012eebb  mov     r8d, 208h
0x1c012eec1  mov     rdx, r14
0x1c012eec4  mov     rcx, rbx
0x1c012eec7  mov     rax, [rax+58h]
0x1c012eecb  call    cs:__guard_dispatch_icall_fptr
0x1c012eed1  mov     ebx, eax
0x1c012eed3  test    eax, eax
0x1c012eed5  js      short loc_1C012EF46
0x1c012eed7  mov     rdx, r14; SourceString
0x1c012eeda  lea     rcx, [rbp+DestinationString]; DestinationString
0x1c012eede  call    cs:__imp_RtlInitUnicodeStringEx
0x1c012eee5  nop     dword ptr [rax+rax+00h]
0x1c012eeea  mov     ebx, eax
0x1c012eeec  test    eax, eax
0x1c012eeee  js      short loc_1C012EF46
0x1c012eef0  and     [rbp+ObjectAttributes.RootDirectory], 0
0x1c012eef5  lea     rax, [rbp+DestinationString]
0x1c012eef9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1c012ef00  xorps   xmm0, xmm0
0x1c012ef03  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1c012ef0a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1c012ef0e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1c012ef12  mov     edx, 0F003Fh; DesiredAccess
0x1c012ef17  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1c012ef1b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1c012ef20  test    esi, esi
0x1c012ef22  jnz     loc_1C012EFAA
0x1c012ef28  call    cs:__imp_ZwOpenKey
0x1c012ef2f  nop     dword ptr [rax+rax+00h]
0x1c012ef34  mov     ebx, eax
0x1c012ef36  test    eax, eax
0x1c012ef38  js      short loc_1C012EF46
0x1c012ef3a  mov     rax, [rbp+KeyHandle]
0x1c012ef3e  and     [rbp+KeyHandle], 0
0x1c012ef43  mov     [rdi], rax
0x1c012ef46  xor     edx, edx; Tag
0x1c012ef48  mov     rcx, r14; P
0x1c012ef4b  call    cs:__imp_ExFreePoolWithTag
0x1c012ef52  nop     dword ptr [rax+rax+00h]
0x1c012ef57  mov     rcx, [rbp+KeyHandle]; Handle
0x1c012ef5b  test    rcx, rcx
0x1c012ef5e  jz      short loc_1C012EF6C
0x1c012ef60  call    cs:__imp_ZwClose
0x1c012ef67  nop     dword ptr [rax+rax+00h]
0x1c012ef6c  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000h
0x1c012ef76  jz      short loc_1C012EF8F
0x1c012ef78  mov     ecx, 89h
0x1c012ef7d  lea     rdx, WPP_2d1f4381eaea39064c91b1a674619a5b_Traceguids
0x1c012ef84  mov     r9d, ebx
0x1c012ef87  mov     r8, rdi
0x1c012ef8a  call    WPP_SF_qD
0x1c012ef8f  lea     r11, [rsp+80h+var_s0]
0x1c012ef97  mov     eax, ebx
0x1c012ef99  mov     rbx, [r11+20h]
0x1c012ef9d  mov     rsi, [r11+28h]
0x1c012efa1  mov     rsp, r11
0x1c012efa4  pop     r14
0x1c012efa6  pop     rdi
0x1c012efa7  pop     rbp
0x1c012efa8  retn
0x1c012efaa  lea     rax, [rbp+arg_10]
0x1c012efae  xor     r9d, r9d; TitleIndex
0x1c012efb1  mov     [rsp+80h+Disposition], rax; Disposition
0x1c012efb6  and     [rsp+80h+var_58], 0
0x1c012efbb  and     [rsp+80h+Class], 0
0x1c012efc1  call    cs:__imp_ZwCreateKey
0x1c012efc8  nop     dword ptr [rax+rax+00h]
0x1c012efcd  mov     ebx, eax
0x1c012efcf  test    eax, eax
0x1c012efd1  js      loc_1C012EF46
0x1c012efd7  cmp     esi, 1
0x1c012efda  jnz     loc_1C012EF3A
0x1c012efe0  cmp     [rbp+arg_10], esi
0x1c012efe3  jz      loc_1C012EF3A
0x1c012efe9  test    cs:WPP_MAIN_CB.DeviceType, 10000h
0x1c012eff3  jz      short loc_1C012F006
0x1c012eff5  mov     ecx, 88h
0x1c012effa  lea     rdx, WPP_2d1f4381eaea39064c91b1a674619a5b_Traceguids
0x1c012f001  call    WPP_SF_
0x1c012f006  mov     ebx, 0C0000035h
0x1c012f00b  jmp     loc_1C012EF46
```
