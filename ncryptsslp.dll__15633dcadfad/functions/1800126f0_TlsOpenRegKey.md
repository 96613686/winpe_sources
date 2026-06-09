# TlsOpenRegKey

- ea: `0x1800126f0`
- end: `0x180012832`
- name: `TlsOpenRegKey`
- size: `322`
- prototype: `__int64 __fastcall(PCWSTR Source, PCWSTR, PHANDLE KeyHandle)`
- caller_count: `6`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012578`
- `0x18001d8e8`
- `0x180023e34`
- `0x180024190`
- `0x180024650`
- `0x180024a3c`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x1800126f0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001272e`
- `ntdll!RtlInitUnicodeString` at `0x18001272e`
- `ntdll!NtOpenKey` at `0x180012769`
- `ntdll!NtOpenKey` at `0x180012769`
- `ntdll!RtlAppendUnicodeToString` at `0x1800127d2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800127e2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800127ee`
- `ntdll!RtlAppendUnicodeToString` at `0x1800127d2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800127e2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800127ee`

## pseudocode

```c
__int64 __fastcall TlsOpenRegKey(PCWSTR Source, PCWSTR a2, PHANDLE KeyHandle)
{
  struct _UNICODE_STRING *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rcx
  USHORT v10; // r14
  struct _UNICODE_STRING *v11; // rax
  struct _UNICODE_STRING v13; // [rsp+28h] [rbp-80h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-70h] BYREF

  v13 = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !a2 )
  {
    RtlInitUnicodeString(&v13, Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &v13;
LABEL_3:
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = NtOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
    goto LABEL_10;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  do
    ++v8;
  while ( Source[v8] );
  v10 = 2 * (v9 + v8) + 4;
  v11 = (struct _UNICODE_STRING *)SafeAllocaAllocateFromHeap((unsigned int)(2 * (v9 + v8) + 4) + 16LL);
  v6 = v11;
  if ( v11 )
  {
    v11->Length = 0;
    v11->MaximumLength = v10;
    v11->Buffer = &v11[1].Length;
    RtlAppendUnicodeToString(v11, Source);
    RtlAppendUnicodeToString(v6, L"\\");
    RtlAppendUnicodeToString(v6, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = v6;
    goto LABEL_3;
  }
  v7 = -1073741801;
LABEL_10:
  if ( v6 )
    MSCryptFree(v6);
  return v7;
}

```

## disassembly

```asm
0x1800126f0  mov     rax, rsp
0x1800126f3  push    rbx
0x1800126f4  push    rsi
0x1800126f5  push    rdi
0x1800126f6  push    r12
0x1800126f8  push    r14
0x1800126fa  push    r15
0x1800126fc  sub     rsp, 78h
0x180012700  mov     r15, r8
0x180012703  mov     rdi, rdx
0x180012706  mov     rsi, rcx
0x180012709  xorps   xmm0, xmm0
0x18001270c  movups  xmmword ptr [rax-80h], xmm0
0x180012710  xor     r12d, r12d
0x180012713  mov     ebx, r12d
0x180012716  movups  xmmword ptr [rax-70h], xmm0
0x18001271a  movups  xmmword ptr [rax-60h], xmm0
0x18001271e  movups  xmmword ptr [rax-50h], xmm0
0x180012722  test    rdx, rdx
0x180012725  jnz     short loc_180012776
0x180012727  mov     rdx, rcx; SourceString
0x18001272a  lea     rcx, [rax-80h]; DestinationString
0x18001272e  call    cs:__imp_RtlInitUnicodeString
0x180012734  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18001273c  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x180012741  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x180012749  lea     rax, [rsp+0A8h+var_80]
0x18001274e  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180012753  xorps   xmm0, xmm0
0x180012756  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001275c  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180012761  mov     edx, 20019h; DesiredAccess
0x180012766  mov     rcx, r15; KeyHandle
0x180012769  call    cs:__imp_NtOpenKey
0x18001276f  mov     edi, eax
0x180012771  jmp     loc_180012813
0x180012776  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001277a  mov     rcx, rax
0x18001277d  inc     rcx
0x180012780  cmp     [rdx+rcx*2], r12w
0x180012785  jnz     short loc_18001277D
0x180012787  inc     rax
0x18001278a  cmp     [rsi+rax*2], r12w
0x18001278f  jnz     short loc_180012787
0x180012791  add     eax, ecx
0x180012793  lea     r14d, ds:4[rax*2]
0x18001279b  mov     ecx, r14d
0x18001279e  add     rcx, 10h
0x1800127a2  call    SafeAllocaAllocateFromHeap
0x1800127a7  mov     rbx, rax
0x1800127aa  mov     [rsp+0A8h+var_88], rax
0x1800127af  test    rax, rax
0x1800127b2  jnz     short loc_1800127BB
0x1800127b4  mov     edi, 0C0000017h
0x1800127b9  jmp     short loc_180012813
0x1800127bb  mov     [rax], r12w
0x1800127bf  mov     [rax+2], r14w
0x1800127c4  add     rax, 10h
0x1800127c8  mov     [rbx+8], rax
0x1800127cc  mov     rdx, rsi; Source
0x1800127cf  mov     rcx, rbx; Destination
0x1800127d2  call    cs:__imp_RtlAppendUnicodeToString
0x1800127d8  lea     rdx, Source; "\\"
0x1800127df  mov     rcx, rbx; Destination
0x1800127e2  call    cs:__imp_RtlAppendUnicodeToString
0x1800127e8  mov     rdx, rdi; Source
0x1800127eb  mov     rcx, rbx; Destination
0x1800127ee  call    cs:__imp_RtlAppendUnicodeToString
0x1800127f4  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1800127fc  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x180012801  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x180012809  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rbx
0x18001280e  jmp     loc_180012753
0x180012813  test    rbx, rbx
0x180012816  jnz     short loc_180012828
0x180012818  mov     eax, edi
0x18001281a  add     rsp, 78h
0x18001281e  pop     r15
0x180012820  pop     r14
0x180012822  pop     r12
0x180012824  pop     rdi
0x180012825  pop     rsi
0x180012826  pop     rbx
0x180012827  retn
0x180012828  mov     rcx, rbx
0x18001282b  call    MSCryptFree
0x180012830  jmp     short loc_180012818
0x180025b96  push    rbp
0x180025b98  sub     rsp, 20h
0x180025b9c  mov     rbp, rdx
0x180025b9f  add     rsp, 20h
0x180025ba3  pop     rbp
0x180025ba4  retn
```
