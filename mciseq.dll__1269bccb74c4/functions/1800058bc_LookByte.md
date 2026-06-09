# LookByte

- ea: `0x1800058bc`
- end: `0x18000597b`
- name: `LookByte`
- size: `191`
- prototype: `char __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180003dc0`
- `0x180003f18`
- `0x180003f68`
- `0x180003fdc`
- `0x180004588`
- `0x180004cc0`
- `0x180004fa4`

## callees

- `0x1800058bc`
- `0x180007010`

## pseudocode

```c
char __fastcall LookByte(__int64 a1)
{
  __int64 v2; // r9
  unsigned __int64 v3; // rax
  char result; // al
  void (__fastcall *v5)(_QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v6)(_QWORD, _QWORD, _QWORD); // rax
  unsigned __int64 *v7; // rcx

  if ( *(_DWORD *)a1 )
    return 0;
  v2 = *(_QWORD *)(a1 + 48);
  if ( !v2 )
    return 0;
  v3 = *(_QWORD *)(a1 + 24);
  if ( v3 <= *(_QWORD *)(a1 + 32) )
    return *(_BYTE *)v3;
  if ( (*(_BYTE *)(v2 + 12) & 4) == 0 )
  {
    if ( *(_QWORD *)(v2 + 16) )
    {
      v6 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 64);
      *(_QWORD *)(a1 + 40) = 0;
      if ( v6 )
        v6(0, 0, *(_QWORD *)(a1 + 72));
      v7 = *(unsigned __int64 **)(*(_QWORD *)(a1 + 48) + 16LL);
      *(_QWORD *)(a1 + 48) = v7;
      v3 = *v7;
      *(_QWORD *)(a1 + 24) = *v7;
      *(_QWORD *)(a1 + 32) = *((unsigned int *)v7 + 2) + v3 - 1;
      return *(_BYTE *)v3;
    }
    *(_DWORD *)a1 = 350;
    return 0;
  }
  v5 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 64);
  *(_DWORD *)(a1 + 56) = 1;
  if ( v5 )
    v5(0, 0, *(_QWORD *)(a1 + 72));
  result = 47;
  *(_QWORD *)(a1 + 48) = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL);
  return result;
}

```

## disassembly

```asm
0x1800058bc  push    rbx
0x1800058be  sub     rsp, 30h
0x1800058c2  mov     rbx, rcx
0x1800058c5  xor     ecx, ecx
0x1800058c7  cmp     [rbx], ecx
0x1800058c9  jnz     loc_180005973
0x1800058cf  mov     r9, [rbx+30h]
0x1800058d3  test    r9, r9
0x1800058d6  jz      loc_180005973
0x1800058dc  mov     rax, [rbx+18h]
0x1800058e0  cmp     rax, [rbx+20h]
0x1800058e4  ja      short loc_1800058ED
0x1800058e6  mov     al, [rax]
0x1800058e8  jmp     loc_180005975
0x1800058ed  test    byte ptr [r9+0Ch], 4
0x1800058f2  jz      short loc_180005924
0x1800058f4  mov     rax, [rbx+40h]
0x1800058f8  mov     dword ptr [rbx+38h], 1
0x1800058ff  test    rax, rax
0x180005902  jz      short loc_180005914
0x180005904  mov     r8, [rbx+48h]
0x180005908  xor     edx, edx
0x18000590a  mov     [rsp+38h+var_18], rcx
0x18000590f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005914  mov     rax, [rbx+30h]
0x180005918  mov     rcx, [rax+10h]
0x18000591c  mov     al, 2Fh ; '/'
0x18000591e  mov     [rbx+30h], rcx
0x180005922  jmp     short loc_180005975
0x180005924  cmp     [r9+10h], rcx
0x180005928  jz      short loc_18000596D
0x18000592a  mov     rax, [rbx+40h]
0x18000592e  mov     [rbx+28h], rcx
0x180005932  test    rax, rax
0x180005935  jz      short loc_180005947
0x180005937  mov     r8, [rbx+48h]
0x18000593b  xor     edx, edx
0x18000593d  mov     [rsp+38h+var_18], rcx
0x180005942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005947  mov     rax, [rbx+30h]
0x18000594b  mov     rcx, [rax+10h]
0x18000594f  mov     [rbx+30h], rcx
0x180005953  mov     rax, [rcx]
0x180005956  mov     [rbx+18h], rax
0x18000595a  mov     ecx, [rcx+8]
0x18000595d  lea     rdx, [rax-1]
0x180005961  add     rdx, rcx
0x180005964  mov     [rbx+20h], rdx
0x180005968  jmp     loc_1800058E6
0x18000596d  mov     dword ptr [rbx], 15Eh
0x180005973  xor     al, al
0x180005975  add     rsp, 30h
0x180005979  pop     rbx
0x18000597a  retn
```
