# AslRegistryBuildMachinePath

- ea: `0x140007268`
- end: `0x140007347`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140007350`

## callees

- `0x140007074`
- `0x140007268`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x140007328`
- `ntdll!RtlAppendUnicodeToString` at `0x140007334`
- `ntdll!RtlAppendUnicodeToString` at `0x140007328`
- `ntdll!RtlAppendUnicodeToString` at `0x140007334`
- `ntdll!RtlAllocateHeap` at `0x1400072cc`
- `ntdll!RtlAllocateHeap` at `0x1400072cc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000730d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000730d`
- `ntdll!RtlInitUnicodeString` at `0x14000728b`
- `ntdll!RtlInitUnicodeString` at `0x14000728b`

## string_xrefs

- `0x14000727a`: `\Registry\Machine`
- `0x1400072f0`: `AslRegistryBuildMachinePath`

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
0x140007268  push    rbx
0x14000726a  push    rbp
0x14000726b  push    rsi
0x14000726c  push    rdi
0x14000726d  sub     rsp, 48h
0x140007271  mov     rdi, rdx
0x140007274  mov     rbx, rcx
0x140007277  xorps   xmm0, xmm0
0x14000727a  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine"
0x140007281  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140007286  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14000728b  call    cs:__imp_RtlInitUnicodeString
0x140007291  xor     esi, esi
0x140007293  mov     [rbx], si
0x140007296  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000729a  inc     rax
0x14000729d  cmp     [rdi+rax*2], si
0x1400072a1  jnz     short loc_14000729A
0x1400072a3  mov     ebp, 1
0x1400072a8  add     ax, bp
0x1400072ab  add     ax, ax
0x1400072ae  add     ax, [rsp+68h+DestinationString.Length]
0x1400072b3  movzx   r8d, ax; Size
0x1400072b7  lea     edx, [rbp+7]; Flags
0x1400072ba  mov     [rbx+2], r8w
0x1400072bf  mov     rcx, gs:60h
0x1400072c8  mov     rcx, [rcx+30h]; HeapHandle
0x1400072cc  call    cs:__imp_RtlAllocateHeap
0x1400072d2  mov     [rbx+8], rax
0x1400072d6  test    rax, rax
0x1400072d9  jnz     short loc_140007305
0x1400072db  movzx   eax, word ptr [rbx+2]
0x1400072df  lea     r9, aFailedToAlloca; "Failed to allocate %d bytes for user ke"...
0x1400072e6  mov     r8d, 62Eh
0x1400072ec  mov     [rsp+68h+var_48], eax
0x1400072f0  lea     rdx, aAslregistrybui_0; "AslRegistryBuildMachinePath"
0x1400072f7  mov     ecx, ebp
0x1400072f9  mov     edi, 0C0000017h
0x1400072fe  call    AslLogCallPrintf
0x140007303  jmp     short loc_14000733C
0x140007305  lea     rdx, [rsp+68h+DestinationString]; Source
0x14000730a  mov     rcx, rbx; Destination
0x14000730d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140007313  test    rdi, rdi
0x140007316  jz      short loc_14000732E
0x140007318  cmp     word ptr [rdi], 5Ch ; '\'
0x14000731c  jz      short loc_14000732E
0x14000731e  lea     rdx, Source; "\\"
0x140007325  mov     rcx, rbx; Destination
0x140007328  call    cs:__imp_RtlAppendUnicodeToString
0x14000732e  mov     rdx, rdi; Source
0x140007331  mov     rcx, rbx; Destination
0x140007334  call    cs:__imp_RtlAppendUnicodeToString
0x14000733a  mov     edi, esi
0x14000733c  mov     eax, edi
0x14000733e  add     rsp, 48h
0x140007342  pop     rdi
0x140007343  pop     rsi
0x140007344  pop     rbp
0x140007345  pop     rbx
0x140007346  retn
```
