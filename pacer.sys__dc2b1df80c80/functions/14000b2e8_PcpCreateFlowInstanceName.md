# PcpCreateFlowInstanceName

- ea: `0x14000b2e8`
- end: `0x14000b3b0`
- name: `PcpCreateFlowInstanceName`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ab0`

## callees

- `0x14000b2e8`
- `0x140013110`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000b311`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b311`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000b333`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000b387`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000b333`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000b387`

## pseudocode

```c
__int64 __fastcall PcpCreateFlowInstanceName(__int64 a1)
{
  unsigned __int32 v2; // edx
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  WCHAR Source[12]; // [rsp+30h] [rbp-28h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, (PCWSTR)(a1 + 52));
  DestinationString.MaximumLength = 28;
  RtlAppendUnicodeToString(&DestinationString, L"Flow:");
  v2 = _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.Dpc.DpcData);
  LODWORD(v3) = 8;
  do
  {
    v4 = v2 & 0xF;
    v2 >>= 4;
    v3 = (unsigned int)(v3 - 1);
    Source[v3] = PcgHexChars[v4];
  }
  while ( (_DWORD)v3 );
  Source[8] = 0;
  RtlAppendUnicodeToString(&DestinationString, Source);
  result = DestinationString.Length;
  *(_WORD *)(a1 + 80) = DestinationString.Length;
  return result;
}

```

## disassembly

```asm
0x14000b2e8  push    rbx
0x14000b2ea  sub     rsp, 50h
0x14000b2ee  mov     rax, cs:__security_cookie
0x14000b2f5  xor     rax, rsp
0x14000b2f8  mov     [rsp+58h+var_10], rax
0x14000b2fd  mov     rbx, rcx
0x14000b300  lea     rdx, [rcx+34h]; SourceString
0x14000b304  xorps   xmm0, xmm0
0x14000b307  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14000b30c  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14000b311  call    cs:__imp_RtlInitUnicodeString
0x14000b318  nop     dword ptr [rax+rax+00h]
0x14000b31d  mov     eax, 1Ch
0x14000b322  lea     rdx, PcgFlowPrefix; "Flow:"
0x14000b329  lea     rcx, [rsp+58h+DestinationString]; Destination
0x14000b32e  mov     [rsp+58h+DestinationString.MaximumLength], ax
0x14000b333  call    cs:__imp_RtlAppendUnicodeToString
0x14000b33a  nop     dword ptr [rax+rax+00h]
0x14000b33f  mov     edx, 1
0x14000b344  lock xadd dword ptr cs:WPP_MAIN_CB.Dpc.DpcData, edx
0x14000b34c  inc     edx
0x14000b34e  mov     r8d, 8
0x14000b354  mov     eax, edx
0x14000b356  lea     r9, PcgHexChars; "0123456789ABCDEF"
0x14000b35d  and     eax, 0Fh
0x14000b360  shr     edx, 4
0x14000b363  dec     r8d
0x14000b366  movzx   eax, word ptr [r9+rax*2]
0x14000b36b  mov     [rsp+r8*2+58h+Source], ax
0x14000b371  test    r8d, r8d
0x14000b374  jnz     short loc_14000B354
0x14000b376  xor     eax, eax
0x14000b378  lea     rdx, [rsp+58h+Source]; Source
0x14000b37d  lea     rcx, [rsp+58h+DestinationString]; Destination
0x14000b382  mov     [rsp+58h+var_18], ax
0x14000b387  call    cs:__imp_RtlAppendUnicodeToString
0x14000b38e  nop     dword ptr [rax+rax+00h]
0x14000b393  movzx   eax, [rsp+58h+DestinationString.Length]
0x14000b398  mov     [rbx+50h], ax
0x14000b39c  mov     rcx, [rsp+58h+var_10]
0x14000b3a1  xor     rcx, rsp; StackCookie
0x14000b3a4  call    __security_check_cookie
0x14000b3a9  add     rsp, 50h
0x14000b3ad  pop     rbx
0x14000b3ae  retn
```
