# DFPParseVarAssignment

- ea: `0x1400021cc`
- end: `0x1400022d6`
- name: `DFPParseVarAssignment`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400038b8`
- `0x140007504`

## callees

- `0x1400021cc`
- `0x140003934`
- `0x140008620`
- `0x14000e406`

## import_xrefs

- `msvcrt!strspn` at `0x140002272`
- `msvcrt!strspn` at `0x14000228e`
- `msvcrt!strspn` at `0x140002272`
- `msvcrt!strspn` at `0x14000228e`
- `msvcrt!strpbrk` at `0x140002212`
- `msvcrt!strpbrk` at `0x140002212`

## string_xrefs

- `0x1400021f7`: `No variable name in %1 command`

## pseudocode

```c
__int64 __fastcall DFPParseVarAssignment(__int64 a1, __int64 a2, const char *a3, __int64 a4)
{
  char *v7; // rax
  const char *v8; // rbp
  int v9; // ecx
  __int64 v10; // rbx
  const char *v11; // rbx
  const char *v12; // rbx
  int v13; // eax
  int v14; // r9d

  if ( *a3 )
  {
    v7 = strpbrk(a3, "= \t");
    v8 = v7;
    if ( v7 )
    {
      v9 = (_DWORD)v7 - (_DWORD)a3;
      if ( (int)v7 - (int)a3 >= 32 )
      {
        ErrSet(a4, "Variable name exceeds maximum length(%1): %2", "%d%s", 31, a3);
        return 0;
      }
      v10 = v9;
      memcpy_0((void *)(a1 + 8), a3, v9);
      *(_BYTE *)(v10 + a1 + 8) = 0;
      v11 = &v8[strspn(v8, " \t")];
      if ( *v11 == 61 )
      {
        v12 = v11 + 1;
        v13 = strspn(v12, " \t");
        return processLineWithQuotes((int)a1 + 40, 256, v13 + (int)v12, v14);
      }
    }
    ErrSet(a4, "%1 assignment operator missing", "%c", 61);
    return 0;
  }
  ErrSet(a4, "No variable name in %1 command", "%s", "Set");
  return 0;
}

```

## disassembly

```asm
0x1400021cc  push    rbx
0x1400021ce  push    rbp
0x1400021cf  push    rsi
0x1400021d0  push    rdi
0x1400021d1  push    r14
0x1400021d3  sub     rsp, 30h
0x1400021d7  cmp     byte ptr [r8], 0
0x1400021db  mov     rsi, r9
0x1400021de  mov     rdi, r8
0x1400021e1  mov     r14, rcx
0x1400021e4  jnz     short loc_140002208
0x1400021e6  lea     r9, aSet; "Set"
0x1400021ed  mov     rcx, rsi
0x1400021f0  lea     r8, aS_4; "%s"
0x1400021f7  lea     rdx, aNoVariableName; "No variable name in %1 command"
0x1400021fe  call    ErrSet
0x140002203  jmp     loc_1400022C9
0x140002208  lea     rdx, asc_140011C88; "= \t"
0x14000220f  mov     rcx, rdi; Str
0x140002212  call    cs:__imp_strpbrk
0x140002218  mov     rbp, rax
0x14000221b  test    rax, rax
0x14000221e  jz      loc_1400022AD
0x140002224  mov     ecx, ebp
0x140002226  sub     ecx, edi
0x140002228  cmp     ecx, 20h ; ' '
0x14000222b  jl      short loc_140002250
0x14000222d  mov     r9d, 1Fh
0x140002233  mov     [rsp+58h+var_38], rdi
0x140002238  lea     r8, aDS; "%d%s"
0x14000223f  mov     rcx, rsi
0x140002242  lea     rdx, aVariableNameEx; "Variable name exceeds maximum length(%1"...
0x140002249  call    ErrSet
0x14000224e  jmp     short loc_1400022C9
0x140002250  movsxd  rbx, ecx
0x140002253  mov     rdx, rdi; Src
0x140002256  mov     r8, rbx; Size
0x140002259  lea     rcx, [r14+8]; void *
0x14000225d  call    memcpy_0
0x140002262  lea     rdx, Control; " \t"
0x140002269  mov     byte ptr [rbx+r14+8], 0
0x14000226f  mov     rcx, rbp; Str
0x140002272  call    cs:__imp_strspn
0x140002278  lea     rbx, [rax+rbp]
0x14000227c  cmp     byte ptr [rbx], 3Dh ; '='
0x14000227f  jnz     short loc_1400022AD
0x140002281  inc     rbx
0x140002284  lea     rdx, Control; " \t"
0x14000228b  mov     rcx, rbx; Str
0x14000228e  call    cs:__imp_strspn
0x140002294  lea     rcx, [r14+28h]
0x140002298  mov     [rsp+58h+var_30], rsi
0x14000229d  mov     edx, 100h
0x1400022a2  lea     r8, [rax+rbx]
0x1400022a6  call    processLineWithQuotes
0x1400022ab  jmp     short loc_1400022CB
0x1400022ad  mov     r9d, 3Dh ; '='
0x1400022b3  lea     r8, aC; "%c"
0x1400022ba  lea     rdx, a1AssignmentOpe; "%1 assignment operator missing"
0x1400022c1  mov     rcx, rsi
0x1400022c4  call    ErrSet
0x1400022c9  xor     eax, eax
0x1400022cb  add     rsp, 30h
0x1400022cf  pop     r14
0x1400022d1  pop     rdi
0x1400022d2  pop     rsi
0x1400022d3  pop     rbp
0x1400022d4  pop     rbx
0x1400022d5  retn
```
