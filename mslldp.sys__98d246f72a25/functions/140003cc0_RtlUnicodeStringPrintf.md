# RtlUnicodeStringPrintf

- ea: `0x140003cc0`
- end: `0x140003d6f`
- name: `RtlUnicodeStringPrintf`
- size: `175`
- prototype: `NTSTATUS(PUNICODE_STRING DestinationString, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140010ca0`
- `0x140012500`

## callees

- `0x140003cc0`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x140003d27`
- `ntoskrnl!_vsnwprintf` at `0x140003d27`

## pseudocode

```c
NTSTATUS RtlUnicodeStringPrintf(PUNICODE_STRING DestinationString, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  unsigned __int16 Length; // cx
  unsigned __int64 MaximumLength; // rax
  wchar_t *Buffer; // r10
  unsigned __int64 v6; // rdi
  int v7; // eax
  NTSTATUS v8; // ecx
  va_list Args; // [rsp+60h] [rbp+18h] BYREF

  va_start(Args, pszFormat);
  Length = DestinationString->Length;
  if ( (Length & 1) != 0 )
    return -1073741811;
  MaximumLength = DestinationString->MaximumLength;
  if ( (MaximumLength & 1) != 0 )
    return -1073741811;
  if ( Length > (unsigned __int16)MaximumLength )
    return -1073741811;
  if ( (_WORD)MaximumLength == 0xFFFF )
    return -1073741811;
  Buffer = DestinationString->Buffer;
  if ( !Buffer && (Length || (_WORD)MaximumLength) )
    return -1073741811;
  v6 = MaximumLength >> 1;
  v7 = _vsnwprintf(Buffer, MaximumLength >> 1, pszFormat, Args);
  if ( v7 >= 0 && v7 <= v6 )
  {
    v8 = 0;
  }
  else
  {
    LOWORD(v7) = v6;
    v8 = -2147483643;
  }
  DestinationString->Length = 2 * v7;
  return v8;
}

```

## disassembly

```asm
0x140003cc0  mov     [rsp+arg_8], rdx
0x140003cc5  mov     qword ptr [rsp+Args], r8
0x140003cca  mov     [rsp+arg_18], r9
0x140003ccf  push    rbx
0x140003cd0  sub     rsp, 40h
0x140003cd4  mov     rbx, rcx
0x140003cd7  movzx   ecx, word ptr [rcx]
0x140003cda  test    cl, 1
0x140003cdd  jnz     loc_140003D64
0x140003ce3  movzx   eax, word ptr [rbx+2]
0x140003ce7  test    al, 1
0x140003ce9  jnz     short loc_140003D64
0x140003ceb  cmp     cx, ax
0x140003cee  ja      short loc_140003D64
0x140003cf0  mov     r8d, 0FFFEh
0x140003cf6  cmp     ax, r8w
0x140003cfa  ja      short loc_140003D64
0x140003cfc  mov     r10, [rbx+8]
0x140003d00  test    r10, r10
0x140003d03  jz      short loc_140003D5A
0x140003d05  mov     [rsp+48h+var_10], rdi
0x140003d0a  lea     r9, [rsp+48h+Args]; Args
0x140003d0f  mov     rdi, rax
0x140003d12  mov     [rsp+48h+var_28], 0
0x140003d1b  mov     r8, rdx; Format
0x140003d1e  shr     rdi, 1
0x140003d21  mov     rdx, rdi; Count
0x140003d24  mov     rcx, r10; Dest
0x140003d27  call    cs:__imp__vsnwprintf
0x140003d2e  nop     dword ptr [rax+rax+00h]
0x140003d33  test    eax, eax
0x140003d35  js      short loc_140003D3E
0x140003d37  cdqe
0x140003d39  cmp     rax, rdi
0x140003d3c  jbe     short loc_140003D6B
0x140003d3e  mov     rax, rdi
0x140003d41  mov     ecx, 80000005h
0x140003d46  mov     rdi, [rsp+48h+var_10]
0x140003d4b  add     ax, ax
0x140003d4e  mov     [rbx], ax
0x140003d51  mov     eax, ecx
0x140003d53  add     rsp, 40h
0x140003d57  pop     rbx
0x140003d58  retn
0x140003d5a  test    cx, cx
0x140003d5d  jnz     short loc_140003D64
0x140003d5f  test    ax, ax
0x140003d62  jz      short loc_140003D05
0x140003d64  mov     eax, 0C000000Dh
0x140003d69  jmp     short loc_140003D53
0x140003d6b  xor     ecx, ecx
0x140003d6d  jmp     short loc_140003D46
```
