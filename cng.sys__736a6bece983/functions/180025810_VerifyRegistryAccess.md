# VerifyRegistryAccess

- ea: `0x180025810`
- end: `0x180025a91`
- name: `VerifyRegistryAccess`
- size: `641`
- prototype: `ULONG __fastcall(__int64, const WCHAR **, ACCESS_MASK)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018af0`
- `0x180025c00`

## callees

- `0x180025810`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800258c6`
- `ntoskrnl!ExAllocatePool2` at `0x1800258c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002597f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002597f`
- `ntoskrnl!ZwClose` at `0x1800259eb`
- `ntoskrnl!ZwClose` at `0x1800259eb`
- `ntoskrnl!ObfDereferenceObject` at `0x1800259dc`
- `ntoskrnl!ObfDereferenceObject` at `0x1800259dc`
- `ntoskrnl!ZwOpenKey` at `0x18002594a`
- `ntoskrnl!ZwOpenKey` at `0x18002594a`
- `ntoskrnl!SkIsSecureKernel` at `0x180025a1e`
- `ntoskrnl!SkIsSecureKernel` at `0x180025a54`
- `ntoskrnl!SkIsSecureKernel` at `0x180025a1e`
- `ntoskrnl!SkIsSecureKernel` at `0x180025a54`
- `ntoskrnl!SkAllocatePool` at `0x180025a76`
- `ntoskrnl!SkAllocatePool` at `0x180025a76`
- `ntoskrnl!SkFreePool` at `0x180025a43`
- `ntoskrnl!SkFreePool` at `0x180025a43`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800259c8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800259c8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800258f0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025903`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800258f0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180025903`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18002598d`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18002598d`

## string_xrefs

- `0x18002584f`: `\Registry\Machine\`

## pseudocode

```c
ULONG __fastcall VerifyRegistryAccess(__int64 a1, const WCHAR **a2, ACCESS_MASK a3)
{
  const WCHAR *v3; // rbx
  __int64 v5; // rax
  unsigned int v7; // edi
  WCHAR *Pool; // rax
  ULONG v9; // eax
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  PWSTR Buffer; // rbx
  NTSTATUS v14; // edi
  int v15; // eax
  ULONG result; // eax
  void *v17; // rdi
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-29h] BYREF
  PVOID Object; // [rsp+48h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  WCHAR Source[20]; // [rsp+80h] [rbp+17h] BYREF

  v3 = *a2;
  Destination = 0;
  KeyHandle = 0;
  v5 = -1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  wcscpy(Source, L"\\Registry\\Machne\\");
  while ( v3[++v5] != 0 )
    ;
  v7 = 2 * v5 + 38;
  LOBYTE(v5) = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
  {
    LODWORD(v5) = ((int)SkIsSecureKernel(a1, a2) >> 31) + 2;
    g_TrustedEnvironment = v5;
  }
  if ( (v5 & 2) != 0 )
    Pool = (WCHAR *)SkAllocatePool(512, v7, 1650945603);
  else
    Pool = (WCHAR *)ExAllocatePool2(64, v7, 1650945603);
  Destination.Buffer = Pool;
  if ( !Pool )
    return 8;
  Destination.Length = 0;
  Destination.MaximumLength = v7;
  RtlAppendUnicodeToString(&Destination, Source);
  RtlAppendUnicodeToString(&Destination, v3);
  v9 = 576;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a3 != 131097 )
    v9 = 1600;
  ObjectAttributes.Attributes = v9;
  ObjectAttributes.ObjectName = &Destination;
  v10 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
  Buffer = Destination.Buffer;
  v14 = v10;
  if ( Destination.Buffer )
  {
    LOBYTE(v15) = g_TrustedEnvironment;
    if ( !g_TrustedEnvironment )
    {
      v15 = ((int)SkIsSecureKernel(v12, v11) >> 31) + 2;
      g_TrustedEnvironment = v15;
    }
    if ( (v15 & 2) != 0 )
      SkFreePool(512, Buffer);
    else
      ExFreePoolWithTag(Buffer, 0x62676E43u);
  }
  result = RtlNtStatusToDosErrorNoTeb(v14);
  if ( !result )
  {
    v17 = KeyHandle;
    *(_QWORD *)&Destination.Length = 0;
    Object = 0;
    if ( ObReferenceObjectByHandle(KeyHandle, 0, 0, 0, &Object, (POBJECT_HANDLE_INFORMATION)&Destination) >= 0 )
    {
      ObfDereferenceObject(Object);
      ZwClose(v17);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180025810  mov     [rsp-8+arg_0], rbx
0x180025815  mov     [rsp-8+arg_18], rsi
0x18002581a  push    rbp
0x18002581b  push    rdi
0x18002581c  push    r14
0x18002581e  lea     rbp, [rsp-47h]
0x180025823  sub     rsp, 0B0h
0x18002582a  mov     rax, cs:__security_cookie
0x180025831  xor     rax, rsp
0x180025834  mov     [rbp+57h+var_18], rax
0x180025838  mov     rbx, [rdx]
0x18002583b  xorps   xmm1, xmm1
0x18002583e  xorps   xmm0, xmm0
0x180025841  xor     r14d, r14d
0x180025844  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180025848  mov     esi, r8d
0x18002584b  mov     [rbp+57h+KeyHandle], r14
0x18002584f  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180025856  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002585d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180025861  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x180025865  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180025869  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180025870  movups  xmmword ptr [rbp+57h+Source], xmm0
0x180025874  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x18002587c  movups  [rbp+57h+var_30], xmm1
0x180025880  movsd   qword ptr [rbp+57h+var_30+0Eh], xmm0
0x180025885  nop     word ptr [rax+rax+00000000h]
0x180025890  cmp     [rbx+rax*2+2], r14w
0x180025896  lea     rax, [rax+1]
0x18002589a  jnz     short loc_180025890
0x18002589c  lea     edi, ds:26h[rax*2]
0x1800258a3  mov     eax, cs:g_TrustedEnvironment
0x1800258a9  test    eax, eax
0x1800258ab  jz      loc_180025A54
0x1800258b1  mov     edx, edi
0x1800258b3  mov     r8d, 62676E43h
0x1800258b9  test    al, 2
0x1800258bb  jnz     loc_180025A71
0x1800258c1  mov     ecx, 40h ; '@'
0x1800258c6  call    cs:__imp_ExAllocatePool2
0x1800258cd  nop     dword ptr [rax+rax+00h]
0x1800258d2  mov     [rbp+57h+Destination.Buffer], rax
0x1800258d6  test    rax, rax
0x1800258d9  jz      loc_180025A87
0x1800258df  lea     rdx, [rbp+57h+Source]; Source
0x1800258e3  mov     [rbp+57h+Destination.Length], r14w
0x1800258e8  lea     rcx, [rbp+57h+Destination]; Destination
0x1800258ec  mov     [rbp+57h+Destination.MaximumLength], di
0x1800258f0  call    cs:__imp_RtlAppendUnicodeToString
0x1800258f7  nop     dword ptr [rax+rax+00h]
0x1800258fc  mov     rdx, rbx; Source
0x1800258ff  lea     rcx, [rbp+57h+Destination]; Destination
0x180025903  call    cs:__imp_RtlAppendUnicodeToString
0x18002590a  nop     dword ptr [rax+rax+00h]
0x18002590f  mov     eax, 240h
0x180025914  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002591b  mov     ecx, 640h
0x180025920  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180025924  xorps   xmm0, xmm0
0x180025927  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002592b  cmp     esi, 20019h
0x180025931  mov     edx, esi; DesiredAccess
0x180025933  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180025938  cmovnz  eax, ecx
0x18002593b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002593f  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x180025942  lea     rax, [rbp+57h+Destination]
0x180025946  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002594a  call    cs:__imp_ZwOpenKey
0x180025951  nop     dword ptr [rax+rax+00h]
0x180025956  mov     rbx, [rbp+57h+Destination.Buffer]
0x18002595a  mov     edi, eax
0x18002595c  test    rbx, rbx
0x18002595f  jz      short loc_18002598B
0x180025961  mov     eax, cs:g_TrustedEnvironment
0x180025967  test    eax, eax
0x180025969  jz      loc_180025A1E
0x18002596f  test    al, 2
0x180025971  jnz     loc_180025A3B
0x180025977  mov     edx, 62676E43h; Tag
0x18002597c  mov     rcx, rbx; P
0x18002597f  call    cs:__imp_ExFreePoolWithTag
0x180025986  nop     dword ptr [rax+rax+00h]
0x18002598b  mov     ecx, edi; Status
0x18002598d  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180025994  nop     dword ptr [rax+rax+00h]
0x180025999  mov     ebx, eax
0x18002599b  test    eax, eax
0x18002599d  jnz     short loc_1800259F9
0x18002599f  mov     rdi, [rbp+57h+KeyHandle]
0x1800259a3  lea     rax, [rbp+57h+Destination]
0x1800259a7  mov     [rsp+0C0h+HandleInformation], rax; HandleInformation
0x1800259ac  xor     r9d, r9d; AccessMode
0x1800259af  lea     rax, [rbp+57h+var_78]
0x1800259b3  mov     qword ptr [rbp+57h+Destination.Length], r14
0x1800259b7  xor     r8d, r8d; ObjectType
0x1800259ba  mov     [rsp+0C0h+Object], rax; Object
0x1800259bf  xor     edx, edx; DesiredAccess
0x1800259c1  mov     [rbp+57h+var_78], r14
0x1800259c5  mov     rcx, rdi; Handle
0x1800259c8  call    cs:__imp_ObReferenceObjectByHandle
0x1800259cf  nop     dword ptr [rax+rax+00h]
0x1800259d4  test    eax, eax
0x1800259d6  js      short loc_1800259F7
0x1800259d8  mov     rcx, [rbp+57h+var_78]; Object
0x1800259dc  call    cs:__imp_ObfDereferenceObject
0x1800259e3  nop     dword ptr [rax+rax+00h]
0x1800259e8  mov     rcx, rdi; Handle
0x1800259eb  call    cs:__imp_ZwClose
0x1800259f2  nop     dword ptr [rax+rax+00h]
0x1800259f7  mov     eax, ebx
0x1800259f9  mov     rcx, [rbp+57h+var_18]
0x1800259fd  xor     rcx, rsp; StackCookie
0x180025a00  call    __security_check_cookie
0x180025a05  lea     r11, [rsp+0C0h+var_10]
0x180025a0d  mov     rbx, [r11+20h]
0x180025a11  mov     rsi, [r11+38h]
0x180025a15  mov     rsp, r11
0x180025a18  pop     r14
0x180025a1a  pop     rdi
0x180025a1b  pop     rbp
0x180025a1c  retn
0x180025a1e  call    cs:__imp_SkIsSecureKernel
0x180025a25  nop     dword ptr [rax+rax+00h]
0x180025a2a  sar     eax, 1Fh
0x180025a2d  add     eax, 2
0x180025a30  mov     cs:g_TrustedEnvironment, eax
0x180025a36  jmp     loc_18002596F
0x180025a3b  mov     rdx, rbx
0x180025a3e  mov     ecx, 200h
0x180025a43  call    cs:__imp_SkFreePool
0x180025a4a  nop     dword ptr [rax+rax+00h]
0x180025a4f  jmp     loc_18002598B
0x180025a54  call    cs:__imp_SkIsSecureKernel
0x180025a5b  nop     dword ptr [rax+rax+00h]
0x180025a60  sar     eax, 1Fh
0x180025a63  add     eax, 2
0x180025a66  mov     cs:g_TrustedEnvironment, eax
0x180025a6c  jmp     loc_1800258B1
0x180025a71  mov     ecx, 200h
0x180025a76  call    cs:__imp_SkAllocatePool
0x180025a7d  nop     dword ptr [rax+rax+00h]
0x180025a82  jmp     loc_1800258D2
0x180025a87  mov     eax, 8
0x180025a8c  jmp     loc_1800259F9
```
