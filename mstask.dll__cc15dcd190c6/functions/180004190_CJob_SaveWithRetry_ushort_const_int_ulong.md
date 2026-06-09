# CJob::SaveWithRetry(ushort const *,int,ulong)

- ea: `0x180004190`
- end: `0x180004218`
- name: `?SaveWithRetry@CJob@@QEAAJPEBGHK@Z`
- size: `136`
- prototype: `__int64 __fastcall(CJob *__hidden this, const unsigned __int16 *, int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dc30`
- `0x18000e010`
- `0x18000e7f8`

## callees

- `0x180004190`
- `0x180004590`

## import_xrefs

- `msvcrt!rand` at `0x1800041c9`
- `msvcrt!rand` at `0x1800041c9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800041f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800041f0`

## pseudocode

```c
__int64 __fastcall CJob::SaveWithRetry(CJob *this, const unsigned __int16 *a2, int a3, DWORD a4)
{
  signed int v4; // ebx
  int i; // edi
  int v10; // eax

  v4 = 0;
  for ( i = 0; i < 3; ++i )
  {
    v4 = CJob::SaveP(this, a2, a3, a4);
    if ( v4 >= 0 )
      return 0;
    v10 = rand();
    Sleep(v10 % 250 + 250);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004190  push    rbx
0x180004192  push    rbp
0x180004193  push    rsi
0x180004194  push    rdi
0x180004195  push    r14
0x180004197  push    r15
0x180004199  sub     rsp, 28h
0x18000419d  xor     ebx, ebx
0x18000419f  mov     esi, r9d
0x1800041a2  xor     edi, edi
0x1800041a4  mov     ebp, r8d
0x1800041a7  mov     r14, rdx
0x1800041aa  mov     r15, rcx
0x1800041ad  cmp     edi, 3
0x1800041b0  jge     short loc_180004209
0x1800041b2  mov     r9d, esi; unsigned int
0x1800041b5  mov     r8d, ebp; int
0x1800041b8  mov     rdx, r14; unsigned __int16 *
0x1800041bb  mov     rcx, r15; this
0x1800041be  call    ?SaveP@CJob@@QEAAJPEBGHK@Z; CJob::SaveP(ushort const *,int,ulong)
0x1800041c3  mov     ebx, eax
0x1800041c5  test    eax, eax
0x1800041c7  jns     short loc_1800041FA
0x1800041c9  call    cs:__imp_rand
0x1800041cf  mov     ecx, eax
0x1800041d1  mov     eax, 10624DD3h
0x1800041d6  imul    ecx
0x1800041d8  sar     edx, 4
0x1800041db  mov     eax, edx
0x1800041dd  shr     eax, 1Fh
0x1800041e0  add     edx, eax
0x1800041e2  imul    eax, edx, 0FAh
0x1800041e8  sub     ecx, eax
0x1800041ea  add     ecx, 0FAh; dwMilliseconds
0x1800041f0  call    cs:__imp_Sleep
0x1800041f6  inc     edi
0x1800041f8  jmp     short loc_1800041AD
0x1800041fa  xor     eax, eax
0x1800041fc  add     rsp, 28h
0x180004200  pop     r15
0x180004202  pop     r14
0x180004204  pop     rdi
0x180004205  pop     rsi
0x180004206  pop     rbp
0x180004207  pop     rbx
0x180004208  retn
0x180004209  mov     eax, ebx
0x18000420b  add     rsp, 28h
0x18000420f  pop     r15
0x180004211  pop     r14
0x180004213  pop     rdi
0x180004214  pop     rsi
0x180004215  pop     rbp
0x180004216  pop     rbx
0x180004217  retn
```
