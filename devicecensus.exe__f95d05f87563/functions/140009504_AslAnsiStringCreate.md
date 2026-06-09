# AslAnsiStringCreate

- ea: `0x140009504`
- end: `0x1400095a3`
- name: `AslAnsiStringCreate`
- size: `159`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400060c0`

## callees

- `0x140007074`
- `0x140009504`
- `0x140009a10`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x140009571`
- `ntdll!RtlInitAnsiString` at `0x140009571`
- `ntdll!RtlFreeHeap` at `0x140009590`
- `ntdll!RtlFreeHeap` at `0x140009590`

## string_xrefs

- `0x14000954c`: `AslAnsiStringCreate`

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
      (const char *)&qword_1400157F8,
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
0x140009504  mov     rax, rsp
0x140009507  mov     [rax+8], rbx
0x14000950b  mov     [rax+10h], rdx
0x14000950f  push    rdi
0x140009510  sub     rsp, 30h
0x140009514  xorps   xmm0, xmm0
0x140009517  mov     qword ptr [rax+10h], 0
0x14000951f  movups  xmmword ptr [rcx], xmm0
0x140009522  mov     rdi, rcx
0x140009525  lea     rcx, [rax+10h]
0x140009529  call    AslStringDuplicateA
0x14000952e  mov     ebx, eax
0x140009530  test    eax, eax
0x140009532  jns     short loc_140009569
0x140009534  mov     [rsp+38h+var_10], eax
0x140009538  lea     r9, aAslstringdupli; "AslStringDuplicate failed with \"%s\" ["...
0x14000953f  lea     rax, qword_1400157F8
0x140009546  mov     r8d, 40Fh
0x14000954c  lea     rdx, aAslansistringc; "AslAnsiStringCreate"
0x140009553  mov     [rsp+38h+var_18], rax
0x140009558  mov     ecx, 1
0x14000955d  call    AslLogCallPrintf
0x140009562  mov     r8, [rsp+38h+SourceString]
0x140009567  jmp     short loc_14000957C
0x140009569  mov     rdx, [rsp+38h+SourceString]; SourceString
0x14000956e  mov     rcx, rdi; DestinationString
0x140009571  call    cs:__imp_RtlInitAnsiString
0x140009577  xor     r8d, r8d; P
0x14000957a  xor     ebx, ebx
0x14000957c  test    r8, r8
0x14000957f  jz      short loc_140009596
0x140009581  mov     rcx, gs:60h
0x14000958a  xor     edx, edx; Flags
0x14000958c  mov     rcx, [rcx+30h]; HeapHandle
0x140009590  call    cs:__imp_RtlFreeHeap
0x140009596  mov     eax, ebx
0x140009598  mov     rbx, [rsp+38h+arg_0]
0x14000959d  add     rsp, 30h
0x1400095a1  pop     rdi
0x1400095a2  retn
```
