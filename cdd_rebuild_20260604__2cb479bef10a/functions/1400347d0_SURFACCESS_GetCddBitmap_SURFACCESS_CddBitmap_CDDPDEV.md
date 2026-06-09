# SURFACCESS::GetCddBitmap(SURFACCESS &,CddBitmap * *,CDDPDEV * *)

- ea: `0x1400347d0`
- end: `0x140034831`
- name: `?GetCddBitmap@SURFACCESS@@QEAAEAEAV1@PEAPEAVCddBitmap@@PEAPEAUCDDPDEV@@@Z`
- size: `97`
- prototype: `unsigned __int8 __fastcall(SURFACCESS *__hidden this, struct SURFACCESS *, struct CddBitmap **, struct CDDPDEV **)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140025090`
- `0x1400255b0`
- `0x140025c90`
- `0x1400261a0`
- `0x1400267f0`
- `0x140026d40`
- `0x140027370`

## callees

- `0x1400347d0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x1400347e6`
- `WIN32K!W32GetSessionState` at `0x1400347e6`

## pseudocode

```c
unsigned __int8 __fastcall SURFACCESS::GetCddBitmap(
        struct CddBitmap ***this,
        struct CddBitmap ***a2,
        struct CddBitmap **a3,
        struct CDDPDEV **a4)
{
  struct CddBitmap **v8; // rcx
  struct CddBitmap **v10; // rcx

  if ( this[2] == (struct CddBitmap **)(*(_QWORD *)(W32GetSessionState(this, a2) + 72) + 8LL) )
  {
    v8 = *this;
    *a3 = **this;
    *a4 = v8[2];
    return 1;
  }
  else
  {
    v10 = *a2;
    *a3 = **a2;
    *a4 = v10[2];
    return 0;
  }
}

```

## disassembly

```asm
0x1400347d0  push    rbx
0x1400347d2  push    rsi
0x1400347d3  push    rdi
0x1400347d4  push    r14
0x1400347d6  sub     rsp, 28h
0x1400347da  mov     rbx, r9
0x1400347dd  mov     rdi, r8
0x1400347e0  mov     r14, rdx
0x1400347e3  mov     rsi, rcx
0x1400347e6  call    cs:__imp_W32GetSessionState
0x1400347ed  nop     dword ptr [rax+rax+00h]
0x1400347f2  mov     r10, [rax+48h]
0x1400347f6  add     r10, 8
0x1400347fa  cmp     [rsi+10h], r10
0x1400347fe  jnz     short loc_140034814
0x140034800  mov     rcx, [rsi]
0x140034803  mov     rax, [rcx]
0x140034806  mov     [rdi], rax
0x140034809  mov     rax, [rcx+10h]
0x14003480d  mov     [rbx], rax
0x140034810  mov     al, 1
0x140034812  jmp     short loc_140034826
0x140034814  mov     rcx, [r14]
0x140034817  mov     rax, [rcx]
0x14003481a  mov     [rdi], rax
0x14003481d  mov     rax, [rcx+10h]
0x140034821  mov     [rbx], rax
0x140034824  xor     al, al
0x140034826  add     rsp, 28h
0x14003482a  pop     r14
0x14003482c  pop     rdi
0x14003482d  pop     rsi
0x14003482e  pop     rbx
0x14003482f  retn
```
