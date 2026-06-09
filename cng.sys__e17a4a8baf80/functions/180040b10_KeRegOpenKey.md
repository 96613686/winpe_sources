# KeRegOpenKey

- ea: `0x180040b10`
- end: `0x180040d46`
- name: `KeRegOpenKey`
- size: `566`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180040358`
- `0x18004058c`
- `0x180040828`
- `0x18004c2d0`
- `0x180051008`
- `0x1800511f0`
- `0x180079c10`
- `0x180079eec`
- `0x18007a334`
- `0x18007a51c`
- `0x18007c4d0`
- `0x18007c71c`
- `0x18007c96c`
- `0x18007ccd8`
- `0x18007cf08`
- `0x18007d1f8`
- `0x18007d39c`
- `0x18007d844`
- `0x18007d8a0`

## callees

- `0x180040b10`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180040d35`
- `ntoskrnl!RtlInitUnicodeString` at `0x180040d35`
- `ntoskrnl!ExAllocatePool2` at `0x180040bc6`
- `ntoskrnl!ExAllocatePool2` at `0x180040bc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x180040c8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180040c8c`
- `ntoskrnl!ZwOpenKey` at `0x180040c59`
- `ntoskrnl!ZwOpenKey` at `0x180040c59`
- `ntoskrnl!SkIsSecureKernel` at `0x180040cc3`
- `ntoskrnl!SkIsSecureKernel` at `0x180040cf3`
- `ntoskrnl!SkIsSecureKernel` at `0x180040cc3`
- `ntoskrnl!SkIsSecureKernel` at `0x180040cf3`
- `ntoskrnl!SkAllocatePool` at `0x180040d15`
- `ntoskrnl!SkAllocatePool` at `0x180040d15`
- `ntoskrnl!SkFreePool` at `0x180040ce5`
- `ntoskrnl!SkFreePool` at `0x180040ce5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180040bf6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180040c0a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180040bf6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180040c0a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180040c9a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180040c9a`

## string_xrefs

- `0x180040b61`: `\Registry\Machine\`

## pseudocode

```c
ULONG __fastcall KeRegOpenKey(void *a1, const WCHAR *a2, ACCESS_MASK a3, void **a4)
{
  void *v7; // rdi
  __int64 v8; // rax
  unsigned int v10; // edi
  WCHAR *Pool; // rax
  ULONG v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  NTSTATUS v15; // esi
  PWSTR Buffer; // rbx
  int v17; // eax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-88h] BYREF
  WCHAR Source[20]; // [rsp+60h] [rbp-58h] BYREF

  v7 = a1;
  Destination = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a1 == (void *)-2147483646LL )
  {
    v8 = -1;
    wcscpy(Source, L"\\Registry\\Machne\\");
    while ( a2[++v8] != 0 )
      ;
    v10 = 2 * v8 + 38;
    LOBYTE(v8) = g_TrustedEnvironment;
    if ( !g_TrustedEnvironment )
    {
      LODWORD(v8) = ((int)SkIsSecureKernel(-2147483646, a2) >> 31) + 2;
      g_TrustedEnvironment = v8;
    }
    if ( (v8 & 2) != 0 )
      Pool = (WCHAR *)SkAllocatePool(512, v10, 1650945603);
    else
      Pool = (WCHAR *)ExAllocatePool2(64, v10, 1650945603);
    Destination.Buffer = Pool;
    if ( !Pool )
      return 8;
    Destination.MaximumLength = v10;
    Destination.Length = 0;
    RtlAppendUnicodeToString(&Destination, Source);
    RtlAppendUnicodeToString(&Destination, a2);
    v7 = 0;
  }
  else
  {
    RtlInitUnicodeString(&Destination, a2);
  }
  v12 = 576;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v7;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a3 != 131097 )
    v12 = 1600;
  ObjectAttributes.Attributes = v12;
  ObjectAttributes.ObjectName = &Destination;
  v15 = ZwOpenKey(a4, a3, &ObjectAttributes);
  if ( !v7 )
  {
    Buffer = Destination.Buffer;
    if ( Destination.Buffer )
    {
      LOBYTE(v17) = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
      {
        v17 = ((int)SkIsSecureKernel(v14, v13) >> 31) + 2;
        g_TrustedEnvironment = v17;
      }
      if ( (v17 & 2) != 0 )
        SkFreePool(512, Buffer);
      else
        ExFreePoolWithTag(Buffer, 0x62676E43u);
    }
  }
  return RtlNtStatusToDosErrorNoTeb(v15);
}

```

## disassembly

```asm
0x180040b10  push    rbx
0x180040b12  push    rbp
0x180040b13  push    rsi
0x180040b14  push    rdi
0x180040b15  sub     rsp, 98h
0x180040b1c  mov     rax, cs:__security_cookie
0x180040b23  xor     rax, rsp
0x180040b26  mov     [rsp+0B8h+var_30], rax
0x180040b2e  xorps   xmm1, xmm1
0x180040b31  xorps   xmm0, xmm0
0x180040b34  mov     rbp, r9
0x180040b37  mov     esi, r8d
0x180040b3a  mov     rbx, rdx
0x180040b3d  mov     rdi, rcx
0x180040b40  movups  xmmword ptr [rsp+0B8h+Destination.Length], xmm0
0x180040b45  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm1
0x180040b4a  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm1
0x180040b4f  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm1
0x180040b54  cmp     rcx, 0FFFFFFFF80000002h
0x180040b5b  jnz     loc_180040D30
0x180040b61  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180040b68  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180040b6f  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180040b76  movups  xmmword ptr [rsp+0B8h+Source], xmm0
0x180040b7b  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180040b83  movups  [rsp+0B8h+var_48], xmm1
0x180040b88  movsd   qword ptr [rsp+0B8h+var_48+0Eh], xmm0
0x180040b8e  xchg    ax, ax
0x180040b90  cmp     word ptr [rdx+rax*2+2], 0
0x180040b96  lea     rax, [rax+1]
0x180040b9a  jnz     short loc_180040B90
0x180040b9c  lea     edi, ds:26h[rax*2]
0x180040ba3  mov     eax, cs:g_TrustedEnvironment
0x180040ba9  test    eax, eax
0x180040bab  jz      loc_180040CF3
0x180040bb1  mov     edx, edi
0x180040bb3  mov     r8d, 62676E43h
0x180040bb9  test    al, 2
0x180040bbb  jnz     loc_180040D10
0x180040bc1  mov     ecx, 40h ; '@'
0x180040bc6  call    cs:__imp_ExAllocatePool2
0x180040bcd  nop     dword ptr [rax+rax+00h]
0x180040bd2  mov     [rsp+0B8h+Destination.Buffer], rax
0x180040bd7  test    rax, rax
0x180040bda  jz      loc_180040D26
0x180040be0  xor     eax, eax
0x180040be2  mov     [rsp+0B8h+Destination.MaximumLength], di
0x180040be7  lea     rdx, [rsp+0B8h+Source]; Source
0x180040bec  mov     [rsp+0B8h+Destination.Length], ax
0x180040bf1  lea     rcx, [rsp+0B8h+Destination]; Destination
0x180040bf6  call    cs:__imp_RtlAppendUnicodeToString
0x180040bfd  nop     dword ptr [rax+rax+00h]
0x180040c02  mov     rdx, rbx; Source
0x180040c05  lea     rcx, [rsp+0B8h+Destination]; Destination
0x180040c0a  call    cs:__imp_RtlAppendUnicodeToString
0x180040c11  nop     dword ptr [rax+rax+00h]
0x180040c16  xor     edi, edi
0x180040c18  mov     eax, 240h
0x180040c1d  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x180040c25  mov     ecx, 640h
0x180040c2a  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rdi
0x180040c2f  xorps   xmm0, xmm0
0x180040c32  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x180040c37  cmp     esi, 20019h
0x180040c3d  mov     edx, esi; DesiredAccess
0x180040c3f  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180040c45  cmovnz  eax, ecx
0x180040c48  mov     rcx, rbp; KeyHandle
0x180040c4b  mov     [rsp+0B8h+ObjectAttributes.Attributes], eax
0x180040c4f  lea     rax, [rsp+0B8h+Destination]
0x180040c54  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x180040c59  call    cs:__imp_ZwOpenKey
0x180040c60  nop     dword ptr [rax+rax+00h]
0x180040c65  mov     esi, eax
0x180040c67  test    rdi, rdi
0x180040c6a  jnz     short loc_180040C98
0x180040c6c  mov     rbx, [rsp+0B8h+Destination.Buffer]
0x180040c71  test    rbx, rbx
0x180040c74  jz      short loc_180040C98
0x180040c76  mov     eax, cs:g_TrustedEnvironment
0x180040c7c  test    eax, eax
0x180040c7e  jz      short loc_180040CC3
0x180040c80  test    al, 2
0x180040c82  jnz     short loc_180040CDD
0x180040c84  mov     edx, 62676E43h; Tag
0x180040c89  mov     rcx, rbx; P
0x180040c8c  call    cs:__imp_ExFreePoolWithTag
0x180040c93  nop     dword ptr [rax+rax+00h]
0x180040c98  mov     ecx, esi; Status
0x180040c9a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180040ca1  nop     dword ptr [rax+rax+00h]
0x180040ca6  mov     rcx, [rsp+0B8h+var_30]
0x180040cae  xor     rcx, rsp; StackCookie
0x180040cb1  call    __security_check_cookie
0x180040cb6  add     rsp, 98h
0x180040cbd  pop     rdi
0x180040cbe  pop     rsi
0x180040cbf  pop     rbp
0x180040cc0  pop     rbx
0x180040cc1  retn
0x180040cc3  call    cs:__imp_SkIsSecureKernel
0x180040cca  nop     dword ptr [rax+rax+00h]
0x180040ccf  sar     eax, 1Fh
0x180040cd2  add     eax, 2
0x180040cd5  mov     cs:g_TrustedEnvironment, eax
0x180040cdb  jmp     short loc_180040C80
0x180040cdd  mov     rdx, rbx
0x180040ce0  mov     ecx, 200h
0x180040ce5  call    cs:__imp_SkFreePool
0x180040cec  nop     dword ptr [rax+rax+00h]
0x180040cf1  jmp     short loc_180040C98
0x180040cf3  call    cs:__imp_SkIsSecureKernel
0x180040cfa  nop     dword ptr [rax+rax+00h]
0x180040cff  sar     eax, 1Fh
0x180040d02  add     eax, 2
0x180040d05  mov     cs:g_TrustedEnvironment, eax
0x180040d0b  jmp     loc_180040BB1
0x180040d10  mov     ecx, 200h
0x180040d15  call    cs:__imp_SkAllocatePool
0x180040d1c  nop     dword ptr [rax+rax+00h]
0x180040d21  jmp     loc_180040BD2
0x180040d26  mov     eax, 8
0x180040d2b  jmp     loc_180040CA6
0x180040d30  lea     rcx, [rsp+0B8h+Destination]; DestinationString
0x180040d35  call    cs:__imp_RtlInitUnicodeString
0x180040d3c  nop     dword ptr [rax+rax+00h]
0x180040d41  jmp     loc_180040C18
```
