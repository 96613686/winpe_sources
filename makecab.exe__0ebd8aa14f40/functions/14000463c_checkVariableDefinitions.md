# checkVariableDefinitions

- ea: `0x14000463c`
- end: `0x1400047b1`
- name: `checkVariableDefinitions`
- size: `373`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006a6c`
- `0x140007934`

## callees

- `0x14000463c`
- `0x1400078ac`
- `0x140008620`

## import_xrefs

- `msvcrt!_strnicmp` at `0x1400046a0`
- `msvcrt!_strnicmp` at `0x1400046f5`
- `msvcrt!_strnicmp` at `0x1400046a0`
- `msvcrt!_strnicmp` at `0x1400046f5`
- `msvcrt!isdigit` at `0x1400046c9`
- `msvcrt!isdigit` at `0x1400046c9`
- `msvcrt!_stricmp` at `0x140004719`
- `msvcrt!_stricmp` at `0x140004719`

## pseudocode

```c
__int64 __fastcall checkVariableDefinitions(__int64 a1, __int64 a2)
{
  unsigned int v4; // r12d
  __int64 i; // rbx
  const char *v6; // rax
  const char *v7; // rsi
  const char **v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r15
  const char *v11; // rdi
  unsigned __int8 v12; // al
  const char *v13; // rax
  const char **v14; // rdi

  v4 = 1;
  for ( i = **(_QWORD **)(a1 + 16); i; i = *(_QWORD *)(i + 32) )
  {
    if ( (*(_DWORD *)(i + 20) & 3) == 0 )
    {
      v6 = apszVarTemplate;
      v7 = *(const char **)i;
      if ( !apszVarTemplate )
        goto LABEL_14;
      v8 = (const char **)&apszVarTemplate;
      while ( 1 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v6[v9] );
        v10 = v9 - 1;
        if ( !_strnicmp(v7, v6, v9 - 1) )
          break;
        v6 = *++v8;
        if ( !*v8 )
          goto LABEL_14;
      }
      v11 = &v7[v10];
      v12 = v7[v10];
      if ( v12 )
      {
        do
        {
          if ( !isdigit(v12) )
            break;
          v12 = *++v11;
        }
        while ( *v11 );
        if ( *v11 )
        {
LABEL_14:
          if ( !_strnicmp(v7, "Inf", 3u) && (v13 = apszParmNames) != 0 )
          {
            v14 = (const char **)&apszParmNames;
            while ( _stricmp(v7 + 3, v13) )
            {
              v13 = *++v14;
              if ( !*v14 )
                goto LABEL_19;
            }
          }
          else
          {
LABEL_19:
            ErrSet(a2, (int)"%1 %2 and variable not defined: %3", "%s%s%s", "Option", "Explicit", v7);
            printError(a1, a2);
            v4 = 0;
            *(_DWORD *)(a2 + 512) = 0;
            *(_BYTE *)a2 = 0;
            *(_DWORD *)(a2 + 544) = 0;
            *(_QWORD *)(a2 + 552) = 0;
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14000463c  push    rbx
0x14000463e  push    rbp
0x14000463f  push    rsi
0x140004640  push    rdi
0x140004641  push    r12
0x140004643  push    r13
0x140004645  push    r14
0x140004647  push    r15
0x140004649  sub     rsp, 38h
0x14000464d  mov     rax, [rcx+10h]
0x140004651  mov     r14, rdx
0x140004654  mov     r13, rcx
0x140004657  mov     r12d, 1
0x14000465d  mov     rbx, [rax]
0x140004660  jmp     loc_140004794
0x140004665  mov     eax, [rbx+14h]
0x140004668  test    al, 3
0x14000466a  jnz     loc_140004790
0x140004670  mov     rax, cs:apszVarTemplate
0x140004677  mov     rsi, [rbx]
0x14000467a  test    rax, rax
0x14000467d  jz      short loc_1400046E5
0x14000467f  lea     rdi, apszVarTemplate
0x140004686  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000468a  inc     rcx
0x14000468d  cmp     byte ptr [rax+rcx], 0
0x140004691  jnz     short loc_14000468A
0x140004693  lea     r15, [rcx-1]
0x140004697  mov     rdx, rax; String2
0x14000469a  mov     r8, r15; MaxCount
0x14000469d  mov     rcx, rsi; String1
0x1400046a0  call    cs:__imp__strnicmp
0x1400046a6  test    eax, eax
0x1400046a8  jz      short loc_1400046B8
0x1400046aa  add     rdi, 8
0x1400046ae  mov     rax, [rdi]
0x1400046b1  test    rax, rax
0x1400046b4  jnz     short loc_140004686
0x1400046b6  jmp     short loc_1400046E5
0x1400046b8  lea     rdi, [r15+rsi]
0x1400046bc  mov     al, [rdi]
0x1400046be  test    al, al
0x1400046c0  jz      loc_140004790
0x1400046c6  movzx   ecx, al; C
0x1400046c9  call    cs:__imp_isdigit
0x1400046cf  test    eax, eax
0x1400046d1  jz      short loc_1400046DC
0x1400046d3  inc     rdi
0x1400046d6  mov     al, [rdi]
0x1400046d8  test    al, al
0x1400046da  jnz     short loc_1400046C6
0x1400046dc  cmp     byte ptr [rdi], 0
0x1400046df  jz      loc_140004790
0x1400046e5  mov     r8d, 3; MaxCount
0x1400046eb  lea     rdx, aInf; "Inf"
0x1400046f2  mov     rcx, rsi; String1
0x1400046f5  call    cs:__imp__strnicmp
0x1400046fb  test    eax, eax
0x1400046fd  jnz     short loc_14000472F
0x1400046ff  mov     rax, cs:apszParmNames
0x140004706  test    rax, rax
0x140004709  jz      short loc_14000472F
0x14000470b  lea     rdi, apszParmNames
0x140004712  mov     rdx, rax; String2
0x140004715  lea     rcx, [rsi+3]; String1
0x140004719  call    cs:__imp__stricmp
0x14000471f  test    eax, eax
0x140004721  jz      short loc_140004790
0x140004723  add     rdi, 8
0x140004727  mov     rax, [rdi]
0x14000472a  test    rax, rax
0x14000472d  jnz     short loc_140004712
0x14000472f  lea     rax, pszSrc; "Explicit"
0x140004736  mov     [rsp+78h+var_50], rsi
0x14000473b  lea     r9, aOption; "Option"
0x140004742  mov     [rsp+78h+var_58], rax
0x140004747  lea     r8, aSSS; "%s%s%s"
0x14000474e  mov     rcx, r14
0x140004751  lea     rdx, a12AndVariableN; "%1 %2 and variable not defined: %3"
0x140004758  call    ErrSet
0x14000475d  mov     rdx, r14
0x140004760  mov     rcx, r13
0x140004763  call    printError
0x140004768  xor     r12d, r12d
0x14000476b  mov     dword ptr [r14+200h], 0
0x140004776  mov     byte ptr [r14], 0
0x14000477a  mov     dword ptr [r14+220h], 0
0x140004785  mov     qword ptr [r14+228h], 0
0x140004790  mov     rbx, [rbx+20h]
0x140004794  test    rbx, rbx
0x140004797  jnz     loc_140004665
0x14000479d  mov     eax, r12d
0x1400047a0  add     rsp, 38h
0x1400047a4  pop     r15
0x1400047a6  pop     r14
0x1400047a8  pop     r13
0x1400047aa  pop     r12
0x1400047ac  pop     rdi
0x1400047ad  pop     rsi
0x1400047ae  pop     rbp
0x1400047af  pop     rbx
0x1400047b0  retn
```
