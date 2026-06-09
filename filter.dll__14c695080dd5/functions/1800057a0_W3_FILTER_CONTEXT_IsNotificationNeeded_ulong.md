# W3_FILTER_CONTEXT::IsNotificationNeeded(ulong)

- ea: `0x1800057a0`
- end: `0x1800057e8`
- name: `?IsNotificationNeeded@W3_FILTER_CONTEXT@@QEAAHK@Z`
- size: `72`
- prototype: `__int64 __fastcall(W3_FILTER_CONTEXT *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d40`
- `0x18000a3e0`
- `0x18000c6a0`

## callees

- `0x1800057a0`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::IsNotificationNeeded(W3_FILTER_CONTEXT *this, unsigned int a2)
{
  _DWORD *v2; // rax
  unsigned int v3; // eax
  __int64 v5; // rax

  if ( *((_DWORD *)this + 64) || (v2 = (_DWORD *)*((_QWORD *)this + 14)) == 0 )
  {
    v5 = 152;
    if ( *((_DWORD *)this + 15) )
      v5 = 148;
    v3 = *(_DWORD *)((char *)this + v5);
    return a2 & v3;
  }
  if ( !v2[4] )
    return 0;
  if ( !*((_DWORD *)this + 15) )
  {
    v3 = v2[18];
    return a2 & v3;
  }
  return a2 & v2[32];
}

```

## disassembly

```asm
0x1800057a0  cmp     dword ptr [rcx+100h], 0
0x1800057a7  jnz     short loc_1800057D0
0x1800057a9  mov     rax, [rcx+70h]
0x1800057ad  test    rax, rax
0x1800057b0  jz      short loc_1800057D0
0x1800057b2  cmp     dword ptr [rax+10h], 0
0x1800057b6  jz      short loc_1800057CD
0x1800057b8  cmp     dword ptr [rcx+3Ch], 0
0x1800057bc  jnz     short loc_1800057C4
0x1800057be  mov     eax, [rax+48h]
0x1800057c1  and     eax, edx
0x1800057c3  retn
0x1800057c4  mov     eax, [rax+80h]
0x1800057ca  and     eax, edx
0x1800057cc  retn
0x1800057cd  xor     eax, eax
0x1800057cf  retn
0x1800057d0  cmp     dword ptr [rcx+3Ch], 0
0x1800057d4  mov     eax, 98h
0x1800057d9  mov     r8d, 94h
0x1800057df  cmovnz  eax, r8d
0x1800057e3  mov     eax, [rax+rcx]
0x1800057e6  jmp     short loc_1800057C1
```
