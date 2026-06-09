# copyBounded

- ea: `0x14000d698`
- end: `0x14000d705`
- name: `copyBounded`
- size: `109`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001de0`
- `0x140002c80`
- `0x140003a30`
- `0x14000a000`

## callees

- `0x14000d698`

## pseudocode

```c
__int64 __fastcall copyBounded(_BYTE **a1, int *a2, _BYTE **a3, int a4)
{
  _BYTE *v4; // rbx
  int v5; // r11d
  _BYTE *v6; // r10
  bool v7; // cc
  char v8; // al
  __int64 result; // rax
  char v10; // al

  v4 = *a1;
  v5 = *a2;
  v6 = *a3;
  v7 = a4 <= 0;
  if ( a4 )
  {
    while ( !v7 )
    {
      if ( v5 <= 0 )
        return 0;
      v10 = *v6;
      --a4;
      *v4 = *v6;
      --v5;
      ++v4;
      ++v6;
      if ( !v10 )
      {
        if ( a4 <= 0 )
          goto LABEL_5;
        return 0;
      }
      v7 = a4 <= 0;
    }
    goto LABEL_5;
  }
  do
  {
    if ( v5 <= 0 )
      break;
    v8 = *v6;
    --v5;
    *v4++ = *v6++;
  }
  while ( v8 );
  if ( !*(v6 - 1) )
  {
LABEL_5:
    *a1 = v4;
    result = 1;
    *a2 = v5;
    *a3 = v6;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x14000d698  mov     [rsp+arg_0], rbx
0x14000d69d  mov     rbx, [rcx]
0x14000d6a0  mov     r11d, [rdx]
0x14000d6a3  mov     r10, [r8]
0x14000d6a6  test    r9d, r9d
0x14000d6a9  jnz     short loc_14000D6E0
0x14000d6ab  test    r11d, r11d
0x14000d6ae  jle     short loc_14000D6C2
0x14000d6b0  mov     al, [r10]
0x14000d6b3  dec     r11d
0x14000d6b6  mov     [rbx], al
0x14000d6b8  inc     r10
0x14000d6bb  inc     rbx
0x14000d6be  test    al, al
0x14000d6c0  jnz     short loc_14000D6AB
0x14000d6c2  cmp     byte ptr [r10-1], 0
0x14000d6c7  jnz     short loc_14000D701
0x14000d6c9  mov     [rcx], rbx
0x14000d6cc  mov     eax, 1
0x14000d6d1  mov     [rdx], r11d
0x14000d6d4  mov     [r8], r10
0x14000d6d7  mov     rbx, [rsp+arg_0]
0x14000d6dc  retn
0x14000d6dd  test    r9d, r9d
0x14000d6e0  jle     short loc_14000D6C9
0x14000d6e2  test    r11d, r11d
0x14000d6e5  jle     short loc_14000D701
0x14000d6e7  mov     al, [r10]
0x14000d6ea  dec     r9d
0x14000d6ed  mov     [rbx], al
0x14000d6ef  dec     r11d
0x14000d6f2  inc     rbx
0x14000d6f5  inc     r10
0x14000d6f8  test    al, al
0x14000d6fa  jnz     short loc_14000D6DD
0x14000d6fc  test    r9d, r9d
0x14000d6ff  jle     short loc_14000D6C9
0x14000d701  xor     eax, eax
0x14000d703  jmp     short loc_14000D6D7
```
