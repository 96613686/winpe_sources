# AslRegistryBuildMachinePath

- ea: `0x140012800`
- end: `0x1400128df`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400128e8`

## callees

- `0x140012800`
- `0x1400151b0`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x1400128c0`
- `ntdll!RtlAppendUnicodeToString` at `0x1400128cc`
- `ntdll!RtlAppendUnicodeToString` at `0x1400128c0`
- `ntdll!RtlAppendUnicodeToString` at `0x1400128cc`
- `ntdll!RtlAllocateHeap` at `0x140012864`
- `ntdll!RtlAllocateHeap` at `0x140012864`
- `ntdll!RtlInitUnicodeString` at `0x140012823`
- `ntdll!RtlInitUnicodeString` at `0x140012823`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400128a5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400128a5`

## string_xrefs

- `0x140012812`: `\Registry\Machine`
- `0x140012888`: `AslRegistryBuildMachinePath`

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
0x140012800  push    rbx
0x140012802  push    rbp
0x140012803  push    rsi
0x140012804  push    rdi
0x140012805  sub     rsp, 48h
0x140012809  mov     rdi, rdx
0x14001280c  mov     rbx, rcx
0x14001280f  xorps   xmm0, xmm0
0x140012812  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine"
0x140012819  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14001281e  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140012823  call    cs:__imp_RtlInitUnicodeString
0x140012829  xor     esi, esi
0x14001282b  mov     [rbx], si
0x14001282e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140012832  inc     rax
0x140012835  cmp     [rdi+rax*2], si
0x140012839  jnz     short loc_140012832
0x14001283b  mov     ebp, 1
0x140012840  add     ax, bp
0x140012843  add     ax, ax
0x140012846  add     ax, [rsp+68h+DestinationString.Length]
0x14001284b  movzx   r8d, ax; Size
0x14001284f  lea     edx, [rbp+7]; Flags
0x140012852  mov     [rbx+2], r8w
0x140012857  mov     rcx, gs:60h
0x140012860  mov     rcx, [rcx+30h]; HeapHandle
0x140012864  call    cs:__imp_RtlAllocateHeap
0x14001286a  mov     [rbx+8], rax
0x14001286e  test    rax, rax
0x140012871  jnz     short loc_14001289D
0x140012873  movzx   eax, word ptr [rbx+2]
0x140012877  lea     r9, aFailedToAlloca_1; "Failed to allocate %d bytes for user ke"...
0x14001287e  mov     r8d, 62Eh
0x140012884  mov     [rsp+68h+var_48], eax
0x140012888  lea     rdx, aAslregistrybui_0; "AslRegistryBuildMachinePath"
0x14001288f  mov     ecx, ebp
0x140012891  mov     edi, 0C0000017h
0x140012896  call    AslLogCallPrintf
0x14001289b  jmp     short loc_1400128D4
0x14001289d  lea     rdx, [rsp+68h+DestinationString]; Source
0x1400128a2  mov     rcx, rbx; Destination
0x1400128a5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400128ab  test    rdi, rdi
0x1400128ae  jz      short loc_1400128C6
0x1400128b0  cmp     word ptr [rdi], 5Ch ; '\'
0x1400128b4  jz      short loc_1400128C6
0x1400128b6  lea     rdx, Source; "\\"
0x1400128bd  mov     rcx, rbx; Destination
0x1400128c0  call    cs:__imp_RtlAppendUnicodeToString
0x1400128c6  mov     rdx, rdi; Source
0x1400128c9  mov     rcx, rbx; Destination
0x1400128cc  call    cs:__imp_RtlAppendUnicodeToString
0x1400128d2  mov     edi, esi
0x1400128d4  mov     eax, edi
0x1400128d6  add     rsp, 48h
0x1400128da  pop     rdi
0x1400128db  pop     rsi
0x1400128dc  pop     rbp
0x1400128dd  pop     rbx
0x1400128de  retn
```
