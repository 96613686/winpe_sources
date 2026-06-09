# Dfdll::CFile::ReadUnicodeFormattedTextFile(ushort const *,Dfdll::CString &,uint)

- ea: `0x18001179c`
- end: `0x180011a53`
- name: `?ReadUnicodeFormattedTextFile@CFile@Dfdll@@SAJPEBGAEAVCString@2@I@Z`
- size: `695`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Dfdll::CString *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000c954`

## callees

- `0x180001fc8`
- `0x180011248`
- `0x1800116ac`
- `0x18001179c`
- `0x180012b30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001182e`
- `KERNEL32!GetLastError` at `0x1800118ed`
- `KERNEL32!GetLastError` at `0x18001182e`
- `KERNEL32!GetLastError` at `0x1800118ed`
- `KERNEL32!CloseHandle` at `0x1800117fa`
- `KERNEL32!CloseHandle` at `0x18001185b`
- `KERNEL32!CloseHandle` at `0x18001187e`
- `KERNEL32!CloseHandle` at `0x18001193c`
- `KERNEL32!CloseHandle` at `0x180011995`
- `KERNEL32!CloseHandle` at `0x1800119cc`
- `KERNEL32!CloseHandle` at `0x1800119f9`
- `KERNEL32!CloseHandle` at `0x180011a30`
- `KERNEL32!CloseHandle` at `0x1800117fa`
- `KERNEL32!CloseHandle` at `0x18001185b`
- `KERNEL32!CloseHandle` at `0x18001187e`
- `KERNEL32!CloseHandle` at `0x18001193c`
- `KERNEL32!CloseHandle` at `0x180011995`
- `KERNEL32!CloseHandle` at `0x1800119cc`
- `KERNEL32!CloseHandle` at `0x1800119f9`
- `KERNEL32!CloseHandle` at `0x180011a30`
- `KERNEL32!GetFileSize` at `0x180011826`
- `KERNEL32!GetFileSize` at `0x180011826`
- `KERNEL32!ReadFile` at `0x1800118e3`
- `KERNEL32!ReadFile` at `0x1800118e3`

## pseudocode

```c
__int64 __fastcall Dfdll::CFile::ReadUnicodeFormattedTextFile(
        const unsigned __int16 *a1,
        struct Dfdll::CString *a2,
        unsigned int a3)
{
  unsigned __int64 v3; // rsi
  const struct std::nothrow_t *v5; // rdx
  signed int v6; // ebx
  HANDLE v7; // rdi
  __int64 FileSize; // rbx
  signed int LastError; // eax
  void *v10; // rcx
  signed int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  DWORD FileSizeHigh; // [rsp+30h] [rbp-30h] BYREF
  void **v15; // [rsp+38h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-20h]
  void **v17; // [rsp+48h] [rbp-18h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-10h]
  int v19; // [rsp+58h] [rbp-8h]
  DWORD nNumberOfBytesToRead; // [rsp+98h] [rbp+38h] BYREF

  v3 = a3;
  v15 = &Dfdll::CFile::`vftable';
  hObject = (HANDLE)-1LL;
  v6 = Dfdll::CFile::Open(&v15, a1, 3);
  if ( v6 < 0 )
  {
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    return (unsigned int)v6;
  }
  v7 = hObject;
  if ( (_DWORD)v3 )
  {
    if ( hObject == (HANDLE)-1LL )
    {
      v6 = -2147024883;
LABEL_12:
      if ( v7 != (HANDLE)-1LL )
        CloseHandle(v7);
      return (unsigned int)v6;
    }
    FileSizeHigh = 0;
    FileSize = GetFileSize(hObject, &FileSizeHigh);
    LastError = GetLastError();
    if ( (_DWORD)FileSize == -1 && LastError )
    {
      v6 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v6 = LastError;
      goto LABEL_12;
    }
    if ( (FileSize | (16 * (unsigned __int64)FileSizeHigh)) > v3 )
    {
      v6 = -2147016584;
      CloseHandle(v7);
      return (unsigned int)v6;
    }
  }
  v10 = 0;
  lpBuffer = 0;
  v19 = 0;
  v17 = &Dfdll::CBuffer<unsigned char>::`vftable';
  nNumberOfBytesToRead = 2;
  if ( v7 == (HANDLE)-1LL )
  {
    v6 = -2147024883;
LABEL_39:
    v17 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( v10 )
      operator delete(v10, v5);
    lpBuffer = 0;
    v19 = 0;
    v17 = &Dfdll::CObject::`vftable';
    if ( v7 != (HANDLE)-1LL )
      CloseHandle(v7);
    return (unsigned int)v6;
  }
  v6 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v17, 2u);
  if ( v6 < 0 )
    goto LABEL_38;
  if ( !ReadFile(v7, lpBuffer, nNumberOfBytesToRead, &nNumberOfBytesToRead, 0) )
  {
    v11 = GetLastError();
    v6 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v6 = v11;
    if ( v6 < 0 )
    {
LABEL_38:
      v10 = lpBuffer;
      goto LABEL_39;
    }
  }
  if ( nNumberOfBytesToRead >= 2 )
  {
    if ( *(_BYTE *)lpBuffer != 0xFF || *((_BYTE *)lpBuffer + 1) != 0xFE )
    {
      v6 = 11;
      v17 = &Dfdll::CBuffer<unsigned char>::`vftable';
      operator delete(lpBuffer, v5);
      lpBuffer = 0;
      v19 = 0;
      v17 = &Dfdll::CObject::`vftable';
      CloseHandle(v7);
      return (unsigned int)v6;
    }
    v6 = Dfdll::CFile::ReadToEnd((Dfdll::CFile *)&v15, a2);
    if ( v6 >= 0 )
    {
      v6 = 0;
      v17 = &Dfdll::CBuffer<unsigned char>::`vftable';
      if ( lpBuffer )
        operator delete(lpBuffer, v12);
    }
    else
    {
      v17 = &Dfdll::CBuffer<unsigned char>::`vftable';
      if ( lpBuffer )
        operator delete(lpBuffer, v12);
    }
  }
  else
  {
    v6 = -2147024885;
    v17 = &Dfdll::CBuffer<unsigned char>::`vftable';
    if ( lpBuffer )
      operator delete(lpBuffer, v5);
  }
  lpBuffer = 0;
  v19 = 0;
  v17 = &Dfdll::CObject::`vftable';
  CloseHandle(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001179c  mov     r11, rsp
0x18001179f  mov     [r11+8], rbx
0x1800117a3  mov     [r11+10h], rsi
0x1800117a7  mov     [r11+18h], rdi
0x1800117ab  push    rbp
0x1800117ac  push    r14
0x1800117ae  push    r15
0x1800117b0  mov     rbp, rsp
0x1800117b3  sub     rsp, 60h
0x1800117b7  mov     esi, r8d
0x1800117ba  mov     r14, rdx
0x1800117bd  lea     rax, ??_7CFile@Dfdll@@6B@; const Dfdll::CFile::`vftable'
0x1800117c4  mov     [rbp+var_28], rax
0x1800117c8  or      [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x1800117cd  mov     r9d, 1
0x1800117d3  mov     [r11-58h], r9d
0x1800117d7  lea     r8d, [r9+2]
0x1800117db  mov     rdx, rcx
0x1800117de  lea     rcx, [rbp+var_28]
0x1800117e2  call    ?Open@CFile@Dfdll@@QEAAJPEBGW4FileOpenMode@12@W4FileShareMode@12@W4FileIOPermission@12@@Z; Dfdll::CFile::Open(ushort const *,Dfdll::CFile::FileOpenMode,Dfdll::CFile::FileShareMode,Dfdll::CFile::FileIOPermission)
0x1800117e7  mov     ebx, eax
0x1800117e9  xor     r15d, r15d
0x1800117ec  test    eax, eax
0x1800117ee  jns     short loc_180011806
0x1800117f0  mov     rcx, [rbp+hObject]; hObject
0x1800117f4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800117f8  jz      short loc_180011801
0x1800117fa  call    cs:__imp_CloseHandle
0x180011800  nop
0x180011801  jmp     loc_180011A37
0x180011806  mov     rdi, [rbp+hObject]
0x18001180a  test    esi, esi
0x18001180c  jz      short loc_18001188A
0x18001180e  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180011812  jnz     short loc_18001181B
0x180011814  mov     ebx, 8007000Dh
0x180011819  jmp     short loc_180011852
0x18001181b  mov     [rbp+FileSizeHigh], r15d
0x18001181f  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x180011823  mov     rcx, rdi; hFile
0x180011826  call    cs:__imp_GetFileSize
0x18001182c  mov     ebx, eax
0x18001182e  call    cs:__imp_GetLastError
0x180011834  cmp     ebx, 0FFFFFFFFh
0x180011837  jnz     short loc_180011867
0x180011839  test    eax, eax
0x18001183b  jz      short loc_180011867
0x18001183d  movzx   ebx, ax
0x180011840  or      ebx, 80070000h
0x180011846  test    eax, eax
0x180011848  cmovle  ebx, eax
0x18001184b  mov     rcx, r15
0x18001184e  test    ebx, ebx
0x180011850  jns     short loc_180011871
0x180011852  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180011856  jz      short loc_180011862
0x180011858  mov     rcx, rdi; hObject
0x18001185b  call    cs:__imp_CloseHandle
0x180011861  nop
0x180011862  jmp     loc_180011A37
0x180011867  mov     ecx, [rbp+FileSizeHigh]
0x18001186a  shl     rcx, 4
0x18001186e  or      rcx, rbx
0x180011871  cmp     rcx, rsi
0x180011874  jbe     short loc_18001188A
0x180011876  mov     ebx, 80072078h
0x18001187b  mov     rcx, rdi; hObject
0x18001187e  call    cs:__imp_CloseHandle
0x180011884  nop
0x180011885  jmp     loc_180011A37
0x18001188a  mov     rcx, r15
0x18001188d  mov     [rbp+lpBuffer], rcx
0x180011891  mov     [rbp+var_8], r15d
0x180011895  lea     rsi, ??_7?$CBuffer@E@Dfdll@@6B@; const Dfdll::CBuffer<uchar>::`vftable'
0x18001189c  mov     [rbp+var_18], rsi
0x1800118a0  mov     [rbp+nNumberOfBytesToRead], 2
0x1800118a7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800118ab  jnz     short loc_1800118B7
0x1800118ad  mov     ebx, 8007000Dh
0x1800118b2  jmp     loc_180011A06
0x1800118b7  mov     edx, 2; unsigned int
0x1800118bc  lea     rcx, [rbp+var_18]; this
0x1800118c0  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x1800118c5  mov     ebx, eax
0x1800118c7  test    eax, eax
0x1800118c9  js      loc_180011A02
0x1800118cf  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x1800118d4  lea     r9, [rbp+nNumberOfBytesToRead]; lpNumberOfBytesRead
0x1800118d8  mov     r8d, [rbp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x1800118dc  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x1800118e0  mov     rcx, rdi; hFile
0x1800118e3  call    cs:__imp_ReadFile
0x1800118e9  test    eax, eax
0x1800118eb  jnz     short loc_180011909
0x1800118ed  call    cs:__imp_GetLastError
0x1800118f3  movzx   ebx, ax
0x1800118f6  or      ebx, 80070000h
0x1800118fc  test    eax, eax
0x1800118fe  cmovle  ebx, eax
0x180011901  test    ebx, ebx
0x180011903  js      loc_180011A02
0x180011909  cmp     [rbp+nNumberOfBytesToRead], 2
0x18001190d  jnb     short loc_180011948
0x18001190f  mov     ebx, 8007000Bh
0x180011914  mov     [rbp+var_18], rsi
0x180011918  mov     rcx, [rbp+lpBuffer]; void *
0x18001191c  test    rcx, rcx
0x18001191f  jz      short loc_180011926
0x180011921  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011926  mov     [rbp+lpBuffer], r15
0x18001192a  mov     [rbp+var_8], r15d
0x18001192e  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180011935  mov     [rbp+var_18], rax
0x180011939  mov     rcx, rdi; hObject
0x18001193c  call    cs:__imp_CloseHandle
0x180011942  nop
0x180011943  jmp     loc_180011A37
0x180011948  mov     rcx, [rbp+lpBuffer]; void *
0x18001194c  cmp     byte ptr [rcx], 0FFh
0x18001194f  jnz     loc_1800119D5
0x180011955  cmp     byte ptr [rcx+1], 0FEh
0x180011959  jnz     short loc_1800119D5
0x18001195b  mov     rdx, r14; struct Dfdll::CString *
0x18001195e  lea     rcx, [rbp+var_28]; this
0x180011962  call    ?ReadToEnd@CFile@Dfdll@@QEAAJAEAVCString@2@@Z; Dfdll::CFile::ReadToEnd(Dfdll::CString &)
0x180011967  mov     ebx, eax
0x180011969  test    eax, eax
0x18001196b  jns     short loc_1800119A1
0x18001196d  mov     [rbp+var_18], rsi
0x180011971  mov     rcx, [rbp+lpBuffer]; void *
0x180011975  test    rcx, rcx
0x180011978  jz      short loc_18001197F
0x18001197a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001197f  mov     [rbp+lpBuffer], r15
0x180011983  mov     [rbp+var_8], r15d
0x180011987  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18001198e  mov     [rbp+var_18], rax
0x180011992  mov     rcx, rdi; hObject
0x180011995  call    cs:__imp_CloseHandle
0x18001199b  nop
0x18001199c  jmp     loc_180011A37
0x1800119a1  mov     ebx, r15d
0x1800119a4  mov     [rbp+var_18], rsi
0x1800119a8  mov     rcx, [rbp+lpBuffer]; void *
0x1800119ac  test    rcx, rcx
0x1800119af  jz      short loc_1800119B6
0x1800119b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800119b6  mov     [rbp+lpBuffer], r15
0x1800119ba  mov     [rbp+var_8], r15d
0x1800119be  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800119c5  mov     [rbp+var_18], rax
0x1800119c9  mov     rcx, rdi; hObject
0x1800119cc  call    cs:__imp_CloseHandle
0x1800119d2  nop
0x1800119d3  jmp     short loc_180011A37
0x1800119d5  mov     ebx, 0Bh
0x1800119da  mov     [rbp+var_18], rsi
0x1800119de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800119e3  mov     [rbp+lpBuffer], r15
0x1800119e7  mov     [rbp+var_8], r15d
0x1800119eb  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800119f2  mov     [rbp+var_18], rax
0x1800119f6  mov     rcx, rdi; hObject
0x1800119f9  call    cs:__imp_CloseHandle
0x1800119ff  nop
0x180011a00  jmp     short loc_180011A37
0x180011a02  mov     rcx, [rbp+lpBuffer]; void *
0x180011a06  mov     [rbp+var_18], rsi
0x180011a0a  test    rcx, rcx
0x180011a0d  jz      short loc_180011A14
0x180011a0f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011a14  mov     [rbp+lpBuffer], r15
0x180011a18  mov     [rbp+var_8], r15d
0x180011a1c  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180011a23  mov     [rbp+var_18], rax
0x180011a27  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180011a2b  jz      short loc_180011A37
0x180011a2d  mov     rcx, rdi; hObject
0x180011a30  call    cs:__imp_CloseHandle
0x180011a36  nop
0x180011a37  mov     eax, ebx
0x180011a39  lea     r11, [rsp+60h+var_s0]
0x180011a3e  mov     rbx, [r11+20h]
0x180011a42  mov     rsi, [r11+28h]
0x180011a46  mov     rdi, [r11+30h]
0x180011a4a  mov     rsp, r11
0x180011a4d  pop     r15
0x180011a4f  pop     r14
0x180011a51  pop     rbp
0x180011a52  retn
```
