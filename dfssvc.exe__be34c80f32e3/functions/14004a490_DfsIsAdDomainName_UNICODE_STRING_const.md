# DfsIsAdDomainName(_UNICODE_STRING const *)

- ea: `0x14004a490`
- end: `0x14004a533`
- name: `?DfsIsAdDomainName@@YAHPEBU_UNICODE_STRING@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003910`
- `0x140005030`
- `0x140011378`
- `0x140012224`
- `0x14001bc08`
- `0x14001be88`
- `0x14001c664`
- `0x14001cafc`
- `0x14001cbd8`
- `0x1400591e4`

## callees

- `0x14004a490`
- `0x14004ac38`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x14004a4d6`
- `ntdll!RtlCompareUnicodeString` at `0x14004a50d`
- `ntdll!RtlCompareUnicodeString` at `0x14004a4d6`
- `ntdll!RtlCompareUnicodeString` at `0x14004a50d`
- `ntdll!RtlInitUnicodeStringEx` at `0x14004a4bc`
- `ntdll!RtlInitUnicodeStringEx` at `0x14004a4f6`
- `ntdll!RtlInitUnicodeStringEx` at `0x14004a4bc`
- `ntdll!RtlInitUnicodeStringEx` at `0x14004a4f6`

## pseudocode

```c
__int64 __fastcall DfsIsAdDomainName(PCUNICODE_STRING String2)
{
  struct CLocalMachine *Instance; // rax
  unsigned int v3; // ebx
  struct CLocalMachine *v4; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  Instance = CLocalMachine::_GetInstance(0);
  RtlInitUnicodeStringEx(&DestinationString, *((PCWSTR *)Instance + 7));
  v3 = 1;
  if ( RtlCompareUnicodeString(&DestinationString, String2, 1u) )
  {
    v4 = CLocalMachine::_GetInstance(0);
    RtlInitUnicodeStringEx(&DestinationString, *((PCWSTR *)v4 + 6));
    return RtlCompareUnicodeString(&DestinationString, String2, 1u) == 0;
  }
  return v3;
}

```

## disassembly

```asm
0x14004a490  mov     [rsp+arg_0], rbx
0x14004a495  mov     [rsp+arg_8], rsi
0x14004a49a  push    rdi
0x14004a49b  sub     rsp, 30h
0x14004a49f  mov     rsi, rcx
0x14004a4a2  xorps   xmm0, xmm0
0x14004a4a5  xor     ecx, ecx; unsigned int *
0x14004a4a7  xor     edi, edi
0x14004a4a9  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14004a4ae  call    ?_GetInstance@CLocalMachine@@SAPEAV1@PEAK@Z; CLocalMachine::_GetInstance(ulong *)
0x14004a4b3  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14004a4b8  mov     rdx, [rax+38h]; SourceString
0x14004a4bc  call    cs:__imp_RtlInitUnicodeStringEx
0x14004a4c3  nop     dword ptr [rax+rax+00h]
0x14004a4c8  lea     ebx, [rdi+1]
0x14004a4cb  mov     rdx, rsi; String2
0x14004a4ce  mov     r8b, bl; CaseInsensitive
0x14004a4d1  lea     rcx, [rsp+38h+DestinationString]; String1
0x14004a4d6  call    cs:__imp_RtlCompareUnicodeString
0x14004a4dd  nop     dword ptr [rax+rax+00h]
0x14004a4e2  test    eax, eax
0x14004a4e4  jz      short loc_14004A520
0x14004a4e6  xor     ecx, ecx; unsigned int *
0x14004a4e8  call    ?_GetInstance@CLocalMachine@@SAPEAV1@PEAK@Z; CLocalMachine::_GetInstance(ulong *)
0x14004a4ed  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14004a4f2  mov     rdx, [rax+30h]; SourceString
0x14004a4f6  call    cs:__imp_RtlInitUnicodeStringEx
0x14004a4fd  nop     dword ptr [rax+rax+00h]
0x14004a502  mov     r8b, bl; CaseInsensitive
0x14004a505  lea     rcx, [rsp+38h+DestinationString]; String1
0x14004a50a  mov     rdx, rsi; String2
0x14004a50d  call    cs:__imp_RtlCompareUnicodeString
0x14004a514  nop     dword ptr [rax+rax+00h]
0x14004a519  test    eax, eax
0x14004a51b  cmovz   edi, ebx
0x14004a51e  mov     ebx, edi
0x14004a520  mov     rsi, [rsp+38h+arg_8]
0x14004a525  mov     eax, ebx
0x14004a527  mov     rbx, [rsp+38h+arg_0]
0x14004a52c  add     rsp, 30h
0x14004a530  pop     rdi
0x14004a531  retn
```
