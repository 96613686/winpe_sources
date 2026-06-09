# CsrEventWrite

- ea: `0x180007260`
- end: `0x1800072b0`
- name: `CsrEventWrite`
- size: `80`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007060`

## callees

- `0x180007260`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180007278`
- `ntdll!EtwEventEnabled` at `0x180007278`
- `ntdll!EtwEventWrite` at `0x18000729d`

## pseudocode

```c
void __fastcall CsrEventWrite(
        PCEVENT_DESCRIPTOR EventDescriptor,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  if ( CsrTraceHandle )
  {
    if ( EtwEventEnabled(CsrTraceHandle, EventDescriptor) )
      EtwEventWrite(CsrTraceHandle, EventDescriptor, 0, 0, a5, a6, a7, a8);
  }
}

```

## disassembly

```asm
0x180007260  push    rbx
0x180007262  sub     rsp, 20h
0x180007266  mov     rbx, rcx
0x180007269  mov     rcx, cs:CsrTraceHandle; RegHandle
0x180007270  test    rcx, rcx
0x180007273  jz      short loc_1800072A9
0x180007275  mov     rdx, rbx; EventDescriptor
0x180007278  call    cs:__imp_EtwEventEnabled
0x18000727f  nop     dword ptr [rax+rax+00h]
0x180007284  test    al, al
0x180007286  jz      short loc_1800072A9
0x180007288  mov     rcx, cs:CsrTraceHandle
0x18000728f  xor     r9d, r9d
0x180007292  xor     r8d, r8d
0x180007295  mov     rdx, rbx
0x180007298  add     rsp, 20h
0x18000729c  pop     rbx
0x18000729d  jmp     cs:__imp_EtwEventWrite
0x1800072a9  add     rsp, 20h
0x1800072ad  pop     rbx
0x1800072ae  retn
```
