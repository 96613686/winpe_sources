# HvSocketProviderUpdateAddresses

- ea: `0x14002052c`
- end: `0x1400209ab`
- name: `HvSocketProviderUpdateAddresses`
- size: `1151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001b140`

## callees

- `0x140009cf8`
- `0x140009df0`
- `0x14000c0a0`
- `0x14002052c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400207d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400207d3`
- `ntoskrnl!ZwClose` at `0x140020960`
- `ntoskrnl!ZwClose` at `0x140020960`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140020977`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002098e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140020977`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002098e`
- `ntoskrnl!ZwCreateKey` at `0x140020835`
- `ntoskrnl!ZwCreateKey` at `0x140020835`
- `ntoskrnl!RtlStringFromGUID` at `0x1400206f3`
- `ntoskrnl!RtlStringFromGUID` at `0x140020737`
- `ntoskrnl!RtlStringFromGUID` at `0x1400206f3`
- `ntoskrnl!RtlStringFromGUID` at `0x140020737`
- `ntoskrnl!ZwSetValueKey` at `0x14002088c`
- `ntoskrnl!ZwSetValueKey` at `0x1400208dc`
- `ntoskrnl!ZwSetValueKey` at `0x14002088c`
- `ntoskrnl!ZwSetValueKey` at `0x1400208dc`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400207c7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400207c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002078f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002078f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002079f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002079f`

## string_xrefs

- `0x14002071f`: `HvSocketProviderUpdateAddresses`
- `0x14002094b`: `HvSocketProviderUpdateAddresses`
- `0x140020856`: `Failed to open HvSocket Addresses registry key.`
- `0x14002091d`: `Registry expects a null terminated string.`

## pseudocode

```c
__int64 __fastcall HvSocketProviderUpdateAddresses(__int64 a1, const GUID *a2, const GUID *a3)
{
  __int64 v6; // r8
  NTSTATUS v7; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  NTSTATUS v10; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  const GUID *v13; // r9
  GUID v14; // xmm1
  void *KeyHandle; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-41h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-21h] BYREF
  struct _UNICODE_STRING v20; // [rsp+78h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-1h] BYREF

  KeyHandle = 0;
  *(_QWORD *)&ValueName.Length = 1703960;
  ValueName.Buffer = L"LocalAddress";
  *(_QWORD *)&v20.Length = 1835034;
  v20.Buffer = L"ParentAddress";
  GuidString = 0;
  UnicodeString = 0;
  if ( !memcmp(a2, &HV_GUID_ZERO, 0x10u)
    || !memcmp(a2, &HV_GUID_BROADCAST, 0x10u)
    || !memcmp(a2, &HV_GUID_CHILDREN, 0x10u)
    || !memcmp(a2, &HV_GUID_LOOPBACK, 0x10u)
    || !memcmp(a2, &HV_GUID_SILOHOST, 0x10u)
    || !memcmp(a2, &HV_GUID_PARENT, 0x10u) )
  {
    v6 = 3221225793LL;
    v7 = -1073741503;
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_40;
    v8 = "Well known guids are not valid as the provider local address.";
    v9 = 840;
    goto LABEL_39;
  }
  if ( memcmp(a3, &HV_GUID_ZERO, 0x10u)
    && (!memcmp(a3, &HV_GUID_ZERO, 0x10u)
     || !memcmp(a3, &HV_GUID_BROADCAST, 0x10u)
     || !memcmp(a3, &HV_GUID_CHILDREN, 0x10u)
     || !memcmp(a3, &HV_GUID_LOOPBACK, 0x10u)
     || !memcmp(a3, &HV_GUID_SILOHOST, 0x10u)
     || !memcmp(a3, &HV_GUID_PARENT, 0x10u)) )
  {
    v6 = 3221225793LL;
    v7 = -1073741503;
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_40;
    v8 = "Well known guids are not valid as the parent local address.";
    v9 = 849;
LABEL_39:
    HvsocketTraceError("HvSocketProviderUpdateAddresses", v9, v6, v8);
    goto LABEL_40;
  }
  v10 = RtlStringFromGUID(a2, &GuidString);
  v7 = v10;
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_40;
    v11 = (unsigned int)v10;
    v12 = 856;
LABEL_19:
    v13 = a2;
    goto LABEL_20;
  }
  v7 = RtlStringFromGUID(a3, &UnicodeString);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_40;
    v13 = a3;
    v11 = (unsigned int)v7;
    v12 = 863;
LABEL_20:
    HvsocketTraceGuidError("HvSocketProviderUpdateAddresses", v12, v11, v13);
    goto LABEL_40;
  }
  if ( GuidString.MaximumLength < (unsigned __int64)GuidString.Length + 2
    || UnicodeString.MaximumLength < (unsigned __int64)UnicodeString.Length + 2 )
  {
    v6 = 3221225793LL;
    v7 = -1073741503;
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_40;
    v8 = "Registry expects a null terminated string.";
    v9 = 871;
    goto LABEL_39;
  }
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v14 = *a3;
  *(GUID *)(a1 + 1456) = *a2;
  *(GUID *)(a1 + 1472) = v14;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_140013048;
  *(_QWORD *)&ObjectAttributes.Attributes = 704;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 1u, 0);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_40;
    v8 = "Failed to open HvSocket Addresses registry key.";
    v6 = (unsigned int)v7;
    v9 = 897;
    goto LABEL_39;
  }
  v7 = ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, GuidString.Buffer, GuidString.Length + 2);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_40;
    v11 = (unsigned int)v7;
    v12 = 909;
    goto LABEL_19;
  }
  v7 = ZwSetValueKey(KeyHandle, &v20, 0, 1u, UnicodeString.Buffer, UnicodeString.Length + 2);
  if ( v7 < 0 && (unsigned int)dword_140013058 > 2 )
  {
    v13 = a3;
    v11 = (unsigned int)v7;
    v12 = 921;
    goto LABEL_20;
  }
LABEL_40:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002052c  push    rbp
0x14002052e  push    rbx
0x14002052f  push    rsi
0x140020530  push    rdi
0x140020531  push    r14
0x140020533  lea     rbp, [rsp-37h]
0x140020538  sub     rsp, 0C0h
0x14002053f  mov     rsi, rdx
0x140020542  mov     [rbp+57h+KeyHandle], 0
0x14002054a  lea     rax, aLocaladdress; "LocalAddress"
0x140020551  mov     qword ptr [rbp+57h+ValueName.Length], 1A0018h
0x140020559  mov     [rbp+57h+ValueName.Buffer], rax
0x14002055d  lea     rdx, HV_GUID_ZERO; Buf2
0x140020564  lea     rax, aParentaddress; "ParentAddress"
0x14002056b  mov     qword ptr [rbp+57h+var_68.Length], 1C001Ah
0x140020573  mov     rdi, r8
0x140020576  mov     [rbp+57h+var_68.Buffer], rax
0x14002057a  mov     r14, rcx
0x14002057d  xorps   xmm0, xmm0
0x140020580  xorps   xmm1, xmm1
0x140020583  mov     ebx, 10h
0x140020588  mov     r8d, ebx; Size
0x14002058b  mov     rcx, rsi; Buf1
0x14002058e  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x140020592  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x140020596  call    memcmp
0x14002059b  test    eax, eax
0x14002059d  jz      loc_14002092B
0x1400205a3  mov     r8d, ebx; Size
0x1400205a6  lea     rdx, HV_GUID_BROADCAST; Buf2
0x1400205ad  mov     rcx, rsi; Buf1
0x1400205b0  call    memcmp
0x1400205b5  test    eax, eax
0x1400205b7  jz      loc_14002092B
0x1400205bd  mov     r8d, ebx; Size
0x1400205c0  lea     rdx, HV_GUID_CHILDREN; Buf2
0x1400205c7  mov     rcx, rsi; Buf1
0x1400205ca  call    memcmp
0x1400205cf  test    eax, eax
0x1400205d1  jz      loc_14002092B
0x1400205d7  mov     r8d, ebx; Size
0x1400205da  lea     rdx, HV_GUID_LOOPBACK; Buf2
0x1400205e1  mov     rcx, rsi; Buf1
0x1400205e4  call    memcmp
0x1400205e9  test    eax, eax
0x1400205eb  jz      loc_14002092B
0x1400205f1  mov     r8d, ebx; Size
0x1400205f4  lea     rdx, HV_GUID_SILOHOST; Buf2
0x1400205fb  mov     rcx, rsi; Buf1
0x1400205fe  call    memcmp
0x140020603  test    eax, eax
0x140020605  jz      loc_14002092B
0x14002060b  mov     r8d, ebx; Size
0x14002060e  lea     rdx, HV_GUID_PARENT; Buf2
0x140020615  mov     rcx, rsi; Buf1
0x140020618  call    memcmp
0x14002061d  test    eax, eax
0x14002061f  jz      loc_14002092B
0x140020625  mov     r8d, ebx; Size
0x140020628  lea     rdx, HV_GUID_ZERO; Buf2
0x14002062f  mov     rcx, rdi; Buf1
0x140020632  call    memcmp
0x140020637  test    eax, eax
0x140020639  jz      loc_1400206EC
0x14002063f  mov     r8d, ebx; Size
0x140020642  lea     rdx, HV_GUID_ZERO; Buf2
0x140020649  mov     rcx, rdi; Buf1
0x14002064c  call    memcmp
0x140020651  test    eax, eax
0x140020653  jz      short loc_1400206C3
0x140020655  mov     r8d, ebx; Size
0x140020658  lea     rdx, HV_GUID_BROADCAST; Buf2
0x14002065f  mov     rcx, rdi; Buf1
0x140020662  call    memcmp
0x140020667  test    eax, eax
0x140020669  jz      short loc_1400206C3
0x14002066b  mov     r8d, ebx; Size
0x14002066e  lea     rdx, HV_GUID_CHILDREN; Buf2
0x140020675  mov     rcx, rdi; Buf1
0x140020678  call    memcmp
0x14002067d  test    eax, eax
0x14002067f  jz      short loc_1400206C3
0x140020681  mov     r8d, ebx; Size
0x140020684  lea     rdx, HV_GUID_LOOPBACK; Buf2
0x14002068b  mov     rcx, rdi; Buf1
0x14002068e  call    memcmp
0x140020693  test    eax, eax
0x140020695  jz      short loc_1400206C3
0x140020697  mov     r8d, ebx; Size
0x14002069a  lea     rdx, HV_GUID_SILOHOST; Buf2
0x1400206a1  mov     rcx, rdi; Buf1
0x1400206a4  call    memcmp
0x1400206a9  test    eax, eax
0x1400206ab  jz      short loc_1400206C3
0x1400206ad  mov     r8d, ebx; Size
0x1400206b0  lea     rdx, HV_GUID_PARENT; Buf2
0x1400206b7  mov     rcx, rdi; Buf1
0x1400206ba  call    memcmp
0x1400206bf  test    eax, eax
0x1400206c1  jnz     short loc_1400206EC
0x1400206c3  mov     eax, cs:dword_140013058
0x1400206c9  mov     r8d, 0C0000141h
0x1400206cf  mov     ebx, r8d
0x1400206d2  cmp     eax, 2
0x1400206d5  jbe     loc_140020957
0x1400206db  lea     r9, aWellKnownGuids_0; "Well known guids are not valid as the p"...
0x1400206e2  mov     edx, 351h
0x1400206e7  jmp     loc_14002094B
0x1400206ec  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1400206f0  mov     rcx, rsi; Guid
0x1400206f3  call    cs:__imp_RtlStringFromGUID
0x1400206fa  nop     dword ptr [rax+rax+00h]
0x1400206ff  mov     ebx, eax
0x140020701  test    eax, eax
0x140020703  jns     short loc_140020730
0x140020705  mov     ecx, cs:dword_140013058
0x14002070b  cmp     ecx, 2
0x14002070e  jbe     loc_140020957
0x140020714  mov     r8d, eax
0x140020717  mov     edx, 358h
0x14002071c  mov     r9, rsi
0x14002071f  lea     rcx, aHvsocketprovid_1; "HvSocketProviderUpdateAddresses"
0x140020726  call    HvsocketTraceGuidError
0x14002072b  jmp     loc_140020957
0x140020730  lea     rdx, [rbp+57h+UnicodeString]; GuidString
0x140020734  mov     rcx, rdi; Guid
0x140020737  call    cs:__imp_RtlStringFromGUID
0x14002073e  nop     dword ptr [rax+rax+00h]
0x140020743  mov     ebx, eax
0x140020745  test    eax, eax
0x140020747  jns     short loc_140020765
0x140020749  mov     eax, cs:dword_140013058
0x14002074f  cmp     eax, 2
0x140020752  jbe     loc_140020957
0x140020758  mov     r9, rdi
0x14002075b  mov     r8d, ebx
0x14002075e  mov     edx, 35Fh
0x140020763  jmp     short loc_14002071F
0x140020765  movzx   ecx, [rbp+57h+GuidString.Length]
0x140020769  movzx   eax, [rbp+57h+GuidString.MaximumLength]
0x14002076d  add     rcx, 2
0x140020771  cmp     rax, rcx
0x140020774  jb      loc_140020909
0x14002077a  movzx   ecx, [rbp+57h+UnicodeString.Length]
0x14002077e  movzx   eax, [rbp+57h+UnicodeString.MaximumLength]
0x140020782  add     rcx, 2
0x140020786  cmp     rax, rcx
0x140020789  jb      loc_140020909
0x14002078f  call    cs:__imp_KeEnterCriticalRegion
0x140020796  nop     dword ptr [rax+rax+00h]
0x14002079b  lea     rcx, [r14+10h]; FastMutex
0x14002079f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400207a6  nop     dword ptr [rax+rax+00h]
0x1400207ab  movaps  xmm0, xmmword ptr [rsi]
0x1400207ae  lea     rcx, [r14+10h]; FastMutex
0x1400207b2  movaps  xmm1, xmmword ptr [rdi]
0x1400207b5  movdqu  xmmword ptr [r14+5B0h], xmm0
0x1400207be  movdqu  xmmword ptr [r14+5C0h], xmm1
0x1400207c7  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400207ce  nop     dword ptr [rax+rax+00h]
0x1400207d3  call    cs:__imp_KeLeaveCriticalRegion
0x1400207da  nop     dword ptr [rax+rax+00h]
0x1400207df  xor     eax, eax
0x1400207e1  mov     [rsp+0E0h+Disposition], 0; Disposition
0x1400207ea  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400207ee  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400207f2  lea     rax, qword_140013048
0x1400207f9  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140020801  xorps   xmm0, xmm0
0x140020804  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140020808  mov     r14d, 1
0x14002080e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 2C0h
0x140020816  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x14002081b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002081f  xor     r9d, r9d; TitleIndex
0x140020822  mov     [rsp+0E0h+Class], 0; Class
0x14002082b  mov     edx, 2001Fh; DesiredAccess
0x140020830  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140020835  call    cs:__imp_ZwCreateKey
0x14002083c  nop     dword ptr [rax+rax+00h]
0x140020841  mov     ebx, eax
0x140020843  test    eax, eax
0x140020845  jns     short loc_14002086A
0x140020847  mov     eax, cs:dword_140013058
0x14002084d  cmp     eax, 2
0x140020850  jbe     loc_140020957
0x140020856  lea     r9, aFailedToOpenHv; "Failed to open HvSocket Addresses regis"...
0x14002085d  mov     r8d, ebx
0x140020860  mov     edx, 381h
0x140020865  jmp     loc_14002094B
0x14002086a  movzx   eax, [rbp+57h+GuidString.Length]
0x14002086e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140020872  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140020876  add     eax, 2
0x140020879  mov     [rsp+0E0h+CreateOptions], eax; DataSize
0x14002087d  mov     r9d, r14d; Type
0x140020880  mov     rax, [rbp+57h+GuidString.Buffer]
0x140020884  xor     r8d, r8d; TitleIndex
0x140020887  mov     [rsp+0E0h+Class], rax; Data
0x14002088c  call    cs:__imp_ZwSetValueKey
0x140020893  nop     dword ptr [rax+rax+00h]
0x140020898  mov     ebx, eax
0x14002089a  test    eax, eax
0x14002089c  jns     short loc_1400208BA
0x14002089e  mov     eax, cs:dword_140013058
0x1400208a4  cmp     eax, 2
0x1400208a7  jbe     loc_140020957
0x1400208ad  mov     r8d, ebx
0x1400208b0  mov     edx, 38Dh
0x1400208b5  jmp     loc_14002071C
0x1400208ba  movzx   eax, [rbp+57h+UnicodeString.Length]
0x1400208be  lea     rdx, [rbp+57h+var_68]; ValueName
0x1400208c2  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400208c6  add     eax, 2
0x1400208c9  mov     [rsp+0E0h+CreateOptions], eax; DataSize
0x1400208cd  mov     r9d, r14d; Type
0x1400208d0  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x1400208d4  xor     r8d, r8d; TitleIndex
0x1400208d7  mov     [rsp+0E0h+Class], rax; Data
0x1400208dc  call    cs:__imp_ZwSetValueKey
0x1400208e3  nop     dword ptr [rax+rax+00h]
0x1400208e8  mov     ebx, eax
0x1400208ea  test    eax, eax
0x1400208ec  jns     short loc_140020957
0x1400208ee  mov     eax, cs:dword_140013058
0x1400208f4  cmp     eax, 2
0x1400208f7  jbe     short loc_140020957
0x1400208f9  mov     r9, rdi
0x1400208fc  mov     r8d, ebx
0x1400208ff  mov     edx, 399h
0x140020904  jmp     loc_14002071F
0x140020909  mov     eax, cs:dword_140013058
0x14002090f  mov     r8d, 0C0000141h
0x140020915  mov     ebx, r8d
0x140020918  cmp     eax, 2
0x14002091b  jbe     short loc_140020957
0x14002091d  lea     r9, aRegistryExpect; "Registry expects a null terminated stri"...
0x140020924  mov     edx, 367h
0x140020929  jmp     short loc_14002094B
0x14002092b  mov     eax, cs:dword_140013058
0x140020931  mov     r8d, 0C0000141h
0x140020937  mov     ebx, r8d
0x14002093a  cmp     eax, 2
0x14002093d  jbe     short loc_140020957
0x14002093f  lea     r9, aWellKnownGuids; "Well known guids are not valid as the p"...
0x140020946  mov     edx, 348h
0x14002094b  lea     rcx, aHvsocketprovid_1; "HvSocketProviderUpdateAddresses"
0x140020952  call    HvsocketTraceError
0x140020957  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002095b  test    rcx, rcx
0x14002095e  jz      short loc_14002096C
0x140020960  call    cs:__imp_ZwClose
0x140020967  nop     dword ptr [rax+rax+00h]
0x14002096c  cmp     [rbp+57h+GuidString.Buffer], 0
0x140020971  jz      short loc_140020983
0x140020973  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x140020977  call    cs:__imp_RtlFreeUnicodeString
0x14002097e  nop     dword ptr [rax+rax+00h]
0x140020983  cmp     [rbp+57h+UnicodeString.Buffer], 0
0x140020988  jz      short loc_14002099A
0x14002098a  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x14002098e  call    cs:__imp_RtlFreeUnicodeString
0x140020995  nop     dword ptr [rax+rax+00h]
0x14002099a  mov     eax, ebx
0x14002099c  add     rsp, 0C0h
0x1400209a3  pop     r14
0x1400209a5  pop     rdi
0x1400209a6  pop     rsi
0x1400209a7  pop     rbx
0x1400209a8  pop     rbp
0x1400209a9  retn
```
