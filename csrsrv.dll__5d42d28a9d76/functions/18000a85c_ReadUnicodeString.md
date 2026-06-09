# ReadUnicodeString

- ea: `0x18000a85c`
- end: `0x18000a99a`
- name: `ReadUnicodeString`
- size: `318`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PVOID BaseAddress, struct _UNICODE_STRING *Buffer)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a2b0`

## callees

- `0x1800035c0`
- `0x18000a85c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000a903`
- `ntdll!RtlAllocateHeap` at `0x18000a903`
- `ntdll!RtlInitUnicodeString` at `0x18000a879`
- `ntdll!RtlInitUnicodeString` at `0x18000a879`
- `ntdll!RtlFreeHeap` at `0x18000a96b`
- `ntdll!RtlFreeHeap` at `0x18000a96b`
- `ntdll!NtReadVirtualMemory` at `0x18000a8a6`
- `ntdll!NtReadVirtualMemory` at `0x18000a939`
- `ntdll!NtReadVirtualMemory` at `0x18000a8a6`
- `ntdll!NtReadVirtualMemory` at `0x18000a939`

## string_xrefs

- `0x18000a8bb`: `ReadUnicodeString`
- `0x18000a94e`: `ReadUnicodeString`

## pseudocode

```c
__int64 __fastcall ReadUnicodeString(HANDLE ProcessHandle, PVOID BaseAddress, struct _UNICODE_STRING *Buffer)
{
  NTSTATUS VirtualMemory; // edi
  __int64 result; // rax
  PVOID Heap; // rax
  void *v9; // rdi
  NTSTATUS v10; // esi

  RtlInitUnicodeString(Buffer, 0);
  if ( BaseAddress )
  {
    VirtualMemory = NtReadVirtualMemory(ProcessHandle, BaseAddress, Buffer, 0x10u, 0);
    if ( VirtualMemory < 0 )
    {
      CsrpLogFailure("ReadUnicodeString");
      return (unsigned int)VirtualMemory;
    }
    if ( Buffer->Length && Buffer->Buffer )
    {
      Heap = RtlAllocateHeap(CsrHeap, CsrBaseTag + 786432, Buffer->Length + 2LL);
      v9 = Heap;
      if ( !Heap )
        return 3221225495LL;
      v10 = NtReadVirtualMemory(ProcessHandle, Buffer->Buffer, Heap, Buffer->Length + 2LL, 0);
      if ( v10 < 0 )
      {
        CsrpLogFailure("ReadUnicodeString");
        RtlFreeHeap(CsrHeap, 0, v9);
        result = (unsigned int)v10;
        Buffer->Buffer = 0;
        return result;
      }
      Buffer->Buffer = (PWSTR)v9;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a85c  mov     [rsp+arg_0], rbx
0x18000a861  mov     [rsp+arg_8], rsi
0x18000a866  push    rdi
0x18000a867  sub     rsp, 30h
0x18000a86b  mov     rdi, rdx
0x18000a86e  mov     rsi, rcx
0x18000a871  xor     edx, edx; SourceString
0x18000a873  mov     rcx, r8; DestinationString
0x18000a876  mov     rbx, r8
0x18000a879  call    cs:__imp_RtlInitUnicodeString
0x18000a880  nop     dword ptr [rax+rax+00h]
0x18000a885  test    rdi, rdi
0x18000a888  jz      loc_18000A987
0x18000a88e  mov     r9d, 10h; NumberOfBytesToRead
0x18000a894  mov     [rsp+38h+NumberOfBytesRead], 0; NumberOfBytesRead
0x18000a89d  mov     r8, rbx; Buffer
0x18000a8a0  mov     rdx, rdi; BaseAddress
0x18000a8a3  mov     rcx, rsi; ProcessHandle
0x18000a8a6  call    cs:__imp_NtReadVirtualMemory
0x18000a8ad  nop     dword ptr [rax+rax+00h]
0x18000a8b2  mov     edi, eax
0x18000a8b4  test    eax, eax
0x18000a8b6  jns     short loc_18000A8D3
0x18000a8b8  mov     r8d, eax
0x18000a8bb  lea     rcx, aReadunicodestr; "ReadUnicodeString"
0x18000a8c2  mov     edx, 0FB4h
0x18000a8c7  call    CsrpLogFailure
0x18000a8cc  mov     eax, edi
0x18000a8ce  jmp     loc_18000A989
0x18000a8d3  xor     eax, eax
0x18000a8d5  cmp     ax, [rbx]
0x18000a8d8  jz      loc_18000A987
0x18000a8de  cmp     [rbx+8], rax
0x18000a8e2  jz      loc_18000A987
0x18000a8e8  movzx   r8d, word ptr [rbx]
0x18000a8ec  mov     edx, cs:CsrBaseTag
0x18000a8f2  add     r8, 2; Size
0x18000a8f6  mov     rcx, cs:CsrHeap; HeapHandle
0x18000a8fd  add     edx, 0C0000h; Flags
0x18000a903  call    cs:__imp_RtlAllocateHeap
0x18000a90a  nop     dword ptr [rax+rax+00h]
0x18000a90f  mov     rdi, rax
0x18000a912  test    rax, rax
0x18000a915  jnz     short loc_18000A91E
0x18000a917  mov     eax, 0C0000017h
0x18000a91c  jmp     short loc_18000A989
0x18000a91e  movzx   r9d, word ptr [rbx]
0x18000a922  mov     r8, rdi; Buffer
0x18000a925  mov     rdx, [rbx+8]; BaseAddress
0x18000a929  add     r9, 2; NumberOfBytesToRead
0x18000a92d  mov     rcx, rsi; ProcessHandle
0x18000a930  mov     [rsp+38h+NumberOfBytesRead], 0; NumberOfBytesRead
0x18000a939  call    cs:__imp_NtReadVirtualMemory
0x18000a940  nop     dword ptr [rax+rax+00h]
0x18000a945  mov     esi, eax
0x18000a947  test    eax, eax
0x18000a949  jns     short loc_18000A983
0x18000a94b  mov     r8d, eax
0x18000a94e  lea     rcx, aReadunicodestr; "ReadUnicodeString"
0x18000a955  mov     edx, 0FCEh
0x18000a95a  call    CsrpLogFailure
0x18000a95f  mov     rcx, cs:CsrHeap; HeapHandle
0x18000a966  mov     r8, rdi; BaseAddress
0x18000a969  xor     edx, edx; Flags
0x18000a96b  call    cs:__imp_RtlFreeHeap
0x18000a972  nop     dword ptr [rax+rax+00h]
0x18000a977  mov     eax, esi
0x18000a979  mov     qword ptr [rbx+8], 0
0x18000a981  jmp     short loc_18000A989
0x18000a983  mov     [rbx+8], rdi
0x18000a987  xor     eax, eax
0x18000a989  mov     rbx, [rsp+38h+arg_0]
0x18000a98e  mov     rsi, [rsp+38h+arg_8]
0x18000a993  add     rsp, 30h
0x18000a997  pop     rdi
0x18000a998  retn
```
