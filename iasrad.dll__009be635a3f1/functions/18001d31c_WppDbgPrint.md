# WppDbgPrint

- ea: `0x18001d31c`
- end: `0x18001d4ad`
- name: `WppDbgPrint`
- size: `401`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `97`
- callee_count: `5`
- tags: ``

## callers

- `0x180004c70`
- `0x1800069f0`
- `0x1800075bc`
- `0x180009f58`
- `0x18000b560`
- `0x18000c480`
- `0x18000c838`
- `0x18000d140`
- `0x18000d1c0`
- `0x18000d3b0`
- `0x18000d5e0`
- `0x18000d7c0`
- `0x18000d950`
- `0x180012988`
- `0x180012c68`
- `0x180013458`
- `0x180013808`
- `0x1800138c8`
- `0x180013a98`
- `0x180013b78`
- `0x180013c04`
- `0x180013f90`
- `0x18001408c`
- `0x180014388`
- `0x1800147b0`
- `0x180014840`
- `0x180014e98`
- `0x180014f88`
- `0x1800151cc`
- `0x1800157dc`
- `0x180015938`
- `0x1800162d8`
- `0x180016618`
- `0x1800168a8`
- `0x180016a08`
- `0x180016d2c`
- `0x180016e00`
- `0x180016efc`
- `0x1800170c4`
- `0x180017544`
- `0x1800178b8`
- `0x1800179a4`
- `0x1800181e8`
- `0x1800186b8`
- `0x180018bec`
- `0x180018ca4`
- `0x180019068`
- `0x180019340`
- `0x18001967c`
- `0x180019944`

## callees

- `0x18001d240`
- `0x18001d31c`
- `0x18002cc30`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `msvcrt!_strnicmp` at `0x18001d40a`
- `msvcrt!_strnicmp` at `0x18001d40a`
- `msvcrt!vsprintf_s` at `0x18001d478`
- `msvcrt!vsprintf_s` at `0x18001d478`

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
0x18001d31c  mov     rax, rsp
0x18001d31f  mov     [rax+8], rcx
0x18001d323  mov     [rax+10h], rdx
0x18001d327  mov     [rax+18h], r8
0x18001d32b  mov     [rax+20h], r9
0x18001d32f  push    rbp
0x18001d330  push    rbx
0x18001d331  push    rsi
0x18001d332  push    rdi
0x18001d333  push    r14
0x18001d335  push    r15
0x18001d337  lea     rbp, [rax-288h]
0x18001d33e  sub     rsp, 358h
0x18001d345  mov     rax, cs:__security_cookie
0x18001d34c  xor     rax, rsp
0x18001d34f  mov     [rbp+280h+var_40], rax
0x18001d356  mov     rbx, rcx
0x18001d359  mov     [rsp+380h+var_360], 0
0x18001d362  lea     rcx, [rsp+380h+Format]; void *
0x18001d367  xor     edx, edx; Val
0x18001d369  mov     r8d, 100h; Size
0x18001d36f  call    memset_0
0x18001d374  xor     edx, edx; Val
0x18001d376  lea     rcx, [rbp+280h+Buffer]; void *
0x18001d37a  mov     r8d, 200h; Size
0x18001d380  call    memset_0
0x18001d385  lea     rdi, [rsp+380h+Format]
0x18001d38a  mov     esi, 0FFh
0x18001d38f  mov     [rsp+380h+var_360], rsi
0x18001d394  mov     [rsp+380h+var_358], rdi
0x18001d399  mov     [rsp+380h+var_350], rbx
0x18001d39e  cmp     byte ptr [rbx], 0
0x18001d3a1  jz      loc_18001D460
0x18001d3a7  xor     r14d, r14d
0x18001d3aa  cmp     r14, 4
0x18001d3ae  jnb     loc_18001D448
0x18001d3b4  mov     r15, r14
0x18001d3b7  lea     rcx, g_WppFormatReplacements
0x18001d3be  shl     r15, 5
0x18001d3c2  add     r15, rcx
0x18001d3c5  mov     rdx, [r15]; String2
0x18001d3c8  test    rdx, rdx
0x18001d3cb  jz      short loc_18001D3DD
0x18001d3cd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d3d1  inc     r8
0x18001d3d4  cmp     byte ptr [rdx+r8], 0
0x18001d3d9  jnz     short loc_18001D3D1
0x18001d3db  jmp     short loc_18001D3E0
0x18001d3dd  xor     r8d, r8d; MaxCount
0x18001d3e0  mov     rcx, [r15+10h]
0x18001d3e4  mov     [r15+8], r8
0x18001d3e8  test    rcx, rcx
0x18001d3eb  jz      short loc_18001D3FC
0x18001d3ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001d3f1  inc     rax
0x18001d3f4  cmp     byte ptr [rcx+rax], 0
0x18001d3f8  jnz     short loc_18001D3F1
0x18001d3fa  jmp     short loc_18001D3FE
0x18001d3fc  xor     eax, eax
0x18001d3fe  mov     [r15+18h], rax
0x18001d402  test    rbx, rbx
0x18001d405  jz      short loc_18001D414
0x18001d407  mov     rcx, rbx; String1
0x18001d40a  call    cs:__imp__strnicmp
0x18001d410  test    eax, eax
0x18001d412  jz      short loc_18001D419
0x18001d414  inc     r14
0x18001d417  jmp     short loc_18001D3AA
0x18001d419  lea     r9, [rsp+380h+var_360]
0x18001d41e  mov     rcx, r15
0x18001d421  lea     r8, [rsp+380h+var_358]
0x18001d426  lea     rdx, [rsp+380h+var_350]
0x18001d42b  call    FormatReplacement_Replace
0x18001d430  test    eax, eax
0x18001d432  jz      short loc_18001D48E
0x18001d434  mov     rbx, [rsp+380h+var_350]
0x18001d439  mov     rdi, [rsp+380h+var_358]
0x18001d43e  mov     rsi, [rsp+380h+var_360]
0x18001d443  jmp     loc_18001D39E
0x18001d448  cmp     rsi, 1
0x18001d44c  jb      short loc_18001D48E
0x18001d44e  mov     al, [rbx]
0x18001d450  inc     rbx
0x18001d453  mov     [rdi], al
0x18001d455  inc     rdi
0x18001d458  dec     rsi
0x18001d45b  jmp     loc_18001D38F
0x18001d460  lea     r9, [rbp+280h+ArgList]; ArgList
0x18001d467  mov     byte ptr [rdi], 0
0x18001d46a  lea     r8, [rsp+380h+Format]; Format
0x18001d46f  mov     edx, 200h; BufferCount
0x18001d474  lea     rcx, [rbp+280h+Buffer]; Buffer
0x18001d478  call    cs:__imp_vsprintf_s
0x18001d47e  lea     rdx, [rbp+280h+Buffer]
0x18001d482  lea     rcx, aS_0; "%s"
0x18001d489  call    IASTracePrintf
0x18001d48e  mov     rcx, [rbp+280h+var_40]
0x18001d495  xor     rcx, rsp; StackCookie
0x18001d498  call    __security_check_cookie
0x18001d49d  add     rsp, 358h
0x18001d4a4  pop     r15
0x18001d4a6  pop     r14
0x18001d4a8  pop     rdi
0x18001d4a9  pop     rsi
0x18001d4aa  pop     rbx
0x18001d4ab  pop     rbp
0x18001d4ac  retn
```
