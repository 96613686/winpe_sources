# _IsImagePath

- ea: `0x180049628`
- end: `0x18004969d`
- name: `_IsImagePath`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003be4c`

## callees

- `0x180049628`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x18004967e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18004967e`

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
0x180049628  sub     rsp, 38h
0x18004962c  mov     dword ptr [rsp+38h+String1+4], 0
0x180049634  test    rcx, rcx
0x180049637  jz      short loc_180049695
0x180049639  movzx   r9d, word ptr [rdx]
0x18004963d  movzx   r10d, word ptr [rcx]
0x180049641  cmp     r10w, r9w
0x180049645  jb      short loc_180049695
0x180049647  mov     rax, [rcx+8]
0x18004964b  mov     r8d, r10d
0x18004964e  sub     r8, r9
0x180049651  mov     [rsp+38h+String1.Length], r9w
0x180049657  shr     r8, 1
0x18004965a  mov     [rsp+38h+String1.MaximumLength], r9w
0x180049660  lea     rcx, [rax+r8*2]
0x180049664  mov     [rsp+38h+String1.Buffer], rcx
0x180049669  cmp     r10w, r9w
0x18004966d  jbe     short loc_180049676
0x18004966f  cmp     word ptr [rcx-2], 5Ch ; '\'
0x180049674  jnz     short loc_180049695
0x180049676  mov     r8b, 1; CaseInSensitive
0x180049679  lea     rcx, [rsp+38h+String1]; String1
0x18004967e  call    cs:__imp_RtlCompareUnicodeString
0x180049685  nop     dword ptr [rax+rax+00h]
0x18004968a  xor     ecx, ecx
0x18004968c  test    eax, eax
0x18004968e  setz    cl
0x180049691  mov     eax, ecx
0x180049693  jmp     short loc_180049697
0x180049695  xor     eax, eax
0x180049697  add     rsp, 38h
0x18004969b  retn
```
