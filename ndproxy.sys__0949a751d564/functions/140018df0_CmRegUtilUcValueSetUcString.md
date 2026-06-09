# CmRegUtilUcValueSetUcString

- ea: `0x140018df0`
- end: `0x140018f23`
- name: `CmRegUtilUcValueSetUcString`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140018734`
- `0x140018fd4`

## callees

- `0x1400081c0`
- `0x1400084c0`
- `0x140018df0`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x140018e4e`
- `ntoskrnl!ZwSetValueKey` at `0x140018eed`
- `ntoskrnl!ZwSetValueKey` at `0x140018e4e`
- `ntoskrnl!ZwSetValueKey` at `0x140018eed`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018e7c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018e7c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018f00`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018f00`

## pseudocode

```c
__int64 __fastcall CmRegUtilUcValueSetUcString(HANDLE KeyHandle, PUNICODE_STRING ValueName, unsigned __int16 *a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 v4; // rax
  unsigned int v8; // ebx
  size_t v9; // rsi
  wchar_t *PoolWithTag; // rax
  const void *v11; // rdx
  struct _UNICODE_STRING Data; // [rsp+30h] [rbp-48h] BYREF

  v3 = *a3;
  v4 = a3[1] - v3;
  Data = 0;
  if ( v4 < 2 )
  {
    v9 = v3 + 2;
    Data.MaximumLength = v3 + 2;
    PoolWithTag = (wchar_t *)ExAllocatePoolWithTag(PagedPool, v3 + 2, 0x63557050u);
    Data.Buffer = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v9);
      v11 = (const void *)*((_QWORD *)a3 + 1);
      Data.Length = *a3;
      memmove(Data.Buffer, v11, Data.Length);
      Data.Buffer[(unsigned __int64)Data.Length >> 1] = 0;
      v8 = ZwSetValueKey(KeyHandle, ValueName, 0, 1u, Data.Buffer, Data.Length + 2);
      RtlFreeUnicodeString(&Data);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * (v3 >> 1)) = 0;
    return (unsigned int)ZwSetValueKey(KeyHandle, ValueName, 0, 1u, *((PVOID *)a3 + 1), *a3 + 2);
  }
  return v8;
}

```

## disassembly

```asm
0x140018df0  push    rbx
0x140018df2  push    rbp
0x140018df3  push    rsi
0x140018df4  push    rdi
0x140018df5  push    r14
0x140018df7  push    r15
0x140018df9  sub     rsp, 48h
0x140018dfd  movzx   r9d, word ptr [r8]
0x140018e01  mov     r15d, 2
0x140018e07  movzx   eax, word ptr [r8+2]
0x140018e0c  xorps   xmm0, xmm0
0x140018e0f  sub     rax, r9
0x140018e12  mov     rbx, r8
0x140018e15  mov     rbp, rdx
0x140018e18  mov     r14, rcx
0x140018e1b  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x140018e20  cmp     rax, r15
0x140018e23  jb      short loc_140018E61
0x140018e25  mov     rax, [r8+8]
0x140018e29  xor     edi, edi
0x140018e2b  shr     r9, 1
0x140018e2e  mov     [rax+r9*2], di
0x140018e33  lea     r9d, [r15-1]; Type
0x140018e37  movzx   eax, word ptr [r8]
0x140018e3b  add     eax, r15d
0x140018e3e  mov     [rsp+78h+DataSize], eax; DataSize
0x140018e42  mov     rax, [r8+8]
0x140018e46  xor     r8d, r8d; TitleIndex
0x140018e49  mov     [rsp+78h+Data], rax; Data
0x140018e4e  call    cs:__imp_ZwSetValueKey
0x140018e55  nop     dword ptr [rax+rax+00h]
0x140018e5a  mov     ebx, eax
0x140018e5c  jmp     loc_140018F13
0x140018e61  lea     rsi, [r9+2]
0x140018e65  mov     r8d, 63557050h; Tag
0x140018e6b  lea     eax, [r15+r9]
0x140018e6f  mov     rdx, rsi; NumberOfBytes
0x140018e72  mov     ecx, 1; PoolType
0x140018e77  mov     [rsp+78h+var_48.MaximumLength], ax
0x140018e7c  call    cs:__imp_ExAllocatePoolWithTag
0x140018e83  nop     dword ptr [rax+rax+00h]
0x140018e88  xor     edi, edi
0x140018e8a  mov     [rsp+78h+var_48.Buffer], rax
0x140018e8f  test    rax, rax
0x140018e92  jz      short loc_140018F0E
0x140018e94  mov     r8, rsi; Size
0x140018e97  xor     edx, edx; Val
0x140018e99  mov     rcx, rax; void *
0x140018e9c  call    memset
0x140018ea1  movzx   r8d, word ptr [rbx]; Size
0x140018ea5  mov     rdx, [rbx+8]; Src
0x140018ea9  mov     rcx, [rsp+78h+var_48.Buffer]; void *
0x140018eae  mov     [rsp+78h+var_48.Length], r8w
0x140018eb4  call    memmove
0x140018eb9  mov     rax, [rsp+78h+var_48.Buffer]
0x140018ebe  lea     r9d, [rdi+1]; Type
0x140018ec2  movzx   ecx, [rsp+78h+var_48.Length]
0x140018ec7  xor     r8d, r8d; TitleIndex
0x140018eca  shr     rcx, 1
0x140018ecd  mov     rdx, rbp; ValueName
0x140018ed0  mov     [rax+rcx*2], di
0x140018ed4  mov     rcx, r14; KeyHandle
0x140018ed7  movzx   eax, [rsp+78h+var_48.Length]
0x140018edc  add     eax, r15d
0x140018edf  mov     [rsp+78h+DataSize], eax; DataSize
0x140018ee3  mov     rax, [rsp+78h+var_48.Buffer]
0x140018ee8  mov     [rsp+78h+Data], rax; Data
0x140018eed  call    cs:__imp_ZwSetValueKey
0x140018ef4  nop     dword ptr [rax+rax+00h]
0x140018ef9  lea     rcx, [rsp+78h+var_48]; UnicodeString
0x140018efe  mov     ebx, eax
0x140018f00  call    cs:__imp_RtlFreeUnicodeString
0x140018f07  nop     dword ptr [rax+rax+00h]
0x140018f0c  jmp     short loc_140018F13
0x140018f0e  mov     ebx, 0C000009Ah
0x140018f13  mov     eax, ebx
0x140018f15  add     rsp, 48h
0x140018f19  pop     r15
0x140018f1b  pop     r14
0x140018f1d  pop     rdi
0x140018f1e  pop     rsi
0x140018f1f  pop     rbp
0x140018f20  pop     rbx
0x140018f21  retn
```
