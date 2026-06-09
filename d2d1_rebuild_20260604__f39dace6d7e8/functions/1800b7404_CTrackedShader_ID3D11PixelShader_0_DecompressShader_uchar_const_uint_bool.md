# CTrackedShader<ID3D11PixelShader,0>::DecompressShader(uchar const *,uint,bool *)

- ea: `0x1800b7404`
- end: `0x1800b7596`
- name: `?DecompressShader@?$CTrackedShader@UID3D11PixelShader@@$0A@@@AEAAJPEBEIPEA_N@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b6f6c`

## callees

- `0x18001fd58`
- `0x1800b7404`
- `0x1800b820c`
- `0x180111548`
- `0x1801d3c04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b74b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b74b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7550`
- `Cabinet!__imp_CreateDecompressor` at `0x1800b7476`
- `Cabinet!__imp_CreateDecompressor` at `0x1800b7476`
- `Cabinet!__imp_Decompress` at `0x1800b74a9`
- `Cabinet!__imp_Decompress` at `0x1800b74f6`
- `Cabinet!__imp_Decompress` at `0x1800b74a9`
- `Cabinet!__imp_Decompress` at `0x1800b74f6`
- `Cabinet!__imp_CloseDecompressor` at `0x1800b7507`
- `Cabinet!__imp_CloseDecompressor` at `0x1800b7507`

## pseudocode

```c
__int64 __fastcall CTrackedShader<ID3D11PixelShader,0>::DecompressShader(
        __int64 a1,
        int *a2,
        unsigned int a3,
        _BYTE *a4)
{
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // r12
  signed int LastError; // eax
  signed int v12; // edi
  int LastErrorAsFailHr; // eax
  unsigned int v15; // ebx
  int v16; // ecx
  signed int v17; // eax
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+98h] [rbp+58h] BYREF

  *a4 = 0;
  if ( a3 < 4 )
    goto LABEL_12;
  v8 = *a2;
  LODWORD(v19) = -1058713334;
  if ( v8 != 1128421444 )
  {
    if ( v8 == (_DWORD)v19 && IsAddressInD2DModule(a2) )
    {
      v18 = 0;
      if ( (unsigned int)CreateDecompressor(2, 0, &v18) )
      {
        v9 = v18;
        v19 = 0;
        v10 = a3;
        if ( (unsigned int)Decompress(v18, a2, a3, 0, 0, &v19)
          || (LastError = GetLastError(), v12 = LastError, LastError == 122) )
        {
          LastErrorAsFailHr = CArray<unsigned char,CPodTraits<unsigned char>,CDefaultAllocator>::Resize(
                                a1 + 16,
                                (unsigned int)v19);
          v12 = LastErrorAsFailHr;
          if ( LastErrorAsFailHr >= 0 )
          {
            if ( (unsigned int)Decompress(v18, a2, v10, *(_QWORD *)(a1 + 16), *(unsigned int *)(a1 + 24), &v19) )
            {
              *a4 = 1;
LABEL_11:
              CloseDecompressor(v9);
              return (unsigned int)v12;
            }
            LastErrorAsFailHr = GetLastErrorAsFailHr();
            v12 = LastErrorAsFailHr;
            if ( LastErrorAsFailHr >= 0 )
              goto LABEL_11;
          }
          v16 = LastErrorAsFailHr;
        }
        else
        {
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          if ( v12 >= 0 )
            goto LABEL_11;
          v16 = v12;
        }
        DoStackCapture(v16);
        goto LABEL_11;
      }
      v17 = GetLastError();
      v15 = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v15 = (unsigned __int16)v17 | 0x80070000;
        if ( (v15 & 0x80000000) == 0 )
          return v15;
      }
      else
      {
        v15 = -2147467259;
      }
      DoStackCapture(v15);
LABEL_13:
      DoStackCapture(v15);
      return v15;
    }
LABEL_12:
    v15 = -2147418113;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x1800b7404  mov     [rsp-38h+arg_0], rbx
0x1800b7409  push    rbp
0x1800b740a  push    rsi
0x1800b740b  push    rdi
0x1800b740c  push    r12
0x1800b740e  push    r13
0x1800b7410  push    r14
0x1800b7412  push    r15
0x1800b7414  mov     rbp, rsp
0x1800b7417  sub     rsp, 40h
0x1800b741b  xor     r15d, r15d
0x1800b741e  mov     edi, r8d
0x1800b7421  mov     [r9], r15b
0x1800b7424  mov     r14, r9
0x1800b7427  mov     rsi, rdx
0x1800b742a  mov     r13, rcx
0x1800b742d  cmp     r8d, 4
0x1800b7431  jb      loc_1800B7511
0x1800b7437  mov     eax, [rdx]
0x1800b7439  mov     [rbp+arg_10], 43425844h
0x1800b7440  mov     dword ptr [rbp+arg_18], 0C0E5510Ah
0x1800b7447  cmp     eax, [rbp+arg_10]
0x1800b744a  jz      loc_1800B754C
0x1800b7450  cmp     eax, dword ptr [rbp+arg_18]
0x1800b7453  jnz     loc_1800B7511
0x1800b7459  mov     rcx, rdx; void *
0x1800b745c  call    ?IsAddressInD2DModule@@YA_NPEBX@Z; IsAddressInD2DModule(void const *)
0x1800b7461  test    al, al
0x1800b7463  jz      loc_1800B7511
0x1800b7469  xor     edx, edx
0x1800b746b  mov     [rbp+var_10], r15
0x1800b746f  lea     r8, [rbp+var_10]
0x1800b7473  lea     ecx, [rdx+2]
0x1800b7476  call    cs:__imp_CreateDecompressor
0x1800b747c  test    eax, eax
0x1800b747e  jz      loc_1800B7550
0x1800b7484  mov     rbx, [rbp+var_10]
0x1800b7488  lea     rax, [rbp+arg_18]
0x1800b748c  mov     [rsp+40h+var_18], rax
0x1800b7491  mov     rcx, rbx
0x1800b7494  xor     r9d, r9d
0x1800b7497  mov     [rsp+40h+var_20], r15
0x1800b749c  mov     r8d, edi
0x1800b749f  mov     [rbp+arg_18], r15
0x1800b74a3  mov     rdx, rsi
0x1800b74a6  mov     r12d, edi
0x1800b74a9  call    cs:__imp_Decompress
0x1800b74af  test    eax, eax
0x1800b74b1  jnz     short loc_1800B74C0
0x1800b74b3  call    cs:__imp_GetLastError
0x1800b74b9  mov     edi, eax
0x1800b74bb  cmp     eax, 7Ah ; 'z'
0x1800b74be  jnz     short loc_1800B7537
0x1800b74c0  mov     edx, dword ptr [rbp+arg_18]
0x1800b74c3  lea     rcx, [r13+10h]
0x1800b74c7  call    ?Resize@?$CArray@EV?$CPodTraits@E@@VCDefaultAllocator@@@@QEAAJI@Z; CArray<uchar,CPodTraits<uchar>,CDefaultAllocator>::Resize(uint)
0x1800b74cc  mov     edi, eax
0x1800b74ce  test    eax, eax
0x1800b74d0  js      loc_1800B758A
0x1800b74d6  mov     eax, [r13+18h]
0x1800b74da  lea     rcx, [rbp+arg_18]
0x1800b74de  mov     r9, [r13+10h]
0x1800b74e2  mov     r8, r12
0x1800b74e5  mov     [rsp+40h+var_18], rcx
0x1800b74ea  mov     rdx, rsi
0x1800b74ed  mov     rcx, [rbp+var_10]
0x1800b74f1  mov     [rsp+40h+var_20], rax
0x1800b74f6  call    cs:__imp_Decompress
0x1800b74fc  test    eax, eax
0x1800b74fe  jz      short loc_1800B757B
0x1800b7500  mov     byte ptr [r14], 1
0x1800b7504  mov     rcx, rbx
0x1800b7507  call    cs:__imp_CloseDecompressor
0x1800b750d  mov     eax, edi
0x1800b750f  jmp     short loc_1800B751F
0x1800b7511  mov     ebx, 8000FFFFh
0x1800b7516  mov     ecx, ebx; int
0x1800b7518  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b751d  mov     eax, ebx
0x1800b751f  mov     rbx, [rsp+40h+arg_0]
0x1800b7527  add     rsp, 40h
0x1800b752b  pop     r15
0x1800b752d  pop     r14
0x1800b752f  pop     r13
0x1800b7531  pop     r12
0x1800b7533  pop     rdi
0x1800b7534  pop     rsi
0x1800b7535  pop     rbp
0x1800b7536  retn
0x1800b7537  test    eax, eax
0x1800b7539  jle     short loc_1800B7544
0x1800b753b  movzx   edi, ax
0x1800b753e  or      edi, 80070000h
0x1800b7544  test    edi, edi
0x1800b7546  jns     short loc_1800B7504
0x1800b7548  mov     ecx, edi
0x1800b754a  jmp     short loc_1800B758C
0x1800b754c  xor     eax, eax
0x1800b754e  jmp     short loc_1800B751F
0x1800b7550  call    cs:__imp_GetLastError
0x1800b7556  mov     ebx, eax
0x1800b7558  test    eax, eax
0x1800b755a  jnz     short loc_1800B756A
0x1800b755c  mov     ebx, 80004005h
0x1800b7561  mov     ecx, ebx; int
0x1800b7563  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b7568  jmp     short loc_1800B7516
0x1800b756a  jle     short loc_1800B7575
0x1800b756c  movzx   ebx, ax
0x1800b756f  or      ebx, 80070000h
0x1800b7575  test    ebx, ebx
0x1800b7577  jns     short loc_1800B751D
0x1800b7579  jmp     short loc_1800B7561
0x1800b757b  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1800b7580  mov     edi, eax
0x1800b7582  test    eax, eax
0x1800b7584  jns     loc_1800B7504
0x1800b758a  mov     ecx, eax; int
0x1800b758c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b7591  jmp     loc_1800B7504
```
