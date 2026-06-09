# TracingFailureDetails::Reset(void)

- ea: `0x180008ca0`
- end: `0x180008cdf`
- name: `?Reset@TracingFailureDetails@@QEAAXXZ`
- size: `63`
- prototype: `void __fastcall(TracingFailureDetails *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000854c`
- `0x180008618`
- `0x180008b64`

## callees

- `0x1800082ec`

## pseudocode

```c
void __fastcall TracingFailureDetails::Reset(TracingFailureDetails *this)
{
  CallStackContext::ClearState((GUID *)this);
  *((_BYTE *)this + 2032) = 0;
  *((_DWORD *)this + 572) = 0;
  *((_DWORD *)this + 576) = 0;
  *((_QWORD *)this + 287) = 0;
  *((_BYTE *)this + 2308) = 0;
  *(_OWORD *)((char *)this + 2309) = 0;
}

```

## disassembly

```asm
0x180008ca0  push    rbx
0x180008ca2  sub     rsp, 20h
0x180008ca6  mov     rbx, rcx
0x180008ca9  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180008cae  xor     eax, eax
0x180008cb0  xorps   xmm0, xmm0
0x180008cb3  mov     [rbx+7F0h], al
0x180008cb9  mov     [rbx+8F0h], eax
0x180008cbf  mov     [rbx+900h], eax
0x180008cc5  mov     [rbx+8F8h], rax
0x180008ccc  mov     [rbx+904h], al
0x180008cd2  movups  xmmword ptr [rbx+905h], xmm0
0x180008cd9  add     rsp, 20h
0x180008cdd  pop     rbx
0x180008cde  retn
```
