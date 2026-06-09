# CPackage::EmbedInitFromFile(ushort const *,int)

- ea: `0x180007b28`
- end: `0x180007cf1`
- name: `?EmbedInitFromFile@CPackage@@IEAAJPEBGH@Z`
- size: `457`
- prototype: `__int64 __fastcall(CPackage *__hidden this, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800046d0`
- `0x180006830`
- `0x180008470`
- `0x180009144`

## callees

- `0x180007b28`
- `0x18000a43c`
- `0x18000a6ec`
- `0x18000baa0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cdc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007be2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180007be2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007ba9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007ba9`

## pseudocode

```c
__int64 __fastcall CPackage::EmbedInitFromFile(CPackage *this, const unsigned __int16 *a2, int a3)
{
  _QWORD *v6; // rax
  HANDLE FileW; // rax
  void *v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rcx
  _WORD *v12; // rax
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  _WORD *v15; // rcx
  struct _IC *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  DWORD FileSizeHigh; // [rsp+80h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 14) )
  {
    v6 = operator new(0x270u);
    *((_QWORD *)this + 14) = v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
    v6[74] = 0;
    *(_QWORD *)(*((_QWORD *)this + 14) + 600LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 14) + 608LL) = 0;
    *(_DWORD *)(*((_QWORD *)this + 14) + 616LL) = 1;
  }
  FileW = CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    *((_DWORD *)this + 26) = 3;
    FileSizeHigh = 0;
    *(_DWORD *)(*((_QWORD *)this + 14) + 68LL) = GetFileSize(FileW, &FileSizeHigh);
    v10 = *((_QWORD *)this + 14);
    if ( *(_DWORD *)(v10 + 68) == -1 )
    {
      v9 = -2147467259;
    }
    else
    {
      *(_DWORD *)(v10 + 64) = 0;
      v9 = 0;
      **((_DWORD **)this + 14) = 64;
      if ( a3 )
      {
        v11 = 2147483646;
        v12 = (_WORD *)(*((_QWORD *)this + 14) + 72LL);
        v13 = a2;
        v14 = 260;
        do
        {
          if ( !v11 )
            break;
          if ( !*v13 )
            break;
          *v12++ = *v13++;
          --v11;
          --v14;
        }
        while ( v14 );
        v15 = v12 - 1;
        if ( v14 )
          v15 = v12;
        *v15 = 0;
        CPackage::_DestroyIC(this);
        v16 = CPackage::_IconCreateFromFile(this, a2);
        v17 = *((_QWORD *)this + 20);
        *((_QWORD *)this + 12) = v16;
        if ( v17 )
          (*(void (__fastcall **)(__int64, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 48LL))(
            v17,
            ((unsigned __int64)this + 32) & -(__int64)(this != 0),
            0,
            0);
        v18 = *((_QWORD *)this + 25);
        if ( v18 )
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 32LL))(
            v18,
            *((unsigned int *)this + 52),
            *((unsigned int *)this + 53));
      }
      *((_DWORD *)this + 38) = 1;
    }
    CloseHandle(v8);
  }
  return v9;
}

```

## disassembly

```asm
0x180007b28  push    rbx
0x180007b2a  push    rbp
0x180007b2b  push    rsi
0x180007b2c  push    rdi
0x180007b2d  push    r14
0x180007b2f  push    r15
0x180007b31  sub     rsp, 48h
0x180007b35  xor     r15d, r15d
0x180007b38  mov     r14d, r8d
0x180007b3b  mov     rbp, rdx
0x180007b3e  mov     rbx, rcx
0x180007b41  cmp     [rcx+70h], r15
0x180007b45  jnz     short loc_180007B85
0x180007b47  mov     ecx, 270h; unsigned __int64
0x180007b4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b51  mov     [rbx+70h], rax
0x180007b55  test    rax, rax
0x180007b58  jz      short loc_180007BC2
0x180007b5a  mov     [rax+250h], r15
0x180007b61  mov     rax, [rbx+70h]
0x180007b65  mov     [rax+258h], r15
0x180007b6c  mov     rax, [rbx+70h]
0x180007b70  mov     [rax+260h], r15
0x180007b77  mov     rax, [rbx+70h]
0x180007b7b  mov     dword ptr [rax+268h], 1
0x180007b85  mov     edi, 3
0x180007b8a  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x180007b8f  mov     r8d, edi; dwShareMode
0x180007b92  mov     [rsp+78h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180007b9a  xor     r9d, r9d; lpSecurityAttributes
0x180007b9d  mov     [rsp+78h+dwCreationDisposition], edi; dwCreationDisposition
0x180007ba1  mov     edx, 80000000h; dwDesiredAccess
0x180007ba6  mov     rcx, rbp; lpFileName
0x180007ba9  call    cs:__imp_CreateFileW
0x180007baf  mov     rsi, rax
0x180007bb2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007bb6  jnz     short loc_180007BCC
0x180007bb8  mov     edi, 80004005h
0x180007bbd  jmp     loc_180007CE2
0x180007bc2  mov     edi, 8007000Eh
0x180007bc7  jmp     loc_180007CE2
0x180007bcc  lea     rdx, [rsp+78h+FileSizeHigh]; lpFileSizeHigh
0x180007bd4  mov     [rbx+68h], edi
0x180007bd7  mov     rcx, rsi; hFile
0x180007bda  mov     [rsp+78h+FileSizeHigh], r15d
0x180007be2  call    cs:__imp_GetFileSize
0x180007be8  mov     rcx, [rbx+70h]
0x180007bec  mov     [rcx+44h], eax
0x180007bef  mov     rax, [rbx+70h]
0x180007bf3  cmp     dword ptr [rax+44h], 0FFFFFFFFh
0x180007bf7  jnz     short loc_180007C03
0x180007bf9  mov     edi, 80004005h
0x180007bfe  jmp     loc_180007CD9
0x180007c03  mov     [rax+40h], r15d
0x180007c07  mov     edi, r15d
0x180007c0a  mov     rax, [rbx+70h]
0x180007c0e  mov     dword ptr [rax], 40h ; '@'
0x180007c14  test    r14d, r14d
0x180007c17  jz      loc_180007CCF
0x180007c1d  mov     rax, [rbx+70h]
0x180007c21  mov     ecx, 7FFFFFFEh
0x180007c26  add     rax, 48h ; 'H'
0x180007c2a  mov     r8, rbp
0x180007c2d  mov     edx, 104h
0x180007c32  test    rcx, rcx
0x180007c35  jz      short loc_180007C56
0x180007c37  movzx   r9d, word ptr [r8]
0x180007c3b  test    r9w, r9w
0x180007c3f  jz      short loc_180007C56
0x180007c41  mov     [rax], r9w
0x180007c45  add     r8, 2
0x180007c49  add     rax, 2
0x180007c4d  dec     rcx
0x180007c50  sub     rdx, 1
0x180007c54  jnz     short loc_180007C32
0x180007c56  test    rdx, rdx
0x180007c59  lea     rcx, [rax-2]
0x180007c5d  cmovnz  rcx, rax
0x180007c61  mov     [rcx], r15w
0x180007c65  mov     rcx, rbx; this
0x180007c68  call    ?_DestroyIC@CPackage@@IEAAXXZ; CPackage::_DestroyIC(void)
0x180007c6d  mov     rdx, rbp; unsigned __int16 *
0x180007c70  mov     rcx, rbx; this
0x180007c73  call    ?_IconCreateFromFile@CPackage@@IEAAPEAU_IC@@PEBG@Z; CPackage::_IconCreateFromFile(ushort const *)
0x180007c78  mov     rcx, [rbx+0A0h]
0x180007c7f  mov     [rbx+60h], rax
0x180007c83  test    rcx, rcx
0x180007c86  jz      short loc_180007CAA
0x180007c88  mov     r9, [rcx]
0x180007c8b  lea     r8, [rbx+20h]
0x180007c8f  mov     rax, rbx
0x180007c92  neg     rax
0x180007c95  mov     rax, [r9+30h]
0x180007c99  sbb     rdx, rdx
0x180007c9c  and     rdx, r8
0x180007c9f  xor     r9d, r9d
0x180007ca2  xor     r8d, r8d
0x180007ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007caa  mov     rcx, [rbx+0C8h]
0x180007cb1  test    rcx, rcx
0x180007cb4  jz      short loc_180007CCF
0x180007cb6  mov     rax, [rcx]
0x180007cb9  mov     r8d, [rbx+0D4h]
0x180007cc0  mov     edx, [rbx+0D0h]
0x180007cc6  mov     rax, [rax+20h]
0x180007cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ccf  mov     dword ptr [rbx+98h], 1
0x180007cd9  mov     rcx, rsi; hObject
0x180007cdc  call    cs:__imp_CloseHandle
0x180007ce2  mov     eax, edi
0x180007ce4  add     rsp, 48h
0x180007ce8  pop     r15
0x180007cea  pop     r14
0x180007cec  pop     rdi
0x180007ced  pop     rsi
0x180007cee  pop     rbp
0x180007cef  pop     rbx
0x180007cf0  retn
```
