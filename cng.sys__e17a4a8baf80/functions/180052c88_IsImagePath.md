# _IsImagePath

- ea: `0x180052c88`
- end: `0x180052cfd`
- name: `_IsImagePath`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800453dc`

## callees

- `0x180052c88`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x180052cde`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180052cde`

## pseudocode

```c
_BOOL8 __fastcall IsImagePath(unsigned __int16 *a1, const UNICODE_STRING *a2)
{
  __int64 Length; // r9
  unsigned int v3; // r10d
  __int64 v4; // rax
  UNICODE_STRING String1; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  if ( a1
    && (Length = a2->Length, v3 = *a1, (unsigned __int16)v3 >= (unsigned __int16)Length)
    && ((v4 = *((_QWORD *)a1 + 1),
         String1.Length = a2->Length,
         String1.MaximumLength = Length,
         String1.Buffer = (PWSTR)(v4 + 2 * (((unsigned __int64)v3 - Length) >> 1)),
         (unsigned __int16)v3 <= (unsigned __int16)Length)
     || *(_WORD *)(v4 + 2 * (((unsigned __int64)v3 - Length) >> 1) - 2) == 92) )
  {
    return RtlCompareUnicodeString(&String1, a2, 1u) == 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180052c88  sub     rsp, 38h
0x180052c8c  mov     dword ptr [rsp+38h+String1+4], 0
0x180052c94  test    rcx, rcx
0x180052c97  jz      short loc_180052CF5
0x180052c99  movzx   r9d, word ptr [rdx]
0x180052c9d  movzx   r10d, word ptr [rcx]
0x180052ca1  cmp     r10w, r9w
0x180052ca5  jb      short loc_180052CF5
0x180052ca7  mov     rax, [rcx+8]
0x180052cab  mov     r8d, r10d
0x180052cae  sub     r8, r9
0x180052cb1  mov     [rsp+38h+String1.Length], r9w
0x180052cb7  shr     r8, 1
0x180052cba  mov     [rsp+38h+String1.MaximumLength], r9w
0x180052cc0  lea     rcx, [rax+r8*2]
0x180052cc4  mov     [rsp+38h+String1.Buffer], rcx
0x180052cc9  cmp     r10w, r9w
0x180052ccd  jbe     short loc_180052CD6
0x180052ccf  cmp     word ptr [rcx-2], 5Ch ; '\'
0x180052cd4  jnz     short loc_180052CF5
0x180052cd6  mov     r8b, 1; CaseInSensitive
0x180052cd9  lea     rcx, [rsp+38h+String1]; String1
0x180052cde  call    cs:__imp_RtlCompareUnicodeString
0x180052ce5  nop     dword ptr [rax+rax+00h]
0x180052cea  xor     ecx, ecx
0x180052cec  test    eax, eax
0x180052cee  setz    cl
0x180052cf1  mov     eax, ecx
0x180052cf3  jmp     short loc_180052CF7
0x180052cf5  xor     eax, eax
0x180052cf7  add     rsp, 38h
0x180052cfb  retn
```
