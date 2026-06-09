# CDirectSoundWaveDownload::UnloadWaveBuffers(void)

- ea: `0x1800193c8`
- end: `0x180019457`
- name: `?UnloadWaveBuffers@CDirectSoundWaveDownload@@AEAAJXZ`
- size: `143`
- prototype: `__int64 __fastcall(CDirectSoundWaveDownload *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000febc`
- `0x180017c60`
- `0x180018324`
- `0x180019af8`

## callees

- `0x1800193c8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectSoundWaveDownload::UnloadWaveBuffers(CDirectSoundWaveDownload *this)
{
  unsigned int v1; // edi
  __int64 i; // rsi
  unsigned int v4; // r14d
  __int64 v5; // rcx

  v1 = 0;
  if ( *((_QWORD *)this + 5) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 9); i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)(*((_QWORD *)this + 5) + 8 * i) )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 64LL))(*((_QWORD *)this + 1));
        v5 = *(_QWORD *)(*((_QWORD *)this + 5) + 8 * i);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        *(_QWORD *)(*((_QWORD *)this + 5) + 8 * i) = 0;
        if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2005397216 )
          v1 = v4;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800193c8  push    rbx
0x1800193ca  push    rbp
0x1800193cb  push    rsi
0x1800193cc  push    rdi
0x1800193cd  push    r12
0x1800193cf  push    r14
0x1800193d1  sub     rsp, 28h
0x1800193d5  xor     edi, edi
0x1800193d7  mov     rbx, rcx
0x1800193da  cmp     [rcx+28h], rdi
0x1800193de  jz      short loc_180019448
0x1800193e0  xor     esi, esi
0x1800193e2  cmp     [rcx+24h], esi
0x1800193e5  jbe     short loc_180019448
0x1800193e7  mov     r12d, 80000000h
0x1800193ed  mov     rax, [rbx+28h]
0x1800193f1  mov     rdx, [rax+rsi*8]
0x1800193f5  test    rdx, rdx
0x1800193f8  jz      short loc_180019441
0x1800193fa  mov     rcx, [rbx+8]
0x1800193fe  mov     rax, [rcx]
0x180019401  mov     rax, [rax+40h]
0x180019405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001940a  mov     r14d, eax
0x18001940d  mov     rax, [rbx+28h]
0x180019411  mov     rcx, [rax+rsi*8]
0x180019415  mov     rax, [rcx]
0x180019418  mov     rax, [rax+10h]
0x18001941c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019421  mov     rax, [rbx+28h]
0x180019425  mov     qword ptr [rax+rsi*8], 0
0x18001942d  lea     eax, [r14+r12]
0x180019431  test    r12d, eax
0x180019434  jnz     short loc_180019441
0x180019436  cmp     r14d, 88781120h
0x18001943d  cmovnz  edi, r14d
0x180019441  inc     esi
0x180019443  cmp     esi, [rbx+24h]
0x180019446  jb      short loc_1800193ED
0x180019448  mov     eax, edi
0x18001944a  add     rsp, 28h
0x18001944e  pop     r14
0x180019450  pop     r12
0x180019452  pop     rdi
0x180019453  pop     rsi
0x180019454  pop     rbp
0x180019455  pop     rbx
0x180019456  retn
```
