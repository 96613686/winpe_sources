# AslAnsiStringFree

- ea: `0x18000b854`
- end: `0x18000b8a3`
- name: `AslAnsiStringFree`
- size: `79`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001734c`
- `0x1800174a4`
- `0x180017cac`

## callees

- `0x18000b854`
- `0x1800191a2`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000b891`
- `ntdll!RtlFreeHeap` at `0x18000b891`

## pseudocode

```c
BOOLEAN __fastcall AslAnsiStringFree(__int64 a1)
{
  void *v2; // rcx
  BOOLEAN result; // al
  void *v4; // r8

  if ( a1 )
  {
    v2 = *(void **)(a1 + 8);
    if ( v2 )
    {
      result = (unsigned __int8)memset_0(v2, 66, *(unsigned __int16 *)(a1 + 2));
      v4 = *(void **)(a1 + 8);
      if ( v4 )
        result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    }
    *(_OWORD *)a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b854  test    rcx, rcx
0x18000b857  jz      short locret_18000B8A2
0x18000b859  push    rbx
0x18000b85a  sub     rsp, 20h
0x18000b85e  mov     rbx, rcx
0x18000b861  mov     rcx, [rcx+8]; void *
0x18000b865  test    rcx, rcx
0x18000b868  jz      short loc_18000B897
0x18000b86a  movzx   r8d, word ptr [rbx+2]; Size
0x18000b86f  mov     edx, 42h ; 'B'; Val
0x18000b874  call    memset_0
0x18000b879  mov     r8, [rbx+8]; P
0x18000b87d  test    r8, r8
0x18000b880  jz      short loc_18000B897
0x18000b882  mov     rcx, gs:60h
0x18000b88b  xor     edx, edx; Flags
0x18000b88d  mov     rcx, [rcx+30h]; HeapHandle
0x18000b891  call    cs:__imp_RtlFreeHeap
0x18000b897  xorps   xmm0, xmm0
0x18000b89a  movups  xmmword ptr [rbx], xmm0
0x18000b89d  add     rsp, 20h
0x18000b8a1  pop     rbx
0x18000b8a2  retn
```
