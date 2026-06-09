# CDDBITMAPLOCK::CDDBITMAPLOCK(CddBitmap *)

- ea: `0x14000c010`
- end: `0x14000c09d`
- name: `??0CDDBITMAPLOCK@@QEAA@PEAVCddBitmap@@@Z`
- size: `141`
- prototype: `CDDBITMAPLOCK *(CDDBITMAPLOCK *__hidden this, struct CddBitmap *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000d63c`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`

## callees

- `0x14000c010`
- `0x14000c1cc`
- `0x1400372d0`

## import_xrefs

- `WIN32K!EngAcquireSemaphore` at `0x14000c036`
- `WIN32K!EngAcquireSemaphore` at `0x14000c036`

## pseudocode

```c
CDDBITMAPLOCK *__fastcall CDDBITMAPLOCK::CDDBITMAPLOCK(CDDBITMAPLOCK *this, struct CddBitmap *a2)
{
  HSEMAPHORE v4; // rcx
  CDDBITMAPLOCK *result; // rax

  *((_QWORD *)this + 1) = a2;
  *(_DWORD *)this = 1;
  v4 = (HSEMAPHORE)*((_QWORD *)a2 + 24);
  if ( v4 )
    EngAcquireSemaphore(v4);
  *((_QWORD *)a2 + 67) = KeGetCurrentThread();
  if ( *((_BYTE *)a2 + 133) )
  {
    (*(void (__fastcall **)(struct CddBitmap *))(*(_QWORD *)a2 + 176LL))(a2);
    *((_BYTE *)a2 + 133) = 0;
    CddBitmap::LogGDIContentAfterDX(a2);
  }
  *((_BYTE *)a2 + 132) = 1;
  result = this;
  *((_BYTE *)a2 + 134) = 1;
  return result;
}

```

## disassembly

```asm
0x14000c010  mov     [rsp+arg_0], rbx
0x14000c015  push    rdi
0x14000c016  sub     rsp, 20h
0x14000c01a  mov     rdi, rcx
0x14000c01d  mov     [rcx+8], rdx
0x14000c021  mov     dword ptr [rcx], 1
0x14000c027  mov     rbx, rdx
0x14000c02a  mov     rcx, [rdx+0C0h]; hsem
0x14000c031  test    rcx, rcx
0x14000c034  jz      short loc_14000C042
0x14000c036  call    cs:__imp_EngAcquireSemaphore
0x14000c03d  nop     dword ptr [rax+rax+00h]
0x14000c042  mov     rax, gs:188h
0x14000c04b  mov     [rbx+218h], rax
0x14000c052  movzx   eax, byte ptr [rbx+85h]
0x14000c059  test    al, al
0x14000c05b  jnz     short loc_14000C07A
0x14000c05d  mov     byte ptr [rbx+84h], 1
0x14000c064  mov     rax, rdi
0x14000c067  mov     byte ptr [rbx+86h], 1
0x14000c06e  mov     rbx, [rsp+28h+arg_0]
0x14000c073  add     rsp, 20h
0x14000c077  pop     rdi
0x14000c078  retn
0x14000c07a  mov     rax, [rbx]
0x14000c07d  mov     rcx, rbx
0x14000c080  mov     rax, [rax+0B0h]
0x14000c087  call    _guard_dispatch_icall
0x14000c08c  mov     rcx, rbx; this
0x14000c08f  mov     byte ptr [rbx+85h], 0
0x14000c096  call    ?LogGDIContentAfterDX@CddBitmap@@QEAAXXZ; CddBitmap::LogGDIContentAfterDX(void)
0x14000c09b  jmp     short loc_14000C05D
```
