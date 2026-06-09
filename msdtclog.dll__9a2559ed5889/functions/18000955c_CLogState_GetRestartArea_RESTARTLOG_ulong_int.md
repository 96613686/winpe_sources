# CLogState::GetRestartArea(_RESTARTLOG *,ulong *,int)

- ea: `0x18000955c`
- end: `0x1800095f9`
- name: `?GetRestartArea@CLogState@@QEAAXPEAU_RESTARTLOG@@PEAKH@Z`
- size: `157`
- prototype: `void __fastcall(CLogState *__hidden this, struct _RESTARTLOG *, unsigned int *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042b4`
- `0x180006328`
- `0x180006f8c`
- `0x180008090`

## callees

- `0x18000955c`
- `0x180009b00`

## pseudocode

```c
void __fastcall CLogState::GetRestartArea(CLogState *this, struct _RESTARTLOG *a2, unsigned int *a3, int a4)
{
  unsigned int v4; // eax
  unsigned int v9; // edi
  unsigned int *v10; // rcx

  v4 = *((_DWORD *)this + 16);
  if ( *((_DWORD *)this + 13) < v4 )
  {
    v10 = (unsigned int *)((char *)this + 48);
LABEL_6:
    v4 = *((_DWORD *)this + 13);
    v9 = *v10;
    goto LABEL_7;
  }
  v9 = *((_DWORD *)this + 15);
  if ( *((_DWORD *)this + 13) == v4 )
  {
    v10 = (unsigned int *)((char *)this + 48);
    if ( *v10 < v9 )
      goto LABEL_6;
  }
LABEL_7:
  if ( *((_QWORD *)this + 4) < __PAIR64__(v4, v9) )
  {
    *((_DWORD *)this + 9) = v4;
    CLogState::_FreeSpace(this, v9);
  }
  *(_OWORD *)a2 = *(_OWORD *)((char *)this + 24);
  *((_OWORD *)a2 + 1) = *(_OWORD *)((char *)this + 40);
  *((_OWORD *)a2 + 2) = *(_OWORD *)((char *)this + 56);
  *((_OWORD *)a2 + 3) = *(_OWORD *)((char *)this + 72);
  *((_OWORD *)a2 + 4) = *(_OWORD *)((char *)this + 88);
  *((_DWORD *)a2 + 20) = *((_DWORD *)this + 26);
  if ( !v9 )
    v9 = *(_DWORD *)a2;
  *((_DWORD *)a2 + 2) = v9;
  *a3 = *((_DWORD *)this + 4);
  *((_DWORD *)this + 34) = a4;
}

```

## disassembly

```asm
0x18000955c  push    rbx
0x18000955e  push    rbp
0x18000955f  push    rsi
0x180009560  push    rdi
0x180009561  push    r14
0x180009563  sub     rsp, 20h
0x180009567  mov     eax, [rcx+40h]
0x18000956a  mov     ebp, r9d
0x18000956d  mov     r14, r8
0x180009570  mov     rsi, rdx
0x180009573  mov     rbx, rcx
0x180009576  cmp     [rcx+34h], eax
0x180009579  jb      short loc_18000958A
0x18000957b  mov     edi, [rcx+3Ch]
0x18000957e  jnz     short loc_180009593
0x180009580  add     rcx, 30h ; '0'
0x180009584  cmp     [rcx], edi
0x180009586  jnb     short loc_180009593
0x180009588  jmp     short loc_18000958E
0x18000958a  add     rcx, 30h ; '0'
0x18000958e  mov     eax, [rbx+34h]
0x180009591  mov     edi, [rcx]
0x180009593  cmp     [rbx+24h], eax
0x180009596  jb      short loc_18000959F
0x180009598  jnz     short loc_1800095AC
0x18000959a  cmp     [rbx+20h], edi
0x18000959d  jnb     short loc_1800095AC
0x18000959f  mov     edx, edi; unsigned int
0x1800095a1  mov     [rbx+24h], eax
0x1800095a4  mov     rcx, rbx; this
0x1800095a7  call    ?_FreeSpace@CLogState@@AEAAXK@Z; CLogState::_FreeSpace(ulong)
0x1800095ac  movups  xmm0, xmmword ptr [rbx+18h]
0x1800095b0  movaps  xmmword ptr [rsi], xmm0
0x1800095b3  movups  xmm1, xmmword ptr [rbx+28h]
0x1800095b7  movaps  xmmword ptr [rsi+10h], xmm1
0x1800095bb  movups  xmm0, xmmword ptr [rbx+38h]
0x1800095bf  movaps  xmmword ptr [rsi+20h], xmm0
0x1800095c3  movups  xmm1, xmmword ptr [rbx+48h]
0x1800095c7  movaps  xmmword ptr [rsi+30h], xmm1
0x1800095cb  movups  xmm0, xmmword ptr [rbx+58h]
0x1800095cf  movaps  xmmword ptr [rsi+40h], xmm0
0x1800095d3  mov     eax, [rbx+68h]
0x1800095d6  mov     [rsi+50h], eax
0x1800095d9  test    edi, edi
0x1800095db  jnz     short loc_1800095DF
0x1800095dd  mov     edi, [rsi]
0x1800095df  mov     [rsi+8], edi
0x1800095e2  mov     eax, [rbx+10h]
0x1800095e5  mov     [r14], eax
0x1800095e8  mov     [rbx+88h], ebp
0x1800095ee  add     rsp, 20h
0x1800095f2  pop     r14
0x1800095f4  pop     rdi
0x1800095f5  pop     rsi
0x1800095f6  pop     rbp
0x1800095f7  pop     rbx
0x1800095f8  retn
```
