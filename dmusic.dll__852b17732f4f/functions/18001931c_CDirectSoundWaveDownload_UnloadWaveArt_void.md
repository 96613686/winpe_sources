# CDirectSoundWaveDownload::UnloadWaveArt(void)

- ea: `0x18001931c`
- end: `0x1800193bf`
- name: `?UnloadWaveArt@CDirectSoundWaveDownload@@AEAAJXZ`
- size: `163`
- prototype: `__int64 __fastcall(CDirectSoundWaveDownload *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000febc`
- `0x180017c60`
- `0x180017fb4`
- `0x180019af8`

## callees

- `0x18001931c`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectSoundWaveDownload::UnloadWaveArt(CDirectSoundWaveDownload *this)
{
  unsigned int v1; // ebx
  __int64 i; // rsi
  unsigned int v4; // r14d
  __int64 v5; // rcx

  v1 = 0;
  if ( *((_QWORD *)this + 7) )
  {
    for ( i = 0;
          (unsigned int)i < *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)this + 48LL) + 2LL);
          i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)(*((_QWORD *)this + 7) + 8 * i) )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 64LL))(*((_QWORD *)this + 1));
        v5 = *(_QWORD *)(*((_QWORD *)this + 7) + 8 * i);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        *(_QWORD *)(*((_QWORD *)this + 7) + 8 * i) = 0;
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
0x18001931c  push    rbx
0x18001931e  push    rbp
0x18001931f  push    rsi
0x180019320  push    rdi
0x180019321  push    r14
0x180019323  push    r15
0x180019325  sub     rsp, 28h
0x180019329  xor     ebx, ebx
0x18001932b  mov     rdi, rcx
0x18001932e  cmp     [rcx+38h], rbx
0x180019332  jz      short loc_1800193B0
0x180019334  mov     rax, [rcx]
0x180019337  xor     esi, esi
0x180019339  mov     rdx, [rax+30h]
0x18001933d  xor     eax, eax
0x18001933f  cmp     ax, [rdx+2]
0x180019343  jnb     short loc_1800193B0
0x180019345  mov     r15d, 80000000h
0x18001934b  mov     rax, [rdi+38h]
0x18001934f  mov     rdx, [rax+rsi*8]
0x180019353  test    rdx, rdx
0x180019356  jz      short loc_18001939F
0x180019358  mov     rcx, [rdi+8]
0x18001935c  mov     rax, [rcx]
0x18001935f  mov     rax, [rax+40h]
0x180019363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019368  mov     r14d, eax
0x18001936b  mov     rax, [rdi+38h]
0x18001936f  mov     rcx, [rax+rsi*8]
0x180019373  mov     rax, [rcx]
0x180019376  mov     rax, [rax+10h]
0x18001937a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001937f  mov     rax, [rdi+38h]
0x180019383  mov     qword ptr [rax+rsi*8], 0
0x18001938b  lea     eax, [r14+r15]
0x18001938f  test    r15d, eax
0x180019392  jnz     short loc_18001939F
0x180019394  cmp     r14d, 88781120h
0x18001939b  cmovnz  ebx, r14d
0x18001939f  mov     rcx, [rdi]
0x1800193a2  inc     esi
0x1800193a4  mov     rdx, [rcx+30h]
0x1800193a8  movzx   ecx, word ptr [rdx+2]
0x1800193ac  cmp     esi, ecx
0x1800193ae  jb      short loc_18001934B
0x1800193b0  mov     eax, ebx
0x1800193b2  add     rsp, 28h
0x1800193b6  pop     r15
0x1800193b8  pop     r14
0x1800193ba  pop     rdi
0x1800193bb  pop     rsi
0x1800193bc  pop     rbp
0x1800193bd  pop     rbx
0x1800193be  retn
```
