# CBusIds::CBusIds(void)

- ea: `0x180002f60`
- end: `0x180002f86`
- name: `??0CBusIds@@QEAA@XZ`
- size: `38`
- prototype: `CBusIds *__fastcall(CBusIds *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180002fb0`

## pseudocode

```c
CBusIds *__fastcall CBusIds::CBusIds(CBusIds *this)
{
  CBusIds *result; // rax

  *((_DWORD *)this + 1) = 0;
  result = this;
  *((_DWORD *)this + 2) = 1;
  *((_DWORD *)this + 3) = 64;
  *((_DWORD *)this + 4) = 65;
  *(_DWORD *)this = 4;
  return result;
}

```

## disassembly

```asm
0x180002f60  mov     dword ptr [rcx+4], 0
0x180002f67  mov     rax, rcx
0x180002f6a  mov     dword ptr [rcx+8], 1
0x180002f71  mov     dword ptr [rcx+0Ch], 40h ; '@'
0x180002f78  mov     dword ptr [rcx+10h], 41h ; 'A'
0x180002f7f  mov     dword ptr [rcx], 4
0x180002f85  retn
```
