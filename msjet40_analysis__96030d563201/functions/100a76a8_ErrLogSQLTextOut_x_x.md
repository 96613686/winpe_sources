# ErrLogSQLTextOut(x,x)

- ea: `0x100a76a8`
- end: `0x100a774a`
- name: `_ErrLogSQLTextOut@8`
- size: `162`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x100a4f90`
- `0x100a64ed`
- `0x100a6625`
- `0x100c2ae6`
- `0x100c374e`
- `0x100d18d5`
- `0x100d22d0`
- `0x100d2aa0`
- `0x100d7070`

## callees

- `0x100a76a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x100a773c`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x100a773c`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x100a76ca`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x100a76ca`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100a7707`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100a772b`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100a7707`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x100a772b`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x100a7718`
- `api-ms-win-crt-private-l1-1-0!_o_fputws` at `0x100a7718`

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
0x100a76a8  mov     edi, edi
0x100a76aa  push    ebp
0x100a76ab  mov     ebp, esp
0x100a76ad  push    ecx
0x100a76ae  push    ecx
0x100a76af  push    ebx
0x100a76b0  push    esi
0x100a76b1  push    edi
0x100a76b2  push    offset Mode; "at"
0x100a76b7  push    offset _szTraceSQLFile; "sqlout.txt"
0x100a76bc  mov     [ebp+var_2], dx
0x100a76c0  xor     esi, esi
0x100a76c2  mov     [ebp+var_8], ecx
0x100a76c5  mov     ebx, 0FFFFF8BCh
0x100a76ca  call    ds:__imp__fopen
0x100a76d0  mov     edi, eax
0x100a76d2  pop     ecx
0x100a76d3  pop     ecx
0x100a76d4  test    edi, edi
0x100a76d6  jnz     short loc_100A76DF
0x100a76d8  mov     eax, 0FFFFFC04h
0x100a76dd  jmp     short loc_100A7745
0x100a76df  movzx   eax, [ebp+var_2]
0x100a76e3  sub     eax, 1
0x100a76e6  jz      short loc_100A7700
0x100a76e8  sub     eax, 1
0x100a76eb  jz      short loc_100A76F9
0x100a76ed  sub     eax, 1
0x100a76f0  jnz     short loc_100A7705
0x100a76f2  mov     esi, offset _szTraceExecute; "SQLExecute: "
0x100a76f7  jmp     short loc_100A7705
0x100a76f9  mov     esi, offset _szTracePrepare; "SQLPrepare: "
0x100a76fe  jmp     short loc_100A7705
0x100a7700  mov     esi, offset _szTraceExecDirect; "SQLExecDirect: "
0x100a7705  push    edi
0x100a7706  push    esi
0x100a7707  call    ds:__imp___o_fputs
0x100a770d  pop     ecx
0x100a770e  pop     ecx
0x100a770f  cmp     eax, 0FFFFFFFFh
0x100a7712  jz      short loc_100A773B
0x100a7714  push    edi
0x100a7715  push    [ebp+var_8]
0x100a7718  call    ds:__imp___o_fputws
0x100a771e  pop     ecx
0x100a771f  pop     ecx
0x100a7720  cmp     eax, 0FFFFFFFFh
0x100a7723  jz      short loc_100A773B
0x100a7725  push    edi
0x100a7726  push    offset _szCrLf; "\r\n"
0x100a772b  call    ds:__imp___o_fputs
0x100a7731  pop     ecx
0x100a7732  pop     ecx
0x100a7733  xor     ecx, ecx
0x100a7735  cmp     eax, 0FFFFFFFFh
0x100a7738  cmovnz  ebx, ecx
0x100a773b  push    edi; Stream
0x100a773c  call    ds:__imp__fclose
0x100a7742  pop     ecx
0x100a7743  mov     eax, ebx
0x100a7745  pop     edi
0x100a7746  pop     esi
0x100a7747  pop     ebx
0x100a7748  leave
0x100a7749  retn
```
