# SecQueryRegKeyBinaryValue

- ea: `0x14002aed8`
- end: `0x14002b0cb`
- name: `SecQueryRegKeyBinaryValue`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140029fc8`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140011650`
- `0x140011700`
- `0x14002aed8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14002af45`
- `ntoskrnl!ZwOpenKey` at `0x14002af45`
- `ntoskrnl!ZwQueryValueKey` at `0x14002af7a`
- `ntoskrnl!ZwQueryValueKey` at `0x14002b006`
- `ntoskrnl!ZwQueryValueKey` at `0x14002af7a`
- `ntoskrnl!ZwQueryValueKey` at `0x14002b006`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002afc8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b054`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002afc8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b054`
- `ntoskrnl!ZwClose` at `0x14002b09f`
- `ntoskrnl!ZwClose` at `0x14002b09f`

## pseudocode

```c
__int64 __fastcall SecQueryRegKeyBinaryValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        _QWORD *a3,
        _DWORD *a4)
{
  NTSTATUS v7; // ebx
  NTSTATUS v8; // eax
  _DWORD *PoolWithTag; // rax
  _DWORD *v10; // rdi
  bool v11; // zf
  SIZE_T v12; // rdx
  PVOID v13; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-19h] BYREF

  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  KeyHandle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v7 >= 0 )
  {
    v8 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    v7 = v8;
    if ( v8 == -1073741789 )
    {
      if ( qword_140020008 )
        PoolWithTag = (_DWORD *)qword_140020008(256, ResultLength, 1985110867);
      else
        PoolWithTag = ExAllocatePoolWithTag(PagedPool, ResultLength, 0x76526353u);
      v10 = PoolWithTag;
      if ( PoolWithTag )
      {
        v7 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, PoolWithTag, ResultLength, &ResultLength);
        if ( v7 >= 0 )
        {
          if ( v10[1] == 3 )
          {
            v11 = qword_140020008 == 0;
            _mm_lfence();
            v12 = (unsigned int)v10[2];
            if ( v11 )
              v13 = ExAllocatePoolWithTag(PagedPool, v12, 0x76526353u);
            else
              v13 = (PVOID)qword_140020008(256, v12, 1985110867);
            *a3 = v13;
            if ( v13 )
            {
              _mm_lfence();
              memmove(v13, v10 + 3, (unsigned int)v10[2]);
              *a4 = v10[2];
            }
            else
            {
              v7 = -1073741670;
            }
          }
          else
          {
            v7 = -1073741788;
          }
        }
        SecFreePool(v10, 0x69426353u);
      }
      else
      {
        v7 = -1073741670;
      }
    }
    else if ( v8 >= 0 )
    {
      v7 = -1073741595;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002aed8  push    rbp
0x14002aeda  push    rbx
0x14002aedb  push    rdi
0x14002aedc  push    r12
0x14002aede  push    r14
0x14002aee0  push    r15
0x14002aee2  lea     rbp, [rsp-2Fh]
0x14002aee7  sub     rsp, 88h
0x14002aeee  mov     rax, cs:__security_cookie
0x14002aef5  xor     rax, rsp
0x14002aef8  mov     [rbp+57h+var_40], rax
0x14002aefc  mov     r15, r8
0x14002aeff  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x14002af03  mov     r14, rdx
0x14002af06  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002af0e  xorps   xmm0, xmm0
0x14002af11  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002af19  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002af1d  mov     [rbp+57h+KeyHandle], 0
0x14002af25  mov     edx, 20019h; DesiredAccess
0x14002af2a  mov     [rbp+57h+var_80], 0
0x14002af31  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002af35  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14002af3d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002af42  mov     r12, r9
0x14002af45  call    cs:__imp_ZwOpenKey
0x14002af4c  nop     dword ptr [rax+rax+00h]
0x14002af51  mov     ebx, eax
0x14002af53  test    eax, eax
0x14002af55  js      loc_14002B096
0x14002af5b  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002af5f  lea     rax, [rbp+57h+var_80]
0x14002af63  xor     r9d, r9d; KeyValueInformation
0x14002af66  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x14002af6b  mov     rdx, r14; ValueName
0x14002af6e  mov     [rsp+0B0h+Length], 0; Length
0x14002af76  lea     r8d, [r9+2]; KeyValueInformationClass
0x14002af7a  call    cs:__imp_ZwQueryValueKey
0x14002af81  nop     dword ptr [rax+rax+00h]
0x14002af86  mov     ebx, eax
0x14002af88  cmp     eax, 0C0000023h
0x14002af8d  jz      short loc_14002AFA1
0x14002af8f  test    eax, eax
0x14002af91  js      loc_14002B096
0x14002af97  mov     ebx, 0C00000E5h
0x14002af9c  jmp     loc_14002B096
0x14002afa1  mov     rax, cs:qword_140020008
0x14002afa8  mov     r8d, 76526353h; Tag
0x14002afae  mov     edx, [rbp+57h+var_80]; NumberOfBytes
0x14002afb1  test    rax, rax
0x14002afb4  jz      short loc_14002AFC3
0x14002afb6  mov     ecx, 100h
0x14002afbb  call    cs:__guard_dispatch_icall_fptr
0x14002afc1  jmp     short loc_14002AFD4
0x14002afc3  mov     ecx, 1; PoolType
0x14002afc8  call    cs:__imp_ExAllocatePoolWithTag
0x14002afcf  nop     dword ptr [rax+rax+00h]
0x14002afd4  mov     rdi, rax
0x14002afd7  test    rax, rax
0x14002afda  jnz     short loc_14002AFE6
0x14002afdc  mov     ebx, 0C000009Ah
0x14002afe1  jmp     loc_14002B096
0x14002afe6  mov     eax, [rbp+57h+var_80]
0x14002afe9  lea     rcx, [rbp+57h+var_80]
0x14002afed  mov     [rsp+0B0h+ResultLength], rcx; ResultLength
0x14002aff2  mov     r9, rdi; KeyValueInformation
0x14002aff5  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002aff9  mov     r8d, 2; KeyValueInformationClass
0x14002afff  mov     rdx, r14; ValueName
0x14002b002  mov     [rsp+0B0h+Length], eax; Length
0x14002b006  call    cs:__imp_ZwQueryValueKey
0x14002b00d  nop     dword ptr [rax+rax+00h]
0x14002b012  mov     ebx, eax
0x14002b014  test    eax, eax
0x14002b016  js      short loc_14002B089
0x14002b018  cmp     dword ptr [rdi+4], 3
0x14002b01c  jz      short loc_14002B025
0x14002b01e  mov     ebx, 0C0000024h
0x14002b023  jmp     short loc_14002B089
0x14002b025  cmp     cs:qword_140020008, 0
0x14002b02d  mov     r8d, 76526353h; Tag
0x14002b033  lfence
0x14002b036  mov     edx, [rdi+8]; NumberOfBytes
0x14002b039  jz      short loc_14002B04F
0x14002b03b  mov     rax, cs:qword_140020008
0x14002b042  mov     ecx, 100h
0x14002b047  call    cs:__guard_dispatch_icall_fptr
0x14002b04d  jmp     short loc_14002B060
0x14002b04f  mov     ecx, 1; PoolType
0x14002b054  call    cs:__imp_ExAllocatePoolWithTag
0x14002b05b  nop     dword ptr [rax+rax+00h]
0x14002b060  mov     [r15], rax
0x14002b063  test    rax, rax
0x14002b066  jnz     short loc_14002B06F
0x14002b068  mov     ebx, 0C000009Ah
0x14002b06d  jmp     short loc_14002B089
0x14002b06f  lfence
0x14002b072  mov     r8d, [rdi+8]; Size
0x14002b076  lea     rdx, [rdi+0Ch]; Src
0x14002b07a  mov     rcx, rax; void *
0x14002b07d  call    memmove
0x14002b082  mov     eax, [rdi+8]
0x14002b085  mov     [r12], eax
0x14002b089  mov     edx, 69426353h; Tag
0x14002b08e  mov     rcx, rdi; P
0x14002b091  call    SecFreePool
0x14002b096  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002b09a  test    rcx, rcx
0x14002b09d  jz      short loc_14002B0AB
0x14002b09f  call    cs:__imp_ZwClose
0x14002b0a6  nop     dword ptr [rax+rax+00h]
0x14002b0ab  mov     eax, ebx
0x14002b0ad  mov     rcx, [rbp+57h+var_40]
0x14002b0b1  xor     rcx, rsp; StackCookie
0x14002b0b4  call    __security_check_cookie
0x14002b0b9  add     rsp, 88h
0x14002b0c0  pop     r15
0x14002b0c2  pop     r14
0x14002b0c4  pop     r12
0x14002b0c6  pop     rdi
0x14002b0c7  pop     rbx
0x14002b0c8  pop     rbp
0x14002b0c9  retn
```
