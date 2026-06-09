# CmRegUtilUcValueSetUcString

- ea: `0x14000a828`
- end: `0x14000a95b`
- name: `CmRegUtilUcValueSetUcString`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a134`
- `0x14000aa0c`

## callees

- `0x140002640`
- `0x140002940`
- `0x14000a828`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a938`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a938`
- `ntoskrnl!ZwSetValueKey` at `0x14000a886`
- `ntoskrnl!ZwSetValueKey` at `0x14000a925`
- `ntoskrnl!ZwSetValueKey` at `0x14000a886`
- `ntoskrnl!ZwSetValueKey` at `0x14000a925`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a8b4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a8b4`

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
0x14000a828  push    rbx
0x14000a82a  push    rbp
0x14000a82b  push    rsi
0x14000a82c  push    rdi
0x14000a82d  push    r14
0x14000a82f  push    r15
0x14000a831  sub     rsp, 48h
0x14000a835  movzx   r9d, word ptr [r8]
0x14000a839  mov     r15d, 2
0x14000a83f  movzx   eax, word ptr [r8+2]
0x14000a844  xorps   xmm0, xmm0
0x14000a847  sub     rax, r9
0x14000a84a  mov     rbx, r8
0x14000a84d  mov     rbp, rdx
0x14000a850  mov     r14, rcx
0x14000a853  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x14000a858  cmp     rax, r15
0x14000a85b  jb      short loc_14000A899
0x14000a85d  mov     rax, [r8+8]
0x14000a861  xor     edi, edi
0x14000a863  shr     r9, 1
0x14000a866  mov     [rax+r9*2], di
0x14000a86b  lea     r9d, [r15-1]; Type
0x14000a86f  movzx   eax, word ptr [r8]
0x14000a873  add     eax, r15d
0x14000a876  mov     [rsp+78h+DataSize], eax; DataSize
0x14000a87a  mov     rax, [r8+8]
0x14000a87e  xor     r8d, r8d; TitleIndex
0x14000a881  mov     [rsp+78h+Data], rax; Data
0x14000a886  call    cs:__imp_ZwSetValueKey
0x14000a88d  nop     dword ptr [rax+rax+00h]
0x14000a892  mov     ebx, eax
0x14000a894  jmp     loc_14000A94B
0x14000a899  lea     rsi, [r9+2]
0x14000a89d  mov     r8d, 63557050h; Tag
0x14000a8a3  lea     eax, [r15+r9]
0x14000a8a7  mov     rdx, rsi; NumberOfBytes
0x14000a8aa  mov     ecx, 1; PoolType
0x14000a8af  mov     [rsp+78h+var_48.MaximumLength], ax
0x14000a8b4  call    cs:__imp_ExAllocatePoolWithTag
0x14000a8bb  nop     dword ptr [rax+rax+00h]
0x14000a8c0  xor     edi, edi
0x14000a8c2  mov     [rsp+78h+var_48.Buffer], rax
0x14000a8c7  test    rax, rax
0x14000a8ca  jz      short loc_14000A946
0x14000a8cc  mov     r8, rsi; Size
0x14000a8cf  xor     edx, edx; Val
0x14000a8d1  mov     rcx, rax; void *
0x14000a8d4  call    memset
0x14000a8d9  movzx   r8d, word ptr [rbx]; Size
0x14000a8dd  mov     rdx, [rbx+8]; Src
0x14000a8e1  mov     rcx, [rsp+78h+var_48.Buffer]; void *
0x14000a8e6  mov     [rsp+78h+var_48.Length], r8w
0x14000a8ec  call    memmove
0x14000a8f1  mov     rax, [rsp+78h+var_48.Buffer]
0x14000a8f6  lea     r9d, [rdi+1]; Type
0x14000a8fa  movzx   ecx, [rsp+78h+var_48.Length]
0x14000a8ff  xor     r8d, r8d; TitleIndex
0x14000a902  shr     rcx, 1
0x14000a905  mov     rdx, rbp; ValueName
0x14000a908  mov     [rax+rcx*2], di
0x14000a90c  mov     rcx, r14; KeyHandle
0x14000a90f  movzx   eax, [rsp+78h+var_48.Length]
0x14000a914  add     eax, r15d
0x14000a917  mov     [rsp+78h+DataSize], eax; DataSize
0x14000a91b  mov     rax, [rsp+78h+var_48.Buffer]
0x14000a920  mov     [rsp+78h+Data], rax; Data
0x14000a925  call    cs:__imp_ZwSetValueKey
0x14000a92c  nop     dword ptr [rax+rax+00h]
0x14000a931  lea     rcx, [rsp+78h+var_48]; UnicodeString
0x14000a936  mov     ebx, eax
0x14000a938  call    cs:__imp_RtlFreeUnicodeString
0x14000a93f  nop     dword ptr [rax+rax+00h]
0x14000a944  jmp     short loc_14000A94B
0x14000a946  mov     ebx, 0C000009Ah
0x14000a94b  mov     eax, ebx
0x14000a94d  add     rsp, 48h
0x14000a951  pop     r15
0x14000a953  pop     r14
0x14000a955  pop     rdi
0x14000a956  pop     rsi
0x14000a957  pop     rbp
0x14000a958  pop     rbx
0x14000a959  retn
```
