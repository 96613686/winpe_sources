# SString::GetCompatibleString(SString const &,SString &,SString::CIterator const &)

- ea: `0x18003a744`
- end: `0x18003a7d2`
- name: `?GetCompatibleString@SString@@AEBAAEBV1@AEBV1@AEAV1@AEBVCIterator@1@@Z`
- size: `142`
- prototype: `const struct SString *(SString *__hidden this, const struct SString *, struct SString *, const struct SString::CIterator *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003a260`
- `0x18003a880`

## callees

- `0x180039fcc`
- `0x18003a16c`
- `0x18003a744`
- `0x18003a7d8`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18003a77b`
- `KERNEL32!DebugBreak` at `0x18003a77b`

## pseudocode

```c
const struct SString *__fastcall SString::GetCompatibleString(
        SString *this,
        const struct SString *a2,
        struct SString *a3,
        const struct SString::CIterator *a4)
{
  SString *v7; // r11

  switch ( *((_DWORD *)this + 2) & 7 )
  {
    case 0:
      return a2;
    case 1:
      if ( (unsigned int)SString::IsRepresentation(a2, 1) )
        return a2;
      SString::ConvertToUnicode(v7, a4);
      break;
    case 4:
      break;
    default:
      DebugBreak();
      __debugbreak();
  }
  if ( !(unsigned int)SString::IsRepresentation(a2, 4) )
  {
    SString::ConvertToUnicode(a2, a3);
    return a3;
  }
  return a2;
}

```

## disassembly

```asm
0x18003a744  mov     [rsp+arg_0], rbx
0x18003a749  mov     [rsp+arg_8], rsi
0x18003a74e  push    rdi
0x18003a74f  sub     rsp, 20h
0x18003a753  mov     r10d, [rcx+8]
0x18003a757  mov     rsi, r9
0x18003a75a  mov     rdi, r8
0x18003a75d  mov     rbx, rdx
0x18003a760  mov     r11, rcx
0x18003a763  and     r10d, 7
0x18003a767  jz      short loc_18003A7BF
0x18003a769  sub     r10d, 1
0x18003a76d  jz      short loc_18003A782
0x18003a76f  sub     r10d, 2
0x18003a773  jz      short loc_18003A77B
0x18003a775  cmp     r10d, 1
0x18003a779  jz      short loc_18003A79E
0x18003a77b  call    cs:__imp_DebugBreak
0x18003a781  int     3; Trap to Debugger
0x18003a782  mov     edx, 1
0x18003a787  mov     rcx, rbx
0x18003a78a  call    ?IsRepresentation@SString@@AEBAHW4Representation@1@@Z; SString::IsRepresentation(SString::Representation)
0x18003a78f  test    eax, eax
0x18003a791  jnz     short loc_18003A7BF
0x18003a793  mov     rdx, rsi; struct SString::CIterator *
0x18003a796  mov     rcx, r11; this
0x18003a799  call    ?ConvertToUnicode@SString@@AEBAXAEBVCIterator@1@@Z; SString::ConvertToUnicode(SString::CIterator const &)
0x18003a79e  mov     edx, 4
0x18003a7a3  mov     rcx, rbx
0x18003a7a6  call    ?IsRepresentation@SString@@AEBAHW4Representation@1@@Z; SString::IsRepresentation(SString::Representation)
0x18003a7ab  test    eax, eax
0x18003a7ad  jnz     short loc_18003A7BF
0x18003a7af  mov     rdx, rdi; struct SString *
0x18003a7b2  mov     rcx, rbx; this
0x18003a7b5  call    ?ConvertToUnicode@SString@@QEBAXAEAV1@@Z; SString::ConvertToUnicode(SString &)
0x18003a7ba  mov     rax, rdi
0x18003a7bd  jmp     short loc_18003A7C2
0x18003a7bf  mov     rax, rbx
0x18003a7c2  mov     rbx, [rsp+28h+arg_0]
0x18003a7c7  mov     rsi, [rsp+28h+arg_8]
0x18003a7cc  add     rsp, 20h
0x18003a7d0  pop     rdi
0x18003a7d1  retn
```
