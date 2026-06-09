# SString::GetCompatibleString(SString const &,SString &)

- ea: `0x14000c458`
- end: `0x14000c519`
- name: `?GetCompatibleString@SString@@AEBAAEBV1@AEBV1@AEAV1@@Z`
- size: `193`
- prototype: `const struct SString *__fastcall(SString *__hidden this, const struct SString *, struct SString *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140001374`

## callees

- `0x14000b010`
- `0x14000b268`
- `0x14000b37c`
- `0x14000c39c`
- `0x14000c458`
- `0x14000c51c`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x14000c4d3`
- `KERNEL32!DebugBreak` at `0x14000c4d3`

## pseudocode

```c
const struct SString *__fastcall SString::GetCompatibleString(
        SString *this,
        const struct SString *a2,
        struct SString *a3)
{
  int v3; // eax

  v3 = *((_DWORD *)this + 2);
  if ( (v3 & 2) != 0 && ((v3 & 7) != 7 || SString::s_IsANSIMultibyte) && !(unsigned int)SString::ScanASCII(this) )
    SString::ConvertToUnicode(this);
  switch ( *((_DWORD *)this + 2) & 7 )
  {
    case 0:
      return a2;
    case 1:
      if ( (unsigned int)SString::IsRepresentation(a2, 1) )
        return a2;
      SString::ConvertToUnicode(this);
      break;
    case 3:
      goto LABEL_14;
    case 4:
      break;
    case 7:
      if ( !(unsigned int)SString::IsRepresentation(a2, 7) )
      {
        SString::ConvertToANSI(a2, a3);
        return a3;
      }
      return a2;
    default:
LABEL_14:
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
0x14000c458  mov     [rsp+arg_0], rbx
0x14000c45d  mov     [rsp+arg_8], rsi
0x14000c462  push    rdi
0x14000c463  sub     rsp, 20h
0x14000c467  mov     eax, [rcx+8]
0x14000c46a  mov     rdi, r8
0x14000c46d  mov     rbx, rdx
0x14000c470  mov     rsi, rcx
0x14000c473  test    al, 2
0x14000c475  jz      short loc_14000C498
0x14000c477  and     eax, 7
0x14000c47a  cmp     al, 7
0x14000c47c  jnz     short loc_14000C487
0x14000c47e  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, 0; int SString::s_IsANSIMultibyte
0x14000c485  jz      short loc_14000C498
0x14000c487  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x14000c48c  test    eax, eax
0x14000c48e  jnz     short loc_14000C498
0x14000c490  mov     rcx, rsi; this
0x14000c493  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x14000c498  mov     ecx, [rsi+8]
0x14000c49b  and     ecx, 7
0x14000c49e  jz      short loc_14000C506
0x14000c4a0  sub     ecx, 1
0x14000c4a3  jz      short loc_14000C4DA
0x14000c4a5  sub     ecx, 2
0x14000c4a8  jz      short loc_14000C4D3
0x14000c4aa  sub     ecx, 1
0x14000c4ad  jz      short loc_14000C4F3
0x14000c4af  cmp     ecx, 3
0x14000c4b2  jnz     short loc_14000C4D3
0x14000c4b4  lea     edx, [rcx+4]
0x14000c4b7  mov     rcx, rbx
0x14000c4ba  call    ?IsRepresentation@SString@@AEBAHW4Representation@1@@Z; SString::IsRepresentation(SString::Representation)
0x14000c4bf  test    eax, eax
0x14000c4c1  jnz     short loc_14000C506
0x14000c4c3  mov     rdx, rdi; struct SString *
0x14000c4c6  mov     rcx, rbx; this
0x14000c4c9  call    ?ConvertToANSI@SString@@QEBAXAEAV1@@Z; SString::ConvertToANSI(SString &)
0x14000c4ce  mov     rax, rdi
0x14000c4d1  jmp     short loc_14000C509
0x14000c4d3  call    cs:__imp_DebugBreak
0x14000c4d9  int     3; Trap to Debugger
0x14000c4da  mov     edx, 1
0x14000c4df  mov     rcx, rbx
0x14000c4e2  call    ?IsRepresentation@SString@@AEBAHW4Representation@1@@Z; SString::IsRepresentation(SString::Representation)
0x14000c4e7  test    eax, eax
0x14000c4e9  jnz     short loc_14000C506
0x14000c4eb  mov     rcx, rsi; this
0x14000c4ee  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x14000c4f3  test    byte ptr [rbx+8], 3
0x14000c4f7  jz      short loc_14000C506
0x14000c4f9  mov     rdx, rdi; struct SString *
0x14000c4fc  mov     rcx, rbx; this
0x14000c4ff  call    ?ConvertToUnicode@SString@@QEBAXAEAV1@@Z; SString::ConvertToUnicode(SString &)
0x14000c504  jmp     short loc_14000C4CE
0x14000c506  mov     rax, rbx
0x14000c509  mov     rbx, [rsp+28h+arg_0]
0x14000c50e  mov     rsi, [rsp+28h+arg_8]
0x14000c513  add     rsp, 20h
0x14000c517  pop     rdi
0x14000c518  retn
```
