# pSetupOpenKey

- ea: `0x180020e58`
- end: `0x180020f33`
- name: `pSetupOpenKey`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020f3c`

## callees

- `0x180020df4`
- `0x180020e58`
- `0x180020f58`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180020ebc`
- `ntdll!RtlInitUnicodeString` at `0x180020ebc`
- `ntdll!NtOpenKey` at `0x180020ef6`
- `ntdll!NtOpenKey` at `0x180020ef6`
- `ntdll!RtlNtStatusToDosError` at `0x180020f02`
- `ntdll!RtlNtStatusToDosError` at `0x180020f02`

## pseudocode

```c
__int64 __fastcall pSetupOpenKey(void *a1, const WCHAR *a2, __int64 a3, ACCESS_MASK a4, _QWORD *a5)
{
  void *v5; // rbx
  void *v8; // rsi
  ULONG v9; // edi
  ULONG v10; // eax
  int v11; // eax
  void *KeyHandle; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  void *v16; // [rsp+B0h] [rbp+38h] BYREF

  KeyHandle = 0;
  v5 = 0;
  v16 = 0;
  v8 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)a1 + 0x80000000 <= 7 )
  {
    v10 = pSetupOpenPredefinedKey(a1, &v16);
    v5 = v16;
    v9 = v10;
    if ( v10 )
      goto LABEL_9;
  }
  else
  {
    v9 = 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  if ( v5 )
    v8 = v5;
  ObjectAttributes.RootDirectory = v8;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenKey(&KeyHandle, a4, &ObjectAttributes);
  if ( v11 >= 0 )
    *a5 = (int)KeyHandle;
  else
    v9 = RtlNtStatusToDosError(v11);
LABEL_9:
  if ( v5 )
    pSetupCloseKey(v5);
  return v9;
}

```

## disassembly

```asm
0x180020e58  push    rbp
0x180020e5a  push    rbx
0x180020e5b  push    rsi
0x180020e5c  push    rdi
0x180020e5d  push    r14
0x180020e5f  push    r15
0x180020e61  mov     rbp, rsp
0x180020e64  sub     rsp, 78h
0x180020e68  xor     eax, eax
0x180020e6a  xorps   xmm0, xmm0
0x180020e6d  mov     [rbp+KeyHandle], rax
0x180020e71  xor     ebx, ebx
0x180020e73  mov     eax, 80000000h
0x180020e78  mov     [rbp+arg_0], rbx
0x180020e7c  add     rax, rcx
0x180020e7f  mov     r14d, r9d
0x180020e82  mov     r15, rdx
0x180020e85  mov     rsi, rcx
0x180020e88  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180020e8c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180020e90  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180020e94  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180020e98  cmp     rax, 7
0x180020e9c  jbe     short loc_180020EA2
0x180020e9e  xor     edi, edi
0x180020ea0  jmp     short loc_180020EB5
0x180020ea2  lea     rdx, [rbp+arg_0]
0x180020ea6  call    pSetupOpenPredefinedKey
0x180020eab  mov     rbx, [rbp+arg_0]
0x180020eaf  mov     edi, eax
0x180020eb1  test    eax, eax
0x180020eb3  jnz     short loc_180020F17
0x180020eb5  mov     rdx, r15; SourceString
0x180020eb8  lea     rcx, [rbp+DestinationString]; DestinationString
0x180020ebc  call    cs:__imp_RtlInitUnicodeString
0x180020ec2  lea     rax, [rbp+DestinationString]
0x180020ec6  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180020ecd  xorps   xmm0, xmm0
0x180020ed0  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180020ed7  test    rbx, rbx
0x180020eda  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180020ede  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180020ee2  mov     edx, r14d; DesiredAccess
0x180020ee5  cmovnz  rsi, rbx
0x180020ee9  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180020eed  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180020ef1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180020ef6  call    cs:__imp_NtOpenKey
0x180020efc  test    eax, eax
0x180020efe  jns     short loc_180020F0C
0x180020f00  mov     ecx, eax; Status
0x180020f02  call    cs:__imp_RtlNtStatusToDosError
0x180020f08  mov     edi, eax
0x180020f0a  jmp     short loc_180020F17
0x180020f0c  mov     rax, [rbp+arg_20]
0x180020f10  movsxd  rcx, dword ptr [rbp+KeyHandle]
0x180020f14  mov     [rax], rcx
0x180020f17  test    rbx, rbx
0x180020f1a  jz      short loc_180020F24
0x180020f1c  mov     rcx, rbx
0x180020f1f  call    pSetupCloseKey
0x180020f24  mov     eax, edi
0x180020f26  add     rsp, 78h
0x180020f2a  pop     r15
0x180020f2c  pop     r14
0x180020f2e  pop     rdi
0x180020f2f  pop     rsi
0x180020f30  pop     rbx
0x180020f31  pop     rbp
0x180020f32  retn
```
