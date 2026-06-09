# MIME_MAP_TABLE::~MIME_MAP_TABLE(void)

- ea: `0x180007360`
- end: `0x1800073bb`
- name: `??1MIME_MAP_TABLE@@EEAA@XZ`
- size: `91`
- prototype: `void __fastcall(MIME_MAP_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800073f0`

## callees

- `0x180007360`
- `0x1800073c4`

## pseudocode

```c
void __fastcall MIME_MAP_TABLE::~MIME_MAP_TABLE(MIME_MAP_TABLE *this, unsigned int a2)
{
  __int64 i; // rbx
  MIME_MAP_ENTRY *v4; // rdi
  MIME_MAP_ENTRY *v5; // rcx

  *(_QWORD *)this = &MIME_MAP_TABLE::`vftable';
  for ( i = 0; i != 131; ++i )
  {
    v4 = (MIME_MAP_ENTRY *)*((_QWORD *)this + i + 1);
    *((_QWORD *)this + i + 1) = 0;
    while ( v4 )
    {
      v5 = v4;
      v4 = (MIME_MAP_ENTRY *)*((_QWORD *)v4 + 1);
      MIME_MAP_ENTRY::`scalar deleting destructor'(v5, a2);
    }
  }
}

```

## disassembly

```asm
0x180007360  mov     [rsp+arg_0], rbx
0x180007365  mov     [rsp+arg_8], rsi
0x18000736a  push    rdi
0x18000736b  sub     rsp, 20h
0x18000736f  lea     rax, ??_7MIME_MAP_TABLE@@6B@; const MIME_MAP_TABLE::`vftable'
0x180007376  mov     rsi, rcx
0x180007379  mov     [rcx], rax
0x18000737c  xor     ebx, ebx
0x18000737e  mov     rdi, [rsi+rbx*8+8]
0x180007383  mov     qword ptr [rsi+rbx*8+8], 0
0x18000738c  jmp     short loc_18000739A
0x18000738e  mov     rcx, rdi; this
0x180007391  mov     rdi, [rdi+8]
0x180007395  call    ??_GMIME_MAP_ENTRY@@QEAAPEAXI@Z; MIME_MAP_ENTRY::`scalar deleting destructor'(uint)
0x18000739a  test    rdi, rdi
0x18000739d  jnz     short loc_18000738E
0x18000739f  inc     rbx
0x1800073a2  cmp     rbx, 83h
0x1800073a9  jnz     short loc_18000737E
0x1800073ab  mov     rbx, [rsp+28h+arg_0]
0x1800073b0  mov     rsi, [rsp+28h+arg_8]
0x1800073b5  add     rsp, 20h
0x1800073b9  pop     rdi
0x1800073ba  retn
```
