# CfgGetCachedSslCipherSuiteOrder

- ea: `0x1800470cc`
- end: `0x180047474`
- name: `CfgGetCachedSslCipherSuiteOrder`
- size: `936`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002160c`

## callees

- `0x180018e40`
- `0x180018f30`
- `0x180021f8c`
- `0x180025aa0`
- `0x180045318`
- `0x1800470cc`
- `0x18007173c`
- `0x18009f616`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180047173`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004733d`
- `ntoskrnl!RtlInitUnicodeString` at `0x180047173`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004733d`
- `ntoskrnl!ZwQueryValueKey` at `0x18004736a`
- `ntoskrnl!ZwQueryValueKey` at `0x1800473ce`
- `ntoskrnl!ZwQueryValueKey` at `0x18004736a`
- `ntoskrnl!ZwQueryValueKey` at `0x1800473ce`
- `ntoskrnl!ZwClose` at `0x1800472f3`
- `ntoskrnl!ZwClose` at `0x1800472f3`
- `ntoskrnl!ZwOpenKey` at `0x1800471b6`
- `ntoskrnl!ZwOpenKey` at `0x1800471b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180047201`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180047201`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180047284`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180047284`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180047212`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180047212`
- `ntoskrnl!ExReleaseResourceLite` at `0x180047273`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800472d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x180047273`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800472d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800472dd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800472dd`
- `ntoskrnl!ZwQueryKey` at `0x1800471e4`
- `ntoskrnl!ZwQueryKey` at `0x1800471e4`

## string_xrefs

- `0x18004721e`: `\Registry\Machine\Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002\`
- `0x18004723f`: `\Registry\Machine\System\CurrentControlSet\Control\Cryptography\MDMPolicies\SSL\`

## pseudocode

```c
__int64 __fastcall CfgGetCachedSslCipherSuiteOrder(wchar_t *Str1, const WCHAR *a2, _QWORD *a3)
{
  __int64 v5; // r15
  struct _CNG_CONFIG_CONTEXT *ConfigContext; // rsi
  NTSTATUS v7; // ebx
  struct _ERESOURCE *v8; // rsi
  __int64 v9; // r14
  __int64 v10; // r12
  _DWORD *v11; // rdi
  NTSTATUS v13; // eax
  ULONG v14; // ebx
  NTSTATUS v15; // eax
  ULONG Length; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _LIST_ENTRY *v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  PCWSTR SourceString; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  _QWORD KeyInformation[16]; // [rsp+B0h] [rbp-50h] BYREF

  SourceString = a2;
  KeyHandle = 0;
  Length = 0;
  v5 = 128;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(KeyInformation, 0, sizeof(KeyInformation));
  v20 = 0;
  ConfigContext = CfgGetConfigContext();
  if ( !a3 )
  {
    v7 = -1073741811;
    goto LABEL_14;
  }
  *a3 = 0;
  RtlInitUnicodeString(&DestinationString, Str1);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( v7 >= 0 )
  {
    v7 = ZwQueryKey(KeyHandle, KeyBasicInformation, KeyInformation, 0x80u, &Length);
    if ( v7 >= 0 )
    {
      v8 = (struct _ERESOURCE *)((char *)ConfigContext + 272);
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(v8, 1u);
      if ( !wcscmp_0(
              Str1,
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL\\00010002\\") )
      {
        v5 = 104;
        v9 = 112;
        v10 = 120;
      }
      else
      {
        if ( wcscmp_0(
               Str1,
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Cryptography\\MDMPolicies\\SSL\\") )
        {
          v7 = -1073741822;
          goto LABEL_13;
        }
        v9 = 136;
        v10 = 144;
      }
      v11 = 0;
      if ( KeyInformation[0] > *(__int64 *)((char *)&v8->SystemResourcesList.Flink + v5) )
      {
        ExReleaseResourceLite(v8);
        ExAcquireResourceExclusiveLite(v8, 1u);
        if ( KeyInformation[0] > *(__int64 *)((char *)&v8->SystemResourcesList.Flink + v5) )
        {
          v19 = 0;
          v17 = 0;
          ValueName = 0;
          v11 = (_DWORD *)BCryptAlloc(2048);
          if ( !v11 )
          {
LABEL_12:
            v7 = -1073741670;
LABEL_13:
            ExReleaseResourceLite(v8);
            KeLeaveCriticalRegion();
            goto LABEL_14;
          }
          RtlInitUnicodeString(&ValueName, SourceString);
          v13 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, v11, 0x800u, &Length);
          v7 = v13;
          if ( v13 < 0 )
          {
            if ( v13 != -1073741789 && v13 != -2147483643 )
              goto LABEL_30;
            BCryptFree(v11);
            v14 = Length;
            v11 = (_DWORD *)BCryptAlloc(Length);
            if ( !v11 )
              goto LABEL_12;
            v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, v11, v14, &Length);
            if ( v7 < 0 )
              goto LABEL_30;
          }
          v7 = CfgGppConvertRegDataToMultiString(v11[1], (int)v11 + 12, v11[2], (unsigned int)&v19, (__int64)&v17);
          if ( v7 < 0 )
          {
LABEL_30:
            BCryptFree(v11);
            goto LABEL_13;
          }
          BCryptFree(*(PVOID *)((char *)&v8->SystemResourcesList.Flink + v9));
          *(struct _LIST_ENTRY **)((char *)&v8->SystemResourcesList.Flink + v9) = v19;
          *(_DWORD *)((char *)&v8->SystemResourcesList.Flink + v10) = v17;
          *(struct _LIST_ENTRY **)((char *)&v8->SystemResourcesList.Flink + v5) = (struct _LIST_ENTRY *)KeyInformation[0];
        }
      }
      v15 = WideMultiString_AllocInit_FromSzMultiString(*(PVOID *)((char *)&v8->SystemResourcesList.Flink + v9));
      if ( v15 )
        v7 = WinErrorToNtStatus(v15);
      else
        *a3 = v20;
      if ( !v11 )
        goto LABEL_13;
      goto LABEL_30;
    }
  }
LABEL_14:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v7 == -2147483643 )
    return (unsigned int)-1073741789;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800470cc  mov     [rsp-8+arg_18], rbx
0x1800470d1  push    rbp
0x1800470d2  push    rsi
0x1800470d3  push    rdi
0x1800470d4  push    r12
0x1800470d6  push    r13
0x1800470d8  push    r14
0x1800470da  push    r15
0x1800470dc  lea     rbp, [rsp-40h]
0x1800470e1  sub     rsp, 140h
0x1800470e8  mov     rax, cs:__security_cookie
0x1800470ef  xor     rax, rsp
0x1800470f2  mov     [rbp+70h+var_40], rax
0x1800470f6  xorps   xmm1, xmm1
0x1800470f9  mov     [rsp+170h+SourceString], rdx
0x1800470fe  mov     r13, r8
0x180047101  mov     [rsp+170h+KeyHandle], 0
0x18004710a  mov     rdi, rcx
0x18004710d  mov     [rsp+170h+Length], 0
0x180047115  xorps   xmm0, xmm0
0x180047118  lea     rcx, [rbp+70h+KeyInformation]; void *
0x18004711c  mov     r15d, 80h
0x180047122  xor     edx, edx; Val
0x180047124  mov     r8d, r15d; Size
0x180047127  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x18004712c  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm1
0x180047131  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm1
0x180047135  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm1
0x180047139  call    memset
0x18004713e  mov     [rsp+170h+var_128], 0
0x180047147  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x18004714c  mov     rsi, rax
0x18004714f  mov     r14d, 0C0000023h
0x180047155  test    r13, r13
0x180047158  jnz     short loc_180047163
0x18004715a  lea     ebx, [r14-16h]
0x18004715e  jmp     loc_1800472E9
0x180047163  mov     rdx, rdi; SourceString
0x180047166  mov     qword ptr [r13+0], 0
0x18004716e  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180047173  call    cs:__imp_RtlInitUnicodeString
0x18004717a  nop     dword ptr [rax+rax+00h]
0x18004717f  lea     rax, [rsp+170h+DestinationString]
0x180047184  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x18004718c  xorps   xmm0, xmm0
0x18004718f  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x180047193  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180047198  mov     [rbp+70h+ObjectAttributes.RootDirectory], 0
0x1800471a0  mov     edx, 1; DesiredAccess
0x1800471a5  mov     [rbp+70h+ObjectAttributes.Attributes], 240h
0x1800471ac  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800471b1  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800471b6  call    cs:__imp_ZwOpenKey
0x1800471bd  nop     dword ptr [rax+rax+00h]
0x1800471c2  mov     ebx, eax
0x1800471c4  test    eax, eax
0x1800471c6  js      loc_1800472E9
0x1800471cc  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800471d1  lea     rax, [rsp+170h+Length]
0x1800471d6  mov     r9d, r15d; Length
0x1800471d9  mov     [rsp+170h+ResultLength], rax; ResultLength
0x1800471de  lea     r8, [rbp+70h+KeyInformation]; KeyInformation
0x1800471e2  xor     edx, edx; KeyInformationClass
0x1800471e4  call    cs:__imp_ZwQueryKey
0x1800471eb  nop     dword ptr [rax+rax+00h]
0x1800471f0  mov     ebx, eax
0x1800471f2  test    eax, eax
0x1800471f4  js      loc_1800472E9
0x1800471fa  add     rsi, 110h
0x180047201  call    cs:__imp_KeEnterCriticalRegion
0x180047208  nop     dword ptr [rax+rax+00h]
0x18004720d  mov     dl, 1; Wait
0x18004720f  mov     rcx, rsi; Resource
0x180047212  call    cs:__imp_ExAcquireResourceSharedLite
0x180047219  nop     dword ptr [rax+rax+00h]
0x18004721e  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\Software\\Policies"...
0x180047225  mov     rcx, rdi; Str1
0x180047228  call    wcscmp_0
0x18004722d  test    eax, eax
0x18004722f  jnz     short loc_18004723F
0x180047231  lea     r15d, [rax+68h]
0x180047235  lea     r14d, [rax+70h]
0x180047239  lea     r12d, [rax+78h]
0x18004723d  jmp     short loc_180047260
0x18004723f  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180047246  mov     rcx, rdi; Str1
0x180047249  call    wcscmp_0
0x18004724e  test    eax, eax
0x180047250  jnz     loc_18004746A
0x180047256  mov     r14d, 88h
0x18004725c  lea     r12d, [r14+8]
0x180047260  mov     rax, [rsi+r15]
0x180047264  xor     edi, edi
0x180047266  cmp     [rbp+70h+KeyInformation], rax
0x18004726a  jle     loc_180047427
0x180047270  mov     rcx, rsi; Resource
0x180047273  call    cs:__imp_ExReleaseResourceLite
0x18004727a  nop     dword ptr [rax+rax+00h]
0x18004727f  mov     dl, 1; Wait
0x180047281  mov     rcx, rsi; Resource
0x180047284  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18004728b  nop     dword ptr [rax+rax+00h]
0x180047290  mov     rax, [rsi+r15]
0x180047294  cmp     [rbp+70h+KeyInformation], rax
0x180047298  jle     loc_180047427
0x18004729e  xorps   xmm0, xmm0
0x1800472a1  mov     [rsp+170h+var_130], rdi
0x1800472a6  mov     ebx, 800h
0x1800472ab  mov     [rsp+170h+var_13C], edi
0x1800472af  mov     ecx, ebx
0x1800472b1  movups  xmmword ptr [rsp+170h+ValueName.Length], xmm0
0x1800472b6  call    BCryptAlloc
0x1800472bb  mov     rdi, rax
0x1800472be  test    rax, rax
0x1800472c1  jnz     short loc_180047333
0x1800472c3  mov     ebx, 0C000009Ah
0x1800472c8  mov     r14d, 0C0000023h
0x1800472ce  mov     rcx, rsi; Resource
0x1800472d1  call    cs:__imp_ExReleaseResourceLite
0x1800472d8  nop     dword ptr [rax+rax+00h]
0x1800472dd  call    cs:__imp_KeLeaveCriticalRegion
0x1800472e4  nop     dword ptr [rax+rax+00h]
0x1800472e9  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x1800472ee  test    rcx, rcx
0x1800472f1  jz      short loc_1800472FF
0x1800472f3  call    cs:__imp_ZwClose
0x1800472fa  nop     dword ptr [rax+rax+00h]
0x1800472ff  cmp     ebx, 80000005h
0x180047305  cmovz   ebx, r14d
0x180047309  mov     eax, ebx
0x18004730b  mov     rcx, [rbp+70h+var_40]
0x18004730f  xor     rcx, rsp; StackCookie
0x180047312  call    __security_check_cookie
0x180047317  mov     rbx, [rsp+170h+arg_18]
0x18004731f  add     rsp, 140h
0x180047326  pop     r15
0x180047328  pop     r14
0x18004732a  pop     r13
0x18004732c  pop     r12
0x18004732e  pop     rdi
0x18004732f  pop     rsi
0x180047330  pop     rbp
0x180047331  retn
0x180047333  mov     rdx, [rsp+170h+SourceString]; SourceString
0x180047338  lea     rcx, [rsp+170h+ValueName]; DestinationString
0x18004733d  call    cs:__imp_RtlInitUnicodeString
0x180047344  nop     dword ptr [rax+rax+00h]
0x180047349  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x18004734e  lea     rax, [rsp+170h+Length]
0x180047353  mov     [rsp+170h+var_148], rax; ResultLength
0x180047358  lea     rdx, [rsp+170h+ValueName]; ValueName
0x18004735d  mov     r9, rdi; KeyValueInformation
0x180047360  mov     dword ptr [rsp+170h+ResultLength], ebx; Length
0x180047364  mov     r8d, 2; KeyValueInformationClass
0x18004736a  call    cs:__imp_ZwQueryValueKey
0x180047371  nop     dword ptr [rax+rax+00h]
0x180047376  mov     ebx, eax
0x180047378  test    eax, eax
0x18004737a  jns     short loc_1800473E0
0x18004737c  cmp     eax, 0C0000023h
0x180047381  jz      short loc_18004738E
0x180047383  cmp     eax, 80000005h
0x180047388  jnz     loc_18004745D
0x18004738e  mov     rcx, rdi; P
0x180047391  call    BCryptFree
0x180047396  mov     ebx, [rsp+170h+Length]
0x18004739a  mov     ecx, ebx
0x18004739c  call    BCryptAlloc
0x1800473a1  mov     rdi, rax
0x1800473a4  test    rax, rax
0x1800473a7  jz      loc_1800472C3
0x1800473ad  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800473b2  lea     rax, [rsp+170h+Length]
0x1800473b7  mov     [rsp+170h+var_148], rax; ResultLength
0x1800473bc  lea     rdx, [rsp+170h+ValueName]; ValueName
0x1800473c1  mov     r9, rdi; KeyValueInformation
0x1800473c4  mov     dword ptr [rsp+170h+ResultLength], ebx; Length
0x1800473c8  mov     r8d, 2; KeyValueInformationClass
0x1800473ce  call    cs:__imp_ZwQueryValueKey
0x1800473d5  nop     dword ptr [rax+rax+00h]
0x1800473da  mov     ebx, eax
0x1800473dc  test    eax, eax
0x1800473de  js      short loc_18004745D
0x1800473e0  mov     r8d, [rdi+8]
0x1800473e4  lea     rax, [rsp+170h+var_13C]
0x1800473e9  mov     ecx, [rdi+4]
0x1800473ec  lea     rdx, [rdi+0Ch]
0x1800473f0  lea     r9, [rsp+170h+var_130]
0x1800473f5  mov     [rsp+170h+ResultLength], rax
0x1800473fa  call    CfgGppConvertRegDataToMultiString
0x1800473ff  mov     ebx, eax
0x180047401  test    eax, eax
0x180047403  js      short loc_18004745D
0x180047405  mov     rcx, [rsi+r14]; P
0x180047409  call    BCryptFree
0x18004740e  mov     rax, [rsp+170h+var_130]
0x180047413  mov     [rsi+r14], rax
0x180047417  mov     eax, [rsp+170h+var_13C]
0x18004741b  mov     [rsi+r12], eax
0x18004741f  mov     rax, [rbp+70h+KeyInformation]
0x180047423  mov     [rsi+r15], rax
0x180047427  mov     edx, [rsi+r12]
0x18004742b  lea     r9, [rsp+170h+var_128]
0x180047430  mov     rcx, [rsi+r14]; P
0x180047434  xor     r8d, r8d
0x180047437  call    WideMultiString_AllocInit_FromSzMultiString
0x18004743c  test    eax, eax
0x18004743e  jz      short loc_18004744B
0x180047440  mov     ecx, eax; Status
0x180047442  call    WinErrorToNtStatus
0x180047447  mov     ebx, eax
0x180047449  jmp     short loc_180047454
0x18004744b  mov     rax, [rsp+170h+var_128]
0x180047450  mov     [r13+0], rax
0x180047454  test    rdi, rdi
0x180047457  jz      loc_1800472C8
0x18004745d  mov     rcx, rdi; P
0x180047460  call    BCryptFree
0x180047465  jmp     loc_1800472C8
0x18004746a  mov     ebx, 0C0000002h
0x18004746f  jmp     loc_1800472CE
```
