# UxOpenSubKeyByIndex

- ea: `0x1c00d9db8`
- end: `0x1c00d9f53`
- name: `UxOpenSubKeyByIndex`
- size: `411`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, ULONG Index@<edx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1c00d9ac0`

## callees

- `0x1c00d9db8`
- `0x1c00da914`
- `0x1c00da948`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1c00fe42e`
- `ntoskrnl!ZwOpenKey` at `0x1c00fe42e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00d9e1c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c00d9e1c`
- `ntoskrnl!ZwCreateKey` at `0x1c00d9e69`
- `ntoskrnl!ZwCreateKey` at `0x1c00d9e69`
- `ntoskrnl!ZwEnumerateKey` at `0x1c00d9ecf`
- `ntoskrnl!ZwEnumerateKey` at `0x1c00d9ecf`
- `ntoskrnl!ZwClose` at `0x1c00d9f05`
- `ntoskrnl!ZwClose` at `0x1c00fe48f`
- `ntoskrnl!ZwClose` at `0x1c00d9f05`
- `ntoskrnl!ZwClose` at `0x1c00fe48f`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d9e9b`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d9e9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d9f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fe3bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00d9f28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fe3bb`

## pseudocode

```c
__int64 __fastcall UxOpenSubKeyByIndex(PCWSTR SourceString, ULONG Index, __int64 a3, _QWORD *a4, HANDLE *a5)
{
  HANDLE *v5; // r15
  _DWORD *v8; // rdi
  NTSTATUS WideString; // ebx
  _DWORD *PoolWithTagPriority; // rax
  NTSTATUS v11; // eax
  unsigned int v13; // eax
  void *KeyHandle; // [rsp+48h] [rbp-31h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-29h] BYREF
  __int128 v16; // [rsp+58h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  SIZE_T NumberOfBytes; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v20; // [rsp+F0h] [rbp+77h] BYREF

  v5 = a5;
  KeyHandle = 0;
  Handle = 0;
  v20 = 0;
  *a5 = 0;
  LODWORD(NumberOfBytes) = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v8 = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  DestinationString = 0;
  *a4 = 0;
  v16 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  WideString = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( WideString >= 0 )
  {
    LODWORD(NumberOfBytes) = 152;
    do
    {
      if ( v8 )
        ExFreePoolWithTag(v8, 0);
      PoolWithTagPriority = ExAllocatePoolWithTagPriority(
                              PagedPool,
                              (unsigned int)NumberOfBytes,
                              0x44526C55u,
                              LowPoolPriority);
      v8 = PoolWithTagPriority;
      if ( !PoolWithTagPriority )
      {
        WideString = -1073741670;
        goto LABEL_9;
      }
      v11 = ZwEnumerateKey(
              KeyHandle,
              Index,
              KeyBasicInformation,
              PoolWithTagPriority,
              NumberOfBytes,
              (PULONG)&NumberOfBytes);
      WideString = v11;
    }
    while ( v11 == -2147483643 || v11 == -1073741789 );
    if ( v11 >= 0 )
    {
      v13 = v8[3];
      if ( (v13 & 1) != 0 || v13 > 0xFFFE )
      {
        WideString = -1073741492;
      }
      else
      {
        *((_QWORD *)&v16 + 1) = v8 + 4;
        LOWORD(v16) = *((_WORD *)v8 + 6);
        WORD1(v16) = *((_WORD *)v8 + 6);
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v16;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        WideString = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( WideString >= 0 )
        {
          WideString = UlAllocateWideString(v8 + 4);
          if ( WideString >= 0 )
          {
            *v5 = Handle;
            *a4 = v20;
            Handle = 0;
            v20 = 0;
          }
        }
      }
    }
  }
LABEL_9:
  UlFreeWideString(&v20);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return (unsigned int)WideString;
}

```

## disassembly

```asm
0x1c00d9db8  mov     rax, rsp
0x1c00d9dbb  mov     [rax+8], rbx
0x1c00d9dbf  mov     [rax+10h], rsi
0x1c00d9dc3  mov     [rax+18h], r8b
0x1c00d9dc7  push    rbp
0x1c00d9dc8  push    rdi
0x1c00d9dc9  push    r12
0x1c00d9dcb  push    r14
0x1c00d9dcd  push    r15
0x1c00d9dcf  lea     rbp, [rax-57h]
0x1c00d9dd3  sub     rsp, 0A0h
0x1c00d9dda  mov     r15, [rbp+4Fh+arg_20]
0x1c00d9dde  xor     r12d, r12d
0x1c00d9de1  mov     esi, edx
0x1c00d9de3  mov     [rbp+4Fh+KeyHandle], r12
0x1c00d9de7  xorps   xmm0, xmm0
0x1c00d9dea  mov     [rbp+4Fh+Handle], r12
0x1c00d9dee  xorps   xmm1, xmm1
0x1c00d9df1  mov     [rbp+4Fh+arg_18], r12
0x1c00d9df5  mov     rdx, rcx; SourceString
0x1c00d9df8  mov     [r15], r12
0x1c00d9dfb  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1c00d9dff  mov     dword ptr [rbp+4Fh+NumberOfBytes], r12d
0x1c00d9e03  mov     r14, r9
0x1c00d9e06  mov     dword ptr [rbp+4Fh+ObjectAttributes+4], r12d
0x1c00d9e0a  mov     edi, r12d
0x1c00d9e0d  mov     dword ptr [rbp+4Fh+ObjectAttributes+1Ch], r12d
0x1c00d9e11  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1c00d9e15  mov     [r9], r12
0x1c00d9e18  movups  [rbp+4Fh+var_70], xmm1
0x1c00d9e1c  call    cs:__imp_RtlInitUnicodeString
0x1c00d9e23  nop     dword ptr [rax+rax+00h]
0x1c00d9e28  lea     rax, [rbp+4Fh+DestinationString]
0x1c00d9e2c  mov     [rsp+0C0h+Disposition], r12; Disposition
0x1c00d9e31  xorps   xmm0, xmm0
0x1c00d9e34  mov     [rsp+0C0h+CreateOptions], r12d; CreateOptions
0x1c00d9e39  xor     r9d, r9d; TitleIndex
0x1c00d9e3c  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1c00d9e40  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1c00d9e44  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1c00d9e4b  mov     edx, 2001Fh; DesiredAccess
0x1c00d9e50  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x1c00d9e54  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1c00d9e58  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1c00d9e5f  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00d9e64  mov     [rsp+0C0h+Class], r12; Class
0x1c00d9e69  call    cs:__imp_ZwCreateKey
0x1c00d9e70  nop     dword ptr [rax+rax+00h]
0x1c00d9e75  mov     ebx, eax
0x1c00d9e77  test    eax, eax
0x1c00d9e79  js      short loc_1C00D9EF3
0x1c00d9e7b  mov     dword ptr [rbp+4Fh+NumberOfBytes], 98h
0x1c00d9e82  test    rdi, rdi
0x1c00d9e85  jnz     loc_1C00FE3B6
0x1c00d9e8b  mov     edx, dword ptr [rbp+4Fh+NumberOfBytes]; NumberOfBytes
0x1c00d9e8e  xor     r9d, r9d; Priority
0x1c00d9e91  mov     r8d, 44526C55h; Tag
0x1c00d9e97  lea     ecx, [r9+1]; PoolType
0x1c00d9e9b  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00d9ea2  nop     dword ptr [rax+rax+00h]
0x1c00d9ea7  mov     rdi, rax
0x1c00d9eaa  test    rax, rax
0x1c00d9ead  jz      loc_1C00FE485
0x1c00d9eb3  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1c00d9eb7  lea     rax, [rbp+4Fh+NumberOfBytes]
0x1c00d9ebb  mov     qword ptr [rsp+0C0h+CreateOptions], rax; ResultLength
0x1c00d9ec0  mov     r9, rdi; KeyInformation
0x1c00d9ec3  mov     eax, dword ptr [rbp+4Fh+NumberOfBytes]
0x1c00d9ec6  xor     r8d, r8d; KeyInformationClass
0x1c00d9ec9  mov     edx, esi; Index
0x1c00d9ecb  mov     dword ptr [rsp+0C0h+Class], eax; Length
0x1c00d9ecf  call    cs:__imp_ZwEnumerateKey
0x1c00d9ed6  nop     dword ptr [rax+rax+00h]
0x1c00d9edb  mov     ebx, eax
0x1c00d9edd  cmp     eax, 80000005h
0x1c00d9ee2  jz      short loc_1C00D9E82
0x1c00d9ee4  cmp     eax, 0C0000023h
0x1c00d9ee9  jz      short loc_1C00D9E82
0x1c00d9eeb  test    eax, eax
0x1c00d9eed  jns     loc_1C00FE3CD
0x1c00d9ef3  lea     rcx, [rbp+4Fh+arg_18]
0x1c00d9ef7  call    UlFreeWideString
0x1c00d9efc  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x1c00d9f00  test    rcx, rcx
0x1c00d9f03  jz      short loc_1C00D9F11
0x1c00d9f05  call    cs:__imp_ZwClose
0x1c00d9f0c  nop     dword ptr [rax+rax+00h]
0x1c00d9f11  mov     rcx, [rbp+4Fh+Handle]; Handle
0x1c00d9f15  test    rcx, rcx
0x1c00d9f18  jnz     loc_1C00FE48F
0x1c00d9f1e  test    rdi, rdi
0x1c00d9f21  jz      short loc_1C00D9F34
0x1c00d9f23  xor     edx, edx; Tag
0x1c00d9f25  mov     rcx, rdi; P
0x1c00d9f28  call    cs:__imp_ExFreePoolWithTag
0x1c00d9f2f  nop     dword ptr [rax+rax+00h]
0x1c00d9f34  lea     r11, [rsp+0C0h+var_20]
0x1c00d9f3c  mov     eax, ebx
0x1c00d9f3e  mov     rbx, [r11+30h]
0x1c00d9f42  mov     rsi, [r11+38h]
0x1c00d9f46  mov     rsp, r11
0x1c00d9f49  pop     r15
0x1c00d9f4b  pop     r14
0x1c00d9f4d  pop     r12
0x1c00d9f4f  pop     rdi
0x1c00d9f50  pop     rbp
0x1c00d9f51  retn
0x1c00fe3b6  xor     edx, edx; Tag
0x1c00fe3b8  mov     rcx, rdi; P
0x1c00fe3bb  call    cs:__imp_ExFreePoolWithTag
0x1c00fe3c2  nop     dword ptr [rax+rax+00h]
0x1c00fe3c7  nop
0x1c00fe3c8  jmp     loc_1C00D9E8B
0x1c00fe3cd  mov     eax, [rdi+0Ch]
0x1c00fe3d0  test    al, 1
0x1c00fe3d2  jnz     loc_1C00FE47B
0x1c00fe3d8  cmp     eax, 0FFFEh
0x1c00fe3dd  ja      loc_1C00FE47B
0x1c00fe3e3  xorps   xmm0, xmm0
0x1c00fe3e6  lea     rsi, [rdi+10h]
0x1c00fe3ea  mov     qword ptr [rbp+4Fh+var_70+8], rsi
0x1c00fe3ee  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1c00fe3f2  movzx   eax, word ptr [rdi+0Ch]
0x1c00fe3f6  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x1c00fe3fa  mov     word ptr [rbp+4Fh+var_70], ax
0x1c00fe3fe  mov     edx, 20019h; DesiredAccess
0x1c00fe403  movzx   eax, word ptr [rdi+0Ch]
0x1c00fe407  mov     word ptr [rbp+4Fh+var_70+2], ax
0x1c00fe40b  mov     rax, [rbp+4Fh+KeyHandle]
0x1c00fe40f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x1c00fe413  lea     rax, [rbp+4Fh+var_70]
0x1c00fe417  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1c00fe41b  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1c00fe422  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1c00fe429  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1c00fe42e  call    cs:__imp_ZwOpenKey
0x1c00fe435  nop     dword ptr [rax+rax+00h]
0x1c00fe43a  mov     ebx, eax
0x1c00fe43c  test    eax, eax
0x1c00fe43e  js      loc_1C00D9EF3
0x1c00fe444  mov     edx, [rdi+0Ch]
0x1c00fe447  lea     r8, [rbp+4Fh+arg_18]
0x1c00fe44b  shr     rdx, 1
0x1c00fe44e  mov     rcx, rsi; Src
0x1c00fe451  call    UlAllocateWideString
0x1c00fe456  mov     ebx, eax
0x1c00fe458  test    eax, eax
0x1c00fe45a  js      loc_1C00D9EF3
0x1c00fe460  mov     rax, [rbp+4Fh+Handle]
0x1c00fe464  mov     [r15], rax
0x1c00fe467  mov     rax, [rbp+4Fh+arg_18]
0x1c00fe46b  mov     [r14], rax
0x1c00fe46e  mov     [rbp+4Fh+Handle], r12
0x1c00fe472  mov     [rbp+4Fh+arg_18], r12
0x1c00fe476  jmp     loc_1C00D9EF3
0x1c00fe47b  mov     ebx, 0C000014Ch
0x1c00fe480  jmp     loc_1C00D9EF3
0x1c00fe485  mov     ebx, 0C000009Ah
0x1c00fe48a  jmp     loc_1C00D9EF3
0x1c00fe48f  call    cs:__imp_ZwClose
0x1c00fe496  nop     dword ptr [rax+rax+00h]
0x1c00fe49b  nop
0x1c00fe49c  jmp     loc_1C00D9F1E
```
