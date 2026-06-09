# CfgGetCachedSslCipherSuiteOrder

- ea: `0x18004663c`
- end: `0x1800469e4`
- name: `CfgGetCachedSslCipherSuiteOrder`
- size: `936`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002454c`

## callees

- `0x18001bd90`
- `0x18001be80`
- `0x180024ecc`
- `0x1800289e0`
- `0x180044888`
- `0x18004663c`
- `0x180070d3c`
- `0x18009d746`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800466e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800468ad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800466e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800468ad`
- `ntoskrnl!ZwQueryValueKey` at `0x1800468da`
- `ntoskrnl!ZwQueryValueKey` at `0x18004693e`
- `ntoskrnl!ZwQueryValueKey` at `0x1800468da`
- `ntoskrnl!ZwQueryValueKey` at `0x18004693e`
- `ntoskrnl!ZwClose` at `0x180046863`
- `ntoskrnl!ZwClose` at `0x180046863`
- `ntoskrnl!ZwOpenKey` at `0x180046726`
- `ntoskrnl!ZwOpenKey` at `0x180046726`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180046771`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180046771`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800467f4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800467f4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180046782`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180046782`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800467e3`
- `ntoskrnl!ExReleaseResourceLite` at `0x180046841`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800467e3`
- `ntoskrnl!ExReleaseResourceLite` at `0x180046841`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004684d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004684d`
- `ntoskrnl!ZwQueryKey` at `0x180046754`
- `ntoskrnl!ZwQueryKey` at `0x180046754`

## string_xrefs

- `0x18004678e`: `\Registry\Machine\Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002\`
- `0x1800467af`: `\Registry\Machine\System\CurrentControlSet\Control\Cryptography\MDMPolicies\SSL\`

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
0x18004663c  mov     [rsp-8+arg_18], rbx
0x180046641  push    rbp
0x180046642  push    rsi
0x180046643  push    rdi
0x180046644  push    r12
0x180046646  push    r13
0x180046648  push    r14
0x18004664a  push    r15
0x18004664c  lea     rbp, [rsp-40h]
0x180046651  sub     rsp, 140h
0x180046658  mov     rax, cs:__security_cookie
0x18004665f  xor     rax, rsp
0x180046662  mov     [rbp+70h+var_40], rax
0x180046666  xorps   xmm1, xmm1
0x180046669  mov     [rsp+170h+SourceString], rdx
0x18004666e  mov     r13, r8
0x180046671  mov     [rsp+170h+KeyHandle], 0
0x18004667a  mov     rdi, rcx
0x18004667d  mov     [rsp+170h+Length], 0
0x180046685  xorps   xmm0, xmm0
0x180046688  lea     rcx, [rbp+70h+KeyInformation]; void *
0x18004668c  mov     r15d, 80h
0x180046692  xor     edx, edx; Val
0x180046694  mov     r8d, r15d; Size
0x180046697  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x18004669c  movups  xmmword ptr [rsp+170h+ObjectAttributes.Length], xmm1
0x1800466a1  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm1
0x1800466a5  movups  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800466a9  call    memset
0x1800466ae  mov     [rsp+170h+var_128], 0
0x1800466b7  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x1800466bc  mov     rsi, rax
0x1800466bf  mov     r14d, 0C0000023h
0x1800466c5  test    r13, r13
0x1800466c8  jnz     short loc_1800466D3
0x1800466ca  lea     ebx, [r14-16h]
0x1800466ce  jmp     loc_180046859
0x1800466d3  mov     rdx, rdi; SourceString
0x1800466d6  mov     qword ptr [r13+0], 0
0x1800466de  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1800466e3  call    cs:__imp_RtlInitUnicodeString
0x1800466ea  nop     dword ptr [rax+rax+00h]
0x1800466ef  lea     rax, [rsp+170h+DestinationString]
0x1800466f4  mov     [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1800466fc  xorps   xmm0, xmm0
0x1800466ff  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x180046703  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x180046708  mov     [rbp+70h+ObjectAttributes.RootDirectory], 0
0x180046710  mov     edx, 1; DesiredAccess
0x180046715  mov     [rbp+70h+ObjectAttributes.Attributes], 240h
0x18004671c  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180046721  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x180046726  call    cs:__imp_ZwOpenKey
0x18004672d  nop     dword ptr [rax+rax+00h]
0x180046732  mov     ebx, eax
0x180046734  test    eax, eax
0x180046736  js      loc_180046859
0x18004673c  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180046741  lea     rax, [rsp+170h+Length]
0x180046746  mov     r9d, r15d; Length
0x180046749  mov     [rsp+170h+ResultLength], rax; ResultLength
0x18004674e  lea     r8, [rbp+70h+KeyInformation]; KeyInformation
0x180046752  xor     edx, edx; KeyInformationClass
0x180046754  call    cs:__imp_ZwQueryKey
0x18004675b  nop     dword ptr [rax+rax+00h]
0x180046760  mov     ebx, eax
0x180046762  test    eax, eax
0x180046764  js      loc_180046859
0x18004676a  add     rsi, 110h
0x180046771  call    cs:__imp_KeEnterCriticalRegion
0x180046778  nop     dword ptr [rax+rax+00h]
0x18004677d  mov     dl, 1; Wait
0x18004677f  mov     rcx, rsi; Resource
0x180046782  call    cs:__imp_ExAcquireResourceSharedLite
0x180046789  nop     dword ptr [rax+rax+00h]
0x18004678e  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\Software\\Policies"...
0x180046795  mov     rcx, rdi; Str1
0x180046798  call    wcscmp_0
0x18004679d  test    eax, eax
0x18004679f  jnz     short loc_1800467AF
0x1800467a1  lea     r15d, [rax+68h]
0x1800467a5  lea     r14d, [rax+70h]
0x1800467a9  lea     r12d, [rax+78h]
0x1800467ad  jmp     short loc_1800467D0
0x1800467af  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800467b6  mov     rcx, rdi; Str1
0x1800467b9  call    wcscmp_0
0x1800467be  test    eax, eax
0x1800467c0  jnz     loc_1800469DA
0x1800467c6  mov     r14d, 88h
0x1800467cc  lea     r12d, [r14+8]
0x1800467d0  mov     rax, [rsi+r15]
0x1800467d4  xor     edi, edi
0x1800467d6  cmp     [rbp+70h+KeyInformation], rax
0x1800467da  jle     loc_180046997
0x1800467e0  mov     rcx, rsi; Resource
0x1800467e3  call    cs:__imp_ExReleaseResourceLite
0x1800467ea  nop     dword ptr [rax+rax+00h]
0x1800467ef  mov     dl, 1; Wait
0x1800467f1  mov     rcx, rsi; Resource
0x1800467f4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800467fb  nop     dword ptr [rax+rax+00h]
0x180046800  mov     rax, [rsi+r15]
0x180046804  cmp     [rbp+70h+KeyInformation], rax
0x180046808  jle     loc_180046997
0x18004680e  xorps   xmm0, xmm0
0x180046811  mov     [rsp+170h+var_130], rdi
0x180046816  mov     ebx, 800h
0x18004681b  mov     [rsp+170h+var_13C], edi
0x18004681f  mov     ecx, ebx
0x180046821  movups  xmmword ptr [rsp+170h+ValueName.Length], xmm0
0x180046826  call    BCryptAlloc
0x18004682b  mov     rdi, rax
0x18004682e  test    rax, rax
0x180046831  jnz     short loc_1800468A3
0x180046833  mov     ebx, 0C000009Ah
0x180046838  mov     r14d, 0C0000023h
0x18004683e  mov     rcx, rsi; Resource
0x180046841  call    cs:__imp_ExReleaseResourceLite
0x180046848  nop     dword ptr [rax+rax+00h]
0x18004684d  call    cs:__imp_KeLeaveCriticalRegion
0x180046854  nop     dword ptr [rax+rax+00h]
0x180046859  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x18004685e  test    rcx, rcx
0x180046861  jz      short loc_18004686F
0x180046863  call    cs:__imp_ZwClose
0x18004686a  nop     dword ptr [rax+rax+00h]
0x18004686f  cmp     ebx, 80000005h
0x180046875  cmovz   ebx, r14d
0x180046879  mov     eax, ebx
0x18004687b  mov     rcx, [rbp+70h+var_40]
0x18004687f  xor     rcx, rsp; StackCookie
0x180046882  call    __security_check_cookie
0x180046887  mov     rbx, [rsp+170h+arg_18]
0x18004688f  add     rsp, 140h
0x180046896  pop     r15
0x180046898  pop     r14
0x18004689a  pop     r13
0x18004689c  pop     r12
0x18004689e  pop     rdi
0x18004689f  pop     rsi
0x1800468a0  pop     rbp
0x1800468a1  retn
0x1800468a3  mov     rdx, [rsp+170h+SourceString]; SourceString
0x1800468a8  lea     rcx, [rsp+170h+ValueName]; DestinationString
0x1800468ad  call    cs:__imp_RtlInitUnicodeString
0x1800468b4  nop     dword ptr [rax+rax+00h]
0x1800468b9  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1800468be  lea     rax, [rsp+170h+Length]
0x1800468c3  mov     [rsp+170h+var_148], rax; ResultLength
0x1800468c8  lea     rdx, [rsp+170h+ValueName]; ValueName
0x1800468cd  mov     r9, rdi; KeyValueInformation
0x1800468d0  mov     dword ptr [rsp+170h+ResultLength], ebx; Length
0x1800468d4  mov     r8d, 2; KeyValueInformationClass
0x1800468da  call    cs:__imp_ZwQueryValueKey
0x1800468e1  nop     dword ptr [rax+rax+00h]
0x1800468e6  mov     ebx, eax
0x1800468e8  test    eax, eax
0x1800468ea  jns     short loc_180046950
0x1800468ec  cmp     eax, 0C0000023h
0x1800468f1  jz      short loc_1800468FE
0x1800468f3  cmp     eax, 80000005h
0x1800468f8  jnz     loc_1800469CD
0x1800468fe  mov     rcx, rdi; P
0x180046901  call    BCryptFree
0x180046906  mov     ebx, [rsp+170h+Length]
0x18004690a  mov     ecx, ebx
0x18004690c  call    BCryptAlloc
0x180046911  mov     rdi, rax
0x180046914  test    rax, rax
0x180046917  jz      loc_180046833
0x18004691d  mov     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x180046922  lea     rax, [rsp+170h+Length]
0x180046927  mov     [rsp+170h+var_148], rax; ResultLength
0x18004692c  lea     rdx, [rsp+170h+ValueName]; ValueName
0x180046931  mov     r9, rdi; KeyValueInformation
0x180046934  mov     dword ptr [rsp+170h+ResultLength], ebx; Length
0x180046938  mov     r8d, 2; KeyValueInformationClass
0x18004693e  call    cs:__imp_ZwQueryValueKey
0x180046945  nop     dword ptr [rax+rax+00h]
0x18004694a  mov     ebx, eax
0x18004694c  test    eax, eax
0x18004694e  js      short loc_1800469CD
0x180046950  mov     r8d, [rdi+8]
0x180046954  lea     rax, [rsp+170h+var_13C]
0x180046959  mov     ecx, [rdi+4]
0x18004695c  lea     rdx, [rdi+0Ch]
0x180046960  lea     r9, [rsp+170h+var_130]
0x180046965  mov     [rsp+170h+ResultLength], rax
0x18004696a  call    CfgGppConvertRegDataToMultiString
0x18004696f  mov     ebx, eax
0x180046971  test    eax, eax
0x180046973  js      short loc_1800469CD
0x180046975  mov     rcx, [rsi+r14]; P
0x180046979  call    BCryptFree
0x18004697e  mov     rax, [rsp+170h+var_130]
0x180046983  mov     [rsi+r14], rax
0x180046987  mov     eax, [rsp+170h+var_13C]
0x18004698b  mov     [rsi+r12], eax
0x18004698f  mov     rax, [rbp+70h+KeyInformation]
0x180046993  mov     [rsi+r15], rax
0x180046997  mov     edx, [rsi+r12]
0x18004699b  lea     r9, [rsp+170h+var_128]
0x1800469a0  mov     rcx, [rsi+r14]; P
0x1800469a4  xor     r8d, r8d
0x1800469a7  call    WideMultiString_AllocInit_FromSzMultiString
0x1800469ac  test    eax, eax
0x1800469ae  jz      short loc_1800469BB
0x1800469b0  mov     ecx, eax; Status
0x1800469b2  call    WinErrorToNtStatus
0x1800469b7  mov     ebx, eax
0x1800469b9  jmp     short loc_1800469C4
0x1800469bb  mov     rax, [rsp+170h+var_128]
0x1800469c0  mov     [r13+0], rax
0x1800469c4  test    rdi, rdi
0x1800469c7  jz      loc_180046838
0x1800469cd  mov     rcx, rdi; P
0x1800469d0  call    BCryptFree
0x1800469d5  jmp     loc_180046838
0x1800469da  mov     ebx, 0C0000002h
0x1800469df  jmp     loc_18004683E
```
