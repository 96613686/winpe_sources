# EapEnumerateKey

- ea: `0x180009940`
- end: `0x1800099e7`
- name: `EapEnumerateKey`
- size: `167`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, ULONG Index)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009130`
- `0x180009ef0`

## callees

- `0x180003630`
- `0x180009940`
- `0x18000aae8`

## import_xrefs

- `ntdll!ZwEnumerateKey` at `0x180009979`
- `ntdll!ZwEnumerateKey` at `0x1800099c7`
- `ntdll!ZwEnumerateKey` at `0x180009979`
- `ntdll!ZwEnumerateKey` at `0x1800099c7`

## pseudocode

```c
NTSTATUS __fastcall EapEnumerateKey(HANDLE KeyHandle, ULONG Index, __int64 a3)
{
  void *v3; // r9
  NTSTATUS result; // eax
  ULONG Length; // ebx
  PVOID v9; // rdi
  ULONG ResultLength; // [rsp+60h] [rbp+18h] BYREF

  v3 = *(void **)a3;
  ResultLength = 0;
  result = ZwEnumerateKey(KeyHandle, Index, KeyBasicInformation, v3, *(_DWORD *)(a3 + 8), &ResultLength);
  if ( result == -1073741789 || result == -2147483643 )
  {
    Length = ResultLength;
    v9 = EaLibAllocate(ResultLength);
    if ( v9 )
    {
      EapReclaimKeyEnumBuffer(a3);
      *(_QWORD *)a3 = v9;
      *(_DWORD *)(a3 + 8) = Length;
      return ZwEnumerateKey(KeyHandle, Index, KeyBasicInformation, v9, Length, &ResultLength);
    }
    else
    {
      return -1073741801;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009940  mov     rax, rsp
0x180009943  mov     [rax+8], rbx
0x180009947  mov     [rax+10h], rbp
0x18000994b  push    rsi
0x18000994c  push    rdi
0x18000994d  push    r14
0x18000994f  sub     rsp, 30h
0x180009953  mov     r9, [r8]; KeyInformation
0x180009956  mov     rsi, r8
0x180009959  mov     dword ptr [rax+18h], 0
0x180009960  lea     rax, [rax+18h]
0x180009964  mov     [rsp+48h+ResultLength], rax; ResultLength
0x180009969  mov     ebp, edx
0x18000996b  mov     eax, [r8+8]
0x18000996f  mov     r14, rcx
0x180009972  xor     r8d, r8d; KeyInformationClass
0x180009975  mov     [rsp+48h+Length], eax; Length
0x180009979  call    cs:__imp_ZwEnumerateKey
0x18000997f  cmp     eax, 0C0000023h
0x180009984  jz      short loc_18000998D
0x180009986  cmp     eax, 80000005h
0x18000998b  jnz     short loc_1800099D4
0x18000998d  mov     ebx, [rsp+48h+arg_10]
0x180009991  mov     ecx, ebx
0x180009993  call    EaLibAllocate
0x180009998  mov     rdi, rax
0x18000999b  test    rax, rax
0x18000999e  jz      short loc_1800099CF
0x1800099a0  mov     rcx, rsi
0x1800099a3  call    EapReclaimKeyEnumBuffer
0x1800099a8  mov     [rsi], rdi
0x1800099ab  mov     [rsi+8], ebx
0x1800099ae  lea     rax, [rsp+48h+arg_10]
0x1800099b3  mov     r9, rdi; KeyInformation
0x1800099b6  mov     [rsp+48h+ResultLength], rax; ResultLength
0x1800099bb  xor     r8d, r8d; KeyInformationClass
0x1800099be  mov     edx, ebp; Index
0x1800099c0  mov     [rsp+48h+Length], ebx; Length
0x1800099c4  mov     rcx, r14; KeyHandle
0x1800099c7  call    cs:__imp_ZwEnumerateKey
0x1800099cd  jmp     short loc_1800099D4
0x1800099cf  mov     eax, 0C0000017h
0x1800099d4  mov     rbx, [rsp+48h+arg_0]
0x1800099d9  mov     rbp, [rsp+48h+arg_8]
0x1800099de  add     rsp, 30h
0x1800099e2  pop     r14
0x1800099e4  pop     rdi
0x1800099e5  pop     rsi
0x1800099e6  retn
```
