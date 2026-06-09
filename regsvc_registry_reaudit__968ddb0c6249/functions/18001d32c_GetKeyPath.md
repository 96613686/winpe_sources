# GetKeyPath

- ea: `0x18001d32c`
- end: `0x18001d385`
- name: `GetKeyPath`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800035a0`

## callees

- `0x18001d32c`
- `0x18001e43d`

## import_xrefs

- `ntdll!NtQueryKey` at `0x18001d355`
- `ntdll!NtQueryKey` at `0x18001d355`

## pseudocode

```c
NTSTATUS __fastcall GetKeyPath(void *a1, __int64 a2)
{
  ULONG v2; // r9d
  void *v3; // r8
  NTSTATUS result; // eax
  ULONG *v6; // rcx
  ULONG ResultLength; // [rsp+48h] [rbp+10h] BYREF

  v2 = *(unsigned __int16 *)(a2 + 2);
  v3 = *(void **)(a2 + 8);
  ResultLength = 0;
  result = NtQueryKey(a1, KeyNameInformation, v3, v2, &ResultLength);
  if ( result >= 0 )
  {
    v6 = *(ULONG **)(a2 + 8);
    ResultLength = *v6;
    memmove_0(v6, v6 + 1, ResultLength);
    *(_WORD *)a2 = ResultLength;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001d32c  push    rbx
0x18001d32e  sub     rsp, 30h
0x18001d332  movzx   r9d, word ptr [rdx+2]; Length
0x18001d337  lea     rax, [rsp+38h+arg_8]
0x18001d33c  mov     r8, [rdx+8]; KeyInformation
0x18001d340  mov     rbx, rdx
0x18001d343  mov     edx, 3; KeyInformationClass
0x18001d348  mov     [rsp+38h+ResultLength], rax; ResultLength
0x18001d34d  mov     [rsp+38h+arg_8], 0
0x18001d355  call    cs:__imp_NtQueryKey
0x18001d35b  test    eax, eax
0x18001d35d  js      short loc_18001D37F
0x18001d35f  mov     rcx, [rbx+8]; void *
0x18001d363  mov     eax, [rcx]
0x18001d365  lea     rdx, [rcx+4]; Src
0x18001d369  mov     r8d, eax; Size
0x18001d36c  mov     [rsp+38h+arg_8], eax
0x18001d370  call    memmove_0
0x18001d375  movzx   eax, word ptr [rsp+38h+arg_8]
0x18001d37a  mov     [rbx], ax
0x18001d37d  xor     eax, eax
0x18001d37f  add     rsp, 30h
0x18001d383  pop     rbx
0x18001d384  retn
```
