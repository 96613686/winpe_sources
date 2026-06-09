# AslRegistryBuildUserPath

- ea: `0x18001f9bc`
- end: `0x18001fab3`
- name: `AslRegistryBuildUserPath`
- size: `247`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180020a94`

## callees

- `0x18001f9bc`
- `0x1800212e4`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18001f9da`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18001f9da`
- `ntdll!RtlAppendUnicodeToString` at `0x18001fa84`
- `ntdll!RtlAppendUnicodeToString` at `0x18001fa84`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001fa78`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001fa78`
- `ntdll!RtlFreeUnicodeString` at `0x18001fa5d`
- `ntdll!RtlFreeUnicodeString` at `0x18001fa5d`
- `ntdll!RtlAllocateHeap` at `0x18001fa29`
- `ntdll!RtlAllocateHeap` at `0x18001fa29`

## string_xrefs

- `0x18001fa45`: `AslRegistryBuildUserPath`
- `0x18001faa0`: `AslRegistryBuildUserPath`
- `0x18001fa8f`: `RtlFormatCurrentUserKeyPath failed [%x]`

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
0x18001f9bc  push    rbx
0x18001f9be  push    rbp
0x18001f9bf  push    rsi
0x18001f9c0  push    rdi
0x18001f9c1  push    r14
0x18001f9c3  sub     rsp, 40h
0x18001f9c7  mov     rdi, rcx
0x18001f9ca  xorps   xmm0, xmm0
0x18001f9cd  lea     rcx, [rsp+68h+KeyPath]; KeyPath
0x18001f9d2  mov     rbp, rdx
0x18001f9d5  movups  xmmword ptr [rsp+68h+KeyPath.Length], xmm0
0x18001f9da  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18001f9e0  xor     r14d, r14d
0x18001f9e3  mov     ebx, eax
0x18001f9e5  test    eax, eax
0x18001f9e7  js      loc_18001FA8F
0x18001f9ed  mov     [rdi], r14w
0x18001f9f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f9f5  inc     rax
0x18001f9f8  cmp     [rbp+rax*2+0], r14w
0x18001f9fe  jnz     short loc_18001F9F5
0x18001fa00  mov     esi, 1
0x18001fa05  add     ax, si
0x18001fa08  add     ax, ax
0x18001fa0b  add     ax, [rsp+68h+KeyPath.Length]
0x18001fa10  movzx   r8d, ax; Size
0x18001fa14  lea     edx, [rsi+7]; Flags
0x18001fa17  mov     [rdi+2], r8w
0x18001fa1c  mov     rcx, gs:60h
0x18001fa25  mov     rcx, [rcx+30h]; HeapHandle
0x18001fa29  call    cs:__imp_RtlAllocateHeap
0x18001fa2f  mov     [rdi+8], rax
0x18001fa33  test    rax, rax
0x18001fa36  jnz     short loc_18001FA70
0x18001fa38  lea     r9, aOutOfMemory; "Out of memory"
0x18001fa3f  mov     r8d, 672h
0x18001fa45  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x18001fa4c  mov     ecx, esi
0x18001fa4e  mov     ebx, 0C0000017h
0x18001fa53  call    AslLogCallPrintf
0x18001fa58  lea     rcx, [rsp+68h+KeyPath]; UnicodeString
0x18001fa5d  call    cs:__imp_RtlFreeUnicodeString
0x18001fa63  mov     eax, ebx
0x18001fa65  add     rsp, 40h
0x18001fa69  pop     r14
0x18001fa6b  pop     rdi
0x18001fa6c  pop     rsi
0x18001fa6d  pop     rbp
0x18001fa6e  pop     rbx
0x18001fa6f  retn
0x18001fa70  lea     rdx, [rsp+68h+KeyPath]; Source
0x18001fa75  mov     rcx, rdi; Destination
0x18001fa78  call    cs:__imp_RtlAppendUnicodeStringToString
0x18001fa7e  mov     rdx, rbp; Source
0x18001fa81  mov     rcx, rdi; Destination
0x18001fa84  call    cs:__imp_RtlAppendUnicodeToString
0x18001fa8a  mov     ebx, r14d
0x18001fa8d  jmp     short loc_18001FA58
0x18001fa8f  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x18001fa96  mov     [rsp+68h+var_48], eax
0x18001fa9a  mov     r8d, 666h
0x18001faa0  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x18001faa7  mov     ecx, 1
0x18001faac  call    AslLogCallPrintf
0x18001fab1  jmp     short loc_18001FA58
```
