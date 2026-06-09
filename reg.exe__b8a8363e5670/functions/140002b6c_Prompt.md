# Prompt

- ea: `0x140002b6c`
- end: `0x140002c18`
- name: `Prompt`
- size: `172`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140003c24`
- `0x14000496c`
- `0x14000672c`
- `0x1400073d4`
- `0x1400075ac`
- `0x140009c68`

## callees

- `0x140001bb2`
- `0x140002b6c`
- `0x14000d0c4`
- `0x14000e864`
- `0x14000ec2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x140002bcb`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x140002bcb`
- `api-ms-win-crt-private-l1-1-0!_o_getwchar` at `0x140002bd7`
- `api-ms-win-crt-private-l1-1-0!_o_getwchar` at `0x140002bd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002bff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002bff`

## pseudocode

```c
__int64 __fastcall Prompt(LPCWSTR lpString, __int64 a2, __int64 a3, int a4)
{
  FILE *v8; // rcx
  FILE *v9; // rax
  wint_t v10; // ax
  __int64 v11; // r8
  int Char2; // eax

  if ( lpString && a3 )
  {
    if ( a4 == 1 )
    {
      return 1;
    }
    else
    {
      do
      {
        v8 = o___acrt_iob_func_0(1u);
        if ( a2 )
          ShowMessageEx(v8, 1, 1, lpString, a2);
        else
          ShowMessage(v8, lpString);
        v9 = o___acrt_iob_func_0(0);
        fflush(v9);
        v10 = getwchar();
        Char2 = FindChar2(a3, v10, v11, 0);
      }
      while ( Char2 == -1 );
      return (unsigned int)(Char2 + 1);
    }
  }
  else
  {
    SetLastError(0x57u);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x140002b6c  push    rbx
0x140002b6e  push    rbp
0x140002b6f  push    rsi
0x140002b70  push    rdi
0x140002b71  sub     rsp, 38h
0x140002b75  mov     rsi, r8
0x140002b78  mov     rdi, rdx
0x140002b7b  mov     rbx, rcx
0x140002b7e  test    rcx, rcx
0x140002b81  jz      short loc_140002BFA
0x140002b83  test    r8, r8
0x140002b86  jz      short loc_140002BFA
0x140002b88  mov     ebp, 1
0x140002b8d  cmp     r9d, ebp
0x140002b90  jnz     short loc_140002B96
0x140002b92  mov     eax, ebp
0x140002b94  jmp     short loc_140002C0E
0x140002b96  mov     ecx, ebp; Ix
0x140002b98  call    _o___acrt_iob_func_0
0x140002b9d  mov     rcx, rax; Stream
0x140002ba0  test    rdi, rdi
0x140002ba3  jz      short loc_140002BB9
0x140002ba5  mov     r9, rbx
0x140002ba8  mov     [rsp+58h+var_38], rdi
0x140002bad  mov     r8d, ebp
0x140002bb0  mov     edx, ebp
0x140002bb2  call    ShowMessageEx
0x140002bb7  jmp     short loc_140002BC1
0x140002bb9  mov     rdx, rbx; lpString
0x140002bbc  call    ShowMessage
0x140002bc1  xor     ecx, ecx; Ix
0x140002bc3  call    _o___acrt_iob_func_0
0x140002bc8  mov     rcx, rax; Stream
0x140002bcb  call    cs:__imp_fflush
0x140002bd2  nop     dword ptr [rax+rax+00h]
0x140002bd7  call    cs:__imp_getwchar
0x140002bde  nop     dword ptr [rax+rax+00h]
0x140002be3  xor     r9d, r9d
0x140002be6  mov     rcx, rsi
0x140002be9  movzx   edx, ax
0x140002bec  call    FindChar2
0x140002bf1  cmp     eax, 0FFFFFFFFh
0x140002bf4  jz      short loc_140002B96
0x140002bf6  inc     eax
0x140002bf8  jmp     short loc_140002C0E
0x140002bfa  mov     ecx, 57h ; 'W'; dwErrCode
0x140002bff  call    cs:__imp_SetLastError
0x140002c06  nop     dword ptr [rax+rax+00h]
0x140002c0b  or      eax, 0FFFFFFFFh
0x140002c0e  add     rsp, 38h
0x140002c12  pop     rdi
0x140002c13  pop     rsi
0x140002c14  pop     rbp
0x140002c15  pop     rbx
0x140002c16  retn
```
