# BFOpenStream(x,x,x)

- ea: `0x10026030`
- end: `0x100260b6`
- name: `_BFOpenStream@12`
- size: `134`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10010790`
- `0x10011010`
- `0x10011730`

## callees

- `0x10025bee`
- `0x10025c47`
- `0x10026030`
- `0x10035b40`

## pseudocode

```c
int __fastcall BFOpenStream(_DWORD *a1, int a2, char a3)
{
  int v4; // ecx
  int v6; // eax

  v4 = a1[7];
  if ( !v4 )
    return -13;
  if ( a1[8] )
    return -10;
  if ( (*(int (__thiscall **)(_DWORD, int, int, _DWORD, int, _DWORD, _DWORD *))(*(_DWORD *)v4 + 16))(
         *(_DWORD *)(*(_DWORD *)v4 + 16),
         v4,
         a2,
         0,
         a3 & 2 | 0x10,
         0,
         a1 + 8) )
  {
    return -9;
  }
  v6 = a1[1];
  a1[16] = 65000;
  a1[21] = 0;
  a1[20] = 0;
  *a1 = 0;
  a1[2] = v6;
  OSSetFilePosition((int)a1, 2u, 0);
  OSGetFilePosition((int)a1, a1 + 22);
  OSSetFilePosition((int)a1, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x10026030  mov     edi, edi
0x10026032  push    ebp
0x10026033  mov     ebp, esp
0x10026035  push    ebx
0x10026036  push    esi
0x10026037  push    edi
0x10026038  mov     edi, ecx
0x1002603a  mov     ecx, [edi+1Ch]
0x1002603d  test    ecx, ecx
0x1002603f  jnz     short loc_10026046
0x10026041  push    0FFFFFFF3h
0x10026043  pop     eax
0x10026044  jmp     short loc_100260AF
0x10026046  lea     eax, [edi+20h]
0x10026049  xor     ebx, ebx
0x1002604b  cmp     [eax], ebx
0x1002604d  jz      short loc_10026053
0x1002604f  push    0FFFFFFF6h
0x10026051  jmp     short loc_10026043
0x10026053  mov     esi, [ecx]
0x10026055  push    eax
0x10026056  mov     eax, [ebp+arg_0]
0x10026059  push    ebx
0x1002605a  mov     esi, [esi+10h]
0x1002605d  and     eax, 2
0x10026060  or      eax, 10h
0x10026063  push    eax
0x10026064  push    ebx
0x10026065  push    edx
0x10026066  push    ecx
0x10026067  mov     ecx, esi
0x10026069  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002606f  call    esi
0x10026071  test    eax, eax
0x10026073  jz      short loc_10026079
0x10026075  push    0FFFFFFF7h
0x10026077  jmp     short loc_10026043
0x10026079  mov     eax, [edi+4]
0x1002607c  mov     ecx, edi
0x1002607e  push    ebx
0x1002607f  push    2
0x10026081  pop     edx
0x10026082  mov     dword ptr [edi+40h], 0FDE8h
0x10026089  mov     [edi+54h], ebx
0x1002608c  mov     [edi+50h], ebx
0x1002608f  mov     [edi], ebx
0x10026091  mov     [edi+8], eax
0x10026094  call    OSSetFilePosition
0x10026099  lea     edx, [edi+58h]
0x1002609c  mov     ecx, edi
0x1002609e  call    OSGetFilePosition
0x100260a3  push    ebx
0x100260a4  xor     edx, edx
0x100260a6  mov     ecx, edi
0x100260a8  call    OSSetFilePosition
0x100260ad  xor     eax, eax
0x100260af  pop     edi
0x100260b0  pop     esi
0x100260b1  pop     ebx
0x100260b2  pop     ebp
0x100260b3  retn    4
```
