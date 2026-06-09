# CSecuritySession::`vector deleting destructor'(uint)

- ea: `0x10043810`
- end: `0x10043834`
- name: `??_ECSecuritySession@@UAEPAXI@Z`
- size: `36`
- prototype: `void *__thiscall(CSecuritySession *__hidden this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x10043810`
- `0x1004cea1`

## pseudocode

```c
CSecuritySession *__thiscall CSecuritySession::`vector deleting destructor'(CSecuritySession *this, char a2)
{
  *(_DWORD *)this = &CSecuritySession::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x10043810  mov     edi, edi
0x10043812  push    ebp
0x10043813  mov     ebp, esp
0x10043815  test    [ebp+arg_0], 1
0x10043819  push    esi
0x1004381a  mov     esi, ecx
0x1004381c  mov     dword ptr [esi], offset ??_7CSecuritySession@@6B@; const CSecuritySession::`vftable'
0x10043822  jz      short loc_1004382D
0x10043824  push    esi; Block
0x10043825  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004382a  add     esp, 4
0x1004382d  mov     eax, esi
0x1004382f  pop     esi
0x10043830  pop     ebp
0x10043831  retn    4
```
