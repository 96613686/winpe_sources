# CdUpcaseName

- ea: `0x140016618`
- end: `0x1400166a6`
- name: `CdUpcaseName`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c8b4`
- `0x14000d898`
- `0x140012a14`
- `0x140016dc0`

## callees

- `0x140016618`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14001666d`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140016689`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14001666d`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140016689`

## pseudocode

```c
NTSTATUS __fastcall CdUpcaseName(__int64 a1, const UNICODE_STRING *a2, struct _UNICODE_STRING *a3)
{
  USHORT Length; // ax
  WCHAR *v6; // rdx
  NTSTATUS result; // eax

  if ( a2 != a3 )
  {
    a3[1].Length = 0;
    Length = a2[1].Length;
    if ( Length )
    {
      a3[1].Length = Length;
      a3[1].MaximumLength = Length;
      v6 = (PWSTR)((char *)a3->Buffer + a2->Length);
      a3[1].Buffer = v6;
      *v6 = 59;
      ++a3[1].Buffer;
    }
  }
  result = RtlUpcaseUnicodeString(a3, a2, 0);
  if ( a2[1].Length )
    return RtlUpcaseUnicodeString(a3 + 1, a2 + 1, 0);
  return result;
}

```

## disassembly

```asm
0x140016618  mov     [rsp+arg_0], rbx
0x14001661d  mov     [rsp+arg_8], rsi
0x140016622  push    rdi
0x140016623  sub     rsp, 20h
0x140016627  xor     esi, esi
0x140016629  mov     rbx, r8
0x14001662c  mov     rdi, rdx
0x14001662f  cmp     rdx, r8
0x140016632  jz      short loc_140016664
0x140016634  mov     [r8+10h], si
0x140016639  movzx   eax, word ptr [rdx+10h]
0x14001663d  test    ax, ax
0x140016640  jz      short loc_140016664
0x140016642  mov     [r8+10h], ax
0x140016647  mov     [r8+12h], ax
0x14001664c  movzx   ecx, word ptr [rdx]
0x14001664f  mov     rdx, [r8+8]
0x140016653  add     rdx, rcx
0x140016656  mov     [r8+18h], rdx
0x14001665a  mov     word ptr [rdx], 3Bh ; ';'
0x14001665f  add     qword ptr [r8+18h], 2
0x140016664  xor     r8d, r8d; AllocateDestinationString
0x140016667  mov     rdx, rdi; SourceString
0x14001666a  mov     rcx, rbx; DestinationString
0x14001666d  call    cs:__imp_RtlUpcaseUnicodeString
0x140016674  nop     dword ptr [rax+rax+00h]
0x140016679  lea     rdx, [rdi+10h]; SourceString
0x14001667d  cmp     [rdx], si
0x140016680  jz      short loc_140016695
0x140016682  lea     rcx, [rbx+10h]; DestinationString
0x140016686  xor     r8d, r8d; AllocateDestinationString
0x140016689  call    cs:__imp_RtlUpcaseUnicodeString
0x140016690  nop     dword ptr [rax+rax+00h]
0x140016695  mov     rbx, [rsp+28h+arg_0]
0x14001669a  mov     rsi, [rsp+28h+arg_8]
0x14001669f  add     rsp, 20h
0x1400166a3  pop     rdi
0x1400166a4  retn
```
