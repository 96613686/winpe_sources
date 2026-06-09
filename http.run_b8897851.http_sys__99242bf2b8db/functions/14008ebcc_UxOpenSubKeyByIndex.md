# UxOpenSubKeyByIndex

- ea: `0x14008ebcc`
- end: `0x14008ee73`
- name: `UxOpenSubKeyByIndex`
- size: `679`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, ULONG Index@<edx>, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14008e460`
- `0x14008e9a0`
- `0x140135ac0`

## callees

- `0x14008ebcc`
- `0x1400906cc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14008ed85`
- `ntoskrnl!ZwOpenKey` at `0x14008ed85`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ec3c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ec3c`
- `ntoskrnl!ZwCreateKey` at `0x14008ec88`
- `ntoskrnl!ZwCreateKey` at `0x14008ec88`
- `ntoskrnl!ZwEnumerateKey` at `0x14008ed00`
- `ntoskrnl!ZwEnumerateKey` at `0x14008ed00`
- `ntoskrnl!ZwClose` at `0x14008edd6`
- `ntoskrnl!ZwClose` at `0x14008ee62`
- `ntoskrnl!ZwClose` at `0x14008edd6`
- `ntoskrnl!ZwClose` at `0x14008ee62`
- `ntoskrnl!ExAllocatePool3` at `0x14008eccb`
- `ntoskrnl!ExAllocatePool3` at `0x14008eccb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008edc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008edf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ee2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008edc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008edf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ee2c`

## pseudocode

```c
__int64 __fastcall UxOpenSubKeyByIndex(PCWSTR SourceString, ULONG Index, __int64 a3, PVOID *a4, HANDLE *a5)
{
  HANDLE *v5; // r15
  PVOID v7; // rsi
  _DWORD *v9; // rdi
  NTSTATUS WideString; // ebx
  _DWORD *Pool3; // rax
  NTSTATUS v12; // eax
  unsigned int v13; // eax
  HANDLE Handle; // [rsp+48h] [rbp-31h] BYREF
  PVOID P; // [rsp+50h] [rbp-29h]
  __int128 v17; // [rsp+58h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  ULONG Length; // [rsp+E8h] [rbp+6Fh] BYREF
  void *KeyHandle; // [rsp+F0h] [rbp+77h] BYREF

  v5 = a5;
  KeyHandle = 0;
  Handle = 0;
  v7 = 0;
  *a4 = 0;
  *v5 = 0;
  P = 0;
  Length = 0;
  v9 = 0;
  DestinationString = 0;
  v17 = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  WideString = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( WideString >= 0 )
  {
    Length = 152;
    do
    {
      if ( v9 )
        ExFreePoolWithTag(v9, 0);
      Pool3 = (_DWORD *)ExAllocatePool3(258, Length, 1146252373, UxLowPriorityPool, 1);
      v9 = Pool3;
      if ( !Pool3 )
      {
        WideString = -1073741670;
        goto LABEL_16;
      }
      v12 = ZwEnumerateKey(KeyHandle, Index, KeyBasicInformation, Pool3, Length, &Length);
      WideString = v12;
    }
    while ( v12 == -2147483643 || v12 == -1073741789 );
    if ( v12 < 0 )
      goto LABEL_16;
    v13 = v9[3];
    if ( (v13 & 1) != 0 || v13 > 0xFFFE )
    {
      WideString = -1073741492;
    }
    else
    {
      *((_QWORD *)&v17 + 1) = v9 + 4;
      LOWORD(v17) = *((_WORD *)v9 + 6);
      WORD1(v17) = *((_WORD *)v9 + 6);
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v17;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      WideString = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
      if ( WideString < 0 )
        goto LABEL_16;
      WideString = UlAllocateWideString(v9 + 4);
      if ( WideString >= 0 )
      {
        *v5 = Handle;
        *a4 = P;
        Handle = 0;
        goto LABEL_16;
      }
      v7 = P;
    }
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
  }
LABEL_16:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  return (unsigned int)WideString;
}

```

## disassembly

```asm
0x14008ebcc  mov     rax, rsp
0x14008ebcf  mov     [rax+8], rbx
0x14008ebd3  mov     [rax+10h], rsi
0x14008ebd7  mov     [rax+18h], r8b
0x14008ebdb  push    rbp
0x14008ebdc  push    rdi
0x14008ebdd  push    r12
0x14008ebdf  push    r14
0x14008ebe1  push    r15
0x14008ebe3  lea     rbp, [rax-57h]
0x14008ebe7  sub     rsp, 0A0h
0x14008ebee  mov     r15, [rbp+4Fh+arg_20]
0x14008ebf2  xorps   xmm0, xmm0
0x14008ebf5  xor     eax, eax
0x14008ebf7  mov     [rbp+4Fh+KeyHandle], 0
0x14008ebff  mov     r12d, edx
0x14008ec02  mov     [rbp+4Fh+Handle], 0
0x14008ec0a  xor     esi, esi
0x14008ec0c  mov     [r9], rax
0x14008ec0f  xorps   xmm1, xmm1
0x14008ec12  mov     [r15], rax
0x14008ec15  mov     rdx, rcx; SourceString
0x14008ec18  mov     [rbp+4Fh+P], rsi
0x14008ec1c  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14008ec20  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14008ec24  mov     [rbp+4Fh+Length], esi
0x14008ec27  mov     r14, r9
0x14008ec2a  xor     edi, edi
0x14008ec2c  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14008ec30  movups  [rbp+4Fh+var_70], xmm1
0x14008ec34  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14008ec38  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x14008ec3c  call    cs:__imp_RtlInitUnicodeString
0x14008ec43  nop     dword ptr [rax+rax+00h]
0x14008ec48  lea     rax, [rbp+4Fh+DestinationString]
0x14008ec4c  mov     [rsp+0C0h+Disposition], rsi; Disposition
0x14008ec51  xorps   xmm0, xmm0
0x14008ec54  mov     [rsp+0C0h+CreateOptions], esi; CreateOptions
0x14008ec58  xor     r9d, r9d; TitleIndex
0x14008ec5b  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14008ec5f  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14008ec63  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14008ec6a  mov     edx, 2001Fh; DesiredAccess
0x14008ec6f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x14008ec73  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14008ec77  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x14008ec7e  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14008ec83  mov     [rsp+0C0h+Class], rsi; Class
0x14008ec88  call    cs:__imp_ZwCreateKey
0x14008ec8f  nop     dword ptr [rax+rax+00h]
0x14008ec94  mov     ebx, eax
0x14008ec96  test    eax, eax
0x14008ec98  js      loc_14008EDCD
0x14008ec9e  mov     [rbp+4Fh+Length], 98h
0x14008eca5  test    rdi, rdi
0x14008eca8  jnz     loc_14008EE27
0x14008ecae  mov     edx, [rbp+4Fh+Length]
0x14008ecb1  lea     r9, UxLowPriorityPool
0x14008ecb8  mov     ecx, 102h
0x14008ecbd  mov     dword ptr [rsp+0C0h+Class], 1
0x14008ecc5  mov     r8d, 44526C55h
0x14008eccb  call    cs:__imp_ExAllocatePool3
0x14008ecd2  nop     dword ptr [rax+rax+00h]
0x14008ecd7  mov     rdi, rax
0x14008ecda  test    rax, rax
0x14008ecdd  jz      loc_14008EE58
0x14008ece3  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14008ece7  lea     rax, [rbp+4Fh+Length]
0x14008eceb  mov     qword ptr [rsp+0C0h+CreateOptions], rax; ResultLength
0x14008ecf0  mov     r9, rdi; KeyInformation
0x14008ecf3  mov     eax, [rbp+4Fh+Length]
0x14008ecf6  xor     r8d, r8d; KeyInformationClass
0x14008ecf9  mov     edx, r12d; Index
0x14008ecfc  mov     dword ptr [rsp+0C0h+Class], eax; Length
0x14008ed00  call    cs:__imp_ZwEnumerateKey
0x14008ed07  nop     dword ptr [rax+rax+00h]
0x14008ed0c  mov     ebx, eax
0x14008ed0e  cmp     eax, 80000005h
0x14008ed13  jz      short loc_14008ECA5
0x14008ed15  cmp     eax, 0C0000023h
0x14008ed1a  jz      short loc_14008ECA5
0x14008ed1c  test    eax, eax
0x14008ed1e  js      loc_14008EDCD
0x14008ed24  mov     eax, [rdi+0Ch]
0x14008ed27  test    al, 1
0x14008ed29  jnz     loc_14008EE20
0x14008ed2f  cmp     eax, 0FFFEh
0x14008ed34  ja      loc_14008EE20
0x14008ed3a  xorps   xmm0, xmm0
0x14008ed3d  lea     rsi, [rdi+10h]
0x14008ed41  mov     qword ptr [rbp+4Fh+var_70+8], rsi
0x14008ed45  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14008ed49  movzx   eax, word ptr [rdi+0Ch]
0x14008ed4d  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x14008ed51  mov     word ptr [rbp+4Fh+var_70], ax
0x14008ed55  mov     edx, 20019h; DesiredAccess
0x14008ed5a  movzx   eax, word ptr [rdi+0Ch]
0x14008ed5e  mov     word ptr [rbp+4Fh+var_70+2], ax
0x14008ed62  mov     rax, [rbp+4Fh+KeyHandle]
0x14008ed66  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x14008ed6a  lea     rax, [rbp+4Fh+var_70]
0x14008ed6e  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14008ed72  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14008ed79  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x14008ed80  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14008ed85  call    cs:__imp_ZwOpenKey
0x14008ed8c  nop     dword ptr [rax+rax+00h]
0x14008ed91  mov     ebx, eax
0x14008ed93  test    eax, eax
0x14008ed95  js      short loc_14008EDCD
0x14008ed97  mov     edx, [rdi+0Ch]
0x14008ed9a  lea     r8, [rbp+4Fh+P]
0x14008ed9e  shr     rdx, 1
0x14008eda1  mov     rcx, rsi; Src
0x14008eda4  call    UlAllocateWideString
0x14008eda9  mov     ebx, eax
0x14008edab  test    eax, eax
0x14008edad  jns     loc_14008EE3D
0x14008edb3  mov     rsi, [rbp+4Fh+P]
0x14008edb7  test    rsi, rsi
0x14008edba  jz      short loc_14008EDCD
0x14008edbc  xor     edx, edx; Tag
0x14008edbe  mov     rcx, rsi; P
0x14008edc1  call    cs:__imp_ExFreePoolWithTag
0x14008edc8  nop     dword ptr [rax+rax+00h]
0x14008edcd  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x14008edd1  test    rcx, rcx
0x14008edd4  jz      short loc_14008EDE2
0x14008edd6  call    cs:__imp_ZwClose
0x14008eddd  nop     dword ptr [rax+rax+00h]
0x14008ede2  mov     rcx, [rbp+4Fh+Handle]; Handle
0x14008ede6  test    rcx, rcx
0x14008ede9  jnz     short loc_14008EE62
0x14008edeb  test    rdi, rdi
0x14008edee  jz      short loc_14008EE01
0x14008edf0  xor     edx, edx; Tag
0x14008edf2  mov     rcx, rdi; P
0x14008edf5  call    cs:__imp_ExFreePoolWithTag
0x14008edfc  nop     dword ptr [rax+rax+00h]
0x14008ee01  lea     r11, [rsp+0C0h+var_20]
0x14008ee09  mov     eax, ebx
0x14008ee0b  mov     rbx, [r11+30h]
0x14008ee0f  mov     rsi, [r11+38h]
0x14008ee13  mov     rsp, r11
0x14008ee16  pop     r15
0x14008ee18  pop     r14
0x14008ee1a  pop     r12
0x14008ee1c  pop     rdi
0x14008ee1d  pop     rbp
0x14008ee1e  retn
0x14008ee20  mov     ebx, 0C000014Ch
0x14008ee25  jmp     short loc_14008EDB7
0x14008ee27  xor     edx, edx; Tag
0x14008ee29  mov     rcx, rdi; P
0x14008ee2c  call    cs:__imp_ExFreePoolWithTag
0x14008ee33  nop     dword ptr [rax+rax+00h]
0x14008ee38  jmp     loc_14008ECAE
0x14008ee3d  mov     rax, [rbp+4Fh+Handle]
0x14008ee41  mov     [r15], rax
0x14008ee44  mov     rax, [rbp+4Fh+P]
0x14008ee48  mov     [r14], rax
0x14008ee4b  mov     [rbp+4Fh+Handle], 0
0x14008ee53  jmp     loc_14008EDCD
0x14008ee58  mov     ebx, 0C000009Ah
0x14008ee5d  jmp     loc_14008EDCD
0x14008ee62  call    cs:__imp_ZwClose
0x14008ee69  nop     dword ptr [rax+rax+00h]
0x14008ee6e  jmp     loc_14008EDEB
```
