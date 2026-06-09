# CmRegUtilUcValueGetFullBuffer

- ea: `0x14000a6b4`
- end: `0x14000a822`
- name: `CmRegUtilUcValueGetFullBuffer`
- size: `366`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PUNICODE_STRING ValueName@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009f4c`

## callees

- `0x140002940`
- `0x14000a6b4`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000a73e`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a7cf`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a73e`
- `ntoskrnl!ZwQueryValueKey` at `0x14000a7cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a759`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a7f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a759`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a7f1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a6fc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a78b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a6fc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a78b`

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
0x14000a6b4  mov     rax, rsp
0x14000a6b7  mov     [rax+8], rbx
0x14000a6bb  mov     [rax+10h], rbp
0x14000a6bf  mov     [rax+20h], r9d
0x14000a6c3  push    rsi
0x14000a6c4  push    rdi
0x14000a6c5  push    r14
0x14000a6c7  sub     rsp, 30h
0x14000a6cb  mov     rsi, [rsp+48h+arg_20]
0x14000a6d0  mov     rbp, rdx
0x14000a6d3  mov     dword ptr [rax+20h], 0
0x14000a6da  mov     r14, rcx
0x14000a6dd  movzx   eax, word ptr [rdx]
0x14000a6e0  mov     r8d, 62527050h; Tag
0x14000a6e6  add     eax, 1Fh
0x14000a6e9  mov     ecx, 200h; PoolType
0x14000a6ee  and     eax, 0FFFFFFF8h
0x14000a6f1  mov     qword ptr [rsi], 0
0x14000a6f8  mov     edx, eax; NumberOfBytes
0x14000a6fa  mov     edi, eax
0x14000a6fc  call    cs:__imp_ExAllocatePoolWithTag
0x14000a703  nop     dword ptr [rax+rax+00h]
0x14000a708  mov     rbx, rax
0x14000a70b  test    rax, rax
0x14000a70e  jz      loc_14000A809
0x14000a714  mov     r8d, edi; Size
0x14000a717  xor     edx, edx; Val
0x14000a719  mov     rcx, rax; void *
0x14000a71c  call    memset
0x14000a721  lea     rax, [rsp+48h+arg_18]
0x14000a726  mov     r9, rbx; KeyValueInformation
0x14000a729  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000a72e  mov     r8d, 1; KeyValueInformationClass
0x14000a734  mov     rdx, rbp; ValueName
0x14000a737  mov     [rsp+48h+Length], edi; Length
0x14000a73b  mov     rcx, r14; KeyHandle
0x14000a73e  call    cs:__imp_ZwQueryValueKey
0x14000a745  nop     dword ptr [rax+rax+00h]
0x14000a74a  mov     edi, eax
0x14000a74c  test    eax, eax
0x14000a74e  jns     loc_14000A7E1
0x14000a754  xor     edx, edx; Tag
0x14000a756  mov     rcx, rbx; P
0x14000a759  call    cs:__imp_ExFreePoolWithTag
0x14000a760  nop     dword ptr [rax+rax+00h]
0x14000a765  cmp     edi, 80000005h
0x14000a76b  jz      short loc_14000A77C
0x14000a76d  cmp     edi, 0C0000023h
0x14000a773  jz      short loc_14000A77C
0x14000a775  mov     eax, edi
0x14000a777  jmp     loc_14000A80E
0x14000a77c  mov     edx, [rsp+48h+arg_18]; NumberOfBytes
0x14000a780  mov     ecx, 200h; PoolType
0x14000a785  mov     r8d, 62527050h; Tag
0x14000a78b  call    cs:__imp_ExAllocatePoolWithTag
0x14000a792  nop     dword ptr [rax+rax+00h]
0x14000a797  mov     rbx, rax
0x14000a79a  test    rax, rax
0x14000a79d  jz      short loc_14000A809
0x14000a79f  mov     r8d, [rsp+48h+arg_18]; Size
0x14000a7a4  xor     edx, edx; Val
0x14000a7a6  mov     rcx, rax; void *
0x14000a7a9  call    memset
0x14000a7ae  lea     rax, [rsp+48h+arg_18]
0x14000a7b3  mov     r9, rbx; KeyValueInformation
0x14000a7b6  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14000a7bb  mov     r8d, 1; KeyValueInformationClass
0x14000a7c1  mov     eax, [rsp+48h+arg_18]
0x14000a7c5  mov     rdx, rbp; ValueName
0x14000a7c8  mov     rcx, r14; KeyHandle
0x14000a7cb  mov     [rsp+48h+Length], eax; Length
0x14000a7cf  call    cs:__imp_ZwQueryValueKey
0x14000a7d6  nop     dword ptr [rax+rax+00h]
0x14000a7db  mov     edi, eax
0x14000a7dd  test    eax, eax
0x14000a7df  js      short loc_14000A7EC
0x14000a7e1  cmp     dword ptr [rbx+4], 3
0x14000a7e5  jz      short loc_14000A802
0x14000a7e7  mov     edi, 0C0000024h
0x14000a7ec  xor     edx, edx; Tag
0x14000a7ee  mov     rcx, rbx; P
0x14000a7f1  call    cs:__imp_ExFreePoolWithTag
0x14000a7f8  nop     dword ptr [rax+rax+00h]
0x14000a7fd  jmp     loc_14000A775
0x14000a802  mov     [rsi], rbx
0x14000a805  xor     eax, eax
0x14000a807  jmp     short loc_14000A80E
0x14000a809  mov     eax, 0C000009Ah
0x14000a80e  mov     rbx, [rsp+48h+arg_0]
0x14000a813  mov     rbp, [rsp+48h+arg_8]
0x14000a818  add     rsp, 30h
0x14000a81c  pop     r14
0x14000a81e  pop     rdi
0x14000a81f  pop     rsi
0x14000a820  retn
```
