# ASN1EncCheck

- ea: `0x180007c70`
- end: `0x180007e35`
- name: `ASN1EncCheck`
- size: `453`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180007260`
- `0x180007380`
- `0x1800077b0`
- `0x1800078b0`
- `0x180007980`
- `0x180007ac0`
- `0x180007b10`
- `0x180007b70`
- `0x180007b80`
- `0x180007e40`

## callees

- `0x180007c70`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007da8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007da8`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180007d06`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180007d06`

## pseudocode

```c
__int64 __fastcall ASN1EncCheck(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbx
  void *v3; // rdi
  unsigned int v4; // r8d
  __int64 result; // rax
  unsigned int v6; // eax
  unsigned int v7; // ecx
  _BYTE *v8; // rax
  unsigned int v9; // ecx
  unsigned int v10; // eax
  char *v11; // rax
  char *v12; // rcx
  __int64 v13; // rax

  v2 = a1;
  if ( !a2 )
    return 1;
  v3 = *(void **)(a1 + 16);
  if ( v3 )
  {
    v4 = *(_DWORD *)(a1 + 24);
    if ( (__int64)((__int64)v3 + v4 - (unsigned __int64)(*(_DWORD *)(a1 + 36) != 0) - *(_QWORD *)(a1 + 40)) < a2 )
    {
      if ( (*(_BYTE *)(a1 + 56) & 8) != 0 )
      {
        while ( 1 )
        {
          result = *(_QWORD *)(v2 + 64);
          *(_DWORD *)(v2 + 32) = -1007;
          if ( v2 == result )
            break;
          v2 = result;
          if ( !result )
            return result;
        }
        return 0;
      }
      v6 = *(_DWORD *)(a1 + 24);
      if ( a2 > v4 )
        v6 = a2;
      v7 = v4 + v6;
      if ( v4 + v6 < v6 )
      {
        while ( 1 )
        {
          result = *(_QWORD *)(v2 + 64);
          *(_DWORD *)(v2 + 32) = -1007;
          if ( v2 == result )
            break;
          v2 = result;
          if ( !result )
            return result;
        }
        return 0;
      }
      *(_DWORD *)(v2 + 24) = v7;
      v8 = LocalReAlloc(v3, v7, 0x42u);
      *(_QWORD *)(v2 + 16) = v8;
      if ( !v8 )
      {
        while ( 1 )
        {
          result = *(_QWORD *)(v2 + 64);
          *(_DWORD *)(v2 + 32) = -1006;
          if ( v2 == result )
            break;
          v2 = result;
          if ( !result )
            return result;
        }
        return 0;
      }
      *(_QWORD *)(v2 + 40) += v8 - (_BYTE *)v3;
    }
    return 1;
  }
  v9 = a2 + *(_DWORD *)(a1 + 48);
  if ( v9 < a2 )
  {
    do
    {
      v13 = *(_QWORD *)(v2 + 64);
      *(_DWORD *)(v2 + 32) = -1007;
      if ( v2 == v13 )
        break;
      v2 = v13;
    }
    while ( v13 );
  }
  else
  {
    v10 = 1024;
    if ( v9 > 0x400 )
      v10 = v9;
    *(_DWORD *)(v2 + 24) = v10;
    v11 = (char *)LocalAlloc(0x40u, v10);
    *(_QWORD *)(v2 + 16) = v11;
    if ( v11 )
    {
      v12 = &v11[*(unsigned int *)(v2 + 48)];
      result = 1;
      *(_QWORD *)(v2 + 40) = v12;
      return result;
    }
    *(_QWORD *)(v2 + 40) = 0;
    while ( 1 )
    {
      result = *(_QWORD *)(v2 + 64);
      *(_DWORD *)(v2 + 32) = -1006;
      if ( v2 == result )
        break;
      v2 = result;
      if ( !result )
        return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007c70  mov     [rsp+arg_0], rbx
0x180007c75  push    rdi
0x180007c76  sub     rsp, 20h
0x180007c7a  mov     rbx, rcx
0x180007c7d  test    edx, edx
0x180007c7f  jz      loc_180007D1C
0x180007c85  mov     rdi, [rcx+10h]
0x180007c89  test    rdi, rdi
0x180007c8c  jz      loc_180007D87
0x180007c92  mov     r8d, [rcx+18h]
0x180007c96  xor     eax, eax
0x180007c98  cmp     [rcx+24h], eax
0x180007c9b  mov     ecx, r8d
0x180007c9e  setnz   al
0x180007ca1  sub     rcx, rax
0x180007ca4  mov     eax, edx
0x180007ca6  sub     rcx, [rbx+28h]
0x180007caa  add     rcx, rdi
0x180007cad  cmp     rcx, rax
0x180007cb0  jge     short loc_180007D1C
0x180007cb2  test    byte ptr [rbx+38h], 8
0x180007cb6  jz      short loc_180007CE7
0x180007cb8  nop     dword ptr [rax+rax+00000000h]
0x180007cc0  mov     rax, [rbx+40h]
0x180007cc4  mov     dword ptr [rbx+20h], 0FFFFFC11h
0x180007ccb  cmp     rbx, rax
0x180007cce  jz      loc_180007E28
0x180007cd4  mov     rbx, rax
0x180007cd7  test    rax, rax
0x180007cda  jnz     short loc_180007CC0
0x180007cdc  mov     rbx, [rsp+28h+arg_0]
0x180007ce1  add     rsp, 20h
0x180007ce5  pop     rdi
0x180007ce6  retn
0x180007ce7  cmp     edx, r8d
0x180007cea  mov     eax, r8d
0x180007ced  cmova   eax, edx
0x180007cf0  lea     ecx, [r8+rax]
0x180007cf4  cmp     ecx, eax
0x180007cf6  jb      short loc_180007D60
0x180007cf8  mov     [rbx+18h], ecx
0x180007cfb  mov     r8d, 42h ; 'B'; uFlags
0x180007d01  mov     edx, ecx; uBytes
0x180007d03  mov     rcx, rdi; hMem
0x180007d06  call    cs:__imp_LocalReAlloc
0x180007d0c  mov     [rbx+10h], rax
0x180007d10  test    rax, rax
0x180007d13  jz      short loc_180007D30
0x180007d15  sub     rax, rdi
0x180007d18  add     [rbx+28h], rax
0x180007d1c  mov     eax, 1
0x180007d21  mov     rbx, [rsp+28h+arg_0]
0x180007d26  add     rsp, 20h
0x180007d2a  pop     rdi
0x180007d2b  retn
0x180007d30  mov     rax, [rbx+40h]
0x180007d34  mov     dword ptr [rbx+20h], 0FFFFFC12h
0x180007d3b  cmp     rbx, rax
0x180007d3e  jz      loc_180007E28
0x180007d44  mov     rbx, rax
0x180007d47  test    rax, rax
0x180007d4a  jnz     short loc_180007D30
0x180007d4c  mov     rbx, [rsp+28h+arg_0]
0x180007d51  add     rsp, 20h
0x180007d55  pop     rdi
0x180007d56  retn
0x180007d60  mov     rax, [rbx+40h]
0x180007d64  mov     dword ptr [rbx+20h], 0FFFFFC11h
0x180007d6b  cmp     rbx, rax
0x180007d6e  jz      loc_180007E28
0x180007d74  mov     rbx, rax
0x180007d77  test    rax, rax
0x180007d7a  jnz     short loc_180007D60
0x180007d7c  mov     rbx, [rsp+28h+arg_0]
0x180007d81  add     rsp, 20h
0x180007d85  pop     rdi
0x180007d86  retn
0x180007d87  mov     ecx, [rcx+30h]
0x180007d8a  add     ecx, edx
0x180007d8c  cmp     ecx, edx
0x180007d8e  jb      loc_180007E10
0x180007d94  mov     eax, 400h
0x180007d99  cmp     ecx, eax
0x180007d9b  cmova   eax, ecx
0x180007d9e  mov     ecx, 40h ; '@'; uFlags
0x180007da3  mov     edx, eax; uBytes
0x180007da5  mov     [rbx+18h], edx
0x180007da8  call    cs:__imp_LocalAlloc
0x180007dae  mov     [rbx+10h], rax
0x180007db2  test    rax, rax
0x180007db5  jz      short loc_180007DD1
0x180007db7  mov     ecx, [rbx+30h]
0x180007dba  add     rcx, rax
0x180007dbd  mov     eax, 1
0x180007dc2  mov     [rbx+28h], rcx
0x180007dc6  mov     rbx, [rsp+28h+arg_0]
0x180007dcb  add     rsp, 20h
0x180007dcf  pop     rdi
0x180007dd0  retn
0x180007dd1  mov     [rbx+28h], rax
0x180007dd5  nop     word ptr [rax+rax+00000000h]
0x180007de0  mov     rax, [rbx+40h]
0x180007de4  mov     dword ptr [rbx+20h], 0FFFFFC12h
0x180007deb  cmp     rbx, rax
0x180007dee  jz      short loc_180007E28
0x180007df0  mov     rbx, rax
0x180007df3  test    rax, rax
0x180007df6  jnz     short loc_180007DE0
0x180007df8  mov     rbx, [rsp+28h+arg_0]
0x180007dfd  add     rsp, 20h
0x180007e01  pop     rdi
0x180007e02  retn
0x180007e10  mov     rax, [rbx+40h]
0x180007e14  mov     dword ptr [rbx+20h], 0FFFFFC11h
0x180007e1b  cmp     rbx, rax
0x180007e1e  jz      short loc_180007E28
0x180007e20  mov     rbx, rax
0x180007e23  test    rax, rax
0x180007e26  jnz     short loc_180007E10
0x180007e28  mov     rbx, [rsp+28h+arg_0]
0x180007e2d  xor     eax, eax
0x180007e2f  add     rsp, 20h
0x180007e33  pop     rdi
0x180007e34  retn
```
