# REQUEST_FILTER_CONFIG::~REQUEST_FILTER_CONFIG(void)

- ea: `0x180007130`
- end: `0x1800071bd`
- name: `??1REQUEST_FILTER_CONFIG@@AEAA@XZ`
- size: `141`
- prototype: `void __fastcall(REQUEST_FILTER_CONFIG *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800071d0`

## callees

- `0x180005520`

## import_xrefs

- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180007190`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x18000719d`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180007190`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x18000719d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000714f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000715c`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007169`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007176`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007183`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800071a7`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000714f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000715c`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007169`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007176`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007183`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800071a7`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800071b6`

## pseudocode

```c
void __fastcall REQUEST_FILTER_CONFIG::~REQUEST_FILTER_CONFIG(REQUEST_FILTER_CONFIG *this)
{
  *(_QWORD *)this = &REQUEST_FILTER_CONFIG::`vftable';
  REQUEST_FILTER_CONFIG::Reset(this);
  MULTISZ::~MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 504));
  MULTISZ::~MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 448));
  MULTISZ::~MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 392));
  MULTISZ::~MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 336));
  MULTISZ::~MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 280));
  MULTISZA::~MULTISZA((REQUEST_FILTER_CONFIG *)((char *)this + 224));
  MULTISZA::~MULTISZA((REQUEST_FILTER_CONFIG *)((char *)this + 168));
  MULTISZ::~MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 112));
  MULTISZ::~MULTISZ((REQUEST_FILTER_CONFIG *)((char *)this + 56));
}

```

## disassembly

```asm
0x180007130  push    rbx
0x180007132  sub     rsp, 20h
0x180007136  lea     rax, ??_7REQUEST_FILTER_CONFIG@@6B@; const REQUEST_FILTER_CONFIG::`vftable'
0x18000713d  mov     rbx, rcx
0x180007140  mov     [rcx], rax
0x180007143  call    ?Reset@REQUEST_FILTER_CONFIG@@AEAAXXZ; REQUEST_FILTER_CONFIG::Reset(void)
0x180007148  lea     rcx, [rbx+1F8h]
0x18000714f  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007155  lea     rcx, [rbx+1C0h]
0x18000715c  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007162  lea     rcx, [rbx+188h]
0x180007169  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000716f  lea     rcx, [rbx+150h]
0x180007176  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000717c  lea     rcx, [rbx+118h]
0x180007183  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007189  lea     rcx, [rbx+0E0h]
0x180007190  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x180007196  lea     rcx, [rbx+0A8h]
0x18000719d  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x1800071a3  lea     rcx, [rbx+70h]
0x1800071a7  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800071ad  lea     rcx, [rbx+38h]
0x1800071b1  add     rsp, 20h
0x1800071b5  pop     rbx
0x1800071b6  jmp     cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
```
