# DFPParse

- ea: `0x140001de0`
- end: `0x1400021c4`
- name: `DFPParse`
- size: `996`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140007934`

## callees

- `0x140001de0`
- `0x140002c80`
- `0x140003310`
- `0x140003748`
- `0x140003a30`
- `0x140008620`
- `0x14000a564`
- `0x14000d698`
- `0x14000e412`
- `0x14000e450`
- `0x14000e4e0`
- `0x14000f010`

## import_xrefs

- `msvcrt!_read` at `0x140001ebd`
- `msvcrt!_read` at `0x140001ebd`
- `msvcrt!strspn` at `0x140002022`
- `msvcrt!strspn` at `0x140002022`
- `msvcrt!printf` at `0x140001f88`
- `msvcrt!printf` at `0x140001f88`

## string_xrefs

- `0x140002185`: `Tried to read from write-only file: %1`

## pseudocode

```c
__int64 __fastcall DFPParse(
        int *a1,
        __int64 a2,
        __int64 (__fastcall *a3)(int *, _DWORD *, __int64, char *, int, __int64),
        __int64 a4)
{
  unsigned int v7; // r14d
  int v8; // r13d
  char *v9; // rbx
  int v10; // r12d
  char *v11; // rax
  unsigned __int64 v12; // rdx
  char v13; // cl
  int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // ebx
  int v17; // eax
  size_t v18; // rcx
  char v19; // al
  char v20; // al
  unsigned int v21; // eax
  int v22; // ecx
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  char *v25; // [rsp+48h] [rbp-B8h] BYREF
  char *p_Str; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall *v27)(int *, _DWORD *, __int64, char *, int, __int64); // [rsp+58h] [rbp-A8h]
  _DWORD v28[3]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v30; // [rsp+168h] [rbp+68h]
  __int64 v31; // [rsp+1168h] [rbp+1068h]
  char Str; // [rsp+1180h] [rbp+1080h] BYREF
  _BYTE v33[1023]; // [rsp+1181h] [rbp+1081h] BYREF
  char v34[1024]; // [rsp+1580h] [rbp+1480h] BYREF

  v27 = a3;
  v28[1] = 0;
  memset_0(v28, 0, 0x1114u);
  a1[786] |= *(_DWORD *)(a2 + 52);
  v7 = 1;
  if ( !*(_DWORD *)(a2 + 44) )
  {
    v8 = 0;
LABEL_3:
    v9 = v34;
    if ( *(_DWORD *)(a2 + 48) )
    {
      v10 = 1024;
      while ( 2 )
      {
        v11 = *(char **)(a2 + 24);
        v12 = *(_QWORD *)(a2 + 32);
        while ( (unsigned __int64)v11 <= v12 )
        {
          v13 = *v11;
          if ( *v11 == 10 )
          {
            *(_QWORD *)(a2 + 24) = v11 + 1;
LABEL_23:
            *v9 = 0;
            v16 = (_DWORD)v9 - (unsigned int)v34 + 1;
            goto LABEL_24;
          }
          if ( v13 != 13 )
          {
            if ( v13 == 26 )
            {
              *(_QWORD *)(a2 + 24) = *(_QWORD *)(a2 + 16);
              *(_DWORD *)(a2 + 40) = 1;
              *(_QWORD *)(a2 + 32) = 0;
              *v9 = 0;
              if ( v9 <= v34 )
                *(_DWORD *)(a2 + 44) = 1;
              v16 = (_DWORD)v9 + 1 - (unsigned int)v34;
LABEL_24:
              if ( !v16 )
                goto LABEL_55;
              *(_DWORD *)(a4 + 528) = ++v8;
              *(_QWORD *)(a4 + 536) = v34;
              if ( a1[20] >= 2 )
                printf("%d: %s\n", v8, v34);
              Str = 0;
              memset_0(v33, 0, sizeof(v33));
              if ( a1[50] )
              {
                v24 = 1024;
                p_Str = &Str;
                v25 = v34;
                v17 = copyBounded(&p_Str, &v24, &v25, 0);
              }
              else
              {
                v17 = substituteVariables(&Str, a4);
              }
              if ( v17 )
              {
                v28[0] = 0;
                v18 = strspn(&Str, " \t");
                v19 = v33[v18 - 1];
                if ( v19 == 59 || !v19 )
                {
                  v28[0] = 1;
                }
                else if ( v19 != 46 || (v20 = v33[v18], v20 == 46) || v20 == 92 )
                {
                  if ( a1[50] )
                  {
                    v28[2] = a1[51];
                    v28[0] = 8;
                    p_Str = &v29;
                    v24 = 512;
                    v25 = &Str;
                    copyBounded(&p_Str, &v24, &v25, 0);
                  }
                  else if ( a1[49] )
                  {
                    parseFileLine(v28, a1, &Str, a4);
                  }
                  else
                  {
                    parseReferenceLine(v28, a1, &Str, a4);
                  }
                }
                else
                {
                  getCommand((__int64)v28, (__int64)a1, &Str, a4);
                }
              }
              v21 = v27(a1, v28, a2, v34, v8, a4);
              v22 = v28[0];
              v7 = v21;
              if ( v28[0] == 5 )
              {
                if ( v31 )
                {
                  GLDestroyList();
                  v22 = v28[0];
                  v31 = 0;
                  goto LABEL_46;
                }
              }
              else
              {
LABEL_46:
                if ( v22 == 13 && v30 )
                {
                  GLDestroyList();
                  v30 = 0;
                }
              }
              if ( v7 && !*(_DWORD *)(a2 + 44) )
                goto LABEL_3;
              return v7;
            }
            if ( v10 <= 1 )
            {
              *v9 = 0;
              goto LABEL_55;
            }
            --v10;
            *v9++ = v13;
          }
          *(_QWORD *)(a2 + 24) = ++v11;
        }
        if ( *(_DWORD *)(a2 + 40) )
        {
          if ( v9 <= v34 )
          {
            *v9 = 0;
            *(_DWORD *)(a2 + 44) = 1;
            break;
          }
          goto LABEL_23;
        }
        v14 = _read(*(_DWORD *)(a2 + 8), *(void **)(a2 + 16), *(_DWORD *)(a2 + 12));
        if ( v14 != *(_DWORD *)(a2 + 12) )
          *(_DWORD *)(a2 + 40) = 1;
        v15 = *(_QWORD *)(a2 + 16);
        *(_QWORD *)(a2 + 24) = v15;
        *(_QWORD *)(a2 + 32) = v14 + v15 - 1;
        if ( v10 > 0 )
          continue;
        break;
      }
    }
    else
    {
      ErrSet(a4, "Tried to read from write-only file: %1", "%s", *(const char **)a2);
    }
LABEL_55:
    v7 &= -(*(_DWORD *)(a2 + 44) != 0);
  }
  return v7;
}

```

## disassembly

```asm
0x140001de0  push    rbp
0x140001de2  push    rbx
0x140001de3  push    rsi
0x140001de4  push    rdi
0x140001de5  push    r12
0x140001de7  push    r13
0x140001de9  push    r14
0x140001deb  push    r15
0x140001ded  lea     rbp, [rsp-1898h]
0x140001df5  mov     eax, 1998h
0x140001dfa  call    _alloca_probe
0x140001dff  sub     rsp, rax
0x140001e02  mov     rax, cs:__security_cookie
0x140001e09  xor     rax, rsp
0x140001e0c  mov     [rbp+18D0h+var_50], rax
0x140001e13  mov     [rsp+19D0h+var_1978], r8
0x140001e18  mov     rdi, rdx
0x140001e1b  mov     rsi, rcx
0x140001e1e  xor     eax, eax
0x140001e20  xor     edx, edx; Val
0x140001e22  mov     [rsp+19D0h+var_196C], eax
0x140001e26  mov     r8d, 1114h; Size
0x140001e2c  lea     rcx, [rsp+19D0h+var_1970]; void *
0x140001e31  mov     r15, r9
0x140001e34  call    memset_0
0x140001e39  mov     eax, [rdi+34h]
0x140001e3c  xor     r12d, r12d
0x140001e3f  or      [rsi+0C48h], eax
0x140001e45  mov     r14d, 1
0x140001e4b  cmp     [rdi+2Ch], r12d
0x140001e4f  jnz     loc_14000219E
0x140001e55  mov     r13d, r12d
0x140001e58  lea     rbx, [rbp+18D0h+var_450]
0x140001e5f  cmp     [rdi+30h], r12d
0x140001e63  jz      loc_14000217B
0x140001e69  mov     r12d, 400h
0x140001e6f  mov     rax, [rdi+18h]
0x140001e73  mov     rdx, [rdi+20h]
0x140001e77  jmp     short loc_140001EA7
0x140001e79  mov     cl, [rax]
0x140001e7b  cmp     cl, 0Ah
0x140001e7e  jz      loc_140001F27
0x140001e84  cmp     cl, 0Dh
0x140001e87  jz      short loc_140001EA0
0x140001e89  cmp     cl, 1Ah
0x140001e8c  jz      short loc_140001EED
0x140001e8e  cmp     r12d, 1
0x140001e92  jle     loc_14000216A
0x140001e98  dec     r12d
0x140001e9b  mov     [rbx], cl
0x140001e9d  inc     rbx
0x140001ea0  inc     rax
0x140001ea3  mov     [rdi+18h], rax
0x140001ea7  cmp     rax, rdx
0x140001eaa  jbe     short loc_140001E79
0x140001eac  cmp     dword ptr [rdi+28h], 0
0x140001eb0  jnz     short loc_140001F30
0x140001eb2  mov     r8d, [rdi+0Ch]; MaxCharCount
0x140001eb6  mov     rdx, [rdi+10h]; DstBuf
0x140001eba  mov     ecx, [rdi+8]; FileHandle
0x140001ebd  call    cs:__imp__read
0x140001ec3  cmp     eax, [rdi+0Ch]
0x140001ec6  jz      short loc_140001ECF
0x140001ec8  mov     dword ptr [rdi+28h], 1
0x140001ecf  mov     rcx, [rdi+10h]
0x140001ed3  mov     [rdi+18h], rcx
0x140001ed7  dec     rcx
0x140001eda  cdqe
0x140001edc  add     rcx, rax
0x140001edf  mov     [rdi+20h], rcx
0x140001ee3  test    r12d, r12d
0x140001ee6  jg      short loc_140001E6F
0x140001ee8  jmp     loc_140002194
0x140001eed  mov     rax, [rdi+10h]
0x140001ef1  xor     r12d, r12d
0x140001ef4  mov     [rdi+18h], rax
0x140001ef8  lea     rax, [rbp+18D0h+var_450]
0x140001eff  mov     dword ptr [rdi+28h], 1
0x140001f06  mov     [rdi+20h], r12
0x140001f0a  mov     [rbx], r12b
0x140001f0d  cmp     rbx, rax
0x140001f10  ja      short loc_140001F19
0x140001f12  mov     dword ptr [rdi+2Ch], 1
0x140001f19  inc     rbx
0x140001f1c  lea     rax, [rbp+18D0h+var_450]
0x140001f23  sub     ebx, eax
0x140001f25  jmp     short loc_140001F51
0x140001f27  inc     rax
0x140001f2a  mov     [rdi+18h], rax
0x140001f2e  jmp     short loc_140001F40
0x140001f30  lea     rax, [rbp+18D0h+var_450]
0x140001f37  cmp     rbx, rax
0x140001f3a  jbe     loc_14000216F
0x140001f40  xor     r12d, r12d
0x140001f43  lea     rax, [rbp+18D0h+var_450]
0x140001f4a  mov     [rbx], r12b
0x140001f4d  sub     ebx, eax
0x140001f4f  inc     ebx
0x140001f51  test    ebx, ebx
0x140001f53  jz      loc_140002194
0x140001f59  inc     r13d
0x140001f5c  lea     rax, [rbp+18D0h+var_450]
0x140001f63  mov     [r15+210h], r13d
0x140001f6a  mov     [r15+218h], rax
0x140001f71  cmp     dword ptr [rsi+50h], 2
0x140001f75  jl      short loc_140001F8E
0x140001f77  lea     r8, [rbp+18D0h+var_450]
0x140001f7e  mov     edx, r13d
0x140001f81  lea     rcx, Format; "%d: %s\n"
0x140001f88  call    cs:__imp_printf
0x140001f8e  xor     edx, edx; Val
0x140001f90  mov     [rbp+18D0h+Str], r12b
0x140001f97  mov     r8d, 3FFh; Size
0x140001f9d  lea     rcx, [rbp+18D0h+var_84F]; void *
0x140001fa4  call    memset_0
0x140001fa9  cmp     [rsi+0C8h], r12d
0x140001fb0  jz      short loc_140001FEB
0x140001fb2  lea     rax, [rbp+18D0h+Str]
0x140001fb9  mov     [rsp+19D0h+var_1990], 400h
0x140001fc1  mov     [rsp+19D0h+var_1980], rax
0x140001fc6  lea     r8, [rsp+19D0h+var_1988]
0x140001fcb  lea     rax, [rbp+18D0h+var_450]
0x140001fd2  xor     r9d, r9d
0x140001fd5  lea     rdx, [rsp+19D0h+var_1990]
0x140001fda  mov     [rsp+19D0h+var_1988], rax
0x140001fdf  lea     rcx, [rsp+19D0h+var_1980]
0x140001fe4  call    copyBounded
0x140001fe9  jmp     short loc_140002007
0x140001feb  mov     r9, [rsi+10h]
0x140001fef  lea     r8, [rbp+18D0h+var_450]
0x140001ff6  lea     rcx, [rbp+18D0h+Str]; Str
0x140001ffd  mov     [rsp+19D0h+var_19B0], r15; __int64
0x140002002  call    substituteVariables
0x140002007  test    eax, eax
0x140002009  jz      loc_1400020F4
0x14000200f  lea     rdx, Control; " \t"
0x140002016  mov     [rsp+19D0h+var_1970], r12d
0x14000201b  lea     rcx, [rbp+18D0h+Str]; Str
0x140002022  call    cs:__imp_strspn
0x140002028  mov     rcx, rax
0x14000202b  mov     al, [rbp+rax+18D0h+Str]
0x140002032  cmp     al, 3Bh ; ';'
0x140002034  jz      loc_1400020EC
0x14000203a  test    al, al
0x14000203c  jz      loc_1400020EC
0x140002042  cmp     al, 2Eh ; '.'
0x140002044  jnz     short loc_140002071
0x140002046  mov     al, [rbp+rcx+18D0h+var_84F]
0x14000204d  cmp     al, 2Eh ; '.'
0x14000204f  jz      short loc_140002071
0x140002051  cmp     al, 5Ch ; '\'
0x140002053  jz      short loc_140002071
0x140002055  mov     r9, r15
0x140002058  lea     r8, [rbp+18D0h+Str]
0x14000205f  mov     rdx, rsi
0x140002062  lea     rcx, [rsp+19D0h+var_1970]
0x140002067  call    getCommand
0x14000206c  jmp     loc_1400020F4
0x140002071  cmp     [rsi+0C8h], r12d
0x140002078  jz      short loc_1400020C3
0x14000207a  mov     eax, [rsi+0CCh]
0x140002080  lea     r8, [rsp+19D0h+var_1988]
0x140002085  mov     [rsp+19D0h+var_1968], eax
0x140002089  lea     rdx, [rsp+19D0h+var_1990]
0x14000208e  lea     rax, [rsp+19D0h+var_1964]
0x140002093  mov     [rsp+19D0h+var_1970], 8
0x14000209b  mov     [rsp+19D0h+var_1980], rax
0x1400020a0  lea     rcx, [rsp+19D0h+var_1980]
0x1400020a5  lea     rax, [rbp+18D0h+Str]
0x1400020ac  mov     [rsp+19D0h+var_1990], 200h
0x1400020b4  xor     r9d, r9d
0x1400020b7  mov     [rsp+19D0h+var_1988], rax
0x1400020bc  call    copyBounded
0x1400020c1  jmp     short loc_1400020F4
0x1400020c3  lea     r8, [rbp+18D0h+Str]
0x1400020ca  mov     r9, r15
0x1400020cd  lea     rcx, [rsp+19D0h+var_1970]
0x1400020d2  mov     rdx, rsi
0x1400020d5  cmp     [rsi+0C4h], r12d
0x1400020dc  jz      short loc_1400020E5
0x1400020de  call    parseFileLine
0x1400020e3  jmp     short loc_1400020F4
0x1400020e5  call    parseReferenceLine
0x1400020ea  jmp     short loc_1400020F4
0x1400020ec  mov     [rsp+19D0h+var_1970], 1
0x1400020f4  mov     rax, [rsp+19D0h+var_1978]
0x1400020f9  lea     r9, [rbp+18D0h+var_450]
0x140002100  mov     [rsp+19D0h+var_19A8], r15
0x140002105  lea     rdx, [rsp+19D0h+var_1970]
0x14000210a  mov     r8, rdi
0x14000210d  mov     dword ptr [rsp+19D0h+var_19B0], r13d
0x140002112  mov     rcx, rsi
0x140002115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000211a  mov     ecx, [rsp+19D0h+var_1970]
0x14000211e  mov     r14d, eax
0x140002121  cmp     ecx, 5
0x140002124  jnz     short loc_140002142
0x140002126  mov     rcx, [rbp+18D0h+var_868]
0x14000212d  test    rcx, rcx
0x140002130  jz      short loc_140002159
0x140002132  call    GLDestroyList
0x140002137  mov     ecx, [rsp+19D0h+var_1970]
0x14000213b  mov     [rbp+18D0h+var_868], r12
0x140002142  cmp     ecx, 0Dh
0x140002145  jnz     short loc_140002159
0x140002147  mov     rcx, [rbp+18D0h+var_1868]
0x14000214b  test    rcx, rcx
0x14000214e  jz      short loc_140002159
0x140002150  call    GLDestroyList
0x140002155  mov     [rbp+18D0h+var_1868], r12
0x140002159  test    r14d, r14d
0x14000215c  jz      short loc_14000219E
0x14000215e  cmp     [rdi+2Ch], r12d
0x140002162  jz      loc_140001E58
0x140002168  jmp     short loc_14000219E
0x14000216a  mov     byte ptr [rbx], 0
0x14000216d  jmp     short loc_140002194
0x14000216f  mov     byte ptr [rbx], 0
0x140002172  mov     dword ptr [rdi+2Ch], 1
0x140002179  jmp     short loc_140002194
0x14000217b  mov     r9, [rdi]
0x14000217e  lea     r8, aS_4; "%s"
0x140002185  lea     rdx, aTriedToReadFro; "Tried to read from write-only file: %1"
0x14000218c  mov     rcx, r15
0x14000218f  call    ErrSet
0x140002194  mov     eax, [rdi+2Ch]
0x140002197  neg     eax
0x140002199  sbb     ecx, ecx
0x14000219b  and     r14d, ecx
0x14000219e  mov     eax, r14d
0x1400021a1  mov     rcx, [rbp+18D0h+var_50]
0x1400021a8  xor     rcx, rsp; StackCookie
0x1400021ab  call    __security_check_cookie
0x1400021b0  add     rsp, 1998h
0x1400021b7  pop     r15
0x1400021b9  pop     r14
0x1400021bb  pop     r13
0x1400021bd  pop     r12
0x1400021bf  pop     rdi
0x1400021c0  pop     rsi
0x1400021c1  pop     rbx
0x1400021c2  pop     rbp
0x1400021c3  retn
```
