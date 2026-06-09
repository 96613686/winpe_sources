# GetNtHeader

- ea: `0x180004d10`
- end: `0x180004db2`
- name: `GetNtHeader`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004520`
- `0x180004940`

## callees

- `0x180004d10`

## pseudocode

```c
unsigned __int64 __fastcall GetNtHeader(__int64 a1, unsigned int a2)
{
  unsigned __int64 v2; // r9
  __int64 v3; // r8
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // r10
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx

  v2 = a1 + a2;
  v3 = 0;
  if ( a2 >= 0x200 && *(_WORD *)a1 == 23117 && *(_DWORD *)(a1 + 60) < a2 )
  {
    v4 = a1 + *(int *)(a1 + 60);
    if ( v4 + 248 <= v2 && *(_DWORD *)v4 == 17744 && *(_WORD *)(v4 + 24) == 267 )
    {
      v5 = v4 + *(unsigned __int16 *)(v4 + 20) + 24LL;
      if ( v5 > v4 )
      {
        v6 = v5 + 40LL * *(unsigned __int16 *)(v4 + 6);
        if ( v5 <= v6 && v6 <= v2 )
        {
          v7 = v4 + 8 * (*(unsigned int *)(v4 + 116) + 15LL);
          if ( v4 + 120 <= v7 && v7 <= v2 )
            return v4;
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180004d10  sub     rsp, 18h
0x180004d14  mov     r9d, edx
0x180004d17  add     r9, rcx
0x180004d1a  xor     r8d, r8d
0x180004d1d  mov     [rsp+18h+var_18], r8
0x180004d21  cmp     edx, 200h
0x180004d27  jb      short loc_180004DA4
0x180004d29  mov     eax, 5A4Dh
0x180004d2e  cmp     [rcx], ax
0x180004d31  jnz     short loc_180004DA4
0x180004d33  cmp     [rcx+3Ch], edx
0x180004d36  jnb     short loc_180004DA4
0x180004d38  movsxd  rdx, dword ptr [rcx+3Ch]
0x180004d3c  add     rdx, rcx
0x180004d3f  lea     rax, [rdx+0F8h]
0x180004d46  cmp     rax, r9
0x180004d49  ja      short loc_180004DA4
0x180004d4b  cmp     dword ptr [rdx], 4550h
0x180004d51  jnz     short loc_180004DA4
0x180004d53  mov     eax, 10Bh
0x180004d58  cmp     [rdx+18h], ax
0x180004d5c  jnz     short loc_180004DA4
0x180004d5e  movzx   r10d, word ptr [rdx+14h]
0x180004d63  add     r10, 18h
0x180004d67  add     r10, rdx
0x180004d6a  cmp     r10, rdx
0x180004d6d  jbe     short loc_180004DA4
0x180004d6f  movzx   eax, word ptr [rdx+6]
0x180004d73  lea     rcx, [rax+rax*4]
0x180004d77  lea     rax, [r10+rcx*8]
0x180004d7b  cmp     r10, rax
0x180004d7e  ja      short loc_180004DA4
0x180004d80  cmp     rax, r9
0x180004d83  ja      short loc_180004DA4
0x180004d85  mov     eax, [rdx+74h]
0x180004d88  add     rax, 0Fh
0x180004d8c  lea     rcx, [rdx+rax*8]
0x180004d90  lea     rax, [rdx+78h]
0x180004d94  cmp     rax, rcx
0x180004d97  ja      short loc_180004DA4
0x180004d99  cmp     rcx, r9
0x180004d9c  cmovbe  r8, rdx
0x180004da0  mov     [rsp+18h+var_18], r8
0x180004da4  jmp     short loc_180004DAA
0x180004da6  mov     r8, [rsp+18h+var_18]
0x180004daa  mov     rax, r8
0x180004dad  add     rsp, 18h
0x180004db1  retn
```
