# EtwpFreeRtBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)

- ea: `0x180010c5c`
- end: `0x180010ce7`
- name: `?EtwpFreeRtBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z`
- size: `139`
- prototype: `void(struct _TRACELOG_CONTEXT *, struct _WMI_BUFFER_HEADER *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000416c`
- `0x18000f384`
- `0x18000fc74`
- `0x18000ff6c`
- `0x180010c00`

## callees

- `0x18000603c`
- `0x180010c5c`

## import_xrefs

- `ntdll!RtlInterlockedClearBitRunEx` at `0x180010cbe`
- `ntdll!RtlInterlockedClearBitRunEx` at `0x180010cbe`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180010cd1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180010cd1`

## pseudocode

```c
void __fastcall EtwpFreeRtBuffer(struct _TRACELOG_CONTEXT *a1, struct _WMI_BUFFER_HEADER *a2)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v5; // r9

  v2 = *((unsigned int *)a1 + 232);
  EtwpRemoveBufferRefEntry(a1, a2);
  v5 = *((_QWORD *)a1 + 117);
  if ( (unsigned __int64)a2 < v5 || (unsigned __int64)a2 >= v5 + *((unsigned int *)a1 + 233) )
    VirtualFree(a2, 0, 0x8000u);
  else
    RtlInterlockedClearBitRunEx(
      (char *)a1 + 944,
      (unsigned int)(((unsigned __int64)a2 - v5) / v2),
      (-(int)v2 & (unsigned int)(v2 + *((_DWORD *)a2 + 12) - 1)) / (unsigned int)v2);
}

```

## disassembly

```asm
0x180010c5c  mov     [rsp+arg_0], rbx
0x180010c61  mov     [rsp+arg_8], rsi
0x180010c66  push    rdi
0x180010c67  sub     rsp, 20h
0x180010c6b  mov     esi, [rcx+3A0h]
0x180010c71  mov     rbx, rdx
0x180010c74  mov     rdi, rcx
0x180010c77  call    ?EtwpRemoveBufferRefEntry@@YAX_KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpRemoveBufferRefEntry(unsigned __int64,_WMI_BUFFER_HEADER *)
0x180010c7c  mov     r9, [rdi+3A8h]
0x180010c83  cmp     rbx, r9
0x180010c86  jb      short loc_180010CC6
0x180010c88  mov     eax, [rdi+3A4h]
0x180010c8e  add     rax, r9
0x180010c91  cmp     rbx, rax
0x180010c94  jnb     short loc_180010CC6
0x180010c96  mov     eax, [rbx+30h]
0x180010c99  xor     edx, edx
0x180010c9b  dec     eax
0x180010c9d  mov     ecx, esi
0x180010c9f  add     eax, esi
0x180010ca1  neg     ecx
0x180010ca3  and     eax, ecx
0x180010ca5  sub     rbx, r9
0x180010ca8  div     esi
0x180010caa  xor     edx, edx
0x180010cac  lea     rcx, [rdi+3B0h]
0x180010cb3  mov     r8d, eax
0x180010cb6  mov     rax, rbx
0x180010cb9  div     rsi
0x180010cbc  mov     edx, eax
0x180010cbe  call    cs:__imp_RtlInterlockedClearBitRunEx
0x180010cc4  jmp     short loc_180010CD7
0x180010cc6  xor     edx, edx; dwSize
0x180010cc8  mov     r8d, 8000h; dwFreeType
0x180010cce  mov     rcx, rbx; lpAddress
0x180010cd1  call    cs:__imp_VirtualFree
0x180010cd7  mov     rbx, [rsp+28h+arg_0]
0x180010cdc  mov     rsi, [rsp+28h+arg_8]
0x180010ce1  add     rsp, 20h
0x180010ce5  pop     rdi
0x180010ce6  retn
```
