# KGetUnlockSetting

- ea: `0x1400528fc`
- end: `0x140052a1b`
- name: `KGetUnlockSetting`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140052a74`

## callees

- `0x140025c20`
- `0x1400528fc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400529dd`
- `ntoskrnl!ZwClose` at `0x1400529dd`
- `ntoskrnl!ZwOpenKey` at `0x140052964`
- `ntoskrnl!ZwOpenKey` at `0x140052964`
- `ntoskrnl!ZwQueryValueKey` at `0x140052998`
- `ntoskrnl!ZwQueryValueKey` at `0x140052998`

## pseudocode

```c
__int64 __fastcall KGetUnlockSetting(UNICODE_STRING *a1, UNICODE_STRING *a2, unsigned int *a3)
{
  NTSTATUS v5; // ebx
  bool v6; // cl
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-9h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+70h] [rbp+27h] BYREF
  int v12; // [rsp+74h] [rbp+2Bh]
  unsigned int v13; // [rsp+78h] [rbp+2Fh]
  unsigned int v14; // [rsp+7Ch] [rbp+33h]

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x20119u, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    v5 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, KeyValueInformation, 0x18u, &ResultLength);
    if ( v5 >= 0 )
    {
      v6 = 1;
      if ( v14 > 1 )
        v6 = v14 == 0xFFFF;
      if ( v12 == 4 && v13 >= 4 && v6 )
        *a3 = v14;
      else
        *a3 = 0xFFFF;
    }
    ZwClose(KeyHandle);
  }
  if ( v5 == -1073741772 )
  {
    *a3 = 0xFFFF;
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400528fc  mov     [rsp-8+arg_18], rbx
0x140052901  push    rbp
0x140052902  push    rsi
0x140052903  push    rdi
0x140052904  lea     rbp, [rsp-47h]
0x140052909  sub     rsp, 90h
0x140052910  mov     rax, cs:__security_cookie
0x140052917  xor     rax, rsp
0x14005291a  mov     [rbp+57h+var_18], rax
0x14005291e  mov     rdi, r8
0x140052921  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x140052925  mov     rsi, rdx
0x140052928  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140052930  xorps   xmm0, xmm0
0x140052933  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14005293b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005293f  mov     [rbp+57h+KeyHandle], 0
0x140052947  mov     edx, 20119h; DesiredAccess
0x14005294c  mov     [rbp+57h+var_70], 0
0x140052953  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140052957  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14005295f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140052964  call    cs:__imp_ZwOpenKey
0x14005296b  nop     dword ptr [rax+rax+00h]
0x140052970  mov     ebx, eax
0x140052972  test    eax, eax
0x140052974  js      short loc_1400529E9
0x140052976  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005297a  lea     rax, [rbp+57h+var_70]
0x14005297e  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140052983  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140052987  mov     r8d, 2; KeyValueInformationClass
0x14005298d  mov     [rsp+0A0h+Length], 18h; Length
0x140052995  mov     rdx, rsi; ValueName
0x140052998  call    cs:__imp_ZwQueryValueKey
0x14005299f  nop     dword ptr [rax+rax+00h]
0x1400529a4  mov     ebx, eax
0x1400529a6  test    eax, eax
0x1400529a8  js      short loc_1400529D9
0x1400529aa  mov     eax, [rbp+57h+var_24]
0x1400529ad  mov     ecx, 1
0x1400529b2  cmp     eax, ecx
0x1400529b4  jbe     short loc_1400529BF
0x1400529b6  cmp     eax, 0FFFFh
0x1400529bb  jz      short loc_1400529BF
0x1400529bd  xor     cl, cl
0x1400529bf  cmp     [rbp+57h+var_2C], 4
0x1400529c3  jnz     short loc_1400529D3
0x1400529c5  cmp     [rbp+57h+var_28], 4
0x1400529c9  jb      short loc_1400529D3
0x1400529cb  test    cl, cl
0x1400529cd  jz      short loc_1400529D3
0x1400529cf  mov     [rdi], eax
0x1400529d1  jmp     short loc_1400529D9
0x1400529d3  mov     dword ptr [rdi], 0FFFFh
0x1400529d9  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400529dd  call    cs:__imp_ZwClose
0x1400529e4  nop     dword ptr [rax+rax+00h]
0x1400529e9  cmp     ebx, 0C0000034h
0x1400529ef  jnz     short loc_1400529F9
0x1400529f1  mov     dword ptr [rdi], 0FFFFh
0x1400529f7  xor     ebx, ebx
0x1400529f9  mov     eax, ebx
0x1400529fb  mov     rcx, [rbp+57h+var_18]
0x1400529ff  xor     rcx, rsp; StackCookie
0x140052a02  call    __security_check_cookie
0x140052a07  mov     rbx, [rsp+0A0h+arg_18]
0x140052a0f  add     rsp, 90h
0x140052a16  pop     rdi
0x140052a17  pop     rsi
0x140052a18  pop     rbp
0x140052a19  retn
```
