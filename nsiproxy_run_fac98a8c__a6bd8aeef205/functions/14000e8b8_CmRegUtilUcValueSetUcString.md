# CmRegUtilUcValueSetUcString

- ea: `0x14000e8b8`
- end: `0x14000e9eb`
- name: `CmRegUtilUcValueSetUcString`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e1c4`
- `0x14000ea9c`

## callees

- `0x140006680`
- `0x140006980`
- `0x14000e8b8`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e944`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e944`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000e9c8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000e9c8`
- `ntoskrnl!ZwSetValueKey` at `0x14000e916`
- `ntoskrnl!ZwSetValueKey` at `0x14000e9b5`
- `ntoskrnl!ZwSetValueKey` at `0x14000e916`
- `ntoskrnl!ZwSetValueKey` at `0x14000e9b5`

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
0x14000e8b8  push    rbx
0x14000e8ba  push    rbp
0x14000e8bb  push    rsi
0x14000e8bc  push    rdi
0x14000e8bd  push    r14
0x14000e8bf  push    r15
0x14000e8c1  sub     rsp, 48h
0x14000e8c5  movzx   r9d, word ptr [r8]
0x14000e8c9  mov     r15d, 2
0x14000e8cf  movzx   eax, word ptr [r8+2]
0x14000e8d4  xorps   xmm0, xmm0
0x14000e8d7  sub     rax, r9
0x14000e8da  mov     rbx, r8
0x14000e8dd  mov     rbp, rdx
0x14000e8e0  mov     r14, rcx
0x14000e8e3  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x14000e8e8  cmp     rax, r15
0x14000e8eb  jb      short loc_14000E929
0x14000e8ed  mov     rax, [r8+8]
0x14000e8f1  xor     edi, edi
0x14000e8f3  shr     r9, 1
0x14000e8f6  mov     [rax+r9*2], di
0x14000e8fb  lea     r9d, [r15-1]; Type
0x14000e8ff  movzx   eax, word ptr [r8]
0x14000e903  add     eax, r15d
0x14000e906  mov     [rsp+78h+DataSize], eax; DataSize
0x14000e90a  mov     rax, [r8+8]
0x14000e90e  xor     r8d, r8d; TitleIndex
0x14000e911  mov     [rsp+78h+Data], rax; Data
0x14000e916  call    cs:__imp_ZwSetValueKey
0x14000e91d  nop     dword ptr [rax+rax+00h]
0x14000e922  mov     ebx, eax
0x14000e924  jmp     loc_14000E9DB
0x14000e929  lea     rsi, [r9+2]
0x14000e92d  mov     r8d, 63557050h; Tag
0x14000e933  lea     eax, [r15+r9]
0x14000e937  mov     rdx, rsi; NumberOfBytes
0x14000e93a  mov     ecx, 1; PoolType
0x14000e93f  mov     [rsp+78h+var_48.MaximumLength], ax
0x14000e944  call    cs:__imp_ExAllocatePoolWithTag
0x14000e94b  nop     dword ptr [rax+rax+00h]
0x14000e950  xor     edi, edi
0x14000e952  mov     [rsp+78h+var_48.Buffer], rax
0x14000e957  test    rax, rax
0x14000e95a  jz      short loc_14000E9D6
0x14000e95c  mov     r8, rsi; Size
0x14000e95f  xor     edx, edx; Val
0x14000e961  mov     rcx, rax; void *
0x14000e964  call    memset
0x14000e969  movzx   r8d, word ptr [rbx]; Size
0x14000e96d  mov     rdx, [rbx+8]; Src
0x14000e971  mov     rcx, [rsp+78h+var_48.Buffer]; void *
0x14000e976  mov     [rsp+78h+var_48.Length], r8w
0x14000e97c  call    memmove
0x14000e981  mov     rax, [rsp+78h+var_48.Buffer]
0x14000e986  lea     r9d, [rdi+1]; Type
0x14000e98a  movzx   ecx, [rsp+78h+var_48.Length]
0x14000e98f  xor     r8d, r8d; TitleIndex
0x14000e992  shr     rcx, 1
0x14000e995  mov     rdx, rbp; ValueName
0x14000e998  mov     [rax+rcx*2], di
0x14000e99c  mov     rcx, r14; KeyHandle
0x14000e99f  movzx   eax, [rsp+78h+var_48.Length]
0x14000e9a4  add     eax, r15d
0x14000e9a7  mov     [rsp+78h+DataSize], eax; DataSize
0x14000e9ab  mov     rax, [rsp+78h+var_48.Buffer]
0x14000e9b0  mov     [rsp+78h+Data], rax; Data
0x14000e9b5  call    cs:__imp_ZwSetValueKey
0x14000e9bc  nop     dword ptr [rax+rax+00h]
0x14000e9c1  lea     rcx, [rsp+78h+var_48]; UnicodeString
0x14000e9c6  mov     ebx, eax
0x14000e9c8  call    cs:__imp_RtlFreeUnicodeString
0x14000e9cf  nop     dword ptr [rax+rax+00h]
0x14000e9d4  jmp     short loc_14000E9DB
0x14000e9d6  mov     ebx, 0C000009Ah
0x14000e9db  mov     eax, ebx
0x14000e9dd  add     rsp, 48h
0x14000e9e1  pop     r15
0x14000e9e3  pop     r14
0x14000e9e5  pop     rdi
0x14000e9e6  pop     rsi
0x14000e9e7  pop     rbp
0x14000e9e8  pop     rbx
0x14000e9e9  retn
```
