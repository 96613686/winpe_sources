# fciTempFile

- ea: `0x1400061d0`
- end: `0x14000627b`
- name: `fciTempFile`
- size: `171`
- prototype: `BOOL __cdecl(char *pszTempName, int cbTempName, void *pv)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400061d0`
- `0x140009b38`

## import_xrefs

- `msvcrt!free` at `0x140006258`
- `msvcrt!free` at `0x140006268`
- `msvcrt!free` at `0x140006258`
- `msvcrt!free` at `0x140006268`

## pseudocode

```c
__int64 __fastcall fciTempFile(char *pszTempName, int cbTempName, void *pv)
{
  unsigned __int64 v3; // rdi
  char *v4; // rbx
  char *v5; // rax
  char *v6; // r8
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  char *v10; // rdx
  char *v11; // rax

  v3 = cbTempName;
  v4 = pszTempName;
  v5 = my_tempnam((__int64)pszTempName, "cab");
  v6 = v5;
  if ( !v5 )
    return 0;
  v7 = -1;
  do
    ++v7;
  while ( v5[v7] );
  if ( v7 >= (unsigned int)v3 )
  {
    free(v5);
    return 0;
  }
  v8 = v3;
  if ( (_DWORD)v3 )
  {
    if ( v3 > 0x7FFFFFFF )
    {
      *v4 = 0;
    }
    else
    {
      v9 = 2147483646;
      v10 = v6;
      do
      {
        if ( !v9 )
          break;
        if ( !*v10 )
          break;
        *v4++ = *v10++;
        --v9;
        --v8;
      }
      while ( v8 );
      v11 = v4 - 1;
      if ( v8 )
        v11 = v4;
      *v11 = 0;
    }
  }
  free(v6);
  return 1;
}

```

## disassembly

```asm
0x1400061d0  mov     [rsp+arg_0], rbx
0x1400061d5  push    rdi
0x1400061d6  sub     rsp, 20h
0x1400061da  movsxd  rdi, edx
0x1400061dd  mov     rbx, rcx
0x1400061e0  lea     rdx, aCab_1; "cab"
0x1400061e7  call    my_tempnam
0x1400061ec  xor     r10d, r10d
0x1400061ef  mov     r8, rax
0x1400061f2  test    rax, rax
0x1400061f5  jz      short loc_14000626E
0x1400061f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400061fb  inc     rcx
0x1400061fe  cmp     [rax+rcx], r10b
0x140006202  jnz     short loc_1400061FB
0x140006204  mov     eax, edi
0x140006206  cmp     rcx, rax
0x140006209  jnb     short loc_140006265
0x14000620b  mov     rcx, rdi
0x14000620e  test    edi, edi
0x140006210  jz      short loc_140006255
0x140006212  cmp     rcx, 7FFFFFFFh
0x140006219  ja      short loc_140006252
0x14000621b  mov     eax, 7FFFFFFEh
0x140006220  mov     rdx, r8
0x140006223  test    rax, rax
0x140006226  jz      short loc_140006242
0x140006228  mov     r9b, [rdx]
0x14000622b  test    r9b, r9b
0x14000622e  jz      short loc_140006242
0x140006230  mov     [rbx], r9b
0x140006233  inc     rdx
0x140006236  inc     rbx
0x140006239  dec     rax
0x14000623c  sub     rcx, 1
0x140006240  jnz     short loc_140006223
0x140006242  test    rcx, rcx
0x140006245  lea     rax, [rbx-1]
0x140006249  cmovnz  rax, rbx
0x14000624d  mov     [rax], r10b
0x140006250  jmp     short loc_140006255
0x140006252  mov     [rbx], r10b
0x140006255  mov     rcx, r8; Block
0x140006258  call    cs:__imp_free
0x14000625e  mov     eax, 1
0x140006263  jmp     short loc_140006270
0x140006265  mov     rcx, r8; Block
0x140006268  call    cs:__imp_free
0x14000626e  xor     eax, eax
0x140006270  mov     rbx, [rsp+28h+arg_0]
0x140006275  add     rsp, 20h
0x140006279  pop     rdi
0x14000627a  retn
```
