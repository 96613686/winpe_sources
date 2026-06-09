# VerifyRegistryAccess

- ea: `0x180032880`
- end: `0x180032b01`
- name: `VerifyRegistryAccess`
- size: `641`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180025b70`
- `0x180032c70`

## callees

- `0x180032880`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180032936`
- `ntoskrnl!ExAllocatePool2` at `0x180032936`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800329ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800329ef`
- `ntoskrnl!ZwClose` at `0x180032a5b`
- `ntoskrnl!ZwClose` at `0x180032a5b`
- `ntoskrnl!ObfDereferenceObject` at `0x180032a4c`
- `ntoskrnl!ObfDereferenceObject` at `0x180032a4c`
- `ntoskrnl!ZwOpenKey` at `0x1800329ba`
- `ntoskrnl!ZwOpenKey` at `0x1800329ba`
- `ntoskrnl!SkIsSecureKernel` at `0x180032a8e`
- `ntoskrnl!SkIsSecureKernel` at `0x180032ac4`
- `ntoskrnl!SkIsSecureKernel` at `0x180032a8e`
- `ntoskrnl!SkIsSecureKernel` at `0x180032ac4`
- `ntoskrnl!SkAllocatePool` at `0x180032ae6`
- `ntoskrnl!SkAllocatePool` at `0x180032ae6`
- `ntoskrnl!SkFreePool` at `0x180032ab3`
- `ntoskrnl!SkFreePool` at `0x180032ab3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180032a38`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180032a38`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180032960`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180032973`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180032960`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180032973`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800329fd`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800329fd`

## string_xrefs

- `0x1800328bf`: `\Registry\Machine\`

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
0x180032880  mov     [rsp-8+arg_0], rbx
0x180032885  mov     [rsp-8+arg_18], rsi
0x18003288a  push    rbp
0x18003288b  push    rdi
0x18003288c  push    r14
0x18003288e  lea     rbp, [rsp-47h]
0x180032893  sub     rsp, 0B0h
0x18003289a  mov     rax, cs:__security_cookie
0x1800328a1  xor     rax, rsp
0x1800328a4  mov     [rbp+57h+var_18], rax
0x1800328a8  mov     rbx, [rdx]
0x1800328ab  xorps   xmm1, xmm1
0x1800328ae  xorps   xmm0, xmm0
0x1800328b1  xor     r14d, r14d
0x1800328b4  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x1800328b8  mov     esi, r8d
0x1800328bb  mov     [rbp+57h+KeyHandle], r14
0x1800328bf  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x1800328c6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800328cd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800328d1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800328d5  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800328d9  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x1800328e0  movups  xmmword ptr [rbp+57h+Source], xmm0
0x1800328e4  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x1800328ec  movups  [rbp+57h+var_30], xmm1
0x1800328f0  movsd   qword ptr [rbp+57h+var_30+0Eh], xmm0
0x1800328f5  nop     word ptr [rax+rax+00000000h]
0x180032900  cmp     [rbx+rax*2+2], r14w
0x180032906  lea     rax, [rax+1]
0x18003290a  jnz     short loc_180032900
0x18003290c  lea     edi, ds:26h[rax*2]
0x180032913  mov     eax, cs:g_TrustedEnvironment
0x180032919  test    eax, eax
0x18003291b  jz      loc_180032AC4
0x180032921  mov     edx, edi
0x180032923  mov     r8d, 62676E43h
0x180032929  test    al, 2
0x18003292b  jnz     loc_180032AE1
0x180032931  mov     ecx, 40h ; '@'
0x180032936  call    cs:__imp_ExAllocatePool2
0x18003293d  nop     dword ptr [rax+rax+00h]
0x180032942  mov     [rbp+57h+Destination.Buffer], rax
0x180032946  test    rax, rax
0x180032949  jz      loc_180032AF7
0x18003294f  lea     rdx, [rbp+57h+Source]; Source
0x180032953  mov     [rbp+57h+Destination.Length], r14w
0x180032958  lea     rcx, [rbp+57h+Destination]; Destination
0x18003295c  mov     [rbp+57h+Destination.MaximumLength], di
0x180032960  call    cs:__imp_RtlAppendUnicodeToString
0x180032967  nop     dword ptr [rax+rax+00h]
0x18003296c  mov     rdx, rbx; Source
0x18003296f  lea     rcx, [rbp+57h+Destination]; Destination
0x180032973  call    cs:__imp_RtlAppendUnicodeToString
0x18003297a  nop     dword ptr [rax+rax+00h]
0x18003297f  mov     eax, 240h
0x180032984  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003298b  mov     ecx, 640h
0x180032990  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180032994  xorps   xmm0, xmm0
0x180032997  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003299b  cmp     esi, 20019h
0x1800329a1  mov     edx, esi; DesiredAccess
0x1800329a3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800329a8  cmovnz  eax, ecx
0x1800329ab  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800329af  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x1800329b2  lea     rax, [rbp+57h+Destination]
0x1800329b6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800329ba  call    cs:__imp_ZwOpenKey
0x1800329c1  nop     dword ptr [rax+rax+00h]
0x1800329c6  mov     rbx, [rbp+57h+Destination.Buffer]
0x1800329ca  mov     edi, eax
0x1800329cc  test    rbx, rbx
0x1800329cf  jz      short loc_1800329FB
0x1800329d1  mov     eax, cs:g_TrustedEnvironment
0x1800329d7  test    eax, eax
0x1800329d9  jz      loc_180032A8E
0x1800329df  test    al, 2
0x1800329e1  jnz     loc_180032AAB
0x1800329e7  mov     edx, 62676E43h; Tag
0x1800329ec  mov     rcx, rbx; P
0x1800329ef  call    cs:__imp_ExFreePoolWithTag
0x1800329f6  nop     dword ptr [rax+rax+00h]
0x1800329fb  mov     ecx, edi; Status
0x1800329fd  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180032a04  nop     dword ptr [rax+rax+00h]
0x180032a09  mov     ebx, eax
0x180032a0b  test    eax, eax
0x180032a0d  jnz     short loc_180032A69
0x180032a0f  mov     rdi, [rbp+57h+KeyHandle]
0x180032a13  lea     rax, [rbp+57h+Destination]
0x180032a17  mov     [rsp+0C0h+HandleInformation], rax; HandleInformation
0x180032a1c  xor     r9d, r9d; AccessMode
0x180032a1f  lea     rax, [rbp+57h+var_78]
0x180032a23  mov     qword ptr [rbp+57h+Destination.Length], r14
0x180032a27  xor     r8d, r8d; ObjectType
0x180032a2a  mov     [rsp+0C0h+Object], rax; Object
0x180032a2f  xor     edx, edx; DesiredAccess
0x180032a31  mov     [rbp+57h+var_78], r14
0x180032a35  mov     rcx, rdi; Handle
0x180032a38  call    cs:__imp_ObReferenceObjectByHandle
0x180032a3f  nop     dword ptr [rax+rax+00h]
0x180032a44  test    eax, eax
0x180032a46  js      short loc_180032A67
0x180032a48  mov     rcx, [rbp+57h+var_78]; Object
0x180032a4c  call    cs:__imp_ObfDereferenceObject
0x180032a53  nop     dword ptr [rax+rax+00h]
0x180032a58  mov     rcx, rdi; Handle
0x180032a5b  call    cs:__imp_ZwClose
0x180032a62  nop     dword ptr [rax+rax+00h]
0x180032a67  mov     eax, ebx
0x180032a69  mov     rcx, [rbp+57h+var_18]
0x180032a6d  xor     rcx, rsp; StackCookie
0x180032a70  call    __security_check_cookie
0x180032a75  lea     r11, [rsp+0C0h+var_10]
0x180032a7d  mov     rbx, [r11+20h]
0x180032a81  mov     rsi, [r11+38h]
0x180032a85  mov     rsp, r11
0x180032a88  pop     r14
0x180032a8a  pop     rdi
0x180032a8b  pop     rbp
0x180032a8c  retn
0x180032a8e  call    cs:__imp_SkIsSecureKernel
0x180032a95  nop     dword ptr [rax+rax+00h]
0x180032a9a  sar     eax, 1Fh
0x180032a9d  add     eax, 2
0x180032aa0  mov     cs:g_TrustedEnvironment, eax
0x180032aa6  jmp     loc_1800329DF
0x180032aab  mov     rdx, rbx
0x180032aae  mov     ecx, 200h
0x180032ab3  call    cs:__imp_SkFreePool
0x180032aba  nop     dword ptr [rax+rax+00h]
0x180032abf  jmp     loc_1800329FB
0x180032ac4  call    cs:__imp_SkIsSecureKernel
0x180032acb  nop     dword ptr [rax+rax+00h]
0x180032ad0  sar     eax, 1Fh
0x180032ad3  add     eax, 2
0x180032ad6  mov     cs:g_TrustedEnvironment, eax
0x180032adc  jmp     loc_180032921
0x180032ae1  mov     ecx, 200h
0x180032ae6  call    cs:__imp_SkAllocatePool
0x180032aed  nop     dword ptr [rax+rax+00h]
0x180032af2  jmp     loc_180032942
0x180032af7  mov     eax, 8
0x180032afc  jmp     loc_180032A69
```
