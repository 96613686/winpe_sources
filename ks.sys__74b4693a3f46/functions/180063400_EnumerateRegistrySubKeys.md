# EnumerateRegistrySubKeys

- ea: `0x180063400`
- end: `0x1800636de`
- name: `EnumerateRegistrySubKeys`
- size: `734`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034a90`
- `0x1800631ec`
- `0x1800633c0`
- `0x180064960`

## callees

- `0x18000c058`
- `0x18000c630`
- `0x180010ef0`
- `0x180019b80`
- `0x180019c60`
- `0x180019fc0`
- `0x180063400`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180063463`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006368a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180063463`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006368a`
- `ntoskrnl!ZwClose` at `0x180063559`
- `ntoskrnl!ZwClose` at `0x1800636cb`
- `ntoskrnl!ZwClose` at `0x180063559`
- `ntoskrnl!ZwClose` at `0x1800636cb`
- `ntoskrnl!ZwOpenKey` at `0x18006349e`
- `ntoskrnl!ZwOpenKey` at `0x18006349e`
- `ntoskrnl!ZwQueryKey` at `0x180063500`
- `ntoskrnl!ZwQueryKey` at `0x180063500`
- `ntoskrnl!ZwEnumerateKey` at `0x180063664`
- `ntoskrnl!ZwEnumerateKey` at `0x180063664`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800636bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800636bb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18006360a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18006360a`

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
0x180063400  push    rbp
0x180063402  push    rbx
0x180063403  push    rsi
0x180063404  push    rdi
0x180063405  push    r12
0x180063407  push    r13
0x180063409  push    r14
0x18006340b  push    r15
0x18006340d  lea     rbp, [rsp-1Fh]
0x180063412  sub     rsp, 0D8h
0x180063419  mov     rax, cs:__security_cookie
0x180063420  xor     rax, rsp
0x180063423  mov     [rbp+57h+var_50], rax
0x180063427  xorps   xmm0, xmm0
0x18006342a  mov     rbx, rcx
0x18006342d  xor     r13d, r13d
0x180063430  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180063434  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180063438  xor     eax, eax
0x18006343a  mov     [rbp+57h+KeyHandle], r13
0x18006343e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180063442  mov     r12, r9
0x180063445  mov     [rbp+57h+var_C8], r13d
0x180063449  mov     r15, r8
0x18006344c  mov     rdi, rdx
0x18006344f  movups  [rbp+57h+KeyInformation], xmm0
0x180063453  movups  [rbp+57h+var_70], xmm0
0x180063457  movups  [rbp+57h+var_60], xmm0
0x18006345b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006345f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180063463  call    cs:__imp_RtlInitUnicodeString
0x18006346a  nop     dword ptr [rax+rax+00h]
0x18006346f  lea     rax, [rbp+57h+DestinationString]
0x180063473  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180063477  xorps   xmm0, xmm0
0x18006347a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006347e  lea     esi, [r13+30h]
0x180063482  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180063489  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006348d  mov     [rbp+57h+ObjectAttributes.Length], esi
0x180063490  mov     edx, 20019h; DesiredAccess
0x180063495  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180063499  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006349e  call    cs:__imp_ZwOpenKey
0x1800634a5  nop     dword ptr [rax+rax+00h]
0x1800634aa  mov     ebx, eax
0x1800634ac  test    eax, eax
0x1800634ae  jns     short loc_1800634E7
0x1800634b0  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800634b7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800634be  jz      short loc_1800634E0
0x1800634c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800634c7  cmp     [rcx+48h], r13w
0x1800634cc  jz      short loc_1800634E0
0x1800634ce  mov     rcx, [rcx+40h]
0x1800634d2  mov     [rsp+110h+var_E0], eax
0x1800634d6  mov     [rsp+110h+var_E8], rdi
0x1800634db  call    WPP_RECORDER_SF_SD
0x1800634e0  mov     eax, ebx
0x1800634e2  jmp     loc_18006356A
0x1800634e7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800634eb  lea     rax, [rbp+57h+var_C8]
0x1800634ef  mov     r9d, esi; Length
0x1800634f2  mov     [rsp+110h+ResultLength], rax; ResultLength
0x1800634f7  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1800634fb  mov     edx, 2; KeyInformationClass
0x180063500  call    cs:__imp_ZwQueryKey
0x180063507  nop     dword ptr [rax+rax+00h]
0x18006350c  mov     edi, eax
0x18006350e  test    eax, eax
0x180063510  jns     short loc_18006358B
0x180063512  lea     rcx, WPP_RECORDER_INITIALIZED
0x180063519  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180063520  jz      short loc_180063555
0x180063522  mov     rcx, cs:WPP_GLOBAL_Control
0x180063529  cmp     [rcx+48h], r13w
0x18006352e  jz      short loc_180063555
0x180063530  mov     rcx, [rcx+40h]
0x180063534  mov     r9d, 42h ; 'B'
0x18006353a  mov     dword ptr [rsp+110h+var_E8], eax
0x18006353e  mov     dl, 5
0x180063540  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063547  mov     [rsp+110h+ResultLength], rax
0x18006354c  lea     r8d, [r9-41h]
0x180063550  call    WPP_RECORDER_SF_D
0x180063555  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180063559  call    cs:__imp_ZwClose
0x180063560  nop     dword ptr [rax+rax+00h]
0x180063565  mov     eax, 0C000009Ah
0x18006356a  mov     rcx, [rbp+57h+var_50]
0x18006356e  xor     rcx, rsp; StackCookie
0x180063571  call    __security_check_cookie
0x180063576  add     rsp, 0D8h
0x18006357d  pop     r15
0x18006357f  pop     r14
0x180063581  pop     r13
0x180063583  pop     r12
0x180063585  pop     rdi
0x180063586  pop     rsi
0x180063587  pop     rbx
0x180063588  pop     rbp
0x180063589  retn
0x18006358b  lea     rcx, WPP_RECORDER_INITIALIZED
0x180063592  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180063599  jz      short loc_1800635CD
0x18006359b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800635a2  cmp     [rcx+48h], r13w
0x1800635a7  jz      short loc_1800635CD
0x1800635a9  mov     eax, dword ptr [rbp+57h+var_70+4]
0x1800635ac  mov     r9d, 43h ; 'C'
0x1800635b2  mov     rcx, [rcx+40h]
0x1800635b6  mov     dl, 5
0x1800635b8  mov     dword ptr [rsp+110h+var_E8], eax
0x1800635bc  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x1800635c3  mov     [rsp+110h+ResultLength], rax
0x1800635c8  call    WPP_RECORDER_SF_d
0x1800635cd  mov     eax, dword ptr [rbp+57h+var_70+8]
0x1800635d0  mov     ecx, 0FFFFFFFFh
0x1800635d5  add     rax, rax
0x1800635d8  cmp     rax, rcx
0x1800635db  ja      loc_180063555
0x1800635e1  lea     ecx, [rax+18h]
0x1800635e4  cmp     ecx, eax
0x1800635e6  jb      loc_180063555
0x1800635ec  lea     r14d, [rcx+2]
0x1800635f0  cmp     r14d, ecx
0x1800635f3  jb      loc_180063555
0x1800635f9  mov     r8d, 696B5753h; Tag
0x1800635ff  mov     edx, r14d; NumberOfBytes
0x180063602  mov     ecx, 401h; PoolType
0x180063607  mov     esi, r14d
0x18006360a  call    cs:__imp_ExAllocatePoolWithTag
0x180063611  nop     dword ptr [rax+rax+00h]
0x180063616  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x18006361d  mov     rbx, rax
0x180063620  jnz     short loc_180063638
0x180063622  test    rax, rax
0x180063625  jz      loc_180063555
0x18006362b  mov     r8d, esi; Size
0x18006362e  xor     edx, edx; Val
0x180063630  mov     rcx, rax; void *
0x180063633  call    memset
0x180063638  test    rbx, rbx
0x18006363b  jz      loc_180063555
0x180063641  mov     esi, r13d
0x180063644  cmp     dword ptr [rbp+57h+var_70+4], r13d
0x180063648  jbe     short loc_1800636B6
0x18006364a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006364e  lea     rax, [rbp+57h+var_C8]
0x180063652  mov     [rsp+110h+var_E8], rax; ResultLength
0x180063657  mov     r9, rbx; KeyInformation
0x18006365a  xor     r8d, r8d; KeyInformationClass
0x18006365d  mov     dword ptr [rsp+110h+ResultLength], r14d; Length
0x180063662  mov     edx, esi; Index
0x180063664  call    cs:__imp_ZwEnumerateKey
0x18006366b  nop     dword ptr [rax+rax+00h]
0x180063670  mov     edi, eax
0x180063672  test    eax, eax
0x180063674  js      short loc_1800636AF
0x180063676  mov     ecx, [rbx+0Ch]
0x180063679  lea     rdx, [rbx+10h]; SourceString
0x18006367d  shr     rcx, 1
0x180063680  mov     [rbx+rcx*2+10h], r13w
0x180063686  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006368a  call    cs:__imp_RtlInitUnicodeString
0x180063691  nop     dword ptr [rax+rax+00h]
0x180063696  mov     rcx, [rbp+57h+KeyHandle]
0x18006369a  lea     rdx, [rbp+57h+DestinationString]
0x18006369e  mov     r8, r12
0x1800636a1  mov     rax, r15
0x1800636a4  call    _guard_dispatch_icall
0x1800636a9  mov     edi, eax
0x1800636ab  test    eax, eax
0x1800636ad  js      short loc_1800636B6
0x1800636af  inc     esi
0x1800636b1  cmp     esi, dword ptr [rbp+57h+var_70+4]
0x1800636b4  jb      short loc_18006364A
0x1800636b6  xor     edx, edx; Tag
0x1800636b8  mov     rcx, rbx; P
0x1800636bb  call    cs:__imp_ExFreePoolWithTag
0x1800636c2  nop     dword ptr [rax+rax+00h]
0x1800636c7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800636cb  call    cs:__imp_ZwClose
0x1800636d2  nop     dword ptr [rax+rax+00h]
0x1800636d7  mov     eax, edi
0x1800636d9  jmp     loc_18006356A
```
