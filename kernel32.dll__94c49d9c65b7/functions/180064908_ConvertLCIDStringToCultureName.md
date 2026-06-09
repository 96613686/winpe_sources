# ConvertLCIDStringToCultureName

- ea: `0x180064908`
- end: `0x1800649bb`
- name: `ConvertLCIDStringToCultureName`
- size: `179`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PVOID MemoryPointer)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18005b8ac`

## callees

- `0x180064908`

## import_xrefs

- `ntdll!RtlUnicodeStringToInteger` at `0x180064975`
- `ntdll!RtlUnicodeStringToInteger` at `0x180064975`
- `ntdll!RtlLCIDToCultureName` at `0x180064997`
- `ntdll!RtlLCIDToCultureName` at `0x180064997`
- `ntdll!RtlSizeHeap` at `0x180064944`
- `ntdll!RtlSizeHeap` at `0x180064944`
- `ntdll!RtlInitUnicodeString` at `0x180064960`
- `ntdll!RtlInitUnicodeString` at `0x180064960`

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
0x180064908  mov     [rsp+arg_8], rbx
0x18006490d  push    rdi
0x18006490e  sub     rsp, 30h
0x180064912  mov     [rsp+38h+Value], 0
0x18006491a  xorps   xmm0, xmm0
0x18006491d  mov     rdi, rdx
0x180064920  mov     rbx, rcx
0x180064923  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180064928  test    rcx, rcx
0x18006492b  jz      short loc_1800649AB
0x18006492d  test    rdx, rdx
0x180064930  jz      short loc_1800649AB
0x180064932  mov     rcx, gs:60h
0x18006493b  mov     r8, rdx; MemoryPointer
0x18006493e  xor     edx, edx; Flags
0x180064940  mov     rcx, [rcx+30h]; HeapHandle
0x180064944  call    cs:__imp_RtlSizeHeap
0x18006494a  add     rax, 0FFFFFFFFFFFFFF56h
0x180064950  cmp     rax, 0FFFFFFFFFFFFFF54h
0x180064956  ja      short loc_1800649AB
0x180064958  mov     rdx, rbx; SourceString
0x18006495b  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180064960  call    cs:__imp_RtlInitUnicodeString
0x180064966  lea     r8, [rsp+38h+Value]; Value
0x18006496b  mov     edx, 10h; Base
0x180064970  lea     rcx, [rsp+38h+DestinationString]; String
0x180064975  call    cs:__imp_RtlUnicodeStringToInteger
0x18006497b  mov     ebx, eax
0x18006497d  test    eax, eax
0x18006497f  js      short loc_1800649A7
0x180064981  mov     ecx, [rsp+38h+Value]
0x180064985  lea     rdx, [rsp+38h+DestinationString]
0x18006498a  mov     [rsp+38h+DestinationString.Buffer], rdi
0x18006498f  mov     dword ptr [rsp+38h+DestinationString.Length], 0AA0000h
0x180064997  call    cs:__imp_RtlLCIDToCultureName
0x18006499d  test    al, al
0x18006499f  mov     ecx, 0C0000001h
0x1800649a4  cmovz   ebx, ecx
0x1800649a7  mov     eax, ebx
0x1800649a9  jmp     short loc_1800649B0
0x1800649ab  mov     eax, 0C000000Dh
0x1800649b0  mov     rbx, [rsp+38h+arg_8]
0x1800649b5  add     rsp, 30h
0x1800649b9  pop     rdi
0x1800649ba  retn
```
