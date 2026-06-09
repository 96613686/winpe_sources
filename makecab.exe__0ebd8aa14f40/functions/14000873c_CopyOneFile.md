# CopyOneFile

- ea: `0x14000873c`
- end: `0x140008953`
- name: `CopyOneFile`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000488c`

## callees

- `0x140006528`
- `0x140008620`
- `0x14000873c`
- `0x14000895c`
- `0x140008b90`
- `0x140008d20`

## import_xrefs

- `msvcrt!_eof` at `0x1400088c4`
- `msvcrt!_eof` at `0x1400088c4`
- `msvcrt!_open` at `0x140008789`
- `msvcrt!_open` at `0x140008866`
- `msvcrt!_open` at `0x140008789`
- `msvcrt!_open` at `0x140008866`
- `msvcrt!_write` at `0x1400088b8`
- `msvcrt!_write` at `0x1400088b8`
- `msvcrt!_close` at `0x1400088d1`
- `msvcrt!_close` at `0x1400088f8`
- `msvcrt!_close` at `0x14000894b`
- `msvcrt!_close` at `0x1400088d1`
- `msvcrt!_close` at `0x1400088f8`
- `msvcrt!_close` at `0x14000894b`
- `msvcrt!_read` at `0x14000889a`
- `msvcrt!_read` at `0x14000889a`
- `msvcrt!malloc` at `0x14000880e`
- `msvcrt!malloc` at `0x14000880e`
- `msvcrt!free` at `0x140008906`
- `msvcrt!free` at `0x140008906`

## string_xrefs

- `0x1400087a8`: `Cannot open file: %1`
- `0x14000887e`: `Cannot open file: %1`
- `0x140008832`: `Could not allocate buffer to copy %1 to %2`
- `0x14000892f`: `Cannot read file: %1`
- `0x140008926`: `Cannot write file: %1`

## pseudocode

```c
_BOOL8 __fastcall CopyOneFile(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8)
{
  unsigned int v8; // edi
  BOOL v9; // r15d
  int v11; // eax
  int v12; // esi
  __int64 v13; // r14
  void *v14; // rbp
  int v15; // eax
  int v16; // r12d
  unsigned int v17; // eax
  __int64 v18; // rcx
  const char *v20; // rdx
  int v21; // [rsp+68h] [rbp+10h] BYREF
  __int16 v22; // [rsp+6Ch] [rbp+14h]
  __int16 v23; // [rsp+6Eh] [rbp+16h]

  v23 = HIWORD(a2);
  v8 = a7;
  v9 = 0;
  v21 = 0;
  v22 = 0;
  if ( a7 )
    v11 = OpenFileUNC(pszDest, 0x8000);
  else
    v11 = _open(pszDest, 0x8000);
  v12 = v11;
  if ( v11 == -1 )
  {
    ErrSet(a8, "Cannot open file: %1", "%s", pszDest);
  }
  else
  {
    v13 = a8;
    v14 = 0;
    if ( (unsigned int)GetFileTimeAndAttr(&v21, pszDest, v8, a8) && (unsigned int)fnofpDiamond(&v21, a6, v13) )
    {
      if ( a3 )
      {
        v14 = malloc(0x8000u);
        if ( v14 )
        {
          if ( v8 )
            v15 = OpenFileUNC(CurrentChar, 33537);
          else
            v15 = _open(CurrentChar, 33537, 384);
          v16 = v15;
          if ( v15 == -1 )
          {
            ErrSet(v13, "Cannot open file: %1", "%s", CurrentChar);
          }
          else
          {
            while ( 1 )
            {
              if ( _eof(v12) )
              {
                _close(v16);
                v9 = SetFileTimeAndAttr(v18, &v21, v13) != 0;
                goto LABEL_22;
              }
              v17 = _read(v12, v14, 0x8000u);
              if ( v17 == -1 )
                break;
              if ( v17 && _write(v16, v14, v17) != v17 )
              {
                v20 = "Cannot write file: %1";
                goto LABEL_27;
              }
            }
            v20 = "Cannot read file: %1";
LABEL_27:
            ErrSet(v13, v20, "%s", pszDest);
            _close(v16);
          }
        }
        else
        {
          ErrSet(v13, "Could not allocate buffer to copy %1 to %2", "%s%s", pszDest, CurrentChar);
        }
      }
      else
      {
        v9 = 1;
      }
    }
LABEL_22:
    _close(v12);
    if ( v14 )
      free(v14);
  }
  return v9;
}

```

## disassembly

```asm
0x14000873c  mov     [rsp+arg_0], rbx
0x140008741  mov     [rsp+arg_10], rbp
0x140008746  mov     [rsp+arg_8], rdx
0x14000874b  push    rsi
0x14000874c  push    rdi
0x14000874d  push    r12
0x14000874f  push    r14
0x140008751  push    r15
0x140008753  sub     rsp, 30h
0x140008757  mov     edi, [rsp+58h+arg_30]
0x14000875e  lea     rbx, pszDest
0x140008765  xor     eax, eax
0x140008767  xor     r15d, r15d
0x14000876a  mov     dword ptr [rsp+58h+arg_8], eax
0x14000876e  mov     r12d, r8d
0x140008771  mov     word ptr [rsp+58h+arg_8+4], ax
0x140008776  mov     edx, 8000h; OpenFlag
0x14000877b  mov     rcx, rbx; FileName
0x14000877e  test    edi, edi
0x140008780  jz      short loc_140008789
0x140008782  call    OpenFileUNC
0x140008787  jmp     short loc_14000878F
0x140008789  call    cs:__imp__open
0x14000878f  mov     esi, eax
0x140008791  cmp     eax, 0FFFFFFFFh
0x140008794  jnz     short loc_1400087B9
0x140008796  mov     rcx, [rsp+58h+arg_38]
0x14000879e  lea     r8, aS_4; "%s"
0x1400087a5  mov     r9, rbx
0x1400087a8  lea     rdx, aCannotOpenFile; "Cannot open file: %1"
0x1400087af  call    ErrSet
0x1400087b4  jmp     loc_14000890C
0x1400087b9  mov     r14, [rsp+58h+arg_38]
0x1400087c1  lea     rcx, [rsp+58h+arg_8]
0x1400087c6  mov     r9, r14
0x1400087c9  mov     r8d, edi
0x1400087cc  mov     rdx, rbx
0x1400087cf  xor     ebp, ebp
0x1400087d1  call    GetFileTimeAndAttr
0x1400087d6  test    eax, eax
0x1400087d8  jz      loc_1400088F6
0x1400087de  mov     rdx, [rsp+58h+arg_28]
0x1400087e6  lea     rcx, [rsp+58h+arg_8]
0x1400087eb  mov     r8, r14
0x1400087ee  call    fnofpDiamond
0x1400087f3  test    eax, eax
0x1400087f5  jz      loc_1400088F6
0x1400087fb  test    r12d, r12d
0x1400087fe  jnz     short loc_140008809
0x140008800  lea     r15d, [rbp+1]
0x140008804  jmp     loc_1400088F6
0x140008809  mov     ecx, 8000h; Size
0x14000880e  call    cs:__imp_malloc
0x140008814  mov     rbp, rax
0x140008817  test    rax, rax
0x14000881a  jnz     short loc_140008846
0x14000881c  lea     rdi, CurrentChar
0x140008823  mov     r9, rbx
0x140008826  lea     r8, aSS_1; "%s%s"
0x14000882d  mov     [rsp+58h+var_38], rdi
0x140008832  lea     rdx, aCouldNotAlloca; "Could not allocate buffer to copy %1 to"...
0x140008839  mov     rcx, r14
0x14000883c  call    ErrSet
0x140008841  jmp     loc_1400088F6
0x140008846  test    edi, edi
0x140008848  mov     edx, 8301h; OpenFlag
0x14000884d  lea     rdi, CurrentChar
0x140008854  mov     rcx, rdi; FileName
0x140008857  jz      short loc_140008860
0x140008859  call    OpenFileUNC
0x14000885e  jmp     short loc_14000886C
0x140008860  mov     r8d, 180h
0x140008866  call    cs:__imp__open
0x14000886c  mov     r12d, eax
0x14000886f  cmp     eax, 0FFFFFFFFh
0x140008872  jnz     short loc_1400088C2
0x140008874  mov     r9, rdi
0x140008877  lea     r8, aS_4; "%s"
0x14000887e  lea     rdx, aCannotOpenFile; "Cannot open file: %1"
0x140008885  mov     rcx, r14
0x140008888  call    ErrSet
0x14000888d  jmp     short loc_1400088F6
0x14000888f  mov     r8d, 8000h; MaxCharCount
0x140008895  mov     rdx, rbp; DstBuf
0x140008898  mov     ecx, esi; FileHandle
0x14000889a  call    cs:__imp__read
0x1400088a0  mov     edi, eax
0x1400088a2  cmp     eax, 0FFFFFFFFh
0x1400088a5  jz      loc_14000892F
0x1400088ab  test    eax, eax
0x1400088ad  jz      short loc_1400088C2
0x1400088af  mov     r8d, eax; MaxCharCount
0x1400088b2  mov     rdx, rbp; Buf
0x1400088b5  mov     ecx, r12d; FileHandle
0x1400088b8  call    cs:__imp__write
0x1400088be  cmp     eax, edi
0x1400088c0  jnz     short loc_140008926
0x1400088c2  mov     ecx, esi; FileHandle
0x1400088c4  call    cs:__imp__eof
0x1400088ca  test    eax, eax
0x1400088cc  jz      short loc_14000888F
0x1400088ce  mov     ecx, r12d; FileHandle
0x1400088d1  call    cs:__imp__close
0x1400088d7  mov     r8, r14
0x1400088da  lea     rdx, [rsp+58h+arg_8]
0x1400088df  call    SetFileTimeAndAttr
0x1400088e4  mov     ecx, r15d
0x1400088e7  test    eax, eax
0x1400088e9  mov     r15d, 1
0x1400088ef  cmovnz  ecx, r15d
0x1400088f3  mov     r15d, ecx
0x1400088f6  mov     ecx, esi; FileHandle
0x1400088f8  call    cs:__imp__close
0x1400088fe  test    rbp, rbp
0x140008901  jz      short loc_14000890C
0x140008903  mov     rcx, rbp; Block
0x140008906  call    cs:__imp_free
0x14000890c  mov     rbx, [rsp+58h+arg_0]
0x140008911  mov     eax, r15d
0x140008914  mov     rbp, [rsp+58h+arg_10]
0x140008919  add     rsp, 30h
0x14000891d  pop     r15
0x14000891f  pop     r14
0x140008921  pop     r12
0x140008923  pop     rdi
0x140008924  pop     rsi
0x140008925  retn
0x140008926  lea     rdx, aCannotWriteFil; "Cannot write file: %1"
0x14000892d  jmp     short loc_140008936
0x14000892f  lea     rdx, aCannotReadFile; "Cannot read file: %1"
0x140008936  lea     r8, aS_4; "%s"
0x14000893d  mov     r9, rbx
0x140008940  mov     rcx, r14
0x140008943  call    ErrSet
0x140008948  mov     ecx, r12d; FileHandle
0x14000894b  call    cs:__imp__close
0x140008951  jmp     short loc_1400088F6
```
