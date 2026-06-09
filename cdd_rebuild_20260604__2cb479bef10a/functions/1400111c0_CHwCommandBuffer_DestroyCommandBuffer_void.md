# CHwCommandBuffer::DestroyCommandBuffer(void)

- ea: `0x1400111c0`
- end: `0x140011217`
- name: `?DestroyCommandBuffer@CHwCommandBuffer@@QEAAXXZ`
- size: `87`
- prototype: `void __fastcall(CHwCommandBuffer *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140028a40`
- `0x140029254`
- `0x14002d4b4`

## callees

- `0x1400111c0`
- `0x140011220`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400111f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400111f9`
- `WIN32K!EngFreeMem` at `0x1400111d7`
- `WIN32K!EngFreeMem` at `0x1400111d7`

## pseudocode

```c
void __fastcall CHwCommandBuffer::DestroyCommandBuffer(CHwCommandBuffer *this)
{
  void *v2; // rcx
  void *v3; // rcx

  CHwCommandBuffer::ResetCommandBuffer(this);
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    EngFreeMem(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 267);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    *((_QWORD *)this + 267) = 0;
  }
}

```

## disassembly

```asm
0x1400111c0  push    rbx
0x1400111c2  sub     rsp, 20h
0x1400111c6  mov     rbx, rcx
0x1400111c9  call    ?ResetCommandBuffer@CHwCommandBuffer@@QEAAXXZ; CHwCommandBuffer::ResetCommandBuffer(void)
0x1400111ce  mov     rcx, [rbx+10h]; pv
0x1400111d2  test    rcx, rcx
0x1400111d5  jz      short loc_1400111EB
0x1400111d7  call    cs:__imp_EngFreeMem
0x1400111de  nop     dword ptr [rax+rax+00h]
0x1400111e3  mov     qword ptr [rbx+10h], 0
0x1400111eb  mov     rcx, [rbx+858h]; P
0x1400111f2  test    rcx, rcx
0x1400111f5  jz      short loc_140011210
0x1400111f7  xor     edx, edx; Tag
0x1400111f9  call    cs:__imp_ExFreePoolWithTag
0x140011200  nop     dword ptr [rax+rax+00h]
0x140011205  mov     qword ptr [rbx+858h], 0
0x140011210  add     rsp, 20h
0x140011214  pop     rbx
0x140011215  retn
```
