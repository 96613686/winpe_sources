# fnvcvCompMemory

- ea: `0x140002700`
- end: `0x14000277e`
- name: `fnvcvCompMemory`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001b84`
- `0x140002700`

## pseudocode

```c
__int64 __fastcall fnvcvCompMemory(__int64 a1, __int64 a2, const char *a3, _BYTE *a4, int a5, __int64 a6)
{
  const char *v7; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax
  _BYTE *v11; // rax

  v7 = a3;
  if ( (unsigned int)CompMemoryFromPSZ(a3, a6) == -1 )
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
0x140002700  mov     [rsp+arg_0], rbx
0x140002705  push    rdi
0x140002706  sub     rsp, 20h
0x14000270a  mov     rdx, [rsp+28h+arg_28]
0x14000270f  mov     rcx, r8
0x140002712  mov     rbx, r9
0x140002715  mov     rdi, r8
0x140002718  call    CompMemoryFromPSZ
0x14000271d  cmp     eax, 0FFFFFFFFh
0x140002720  jnz     short loc_140002726
0x140002722  xor     eax, eax
0x140002724  jmp     short loc_140002773
0x140002726  movsxd  rax, [rsp+28h+arg_20]
0x14000272b  mov     rcx, rax
0x14000272e  test    eax, eax
0x140002730  jz      short loc_14000276E
0x140002732  cmp     rax, 7FFFFFFFh
0x140002738  ja      short loc_14000276B
0x14000273a  mov     eax, 7FFFFFFEh
0x14000273f  test    rax, rax
0x140002742  jz      short loc_14000275B
0x140002744  mov     dl, [rdi]
0x140002746  test    dl, dl
0x140002748  jz      short loc_14000275B
0x14000274a  mov     [rbx], dl
0x14000274c  inc     rdi
0x14000274f  inc     rbx
0x140002752  dec     rax
0x140002755  sub     rcx, 1
0x140002759  jnz     short loc_14000273F
0x14000275b  test    rcx, rcx
0x14000275e  lea     rax, [rbx-1]
0x140002762  cmovnz  rax, rbx
0x140002766  mov     byte ptr [rax], 0
0x140002769  jmp     short loc_14000276E
0x14000276b  mov     byte ptr [rbx], 0
0x14000276e  mov     eax, 1
0x140002773  mov     rbx, [rsp+28h+arg_0]
0x140002778  add     rsp, 20h
0x14000277c  pop     rdi
0x14000277d  retn
```
