# GmsapDuplicateWStr

- ea: `0x1800031b0`
- end: `0x1800031f9`
- name: `GmsapDuplicateWStr`
- size: `73`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003160`
- `0x18000461c`

## callees

- `0x1800031b0`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x1800031de`
- `ntdll!RtlDuplicateUnicodeString` at `0x1800031de`

## pseudocode

```c
NTSTATUS __fastcall GmsapDuplicateWStr(PCUNICODE_STRING SourceString, PWSTR *a2)
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  __int128 v5; // [rsp+30h] [rbp-18h]

  result = 0;
  *a2 = 0;
  if ( SourceString )
  {
    DestinationString = 0;
    v5 = 0;
    result = RtlDuplicateUnicodeString(3u, SourceString, &DestinationString);
    *a2 = DestinationString.Buffer;
  }
  return result;
}

```

## disassembly

```asm
0x1800031b0  push    rbx
0x1800031b2  sub     rsp, 40h
0x1800031b6  xor     eax, eax
0x1800031b8  mov     rbx, rdx
0x1800031bb  mov     [rdx], rax
0x1800031be  test    rcx, rcx
0x1800031c1  jz      short loc_1800031F2
0x1800031c3  xorps   xmm0, xmm0
0x1800031c6  lea     r8, [rsp+48h+DestinationString]; DestinationString
0x1800031cb  xorps   xmm1, xmm1
0x1800031ce  mov     rdx, rcx; SourceString
0x1800031d1  lea     ecx, [rax+3]; Flags
0x1800031d4  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800031d9  movups  [rsp+48h+var_18], xmm1
0x1800031de  call    cs:__imp_RtlDuplicateUnicodeString
0x1800031e5  nop     dword ptr [rax+rax+00h]
0x1800031ea  mov     rcx, [rsp+48h+DestinationString.Buffer]
0x1800031ef  mov     [rbx], rcx
0x1800031f2  add     rsp, 40h
0x1800031f6  pop     rbx
0x1800031f7  retn
```
