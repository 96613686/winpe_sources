# CcpConfigRejReceived

- ea: `0x1800251c0`
- end: `0x18002529f`
- name: `CcpConfigRejReceived`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x1800251c0`
- `0x180025738`
- `0x180032454`

## pseudocode

```c
__int64 __fastcall CcpConfigRejReceived(__int64 a1, unsigned __int8 *a2)
{
  _BYTE *v2; // rbx
  int v4; // esi
  unsigned int *v5; // rdi
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  _BYTE Buf1[512]; // [rsp+20h] [rbp-238h] BYREF

  v2 = a2 + 4;
  v4 = (a2[2] << 8) + a2[3] - 4;
  while ( (unsigned int)v4 >= 2 )
  {
    if ( v2[1] < 2u )
      return 722;
    v4 -= (unsigned __int8)v2[1];
    if ( v4 < 0 )
      return 722;
    v5 = (unsigned int *)(a1 + 404);
    result = CcpMakeOption(a1 + 404, (unsigned __int8)*v2, Buf1, 500);
    if ( (_DWORD)result )
      return result;
    if ( memcmp_0(Buf1, v2, (unsigned __int8)v2[1]) )
      return 722;
    if ( *v2 != 0xFF )
    {
      v7 = *v5;
      if ( *v2 )
      {
        if ( *v2 == 18 )
          v8 = v7 & 0xFFFFFFFE;
        else
          v8 = v7 & 0xFFFFFFFB;
      }
      else
      {
        v8 = v7 & 0xFFFFFFFD;
      }
      *v5 = v8;
    }
    v2 += (unsigned __int8)v2[1];
  }
  return *(_DWORD *)(a1 + 404) == 0 ? 0x2DC : 0;
}

```

## disassembly

```asm
0x1800251c0  push    rbx
0x1800251c2  push    rbp
0x1800251c3  push    rsi
0x1800251c4  push    rdi
0x1800251c5  sub     rsp, 238h
0x1800251cc  mov     rax, cs:__security_cookie
0x1800251d3  xor     rax, rsp
0x1800251d6  mov     [rsp+258h+var_38], rax
0x1800251de  movzx   r8d, byte ptr [rdx+2]
0x1800251e3  lea     rbx, [rdx+4]
0x1800251e7  movzx   esi, byte ptr [rdx+3]
0x1800251eb  mov     rbp, rcx
0x1800251ee  shl     r8d, 8
0x1800251f2  add     esi, 0FFFFFFFCh
0x1800251f5  add     esi, r8d
0x1800251f8  cmp     esi, 2
0x1800251fb  jb      short loc_180025272
0x1800251fd  cmp     byte ptr [rbx+1], 2
0x180025201  jb      short loc_18002526B
0x180025203  movzx   eax, byte ptr [rbx+1]
0x180025207  sub     esi, eax
0x180025209  js      short loc_18002526B
0x18002520b  movzx   edx, byte ptr [rbx]
0x18002520e  lea     rdi, [rbp+194h]
0x180025215  mov     rcx, rdi
0x180025218  lea     r8, [rsp+258h+Buf1]
0x18002521d  mov     r9d, 1F4h
0x180025223  call    CcpMakeOption
0x180025228  test    eax, eax
0x18002522a  jnz     short loc_180025283
0x18002522c  movzx   r8d, byte ptr [rbx+1]; Size
0x180025231  lea     rcx, [rsp+258h+Buf1]; Buf1
0x180025236  mov     rdx, rbx; Buf2
0x180025239  call    memcmp_0
0x18002523e  test    eax, eax
0x180025240  jnz     short loc_18002526B
0x180025242  cmp     byte ptr [rbx], 0FEh
0x180025245  ja      short loc_180025262
0x180025247  cmp     byte ptr [rbx], 0
0x18002524a  mov     eax, [rdi]
0x18002524c  jz      short loc_18002525D
0x18002524e  cmp     byte ptr [rbx], 12h
0x180025251  jz      short loc_180025258
0x180025253  and     eax, 0FFFFFFFBh
0x180025256  jmp     short loc_180025260
0x180025258  and     eax, 0FFFFFFFEh
0x18002525b  jmp     short loc_180025260
0x18002525d  and     eax, 0FFFFFFFDh
0x180025260  mov     [rdi], eax
0x180025262  movzx   eax, byte ptr [rbx+1]
0x180025266  add     rbx, rax
0x180025269  jmp     short loc_1800251F8
0x18002526b  mov     eax, 2D2h
0x180025270  jmp     short loc_180025283
0x180025272  mov     eax, [rbp+194h]
0x180025278  neg     eax
0x18002527a  sbb     eax, eax
0x18002527c  not     eax
0x18002527e  and     eax, 2DCh
0x180025283  mov     rcx, [rsp+258h+var_38]
0x18002528b  xor     rcx, rsp; StackCookie
0x18002528e  call    __security_check_cookie
0x180025293  add     rsp, 238h
0x18002529a  pop     rdi
0x18002529b  pop     rsi
0x18002529c  pop     rbp
0x18002529d  pop     rbx
0x18002529e  retn
```
