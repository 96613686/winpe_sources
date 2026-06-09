# pSetupOpenKey

- ea: `0x18007ddd8`
- end: `0x18007deb3`
- name: `pSetupOpenKey`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007debc`

## callees

- `0x18007dd74`
- `0x18007ddd8`
- `0x18007ded8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18007de82`
- `ntdll!RtlNtStatusToDosError` at `0x18007de82`
- `ntdll!NtOpenKey` at `0x18007de76`
- `ntdll!NtOpenKey` at `0x18007de76`
- `ntdll!RtlInitUnicodeString` at `0x18007de3c`
- `ntdll!RtlInitUnicodeString` at `0x18007de3c`

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
0x18007ddd8  push    rbp
0x18007ddda  push    rbx
0x18007dddb  push    rsi
0x18007dddc  push    rdi
0x18007dddd  push    r14
0x18007dddf  push    r15
0x18007dde1  mov     rbp, rsp
0x18007dde4  sub     rsp, 78h
0x18007dde8  xor     eax, eax
0x18007ddea  xorps   xmm0, xmm0
0x18007dded  mov     [rbp+KeyHandle], rax
0x18007ddf1  xor     ebx, ebx
0x18007ddf3  mov     eax, 80000000h
0x18007ddf8  mov     [rbp+arg_0], rbx
0x18007ddfc  add     rax, rcx
0x18007ddff  mov     r14d, r9d
0x18007de02  mov     r15, rdx
0x18007de05  mov     rsi, rcx
0x18007de08  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18007de0c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007de10  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18007de14  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18007de18  cmp     rax, 7
0x18007de1c  jbe     short loc_18007DE22
0x18007de1e  xor     edi, edi
0x18007de20  jmp     short loc_18007DE35
0x18007de22  lea     rdx, [rbp+arg_0]
0x18007de26  call    pSetupOpenPredefinedKey
0x18007de2b  mov     rbx, [rbp+arg_0]
0x18007de2f  mov     edi, eax
0x18007de31  test    eax, eax
0x18007de33  jnz     short loc_18007DE97
0x18007de35  mov     rdx, r15; SourceString
0x18007de38  lea     rcx, [rbp+DestinationString]; DestinationString
0x18007de3c  call    cs:__imp_RtlInitUnicodeString
0x18007de42  lea     rax, [rbp+DestinationString]
0x18007de46  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007de4d  xorps   xmm0, xmm0
0x18007de50  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18007de57  test    rbx, rbx
0x18007de5a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18007de5e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007de62  mov     edx, r14d; DesiredAccess
0x18007de65  cmovnz  rsi, rbx
0x18007de69  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18007de6d  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18007de71  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007de76  call    cs:__imp_NtOpenKey
0x18007de7c  test    eax, eax
0x18007de7e  jns     short loc_18007DE8C
0x18007de80  mov     ecx, eax; Status
0x18007de82  call    cs:__imp_RtlNtStatusToDosError
0x18007de88  mov     edi, eax
0x18007de8a  jmp     short loc_18007DE97
0x18007de8c  mov     rax, [rbp+arg_20]
0x18007de90  movsxd  rcx, dword ptr [rbp+KeyHandle]
0x18007de94  mov     [rax], rcx
0x18007de97  test    rbx, rbx
0x18007de9a  jz      short loc_18007DEA4
0x18007de9c  mov     rcx, rbx
0x18007de9f  call    pSetupCloseKey
0x18007dea4  mov     eax, edi
0x18007dea6  add     rsp, 78h
0x18007deaa  pop     r15
0x18007deac  pop     r14
0x18007deae  pop     rdi
0x18007deaf  pop     rsi
0x18007deb0  pop     rbx
0x18007deb1  pop     rbp
0x18007deb2  retn
```
