# DecompressGetPalette

- ea: `0x180006dd8`
- end: `0x180006e85`
- name: `DecompressGetPalette`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e00`

## callees

- `0x180006dd8`
- `0x180007020`
- `0x180007c95`

## pseudocode

```c
__int64 __fastcall DecompressGetPalette(__int64 a1, int *a2, int *a3)
{
  __int64 result; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  char v8; // al
  int v9; // ecx

  result = DecompressQueryFmt(a1, a2);
  if ( !(_DWORD)result )
  {
    if ( *((_WORD *)a3 + 7) == 8 )
    {
      if ( *((_WORD *)a2 + 7) == 8 )
      {
        v9 = a2[8];
        if ( !v9 )
        {
          v9 = 256;
          a2[8] = 256;
        }
        memmove_0((char *)a3 + *a3, (char *)a2 + *a2, 4LL * v9);
        a3[8] = a2[8];
      }
      else
      {
        v6 = 0;
        a3[8] = 256;
        v7 = 0;
        do
        {
          v8 = *((_BYTE *)dpal775 + v7);
          v7 += 3;
          BYTE2(a3[v6 + 10]) = v8;
          BYTE1(a3[v6 + 10]) = *((_BYTE *)dpal775 + v7 - 2);
          LOBYTE(a3[v6 + 10]) = *((_BYTE *)dpal775 + v7 - 1);
          HIBYTE(a3[v6++ + 10]) = 0;
        }
        while ( v6 != 256 );
      }
      return 0;
    }
    else
    {
      return 4294967294LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006dd8  mov     [rsp+arg_0], rbx
0x180006ddd  push    rdi
0x180006dde  sub     rsp, 20h
0x180006de2  mov     rdi, r8
0x180006de5  mov     rbx, rdx
0x180006de8  call    DecompressQueryFmt
0x180006ded  test    eax, eax
0x180006def  jnz     loc_180006E7A
0x180006df5  cmp     word ptr [rdi+0Eh], 8
0x180006dfa  jz      short loc_180006E03
0x180006dfc  mov     eax, 0FFFFFFFEh
0x180006e01  jmp     short loc_180006E7A
0x180006e03  cmp     word ptr [rbx+0Eh], 8
0x180006e08  jz      short loc_180006E4B
0x180006e0a  mov     ecx, 100h
0x180006e0f  lea     r9, dpal775
0x180006e16  xor     edx, edx
0x180006e18  mov     [rdi+20h], ecx
0x180006e1b  xor     r8d, r8d
0x180006e1e  mov     al, [r8+r9]
0x180006e22  lea     r8, [r8+3]
0x180006e26  mov     [rdi+rdx*4+2Ah], al
0x180006e2a  mov     al, [r8+r9-2]
0x180006e2f  mov     [rdi+rdx*4+29h], al
0x180006e33  mov     al, [r8+r9-1]
0x180006e38  mov     [rdi+rdx*4+28h], al
0x180006e3c  mov     byte ptr [rdi+rdx*4+2Bh], 0
0x180006e41  inc     rdx
0x180006e44  cmp     rdx, rcx
0x180006e47  jnz     short loc_180006E1E
0x180006e49  jmp     short loc_180006E78
0x180006e4b  mov     ecx, [rbx+20h]
0x180006e4e  test    ecx, ecx
0x180006e50  jnz     short loc_180006E5A
0x180006e52  mov     ecx, 100h
0x180006e57  mov     [rbx+20h], ecx
0x180006e5a  movsxd  rdx, dword ptr [rbx]
0x180006e5d  movsxd  r8, ecx
0x180006e60  add     rdx, rbx; Src
0x180006e63  movsxd  rcx, dword ptr [rdi]
0x180006e66  add     rcx, rdi; void *
0x180006e69  shl     r8, 2; Size
0x180006e6d  call    memmove_0
0x180006e72  mov     eax, [rbx+20h]
0x180006e75  mov     [rdi+20h], eax
0x180006e78  xor     eax, eax
0x180006e7a  mov     rbx, [rsp+28h+arg_0]
0x180006e7f  add     rsp, 20h
0x180006e83  pop     rdi
0x180006e84  retn
```
