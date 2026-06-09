# CJob::Create(void)

- ea: `0x18000865c`
- end: `0x180008680`
- name: `?Create@CJob@@SAPEAV1@XZ`
- size: `36`
- prototype: `struct CJob *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cf80`
- `0x18000e7f8`
- `0x18000f100`
- `0x18000f510`
- `0x18000f9e0`

## callees

- `0x1800029a8`
- `0x18000865c`
- `0x180009ef8`

## pseudocode

```c
struct CJob *CJob::Create(void)
{
  struct CJob *result; // rax

  result = (struct CJob *)operator new(0x108u);
  if ( result )
    return CJob::CJob(result);
  return result;
}

```

## disassembly

```asm
0x18000865c  sub     rsp, 28h
0x180008660  mov     ecx, 108h; Size
0x180008665  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000866a  test    rax, rax
0x18000866d  jz      short loc_18000867B
0x18000866f  mov     rcx, rax; this
0x180008672  add     rsp, 28h
0x180008676  jmp     ??0CJob@@QEAA@XZ; CJob::CJob(void)
0x18000867b  add     rsp, 28h
0x18000867f  retn
```
