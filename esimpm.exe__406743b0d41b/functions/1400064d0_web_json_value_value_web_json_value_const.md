# web::json::value::value(web::json::value const &)

- ea: `0x1400064d0`
- end: `0x140006524`
- name: `??0value@json@web@@QEAA@AEBV012@@Z`
- size: `84`
- prototype: `web::json::value *__fastcall(web::json::value *this, const struct web::json::value *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002595c`
- `0x1400393ec`
- `0x14003a9d8`
- `0x14003aba0`
- `0x14003adc4`
- `0x14003b25c`
- `0x14003b63c`
- `0x14003b8bc`
- `0x14003ba84`

## callees

- `0x1400064d0`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
web::json::value *__fastcall web::json::value::value(web::json::value *this, const struct web::json::value *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rdx
  web::json::value *v5; // rcx
  web::json::value *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = this;
  v3 = (__int64 *)(***(__int64 (__fastcall ****)(_QWORD, web::json::value **))a2)(*(_QWORD *)a2, &v7);
  v4 = *v3;
  *v3 = 0;
  v5 = v7;
  *(_QWORD *)this = v4;
  if ( v5 )
    (*(void (__fastcall **)(web::json::value *, __int64))(*(_QWORD *)v5 + 192LL))(v5, 1);
  return this;
}

```

## disassembly

```asm
0x1400064d0  mov     [rsp+arg_0], rcx
0x1400064d5  push    rbx
0x1400064d6  sub     rsp, 20h
0x1400064da  mov     rbx, rcx
0x1400064dd  mov     rcx, [rdx]
0x1400064e0  lea     rdx, [rsp+28h+arg_0]
0x1400064e5  mov     rax, [rcx]
0x1400064e8  mov     rax, [rax]
0x1400064eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064f0  mov     rdx, [rax]
0x1400064f3  mov     qword ptr [rax], 0
0x1400064fa  mov     rcx, [rsp+28h+arg_0]
0x1400064ff  mov     [rbx], rdx
0x140006502  test    rcx, rcx
0x140006505  jz      short loc_14000651B
0x140006507  mov     rax, [rcx]
0x14000650a  mov     edx, 1
0x14000650f  mov     rax, [rax+0C0h]
0x140006516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000651b  mov     rax, rbx
0x14000651e  add     rsp, 20h
0x140006522  pop     rbx
0x140006523  retn
```
