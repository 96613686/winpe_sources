# VerifyRegistryAccess

- ea: `0x180028750`
- end: `0x1800289d1`
- name: `VerifyRegistryAccess`
- size: `641`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ba40`
- `0x180028b40`

## callees

- `0x180028750`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180028806`
- `ntoskrnl!ExAllocatePool2` at `0x180028806`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800288bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800288bf`
- `ntoskrnl!ZwClose` at `0x18002892b`
- `ntoskrnl!ZwClose` at `0x18002892b`
- `ntoskrnl!ObfDereferenceObject` at `0x18002891c`
- `ntoskrnl!ObfDereferenceObject` at `0x18002891c`
- `ntoskrnl!ZwOpenKey` at `0x18002888a`
- `ntoskrnl!ZwOpenKey` at `0x18002888a`
- `ntoskrnl!SkIsSecureKernel` at `0x18002895e`
- `ntoskrnl!SkIsSecureKernel` at `0x180028994`
- `ntoskrnl!SkIsSecureKernel` at `0x18002895e`
- `ntoskrnl!SkIsSecureKernel` at `0x180028994`
- `ntoskrnl!SkAllocatePool` at `0x1800289b6`
- `ntoskrnl!SkAllocatePool` at `0x1800289b6`
- `ntoskrnl!SkFreePool` at `0x180028983`
- `ntoskrnl!SkFreePool` at `0x180028983`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180028908`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180028908`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180028830`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180028843`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180028830`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180028843`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800288cd`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800288cd`

## string_xrefs

- `0x18002878f`: `\Registry\Machine\`

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
0x180028750  mov     [rsp-8+arg_0], rbx
0x180028755  mov     [rsp-8+arg_18], rsi
0x18002875a  push    rbp
0x18002875b  push    rdi
0x18002875c  push    r14
0x18002875e  lea     rbp, [rsp-47h]
0x180028763  sub     rsp, 0B0h
0x18002876a  mov     rax, cs:__security_cookie
0x180028771  xor     rax, rsp
0x180028774  mov     [rbp+57h+var_18], rax
0x180028778  mov     rbx, [rdx]
0x18002877b  xorps   xmm1, xmm1
0x18002877e  xorps   xmm0, xmm0
0x180028781  xor     r14d, r14d
0x180028784  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180028788  mov     esi, r8d
0x18002878b  mov     [rbp+57h+KeyHandle], r14
0x18002878f  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180028796  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002879d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800287a1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800287a5  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800287a9  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x1800287b0  movups  xmmword ptr [rbp+57h+Source], xmm0
0x1800287b4  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x1800287bc  movups  [rbp+57h+var_30], xmm1
0x1800287c0  movsd   qword ptr [rbp+57h+var_30+0Eh], xmm0
0x1800287c5  nop     word ptr [rax+rax+00000000h]
0x1800287d0  cmp     [rbx+rax*2+2], r14w
0x1800287d6  lea     rax, [rax+1]
0x1800287da  jnz     short loc_1800287D0
0x1800287dc  lea     edi, ds:26h[rax*2]
0x1800287e3  mov     eax, cs:g_TrustedEnvironment
0x1800287e9  test    eax, eax
0x1800287eb  jz      loc_180028994
0x1800287f1  mov     edx, edi
0x1800287f3  mov     r8d, 62676E43h
0x1800287f9  test    al, 2
0x1800287fb  jnz     loc_1800289B1
0x180028801  mov     ecx, 40h ; '@'
0x180028806  call    cs:__imp_ExAllocatePool2
0x18002880d  nop     dword ptr [rax+rax+00h]
0x180028812  mov     [rbp+57h+Destination.Buffer], rax
0x180028816  test    rax, rax
0x180028819  jz      loc_1800289C7
0x18002881f  lea     rdx, [rbp+57h+Source]; Source
0x180028823  mov     [rbp+57h+Destination.Length], r14w
0x180028828  lea     rcx, [rbp+57h+Destination]; Destination
0x18002882c  mov     [rbp+57h+Destination.MaximumLength], di
0x180028830  call    cs:__imp_RtlAppendUnicodeToString
0x180028837  nop     dword ptr [rax+rax+00h]
0x18002883c  mov     rdx, rbx; Source
0x18002883f  lea     rcx, [rbp+57h+Destination]; Destination
0x180028843  call    cs:__imp_RtlAppendUnicodeToString
0x18002884a  nop     dword ptr [rax+rax+00h]
0x18002884f  mov     eax, 240h
0x180028854  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002885b  mov     ecx, 640h
0x180028860  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180028864  xorps   xmm0, xmm0
0x180028867  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002886b  cmp     esi, 20019h
0x180028871  mov     edx, esi; DesiredAccess
0x180028873  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180028878  cmovnz  eax, ecx
0x18002887b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18002887f  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x180028882  lea     rax, [rbp+57h+Destination]
0x180028886  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002888a  call    cs:__imp_ZwOpenKey
0x180028891  nop     dword ptr [rax+rax+00h]
0x180028896  mov     rbx, [rbp+57h+Destination.Buffer]
0x18002889a  mov     edi, eax
0x18002889c  test    rbx, rbx
0x18002889f  jz      short loc_1800288CB
0x1800288a1  mov     eax, cs:g_TrustedEnvironment
0x1800288a7  test    eax, eax
0x1800288a9  jz      loc_18002895E
0x1800288af  test    al, 2
0x1800288b1  jnz     loc_18002897B
0x1800288b7  mov     edx, 62676E43h; Tag
0x1800288bc  mov     rcx, rbx; P
0x1800288bf  call    cs:__imp_ExFreePoolWithTag
0x1800288c6  nop     dword ptr [rax+rax+00h]
0x1800288cb  mov     ecx, edi; Status
0x1800288cd  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800288d4  nop     dword ptr [rax+rax+00h]
0x1800288d9  mov     ebx, eax
0x1800288db  test    eax, eax
0x1800288dd  jnz     short loc_180028939
0x1800288df  mov     rdi, [rbp+57h+KeyHandle]
0x1800288e3  lea     rax, [rbp+57h+Destination]
0x1800288e7  mov     [rsp+0C0h+HandleInformation], rax; HandleInformation
0x1800288ec  xor     r9d, r9d; AccessMode
0x1800288ef  lea     rax, [rbp+57h+var_78]
0x1800288f3  mov     qword ptr [rbp+57h+Destination.Length], r14
0x1800288f7  xor     r8d, r8d; ObjectType
0x1800288fa  mov     [rsp+0C0h+Object], rax; Object
0x1800288ff  xor     edx, edx; DesiredAccess
0x180028901  mov     [rbp+57h+var_78], r14
0x180028905  mov     rcx, rdi; Handle
0x180028908  call    cs:__imp_ObReferenceObjectByHandle
0x18002890f  nop     dword ptr [rax+rax+00h]
0x180028914  test    eax, eax
0x180028916  js      short loc_180028937
0x180028918  mov     rcx, [rbp+57h+var_78]; Object
0x18002891c  call    cs:__imp_ObfDereferenceObject
0x180028923  nop     dword ptr [rax+rax+00h]
0x180028928  mov     rcx, rdi; Handle
0x18002892b  call    cs:__imp_ZwClose
0x180028932  nop     dword ptr [rax+rax+00h]
0x180028937  mov     eax, ebx
0x180028939  mov     rcx, [rbp+57h+var_18]
0x18002893d  xor     rcx, rsp; StackCookie
0x180028940  call    __security_check_cookie
0x180028945  lea     r11, [rsp+0C0h+var_10]
0x18002894d  mov     rbx, [r11+20h]
0x180028951  mov     rsi, [r11+38h]
0x180028955  mov     rsp, r11
0x180028958  pop     r14
0x18002895a  pop     rdi
0x18002895b  pop     rbp
0x18002895c  retn
0x18002895e  call    cs:__imp_SkIsSecureKernel
0x180028965  nop     dword ptr [rax+rax+00h]
0x18002896a  sar     eax, 1Fh
0x18002896d  add     eax, 2
0x180028970  mov     cs:g_TrustedEnvironment, eax
0x180028976  jmp     loc_1800288AF
0x18002897b  mov     rdx, rbx
0x18002897e  mov     ecx, 200h
0x180028983  call    cs:__imp_SkFreePool
0x18002898a  nop     dword ptr [rax+rax+00h]
0x18002898f  jmp     loc_1800288CB
0x180028994  call    cs:__imp_SkIsSecureKernel
0x18002899b  nop     dword ptr [rax+rax+00h]
0x1800289a0  sar     eax, 1Fh
0x1800289a3  add     eax, 2
0x1800289a6  mov     cs:g_TrustedEnvironment, eax
0x1800289ac  jmp     loc_1800287F1
0x1800289b1  mov     ecx, 200h
0x1800289b6  call    cs:__imp_SkAllocatePool
0x1800289bd  nop     dword ptr [rax+rax+00h]
0x1800289c2  jmp     loc_180028812
0x1800289c7  mov     eax, 8
0x1800289cc  jmp     loc_180028939
```
