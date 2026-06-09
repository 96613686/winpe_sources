# CmRegUtilUcValueSetUcString

- ea: `0x140012608`
- end: `0x14001273b`
- name: `CmRegUtilUcValueSetUcString`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PUNICODE_STRING ValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140011f14`
- `0x1400127ec`

## callees

- `0x140003a80`
- `0x140003d80`
- `0x140012608`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x140012666`
- `ntoskrnl!ZwSetValueKey` at `0x140012705`
- `ntoskrnl!ZwSetValueKey` at `0x140012666`
- `ntoskrnl!ZwSetValueKey` at `0x140012705`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140012694`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140012694`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012718`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140012718`

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
0x140012608  push    rbx
0x14001260a  push    rbp
0x14001260b  push    rsi
0x14001260c  push    rdi
0x14001260d  push    r14
0x14001260f  push    r15
0x140012611  sub     rsp, 48h
0x140012615  movzx   r9d, word ptr [r8]
0x140012619  mov     r15d, 2
0x14001261f  movzx   eax, word ptr [r8+2]
0x140012624  xorps   xmm0, xmm0
0x140012627  sub     rax, r9
0x14001262a  mov     rbx, r8
0x14001262d  mov     rbp, rdx
0x140012630  mov     r14, rcx
0x140012633  movups  xmmword ptr [rsp+78h+var_48.Length], xmm0
0x140012638  cmp     rax, r15
0x14001263b  jb      short loc_140012679
0x14001263d  mov     rax, [r8+8]
0x140012641  xor     edi, edi
0x140012643  shr     r9, 1
0x140012646  mov     [rax+r9*2], di
0x14001264b  lea     r9d, [r15-1]; Type
0x14001264f  movzx   eax, word ptr [r8]
0x140012653  add     eax, r15d
0x140012656  mov     [rsp+78h+DataSize], eax; DataSize
0x14001265a  mov     rax, [r8+8]
0x14001265e  xor     r8d, r8d; TitleIndex
0x140012661  mov     [rsp+78h+Data], rax; Data
0x140012666  call    cs:__imp_ZwSetValueKey
0x14001266d  nop     dword ptr [rax+rax+00h]
0x140012672  mov     ebx, eax
0x140012674  jmp     loc_14001272B
0x140012679  lea     rsi, [r9+2]
0x14001267d  mov     r8d, 63557050h; Tag
0x140012683  lea     eax, [r15+r9]
0x140012687  mov     rdx, rsi; NumberOfBytes
0x14001268a  mov     ecx, 1; PoolType
0x14001268f  mov     [rsp+78h+var_48.MaximumLength], ax
0x140012694  call    cs:__imp_ExAllocatePoolWithTag
0x14001269b  nop     dword ptr [rax+rax+00h]
0x1400126a0  xor     edi, edi
0x1400126a2  mov     [rsp+78h+var_48.Buffer], rax
0x1400126a7  test    rax, rax
0x1400126aa  jz      short loc_140012726
0x1400126ac  mov     r8, rsi; Size
0x1400126af  xor     edx, edx; Val
0x1400126b1  mov     rcx, rax; void *
0x1400126b4  call    memset
0x1400126b9  movzx   r8d, word ptr [rbx]; Size
0x1400126bd  mov     rdx, [rbx+8]; Src
0x1400126c1  mov     rcx, [rsp+78h+var_48.Buffer]; void *
0x1400126c6  mov     [rsp+78h+var_48.Length], r8w
0x1400126cc  call    memmove
0x1400126d1  mov     rax, [rsp+78h+var_48.Buffer]
0x1400126d6  lea     r9d, [rdi+1]; Type
0x1400126da  movzx   ecx, [rsp+78h+var_48.Length]
0x1400126df  xor     r8d, r8d; TitleIndex
0x1400126e2  shr     rcx, 1
0x1400126e5  mov     rdx, rbp; ValueName
0x1400126e8  mov     [rax+rcx*2], di
0x1400126ec  mov     rcx, r14; KeyHandle
0x1400126ef  movzx   eax, [rsp+78h+var_48.Length]
0x1400126f4  add     eax, r15d
0x1400126f7  mov     [rsp+78h+DataSize], eax; DataSize
0x1400126fb  mov     rax, [rsp+78h+var_48.Buffer]
0x140012700  mov     [rsp+78h+Data], rax; Data
0x140012705  call    cs:__imp_ZwSetValueKey
0x14001270c  nop     dword ptr [rax+rax+00h]
0x140012711  lea     rcx, [rsp+78h+var_48]; UnicodeString
0x140012716  mov     ebx, eax
0x140012718  call    cs:__imp_RtlFreeUnicodeString
0x14001271f  nop     dword ptr [rax+rax+00h]
0x140012724  jmp     short loc_14001272B
0x140012726  mov     ebx, 0C000009Ah
0x14001272b  mov     eax, ebx
0x14001272d  add     rsp, 48h
0x140012731  pop     r15
0x140012733  pop     r14
0x140012735  pop     rdi
0x140012736  pop     rsi
0x140012737  pop     rbp
0x140012738  pop     rbx
0x140012739  retn
```
