# PrvReg_Acquire

- ea: `0x1800258d0`
- end: `0x180025b64`
- name: `PrvReg_Acquire`
- size: `660`
- prototype: `__int64 __fastcall(PERESOURCE Resource, ACCESS_MASK DesiredAccess)`
- caller_count: `6`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180035ce4`
- `0x1800740f0`
- `0x18007504c`
- `0x180075710`
- `0x180075e40`
- `0x1800765e0`

## callees

- `0x1800258d0`
- `0x180025ec0`
- `0x180025f40`
- `0x180040358`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180025986`
- `ntoskrnl!ExAllocatePool2` at `0x180025986`
- `ntoskrnl!ZwOpenKey` at `0x180025a0a`
- `ntoskrnl!ZwOpenKey` at `0x180025a0a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025a45`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025a94`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025a45`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180025a94`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180025aa5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180025b47`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180025aa5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180025b47`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180025a62`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180025a62`
- `ntoskrnl!ExReleaseResourceLite` at `0x180025abb`
- `ntoskrnl!ExReleaseResourceLite` at `0x180025b1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180025abb`
- `ntoskrnl!ExReleaseResourceLite` at `0x180025b1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025ac7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025b28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025ac7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025b28`
- `ntoskrnl!SkIsSecureKernel` at `0x180025ad8`
- `ntoskrnl!SkIsSecureKernel` at `0x180025ad8`
- `ntoskrnl!SkAllocatePool` at `0x180025afa`
- `ntoskrnl!SkAllocatePool` at `0x180025afa`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800259b0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800259c3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800259b0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800259c3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180025a23`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180025a23`

## string_xrefs

- `0x18002590f`: `\Registry\Machine\`

## pseudocode

```c
ULONG __fastcall PrvReg_Acquire(PERESOURCE Resource, __int64 DesiredAccess)
{
  ACCESS_MASK v2; // esi
  __int64 v4; // rax
  unsigned int v6; // ebx
  WCHAR *Pool; // rax
  ULONG v8; // eax
  NTSTATUS v9; // ebx
  ULONG result; // eax
  int Root; // ebx
  void *KeyHandle; // [rsp+20h] [rbp-49h] BYREF
  _UNICODE_STRING Destination; // [rsp+28h] [rbp-41h] BYREF
  int v14; // [rsp+3Ch] [rbp-2Dh]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  WCHAR Source[20]; // [rsp+70h] [rbp+7h] BYREF

  Destination = 0;
  v14 = 0;
  v2 = DesiredAccess;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyHandle = 0;
  v4 = -1;
  wcscpy(Source, L"\\Registry\\Machne\\");
  while ( ::Source[++v4] != 0 )
    ;
  v6 = 2 * v4 + 38;
  LOBYTE(v4) = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
  {
    LODWORD(v4) = ((int)SkIsSecureKernel(Resource, DesiredAccess) >> 31) + 2;
    g_TrustedEnvironment = v4;
  }
  if ( (v4 & 2) != 0 )
    Pool = (WCHAR *)SkAllocatePool(512, v6, 1650945603);
  else
    Pool = (WCHAR *)ExAllocatePool2(64, v6, 1650945603);
  Destination.Buffer = Pool;
  if ( !Pool )
    return 8;
  Destination.Length = 0;
  Destination.MaximumLength = v6;
  RtlAppendUnicodeToString(&Destination, Source);
  RtlAppendUnicodeToString(&Destination, L"System\\CurrentControlSet\\Control\\Cryptography\\Providers");
  v8 = 576;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( v2 != 131097 )
    v8 = 1600;
  ObjectAttributes.Attributes = v8;
  ObjectAttributes.ObjectName = &Destination;
  v9 = ZwOpenKey(&KeyHandle, v2, &ObjectAttributes);
  BCryptFree(Destination.Buffer);
  result = RtlNtStatusToDosErrorNoTeb(v9);
  if ( !result )
  {
    KeRegCloseKey(KeyHandle);
    if ( !LODWORD(Resource[1].OwnerTable) )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(Resource, 1u);
      if ( !LODWORD(Resource[1].OwnerTable) )
      {
        Root = PrvReg_LoadRoot(Resource);
        if ( Root )
        {
          ExReleaseResourceLite(Resource);
          KeLeaveCriticalRegion();
          return Root;
        }
        LODWORD(Resource[1].OwnerTable) = 1;
      }
      ExReleaseResourceLite(Resource);
      KeLeaveCriticalRegion();
    }
    KeEnterCriticalRegion();
    if ( v2 == 196639 )
    {
      ExAcquireResourceExclusiveLite(Resource, 1u);
      return 0;
    }
    else
    {
      ExAcquireResourceSharedLite(Resource, 1u);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800258d0  mov     [rsp-8+arg_10], rbx
0x1800258d5  push    rbp
0x1800258d6  push    rsi
0x1800258d7  push    rdi
0x1800258d8  push    r14
0x1800258da  push    r15
0x1800258dc  lea     rbp, [rsp-37h]
0x1800258e1  sub     rsp, 0A0h
0x1800258e8  mov     rax, cs:__security_cookie
0x1800258ef  xor     rax, rsp
0x1800258f2  mov     [rbp+57h+var_28], rax
0x1800258f6  xorps   xmm1, xmm1
0x1800258f9  lea     r14, Source; "System\\CurrentControlSet\\Control\\Cry"...
0x180025900  xorps   xmm0, xmm0
0x180025903  xor     eax, eax
0x180025905  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180025909  xor     r15d, r15d
0x18002590c  mov     [rbp+57h+var_84], eax
0x18002590f  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180025916  mov     esi, edx
0x180025918  mov     rdi, rcx
0x18002591b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18002591f  mov     [rbp+57h+KeyHandle], r15
0x180025923  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002592a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18002592e  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180025932  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180025939  movups  xmmword ptr [rbp+57h+Source], xmm0
0x18002593d  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180025945  movups  [rbp+57h+var_40], xmm1
0x180025949  movsd   qword ptr [rbp+57h+var_40+0Eh], xmm0
0x18002594e  xchg    ax, ax
0x180025950  cmp     [r14+rax*2+2], r15w
0x180025956  lea     rax, [rax+1]
0x18002595a  jnz     short loc_180025950
0x18002595c  lea     ebx, ds:26h[rax*2]
0x180025963  mov     eax, cs:g_TrustedEnvironment
0x180025969  test    eax, eax
0x18002596b  jz      loc_180025AD8
0x180025971  mov     edx, ebx
0x180025973  mov     r8d, 62676E43h
0x180025979  test    al, 2
0x18002597b  jnz     loc_180025AF5
0x180025981  mov     ecx, 40h ; '@'
0x180025986  call    cs:__imp_ExAllocatePool2
0x18002598d  nop     dword ptr [rax+rax+00h]
0x180025992  mov     [rbp+57h+Destination.Buffer], rax
0x180025996  test    rax, rax
0x180025999  jz      loc_180025B5A
0x18002599f  lea     rdx, [rbp+57h+Source]; Source
0x1800259a3  mov     [rbp+57h+Destination.Length], r15w
0x1800259a8  lea     rcx, [rbp+57h+Destination]; Destination
0x1800259ac  mov     [rbp+57h+Destination.MaximumLength], bx
0x1800259b0  call    cs:__imp_RtlAppendUnicodeToString
0x1800259b7  nop     dword ptr [rax+rax+00h]
0x1800259bc  mov     rdx, r14; Source
0x1800259bf  lea     rcx, [rbp+57h+Destination]; Destination
0x1800259c3  call    cs:__imp_RtlAppendUnicodeToString
0x1800259ca  nop     dword ptr [rax+rax+00h]
0x1800259cf  mov     eax, 240h
0x1800259d4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800259db  mov     ecx, 640h
0x1800259e0  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800259e4  xorps   xmm0, xmm0
0x1800259e7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800259eb  cmp     esi, 20019h
0x1800259f1  mov     edx, esi; DesiredAccess
0x1800259f3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800259f8  cmovnz  eax, ecx
0x1800259fb  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800259ff  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x180025a02  lea     rax, [rbp+57h+Destination]
0x180025a06  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180025a0a  call    cs:__imp_ZwOpenKey
0x180025a11  nop     dword ptr [rax+rax+00h]
0x180025a16  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x180025a1a  mov     ebx, eax
0x180025a1c  call    BCryptFree
0x180025a21  mov     ecx, ebx; Status
0x180025a23  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180025a2a  nop     dword ptr [rax+rax+00h]
0x180025a2f  mov     ebx, eax
0x180025a31  test    eax, eax
0x180025a33  jnz     short loc_180025A70
0x180025a35  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180025a39  call    KeRegCloseKey
0x180025a3e  mov     eax, [rdi+78h]
0x180025a41  test    eax, eax
0x180025a43  jz      short loc_180025A94
0x180025a45  call    cs:__imp_KeEnterCriticalRegion
0x180025a4c  nop     dword ptr [rax+rax+00h]
0x180025a51  mov     dl, 1; Wait
0x180025a53  mov     rcx, rdi; Resource
0x180025a56  cmp     esi, 3001Fh
0x180025a5c  jz      loc_180025B47
0x180025a62  call    cs:__imp_ExAcquireResourceSharedLite
0x180025a69  nop     dword ptr [rax+rax+00h]
0x180025a6e  mov     eax, ebx
0x180025a70  mov     rcx, [rbp+57h+var_28]
0x180025a74  xor     rcx, rsp; StackCookie
0x180025a77  call    __security_check_cookie
0x180025a7c  mov     rbx, [rsp+0C0h+arg_10]
0x180025a84  add     rsp, 0A0h
0x180025a8b  pop     r15
0x180025a8d  pop     r14
0x180025a8f  pop     rdi
0x180025a90  pop     rsi
0x180025a91  pop     rbp
0x180025a92  retn
0x180025a94  call    cs:__imp_KeEnterCriticalRegion
0x180025a9b  nop     dword ptr [rax+rax+00h]
0x180025aa0  mov     dl, 1; Wait
0x180025aa2  mov     rcx, rdi; Resource
0x180025aa5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180025aac  nop     dword ptr [rax+rax+00h]
0x180025ab1  mov     eax, [rdi+78h]
0x180025ab4  test    eax, eax
0x180025ab6  jz      short loc_180025B0B
0x180025ab8  mov     rcx, rdi; Resource
0x180025abb  call    cs:__imp_ExReleaseResourceLite
0x180025ac2  nop     dword ptr [rax+rax+00h]
0x180025ac7  call    cs:__imp_KeLeaveCriticalRegion
0x180025ace  nop     dword ptr [rax+rax+00h]
0x180025ad3  jmp     loc_180025A45
0x180025ad8  call    cs:__imp_SkIsSecureKernel
0x180025adf  nop     dword ptr [rax+rax+00h]
0x180025ae4  sar     eax, 1Fh
0x180025ae7  add     eax, 2
0x180025aea  mov     cs:g_TrustedEnvironment, eax
0x180025af0  jmp     loc_180025971
0x180025af5  mov     ecx, 200h
0x180025afa  call    cs:__imp_SkAllocatePool
0x180025b01  nop     dword ptr [rax+rax+00h]
0x180025b06  jmp     loc_180025992
0x180025b0b  mov     rcx, rdi
0x180025b0e  call    _PrvReg_LoadRoot
0x180025b13  mov     ebx, eax
0x180025b15  test    eax, eax
0x180025b17  jz      short loc_180025B3B
0x180025b19  mov     rcx, rdi; Resource
0x180025b1c  call    cs:__imp_ExReleaseResourceLite
0x180025b23  nop     dword ptr [rax+rax+00h]
0x180025b28  call    cs:__imp_KeLeaveCriticalRegion
0x180025b2f  nop     dword ptr [rax+rax+00h]
0x180025b34  mov     eax, ebx
0x180025b36  jmp     loc_180025A70
0x180025b3b  mov     dword ptr [rdi+78h], 1
0x180025b42  jmp     loc_180025AB8
0x180025b47  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180025b4e  nop     dword ptr [rax+rax+00h]
0x180025b53  mov     eax, ebx
0x180025b55  jmp     loc_180025A70
0x180025b5a  mov     eax, 8
0x180025b5f  jmp     loc_180025A70
```
