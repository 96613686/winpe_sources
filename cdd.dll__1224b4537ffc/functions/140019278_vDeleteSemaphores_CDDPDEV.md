# vDeleteSemaphores(CDDPDEV *)

- ea: `0x140019278`
- end: `0x140019316`
- name: `?vDeleteSemaphores@@YAXPEAUCDDPDEV@@@Z`
- size: `158`
- prototype: `void __fastcall(struct CDDPDEV *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140028a40`

## callees

- `0x140019278`

## import_xrefs

- `WIN32K!EngDeleteSemaphore` at `0x14001929c`
- `WIN32K!EngDeleteSemaphore` at `0x1400192d2`
- `WIN32K!EngDeleteSemaphore` at `0x140019305`
- `WIN32K!EngDeleteSemaphore` at `0x14001929c`
- `WIN32K!EngDeleteSemaphore` at `0x1400192d2`
- `WIN32K!EngDeleteSemaphore` at `0x140019305`
- `WIN32K!EngFreeMem` at `0x1400192f7`
- `WIN32K!EngFreeMem` at `0x1400192f7`

## pseudocode

```c
void __fastcall vDeleteSemaphores(struct CDDPDEV *a1)
{
  HSEMAPHORE v2; // rcx
  HSEMAPHORE v3; // rcx
  void *v4; // rcx
  __int64 v5; // rbx
  __int64 i; // rsi
  HSEMAPHORE v7; // rcx

  v2 = (HSEMAPHORE)*((_QWORD *)a1 + 365);
  if ( v2 )
    EngDeleteSemaphore(v2);
  v3 = (HSEMAPHORE)*((_QWORD *)a1 + 448);
  if ( v3 )
    EngDeleteSemaphore(v3);
  v4 = (void *)*((_QWORD *)a1 + 449);
  if ( v4 )
    EngFreeMem(v4);
  v5 = 0;
  do
  {
    for ( i = 0; i != 9; ++i )
    {
      v7 = (HSEMAPHORE)*((_QWORD *)a1 + 8 * v5 + i + (unsigned int)v5 + 366);
      if ( v7 )
        EngDeleteSemaphore(v7);
    }
    v5 = (unsigned int)(v5 + 1);
  }
  while ( (unsigned int)v5 < 9 );
}

```

## disassembly

```asm
0x140019278  push    rbx
0x14001927a  push    rbp
0x14001927b  push    rsi
0x14001927c  push    rdi
0x14001927d  sub     rsp, 28h
0x140019281  mov     rdi, rcx
0x140019284  mov     rcx, [rcx+0B68h]; hsem
0x14001928b  test    rcx, rcx
0x14001928e  jnz     short loc_140019305
0x140019290  mov     rcx, [rdi+0E00h]; hsem
0x140019297  test    rcx, rcx
0x14001929a  jz      short loc_1400192A8
0x14001929c  call    cs:__imp_EngDeleteSemaphore
0x1400192a3  nop     dword ptr [rax+rax+00h]
0x1400192a8  mov     rcx, [rdi+0E08h]; pv
0x1400192af  test    rcx, rcx
0x1400192b2  jnz     short loc_1400192F7
0x1400192b4  xor     ebx, ebx
0x1400192b6  mov     eax, ebx
0x1400192b8  lea     rbp, ds:16Eh[rbx*8]
0x1400192c0  add     rbp, rax
0x1400192c3  xor     esi, esi
0x1400192c5  lea     rax, [rsi+rbp]
0x1400192c9  mov     rcx, [rdi+rax*8]; hsem
0x1400192cd  test    rcx, rcx
0x1400192d0  jz      short loc_1400192DE
0x1400192d2  call    cs:__imp_EngDeleteSemaphore
0x1400192d9  nop     dword ptr [rax+rax+00h]
0x1400192de  inc     rsi
0x1400192e1  cmp     rsi, 9
0x1400192e5  jnz     short loc_1400192C5
0x1400192e7  inc     ebx
0x1400192e9  cmp     ebx, esi
0x1400192eb  jb      short loc_1400192B6
0x1400192ed  add     rsp, 28h
0x1400192f1  pop     rdi
0x1400192f2  pop     rsi
0x1400192f3  pop     rbp
0x1400192f4  pop     rbx
0x1400192f5  retn
0x1400192f7  call    cs:__imp_EngFreeMem
0x1400192fe  nop     dword ptr [rax+rax+00h]
0x140019303  jmp     short loc_1400192B4
0x140019305  call    cs:__imp_EngDeleteSemaphore
0x14001930c  nop     dword ptr [rax+rax+00h]
0x140019311  jmp     loc_140019290
```
