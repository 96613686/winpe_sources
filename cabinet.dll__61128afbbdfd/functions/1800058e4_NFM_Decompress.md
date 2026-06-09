# NFM_Decompress

- ea: `0x1800058e4`
- end: `0x1800059aa`
- name: `NFM_Decompress`
- size: `198`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800051d0`
- `0x180012960`

## callees

- `0x1800058e4`
- `0x180006c2c`
- `0x180007db0`
- `0x180012124`

## pseudocode

```c
__int64 __fastcall NFM_Decompress(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // eax
  unsigned int v4; // edi
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx

  v2 = *a2;
  v4 = *(_DWORD *)(a1 + 44);
  *(_DWORD *)(a1 + 40) = *a2;
  if ( v2 > v4 )
    *(_DWORD *)(a1 + 40) = v4;
  else
    v4 = v2;
  if ( !v4 )
  {
LABEL_4:
    *a2 = (unsigned __int16)(v4 - *(_WORD *)(a1 + 40));
    return 0;
  }
  v7 = *(_DWORD *)(a1 + 56);
  if ( !v7 )
  {
LABEL_11:
    while ( !*(_DWORD *)a1 && *(_DWORD *)(a1 + 40) )
    {
      v10 = InflateBlock(a1);
      if ( v10 )
        return (unsigned int)(v10 != 3) + 2;
    }
    goto LABEL_4;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    InflateStored(a1, 1);
    goto LABEL_11;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    InflateCodes(a1, *(_QWORD *)(a1 + 72), *(_QWORD *)(a1 + 80), *(_DWORD *)(a1 + 88), *(_DWORD *)(a1 + 92), 1);
    goto LABEL_11;
  }
  if ( v9 == 1 )
  {
    *a2 = 0;
    return 0;
  }
  return 3;
}

```

## disassembly

```asm
0x1800058e4  mov     [rsp+arg_0], rbx
0x1800058e9  mov     [rsp+arg_8], rsi
0x1800058ee  push    rdi
0x1800058ef  sub     rsp, 30h
0x1800058f3  mov     eax, [rdx]
0x1800058f5  mov     rsi, rdx
0x1800058f8  mov     edi, [rcx+2Ch]
0x1800058fb  mov     rbx, rcx
0x1800058fe  mov     [rcx+28h], eax
0x180005901  cmp     eax, edi
0x180005903  ja      short loc_180005969
0x180005905  mov     edi, eax
0x180005907  test    edi, edi
0x180005909  jnz     short loc_180005926
0x18000590b  sub     di, [rbx+28h]
0x18000590f  movzx   eax, di
0x180005912  mov     [rsi], eax
0x180005914  xor     eax, eax
0x180005916  mov     rbx, [rsp+38h+arg_0]
0x18000591b  mov     rsi, [rsp+38h+arg_8]
0x180005920  add     rsp, 30h
0x180005924  pop     rdi
0x180005925  retn
0x180005926  mov     ecx, [rcx+38h]
0x180005929  test    ecx, ecx
0x18000592b  jz      short loc_180005943
0x18000592d  sub     ecx, 1
0x180005930  jz      short loc_18000599B
0x180005932  sub     ecx, 1
0x180005935  jz      short loc_180005976
0x180005937  cmp     ecx, 1
0x18000593a  jz      short loc_18000596E
0x18000593c  mov     eax, 3
0x180005941  jmp     short loc_180005916
0x180005943  cmp     dword ptr [rbx], 0
0x180005946  jnz     short loc_18000590B
0x180005948  cmp     dword ptr [rbx+28h], 0
0x18000594c  jbe     short loc_18000590B
0x18000594e  mov     rcx, rbx
0x180005951  call    InflateBlock
0x180005956  mov     ecx, eax
0x180005958  test    eax, eax
0x18000595a  jz      short loc_180005943
0x18000595c  xor     eax, eax
0x18000595e  cmp     ecx, 3
0x180005961  setnz   al
0x180005964  add     eax, 2
0x180005967  jmp     short loc_180005916
0x180005969  mov     [rcx+28h], edi
0x18000596c  jmp     short loc_180005907
0x18000596e  mov     dword ptr [rdx], 0
0x180005974  jmp     short loc_180005914
0x180005976  mov     eax, [rbx+5Ch]
0x180005979  mov     rcx, rbx
0x18000597c  mov     r9d, [rbx+58h]
0x180005980  mov     r8, [rbx+50h]
0x180005984  mov     rdx, [rbx+48h]
0x180005988  mov     [rsp+38h+var_10], 1
0x180005990  mov     [rsp+38h+var_18], eax
0x180005994  call    InflateCodes
0x180005999  jmp     short loc_180005943
0x18000599b  mov     edx, 1
0x1800059a0  mov     rcx, rbx
0x1800059a3  call    InflateStored
0x1800059a8  jmp     short loc_180005943
```
