# AllocAndCopy(ulong,void *)

- ea: `0x180057030`
- end: `0x180057075`
- name: `?AllocAndCopy@@YAPEAXKPEAX@Z`
- size: `69`
- prototype: `void *__fastcall(size_t Size, void *Src)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052a24`
- `0x180052bc8`
- `0x180052c54`

## callees

- `0x180057030`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057046`

## pseudocode

```c
void *__fastcall AllocAndCopy(size_t Size, void *Src)
{
  unsigned int v2; // edi
  void *v4; // rax
  void *v5; // rbx

  v2 = Size;
  v4 = CoTaskMemAlloc((unsigned int)Size);
  v5 = v4;
  if ( v4 )
    memcpy_0(v4, Src, v2);
  return v5;
}

```

## disassembly

```asm
0x180057030  mov     [rsp+arg_0], rbx
0x180057035  mov     [rsp+arg_8], rsi
0x18005703a  push    rdi
0x18005703b  sub     rsp, 20h
0x18005703f  mov     edi, ecx
0x180057041  mov     rsi, rdx
0x180057044  mov     ecx, ecx; cb
0x180057046  call    cs:__imp_CoTaskMemAlloc
0x18005704c  mov     rbx, rax
0x18005704f  test    rax, rax
0x180057052  jz      short loc_180057062
0x180057054  mov     r8d, edi; Size
0x180057057  mov     rdx, rsi; Src
0x18005705a  mov     rcx, rax; void *
0x18005705d  call    memcpy_0
0x180057062  mov     rsi, [rsp+28h+arg_8]
0x180057067  mov     rax, rbx
0x18005706a  mov     rbx, [rsp+28h+arg_0]
0x18005706f  add     rsp, 20h
0x180057073  pop     rdi
0x180057074  retn
```
