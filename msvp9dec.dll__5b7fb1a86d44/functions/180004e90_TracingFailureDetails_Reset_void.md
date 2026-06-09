# TracingFailureDetails::Reset(void)

- ea: `0x180004e90`
- end: `0x180004ecf`
- name: `?Reset@TracingFailureDetails@@QEAAXXZ`
- size: `63`
- prototype: `void __fastcall(TracingFailureDetails *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026d8`
- `0x1800049b0`
- `0x180004a28`

## callees

- `0x180001cf0`

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
0x180004e90  push    rbx
0x180004e92  sub     rsp, 20h
0x180004e96  mov     rbx, rcx
0x180004e99  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180004e9e  xor     eax, eax
0x180004ea0  xorps   xmm0, xmm0
0x180004ea3  mov     [rbx+7F0h], al
0x180004ea9  mov     [rbx+8F0h], eax
0x180004eaf  mov     [rbx+900h], eax
0x180004eb5  mov     [rbx+8F8h], rax
0x180004ebc  mov     [rbx+904h], al
0x180004ec2  movups  xmmword ptr [rbx+905h], xmm0
0x180004ec9  add     rsp, 20h
0x180004ecd  pop     rbx
0x180004ece  retn
```
