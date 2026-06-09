# scl_ComputeScaling

- ea: `0x14000e074`
- end: `0x14000e117`
- name: `scl_ComputeScaling`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d918`
- `0x1400622d4`

## callees

- `0x14000e074`
- `0x14000e120`
- `0x14000e134`

## pseudocode

```c
__int64 (__fastcall *__fastcall scl_ComputeScaling(_DWORD *a1, unsigned int a2, int a3))()
{
  int v4; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // ecx
  int v8; // edi
  int v9; // ebx
  int v10; // eax

  v4 = mth_CountLowZeros(a3 | a2);
  v7 = v4 - 1;
  v8 = v5 >> (v4 - 1);
  if ( v4 - 1 <= 0 )
    v8 = v5;
  v9 = v6 >> v7;
  if ( v7 <= 0 )
    v9 = v6;
  if ( v8 >= 0x2000000 )
    v9 >>= 6;
  else
    v8 <<= 6;
  *a1 = DWRITE_FixDiv(v8, v9);
  if ( v8 > 0x7FFF )
    return (__int64 (__fastcall *)())&scl_FixRound;
  if ( ((v9 - 1) & v9) != 0 || !v9 )
    v10 = -1;
  else
    v10 = mth_CountLowZeros(v9);
  a1[2] = v8;
  a1[1] = v9;
  if ( v10 < 0 )
    return scl_SRound;
  a1[3] = v10;
  return scl_FRound;
}

```

## disassembly

```asm
0x14000e074  mov     [rsp+arg_0], rbx
0x14000e079  mov     [rsp+arg_8], rsi
0x14000e07e  push    rdi
0x14000e07f  sub     rsp, 20h
0x14000e083  mov     rsi, rcx
0x14000e086  mov     ecx, edx
0x14000e088  or      ecx, r8d; unsigned int
0x14000e08b  call    ?mth_CountLowZeros@@YAHI@Z; mth_CountLowZeros(uint)
0x14000e090  mov     edi, edx
0x14000e092  mov     ebx, r8d
0x14000e095  lea     ecx, [rax-1]
0x14000e098  sar     edi, cl
0x14000e09a  test    ecx, ecx
0x14000e09c  cmovle  edi, edx
0x14000e09f  sar     ebx, cl
0x14000e0a1  test    ecx, ecx
0x14000e0a3  cmovle  ebx, r8d
0x14000e0a7  cmp     edi, 2000000h
0x14000e0ad  jge     short loc_14000E112
0x14000e0af  shl     edi, 6
0x14000e0b2  mov     edx, ebx; int
0x14000e0b4  mov     ecx, edi; int
0x14000e0b6  call    ?DWRITE_FixDiv@@YAHHH@Z; DWRITE_FixDiv(int,int)
0x14000e0bb  mov     [rsi], eax
0x14000e0bd  cmp     edi, 7FFFh
0x14000e0c3  jg      short loc_14000E100
0x14000e0c5  lea     eax, [rbx-1]
0x14000e0c8  test    ebx, eax
0x14000e0ca  jnz     short loc_14000E0FB
0x14000e0cc  test    ebx, ebx
0x14000e0ce  jz      short loc_14000E0FB
0x14000e0d0  mov     ecx, ebx; unsigned int
0x14000e0d2  call    ?mth_CountLowZeros@@YAHI@Z; mth_CountLowZeros(uint)
0x14000e0d7  mov     [rsi+8], edi
0x14000e0da  mov     [rsi+4], ebx
0x14000e0dd  test    eax, eax
0x14000e0df  js      short loc_14000E109
0x14000e0e1  mov     [rsi+0Ch], eax
0x14000e0e4  lea     rax, scl_FRound
0x14000e0eb  mov     rbx, [rsp+28h+arg_0]
0x14000e0f0  mov     rsi, [rsp+28h+arg_8]
0x14000e0f5  add     rsp, 20h
0x14000e0f9  pop     rdi
0x14000e0fa  retn
0x14000e0fb  or      eax, 0FFFFFFFFh
0x14000e0fe  jmp     short loc_14000E0D7
0x14000e100  lea     rax, scl_FixRound
0x14000e107  jmp     short loc_14000E0EB
0x14000e109  lea     rax, scl_SRound
0x14000e110  jmp     short loc_14000E0EB
0x14000e112  sar     ebx, 6
0x14000e115  jmp     short loc_14000E0B2
```
