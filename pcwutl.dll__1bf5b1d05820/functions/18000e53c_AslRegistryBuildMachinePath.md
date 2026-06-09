# AslRegistryBuildMachinePath

- ea: `0x18000e53c`
- end: `0x18000e61b`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e624`

## callees

- `0x18000e240`
- `0x18000e53c`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18000e5fc`
- `ntdll!RtlAppendUnicodeToString` at `0x18000e608`
- `ntdll!RtlAppendUnicodeToString` at `0x18000e5fc`
- `ntdll!RtlAppendUnicodeToString` at `0x18000e608`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000e5e1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000e5e1`
- `ntdll!RtlAllocateHeap` at `0x18000e5a0`
- `ntdll!RtlAllocateHeap` at `0x18000e5a0`
- `ntdll!RtlInitUnicodeString` at `0x18000e55f`
- `ntdll!RtlInitUnicodeString` at `0x18000e55f`

## string_xrefs

- `0x18000e54e`: `\Registry\Machine`
- `0x18000e5c4`: `AslRegistryBuildMachinePath`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildMachinePath(PUNICODE_STRING Destination, PCWSTR Source)
{
  __int64 v4; // rax
  USHORT v5; // ax
  WCHAR *Heap; // rax
  unsigned int v7; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine");
  Destination->Length = 0;
  v4 = -1;
  do
    ++v4;
  while ( Source[v4] );
  v5 = DestinationString.Length + 2 * (v4 + 1);
  Destination->MaximumLength = v5;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v5);
  Destination->Buffer = Heap;
  if ( Heap )
  {
    RtlAppendUnicodeStringToString(Destination, &DestinationString);
    if ( Source && *Source != 92 )
      RtlAppendUnicodeToString(Destination, L"\\");
    RtlAppendUnicodeToString(Destination, Source);
    return 0;
  }
  else
  {
    v7 = -1073741801;
    AslLogCallPrintf(
      1,
      "AslRegistryBuildMachinePath",
      1582,
      "Failed to allocate %d bytes for user key buffer",
      Destination->MaximumLength);
  }
  return v7;
}

```

## disassembly

```asm
0x18000e53c  push    rbx
0x18000e53e  push    rbp
0x18000e53f  push    rsi
0x18000e540  push    rdi
0x18000e541  sub     rsp, 48h
0x18000e545  mov     rdi, rdx
0x18000e548  mov     rbx, rcx
0x18000e54b  xorps   xmm0, xmm0
0x18000e54e  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine"
0x18000e555  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18000e55a  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18000e55f  call    cs:__imp_RtlInitUnicodeString
0x18000e565  xor     esi, esi
0x18000e567  mov     [rbx], si
0x18000e56a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e56e  inc     rax
0x18000e571  cmp     [rdi+rax*2], si
0x18000e575  jnz     short loc_18000E56E
0x18000e577  mov     ebp, 1
0x18000e57c  add     ax, bp
0x18000e57f  add     ax, ax
0x18000e582  add     ax, [rsp+68h+DestinationString.Length]
0x18000e587  movzx   r8d, ax; Size
0x18000e58b  lea     edx, [rbp+7]; Flags
0x18000e58e  mov     [rbx+2], r8w
0x18000e593  mov     rcx, gs:60h
0x18000e59c  mov     rcx, [rcx+30h]; HeapHandle
0x18000e5a0  call    cs:__imp_RtlAllocateHeap
0x18000e5a6  mov     [rbx+8], rax
0x18000e5aa  test    rax, rax
0x18000e5ad  jnz     short loc_18000E5D9
0x18000e5af  movzx   eax, word ptr [rbx+2]
0x18000e5b3  lea     r9, aFailedToAlloca; "Failed to allocate %d bytes for user ke"...
0x18000e5ba  mov     r8d, 62Eh
0x18000e5c0  mov     [rsp+68h+var_48], eax
0x18000e5c4  lea     rdx, aAslregistrybui_0; "AslRegistryBuildMachinePath"
0x18000e5cb  mov     ecx, ebp
0x18000e5cd  mov     edi, 0C0000017h
0x18000e5d2  call    AslLogCallPrintf
0x18000e5d7  jmp     short loc_18000E610
0x18000e5d9  lea     rdx, [rsp+68h+DestinationString]; Source
0x18000e5de  mov     rcx, rbx; Destination
0x18000e5e1  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000e5e7  test    rdi, rdi
0x18000e5ea  jz      short loc_18000E602
0x18000e5ec  cmp     word ptr [rdi], 5Ch ; '\'
0x18000e5f0  jz      short loc_18000E602
0x18000e5f2  lea     rdx, asc_18001D1B4; "\\"
0x18000e5f9  mov     rcx, rbx; Destination
0x18000e5fc  call    cs:__imp_RtlAppendUnicodeToString
0x18000e602  mov     rdx, rdi; Source
0x18000e605  mov     rcx, rbx; Destination
0x18000e608  call    cs:__imp_RtlAppendUnicodeToString
0x18000e60e  mov     edi, esi
0x18000e610  mov     eax, edi
0x18000e612  add     rsp, 48h
0x18000e616  pop     rdi
0x18000e617  pop     rsi
0x18000e618  pop     rbp
0x18000e619  pop     rbx
0x18000e61a  retn
```
