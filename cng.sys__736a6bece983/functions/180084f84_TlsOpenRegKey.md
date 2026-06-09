# TlsOpenRegKey

- ea: `0x180084f84`
- end: `0x1800850e1`
- name: `TlsOpenRegKey`
- size: `349`
- prototype: `__int64 __fastcall(PCWSTR Source, PCWSTR, PHANDLE KeyHandle)`
- caller_count: `7`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180046720`
- `0x180082418`
- `0x180083314`
- `0x180085164`
- `0x180085568`
- `0x1800859f8`
- `0x180085e34`

## callees

- `0x180003f70`
- `0x180006470`
- `0x180084f84`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180084fc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x180084fc2`
- `ntoskrnl!ZwOpenKey` at `0x1800850b5`
- `ntoskrnl!ZwOpenKey` at `0x1800850b5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180085051`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180085067`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180085079`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180085051`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180085067`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180085079`

## pseudocode

```c
__int64 __fastcall TlsOpenRegKey(PCWSTR Source, PCWSTR a2, PHANDLE KeyHandle, __int64 a4)
{
  struct _UNICODE_STRING *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  USHORT v10; // r14
  struct _UNICODE_STRING *v11; // rax
  unsigned int v12; // edi
  struct _UNICODE_STRING v14; // [rsp+28h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-70h] BYREF

  v14 = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a2 )
  {
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    do
      ++v8;
    while ( Source[v8] );
    v10 = 2 * (v9 + v8) + 4;
    v11 = (struct _UNICODE_STRING *)MSCryptAlloc((unsigned int)(2 * (v9 + v8) + 4) + 16LL, a2, KeyHandle, a4);
    v7 = v11;
    if ( !v11 )
    {
      v12 = -1073741801;
      goto LABEL_10;
    }
    v11->Length = 0;
    v11->MaximumLength = v10;
    v11->Buffer = &v11[1].Length;
    RtlAppendUnicodeToString(v11, Source);
    RtlAppendUnicodeToString(v7, L"\\");
    RtlAppendUnicodeToString(v7, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = v7;
  }
  else
  {
    RtlInitUnicodeString(&v14, Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &v14;
  }
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
LABEL_10:
  if ( v7 )
    MSCryptFree(v7);
  return v12;
}

```

## disassembly

```asm
0x180084f84  mov     rax, rsp
0x180084f87  push    rbx
0x180084f88  push    rsi
0x180084f89  push    rdi
0x180084f8a  push    r12
0x180084f8c  push    r14
0x180084f8e  push    r15
0x180084f90  sub     rsp, 78h
0x180084f94  mov     r15, r8
0x180084f97  mov     rdi, rdx
0x180084f9a  mov     rsi, rcx
0x180084f9d  xorps   xmm0, xmm0
0x180084fa0  movups  xmmword ptr [rax-80h], xmm0
0x180084fa4  xor     r12d, r12d
0x180084fa7  mov     ebx, r12d
0x180084faa  movups  xmmword ptr [rax-70h], xmm0
0x180084fae  movups  xmmword ptr [rax-60h], xmm0
0x180084fb2  movups  xmmword ptr [rax-50h], xmm0
0x180084fb6  test    rdx, rdx
0x180084fb9  jnz     short loc_180084FF2
0x180084fbb  mov     rdx, rcx; SourceString
0x180084fbe  lea     rcx, [rax-80h]; DestinationString
0x180084fc2  call    cs:__imp_RtlInitUnicodeString
0x180084fc9  nop     dword ptr [rax+rax+00h]
0x180084fce  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180084fd6  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x180084fdb  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x180084fe3  lea     rax, [rsp+0A8h+var_80]
0x180084fe8  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180084fed  jmp     loc_18008509F
0x180084ff2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180084ff6  mov     rcx, rax
0x180084ff9  inc     rcx
0x180084ffc  cmp     [rdx+rcx*2], r12w
0x180085001  jnz     short loc_180084FF9
0x180085003  inc     rax
0x180085006  cmp     [rsi+rax*2], r12w
0x18008500b  jnz     short loc_180085003
0x18008500d  add     eax, ecx
0x18008500f  lea     r14d, ds:4[rax*2]
0x180085017  mov     ecx, r14d
0x18008501a  add     rcx, 10h
0x18008501e  call    MSCryptAlloc
0x180085023  mov     rbx, rax
0x180085026  mov     [rsp+0A8h+var_88], rax
0x18008502b  test    rax, rax
0x18008502e  jnz     short loc_18008503A
0x180085030  mov     edi, 0C0000017h
0x180085035  jmp     loc_1800850C3
0x18008503a  mov     [rax], r12w
0x18008503e  mov     [rax+2], r14w
0x180085043  add     rax, 10h
0x180085047  mov     [rbx+8], rax
0x18008504b  mov     rdx, rsi; Source
0x18008504e  mov     rcx, rbx; Destination
0x180085051  call    cs:__imp_RtlAppendUnicodeToString
0x180085058  nop     dword ptr [rax+rax+00h]
0x18008505d  lea     rdx, asc_1800B0C40; "\\"
0x180085064  mov     rcx, rbx; Destination
0x180085067  call    cs:__imp_RtlAppendUnicodeToString
0x18008506e  nop     dword ptr [rax+rax+00h]
0x180085073  mov     rdx, rdi; Source
0x180085076  mov     rcx, rbx; Destination
0x180085079  call    cs:__imp_RtlAppendUnicodeToString
0x180085080  nop     dword ptr [rax+rax+00h]
0x180085085  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x18008508d  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x180085092  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x18008509a  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rbx
0x18008509f  xorps   xmm0, xmm0
0x1800850a2  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800850a8  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800850ad  mov     edx, 20019h; DesiredAccess
0x1800850b2  mov     rcx, r15; KeyHandle
0x1800850b5  call    cs:__imp_ZwOpenKey
0x1800850bc  nop     dword ptr [rax+rax+00h]
0x1800850c1  mov     edi, eax
0x1800850c3  test    rbx, rbx
0x1800850c6  jz      short loc_1800850D0
0x1800850c8  mov     rcx, rbx; P
0x1800850cb  call    MSCryptFree
0x1800850d0  mov     eax, edi
0x1800850d2  add     rsp, 78h
0x1800850d6  pop     r15
0x1800850d8  pop     r14
0x1800850da  pop     r12
0x1800850dc  pop     rdi
0x1800850dd  pop     rsi
0x1800850de  pop     rbx
0x1800850df  retn
0x1800a00ca  push    rbp
0x1800a00cc  sub     rsp, 20h
0x1800a00d0  mov     rbp, rdx
0x1800a00d3  add     rsp, 20h
0x1800a00d7  pop     rbp
0x1800a00d8  retn
```
