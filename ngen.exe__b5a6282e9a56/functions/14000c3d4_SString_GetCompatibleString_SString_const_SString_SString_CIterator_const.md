# SString::GetCompatibleString(SString const &,SString &,SString::CIterator const &)

- ea: `0x14000c3d4`
- end: `0x14000c457`
- name: `?GetCompatibleString@SString@@AEBAAEBV1@AEBV1@AEAV1@AEBVCIterator@1@@Z`
- size: `131`
- prototype: `const struct SString *__fastcall(SString *this, const struct SString *, struct SString *, const struct SString::CIterator *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b578`
- `0x14000b898`

## callees

- `0x14000b124`
- `0x14000b268`
- `0x14000c39c`
- `0x14000c3d4`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x14000c40b`
- `KERNEL32!DebugBreak` at `0x14000c40b`

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
  if ( (*((_BYTE *)a2 + 8) & 3) != 0 )
  {
    SString::ConvertToUnicode(a2, a3);
    return a3;
  }
  return a2;
}

```

## disassembly

```asm
0x14000c3d4  mov     [rsp+arg_0], rbx
0x14000c3d9  mov     [rsp+arg_8], rsi
0x14000c3de  push    rdi
0x14000c3df  sub     rsp, 20h
0x14000c3e3  mov     r10d, [rcx+8]
0x14000c3e7  mov     rsi, r9
0x14000c3ea  mov     rdi, r8
0x14000c3ed  mov     rbx, rdx
0x14000c3f0  mov     r11, rcx
0x14000c3f3  and     r10d, 7
0x14000c3f7  jz      short loc_14000C444
0x14000c3f9  sub     r10d, 1
0x14000c3fd  jz      short loc_14000C412
0x14000c3ff  sub     r10d, 2
0x14000c403  jz      short loc_14000C40B
0x14000c405  cmp     r10d, 1
0x14000c409  jz      short loc_14000C42E
0x14000c40b  call    cs:__imp_DebugBreak
0x14000c411  int     3; Trap to Debugger
0x14000c412  mov     edx, 1
0x14000c417  mov     rcx, rbx
0x14000c41a  call    ?IsRepresentation@SString@@AEBAHW4Representation@1@@Z; SString::IsRepresentation(SString::Representation)
0x14000c41f  test    eax, eax
0x14000c421  jnz     short loc_14000C444
0x14000c423  mov     rdx, rsi; struct SString::CIterator *
0x14000c426  mov     rcx, r11; this
0x14000c429  call    ?ConvertToUnicode@SString@@AEBAXAEBVCIterator@1@@Z; SString::ConvertToUnicode(SString::CIterator const &)
0x14000c42e  test    byte ptr [rbx+8], 3
0x14000c432  jz      short loc_14000C444
0x14000c434  mov     rdx, rdi; struct SString *
0x14000c437  mov     rcx, rbx; this
0x14000c43a  call    ?ConvertToUnicode@SString@@QEBAXAEAV1@@Z; SString::ConvertToUnicode(SString &)
0x14000c43f  mov     rax, rdi
0x14000c442  jmp     short loc_14000C447
0x14000c444  mov     rax, rbx
0x14000c447  mov     rbx, [rsp+28h+arg_0]
0x14000c44c  mov     rsi, [rsp+28h+arg_8]
0x14000c451  add     rsp, 20h
0x14000c455  pop     rdi
0x14000c456  retn
```
