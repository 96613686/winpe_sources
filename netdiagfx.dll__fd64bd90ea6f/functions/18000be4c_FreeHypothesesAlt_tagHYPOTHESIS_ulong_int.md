# FreeHypothesesAlt(tagHYPOTHESIS *,ulong,int)

- ea: `0x18000be4c`
- end: `0x18000be89`
- name: `?FreeHypothesesAlt@@YAXPEAUtagHYPOTHESIS@@KH@Z`
- size: `61`
- prototype: `void __fastcall(struct tagHYPOTHESIS *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008ccc`

## callees

- `0x18000be4c`
- `0x18002b550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be78`

## pseudocode

```c
void __fastcall FreeHypothesesAlt(struct tagHYPOTHESIS *a1, unsigned int a2, int a3)
{
  if ( a1 && a2 )
  {
    FreeHypothesesEmbeddedMemory(a2, a1);
    if ( a3 )
      CoTaskMemFree(a1);
  }
}

```

## disassembly

```asm
0x18000be4c  test    rcx, rcx
0x18000be4f  jz      short locret_18000BE88
0x18000be51  mov     [rsp+arg_0], rbx
0x18000be56  push    rdi
0x18000be57  sub     rsp, 20h
0x18000be5b  mov     eax, edx
0x18000be5d  mov     edi, r8d
0x18000be60  mov     rbx, rcx
0x18000be63  test    eax, eax
0x18000be65  jz      short loc_18000BE7E
0x18000be67  mov     rdx, rcx; struct tagHYPOTHESIS *
0x18000be6a  mov     ecx, eax; unsigned int
0x18000be6c  call    ?FreeHypothesesEmbeddedMemory@@YAXKPEAUtagHYPOTHESIS@@@Z; FreeHypothesesEmbeddedMemory(ulong,tagHYPOTHESIS *)
0x18000be71  test    edi, edi
0x18000be73  jz      short loc_18000BE7E
0x18000be75  mov     rcx, rbx; pv
0x18000be78  call    cs:__imp_CoTaskMemFree
0x18000be7e  mov     rbx, [rsp+28h+arg_0]
0x18000be83  add     rsp, 20h
0x18000be87  pop     rdi
0x18000be88  retn
```
