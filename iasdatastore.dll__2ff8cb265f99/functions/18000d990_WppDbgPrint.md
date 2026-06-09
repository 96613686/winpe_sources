# WppDbgPrint

- ea: `0x18000d990`
- end: `0x18000db61`
- name: `WppDbgPrint`
- size: `465`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `37`
- callee_count: `4`
- tags: ``

## callers

- `0x180006b50`
- `0x180006c10`
- `0x180006cd0`
- `0x180006e00`
- `0x180006ee0`
- `0x180006f90`
- `0x180007060`
- `0x1800079fc`
- `0x180007fb4`
- `0x1800081b8`
- `0x1800086c8`
- `0x180008b90`
- `0x180008d7c`
- `0x1800093cc`
- `0x180009af8`
- `0x18000a19c`
- `0x18000a334`
- `0x18000a4a0`
- `0x18000b210`
- `0x18000c2b0`
- `0x18000c340`
- `0x18000c4f0`
- `0x18000c580`
- `0x18000c910`
- `0x18000c9c0`
- `0x18000e2e4`
- `0x18000e360`
- `0x18000e3ee`
- `0x18000e46a`
- `0x18000e4e8`
- `0x18000e566`
- `0x18000e5f4`
- `0x18000e971`
- `0x18000ebba`
- `0x18000ee30`
- `0x18000eec1`
- `0x18000ef57`

## callees

- `0x18000cd60`
- `0x18000d990`
- `0x18000dce6`
- `0x18000dd10`

## import_xrefs

- `msvcrt!vsprintf_s` at `0x18000daad`
- `msvcrt!vsprintf_s` at `0x18000daad`
- `msvcrt!_strnicmp` at `0x18000da5f`
- `msvcrt!_strnicmp` at `0x18000da5f`

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
0x18000d990  mov     rax, rsp
0x18000d993  mov     [rax+8], rcx
0x18000d997  mov     [rax+10h], rdx
0x18000d99b  mov     [rax+18h], r8
0x18000d99f  mov     [rax+20h], r9
0x18000d9a3  push    rbx
0x18000d9a4  push    rbp
0x18000d9a5  push    rsi
0x18000d9a6  push    rdi
0x18000d9a7  push    r13
0x18000d9a9  push    r14
0x18000d9ab  sub     rsp, 348h
0x18000d9b2  mov     rax, cs:__security_cookie
0x18000d9b9  xor     rax, rsp
0x18000d9bc  mov     [rsp+378h+var_48], rax
0x18000d9c4  mov     rbx, rcx
0x18000d9c7  mov     [rsp+378h+var_358], 0
0x18000d9d0  lea     rcx, [rsp+378h+Format]; void *
0x18000d9d5  xor     edx, edx; Val
0x18000d9d7  mov     r8d, 100h; Size
0x18000d9dd  call    memset_0
0x18000d9e2  xor     edx, edx; Val
0x18000d9e4  lea     rcx, [rsp+378h+Buffer]; void *
0x18000d9ec  mov     r8d, 200h; Size
0x18000d9f2  call    memset_0
0x18000d9f7  lea     r14, [rsp+378h+Format]
0x18000d9fc  mov     edi, 0FFh
0x18000da01  jmp     loc_18000DA86
0x18000da06  xor     ebp, ebp
0x18000da08  mov     rsi, rbp
0x18000da0b  lea     r13, g_WppFormatReplacements
0x18000da12  shl     rsi, 5
0x18000da16  mov     rdx, [rsi+r13]; String2
0x18000da1a  test    rdx, rdx
0x18000da1d  jz      short loc_18000DA2F
0x18000da1f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000da23  inc     r8
0x18000da26  cmp     byte ptr [rdx+r8], 0
0x18000da2b  jnz     short loc_18000DA23
0x18000da2d  jmp     short loc_18000DA32
0x18000da2f  xor     r8d, r8d; MaxCount
0x18000da32  mov     rcx, [rsi+r13+10h]
0x18000da37  mov     [rsi+r13+8], r8
0x18000da3c  test    rcx, rcx
0x18000da3f  jz      short loc_18000DA50
0x18000da41  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000da45  inc     rax
0x18000da48  cmp     byte ptr [rcx+rax], 0
0x18000da4c  jnz     short loc_18000DA45
0x18000da4e  jmp     short loc_18000DA52
0x18000da50  xor     eax, eax
0x18000da52  mov     [rsi+r13+18h], rax
0x18000da57  test    rbx, rbx
0x18000da5a  jz      short loc_18000DA69
0x18000da5c  mov     rcx, rbx; String1
0x18000da5f  call    cs:__imp__strnicmp
0x18000da65  test    eax, eax
0x18000da67  jz      short loc_18000DAE7
0x18000da69  inc     rbp
0x18000da6c  cmp     rbp, 4
0x18000da70  jb      short loc_18000DA08
0x18000da72  cmp     rdi, 1
0x18000da76  jb      short loc_18000DAC7
0x18000da78  mov     al, [rbx]
0x18000da7a  inc     rbx
0x18000da7d  mov     [r14], al
0x18000da80  inc     r14
0x18000da83  dec     rdi
0x18000da86  cmp     byte ptr [rbx], 0
0x18000da89  jnz     loc_18000DA06
0x18000da8f  lea     r9, [rsp+378h+ArgList]; ArgList
0x18000da97  mov     byte ptr [r14], 0
0x18000da9b  lea     r8, [rsp+378h+Format]; Format
0x18000daa0  mov     edx, 200h; BufferCount
0x18000daa5  lea     rcx, [rsp+378h+Buffer]; Buffer
0x18000daad  call    cs:__imp_vsprintf_s
0x18000dab3  lea     rdx, [rsp+378h+Buffer]
0x18000dabb  lea     rcx, szFormat; "%s"
0x18000dac2  call    IASTracePrintf
0x18000dac7  mov     rcx, [rsp+378h+var_48]
0x18000dacf  xor     rcx, rsp; StackCookie
0x18000dad2  call    __security_check_cookie
0x18000dad7  add     rsp, 348h
0x18000dade  pop     r14
0x18000dae0  pop     r13
0x18000dae2  pop     rdi
0x18000dae3  pop     rsi
0x18000dae4  pop     rbp
0x18000dae5  pop     rbx
0x18000dae6  retn
0x18000dae7  cmp     rdi, [rsi+r13+18h]
0x18000daec  jb      short loc_18000DAC7
0x18000daee  test    rdi, rdi
0x18000daf1  jz      short loc_18000DAC7
0x18000daf3  cmp     rdi, 7FFFFFFFh
0x18000dafa  ja      short loc_18000DB58
0x18000dafc  mov     r8, [rsi+r13+10h]
0x18000db01  mov     edx, 7FFFFFFEh
0x18000db06  mov     rcx, rdi
0x18000db09  mov     rax, r14
0x18000db0c  xor     r10d, r10d
0x18000db0f  test    rdx, rdx
0x18000db12  jz      short loc_18000DB3C
0x18000db14  mov     r9b, [r8]
0x18000db17  test    r9b, r9b
0x18000db1a  jz      short loc_18000DB2E
0x18000db1c  mov     [rax], r9b
0x18000db1f  inc     r8
0x18000db22  inc     rax
0x18000db25  dec     rdx
0x18000db28  sub     rcx, 1
0x18000db2c  jnz     short loc_18000DB0F
0x18000db2e  test    rcx, rcx
0x18000db31  jnz     short loc_18000DB3C
0x18000db33  dec     rax
0x18000db36  mov     r10d, 8007007Ah
0x18000db3c  mov     byte ptr [rax], 0
0x18000db3f  test    r10d, r10d
0x18000db42  js      short loc_18000DAC7
0x18000db44  add     rbx, [rsi+r13+8]
0x18000db49  add     r14, [rsi+r13+18h]
0x18000db4e  sub     rdi, [rsi+r13+18h]
0x18000db53  jmp     loc_18000DA86
0x18000db58  mov     byte ptr [r14], 0
0x18000db5c  jmp     loc_18000DAC7
```
