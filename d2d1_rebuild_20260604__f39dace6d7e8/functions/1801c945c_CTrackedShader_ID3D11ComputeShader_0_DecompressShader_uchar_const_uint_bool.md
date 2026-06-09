# CTrackedShader<ID3D11ComputeShader,0>::DecompressShader(uchar const *,uint,bool *)

- ea: `0x1801c945c`
- end: `0x1801c95c9`
- name: `?DecompressShader@?$CTrackedShader@UID3D11ComputeShader@@$0A@@@AEAAJPEBEIPEA_N@Z`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1802300b8`

## callees

- `0x18001fd58`
- `0x1800b820c`
- `0x180111548`
- `0x1801c945c`
- `0x1801d3c04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c951e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c951e`
- `Cabinet!__imp_CreateDecompressor` at `0x1801c94d1`
- `Cabinet!__imp_CreateDecompressor` at `0x1801c94d1`
- `Cabinet!__imp_Decompress` at `0x1801c9514`
- `Cabinet!__imp_Decompress` at `0x1801c957b`
- `Cabinet!__imp_Decompress` at `0x1801c9514`
- `Cabinet!__imp_Decompress` at `0x1801c957b`
- `Cabinet!__imp_CloseDecompressor` at `0x1801c9599`
- `Cabinet!__imp_CloseDecompressor` at `0x1801c9599`

## pseudocode

```c
__int64 __fastcall CTrackedShader<ID3D11ComputeShader,0>::DecompressShader(
        __int64 a1,
        int *a2,
        unsigned int a3,
        _BYTE *a4)
{
  __int64 v4; // rdi
  int v8; // eax
  int LastErrorAsFailHr; // ebx
  __int64 v11; // rbx
  __int64 v12; // r12
  signed int LastError; // eax
  signed int v14; // edi
  int v15; // ecx
  int v16; // eax
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+98h] [rbp+58h] BYREF

  v4 = a3;
  *a4 = 0;
  if ( a3 >= 4 )
  {
    v8 = *a2;
    LODWORD(v18) = -1058713334;
    if ( v8 == 1128421444 )
      return 0;
    if ( v8 == (_DWORD)v18 && IsAddressInD2DModule(a2) )
    {
      v17 = 0;
      if ( !(unsigned int)CreateDecompressor(2, 0, &v17) )
      {
        LastErrorAsFailHr = GetLastErrorAsFailHr();
        if ( LastErrorAsFailHr >= 0 )
          return (unsigned int)LastErrorAsFailHr;
        goto LABEL_24;
      }
      v11 = v17;
      v18 = 0;
      v12 = v4;
      if ( (unsigned int)Decompress(v17, a2, v4, 0, 0, &v18)
        || (LastError = GetLastError(), v14 = LastError, LastError == 122) )
      {
        v16 = CArray<unsigned char,CPodTraits<unsigned char>,CDefaultAllocator>::Resize(a1 + 16, (unsigned int)v18);
        v14 = v16;
        if ( v16 >= 0 )
        {
          if ( (unsigned int)Decompress(v17, a2, v12, *(_QWORD *)(a1 + 16), *(unsigned int *)(a1 + 24), &v18) )
          {
            *a4 = 1;
            goto LABEL_22;
          }
          v16 = GetLastErrorAsFailHr();
          v14 = v16;
          if ( v16 >= 0 )
          {
LABEL_22:
            CloseDecompressor(v11);
            return (unsigned int)v14;
          }
        }
        v15 = v16;
      }
      else
      {
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        if ( v14 >= 0 )
          goto LABEL_22;
        v15 = v14;
      }
      DoStackCapture(v15);
      goto LABEL_22;
    }
  }
  LastErrorAsFailHr = -2147418113;
LABEL_24:
  DoStackCapture(LastErrorAsFailHr);
  return (unsigned int)LastErrorAsFailHr;
}

```

## disassembly

```asm
0x1801c945c  mov     [rsp-38h+arg_0], rbx
0x1801c9461  push    rbp
0x1801c9462  push    rsi
0x1801c9463  push    rdi
0x1801c9464  push    r12
0x1801c9466  push    r13
0x1801c9468  push    r14
0x1801c946a  push    r15
0x1801c946c  mov     rbp, rsp
0x1801c946f  sub     rsp, 40h
0x1801c9473  xor     r15d, r15d
0x1801c9476  mov     edi, r8d
0x1801c9479  mov     [r9], r15b
0x1801c947c  mov     r14, r9
0x1801c947f  mov     rsi, rdx
0x1801c9482  mov     r13, rcx
0x1801c9485  cmp     r8d, 4
0x1801c9489  jb      loc_1801C95A3
0x1801c948f  mov     eax, [rdx]
0x1801c9491  mov     [rbp+arg_10], 43425844h
0x1801c9498  mov     dword ptr [rbp+arg_18], 0C0E5510Ah
0x1801c949f  cmp     eax, [rbp+arg_10]
0x1801c94a2  jnz     short loc_1801C94AB
0x1801c94a4  xor     eax, eax
0x1801c94a6  jmp     loc_1801C95B1
0x1801c94ab  cmp     eax, dword ptr [rbp+arg_18]
0x1801c94ae  jnz     loc_1801C95A3
0x1801c94b4  mov     rcx, rsi; void *
0x1801c94b7  call    ?IsAddressInD2DModule@@YA_NPEBX@Z; IsAddressInD2DModule(void const *)
0x1801c94bc  test    al, al
0x1801c94be  jz      loc_1801C95A3
0x1801c94c4  xor     edx, edx
0x1801c94c6  mov     [rbp+var_10], r15
0x1801c94ca  lea     r8, [rbp+var_10]
0x1801c94ce  lea     ecx, [rdx+2]
0x1801c94d1  call    cs:__imp_CreateDecompressor
0x1801c94d7  test    eax, eax
0x1801c94d9  jnz     short loc_1801C94EF
0x1801c94db  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1801c94e0  mov     ebx, eax
0x1801c94e2  test    eax, eax
0x1801c94e4  js      loc_1801C95A8
0x1801c94ea  jmp     loc_1801C95AF
0x1801c94ef  mov     rbx, [rbp+var_10]
0x1801c94f3  lea     rax, [rbp+arg_18]
0x1801c94f7  mov     [rsp+40h+var_18], rax
0x1801c94fc  mov     rcx, rbx
0x1801c94ff  xor     r9d, r9d
0x1801c9502  mov     [rsp+40h+var_20], r15
0x1801c9507  mov     r8, rdi
0x1801c950a  mov     [rbp+arg_18], r15
0x1801c950e  mov     rdx, rsi
0x1801c9511  mov     r12, rdi
0x1801c9514  call    cs:__imp_Decompress
0x1801c951a  test    eax, eax
0x1801c951c  jnz     short loc_1801C9540
0x1801c951e  call    cs:__imp_GetLastError
0x1801c9524  mov     edi, eax
0x1801c9526  cmp     eax, 7Ah ; 'z'
0x1801c9529  jz      short loc_1801C9540
0x1801c952b  test    eax, eax
0x1801c952d  jle     short loc_1801C9538
0x1801c952f  movzx   edi, ax
0x1801c9532  or      edi, 80070000h
0x1801c9538  test    edi, edi
0x1801c953a  jns     short loc_1801C9596
0x1801c953c  mov     ecx, edi
0x1801c953e  jmp     short loc_1801C9554
0x1801c9540  mov     edx, dword ptr [rbp+arg_18]
0x1801c9543  lea     rcx, [r13+10h]
0x1801c9547  call    ?Resize@?$CArray@EV?$CPodTraits@E@@VCDefaultAllocator@@@@QEAAJI@Z; CArray<uchar,CPodTraits<uchar>,CDefaultAllocator>::Resize(uint)
0x1801c954c  mov     edi, eax
0x1801c954e  test    eax, eax
0x1801c9550  jns     short loc_1801C955B
0x1801c9552  mov     ecx, eax; int
0x1801c9554  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801c9559  jmp     short loc_1801C9596
0x1801c955b  mov     eax, [r13+18h]
0x1801c955f  lea     rcx, [rbp+arg_18]
0x1801c9563  mov     r9, [r13+10h]
0x1801c9567  mov     r8, r12
0x1801c956a  mov     [rsp+40h+var_18], rcx
0x1801c956f  mov     rdx, rsi
0x1801c9572  mov     rcx, [rbp+var_10]
0x1801c9576  mov     [rsp+40h+var_20], rax
0x1801c957b  call    cs:__imp_Decompress
0x1801c9581  test    eax, eax
0x1801c9583  jnz     short loc_1801C9592
0x1801c9585  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1801c958a  mov     edi, eax
0x1801c958c  test    eax, eax
0x1801c958e  jns     short loc_1801C9596
0x1801c9590  jmp     short loc_1801C9552
0x1801c9592  mov     byte ptr [r14], 1
0x1801c9596  mov     rcx, rbx
0x1801c9599  call    cs:__imp_CloseDecompressor
0x1801c959f  mov     eax, edi
0x1801c95a1  jmp     short loc_1801C95B1
0x1801c95a3  mov     ebx, 8000FFFFh
0x1801c95a8  mov     ecx, ebx; int
0x1801c95aa  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801c95af  mov     eax, ebx
0x1801c95b1  mov     rbx, [rsp+40h+arg_0]
0x1801c95b9  add     rsp, 40h
0x1801c95bd  pop     r15
0x1801c95bf  pop     r14
0x1801c95c1  pop     r13
0x1801c95c3  pop     r12
0x1801c95c5  pop     rdi
0x1801c95c6  pop     rsi
0x1801c95c7  pop     rbp
0x1801c95c8  retn
```
