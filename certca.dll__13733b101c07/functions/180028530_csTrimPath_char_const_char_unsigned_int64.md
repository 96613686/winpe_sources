# csTrimPath(char const *,char *,unsigned __int64)

- ea: `0x180028530`
- end: `0x180028747`
- name: `?csTrimPath@@YAPEBDPEBDPEAD_K@Z`
- size: `535`
- prototype: `char *__fastcall(const char *Str1, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180028260`
- `0x180028360`

## callees

- `0x180016434`
- `0x180028530`
- `0x18003827a`

## import_xrefs

- `msvcrt!strchr` at `0x18002858e`
- `msvcrt!strchr` at `0x18002858e`
- `msvcrt!strrchr` at `0x18002861a`
- `msvcrt!strrchr` at `0x18002861a`

## pseudocode

```c
char *__fastcall csTrimPath(const char *Str1, char *a2)
{
  const char *v2; // r14
  unsigned __int64 v4; // r13
  unsigned __int64 v5; // rax
  const char *v6; // rdi
  char *v7; // rax
  char *v8; // rbx
  unsigned int v9; // ecx
  const char *v10; // r8
  char *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  char *v14; // rax
  const char *v15; // rsi
  int v16; // ebp
  unsigned int v17; // ebx
  __int64 v18; // rax
  char *v19; // rbx
  char *v20; // rbp
  char v21; // si
  unsigned int v23; // [rsp+70h] [rbp+18h]
  char *v24; // [rsp+78h] [rbp+20h]

  v2 = "unknown.cpp";
  if ( Str1 )
    v2 = Str1;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( v2[v5] );
  if ( v5 < 0x208 )
  {
    *a2 = 0;
    v6 = v2;
    v7 = strchr(v2, 124);
    v8 = v7;
    if ( v7 && v7[1] == 124 )
    {
      v9 = (_DWORD)v7 - (_DWORD)v2;
      v10 = v2;
      v11 = a2;
      if ( (unsigned int)((_DWORD)v7 - (_DWORD)v2) > 0x101 )
        v9 = 257;
      v12 = v9;
      v13 = 520;
      do
      {
        if ( !v12 )
          break;
        if ( !*v10 )
          break;
        *v11++ = *v10++;
        --v12;
        --v13;
      }
      while ( v13 );
      v14 = v11 - 1;
      if ( v13 )
        v14 = v11;
      *v14 = 0;
      if ( !v13 || StringCchCatA(a2, 0x208u, ": ") )
        return (char *)v2;
      v6 = v8 + 2;
    }
    v24 = strrchr(v6, 92);
    v15 = v24;
    if ( v24 )
    {
      v16 = 1;
      do
      {
        if ( v15 <= v6 )
          break;
        v17 = HIDWORD(v24);
        v23 = (unsigned int)v15--;
        HIDWORD(v24) = HIDWORD(v15);
        if ( *v15 == 92 )
        {
          if ( !strncmp_0(v15, "\\..\\", 4u) || !strncmp_0(v15, "\\.\\", 3u) )
          {
            ++v16;
          }
          else
          {
            --v16;
            v6 = (const char *)__PAIR64__(v17, v23);
          }
        }
      }
      while ( v16 );
      v18 = -1;
      do
        ++v18;
      while ( a2[v18] );
      do
        ++v4;
      while ( v6[v4] );
      if ( v4 < 520 - v18 )
      {
        v19 = &a2[v18];
        v20 = a2 + 519;
        while ( 1 )
        {
          while ( 1 )
          {
            if ( !*v6 )
            {
              if ( v19 < v20 )
              {
                *v19 = 0;
                return a2;
              }
              return (char *)v2;
            }
            if ( v19 >= v20 )
              return (char *)v2;
            v21 = *v6;
            if ( *v6 == 92 )
              break;
LABEL_39:
            ++v6;
            *v19++ = v21;
          }
          if ( !strncmp_0(v6, "\\..\\", 4u) )
          {
            v6 += 3;
          }
          else
          {
            if ( strncmp_0(v6, "\\.\\", 3u) )
              goto LABEL_39;
            v6 += 2;
          }
        }
      }
    }
  }
  return (char *)v2;
}

```

## disassembly

```asm
0x180028530  mov     [rsp+arg_8], rbx
0x180028535  mov     [rsp+arg_10], r8
0x18002853a  push    rbp
0x18002853b  push    rsi
0x18002853c  push    rdi
0x18002853d  push    r12
0x18002853f  push    r13
0x180028541  push    r14
0x180028543  push    r15
0x180028545  sub     rsp, 20h
0x180028549  xor     ebp, ebp
0x18002854b  lea     r14, aUnknownCpp; "unknown.cpp"
0x180028552  test    rcx, rcx
0x180028555  mov     r12, rdx
0x180028558  cmovnz  r14, rcx
0x18002855c  or      r13, 0FFFFFFFFFFFFFFFFh
0x180028560  mov     rax, r13
0x180028563  inc     rax
0x180028566  cmp     [r14+rax], bpl
0x18002856a  jnz     short loc_180028563
0x18002856c  mov     r15d, 208h
0x180028572  cmp     rax, r15
0x180028575  jnb     loc_18002872F
0x18002857b  mov     [rdx], bpl
0x18002857e  mov     rcx, r14; Str
0x180028581  mov     edx, 7Ch ; '|'; Val
0x180028586  mov     [rsp+58h+arg_0], r14
0x18002858b  mov     rdi, r14
0x18002858e  call    cs:__imp_strchr
0x180028594  mov     rbx, rax
0x180028597  test    rax, rax
0x18002859a  jz      short loc_180028612
0x18002859c  cmp     byte ptr [rax+1], 7Ch ; '|'
0x1800285a0  jnz     short loc_180028612
0x1800285a2  mov     eax, 101h
0x1800285a7  mov     ecx, ebx
0x1800285a9  sub     ecx, r14d
0x1800285ac  mov     r8, r14
0x1800285af  cmp     ecx, eax
0x1800285b1  mov     rdx, r12
0x1800285b4  cmova   ecx, eax
0x1800285b7  mov     eax, ecx
0x1800285b9  mov     ecx, r15d
0x1800285bc  test    rax, rax
0x1800285bf  jz      short loc_1800285DB
0x1800285c1  mov     r9b, [r8]
0x1800285c4  test    r9b, r9b
0x1800285c7  jz      short loc_1800285DB
0x1800285c9  mov     [rdx], r9b
0x1800285cc  inc     r8
0x1800285cf  inc     rdx
0x1800285d2  dec     rax
0x1800285d5  sub     rcx, 1
0x1800285d9  jnz     short loc_1800285BC
0x1800285db  test    rcx, rcx
0x1800285de  lea     rax, [rdx-1]
0x1800285e2  cmovnz  rax, rdx
0x1800285e6  mov     [rax], bpl
0x1800285e9  jz      loc_18002872F
0x1800285ef  lea     r8, asc_180063288; ": "
0x1800285f6  mov     rdx, r15; unsigned __int64
0x1800285f9  mov     rcx, r12; char *
0x1800285fc  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180028601  test    eax, eax
0x180028603  jnz     loc_18002872F
0x180028609  lea     rdi, [rbx+2]
0x18002860d  mov     [rsp+58h+arg_0], rdi
0x180028612  mov     edx, 5Ch ; '\'; Ch
0x180028617  mov     rcx, rdi; Str
0x18002861a  call    cs:__imp_strrchr
0x180028620  mov     [rsp+58h+arg_18], rax
0x180028625  mov     rsi, rax
0x180028628  test    rax, rax
0x18002862b  jz      loc_18002872F
0x180028631  mov     ebp, 1
0x180028636  cmp     rsi, rdi
0x180028639  jbe     short loc_18002869D
0x18002863b  mov     ebx, dword ptr [rsp+58h+arg_18+4]
0x18002863f  mov     dword ptr [rsp+58h+arg_10], esi
0x180028643  dec     rsi
0x180028646  mov     [rsp+58h+arg_18], rsi
0x18002864b  cmp     byte ptr [rsi], 5Ch ; '\'
0x18002864e  jnz     short loc_180028699
0x180028650  mov     r8d, 4; MaxCount
0x180028656  lea     rdx, asc_18006AE5C; "\\..\\"
0x18002865d  mov     rcx, rsi; Str1
0x180028660  call    strncmp_0
0x180028665  test    eax, eax
0x180028667  jz      short loc_180028697
0x180028669  mov     r8d, 3; MaxCount
0x18002866f  lea     rdx, asc_18006AE64; "\\.\\"
0x180028676  mov     rcx, rsi; Str1
0x180028679  call    strncmp_0
0x18002867e  test    eax, eax
0x180028680  jz      short loc_180028697
0x180028682  mov     eax, dword ptr [rsp+58h+arg_10]
0x180028686  dec     ebp
0x180028688  mov     dword ptr [rsp+58h+arg_0], eax
0x18002868c  mov     dword ptr [rsp+58h+arg_0+4], ebx
0x180028690  mov     rdi, [rsp+58h+arg_0]
0x180028695  jmp     short loc_180028699
0x180028697  inc     ebp
0x180028699  test    ebp, ebp
0x18002869b  jnz     short loc_180028636
0x18002869d  mov     rax, r13
0x1800286a0  inc     rax
0x1800286a3  cmp     byte ptr [r12+rax], 0
0x1800286a8  jnz     short loc_1800286A0
0x1800286aa  inc     r13
0x1800286ad  cmp     byte ptr [rdi+r13], 0
0x1800286b2  jnz     short loc_1800286AA
0x1800286b4  sub     r15, rax
0x1800286b7  cmp     r13, r15
0x1800286ba  jnb     short loc_18002872F
0x1800286bc  lea     rbx, [rax+r12]
0x1800286c0  lea     rbp, [r12+207h]
0x1800286c8  jmp     short loc_18002871F
0x1800286ca  cmp     rbx, rbp
0x1800286cd  jnb     short loc_18002872F
0x1800286cf  mov     sil, [rdi]
0x1800286d2  cmp     sil, 5Ch ; '\'
0x1800286d6  jnz     short loc_180028716
0x1800286d8  mov     r8d, 4; MaxCount
0x1800286de  lea     rdx, asc_18006AE5C; "\\..\\"
0x1800286e5  mov     rcx, rdi; Str1
0x1800286e8  call    strncmp_0
0x1800286ed  test    eax, eax
0x1800286ef  jnz     short loc_1800286F7
0x1800286f1  add     rdi, 3
0x1800286f5  jmp     short loc_18002871F
0x1800286f7  mov     r8d, 3; MaxCount
0x1800286fd  lea     rdx, asc_18006AE64; "\\.\\"
0x180028704  mov     rcx, rdi; Str1
0x180028707  call    strncmp_0
0x18002870c  test    eax, eax
0x18002870e  jnz     short loc_180028716
0x180028710  add     rdi, 2
0x180028714  jmp     short loc_18002871F
0x180028716  inc     rdi
0x180028719  mov     [rbx], sil
0x18002871c  inc     rbx
0x18002871f  cmp     byte ptr [rdi], 0
0x180028722  jnz     short loc_1800286CA
0x180028724  cmp     rbx, rbp
0x180028727  jnb     short loc_18002872F
0x180028729  mov     byte ptr [rbx], 0
0x18002872c  mov     r14, r12
0x18002872f  mov     rbx, [rsp+58h+arg_8]
0x180028734  mov     rax, r14
0x180028737  add     rsp, 20h
0x18002873b  pop     r15
0x18002873d  pop     r14
0x18002873f  pop     r13
0x180028741  pop     r12
0x180028743  pop     rdi
0x180028744  pop     rsi
0x180028745  pop     rbp
0x180028746  retn
```
