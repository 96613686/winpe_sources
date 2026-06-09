# PrvReg_Acquire

- ea: `0x180018850`
- end: `0x180018ae4`
- name: `PrvReg_Acquire`
- size: `660`
- prototype: `ULONG __fastcall(PERESOURCE Resource, __int64 DesiredAccess)`
- caller_count: `6`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180028c74`
- `0x18006a950`
- `0x18006b8ac`
- `0x18006bf70`
- `0x18006c6a0`
- `0x18006ce40`

## callees

- `0x180018850`
- `0x180018e40`
- `0x180018ec0`
- `0x180036de8`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180018906`
- `ntoskrnl!ExAllocatePool2` at `0x180018906`
- `ntoskrnl!ZwOpenKey` at `0x18001898a`
- `ntoskrnl!ZwOpenKey` at `0x18001898a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800189c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180018a14`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800189c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180018a14`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180018a25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180018ac7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180018a25`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180018ac7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800189e2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800189e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x180018a3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180018a9c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180018a3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x180018a9c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180018a47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180018aa8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180018a47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180018aa8`
- `ntoskrnl!SkIsSecureKernel` at `0x180018a58`
- `ntoskrnl!SkIsSecureKernel` at `0x180018a58`
- `ntoskrnl!SkAllocatePool` at `0x180018a7a`
- `ntoskrnl!SkAllocatePool` at `0x180018a7a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180018930`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180018943`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180018930`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180018943`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800189a3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1800189a3`

## string_xrefs

- `0x18001888f`: `\Registry\Machine\`

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
0x180018850  mov     [rsp-8+arg_10], rbx
0x180018855  push    rbp
0x180018856  push    rsi
0x180018857  push    rdi
0x180018858  push    r14
0x18001885a  push    r15
0x18001885c  lea     rbp, [rsp-37h]
0x180018861  sub     rsp, 0A0h
0x180018868  mov     rax, cs:__security_cookie
0x18001886f  xor     rax, rsp
0x180018872  mov     [rbp+57h+var_28], rax
0x180018876  xorps   xmm1, xmm1
0x180018879  lea     r14, Source; "System\\CurrentControlSet\\Control\\Cry"...
0x180018880  xorps   xmm0, xmm0
0x180018883  xor     eax, eax
0x180018885  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180018889  xor     r15d, r15d
0x18001888c  mov     [rbp+57h+var_84], eax
0x18001888f  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180018896  mov     esi, edx
0x180018898  mov     rdi, rcx
0x18001889b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18001889f  mov     [rbp+57h+KeyHandle], r15
0x1800188a3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800188aa  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800188ae  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800188b2  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x1800188b9  movups  xmmword ptr [rbp+57h+Source], xmm0
0x1800188bd  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x1800188c5  movups  [rbp+57h+var_40], xmm1
0x1800188c9  movsd   qword ptr [rbp+57h+var_40+0Eh], xmm0
0x1800188ce  xchg    ax, ax
0x1800188d0  cmp     [r14+rax*2+2], r15w
0x1800188d6  lea     rax, [rax+1]
0x1800188da  jnz     short loc_1800188D0
0x1800188dc  lea     ebx, ds:26h[rax*2]
0x1800188e3  mov     eax, cs:g_TrustedEnvironment
0x1800188e9  test    eax, eax
0x1800188eb  jz      loc_180018A58
0x1800188f1  mov     edx, ebx
0x1800188f3  mov     r8d, 62676E43h
0x1800188f9  test    al, 2
0x1800188fb  jnz     loc_180018A75
0x180018901  mov     ecx, 40h ; '@'
0x180018906  call    cs:__imp_ExAllocatePool2
0x18001890d  nop     dword ptr [rax+rax+00h]
0x180018912  mov     [rbp+57h+Destination.Buffer], rax
0x180018916  test    rax, rax
0x180018919  jz      loc_180018ADA
0x18001891f  lea     rdx, [rbp+57h+Source]; Source
0x180018923  mov     [rbp+57h+Destination.Length], r15w
0x180018928  lea     rcx, [rbp+57h+Destination]; Destination
0x18001892c  mov     [rbp+57h+Destination.MaximumLength], bx
0x180018930  call    cs:__imp_RtlAppendUnicodeToString
0x180018937  nop     dword ptr [rax+rax+00h]
0x18001893c  mov     rdx, r14; Source
0x18001893f  lea     rcx, [rbp+57h+Destination]; Destination
0x180018943  call    cs:__imp_RtlAppendUnicodeToString
0x18001894a  nop     dword ptr [rax+rax+00h]
0x18001894f  mov     eax, 240h
0x180018954  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001895b  mov     ecx, 640h
0x180018960  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180018964  xorps   xmm0, xmm0
0x180018967  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001896b  cmp     esi, 20019h
0x180018971  mov     edx, esi; DesiredAccess
0x180018973  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180018978  cmovnz  eax, ecx
0x18001897b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001897f  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x180018982  lea     rax, [rbp+57h+Destination]
0x180018986  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001898a  call    cs:__imp_ZwOpenKey
0x180018991  nop     dword ptr [rax+rax+00h]
0x180018996  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x18001899a  mov     ebx, eax
0x18001899c  call    BCryptFree
0x1800189a1  mov     ecx, ebx; Status
0x1800189a3  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800189aa  nop     dword ptr [rax+rax+00h]
0x1800189af  mov     ebx, eax
0x1800189b1  test    eax, eax
0x1800189b3  jnz     short loc_1800189F0
0x1800189b5  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800189b9  call    KeRegCloseKey
0x1800189be  mov     eax, [rdi+78h]
0x1800189c1  test    eax, eax
0x1800189c3  jz      short loc_180018A14
0x1800189c5  call    cs:__imp_KeEnterCriticalRegion
0x1800189cc  nop     dword ptr [rax+rax+00h]
0x1800189d1  mov     dl, 1; Wait
0x1800189d3  mov     rcx, rdi; Resource
0x1800189d6  cmp     esi, 3001Fh
0x1800189dc  jz      loc_180018AC7
0x1800189e2  call    cs:__imp_ExAcquireResourceSharedLite
0x1800189e9  nop     dword ptr [rax+rax+00h]
0x1800189ee  mov     eax, ebx
0x1800189f0  mov     rcx, [rbp+57h+var_28]
0x1800189f4  xor     rcx, rsp; StackCookie
0x1800189f7  call    __security_check_cookie
0x1800189fc  mov     rbx, [rsp+0C0h+arg_10]
0x180018a04  add     rsp, 0A0h
0x180018a0b  pop     r15
0x180018a0d  pop     r14
0x180018a0f  pop     rdi
0x180018a10  pop     rsi
0x180018a11  pop     rbp
0x180018a12  retn
0x180018a14  call    cs:__imp_KeEnterCriticalRegion
0x180018a1b  nop     dword ptr [rax+rax+00h]
0x180018a20  mov     dl, 1; Wait
0x180018a22  mov     rcx, rdi; Resource
0x180018a25  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180018a2c  nop     dword ptr [rax+rax+00h]
0x180018a31  mov     eax, [rdi+78h]
0x180018a34  test    eax, eax
0x180018a36  jz      short loc_180018A8B
0x180018a38  mov     rcx, rdi; Resource
0x180018a3b  call    cs:__imp_ExReleaseResourceLite
0x180018a42  nop     dword ptr [rax+rax+00h]
0x180018a47  call    cs:__imp_KeLeaveCriticalRegion
0x180018a4e  nop     dword ptr [rax+rax+00h]
0x180018a53  jmp     loc_1800189C5
0x180018a58  call    cs:__imp_SkIsSecureKernel
0x180018a5f  nop     dword ptr [rax+rax+00h]
0x180018a64  sar     eax, 1Fh
0x180018a67  add     eax, 2
0x180018a6a  mov     cs:g_TrustedEnvironment, eax
0x180018a70  jmp     loc_1800188F1
0x180018a75  mov     ecx, 200h
0x180018a7a  call    cs:__imp_SkAllocatePool
0x180018a81  nop     dword ptr [rax+rax+00h]
0x180018a86  jmp     loc_180018912
0x180018a8b  mov     rcx, rdi
0x180018a8e  call    _PrvReg_LoadRoot
0x180018a93  mov     ebx, eax
0x180018a95  test    eax, eax
0x180018a97  jz      short loc_180018ABB
0x180018a99  mov     rcx, rdi; Resource
0x180018a9c  call    cs:__imp_ExReleaseResourceLite
0x180018aa3  nop     dword ptr [rax+rax+00h]
0x180018aa8  call    cs:__imp_KeLeaveCriticalRegion
0x180018aaf  nop     dword ptr [rax+rax+00h]
0x180018ab4  mov     eax, ebx
0x180018ab6  jmp     loc_1800189F0
0x180018abb  mov     dword ptr [rdi+78h], 1
0x180018ac2  jmp     loc_180018A38
0x180018ac7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180018ace  nop     dword ptr [rax+rax+00h]
0x180018ad3  mov     eax, ebx
0x180018ad5  jmp     loc_1800189F0
0x180018ada  mov     eax, 8
0x180018adf  jmp     loc_1800189F0
```
