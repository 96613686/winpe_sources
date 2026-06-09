# UxpSslInitializeIpConfigurationByRegistryIndex

- ea: `0x1c00d9680`
- end: `0x1c00d9894`
- name: `UxpSslInitializeIpConfigurationByRegistryIndex`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1c001874c`
- `0x1c001b610`
- `0x1c008f21c`
- `0x1c00d9680`
- `0x1c00da914`
- `0x1c00da948`
- `0x1c01206b4`
- `0x1c0131208`
- `0x1c01328f0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1c00fdcf6`
- `ntoskrnl!ZwOpenKey` at `0x1c00fdcf6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00d970b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00fde54`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00d970b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00fde54`
- `ntoskrnl!ZwCreateKey` at `0x1c00d9758`
- `ntoskrnl!ZwCreateKey` at `0x1c00d9758`
- `ntoskrnl!ZwEnumerateKey` at `0x1c00d97bf`
- `ntoskrnl!ZwEnumerateKey` at `0x1c00d97bf`
- `ntoskrnl!ZwClose` at `0x1c00d97f5`
- `ntoskrnl!ZwClose` at `0x1c00fdd55`
- `ntoskrnl!ZwClose` at `0x1c00fde69`
- `ntoskrnl!ZwClose` at `0x1c00d97f5`
- `ntoskrnl!ZwClose` at `0x1c00fdd55`
- `ntoskrnl!ZwClose` at `0x1c00fde69`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d978a`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d978a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d9818`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fdc83`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d9818`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fdc83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d9858`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00fddcf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d9858`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00fddcf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00d984c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00fddc3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00d984c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00fddc3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d96be`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d96be`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d96a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d96a2`

## string_xrefs

- `0x1c00d96cd`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters\SslBindingInfo`

## pseudocode

```c
__int64 __fastcall UxpSslInitializeIpConfigurationByRegistryIndex(__int64 a1, ULONG a2)
{
  _DWORD *v4; // rbx
  const WCHAR *v5; // r15
  HANDLE v6; // r14
  NTSTATUS WideString; // edi
  _DWORD *PoolWithTagPriority; // rax
  NTSTATUS v9; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  HANDLE Handle; // [rsp+40h] [rbp-39h] BYREF
  const WCHAR *v14; // [rsp+48h] [rbp-31h] BYREF
  __int128 v15; // [rsp+50h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  SIZE_T NumberOfBytes; // [rsp+E0h] [rbp+67h] BYREF
  const WCHAR *v19; // [rsp+F0h] [rbp+77h] BYREF
  void *KeyHandle; // [rsp+F8h] [rbp+7Fh] BYREF

  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(*(_QWORD *)(a1 + 21928) + 4048LL, 0);
  KeyHandle = 0;
  Handle = 0;
  v19 = 0;
  DestinationString = 0;
  LODWORD(NumberOfBytes) = 0;
  v4 = 0;
  v15 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v5 = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v6 = 0;
  v14 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters\\SslBindingInfo");
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
      v11 = v4[3];
      if ( (v11 & 1) != 0 || v11 > 0xFFFE )
      {
        WideString = -1073741492;
      }
      else
      {
        *((_QWORD *)&v15 + 1) = v4 + 4;
        LOWORD(v15) = *((_WORD *)v4 + 6);
        WORD1(v15) = *((_WORD *)v4 + 6);
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v15;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        WideString = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( WideString >= 0 )
        {
          WideString = UlAllocateWideString(v4 + 4);
          if ( WideString >= 0 )
          {
            v5 = v19;
            v6 = Handle;
            v14 = v19;
            Handle = 0;
            v19 = 0;
          }
        }
      }
    }
  }
LABEL_9:
  UlFreeWideString(&v19);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( WideString < 0 )
  {
    if ( (WPP_MAIN_CB.DeviceType & 0x10000) != 0 )
      WPP_SF_(14, WPP_89f138b174f63fbd963e3069eb8413da_Traceguids);
    goto LABEL_18;
  }
  if ( (int)StringToHostAddressW(v5, (void *)(a1 + 256)) < 0 )
  {
    WideString = -1073741492;
LABEL_18:
    ExReleasePushLockSharedEx(*(_QWORD *)(a1 + 21928) + 4048LL, 0);
    KeLeaveCriticalRegion();
    goto LABEL_19;
  }
  WideString = UxpSslReadConfigurationPropertiesFromRegistry(a1, v6);
  if ( WideString < 0 )
    goto LABEL_18;
  ExReleasePushLockSharedEx(*(_QWORD *)(a1 + 21928) + 4048LL, 0);
  KeLeaveCriticalRegion();
  WideString = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 416) + 48LL))(a1);
  if ( WideString >= 0 )
  {
    WideString = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 416) + 56LL))(a1);
    if ( WideString >= 0 )
    {
      v12 = UxpSslComputeSocketAddressHashCode(a1 + 256);
      *(_DWORD *)(a1 + 244) = v12;
      *(_DWORD *)(a1 + 248) = v12 % UxSslGeneratorBucketIndex;
      RtlStringCbCopyW((NTSTRSAFE_PWSTR)(a1 + 440), 0x80u, v5);
      RtlInitUnicodeString((PUNICODE_STRING)(a1 + 424), (PCWSTR)(a1 + 440));
    }
  }
LABEL_19:
  if ( v6 )
    ZwClose(v6);
  UlFreeWideString(&v14);
  return (unsigned int)WideString;
}

```

## disassembly

```asm
0x1c00d9680  mov     [rsp-8+arg_8], rbx
0x1c00d9685  push    rbp
0x1c00d9686  push    rsi
0x1c00d9687  push    rdi
0x1c00d9688  push    r12
0x1c00d968a  push    r13
0x1c00d968c  push    r14
0x1c00d968e  push    r15
0x1c00d9690  lea     rbp, [rsp-27h]
0x1c00d9695  sub     rsp, 0A0h
0x1c00d969c  mov     r12d, edx
0x1c00d969f  mov     rsi, rcx
0x1c00d96a2  call    cs:__imp_KeEnterCriticalRegion
0x1c00d96a9  nop     dword ptr [rax+rax+00h]
0x1c00d96ae  mov     rcx, [rsi+55A8h]
0x1c00d96b5  xor     edx, edx
0x1c00d96b7  add     rcx, 0FD0h
0x1c00d96be  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00d96c5  nop     dword ptr [rax+rax+00h]
0x1c00d96ca  xor     r13d, r13d
0x1c00d96cd  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c00d96d4  xorps   xmm0, xmm0
0x1c00d96d7  mov     [rbp+57h+KeyHandle], r13
0x1c00d96db  xorps   xmm1, xmm1
0x1c00d96de  mov     [rbp+57h+Handle], r13
0x1c00d96e2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1c00d96e6  mov     [rbp+57h+arg_10], r13
0x1c00d96ea  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1c00d96ee  mov     dword ptr [rbp+57h+NumberOfBytes], r13d
0x1c00d96f2  mov     ebx, r13d
0x1c00d96f5  movups  [rbp+57h+var_80], xmm1
0x1c00d96f9  mov     dword ptr [rbp+57h+ObjectAttributes+4], r13d
0x1c00d96fd  mov     r15d, r13d
0x1c00d9700  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r13d
0x1c00d9704  mov     r14d, r13d
0x1c00d9707  mov     [rbp+57h+var_88], r13
0x1c00d970b  call    cs:__imp_RtlInitUnicodeString
0x1c00d9712  nop     dword ptr [rax+rax+00h]
0x1c00d9717  lea     rax, [rbp+57h+DestinationString]
0x1c00d971b  mov     [rsp+0D0h+Disposition], r13; Disposition
0x1c00d9720  xorps   xmm0, xmm0
0x1c00d9723  mov     [rsp+0D0h+CreateOptions], r13d; CreateOptions
0x1c00d9728  xor     r9d, r9d; TitleIndex
0x1c00d972b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1c00d972f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1c00d9733  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1c00d973a  mov     edx, 2001Fh; DesiredAccess
0x1c00d973f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x1c00d9743  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1c00d9747  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1c00d974e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00d9753  mov     [rsp+0D0h+Class], r13; Class
0x1c00d9758  call    cs:__imp_ZwCreateKey
0x1c00d975f  nop     dword ptr [rax+rax+00h]
0x1c00d9764  mov     edi, eax
0x1c00d9766  test    eax, eax
0x1c00d9768  js      short loc_1C00D97E3
0x1c00d976a  mov     dword ptr [rbp+57h+NumberOfBytes], 98h
0x1c00d9771  test    rbx, rbx
0x1c00d9774  jnz     loc_1C00FDC7E
0x1c00d977a  mov     edx, dword ptr [rbp+57h+NumberOfBytes]; NumberOfBytes
0x1c00d977d  xor     r9d, r9d; Priority
0x1c00d9780  mov     r8d, 44526C55h; Tag
0x1c00d9786  lea     ecx, [r9+1]; PoolType
0x1c00d978a  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00d9791  nop     dword ptr [rax+rax+00h]
0x1c00d9796  mov     rbx, rax
0x1c00d9799  test    rax, rax
0x1c00d979c  jz      loc_1C00FDD4B
0x1c00d97a2  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1c00d97a6  lea     rax, [rbp+57h+NumberOfBytes]
0x1c00d97aa  mov     qword ptr [rsp+0D0h+CreateOptions], rax; ResultLength
0x1c00d97af  mov     r9, rbx; KeyInformation
0x1c00d97b2  mov     eax, dword ptr [rbp+57h+NumberOfBytes]
0x1c00d97b5  xor     r8d, r8d; KeyInformationClass
0x1c00d97b8  mov     edx, r12d; Index
0x1c00d97bb  mov     dword ptr [rsp+0D0h+Class], eax; Length
0x1c00d97bf  call    cs:__imp_ZwEnumerateKey
0x1c00d97c6  nop     dword ptr [rax+rax+00h]
0x1c00d97cb  mov     edi, eax
0x1c00d97cd  cmp     eax, 80000005h
0x1c00d97d2  jz      short loc_1C00D9771
0x1c00d97d4  cmp     eax, 0C0000023h
0x1c00d97d9  jz      short loc_1C00D9771
0x1c00d97db  test    eax, eax
0x1c00d97dd  jns     loc_1C00FDC95
0x1c00d97e3  lea     rcx, [rbp+57h+arg_10]
0x1c00d97e7  call    UlFreeWideString
0x1c00d97ec  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1c00d97f0  test    rcx, rcx
0x1c00d97f3  jz      short loc_1C00D9801
0x1c00d97f5  call    cs:__imp_ZwClose
0x1c00d97fc  nop     dword ptr [rax+rax+00h]
0x1c00d9801  mov     rcx, [rbp+57h+Handle]; Handle
0x1c00d9805  test    rcx, rcx
0x1c00d9808  jnz     loc_1C00FDD55
0x1c00d980e  test    rbx, rbx
0x1c00d9811  jz      short loc_1C00D9824
0x1c00d9813  xor     edx, edx; Tag
0x1c00d9815  mov     rcx, rbx; P
0x1c00d9818  call    cs:__imp_ExFreePoolWithTag
0x1c00d981f  nop     dword ptr [rax+rax+00h]
0x1c00d9824  test    edi, edi
0x1c00d9826  jns     loc_1C00FDD7E
0x1c00d982c  test    cs:WPP_MAIN_CB.DeviceType, 10000h
0x1c00d9836  jnz     loc_1C00FDD67
0x1c00d983c  mov     rcx, [rsi+55A8h]
0x1c00d9843  xor     edx, edx
0x1c00d9845  add     rcx, 0FD0h
0x1c00d984c  call    cs:__imp_ExReleasePushLockSharedEx
0x1c00d9853  nop     dword ptr [rax+rax+00h]
0x1c00d9858  call    cs:__imp_KeLeaveCriticalRegion
0x1c00d985f  nop     dword ptr [rax+rax+00h]
0x1c00d9864  test    r14, r14
0x1c00d9867  jnz     loc_1C00FDE66
0x1c00d986d  lea     rcx, [rbp+57h+var_88]
0x1c00d9871  call    UlFreeWideString
0x1c00d9876  mov     rbx, [rsp+0D0h+arg_8]
0x1c00d987e  mov     eax, edi
0x1c00d9880  add     rsp, 0A0h
0x1c00d9887  pop     r15
0x1c00d9889  pop     r14
0x1c00d988b  pop     r13
0x1c00d988d  pop     r12
0x1c00d988f  pop     rdi
0x1c00d9890  pop     rsi
0x1c00d9891  pop     rbp
0x1c00d9892  retn
0x1c00fdc7e  xor     edx, edx; Tag
0x1c00fdc80  mov     rcx, rbx; P
0x1c00fdc83  call    cs:__imp_ExFreePoolWithTag
0x1c00fdc8a  nop     dword ptr [rax+rax+00h]
0x1c00fdc8f  nop
0x1c00fdc90  jmp     loc_1C00D977A
0x1c00fdc95  mov     eax, [rbx+0Ch]
0x1c00fdc98  test    al, 1
0x1c00fdc9a  jnz     loc_1C00FDD41
0x1c00fdca0  cmp     eax, 0FFFEh
0x1c00fdca5  ja      loc_1C00FDD41
0x1c00fdcab  xorps   xmm0, xmm0
0x1c00fdcae  lea     r12, [rbx+10h]
0x1c00fdcb2  mov     qword ptr [rbp+57h+var_80+8], r12
0x1c00fdcb6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1c00fdcba  movzx   eax, word ptr [rbx+0Ch]
0x1c00fdcbe  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1c00fdcc2  mov     word ptr [rbp+57h+var_80], ax
0x1c00fdcc6  mov     edx, 20019h; DesiredAccess
0x1c00fdccb  movzx   eax, word ptr [rbx+0Ch]
0x1c00fdccf  mov     word ptr [rbp+57h+var_80+2], ax
0x1c00fdcd3  mov     rax, [rbp+57h+KeyHandle]
0x1c00fdcd7  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1c00fdcdb  lea     rax, [rbp+57h+var_80]
0x1c00fdcdf  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1c00fdce3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1c00fdcea  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1c00fdcf1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00fdcf6  call    cs:__imp_ZwOpenKey
0x1c00fdcfd  nop     dword ptr [rax+rax+00h]
0x1c00fdd02  mov     edi, eax
0x1c00fdd04  test    eax, eax
0x1c00fdd06  js      loc_1C00D97E3
0x1c00fdd0c  mov     edx, [rbx+0Ch]
0x1c00fdd0f  lea     r8, [rbp+57h+arg_10]
0x1c00fdd13  shr     rdx, 1
0x1c00fdd16  mov     rcx, r12; Src
0x1c00fdd19  call    UlAllocateWideString
0x1c00fdd1e  mov     edi, eax
0x1c00fdd20  test    eax, eax
0x1c00fdd22  js      loc_1C00D97E3
0x1c00fdd28  mov     r15, [rbp+57h+arg_10]
0x1c00fdd2c  mov     r14, [rbp+57h+Handle]
0x1c00fdd30  mov     [rbp+57h+var_88], r15
0x1c00fdd34  mov     [rbp+57h+Handle], r13
0x1c00fdd38  mov     [rbp+57h+arg_10], r13
0x1c00fdd3c  jmp     loc_1C00D97E3
0x1c00fdd41  mov     edi, 0C000014Ch
0x1c00fdd46  jmp     loc_1C00D97E3
0x1c00fdd4b  mov     edi, 0C000009Ah
0x1c00fdd50  jmp     loc_1C00D97E3
0x1c00fdd55  call    cs:__imp_ZwClose
0x1c00fdd5c  nop     dword ptr [rax+rax+00h]
0x1c00fdd61  nop
0x1c00fdd62  jmp     loc_1C00D980E
0x1c00fdd67  mov     ecx, 0Eh
0x1c00fdd6c  lea     rdx, WPP_89f138b174f63fbd963e3069eb8413da_Traceguids
0x1c00fdd73  call    WPP_SF_
0x1c00fdd78  nop
0x1c00fdd79  jmp     loc_1C00D983C
0x1c00fdd7e  lea     rbx, [rsi+100h]
0x1c00fdd85  mov     rcx, r15; AddressString
0x1c00fdd88  mov     rdx, rbx; void *
0x1c00fdd8b  call    StringToHostAddressW
0x1c00fdd90  test    eax, eax
0x1c00fdd92  jns     short loc_1C00FDD9E
0x1c00fdd94  mov     edi, 0C000014Ch
0x1c00fdd99  jmp     loc_1C00D983C
0x1c00fdd9e  mov     rdx, r14
0x1c00fdda1  mov     rcx, rsi
0x1c00fdda4  call    UxpSslReadConfigurationPropertiesFromRegistry
0x1c00fdda9  mov     edi, eax
0x1c00fddab  test    eax, eax
0x1c00fddad  js      loc_1C00D983C
0x1c00fddb3  mov     rcx, [rsi+55A8h]
0x1c00fddba  xor     edx, edx
0x1c00fddbc  add     rcx, 0FD0h
0x1c00fddc3  call    cs:__imp_ExReleasePushLockSharedEx
0x1c00fddca  nop     dword ptr [rax+rax+00h]
0x1c00fddcf  call    cs:__imp_KeLeaveCriticalRegion
0x1c00fddd6  nop     dword ptr [rax+rax+00h]
0x1c00fdddb  mov     rax, [rsi+1A0h]
0x1c00fdde2  mov     rcx, rsi
0x1c00fdde5  mov     rax, [rax+30h]
0x1c00fdde9  call    cs:__guard_dispatch_icall_fptr
0x1c00fddef  mov     edi, eax
0x1c00fddf1  test    eax, eax
0x1c00fddf3  js      loc_1C00D9864
0x1c00fddf9  mov     rax, [rsi+1A0h]
0x1c00fde00  mov     rcx, rsi
0x1c00fde03  mov     rax, [rax+38h]
0x1c00fde07  call    cs:__guard_dispatch_icall_fptr
0x1c00fde0d  mov     edi, eax
0x1c00fde0f  test    eax, eax
0x1c00fde11  js      loc_1C00D9864
0x1c00fde17  mov     rcx, rbx
0x1c00fde1a  call    UxpSslComputeSocketAddressHashCode
0x1c00fde1f  xor     edx, edx
0x1c00fde21  mov     [rsi+0F4h], eax
0x1c00fde27  div     cs:UxSslGeneratorBucketIndex
0x1c00fde2d  lea     rbx, [rsi+1B8h]
0x1c00fde34  mov     r8, r15; pszSrc
0x1c00fde37  mov     [rsi+0F8h], edx
0x1c00fde3d  mov     rcx, rbx; pszDest
0x1c00fde40  mov     edx, 80h; cbDest
0x1c00fde45  call    RtlStringCbCopyW
0x1c00fde4a  lea     rcx, [rsi+1A8h]; DestinationString
0x1c00fde51  mov     rdx, rbx; SourceString
0x1c00fde54  call    cs:__imp_RtlInitUnicodeString
0x1c00fde5b  nop     dword ptr [rax+rax+00h]
0x1c00fde60  nop
0x1c00fde61  jmp     loc_1C00D9864
0x1c00fde66  mov     rcx, r14; Handle
0x1c00fde69  call    cs:__imp_ZwClose
0x1c00fde70  nop     dword ptr [rax+rax+00h]
0x1c00fde75  nop
0x1c00fde76  jmp     loc_1C00D986D
```
