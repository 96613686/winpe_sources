# ConvertLCIDStringToCultureName

- ea: `0x18006b5cc`
- end: `0x18006b6a0`
- name: `ConvertLCIDStringToCultureName`
- size: `212`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PVOID MemoryPointer)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800611d8`

## callees

- `0x18006b5cc`

## import_xrefs

- `ntdll!RtlUnicodeStringToInteger` at `0x18006b64d`
- `ntdll!RtlUnicodeStringToInteger` at `0x18006b64d`
- `ntdll!RtlLCIDToCultureName` at `0x18006b675`
- `ntdll!RtlLCIDToCultureName` at `0x18006b675`
- `ntdll!RtlSizeHeap` at `0x18006b610`
- `ntdll!RtlSizeHeap` at `0x18006b610`
- `ntdll!RtlInitUnicodeString` at `0x18006b632`
- `ntdll!RtlInitUnicodeString` at `0x18006b632`

## pseudocode

```c
__int64 __fastcall ConvertLCIDStringToCultureName(PCWSTR SourceString, PVOID MemoryPointer)
{
  NTSTATUS v4; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  ULONG Value; // [rsp+40h] [rbp+8h] BYREF

  Value = 0;
  DestinationString = 0;
  if ( !SourceString
    || !MemoryPointer
    || RtlSizeHeap(NtCurrentPeb()->ProcessHeap, 0, MemoryPointer) - 170 > 0xFFFFFFFFFFFFFF54uLL )
  {
    return 3221225485LL;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v4 = RtlUnicodeStringToInteger(&DestinationString, 0x10u, &Value);
  if ( v4 >= 0 )
  {
    DestinationString.Buffer = (PWSTR)MemoryPointer;
    *(_DWORD *)&DestinationString.Length = 11141120;
    if ( !(unsigned __int8)RtlLCIDToCultureName(Value, &DestinationString) )
      return (unsigned int)-1073741823;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006b5cc  mov     [rsp+arg_8], rbx
0x18006b5d1  push    rdi
0x18006b5d2  sub     rsp, 30h
0x18006b5d6  mov     [rsp+38h+Value], 0
0x18006b5de  xorps   xmm0, xmm0
0x18006b5e1  mov     rdi, rdx
0x18006b5e4  mov     rbx, rcx
0x18006b5e7  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18006b5ec  test    rcx, rcx
0x18006b5ef  jz      loc_18006B68F
0x18006b5f5  test    rdx, rdx
0x18006b5f8  jz      loc_18006B68F
0x18006b5fe  mov     rcx, gs:60h
0x18006b607  mov     r8, rdx; MemoryPointer
0x18006b60a  xor     edx, edx; Flags
0x18006b60c  mov     rcx, [rcx+30h]; HeapHandle
0x18006b610  call    cs:__imp_RtlSizeHeap
0x18006b617  nop     dword ptr [rax+rax+00h]
0x18006b61c  add     rax, 0FFFFFFFFFFFFFF56h
0x18006b622  cmp     rax, 0FFFFFFFFFFFFFF54h
0x18006b628  ja      short loc_18006B68F
0x18006b62a  mov     rdx, rbx; SourceString
0x18006b62d  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18006b632  call    cs:__imp_RtlInitUnicodeString
0x18006b639  nop     dword ptr [rax+rax+00h]
0x18006b63e  lea     r8, [rsp+38h+Value]; Value
0x18006b643  mov     edx, 10h; Base
0x18006b648  lea     rcx, [rsp+38h+DestinationString]; String
0x18006b64d  call    cs:__imp_RtlUnicodeStringToInteger
0x18006b654  nop     dword ptr [rax+rax+00h]
0x18006b659  mov     ebx, eax
0x18006b65b  test    eax, eax
0x18006b65d  js      short loc_18006B68B
0x18006b65f  mov     ecx, [rsp+38h+Value]
0x18006b663  lea     rdx, [rsp+38h+DestinationString]
0x18006b668  mov     [rsp+38h+DestinationString.Buffer], rdi
0x18006b66d  mov     dword ptr [rsp+38h+DestinationString.Length], 0AA0000h
0x18006b675  call    cs:__imp_RtlLCIDToCultureName
0x18006b67c  nop     dword ptr [rax+rax+00h]
0x18006b681  test    al, al
0x18006b683  mov     ecx, 0C0000001h
0x18006b688  cmovz   ebx, ecx
0x18006b68b  mov     eax, ebx
0x18006b68d  jmp     short loc_18006B694
0x18006b68f  mov     eax, 0C000000Dh
0x18006b694  mov     rbx, [rsp+38h+arg_8]
0x18006b699  add     rsp, 30h
0x18006b69d  pop     rdi
0x18006b69e  retn
```
