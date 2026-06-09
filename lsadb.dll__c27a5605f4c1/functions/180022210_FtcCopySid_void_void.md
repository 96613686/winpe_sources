# FtcCopySid(void * *,void *)

- ea: `0x180022210`
- end: `0x18002226f`
- name: `?FtcCopySid@@YAEPEAPEAXPEAX@Z`
- size: `95`
- prototype: `unsigned __int8(void **, void *)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002934c`
- `0x1800294ac`
- `0x1800295ac`
- `0x18002970c`
- `0x180029928`

## callees

- `0x180022210`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022241`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022241`
- `ntdll!RtlCopySid` at `0x180022257`
- `ntdll!RtlCopySid` at `0x180022257`
- `ntdll!RtlLengthSid` at `0x180022232`
- `ntdll!RtlLengthSid` at `0x180022232`

## pseudocode

```c
unsigned __int8 __fastcall FtcCopySid(void **a1, void *a2)
{
  ULONG v4; // esi
  HLOCAL v5; // rax

  if ( !a2 )
  {
    *a1 = 0;
LABEL_5:
    LOBYTE(v5) = 1;
    return (unsigned __int8)v5;
  }
  v4 = RtlLengthSid(a2);
  v5 = LocalAlloc(0x40u, v4);
  *a1 = v5;
  if ( v5 )
  {
    RtlCopySid(v4, v5, a2);
    goto LABEL_5;
  }
  return (unsigned __int8)v5;
}

```

## disassembly

```asm
0x180022210  mov     [rsp+arg_0], rbx
0x180022215  mov     [rsp+arg_8], rsi
0x18002221a  push    rdi
0x18002221b  sub     rsp, 20h
0x18002221f  mov     rbx, rdx
0x180022222  mov     rdi, rcx
0x180022225  test    rdx, rdx
0x180022228  jnz     short loc_18002222F
0x18002222a  mov     [rcx], rdx
0x18002222d  jmp     short loc_18002225D
0x18002222f  mov     rcx, rbx; Sid
0x180022232  call    cs:__imp_RtlLengthSid
0x180022238  mov     edx, eax; uBytes
0x18002223a  mov     ecx, 40h ; '@'; uFlags
0x18002223f  mov     esi, eax
0x180022241  call    cs:__imp_LocalAlloc
0x180022247  mov     [rdi], rax
0x18002224a  test    rax, rax
0x18002224d  jz      short loc_18002225F
0x18002224f  mov     r8, rbx; SourceSid
0x180022252  mov     rdx, rax; DestinationSid
0x180022255  mov     ecx, esi; DestinationSidLength
0x180022257  call    cs:__imp_RtlCopySid
0x18002225d  mov     al, 1
0x18002225f  mov     rbx, [rsp+28h+arg_0]
0x180022264  mov     rsi, [rsp+28h+arg_8]
0x180022269  add     rsp, 20h
0x18002226d  pop     rdi
0x18002226e  retn
```
