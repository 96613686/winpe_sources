# WppDbgPrint

- ea: `0x180017754`
- end: `0x180017925`
- name: `WppDbgPrint`
- size: `465`
- prototype: `int(char *String1, ...)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180002900`
- `0x180002cc0`
- `0x18000cad0`
- `0x1800138d0`
- `0x180013b2c`
- `0x180014128`
- `0x180015304`
- `0x180018688`
- `0x180018716`

## callees

- `0x180014e70`
- `0x180017754`
- `0x1800181a2`
- `0x1800181e0`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180017823`
- `msvcrt!_strnicmp` at `0x180017823`
- `msvcrt!vsprintf_s` at `0x180017871`
- `msvcrt!vsprintf_s` at `0x180017871`

## pseudocode

```c
int WppDbgPrint(char *String1, ...)
{
  char *v2; // r14
  unsigned __int64 v3; // rdi
  __int64 v4; // rbp
  __int64 v5; // rsi
  const char *v6; // rdx
  size_t v7; // r8
  char *v8; // rcx
  __int64 v9; // rax
  char v10; // al
  char *v11; // r8
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  int v14; // r10d
  char Format[256]; // [rsp+30h] [rbp-348h] BYREF
  char Buffer[512]; // [rsp+130h] [rbp-248h] BYREF
  va_list ArgList; // [rsp+388h] [rbp+10h] BYREF

  va_start(ArgList, String1);
  memset_0(Format, 0, sizeof(Format));
  memset_0(Buffer, 0, sizeof(Buffer));
  v2 = Format;
  v3 = 255;
LABEL_18:
  while ( 2 )
  {
    if ( *String1 )
    {
      v4 = 0;
      while ( 1 )
      {
        v5 = 4 * v4;
        v6 = (&g_WppFormatReplacements)[4 * v4];
        if ( v6 )
        {
          v7 = -1;
          do
            ++v7;
          while ( v6[v7] );
        }
        else
        {
          v7 = 0;
        }
        v8 = (&g_WppFormatReplacements)[v5 + 2];
        (&g_WppFormatReplacements)[v5 + 1] = (char *)v7;
        if ( v8 )
        {
          v9 = -1;
          do
            ++v9;
          while ( v8[v9] );
        }
        else
        {
          v9 = 0;
        }
        (&g_WppFormatReplacements)[v5 + 3] = (char *)v9;
        if ( String1 )
        {
          LODWORD(v9) = _strnicmp(String1, v6, v7);
          if ( !(_DWORD)v9 )
            break;
        }
        if ( (unsigned __int64)++v4 >= 4 )
        {
          if ( !v3 )
            return v9;
          v10 = *String1++;
          *v2++ = v10;
          --v3;
          goto LABEL_18;
        }
      }
      if ( v3 >= (unsigned __int64)(&g_WppFormatReplacements)[v5 + 3] && v3 )
      {
        if ( v3 > 0x7FFFFFFF )
        {
          *v2 = 0;
        }
        else
        {
          v11 = (&g_WppFormatReplacements)[v5 + 2];
          v12 = 2147483646;
          v13 = v3;
          v9 = (__int64)v2;
          v14 = 0;
          while ( v12 )
          {
            if ( *v11 )
            {
              *(_BYTE *)v9++ = *v11++;
              --v12;
              if ( --v13 )
                continue;
            }
            if ( !v13 )
            {
              --v9;
              v14 = -2147024774;
            }
            break;
          }
          *(_BYTE *)v9 = 0;
          if ( v14 >= 0 )
          {
            String1 = &String1[(_QWORD)(&g_WppFormatReplacements)[v5 + 1]];
            v2 = &v2[(_QWORD)(&g_WppFormatReplacements)[v5 + 3]];
            v3 -= (unsigned __int64)(&g_WppFormatReplacements)[v5 + 3];
            continue;
          }
        }
      }
    }
    else
    {
      *v2 = 0;
      vsprintf_s(Buffer, 0x200u, Format, ArgList);
      LODWORD(v9) = IASTracePrintf("%s");
    }
    return v9;
  }
}

```

## disassembly

```asm
0x180017754  mov     rax, rsp
0x180017757  mov     [rax+8], rcx
0x18001775b  mov     [rax+10h], rdx
0x18001775f  mov     [rax+18h], r8
0x180017763  mov     [rax+20h], r9
0x180017767  push    rbx
0x180017768  push    rbp
0x180017769  push    rsi
0x18001776a  push    rdi
0x18001776b  push    r13
0x18001776d  push    r14
0x18001776f  sub     rsp, 348h
0x180017776  mov     rax, cs:__security_cookie
0x18001777d  xor     rax, rsp
0x180017780  mov     [rsp+378h+var_48], rax
0x180017788  mov     rbx, rcx
0x18001778b  mov     [rsp+378h+var_358], 0
0x180017794  lea     rcx, [rsp+378h+Format]; void *
0x180017799  xor     edx, edx; Val
0x18001779b  mov     r8d, 100h; Size
0x1800177a1  call    memset_0
0x1800177a6  xor     edx, edx; Val
0x1800177a8  lea     rcx, [rsp+378h+Buffer]; void *
0x1800177b0  mov     r8d, 200h; Size
0x1800177b6  call    memset_0
0x1800177bb  lea     r14, [rsp+378h+Format]
0x1800177c0  mov     edi, 0FFh
0x1800177c5  jmp     loc_18001784A
0x1800177ca  xor     ebp, ebp
0x1800177cc  mov     rsi, rbp
0x1800177cf  lea     r13, g_WppFormatReplacements
0x1800177d6  shl     rsi, 5
0x1800177da  mov     rdx, [rsi+r13]; String2
0x1800177de  test    rdx, rdx
0x1800177e1  jz      short loc_1800177F3
0x1800177e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800177e7  inc     r8
0x1800177ea  cmp     byte ptr [rdx+r8], 0
0x1800177ef  jnz     short loc_1800177E7
0x1800177f1  jmp     short loc_1800177F6
0x1800177f3  xor     r8d, r8d; MaxCount
0x1800177f6  mov     rcx, [rsi+r13+10h]
0x1800177fb  mov     [rsi+r13+8], r8
0x180017800  test    rcx, rcx
0x180017803  jz      short loc_180017814
0x180017805  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017809  inc     rax
0x18001780c  cmp     byte ptr [rcx+rax], 0
0x180017810  jnz     short loc_180017809
0x180017812  jmp     short loc_180017816
0x180017814  xor     eax, eax
0x180017816  mov     [rsi+r13+18h], rax
0x18001781b  test    rbx, rbx
0x18001781e  jz      short loc_18001782D
0x180017820  mov     rcx, rbx; String1
0x180017823  call    cs:__imp__strnicmp
0x180017829  test    eax, eax
0x18001782b  jz      short loc_1800178AB
0x18001782d  inc     rbp
0x180017830  cmp     rbp, 4
0x180017834  jb      short loc_1800177CC
0x180017836  cmp     rdi, 1
0x18001783a  jb      short loc_18001788B
0x18001783c  mov     al, [rbx]
0x18001783e  inc     rbx
0x180017841  mov     [r14], al
0x180017844  inc     r14
0x180017847  dec     rdi
0x18001784a  cmp     byte ptr [rbx], 0
0x18001784d  jnz     loc_1800177CA
0x180017853  lea     r9, [rsp+378h+ArgList]; ArgList
0x18001785b  mov     byte ptr [r14], 0
0x18001785f  lea     r8, [rsp+378h+Format]; Format
0x180017864  mov     edx, 200h; BufferCount
0x180017869  lea     rcx, [rsp+378h+Buffer]; Buffer
0x180017871  call    cs:__imp_vsprintf_s
0x180017877  lea     rdx, [rsp+378h+Buffer]
0x18001787f  lea     rcx, szFormat; "%s"
0x180017886  call    IASTracePrintf
0x18001788b  mov     rcx, [rsp+378h+var_48]
0x180017893  xor     rcx, rsp; StackCookie
0x180017896  call    __security_check_cookie
0x18001789b  add     rsp, 348h
0x1800178a2  pop     r14
0x1800178a4  pop     r13
0x1800178a6  pop     rdi
0x1800178a7  pop     rsi
0x1800178a8  pop     rbp
0x1800178a9  pop     rbx
0x1800178aa  retn
0x1800178ab  cmp     rdi, [rsi+r13+18h]
0x1800178b0  jb      short loc_18001788B
0x1800178b2  test    rdi, rdi
0x1800178b5  jz      short loc_18001788B
0x1800178b7  cmp     rdi, 7FFFFFFFh
0x1800178be  ja      short loc_18001791C
0x1800178c0  mov     r8, [rsi+r13+10h]
0x1800178c5  mov     edx, 7FFFFFFEh
0x1800178ca  mov     rcx, rdi
0x1800178cd  mov     rax, r14
0x1800178d0  xor     r10d, r10d
0x1800178d3  test    rdx, rdx
0x1800178d6  jz      short loc_180017900
0x1800178d8  mov     r9b, [r8]
0x1800178db  test    r9b, r9b
0x1800178de  jz      short loc_1800178F2
0x1800178e0  mov     [rax], r9b
0x1800178e3  inc     r8
0x1800178e6  inc     rax
0x1800178e9  dec     rdx
0x1800178ec  sub     rcx, 1
0x1800178f0  jnz     short loc_1800178D3
0x1800178f2  test    rcx, rcx
0x1800178f5  jnz     short loc_180017900
0x1800178f7  dec     rax
0x1800178fa  mov     r10d, 8007007Ah
0x180017900  mov     byte ptr [rax], 0
0x180017903  test    r10d, r10d
0x180017906  js      short loc_18001788B
0x180017908  add     rbx, [rsi+r13+8]
0x18001790d  add     r14, [rsi+r13+18h]
0x180017912  sub     rdi, [rsi+r13+18h]
0x180017917  jmp     loc_18001784A
0x18001791c  mov     byte ptr [r14], 0
0x180017920  jmp     loc_18001788B
```
