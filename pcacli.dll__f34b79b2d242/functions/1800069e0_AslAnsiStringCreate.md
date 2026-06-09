# AslAnsiStringCreate

- ea: `0x1800069e0`
- end: `0x180006a80`
- name: `AslAnsiStringCreate`
- size: `160`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800050e0`

## callees

- `0x1800069e0`
- `0x180006a90`
- `0x180007738`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x180006a4e`
- `ntdll!RtlInitAnsiString` at `0x180006a4e`
- `ntdll!RtlFreeHeap` at `0x180006a6d`
- `ntdll!RtlFreeHeap` at `0x180006a6d`

## string_xrefs

- `0x180006a29`: `AslAnsiStringCreate`

## pseudocode

```c
__int64 __fastcall AslAnsiStringCreate(PANSI_STRING DestinationString)
{
  int v2; // eax
  unsigned int v3; // ebx
  char *v4; // r8
  PCSZ SourceString; // [rsp+48h] [rbp+10h] BYREF

  SourceString = 0;
  *DestinationString = 0;
  v2 = AslStringDuplicateA(&SourceString);
  v3 = v2;
  if ( v2 >= 0 )
  {
    RtlInitAnsiString(DestinationString, SourceString);
    v4 = 0;
    v3 = 0;
  }
  else
  {
    AslLogCallPrintf(
      1,
      "AslAnsiStringCreate",
      1039,
      "AslStringDuplicate failed with \"%s\" [%x]",
      (const char *)&dword_18000F424,
      v2);
    v4 = (char *)SourceString;
  }
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return v3;
}

```

## disassembly

```asm
0x1800069e0  mov     [rsp+arg_0], rbx
0x1800069e5  mov     [rsp+SourceString], rdx
0x1800069ea  push    rdi
0x1800069eb  sub     rsp, 30h
0x1800069ef  xorps   xmm0, xmm0
0x1800069f2  mov     [rsp+38h+SourceString], 0
0x1800069fb  movups  xmmword ptr [rcx], xmm0
0x1800069fe  mov     rdi, rcx
0x180006a01  lea     rcx, [rsp+38h+SourceString]
0x180006a06  call    AslStringDuplicateA
0x180006a0b  mov     ebx, eax
0x180006a0d  test    eax, eax
0x180006a0f  jns     short loc_180006A46
0x180006a11  mov     [rsp+38h+var_10], eax
0x180006a15  lea     r9, aAslstringdupli; "AslStringDuplicate failed with \"%s\" ["...
0x180006a1c  lea     rax, dword_18000F424
0x180006a23  mov     r8d, 40Fh
0x180006a29  lea     rdx, aAslansistringc; "AslAnsiStringCreate"
0x180006a30  mov     [rsp+38h+var_18], rax
0x180006a35  mov     ecx, 1
0x180006a3a  call    AslLogCallPrintf
0x180006a3f  mov     r8, [rsp+38h+SourceString]
0x180006a44  jmp     short loc_180006A59
0x180006a46  mov     rdx, [rsp+38h+SourceString]; SourceString
0x180006a4b  mov     rcx, rdi; DestinationString
0x180006a4e  call    cs:__imp_RtlInitAnsiString
0x180006a54  xor     r8d, r8d; P
0x180006a57  xor     ebx, ebx
0x180006a59  test    r8, r8
0x180006a5c  jz      short loc_180006A73
0x180006a5e  mov     rcx, gs:60h
0x180006a67  xor     edx, edx; Flags
0x180006a69  mov     rcx, [rcx+30h]; HeapHandle
0x180006a6d  call    cs:__imp_RtlFreeHeap
0x180006a73  mov     eax, ebx
0x180006a75  mov     rbx, [rsp+38h+arg_0]
0x180006a7a  add     rsp, 30h
0x180006a7e  pop     rdi
0x180006a7f  retn
```
