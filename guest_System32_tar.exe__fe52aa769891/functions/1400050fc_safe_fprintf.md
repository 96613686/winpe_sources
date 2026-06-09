# safe_fprintf

- ea: `0x1400050fc`
- end: `0x140005388`
- name: `safe_fprintf`
- size: `652`
- prototype: `__int64 __fastcall(FILE *Stream, char *Format)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x14000422c`
- `0x140004d0c`
- `0x14000583c`
- `0x140006db0`
- `0x140006ea4`

## callees

- `0x140001340`
- `0x140001380`
- `0x140001cb6`
- `0x140001d10`
- `0x140001dc0`
- `0x140004a54`
- `0x1400050fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005185`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005185`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400051df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005359`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400051df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005359`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x14000529b`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x14000529b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400051e8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400051e8`
- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x140005255`
- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x140005281`
- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x140005255`
- `api-ms-win-crt-private-l1-1-0!_o_mbtowc` at `0x140005281`

## pseudocode

```c
void safe_fprintf(FILE *Stream, char *Format, ...)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // r8
  char *v8; // rdi
  char *v9; // r15
  unsigned __int64 v10; // rbx
  char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int64 v14; // rbx
  char v15; // r12
  int v16; // eax
  int v17; // r14d
  __int64 v18; // rcx
  wchar_t DstCh[4]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+30h] [rbp-D8h]
  char v21[256]; // [rsp+38h] [rbp-D0h] BYREF
  char Buffer[256]; // [rsp+138h] [rbp+30h] BYREF
  __int64 ArgList; // [rsp+2A8h] [rbp+1A0h] BYREF
  va_list ArgLista; // [rsp+2A8h] [rbp+1A0h]
  __int64 v26; // [rsp+2B0h] [rbp+1A8h]
  va_list va1; // [rsp+2B8h] [rbp+1B0h] BYREF

  va_start(va1, Format);
  va_start(ArgLista, Format);
  ArgList = va_arg(va1, _QWORD);
  v26 = va_arg(va1, _QWORD);
  DstCh[0] = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v20 = 0;
  LODWORD(v6) = vsnprintf(Buffer, 0x100u, Format, ArgLista);
  if ( (int)v6 < 0 && *(_DWORD *)_o__errno(v5, v4, v7) == 132 )
    return;
  v8 = Buffer;
  v9 = 0;
  v10 = 256;
  while ( (int)v6 >= 0 )
  {
    if ( (int)v6 < v10 )
      goto LABEL_18;
    v10 = (int)v6 + 1LL;
LABEL_11:
    free(v9);
    v11 = (char *)malloc(v10);
    v9 = v11;
    if ( !v11 )
    {
      Buffer[255] = 0;
      v8 = Buffer;
      v6 = -1;
      do
        ++v6;
      while ( Buffer[v6] );
      goto LABEL_18;
    }
    v8 = v11;
    LODWORD(v6) = vsnprintf(v11, v10, Format, ArgLista);
    v20 = 0;
  }
  if ( v10 < 0x2000 )
  {
    v10 *= 2LL;
    goto LABEL_11;
  }
  if ( v10 < 0xF4240 )
  {
    v10 += v10 >> 2;
    goto LABEL_11;
  }
  v8[v10 - 1] = 0;
  v6 = -1;
  do
    ++v6;
  while ( v8[v6] );
LABEL_18:
  if ( mbtowc(0, 0, 1u) != -1 )
  {
    v14 = 0;
    v15 = 1;
    while ( *v8 )
    {
      if ( !v15 || (v16 = mbtowc(DstCh, v8, (int)v6), v17 = v16, v16 == -1) )
      {
        LOBYTE(v13) = *v8;
        v14 += bsdtar_expand_char(v21, v12, v14, v13);
        ++v8;
        v15 = 0;
      }
      else
      {
        LODWORD(v6) = v6 - v16;
        if ( !iswctype(DstCh[0], 0x157u) || DstCh[0] == 92 )
        {
          while ( v17 > 0 )
          {
            LOBYTE(v13) = *v8;
            --v17;
            v14 += bsdtar_expand_char(v21, v12, v14, v13);
            ++v8;
          }
        }
        else
        {
          while ( v17 > 0 )
          {
            --v17;
            v21[v14++] = *v8++;
          }
        }
      }
      if ( v14 > 0x80 )
      {
        if ( v14 >= 0x100 )
          _report_rangecheckfailure(v18);
        v21[v14] = 0;
        fprintf(Stream, "%s", v21);
        v14 = 0;
      }
    }
    v21[v14] = 0;
    fprintf(Stream, "%s", v21);
  }
  free(v9);
}

```

## disassembly

```asm
0x1400050fc  mov     rax, rsp
0x1400050ff  mov     [rax+10h], rdx
0x140005103  mov     [rax+18h], r8
0x140005107  mov     [rax+20h], r9
0x14000510b  push    rbp
0x14000510c  push    rbx
0x14000510d  push    rsi
0x14000510e  push    rdi
0x14000510f  push    r12
0x140005111  push    r13
0x140005113  push    r14
0x140005115  push    r15
0x140005117  lea     rbp, [rax-188h]
0x14000511e  sub     rsp, 248h
0x140005125  mov     rax, cs:__security_cookie
0x14000512c  xor     rax, rsp
0x14000512f  mov     [rbp+180h+var_50], rax
0x140005136  mov     rbx, rdx
0x140005139  mov     [rsp+280h+var_258], 0
0x140005142  mov     r13, rcx
0x140005145  xor     eax, eax
0x140005147  mov     r14d, 100h
0x14000514d  mov     [rsp+280h+DstCh], ax
0x140005152  mov     r8d, r14d; Size
0x140005155  lea     rcx, [rbp+180h+Buffer]; void *
0x140005159  xor     edx, edx; Val
0x14000515b  call    memset_0
0x140005160  lea     r9, [rbp+180h+ArgList]; ArgList
0x140005167  mov     r8, rbx; Format
0x14000516a  mov     edx, r14d; BufferCount
0x14000516d  lea     rcx, [rbp+180h+Buffer]; Buffer
0x140005171  call    vsnprintf
0x140005176  mov     [rsp+280h+var_258], 0
0x14000517f  mov     esi, eax
0x140005181  test    eax, eax
0x140005183  jns     short loc_140005197
0x140005185  call    cs:__imp__o__errno
0x14000518b  cmp     dword ptr [rax], 84h
0x140005191  jz      loc_14000535F
0x140005197  lea     rdi, [rbp+180h+Buffer]
0x14000519b  xor     r15d, r15d
0x14000519e  mov     rbx, r14
0x1400051a1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400051a5  test    esi, esi
0x1400051a7  js      short loc_1400051BB
0x1400051a9  movsxd  rax, esi
0x1400051ac  cmp     rax, rbx
0x1400051af  jb      loc_14000524D
0x1400051b5  lea     rbx, [rax+1]
0x1400051b9  jmp     short loc_1400051DC
0x1400051bb  cmp     rbx, 2000h
0x1400051c2  jnb     short loc_1400051C9
0x1400051c4  add     rbx, rbx
0x1400051c7  jmp     short loc_1400051DC
0x1400051c9  cmp     rbx, 0F4240h
0x1400051d0  jnb     short loc_14000523C
0x1400051d2  mov     rax, rbx
0x1400051d5  shr     rax, 2
0x1400051d9  add     rbx, rax
0x1400051dc  mov     rcx, r15; Block
0x1400051df  call    cs:__imp_free
0x1400051e5  mov     rcx, rbx; Size
0x1400051e8  call    cs:__imp_malloc
0x1400051ee  mov     r15, rax
0x1400051f1  test    rax, rax
0x1400051f4  jz      short loc_14000521F
0x1400051f6  mov     r8, [rbp+180h+Format]; Format
0x1400051fd  lea     r9, [rbp+180h+ArgList]; ArgList
0x140005204  mov     rdx, rbx; BufferCount
0x140005207  mov     rcx, rax; Buffer
0x14000520a  mov     rdi, rax
0x14000520d  call    vsnprintf
0x140005212  mov     esi, eax
0x140005214  mov     [rsp+280h+var_258], 0
0x14000521d  jmp     short loc_1400051A1
0x14000521f  mov     [rbp+180h+var_51], 0
0x140005226  lea     rdi, [rbp+180h+Buffer]
0x14000522a  lea     rax, [rbp+180h+Buffer]
0x14000522e  mov     rsi, r14
0x140005231  inc     rsi
0x140005234  cmp     byte ptr [rax+rsi], 0
0x140005238  jnz     short loc_140005231
0x14000523a  jmp     short loc_14000524D
0x14000523c  mov     byte ptr [rbx+rdi-1], 0
0x140005241  mov     rsi, r14
0x140005244  inc     rsi
0x140005247  cmp     byte ptr [rdi+rsi], 0
0x14000524b  jnz     short loc_140005244
0x14000524d  xor     edx, edx; SrcCh
0x14000524f  xor     ecx, ecx; DstCh
0x140005251  lea     r8d, [rdx+1]; SrcSizeInBytes
0x140005255  call    cs:__imp_mbtowc
0x14000525b  cmp     eax, r14d
0x14000525e  jz      loc_140005356
0x140005264  xor     ebx, ebx
0x140005266  mov     r12b, 1
0x140005269  cmp     [rdi], bl
0x14000526b  jz      loc_14000533D
0x140005271  test    r12b, r12b
0x140005274  jz      short loc_1400052E5
0x140005276  movsxd  r8, esi; SrcSizeInBytes
0x140005279  lea     rcx, [rsp+280h+DstCh]; DstCh
0x14000527e  mov     rdx, rdi; SrcCh
0x140005281  call    cs:__imp_mbtowc
0x140005287  mov     r14d, eax
0x14000528a  cmp     eax, 0FFFFFFFFh
0x14000528d  jz      short loc_1400052E5
0x14000528f  movzx   ecx, [rsp+280h+DstCh]; C
0x140005294  mov     edx, 157h; Type
0x140005299  sub     esi, eax
0x14000529b  call    cs:__imp_iswctype
0x1400052a1  test    eax, eax
0x1400052a3  jz      short loc_1400052DE
0x1400052a5  cmp     [rsp+280h+DstCh], 5Ch ; '\'
0x1400052ab  jz      short loc_1400052DE
0x1400052ad  jmp     short loc_1400052BE
0x1400052af  mov     al, [rdi]
0x1400052b1  dec     r14d
0x1400052b4  mov     [rsp+rbx+30h], al
0x1400052b8  inc     rbx
0x1400052bb  inc     rdi
0x1400052be  test    r14d, r14d
0x1400052c1  jg      short loc_1400052AF
0x1400052c3  jmp     short loc_1400052FE
0x1400052c5  mov     r9b, [rdi]
0x1400052c8  lea     rcx, [rsp+30h]
0x1400052cd  mov     r8, rbx
0x1400052d0  dec     r14d
0x1400052d3  call    bsdtar_expand_char
0x1400052d8  add     rbx, rax
0x1400052db  inc     rdi
0x1400052de  test    r14d, r14d
0x1400052e1  jg      short loc_1400052C5
0x1400052e3  jmp     short loc_1400052FE
0x1400052e5  mov     r9b, [rdi]
0x1400052e8  lea     rcx, [rsp+30h]
0x1400052ed  mov     r8, rbx
0x1400052f0  call    bsdtar_expand_char
0x1400052f5  add     rbx, rax
0x1400052f8  inc     rdi
0x1400052fb  xor     r12b, r12b
0x1400052fe  cmp     rbx, 80h
0x140005305  jbe     short loc_14000532B
0x140005307  cmp     rbx, 100h
0x14000530e  jnb     short loc_140005382
0x140005310  lea     r8, [rsp+30h]
0x140005315  mov     byte ptr [rsp+rbx+30h], 0
0x14000531a  lea     rdx, aS_5; "%s"
0x140005321  mov     rcx, r13; Stream
0x140005324  call    fprintf
0x140005329  xor     ebx, ebx
0x14000532b  cmp     byte ptr [rdi], 0
0x14000532e  jnz     loc_140005271
0x140005334  cmp     rbx, 100h
0x14000533b  jnb     short loc_140005382
0x14000533d  lea     r8, [rsp+30h]
0x140005342  mov     byte ptr [rsp+rbx+30h], 0
0x140005347  lea     rdx, aS_5; "%s"
0x14000534e  mov     rcx, r13; Stream
0x140005351  call    fprintf
0x140005356  mov     rcx, r15; Block
0x140005359  call    cs:__imp_free
0x14000535f  mov     rcx, [rbp+180h+var_50]
0x140005366  xor     rcx, rsp; StackCookie
0x140005369  call    __security_check_cookie
0x14000536e  add     rsp, 248h
0x140005375  pop     r15
0x140005377  pop     r14
0x140005379  pop     r13
0x14000537b  pop     r12
0x14000537d  pop     rdi
0x14000537e  pop     rsi
0x14000537f  pop     rbx
0x140005380  pop     rbp
0x140005381  retn
0x140005382  call    __report_rangecheckfailure
```
