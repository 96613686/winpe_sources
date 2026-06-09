# CmRegUtilUcValueSetUcString

- ea: `0x1400108a0`
- end: `0x1400109d3`
- name: `CmRegUtilUcValueSetUcString`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400102e4`
- `0x140010a84`

## callees

- `0x1400014c0`
- `0x1400017c0`
- `0x1400108a0`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1400108fe`
- `ntoskrnl!ZwSetValueKey` at `0x14001099d`
- `ntoskrnl!ZwSetValueKey` at `0x1400108fe`
- `ntoskrnl!ZwSetValueKey` at `0x14001099d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400109b0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400109b0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001092c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001092c`

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
0x1400108a0  push    rbx
0x1400108a2  push    rbp
0x1400108a3  push    rsi
0x1400108a4  push    rdi
0x1400108a5  push    r14
0x1400108a7  push    r15
0x1400108a9  sub     rsp, 48h
0x1400108ad  movzx   r9d, word ptr [r8]
0x1400108b1  mov     r15d, 2
0x1400108b7  movzx   eax, word ptr [r8+2]
0x1400108bc  xorps   xmm0, xmm0
0x1400108bf  sub     rax, r9
0x1400108c2  mov     rbx, r8
0x1400108c5  mov     rbp, rdx
0x1400108c8  mov     r14, rcx
0x1400108cb  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x1400108d0  cmp     rax, r15
0x1400108d3  jb      short loc_140010911
0x1400108d5  mov     rax, [r8+8]
0x1400108d9  xor     edi, edi
0x1400108db  shr     r9, 1
0x1400108de  mov     [rax+r9*2], di
0x1400108e3  lea     r9d, [r15-1]; Type
0x1400108e7  movzx   eax, word ptr [r8]
0x1400108eb  add     eax, r15d
0x1400108ee  mov     [rsp+78h+DataSize], eax; DataSize
0x1400108f2  mov     rax, [r8+8]
0x1400108f6  xor     r8d, r8d; TitleIndex
0x1400108f9  mov     [rsp+78h+Data], rax; Data
0x1400108fe  call    cs:__imp_ZwSetValueKey
0x140010905  nop     dword ptr [rax+rax+00h]
0x14001090a  mov     ebx, eax
0x14001090c  jmp     loc_1400109C3
0x140010911  lea     rsi, [r9+2]
0x140010915  mov     r8d, 63557050h; Tag
0x14001091b  lea     eax, [r15+r9]
0x14001091f  mov     rdx, rsi; NumberOfBytes
0x140010922  mov     ecx, 1; PoolType
0x140010927  mov     [rsp+78h+var_48.MaximumLength], ax
0x14001092c  call    cs:__imp_ExAllocatePoolWithTag
0x140010933  nop     dword ptr [rax+rax+00h]
0x140010938  xor     edi, edi
0x14001093a  mov     [rsp+78h+var_48.Buffer], rax
0x14001093f  test    rax, rax
0x140010942  jz      short loc_1400109BE
0x140010944  mov     r8, rsi; Size
0x140010947  xor     edx, edx; Val
0x140010949  mov     rcx, rax; void *
0x14001094c  call    memset
0x140010951  movzx   r8d, word ptr [rbx]; Size
0x140010955  mov     rdx, [rbx+8]; Src
0x140010959  mov     rcx, [rsp+78h+var_48.Buffer]; void *
0x14001095e  mov     [rsp+78h+var_48.Length], r8w
0x140010964  call    memmove
0x140010969  mov     rax, [rsp+78h+var_48.Buffer]
0x14001096e  lea     r9d, [rdi+1]; Type
0x140010972  movzx   ecx, [rsp+78h+var_48.Length]
0x140010977  xor     r8d, r8d; TitleIndex
0x14001097a  shr     rcx, 1
0x14001097d  mov     rdx, rbp; ValueName
0x140010980  mov     [rax+rcx*2], di
0x140010984  mov     rcx, r14; KeyHandle
0x140010987  movzx   eax, [rsp+78h+var_48.Length]
0x14001098c  add     eax, r15d
0x14001098f  mov     [rsp+78h+DataSize], eax; DataSize
0x140010993  mov     rax, [rsp+78h+var_48.Buffer]
0x140010998  mov     [rsp+78h+Data], rax; Data
0x14001099d  call    cs:__imp_ZwSetValueKey
0x1400109a4  nop     dword ptr [rax+rax+00h]
0x1400109a9  lea     rcx, [rsp+78h+var_48]; UnicodeString
0x1400109ae  mov     ebx, eax
0x1400109b0  call    cs:__imp_RtlFreeUnicodeString
0x1400109b7  nop     dword ptr [rax+rax+00h]
0x1400109bc  jmp     short loc_1400109C3
0x1400109be  mov     ebx, 0C000009Ah
0x1400109c3  mov     eax, ebx
0x1400109c5  add     rsp, 48h
0x1400109c9  pop     r15
0x1400109cb  pop     r14
0x1400109cd  pop     rdi
0x1400109ce  pop     rsi
0x1400109cf  pop     rbp
0x1400109d0  pop     rbx
0x1400109d1  retn
```
