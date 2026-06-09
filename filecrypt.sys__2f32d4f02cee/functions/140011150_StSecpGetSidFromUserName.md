# StSecpGetSidFromUserName

- ea: `0x140011150`
- end: `0x1400111df`
- name: `StSecpGetSidFromUserName`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140010f90`

## callees

- `0x140001060`
- `0x140011150`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400111c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400111c1`
- `ntoskrnl!ExAllocatePool2` at `0x140011175`
- `ntoskrnl!ExAllocatePool2` at `0x140011175`

## pseudocode

```c
NTSTATUS __fastcall StSecpGetSidFromUserName(STRSAFE_PCNZWCH *a1, wchar_t **a2)
{
  unsigned __int64 v4; // rbx
  wchar_t *Pool2; // rdi
  size_t *v6; // r8
  size_t v7; // rbx
  NTSTATUS result; // eax
  int v9; // ebx

  v4 = *(unsigned __int16 *)a1 + 2LL;
  Pool2 = (wchar_t *)ExAllocatePool2(64, v4, 1850963027);
  if ( !Pool2 )
    return -1073741801;
  v7 = v4 >> 1;
  if ( v7 )
  {
    result = RtlStringCopyWorkerW(Pool2, v7, v6, a1[1], (unsigned __int64)*(unsigned __int16 *)a1 >> 1);
    v9 = result;
    if ( result >= 0 )
    {
      *a2 = Pool2;
      return result;
    }
  }
  else
  {
    v9 = -1073741811;
  }
  ExFreePoolWithTag(Pool2, 0);
  return v9;
}

```

## disassembly

```asm
0x140011150  push    rbx
0x140011152  push    rsi
0x140011153  push    rdi
0x140011154  push    r14
0x140011156  sub     rsp, 38h
0x14001115a  movzx   ebx, word ptr [rcx]
0x14001115d  mov     r14, rdx
0x140011160  mov     rsi, rcx
0x140011163  add     rbx, 2
0x140011167  mov     rdx, rbx
0x14001116a  mov     r8d, 6E537453h
0x140011170  mov     ecx, 40h ; '@'
0x140011175  call    cs:__imp_ExAllocatePool2
0x14001117c  nop     dword ptr [rax+rax+00h]
0x140011181  mov     rdi, rax
0x140011184  test    rax, rax
0x140011187  jz      short loc_1400111D1
0x140011189  shr     rbx, 1
0x14001118c  jz      short loc_1400111D8
0x14001118e  movzx   eax, word ptr [rsi]
0x140011191  mov     rdx, rbx; cchDest
0x140011194  mov     r9, [rsi+8]; pszSrc
0x140011198  mov     rcx, rdi; pszDest
0x14001119b  shr     rax, 1
0x14001119e  mov     [rsp+58h+cchToCopy], rax; cchToCopy
0x1400111a3  call    RtlStringCopyWorkerW
0x1400111a8  mov     ebx, eax
0x1400111aa  test    eax, eax
0x1400111ac  js      short loc_1400111BC
0x1400111ae  mov     [r14], rdi
0x1400111b1  add     rsp, 38h
0x1400111b5  pop     r14
0x1400111b7  pop     rdi
0x1400111b8  pop     rsi
0x1400111b9  pop     rbx
0x1400111ba  retn
0x1400111bc  xor     edx, edx; Tag
0x1400111be  mov     rcx, rdi; P
0x1400111c1  call    cs:__imp_ExFreePoolWithTag
0x1400111c8  nop     dword ptr [rax+rax+00h]
0x1400111cd  mov     eax, ebx
0x1400111cf  jmp     short loc_1400111B1
0x1400111d1  mov     eax, 0C0000017h
0x1400111d6  jmp     short loc_1400111B1
0x1400111d8  mov     ebx, 0C000000Dh
0x1400111dd  jmp     short loc_1400111BC
```
