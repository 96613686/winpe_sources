# KeRegCreateKey

- ea: `0x1800735b0`
- end: `0x18007369c`
- name: `KeRegCreateKey`
- size: `236`
- prototype: `ULONG __fastcall(void *, const WCHAR *, __int64, void **)`
- caller_count: `8`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180046f18`
- `0x180047100`
- `0x180070194`
- `0x18007037c`
- `0x180072b38`
- `0x180072d68`
- `0x180073058`
- `0x1800731fc`

## callees

- `0x18001bd90`
- `0x180036ce0`
- `0x1800735b0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180073605`
- `ntoskrnl!RtlInitUnicodeString` at `0x180073605`
- `ntoskrnl!ZwCreateKey` at `0x18007365c`
- `ntoskrnl!ZwCreateKey` at `0x18007365c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18007367a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18007367a`

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
0x1800735b0  mov     [rsp-8+arg_0], rbx
0x1800735b5  mov     [rsp-8+arg_8], rdi
0x1800735ba  push    rbp
0x1800735bb  mov     rbp, rsp
0x1800735be  sub     rsp, 80h
0x1800735c5  xorps   xmm1, xmm1
0x1800735c8  xorps   xmm0, xmm0
0x1800735cb  mov     rbx, rcx
0x1800735ce  cmp     rcx, 0FFFFFFFF80000002h
0x1800735d5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800735d9  mov     rdi, r9
0x1800735dc  lea     rcx, [rbp+DestinationString]; Destination
0x1800735e0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1800735e4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1800735e8  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1800735ec  jnz     short loc_180073605
0x1800735ee  call    _NewLocalMachineKeyNameString
0x1800735f3  test    eax, eax
0x1800735f5  jnz     short loc_180073601
0x1800735f7  mov     eax, 8
0x1800735fc  jmp     loc_180073686
0x180073601  xor     ebx, ebx
0x180073603  jmp     short loc_180073611
0x180073605  call    cs:__imp_RtlInitUnicodeString
0x18007360c  nop     dword ptr [rax+rax+00h]
0x180073611  lea     rax, [rbp+DestinationString]
0x180073615  mov     [rsp+80h+Disposition], 0; Disposition
0x18007361e  xorps   xmm0, xmm0
0x180073621  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x180073629  xor     r9d, r9d; TitleIndex
0x18007362c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180073630  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180073634  mov     [rsp+80h+Class], 0; Class
0x18007363d  mov     edx, 3001Fh; DesiredAccess
0x180073642  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180073649  mov     rcx, rdi; KeyHandle
0x18007364c  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x180073650  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180073655  mov     [rbp+ObjectAttributes.Attributes], 640h
0x18007365c  call    cs:__imp_ZwCreateKey
0x180073663  nop     dword ptr [rax+rax+00h]
0x180073668  mov     edi, eax
0x18007366a  test    rbx, rbx
0x18007366d  jnz     short loc_180073678
0x18007366f  mov     rcx, [rbp+DestinationString.Buffer]; P
0x180073673  call    BCryptFree
0x180073678  mov     ecx, edi; Status
0x18007367a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180073681  nop     dword ptr [rax+rax+00h]
0x180073686  lea     r11, [rsp+80h+var_s0]
0x18007368e  mov     rbx, [r11+10h]
0x180073692  mov     rdi, [r11+18h]
0x180073696  mov     rsp, r11
0x180073699  pop     rbp
0x18007369a  retn
```
