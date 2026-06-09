# web::json::json_exception::json_exception(char const * const)

- ea: `0x140006470`
- end: `0x1400064a1`
- name: `??0json_exception@json@web@@QEAA@QEBD@Z`
- size: `49`
- prototype: `web::json::json_exception *__fastcall(web::json::json_exception *this, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140007420`
- `0x140007470`
- `0x140007530`
- `0x1400075b0`
- `0x1400075f0`
- `0x140007630`

## callees

- `0x14001e8f4`

## pseudocode

```c
web::json::json_exception *__fastcall web::json::json_exception::json_exception(
        web::json::json_exception *this,
        const char *a2)
{
  *(_OWORD *)((char *)this + 8) = 0;
  *(_QWORD *)this = &web::json::json_exception::`vftable';
  std::string::string((char *)this + 24, a2);
  return this;
}

```

## disassembly

```asm
0x140006470  mov     [rsp+arg_0], rcx
0x140006475  push    rbx
0x140006476  sub     rsp, 20h
0x14000647a  mov     rbx, rcx
0x14000647d  xorps   xmm0, xmm0
0x140006480  movups  xmmword ptr [rcx+8], xmm0
0x140006484  lea     rax, ??_7json_exception@json@web@@6B@; const web::json::json_exception::`vftable'
0x14000648b  mov     [rcx], rax
0x14000648e  add     rcx, 18h
0x140006492  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140006497  nop
0x140006498  mov     rax, rbx
0x14000649b  add     rsp, 20h
0x14000649f  pop     rbx
0x1400064a0  retn
```
