# GetNextLine(void *,uchar * &,BUFFER *,BUFFER *,ulong &,uchar * &)

- ea: `0x18001e290`
- end: `0x18001e4b9`
- name: `?GetNextLine@@YAJPEAXAEAPEAEPEAVBUFFER@@2AEAK1@Z`
- size: `553`
- prototype: `int(void *, unsigned __int8 **, struct BUFFER *, struct BUFFER *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180021330`

## callees

- `0x18001dedc`
- `0x18001e290`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18001e3f3`
- `KERNEL32!ReadFile` at `0x18001e3f3`
- `KERNEL32!GetLastError` at `0x18001e3fd`
- `KERNEL32!GetLastError` at `0x18001e3fd`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001e3c6`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001e3c6`
- `IisRTL!PuDbgPrint` at `0x18001e308`
- `IisRTL!PuDbgPrint` at `0x18001e35f`
- `IisRTL!PuDbgPrint` at `0x18001e3bd`
- `IisRTL!PuDbgPrint` at `0x18001e463`
- `IisRTL!PuDbgPrint` at `0x18001e308`
- `IisRTL!PuDbgPrint` at `0x18001e35f`
- `IisRTL!PuDbgPrint` at `0x18001e3bd`
- `IisRTL!PuDbgPrint` at `0x18001e463`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e3d1`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e40e`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e41d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e3d1`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e40e`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e41d`

## string_xrefs

- `0x18001e2fc`: `Entering GetNextLine, pbrNextPtr = %p, pbrEndReadData = %p\n`
- `0x18001e353`: `GetNextLine calling GetLineFromBuffer, pbrNextPtr = %p, pbrEndReadData = %p\n`
- `0x18001e39d`: `GetNextLine calling ReadFile\n`
- `0x18001e457`: `GetNextLine after call to ReadFile, pbrNextPter = %p, pbrEndReadData = %p\n`

## pseudocode

```c
__int64 __fastcall GetNextLine(
        void *a1,
        unsigned __int8 **a2,
        struct BUFFER *a3,
        struct BUFFER *a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  signed int LastError; // edi
  int v7; // esi
  unsigned int LineFromBuffer; // ebp
  DWORD Size; // ebx
  void *Ptr; // rax
  __int64 v14; // rbx
  unsigned __int8 *v15; // rax
  bool v16; // zf
  unsigned int v17; // ecx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-54h] BYREF
  int v21[20]; // [rsp+48h] [rbp-50h] BYREF

  LastError = 0;
  v7 = 0;
  NumberOfBytesRead = 0;
  v20 = 0;
  LineFromBuffer = 38;
  v21[0] = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      1688,
      "GetNextLine",
      "Entering GetNextLine, pbrNextPtr = %p, pbrEndReadData = %p\n",
      *a6,
      *a2);
  do
  {
    if ( LineFromBuffer != 38 )
      break;
    if ( v7 )
      goto LABEL_18;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        1701,
        "GetNextLine",
        "GetNextLine calling GetLineFromBuffer, pbrNextPtr = %p, pbrEndReadData = %p\n",
        *a6,
        *a2);
    LineFromBuffer = GetLineFromBuffer(a6, a2, a4, &v20, v21);
    if ( LineFromBuffer == 38 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          1711,
          "GetNextLine",
          "GetNextLine calling ReadFile\n");
      Size = BUFFER::QuerySize(a3);
      Ptr = BUFFER::QueryPtr(a3);
      if ( ReadFile(a1, Ptr, Size, &NumberOfBytesRead, 0) )
      {
        v14 = NumberOfBytesRead;
        *a2 = (unsigned __int8 *)BUFFER::QueryPtr(a3) + v14;
        v15 = (unsigned __int8 *)BUFFER::QueryPtr(a3);
        v16 = (g_dwDebugFlags & 3) == 0;
        *a6 = v15;
        if ( !v16 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            1727,
            "GetNextLine",
            "GetNextLine after call to ReadFile, pbrNextPter = %p, pbrEndReadData = %p\n",
            v15,
            *a2);
        if ( !NumberOfBytesRead )
          v7 = 1;
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  while ( !LastError );
  if ( v7 )
  {
LABEL_18:
    v17 = 0;
    goto LABEL_21;
  }
  v17 = v20;
  if ( LineFromBuffer )
    LastError = LineFromBuffer;
LABEL_21:
  *a5 = v17;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001e290  mov     rax, rsp
0x18001e293  mov     [rax+8], rcx
0x18001e297  push    rbx
0x18001e298  push    rbp
0x18001e299  push    rsi
0x18001e29a  push    rdi
0x18001e29b  push    r12
0x18001e29d  push    r13
0x18001e29f  push    r14
0x18001e2a1  push    r15
0x18001e2a3  sub     rsp, 58h
0x18001e2a7  mov     r15, [rsp+98h+arg_28]
0x18001e2af  xor     edi, edi
0x18001e2b1  xor     esi, esi
0x18001e2b3  mov     [rax-58h], edi
0x18001e2b6  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e2bd  mov     r13, r9
0x18001e2c0  mov     r12, r8
0x18001e2c3  mov     [rax-54h], edi
0x18001e2c6  lea     ebp, [rdi+26h]
0x18001e2c9  mov     [rax-50h], edi
0x18001e2cc  mov     r14, rdx
0x18001e2cf  jz      short loc_18001E30E
0x18001e2d1  mov     rax, [rdx]
0x18001e2d4  lea     r9, aGetnextline; "GetNextLine"
0x18001e2db  mov     rcx, cs:g_pDebug
0x18001e2e2  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001e2e9  mov     [rsp+98h+var_68], rax
0x18001e2ee  mov     r8d, 698h
0x18001e2f4  mov     rax, [r15]
0x18001e2f7  mov     [rsp+98h+var_70], rax
0x18001e2fc  lea     rax, aEnteringGetnex; "Entering GetNextLine, pbrNextPtr = %p, "...
0x18001e303  mov     [rsp+98h+lpOverlapped], rax
0x18001e308  call    cs:__imp_PuDbgPrint
0x18001e30e  cmp     ebp, 26h ; '&'
0x18001e311  jnz     loc_18001E47E
0x18001e317  test    esi, esi
0x18001e319  jnz     loc_18001E482
0x18001e31f  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e326  jz      short loc_18001E365
0x18001e328  mov     rax, [r14]
0x18001e32b  lea     r9, aGetnextline; "GetNextLine"
0x18001e332  mov     rcx, cs:g_pDebug
0x18001e339  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001e340  mov     [rsp+98h+var_68], rax
0x18001e345  mov     r8d, 6A5h
0x18001e34b  mov     rax, [r15]
0x18001e34e  mov     [rsp+98h+var_70], rax
0x18001e353  lea     rax, aGetnextlineCal_0; "GetNextLine calling GetLineFromBuffer, "...
0x18001e35a  mov     [rsp+98h+lpOverlapped], rax
0x18001e35f  call    cs:__imp_PuDbgPrint
0x18001e365  lea     rax, [rsp+98h+var_50]
0x18001e36a  mov     r8, r13; struct BUFFER *
0x18001e36d  lea     r9, [rsp+98h+var_54]; unsigned int *
0x18001e372  mov     [rsp+98h+lpOverlapped], rax; int *
0x18001e377  mov     rdx, r14; unsigned __int8 **
0x18001e37a  mov     rcx, r15; unsigned __int8 **
0x18001e37d  call    ?GetLineFromBuffer@@YAKAEAPEAE0PEAVBUFFER@@AEAKAEAH@Z; GetLineFromBuffer(uchar * &,uchar * &,BUFFER *,ulong &,int &)
0x18001e382  mov     ebp, eax
0x18001e384  cmp     eax, 26h ; '&'
0x18001e387  jnz     loc_18001E476
0x18001e38d  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e394  jz      short loc_18001E3C3
0x18001e396  mov     rcx, cs:g_pDebug
0x18001e39d  lea     rax, aGetnextlineCal; "GetNextLine calling ReadFile\n"
0x18001e3a4  lea     r9, aGetnextline; "GetNextLine"
0x18001e3ab  mov     [rsp+98h+lpOverlapped], rax
0x18001e3b0  mov     r8d, 6AFh
0x18001e3b6  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001e3bd  call    cs:__imp_PuDbgPrint
0x18001e3c3  mov     rcx, r12
0x18001e3c6  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18001e3cc  mov     rcx, r12
0x18001e3cf  mov     ebx, eax
0x18001e3d1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001e3d7  mov     rcx, [rsp+98h+hFile]; hFile
0x18001e3df  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001e3e4  mov     rdx, rax; lpBuffer
0x18001e3e7  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x18001e3f0  mov     r8d, ebx; nNumberOfBytesToRead
0x18001e3f3  call    cs:__imp_ReadFile
0x18001e3f9  test    eax, eax
0x18001e3fb  jnz     short loc_18001E407
0x18001e3fd  call    cs:__imp_GetLastError
0x18001e403  mov     edi, eax
0x18001e405  jmp     short loc_18001E476
0x18001e407  mov     ebx, [rsp+98h+NumberOfBytesRead]
0x18001e40b  mov     rcx, r12
0x18001e40e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001e414  add     rax, rbx
0x18001e417  mov     rcx, r12
0x18001e41a  mov     [r14], rax
0x18001e41d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001e423  test    byte ptr cs:g_dwDebugFlags, 3
0x18001e42a  mov     [r15], rax
0x18001e42d  jz      short loc_18001E469
0x18001e42f  mov     rcx, [r14]
0x18001e432  lea     r9, aGetnextline; "GetNextLine"
0x18001e439  mov     [rsp+98h+var_68], rcx
0x18001e43e  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001e445  mov     rcx, cs:g_pDebug
0x18001e44c  mov     r8d, 6BFh
0x18001e452  mov     [rsp+98h+var_70], rax
0x18001e457  lea     rax, aGetnextlineAft; "GetNextLine after call to ReadFile, pbr"...
0x18001e45e  mov     [rsp+98h+lpOverlapped], rax
0x18001e463  call    cs:__imp_PuDbgPrint
0x18001e469  cmp     [rsp+98h+NumberOfBytesRead], 0
0x18001e46e  mov     eax, 1
0x18001e473  cmovz   esi, eax
0x18001e476  test    edi, edi
0x18001e478  jz      loc_18001E30E
0x18001e47e  test    esi, esi
0x18001e480  jz      short loc_18001E486
0x18001e482  xor     ecx, ecx
0x18001e484  jmp     short loc_18001E48F
0x18001e486  mov     ecx, [rsp+98h+var_54]
0x18001e48a  test    ebp, ebp
0x18001e48c  cmovnz  edi, ebp
0x18001e48f  mov     rax, [rsp+98h+arg_20]
0x18001e497  mov     [rax], ecx
0x18001e499  test    edi, edi
0x18001e49b  jle     short loc_18001E4A6
0x18001e49d  movzx   edi, di
0x18001e4a0  or      edi, 80070000h
0x18001e4a6  mov     eax, edi
0x18001e4a8  add     rsp, 58h
0x18001e4ac  pop     r15
0x18001e4ae  pop     r14
0x18001e4b0  pop     r13
0x18001e4b2  pop     r12
0x18001e4b4  pop     rdi
0x18001e4b5  pop     rsi
0x18001e4b6  pop     rbp
0x18001e4b7  pop     rbx
0x18001e4b8  retn
```
