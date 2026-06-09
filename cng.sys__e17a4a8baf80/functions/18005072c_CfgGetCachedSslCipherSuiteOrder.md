# CfgGetCachedSslCipherSuiteOrder

- ea: `0x18005072c`
- end: `0x180050ad4`
- name: `CfgGetCachedSslCipherSuiteOrder`
- size: `936`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e67c`

## callees

- `0x180025ec0`
- `0x180025fb0`
- `0x18002effc`
- `0x180032b10`
- `0x18004e978`
- `0x18005072c`
- `0x18007aedc`
- `0x1800a4232`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800507d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005099d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800507d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005099d`
- `ntoskrnl!ZwQueryValueKey` at `0x1800509ca`
- `ntoskrnl!ZwQueryValueKey` at `0x180050a2e`
- `ntoskrnl!ZwQueryValueKey` at `0x1800509ca`
- `ntoskrnl!ZwQueryValueKey` at `0x180050a2e`
- `ntoskrnl!ZwClose` at `0x180050953`
- `ntoskrnl!ZwClose` at `0x180050953`
- `ntoskrnl!ZwOpenKey` at `0x180050816`
- `ntoskrnl!ZwOpenKey` at `0x180050816`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180050861`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180050861`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800508e4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800508e4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180050872`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180050872`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800508d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x180050931`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800508d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x180050931`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005093d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005093d`
- `ntoskrnl!ZwQueryKey` at `0x180050844`
- `ntoskrnl!ZwQueryKey` at `0x180050844`

## string_xrefs

- `0x18005087e`: `\Registry\Machine\Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002\`
- `0x18005089f`: `\Registry\Machine\System\CurrentControlSet\Control\Cryptography\MDMPolicies\SSL\`

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
0x18005072c  mov     [rsp-8+arg_18], rbx
0x180050731  push    rbp
0x180050732  push    rsi
0x180050733  push    rdi
0x180050734  push    r12
0x180050736  push    r13
0x180050738  push    r14
0x18005073a  push    r15
0x18005073c  lea     rbp, [rsp-40h]
0x180050741  sub     rsp, 140h
0x180050748  mov     rax, cs:__security_cookie
0x18005074f  xor     rax, rsp
0x180050752  mov     [rbp+70h+var_40], rax
0x180050756  xorps   xmm1, xmm1
0x180050759  mov     [rsp+170h+SourceString], rdx
0x18005075e  mov     r13, r8
0x180050761  mov     [rsp+170h+KeyHandle], 0
0x18005076a  mov     rdi, rcx
0x18005076d  mov     [rsp+170h+Length], 0
0x180050775  xorps   xmm0, xmm0
0x180050778  lea     rcx, [rbp+70h+KeyInformation]; void *
0x18005077c  mov     r15d, 80h
0x180050782  xor     edx, edx; Val
0x180050784  mov     r8d, r15d; Size
0x180050787  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x18005078c  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm1
0x180050791  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm1
0x180050795  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm1
0x180050799  call    memset
0x18005079e  mov     [rsp+170h+var_128], 0
0x1800507a7  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x1800507ac  mov     rsi, rax
0x1800507af  mov     r14d, 0C0000023h
0x1800507b5  test    r13, r13
0x1800507b8  jnz     short loc_1800507C3
0x1800507ba  lea     ebx, [r14-16h]
0x1800507be  jmp     loc_180050949
0x1800507c3  mov     rdx, rdi; SourceString
0x1800507c6  mov     qword ptr [r13+0], 0
0x1800507ce  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1800507d3  call    cs:__imp_RtlInitUnicodeString
0x1800507da  nop     dword ptr [rax+rax+00h]
0x1800507df  lea     rax, [rsp+170h+DestinationString]
0x1800507e4  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1800507ec  xorps   xmm0, xmm0
0x1800507ef  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x1800507f3  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1800507f8  mov     [rbp+70h+ObjectAttributes.RootDirectory], 0
0x180050800  mov     edx, 1; DesiredAccess
0x180050805  mov     [rbp+70h+ObjectAttributes.Attributes], 240h
0x18005080c  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180050811  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x180050816  call    cs:__imp_ZwOpenKey
0x18005081d  nop     dword ptr [rax+rax+00h]
0x180050822  mov     ebx, eax
0x180050824  test    eax, eax
0x180050826  js      loc_180050949
0x18005082c  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180050831  lea     rax, [rsp+170h+Length]
0x180050836  mov     r9d, r15d; Length
0x180050839  mov     [rsp+170h+ResultLength], rax; ResultLength
0x18005083e  lea     r8, [rbp+70h+KeyInformation]; KeyInformation
0x180050842  xor     edx, edx; KeyInformationClass
0x180050844  call    cs:__imp_ZwQueryKey
0x18005084b  nop     dword ptr [rax+rax+00h]
0x180050850  mov     ebx, eax
0x180050852  test    eax, eax
0x180050854  js      loc_180050949
0x18005085a  add     rsi, 110h
0x180050861  call    cs:__imp_KeEnterCriticalRegion
0x180050868  nop     dword ptr [rax+rax+00h]
0x18005086d  mov     dl, 1; Wait
0x18005086f  mov     rcx, rsi; Resource
0x180050872  call    cs:__imp_ExAcquireResourceSharedLite
0x180050879  nop     dword ptr [rax+rax+00h]
0x18005087e  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\Software\\Policies"...
0x180050885  mov     rcx, rdi; Str1
0x180050888  call    wcscmp_0
0x18005088d  test    eax, eax
0x18005088f  jnz     short loc_18005089F
0x180050891  lea     r15d, [rax+68h]
0x180050895  lea     r14d, [rax+70h]
0x180050899  lea     r12d, [rax+78h]
0x18005089d  jmp     short loc_1800508C0
0x18005089f  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800508a6  mov     rcx, rdi; Str1
0x1800508a9  call    wcscmp_0
0x1800508ae  test    eax, eax
0x1800508b0  jnz     loc_180050ACA
0x1800508b6  mov     r14d, 88h
0x1800508bc  lea     r12d, [r14+8]
0x1800508c0  mov     rax, [rsi+r15]
0x1800508c4  xor     edi, edi
0x1800508c6  cmp     [rbp+70h+KeyInformation], rax
0x1800508ca  jle     loc_180050A87
0x1800508d0  mov     rcx, rsi; Resource
0x1800508d3  call    cs:__imp_ExReleaseResourceLite
0x1800508da  nop     dword ptr [rax+rax+00h]
0x1800508df  mov     dl, 1; Wait
0x1800508e1  mov     rcx, rsi; Resource
0x1800508e4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800508eb  nop     dword ptr [rax+rax+00h]
0x1800508f0  mov     rax, [rsi+r15]
0x1800508f4  cmp     [rbp+70h+KeyInformation], rax
0x1800508f8  jle     loc_180050A87
0x1800508fe  xorps   xmm0, xmm0
0x180050901  mov     [rsp+170h+var_130], rdi
0x180050906  mov     ebx, 800h
0x18005090b  mov     [rsp+170h+var_13C], edi
0x18005090f  mov     ecx, ebx
0x180050911  movups  xmmword ptr [rsp+170h+ValueName.Length], xmm0
0x180050916  call    BCryptAlloc
0x18005091b  mov     rdi, rax
0x18005091e  test    rax, rax
0x180050921  jnz     short loc_180050993
0x180050923  mov     ebx, 0C000009Ah
0x180050928  mov     r14d, 0C0000023h
0x18005092e  mov     rcx, rsi; Resource
0x180050931  call    cs:__imp_ExReleaseResourceLite
0x180050938  nop     dword ptr [rax+rax+00h]
0x18005093d  call    cs:__imp_KeLeaveCriticalRegion
0x180050944  nop     dword ptr [rax+rax+00h]
0x180050949  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x18005094e  test    rcx, rcx
0x180050951  jz      short loc_18005095F
0x180050953  call    cs:__imp_ZwClose
0x18005095a  nop     dword ptr [rax+rax+00h]
0x18005095f  cmp     ebx, 80000005h
0x180050965  cmovz   ebx, r14d
0x180050969  mov     eax, ebx
0x18005096b  mov     rcx, [rbp+70h+var_40]
0x18005096f  xor     rcx, rsp; StackCookie
0x180050972  call    __security_check_cookie
0x180050977  mov     rbx, [rsp+170h+arg_18]
0x18005097f  add     rsp, 140h
0x180050986  pop     r15
0x180050988  pop     r14
0x18005098a  pop     r13
0x18005098c  pop     r12
0x18005098e  pop     rdi
0x18005098f  pop     rsi
0x180050990  pop     rbp
0x180050991  retn
0x180050993  mov     rdx, [rsp+170h+SourceString]; SourceString
0x180050998  lea     rcx, [rsp+170h+ValueName]; DestinationString
0x18005099d  call    cs:__imp_RtlInitUnicodeString
0x1800509a4  nop     dword ptr [rax+rax+00h]
0x1800509a9  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800509ae  lea     rax, [rsp+170h+Length]
0x1800509b3  mov     [rsp+170h+var_148], rax; ResultLength
0x1800509b8  lea     rdx, [rsp+170h+ValueName]; ValueName
0x1800509bd  mov     r9, rdi; KeyValueInformation
0x1800509c0  mov     dword ptr [rsp+170h+ResultLength], ebx; Length
0x1800509c4  mov     r8d, 2; KeyValueInformationClass
0x1800509ca  call    cs:__imp_ZwQueryValueKey
0x1800509d1  nop     dword ptr [rax+rax+00h]
0x1800509d6  mov     ebx, eax
0x1800509d8  test    eax, eax
0x1800509da  jns     short loc_180050A40
0x1800509dc  cmp     eax, 0C0000023h
0x1800509e1  jz      short loc_1800509EE
0x1800509e3  cmp     eax, 80000005h
0x1800509e8  jnz     loc_180050ABD
0x1800509ee  mov     rcx, rdi; P
0x1800509f1  call    BCryptFree
0x1800509f6  mov     ebx, [rsp+170h+Length]
0x1800509fa  mov     ecx, ebx
0x1800509fc  call    BCryptAlloc
0x180050a01  mov     rdi, rax
0x180050a04  test    rax, rax
0x180050a07  jz      loc_180050923
0x180050a0d  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180050a12  lea     rax, [rsp+170h+Length]
0x180050a17  mov     [rsp+170h+var_148], rax; ResultLength
0x180050a1c  lea     rdx, [rsp+170h+ValueName]; ValueName
0x180050a21  mov     r9, rdi; KeyValueInformation
0x180050a24  mov     dword ptr [rsp+170h+ResultLength], ebx; Length
0x180050a28  mov     r8d, 2; KeyValueInformationClass
0x180050a2e  call    cs:__imp_ZwQueryValueKey
0x180050a35  nop     dword ptr [rax+rax+00h]
0x180050a3a  mov     ebx, eax
0x180050a3c  test    eax, eax
0x180050a3e  js      short loc_180050ABD
0x180050a40  mov     r8d, [rdi+8]
0x180050a44  lea     rax, [rsp+170h+var_13C]
0x180050a49  mov     ecx, [rdi+4]
0x180050a4c  lea     rdx, [rdi+0Ch]
0x180050a50  lea     r9, [rsp+170h+var_130]
0x180050a55  mov     [rsp+170h+ResultLength], rax
0x180050a5a  call    CfgGppConvertRegDataToMultiString
0x180050a5f  mov     ebx, eax
0x180050a61  test    eax, eax
0x180050a63  js      short loc_180050ABD
0x180050a65  mov     rcx, [rsi+r14]; P
0x180050a69  call    BCryptFree
0x180050a6e  mov     rax, [rsp+170h+var_130]
0x180050a73  mov     [rsi+r14], rax
0x180050a77  mov     eax, [rsp+170h+var_13C]
0x180050a7b  mov     [rsi+r12], eax
0x180050a7f  mov     rax, [rbp+70h+KeyInformation]
0x180050a83  mov     [rsi+r15], rax
0x180050a87  mov     edx, [rsi+r12]
0x180050a8b  lea     r9, [rsp+170h+var_128]
0x180050a90  mov     rcx, [rsi+r14]; P
0x180050a94  xor     r8d, r8d
0x180050a97  call    WideMultiString_AllocInit_FromSzMultiString
0x180050a9c  test    eax, eax
0x180050a9e  jz      short loc_180050AAB
0x180050aa0  mov     ecx, eax; Status
0x180050aa2  call    WinErrorToNtStatus
0x180050aa7  mov     ebx, eax
0x180050aa9  jmp     short loc_180050AB4
0x180050aab  mov     rax, [rsp+170h+var_128]
0x180050ab0  mov     [r13+0], rax
0x180050ab4  test    rdi, rdi
0x180050ab7  jz      loc_180050928
0x180050abd  mov     rcx, rdi; P
0x180050ac0  call    BCryptFree
0x180050ac5  jmp     loc_180050928
0x180050aca  mov     ebx, 0C0000002h
0x180050acf  jmp     loc_18005092E
```
