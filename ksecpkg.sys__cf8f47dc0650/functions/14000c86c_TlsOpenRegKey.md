# TlsOpenRegKey

- ea: `0x14000c86c`
- end: `0x14000c9e7`
- name: `TlsOpenRegKey`
- size: `379`
- prototype: `__int64 __fastcall(PCWSTR Source, PCWSTR, PHANDLE KeyHandle)`
- caller_count: `5`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000bff0`
- `0x14000ca84`
- `0x14000ce40`
- `0x14000d200`
- `0x14000d5d8`

## callees

- `0x14000c86c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c94b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c961`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c973`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c94b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c961`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000c973`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c9ca`
- `ntoskrnl!ExAllocatePool2` at `0x14000c911`
- `ntoskrnl!ExAllocatePool2` at `0x14000c911`
- `ntoskrnl!ZwOpenKey` at `0x14000c9af`
- `ntoskrnl!ZwOpenKey` at `0x14000c9af`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c8aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c8aa`

## pseudocode

```c
__int64 __fastcall TlsOpenRegKey(PCWSTR Source, PCWSTR a2, PHANDLE KeyHandle)
{
  struct _UNICODE_STRING *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  USHORT v9; // r14
  struct _UNICODE_STRING *Pool2; // rax
  unsigned int v11; // edi
  struct _UNICODE_STRING v13; // [rsp+28h] [rbp-80h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-70h] BYREF

  v13 = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a2 )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    do
      ++v7;
    while ( Source[v7] );
    v9 = 2 * (v8 + v7) + 4;
    Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(64, (unsigned int)(2 * (v8 + v7) + 4) + 16LL, 1131180883);
    v6 = Pool2;
    if ( !Pool2 )
    {
      v11 = -1073741801;
      goto LABEL_10;
    }
    Pool2->Length = 0;
    Pool2->MaximumLength = v9;
    Pool2->Buffer = &Pool2[1].Length;
    RtlAppendUnicodeToString(Pool2, Source);
    RtlAppendUnicodeToString(v6, L"\\");
    RtlAppendUnicodeToString(v6, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = v6;
  }
  else
  {
    RtlInitUnicodeString(&v13, Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &v13;
  }
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
LABEL_10:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x436C7353u);
  return v11;
}

```

## disassembly

```asm
0x14000c86c  mov     rax, rsp
0x14000c86f  push    rbx
0x14000c870  push    rsi
0x14000c871  push    rdi
0x14000c872  push    r12
0x14000c874  push    r14
0x14000c876  push    r15
0x14000c878  sub     rsp, 78h
0x14000c87c  mov     r15, r8
0x14000c87f  mov     rdi, rdx
0x14000c882  mov     rsi, rcx
0x14000c885  xorps   xmm0, xmm0
0x14000c888  movups  xmmword ptr [rax-80h], xmm0
0x14000c88c  xor     r12d, r12d
0x14000c88f  mov     ebx, r12d
0x14000c892  movups  xmmword ptr [rax-70h], xmm0
0x14000c896  movups  xmmword ptr [rax-60h], xmm0
0x14000c89a  movups  xmmword ptr [rax-50h], xmm0
0x14000c89e  test    rdx, rdx
0x14000c8a1  jnz     short loc_14000C8DA
0x14000c8a3  mov     rdx, rcx; SourceString
0x14000c8a6  lea     rcx, [rax-80h]; DestinationString
0x14000c8aa  call    cs:__imp_RtlInitUnicodeString
0x14000c8b1  nop     dword ptr [rax+rax+00h]
0x14000c8b6  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x14000c8be  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x14000c8c3  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x14000c8cb  lea     rax, [rsp+0A8h+var_80]
0x14000c8d0  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x14000c8d5  jmp     loc_14000C999
0x14000c8da  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c8de  mov     rcx, rax
0x14000c8e1  inc     rcx
0x14000c8e4  cmp     [rdx+rcx*2], r12w
0x14000c8e9  jnz     short loc_14000C8E1
0x14000c8eb  inc     rax
0x14000c8ee  cmp     [rsi+rax*2], r12w
0x14000c8f3  jnz     short loc_14000C8EB
0x14000c8f5  add     eax, ecx
0x14000c8f7  lea     r14d, ds:4[rax*2]
0x14000c8ff  mov     edx, r14d
0x14000c902  add     rdx, 10h
0x14000c906  mov     ecx, 40h ; '@'
0x14000c90b  mov     r8d, 436C7353h
0x14000c911  call    cs:__imp_ExAllocatePool2
0x14000c918  nop     dword ptr [rax+rax+00h]
0x14000c91d  mov     rbx, rax
0x14000c920  mov     [rsp+0A8h+var_88], rax
0x14000c925  test    rax, rax
0x14000c928  jnz     short loc_14000C934
0x14000c92a  mov     edi, 0C0000017h
0x14000c92f  jmp     loc_14000C9BD
0x14000c934  mov     [rax], r12w
0x14000c938  mov     [rax+2], r14w
0x14000c93d  add     rax, 10h
0x14000c941  mov     [rbx+8], rax
0x14000c945  mov     rdx, rsi; Source
0x14000c948  mov     rcx, rbx; Destination
0x14000c94b  call    cs:__imp_RtlAppendUnicodeToString
0x14000c952  nop     dword ptr [rax+rax+00h]
0x14000c957  lea     rdx, Source; "\\"
0x14000c95e  mov     rcx, rbx; Destination
0x14000c961  call    cs:__imp_RtlAppendUnicodeToString
0x14000c968  nop     dword ptr [rax+rax+00h]
0x14000c96d  mov     rdx, rdi; Source
0x14000c970  mov     rcx, rbx; Destination
0x14000c973  call    cs:__imp_RtlAppendUnicodeToString
0x14000c97a  nop     dword ptr [rax+rax+00h]
0x14000c97f  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x14000c987  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x14000c98c  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x14000c994  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rbx
0x14000c999  xorps   xmm0, xmm0
0x14000c99c  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000c9a2  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x14000c9a7  mov     edx, 20019h; DesiredAccess
0x14000c9ac  mov     rcx, r15; KeyHandle
0x14000c9af  call    cs:__imp_ZwOpenKey
0x14000c9b6  nop     dword ptr [rax+rax+00h]
0x14000c9bb  mov     edi, eax
0x14000c9bd  test    rbx, rbx
0x14000c9c0  jz      short loc_14000C9D6
0x14000c9c2  mov     edx, 436C7353h; Tag
0x14000c9c7  mov     rcx, rbx; P
0x14000c9ca  call    cs:__imp_ExFreePoolWithTag
0x14000c9d1  nop     dword ptr [rax+rax+00h]
0x14000c9d6  mov     eax, edi
0x14000c9d8  add     rsp, 78h
0x14000c9dc  pop     r15
0x14000c9de  pop     r14
0x14000c9e0  pop     r12
0x14000c9e2  pop     rdi
0x14000c9e3  pop     rsi
0x14000c9e4  pop     rbx
0x14000c9e5  retn
0x140010bad  push    rbp
0x140010baf  sub     rsp, 20h
0x140010bb3  mov     rbp, rdx
0x140010bb6  add     rsp, 20h
0x140010bba  pop     rbp
0x140010bbb  retn
```
