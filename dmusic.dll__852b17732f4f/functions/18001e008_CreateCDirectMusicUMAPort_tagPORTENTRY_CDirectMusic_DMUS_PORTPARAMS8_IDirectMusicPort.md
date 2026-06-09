# CreateCDirectMusicUMAPort(tagPORTENTRY *,CDirectMusic *,_DMUS_PORTPARAMS8 *,IDirectMusicPort * *)

- ea: `0x18001e008`
- end: `0x18001e0c2`
- name: `?CreateCDirectMusicUMAPort@@YAJPEAUtagPORTENTRY@@PEAVCDirectMusic@@PEAU_DMUS_PORTPARAMS8@@PEAPEAUIDirectMusicPort@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(struct tagPORTENTRY *, struct CDirectMusic *, struct _DMUS_PORTPARAMS8 *, struct IDirectMusicPort **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800131a0`

## callees

- `0x1800012c4`
- `0x18001d3f8`
- `0x18001d7c8`
- `0x18001e008`
- `0x18001f51c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e039`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e039`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateCDirectMusicUMAPort(
        struct tagPORTENTRY *a1,
        struct CDirectMusic *a2,
        struct _DMUS_PORTPARAMS8 *a3,
        struct IDirectMusicPort **a4)
{
  struct IDirectMusicPort **v4; // rsi
  struct _DMUS_PORTPARAMS8 *v5; // rdi
  CDirectMusicUMAPort *v8; // rax
  CDirectMusicUMAPort *v9; // rbx
  int v10; // edi
  CDirectMusicUMAPort *v12; // [rsp+20h] [rbp-28h]

  v4 = a4;
  v5 = a3;
  v8 = (CDirectMusicUMAPort *)malloc(0x8B10u);
  try
  {
    if ( v8 )
      v9 = CDirectMusicUMAPort::CDirectMusicUMAPort(v8, a1, a2);
    else
      v9 = 0;
    v12 = v9;
  }
  catch ( ... )
  {
    v4 = a4;
    v5 = a3;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = CDirectMusicUMAPort::Init(v9, v5);
    if ( v10 < 0 )
    {
      CDirectMusicUMAPort::~CDirectMusicUMAPort((struct _RTL_CRITICAL_SECTION *)v9);
      operator delete(v9);
    }
    else
    {
      *v4 = (struct IDirectMusicPort *)((char *)v9 + 384);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001e008  mov     [rsp+arg_0], rbx
0x18001e00d  mov     [rsp+arg_18], r9
0x18001e012  mov     [rsp+arg_10], r8
0x18001e017  push    rsi
0x18001e018  push    rdi
0x18001e019  push    r14
0x18001e01b  sub     rsp, 30h
0x18001e01f  mov     rsi, r9
0x18001e022  mov     rdi, r8
0x18001e025  mov     rbx, rdx
0x18001e028  mov     r14, rcx
0x18001e02b  mov     [rsp+48h+var_28], 0
0x18001e034  mov     ecx, 8B10h; Size
0x18001e039  call    cs:__imp_malloc
0x18001e03f  mov     [rsp+48h+var_20], rax
0x18001e044  test    rax, rax
0x18001e047  jz      short loc_18001E05C
0x18001e049  mov     r8, rbx; struct CDirectMusic *
0x18001e04c  mov     rdx, r14; struct tagPORTENTRY *
0x18001e04f  mov     rcx, rax; this
0x18001e052  call    ??0CDirectMusicUMAPort@@QEAA@PEAUtagPORTENTRY@@PEAVCDirectMusic@@@Z; CDirectMusicUMAPort::CDirectMusicUMAPort(tagPORTENTRY *,CDirectMusic *)
0x18001e057  mov     rbx, rax
0x18001e05a  jmp     short loc_18001E05E
0x18001e05c  xor     ebx, ebx
0x18001e05e  mov     [rsp+48h+var_28], rbx
0x18001e063  jmp     short loc_18001E074
0x18001e065  mov     rsi, [rsp+48h+arg_18]
0x18001e06a  mov     rdi, [rsp+48h+arg_10]
0x18001e06f  mov     rbx, [rsp+48h+var_28]
0x18001e074  test    rbx, rbx
0x18001e077  jnz     short loc_18001E080
0x18001e079  mov     edi, 8007000Eh
0x18001e07e  jmp     short loc_18001E0B2
0x18001e080  mov     rdx, rdi; struct _DMUS_PORTPARAMS8 *
0x18001e083  mov     rcx, rbx; this
0x18001e086  call    ?Init@CDirectMusicUMAPort@@QEAAJPEAU_DMUS_PORTPARAMS8@@@Z; CDirectMusicUMAPort::Init(_DMUS_PORTPARAMS8 *)
0x18001e08b  mov     edi, eax
0x18001e08d  test    eax, eax
0x18001e08f  js      short loc_18001E09D
0x18001e091  lea     rcx, [rbx+180h]
0x18001e098  mov     [rsi], rcx
0x18001e09b  jmp     short loc_18001E0B2
0x18001e09d  mov     rcx, rbx; this
0x18001e0a0  call    ??1CDirectMusicUMAPort@@UEAA@XZ; CDirectMusicUMAPort::~CDirectMusicUMAPort(void)
0x18001e0a5  mov     edx, 8B10h; unsigned __int64
0x18001e0aa  mov     rcx, rbx; void *
0x18001e0ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e0b2  mov     eax, edi
0x18001e0b4  mov     rbx, [rsp+48h+arg_0]
0x18001e0b9  add     rsp, 30h
0x18001e0bd  pop     r14
0x18001e0bf  pop     rdi
0x18001e0c0  pop     rsi
0x18001e0c1  retn
```
