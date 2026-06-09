# CTrackedShader<ID3D11VertexShader,1>::DecompressShader(uchar const *,uint,bool *)

- ea: `0x1800b60cc`
- end: `0x1800b6259`
- name: `?DecompressShader@?$CTrackedShader@UID3D11VertexShader@@$00@@AEAAJPEBEIPEA_N@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b5e98`

## callees

- `0x18001fd58`
- `0x1800b60cc`
- `0x1800b820c`
- `0x180111548`
- `0x1801d3c04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b61e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b61e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6202`
- `Cabinet!__imp_CreateDecompressor` at `0x1800b6154`
- `Cabinet!__imp_CreateDecompressor` at `0x1800b6154`
- `Cabinet!__imp_Decompress` at `0x1800b6187`
- `Cabinet!__imp_Decompress` at `0x1800b61c7`
- `Cabinet!__imp_Decompress` at `0x1800b6187`
- `Cabinet!__imp_Decompress` at `0x1800b61c7`
- `Cabinet!__imp_CloseDecompressor` at `0x1800b61d8`
- `Cabinet!__imp_CloseDecompressor` at `0x1800b61d8`

## pseudocode

```c
__int64 __fastcall CTrackedShader<ID3D11VertexShader,1>::DecompressShader(
        __int64 a1,
        int *a2,
        unsigned int a3,
        _BYTE *a4)
{
  __int64 v4; // rdi
  int v8; // eax
  __int64 v10; // rbx
  __int64 v11; // r12
  int LastErrorAsFailHr; // eax
  signed int v13; // edi
  signed int v14; // eax
  unsigned int v15; // ebx
  signed int LastError; // eax
  int v17; // ecx
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+98h] [rbp+58h] BYREF

  v4 = a3;
  *a4 = 0;
  if ( a3 < 4 )
    goto LABEL_29;
  v8 = *a2;
  LODWORD(v19) = -1058713334;
  if ( v8 == 1128421444 )
    return 0;
  if ( v8 == (_DWORD)v19 && IsAddressInD2DModule(a2) )
  {
    v18 = 0;
    if ( (unsigned int)CreateDecompressor(2, 0, &v18) )
    {
      v10 = v18;
      v19 = 0;
      v11 = v4;
      if ( !(unsigned int)Decompress(v18, a2, v4, 0, 0, &v19) )
      {
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError != 122 )
        {
          if ( LastError > 0 )
            v13 = (unsigned __int16)LastError | 0x80070000;
          if ( v13 >= 0 )
            goto LABEL_11;
          v17 = v13;
          goto LABEL_24;
        }
      }
      LastErrorAsFailHr = CArray<unsigned char,CPodTraits<unsigned char>,CDefaultAllocator>::Resize(
                            a1 + 16,
                            (unsigned int)v19);
      v13 = LastErrorAsFailHr;
      if ( LastErrorAsFailHr >= 0 )
      {
        if ( (unsigned int)Decompress(v18, a2, v11, *(_QWORD *)(a1 + 16), *(unsigned int *)(a1 + 24), &v19) )
        {
          *a4 = 1;
LABEL_11:
          CloseDecompressor(v10);
          return (unsigned int)v13;
        }
        LastErrorAsFailHr = GetLastErrorAsFailHr();
        v13 = LastErrorAsFailHr;
        if ( LastErrorAsFailHr >= 0 )
          goto LABEL_11;
      }
      v17 = LastErrorAsFailHr;
LABEL_24:
      DoStackCapture(v17);
      goto LABEL_11;
    }
    v14 = GetLastError();
    v15 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      if ( (v15 & 0x80000000) == 0 )
        return v15;
    }
    else
    {
      v15 = -2147467259;
    }
    DoStackCapture(v15);
  }
  else
  {
LABEL_29:
    v15 = -2147418113;
  }
  DoStackCapture(v15);
  return v15;
}

```

## disassembly

```asm
0x1800b60cc  mov     [rsp-38h+arg_0], rbx
0x1800b60d1  push    rbp
0x1800b60d2  push    rsi
0x1800b60d3  push    rdi
0x1800b60d4  push    r12
0x1800b60d6  push    r13
0x1800b60d8  push    r14
0x1800b60da  push    r15
0x1800b60dc  mov     rbp, rsp
0x1800b60df  sub     rsp, 40h
0x1800b60e3  xor     r15d, r15d
0x1800b60e6  mov     edi, r8d
0x1800b60e9  mov     [r9], r15b
0x1800b60ec  mov     r14, r9
0x1800b60ef  mov     rsi, rdx
0x1800b60f2  mov     r13, rcx
0x1800b60f5  cmp     r8d, 4
0x1800b60f9  jb      loc_1800B6252
0x1800b60ff  mov     eax, [rdx]
0x1800b6101  mov     [rbp+arg_10], 43425844h
0x1800b6108  mov     dword ptr [rbp+arg_18], 0C0E5510Ah
0x1800b610f  cmp     eax, [rbp+arg_10]
0x1800b6112  jnz     short loc_1800B612E
0x1800b6114  xor     eax, eax
0x1800b6116  mov     rbx, [rsp+40h+arg_0]
0x1800b611e  add     rsp, 40h
0x1800b6122  pop     r15
0x1800b6124  pop     r14
0x1800b6126  pop     r13
0x1800b6128  pop     r12
0x1800b612a  pop     rdi
0x1800b612b  pop     rsi
0x1800b612c  pop     rbp
0x1800b612d  retn
0x1800b612e  cmp     eax, dword ptr [rbp+arg_18]
0x1800b6131  jnz     loc_1800B6252
0x1800b6137  mov     rcx, rsi; void *
0x1800b613a  call    ?IsAddressInD2DModule@@YA_NPEBX@Z; IsAddressInD2DModule(void const *)
0x1800b613f  test    al, al
0x1800b6141  jz      loc_1800B6252
0x1800b6147  xor     edx, edx
0x1800b6149  mov     [rbp+var_10], r15
0x1800b614d  lea     r8, [rbp+var_10]
0x1800b6151  lea     ecx, [rdx+2]
0x1800b6154  call    cs:__imp_CreateDecompressor
0x1800b615a  test    eax, eax
0x1800b615c  jz      loc_1800B61E5
0x1800b6162  mov     rbx, [rbp+var_10]
0x1800b6166  lea     rax, [rbp+arg_18]
0x1800b616a  mov     [rsp+40h+var_18], rax
0x1800b616f  mov     rcx, rbx
0x1800b6172  xor     r9d, r9d
0x1800b6175  mov     [rsp+40h+var_20], r15
0x1800b617a  mov     r8, rdi
0x1800b617d  mov     [rbp+arg_18], r15
0x1800b6181  mov     rdx, rsi
0x1800b6184  mov     r12, rdi
0x1800b6187  call    cs:__imp_Decompress
0x1800b618d  test    eax, eax
0x1800b618f  jz      short loc_1800B6202
0x1800b6191  mov     edx, dword ptr [rbp+arg_18]
0x1800b6194  lea     rcx, [r13+10h]
0x1800b6198  call    ?Resize@?$CArray@EV?$CPodTraits@E@@VCDefaultAllocator@@@@QEAAJI@Z; CArray<uchar,CPodTraits<uchar>,CDefaultAllocator>::Resize(uint)
0x1800b619d  mov     edi, eax
0x1800b619f  test    eax, eax
0x1800b61a1  js      loc_1800B622F
0x1800b61a7  mov     eax, [r13+18h]
0x1800b61ab  lea     rcx, [rbp+arg_18]
0x1800b61af  mov     r9, [r13+10h]
0x1800b61b3  mov     r8, r12
0x1800b61b6  mov     [rsp+40h+var_18], rcx
0x1800b61bb  mov     rdx, rsi
0x1800b61be  mov     rcx, [rbp+var_10]
0x1800b61c2  mov     [rsp+40h+var_20], rax
0x1800b61c7  call    cs:__imp_Decompress
0x1800b61cd  test    eax, eax
0x1800b61cf  jz      short loc_1800B6224
0x1800b61d1  mov     byte ptr [r14], 1
0x1800b61d5  mov     rcx, rbx
0x1800b61d8  call    cs:__imp_CloseDecompressor
0x1800b61de  mov     eax, edi
0x1800b61e0  jmp     loc_1800B6116
0x1800b61e5  call    cs:__imp_GetLastError
0x1800b61eb  mov     ebx, eax
0x1800b61ed  test    eax, eax
0x1800b61ef  jz      short loc_1800B6238
0x1800b61f1  jle     short loc_1800B61FC
0x1800b61f3  movzx   ebx, ax
0x1800b61f6  or      ebx, 80070000h
0x1800b61fc  test    ebx, ebx
0x1800b61fe  jns     short loc_1800B624B
0x1800b6200  jmp     short loc_1800B623D
0x1800b6202  call    cs:__imp_GetLastError
0x1800b6208  mov     edi, eax
0x1800b620a  cmp     eax, 7Ah ; 'z'
0x1800b620d  jz      short loc_1800B6191
0x1800b620f  test    eax, eax
0x1800b6211  jle     short loc_1800B621C
0x1800b6213  movzx   edi, ax
0x1800b6216  or      edi, 80070000h
0x1800b621c  test    edi, edi
0x1800b621e  jns     short loc_1800B61D5
0x1800b6220  mov     ecx, edi
0x1800b6222  jmp     short loc_1800B6231
0x1800b6224  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1800b6229  mov     edi, eax
0x1800b622b  test    eax, eax
0x1800b622d  jns     short loc_1800B61D5
0x1800b622f  mov     ecx, eax; int
0x1800b6231  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b6236  jmp     short loc_1800B61D5
0x1800b6238  mov     ebx, 80004005h
0x1800b623d  mov     ecx, ebx; int
0x1800b623f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b6244  mov     ecx, ebx; int
0x1800b6246  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b624b  mov     eax, ebx
0x1800b624d  jmp     loc_1800B6116
0x1800b6252  mov     ebx, 8000FFFFh
0x1800b6257  jmp     short loc_1800B6244
```
