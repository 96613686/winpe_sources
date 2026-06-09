# WppDbgPrint

- ea: `0x1800254a0`
- end: `0x180025631`
- name: `WppDbgPrint`
- size: `401`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `120`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b520`
- `0x18000b82c`
- `0x18000b960`
- `0x18000bce0`
- `0x18000bf20`
- `0x18000cab4`
- `0x18000cd70`
- `0x18000ce58`
- `0x18000d154`
- `0x18000d630`
- `0x18000dbc0`
- `0x18000dfe0`
- `0x18000e2d0`
- `0x18000e538`
- `0x18000eb28`
- `0x18000efbc`
- `0x18000f040`
- `0x18000f544`
- `0x18000f6e0`
- `0x18000f890`
- `0x18000fb84`
- `0x18000fdd4`
- `0x18000ffa0`
- `0x180010058`
- `0x180010274`
- `0x18001032c`
- `0x1800103e4`
- `0x180010680`
- `0x180011708`
- `0x18001224c`
- `0x18001247c`
- `0x180012a38`
- `0x180012c74`
- `0x180013084`
- `0x1800133bc`
- `0x180013ce0`
- `0x180013ec0`
- `0x180013ff4`
- `0x180014608`
- `0x1800148b0`
- `0x180015190`
- `0x180015a80`
- `0x180015e30`
- `0x180015f00`
- `0x1800160d0`
- `0x180016d0c`
- `0x180017074`
- `0x180017258`
- `0x180017330`
- `0x180017900`

## callees

- `0x18000a9b0`
- `0x1800253c4`
- `0x1800254a0`
- `0x18002b472`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!vsprintf_s` at `0x1800255fc`
- `msvcrt!vsprintf_s` at `0x1800255fc`
- `msvcrt!_strnicmp` at `0x18002558e`
- `msvcrt!_strnicmp` at `0x18002558e`

## pseudocode

```c
char WppDbgPrint(char *String1, ...)
{
  __int64 v2; // rax
  char *v3; // rdi
  __int64 i; // rsi
  unsigned __int64 j; // r14
  char **v6; // r15
  const char *v7; // rdx
  size_t v8; // r8
  char *v9; // rcx
  __int64 v11; // [rsp+28h] [rbp-E0h] BYREF
  char *v12; // [rsp+30h] [rbp-D8h] BYREF
  char *v13; // [rsp+38h] [rbp-D0h] BYREF
  char Format[256]; // [rsp+48h] [rbp-C0h] BYREF
  char Buffer[512]; // [rsp+148h] [rbp+40h] BYREF
  va_list ArgList; // [rsp+3A0h] [rbp+298h] BYREF

  va_start(ArgList, String1);
  v11 = 0;
  memset_0(Format, 0, sizeof(Format));
  LOBYTE(v2) = (unsigned __int8)memset_0(Buffer, 0, sizeof(Buffer));
  v3 = Format;
  for ( i = 255; ; --i )
  {
    v11 = i;
    v12 = v3;
    v13 = String1;
LABEL_3:
    if ( !*String1 )
      break;
    for ( j = 0; j < 4; ++j )
    {
      v6 = &(&g_WppFormatReplacements)[4 * j];
      v7 = *v6;
      if ( *v6 )
      {
        v8 = -1;
        do
          ++v8;
        while ( v7[v8] );
      }
      else
      {
        v8 = 0;
      }
      v9 = v6[2];
      v6[1] = (char *)v8;
      if ( v9 )
      {
        v2 = -1;
        do
          ++v2;
        while ( v9[v2] );
      }
      else
      {
        v2 = 0;
      }
      v6[3] = (char *)v2;
      if ( String1 )
      {
        LODWORD(v2) = _strnicmp(String1, v7, v8);
        if ( !(_DWORD)v2 )
        {
          LODWORD(v2) = FormatReplacement_Replace(&(&g_WppFormatReplacements)[4 * j], &v13, &v12, &v11);
          if ( !(_DWORD)v2 )
            return v2;
          String1 = v13;
          v3 = v12;
          i = v11;
          goto LABEL_3;
        }
      }
    }
    if ( !i )
      return v2;
    LOBYTE(v2) = *String1++;
    *v3++ = v2;
  }
  *v3 = 0;
  vsprintf_s(Buffer, 0x200u, Format, ArgList);
  LOBYTE(v2) = IASTracePrintf("%s");
  return v2;
}

```

## disassembly

```asm
0x1800254a0  mov     rax, rsp
0x1800254a3  mov     [rax+8], rcx
0x1800254a7  mov     [rax+10h], rdx
0x1800254ab  mov     [rax+18h], r8
0x1800254af  mov     [rax+20h], r9
0x1800254b3  push    rbp
0x1800254b4  push    rbx
0x1800254b5  push    rsi
0x1800254b6  push    rdi
0x1800254b7  push    r14
0x1800254b9  push    r15
0x1800254bb  lea     rbp, [rax-288h]
0x1800254c2  sub     rsp, 358h
0x1800254c9  mov     rax, cs:__security_cookie
0x1800254d0  xor     rax, rsp
0x1800254d3  mov     [rbp+280h+var_40], rax
0x1800254da  mov     rbx, rcx
0x1800254dd  mov     [rsp+380h+var_360], 0
0x1800254e6  lea     rcx, [rsp+380h+Format]; void *
0x1800254eb  xor     edx, edx; Val
0x1800254ed  mov     r8d, 100h; Size
0x1800254f3  call    memset_0
0x1800254f8  xor     edx, edx; Val
0x1800254fa  lea     rcx, [rbp+280h+Buffer]; void *
0x1800254fe  mov     r8d, 200h; Size
0x180025504  call    memset_0
0x180025509  lea     rdi, [rsp+380h+Format]
0x18002550e  mov     esi, 0FFh
0x180025513  mov     [rsp+380h+var_360], rsi
0x180025518  mov     [rsp+380h+var_358], rdi
0x18002551d  mov     [rsp+380h+var_350], rbx
0x180025522  cmp     byte ptr [rbx], 0
0x180025525  jz      loc_1800255E4
0x18002552b  xor     r14d, r14d
0x18002552e  cmp     r14, 4
0x180025532  jnb     loc_1800255CC
0x180025538  mov     r15, r14
0x18002553b  lea     rcx, g_WppFormatReplacements
0x180025542  shl     r15, 5
0x180025546  add     r15, rcx
0x180025549  mov     rdx, [r15]; String2
0x18002554c  test    rdx, rdx
0x18002554f  jz      short loc_180025561
0x180025551  or      r8, 0FFFFFFFFFFFFFFFFh
0x180025555  inc     r8
0x180025558  cmp     byte ptr [rdx+r8], 0
0x18002555d  jnz     short loc_180025555
0x18002555f  jmp     short loc_180025564
0x180025561  xor     r8d, r8d; MaxCount
0x180025564  mov     rcx, [r15+10h]
0x180025568  mov     [r15+8], r8
0x18002556c  test    rcx, rcx
0x18002556f  jz      short loc_180025580
0x180025571  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025575  inc     rax
0x180025578  cmp     byte ptr [rcx+rax], 0
0x18002557c  jnz     short loc_180025575
0x18002557e  jmp     short loc_180025582
0x180025580  xor     eax, eax
0x180025582  mov     [r15+18h], rax
0x180025586  test    rbx, rbx
0x180025589  jz      short loc_180025598
0x18002558b  mov     rcx, rbx; String1
0x18002558e  call    cs:__imp__strnicmp
0x180025594  test    eax, eax
0x180025596  jz      short loc_18002559D
0x180025598  inc     r14
0x18002559b  jmp     short loc_18002552E
0x18002559d  lea     r9, [rsp+380h+var_360]
0x1800255a2  mov     rcx, r15
0x1800255a5  lea     r8, [rsp+380h+var_358]
0x1800255aa  lea     rdx, [rsp+380h+var_350]
0x1800255af  call    FormatReplacement_Replace
0x1800255b4  test    eax, eax
0x1800255b6  jz      short loc_180025612
0x1800255b8  mov     rbx, [rsp+380h+var_350]
0x1800255bd  mov     rdi, [rsp+380h+var_358]
0x1800255c2  mov     rsi, [rsp+380h+var_360]
0x1800255c7  jmp     loc_180025522
0x1800255cc  cmp     rsi, 1
0x1800255d0  jb      short loc_180025612
0x1800255d2  mov     al, [rbx]
0x1800255d4  inc     rbx
0x1800255d7  mov     [rdi], al
0x1800255d9  inc     rdi
0x1800255dc  dec     rsi
0x1800255df  jmp     loc_180025513
0x1800255e4  lea     r9, [rbp+280h+ArgList]; ArgList
0x1800255eb  mov     byte ptr [rdi], 0
0x1800255ee  lea     r8, [rsp+380h+Format]; Format
0x1800255f3  mov     edx, 200h; BufferCount
0x1800255f8  lea     rcx, [rbp+280h+Buffer]; Buffer
0x1800255fc  call    cs:__imp_vsprintf_s
0x180025602  lea     rdx, [rbp+280h+Buffer]
0x180025606  lea     rcx, szFormat; "%s"
0x18002560d  call    IASTracePrintf
0x180025612  mov     rcx, [rbp+280h+var_40]
0x180025619  xor     rcx, rsp; StackCookie
0x18002561c  call    __security_check_cookie
0x180025621  add     rsp, 358h
0x180025628  pop     r15
0x18002562a  pop     r14
0x18002562c  pop     rdi
0x18002562d  pop     rsi
0x18002562e  pop     rbx
0x18002562f  pop     rbp
0x180025630  retn
```
