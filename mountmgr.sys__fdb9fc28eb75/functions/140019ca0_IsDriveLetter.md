# IsDriveLetter

- ea: `0x140019ca0`
- end: `0x140019cf7`
- name: `IsDriveLetter`
- size: `87`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b3e0`
- `0x14000bbe4`
- `0x14000be4c`
- `0x14000c2d4`
- `0x14000c528`
- `0x140014fc0`
- `0x140018450`
- `0x140018560`
- `0x140019af0`

## callees

- `0x140019ca0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140019cdc`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140019cdc`

## pseudocode

```c
bool __fastcall IsDriveLetter(PCUNICODE_STRING String2)
{
  PWSTR Buffer; // rdx
  WCHAR v2; // r8
  bool result; // al

  result = String2->Length == 28
        && ((Buffer = String2->Buffer, v2 = Buffer[12], (unsigned __int16)(v2 - 65) <= 0x19u) || v2 == 255)
        && Buffer[13] == 58
        && RtlPrefixUnicodeString(&::String2, String2, 1u) != 0;
  return result;
}

```

## disassembly

```asm
0x140019ca0  sub     rsp, 28h
0x140019ca4  cmp     word ptr [rcx], 1Ch
0x140019ca8  jnz     short loc_140019CEF
0x140019caa  mov     rdx, [rcx+8]
0x140019cae  movzx   r8d, word ptr [rdx+18h]
0x140019cb3  lea     eax, [r8-41h]
0x140019cb7  cmp     ax, 19h
0x140019cbb  jbe     short loc_140019CC8
0x140019cbd  mov     eax, 0FFh
0x140019cc2  cmp     r8w, ax
0x140019cc6  jnz     short loc_140019CEF
0x140019cc8  cmp     word ptr [rdx+1Ah], 3Ah ; ':'
0x140019ccd  jnz     short loc_140019CEF
0x140019ccf  mov     rdx, rcx; String2
0x140019cd2  mov     r8b, 1; CaseInSensitive
0x140019cd5  lea     rcx, String2; String1
0x140019cdc  call    cs:__imp_RtlPrefixUnicodeString
0x140019ce3  nop     dword ptr [rax+rax+00h]
0x140019ce8  test    al, al
0x140019cea  setnz   al
0x140019ced  jmp     short loc_140019CF1
0x140019cef  xor     al, al
0x140019cf1  add     rsp, 28h
0x140019cf5  retn
```
