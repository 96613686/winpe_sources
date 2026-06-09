# PrvReg_Acquire

- ea: `0x18001b7a0`
- end: `0x18001ba34`
- name: `PrvReg_Acquire`
- size: `660`
- prototype: `ULONG __fastcall(PERESOURCE Resource, __int64 DesiredAccess)`
- caller_count: `6`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002bbb4`
- `0x180069f50`
- `0x18006aeac`
- `0x18006b570`
- `0x18006bca0`
- `0x18006c440`

## callees

- `0x18001b7a0`
- `0x18001bd90`
- `0x18001be10`
- `0x1800362e8`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18001b856`
- `ntoskrnl!ExAllocatePool2` at `0x18001b856`
- `ntoskrnl!ZwOpenKey` at `0x18001b8da`
- `ntoskrnl!ZwOpenKey` at `0x18001b8da`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001b915`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001b964`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001b915`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001b964`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001b975`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001ba17`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001b975`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18001ba17`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18001b932`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x18001b932`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001b98b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001b9ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001b98b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001b9ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001b997`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001b9f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001b997`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001b9f8`
- `ntoskrnl!SkIsSecureKernel` at `0x18001b9a8`
- `ntoskrnl!SkIsSecureKernel` at `0x18001b9a8`
- `ntoskrnl!SkAllocatePool` at `0x18001b9ca`
- `ntoskrnl!SkAllocatePool` at `0x18001b9ca`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001b880`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001b893`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001b880`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18001b893`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18001b8f3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18001b8f3`

## string_xrefs

- `0x18001b7df`: `\Registry\Machine\`

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
  ULONG Root; // ebx
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
  Root = result;
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
      return Root;
    }
    else
    {
      ExAcquireResourceSharedLite(Resource, 1u);
      return Root;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b7a0  mov     [rsp-8+arg_10], rbx
0x18001b7a5  push    rbp
0x18001b7a6  push    rsi
0x18001b7a7  push    rdi
0x18001b7a8  push    r14
0x18001b7aa  push    r15
0x18001b7ac  lea     rbp, [rsp-37h]
0x18001b7b1  sub     rsp, 0A0h
0x18001b7b8  mov     rax, cs:__security_cookie
0x18001b7bf  xor     rax, rsp
0x18001b7c2  mov     [rbp+57h+var_28], rax
0x18001b7c6  xorps   xmm1, xmm1
0x18001b7c9  lea     r14, Source; "System\\CurrentControlSet\\Control\\Cry"...
0x18001b7d0  xorps   xmm0, xmm0
0x18001b7d3  xor     eax, eax
0x18001b7d5  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x18001b7d9  xor     r15d, r15d
0x18001b7dc  mov     [rbp+57h+var_84], eax
0x18001b7df  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x18001b7e6  mov     esi, edx
0x18001b7e8  mov     rdi, rcx
0x18001b7eb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18001b7ef  mov     [rbp+57h+KeyHandle], r15
0x18001b7f3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001b7fa  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18001b7fe  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18001b802  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x18001b809  movups  xmmword ptr [rbp+57h+Source], xmm0
0x18001b80d  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x18001b815  movups  [rbp+57h+var_40], xmm1
0x18001b819  movsd   qword ptr [rbp+57h+var_40+0Eh], xmm0
0x18001b81e  xchg    ax, ax
0x18001b820  cmp     [r14+rax*2+2], r15w
0x18001b826  lea     rax, [rax+1]
0x18001b82a  jnz     short loc_18001B820
0x18001b82c  lea     ebx, ds:26h[rax*2]
0x18001b833  mov     eax, cs:g_TrustedEnvironment
0x18001b839  test    eax, eax
0x18001b83b  jz      loc_18001B9A8
0x18001b841  mov     edx, ebx
0x18001b843  mov     r8d, 62676E43h
0x18001b849  test    al, 2
0x18001b84b  jnz     loc_18001B9C5
0x18001b851  mov     ecx, 40h ; '@'
0x18001b856  call    cs:__imp_ExAllocatePool2
0x18001b85d  nop     dword ptr [rax+rax+00h]
0x18001b862  mov     [rbp+57h+Destination.Buffer], rax
0x18001b866  test    rax, rax
0x18001b869  jz      loc_18001BA2A
0x18001b86f  lea     rdx, [rbp+57h+Source]; Source
0x18001b873  mov     [rbp+57h+Destination.Length], r15w
0x18001b878  lea     rcx, [rbp+57h+Destination]; Destination
0x18001b87c  mov     [rbp+57h+Destination.MaximumLength], bx
0x18001b880  call    cs:__imp_RtlAppendUnicodeToString
0x18001b887  nop     dword ptr [rax+rax+00h]
0x18001b88c  mov     rdx, r14; Source
0x18001b88f  lea     rcx, [rbp+57h+Destination]; Destination
0x18001b893  call    cs:__imp_RtlAppendUnicodeToString
0x18001b89a  nop     dword ptr [rax+rax+00h]
0x18001b89f  mov     eax, 240h
0x18001b8a4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001b8ab  mov     ecx, 640h
0x18001b8b0  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18001b8b4  xorps   xmm0, xmm0
0x18001b8b7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001b8bb  cmp     esi, 20019h
0x18001b8c1  mov     edx, esi; DesiredAccess
0x18001b8c3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001b8c8  cmovnz  eax, ecx
0x18001b8cb  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001b8cf  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x18001b8d2  lea     rax, [rbp+57h+Destination]
0x18001b8d6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001b8da  call    cs:__imp_ZwOpenKey
0x18001b8e1  nop     dword ptr [rax+rax+00h]
0x18001b8e6  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x18001b8ea  mov     ebx, eax
0x18001b8ec  call    BCryptFree
0x18001b8f1  mov     ecx, ebx; Status
0x18001b8f3  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001b8fa  nop     dword ptr [rax+rax+00h]
0x18001b8ff  mov     ebx, eax
0x18001b901  test    eax, eax
0x18001b903  jnz     short loc_18001B940
0x18001b905  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18001b909  call    KeRegCloseKey
0x18001b90e  mov     eax, [rdi+78h]
0x18001b911  test    eax, eax
0x18001b913  jz      short loc_18001B964
0x18001b915  call    cs:__imp_KeEnterCriticalRegion
0x18001b91c  nop     dword ptr [rax+rax+00h]
0x18001b921  mov     dl, 1; Wait
0x18001b923  mov     rcx, rdi; Resource
0x18001b926  cmp     esi, 3001Fh
0x18001b92c  jz      loc_18001BA17
0x18001b932  call    cs:__imp_ExAcquireResourceSharedLite
0x18001b939  nop     dword ptr [rax+rax+00h]
0x18001b93e  mov     eax, ebx
0x18001b940  mov     rcx, [rbp+57h+var_28]
0x18001b944  xor     rcx, rsp; StackCookie
0x18001b947  call    __security_check_cookie
0x18001b94c  mov     rbx, [rsp+0C0h+arg_10]
0x18001b954  add     rsp, 0A0h
0x18001b95b  pop     r15
0x18001b95d  pop     r14
0x18001b95f  pop     rdi
0x18001b960  pop     rsi
0x18001b961  pop     rbp
0x18001b962  retn
0x18001b964  call    cs:__imp_KeEnterCriticalRegion
0x18001b96b  nop     dword ptr [rax+rax+00h]
0x18001b970  mov     dl, 1; Wait
0x18001b972  mov     rcx, rdi; Resource
0x18001b975  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18001b97c  nop     dword ptr [rax+rax+00h]
0x18001b981  mov     eax, [rdi+78h]
0x18001b984  test    eax, eax
0x18001b986  jz      short loc_18001B9DB
0x18001b988  mov     rcx, rdi; Resource
0x18001b98b  call    cs:__imp_ExReleaseResourceLite
0x18001b992  nop     dword ptr [rax+rax+00h]
0x18001b997  call    cs:__imp_KeLeaveCriticalRegion
0x18001b99e  nop     dword ptr [rax+rax+00h]
0x18001b9a3  jmp     loc_18001B915
0x18001b9a8  call    cs:__imp_SkIsSecureKernel
0x18001b9af  nop     dword ptr [rax+rax+00h]
0x18001b9b4  sar     eax, 1Fh
0x18001b9b7  add     eax, 2
0x18001b9ba  mov     cs:g_TrustedEnvironment, eax
0x18001b9c0  jmp     loc_18001B841
0x18001b9c5  mov     ecx, 200h
0x18001b9ca  call    cs:__imp_SkAllocatePool
0x18001b9d1  nop     dword ptr [rax+rax+00h]
0x18001b9d6  jmp     loc_18001B862
0x18001b9db  mov     rcx, rdi
0x18001b9de  call    _PrvReg_LoadRoot
0x18001b9e3  mov     ebx, eax
0x18001b9e5  test    eax, eax
0x18001b9e7  jz      short loc_18001BA0B
0x18001b9e9  mov     rcx, rdi; Resource
0x18001b9ec  call    cs:__imp_ExReleaseResourceLite
0x18001b9f3  nop     dword ptr [rax+rax+00h]
0x18001b9f8  call    cs:__imp_KeLeaveCriticalRegion
0x18001b9ff  nop     dword ptr [rax+rax+00h]
0x18001ba04  mov     eax, ebx
0x18001ba06  jmp     loc_18001B940
0x18001ba0b  mov     dword ptr [rdi+78h], 1
0x18001ba12  jmp     loc_18001B988
0x18001ba17  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18001ba1e  nop     dword ptr [rax+rax+00h]
0x18001ba23  mov     eax, ebx
0x18001ba25  jmp     loc_18001B940
0x18001ba2a  mov     eax, 8
0x18001ba2f  jmp     loc_18001B940
```
