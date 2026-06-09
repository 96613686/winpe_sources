# EdppReadExclusions

- ea: `0x140053690`
- end: `0x1400537f7`
- name: `EdppReadExclusions`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400510ac`

## callees

- `0x140053690`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400536fb`
- `ntoskrnl!ZwOpenKey` at `0x1400536fb`
- `ntoskrnl!ZwQueryValueKey` at `0x140053730`
- `ntoskrnl!ZwQueryValueKey` at `0x140053792`
- `ntoskrnl!ZwQueryValueKey` at `0x140053730`
- `ntoskrnl!ZwQueryValueKey` at `0x140053792`
- `ntoskrnl!ZwClose` at `0x1400537d3`
- `ntoskrnl!ZwClose` at `0x1400537d3`
- `ntoskrnl!ExAllocatePool2` at `0x140053757`
- `ntoskrnl!ExAllocatePool2` at `0x140053757`

## pseudocode

```c
__int64 __fastcall EdppReadExclusions(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, __int64 a3, __int64 a4)
{
  NTSTATUS v7; // ebx
  void *Pool2; // rax
  __int16 v9; // ax
  void *KeyHandle; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+30h] BYREF

  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ResultLength = 0;
  if ( a3 )
  {
    ObjectAttributes.ObjectName = a1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v7 >= 0 )
    {
      v7 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
      if ( v7 == -1073741789 )
      {
        Pool2 = (void *)ExAllocatePool2(256, ResultLength, 1836279365);
        *(_QWORD *)a3 = Pool2;
        if ( Pool2 )
        {
          v7 = ZwQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, Pool2, ResultLength, &ResultLength);
          if ( v7 >= 0 )
          {
            if ( *(_DWORD *)(*(_QWORD *)a3 + 4LL) == 7 )
            {
              v9 = *(_WORD *)(*(_QWORD *)a3 + 8LL);
              *(_WORD *)a4 = v9;
              *(_WORD *)(a4 + 2) = v9;
              *(_QWORD *)(a4 + 8) = *(_QWORD *)a3 + 12LL;
            }
            else
            {
              v7 = -1073741811;
            }
          }
        }
        else
        {
          v7 = -1073741670;
        }
      }
    }
    if ( KeyHandle )
      ZwClose(KeyHandle);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140053690  mov     [rsp-18h+arg_0], rbx
0x140053695  mov     [rsp-18h+arg_8], rsi
0x14005369a  push    rbp
0x14005369b  push    rdi
0x14005369c  push    r14
0x14005369e  mov     rbp, rsp
0x1400536a1  sub     rsp, 70h
0x1400536a5  xor     eax, eax
0x1400536a7  mov     [rbp+KeyHandle], 0
0x1400536af  mov     dword ptr [rbp+ObjectAttributes+4], eax
0x1400536b2  mov     rsi, r9
0x1400536b5  mov     dword ptr [rbp+ObjectAttributes+1Ch], eax
0x1400536b8  mov     rdi, r8
0x1400536bb  mov     [rbp+arg_10], eax
0x1400536be  mov     r14, rdx
0x1400536c1  test    r8, r8
0x1400536c4  jnz     short loc_1400536D0
0x1400536c6  mov     ebx, 0C000000Dh
0x1400536cb  jmp     loc_1400537DF
0x1400536d0  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x1400536d4  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400536d8  xorps   xmm0, xmm0
0x1400536db  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400536e2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400536e6  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400536ea  mov     edx, 20019h; DesiredAccess
0x1400536ef  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400536f6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400536fb  call    cs:__imp_ZwOpenKey
0x140053702  nop     dword ptr [rax+rax+00h]
0x140053707  mov     ebx, eax
0x140053709  test    eax, eax
0x14005370b  js      loc_1400537CA
0x140053711  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140053715  lea     rax, [rbp+arg_10]
0x140053719  xor     r9d, r9d; KeyValueInformation
0x14005371c  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140053721  mov     rdx, r14; ValueName
0x140053724  mov     [rsp+70h+Length], 0; Length
0x14005372c  lea     r8d, [r9+2]; KeyValueInformationClass
0x140053730  call    cs:__imp_ZwQueryValueKey
0x140053737  nop     dword ptr [rax+rax+00h]
0x14005373c  mov     ebx, eax
0x14005373e  cmp     eax, 0C0000023h
0x140053743  jnz     loc_1400537CA
0x140053749  mov     edx, [rbp+arg_10]
0x14005374c  mov     ecx, 100h
0x140053751  mov     r8d, 6D736645h
0x140053757  call    cs:__imp_ExAllocatePool2
0x14005375e  nop     dword ptr [rax+rax+00h]
0x140053763  mov     [rdi], rax
0x140053766  mov     r9, rax; KeyValueInformation
0x140053769  test    rax, rax
0x14005376c  jnz     short loc_140053775
0x14005376e  mov     ebx, 0C000009Ah
0x140053773  jmp     short loc_1400537CA
0x140053775  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140053779  lea     rax, [rbp+arg_10]
0x14005377d  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140053782  mov     r8d, 2; KeyValueInformationClass
0x140053788  mov     eax, [rbp+arg_10]
0x14005378b  mov     rdx, r14; ValueName
0x14005378e  mov     [rsp+70h+Length], eax; Length
0x140053792  call    cs:__imp_ZwQueryValueKey
0x140053799  nop     dword ptr [rax+rax+00h]
0x14005379e  mov     ebx, eax
0x1400537a0  test    eax, eax
0x1400537a2  js      short loc_1400537CA
0x1400537a4  mov     rax, [rdi]
0x1400537a7  cmp     dword ptr [rax+4], 7
0x1400537ab  jz      short loc_1400537B4
0x1400537ad  mov     ebx, 0C000000Dh
0x1400537b2  jmp     short loc_1400537CA
0x1400537b4  movzx   eax, word ptr [rax+8]
0x1400537b8  mov     [rsi], ax
0x1400537bb  mov     [rsi+2], ax
0x1400537bf  mov     rax, [rdi]
0x1400537c2  add     rax, 0Ch
0x1400537c6  mov     [rsi+8], rax
0x1400537ca  mov     rcx, [rbp+KeyHandle]; Handle
0x1400537ce  test    rcx, rcx
0x1400537d1  jz      short loc_1400537DF
0x1400537d3  call    cs:__imp_ZwClose
0x1400537da  nop     dword ptr [rax+rax+00h]
0x1400537df  lea     r11, [rsp+70h+var_s0]
0x1400537e4  mov     eax, ebx
0x1400537e6  mov     rbx, [r11+20h]
0x1400537ea  mov     rsi, [r11+28h]
0x1400537ee  mov     rsp, r11
0x1400537f1  pop     r14
0x1400537f3  pop     rdi
0x1400537f4  pop     rbp
0x1400537f5  retn
```
