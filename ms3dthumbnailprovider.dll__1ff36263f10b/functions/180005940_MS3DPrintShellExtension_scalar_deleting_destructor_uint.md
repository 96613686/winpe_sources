# MS3DPrintShellExtension::`scalar deleting destructor'(uint)

- ea: `0x180005940`
- end: `0x180005995`
- name: `??_GMS3DPrintShellExtension@@UEAAPEAXI@Z`
- size: `85`
- prototype: `void *__fastcall(MS3DPrintShellExtension *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001f44`
- `0x180005940`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x18000596e`
- `ADVAPI32!EventUnregister` at `0x18000596e`

## pseudocode

```c
MS3DPrintShellExtension *__fastcall MS3DPrintShellExtension::`scalar deleting destructor'(
        MS3DPrintShellExtension *this,
        char a2)
{
  __int64 v4; // rax
  REGHANDLE v5; // rcx

  *(_QWORD *)this = &wil::TraceLoggingProvider::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v4 = *((_QWORD *)this + 1);
    v5 = *(_QWORD *)(v4 + 32);
    *(_DWORD *)v4 = 0;
    *(_QWORD *)(v4 + 32) = 0;
    EventUnregister(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005940  mov     [rsp+arg_0], rbx
0x180005945  push    rdi
0x180005946  sub     rsp, 20h
0x18000594a  mov     edi, edx
0x18000594c  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180005953  xor     edx, edx
0x180005955  mov     [rcx], rax
0x180005958  mov     rbx, rcx
0x18000595b  cmp     [rcx+10h], dl
0x18000595e  jz      short loc_180005974
0x180005960  mov     rax, [rcx+8]
0x180005964  mov     rcx, [rax+20h]; RegHandle
0x180005968  mov     [rax], edx
0x18000596a  mov     [rax+20h], rdx
0x18000596e  call    cs:__imp_EventUnregister
0x180005974  test    dil, 1
0x180005978  jz      short loc_180005987
0x18000597a  mov     edx, 20h ; ' '
0x18000597f  mov     rcx, rbx; Block
0x180005982  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005987  mov     rax, rbx
0x18000598a  mov     rbx, [rsp+28h+arg_0]
0x18000598f  add     rsp, 20h
0x180005993  pop     rdi
0x180005994  retn
```
