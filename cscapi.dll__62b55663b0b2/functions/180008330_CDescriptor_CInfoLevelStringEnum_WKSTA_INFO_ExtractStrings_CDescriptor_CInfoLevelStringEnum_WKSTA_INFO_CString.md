# CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::ExtractStrings(CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CStrings *,void *)

- ea: `0x180008330`
- end: `0x18000837e`
- name: `?ExtractStrings@?$CDescriptor@VCInfoLevelStringEnum_WKSTA_INFO@@@@QEAAXPEAVCStrings@1@PEAX@Z`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001020`
- `0x180006750`

## callees

- `0x180008330`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180008366`
- `ntdll!RtlInitUnicodeString` at `0x180008366`

## pseudocode

```c
void __fastcall CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::ExtractStrings(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rbx
  const WCHAR **v7; // r8
  const WCHAR *v8; // rdx

  for ( i = 0; i != 3; ++i )
  {
    if ( *(_DWORD *)(a1 + 4 * i + 20) == -1 || (v7 = (const WCHAR **)(a3 + *(unsigned int *)(a1 + 4 * i + 20))) == 0 )
      v8 = 0;
    else
      v8 = *v7;
    RtlInitUnicodeString((PUNICODE_STRING)(a2 + 16 * i), v8);
  }
}

```

## disassembly

```asm
0x180008330  push    rbx
0x180008332  push    rbp
0x180008333  push    rsi
0x180008334  push    rdi
0x180008335  sub     rsp, 28h
0x180008339  mov     rsi, r8
0x18000833c  mov     rbp, rdx
0x18000833f  mov     rdi, rcx
0x180008342  xor     ebx, ebx
0x180008344  cmp     dword ptr [rdi+rbx*4+14h], 0FFFFFFFFh
0x180008349  jz      short loc_18000835A
0x18000834b  mov     r8d, [rdi+rbx*4+14h]
0x180008350  add     r8, rsi
0x180008353  jz      short loc_18000835A
0x180008355  mov     rdx, [r8]
0x180008358  jmp     short loc_18000835C
0x18000835a  xor     edx, edx; SourceString
0x18000835c  mov     rcx, rbx
0x18000835f  shl     rcx, 4
0x180008363  add     rcx, rbp; DestinationString
0x180008366  call    cs:__imp_RtlInitUnicodeString
0x18000836c  inc     rbx
0x18000836f  cmp     rbx, 3
0x180008373  jnz     short loc_180008344
0x180008375  add     rsp, 28h
0x180008379  pop     rdi
0x18000837a  pop     rsi
0x18000837b  pop     rbp
0x18000837c  pop     rbx
0x18000837d  retn
```
