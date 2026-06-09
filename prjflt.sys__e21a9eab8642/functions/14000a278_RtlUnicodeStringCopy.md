# RtlUnicodeStringCopy

- ea: `0x14000a278`
- end: `0x14000a36e`
- name: `RtlUnicodeStringCopy`
- size: `246`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140040670`

## callees

- `0x14000a278`

## pseudocode

```c
NTSTATUS __stdcall RtlUnicodeStringCopy(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString)
{
  USHORT Length; // r8
  unsigned __int64 MaximumLength; // rax
  PWSTR Buffer; // rbx
  unsigned __int64 v7; // rdx
  USHORT v8; // cx
  PWSTR v9; // r11
  unsigned __int64 v10; // r8
  NTSTATUS v11; // ecx
  unsigned __int64 v12; // r10
  __int16 v13; // dx

  Length = DestinationString->Length;
  if ( (DestinationString->Length & 1) != 0 )
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
  v7 = SourceString->Length;
  if ( (v7 & 1) != 0
    || (v8 = SourceString->MaximumLength, (v8 & 1) != 0)
    || (unsigned __int16)v7 > v8
    || v8 == 0xFFFF
    || (v9 = SourceString->Buffer) == 0 && ((_WORD)v7 || v8) )
  {
    v13 = 0;
    v11 = -1073741811;
  }
  else
  {
    v10 = v7 >> 1;
    v11 = 0;
    v12 = MaximumLength >> 1;
    v13 = 0;
    if ( MaximumLength >> 1 )
    {
      while ( v10 )
      {
        --v10;
        *Buffer++ = *v9++;
        ++v13;
        if ( !--v12 )
          goto LABEL_18;
      }
    }
    else
    {
LABEL_18:
      if ( v10 )
        v11 = -2147483643;
    }
  }
  DestinationString->Length = 2 * v13;
  return v11;
}

```

## disassembly

```asm
0x14000a278  mov     [rsp+arg_0], rbx
0x14000a27d  mov     [rsp+arg_8], rdi
0x14000a282  movzx   r8d, word ptr [rcx]
0x14000a286  mov     r10, rdx
0x14000a289  mov     r9, rcx
0x14000a28c  test    r8b, 1
0x14000a290  jnz     loc_14000A35B
0x14000a296  movzx   eax, word ptr [rcx+2]
0x14000a29a  test    al, 1
0x14000a29c  jnz     loc_14000A35B
0x14000a2a2  cmp     r8w, ax
0x14000a2a6  ja      loc_14000A35B
0x14000a2ac  mov     r11d, 0FFFEh
0x14000a2b2  cmp     ax, r11w
0x14000a2b6  ja      loc_14000A35B
0x14000a2bc  mov     rbx, [rcx+8]
0x14000a2c0  xor     edi, edi
0x14000a2c2  test    rbx, rbx
0x14000a2c5  jnz     short loc_14000A2DA
0x14000a2c7  test    r8w, r8w
0x14000a2cb  jnz     loc_14000A35B
0x14000a2d1  test    ax, ax
0x14000a2d4  jnz     loc_14000A35B
0x14000a2da  movzx   edx, word ptr [rdx]
0x14000a2dd  test    dl, 1
0x14000a2e0  jnz     short loc_14000A34A
0x14000a2e2  movzx   ecx, word ptr [r10+2]
0x14000a2e7  test    cl, 1
0x14000a2ea  jnz     short loc_14000A34A
0x14000a2ec  cmp     dx, cx
0x14000a2ef  ja      short loc_14000A34A
0x14000a2f1  cmp     cx, r11w
0x14000a2f5  ja      short loc_14000A34A
0x14000a2f7  mov     r11, [r10+8]
0x14000a2fb  test    r11, r11
0x14000a2fe  jnz     short loc_14000A30A
0x14000a300  test    dx, dx
0x14000a303  jnz     short loc_14000A34A
0x14000a305  test    cx, cx
0x14000a308  jnz     short loc_14000A34A
0x14000a30a  mov     r8, rdx
0x14000a30d  mov     r10, rax
0x14000a310  shr     r8, 1
0x14000a313  mov     ecx, edi
0x14000a315  shr     r10, 1
0x14000a318  mov     rdx, rdi
0x14000a31b  jz      short loc_14000A33D
0x14000a31d  test    r8, r8
0x14000a320  jz      short loc_14000A352
0x14000a322  movzx   eax, word ptr [r11]
0x14000a326  dec     r8
0x14000a329  mov     [rbx], ax
0x14000a32c  add     r11, 2
0x14000a330  add     rbx, 2
0x14000a334  inc     rdx
0x14000a337  sub     r10, 1
0x14000a33b  jnz     short loc_14000A31D
0x14000a33d  test    r8, r8
0x14000a340  mov     eax, 80000005h
0x14000a345  cmovnz  ecx, eax
0x14000a348  jmp     short loc_14000A352
0x14000a34a  mov     rdx, rdi
0x14000a34d  mov     ecx, 0C000000Dh
0x14000a352  add     dx, dx
0x14000a355  mov     [r9], dx
0x14000a359  jmp     short loc_14000A360
0x14000a35b  mov     ecx, 0C000000Dh
0x14000a360  mov     rbx, [rsp+arg_0]
0x14000a365  mov     eax, ecx
0x14000a367  mov     rdi, [rsp+arg_8]
0x14000a36c  retn
```
