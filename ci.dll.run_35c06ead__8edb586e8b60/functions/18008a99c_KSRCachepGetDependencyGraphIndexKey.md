# KSRCachepGetDependencyGraphIndexKey

- ea: `0x18008a99c`
- end: `0x18008ab22`
- name: `KSRCachepGetDependencyGraphIndexKey`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008a5a4`

## callees

- `0x18000ed24`
- `0x18002c0d0`
- `0x18008a99c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18008aae3`
- `ntoskrnl!ZwClose` at `0x18008aaf9`
- `ntoskrnl!ZwClose` at `0x18008aae3`
- `ntoskrnl!ZwClose` at `0x18008aaf9`
- `ntoskrnl!ZwOpenKey` at `0x18008aa23`
- `ntoskrnl!ZwOpenKey` at `0x18008aaae`
- `ntoskrnl!ZwOpenKey` at `0x18008aa23`
- `ntoskrnl!ZwOpenKey` at `0x18008aaae`

## string_xrefs

- `0x18008a9cf`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\DependencyGraph\Index\UserAndDependentPackageAndDependencyType`

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
0x18008a99c  push    rbp
0x18008a99e  push    rbx
0x18008a99f  push    rsi
0x18008a9a0  push    rdi
0x18008a9a1  push    r14
0x18008a9a3  lea     rbp, [rsp-37h]
0x18008a9a8  sub     rsp, 0F0h
0x18008a9af  mov     rax, cs:__security_cookie
0x18008a9b6  xor     rax, rsp
0x18008a9b9  mov     [rbp+57h+var_30], rax
0x18008a9bd  xor     eax, eax
0x18008a9bf  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008a9c7  mov     [rsp+110h+KeyHandle], rax
0x18008a9cc  xorps   xmm0, xmm0
0x18008a9cf  lea     rax, aRegistryMachin_1; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008a9d6  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a9de  mov     [rbp+57h+var_C8], rax
0x18008a9e2  mov     r14, r8
0x18008a9e5  lea     rax, [rbp+57h+var_D0]
0x18008a9e9  mov     [rbp+57h+var_D0], 1340132h
0x18008a9f1  mov     rsi, rdx
0x18008a9f4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008a9f8  mov     rdi, rcx
0x18008a9fb  mov     [rsp+110h+Handle], 0
0x18008aa04  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008aa08  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008aa10  mov     edx, 20019h; DesiredAccess
0x18008aa15  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x18008aa1a  movups  [rbp+57h+var_C0], xmm0
0x18008aa1e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008aa23  call    cs:__imp_ZwOpenKey
0x18008aa2a  nop     dword ptr [rax+rax+00h]
0x18008aa2f  mov     ebx, eax
0x18008aa31  test    eax, eax
0x18008aa33  js      loc_18008AAD1
0x18008aa39  mov     r9, rsi
0x18008aa3c  mov     [rsp+110h+var_F0], rdi
0x18008aa41  lea     r8, aWzWz8; "%wZ^%wZ^8"
0x18008aa48  mov     edx, 48h ; 'H'; cbDest
0x18008aa4d  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18008aa51  call    RtlStringCbPrintfW
0x18008aa56  mov     ebx, eax
0x18008aa58  test    eax, eax
0x18008aa5a  js      short loc_18008AAD1
0x18008aa5c  movzx   eax, word ptr [rdi]
0x18008aa5f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008aa63  movzx   ecx, word ptr [rsi]
0x18008aa66  add     ax, 6
0x18008aa6a  add     cx, ax
0x18008aa6d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008aa74  lea     rax, [rbp+57h+pszDest]
0x18008aa78  mov     word ptr [rbp+57h+var_C0], cx
0x18008aa7c  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18008aa80  xorps   xmm0, xmm0
0x18008aa83  mov     rax, [rsp+110h+KeyHandle]
0x18008aa88  mov     edx, 20019h; DesiredAccess
0x18008aa8d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008aa91  lea     rax, [rbp+57h+var_C0]
0x18008aa95  mov     word ptr [rbp+57h+var_C0+2], cx
0x18008aa99  lea     rcx, [rsp+110h+Handle]; KeyHandle
0x18008aa9e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008aaa2  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008aaa9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008aaae  call    cs:__imp_ZwOpenKey
0x18008aab5  nop     dword ptr [rax+rax+00h]
0x18008aaba  mov     ebx, eax
0x18008aabc  test    eax, eax
0x18008aabe  js      short loc_18008AAD1
0x18008aac0  mov     rax, [rsp+110h+Handle]
0x18008aac5  xor     ecx, ecx
0x18008aac7  mov     [r14], rax
0x18008aaca  mov     [rsp+110h+Handle], rcx
0x18008aacf  jmp     short loc_18008AAD6
0x18008aad1  mov     rcx, [rsp+110h+Handle]
0x18008aad6  mov     rax, [rsp+110h+KeyHandle]
0x18008aadb  test    rax, rax
0x18008aade  jz      short loc_18008AAF4
0x18008aae0  mov     rcx, rax; Handle
0x18008aae3  call    cs:__imp_ZwClose
0x18008aaea  nop     dword ptr [rax+rax+00h]
0x18008aaef  mov     rcx, [rsp+110h+Handle]; Handle
0x18008aaf4  test    rcx, rcx
0x18008aaf7  jz      short loc_18008AB05
0x18008aaf9  call    cs:__imp_ZwClose
0x18008ab00  nop     dword ptr [rax+rax+00h]
0x18008ab05  mov     eax, ebx
0x18008ab07  mov     rcx, [rbp+57h+var_30]
0x18008ab0b  xor     rcx, rsp; StackCookie
0x18008ab0e  call    __security_check_cookie
0x18008ab13  add     rsp, 0F0h
0x18008ab1a  pop     r14
0x18008ab1c  pop     rdi
0x18008ab1d  pop     rsi
0x18008ab1e  pop     rbx
0x18008ab1f  pop     rbp
0x18008ab20  retn
```
