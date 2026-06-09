# CmRegUtilUcValueGetFullBuffer

- ea: `0x14000e744`
- end: `0x14000e8b2`
- name: `CmRegUtilUcValueGetFullBuffer`
- size: `366`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PUNICODE_STRING ValueName@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dfdc`

## callees

- `0x140006980`
- `0x14000e744`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e881`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e881`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e78c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e81b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e78c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e81b`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e7ce`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e85f`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e7ce`
- `ntoskrnl!ZwQueryValueKey` at `0x14000e85f`

## pseudocode

```c
__int64 __fastcall CmRegUtilUcValueGetFullBuffer(
        HANDLE KeyHandle,
        PUNICODE_STRING ValueName,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *v5; // rsi
  unsigned int v8; // eax
  ULONG Length; // edi
  _DWORD *PoolWithTag; // rax
  _DWORD *v11; // rbx
  NTSTATUS v12; // edi
  _DWORD *v14; // rax
  ULONG ResultLength; // [rsp+68h] [rbp+20h] BYREF

  v5 = a5;
  ResultLength = 0;
  v8 = (ValueName->Length + 31) & 0xFFFFFFF8;
  *a5 = 0;
  Length = v8;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v8, 0x62527050u);
  v11 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, Length);
  v12 = ZwQueryValueKey(KeyHandle, ValueName, KeyValueFullInformation, v11, Length, &ResultLength);
  if ( v12 < 0 )
  {
    ExFreePoolWithTag(v11, 0);
    if ( v12 != -2147483643 && v12 != -1073741789 )
      return (unsigned int)v12;
    v14 = ExAllocatePoolWithTag((POOL_TYPE)512, ResultLength, 0x62527050u);
    v11 = v14;
    if ( v14 )
    {
      memset(v14, 0, ResultLength);
      v12 = ZwQueryValueKey(KeyHandle, ValueName, KeyValueFullInformation, v11, ResultLength, &ResultLength);
      if ( v12 < 0 )
      {
LABEL_10:
        ExFreePoolWithTag(v11, 0);
        return (unsigned int)v12;
      }
      goto LABEL_8;
    }
    return 3221225626LL;
  }
LABEL_8:
  if ( v11[1] != 3 )
  {
    v12 = -1073741788;
    goto LABEL_10;
  }
  *v5 = v11;
  return 0;
}

```

## disassembly

```asm
0x14000e744  mov     rax, rsp
0x14000e747  mov     [rax+8], rbx
0x14000e74b  mov     [rax+10h], rbp
0x14000e74f  mov     [rax+20h], r9d
0x14000e753  push    rsi
0x14000e754  push    rdi
0x14000e755  push    r14
0x14000e757  sub     rsp, 30h
0x14000e75b  mov     rsi, [rsp+48h+arg_20]
0x14000e760  mov     rbp, rdx
0x14000e763  mov     dword ptr [rax+20h], 0
0x14000e76a  mov     r14, rcx
0x14000e76d  movzx   eax, word ptr [rdx]
0x14000e770  mov     r8d, 62527050h; Tag
0x14000e776  add     eax, 1Fh
0x14000e779  mov     ecx, 200h; PoolType
0x14000e77e  and     eax, 0FFFFFFF8h
0x14000e781  mov     qword ptr [rsi], 0
0x14000e788  mov     edx, eax; NumberOfBytes
0x14000e78a  mov     edi, eax
0x14000e78c  call    cs:__imp_ExAllocatePoolWithTag
0x14000e793  nop     dword ptr [rax+rax+00h]
0x14000e798  mov     rbx, rax
0x14000e79b  test    rax, rax
0x14000e79e  jz      loc_14000E899
0x14000e7a4  mov     r8d, edi; Size
0x14000e7a7  xor     edx, edx; Val
0x14000e7a9  mov     rcx, rax; void *
0x14000e7ac  call    memset
0x14000e7b1  lea     rax, [rsp+48h+arg_18]
0x14000e7b6  mov     r9, rbx; KeyValueInformation
0x14000e7b9  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000e7be  mov     r8d, 1; KeyValueInformationClass
0x14000e7c4  mov     rdx, rbp; ValueName
0x14000e7c7  mov     [rsp+48h+Length], edi; Length
0x14000e7cb  mov     rcx, r14; KeyHandle
0x14000e7ce  call    cs:__imp_ZwQueryValueKey
0x14000e7d5  nop     dword ptr [rax+rax+00h]
0x14000e7da  mov     edi, eax
0x14000e7dc  test    eax, eax
0x14000e7de  jns     loc_14000E871
0x14000e7e4  xor     edx, edx; Tag
0x14000e7e6  mov     rcx, rbx; P
0x14000e7e9  call    cs:__imp_ExFreePoolWithTag
0x14000e7f0  nop     dword ptr [rax+rax+00h]
0x14000e7f5  cmp     edi, 80000005h
0x14000e7fb  jz      short loc_14000E80C
0x14000e7fd  cmp     edi, 0C0000023h
0x14000e803  jz      short loc_14000E80C
0x14000e805  mov     eax, edi
0x14000e807  jmp     loc_14000E89E
0x14000e80c  mov     edx, [rsp+48h+arg_18]; NumberOfBytes
0x14000e810  mov     ecx, 200h; PoolType
0x14000e815  mov     r8d, 62527050h; Tag
0x14000e81b  call    cs:__imp_ExAllocatePoolWithTag
0x14000e822  nop     dword ptr [rax+rax+00h]
0x14000e827  mov     rbx, rax
0x14000e82a  test    rax, rax
0x14000e82d  jz      short loc_14000E899
0x14000e82f  mov     r8d, [rsp+48h+arg_18]; Size
0x14000e834  xor     edx, edx; Val
0x14000e836  mov     rcx, rax; void *
0x14000e839  call    memset
0x14000e83e  lea     rax, [rsp+48h+arg_18]
0x14000e843  mov     r9, rbx; KeyValueInformation
0x14000e846  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000e84b  mov     r8d, 1; KeyValueInformationClass
0x14000e851  mov     eax, [rsp+48h+arg_18]
0x14000e855  mov     rdx, rbp; ValueName
0x14000e858  mov     rcx, r14; KeyHandle
0x14000e85b  mov     [rsp+48h+Length], eax; Length
0x14000e85f  call    cs:__imp_ZwQueryValueKey
0x14000e866  nop     dword ptr [rax+rax+00h]
0x14000e86b  mov     edi, eax
0x14000e86d  test    eax, eax
0x14000e86f  js      short loc_14000E87C
0x14000e871  cmp     dword ptr [rbx+4], 3
0x14000e875  jz      short loc_14000E892
0x14000e877  mov     edi, 0C0000024h
0x14000e87c  xor     edx, edx; Tag
0x14000e87e  mov     rcx, rbx; P
0x14000e881  call    cs:__imp_ExFreePoolWithTag
0x14000e888  nop     dword ptr [rax+rax+00h]
0x14000e88d  jmp     loc_14000E805
0x14000e892  mov     [rsi], rbx
0x14000e895  xor     eax, eax
0x14000e897  jmp     short loc_14000E89E
0x14000e899  mov     eax, 0C000009Ah
0x14000e89e  mov     rbx, [rsp+48h+arg_0]
0x14000e8a3  mov     rbp, [rsp+48h+arg_8]
0x14000e8a8  add     rsp, 30h
0x14000e8ac  pop     r14
0x14000e8ae  pop     rdi
0x14000e8af  pop     rsi
0x14000e8b0  retn
```
