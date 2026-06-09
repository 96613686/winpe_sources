# ALLOW_LIST::~ALLOW_LIST(void)

- ea: `0x18000203c`
- end: `0x1800020b1`
- name: `??1ALLOW_LIST@@UEAA@XZ`
- size: `117`
- prototype: `void __fastcall(ALLOW_LIST *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002150`

## callees

- `0x18000203c`
- `0x180007010`

## import_xrefs

- `msvcrt!free` at `0x180002093`
- `msvcrt!free` at `0x180002093`

## pseudocode

```c
void __fastcall ALLOW_LIST::~ALLOW_LIST(ALLOW_LIST *this)
{
  __int64 v1; // rsi
  void **v2; // rdi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  v1 = 0;
  v2 = (void **)((char *)this + 8);
  for ( *(_QWORD *)this = &ALLOW_LIST::`vftable'; (unsigned int)v1 < *((_DWORD *)this + 5); v1 = (unsigned int)(v1 + 1) )
  {
    v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)*v2 + v1);
    if ( v4 )
    {
      (**v4)(v4, 1);
      *((_QWORD *)*v2 + v1) = 0;
    }
  }
  if ( *v2 )
  {
    free(*v2);
    *v2 = 0;
  }
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x18000203c  push    rbx
0x18000203e  push    rbp
0x18000203f  push    rsi
0x180002040  push    rdi
0x180002041  sub     rsp, 28h
0x180002045  xor     esi, esi
0x180002047  lea     rax, ??_7ALLOW_LIST@@6B@; const ALLOW_LIST::`vftable'
0x18000204e  lea     rdi, [rcx+8]
0x180002052  mov     rbx, rcx
0x180002055  mov     [rcx], rax
0x180002058  cmp     [rcx+14h], esi
0x18000205b  jbe     short loc_18000208B
0x18000205d  mov     rax, [rdi]
0x180002060  mov     rcx, [rax+rsi*8]
0x180002064  test    rcx, rcx
0x180002067  jz      short loc_180002084
0x180002069  mov     rax, [rcx]
0x18000206c  mov     edx, 1
0x180002071  mov     rax, [rax]
0x180002074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002079  mov     rax, [rdi]
0x18000207c  mov     qword ptr [rax+rsi*8], 0
0x180002084  inc     esi
0x180002086  cmp     esi, [rbx+14h]
0x180002089  jb      short loc_18000205D
0x18000208b  mov     rcx, [rdi]; Block
0x18000208e  test    rcx, rcx
0x180002091  jz      short loc_1800020A0
0x180002093  call    cs:__imp_free
0x180002099  mov     qword ptr [rdi], 0
0x1800020a0  mov     qword ptr [rbx+10h], 0
0x1800020a8  add     rsp, 28h
0x1800020ac  pop     rdi
0x1800020ad  pop     rsi
0x1800020ae  pop     rbp
0x1800020af  pop     rbx
0x1800020b0  retn
```
