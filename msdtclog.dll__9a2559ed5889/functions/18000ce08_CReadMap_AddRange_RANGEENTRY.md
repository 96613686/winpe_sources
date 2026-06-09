# CReadMap::AddRange(_RANGEENTRY &)

- ea: `0x18000ce08`
- end: `0x18000ce62`
- name: `?AddRange@CReadMap@@QEAAXAEAU_RANGEENTRY@@@Z`
- size: `90`
- prototype: `void __fastcall(CReadMap *__hidden this, struct _RANGEENTRY *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c40`
- `0x180009cd8`

## callees

- `0x18000ce08`

## pseudocode

```c
void __fastcall CReadMap::AddRange(CReadMap *this, struct _RANGEENTRY *a2)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int128 v4; // xmm1

  if ( *((_DWORD *)this + 11)
    && *((_DWORD *)this + 5) == *((_DWORD *)a2 + 2)
    && *((_DWORD *)this + 6) == *((_DWORD *)a2 + 3) )
  {
    *((_DWORD *)this + 4) = *((_DWORD *)a2 + 1);
    v2 = 32LL * *((unsigned int *)this + 2);
    *(_OWORD *)((char *)this + v2 + 48) = *(_OWORD *)((char *)this + 12);
    *(_OWORD *)((char *)this + v2 + 64) = *(_OWORD *)((char *)this + 28);
    *((_DWORD *)this + 11) = 0;
  }
  else
  {
    v3 = 32LL * *((unsigned int *)this + 2);
    v4 = *((_OWORD *)a2 + 1);
    *(_OWORD *)((char *)this + v3 + 48) = *(_OWORD *)a2;
    *(_OWORD *)((char *)this + v3 + 64) = v4;
  }
  ++*((_DWORD *)this + 2);
}

```

## disassembly

```asm
0x18000ce08  cmp     dword ptr [rcx+2Ch], 0
0x18000ce0c  jz      short loc_18000CE46
0x18000ce0e  mov     eax, [rdx+8]
0x18000ce11  cmp     [rcx+14h], eax
0x18000ce14  jnz     short loc_18000CE46
0x18000ce16  mov     eax, [rdx+0Ch]
0x18000ce19  cmp     [rcx+18h], eax
0x18000ce1c  jnz     short loc_18000CE46
0x18000ce1e  mov     eax, [rdx+4]
0x18000ce21  mov     [rcx+10h], eax
0x18000ce24  mov     eax, [rcx+8]
0x18000ce27  movups  xmm0, xmmword ptr [rcx+0Ch]
0x18000ce2b  shl     rax, 5
0x18000ce2f  movups  xmmword ptr [rax+rcx+30h], xmm0
0x18000ce34  movups  xmm1, xmmword ptr [rcx+1Ch]
0x18000ce38  movups  xmmword ptr [rax+rcx+40h], xmm1
0x18000ce3d  mov     dword ptr [rcx+2Ch], 0
0x18000ce44  jmp     short loc_18000CE5E
0x18000ce46  mov     eax, [rcx+8]
0x18000ce49  movups  xmm0, xmmword ptr [rdx]
0x18000ce4c  shl     rax, 5
0x18000ce50  movups  xmm1, xmmword ptr [rdx+10h]
0x18000ce54  movups  xmmword ptr [rax+rcx+30h], xmm0
0x18000ce59  movups  xmmword ptr [rax+rcx+40h], xmm1
0x18000ce5e  inc     dword ptr [rcx+8]
0x18000ce61  retn
```
