# DfscPathPrefixMatch

- ea: `0x140002394`
- end: `0x1400023fc`
- name: `DfscPathPrefixMatch`
- size: `104`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140014d30`
- `0x14001520c`
- `0x140027b74`

## callees

- `0x140002394`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400023e0`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400023e0`

## pseudocode

```c
bool __fastcall DfscPathPrefixMatch(PCUNICODE_STRING String1, const UNICODE_STRING *a2)
{
  unsigned int Length; // eax
  unsigned __int16 v4; // r8
  PWSTR Buffer; // rax
  unsigned __int64 v6; // rcx
  WCHAR v7; // r8
  bool result; // al

  Length = String1->Length;
  result = Length >= 2
        && (v4 = a2->Length, a2->Length >= 2u)
        && (unsigned __int16)Length <= v4
        && ((_WORD)Length == v4
         || (Buffer = a2->Buffer, v6 = (unsigned __int64)String1->Length >> 1, v7 = Buffer[v6], v7 == 92)
         || v7 == 58
         || Buffer[v6 - 1] == 92)
        && RtlPrefixUnicodeString(String1, a2, 1u);
  return result;
}

```

## disassembly

```asm
0x140002394  sub     rsp, 28h
0x140002398  movzx   eax, word ptr [rcx]
0x14000239b  mov     r9, rcx
0x14000239e  cmp     eax, 2
0x1400023a1  jb      short loc_1400023F4
0x1400023a3  movzx   r8d, word ptr [rdx]
0x1400023a7  cmp     r8w, 2
0x1400023ac  jb      short loc_1400023F4
0x1400023ae  cmp     ax, r8w
0x1400023b2  ja      short loc_1400023F4
0x1400023b4  jz      short loc_1400023DA
0x1400023b6  mov     ecx, eax
0x1400023b8  mov     rax, [rdx+8]
0x1400023bc  shr     rcx, 1
0x1400023bf  movzx   r8d, word ptr [rax+rcx*2]
0x1400023c4  cmp     r8w, 5Ch ; '\'
0x1400023c9  jz      short loc_1400023DA
0x1400023cb  cmp     r8w, 3Ah ; ':'
0x1400023d0  jz      short loc_1400023DA
0x1400023d2  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400023d8  jnz     short loc_1400023F4
0x1400023da  mov     r8b, 1; CaseInSensitive
0x1400023dd  mov     rcx, r9; String1
0x1400023e0  call    cs:__imp_RtlPrefixUnicodeString
0x1400023e7  nop     dword ptr [rax+rax+00h]
0x1400023ec  test    al, al
0x1400023ee  jz      short loc_1400023F4
0x1400023f0  mov     al, 1
0x1400023f2  jmp     short loc_1400023F6
0x1400023f4  xor     al, al
0x1400023f6  add     rsp, 28h
0x1400023fa  retn
```
