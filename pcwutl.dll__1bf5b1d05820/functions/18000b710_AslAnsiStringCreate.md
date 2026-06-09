# AslAnsiStringCreate

- ea: `0x18000b710`
- end: `0x18000b7af`
- name: `AslAnsiStringCreate`
- size: `159`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800171d0`

## callees

- `0x18000b710`
- `0x18000e240`
- `0x18000f130`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x18000b77d`
- `ntdll!RtlInitAnsiString` at `0x18000b77d`
- `ntdll!RtlFreeHeap` at `0x18000b79c`
- `ntdll!RtlFreeHeap` at `0x18000b79c`

## string_xrefs

- `0x18000b758`: `AslAnsiStringCreate`

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
    AslLogCallPrintf(1, "AslAnsiStringCreate", 1039, "AslStringDuplicate failed with \"%s\" [%x]", byte_1800216C9, v2);
    v4 = (char *)SourceString;
  }
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return v3;
}

```

## disassembly

```asm
0x18000b710  mov     rax, rsp
0x18000b713  mov     [rax+8], rbx
0x18000b717  mov     [rax+10h], rdx
0x18000b71b  push    rdi
0x18000b71c  sub     rsp, 30h
0x18000b720  xorps   xmm0, xmm0
0x18000b723  mov     qword ptr [rax+10h], 0
0x18000b72b  movups  xmmword ptr [rcx], xmm0
0x18000b72e  mov     rdi, rcx
0x18000b731  lea     rcx, [rax+10h]
0x18000b735  call    AslStringDuplicateA
0x18000b73a  mov     ebx, eax
0x18000b73c  test    eax, eax
0x18000b73e  jns     short loc_18000B775
0x18000b740  mov     [rsp+38h+var_10], eax
0x18000b744  lea     r9, aAslstringdupli; "AslStringDuplicate failed with \"%s\" ["...
0x18000b74b  lea     rax, byte_1800216C9
0x18000b752  mov     r8d, 40Fh
0x18000b758  lea     rdx, aAslansistringc; "AslAnsiStringCreate"
0x18000b75f  mov     [rsp+38h+var_18], rax
0x18000b764  mov     ecx, 1
0x18000b769  call    AslLogCallPrintf
0x18000b76e  mov     r8, [rsp+38h+SourceString]
0x18000b773  jmp     short loc_18000B788
0x18000b775  mov     rdx, [rsp+38h+SourceString]; SourceString
0x18000b77a  mov     rcx, rdi; DestinationString
0x18000b77d  call    cs:__imp_RtlInitAnsiString
0x18000b783  xor     r8d, r8d; P
0x18000b786  xor     ebx, ebx
0x18000b788  test    r8, r8
0x18000b78b  jz      short loc_18000B7A2
0x18000b78d  mov     rcx, gs:60h
0x18000b796  xor     edx, edx; Flags
0x18000b798  mov     rcx, [rcx+30h]; HeapHandle
0x18000b79c  call    cs:__imp_RtlFreeHeap
0x18000b7a2  mov     eax, ebx
0x18000b7a4  mov     rbx, [rsp+38h+arg_0]
0x18000b7a9  add     rsp, 30h
0x18000b7ad  pop     rdi
0x18000b7ae  retn
```
