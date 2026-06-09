# QDIDecompress

- ea: `0x180015c9c`
- end: `0x180015d35`
- name: `QDIDecompress`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800051d0`

## callees

- `0x180015c9c`
- `0x180016288`
- `0x180016a44`

## pseudocode

```c
__int64 __fastcall QDIDecompress(__int64 a1, __int64 a2, int a3, __int64 a4, _DWORD *a5)
{
  if ( *(_DWORD *)a1 != 1128875089 )
    return 2;
  if ( *a5 > *(_DWORD *)(a1 + 24) )
    return 3;
  *(_WORD *)(a1 + 380) = *a5;
  *(_DWORD *)(a1 + 392) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 384) = a4;
  *(_QWORD *)(a1 + 48) = a2;
  *(_DWORD *)(a1 + 44) = a3;
  Arith_Init(a1);
  while ( *(_WORD *)(a1 + 380) )
  {
    if ( *(_DWORD *)(a1 + 40) )
      return 4;
    Lz_NextToken(a1);
  }
  if ( !*(_DWORD *)(a1 + 40) && !*(_DWORD *)(a1 + 392) && !*(_DWORD *)(a1 + 400) )
    return 0;
  return 4;
}

```

## disassembly

```asm
0x180015c9c  mov     [rsp+arg_0], rbx
0x180015ca1  push    rdi
0x180015ca2  sub     rsp, 20h
0x180015ca6  cmp     dword ptr [rcx], 43494451h
0x180015cac  mov     rbx, rcx
0x180015caf  jz      short loc_180015CB8
0x180015cb1  mov     eax, 2
0x180015cb6  jmp     short loc_180015D2A
0x180015cb8  mov     rax, [rsp+28h+arg_20]
0x180015cbd  mov     ecx, [rax]
0x180015cbf  cmp     ecx, [rbx+18h]
0x180015cc2  jbe     short loc_180015CCB
0x180015cc4  mov     eax, 3
0x180015cc9  jmp     short loc_180015D2A
0x180015ccb  xor     edi, edi
0x180015ccd  mov     [rbx+17Ch], cx
0x180015cd4  mov     rcx, rbx
0x180015cd7  mov     [rbx+188h], edi
0x180015cdd  mov     [rbx+28h], edi
0x180015ce0  mov     [rbx+180h], r9
0x180015ce7  mov     [rbx+30h], rdx
0x180015ceb  mov     [rbx+2Ch], r8d
0x180015cef  call    Arith_Init
0x180015cf4  jmp     short loc_180015D03
0x180015cf6  cmp     [rbx+28h], edi
0x180015cf9  jnz     short loc_180015D25
0x180015cfb  mov     rcx, rbx
0x180015cfe  call    Lz_NextToken
0x180015d03  cmp     [rbx+17Ch], di
0x180015d0a  jnz     short loc_180015CF6
0x180015d0c  cmp     [rbx+28h], edi
0x180015d0f  jnz     short loc_180015D25
0x180015d11  cmp     [rbx+188h], edi
0x180015d17  jnz     short loc_180015D25
0x180015d19  cmp     [rbx+190h], edi
0x180015d1f  jnz     short loc_180015D25
0x180015d21  xor     eax, eax
0x180015d23  jmp     short loc_180015D2A
0x180015d25  mov     eax, 4
0x180015d2a  mov     rbx, [rsp+28h+arg_0]
0x180015d2f  add     rsp, 20h
0x180015d33  pop     rdi
0x180015d34  retn
```
