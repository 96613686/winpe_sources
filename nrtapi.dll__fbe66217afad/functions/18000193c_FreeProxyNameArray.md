# FreeProxyNameArray

- ea: `0x18000193c`
- end: `0x1800019ac`
- name: `FreeProxyNameArray`
- size: `112`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001560`
- `0x1800019b4`

## callees

- `0x18000193c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000198f`
- `ntdll!RtlFreeHeap` at `0x18000198f`
- `ntdll!RtlFreeUnicodeString` at `0x180001969`
- `ntdll!RtlFreeUnicodeString` at `0x180001969`

## pseudocode

```c
BOOLEAN __fastcall FreeProxyNameArray(struct _UNICODE_STRING *P, unsigned __int16 a2)
{
  unsigned __int16 i; // bx
  BOOLEAN result; // al

  if ( P )
  {
    for ( i = 0; i < a2; ++i )
      RtlFreeUnicodeString(&P[i]);
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x18000193c  test    rcx, rcx
0x18000193f  jz      short locret_1800019AA
0x180001941  mov     [rsp+arg_0], rbx
0x180001946  mov     [rsp+arg_8], rsi
0x18000194b  push    rdi
0x18000194c  sub     rsp, 20h
0x180001950  xor     ebx, ebx
0x180001952  xor     eax, eax
0x180001954  movzx   esi, dx
0x180001957  mov     rdi, rcx
0x18000195a  cmp     ax, dx
0x18000195d  jnb     short loc_18000197D
0x18000195f  movzx   ecx, bx
0x180001962  shl     rcx, 4
0x180001966  add     rcx, rdi; UnicodeString
0x180001969  call    cs:__imp_RtlFreeUnicodeString
0x180001970  nop     dword ptr [rax+rax+00h]
0x180001975  inc     bx
0x180001978  cmp     bx, si
0x18000197b  jb      short loc_18000195F
0x18000197d  mov     rcx, gs:60h
0x180001986  mov     r8, rdi; P
0x180001989  xor     edx, edx; Flags
0x18000198b  mov     rcx, [rcx+30h]; HeapHandle
0x18000198f  call    cs:__imp_RtlFreeHeap
0x180001996  nop     dword ptr [rax+rax+00h]
0x18000199b  mov     rbx, [rsp+28h+arg_0]
0x1800019a0  mov     rsi, [rsp+28h+arg_8]
0x1800019a5  add     rsp, 20h
0x1800019a9  pop     rdi
0x1800019aa  retn
```
