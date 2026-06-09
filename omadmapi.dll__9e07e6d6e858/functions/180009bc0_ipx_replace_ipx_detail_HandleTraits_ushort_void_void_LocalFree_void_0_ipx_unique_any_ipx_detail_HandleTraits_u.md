# ipx::replace<ipx::detail::_HandleTraits<ushort *,void * (*)(void *),&LocalFree(void *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<ushort *,void * (*)(void *),&LocalFree(void *),0>> &)

- ea: `0x180009bc0`
- end: `0x180009bee`
- name: `??$replace@U?$_HandleTraits@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAGAEAV?$unique_any@U?$_HandleTraits@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@detail@ipx@@@0@@Z`
- size: `46`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b26c`
- `0x18000e5d4`
- `0x180016700`
- `0x180016a10`

## callees

- `0x180009bc0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009bd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009bd1`

## pseudocode

```c
void **__fastcall ipx::replace<ipx::detail::_HandleTraits<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>>(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    LocalFree(v2);
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180009bc0  push    rbx
0x180009bc2  sub     rsp, 20h
0x180009bc6  mov     rbx, rcx
0x180009bc9  mov     rcx, [rcx]; hMem
0x180009bcc  test    rcx, rcx
0x180009bcf  jz      short loc_180009BE4
0x180009bd1  call    cs:__imp_LocalFree
0x180009bd8  nop     dword ptr [rax+rax+00h]
0x180009bdd  mov     qword ptr [rbx], 0
0x180009be4  mov     rax, rbx
0x180009be7  add     rsp, 20h
0x180009beb  pop     rbx
0x180009bec  retn
```
