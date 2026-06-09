# MCICompressGlobal

- ea: `0x180003730`
- end: `0x180003868`
- name: `MCICompressGlobal`
- size: `312`
- prototype: `__int64 __fastcall(__int64, _WORD *, __int64, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800019d0`
- `0x180003340`
- `0x180003870`

## callees

- `0x1800017f8`
- `0x180003730`
- `0x18000bfb0`
- `0x18001b625`

## pseudocode

```c
__int64 __fastcall MCICompressGlobal(__int64 a1, _WORD *a2, __int64 a3, int a4)
{
  int v6; // ecx
  int v7; // ecx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // eax
  unsigned int v11; // edx
  unsigned int v13; // eax
  __int64 v14; // rax
  int v15; // [rsp+40h] [rbp+8h] BYREF

  v15 = 0;
  v6 = *(_WORD *)(a1 + 676) & 0xF;
  if ( !v6 )
  {
    v13 = *(_DWORD *)(a1 + 668);
    if ( *(_DWORD *)(a1 + 660) >= v13 )
    {
      *a2 = v13;
      memcpy_0(*(void **)(a1 + 688), *(const void **)(a1 + 680), (unsigned __int16)v13);
      return 1;
    }
    goto LABEL_15;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    if ( *(_DWORD *)v8 == 1128874829 )
    {
      v9 = *(unsigned int *)(a1 + 668);
      v10 = *(_DWORD *)(v8 + 16);
      if ( (unsigned int)v9 <= v10 )
      {
        v11 = *(_DWORD *)(a1 + 660);
        if ( v11 >= v10 + 12
          && !(unsigned int)NFMcompress(
                              *(_QWORD *)(v8 + 24),
                              *(_QWORD *)(a1 + 680),
                              v9,
                              *(_QWORD *)(a1 + 688),
                              v11,
                              &v15) )
        {
          *a2 = v15;
          return 1;
        }
      }
    }
    goto LABEL_15;
  }
  if ( v7 == 2 )
  {
    if ( !(unsigned int)LCICompress(
                          *(_QWORD *)(a1 + 8),
                          *(_QWORD *)(a1 + 680),
                          *(_DWORD *)(a1 + 668),
                          a4,
                          *(_DWORD *)(a1 + 660),
                          (__int64)&v15) )
    {
      *(_DWORD *)a2 = v15;
      return 1;
    }
LABEL_15:
    v14 = *(_QWORD *)(a1 + 88);
    *(_QWORD *)v14 = 8;
    goto LABEL_16;
  }
  v14 = *(_QWORD *)(a1 + 88);
  *(_QWORD *)v14 = 5;
LABEL_16:
  *(_DWORD *)(v14 + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x180003730  mov     [rsp+arg_8], rbx
0x180003735  push    rdi
0x180003736  sub     rsp, 30h
0x18000373a  mov     rbx, rcx
0x18000373d  mov     [rsp+38h+arg_0], 0
0x180003745  movzx   ecx, word ptr [rcx+2A4h]
0x18000374c  mov     rdi, rdx
0x18000374f  and     ecx, 0Fh
0x180003752  jz      loc_1800037DA
0x180003758  sub     ecx, 1
0x18000375b  jnz     loc_180003806
0x180003761  mov     rcx, [rbx+8]
0x180003765  cmp     dword ptr [rcx], 4349434Dh
0x18000376b  jnz     loc_18000384F
0x180003771  mov     r8d, [rbx+29Ch]
0x180003778  mov     eax, [rcx+10h]
0x18000377b  cmp     r8d, eax
0x18000377e  ja      loc_18000384F
0x180003784  mov     edx, [rbx+294h]
0x18000378a  add     eax, 0Ch
0x18000378d  cmp     edx, eax
0x18000378f  jb      loc_18000384F
0x180003795  mov     r9, [rbx+2B0h]
0x18000379c  lea     rax, [rsp+38h+arg_0]
0x1800037a1  mov     rcx, [rcx+18h]
0x1800037a5  mov     [rsp+38h+var_10], rax
0x1800037aa  mov     [rsp+38h+var_18], edx
0x1800037ae  mov     rdx, [rbx+2A8h]
0x1800037b5  call    NFMcompress
0x1800037ba  test    eax, eax
0x1800037bc  jnz     loc_18000384F
0x1800037c2  movzx   eax, word ptr [rsp+38h+arg_0]
0x1800037c7  mov     [rdi], ax
0x1800037ca  mov     eax, 1
0x1800037cf  mov     rbx, [rsp+38h+arg_8]
0x1800037d4  add     rsp, 30h
0x1800037d8  pop     rdi
0x1800037d9  retn
0x1800037da  mov     eax, [rbx+29Ch]
0x1800037e0  cmp     [rbx+294h], eax
0x1800037e6  jb      short loc_18000384F
0x1800037e8  movzx   eax, ax
0x1800037eb  mov     [rdx], ax
0x1800037ee  mov     r8d, eax; Size
0x1800037f1  mov     rdx, [rbx+2A8h]; Src
0x1800037f8  mov     rcx, [rbx+2B0h]; void *
0x1800037ff  call    memcpy_0
0x180003804  jmp     short loc_1800037CA
0x180003806  cmp     ecx, 2
0x180003809  jnz     short loc_180003842
0x18000380b  mov     r8d, [rbx+29Ch]
0x180003812  lea     rax, [rsp+38h+arg_0]
0x180003817  mov     rdx, [rbx+2A8h]
0x18000381e  mov     rcx, [rbx+8]
0x180003822  mov     [rsp+38h+var_10], rax
0x180003827  mov     eax, [rbx+294h]
0x18000382d  mov     [rsp+38h+var_18], eax
0x180003831  call    LCICompress
0x180003836  test    eax, eax
0x180003838  jnz     short loc_18000384F
0x18000383a  mov     eax, [rsp+38h+arg_0]
0x18000383e  mov     [rdi], eax
0x180003840  jmp     short loc_1800037CA
0x180003842  mov     rax, [rbx+58h]
0x180003846  mov     qword ptr [rax], 5
0x18000384d  jmp     short loc_18000385A
0x18000384f  mov     rax, [rbx+58h]
0x180003853  mov     qword ptr [rax], 8
0x18000385a  mov     dword ptr [rax+8], 1
0x180003861  xor     eax, eax
0x180003863  jmp     loc_1800037CF
```
