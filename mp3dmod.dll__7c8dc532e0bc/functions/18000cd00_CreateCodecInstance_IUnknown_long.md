# CreateCodecInstance(IUnknown *,long *)

- ea: `0x18000cd00`
- end: `0x18000cd4a`
- name: `?CreateCodecInstance@@YAPEAVCComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `74`
- prototype: `struct CComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000cd00`
- `0x18000e084`
- `0x18000e2bc`

## pseudocode

```c
struct CComBase *__fastcall CreateCodecInstance(struct IUnknown *a1, int *a2)
{
  CMP3DecoderDMO *v4; // rax

  v4 = (CMP3DecoderDMO *)operator new(0x330u);
  if ( v4 )
    v4 = CMP3DecoderDMO::CMP3DecoderDMO(v4, a1, a2);
  return (struct CComBase *)(((unsigned __int64)v4 + 296) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x18000cd00  mov     [rsp+arg_0], rbx
0x18000cd05  push    rdi
0x18000cd06  sub     rsp, 20h
0x18000cd0a  mov     rdi, rcx
0x18000cd0d  mov     rbx, rdx
0x18000cd10  mov     ecx, 330h; Size
0x18000cd15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cd1a  test    rax, rax
0x18000cd1d  jnz     short loc_18000CD3A
0x18000cd1f  mov     rbx, [rsp+28h+arg_0]
0x18000cd24  lea     rcx, [rax+128h]
0x18000cd2b  neg     rax
0x18000cd2e  sbb     rax, rax
0x18000cd31  and     rax, rcx
0x18000cd34  add     rsp, 20h
0x18000cd38  pop     rdi
0x18000cd39  retn
0x18000cd3a  mov     r8, rbx; int *
0x18000cd3d  mov     rdx, rdi; struct IUnknown *
0x18000cd40  mov     rcx, rax; this
0x18000cd43  call    ??0CMP3DecoderDMO@@QEAA@PEAUIUnknown@@PEAJ@Z; CMP3DecoderDMO::CMP3DecoderDMO(IUnknown *,long *)
0x18000cd48  jmp     short loc_18000CD1F
```
