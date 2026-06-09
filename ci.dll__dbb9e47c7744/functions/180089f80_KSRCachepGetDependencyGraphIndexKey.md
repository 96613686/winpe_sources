# KSRCachepGetDependencyGraphIndexKey

- ea: `0x180089f80`
- end: `0x18008a106`
- name: `KSRCachepGetDependencyGraphIndexKey`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089b88`

## callees

- `0x18000ed14`
- `0x18002bf20`
- `0x180089f80`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18008a0c7`
- `ntoskrnl!ZwClose` at `0x18008a0dd`
- `ntoskrnl!ZwClose` at `0x18008a0c7`
- `ntoskrnl!ZwClose` at `0x18008a0dd`
- `ntoskrnl!ZwOpenKey` at `0x18008a007`
- `ntoskrnl!ZwOpenKey` at `0x18008a092`
- `ntoskrnl!ZwOpenKey` at `0x18008a007`
- `ntoskrnl!ZwOpenKey` at `0x18008a092`

## string_xrefs

- `0x180089fb3`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\DependencyGraph\Index\UserAndDependentPackageAndDependencyType`

## pseudocode

```c
__int64 __fastcall KSRCachepGetDependencyGraphIndexKey(_WORD *a1, _WORD *a2, HANDLE *a3)
{
  NTSTATUS v6; // ebx
  __int16 v7; // cx
  HANDLE v8; // rcx
  HANDLE Handle; // [rsp+30h] [rbp-89h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v12[2]; // [rsp+40h] [rbp-79h] BYREF
  __int128 v13; // [rsp+50h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-59h] BYREF
  wchar_t pszDest[40]; // [rsp+90h] [rbp-29h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v12[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\Dependen"
            "cyGraph\\Index\\UserAndDependentPackageAndDependencyType";
  v12[0] = 20185394;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
  Handle = 0;
  ObjectAttributes.RootDirectory = 0;
  v13 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v6 < 0 )
    goto LABEL_5;
  v6 = RtlStringCbPrintfW(pszDest, 0x48u, L"%wZ^%wZ^8", a2, a1);
  if ( v6 < 0 )
    goto LABEL_5;
  v7 = *a1 + 6 + *a2;
  ObjectAttributes.Length = 48;
  LOWORD(v13) = v7;
  *((_QWORD *)&v13 + 1) = pszDest;
  ObjectAttributes.RootDirectory = KeyHandle;
  WORD1(v13) = v7;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v13;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
  if ( v6 < 0 )
  {
LABEL_5:
    v8 = Handle;
  }
  else
  {
    v8 = 0;
    *a3 = Handle;
    Handle = 0;
  }
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    v8 = Handle;
  }
  if ( v8 )
    ZwClose(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180089f80  push    rbp
0x180089f82  push    rbx
0x180089f83  push    rsi
0x180089f84  push    rdi
0x180089f85  push    r14
0x180089f87  lea     rbp, [rsp-37h]
0x180089f8c  sub     rsp, 0F0h
0x180089f93  mov     rax, cs:__security_cookie
0x180089f9a  xor     rax, rsp
0x180089f9d  mov     [rbp+57h+var_30], rax
0x180089fa1  xor     eax, eax
0x180089fa3  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180089fab  mov     [rsp+110h+KeyHandle], rax
0x180089fb0  xorps   xmm0, xmm0
0x180089fb3  lea     rax, aRegistryMachin_1; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180089fba  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180089fc2  mov     [rbp+57h+var_C8], rax
0x180089fc6  mov     r14, r8
0x180089fc9  lea     rax, [rbp+57h+var_D0]
0x180089fcd  mov     [rbp+57h+var_D0], 1340132h
0x180089fd5  mov     rsi, rdx
0x180089fd8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180089fdc  mov     rdi, rcx
0x180089fdf  mov     [rsp+110h+Handle], 0
0x180089fe8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180089fec  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180089ff4  mov     edx, 20019h; DesiredAccess
0x180089ff9  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x180089ffe  movups  [rbp+57h+var_C0], xmm0
0x18008a002  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a007  call    cs:__imp_ZwOpenKey
0x18008a00e  nop     dword ptr [rax+rax+00h]
0x18008a013  mov     ebx, eax
0x18008a015  test    eax, eax
0x18008a017  js      loc_18008A0B5
0x18008a01d  mov     r9, rsi
0x18008a020  mov     [rsp+110h+var_F0], rdi
0x18008a025  lea     r8, aWzWz8; "%wZ^%wZ^8"
0x18008a02c  mov     edx, 48h ; 'H'; cbDest
0x18008a031  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18008a035  call    RtlStringCbPrintfW
0x18008a03a  mov     ebx, eax
0x18008a03c  test    eax, eax
0x18008a03e  js      short loc_18008A0B5
0x18008a040  movzx   eax, word ptr [rdi]
0x18008a043  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008a047  movzx   ecx, word ptr [rsi]
0x18008a04a  add     ax, 6
0x18008a04e  add     cx, ax
0x18008a051  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008a058  lea     rax, [rbp+57h+pszDest]
0x18008a05c  mov     word ptr [rbp+57h+var_C0], cx
0x18008a060  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18008a064  xorps   xmm0, xmm0
0x18008a067  mov     rax, [rsp+110h+KeyHandle]
0x18008a06c  mov     edx, 20019h; DesiredAccess
0x18008a071  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008a075  lea     rax, [rbp+57h+var_C0]
0x18008a079  mov     word ptr [rbp+57h+var_C0+2], cx
0x18008a07d  lea     rcx, [rsp+110h+Handle]; KeyHandle
0x18008a082  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008a086  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a08d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a092  call    cs:__imp_ZwOpenKey
0x18008a099  nop     dword ptr [rax+rax+00h]
0x18008a09e  mov     ebx, eax
0x18008a0a0  test    eax, eax
0x18008a0a2  js      short loc_18008A0B5
0x18008a0a4  mov     rax, [rsp+110h+Handle]
0x18008a0a9  xor     ecx, ecx
0x18008a0ab  mov     [r14], rax
0x18008a0ae  mov     [rsp+110h+Handle], rcx
0x18008a0b3  jmp     short loc_18008A0BA
0x18008a0b5  mov     rcx, [rsp+110h+Handle]
0x18008a0ba  mov     rax, [rsp+110h+KeyHandle]
0x18008a0bf  test    rax, rax
0x18008a0c2  jz      short loc_18008A0D8
0x18008a0c4  mov     rcx, rax; Handle
0x18008a0c7  call    cs:__imp_ZwClose
0x18008a0ce  nop     dword ptr [rax+rax+00h]
0x18008a0d3  mov     rcx, [rsp+110h+Handle]; Handle
0x18008a0d8  test    rcx, rcx
0x18008a0db  jz      short loc_18008A0E9
0x18008a0dd  call    cs:__imp_ZwClose
0x18008a0e4  nop     dword ptr [rax+rax+00h]
0x18008a0e9  mov     eax, ebx
0x18008a0eb  mov     rcx, [rbp+57h+var_30]
0x18008a0ef  xor     rcx, rsp; StackCookie
0x18008a0f2  call    __security_check_cookie
0x18008a0f7  add     rsp, 0F0h
0x18008a0fe  pop     r14
0x18008a100  pop     rdi
0x18008a101  pop     rsi
0x18008a102  pop     rbx
0x18008a103  pop     rbp
0x18008a104  retn
```
