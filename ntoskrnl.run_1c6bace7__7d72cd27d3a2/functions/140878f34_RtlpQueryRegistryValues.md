# RtlpQueryRegistryValues

- ea: `0x140878f34`
- end: `0x140879459`
- name: `RtlpQueryRegistryValues`
- size: `1317`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, _QWORD *, __int64, ULONG, char)`
- caller_count: `33`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1407558f0`
- `0x140768300`
- `0x14077aa58`
- `0x1407b0d4c`
- `0x1407b0de0`
- `0x1407b1db4`
- `0x1407bcea4`
- `0x1407bd704`
- `0x1407cf488`
- `0x1407d2b08`
- `0x1407d9324`
- `0x1407d9848`
- `0x1407e508c`
- `0x1407e6498`
- `0x1407e6534`
- `0x1408426a0`
- `0x140877ab4`
- `0x140878eb0`
- `0x140878ed0`
- `0x140879fb4`
- `0x1409b85fc`
- `0x1409bb074`
- `0x1409bb5a0`
- `0x140a13b44`
- `0x140a67d30`
- `0x140a73ef8`
- `0x140a74e44`
- `0x140a755b8`
- `0x140a779a8`
- `0x140a88404`
- `0x140adfc3c`
- `0x140ae7d10`
- `0x140b0a484`

## callees

- `0x140387f20`
- `0x140403380`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd640`
- `0x1406dd6c0`
- `0x1406defc0`
- `0x1406eb0e0`
- `0x140878f34`
- `0x140879460`
- `0x1408798f4`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x1408792b6`: `RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n`
- `0x1408793eb`: `RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n`

## pseudocode

```c
__int64 __fastcall RtlpQueryRegistryValues(__int64 a1, const WCHAR *a2, _QWORD *a3, __int64 a4, ULONG a5, char a6)
{
  __int64 v6; // r15
  const WCHAR *v8; // rbx
  int v9; // r14d
  __int64 result; // rax
  int v11; // r14d
  __int64 Pool2; // rax
  __int64 v13; // rdi
  NTSTATUS v14; // ebx
  __int64 Length; // rsi
  int *v16; // r13
  int v17; // eax
  const WCHAR *v18; // rdx
  int v19; // r14d
  NTSTATUS v20; // eax
  int v21; // eax
  __int64 v22; // rsi
  __int64 v23; // rax
  __int64 v24; // r14
  int v25; // r15d
  ULONG i; // esi
  NTSTATUS v27; // eax
  NTSTATUS v28; // eax
  char v29; // al
  int v30; // eax
  __int64 v31; // r14
  __int64 v32; // rax
  int ResultLength; // [rsp+28h] [rbp-71h]
  int ResultLengtha; // [rsp+28h] [rbp-71h]
  HANDLE KeyHandle; // [rsp+40h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-51h] BYREF
  ULONG v37[2]; // [rsp+50h] [rbp-49h]
  UNICODE_STRING ValueName; // [rsp+58h] [rbp-41h] BYREF
  UNICODE_STRING DestinationString; // [rsp+68h] [rbp-31h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  int v41; // [rsp+F0h] [rbp+57h]

  v6 = a4;
  Handle = 0;
  KeyHandle = 0;
  a5 = 0;
  v8 = a2;
  v9 = a1;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  ValueName = 0;
  result = RtlpGetRegistryHandle(a1, a2, 0, &Handle);
  if ( (int)result < 0 )
    return result;
  v11 = v9 & 0x40000000;
  v41 = v11;
  if ( v11 )
    v8 = 0;
  RtlInitUnicodeString(&DestinationString, v8);
  Pool2 = ExAllocatePool2(256, 136, 1987211602);
  v13 = Pool2;
  if ( !Pool2 )
  {
    if ( !v11 )
      ZwClose(Handle);
    return 3221225495LL;
  }
  *(_DWORD *)(Pool2 + 8) = 0;
  v14 = 0;
  LODWORD(Length) = 134;
  *(_QWORD *)v37 = 134;
  KeyHandle = Handle;
LABEL_20:
  v16 = (int *)(a3 + 1);
  if ( !*a3 && (*v16 & 0x21) == 0 )
    goto LABEL_9;
  v17 = *v16;
  if ( (*v16 & 0x20) != 0 && (!a3[2] || (v17 & 1) != 0 || *a3) )
    goto LABEL_48;
  if ( (v17 & 3) != 0 && KeyHandle != Handle )
  {
    ZwClose(KeyHandle);
    KeyHandle = Handle;
  }
  v18 = (const WCHAR *)a3[2];
  if ( (*v16 & 1) != 0 )
  {
    if ( !v18 )
    {
LABEL_48:
      v14 = -1073741811;
      goto LABEL_9;
    }
    RtlInitUnicodeString(&DestinationString, v18);
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v14 = ZwOpenKey(&KeyHandle, 0x2000000u, &ObjectAttributes);
    if ( v14 < 0 )
      goto LABEL_40;
    if ( !*a3 )
      goto LABEL_41;
LABEL_50:
    LODWORD(v24) = v37[0];
    v25 = 0;
    for ( i = 0; ; ++i )
    {
      v27 = ZwEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, (PVOID)v13, v24, &a5);
      v14 = v27;
      if ( v27 == -2147483643 )
      {
        v14 = -1073741789;
      }
      else
      {
        if ( v27 == -2147483622 )
        {
          if ( i || (*v16 & 4) == 0 )
            v14 = 0;
          else
            v14 = -1073741772;
          goto LABEL_40;
        }
        if ( v27 >= 0 )
        {
          a5 = v24;
          v30 = RtlpCallQueryRegistryRoutine(
                  (__int64)KeyHandle,
                  (__int64)a3,
                  (_DWORD *)v13,
                  (int *)&a5,
                  a4,
                  ResultLengtha,
                  a6);
          v14 = v30;
          goto LABEL_70;
        }
      }
      v30 = v14;
LABEL_70:
      if ( v30 == -1073741789 )
      {
        v31 = a5;
        if ( v13 )
          ExFreePoolWithTag((PVOID)v13, 0);
        v32 = ExAllocatePool2(256, v31 + 10, 1987211602);
        v13 = v32;
        if ( !v32 )
        {
LABEL_8:
          v14 = -1073741801;
          goto LABEL_9;
        }
        v14 = 0;
        v24 = v31 + 8;
        *(_DWORD *)(v32 + 8) = 0;
        *(_QWORD *)v37 = v24;
        if ( v25 > 4 )
        {
          DbgPrint("RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n", 1646);
          goto LABEL_41;
        }
        --i;
        ++v25;
      }
      else
      {
        if ( v30 < 0 )
          goto LABEL_40;
        v25 = 0;
        if ( (*v16 & 0x40) != 0 )
        {
          ValueName.Buffer = (wchar_t *)(v13 + 20);
          ValueName.Length = *(_WORD *)(v13 + 16);
          ValueName.MaximumLength = *(_WORD *)(v13 + 16);
          if ( ZwDeleteValueKey(KeyHandle, &ValueName) >= 0 )
            --i;
        }
      }
    }
  }
  if ( v18 )
  {
    RtlInitUnicodeString(&ValueName, v18);
    v19 = 0;
    while ( 1 )
    {
      if ( v19 > 4 )
      {
        DbgPrint("RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n", 1459);
        goto LABEL_9;
      }
      ++v19;
      v20 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, (PVOID)v13, Length, &a5);
      v14 = v20;
      if ( v20 == -2147483643 )
        break;
      if ( v20 >= 0 )
      {
        if ( *(_DWORD *)(v13 + 4) == 7 )
        {
          *(_WORD *)(a5 + v13) = 0;
          *(_DWORD *)(v13 + 12) += 2;
        }
        a5 = Length;
        v21 = RtlpCallQueryRegistryRoutine(
                (__int64)KeyHandle,
                (__int64)a3,
                (_DWORD *)v13,
                (int *)&a5,
                v6,
                ResultLength,
                a6);
        v14 = v21;
        if ( v21 != -1073741789 )
        {
          if ( v21 < 0 )
            goto LABEL_9;
          if ( (*v16 & 0x40) != 0 )
            ZwDeleteValueKey(KeyHandle, &ValueName);
LABEL_41:
          LODWORD(Length) = v37[0];
          a3 += 7;
          v6 = a4;
          goto LABEL_20;
        }
        v22 = a5;
LABEL_43:
        ExFreePoolWithTag((PVOID)v13, 0);
        goto LABEL_44;
      }
      if ( v20 != -1073741772 )
        goto LABEL_62;
      v29 = a6;
      *(_DWORD *)(v13 + 4) = 0;
      *(_DWORD *)(v13 + 12) = 0;
      a5 = Length;
      v28 = RtlpCallQueryRegistryRoutine(
              (__int64)KeyHandle,
              (__int64)a3,
              (_DWORD *)v13,
              (int *)&a5,
              v6,
              ResultLength,
              v29);
      v14 = v28;
LABEL_65:
      if ( v28 != -1073741789 )
        goto LABEL_40;
      v22 = a5;
      if ( v13 )
        goto LABEL_43;
LABEL_44:
      v23 = ExAllocatePool2(256, v22 + 10, 1987211602);
      v13 = v23;
      if ( !v23 )
        goto LABEL_8;
      v14 = 0;
      Length = v22 + 8;
      *(_DWORD *)(v23 + 8) = 0;
      *(_QWORD *)v37 = Length;
    }
    v14 = -1073741789;
LABEL_62:
    v28 = v14;
    goto LABEL_65;
  }
  if ( (*v16 & 8) == 0 )
    goto LABEL_50;
  v14 = guard_dispatch_icall_no_overrides(0, 0, 0);
LABEL_40:
  if ( v14 >= 0 )
    goto LABEL_41;
LABEL_9:
  if ( Handle && !v41 )
    ZwClose(Handle);
  if ( KeyHandle && KeyHandle != Handle )
    ZwClose(KeyHandle);
  if ( v13 )
    ExFreePoolWithTag((PVOID)v13, 0);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140878f34  mov     [rsp-8+arg_8], rbx
0x140878f39  mov     [rsp-8+arg_18], r9
0x140878f3e  push    rbp
0x140878f3f  push    rsi
0x140878f40  push    rdi
0x140878f41  push    r12
0x140878f43  push    r13
0x140878f45  push    r14
0x140878f47  push    r15
0x140878f49  lea     rbp, [rsp-17h]
0x140878f4e  sub     rsp, 0B0h
0x140878f55  xorps   xmm0, xmm0
0x140878f58  xor     esi, esi
0x140878f5a  mov     r15, r9
0x140878f5d  mov     [rbp+47h+Handle], rsi
0x140878f61  mov     r12, r8
0x140878f64  mov     [rbp+47h+KeyHandle], rsi
0x140878f68  xorps   xmm1, xmm1
0x140878f6b  mov     [rbp+47h+arg_20], esi
0x140878f6e  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x140878f72  xor     eax, eax
0x140878f74  lea     r9, [rbp+47h+Handle]
0x140878f78  xor     r8d, r8d
0x140878f7b  mov     rbx, rdx
0x140878f7e  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x140878f82  mov     r14d, ecx
0x140878f85  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x140878f89  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x140878f8d  movups  xmmword ptr [rbp+47h+ValueName.Length], xmm1
0x140878f91  call    RtlpGetRegistryHandle
0x140878f96  test    eax, eax
0x140878f98  js      loc_140879027
0x140878f9e  and     r14d, 40000000h
0x140878fa5  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x140878fa9  mov     [rbp+47h+arg_0], r14d
0x140878fad  cmovnz  rbx, rsi
0x140878fb1  mov     rdx, rbx; SourceString
0x140878fb4  call    RtlInitUnicodeString
0x140878fb9  mov     edx, 88h
0x140878fbe  mov     r8d, 76727152h
0x140878fc4  lea     ecx, [rdx+78h]
0x140878fc7  call    ExAllocatePool2
0x140878fcc  mov     rdi, rax
0x140878fcf  test    rax, rax
0x140878fd2  jnz     short loc_140879043
0x140878fd4  test    r14d, r14d
0x140878fd7  jnz     short loc_140878FE2
0x140878fd9  mov     rcx, [rbp+47h+Handle]; Handle
0x140878fdd  call    ZwClose
0x140878fe2  mov     eax, 0C0000017h
0x140878fe7  jmp     short loc_140879027
0x140878fe9  mov     ebx, 0C0000017h
0x140878fee  mov     rcx, [rbp+47h+Handle]; Handle
0x140878ff2  test    rcx, rcx
0x140878ff5  jz      short loc_140879002
0x140878ff7  cmp     [rbp+47h+arg_0], 0
0x140878ffb  jnz     short loc_140879002
0x140878ffd  call    ZwClose
0x140879002  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x140879006  test    rcx, rcx
0x140879009  jz      short loc_140879016
0x14087900b  cmp     rcx, [rbp+47h+Handle]
0x14087900f  jz      short loc_140879016
0x140879011  call    ZwClose
0x140879016  test    rdi, rdi
0x140879019  jz      short loc_140879025
0x14087901b  xor     edx, edx; Tag
0x14087901d  mov     rcx, rdi; P
0x140879020  call    ExFreePoolWithTag
0x140879025  mov     eax, ebx
0x140879027  mov     rbx, [rsp+0E0h+arg_8]
0x14087902f  add     rsp, 0B0h
0x140879036  pop     r15
0x140879038  pop     r14
0x14087903a  pop     r13
0x14087903c  pop     r12
0x14087903e  pop     rdi
0x14087903f  pop     rsi
0x140879040  pop     rbp
0x140879041  retn
0x140879043  mov     [rax+8], esi
0x140879046  mov     ebx, esi
0x140879048  mov     rax, [rbp+47h+Handle]
0x14087904c  mov     esi, 86h
0x140879051  mov     qword ptr [rbp+47h+var_90], rsi
0x140879055  mov     [rbp+47h+KeyHandle], rax
0x140879059  mov     rcx, [r12]
0x14087905d  lea     r13, [r12+8]
0x140879062  test    rcx, rcx
0x140879065  jz      loc_140879210
0x14087906b  mov     eax, [r13+0]
0x14087906f  test    al, 20h
0x140879071  jz      short loc_140879090
0x140879073  cmp     qword ptr [r12+10h], 0
0x140879079  jz      loc_140879221
0x14087907f  test    al, 1
0x140879081  jnz     loc_140879221
0x140879087  test    rcx, rcx
0x14087908a  jnz     loc_140879221
0x140879090  test    al, 3
0x140879092  jnz     loc_140879291
0x140879098  mov     eax, [r13+0]
0x14087909c  mov     rdx, [r12+10h]; SourceString
0x1408790a1  test    al, 1
0x1408790a3  jnz     loc_140879164
0x1408790a9  test    rdx, rdx
0x1408790ac  jz      loc_14087922B
0x1408790b2  lea     rcx, [rbp+47h+ValueName]; DestinationString
0x1408790b6  call    RtlInitUnicodeString
0x1408790bb  xor     r14d, r14d
0x1408790be  cmp     r14d, 4
0x1408790c2  jg      loc_1408792B1
0x1408790c8  mov     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x1408790cc  lea     rax, [rbp+47h+arg_20]
0x1408790d0  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1408790d5  lea     rdx, [rbp+47h+ValueName]; ValueName
0x1408790d9  mov     r9, rdi; KeyValueInformation
0x1408790dc  mov     [rsp+0E0h+Length], esi; Length
0x1408790e0  mov     r8d, 1; KeyValueInformationClass
0x1408790e6  inc     r14d
0x1408790e9  call    ZwQueryValueKey
0x1408790ee  mov     ebx, eax
0x1408790f0  cmp     eax, 80000005h
0x1408790f5  jz      loc_1408792F0
0x1408790fb  test    eax, eax
0x1408790fd  js      loc_1408792F9
0x140879103  cmp     dword ptr [rdi+4], 7
0x140879107  jnz     short loc_140879116
0x140879109  mov     ecx, [rbp+47h+arg_20]
0x14087910c  xor     eax, eax
0x14087910e  mov     [rcx+rdi], ax
0x140879112  add     dword ptr [rdi+0Ch], 2
0x140879116  mov     al, [rbp+47h+arg_28]
0x140879119  lea     r9, [rbp+47h+arg_20]
0x14087911d  mov     rcx, [rbp+47h+KeyHandle]
0x140879121  mov     r8, rdi
0x140879124  mov     [rsp+0E0h+var_B0], al
0x140879128  mov     rdx, r12
0x14087912b  mov     qword ptr [rsp+0E0h+Length], r15
0x140879130  mov     [rbp+47h+arg_20], esi
0x140879133  call    RtlpCallQueryRegistryRoutine
0x140879138  mov     ebx, eax
0x14087913a  cmp     eax, 0C0000023h
0x14087913f  jz      loc_1408791D1
0x140879145  test    eax, eax
0x140879147  js      loc_140878FEE
0x14087914d  mov     eax, [r13+0]
0x140879151  test    al, 40h
0x140879153  jz      short loc_1408791C0
0x140879155  mov     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x140879159  lea     rdx, [rbp+47h+ValueName]; ValueName
0x14087915d  call    ZwDeleteValueKey
0x140879162  jmp     short loc_1408791C0
0x140879164  test    rdx, rdx
0x140879167  jz      loc_140879221
0x14087916d  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x140879171  call    RtlInitUnicodeString
0x140879176  mov     rax, [rbp+47h+Handle]
0x14087917a  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14087917e  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x140879182  lea     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x140879186  lea     rax, [rbp+47h+DestinationString]
0x14087918a  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x140879191  xorps   xmm0, xmm0
0x140879194  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x140879198  mov     edx, 2000000h; DesiredAccess
0x14087919d  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x1408791a4  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1408791a9  call    ZwOpenKey
0x1408791ae  mov     ebx, eax
0x1408791b0  test    eax, eax
0x1408791b2  jns     loc_140879285
0x1408791b8  test    ebx, ebx
0x1408791ba  js      loc_140878FEE
0x1408791c0  mov     rsi, qword ptr [rbp+47h+var_90]
0x1408791c4  add     r12, 38h ; '8'
0x1408791c8  mov     r15, [rbp+47h+arg_18]
0x1408791cc  jmp     loc_140879059
0x1408791d1  mov     esi, [rbp+47h+arg_20]
0x1408791d4  xor     edx, edx; Tag
0x1408791d6  mov     rcx, rdi; P
0x1408791d9  call    ExFreePoolWithTag
0x1408791de  mov     r8d, 76727152h
0x1408791e4  lea     rdx, [rsi+0Ah]
0x1408791e8  mov     ecx, 100h
0x1408791ed  call    ExAllocatePool2
0x1408791f2  mov     rdi, rax
0x1408791f5  test    rax, rax
0x1408791f8  jz      loc_140878FE9
0x1408791fe  xor     ebx, ebx
0x140879200  add     rsi, 8
0x140879204  mov     [rax+8], ebx
0x140879207  mov     qword ptr [rbp+47h+var_90], rsi
0x14087920b  jmp     loc_1408790BE
0x140879210  mov     eax, [r13+0]
0x140879214  test    al, 21h
0x140879216  jnz     loc_14087906B
0x14087921c  jmp     loc_140878FEE
0x140879221  mov     ebx, 0C000000Dh
0x140879226  jmp     loc_140878FEE
0x14087922b  test    al, 8
0x14087922d  jnz     loc_1408792C7
0x140879233  mov     r14, qword ptr [rbp+47h+var_90]
0x140879237  xor     r15d, r15d
0x14087923a  xor     esi, esi
0x14087923c  mov     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x140879240  lea     rax, [rbp+47h+arg_20]
0x140879244  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x140879249  mov     r9, rdi; KeyValueInformation
0x14087924c  mov     r8d, 1; KeyValueInformationClass
0x140879252  mov     [rsp+0E0h+Length], r14d; Length
0x140879257  mov     edx, esi; Index
0x140879259  call    ZwEnumerateValueKey
0x14087925e  mov     ebx, eax
0x140879260  cmp     eax, 80000005h
0x140879265  jz      loc_140879403
0x14087926b  cmp     eax, 8000001Ah
0x140879270  jnz     loc_14087934E
0x140879276  test    esi, esi
0x140879278  jz      loc_140879443
0x14087927e  xor     ebx, ebx
0x140879280  jmp     loc_1408791B8
0x140879285  cmp     qword ptr [r12], 0
0x14087928a  jnz     short loc_140879233
0x14087928c  jmp     loc_1408791C0
0x140879291  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x140879295  cmp     rcx, [rbp+47h+Handle]
0x140879299  jz      loc_140879098
0x14087929f  call    ZwClose
0x1408792a4  mov     rax, [rbp+47h+Handle]
0x1408792a8  mov     [rbp+47h+KeyHandle], rax
0x1408792ac  jmp     loc_140879098
0x1408792b1  mov     edx, 5B3h
0x1408792b6  lea     rcx, aRtlpqueryregis; "RtlpQueryRegistryValues: Miscomputed bu"...
0x1408792bd  call    DbgPrint
0x1408792c2  jmp     loc_140878FEE
0x1408792c7  mov     rcx, [r12+18h]
0x1408792cc  xor     r9d, r9d
0x1408792cf  mov     rax, [r12]
0x1408792d3  xor     r8d, r8d
0x1408792d6  mov     [rsp+0E0h+ResultLength], rcx
0x1408792db  xor     edx, edx
0x1408792dd  xor     ecx, ecx
0x1408792df  mov     qword ptr [rsp+0E0h+Length], r15
0x1408792e4  call    _guard_dispatch_icall_no_overrides
0x1408792e9  mov     ebx, eax
0x1408792eb  jmp     loc_1408791B8
0x1408792f0  mov     ebx, 0C0000023h
0x1408792f5  mov     eax, ebx
0x1408792f7  jmp     short loc_140879332
0x1408792f9  cmp     eax, 0C0000034h
0x1408792fe  jnz     short loc_1408792F5
0x140879300  mov     al, [rbp+47h+arg_28]
0x140879303  lea     r9, [rbp+47h+arg_20]
0x140879307  mov     dword ptr [rdi+4], 0
0x14087930e  mov     r8, rdi
0x140879311  mov     dword ptr [rdi+0Ch], 0
0x140879318  mov     rdx, r12
0x14087931b  mov     rcx, [rbp+47h+KeyHandle]
0x14087931f  mov     [rsp+0E0h+var_B0], al
0x140879323  mov     qword ptr [rsp+0E0h+Length], r15
0x140879328  mov     [rbp+47h+arg_20], esi
0x14087932b  call    RtlpCallQueryRegistryRoutine
0x140879330  mov     ebx, eax
0x140879332  cmp     eax, 0C0000023h
0x140879337  jnz     loc_1408791B8
0x14087933d  mov     esi, [rbp+47h+arg_20]
0x140879340  test    rdi, rdi
0x140879343  jnz     loc_1408791D4
0x140879349  jmp     loc_1408791DE
0x14087934e  test    eax, eax
0x140879350  js      loc_140879408
0x140879356  mov     al, [rbp+47h+arg_28]
0x140879359  lea     r9, [rbp+47h+arg_20]
0x14087935d  mov     rcx, [rbp+47h+KeyHandle]
0x140879361  mov     r8, rdi
0x140879364  mov     [rsp+0E0h+var_B0], al
0x140879368  mov     rdx, r12
0x14087936b  mov     rax, [rbp+47h+arg_18]
0x14087936f  mov     qword ptr [rsp+0E0h+Length], rax
0x140879374  mov     [rbp+47h+arg_20], r14d
0x140879378  call    RtlpCallQueryRegistryRoutine
0x14087937d  mov     ebx, eax
0x14087937f  cmp     eax, 0C0000023h
0x140879384  jz      short loc_1408793A0
0x140879386  test    eax, eax
0x140879388  js      loc_1408791B8
0x14087938e  mov     eax, [r13+0]
0x140879392  xor     r15d, r15d
0x140879395  test    al, 40h
0x140879397  jnz     short loc_14087940F
0x140879399  inc     esi
0x14087939b  jmp     loc_14087923C
0x1408793a0  mov     r14d, [rbp+47h+arg_20]
0x1408793a4  test    rdi, rdi
0x1408793a7  jz      short loc_1408793B3
0x1408793a9  xor     edx, edx; Tag
0x1408793ab  mov     rcx, rdi; P
0x1408793ae  call    ExFreePoolWithTag
0x1408793b3  mov     r8d, 76727152h
  ... truncated ...
```
