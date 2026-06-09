# Decompress

- ea: `0x180003548`
- end: `0x18000363f`
- name: `Decompress`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180003548`
- `0x180003e04`

## pseudocode

```c
__int64 __fastcall Decompress(__int64 a1, __int64 a2)
{
  __int64 v5; // rbx
  int v6; // r8d
  signed int v7; // r9d
  int v8; // ecx
  int v9; // ecx
  int v10; // edx
  int v11; // eax

  if ( !*(_DWORD *)a1 )
    return 4294967196LL;
  if ( *(int *)a2 < 0 )
    return 1;
  if ( *(_DWORD *)(*(_QWORD *)(a2 + 8) + 20LL) < *(_DWORD *)(a1 + 24) )
    return 4294967095LL;
  v5 = *(_QWORD *)(a2 + 24);
  v6 = *(_DWORD *)(v5 + 8);
  v7 = (((*(_DWORD *)(v5 + 4) * *(unsigned __int16 *)(v5 + 14)) >> 3) + 3) & 0xFFFFFFFC;
  v8 = -v6;
  if ( v6 <= 0 )
  {
    v9 = 0;
  }
  else
  {
    if ( v6 >= 0 )
      v8 = *(_DWORD *)(v5 + 8);
    v9 = v7 * (v8 - 1);
    v7 = -v7;
  }
  if ( *(_DWORD *)(v5 + 4) >= (int)*(unsigned __int16 *)(a1 + 4) && *(int *)(v5 + 4) <= 20000 )
  {
    v10 = *(unsigned __int16 *)(a1 + 6);
    v11 = -v6;
    if ( v6 > 0 )
      v11 = *(_DWORD *)(v5 + 8);
    if ( v11 >= v10 && v11 <= 20000 )
    {
      if ( v9 >= 0 )
      {
        if ( v7 < 0 )
        {
          if ( (unsigned int)(v9 - v7) > *(_DWORD *)(v5 + 20) || v9 + v7 * (v10 - 1) < 0 )
            return 4294967095LL;
          goto LABEL_23;
        }
        if ( (unsigned int)(v9 + v7 * v10) <= *(_DWORD *)(v5 + 20) )
        {
LABEL_23:
          ConvertToRGB(a1, *(_QWORD *)(a2 + 16), *(_DWORD *)(a2 + 32) + v9, v7, v5);
          return 0;
        }
      }
      return 4294967095LL;
    }
  }
  return 4294967290LL;
}

```

## disassembly

```asm
0x180003548  push    rbx
0x18000354a  sub     rsp, 30h
0x18000354e  cmp     dword ptr [rcx], 0
0x180003551  mov     r10, rdx
0x180003554  mov     r11, rcx
0x180003557  jnz     short loc_180003563
0x180003559  mov     eax, 0FFFFFF9Ch
0x18000355e  jmp     loc_18000360B
0x180003563  cmp     dword ptr [rdx], 0
0x180003566  jge     short loc_180003572
0x180003568  mov     eax, 1
0x18000356d  jmp     loc_18000360B
0x180003572  mov     rcx, [rdx+8]
0x180003576  mov     eax, [r11+18h]
0x18000357a  cmp     [rcx+14h], eax
0x18000357d  jb      loc_180003606
0x180003583  mov     rbx, [rdx+18h]
0x180003587  movzx   r9d, word ptr [rbx+0Eh]
0x18000358c  imul    r9d, [rbx+4]
0x180003591  mov     r8d, [rbx+8]
0x180003595  mov     ecx, r8d
0x180003598  sar     r9d, 3
0x18000359c  add     r9d, 3
0x1800035a0  and     r9d, 0FFFFFFFCh
0x1800035a4  neg     ecx
0x1800035a6  jns     short loc_1800035BA
0x1800035a8  test    r8d, r8d
0x1800035ab  cmovns  ecx, r8d
0x1800035af  dec     ecx
0x1800035b1  imul    ecx, r9d
0x1800035b5  neg     r9d
0x1800035b8  jmp     short loc_1800035BC
0x1800035ba  xor     ecx, ecx
0x1800035bc  movzx   eax, word ptr [r11+4]
0x1800035c1  cmp     [rbx+4], eax
0x1800035c4  jl      short loc_180003638
0x1800035c6  cmp     dword ptr [rbx+4], 4E20h
0x1800035cd  jg      short loc_180003638
0x1800035cf  movzx   edx, word ptr [r11+6]
0x1800035d4  mov     eax, r8d
0x1800035d7  neg     eax
0x1800035d9  cmovs   eax, r8d
0x1800035dd  cmp     eax, edx
0x1800035df  jl      short loc_180003638
0x1800035e1  cmp     eax, 4E20h
0x1800035e6  jg      short loc_180003638
0x1800035e8  test    ecx, ecx
0x1800035ea  js      short loc_180003606
0x1800035ec  test    r9d, r9d
0x1800035ef  jns     short loc_180003611
0x1800035f1  mov     eax, ecx
0x1800035f3  sub     eax, r9d
0x1800035f6  cmp     eax, [rbx+14h]
0x1800035f9  ja      short loc_180003606
0x1800035fb  lea     eax, [rdx-1]
0x1800035fe  imul    eax, r9d
0x180003602  add     eax, ecx
0x180003604  jns     short loc_18000361C
0x180003606  mov     eax, 0FFFFFF37h
0x18000360b  add     rsp, 30h
0x18000360f  pop     rbx
0x180003610  retn
0x180003611  imul    edx, r9d
0x180003615  add     edx, ecx
0x180003617  cmp     edx, [rbx+14h]
0x18000361a  ja      short loc_180003606
0x18000361c  mov     rdx, [r10+10h]
0x180003620  movsxd  r8, ecx
0x180003623  mov     rcx, r11
0x180003626  add     r8, [r10+20h]
0x18000362a  mov     [rsp+38h+var_18], rbx
0x18000362f  call    ConvertToRGB
0x180003634  xor     eax, eax
0x180003636  jmp     short loc_18000360B
0x180003638  mov     eax, 0FFFFFFFAh
0x18000363d  jmp     short loc_18000360B
```
