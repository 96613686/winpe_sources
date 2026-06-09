# UxpSslInitializeCcsConfigurationByRegistryIndex

- ea: `0x1c00d98a0`
- end: `0x1c00d9ab9`
- name: `UxpSslInitializeCcsConfigurationByRegistryIndex`
- size: `537`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1c0002c1c`
- `0x1c0019284`
- `0x1c001b610`
- `0x1c008f21c`
- `0x1c00d98a0`
- `0x1c00da914`
- `0x1c00da948`
- `0x1c0131208`
- `0x1c01328f0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1c00fdef4`
- `ntoskrnl!ZwOpenKey` at `0x1c00fdef4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00d9930`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00fe0a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00d9930`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00fe0a5`
- `ntoskrnl!ZwCreateKey` at `0x1c00d997d`
- `ntoskrnl!ZwCreateKey` at `0x1c00d997d`
- `ntoskrnl!ZwEnumerateKey` at `0x1c00d99e4`
- `ntoskrnl!ZwEnumerateKey` at `0x1c00d99e4`
- `ntoskrnl!ZwClose` at `0x1c00d9a1a`
- `ntoskrnl!ZwClose` at `0x1c00fdf53`
- `ntoskrnl!ZwClose` at `0x1c00fe0ba`
- `ntoskrnl!ZwClose` at `0x1c00d9a1a`
- `ntoskrnl!ZwClose` at `0x1c00fdf53`
- `ntoskrnl!ZwClose` at `0x1c00fe0ba`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d99af`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d99af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d9a3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fde81`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d9a3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fde81`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d9a7d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00fe019`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d9a7d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00fe019`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00d9a71`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00fe00d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00d9a71`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00fe00d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d98e6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d98e6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d98ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d98ca`

## string_xrefs

- `0x1c00d9900`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters\SslCcsBindingInfo`

## pseudocode

```c
__int64 __fastcall UxpSslInitializeCcsConfigurationByRegistryIndex(__int64 a1, ULONG a2)
{
  _DWORD *v4; // rbx
  int v5; // r12d
  HANDLE v6; // r14
  NTSTATUS WideString; // edi
  _DWORD *PoolWithTagPriority; // rax
  NTSTATUS v9; // eax
  int v10; // ecx
  unsigned int v12; // eax
  int v13; // eax
  __int64 v14; // r9
  int Class; // [rsp+20h] [rbp-69h]
  void *KeyHandle; // [rsp+40h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-41h] BYREF
  __int64 v18; // [rsp+50h] [rbp-39h] BYREF
  __int128 v19; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int16 v22; // [rsp+F0h] [rbp+67h] BYREF
  SIZE_T NumberOfBytes; // [rsp+100h] [rbp+77h] BYREF
  __int64 v24; // [rsp+108h] [rbp+7Fh] BYREF

  v22 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(*(_QWORD *)(a1 + 21928) + 4048LL, 0);
  KeyHandle = 0;
  Handle = 0;
  v24 = 0;
  LODWORD(NumberOfBytes) = 0;
  DestinationString = 0;
  v4 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v19 = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v5 = 0;
  v18 = 0;
  v6 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters\\SslCcsBindingInfo");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  WideString = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( WideString >= 0 )
  {
    LODWORD(NumberOfBytes) = 152;
    do
    {
      if ( v4 )
        ExFreePoolWithTag(v4, 0);
      PoolWithTagPriority = ExAllocatePoolWithTagPriority(
                              PagedPool,
                              (unsigned int)NumberOfBytes,
                              0x44526C55u,
                              LowPoolPriority);
      v4 = PoolWithTagPriority;
      if ( !PoolWithTagPriority )
      {
        WideString = -1073741670;
        goto LABEL_9;
      }
      v9 = ZwEnumerateKey(
             KeyHandle,
             a2,
             KeyBasicInformation,
             PoolWithTagPriority,
             NumberOfBytes,
             (PULONG)&NumberOfBytes);
      WideString = v9;
    }
    while ( v9 == -2147483643 || v9 == -1073741789 );
    if ( v9 >= 0 )
    {
      v12 = v4[3];
      if ( (v12 & 1) != 0 || v12 > 0xFFFE )
      {
        WideString = -1073741492;
      }
      else
      {
        *((_QWORD *)&v19 + 1) = v4 + 4;
        LOWORD(v19) = *((_WORD *)v4 + 6);
        WORD1(v19) = *((_WORD *)v4 + 6);
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v19;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        WideString = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( WideString >= 0 )
        {
          WideString = UlAllocateWideString(v4 + 4);
          if ( WideString >= 0 )
          {
            v5 = v24;
            v6 = Handle;
            v18 = v24;
            Handle = 0;
            v24 = 0;
          }
        }
      }
    }
  }
LABEL_9:
  UlFreeWideString(&v24);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  v10 = (int)Handle;
  if ( Handle )
    ZwClose(Handle);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( WideString < 0 )
  {
    if ( (WPP_MAIN_CB.DeviceType & 0x10000) != 0 )
      WPP_SF_(48, WPP_89f138b174f63fbd963e3069eb8413da_Traceguids);
    goto LABEL_18;
  }
  LOBYTE(v10) = 1;
  if ( (int)HttpStringToUShort(v10, v5, 0, 0, Class, 0, (__int64)&v22) < 0 )
  {
    if ( (WPP_MAIN_CB.DeviceType & 0x10000) != 0 )
      WPP_SF_(49, WPP_89f138b174f63fbd963e3069eb8413da_Traceguids);
    WideString = -1073741492;
    goto LABEL_18;
  }
  *(_QWORD *)(a1 + 256) = 2;
  *(_QWORD *)(a1 + 264) = 0;
  *(_WORD *)(a1 + 258) = __ROR2__(v22, 8);
  WideString = UxpSslReadConfigurationPropertiesFromRegistry(a1, v6);
  if ( WideString < 0 )
  {
LABEL_18:
    ExReleasePushLockSharedEx(*(_QWORD *)(a1 + 21928) + 4048LL, 0);
    KeLeaveCriticalRegion();
    goto LABEL_19;
  }
  ExReleasePushLockSharedEx(*(_QWORD *)(a1 + 21928) + 4048LL, 0);
  KeLeaveCriticalRegion();
  WideString = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 416) + 48LL))(a1);
  if ( WideString >= 0 )
  {
    WideString = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 416) + 56LL))(a1);
    if ( WideString >= 0 )
    {
      v13 = UxpSslComputeSocketAddressHashCode(a1 + 256);
      v14 = v22;
      *(_DWORD *)(a1 + 244) = v13;
      *(_DWORD *)(a1 + 248) = UxSslGeneratorBucketIndex;
      RtlStringCbPrintfW((NTSTRSAFE_PWSTR)(a1 + 440), 0x80u, L"CCS=%d", v14);
      RtlInitUnicodeString((PUNICODE_STRING)(a1 + 424), (PCWSTR)(a1 + 440));
    }
  }
LABEL_19:
  if ( v6 )
    ZwClose(v6);
  UlFreeWideString(&v18);
  return (unsigned int)WideString;
}

```

## disassembly

```asm
0x1c00d98a0  mov     [rsp-8+arg_8], rbx
0x1c00d98a5  push    rbp
0x1c00d98a6  push    rsi
0x1c00d98a7  push    rdi
0x1c00d98a8  push    r12
0x1c00d98aa  push    r13
0x1c00d98ac  push    r14
0x1c00d98ae  push    r15
0x1c00d98b0  lea     rbp, [rsp-27h]
0x1c00d98b5  sub     rsp, 0B0h
0x1c00d98bc  xor     r13d, r13d
0x1c00d98bf  mov     r15d, edx
0x1c00d98c2  mov     [rbp+57h+arg_0], r13w
0x1c00d98c7  mov     rsi, rcx
0x1c00d98ca  call    cs:__imp_KeEnterCriticalRegion
0x1c00d98d1  nop     dword ptr [rax+rax+00h]
0x1c00d98d6  mov     rcx, [rsi+55A8h]
0x1c00d98dd  xor     edx, edx
0x1c00d98df  add     rcx, 0FD0h
0x1c00d98e6  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00d98ed  nop     dword ptr [rax+rax+00h]
0x1c00d98f2  xorps   xmm0, xmm0
0x1c00d98f5  mov     [rbp+57h+KeyHandle], r13
0x1c00d98f9  xorps   xmm1, xmm1
0x1c00d98fc  mov     [rbp+57h+Handle], r13
0x1c00d9900  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c00d9907  mov     [rbp+57h+arg_18], r13
0x1c00d990b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1c00d990f  mov     dword ptr [rbp+57h+NumberOfBytes], r13d
0x1c00d9913  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1c00d9917  mov     ebx, r13d
0x1c00d991a  mov     dword ptr [rbp+57h+ObjectAttributes+4], r13d
0x1c00d991e  movups  [rbp+57h+var_88], xmm1
0x1c00d9922  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r13d
0x1c00d9926  mov     r12d, r13d
0x1c00d9929  mov     [rbp+57h+var_90], r13
0x1c00d992d  mov     r14d, r13d
0x1c00d9930  call    cs:__imp_RtlInitUnicodeString
0x1c00d9937  nop     dword ptr [rax+rax+00h]
0x1c00d993c  lea     rax, [rbp+57h+DestinationString]
0x1c00d9940  mov     [rsp+0E0h+Disposition], r13; Disposition
0x1c00d9945  xorps   xmm0, xmm0
0x1c00d9948  mov     [rsp+0E0h+CreateOptions], r13d; CreateOptions
0x1c00d994d  xor     r9d, r9d; TitleIndex
0x1c00d9950  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1c00d9954  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1c00d9958  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1c00d995f  mov     edx, 2001Fh; DesiredAccess
0x1c00d9964  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x1c00d9968  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1c00d996c  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1c00d9973  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00d9978  mov     [rsp+0E0h+Class], r13; Class
0x1c00d997d  call    cs:__imp_ZwCreateKey
0x1c00d9984  nop     dword ptr [rax+rax+00h]
0x1c00d9989  mov     edi, eax
0x1c00d998b  test    eax, eax
0x1c00d998d  js      short loc_1C00D9A08
0x1c00d998f  mov     dword ptr [rbp+57h+NumberOfBytes], 98h
0x1c00d9996  test    rbx, rbx
0x1c00d9999  jnz     loc_1C00FDE7C
0x1c00d999f  mov     edx, dword ptr [rbp+57h+NumberOfBytes]; NumberOfBytes
0x1c00d99a2  xor     r9d, r9d; Priority
0x1c00d99a5  mov     r8d, 44526C55h; Tag
0x1c00d99ab  lea     ecx, [r9+1]; PoolType
0x1c00d99af  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00d99b6  nop     dword ptr [rax+rax+00h]
0x1c00d99bb  mov     rbx, rax
0x1c00d99be  test    rax, rax
0x1c00d99c1  jz      loc_1C00FDF49
0x1c00d99c7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1c00d99cb  lea     rax, [rbp+57h+NumberOfBytes]
0x1c00d99cf  mov     qword ptr [rsp+0E0h+CreateOptions], rax; ResultLength
0x1c00d99d4  mov     r9, rbx; KeyInformation
0x1c00d99d7  mov     eax, dword ptr [rbp+57h+NumberOfBytes]
0x1c00d99da  xor     r8d, r8d; KeyInformationClass
0x1c00d99dd  mov     edx, r15d; Index
0x1c00d99e0  mov     dword ptr [rsp+0E0h+Class], eax; Length
0x1c00d99e4  call    cs:__imp_ZwEnumerateKey
0x1c00d99eb  nop     dword ptr [rax+rax+00h]
0x1c00d99f0  mov     edi, eax
0x1c00d99f2  cmp     eax, 80000005h
0x1c00d99f7  jz      short loc_1C00D9996
0x1c00d99f9  cmp     eax, 0C0000023h
0x1c00d99fe  jz      short loc_1C00D9996
0x1c00d9a00  test    eax, eax
0x1c00d9a02  jns     loc_1C00FDE93
0x1c00d9a08  lea     rcx, [rbp+57h+arg_18]
0x1c00d9a0c  call    UlFreeWideString
0x1c00d9a11  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1c00d9a15  test    rcx, rcx
0x1c00d9a18  jz      short loc_1C00D9A26
0x1c00d9a1a  call    cs:__imp_ZwClose
0x1c00d9a21  nop     dword ptr [rax+rax+00h]
0x1c00d9a26  mov     rcx, [rbp+57h+Handle]; Handle
0x1c00d9a2a  test    rcx, rcx
0x1c00d9a2d  jnz     loc_1C00FDF53
0x1c00d9a33  test    rbx, rbx
0x1c00d9a36  jz      short loc_1C00D9A49
0x1c00d9a38  xor     edx, edx; Tag
0x1c00d9a3a  mov     rcx, rbx; P
0x1c00d9a3d  call    cs:__imp_ExFreePoolWithTag
0x1c00d9a44  nop     dword ptr [rax+rax+00h]
0x1c00d9a49  test    edi, edi
0x1c00d9a4b  jns     loc_1C00FDF7C
0x1c00d9a51  test    cs:WPP_MAIN_CB.DeviceType, 10000h
0x1c00d9a5b  jnz     loc_1C00FDF65
0x1c00d9a61  mov     rcx, [rsi+55A8h]
0x1c00d9a68  xor     edx, edx
0x1c00d9a6a  add     rcx, 0FD0h
0x1c00d9a71  call    cs:__imp_ExReleasePushLockSharedEx
0x1c00d9a78  nop     dword ptr [rax+rax+00h]
0x1c00d9a7d  call    cs:__imp_KeLeaveCriticalRegion
0x1c00d9a84  nop     dword ptr [rax+rax+00h]
0x1c00d9a89  test    r14, r14
0x1c00d9a8c  jnz     loc_1C00FE0B7
0x1c00d9a92  lea     rcx, [rbp+57h+var_90]
0x1c00d9a96  call    UlFreeWideString
0x1c00d9a9b  mov     rbx, [rsp+0E0h+arg_8]
0x1c00d9aa3  mov     eax, edi
0x1c00d9aa5  add     rsp, 0B0h
0x1c00d9aac  pop     r15
0x1c00d9aae  pop     r14
0x1c00d9ab0  pop     r13
0x1c00d9ab2  pop     r12
0x1c00d9ab4  pop     rdi
0x1c00d9ab5  pop     rsi
0x1c00d9ab6  pop     rbp
0x1c00d9ab7  retn
0x1c00fde7c  xor     edx, edx; Tag
0x1c00fde7e  mov     rcx, rbx; P
0x1c00fde81  call    cs:__imp_ExFreePoolWithTag
0x1c00fde88  nop     dword ptr [rax+rax+00h]
0x1c00fde8d  nop
0x1c00fde8e  jmp     loc_1C00D999F
0x1c00fde93  mov     eax, [rbx+0Ch]
0x1c00fde96  test    al, 1
0x1c00fde98  jnz     loc_1C00FDF3F
0x1c00fde9e  cmp     eax, 0FFFEh
0x1c00fdea3  ja      loc_1C00FDF3F
0x1c00fdea9  xorps   xmm0, xmm0
0x1c00fdeac  lea     r15, [rbx+10h]
0x1c00fdeb0  mov     qword ptr [rbp+57h+var_88+8], r15
0x1c00fdeb4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1c00fdeb8  movzx   eax, word ptr [rbx+0Ch]
0x1c00fdebc  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1c00fdec0  mov     word ptr [rbp+57h+var_88], ax
0x1c00fdec4  mov     edx, 20019h; DesiredAccess
0x1c00fdec9  movzx   eax, word ptr [rbx+0Ch]
0x1c00fdecd  mov     word ptr [rbp+57h+var_88+2], ax
0x1c00fded1  mov     rax, [rbp+57h+KeyHandle]
0x1c00fded5  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1c00fded9  lea     rax, [rbp+57h+var_88]
0x1c00fdedd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1c00fdee1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1c00fdee8  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1c00fdeef  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00fdef4  call    cs:__imp_ZwOpenKey
0x1c00fdefb  nop     dword ptr [rax+rax+00h]
0x1c00fdf00  mov     edi, eax
0x1c00fdf02  test    eax, eax
0x1c00fdf04  js      loc_1C00D9A08
0x1c00fdf0a  mov     edx, [rbx+0Ch]
0x1c00fdf0d  lea     r8, [rbp+57h+arg_18]
0x1c00fdf11  shr     rdx, 1
0x1c00fdf14  mov     rcx, r15; Src
0x1c00fdf17  call    UlAllocateWideString
0x1c00fdf1c  mov     edi, eax
0x1c00fdf1e  test    eax, eax
0x1c00fdf20  js      loc_1C00D9A08
0x1c00fdf26  mov     r12, [rbp+57h+arg_18]
0x1c00fdf2a  mov     r14, [rbp+57h+Handle]
0x1c00fdf2e  mov     [rbp+57h+var_90], r12
0x1c00fdf32  mov     [rbp+57h+Handle], r13
0x1c00fdf36  mov     [rbp+57h+arg_18], r13
0x1c00fdf3a  jmp     loc_1C00D9A08
0x1c00fdf3f  mov     edi, 0C000014Ch
0x1c00fdf44  jmp     loc_1C00D9A08
0x1c00fdf49  mov     edi, 0C000009Ah
0x1c00fdf4e  jmp     loc_1C00D9A08
0x1c00fdf53  call    cs:__imp_ZwClose
0x1c00fdf5a  nop     dword ptr [rax+rax+00h]
0x1c00fdf5f  nop
0x1c00fdf60  jmp     loc_1C00D9A33
0x1c00fdf65  mov     ecx, 30h ; '0'
0x1c00fdf6a  lea     rdx, WPP_89f138b174f63fbd963e3069eb8413da_Traceguids
0x1c00fdf71  call    WPP_SF_
0x1c00fdf76  nop
0x1c00fdf77  jmp     loc_1C00D9A61
0x1c00fdf7c  lea     rax, [rbp+57h+arg_0]
0x1c00fdf80  xor     r9d, r9d
0x1c00fdf83  mov     [rsp+0E0h+Disposition], rax
0x1c00fdf88  xor     r8d, r8d
0x1c00fdf8b  mov     rdx, r12
0x1c00fdf8e  mov     qword ptr [rsp+0E0h+CreateOptions], r13
0x1c00fdf93  mov     cl, 1
0x1c00fdf95  call    HttpStringToUShort
0x1c00fdf9a  test    eax, eax
0x1c00fdf9c  jns     short loc_1C00FDFC5
0x1c00fdf9e  test    cs:WPP_MAIN_CB.DeviceType, 10000h
0x1c00fdfa8  jz      short loc_1C00FDFBB
0x1c00fdfaa  mov     ecx, 31h ; '1'
0x1c00fdfaf  lea     rdx, WPP_89f138b174f63fbd963e3069eb8413da_Traceguids
0x1c00fdfb6  call    WPP_SF_
0x1c00fdfbb  mov     edi, 0C000014Ch
0x1c00fdfc0  jmp     loc_1C00D9A61
0x1c00fdfc5  xor     eax, eax
0x1c00fdfc7  lea     rbx, [rsi+100h]
0x1c00fdfce  mov     qword ptr [rbx], 2
0x1c00fdfd5  mov     rdx, r14
0x1c00fdfd8  mov     [rbx+8], rax
0x1c00fdfdc  mov     rcx, rsi
0x1c00fdfdf  movzx   eax, [rbp+57h+arg_0]
0x1c00fdfe3  ror     ax, 8
0x1c00fdfe7  mov     [rsi+102h], ax
0x1c00fdfee  call    UxpSslReadConfigurationPropertiesFromRegistry
0x1c00fdff3  mov     edi, eax
0x1c00fdff5  test    eax, eax
0x1c00fdff7  js      loc_1C00D9A61
0x1c00fdffd  mov     rcx, [rsi+55A8h]
0x1c00fe004  xor     edx, edx
0x1c00fe006  add     rcx, 0FD0h
0x1c00fe00d  call    cs:__imp_ExReleasePushLockSharedEx
0x1c00fe014  nop     dword ptr [rax+rax+00h]
0x1c00fe019  call    cs:__imp_KeLeaveCriticalRegion
0x1c00fe020  nop     dword ptr [rax+rax+00h]
0x1c00fe025  mov     rax, [rsi+1A0h]
0x1c00fe02c  mov     rcx, rsi
0x1c00fe02f  mov     rax, [rax+30h]
0x1c00fe033  call    cs:__guard_dispatch_icall_fptr
0x1c00fe039  mov     edi, eax
0x1c00fe03b  test    eax, eax
0x1c00fe03d  js      loc_1C00D9A89
0x1c00fe043  mov     rax, [rsi+1A0h]
0x1c00fe04a  mov     rcx, rsi
0x1c00fe04d  mov     rax, [rax+38h]
0x1c00fe051  call    cs:__guard_dispatch_icall_fptr
0x1c00fe057  mov     edi, eax
0x1c00fe059  test    eax, eax
0x1c00fe05b  js      loc_1C00D9A89
0x1c00fe061  mov     rcx, rbx
0x1c00fe064  call    UxpSslComputeSocketAddressHashCode
0x1c00fe069  movzx   r9d, [rbp+57h+arg_0]
0x1c00fe06e  lea     rbx, [rsi+1B8h]
0x1c00fe075  mov     [rsi+0F4h], eax
0x1c00fe07b  lea     r8, aCcsD; "CCS=%d"
0x1c00fe082  mov     eax, cs:UxSslGeneratorBucketIndex
0x1c00fe088  mov     rcx, rbx; pszDest
0x1c00fe08b  mov     edx, 80h; cbDest
0x1c00fe090  mov     [rsi+0F8h], eax
0x1c00fe096  call    RtlStringCbPrintfW
0x1c00fe09b  lea     rcx, [rsi+1A8h]; DestinationString
0x1c00fe0a2  mov     rdx, rbx; SourceString
0x1c00fe0a5  call    cs:__imp_RtlInitUnicodeString
0x1c00fe0ac  nop     dword ptr [rax+rax+00h]
0x1c00fe0b1  nop
0x1c00fe0b2  jmp     loc_1C00D9A89
0x1c00fe0b7  mov     rcx, r14; Handle
0x1c00fe0ba  call    cs:__imp_ZwClose
0x1c00fe0c1  nop     dword ptr [rax+rax+00h]
0x1c00fe0c6  nop
0x1c00fe0c7  jmp     loc_1C00D9A92
```
