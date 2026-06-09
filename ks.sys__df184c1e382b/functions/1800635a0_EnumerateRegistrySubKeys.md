# EnumerateRegistrySubKeys

- ea: `0x1800635a0`
- end: `0x18006387e`
- name: `EnumerateRegistrySubKeys`
- size: `734`
- prototype: `__int64 __fastcall(void *, const WCHAR *, __int64 (__fastcall *)(void *, UNICODE_STRING *, __int64), __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034ba0`
- `0x18006338c`
- `0x180063560`
- `0x180064b00`

## callees

- `0x18000c058`
- `0x18000c630`
- `0x180011790`
- `0x180019bd0`
- `0x180019cb0`
- `0x18001a000`
- `0x1800635a0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180063603`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006382a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180063603`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006382a`
- `ntoskrnl!ZwClose` at `0x1800636f9`
- `ntoskrnl!ZwClose` at `0x18006386b`
- `ntoskrnl!ZwClose` at `0x1800636f9`
- `ntoskrnl!ZwClose` at `0x18006386b`
- `ntoskrnl!ZwOpenKey` at `0x18006363e`
- `ntoskrnl!ZwOpenKey` at `0x18006363e`
- `ntoskrnl!ZwQueryKey` at `0x1800636a0`
- `ntoskrnl!ZwQueryKey` at `0x1800636a0`
- `ntoskrnl!ZwEnumerateKey` at `0x180063804`
- `ntoskrnl!ZwEnumerateKey` at `0x180063804`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006385b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006385b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800637aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800637aa`

## pseudocode

```c
__int64 __fastcall EnumerateRegistrySubKeys(
        void *a1,
        const WCHAR *a2,
        __int64 (__fastcall *a3)(void *, UNICODE_STRING *, __int64),
        __int64 a4)
{
  int v7; // edx
  NTSTATUS v8; // ebx
  int v9; // r8d
  int v10; // r9d
  NTSTATUS v12; // eax
  int v13; // edx
  int v14; // r8d
  NTSTATUS v15; // edi
  unsigned __int64 v16; // rax
  ULONG v17; // r14d
  WCHAR *PoolWithTag; // rax
  WCHAR *v19; // rbx
  ULONG i; // esi
  void *KeyHandle; // [rsp+40h] [rbp-79h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-71h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-59h] BYREF
  __int128 KeyInformation; // [rsp+90h] [rbp-29h] BYREF
  __int128 v26; // [rsp+A0h] [rbp-19h]
  __int128 v27; // [rsp+B0h] [rbp-9h]

  KeyHandle = 0;
  ResultLength = 0;
  KeyInformation = 0;
  v26 = 0;
  v27 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_SD(WPP_GLOBAL_Control->DeviceExtension, v7, v9, v10);
    }
    return (unsigned int)v8;
  }
  v12 = ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
  v15 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v13) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        1,
        66,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        v12);
    }
    goto LABEL_10;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v13) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      67,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
      SBYTE4(v26));
  }
  v16 = 2LL * DWORD2(v26);
  if ( v16 > 0xFFFFFFFF )
    goto LABEL_10;
  if ( (int)v16 + 24 < (unsigned int)v16 )
    goto LABEL_10;
  v17 = v16 + 26;
  if ( (int)v16 + 26 < (unsigned int)(v16 + 24) )
    goto LABEL_10;
  PoolWithTag = (WCHAR *)ExAllocatePoolWithTag((POOL_TYPE)1025, v17, 0x696B5753u);
  v19 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( !PoolWithTag )
    {
LABEL_10:
      ZwClose(KeyHandle);
      return 3221225626LL;
    }
    memset(PoolWithTag, 0, v17);
  }
  if ( !v19 )
    goto LABEL_10;
  for ( i = 0; i < DWORD1(v26); ++i )
  {
    v15 = ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, v19, v17, &ResultLength);
    if ( v15 >= 0 )
    {
      v19[((unsigned __int64)*((unsigned int *)v19 + 3) >> 1) + 8] = 0;
      RtlInitUnicodeString(&DestinationString, v19 + 8);
      v15 = a3(KeyHandle, &DestinationString, a4);
      if ( v15 < 0 )
        break;
    }
  }
  ExFreePoolWithTag(v19, 0);
  ZwClose(KeyHandle);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800635a0  push    rbp
0x1800635a2  push    rbx
0x1800635a3  push    rsi
0x1800635a4  push    rdi
0x1800635a5  push    r12
0x1800635a7  push    r13
0x1800635a9  push    r14
0x1800635ab  push    r15
0x1800635ad  lea     rbp, [rsp-1Fh]
0x1800635b2  sub     rsp, 0D8h
0x1800635b9  mov     rax, cs:__security_cookie
0x1800635c0  xor     rax, rsp
0x1800635c3  mov     [rbp+57h+var_50], rax
0x1800635c7  xorps   xmm0, xmm0
0x1800635ca  mov     rbx, rcx
0x1800635cd  xor     r13d, r13d
0x1800635d0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800635d4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800635d8  xor     eax, eax
0x1800635da  mov     [rbp+57h+KeyHandle], r13
0x1800635de  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800635e2  mov     r12, r9
0x1800635e5  mov     [rbp+57h+var_C8], r13d
0x1800635e9  mov     r15, r8
0x1800635ec  mov     rdi, rdx
0x1800635ef  movups  [rbp+57h+KeyInformation], xmm0
0x1800635f3  movups  [rbp+57h+var_70], xmm0
0x1800635f7  movups  [rbp+57h+var_60], xmm0
0x1800635fb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800635ff  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180063603  call    cs:__imp_RtlInitUnicodeString
0x18006360a  nop     dword ptr [rax+rax+00h]
0x18006360f  lea     rax, [rbp+57h+DestinationString]
0x180063613  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180063617  xorps   xmm0, xmm0
0x18006361a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006361e  lea     esi, [r13+30h]
0x180063622  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180063629  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006362d  mov     [rbp+57h+ObjectAttributes.Length], esi
0x180063630  mov     edx, 20019h; DesiredAccess
0x180063635  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180063639  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006363e  call    cs:__imp_ZwOpenKey
0x180063645  nop     dword ptr [rax+rax+00h]
0x18006364a  mov     ebx, eax
0x18006364c  test    eax, eax
0x18006364e  jns     short loc_180063687
0x180063650  lea     rcx, WPP_RECORDER_INITIALIZED
0x180063657  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18006365e  jz      short loc_180063680
0x180063660  mov     rcx, cs:WPP_GLOBAL_Control
0x180063667  cmp     [rcx+48h], r13w
0x18006366c  jz      short loc_180063680
0x18006366e  mov     rcx, [rcx+40h]
0x180063672  mov     [rsp+110h+var_E0], eax
0x180063676  mov     [rsp+110h+var_E8], rdi
0x18006367b  call    WPP_RECORDER_SF_SD
0x180063680  mov     eax, ebx
0x180063682  jmp     loc_18006370A
0x180063687  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006368b  lea     rax, [rbp+57h+var_C8]
0x18006368f  mov     r9d, esi; Length
0x180063692  mov     [rsp+110h+ResultLength], rax; ResultLength
0x180063697  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x18006369b  mov     edx, 2; KeyInformationClass
0x1800636a0  call    cs:__imp_ZwQueryKey
0x1800636a7  nop     dword ptr [rax+rax+00h]
0x1800636ac  mov     edi, eax
0x1800636ae  test    eax, eax
0x1800636b0  jns     short loc_18006372B
0x1800636b2  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800636b9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800636c0  jz      short loc_1800636F5
0x1800636c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800636c9  cmp     [rcx+48h], r13w
0x1800636ce  jz      short loc_1800636F5
0x1800636d0  mov     rcx, [rcx+40h]
0x1800636d4  mov     r9d, 42h ; 'B'
0x1800636da  mov     dword ptr [rsp+110h+var_E8], eax
0x1800636de  mov     dl, 5
0x1800636e0  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x1800636e7  mov     [rsp+110h+ResultLength], rax
0x1800636ec  lea     r8d, [r9-41h]
0x1800636f0  call    WPP_RECORDER_SF_D
0x1800636f5  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800636f9  call    cs:__imp_ZwClose
0x180063700  nop     dword ptr [rax+rax+00h]
0x180063705  mov     eax, 0C000009Ah
0x18006370a  mov     rcx, [rbp+57h+var_50]
0x18006370e  xor     rcx, rsp; StackCookie
0x180063711  call    __security_check_cookie
0x180063716  add     rsp, 0D8h
0x18006371d  pop     r15
0x18006371f  pop     r14
0x180063721  pop     r13
0x180063723  pop     r12
0x180063725  pop     rdi
0x180063726  pop     rsi
0x180063727  pop     rbx
0x180063728  pop     rbp
0x180063729  retn
0x18006372b  lea     rcx, WPP_RECORDER_INITIALIZED
0x180063732  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180063739  jz      short loc_18006376D
0x18006373b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063742  cmp     [rcx+48h], r13w
0x180063747  jz      short loc_18006376D
0x180063749  mov     eax, dword ptr [rbp+57h+var_70+4]
0x18006374c  mov     r9d, 43h ; 'C'
0x180063752  mov     rcx, [rcx+40h]
0x180063756  mov     dl, 5
0x180063758  mov     dword ptr [rsp+110h+var_E8], eax
0x18006375c  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063763  mov     [rsp+110h+ResultLength], rax
0x180063768  call    WPP_RECORDER_SF_d
0x18006376d  mov     eax, dword ptr [rbp+57h+var_70+8]
0x180063770  mov     ecx, 0FFFFFFFFh
0x180063775  add     rax, rax
0x180063778  cmp     rax, rcx
0x18006377b  ja      loc_1800636F5
0x180063781  lea     ecx, [rax+18h]
0x180063784  cmp     ecx, eax
0x180063786  jb      loc_1800636F5
0x18006378c  lea     r14d, [rcx+2]
0x180063790  cmp     r14d, ecx
0x180063793  jb      loc_1800636F5
0x180063799  mov     r8d, 696B5753h; Tag
0x18006379f  mov     edx, r14d; NumberOfBytes
0x1800637a2  mov     ecx, 401h; PoolType
0x1800637a7  mov     esi, r14d
0x1800637aa  call    cs:__imp_ExAllocatePoolWithTag
0x1800637b1  nop     dword ptr [rax+rax+00h]
0x1800637b6  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x1800637bd  mov     rbx, rax
0x1800637c0  jnz     short loc_1800637D8
0x1800637c2  test    rax, rax
0x1800637c5  jz      loc_1800636F5
0x1800637cb  mov     r8d, esi; Size
0x1800637ce  xor     edx, edx; Val
0x1800637d0  mov     rcx, rax; void *
0x1800637d3  call    memset
0x1800637d8  test    rbx, rbx
0x1800637db  jz      loc_1800636F5
0x1800637e1  mov     esi, r13d
0x1800637e4  cmp     dword ptr [rbp+57h+var_70+4], r13d
0x1800637e8  jbe     short loc_180063856
0x1800637ea  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800637ee  lea     rax, [rbp+57h+var_C8]
0x1800637f2  mov     [rsp+110h+var_E8], rax; ResultLength
0x1800637f7  mov     r9, rbx; KeyInformation
0x1800637fa  xor     r8d, r8d; KeyInformationClass
0x1800637fd  mov     dword ptr [rsp+110h+ResultLength], r14d; Length
0x180063802  mov     edx, esi; Index
0x180063804  call    cs:__imp_ZwEnumerateKey
0x18006380b  nop     dword ptr [rax+rax+00h]
0x180063810  mov     edi, eax
0x180063812  test    eax, eax
0x180063814  js      short loc_18006384F
0x180063816  mov     ecx, [rbx+0Ch]
0x180063819  lea     rdx, [rbx+10h]; SourceString
0x18006381d  shr     rcx, 1
0x180063820  mov     [rbx+rcx*2+10h], r13w
0x180063826  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006382a  call    cs:__imp_RtlInitUnicodeString
0x180063831  nop     dword ptr [rax+rax+00h]
0x180063836  mov     rcx, [rbp+57h+KeyHandle]
0x18006383a  lea     rdx, [rbp+57h+DestinationString]
0x18006383e  mov     r8, r12
0x180063841  mov     rax, r15
0x180063844  call    _guard_dispatch_icall
0x180063849  mov     edi, eax
0x18006384b  test    eax, eax
0x18006384d  js      short loc_180063856
0x18006384f  inc     esi
0x180063851  cmp     esi, dword ptr [rbp+57h+var_70+4]
0x180063854  jb      short loc_1800637EA
0x180063856  xor     edx, edx; Tag
0x180063858  mov     rcx, rbx; P
0x18006385b  call    cs:__imp_ExFreePoolWithTag
0x180063862  nop     dword ptr [rax+rax+00h]
0x180063867  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18006386b  call    cs:__imp_ZwClose
0x180063872  nop     dword ptr [rax+rax+00h]
0x180063877  mov     eax, edi
0x180063879  jmp     loc_18006370A
```
