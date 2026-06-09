# KeRegOpenKey

- ea: `0x1800375a0`
- end: `0x1800377d6`
- name: `KeRegOpenKey`
- size: `566`
- prototype: `ULONG __fastcall(void *, const WCHAR *, ACCESS_MASK, void **)`
- caller_count: `19`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180036de8`
- `0x18003701c`
- `0x1800372b8`
- `0x180042d80`
- `0x1800479a8`
- `0x180047b90`
- `0x180070470`
- `0x18007074c`
- `0x180070b94`
- `0x180070d7c`
- `0x180072d30`
- `0x180072f7c`
- `0x1800731cc`
- `0x180073538`
- `0x180073768`
- `0x180073a58`
- `0x180073bfc`
- `0x1800740a4`
- `0x180074100`

## callees

- `0x1800375a0`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800377c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800377c5`
- `ntoskrnl!ExAllocatePool2` at `0x180037656`
- `ntoskrnl!ExAllocatePool2` at `0x180037656`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003771c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003771c`
- `ntoskrnl!ZwOpenKey` at `0x1800376e9`
- `ntoskrnl!ZwOpenKey` at `0x1800376e9`
- `ntoskrnl!SkIsSecureKernel` at `0x180037753`
- `ntoskrnl!SkIsSecureKernel` at `0x180037783`
- `ntoskrnl!SkIsSecureKernel` at `0x180037753`
- `ntoskrnl!SkIsSecureKernel` at `0x180037783`
- `ntoskrnl!SkAllocatePool` at `0x1800377a5`
- `ntoskrnl!SkAllocatePool` at `0x1800377a5`
- `ntoskrnl!SkFreePool` at `0x180037775`
- `ntoskrnl!SkFreePool` at `0x180037775`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180037686`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003769a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180037686`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003769a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18003772a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18003772a`

## string_xrefs

- `0x1800375f1`: `\Registry\Machine\`

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
0x1800375a0  push    rbx
0x1800375a2  push    rbp
0x1800375a3  push    rsi
0x1800375a4  push    rdi
0x1800375a5  sub     rsp, 98h
0x1800375ac  mov     rax, cs:__security_cookie
0x1800375b3  xor     rax, rsp
0x1800375b6  mov     [rsp+0B8h+var_30], rax
0x1800375be  xorps   xmm1, xmm1
0x1800375c1  xorps   xmm0, xmm0
0x1800375c4  mov     rbp, r9
0x1800375c7  mov     esi, r8d
0x1800375ca  mov     rbx, rdx
0x1800375cd  mov     rdi, rcx
0x1800375d0  movups  xmmword ptr [rsp+0B8h+Destination.Length], xmm0
0x1800375d5  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm1
0x1800375da  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm1
0x1800375df  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800375e4  cmp     rcx, 0FFFFFFFF80000002h
0x1800375eb  jnz     loc_1800377C0
0x1800375f1  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x1800375f8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800375ff  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180037606  movups  xmmword ptr [rsp+0B8h+Source], xmm0
0x18003760b  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180037613  movups  [rsp+0B8h+var_48], xmm1
0x180037618  movsd   qword ptr [rsp+0B8h+var_48+0Eh], xmm0
0x18003761e  xchg    ax, ax
0x180037620  cmp     word ptr [rdx+rax*2+2], 0
0x180037626  lea     rax, [rax+1]
0x18003762a  jnz     short loc_180037620
0x18003762c  lea     edi, ds:26h[rax*2]
0x180037633  mov     eax, cs:g_TrustedEnvironment
0x180037639  test    eax, eax
0x18003763b  jz      loc_180037783
0x180037641  mov     edx, edi
0x180037643  mov     r8d, 62676E43h
0x180037649  test    al, 2
0x18003764b  jnz     loc_1800377A0
0x180037651  mov     ecx, 40h ; '@'
0x180037656  call    cs:__imp_ExAllocatePool2
0x18003765d  nop     dword ptr [rax+rax+00h]
0x180037662  mov     [rsp+0B8h+Destination.Buffer], rax
0x180037667  test    rax, rax
0x18003766a  jz      loc_1800377B6
0x180037670  xor     eax, eax
0x180037672  mov     [rsp+0B8h+Destination.MaximumLength], di
0x180037677  lea     rdx, [rsp+0B8h+Source]; Source
0x18003767c  mov     [rsp+0B8h+Destination.Length], ax
0x180037681  lea     rcx, [rsp+0B8h+Destination]; Destination
0x180037686  call    cs:__imp_RtlAppendUnicodeToString
0x18003768d  nop     dword ptr [rax+rax+00h]
0x180037692  mov     rdx, rbx; Source
0x180037695  lea     rcx, [rsp+0B8h+Destination]; Destination
0x18003769a  call    cs:__imp_RtlAppendUnicodeToString
0x1800376a1  nop     dword ptr [rax+rax+00h]
0x1800376a6  xor     edi, edi
0x1800376a8  mov     eax, 240h
0x1800376ad  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x1800376b5  mov     ecx, 640h
0x1800376ba  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rdi
0x1800376bf  xorps   xmm0, xmm0
0x1800376c2  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x1800376c7  cmp     esi, 20019h
0x1800376cd  mov     edx, esi; DesiredAccess
0x1800376cf  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800376d5  cmovnz  eax, ecx
0x1800376d8  mov     rcx, rbp; KeyHandle
0x1800376db  mov     [rsp+0B8h+ObjectAttributes.Attributes], eax
0x1800376df  lea     rax, [rsp+0B8h+Destination]
0x1800376e4  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x1800376e9  call    cs:__imp_ZwOpenKey
0x1800376f0  nop     dword ptr [rax+rax+00h]
0x1800376f5  mov     esi, eax
0x1800376f7  test    rdi, rdi
0x1800376fa  jnz     short loc_180037728
0x1800376fc  mov     rbx, [rsp+0B8h+Destination.Buffer]
0x180037701  test    rbx, rbx
0x180037704  jz      short loc_180037728
0x180037706  mov     eax, cs:g_TrustedEnvironment
0x18003770c  test    eax, eax
0x18003770e  jz      short loc_180037753
0x180037710  test    al, 2
0x180037712  jnz     short loc_18003776D
0x180037714  mov     edx, 62676E43h; Tag
0x180037719  mov     rcx, rbx; P
0x18003771c  call    cs:__imp_ExFreePoolWithTag
0x180037723  nop     dword ptr [rax+rax+00h]
0x180037728  mov     ecx, esi; Status
0x18003772a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180037731  nop     dword ptr [rax+rax+00h]
0x180037736  mov     rcx, [rsp+0B8h+var_30]
0x18003773e  xor     rcx, rsp; StackCookie
0x180037741  call    __security_check_cookie
0x180037746  add     rsp, 98h
0x18003774d  pop     rdi
0x18003774e  pop     rsi
0x18003774f  pop     rbp
0x180037750  pop     rbx
0x180037751  retn
0x180037753  call    cs:__imp_SkIsSecureKernel
0x18003775a  nop     dword ptr [rax+rax+00h]
0x18003775f  sar     eax, 1Fh
0x180037762  add     eax, 2
0x180037765  mov     cs:g_TrustedEnvironment, eax
0x18003776b  jmp     short loc_180037710
0x18003776d  mov     rdx, rbx
0x180037770  mov     ecx, 200h
0x180037775  call    cs:__imp_SkFreePool
0x18003777c  nop     dword ptr [rax+rax+00h]
0x180037781  jmp     short loc_180037728
0x180037783  call    cs:__imp_SkIsSecureKernel
0x18003778a  nop     dword ptr [rax+rax+00h]
0x18003778f  sar     eax, 1Fh
0x180037792  add     eax, 2
0x180037795  mov     cs:g_TrustedEnvironment, eax
0x18003779b  jmp     loc_180037641
0x1800377a0  mov     ecx, 200h
0x1800377a5  call    cs:__imp_SkAllocatePool
0x1800377ac  nop     dword ptr [rax+rax+00h]
0x1800377b1  jmp     loc_180037662
0x1800377b6  mov     eax, 8
0x1800377bb  jmp     loc_180037736
0x1800377c0  lea     rcx, [rsp+0B8h+Destination]; DestinationString
0x1800377c5  call    cs:__imp_RtlInitUnicodeString
0x1800377cc  nop     dword ptr [rax+rax+00h]
0x1800377d1  jmp     loc_1800376A8
```
