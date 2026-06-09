# KeRegOpenKey

- ea: `0x180036aa0`
- end: `0x180036cd6`
- name: `KeRegOpenKey`
- size: `566`
- prototype: `ULONG __fastcall(void *, const WCHAR *, ACCESS_MASK, void **)`
- caller_count: `19`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800362e8`
- `0x18003651c`
- `0x1800367b8`
- `0x1800422f0`
- `0x180046f18`
- `0x180047100`
- `0x18006fa70`
- `0x18006fd4c`
- `0x180070194`
- `0x18007037c`
- `0x180072330`
- `0x18007257c`
- `0x1800727cc`
- `0x180072b38`
- `0x180072d68`
- `0x180073058`
- `0x1800731fc`
- `0x1800736a4`
- `0x180073700`

## callees

- `0x180036aa0`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180036cc5`
- `ntoskrnl!RtlInitUnicodeString` at `0x180036cc5`
- `ntoskrnl!ExAllocatePool2` at `0x180036b56`
- `ntoskrnl!ExAllocatePool2` at `0x180036b56`
- `ntoskrnl!ExFreePoolWithTag` at `0x180036c1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180036c1c`
- `ntoskrnl!ZwOpenKey` at `0x180036be9`
- `ntoskrnl!ZwOpenKey` at `0x180036be9`
- `ntoskrnl!SkIsSecureKernel` at `0x180036c53`
- `ntoskrnl!SkIsSecureKernel` at `0x180036c83`
- `ntoskrnl!SkIsSecureKernel` at `0x180036c53`
- `ntoskrnl!SkIsSecureKernel` at `0x180036c83`
- `ntoskrnl!SkAllocatePool` at `0x180036ca5`
- `ntoskrnl!SkAllocatePool` at `0x180036ca5`
- `ntoskrnl!SkFreePool` at `0x180036c75`
- `ntoskrnl!SkFreePool` at `0x180036c75`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180036b86`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180036b9a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180036b86`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180036b9a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180036c2a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180036c2a`

## string_xrefs

- `0x180036af1`: `\Registry\Machine\`

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
0x180036aa0  push    rbx
0x180036aa2  push    rbp
0x180036aa3  push    rsi
0x180036aa4  push    rdi
0x180036aa5  sub     rsp, 98h
0x180036aac  mov     rax, cs:__security_cookie
0x180036ab3  xor     rax, rsp
0x180036ab6  mov     [rsp+0B8h+var_30], rax
0x180036abe  xorps   xmm1, xmm1
0x180036ac1  xorps   xmm0, xmm0
0x180036ac4  mov     rbp, r9
0x180036ac7  mov     esi, r8d
0x180036aca  mov     rbx, rdx
0x180036acd  mov     rdi, rcx
0x180036ad0  movups  xmmword ptr [rsp+0B8h+Destination.Length], xmm0
0x180036ad5  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm1
0x180036ada  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm1
0x180036adf  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm1
0x180036ae4  cmp     rcx, 0FFFFFFFF80000002h
0x180036aeb  jnz     loc_180036CC0
0x180036af1  movups  xmm0, xmmword ptr cs:aRegistryMachin_1; "\\Registry\\Machine\\"
0x180036af8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180036aff  movups  xmm1, xmmword ptr cs:aRegistryMachin_1+10h; "y\\Machine\\"
0x180036b06  movups  xmmword ptr [rsp+0B8h+Source], xmm0
0x180036b0b  movsd   xmm0, qword ptr cs:aRegistryMachin_1+1Eh; "ne\\"
0x180036b13  movups  [rsp+0B8h+var_48], xmm1
0x180036b18  movsd   qword ptr [rsp+0B8h+var_48+0Eh], xmm0
0x180036b1e  xchg    ax, ax
0x180036b20  cmp     word ptr [rdx+rax*2+2], 0
0x180036b26  lea     rax, [rax+1]
0x180036b2a  jnz     short loc_180036B20
0x180036b2c  lea     edi, ds:26h[rax*2]
0x180036b33  mov     eax, cs:g_TrustedEnvironment
0x180036b39  test    eax, eax
0x180036b3b  jz      loc_180036C83
0x180036b41  mov     edx, edi
0x180036b43  mov     r8d, 62676E43h
0x180036b49  test    al, 2
0x180036b4b  jnz     loc_180036CA0
0x180036b51  mov     ecx, 40h ; '@'
0x180036b56  call    cs:__imp_ExAllocatePool2
0x180036b5d  nop     dword ptr [rax+rax+00h]
0x180036b62  mov     [rsp+0B8h+Destination.Buffer], rax
0x180036b67  test    rax, rax
0x180036b6a  jz      loc_180036CB6
0x180036b70  xor     eax, eax
0x180036b72  mov     [rsp+0B8h+Destination.MaximumLength], di
0x180036b77  lea     rdx, [rsp+0B8h+Source]; Source
0x180036b7c  mov     [rsp+0B8h+Destination.Length], ax
0x180036b81  lea     rcx, [rsp+0B8h+Destination]; Destination
0x180036b86  call    cs:__imp_RtlAppendUnicodeToString
0x180036b8d  nop     dword ptr [rax+rax+00h]
0x180036b92  mov     rdx, rbx; Source
0x180036b95  lea     rcx, [rsp+0B8h+Destination]; Destination
0x180036b9a  call    cs:__imp_RtlAppendUnicodeToString
0x180036ba1  nop     dword ptr [rax+rax+00h]
0x180036ba6  xor     edi, edi
0x180036ba8  mov     eax, 240h
0x180036bad  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x180036bb5  mov     ecx, 640h
0x180036bba  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rdi
0x180036bbf  xorps   xmm0, xmm0
0x180036bc2  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x180036bc7  cmp     esi, 20019h
0x180036bcd  mov     edx, esi; DesiredAccess
0x180036bcf  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180036bd5  cmovnz  eax, ecx
0x180036bd8  mov     rcx, rbp; KeyHandle
0x180036bdb  mov     [rsp+0B8h+ObjectAttributes.Attributes], eax
0x180036bdf  lea     rax, [rsp+0B8h+Destination]
0x180036be4  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x180036be9  call    cs:__imp_ZwOpenKey
0x180036bf0  nop     dword ptr [rax+rax+00h]
0x180036bf5  mov     esi, eax
0x180036bf7  test    rdi, rdi
0x180036bfa  jnz     short loc_180036C28
0x180036bfc  mov     rbx, [rsp+0B8h+Destination.Buffer]
0x180036c01  test    rbx, rbx
0x180036c04  jz      short loc_180036C28
0x180036c06  mov     eax, cs:g_TrustedEnvironment
0x180036c0c  test    eax, eax
0x180036c0e  jz      short loc_180036C53
0x180036c10  test    al, 2
0x180036c12  jnz     short loc_180036C6D
0x180036c14  mov     edx, 62676E43h; Tag
0x180036c19  mov     rcx, rbx; P
0x180036c1c  call    cs:__imp_ExFreePoolWithTag
0x180036c23  nop     dword ptr [rax+rax+00h]
0x180036c28  mov     ecx, esi; Status
0x180036c2a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180036c31  nop     dword ptr [rax+rax+00h]
0x180036c36  mov     rcx, [rsp+0B8h+var_30]
0x180036c3e  xor     rcx, rsp; StackCookie
0x180036c41  call    __security_check_cookie
0x180036c46  add     rsp, 98h
0x180036c4d  pop     rdi
0x180036c4e  pop     rsi
0x180036c4f  pop     rbp
0x180036c50  pop     rbx
0x180036c51  retn
0x180036c53  call    cs:__imp_SkIsSecureKernel
0x180036c5a  nop     dword ptr [rax+rax+00h]
0x180036c5f  sar     eax, 1Fh
0x180036c62  add     eax, 2
0x180036c65  mov     cs:g_TrustedEnvironment, eax
0x180036c6b  jmp     short loc_180036C10
0x180036c6d  mov     rdx, rbx
0x180036c70  mov     ecx, 200h
0x180036c75  call    cs:__imp_SkFreePool
0x180036c7c  nop     dword ptr [rax+rax+00h]
0x180036c81  jmp     short loc_180036C28
0x180036c83  call    cs:__imp_SkIsSecureKernel
0x180036c8a  nop     dword ptr [rax+rax+00h]
0x180036c8f  sar     eax, 1Fh
0x180036c92  add     eax, 2
0x180036c95  mov     cs:g_TrustedEnvironment, eax
0x180036c9b  jmp     loc_180036B41
0x180036ca0  mov     ecx, 200h
0x180036ca5  call    cs:__imp_SkAllocatePool
0x180036cac  nop     dword ptr [rax+rax+00h]
0x180036cb1  jmp     loc_180036B62
0x180036cb6  mov     eax, 8
0x180036cbb  jmp     loc_180036C36
0x180036cc0  lea     rcx, [rsp+0B8h+Destination]; DestinationString
0x180036cc5  call    cs:__imp_RtlInitUnicodeString
0x180036ccc  nop     dword ptr [rax+rax+00h]
0x180036cd1  jmp     loc_180036BA8
```
