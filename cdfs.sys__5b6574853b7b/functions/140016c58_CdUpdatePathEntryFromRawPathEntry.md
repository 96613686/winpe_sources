# CdUpdatePathEntryFromRawPathEntry

- ea: `0x140016c58`
- end: `0x140016db7`
- name: `CdUpdatePathEntryFromRawPathEntry`
- size: `351`
- prototype: `char __fastcall(__int64, int, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140016998`
- `0x140016a20`

## callees

- `0x140001114`
- `0x140016c58`

## pseudocode

```c
char __fastcall CdUpdatePathEntryFromRawPathEntry(__int64 a1, int a2, char a3, __int64 a4, __int64 a5)
{
  char *v7; // rbx
  unsigned __int8 v8; // al
  int v9; // edi
  char v10; // al
  char result; // al
  unsigned int v12; // edx
  unsigned __int8 v13; // al
  int *v14; // rcx
  int v15; // r8d

  v7 = (char *)(*(_QWORD *)a4 + *(unsigned int *)(a4 + 24));
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 1) != 0 )
    v8 = v7[5];
  else
    v8 = *v7;
  v9 = v8;
  *(_DWORD *)(a5 + 20) = v8;
  v10 = *(_BYTE *)(a4 + 29);
  if ( v9 )
  {
    if ( v10 )
    {
      if ( a3 )
      {
        v12 = *(_DWORD *)(a4 + 12) - *(_DWORD *)(a4 + 24);
        if ( v12 < 0x108 )
        {
          if ( v12 < 9
            || ((*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 1) == 0 ? (v13 = *v7) : (v13 = v7[5]),
                v12 < (unsigned int)v13 + 8) )
          {
            CdRaiseStatusEx(a1, 3221225522LL, 0, 1245184, 744);
          }
        }
      }
    }
    *(_DWORD *)a5 = a2;
    *(_DWORD *)(a5 + 4) = *(_DWORD *)(a4 + 24) + *(_DWORD *)(a4 + 8);
    v14 = (int *)v7;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 1) == 0 )
      v14 = (int *)(v7 + 2);
    v15 = *v14;
    *(_DWORD *)(a5 + 8) = *v14;
    result = 1;
    *(_DWORD *)(a5 + 8) = v15 + (unsigned __int8)v7[((*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 1) != 0 ? 3 : 0) + 1];
    *(_WORD *)(a5 + 16) = *((_WORD *)v7 + 3);
    *(_DWORD *)(a5 + 12) = (v9 + 9) & 0xFFFFFFFE;
    *(_QWORD *)(a5 + 24) = v7 + 8;
  }
  else
  {
    if ( !v10 || (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 440LL) & *(_DWORD *)(a4 + 12)) != 0 )
      CdRaiseStatusEx(a1, 3221225522LL, 0, 1245184, 713);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140016c58  mov     [rsp+arg_0], rbx
0x140016c5d  mov     [rsp+arg_8], rsi
0x140016c62  push    rdi
0x140016c63  sub     rsp, 30h
0x140016c67  mov     rax, [rcx+10h]
0x140016c6b  mov     esi, edx
0x140016c6d  mov     ebx, [r9+18h]
0x140016c71  mov     r11, rcx
0x140016c74  add     rbx, [r9]
0x140016c77  mov     r10d, [rax+30h]
0x140016c7b  test    r10b, 1
0x140016c7f  jz      short loc_140016C86
0x140016c81  mov     al, [rbx+5]
0x140016c84  jmp     short loc_140016C88
0x140016c86  mov     al, [rbx]
0x140016c88  mov     r10, [rsp+38h+arg_20]
0x140016c8d  movzx   edi, al
0x140016c90  mov     [r10+14h], edi
0x140016c94  mov     al, [r9+1Dh]
0x140016c98  test    edi, edi
0x140016c9a  jnz     short loc_140016CBF
0x140016c9c  test    al, al
0x140016c9e  jz      loc_140016D79
0x140016ca4  mov     rax, [rcx+10h]
0x140016ca8  mov     ecx, [rax+1B8h]
0x140016cae  test    [r9+0Ch], ecx
0x140016cb2  jnz     loc_140016D79
0x140016cb8  xor     al, al
0x140016cba  jmp     loc_140016D68
0x140016cbf  test    al, al
0x140016cc1  jz      short loc_140016D02
0x140016cc3  test    r8b, r8b
0x140016cc6  jz      short loc_140016D02
0x140016cc8  mov     edx, [r9+0Ch]
0x140016ccc  sub     edx, [r9+18h]
0x140016cd0  cmp     edx, 108h
0x140016cd6  jnb     short loc_140016D02
0x140016cd8  cmp     edx, 9
0x140016cdb  jb      loc_140016D98
0x140016ce1  mov     rax, [rcx+10h]
0x140016ce5  mov     ecx, [rax+30h]
0x140016ce8  test    cl, 1
0x140016ceb  jz      short loc_140016CF2
0x140016ced  mov     al, [rbx+5]
0x140016cf0  jmp     short loc_140016CF4
0x140016cf2  mov     al, [rbx]
0x140016cf4  movzx   eax, al
0x140016cf7  add     eax, 8
0x140016cfa  cmp     edx, eax
0x140016cfc  jb      loc_140016D98
0x140016d02  mov     [r10], esi
0x140016d05  mov     eax, [r9+8]
0x140016d09  add     eax, [r9+18h]
0x140016d0d  mov     [r10+4], eax
0x140016d11  mov     rax, [r11+10h]
0x140016d15  mov     ecx, [rax+30h]
0x140016d18  test    cl, 1
0x140016d1b  lea     rax, [rbx+2]
0x140016d1f  mov     rcx, rbx
0x140016d22  cmovz   rcx, rax
0x140016d26  mov     r8d, [rcx]
0x140016d29  mov     [r10+8], r8d
0x140016d2d  mov     rax, [r11+10h]
0x140016d31  mov     ecx, [rax+30h]
0x140016d34  mov     al, 1
0x140016d36  and     cl, 1
0x140016d39  neg     cl
0x140016d3b  sbb     rdx, rdx
0x140016d3e  and     edx, 3
0x140016d41  movzx   ecx, byte ptr [rdx+rbx+1]
0x140016d46  add     ecx, r8d
0x140016d49  mov     [r10+8], ecx
0x140016d4d  movzx   ecx, word ptr [rbx+6]
0x140016d51  mov     [r10+10h], cx
0x140016d56  lea     ecx, [rdi+9]
0x140016d59  and     ecx, 0FFFFFFFEh
0x140016d5c  mov     [r10+0Ch], ecx
0x140016d60  lea     rcx, [rbx+8]
0x140016d64  mov     [r10+18h], rcx
0x140016d68  mov     rbx, [rsp+38h+arg_0]
0x140016d6d  mov     rsi, [rsp+38h+arg_8]
0x140016d72  add     rsp, 30h
0x140016d76  pop     rdi
0x140016d77  retn
0x140016d79  mov     r9d, 130000h
0x140016d7f  mov     [rsp+38h+var_18], 2C9h
0x140016d87  xor     r8d, r8d
0x140016d8a  mov     edx, 0C0000032h
0x140016d8f  mov     rcx, r11
0x140016d92  call    CdRaiseStatusEx
0x140016d98  mov     r9d, 130000h
0x140016d9e  mov     [rsp+38h+var_18], 2E8h
0x140016da6  xor     r8d, r8d
0x140016da9  mov     edx, 0C0000032h
0x140016dae  mov     rcx, r11
0x140016db1  call    CdRaiseStatusEx
```
