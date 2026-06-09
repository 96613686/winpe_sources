# W3_FILTER_CONTEXT::IsDisableNotificationNeeded(ulong,ulong)

- ea: `0x18000af04`
- end: `0x18000af3f`
- name: `?IsDisableNotificationNeeded@W3_FILTER_CONTEXT@@QEAAHKK@Z`
- size: `59`
- prototype: `__int64 __fastcall(W3_FILTER_CONTEXT *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a20`
- `0x18000af48`

## callees

- `0x18000af04`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000af29`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000af29`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::IsDisableNotificationNeeded(
        W3_FILTER_CONTEXT *this,
        unsigned int a2,
        unsigned int a3)
{
  BUFFER *v3; // rcx

  if ( *((_DWORD *)this + 15) )
    v3 = (W3_FILTER_CONTEXT *)((char *)this + 160);
  else
    v3 = (W3_FILTER_CONTEXT *)((char *)this + 208);
  return a3 & *((_DWORD *)BUFFER::QueryPtr(v3) + a2);
}

```

## disassembly

```asm
0x18000af04  mov     [rsp+arg_0], rbx
0x18000af09  push    rdi
0x18000af0a  sub     rsp, 20h
0x18000af0e  cmp     dword ptr [rcx+3Ch], 0
0x18000af12  mov     ebx, r8d
0x18000af15  mov     edi, edx
0x18000af17  jz      short loc_18000AF22
0x18000af19  add     rcx, 0A0h
0x18000af20  jmp     short loc_18000AF29
0x18000af22  add     rcx, 0D0h
0x18000af29  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000af2f  mov     eax, [rax+rdi*4]
0x18000af32  and     eax, ebx
0x18000af34  mov     rbx, [rsp+28h+arg_0]
0x18000af39  add     rsp, 20h
0x18000af3d  pop     rdi
0x18000af3e  retn
```
