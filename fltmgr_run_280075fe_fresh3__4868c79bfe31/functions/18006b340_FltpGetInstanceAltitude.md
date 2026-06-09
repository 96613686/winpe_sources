# FltpGetInstanceAltitude

- ea: `0x18006b340`
- end: `0x18006b69c`
- name: `FltpGetInstanceAltitude`
- size: `860`
- prototype: `__int64 __fastcall(__int64, void *, __int64, UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004c810`

## callees

- `0x180009f20`
- `0x180024900`
- `0x18006a860`
- `0x18006b340`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18006b48a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006b5ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006b617`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006b659`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006b48a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006b5ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006b617`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006b659`
- `ntoskrnl!ExAllocatePool2` at `0x18006b3e7`
- `ntoskrnl!ExAllocatePool2` at `0x18006b4a6`
- `ntoskrnl!ExAllocatePool2` at `0x18006b4e4`
- `ntoskrnl!ExAllocatePool2` at `0x18006b5d6`
- `ntoskrnl!ExAllocatePool2` at `0x18006b3e7`
- `ntoskrnl!ExAllocatePool2` at `0x18006b4a6`
- `ntoskrnl!ExAllocatePool2` at `0x18006b4e4`
- `ntoskrnl!ExAllocatePool2` at `0x18006b5d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b418`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b568`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b418`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b568`
- `ntoskrnl!ZwClose` at `0x18006b66e`
- `ntoskrnl!ZwClose` at `0x18006b683`
- `ntoskrnl!ZwClose` at `0x18006b66e`
- `ntoskrnl!ZwClose` at `0x18006b683`
- `ntoskrnl!ZwOpenKey` at `0x18006b547`
- `ntoskrnl!ZwOpenKey` at `0x18006b547`
- `ntoskrnl!ZwQueryValueKey` at `0x18006b448`
- `ntoskrnl!ZwQueryValueKey` at `0x18006b592`
- `ntoskrnl!ZwQueryValueKey` at `0x18006b448`
- `ntoskrnl!ZwQueryValueKey` at `0x18006b592`
- `ntoskrnl!RtlCreateUnicodeString` at `0x18006b5f8`
- `ntoskrnl!RtlCreateUnicodeString` at `0x18006b5f8`

## pseudocode

```c
__int64 __fastcall FltpGetInstanceAltitude(__int64 a1, void *a2, __int64 a3, UNICODE_STRING *a4)
{
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 v6; // rcx
  __int64 v8; // rbx
  ULONG Length; // esi
  _WORD *Pool2; // rdi
  void *v11; // rax
  NTSTATUS v12; // eax
  HANDLE Handle; // [rsp+38h] [rbp-29h] BYREF
  __int64 v15; // [rsp+40h] [rbp-21h] BYREF
  PVOID P; // [rsp+48h] [rbp-19h]
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-11h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-1h] BYREF
  __int64 v19; // [rsp+98h] [rbp+37h]
  __int64 v20; // [rsp+A0h] [rbp+3Fh]
  HANDLE KeyHandle; // [rsp+D0h] [rbp+6Fh] BYREF
  __int64 ResultLength; // [rsp+D8h] [rbp+77h] BYREF

  ResultLength = a3;
  KeyHandle = a2;
  v6 = *(_QWORD *)(a1 + 104);
  v20 = v4;
  v19 = v5;
  KeyHandle = 0;
  Handle = 0;
  v15 = 0;
  LODWORD(ResultLength) = 0;
  P = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v8 = (unsigned int)FltpOpenInstancesRegistryKey(v6, &KeyHandle);
  if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 1262, 3221225524LL) >= 0 )
  {
    Length = 80;
    Pool2 = (_WORD *)ExAllocatePool2(256, 80, 1920224582);
    if ( Pool2 )
    {
      RtlInitUnicodeString(&DestinationString, L"DEFAULTINSTANCE");
      while ( 1 )
      {
        v8 = (unsigned int)ZwQueryValueKey(
                             KeyHandle,
                             &DestinationString,
                             KeyValuePartialInformation,
                             Pool2,
                             Length,
                             (PULONG)&ResultLength);
        if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 1309, 0) >= 0 )
          break;
        if ( (_DWORD)v8 != -1073741789 && (_DWORD)v8 != -2147483643 )
          goto LABEL_21;
        ExFreePoolWithTag(Pool2, 0x72744D46u);
        Length = ResultLength;
        Pool2 = (_WORD *)ExAllocatePool2(256, (unsigned int)ResultLength, 1920224582);
        if ( !Pool2 )
        {
          LODWORD(v8) = -1073741670;
          goto LABEL_22;
        }
      }
      WORD1(v15) = Pool2[4];
      LOWORD(v15) = WORD1(v15) - 2;
      v11 = (void *)ExAllocatePool2(256, WORD1(v15), 1920224582);
      P = v11;
      if ( v11 )
      {
        memmove(v11, Pool2 + 6, (unsigned __int16)v15);
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v15;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        LODWORD(v8) = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( (int)v8 >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, L"ALTITUDE");
          while ( 1 )
          {
            v12 = ZwQueryValueKey(
                    Handle,
                    &DestinationString,
                    KeyValuePartialInformation,
                    Pool2,
                    Length,
                    (PULONG)&ResultLength);
            LODWORD(v8) = v12;
            if ( v12 >= 0 )
              break;
            if ( v12 != -1073741789 && v12 != -2147483643 )
              goto LABEL_21;
            ExFreePoolWithTag(Pool2, 0x72744D46u);
            Length = ResultLength;
            Pool2 = (_WORD *)ExAllocatePool2(256, (unsigned int)ResultLength, 1920224582);
            if ( !Pool2 )
            {
              LODWORD(v8) = -1073741670;
              goto LABEL_22;
            }
          }
          LODWORD(v8) = -1073741670;
          if ( RtlCreateUnicodeString(a4, Pool2 + 6) )
            LODWORD(v8) = 0;
        }
      }
      else
      {
        LODWORD(v8) = -1073741670;
      }
LABEL_21:
      ExFreePoolWithTag(Pool2, 0x72744D46u);
    }
    else
    {
      LODWORD(v8) = -1073741670;
    }
  }
LABEL_22:
  if ( P )
    ExFreePoolWithTag(P, 0x72744D46u);
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006b340  mov     rax, rsp
0x18006b343  mov     [rax+18h], r8
0x18006b347  mov     [rax+10h], rdx
0x18006b34b  push    rbp
0x18006b34c  push    rbx
0x18006b34d  lea     rbp, [rax-5Fh]
0x18006b351  sub     rsp, 0A8h
0x18006b358  mov     rcx, [rcx+68h]
0x18006b35c  lea     rdx, [rbp+57h+KeyHandle]
0x18006b360  xorps   xmm0, xmm0
0x18006b363  mov     [rax-20h], r14
0x18006b367  mov     [rax-28h], r15
0x18006b36b  mov     r14, r9
0x18006b36e  xor     r15d, r15d
0x18006b371  xor     eax, eax
0x18006b373  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006b377  mov     [rbp+57h+KeyHandle], r15
0x18006b37b  mov     [rbp+57h+Handle], r15
0x18006b37f  mov     [rbp+57h+var_78], r15
0x18006b383  mov     dword ptr [rbp+57h+ResultLength], r15d
0x18006b387  mov     [rbp+57h+P], r15
0x18006b38b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006b38f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18006b393  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006b397  call    FltpOpenInstancesRegistryKey
0x18006b39c  mov     r8d, 4EEh
0x18006b3a2  mov     qword ptr [rsp+0B0h+Length], r15
0x18006b3a7  mov     r9d, 0C0000034h
0x18006b3ad  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006b3b4  mov     ecx, eax
0x18006b3b6  mov     ebx, eax
0x18006b3b8  call    FltpDbgStatus
0x18006b3bd  test    eax, eax
0x18006b3bf  js      loc_18006B63B
0x18006b3c5  mov     [rsp+0B0h+arg_0], rsi
0x18006b3cd  mov     r8d, 72744D46h
0x18006b3d3  mov     esi, 50h ; 'P'
0x18006b3d8  mov     [rsp+0B0h+arg_18], rdi
0x18006b3e0  mov     edx, esi
0x18006b3e2  mov     ecx, 100h
0x18006b3e7  call    cs:__imp_ExAllocatePool2
0x18006b3ee  nop     dword ptr [rax+rax+00h]
0x18006b3f3  mov     rdi, rax
0x18006b3f6  test    rax, rax
0x18006b3f9  jnz     short loc_18006B405
0x18006b3fb  mov     ebx, 0C000009Ah
0x18006b400  jmp     loc_18006B62B
0x18006b405  lea     rdx, FltpRegDefaultInstanceValueName; "DEFAULTINSTANCE"
0x18006b40c  mov     [rsp+0A0h], r12
0x18006b414  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006b418  call    cs:__imp_RtlInitUnicodeString
0x18006b41f  nop     dword ptr [rax+rax+00h]
0x18006b424  mov     r12d, 51Dh
0x18006b42a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006b42e  lea     rax, [rbp+57h+ResultLength]
0x18006b432  mov     [rsp+28h], rax; ResultLength
0x18006b437  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18006b43b  mov     r9, rdi; KeyValueInformation
0x18006b43e  mov     [rsp+0B0h+Length], esi; Length
0x18006b442  mov     r8d, 2; KeyValueInformationClass
0x18006b448  call    cs:__imp_ZwQueryValueKey
0x18006b44f  nop     dword ptr [rax+rax+00h]
0x18006b454  xor     r9d, r9d
0x18006b457  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006b45e  mov     ecx, eax
0x18006b460  mov     r8d, r12d
0x18006b463  mov     ebx, eax
0x18006b465  call    FltpDbgStatus
0x18006b46a  test    eax, eax
0x18006b46c  jns     short loc_18006B4C8
0x18006b46e  cmp     ebx, 0C0000023h
0x18006b474  jz      short loc_18006B482
0x18006b476  cmp     ebx, 80000005h
0x18006b47c  jnz     loc_18006B60F
0x18006b482  mov     edx, 72744D46h; Tag
0x18006b487  mov     rcx, rdi; P
0x18006b48a  call    cs:__imp_ExFreePoolWithTag
0x18006b491  nop     dword ptr [rax+rax+00h]
0x18006b496  mov     esi, dword ptr [rbp+57h+ResultLength]
0x18006b499  mov     ecx, 100h
0x18006b49e  mov     edx, esi
0x18006b4a0  mov     r8d, 72744D46h
0x18006b4a6  call    cs:__imp_ExAllocatePool2
0x18006b4ad  nop     dword ptr [rax+rax+00h]
0x18006b4b2  mov     rdi, rax
0x18006b4b5  test    rax, rax
0x18006b4b8  jnz     loc_18006B42A
0x18006b4be  mov     ebx, 0C000009Ah
0x18006b4c3  jmp     loc_18006B623
0x18006b4c8  movzx   ecx, word ptr [rdi+8]
0x18006b4cc  mov     r8d, 72744D46h
0x18006b4d2  mov     word ptr [rbp+57h+var_78+2], cx
0x18006b4d6  mov     edx, ecx
0x18006b4d8  lea     eax, [rcx-2]
0x18006b4db  mov     ecx, 100h
0x18006b4e0  mov     word ptr [rbp+57h+var_78], ax
0x18006b4e4  call    cs:__imp_ExAllocatePool2
0x18006b4eb  nop     dword ptr [rax+rax+00h]
0x18006b4f0  mov     [rbp+57h+P], rax
0x18006b4f4  test    rax, rax
0x18006b4f7  jnz     short loc_18006B503
0x18006b4f9  mov     ebx, 0C000009Ah
0x18006b4fe  jmp     loc_18006B60F
0x18006b503  movzx   r8d, word ptr [rbp+57h+var_78]; Size
0x18006b508  lea     rdx, [rdi+0Ch]; Src
0x18006b50c  mov     rcx, rax; void *
0x18006b50f  call    memmove
0x18006b514  mov     rax, [rbp+57h+KeyHandle]
0x18006b518  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006b51c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18006b520  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18006b524  lea     rax, [rbp+57h+var_78]
0x18006b528  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006b52f  xorps   xmm0, xmm0
0x18006b532  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006b536  mov     edx, 20019h; DesiredAccess
0x18006b53b  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18006b542  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006b547  call    cs:__imp_ZwOpenKey
0x18006b54e  nop     dword ptr [rax+rax+00h]
0x18006b553  mov     ebx, eax
0x18006b555  test    eax, eax
0x18006b557  js      loc_18006B60F
0x18006b55d  lea     rdx, FltpRegAltitudeValueName; "ALTITUDE"
0x18006b564  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006b568  call    cs:__imp_RtlInitUnicodeString
0x18006b56f  nop     dword ptr [rax+rax+00h]
0x18006b574  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18006b578  lea     rax, [rbp+57h+ResultLength]
0x18006b57c  mov     [rsp+28h], rax; ResultLength
0x18006b581  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18006b585  mov     r9, rdi; KeyValueInformation
0x18006b588  mov     [rsp+0B0h+Length], esi; Length
0x18006b58c  mov     r8d, 2; KeyValueInformationClass
0x18006b592  call    cs:__imp_ZwQueryValueKey
0x18006b599  nop     dword ptr [rax+rax+00h]
0x18006b59e  mov     ebx, eax
0x18006b5a0  test    eax, eax
0x18006b5a2  jns     short loc_18006B5F1
0x18006b5a4  cmp     eax, 0C0000023h
0x18006b5a9  jz      short loc_18006B5B2
0x18006b5ab  cmp     eax, 80000005h
0x18006b5b0  jnz     short loc_18006B60F
0x18006b5b2  mov     edx, 72744D46h; Tag
0x18006b5b7  mov     rcx, rdi; P
0x18006b5ba  call    cs:__imp_ExFreePoolWithTag
0x18006b5c1  nop     dword ptr [rax+rax+00h]
0x18006b5c6  mov     esi, dword ptr [rbp+57h+ResultLength]
0x18006b5c9  mov     ecx, 100h
0x18006b5ce  mov     edx, esi
0x18006b5d0  mov     r8d, 72744D46h
0x18006b5d6  call    cs:__imp_ExAllocatePool2
0x18006b5dd  nop     dword ptr [rax+rax+00h]
0x18006b5e2  mov     rdi, rax
0x18006b5e5  test    rax, rax
0x18006b5e8  jnz     short loc_18006B574
0x18006b5ea  mov     ebx, 0C000009Ah
0x18006b5ef  jmp     short loc_18006B623
0x18006b5f1  lea     rdx, [rdi+0Ch]; SourceString
0x18006b5f5  mov     rcx, r14; DestinationString
0x18006b5f8  call    cs:__imp_RtlCreateUnicodeString
0x18006b5ff  nop     dword ptr [rax+rax+00h]
0x18006b604  test    al, al
0x18006b606  mov     ebx, 0C000009Ah
0x18006b60b  cmovnz  ebx, r15d
0x18006b60f  mov     edx, 72744D46h; Tag
0x18006b614  mov     rcx, rdi; P
0x18006b617  call    cs:__imp_ExFreePoolWithTag
0x18006b61e  nop     dword ptr [rax+rax+00h]
0x18006b623  mov     r12, [rsp+0A0h]
0x18006b62b  mov     rsi, [rsp+0B0h+arg_0]
0x18006b633  mov     rdi, [rsp+0B0h+arg_18]
0x18006b63b  mov     rcx, [rbp+57h+P]; P
0x18006b63f  mov     r15, [rsp+0B0h+var_20]
0x18006b647  mov     r14, [rsp+0B0h+var_18]
0x18006b64f  test    rcx, rcx
0x18006b652  jz      short loc_18006B665
0x18006b654  mov     edx, 72744D46h; Tag
0x18006b659  call    cs:__imp_ExFreePoolWithTag
0x18006b660  nop     dword ptr [rax+rax+00h]
0x18006b665  mov     rcx, [rbp+57h+Handle]; Handle
0x18006b669  test    rcx, rcx
0x18006b66c  jz      short loc_18006B67A
0x18006b66e  call    cs:__imp_ZwClose
0x18006b675  nop     dword ptr [rax+rax+00h]
0x18006b67a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18006b67e  test    rcx, rcx
0x18006b681  jz      short loc_18006B68F
0x18006b683  call    cs:__imp_ZwClose
0x18006b68a  nop     dword ptr [rax+rax+00h]
0x18006b68f  mov     eax, ebx
0x18006b691  add     rsp, 0A8h
0x18006b698  pop     rbx
0x18006b699  pop     rbp
0x18006b69a  retn
```
