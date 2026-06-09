# CIISComputer::ADSIInitializeDispatchManager(long)

- ea: `0x1800051a0`
- end: `0x1800051c5`
- name: `?ADSIInitializeDispatchManager@CIISComputer@@UEAAJJ@Z`
- size: `37`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800051a0`

## pseudocode

```c
__int64 __fastcall CIISComputer::ADSIInitializeDispatchManager(CIISComputer *this, unsigned int a2)
{
  __int64 result; // rax

  if ( *((_DWORD *)this + 16) || a2 > 0xFF )
    return 2147500037LL;
  *(_DWORD *)(*((_QWORD *)this + 9) + 52LL) = a2;
  result = 0;
  *((_DWORD *)this + 16) = 1;
  return result;
}

```

## disassembly

```asm
0x1800051a0  cmp     dword ptr [rcx+40h], 0
0x1800051a4  jnz     short loc_1800051AE
0x1800051a6  cmp     edx, 0FFh
0x1800051ac  jbe     short loc_1800051B4
0x1800051ae  mov     eax, 80004005h
0x1800051b3  retn
0x1800051b4  mov     rax, [rcx+48h]
0x1800051b8  mov     [rax+34h], edx
0x1800051bb  xor     eax, eax
0x1800051bd  mov     dword ptr [rcx+40h], 1
0x1800051c4  retn
```
