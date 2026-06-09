# REQUEST_FILTER_CONFIG::REQUEST_FILTER_CONFIG(void)

- ea: `0x180005460`
- end: `0x18000550f`
- name: `??0REQUEST_FILTER_CONFIG@@QEAA@XZ`
- size: `175`
- prototype: `REQUEST_FILTER_CONFIG *__fastcall(REQUEST_FILTER_CONFIG *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800010c0`

## callees

- `0x180005520`

## import_xrefs

- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005477`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005481`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054a8`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054b5`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054c2`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054cf`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054dc`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005477`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005481`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054a8`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054b5`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054c2`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054cf`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800054dc`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x18000548e`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x18000549b`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x18000548e`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x18000549b`

## pseudocode

```c
REQUEST_FILTER_CONFIG *__fastcall REQUEST_FILTER_CONFIG::REQUEST_FILTER_CONFIG(REQUEST_FILTER_CONFIG *this)
{
  *(_QWORD *)this = &REQUEST_FILTER_CONFIG::`vftable';
  MULTISZ::MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 56));
  MULTISZ::MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 112));
  MULTISZA::MULTISZA((REQUEST_FILTER_CONFIG *)((char *)this + 168));
  MULTISZA::MULTISZA((REQUEST_FILTER_CONFIG *)((char *)this + 224));
  MULTISZ::MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 280));
  MULTISZ::MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 336));
  MULTISZ::MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 392));
  MULTISZ::MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 448));
  MULTISZ::MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 504));
  *((_QWORD *)this + 70) = 0;
  *((_DWORD *)this + 142) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 146) = 0;
  REQUEST_FILTER_CONFIG::Reset(this);
  return this;
}

```

## disassembly

```asm
0x180005460  push    rbx
0x180005462  sub     rsp, 20h
0x180005466  lea     rax, ??_7REQUEST_FILTER_CONFIG@@6B@; const REQUEST_FILTER_CONFIG::`vftable'
0x18000546d  mov     rbx, rcx
0x180005470  mov     [rcx], rax
0x180005473  add     rcx, 38h ; '8'
0x180005477  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000547d  lea     rcx, [rbx+70h]
0x180005481  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180005487  lea     rcx, [rbx+0A8h]
0x18000548e  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x180005494  lea     rcx, [rbx+0E0h]
0x18000549b  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x1800054a1  lea     rcx, [rbx+118h]
0x1800054a8  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800054ae  lea     rcx, [rbx+150h]
0x1800054b5  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800054bb  lea     rcx, [rbx+188h]
0x1800054c2  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800054c8  lea     rcx, [rbx+1C0h]
0x1800054cf  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800054d5  lea     rcx, [rbx+1F8h]
0x1800054dc  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800054e2  xor     eax, eax
0x1800054e4  mov     rcx, rbx; this
0x1800054e7  mov     [rbx+230h], rax
0x1800054ee  mov     [rbx+238h], eax
0x1800054f4  mov     [rbx+240h], rax
0x1800054fb  mov     [rbx+248h], eax
0x180005501  call    ?Reset@REQUEST_FILTER_CONFIG@@AEAAXXZ; REQUEST_FILTER_CONFIG::Reset(void)
0x180005506  mov     rax, rbx
0x180005509  add     rsp, 20h
0x18000550d  pop     rbx
0x18000550e  retn
```
