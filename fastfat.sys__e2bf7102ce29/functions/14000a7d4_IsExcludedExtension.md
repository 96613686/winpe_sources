# IsExcludedExtension

- ea: `0x14000a7d4`
- end: `0x14000a867`
- name: `IsExcludedExtension`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14005323c`

## callees

- `0x14000a7d4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a82c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a82c`

## pseudocode

```c
char __fastcall IsExcludedExtension(WCHAR *a1, __int16 a2)
{
  int v2; // edi
  int v3; // ebx
  __int64 v4; // rsi
  LONG v5; // ecx
  int v6; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-18h] BYREF

  v2 = 0;
  *(&String2.MaximumLength + 2) = 0;
  String2.Length = 2 * a2;
  v3 = dword_140017A18 - 1;
  *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * a2);
  String2.Buffer = a1;
  while ( v3 >= v2 )
  {
    v4 = (v3 + v2) / 2;
    v5 = RtlCompareUnicodeString((PCUNICODE_STRING)(qword_140017A10 + 16 * v4), &String2, 1u);
    if ( !v5 )
      return 1;
    v6 = v4 + 1;
    if ( v5 >= 0 )
      v6 = v2;
    v2 = v6;
    if ( v5 >= 0 )
      v3 = v4 - 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14000a7d4  mov     rax, rsp
0x14000a7d7  mov     [rax+8], rbx
0x14000a7db  mov     [rax+10h], rsi
0x14000a7df  push    rdi
0x14000a7e0  sub     rsp, 30h
0x14000a7e4  mov     ebx, cs:dword_140017A18
0x14000a7ea  add     dx, dx
0x14000a7ed  xorps   xmm0, xmm0
0x14000a7f0  xor     edi, edi
0x14000a7f2  movups  xmmword ptr [rax-18h], xmm0
0x14000a7f6  mov     [rax-18h], dx
0x14000a7fa  dec     ebx
0x14000a7fc  mov     [rax-16h], dx
0x14000a800  mov     [rax-10h], rcx
0x14000a804  cmp     ebx, edi
0x14000a806  jl      short loc_14000A854
0x14000a808  lea     eax, [rbx+rdi]
0x14000a80b  mov     ecx, 2
0x14000a810  cdq
0x14000a811  mov     r8b, 1; CaseInSensitive
0x14000a814  idiv    ecx
0x14000a816  lea     rdx, [rsp+38h+String2]; String2
0x14000a81b  movsxd  rsi, eax
0x14000a81e  mov     rcx, rsi
0x14000a821  shl     rcx, 4
0x14000a825  add     rcx, cs:qword_140017A10; String1
0x14000a82c  call    cs:__imp_RtlCompareUnicodeString
0x14000a833  nop     dword ptr [rax+rax+00h]
0x14000a838  mov     ecx, eax
0x14000a83a  test    eax, eax
0x14000a83c  jz      short loc_14000A850
0x14000a83e  test    ecx, ecx
0x14000a840  lea     eax, [rsi+1]
0x14000a843  cmovns  eax, edi
0x14000a846  mov     edi, eax
0x14000a848  lea     eax, [rsi-1]
0x14000a84b  cmovns  ebx, eax
0x14000a84e  jmp     short loc_14000A804
0x14000a850  mov     al, 1
0x14000a852  jmp     short loc_14000A856
0x14000a854  xor     al, al
0x14000a856  mov     rbx, [rsp+38h+arg_0]
0x14000a85b  mov     rsi, [rsp+38h+arg_8]
0x14000a860  add     rsp, 30h
0x14000a864  pop     rdi
0x14000a865  retn
```
