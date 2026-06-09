# BfsRegistryPreCreateCallback

- ea: `0x14000f304`
- end: `0x14000f768`
- name: `BfsRegistryPreCreateCallback`
- size: `1124`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400010c0`

## callees

- `0x140001008`
- `0x14000ed84`
- `0x14000f304`
- `0x1400102dc`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f445`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f445`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f53e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f570`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f75a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f53e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f570`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f75a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000f3d9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000f3d9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f41c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f4f1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f557`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f72a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f41c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f4f1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f557`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f72a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f374`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f4b8`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f4d6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f374`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f4b8`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f4d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f35e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f35e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f659`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f659`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f682`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f682`
- `ntoskrnl!ExAllocatePool2` at `0x14000f5ff`
- `ntoskrnl!ExAllocatePool2` at `0x14000f6c7`
- `ntoskrnl!ExAllocatePool2` at `0x14000f5ff`
- `ntoskrnl!ExAllocatePool2` at `0x14000f6c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f38a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f3c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f434`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f66f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f38a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f3c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f434`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f66f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f39d`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f39d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f3ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f428`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f4fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f57c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f68e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f736`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f3ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f428`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f4fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f57c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f68e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f736`

## string_xrefs

- `0x14000f337`: `\Registry\WC\Silo`

## pseudocode

```c
__int64 __fastcall BfsRegistryPreCreateCallback(int a1, __int64 a2, void *a3)
{
  PVOID *v6; // rdi
  BOOLEAN v7; // r12
  int RegistryPrefix; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // ebx
  int v13; // r15d
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // esi
  __int64 Pool2; // rax
  bool v20; // cc
  _DWORD *v21; // rax
  int v22; // eax
  int v23; // ecx
  int v24; // [rsp+20h] [rbp-79h]
  int v25; // [rsp+30h] [rbp-69h] BYREF
  int v26; // [rsp+34h] [rbp-65h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-61h] BYREF
  __int128 v28; // [rsp+48h] [rbp-51h] BYREF
  PVOID Object[2]; // [rsp+58h] [rbp-41h]
  __int64 v30; // [rsp+68h] [rbp-31h]
  UNICODE_STRING String1; // [rsp+70h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+80h] [rbp-19h] BYREF
  int *v33; // [rsp+A0h] [rbp+7h]
  __int64 v34; // [rsp+A8h] [rbp+Fh]

  v30 = 0;
  v28 = 0;
  *(_OWORD *)Object = 0;
  DestinationString = 0;
  String1 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\WC\\Silo");
  if ( !RtlPrefixUnicodeString(&DestinationString, *(PCUNICODE_STRING *)a2, 1u) )
    return 0;
  v6 = 0;
  KeEnterCriticalRegion();
  v7 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( !v7 )
    goto LABEL_35;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&gBfsPolicyTable, 0);
  v25 = 1;
  RegistryPrefix = BfsGetRegistryPrefix(a3, &DestinationString, &String1, &v25);
  v12 = RegistryPrefix;
  if ( RegistryPrefix < 0 )
  {
    if ( RegistryPrefix != -1073741267 )
      goto LABEL_8;
    if ( v25 == 1 )
    {
      ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
      KeLeaveCriticalRegion();
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&gBfsPolicyTable, 0);
    v25 = 2;
    v12 = BfsGetRegistryPrefix(a3, &DestinationString, &String1, &v25);
    if ( v12 < 0 )
    {
LABEL_8:
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v26 = v12;
        v33 = &v26;
        v34 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v9, (unsigned __int8 *)&byte_140016D91, v10, v11, v24, &v32);
      }
      v13 = v25;
      goto LABEL_51;
    }
  }
  if ( !RtlPrefixUnicodeString(&DestinationString, *(PCUNICODE_STRING *)a2, 1u)
    && !RtlPrefixUnicodeString(&String1, *(PCUNICODE_STRING *)a2, 1u) )
  {
    if ( v25 == 1 )
    {
      ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
    }
    else
    {
      if ( v25 != 2 )
        return 0;
      ExReleasePushLockExclusiveEx(&gBfsPolicyTable, 0);
    }
    KeLeaveCriticalRegion();
    return 0;
  }
  if ( v25 == 1 )
  {
    ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
  }
  else
  {
    if ( v25 != 2 )
      goto LABEL_24;
    ExReleasePushLockExclusiveEx(&gBfsPolicyTable, 0);
  }
  KeLeaveCriticalRegion();
LABEL_24:
  LODWORD(v30) = a1;
  v13 = 0;
  *(_QWORD *)&v28 = a2;
  *((_QWORD *)&v28 + 1) = a3;
  v12 = BfsQueueIoWorkItemAndWait(&v28);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_36;
    v26 = v12;
    goto LABEL_27;
  }
  v18 = HIDWORD(Object[1]);
  if ( !LODWORD(Object[1]) )
  {
    if ( !HIDWORD(Object[1]) )
      goto LABEL_36;
    Pool2 = ExAllocatePool2(256, (unsigned int)(LODWORD(Object[1]) + 24), 1330669122);
    v6 = (PVOID *)Pool2;
    if ( !Pool2 )
    {
      v15 = (unsigned int)dword_140019000;
      v20 = (unsigned int)dword_140019000 <= 3;
LABEL_32:
      v12 = -1073741801;
      if ( v20 )
        goto LABEL_36;
      v26 = -1073741801;
LABEL_27:
      v34 = 4;
      v33 = &v26;
      tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)&byte_140016D91, v16, v17, v24, &v32);
      goto LABEL_36;
    }
    *(_DWORD *)Pool2 = 2;
    *(_DWORD *)(Pool2 + 4) = v18;
    *(_DWORD *)(Pool2 + 8) = v18;
    *(_DWORD *)(Pool2 + 12) = *(_DWORD *)(a2 + 24);
    *(PVOID *)(Pool2 + 16) = Object[0];
    *(_QWORD *)(a2 + 80) = Pool2;
LABEL_35:
    v12 = 0;
    goto LABEL_36;
  }
  if ( LODWORD(Object[1]) == HIDWORD(Object[1])
    || (*(_DWORD *)(a2 + 56) & 0x2020006) == 0
    || (HIDWORD(Object[1]) & 0x20006) == 0 )
  {
    goto LABEL_36;
  }
  v21 = (_DWORD *)ExAllocatePool2(256, 24, 1330669122);
  v6 = (PVOID *)v21;
  if ( !v21 )
  {
    v20 = (unsigned int)dword_140019000 <= 3;
    goto LABEL_32;
  }
  *v21 = 1;
  v22 = v18;
  v23 = *(_DWORD *)(a2 + 56);
  if ( (v23 & 0x2000000) == 0 )
    v22 = v18 & v23;
  v12 = 0;
  *((_DWORD *)v6 + 1) = v22;
  *((_DWORD *)v6 + 2) = v18;
  *((_DWORD *)v6 + 3) = *(_DWORD *)(a2 + 24);
  v6[2] = Object[0];
  *(_QWORD *)(a2 + 80) = v6;
LABEL_51:
  if ( v13 == 1 )
  {
    ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
LABEL_53:
    KeLeaveCriticalRegion();
    goto LABEL_36;
  }
  if ( v13 == 2 )
  {
    ExReleasePushLockExclusiveEx(&gBfsPolicyTable, 0);
    goto LABEL_53;
  }
LABEL_36:
  if ( Object[0] && !v6 )
    ObfDereferenceObject(Object[0]);
  if ( v7 )
  {
    if ( !v6 )
    {
      KeEnterCriticalRegion();
      ExReleaseRundownProtection(&gBfsRundownProtection);
      KeLeaveCriticalRegion();
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000f304  mov     [rsp-8+arg_18], rbx
0x14000f309  push    rbp
0x14000f30a  push    rsi
0x14000f30b  push    rdi
0x14000f30c  push    r12
0x14000f30e  push    r13
0x14000f310  push    r14
0x14000f312  push    r15
0x14000f314  lea     rbp, [rsp-27h]
0x14000f319  sub     rsp, 0C0h
0x14000f320  mov     rax, cs:__security_cookie
0x14000f327  xor     rax, rsp
0x14000f32a  mov     [rbp+57h+var_40], rax
0x14000f32e  xorps   xmm0, xmm0
0x14000f331  mov     r14, rdx
0x14000f334  mov     r13d, ecx
0x14000f337  lea     rdx, aRegistryWcSilo; "\\Registry\\WC\\Silo"
0x14000f33e  xor     eax, eax
0x14000f340  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000f344  xorps   xmm1, xmm1
0x14000f347  mov     [rbp+57h+var_88], rax
0x14000f34b  movups  [rbp+57h+var_A8], xmm0
0x14000f34f  mov     rsi, r8
0x14000f352  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14000f356  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000f35a  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x14000f35e  call    cs:__imp_RtlInitUnicodeString
0x14000f365  nop     dword ptr [rax+rax+00h]
0x14000f36a  mov     rdx, [r14]; String2
0x14000f36d  lea     rcx, [rbp+57h+DestinationString]; String1
0x14000f371  mov     r8b, 1; CaseInSensitive
0x14000f374  call    cs:__imp_RtlPrefixUnicodeString
0x14000f37b  nop     dword ptr [rax+rax+00h]
0x14000f380  test    al, al
0x14000f382  jz      loc_14000F509
0x14000f388  xor     edi, edi
0x14000f38a  call    cs:__imp_KeEnterCriticalRegion
0x14000f391  nop     dword ptr [rax+rax+00h]
0x14000f396  lea     rcx, gBfsRundownProtection; RunRef
0x14000f39d  call    cs:__imp_ExAcquireRundownProtection
0x14000f3a4  nop     dword ptr [rax+rax+00h]
0x14000f3a9  mov     r12b, al
0x14000f3ac  call    cs:__imp_KeLeaveCriticalRegion
0x14000f3b3  nop     dword ptr [rax+rax+00h]
0x14000f3b8  test    r12b, r12b
0x14000f3bb  jz      loc_14000F649
0x14000f3c1  call    cs:__imp_KeEnterCriticalRegion
0x14000f3c8  nop     dword ptr [rax+rax+00h]
0x14000f3cd  lea     r15, gBfsPolicyTable
0x14000f3d4  xor     edx, edx
0x14000f3d6  mov     rcx, r15
0x14000f3d9  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000f3e0  nop     dword ptr [rax+rax+00h]
0x14000f3e5  lea     r9, [rbp+57h+var_C0]
0x14000f3e9  mov     [rbp+57h+var_C0], 1
0x14000f3f0  lea     r8, [rbp+57h+String1]
0x14000f3f4  mov     rcx, rsi; Token
0x14000f3f7  lea     rdx, [rbp+57h+DestinationString]
0x14000f3fb  call    BfsGetRegistryPrefix
0x14000f400  mov     ebx, eax
0x14000f402  test    eax, eax
0x14000f404  jns     loc_14000F4AE
0x14000f40a  cmp     eax, 0C000022Dh
0x14000f40f  jnz     short loc_14000F472
0x14000f411  cmp     [rbp+57h+var_C0], 1
0x14000f415  jnz     short loc_14000F434
0x14000f417  xor     edx, edx
0x14000f419  mov     rcx, r15
0x14000f41c  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f423  nop     dword ptr [rax+rax+00h]
0x14000f428  call    cs:__imp_KeLeaveCriticalRegion
0x14000f42f  nop     dword ptr [rax+rax+00h]
0x14000f434  call    cs:__imp_KeEnterCriticalRegion
0x14000f43b  nop     dword ptr [rax+rax+00h]
0x14000f440  xor     edx, edx
0x14000f442  mov     rcx, r15
0x14000f445  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000f44c  nop     dword ptr [rax+rax+00h]
0x14000f451  lea     r9, [rbp+57h+var_C0]
0x14000f455  mov     [rbp+57h+var_C0], 2
0x14000f45c  lea     r8, [rbp+57h+String1]
0x14000f460  mov     rcx, rsi; Token
0x14000f463  lea     rdx, [rbp+57h+DestinationString]
0x14000f467  call    BfsGetRegistryPrefix
0x14000f46c  mov     ebx, eax
0x14000f46e  test    eax, eax
0x14000f470  jns     short loc_14000F4AE
0x14000f472  mov     eax, cs:dword_140019000
0x14000f478  cmp     eax, 3
0x14000f47b  jbe     short loc_14000F4A5
0x14000f47d  lea     rax, [rbp+57h+var_BC]
0x14000f481  mov     [rbp+57h+var_BC], ebx
0x14000f484  mov     [rbp+57h+var_50], rax
0x14000f488  lea     rdx, byte_140016D91; int
0x14000f48f  lea     rax, [rbp+57h+var_70]
0x14000f493  mov     [rbp+57h+var_48], 4
0x14000f49b  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x14000f4a0  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f4a5  mov     r15d, [rbp+57h+var_C0]
0x14000f4a9  jmp     loc_14000F71B
0x14000f4ae  mov     rdx, [r14]; String2
0x14000f4b1  lea     rcx, [rbp+57h+DestinationString]; String1
0x14000f4b5  mov     r8b, 1; CaseInSensitive
0x14000f4b8  call    cs:__imp_RtlPrefixUnicodeString
0x14000f4bf  nop     dword ptr [rax+rax+00h]
0x14000f4c4  test    al, al
0x14000f4c6  jnz     loc_14000F54C
0x14000f4cc  mov     rdx, [r14]; String2
0x14000f4cf  lea     rcx, [rbp+57h+String1]; String1
0x14000f4d3  mov     r8b, 1; CaseInSensitive
0x14000f4d6  call    cs:__imp_RtlPrefixUnicodeString
0x14000f4dd  nop     dword ptr [rax+rax+00h]
0x14000f4e2  test    al, al
0x14000f4e4  jnz     short loc_14000F54C
0x14000f4e6  cmp     [rbp+57h+var_C0], 1
0x14000f4ea  jnz     short loc_14000F533
0x14000f4ec  xor     edx, edx
0x14000f4ee  mov     rcx, r15
0x14000f4f1  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f4f8  nop     dword ptr [rax+rax+00h]
0x14000f4fd  call    cs:__imp_KeLeaveCriticalRegion
0x14000f504  nop     dword ptr [rax+rax+00h]
0x14000f509  xor     eax, eax
0x14000f50b  mov     rcx, [rbp+57h+var_40]
0x14000f50f  xor     rcx, rsp; StackCookie
0x14000f512  call    __security_check_cookie
0x14000f517  mov     rbx, [rsp+0F0h+arg_18]
0x14000f51f  add     rsp, 0C0h
0x14000f526  pop     r15
0x14000f528  pop     r14
0x14000f52a  pop     r13
0x14000f52c  pop     r12
0x14000f52e  pop     rdi
0x14000f52f  pop     rsi
0x14000f530  pop     rbp
0x14000f531  retn
0x14000f533  cmp     [rbp+57h+var_C0], 2
0x14000f537  jnz     short loc_14000F509
0x14000f539  xor     edx, edx
0x14000f53b  mov     rcx, r15
0x14000f53e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f545  nop     dword ptr [rax+rax+00h]
0x14000f54a  jmp     short loc_14000F4FD
0x14000f54c  cmp     [rbp+57h+var_C0], 1
0x14000f550  jnz     short loc_14000F565
0x14000f552  xor     edx, edx
0x14000f554  mov     rcx, r15
0x14000f557  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f55e  nop     dword ptr [rax+rax+00h]
0x14000f563  jmp     short loc_14000F57C
0x14000f565  cmp     [rbp+57h+var_C0], 2
0x14000f569  jnz     short loc_14000F588
0x14000f56b  xor     edx, edx
0x14000f56d  mov     rcx, r15
0x14000f570  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f577  nop     dword ptr [rax+rax+00h]
0x14000f57c  call    cs:__imp_KeLeaveCriticalRegion
0x14000f583  nop     dword ptr [rax+rax+00h]
0x14000f588  lea     rcx, [rbp+57h+var_A8]
0x14000f58c  mov     dword ptr [rbp+57h+var_88], r13d
0x14000f590  xor     r15d, r15d
0x14000f593  mov     qword ptr [rbp+57h+var_A8], r14
0x14000f597  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x14000f59b  call    BfsQueueIoWorkItemAndWait
0x14000f5a0  mov     ebx, eax
0x14000f5a2  test    eax, eax
0x14000f5a4  jns     short loc_14000F5DF
0x14000f5a6  mov     eax, cs:dword_140019000
0x14000f5ac  cmp     eax, 3
0x14000f5af  jbe     loc_14000F64B
0x14000f5b5  mov     [rbp+57h+var_BC], ebx
0x14000f5b8  lea     rax, [rbp+57h+var_BC]
0x14000f5bc  mov     [rbp+57h+var_48], 4
0x14000f5c4  mov     [rbp+57h+var_50], rax
0x14000f5c8  lea     rdx, byte_140016D91; int
0x14000f5cf  lea     rax, [rbp+57h+var_70]
0x14000f5d3  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x14000f5d8  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f5dd  jmp     short loc_14000F64B
0x14000f5df  mov     eax, dword ptr [rbp+57h+Object+8]
0x14000f5e2  mov     esi, dword ptr [rbp+57h+Object+0Ch]
0x14000f5e5  test    eax, eax
0x14000f5e7  jnz     loc_14000F6A1
0x14000f5ed  test    esi, esi
0x14000f5ef  jz      short loc_14000F64B
0x14000f5f1  lea     edx, [rax+18h]
0x14000f5f4  mov     ecx, 100h
0x14000f5f9  mov     r8d, 4F506642h
0x14000f5ff  call    cs:__imp_ExAllocatePool2
0x14000f606  nop     dword ptr [rax+rax+00h]
0x14000f60b  mov     rdi, rax
0x14000f60e  test    rax, rax
0x14000f611  jnz     short loc_14000F62A
0x14000f613  mov     ecx, cs:dword_140019000
0x14000f619  cmp     ecx, 3
0x14000f61c  mov     edx, 0C0000017h
0x14000f621  mov     ebx, edx
0x14000f623  jbe     short loc_14000F64B
0x14000f625  mov     [rbp+57h+var_BC], edx
0x14000f628  jmp     short loc_14000F5B8
0x14000f62a  mov     dword ptr [rax], 2
0x14000f630  mov     [rax+4], esi
0x14000f633  mov     [rax+8], esi
0x14000f636  mov     eax, [r14+18h]
0x14000f63a  mov     [rdi+0Ch], eax
0x14000f63d  mov     rax, [rbp+57h+Object]
0x14000f641  mov     [rdi+10h], rax
0x14000f645  mov     [r14+50h], rdi
0x14000f649  xor     ebx, ebx
0x14000f64b  mov     rcx, [rbp+57h+Object]; Object
0x14000f64f  test    rcx, rcx
0x14000f652  jz      short loc_14000F665
0x14000f654  test    rdi, rdi
0x14000f657  jnz     short loc_14000F665
0x14000f659  call    cs:__imp_ObfDereferenceObject
0x14000f660  nop     dword ptr [rax+rax+00h]
0x14000f665  test    r12b, r12b
0x14000f668  jz      short loc_14000F69A
0x14000f66a  test    rdi, rdi
0x14000f66d  jnz     short loc_14000F69A
0x14000f66f  call    cs:__imp_KeEnterCriticalRegion
0x14000f676  nop     dword ptr [rax+rax+00h]
0x14000f67b  lea     rcx, gBfsRundownProtection; RunRef
0x14000f682  call    cs:__imp_ExReleaseRundownProtection
0x14000f689  nop     dword ptr [rax+rax+00h]
0x14000f68e  call    cs:__imp_KeLeaveCriticalRegion
0x14000f695  nop     dword ptr [rax+rax+00h]
0x14000f69a  mov     eax, ebx
0x14000f69c  jmp     loc_14000F50B
0x14000f6a1  cmp     eax, esi
0x14000f6a3  jz      short loc_14000F64B
0x14000f6a5  test    dword ptr [r14+38h], 2020006h
0x14000f6ad  jz      short loc_14000F64B
0x14000f6af  test    esi, 20006h
0x14000f6b5  jz      short loc_14000F64B
0x14000f6b7  mov     edx, 18h
0x14000f6bc  mov     ecx, 100h
0x14000f6c1  mov     r8d, 4F506642h
0x14000f6c7  call    cs:__imp_ExAllocatePool2
0x14000f6ce  nop     dword ptr [rax+rax+00h]
0x14000f6d3  mov     rdi, rax
0x14000f6d6  test    rax, rax
0x14000f6d9  jnz     short loc_14000F6E9
0x14000f6db  mov     eax, cs:dword_140019000
0x14000f6e1  cmp     eax, 3
0x14000f6e4  jmp     loc_14000F61C
0x14000f6e9  mov     dword ptr [rax], 1
0x14000f6ef  mov     eax, esi
0x14000f6f1  mov     edx, [r14+38h]
0x14000f6f5  mov     ecx, edx
0x14000f6f7  and     edx, esi
0x14000f6f9  bt      ecx, 19h
0x14000f6fd  cmovnb  eax, edx
0x14000f700  xor     ebx, ebx
0x14000f702  mov     [rdi+4], eax
0x14000f705  mov     [rdi+8], esi
0x14000f708  mov     eax, [r14+18h]
0x14000f70c  mov     [rdi+0Ch], eax
0x14000f70f  mov     rax, [rbp+57h+Object]
0x14000f713  mov     [rdi+10h], rax
0x14000f717  mov     [r14+50h], rdi
0x14000f71b  cmp     r15d, 1
0x14000f71f  jnz     short loc_14000F747
0x14000f721  xor     edx, edx
0x14000f723  lea     rcx, gBfsPolicyTable
0x14000f72a  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f731  nop     dword ptr [rax+rax+00h]
0x14000f736  call    cs:__imp_KeLeaveCriticalRegion
0x14000f73d  nop     dword ptr [rax+rax+00h]
0x14000f742  jmp     loc_14000F64B
0x14000f747  cmp     r15d, 2
0x14000f74b  jnz     loc_14000F64B
0x14000f751  xor     edx, edx
0x14000f753  lea     rcx, gBfsPolicyTable
0x14000f75a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f761  nop     dword ptr [rax+rax+00h]
0x14000f766  jmp     short loc_14000F736
```
