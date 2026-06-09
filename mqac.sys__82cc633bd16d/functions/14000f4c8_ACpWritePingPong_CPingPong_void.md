# ACpWritePingPong(CPingPong *,void *)

- ea: `0x14000f4c8`
- end: `0x14000f52e`
- name: `?ACpWritePingPong@@YAJPEAVCPingPong@@PEAX@Z`
- size: `102`
- prototype: `int(struct CPingPong *, void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x14000f950`
- `0x140010470`
- `0x1400104c4`

## import_xrefs

- `ntoskrnl!ZwWriteFile` at `0x14000f51c`
- `ntoskrnl!ZwWriteFile` at `0x14000f51c`

## pseudocode

```c
NTSTATUS __fastcall ACpWritePingPong(struct CPingPong *a1, void *a2)
{
  struct _IO_STATUS_BLOCK v3; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER v4; // [rsp+70h] [rbp+8h] BYREF

  v4.QuadPart = (unsigned __int64)((++*((_DWORD *)a1 + 1) & 1) == 0) << 12;
  v3 = 0;
  return ZwWriteFile(a2, 0, 0, 0, &v3, a1, 0x1000u, &v4, 0);
}

```

## disassembly

```asm
0x14000f4c8  mov     r11, rsp
0x14000f4cb  sub     rsp, 68h
0x14000f4cf  inc     dword ptr [rcx+4]
0x14000f4d2  mov     r10, rdx
0x14000f4d5  mov     eax, [rcx+4]
0x14000f4d8  xorps   xmm0, xmm0
0x14000f4db  not     eax
0x14000f4dd  mov     qword ptr [r11-28h], 0
0x14000f4e5  and     eax, 1
0x14000f4e8  xor     r9d, r9d; ApcContext
0x14000f4eb  shl     rax, 0Ch
0x14000f4ef  xor     r8d, r8d; ApcRoutine
0x14000f4f2  mov     [r11+8], rax
0x14000f4f6  xor     edx, edx; Event
0x14000f4f8  lea     rax, [r11+8]
0x14000f4fc  mov     [r11-30h], rax
0x14000f500  lea     rax, [r11-18h]
0x14000f504  mov     [rsp+68h+Length], 1000h; Length
0x14000f50c  mov     [r11-40h], rcx
0x14000f510  mov     rcx, r10; FileHandle
0x14000f513  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x14000f518  mov     [r11-48h], rax
0x14000f51c  call    cs:__imp_ZwWriteFile
0x14000f523  nop     dword ptr [rax+rax+00h]
0x14000f528  add     rsp, 68h
0x14000f52c  retn
```
