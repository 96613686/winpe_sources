# CompressEnd

- ea: `0x180001f30`
- end: `0x180001f51`
- name: `CompressEnd`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180001f30`
- `0x180001f58`

## pseudocode

```c
__int64 __fastcall CompressEnd(_DWORD *a1)
{
  if ( *a1 )
  {
    CompressFree();
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180001f30  push    rbx
0x180001f32  sub     rsp, 20h
0x180001f36  cmp     dword ptr [rcx], 0
0x180001f39  mov     rbx, rcx
0x180001f3c  jz      short loc_180001F49
0x180001f3e  call    CompressFree
0x180001f43  mov     dword ptr [rbx], 0
0x180001f49  xor     eax, eax
0x180001f4b  add     rsp, 20h
0x180001f4f  pop     rbx
0x180001f50  retn
```
