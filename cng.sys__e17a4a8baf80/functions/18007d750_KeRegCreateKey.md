# KeRegCreateKey

- ea: `0x18007d750`
- end: `0x18007d83c`
- name: `KeRegCreateKey`
- size: `236`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180051008`
- `0x1800511f0`
- `0x18007a334`
- `0x18007a51c`
- `0x18007ccd8`
- `0x18007cf08`
- `0x18007d1f8`
- `0x18007d39c`

## callees

- `0x180025ec0`
- `0x180040d50`
- `0x18007d750`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18007d7a5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007d7a5`
- `ntoskrnl!ZwCreateKey` at `0x18007d7fc`
- `ntoskrnl!ZwCreateKey` at `0x18007d7fc`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18007d81a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18007d81a`

## pseudocode

```c
ULONG __fastcall KeRegCreateKey(void *a1, const WCHAR *a2, __int64 a3, void **a4)
{
  void *v4; // rbx
  NTSTATUS v7; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  v4 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a1 == (void *)-2147483646LL )
  {
    if ( !(unsigned int)NewLocalMachineKeyNameString(&DestinationString, a2) )
      return 8;
    v4 = 0;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, a2);
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v4;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 1600;
  v7 = ZwCreateKey(a4, 0x3001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( !v4 )
    BCryptFree(DestinationString.Buffer);
  return RtlNtStatusToDosErrorNoTeb(v7);
}

```

## disassembly

```asm
0x18007d750  mov     [rsp-8+arg_0], rbx
0x18007d755  mov     [rsp-8+arg_8], rdi
0x18007d75a  push    rbp
0x18007d75b  mov     rbp, rsp
0x18007d75e  sub     rsp, 80h
0x18007d765  xorps   xmm1, xmm1
0x18007d768  xorps   xmm0, xmm0
0x18007d76b  mov     rbx, rcx
0x18007d76e  cmp     rcx, 0FFFFFFFF80000002h
0x18007d775  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007d779  mov     rdi, r9
0x18007d77c  lea     rcx, [rbp+DestinationString]; Destination
0x18007d780  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x18007d784  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x18007d788  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x18007d78c  jnz     short loc_18007D7A5
0x18007d78e  call    _NewLocalMachineKeyNameString
0x18007d793  test    eax, eax
0x18007d795  jnz     short loc_18007D7A1
0x18007d797  mov     eax, 8
0x18007d79c  jmp     loc_18007D826
0x18007d7a1  xor     ebx, ebx
0x18007d7a3  jmp     short loc_18007D7B1
0x18007d7a5  call    cs:__imp_RtlInitUnicodeString
0x18007d7ac  nop     dword ptr [rax+rax+00h]
0x18007d7b1  lea     rax, [rbp+DestinationString]
0x18007d7b5  mov     [rsp+80h+Disposition], 0; Disposition
0x18007d7be  xorps   xmm0, xmm0
0x18007d7c1  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x18007d7c9  xor     r9d, r9d; TitleIndex
0x18007d7cc  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18007d7d0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007d7d4  mov     [rsp+80h+Class], 0; Class
0x18007d7dd  mov     edx, 3001Fh; DesiredAccess
0x18007d7e2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007d7e9  mov     rcx, rdi; KeyHandle
0x18007d7ec  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18007d7f0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007d7f5  mov     [rbp+ObjectAttributes.Attributes], 640h
0x18007d7fc  call    cs:__imp_ZwCreateKey
0x18007d803  nop     dword ptr [rax+rax+00h]
0x18007d808  mov     edi, eax
0x18007d80a  test    rbx, rbx
0x18007d80d  jnz     short loc_18007D818
0x18007d80f  mov     rcx, [rbp+DestinationString.Buffer]; P
0x18007d813  call    BCryptFree
0x18007d818  mov     ecx, edi; Status
0x18007d81a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18007d821  nop     dword ptr [rax+rax+00h]
0x18007d826  lea     r11, [rsp+80h+var_s0]
0x18007d82e  mov     rbx, [r11+10h]
0x18007d832  mov     rdi, [r11+18h]
0x18007d836  mov     rsp, r11
0x18007d839  pop     rbp
0x18007d83a  retn
```
