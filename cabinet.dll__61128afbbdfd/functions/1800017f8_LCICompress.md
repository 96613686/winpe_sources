# LCICompress

- ea: `0x1800017f8`
- end: `0x180001868`
- name: `LCICompress`
- size: `112`
- prototype: `__int64(__int64, int, unsigned int, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003730`

## callees

- `0x1800017f8`
- `0x180001870`

## pseudocode

```c
__int64 LCICompress(__int64 a1, int a2, unsigned int a3, ...)
{
  bool v3; // zf
  unsigned int v4; // eax
  __int64 v6; // [rsp+58h] [rbp+20h] BYREF
  va_list va; // [rsp+58h] [rbp+20h]
  __int64 v8; // [rsp+60h] [rbp+28h]
  _DWORD *v9; // [rsp+68h] [rbp+30h]
  va_list va1; // [rsp+70h] [rbp+38h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v6 = va_arg(va1, _QWORD);
  v8 = va_arg(va1, _QWORD);
  v9 = va_arg(va1, _DWORD *);
  v3 = *(_DWORD *)a1 == 1128874828;
  LODWORD(v6) = 0;
  if ( !v3 )
    return 2;
  v4 = *(_DWORD *)(a1 + 24);
  if ( a3 > v4 || (unsigned int)v8 < v4 + 6144 )
    return 2;
  if ( (unsigned int)LZX_Encode(*(_QWORD *)(a1 + 32), a2, a3, (unsigned int)va, *(_DWORD *)(a1 + 28)) )
  {
    *v9 = 0;
    return 4;
  }
  else
  {
    *v9 = v6;
    return 0;
  }
}

```

## disassembly

```asm
0x1800017f8  mov     [rsp+arg_18], r9
0x1800017fd  sub     rsp, 38h
0x180001801  cmp     dword ptr [rcx], 4349434Ch
0x180001807  mov     dword ptr [rsp+38h+arg_18], 0
0x18000180f  jnz     short loc_18000185E
0x180001811  mov     eax, [rcx+18h]
0x180001814  cmp     r8d, eax
0x180001817  ja      short loc_18000185E
0x180001819  add     eax, 1800h
0x18000181e  cmp     dword ptr [rsp+38h+arg_20], eax
0x180001822  jb      short loc_18000185E
0x180001824  mov     eax, [rcx+1Ch]
0x180001827  lea     r9, [rsp+38h+arg_18]
0x18000182c  mov     rcx, [rcx+20h]
0x180001830  mov     [rsp+38h+var_18], eax
0x180001834  call    LZX_Encode
0x180001839  test    eax, eax
0x18000183b  jnz     short loc_18000184C
0x18000183d  mov     eax, dword ptr [rsp+38h+arg_18]
0x180001841  mov     rcx, [rsp+38h+arg_28]
0x180001846  mov     [rcx], eax
0x180001848  xor     eax, eax
0x18000184a  jmp     short loc_180001863
0x18000184c  mov     rax, [rsp+38h+arg_28]
0x180001851  mov     dword ptr [rax], 0
0x180001857  mov     eax, 4
0x18000185c  jmp     short loc_180001863
0x18000185e  mov     eax, 2
0x180001863  add     rsp, 38h
0x180001867  retn
```
