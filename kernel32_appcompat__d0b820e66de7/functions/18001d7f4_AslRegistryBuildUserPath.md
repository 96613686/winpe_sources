# AslRegistryBuildUserPath

- ea: `0x18001d7f4`
- end: `0x18001d90a`
- name: `AslRegistryBuildUserPath`
- size: `278`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001e880`

## callees

- `0x18001d7f4`
- `0x18001f138`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18001d812`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18001d812`
- `ntdll!RtlAppendUnicodeToString` at `0x18001d8d5`
- `ntdll!RtlAppendUnicodeToString` at `0x18001d8d5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001d8c3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001d8c3`
- `ntdll!RtlFreeUnicodeString` at `0x18001d8a1`
- `ntdll!RtlFreeUnicodeString` at `0x18001d8a1`
- `ntdll!RtlAllocateHeap` at `0x18001d867`
- `ntdll!RtlAllocateHeap` at `0x18001d867`

## string_xrefs

- `0x18001d889`: `AslRegistryBuildUserPath`
- `0x18001d8f7`: `AslRegistryBuildUserPath`
- `0x18001d8e6`: `RtlFormatCurrentUserKeyPath failed [%x]`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildUserPath(PUNICODE_STRING Destination, PCWSTR Source)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rax
  USHORT v6; // ax
  WCHAR *Heap; // rax
  struct _UNICODE_STRING KeyPath; // [rsp+30h] [rbp-38h] BYREF

  KeyPath = 0;
  v4 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v4 < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslRegistryBuildUserPath",
      1638,
      (unsigned int)"RtlFormatCurrentUserKeyPath failed [%x]");
  }
  else
  {
    Destination->Length = 0;
    v5 = -1;
    do
      ++v5;
    while ( Source[v5] );
    v6 = KeyPath.Length + 2 * (v5 + 1);
    Destination->MaximumLength = v6;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v6);
    Destination->Buffer = Heap;
    if ( Heap )
    {
      RtlAppendUnicodeStringToString(Destination, &KeyPath);
      RtlAppendUnicodeToString(Destination, Source);
      v4 = 0;
    }
    else
    {
      v4 = -1073741801;
      AslLogCallPrintf(1, (unsigned int)"AslRegistryBuildUserPath", 1650, (unsigned int)"Out of memory");
    }
  }
  RtlFreeUnicodeString(&KeyPath);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d7f4  push    rbx
0x18001d7f6  push    rbp
0x18001d7f7  push    rsi
0x18001d7f8  push    rdi
0x18001d7f9  push    r14
0x18001d7fb  sub     rsp, 40h
0x18001d7ff  mov     rdi, rcx
0x18001d802  xorps   xmm0, xmm0
0x18001d805  lea     rcx, [rsp+68h+KeyPath]; KeyPath
0x18001d80a  mov     rbp, rdx
0x18001d80d  movups  xmmword ptr [rsp+68h+KeyPath.Length], xmm0
0x18001d812  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18001d819  nop     dword ptr [rax+rax+00h]
0x18001d81e  xor     r14d, r14d
0x18001d821  mov     ebx, eax
0x18001d823  test    eax, eax
0x18001d825  js      loc_18001D8E6
0x18001d82b  mov     [rdi], r14w
0x18001d82f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d833  inc     rax
0x18001d836  cmp     [rbp+rax*2+0], r14w
0x18001d83c  jnz     short loc_18001D833
0x18001d83e  mov     esi, 1
0x18001d843  add     ax, si
0x18001d846  add     ax, ax
0x18001d849  add     ax, [rsp+68h+KeyPath.Length]
0x18001d84e  movzx   r8d, ax; Size
0x18001d852  lea     edx, [rsi+7]; Flags
0x18001d855  mov     [rdi+2], r8w
0x18001d85a  mov     rcx, gs:60h
0x18001d863  mov     rcx, [rcx+30h]; HeapHandle
0x18001d867  call    cs:__imp_RtlAllocateHeap
0x18001d86e  nop     dword ptr [rax+rax+00h]
0x18001d873  mov     [rdi+8], rax
0x18001d877  test    rax, rax
0x18001d87a  jnz     short loc_18001D8BB
0x18001d87c  lea     r9, aOutOfMemory; "Out of memory"
0x18001d883  mov     r8d, 672h
0x18001d889  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x18001d890  mov     ecx, esi
0x18001d892  mov     ebx, 0C0000017h
0x18001d897  call    AslLogCallPrintf
0x18001d89c  lea     rcx, [rsp+68h+KeyPath]; UnicodeString
0x18001d8a1  call    cs:__imp_RtlFreeUnicodeString
0x18001d8a8  nop     dword ptr [rax+rax+00h]
0x18001d8ad  mov     eax, ebx
0x18001d8af  add     rsp, 40h
0x18001d8b3  pop     r14
0x18001d8b5  pop     rdi
0x18001d8b6  pop     rsi
0x18001d8b7  pop     rbp
0x18001d8b8  pop     rbx
0x18001d8b9  retn
0x18001d8bb  lea     rdx, [rsp+68h+KeyPath]; Source
0x18001d8c0  mov     rcx, rdi; Destination
0x18001d8c3  call    cs:__imp_RtlAppendUnicodeStringToString
0x18001d8ca  nop     dword ptr [rax+rax+00h]
0x18001d8cf  mov     rdx, rbp; Source
0x18001d8d2  mov     rcx, rdi; Destination
0x18001d8d5  call    cs:__imp_RtlAppendUnicodeToString
0x18001d8dc  nop     dword ptr [rax+rax+00h]
0x18001d8e1  mov     ebx, r14d
0x18001d8e4  jmp     short loc_18001D89C
0x18001d8e6  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x18001d8ed  mov     [rsp+68h+var_48], eax
0x18001d8f1  mov     r8d, 666h
0x18001d8f7  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x18001d8fe  mov     ecx, 1
0x18001d903  call    AslLogCallPrintf
0x18001d908  jmp     short loc_18001D89C
```
