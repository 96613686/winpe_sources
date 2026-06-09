# _IsImagePath

- ea: `0x180048b98`
- end: `0x180048c0d`
- name: `_IsImagePath`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003b34c`

## callees

- `0x180048b98`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x180048bee`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180048bee`

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
0x180048b98  sub     rsp, 38h
0x180048b9c  mov     dword ptr [rsp+38h+String1+4], 0
0x180048ba4  test    rcx, rcx
0x180048ba7  jz      short loc_180048C05
0x180048ba9  movzx   r9d, word ptr [rdx]
0x180048bad  movzx   r10d, word ptr [rcx]
0x180048bb1  cmp     r10w, r9w
0x180048bb5  jb      short loc_180048C05
0x180048bb7  mov     rax, [rcx+8]
0x180048bbb  mov     r8d, r10d
0x180048bbe  sub     r8, r9
0x180048bc1  mov     [rsp+38h+String1.Length], r9w
0x180048bc7  shr     r8, 1
0x180048bca  mov     [rsp+38h+String1.MaximumLength], r9w
0x180048bd0  lea     rcx, [rax+r8*2]
0x180048bd4  mov     [rsp+38h+String1.Buffer], rcx
0x180048bd9  cmp     r10w, r9w
0x180048bdd  jbe     short loc_180048BE6
0x180048bdf  cmp     word ptr [rcx-2], 5Ch ; '\'
0x180048be4  jnz     short loc_180048C05
0x180048be6  mov     r8b, 1; CaseInSensitive
0x180048be9  lea     rcx, [rsp+38h+String1]; String1
0x180048bee  call    cs:__imp_RtlCompareUnicodeString
0x180048bf5  nop     dword ptr [rax+rax+00h]
0x180048bfa  xor     ecx, ecx
0x180048bfc  test    eax, eax
0x180048bfe  setz    cl
0x180048c01  mov     eax, ecx
0x180048c03  jmp     short loc_180048C07
0x180048c05  xor     eax, eax
0x180048c07  add     rsp, 38h
0x180048c0b  retn
```
