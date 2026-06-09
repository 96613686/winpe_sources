# KSRCachepGetDependencyGraphIndexKey

- ea: `0x180088950`
- end: `0x180088ad6`
- name: `KSRCachepGetDependencyGraphIndexKey`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180088558`

## callees

- `0x18000ed14`
- `0x18002bef0`
- `0x180088950`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180088a97`
- `ntoskrnl!ZwClose` at `0x180088aad`
- `ntoskrnl!ZwClose` at `0x180088a97`
- `ntoskrnl!ZwClose` at `0x180088aad`
- `ntoskrnl!ZwOpenKey` at `0x1800889d7`
- `ntoskrnl!ZwOpenKey` at `0x180088a62`
- `ntoskrnl!ZwOpenKey` at `0x1800889d7`
- `ntoskrnl!ZwOpenKey` at `0x180088a62`

## string_xrefs

- `0x180088983`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\DependencyGraph\Index\UserAndDependentPackageAndDependencyType`

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
0x180088950  push    rbp
0x180088952  push    rbx
0x180088953  push    rsi
0x180088954  push    rdi
0x180088955  push    r14
0x180088957  lea     rbp, [rsp-37h]
0x18008895c  sub     rsp, 0F0h
0x180088963  mov     rax, cs:__security_cookie
0x18008896a  xor     rax, rsp
0x18008896d  mov     [rbp+57h+var_30], rax
0x180088971  xor     eax, eax
0x180088973  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008897b  mov     [rsp+110h+KeyHandle], rax
0x180088980  xorps   xmm0, xmm0
0x180088983  lea     rax, aRegistryMachin_1; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008898a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180088992  mov     [rbp+57h+var_C8], rax
0x180088996  mov     r14, r8
0x180088999  lea     rax, [rbp+57h+var_D0]
0x18008899d  mov     [rbp+57h+var_D0], 1340132h
0x1800889a5  mov     rsi, rdx
0x1800889a8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800889ac  mov     rdi, rcx
0x1800889af  mov     [rsp+110h+Handle], 0
0x1800889b8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800889bc  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800889c4  mov     edx, 20019h; DesiredAccess
0x1800889c9  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x1800889ce  movups  [rbp+57h+var_C0], xmm0
0x1800889d2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800889d7  call    cs:__imp_ZwOpenKey
0x1800889de  nop     dword ptr [rax+rax+00h]
0x1800889e3  mov     ebx, eax
0x1800889e5  test    eax, eax
0x1800889e7  js      loc_180088A85
0x1800889ed  mov     r9, rsi
0x1800889f0  mov     [rsp+110h+var_F0], rdi
0x1800889f5  lea     r8, aWzWz8; "%wZ^%wZ^8"
0x1800889fc  mov     edx, 48h ; 'H'; cbDest
0x180088a01  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180088a05  call    RtlStringCbPrintfW
0x180088a0a  mov     ebx, eax
0x180088a0c  test    eax, eax
0x180088a0e  js      short loc_180088A85
0x180088a10  movzx   eax, word ptr [rdi]
0x180088a13  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180088a17  movzx   ecx, word ptr [rsi]
0x180088a1a  add     ax, 6
0x180088a1e  add     cx, ax
0x180088a21  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180088a28  lea     rax, [rbp+57h+pszDest]
0x180088a2c  mov     word ptr [rbp+57h+var_C0], cx
0x180088a30  mov     qword ptr [rbp+57h+var_C0+8], rax
0x180088a34  xorps   xmm0, xmm0
0x180088a37  mov     rax, [rsp+110h+KeyHandle]
0x180088a3c  mov     edx, 20019h; DesiredAccess
0x180088a41  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180088a45  lea     rax, [rbp+57h+var_C0]
0x180088a49  mov     word ptr [rbp+57h+var_C0+2], cx
0x180088a4d  lea     rcx, [rsp+110h+Handle]; KeyHandle
0x180088a52  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180088a56  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180088a5d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088a62  call    cs:__imp_ZwOpenKey
0x180088a69  nop     dword ptr [rax+rax+00h]
0x180088a6e  mov     ebx, eax
0x180088a70  test    eax, eax
0x180088a72  js      short loc_180088A85
0x180088a74  mov     rax, [rsp+110h+Handle]
0x180088a79  xor     ecx, ecx
0x180088a7b  mov     [r14], rax
0x180088a7e  mov     [rsp+110h+Handle], rcx
0x180088a83  jmp     short loc_180088A8A
0x180088a85  mov     rcx, [rsp+110h+Handle]
0x180088a8a  mov     rax, [rsp+110h+KeyHandle]
0x180088a8f  test    rax, rax
0x180088a92  jz      short loc_180088AA8
0x180088a94  mov     rcx, rax; Handle
0x180088a97  call    cs:__imp_ZwClose
0x180088a9e  nop     dword ptr [rax+rax+00h]
0x180088aa3  mov     rcx, [rsp+110h+Handle]; Handle
0x180088aa8  test    rcx, rcx
0x180088aab  jz      short loc_180088AB9
0x180088aad  call    cs:__imp_ZwClose
0x180088ab4  nop     dword ptr [rax+rax+00h]
0x180088ab9  mov     eax, ebx
0x180088abb  mov     rcx, [rbp+57h+var_30]
0x180088abf  xor     rcx, rsp; StackCookie
0x180088ac2  call    __security_check_cookie
0x180088ac7  add     rsp, 0F0h
0x180088ace  pop     r14
0x180088ad0  pop     rdi
0x180088ad1  pop     rsi
0x180088ad2  pop     rbx
0x180088ad3  pop     rbp
0x180088ad4  retn
```
