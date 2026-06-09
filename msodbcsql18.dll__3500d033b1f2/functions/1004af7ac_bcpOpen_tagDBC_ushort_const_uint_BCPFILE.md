# bcpOpen(tagDBC *,ushort const *,uint,BCPFILE *)

- ea: `0x1004af7ac`
- end: `0x1004af969`
- name: `?bcpOpen@@YAFPEAUtagDBC@@PEBGIPEAUBCPFILE@@@Z`
- size: `445`
- prototype: `__int16 __fastcall(struct tagDBC *, LPCWSTR lpFileName, unsigned int, struct BCPFILE *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10049a784`
- `0x10049b4a0`
- `0x10049de40`

## callees

- `0x1004a0698`
- `0x1004aca40`
- `0x1004af7ac`
- `0x1005212b4`
- `0x100525dbc`
- `0x100546a7c`
- `0x100548140`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x1004af924`
- `KERNEL32!MapViewOfFile` at `0x1004af924`
- `KERNEL32!CreateFileMappingA` at `0x1004af903`
- `KERNEL32!CreateFileMappingA` at `0x1004af903`
- `KERNEL32!CreateFileW` at `0x1004af815`
- `KERNEL32!CreateFileW` at `0x1004af815`

## pseudocode

```c
__int64 __fastcall bcpOpen(struct tagDBC *a1, LPCWSTR lpFileName, int a3, struct BCPFILE *a4)
{
  unsigned __int16 v4; // di
  DWORD v9; // edx
  HANDLE FileW; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  bool v13; // zf
  void *v14; // rax
  HANDLE FileMappingA; // rax
  LPVOID v16; // rax
  int v18; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  v18 = 0;
  memset_0(a4, 0, 0x48u);
  v9 = -1073741824;
  if ( a3 == 1 )
    v9 = 0x80000000;
  FileW = CreateFileW(lpFileName, v9, 1u, 0, 3 - (unsigned int)(a3 != 1), 0x8000080u, 0);
  *(_QWORD *)a4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    *(_QWORD *)a4 = 0;
    v4 = -1;
    if ( (bidGblFlags & 2) == 0 )
      return v4;
    v11 = 6825993;
  }
  else
  {
    v12 = FILELENGTH(a4, &v18);
    v13 = v18 == 1;
    *((_QWORD *)a4 + 4) = v12;
    if ( v13 )
    {
      bcpClose(a1, a4);
      v4 = -1;
      if ( (bidGblFlags & 2) == 0 )
        return v4;
      v11 = 6836233;
    }
    else
    {
      *((_QWORD *)a4 + 5) = 0;
      *((_QWORD *)a4 + 6) = 0;
      *((_QWORD *)a4 + 7) = 0;
      if ( a3 != 2 || (v14 = SQLAllocateMemoryEx(a1, 0x10000u, 1), (*((_QWORD *)a4 + 3) = v14) != 0) )
      {
        *((_DWORD *)a4 + 16) = 0;
        if ( a3 == 1 && (unsigned __int64)(*((_QWORD *)a4 + 4) - 1LL) <= 0x1FFFFFE )
        {
          FileMappingA = CreateFileMappingA(*(HANDLE *)a4, 0, 2u, 0, 0, 0);
          *((_QWORD *)a4 + 1) = FileMappingA;
          if ( FileMappingA )
          {
            v16 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
            *((_QWORD *)a4 + 2) = v16;
            if ( v16 )
              *((_DWORD *)a4 + 16) = 1;
          }
        }
        goto LABEL_19;
      }
      bcpClose(a1, a4);
      v4 = -1;
      if ( (bidGblFlags & 2) == 0 )
        return v4;
      v11 = 6849545;
    }
  }
  bidTraceMark(0, v11);
LABEL_19:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x68C809u, v4);
  return v4;
}

```

## disassembly

```asm
0x1004af7ac  mov     [rsp+arg_0], rbx
0x1004af7b1  mov     [rsp+arg_8], rbp
0x1004af7b6  push    rsi
0x1004af7b7  push    rdi
0x1004af7b8  push    r14
0x1004af7ba  sub     rsp, 40h
0x1004af7be  xor     edi, edi
0x1004af7c0  mov     r14d, r8d
0x1004af7c3  mov     rbx, rdx
0x1004af7c6  mov     [rsp+58h+arg_10], edi
0x1004af7ca  mov     rbp, rcx
0x1004af7cd  xor     edx, edx; Val
0x1004af7cf  mov     rcx, r9; void *
0x1004af7d2  mov     rsi, r9
0x1004af7d5  lea     r8d, [rdi+48h]; Size
0x1004af7d9  call    memset_0
0x1004af7de  lea     eax, [r14-1]
0x1004af7e2  mov     [rsp+58h+hTemplateFile], rdi; hTemplateFile
0x1004af7e7  neg     eax
0x1004af7e9  mov     [rsp+58h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x1004af7f1  mov     edx, 0C0000000h
0x1004af7f6  lea     r8d, [rdi+1]; dwShareMode
0x1004af7fa  sbb     ecx, ecx
0x1004af7fc  mov     eax, 80000000h
0x1004af801  add     ecx, 3
0x1004af804  mov     [rsp+58h+dwCreationDisposition], ecx; dwCreationDisposition
0x1004af808  cmp     r14d, 1
0x1004af80c  mov     rcx, rbx; lpFileName
0x1004af80f  cmovz   edx, eax; dwDesiredAccess
0x1004af812  xor     r9d, r9d; lpSecurityAttributes
0x1004af815  call    cs:__imp_CreateFileW
0x1004af81b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1004af81f  mov     [rsi], rax
0x1004af822  cmp     rax, rbx
0x1004af825  jnz     short loc_1004AF84B
0x1004af827  mov     [rsi], rdi
0x1004af82a  movzx   edi, bx
0x1004af82d  test    byte ptr cs:_bidGblFlags, 2
0x1004af834  jz      loc_1004AF953
0x1004af83a  mov     edx, 682809h
0x1004af83f  xor     ecx, ecx
0x1004af841  call    _bidTraceMark
0x1004af846  jmp     loc_1004AF937
0x1004af84b  lea     rdx, [rsp+58h+arg_10]; int *
0x1004af850  mov     rcx, rsi; struct BCPFILE *
0x1004af853  call    ?FILELENGTH@@YA_KPEAUBCPFILE@@PEAH@Z; FILELENGTH(BCPFILE *,int *)
0x1004af858  cmp     [rsp+58h+arg_10], 1
0x1004af85d  mov     [rsi+20h], rax
0x1004af861  jnz     short loc_1004AF885
0x1004af863  mov     rdx, rsi; struct BCPFILE *
0x1004af866  mov     rcx, rbp; struct tagDBC *
0x1004af869  call    ?bcpClose@@YAFPEAUtagDBC@@PEAUBCPFILE@@@Z; bcpClose(tagDBC *,BCPFILE *)
0x1004af86e  test    byte ptr cs:_bidGblFlags, 2
0x1004af875  movzx   edi, bx
0x1004af878  jz      loc_1004AF953
0x1004af87e  mov     edx, 685009h
0x1004af883  jmp     short loc_1004AF83F
0x1004af885  mov     [rsi+28h], rdi
0x1004af889  mov     [rsi+30h], rdi
0x1004af88d  mov     [rsi+38h], rdi
0x1004af891  cmp     r14d, 2
0x1004af895  jnz     short loc_1004AF8D6
0x1004af897  mov     edx, 10000h; dwBytes
0x1004af89c  lea     r8d, [r14-1]; int
0x1004af8a0  mov     rcx, rbp; struct tagOBJBASE *
0x1004af8a3  call    ?SQLAllocateMemoryEx@@YAPEAXPEAUtagOBJBASE@@_KH@Z; SQLAllocateMemoryEx(tagOBJBASE *,unsigned __int64,int)
0x1004af8a8  mov     [rsi+18h], rax
0x1004af8ac  test    rax, rax
0x1004af8af  jnz     short loc_1004AF8D6
0x1004af8b1  mov     rdx, rsi; struct BCPFILE *
0x1004af8b4  mov     rcx, rbp; struct tagDBC *
0x1004af8b7  call    ?bcpClose@@YAFPEAUtagDBC@@PEAUBCPFILE@@@Z; bcpClose(tagDBC *,BCPFILE *)
0x1004af8bc  test    byte ptr cs:_bidGblFlags, r14b
0x1004af8c3  movzx   edi, bx
0x1004af8c6  jz      loc_1004AF953
0x1004af8cc  mov     edx, 688409h
0x1004af8d1  jmp     loc_1004AF83F
0x1004af8d6  mov     [rsi+40h], edi
0x1004af8d9  cmp     r14d, 1
0x1004af8dd  jnz     short loc_1004AF937
0x1004af8df  mov     rax, [rsi+20h]
0x1004af8e3  dec     rax
0x1004af8e6  cmp     rax, 1FFFFFEh
0x1004af8ec  ja      short loc_1004AF937
0x1004af8ee  mov     rcx, [rsi]; hFile
0x1004af8f1  lea     r8d, [r14+1]; flProtect
0x1004af8f5  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rdi; lpName
0x1004af8fa  xor     r9d, r9d; dwMaximumSizeHigh
0x1004af8fd  xor     edx, edx; lpFileMappingAttributes
0x1004af8ff  mov     [rsp+58h+dwCreationDisposition], edi; dwMaximumSizeLow
0x1004af903  call    cs:__imp_CreateFileMappingA
0x1004af909  mov     [rsi+8], rax
0x1004af90d  test    rax, rax
0x1004af910  jz      short loc_1004AF937
0x1004af912  xor     r9d, r9d; dwFileOffsetLow
0x1004af915  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; dwNumberOfBytesToMap
0x1004af91a  xor     r8d, r8d; dwFileOffsetHigh
0x1004af91d  lea     edx, [r14+3]; dwDesiredAccess
0x1004af921  mov     rcx, rax; hFileMappingObject
0x1004af924  call    cs:__imp_MapViewOfFile
0x1004af92a  mov     [rsi+10h], rax
0x1004af92e  test    rax, rax
0x1004af931  jz      short loc_1004AF937
0x1004af933  mov     [rsi+40h], r14d
0x1004af937  test    byte ptr cs:_bidGblFlags, 2
0x1004af93e  jz      short loc_1004AF953
0x1004af940  movzx   r8d, di; __int16
0x1004af944  mov     edx, 68C809h; unsigned __int64
0x1004af949  xor     ecx, ecx; unsigned __int64
0x1004af94b  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x1004af950  movzx   edi, ax
0x1004af953  mov     rbx, [rsp+58h+arg_0]
0x1004af958  movzx   eax, di
0x1004af95b  mov     rbp, [rsp+58h+arg_8]
0x1004af960  add     rsp, 40h
0x1004af964  pop     r14
0x1004af966  pop     rdi
0x1004af967  pop     rsi
0x1004af968  retn
```
