# lafe_line_reader_next

- ea: `0x140007314`
- end: `0x1400074c7`
- name: `lafe_line_reader_next`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005bbc`

## callees

- `0x140001b96`
- `0x1400071a4`
- `0x1400072c8`
- `0x140007314`
- `0x1400076dd`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007478`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007478`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14000743e`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14000743e`
- `api-ms-win-crt-private-l1-1-0!_o_feof` at `0x14000741e`
- `api-ms-win-crt-private-l1-1-0!_o_feof` at `0x14000741e`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x140007411`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x140007411`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1400073f5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1400073f5`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1400073b9`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1400073b9`

## string_xrefs

- `0x140007481`: `Can't read %s`

## pseudocode

```c
_BYTE *__fastcall lafe_line_reader_next(_QWORD *a1)
{
  const void **v2; // rdi
  _BYTE *v3; // rsi
  _BYTE *v4; // rax
  unsigned __int64 v5; // rcx
  _BYTE *v6; // rcx
  _BYTE *v7; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  FILE *v16; // rsi

  v2 = (const void **)(a1 + 3);
  while ( 1 )
  {
    while ( 1 )
    {
      v4 = (_BYTE *)a1[2];
      v5 = a1[4];
      if ( v5 >= (unsigned __int64)v4 )
        break;
      v3 = *v2;
      a1[4] = v5 + 1;
      *v2 = (const void *)(v5 + 1);
      lafe_line_reader_find_eol(a1);
      if ( *((_DWORD *)a1 + 14) || *v3 )
        return v3;
    }
    v6 = *v2;
    if ( !*a1 )
      break;
    if ( (unsigned __int64)v6 <= a1[1] )
    {
      v9 = a1[6];
      v10 = 2 * v9;
      if ( 2 * v9 <= v9 )
        lafe_errc(1);
      v11 = a1[1];
      a1[6] = v10;
      v12 = _o_realloc(v11, v10 + 1);
      v7 = (_BYTE *)v12;
      if ( !v12 )
        lafe_errc(1);
      v8 = v12 - a1[1];
      a1[2] += v8;
      a1[1] = v7;
    }
    else
    {
      memmove_0((void *)a1[1], *v2, v4 - v6);
      v7 = (_BYTE *)a1[1];
      a1[2] += v7 - (_BYTE *)*v2;
      v8 = v7 - (_BYTE *)*v2;
    }
    a1[4] += v8;
    *v2 = v7;
    a1[2] += fread((void *)a1[2], 1u, a1[6] + a1[1] - a1[2], (FILE *)*a1);
    *(_BYTE *)a1[2] = 0;
    lafe_line_reader_find_eol(a1);
    if ( (unsigned int)_o_ferror(*a1) )
    {
      _o__errno(v14, v13, v15);
      lafe_errc(1);
    }
    if ( feof((FILE *)*a1) )
    {
      v16 = (FILE *)*a1;
      if ( v16 != o___acrt_iob_func_0(0) )
        fclose(v16);
      *a1 = 0;
    }
  }
  if ( v6 == v4 )
    return 0;
  *v2 = v4;
  return v6;
}

```

## disassembly

```asm
0x140007314  mov     [rsp+arg_0], rbx
0x140007319  mov     [rsp+arg_8], rsi
0x14000731e  push    rdi
0x14000731f  sub     rsp, 20h
0x140007323  mov     rbx, rcx
0x140007326  lea     rdi, [rcx+18h]
0x14000732a  jmp     short loc_140007355
0x14000732c  mov     rsi, [rdi]
0x14000732f  lea     rax, [rcx+1]
0x140007333  mov     rcx, rbx
0x140007336  mov     [rbx+20h], rax
0x14000733a  mov     [rdi], rax
0x14000733d  call    lafe_line_reader_find_eol
0x140007342  cmp     dword ptr [rbx+38h], 0
0x140007346  jnz     loc_140007450
0x14000734c  cmp     byte ptr [rsi], 0
0x14000734f  jnz     loc_140007450
0x140007355  mov     rax, [rbx+10h]
0x140007359  mov     rcx, [rbx+20h]
0x14000735d  cmp     rcx, rax
0x140007360  jb      short loc_14000732C
0x140007362  cmp     qword ptr [rbx], 0
0x140007366  mov     rcx, [rdi]
0x140007369  jz      loc_140007455
0x14000736f  cmp     rcx, [rbx+8]
0x140007373  jbe     short loc_14000739D
0x140007375  sub     rax, rcx
0x140007378  mov     rdx, rcx; Src
0x14000737b  mov     rcx, [rbx+8]; void *
0x14000737f  mov     r8, rax; Size
0x140007382  call    memmove_0
0x140007387  mov     rcx, [rbx+8]
0x14000738b  mov     rax, rcx
0x14000738e  sub     rax, [rdi]
0x140007391  add     [rbx+10h], rax
0x140007395  mov     rax, rcx
0x140007398  sub     rax, [rdi]
0x14000739b  jmp     short loc_1400073D7
0x14000739d  mov     rax, [rbx+30h]
0x1400073a1  lea     rdx, [rax+rax]
0x1400073a5  cmp     rdx, rax
0x1400073a8  jbe     loc_1400074AE
0x1400073ae  mov     rcx, [rbx+8]
0x1400073b2  mov     [rbx+30h], rdx
0x1400073b6  inc     rdx
0x1400073b9  call    cs:__imp__o_realloc
0x1400073bf  mov     rcx, rax
0x1400073c2  test    rax, rax
0x1400073c5  jz      loc_140007495
0x1400073cb  sub     rax, [rbx+8]
0x1400073cf  add     [rbx+10h], rax
0x1400073d3  mov     [rbx+8], rcx
0x1400073d7  add     [rbx+20h], rax
0x1400073db  mov     edx, 1; ElementSize
0x1400073e0  mov     [rdi], rcx
0x1400073e3  mov     rcx, [rbx+10h]; Buffer
0x1400073e7  mov     r8, [rbx+8]
0x1400073eb  mov     r9, [rbx]; Stream
0x1400073ee  sub     r8, rcx
0x1400073f1  add     r8, [rbx+30h]; ElementCount
0x1400073f5  call    cs:__imp_fread
0x1400073fb  add     [rbx+10h], rax
0x1400073ff  mov     rcx, rbx
0x140007402  mov     rax, [rbx+10h]
0x140007406  mov     byte ptr [rax], 0
0x140007409  call    lafe_line_reader_find_eol
0x14000740e  mov     rcx, [rbx]
0x140007411  call    cs:__imp__o_ferror
0x140007417  test    eax, eax
0x140007419  jnz     short loc_140007474
0x14000741b  mov     rcx, [rbx]; Stream
0x14000741e  call    cs:__imp_feof
0x140007424  test    eax, eax
0x140007426  jz      loc_140007355
0x14000742c  mov     rsi, [rbx]
0x14000742f  xor     ecx, ecx; Ix
0x140007431  call    _o___acrt_iob_func_0
0x140007436  cmp     rsi, rax
0x140007439  jz      short loc_140007444
0x14000743b  mov     rcx, rsi; Stream
0x14000743e  call    cs:__imp_fclose
0x140007444  mov     qword ptr [rbx], 0
0x14000744b  jmp     loc_140007355
0x140007450  mov     rax, rsi
0x140007453  jmp     short loc_140007464
0x140007455  cmp     rcx, rax
0x140007458  jnz     short loc_14000745E
0x14000745a  xor     eax, eax
0x14000745c  jmp     short loc_140007464
0x14000745e  mov     [rdi], rax
0x140007461  mov     rax, rcx
0x140007464  mov     rbx, [rsp+28h+arg_0]
0x140007469  mov     rsi, [rsp+28h+arg_8]
0x14000746e  add     rsp, 20h
0x140007472  pop     rdi
0x140007473  retn
0x140007474  mov     rbx, [rbx+28h]
0x140007478  call    cs:__imp__o__errno
0x14000747e  mov     r9, rbx
0x140007481  lea     r8, aCanTReadS; "Can't read %s"
0x140007488  mov     ecx, 1; Code
0x14000748d  mov     edx, [rax]
0x14000748f  call    lafe_errc
0x140007495  mov     r9, [rbx+28h]
0x140007499  lea     r8, aLineTooLongInS; "Line too long in %s"
0x1400074a0  mov     edx, 0Ch
0x1400074a5  lea     ecx, [rdx-0Bh]; Code
0x1400074a8  call    lafe_errc
0x1400074ae  mov     r9, [rbx+28h]
0x1400074b2  lea     r8, aLineTooLongInS; "Line too long in %s"
0x1400074b9  mov     edx, 0Ch
0x1400074be  lea     ecx, [rdx-0Bh]; Code
0x1400074c1  call    lafe_errc
```
