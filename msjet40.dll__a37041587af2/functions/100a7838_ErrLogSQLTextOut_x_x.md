# ErrLogSQLTextOut(x,x)

- ea: `0x100a7838`
- end: `0x100a78da`
- name: `_ErrLogSQLTextOut@8`
- size: `162`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x100a5120`
- `0x100a667d`
- `0x100a67b5`
- `0x100c2c76`
- `0x100c38de`
- `0x100d1a65`
- `0x100d2460`
- `0x100d2c30`
- `0x100d7200`

## callees

- `0x100a7838`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x100a78cc`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x100a78cc`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x100a785a`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x100a785a`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100a7897`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100a78bb`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100a7897`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100a78bb`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x100a78a8`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x100a78a8`

## pseudocode

```c
int __fastcall ErrLogSQLTextOut(int a1, __int16 a2)
{
  const char *v2; // esi
  int v3; // ebx
  FILE *v4; // edi

  v2 = 0;
  v3 = -1860;
  v4 = _fopen("sqlout.txt", "at");
  if ( !v4 )
    return -1020;
  switch ( a2 )
  {
    case 1:
      v2 = "SQLExecDirect: ";
      break;
    case 2:
      v2 = "SQLPrepare: ";
      break;
    case 3:
      v2 = "SQLExecute: ";
      break;
  }
  if ( __o_fputs(v2, v4) != -1 && __o_fputws(a1, v4) != -1 && __o_fputs("\r\n", v4) != -1 )
    v3 = 0;
  _fclose(v4);
  return v3;
}

```

## disassembly

```asm
0x100a7838  mov     edi, edi
0x100a783a  push    ebp
0x100a783b  mov     ebp, esp
0x100a783d  push    ecx
0x100a783e  push    ecx
0x100a783f  push    ebx
0x100a7840  push    esi
0x100a7841  push    edi
0x100a7842  push    offset Mode; "at"
0x100a7847  push    offset _szTraceSQLFile; "sqlout.txt"
0x100a784c  mov     [ebp+var_2], dx
0x100a7850  xor     esi, esi
0x100a7852  mov     [ebp+var_8], ecx
0x100a7855  mov     ebx, 0FFFFF8BCh
0x100a785a  call    ds:__imp__fopen
0x100a7860  mov     edi, eax
0x100a7862  pop     ecx
0x100a7863  pop     ecx
0x100a7864  test    edi, edi
0x100a7866  jnz     short loc_100A786F
0x100a7868  mov     eax, 0FFFFFC04h
0x100a786d  jmp     short loc_100A78D5
0x100a786f  movzx   eax, [ebp+var_2]
0x100a7873  sub     eax, 1
0x100a7876  jz      short loc_100A7890
0x100a7878  sub     eax, 1
0x100a787b  jz      short loc_100A7889
0x100a787d  sub     eax, 1
0x100a7880  jnz     short loc_100A7895
0x100a7882  mov     esi, offset _szTraceExecute; "SQLExecute: "
0x100a7887  jmp     short loc_100A7895
0x100a7889  mov     esi, offset _szTracePrepare; "SQLPrepare: "
0x100a788e  jmp     short loc_100A7895
0x100a7890  mov     esi, offset _szTraceExecDirect; "SQLExecDirect: "
0x100a7895  push    edi
0x100a7896  push    esi
0x100a7897  call    ds:__imp___o_fputs
0x100a789d  pop     ecx
0x100a789e  pop     ecx
0x100a789f  cmp     eax, 0FFFFFFFFh
0x100a78a2  jz      short loc_100A78CB
0x100a78a4  push    edi
0x100a78a5  push    [ebp+var_8]
0x100a78a8  call    ds:__imp___o_fputws
0x100a78ae  pop     ecx
0x100a78af  pop     ecx
0x100a78b0  cmp     eax, 0FFFFFFFFh
0x100a78b3  jz      short loc_100A78CB
0x100a78b5  push    edi
0x100a78b6  push    offset _szCrLf; "\r\n"
0x100a78bb  call    ds:__imp___o_fputs
0x100a78c1  pop     ecx
0x100a78c2  pop     ecx
0x100a78c3  xor     ecx, ecx
0x100a78c5  cmp     eax, 0FFFFFFFFh
0x100a78c8  cmovnz  ebx, ecx
0x100a78cb  push    edi; Stream
0x100a78cc  call    ds:__imp__fclose
0x100a78d2  pop     ecx
0x100a78d3  mov     eax, ebx
0x100a78d5  pop     edi
0x100a78d6  pop     esi
0x100a78d7  pop     ebx
0x100a78d8  leave
0x100a78d9  retn
```
