# IMetricsMaxSizeFormat

- ea: `0x180001940`
- end: `0x180001a2c`
- name: `IMetricsMaxSizeFormat`
- size: `236`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180002540`
- `0x180006f00`
- `0x18000c434`
- `0x18000cfe0`
- `0x18000da50`
- `0x1800102b0`
- `0x180010548`

## callees

- `0x180001940`
- `0x180002220`
- `0x180003ec0`

## pseudocode

```c
__int64 __fastcall IMetricsMaxSizeFormat(__int64 a1, int *a2, unsigned int *a3)
{
  __int64 v3; // rbx
  int *v5; // rdi
  unsigned int v6; // esi
  unsigned int v7; // r9d
  __int64 v8; // rdx
  unsigned int v9; // ecx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  unsigned int v12; // ecx
  __int64 result; // rax
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = a1;
  v5 = a2;
  if ( !a1 )
    v3 = gplag;
  v6 = 0;
  if ( a2 )
  {
    if ( ValidateHandle(a2, 0) )
    {
      if ( *v5 == 1 )
        goto LABEL_16;
      if ( ValidateHandle(v5, 2) )
      {
        v5 = *(int **)(v5 + 5);
LABEL_16:
        v10 = v5[16];
        if ( v10 )
        {
          v11 = 0;
          do
          {
            v12 = *(_DWORD *)(*(_QWORD *)(v5 + 17) + 8 * v11 + 4);
            if ( v12 <= v6 )
              v12 = v6;
            v11 = (unsigned int)(v11 + 1);
            v6 = v12;
          }
          while ( (unsigned int)v11 < v10 );
        }
        goto LABEL_21;
      }
    }
    return 5;
  }
  v14 = 0;
  if ( !(unsigned int)IDriverGetNext(v3, &v14, 0, 0) )
  {
    do
    {
      v7 = *(_DWORD *)(v14 + 64);
      if ( v7 )
      {
        v8 = 0;
        do
        {
          v9 = *(_DWORD *)(*(_QWORD *)(v14 + 68) + 8 * v8 + 4);
          if ( v9 <= v6 )
            v9 = v6;
          v8 = (unsigned int)(v8 + 1);
          v6 = v9;
        }
        while ( (unsigned int)v8 < v7 );
      }
    }
    while ( !(unsigned int)IDriverGetNext(v3, &v14, v14, 0) );
  }
LABEL_21:
  *a3 = v6;
  result = 512;
  if ( v6 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180001940  push    rbx
0x180001942  push    rsi
0x180001943  push    rdi
0x180001944  push    r14
0x180001946  sub     rsp, 28h
0x18000194a  test    rcx, rcx
0x18000194d  mov     rbx, rcx
0x180001950  mov     r14, r8
0x180001953  mov     rdi, rdx
0x180001956  cmovz   rbx, cs:gplag
0x18000195e  xor     esi, esi
0x180001960  test    rdx, rdx
0x180001963  jnz     short loc_1800019C2
0x180001965  xor     r9d, r9d
0x180001968  mov     [rsp+48h+arg_0], rsi
0x18000196d  xor     r8d, r8d
0x180001970  lea     rdx, [rsp+48h+arg_0]
0x180001975  mov     rcx, rbx
0x180001978  call    IDriverGetNext
0x18000197d  test    eax, eax
0x18000197f  jnz     loc_180001A0C
0x180001985  mov     r8, [rsp+48h+arg_0]
0x18000198a  mov     r9d, [r8+40h]
0x18000198e  test    r9d, r9d
0x180001991  jz      short loc_1800019AC
0x180001993  mov     r10, [r8+44h]
0x180001997  xor     edx, edx
0x180001999  mov     ecx, [r10+rdx*8+4]
0x18000199e  cmp     ecx, esi
0x1800019a0  cmovbe  ecx, esi
0x1800019a3  inc     edx
0x1800019a5  mov     esi, ecx
0x1800019a7  cmp     edx, r9d
0x1800019aa  jb      short loc_180001999
0x1800019ac  xor     r9d, r9d
0x1800019af  lea     rdx, [rsp+48h+arg_0]
0x1800019b4  mov     rcx, rbx
0x1800019b7  call    IDriverGetNext
0x1800019bc  test    eax, eax
0x1800019be  jz      short loc_180001985
0x1800019c0  jmp     short loc_180001A0C
0x1800019c2  xor     edx, edx
0x1800019c4  mov     rcx, rdi
0x1800019c7  call    ValidateHandle
0x1800019cc  test    eax, eax
0x1800019ce  jz      short loc_180001A1D
0x1800019d0  cmp     dword ptr [rdi], 1
0x1800019d3  jz      short loc_1800019EA
0x1800019d5  mov     edx, 2
0x1800019da  mov     rcx, rdi
0x1800019dd  call    ValidateHandle
0x1800019e2  test    eax, eax
0x1800019e4  jz      short loc_180001A1D
0x1800019e6  mov     rdi, [rdi+14h]
0x1800019ea  mov     r8d, [rdi+40h]
0x1800019ee  test    r8d, r8d
0x1800019f1  jz      short loc_180001A0C
0x1800019f3  mov     r9, [rdi+44h]
0x1800019f7  xor     edx, edx
0x1800019f9  mov     ecx, [r9+rdx*8+4]
0x1800019fe  cmp     ecx, esi
0x180001a00  cmovbe  ecx, esi
0x180001a03  inc     edx
0x180001a05  mov     esi, ecx
0x180001a07  cmp     edx, r8d
0x180001a0a  jb      short loc_1800019F9
0x180001a0c  xor     ecx, ecx
0x180001a0e  mov     [r14], esi
0x180001a11  test    esi, esi
0x180001a13  mov     eax, 200h
0x180001a18  cmovnz  eax, ecx
0x180001a1b  jmp     short loc_180001A22
0x180001a1d  mov     eax, 5
0x180001a22  add     rsp, 28h
0x180001a26  pop     r14
0x180001a28  pop     rdi
0x180001a29  pop     rsi
0x180001a2a  pop     rbx
0x180001a2b  retn
```
