# CPackage::OLE2MPlayerReadFromStream(IStream *)

- ea: `0x180009bc8`
- end: `0x180009dd0`
- name: `?OLE2MPlayerReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180009370`

## callees

- `0x1800079ac`
- `0x1800095e0`
- `0x180009bc8`
- `0x18000a6ec`
- `0x18000a718`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180009d27`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x180009d27`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009cba`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009cba`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180009d50`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180009d50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009dbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009dbb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009c1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009c1f`

## pseudocode

```c
__int64 __fastcall CPackage::OLE2MPlayerReadFromStream(CPackage *this, struct IStream *a2)
{
  struct IStreamVtbl *lpVtbl; // rax
  int TempFileName; // ebx
  _BYTE *v6; // rax
  _BYTE *v7; // rsi
  _BYTE *v8; // rbx
  int i; // ecx
  const CHAR *v10; // rbx
  const CHAR *v11; // rdx
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  _DWORD *v14; // rax
  __int64 v15; // rbp
  __int64 v16; // rax
  __int64 v17; // rcx
  _WORD *v18; // rdx
  _WORD *v19; // rax
  _WORD *v20; // rcx
  SIZE_T uBytes; // [rsp+70h] [rbp+8h] BYREF

  *((_DWORD *)this + 26) = 3;
  lpVtbl = a2->lpVtbl;
  LODWORD(uBytes) = 0;
  TempFileName = ((__int64 (__fastcall *)(struct IStream *, SIZE_T *, __int64, _QWORD))lpVtbl->Read)(a2, &uBytes, 4, 0);
  if ( TempFileName >= 0 )
  {
    if ( (_DWORD)uBytes )
    {
      v6 = LocalAlloc(0, (unsigned int)uBytes);
      v7 = v6;
      if ( v6 )
      {
        TempFileName = ((__int64 (__fastcall *)(struct IStream *, _BYTE *, _QWORD, _QWORD))a2->lpVtbl->Read)(
                         a2,
                         v6,
                         (unsigned int)uBytes,
                         0);
        if ( TempFileName >= 0 )
        {
          v8 = v7;
          for ( i = 0; *v8; ++v8 )
          {
            if ( v8 >= &v7[(unsigned int)uBytes] )
              break;
          }
          v10 = v8 + 1;
          v11 = &v7[(unsigned int)uBytes];
          if ( v10 < v11 )
          {
            do
            {
              if ( !v10[i] )
                break;
              ++i;
            }
            while ( &v10[i] < v11 );
          }
          if ( &v10[i] >= v11 )
            goto LABEL_26;
          v12 = *((_QWORD *)this + 14);
          if ( v12 )
          {
            v13 = *(const WCHAR **)(v12 + 592);
            if ( v13 )
            {
              DeleteFileW(v13);
              operator delete(*(void **)(*((_QWORD *)this + 14) + 592LL));
            }
            operator delete(*((void **)this + 14));
          }
          v14 = operator new(0x270u);
          *((_QWORD *)this + 14) = v14;
          if ( !v14 )
          {
LABEL_26:
            TempFileName = -2147467259;
            goto LABEL_27;
          }
          *v14 = 64;
          v15 = 260;
          *(_DWORD *)(*((_QWORD *)this + 14) + 68LL) = uBytes;
          *(_DWORD *)(*((_QWORD *)this + 14) + 64LL) = 0;
          *(_DWORD *)(*((_QWORD *)this + 14) + 616LL) = 0;
          SHAnsiToUnicode(v10, (PWSTR)(*((_QWORD *)this + 14) + 72LL), 260);
          TempFileName = CPackage::CreateTempFileName(this);
          if ( TempFileName >= 0 )
          {
            if ( CopyFileW((LPCWSTR)(*((_QWORD *)this + 14) + 72LL), *(LPCWSTR *)(*((_QWORD *)this + 14) + 592LL), 1) )
            {
              v16 = *((_QWORD *)this + 14);
              v17 = 2147483646;
              v18 = *(_WORD **)(v16 + 592);
              v19 = (_WORD *)(v16 + 72);
              do
              {
                if ( !v17 )
                  break;
                if ( !*v18 )
                  break;
                *v19++ = *v18++;
                --v17;
                --v15;
              }
              while ( v15 );
              v20 = v19 - 1;
              if ( v15 )
                v20 = v19;
              *v20 = 0;
              MarkFileUnsafe(*(const unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL));
              goto LABEL_27;
            }
            goto LABEL_26;
          }
        }
LABEL_27:
        LocalFree(v7);
      }
    }
  }
  return (unsigned int)TempFileName;
}

```

## disassembly

```asm
0x180009bc8  push    rbx
0x180009bca  push    rbp
0x180009bcb  push    rsi
0x180009bcc  push    rdi
0x180009bcd  push    r14
0x180009bcf  push    r15
0x180009bd1  sub     rsp, 38h
0x180009bd5  mov     dword ptr [rcx+68h], 3
0x180009bdc  mov     r14, rdx
0x180009bdf  mov     rax, [rdx]
0x180009be2  xor     r15d, r15d
0x180009be5  mov     rdi, rcx
0x180009be8  mov     dword ptr [rsp+68h+uBytes], r15d
0x180009bed  xor     r9d, r9d
0x180009bf0  lea     rdx, [rsp+68h+uBytes]
0x180009bf5  mov     rcx, r14
0x180009bf8  mov     rax, [rax+18h]
0x180009bfc  lea     r8d, [r15+4]
0x180009c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c05  mov     ebx, eax
0x180009c07  test    eax, eax
0x180009c09  js      loc_180009DC1
0x180009c0f  mov     eax, dword ptr [rsp+68h+uBytes]
0x180009c13  test    eax, eax
0x180009c15  jz      loc_180009DC1
0x180009c1b  mov     edx, eax; uBytes
0x180009c1d  xor     ecx, ecx; uFlags
0x180009c1f  call    cs:__imp_LocalAlloc
0x180009c25  mov     rsi, rax
0x180009c28  test    rax, rax
0x180009c2b  jz      loc_180009DC1
0x180009c31  mov     rcx, [r14]
0x180009c34  xor     r9d, r9d
0x180009c37  mov     r8d, dword ptr [rsp+68h+uBytes]
0x180009c3c  mov     rdx, rsi
0x180009c3f  mov     rax, [rcx+18h]
0x180009c43  mov     rcx, r14
0x180009c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c4b  mov     ebx, eax
0x180009c4d  test    eax, eax
0x180009c4f  js      loc_180009DB8
0x180009c55  mov     rbx, rsi
0x180009c58  mov     ecx, r15d
0x180009c5b  cmp     [rsi], r15b
0x180009c5e  jz      short loc_180009C74
0x180009c60  mov     eax, dword ptr [rsp+68h+uBytes]
0x180009c64  add     rax, rsi
0x180009c67  cmp     rbx, rax
0x180009c6a  jnb     short loc_180009C74
0x180009c6c  inc     rbx
0x180009c6f  cmp     [rbx], r15b
0x180009c72  jnz     short loc_180009C60
0x180009c74  mov     edx, dword ptr [rsp+68h+uBytes]
0x180009c78  inc     rbx
0x180009c7b  add     rdx, rsi
0x180009c7e  cmp     rbx, rdx
0x180009c81  jnb     short loc_180009C97
0x180009c83  mov     eax, ecx
0x180009c85  cmp     [rax+rbx], r15b
0x180009c89  jz      short loc_180009C97
0x180009c8b  inc     ecx
0x180009c8d  mov     eax, ecx
0x180009c8f  add     rax, rbx
0x180009c92  cmp     rax, rdx
0x180009c95  jb      short loc_180009C83
0x180009c97  mov     eax, ecx
0x180009c99  add     rax, rbx
0x180009c9c  cmp     rax, rdx
0x180009c9f  jnb     loc_180009DB3
0x180009ca5  mov     rax, [rdi+70h]
0x180009ca9  test    rax, rax
0x180009cac  jz      short loc_180009CD9
0x180009cae  mov     rcx, [rax+250h]; lpFileName
0x180009cb5  test    rcx, rcx
0x180009cb8  jz      short loc_180009CD0
0x180009cba  call    cs:__imp_DeleteFileW
0x180009cc0  mov     rcx, [rdi+70h]
0x180009cc4  mov     rcx, [rcx+250h]; lpMem
0x180009ccb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009cd0  mov     rcx, [rdi+70h]; lpMem
0x180009cd4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009cd9  mov     ecx, 270h; unsigned __int64
0x180009cde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ce3  mov     [rdi+70h], rax
0x180009ce7  test    rax, rax
0x180009cea  jz      loc_180009DB3
0x180009cf0  mov     dword ptr [rax], 40h ; '@'
0x180009cf6  mov     ebp, 104h
0x180009cfb  mov     rdx, [rdi+70h]
0x180009cff  mov     r8d, ebp; cwchBuf
0x180009d02  mov     eax, dword ptr [rsp+68h+uBytes]
0x180009d06  mov     rcx, rbx; pszSrc
0x180009d09  mov     [rdx+44h], eax
0x180009d0c  mov     rax, [rdi+70h]
0x180009d10  mov     [rax+40h], r15d
0x180009d14  mov     rax, [rdi+70h]
0x180009d18  mov     [rax+268h], r15d
0x180009d1f  mov     rdx, [rdi+70h]
0x180009d23  add     rdx, 48h ; 'H'; pwszDst
0x180009d27  call    cs:__imp_SHAnsiToUnicode
0x180009d2d  mov     rcx, rdi; this
0x180009d30  call    ?CreateTempFileName@CPackage@@IEAAJXZ; CPackage::CreateTempFileName(void)
0x180009d35  mov     ebx, eax
0x180009d37  test    eax, eax
0x180009d39  js      short loc_180009DB8
0x180009d3b  mov     rdx, [rdi+70h]
0x180009d3f  mov     r8d, 1; bFailIfExists
0x180009d45  lea     rcx, [rdx+48h]; lpExistingFileName
0x180009d49  mov     rdx, [rdx+250h]; lpNewFileName
0x180009d50  call    cs:__imp_CopyFileW
0x180009d56  test    eax, eax
0x180009d58  jz      short loc_180009DB3
0x180009d5a  mov     rax, [rdi+70h]
0x180009d5e  mov     ecx, 7FFFFFFEh
0x180009d63  mov     rdx, [rax+250h]
0x180009d6a  add     rax, 48h ; 'H'
0x180009d6e  test    rcx, rcx
0x180009d71  jz      short loc_180009D92
0x180009d73  movzx   r8d, word ptr [rdx]
0x180009d77  test    r8w, r8w
0x180009d7b  jz      short loc_180009D92
0x180009d7d  mov     [rax], r8w
0x180009d81  add     rdx, 2
0x180009d85  add     rax, 2
0x180009d89  dec     rcx
0x180009d8c  sub     rbp, 1
0x180009d90  jnz     short loc_180009D6E
0x180009d92  test    rbp, rbp
0x180009d95  lea     rcx, [rax-2]
0x180009d99  cmovnz  rcx, rax
0x180009d9d  mov     [rcx], r15w
0x180009da1  mov     rcx, [rdi+70h]
0x180009da5  mov     rcx, [rcx+250h]; unsigned __int16 *
0x180009dac  call    ?MarkFileUnsafe@@YAJPEBG@Z; MarkFileUnsafe(ushort const *)
0x180009db1  jmp     short loc_180009DB8
0x180009db3  mov     ebx, 80004005h
0x180009db8  mov     rcx, rsi; hMem
0x180009dbb  call    cs:__imp_LocalFree
0x180009dc1  mov     eax, ebx
0x180009dc3  add     rsp, 38h
0x180009dc7  pop     r15
0x180009dc9  pop     r14
0x180009dcb  pop     rdi
0x180009dcc  pop     rsi
0x180009dcd  pop     rbp
0x180009dce  pop     rbx
0x180009dcf  retn
```
