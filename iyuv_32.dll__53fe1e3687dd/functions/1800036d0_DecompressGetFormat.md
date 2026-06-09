# DecompressGetFormat

- ea: `0x1800036d0`
- end: `0x1800037be`
- name: `DecompressGetFormat`
- size: `238`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x1800036d0`
- `0x1800038d4`

## pseudocode

```c
__int64 __fastcall DecompressGetFormat(_DWORD *a1, __int64 a2)
{
  unsigned int v3; // [rsp+20h] [rbp-18h]

  v3 = DecompressQuery(a1, 0);
  if ( v3 )
    return v3;
  if ( !a2 )
    return 40;
  *(_DWORD *)a2 = 40;
  *(_DWORD *)(a2 + 4) = a1[1];
  *(_DWORD *)(a2 + 8) = a1[2];
  *(_WORD *)(a2 + 12) = 1;
  *(_DWORD *)(a2 + 16) = 0;
  *(_DWORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 28) = 0;
  *(_DWORD *)(a2 + 20) = 3 * a1[2] * a1[1];
  *(_WORD *)(a2 + 14) = 24;
  *(_DWORD *)(a2 + 32) = 0;
  *(_DWORD *)(a2 + 36) = 0;
  return 0;
}

```

## disassembly

```asm
0x1800036d0  mov     [rsp+arg_8], rdx
0x1800036d5  mov     [rsp+arg_0], rcx
0x1800036da  sub     rsp, 38h
0x1800036de  mov     [rsp+38h+var_18], 0
0x1800036e6  xor     edx, edx
0x1800036e8  mov     rcx, [rsp+38h+arg_0]
0x1800036ed  call    DecompressQuery
0x1800036f2  mov     [rsp+38h+var_18], eax
0x1800036f6  cmp     [rsp+38h+var_18], 0
0x1800036fb  jz      short loc_180003706
0x1800036fd  mov     eax, [rsp+38h+var_18]
0x180003701  jmp     loc_1800037B9
0x180003706  cmp     [rsp+38h+arg_8], 0
0x18000370c  jnz     short loc_180003718
0x18000370e  mov     eax, 28h ; '('
0x180003713  jmp     loc_1800037B9
0x180003718  mov     rax, [rsp+38h+arg_8]
0x18000371d  mov     dword ptr [rax], 28h ; '('
0x180003723  mov     rax, [rsp+38h+arg_8]
0x180003728  mov     rcx, [rsp+38h+arg_0]
0x18000372d  mov     ecx, [rcx+4]
0x180003730  mov     [rax+4], ecx
0x180003733  mov     rax, [rsp+38h+arg_8]
0x180003738  mov     rcx, [rsp+38h+arg_0]
0x18000373d  mov     ecx, [rcx+8]
0x180003740  mov     [rax+8], ecx
0x180003743  mov     eax, 1
0x180003748  mov     rcx, [rsp+38h+arg_8]
0x18000374d  mov     [rcx+0Ch], ax
0x180003751  mov     rax, [rsp+38h+arg_8]
0x180003756  mov     dword ptr [rax+10h], 0
0x18000375d  mov     rax, [rsp+38h+arg_8]
0x180003762  mov     dword ptr [rax+18h], 0
0x180003769  mov     rax, [rsp+38h+arg_8]
0x18000376e  mov     dword ptr [rax+1Ch], 0
0x180003775  mov     rax, [rsp+38h+arg_0]
0x18000377a  mov     rcx, [rsp+38h+arg_0]
0x18000377f  mov     eax, [rax+4]
0x180003782  imul    eax, [rcx+8]
0x180003786  imul    eax, 3
0x180003789  mov     rcx, [rsp+38h+arg_8]
0x18000378e  mov     [rcx+14h], eax
0x180003791  mov     eax, 18h
0x180003796  mov     rcx, [rsp+38h+arg_8]
0x18000379b  mov     [rcx+0Eh], ax
0x18000379f  mov     rax, [rsp+38h+arg_8]
0x1800037a4  mov     dword ptr [rax+20h], 0
0x1800037ab  mov     rax, [rsp+38h+arg_8]
0x1800037b0  mov     dword ptr [rax+24h], 0
0x1800037b7  xor     eax, eax
0x1800037b9  add     rsp, 38h
0x1800037bd  retn
```
