# fnvcvCompType

- ea: `0x140002790`
- end: `0x14000280e`
- name: `fnvcvCompType`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001c80`
- `0x140002790`

## pseudocode

```c
__int64 __fastcall fnvcvCompType(__int64 a1, __int64 a2, char *a3, _BYTE *a4, int a5, __int64 a6)
{
  char *v7; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax
  _BYTE *v11; // rax

  v7 = a3;
  if ( (unsigned int)CompTypeFromPSZ(a3, a6) == -1 )
    return 0;
  v9 = a5;
  if ( a5 )
  {
    if ( (unsigned __int64)a5 > 0x7FFFFFFF )
    {
      *a4 = 0;
    }
    else
    {
      v10 = 2147483646;
      do
      {
        if ( !v10 )
          break;
        if ( !*v7 )
          break;
        *a4++ = *v7++;
        --v10;
        --v9;
      }
      while ( v9 );
      v11 = a4 - 1;
      if ( v9 )
        v11 = a4;
      *v11 = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140002790  mov     [rsp+arg_0], rbx
0x140002795  push    rdi
0x140002796  sub     rsp, 20h
0x14000279a  mov     rdx, [rsp+28h+arg_28]
0x14000279f  mov     rcx, r8; String1
0x1400027a2  mov     rbx, r9
0x1400027a5  mov     rdi, r8
0x1400027a8  call    CompTypeFromPSZ
0x1400027ad  cmp     eax, 0FFFFFFFFh
0x1400027b0  jnz     short loc_1400027B6
0x1400027b2  xor     eax, eax
0x1400027b4  jmp     short loc_140002803
0x1400027b6  movsxd  rax, [rsp+28h+arg_20]
0x1400027bb  mov     rcx, rax
0x1400027be  test    eax, eax
0x1400027c0  jz      short loc_1400027FE
0x1400027c2  cmp     rax, 7FFFFFFFh
0x1400027c8  ja      short loc_1400027FB
0x1400027ca  mov     eax, 7FFFFFFEh
0x1400027cf  test    rax, rax
0x1400027d2  jz      short loc_1400027EB
0x1400027d4  mov     dl, [rdi]
0x1400027d6  test    dl, dl
0x1400027d8  jz      short loc_1400027EB
0x1400027da  mov     [rbx], dl
0x1400027dc  inc     rdi
0x1400027df  inc     rbx
0x1400027e2  dec     rax
0x1400027e5  sub     rcx, 1
0x1400027e9  jnz     short loc_1400027CF
0x1400027eb  test    rcx, rcx
0x1400027ee  lea     rax, [rbx-1]
0x1400027f2  cmovnz  rax, rbx
0x1400027f6  mov     byte ptr [rax], 0
0x1400027f9  jmp     short loc_1400027FE
0x1400027fb  mov     byte ptr [rbx], 0
0x1400027fe  mov     eax, 1
0x140002803  mov     rbx, [rsp+28h+arg_0]
0x140002808  add     rsp, 20h
0x14000280c  pop     rdi
0x14000280d  retn
```
