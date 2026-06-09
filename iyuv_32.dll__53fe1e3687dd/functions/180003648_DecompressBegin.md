# DecompressBegin

- ea: `0x180003648`
- end: `0x1800036ca`
- name: `DecompressBegin`
- size: `130`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180003648`
- `0x1800038d4`

## pseudocode

```c
__int64 __fastcall DecompressBegin(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int v7; // edx

  if ( !*(_DWORD *)a1 )
  {
    result = DecompressQuery(a2, a3);
    if ( (_DWORD)result )
      return result;
    if ( !a3 )
      return 4294967294LL;
    v7 = a2[2] * a2[1];
    *(_WORD *)(a1 + 4) = *((_WORD *)a2 + 2);
    *(_WORD *)(a1 + 6) = *((_WORD *)a2 + 4);
    *(_DWORD *)(a1 + 12) = 0;
    *(_DWORD *)(a1 + 16) = v7;
    *(_DWORD *)a1 = 1;
    *(_DWORD *)(a1 + 20) = (v7 >> 2) + v7;
    *(_DWORD *)(a1 + 24) = v7 + 2 * (v7 >> 2);
  }
  return 0;
}

```

## disassembly

```asm
0x180003648  mov     [rsp+arg_0], rbx
0x18000364d  mov     [rsp+arg_8], rsi
0x180003652  push    rdi
0x180003653  sub     rsp, 20h
0x180003657  cmp     dword ptr [rcx], 0
0x18000365a  mov     rsi, r8
0x18000365d  mov     rdi, rdx
0x180003660  mov     rbx, rcx
0x180003663  jnz     short loc_1800036B8
0x180003665  mov     rdx, r8
0x180003668  mov     rcx, rdi
0x18000366b  call    DecompressQuery
0x180003670  test    eax, eax
0x180003672  jnz     short loc_1800036BA
0x180003674  test    rsi, rsi
0x180003677  jnz     short loc_180003680
0x180003679  mov     eax, 0FFFFFFFEh
0x18000367e  jmp     short loc_1800036BA
0x180003680  movzx   eax, word ptr [rdi+4]
0x180003684  mov     edx, [rdi+4]
0x180003687  imul    edx, [rdi+8]
0x18000368b  mov     [rbx+4], ax
0x18000368f  movzx   eax, word ptr [rdi+8]
0x180003693  mov     [rbx+6], ax
0x180003697  mov     dword ptr [rbx+0Ch], 0
0x18000369e  mov     ecx, edx
0x1800036a0  mov     [rbx+10h], edx
0x1800036a3  shr     ecx, 2
0x1800036a6  mov     dword ptr [rbx], 1
0x1800036ac  lea     eax, [rcx+rdx]
0x1800036af  mov     [rbx+14h], eax
0x1800036b2  lea     eax, [rdx+rcx*2]
0x1800036b5  mov     [rbx+18h], eax
0x1800036b8  xor     eax, eax
0x1800036ba  mov     rbx, [rsp+28h+arg_0]
0x1800036bf  mov     rsi, [rsp+28h+arg_8]
0x1800036c4  add     rsp, 20h
0x1800036c8  pop     rdi
0x1800036c9  retn
```
