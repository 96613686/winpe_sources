# KeRegCreateKey

- ea: `0x180073fb0`
- end: `0x18007409c`
- name: `KeRegCreateKey`
- size: `236`
- prototype: `ULONG __fastcall(void *, const WCHAR *, __int64, void **)`
- caller_count: `8`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800479a8`
- `0x180047b90`
- `0x180070b94`
- `0x180070d7c`
- `0x180073538`
- `0x180073768`
- `0x180073a58`
- `0x180073bfc`

## callees

- `0x180018e40`
- `0x1800377e0`
- `0x180073fb0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180074005`
- `ntoskrnl!RtlInitUnicodeString` at `0x180074005`
- `ntoskrnl!ZwCreateKey` at `0x18007405c`
- `ntoskrnl!ZwCreateKey` at `0x18007405c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18007407a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18007407a`

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
0x180073fb0  mov     [rsp-8+arg_0], rbx
0x180073fb5  mov     [rsp-8+arg_8], rdi
0x180073fba  push    rbp
0x180073fbb  mov     rbp, rsp
0x180073fbe  sub     rsp, 80h
0x180073fc5  xorps   xmm1, xmm1
0x180073fc8  xorps   xmm0, xmm0
0x180073fcb  mov     rbx, rcx
0x180073fce  cmp     rcx, 0FFFFFFFF80000002h
0x180073fd5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180073fd9  mov     rdi, r9
0x180073fdc  lea     rcx, [rbp+DestinationString]; Destination
0x180073fe0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x180073fe4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x180073fe8  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180073fec  jnz     short loc_180074005
0x180073fee  call    _NewLocalMachineKeyNameString
0x180073ff3  test    eax, eax
0x180073ff5  jnz     short loc_180074001
0x180073ff7  mov     eax, 8
0x180073ffc  jmp     loc_180074086
0x180074001  xor     ebx, ebx
0x180074003  jmp     short loc_180074011
0x180074005  call    cs:__imp_RtlInitUnicodeString
0x18007400c  nop     dword ptr [rax+rax+00h]
0x180074011  lea     rax, [rbp+DestinationString]
0x180074015  mov     [rsp+80h+Disposition], 0; Disposition
0x18007401e  xorps   xmm0, xmm0
0x180074021  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x180074029  xor     r9d, r9d; TitleIndex
0x18007402c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180074030  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180074034  mov     [rsp+80h+Class], 0; Class
0x18007403d  mov     edx, 3001Fh; DesiredAccess
0x180074042  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180074049  mov     rcx, rdi; KeyHandle
0x18007404c  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x180074050  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180074055  mov     [rbp+ObjectAttributes.Attributes], 640h
0x18007405c  call    cs:__imp_ZwCreateKey
0x180074063  nop     dword ptr [rax+rax+00h]
0x180074068  mov     edi, eax
0x18007406a  test    rbx, rbx
0x18007406d  jnz     short loc_180074078
0x18007406f  mov     rcx, [rbp+DestinationString.Buffer]; P
0x180074073  call    BCryptFree
0x180074078  mov     ecx, edi; Status
0x18007407a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180074081  nop     dword ptr [rax+rax+00h]
0x180074086  lea     r11, [rsp+80h+var_s0]
0x18007408e  mov     rbx, [r11+10h]
0x180074092  mov     rdi, [r11+18h]
0x180074096  mov     rsp, r11
0x180074099  pop     rbp
0x18007409a  retn
```
