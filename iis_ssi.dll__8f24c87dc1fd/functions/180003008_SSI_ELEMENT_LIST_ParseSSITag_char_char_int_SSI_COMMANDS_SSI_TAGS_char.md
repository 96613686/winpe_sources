# SSI_ELEMENT_LIST::ParseSSITag(char * *,char *,int *,SSI_COMMANDS *,SSI_TAGS *,char *)

- ea: `0x180003008`
- end: `0x1800032fe`
- name: `?ParseSSITag@SSI_ELEMENT_LIST@@CAHPEAPEADPEADPEAHPEAW4SSI_COMMANDS@@PEAW4SSI_TAGS@@1@Z`
- size: `758`
- prototype: `__int64 __fastcall(const char **, char *, int *, enum SSI_COMMANDS *, enum SSI_TAGS *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002dc0`

## callees

- `0x180003008`
- `0x180005726`
- `0x180005732`
- `0x180005756`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180003161`
- `msvcrt!_strnicmp` at `0x180003216`
- `msvcrt!_strnicmp` at `0x180003161`
- `msvcrt!_strnicmp` at `0x180003216`
- `msvcrt!isspace` at `0x1800031b6`
- `msvcrt!isspace` at `0x1800031b6`
- `msvcrt!tolower` at `0x180003130`
- `msvcrt!tolower` at `0x1800031e4`
- `msvcrt!tolower` at `0x180003130`
- `msvcrt!tolower` at `0x1800031e4`

## pseudocode

```c
__int64 __fastcall SSI_ELEMENT_LIST::ParseSSITag(
        const char **a1,
        char *a2,
        int *a3,
        enum SSI_COMMANDS *a4,
        enum SSI_TAGS *a5,
        char *a6)
{
  unsigned int v6; // ebx
  int v7; // r13d
  unsigned int v9; // r12d
  int v10; // r15d
  const char *v11; // r14
  __int64 v12; // rbp
  const char *v13; // rsi
  const char *v14; // rax
  const char *v15; // rdi
  unsigned int v16; // ebx
  __int64 result; // rax
  const char *v18; // rbp
  unsigned int v19; // esi
  int v20; // eax
  const char *v21; // rcx
  unsigned int v22; // edx
  const char *i; // rbx
  unsigned int v24; // esi
  int v25; // eax
  const char *v26; // rcx
  unsigned int v27; // edx
  const char *v28; // rcx
  char *v29; // rax
  char *v30; // rbx
  void *v31; // rax
  unsigned __int64 v32; // rax
  char *v33; // rdx
  __int64 v34; // r8
  char *v35; // rcx

  *a3 = 0;
  v6 = (_DWORD)a2 - *(_DWORD *)a1;
  v7 = (int)a2;
  if ( v6 < 4 )
  {
    if ( v6 < 2 )
      return 1;
    goto LABEL_5;
  }
  if ( strncmp_0(*a1, "<!--", 4u) )
  {
LABEL_5:
    if ( !strncmp_0(*a1, "<%", 2u) )
    {
      v9 = 1;
      v10 = 37;
      goto LABEL_7;
    }
    return 1;
  }
  v9 = 0;
  v10 = 45;
LABEL_7:
  v11 = "%>";
  if ( !v9 )
    v11 = "-->";
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  v13 = *a1;
  while ( 1 )
  {
    v14 = (const char *)memchr_0(v13, v10, v6);
    v15 = v14;
    if ( !v14 )
      return 0;
    v16 = (_DWORD)v13 - (_DWORD)v14 + v6;
    if ( v16 < (unsigned int)v12 )
      return 0;
    if ( !memcmp_0(v14, v11, (unsigned int)v12) )
      break;
    v13 = v15 + 1;
    v6 = v16 - 1;
    if ( !v6 )
      return 0;
  }
  v18 = (const char *)memchr_0(*a1, 35, v15 - *a1);
  if ( !v18 )
    return 1;
  v19 = 0;
  if ( !SSICmdMap )
    return 1;
  while ( 1 )
  {
    v20 = tolower(*v18);
    v21 = (const char *)*(&SSICmdMap + 2 * v19);
    if ( *v21 == v20 )
    {
      v22 = dword_18000A0A8[4 * v19];
      if ( v7 - (int)v18 >= v22 && !_strnicmp(v21, v18, v22) )
        break;
    }
    if ( !*(&SSICmdMap + 2 * ++v19) )
      return 1;
  }
  *(_DWORD *)a4 = dword_18000A0AC[4 * v19];
  for ( i = &v18[dword_18000A0A8[4 * v19]]; i < v15; ++i )
  {
    if ( !isspace(*(unsigned __int8 *)i) )
      goto LABEL_29;
  }
  i = 0;
LABEL_29:
  if ( !i )
    return 1;
  v24 = 0;
  if ( !SSITagMap )
    return 1;
  while ( 1 )
  {
    v25 = tolower(*i);
    v26 = (const char *)*(&SSITagMap + 2 * v24);
    if ( *v26 == v25 )
    {
      v27 = dword_18000A008[4 * v24];
      if ( v7 - (int)i >= v27 && !_strnicmp(v26, i, v27) )
        break;
    }
    if ( !*(&SSITagMap + 2 * ++v24) )
      return 1;
  }
  *(_DWORD *)a5 = dword_18000A00C[4 * v24];
  v28 = &i[dword_18000A008[4 * v24]];
  v29 = (char *)memchr_0(v28, 34, v15 - v28);
  if ( !v29 )
    return 1;
  v30 = v29 + 1;
  v31 = memchr_0(v29 + 1, 34, v15 - (v29 + 1));
  if ( !v31 )
    return 1;
  v32 = (unsigned int)((_DWORD)v31 - (_DWORD)v30);
  if ( v32 <= 0x7FFFFFFE )
  {
    v33 = a6;
    v34 = 2050;
    do
    {
      if ( !v32 )
        break;
      if ( !*v30 )
        break;
      *v33++ = *v30++;
      --v32;
      --v34;
    }
    while ( v34 );
    v35 = v33 - 1;
    if ( v34 )
      v35 = v33;
    *v35 = 0;
  }
  else
  {
    *a6 = 0;
  }
  result = 1;
  *a3 = 1;
  *a1 = &v15[(v9 ^ 1LL) + 2];
  return result;
}

```

## disassembly

```asm
0x180003008  mov     rax, rsp
0x18000300b  mov     [rax+10h], rbx
0x18000300f  mov     [rax+20h], r9
0x180003013  mov     [rax+18h], r8
0x180003017  mov     [rax+8], rcx
0x18000301b  push    rbp
0x18000301c  push    rsi
0x18000301d  push    rdi
0x18000301e  push    r12
0x180003020  push    r13
0x180003022  push    r14
0x180003024  push    r15
0x180003026  sub     rsp, 20h
0x18000302a  mov     ebx, edx
0x18000302c  mov     dword ptr [r8], 0
0x180003033  sub     ebx, [rcx]
0x180003035  mov     r8d, 4; MaxCount
0x18000303b  mov     r13, rdx
0x18000303e  mov     rdi, rcx
0x180003041  cmp     ebx, r8d
0x180003044  jb      short loc_180003062
0x180003046  mov     rcx, [rcx]; Str1
0x180003049  lea     rdx, Str2; "<!--"
0x180003050  call    strncmp_0
0x180003055  test    eax, eax
0x180003057  jnz     short loc_18000306B
0x180003059  xor     r12d, r12d
0x18000305c  lea     r15d, [rax+2Dh]
0x180003060  jmp     short loc_180003090
0x180003062  cmp     ebx, 2
0x180003065  jb      loc_18000317D
0x18000306b  mov     rcx, [rdi]; Str1
0x18000306e  lea     rdx, asc_180007E1C; "<%"
0x180003075  mov     r8d, 2; MaxCount
0x18000307b  call    strncmp_0
0x180003080  test    eax, eax
0x180003082  jnz     loc_18000317D
0x180003088  lea     r12d, [rax+1]
0x18000308c  lea     r15d, [rax+25h]
0x180003090  test    r12d, r12d
0x180003093  lea     rax, asc_180007E24; "-->"
0x18000309a  lea     r14, asc_180007E20; "%>"
0x1800030a1  cmovz   r14, rax
0x1800030a5  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800030a9  inc     rbp
0x1800030ac  cmp     byte ptr [r14+rbp], 0
0x1800030b1  jnz     short loc_1800030A9
0x1800030b3  test    ebx, ebx
0x1800030b5  jz      short loc_1800030F3
0x1800030b7  mov     rsi, [rdi]
0x1800030ba  mov     r8d, ebx; MaxCount
0x1800030bd  mov     edx, r15d; Val
0x1800030c0  mov     rcx, rsi; Buf
0x1800030c3  call    memchr_0
0x1800030c8  mov     rdi, rax
0x1800030cb  test    rax, rax
0x1800030ce  jz      short loc_1800030F3
0x1800030d0  sub     esi, edi
0x1800030d2  add     ebx, esi
0x1800030d4  cmp     ebx, ebp
0x1800030d6  jb      short loc_1800030F3
0x1800030d8  mov     r8d, ebp; Size
0x1800030db  mov     rdx, r14; Buf2
0x1800030de  mov     rcx, rax; Buf1
0x1800030e1  call    memcmp_0
0x1800030e6  test    eax, eax
0x1800030e8  jz      short loc_1800030FA
0x1800030ea  lea     rsi, [rdi+1]
0x1800030ee  sub     ebx, 1
0x1800030f1  jnz     short loc_1800030BA
0x1800030f3  xor     eax, eax
0x1800030f5  jmp     loc_180003182
0x1800030fa  mov     r15, [rsp+58h+arg_0]
0x1800030ff  mov     r8, rdi
0x180003102  mov     edx, 23h ; '#'; Val
0x180003107  sub     r8, [r15]; MaxCount
0x18000310a  mov     rcx, [r15]; Buf
0x18000310d  call    memchr_0
0x180003112  mov     rbp, rax
0x180003115  test    rax, rax
0x180003118  jz      short loc_18000317D
0x18000311a  xor     esi, esi
0x18000311c  cmp     cs:?SSICmdMap@@3PAU_SSI_CMD_MAP@@A, rsi; _SSI_CMD_MAP near * SSICmdMap
0x180003123  jz      short loc_18000317D
0x180003125  lea     r14, cs:180000000h
0x18000312c  movsx   ecx, byte ptr [rbp+0]; C
0x180003130  call    cs:__imp_tolower
0x180003136  mov     ebx, esi
0x180003138  add     rbx, rbx
0x18000313b  mov     rcx, rva ?SSICmdMap@@3PAU_SSI_CMD_MAP@@A[r14+rbx*8]; String1
0x180003143  movsx   edx, byte ptr [rcx]
0x180003146  cmp     edx, eax
0x180003148  jnz     short loc_18000316B
0x18000314a  mov     edx, rva dword_18000A0A8[r14+rbx*8]
0x180003152  mov     eax, r13d
0x180003155  sub     eax, ebp
0x180003157  cmp     eax, edx
0x180003159  jb      short loc_18000316B
0x18000315b  mov     r8d, edx; MaxCount
0x18000315e  mov     rdx, rbp; String2
0x180003161  call    cs:__imp__strnicmp
0x180003167  test    eax, eax
0x180003169  jz      short loc_180003197
0x18000316b  inc     esi
0x18000316d  mov     eax, esi
0x18000316f  add     rax, rax
0x180003172  cmp     rva ?SSICmdMap@@3PAU_SSI_CMD_MAP@@A[r14+rax*8], 0; _SSI_CMD_MAP near * SSICmdMap ...
0x18000317b  jnz     short loc_18000312C
0x18000317d  mov     eax, 1
0x180003182  mov     rbx, [rsp+58h+arg_8]
0x180003187  add     rsp, 20h
0x18000318b  pop     r15
0x18000318d  pop     r14
0x18000318f  pop     r13
0x180003191  pop     r12
0x180003193  pop     rdi
0x180003194  pop     rsi
0x180003195  pop     rbp
0x180003196  retn
0x180003197  mov     rcx, [rsp+58h+arg_18]
0x18000319c  mov     eax, rva dword_18000A0AC[r14+rbx*8]
0x1800031a4  mov     [rcx], eax
0x1800031a6  mov     ebx, rva dword_18000A0A8[r14+rbx*8]
0x1800031ae  add     rbx, rbp
0x1800031b1  jmp     short loc_1800031C3
0x1800031b3  movzx   ecx, byte ptr [rbx]; C
0x1800031b6  call    cs:__imp_isspace
0x1800031bc  test    eax, eax
0x1800031be  jz      short loc_1800031CA
0x1800031c0  inc     rbx
0x1800031c3  cmp     rbx, rdi
0x1800031c6  jb      short loc_1800031B3
0x1800031c8  xor     ebx, ebx
0x1800031ca  test    rbx, rbx
0x1800031cd  jz      short loc_18000317D
0x1800031cf  xor     esi, esi
0x1800031d1  cmp     cs:?SSITagMap@@3PAU_SSI_TAG_MAP@@A, rsi; _SSI_TAG_MAP near * SSITagMap
0x1800031d8  jz      short loc_18000317D
0x1800031da  lea     rbp, cs:180000000h
0x1800031e1  movsx   ecx, byte ptr [rbx]; C
0x1800031e4  call    cs:__imp_tolower
0x1800031ea  mov     r14d, esi
0x1800031ed  add     r14, r14
0x1800031f0  mov     rcx, ss:rva ?SSITagMap@@3PAU_SSI_TAG_MAP@@A[rbp+r14*8]; String1
0x1800031f8  movsx   edx, byte ptr [rcx]
0x1800031fb  cmp     edx, eax
0x1800031fd  jnz     short loc_180003220
0x1800031ff  mov     edx, ss:rva dword_18000A008[rbp+r14*8]
0x180003207  mov     eax, r13d
0x18000320a  sub     eax, ebx
0x18000320c  cmp     eax, edx
0x18000320e  jb      short loc_180003220
0x180003210  mov     r8d, edx; MaxCount
0x180003213  mov     rdx, rbx; String2
0x180003216  call    cs:__imp__strnicmp
0x18000321c  test    eax, eax
0x18000321e  jz      short loc_180003237
0x180003220  inc     esi
0x180003222  mov     eax, esi
0x180003224  add     rax, rax
0x180003227  cmp     ss:rva ?SSITagMap@@3PAU_SSI_TAG_MAP@@A[rbp+rax*8], 0; _SSI_TAG_MAP near * SSITagMap ...
0x180003230  jnz     short loc_1800031E1
0x180003232  jmp     loc_18000317D
0x180003237  mov     ecx, ss:rva dword_18000A00C[rbp+r14*8]
0x18000323f  mov     rax, [rsp+58h+arg_20]
0x180003247  mov     [rax], ecx
0x180003249  mov     ecx, ss:rva dword_18000A008[rbp+r14*8]
0x180003251  add     rcx, rbx; Buf
0x180003254  mov     r8, rdi
0x180003257  mov     esi, 22h ; '"'
0x18000325c  sub     r8, rcx; MaxCount
0x18000325f  mov     edx, esi; Val
0x180003261  call    memchr_0
0x180003266  test    rax, rax
0x180003269  jz      loc_18000317D
0x18000326f  lea     rbx, [rax+1]
0x180003273  mov     r8, rdi
0x180003276  sub     r8, rbx; MaxCount
0x180003279  mov     rcx, rbx; Buf
0x18000327c  mov     edx, esi; Val
0x18000327e  call    memchr_0
0x180003283  test    rax, rax
0x180003286  jz      loc_18000317D
0x18000328c  mov     r9d, r12d
0x18000328f  lea     r10d, [rsi-21h]
0x180003293  xor     r9, r10
0x180003296  sub     eax, ebx
0x180003298  cmp     rax, 7FFFFFFEh
0x18000329e  jbe     short loc_1800032AD
0x1800032a0  mov     rax, [rsp+58h+arg_28]
0x1800032a8  mov     byte ptr [rax], 0
0x1800032ab  jmp     short loc_1800032E4
0x1800032ad  mov     rdx, [rsp+58h+arg_28]
0x1800032b5  mov     r8d, 802h
0x1800032bb  test    rax, rax
0x1800032be  jz      short loc_1800032D6
0x1800032c0  mov     cl, [rbx]
0x1800032c2  test    cl, cl
0x1800032c4  jz      short loc_1800032D6
0x1800032c6  mov     [rdx], cl
0x1800032c8  add     rbx, r10
0x1800032cb  add     rdx, r10
0x1800032ce  sub     rax, r10
0x1800032d1  sub     r8, r10
0x1800032d4  jnz     short loc_1800032BB
0x1800032d6  test    r8, r8
0x1800032d9  lea     rcx, [rdx-1]
0x1800032dd  cmovnz  rcx, rdx
0x1800032e1  mov     byte ptr [rcx], 0
0x1800032e4  mov     rcx, [rsp+58h+arg_10]
0x1800032e9  mov     eax, r10d
0x1800032ec  mov     [rcx], r10d
0x1800032ef  lea     rcx, [rdi+2]
0x1800032f3  add     rcx, r9
0x1800032f6  mov     [r15], rcx
0x1800032f9  jmp     loc_180003182
```
