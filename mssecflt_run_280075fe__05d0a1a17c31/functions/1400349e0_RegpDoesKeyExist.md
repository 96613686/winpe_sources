# RegpDoesKeyExist

- ea: `0x1400349e0`
- end: `0x140034adb`
- name: `RegpDoesKeyExist`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400397e4`

## callees

- `0x140011650`
- `0x1400349e0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140034a7b`
- `ntoskrnl!ZwOpenKey` at `0x140034a7b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140034a3c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140034a3c`
- `ntoskrnl!ZwClose` at `0x140034a92`
- `ntoskrnl!ZwClose` at `0x140034aaf`
- `ntoskrnl!ZwClose` at `0x140034a92`
- `ntoskrnl!ZwClose` at `0x140034aaf`

## pseudocode

```c
char __fastcall RegpDoesKeyExist(void *a1, struct _UNICODE_STRING *a2)
{
  HANDLE v2; // rax
  NTSTATUS v4; // ebx
  HANDLE Handle; // [rsp+48h] [rbp+7h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp+Fh] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+17h] BYREF

  v2 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  KeyHandle = 0;
  Handle = 0;
  if ( a1 )
  {
    if ( ObOpenObjectByPointer(a1, 0x200u, 0, 0x20019u, 0, 0, &Handle) < 0 )
      return 0;
    v2 = Handle;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v2;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x82000000, &ObjectAttributes);
  if ( Handle )
    ZwClose(Handle);
  if ( v4 < 0 )
    return 0;
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return 1;
}

```

## disassembly

```asm
0x1400349e0  mov     r11, rsp
0x1400349e3  mov     [r11+18h], rbx
0x1400349e7  push    rbp
0x1400349e8  lea     rbp, [r11-5Fh]
0x1400349ec  sub     rsp, 90h
0x1400349f3  mov     rax, cs:__security_cookie
0x1400349fa  xor     rax, rsp
0x1400349fd  mov     [rbp+57h+var_10], rax
0x140034a01  xor     eax, eax
0x140034a03  mov     rbx, rdx
0x140034a06  mov     dword ptr [rbp+57h+ObjectAttributes+4], eax
0x140034a09  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], eax
0x140034a0c  mov     [rbp+57h+KeyHandle], rax
0x140034a10  mov     [rbp+57h+Handle], rax
0x140034a14  test    rcx, rcx
0x140034a17  jz      short loc_140034A50
0x140034a19  lea     rax, [rbp+57h+Handle]
0x140034a1d  mov     r9d, 20019h; DesiredAccess
0x140034a23  mov     [r11-68h], rax
0x140034a27  xor     r8d, r8d; PassedAccessState
0x140034a2a  mov     byte ptr [rsp+28h], 0; AccessMode
0x140034a2f  mov     edx, 200h; HandleAttributes
0x140034a34  mov     qword ptr [r11-78h], 0
0x140034a3c  call    cs:__imp_ObOpenObjectByPointer
0x140034a43  nop     dword ptr [rax+rax+00h]
0x140034a48  test    eax, eax
0x140034a4a  js      short loc_140034AA2
0x140034a4c  mov     rax, [rbp+57h+Handle]
0x140034a50  xorps   xmm0, xmm0
0x140034a53  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140034a5a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140034a5e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140034a62  mov     edx, 82000000h; DesiredAccess
0x140034a67  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140034a6e  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140034a72  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x140034a76  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140034a7b  call    cs:__imp_ZwOpenKey
0x140034a82  nop     dword ptr [rax+rax+00h]
0x140034a87  mov     rcx, [rbp+57h+Handle]; Handle
0x140034a8b  mov     ebx, eax
0x140034a8d  test    rcx, rcx
0x140034a90  jz      short loc_140034A9E
0x140034a92  call    cs:__imp_ZwClose
0x140034a99  nop     dword ptr [rax+rax+00h]
0x140034a9e  test    ebx, ebx
0x140034aa0  jns     short loc_140034AA6
0x140034aa2  xor     al, al
0x140034aa4  jmp     short loc_140034ABD
0x140034aa6  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140034aaa  test    rcx, rcx
0x140034aad  jz      short loc_140034ABB
0x140034aaf  call    cs:__imp_ZwClose
0x140034ab6  nop     dword ptr [rax+rax+00h]
0x140034abb  mov     al, 1
0x140034abd  mov     rcx, [rbp+57h+var_10]
0x140034ac1  xor     rcx, rsp; StackCookie
0x140034ac4  call    __security_check_cookie
0x140034ac9  mov     rbx, [rsp+90h+arg_10]
0x140034ad1  add     rsp, 90h
0x140034ad8  pop     rbp
0x140034ad9  retn
```
