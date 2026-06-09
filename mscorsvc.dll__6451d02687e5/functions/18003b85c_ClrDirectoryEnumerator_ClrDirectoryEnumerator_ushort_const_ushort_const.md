# ClrDirectoryEnumerator::ClrDirectoryEnumerator(ushort const *,ushort const *)

- ea: `0x18003b85c`
- end: `0x18003bc2d`
- name: `??0ClrDirectoryEnumerator@@QEAA@PEBG0@Z`
- size: `977`
- prototype: `ClrDirectoryEnumerator *__fastcall(LPWIN32_FIND_DATAW lpFindFileData, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18002f454`

## callees

- `0x180001de0`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180032ef4`
- `0x18003303c`
- `0x1800351e8`
- `0x18003b85c`
- `0x18003dc30`
- `0x18003f263`

## import_xrefs

- `KERNEL32!FindClose` at `0x18003bb77`
- `KERNEL32!FindClose` at `0x18003bb77`
- `KERNEL32!FindFirstFileW` at `0x18003bb65`
- `KERNEL32!FindFirstFileW` at `0x18003bb65`
- `KERNEL32!GetLastError` at `0x18003bc12`
- `KERNEL32!GetLastError` at `0x18003bc12`
- `KERNEL32!HeapFree` at `0x18003ba9d`
- `KERNEL32!HeapFree` at `0x18003bbde`
- `KERNEL32!HeapFree` at `0x18003ba9d`
- `KERNEL32!HeapFree` at `0x18003bbde`
- `KERNEL32!GetProcessHeap` at `0x18003ba88`
- `KERNEL32!GetProcessHeap` at `0x18003bbc9`
- `KERNEL32!GetProcessHeap` at `0x18003ba88`
- `KERNEL32!GetProcessHeap` at `0x18003bbc9`

## pseudocode

```c
ClrDirectoryEnumerator *__fastcall ClrDirectoryEnumerator::ClrDirectoryEnumerator(
        LPWIN32_FIND_DATAW lpFindFileData,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  LPWIN32_FIND_DATAW v5; // rsi
  int v6; // ebx
  size_t v7; // rdi
  unsigned int v8; // r15d
  int v9; // r14d
  char v10; // cl
  unsigned int v11; // eax
  __int64 v12; // rdx
  char v13; // al
  void *v14; // r14
  HANDLE ProcessHeap; // rax
  void *v16; // rdi
  int v17; // ecx
  size_t v18; // r8
  HANDLE FirstFileW; // rbx
  void *v20; // rbx
  HANDLE v21; // rax
  _DWORD v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v24; // [rsp+28h] [rbp-D8h]
  void *v25; // [rsp+30h] [rbp-D0h]
  size_t Size; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+40h] [rbp-C0h]
  void *Src; // [rsp+48h] [rbp-B8h]
  _DWORD v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  void *v31; // [rsp+60h] [rbp-A0h]
  LPWIN32_FIND_DATAW v32; // [rsp+70h] [rbp-90h]
  LPWIN32_FIND_DATAW v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v35; // [rsp+94h] [rbp-6Ch]
  LPVOID lpMem; // [rsp+A0h] [rbp-60h]
  __int16 v37; // [rsp+A8h] [rbp-58h] BYREF

  v32 = lpFindFileData;
  v5 = lpFindFileData + 1;
  v33 = lpFindFileData + 1;
  *(_QWORD *)&lpFindFileData[1].dwFileAttributes = -1;
  lpFindFileData[1].ftCreationTime.dwHighDateTime = 0;
  v35 = 512;
  lpMem = &v37;
  v34 = 2;
  v37 = 0;
  v23[0] = 4;
  v23[1] = 4;
  v25 = (void *)L"\\";
  v24 = 276;
  v29[0] = 2;
  v29[1] = 2;
  v30 = 16;
  v31 = (void *)&SString::s_EmptyBuffer;
  SString::Set((SString *)v29, L"*");
  Size = 0x200000002LL;
  v27 = 16;
  Src = (void *)&SString::s_EmptyBuffer;
  SString::Set((SString *)&Size, a2);
  v6 = v27;
  if ( (v27 & 2) != 0 && ((v27 & 7) != 7 || SString::s_IsANSIMultibyte) )
  {
    if ( !(unsigned int)SString::ScanASCII((SString *)&Size) )
      SString::ConvertToUnicode((SString *)&Size);
    v6 = v27;
  }
  v7 = (unsigned int)Size;
  v8 = (unsigned int)Size >> ((v6 & 1) == 0);
  v9 = v23[0] >> ((v24 & 1) == 0);
  v10 = v30;
  if ( (v30 & 2) != 0 && ((v30 & 7) != 7 || SString::s_IsANSIMultibyte) )
  {
    if ( !(unsigned int)SString::ScanASCII((SString *)v29) )
      SString::ConvertToUnicode((SString *)v29);
    v10 = v30;
  }
  v11 = 2 * (v8 + v9 + (v29[0] >> ((v10 & 1) == 0))) - 6;
  v12 = (unsigned int)v35;
  if ( v11 > (unsigned int)v35 )
  {
    SBuffer::ReallocateBuffer(&v34, v11, 1);
    v12 = (unsigned int)v35;
  }
  if ( (v6 & 0x10) != 0 )
  {
    v13 = BYTE4(v35);
    if ( (v35 & 0x1000000000LL) != 0 || (unsigned int)v12 < (unsigned int)v7 )
    {
      if ( (v35 & 0x800000000LL) != 0 )
      {
        v14 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v14);
        }
      }
      v34 = v7;
      v35 = __PAIR64__(v6, HIDWORD(Size));
      v16 = Src;
      lpMem = Src;
      v17 = v6;
      goto LABEL_30;
    }
  }
  else
  {
    if ( (unsigned int)v7 > (unsigned int)v12 )
    {
      SBuffer::ReallocateBuffer(&v34, (unsigned int)v7, 0);
      v12 = (unsigned int)v35;
    }
    v13 = BYTE4(v35);
  }
  v34 = v7;
  if ( (v13 & 0x10) != 0 )
    SBuffer::ReallocateBuffer(&v34, v12, 1);
  v18 = v7;
  v16 = Src;
  memcpy_0(lpMem, Src, v18);
  v17 = HIDWORD(v35);
LABEL_30:
  HIDWORD(v35) = v6 & 7 | v17 & 0xFFFFFEF8;
  SString::Append((SString *)&v34, (const struct SString *)v23);
  SString::Append((SString *)&v34, (const struct SString *)v29);
  if ( (v6 & 8) != 0 )
    operator delete(v16);
  if ( (v30 & 8) != 0 )
    operator delete(v31);
  SString::ConvertToUnicode((SString *)&v34);
  FirstFileW = FindFirstFileW((LPCWSTR)lpMem, lpFindFileData);
  if ( v5->ftCreationTime.dwHighDateTime )
  {
    FindClose(*(HANDLE *)&v5->dwFileAttributes);
    v5->ftCreationTime.dwHighDateTime = 0;
  }
  *(_QWORD *)&v5->dwFileAttributes = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( ((GetLastError() - 2) & 0xFFFFFFEF) != 0 )
      ThrowLastError();
  }
  else
  {
    v5->ftCreationTime.dwHighDateTime = 1;
  }
  lpFindFileData[1].ftLastAccessTime.dwHighDateTime = 0;
  if ( (v24 & 8) != 0 )
    operator delete(v25);
  if ( (v35 & 0x800000000LL) != 0 )
  {
    v20 = lpMem;
    if ( lpMem )
    {
      v21 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v21 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v21;
      }
      HeapFree(v21, 0, v20);
    }
  }
  return (ClrDirectoryEnumerator *)lpFindFileData;
}

```

## disassembly

```asm
0x18003b85c  mov     [rsp-8+arg_10], rbx
0x18003b861  push    rbp
0x18003b862  push    rsi
0x18003b863  push    rdi
0x18003b864  push    r12
0x18003b866  push    r13
0x18003b868  push    r14
0x18003b86a  push    r15
0x18003b86c  lea     rbp, [rsp-1C0h]
0x18003b874  sub     rsp, 2C0h
0x18003b87b  mov     rax, cs:__security_cookie
0x18003b882  xor     rax, rsp
0x18003b885  mov     [rbp+1F0h+var_40], rax
0x18003b88c  mov     rbx, rdx
0x18003b88f  mov     r13, rcx
0x18003b892  mov     [rsp+2F0h+var_280], rcx
0x18003b897  lea     rsi, [rcx+250h]
0x18003b89e  mov     [rbp+1F0h+var_270], rsi
0x18003b8a2  or      qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18003b8a6  xor     r12d, r12d
0x18003b8a9  mov     [rsi+8], r12d
0x18003b8ad  mov     [rbp+1F0h+var_260], r12
0x18003b8b1  mov     [rbp+1F0h+var_260+4], 200h
0x18003b8b9  mov     [rbp+1F0h+lpMem], r12
0x18003b8bd  lea     rax, [rbp+1F0h+var_248]
0x18003b8c1  mov     [rbp+1F0h+lpMem], rax
0x18003b8c5  lea     r14d, [r12+2]
0x18003b8ca  mov     dword ptr [rbp+1F0h+var_260], r14d
0x18003b8ce  mov     rax, [rbp+1F0h+lpMem]
0x18003b8d2  mov     [rax], r12w
0x18003b8d6  lea     edx, [r12+4]
0x18003b8db  mov     [rsp+2F0h+var_2D0], edx
0x18003b8df  mov     [rsp+2F0h+var_2CC], edx
0x18003b8e3  lea     r15d, [r12+10h]
0x18003b8e8  mov     [rsp+2F0h+var_2C8], r15d
0x18003b8ed  lea     rax, asc_180049544; "\\"
0x18003b8f4  mov     [rsp+2F0h+var_2C0], rax
0x18003b8f9  mov     ecx, [rsp+2F0h+var_2C8]
0x18003b8fd  and     ecx, 0FFFFFFF8h
0x18003b900  mov     [rsp+2F0h+var_2C8], ecx
0x18003b904  mov     eax, ecx
0x18003b906  or      eax, edx
0x18003b908  mov     [rsp+2F0h+var_2C8], eax
0x18003b90c  or      ecx, 104h
0x18003b912  mov     [rsp+2F0h+var_2C8], ecx
0x18003b916  mov     [rsp+2F0h+var_2A0], r14d
0x18003b91b  mov     [rsp+2F0h+var_29C], r14d
0x18003b920  mov     [rsp+2F0h+var_298], r15d
0x18003b925  lea     rdi, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18003b92c  mov     [rsp+2F0h+var_290], rdi
0x18003b931  lea     rdx, asc_180052DBC; "*"
0x18003b938  lea     rcx, [rsp+2F0h+var_2A0]; this
0x18003b93d  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18003b942  nop
0x18003b943  mov     dword ptr [rsp+2F0h+Size], r14d
0x18003b948  mov     dword ptr [rsp+2F0h+Size+4], r14d
0x18003b94d  mov     [rsp+2F0h+var_2B0], r15d
0x18003b952  mov     [rsp+2F0h+Src], rdi
0x18003b957  mov     rdx, rbx; unsigned __int16 *
0x18003b95a  lea     rcx, [rsp+2F0h+Size]; this
0x18003b95f  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18003b964  nop
0x18003b965  mov     ebx, [rsp+2F0h+var_2B0]
0x18003b969  test    r14b, bl
0x18003b96c  jz      short loc_18003B99C
0x18003b96e  mov     eax, ebx
0x18003b970  and     eax, 7
0x18003b973  cmp     al, 7
0x18003b975  jnz     short loc_18003B980
0x18003b977  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, r12d; int SString::s_IsANSIMultibyte
0x18003b97e  jz      short loc_18003B99C
0x18003b980  lea     rcx, [rsp+2F0h+Size]; this
0x18003b985  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003b98a  test    eax, eax
0x18003b98c  jnz     short loc_18003B998
0x18003b98e  lea     rcx, [rsp+2F0h+Size]; this
0x18003b993  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003b998  mov     ebx, [rsp+2F0h+var_2B0]
0x18003b99c  mov     ecx, ebx
0x18003b99e  not     ecx
0x18003b9a0  and     ecx, 1
0x18003b9a3  mov     edi, dword ptr [rsp+2F0h+Size]
0x18003b9a7  mov     r15d, edi
0x18003b9aa  shr     r15d, cl
0x18003b9ad  mov     ecx, [rsp+2F0h+var_2C8]
0x18003b9b1  test    r14b, cl
0x18003b9b4  jz      short loc_18003B9E4
0x18003b9b6  mov     eax, ecx
0x18003b9b8  and     eax, 7
0x18003b9bb  cmp     al, 7
0x18003b9bd  jnz     short loc_18003B9C8
0x18003b9bf  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, r12d; int SString::s_IsANSIMultibyte
0x18003b9c6  jz      short loc_18003B9E4
0x18003b9c8  lea     rcx, [rsp+2F0h+var_2D0]; this
0x18003b9cd  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003b9d2  test    eax, eax
0x18003b9d4  jnz     short loc_18003B9E0
0x18003b9d6  lea     rcx, [rsp+2F0h+var_2D0]; this
0x18003b9db  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003b9e0  mov     ecx, [rsp+2F0h+var_2C8]
0x18003b9e4  not     ecx
0x18003b9e6  and     ecx, 1
0x18003b9e9  mov     r14d, [rsp+2F0h+var_2D0]
0x18003b9ee  shr     r14d, cl
0x18003b9f1  mov     ecx, [rsp+2F0h+var_298]
0x18003b9f5  test    cl, 2
0x18003b9f8  jz      short loc_18003BA28
0x18003b9fa  mov     eax, ecx
0x18003b9fc  and     eax, 7
0x18003b9ff  cmp     al, 7
0x18003ba01  jnz     short loc_18003BA0C
0x18003ba03  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, r12d; int SString::s_IsANSIMultibyte
0x18003ba0a  jz      short loc_18003BA28
0x18003ba0c  lea     rcx, [rsp+2F0h+var_2A0]; this
0x18003ba11  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003ba16  test    eax, eax
0x18003ba18  jnz     short loc_18003BA24
0x18003ba1a  lea     rcx, [rsp+2F0h+var_2A0]; this
0x18003ba1f  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003ba24  mov     ecx, [rsp+2F0h+var_298]
0x18003ba28  not     ecx
0x18003ba2a  and     ecx, 1
0x18003ba2d  mov     eax, [rsp+2F0h+var_2A0]
0x18003ba31  shr     eax, cl
0x18003ba33  add     eax, r14d
0x18003ba36  add     eax, r15d
0x18003ba39  lea     eax, ds:0FFFFFFFFFFFFFFFAh[rax*2]
0x18003ba40  mov     edx, dword ptr [rbp+1F0h+var_260+4]
0x18003ba43  cmp     eax, edx
0x18003ba45  jbe     short loc_18003BA5B
0x18003ba47  mov     r8d, 1
0x18003ba4d  mov     edx, eax
0x18003ba4f  lea     rcx, [rbp+1F0h+var_260]
0x18003ba53  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003ba58  mov     edx, dword ptr [rbp+1F0h+var_260+4]
0x18003ba5b  mov     r15b, 8
0x18003ba5e  test    bl, 10h
0x18003ba61  jz      short loc_18003BABD
0x18003ba63  mov     eax, [rbp+1F0h+var_258]
0x18003ba66  test    al, 10h
0x18003ba68  jnz     short loc_18003BA6E
0x18003ba6a  cmp     edx, edi
0x18003ba6c  jnb     short loc_18003BAD5
0x18003ba6e  test    r15b, al
0x18003ba71  jz      short loc_18003BAA3
0x18003ba73  mov     r14, [rbp+1F0h+lpMem]
0x18003ba77  test    r14, r14
0x18003ba7a  jz      short loc_18003BAA3
0x18003ba7c  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003ba83  test    rax, rax
0x18003ba86  jnz     short loc_18003BA95
0x18003ba88  call    cs:__imp_GetProcessHeap
0x18003ba8e  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003ba95  mov     r8, r14; lpMem
0x18003ba98  xor     edx, edx; dwFlags
0x18003ba9a  mov     rcx, rax; hHeap
0x18003ba9d  call    cs:__imp_HeapFree
0x18003baa3  mov     dword ptr [rbp+1F0h+var_260], edi
0x18003baa6  mov     eax, dword ptr [rsp+2F0h+Size+4]
0x18003baaa  mov     dword ptr [rbp+1F0h+var_260+4], eax
0x18003baad  mov     rdi, [rsp+2F0h+Src]
0x18003bab2  mov     [rbp+1F0h+lpMem], rdi
0x18003bab6  mov     ecx, ebx
0x18003bab8  mov     [rbp+1F0h+var_258], ebx
0x18003babb  jmp     short loc_18003BB02
0x18003babd  cmp     edi, edx
0x18003babf  jbe     short loc_18003BAD2
0x18003bac1  xor     r8d, r8d
0x18003bac4  mov     edx, edi
0x18003bac6  lea     rcx, [rbp+1F0h+var_260]
0x18003baca  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003bacf  mov     edx, dword ptr [rbp+1F0h+var_260+4]
0x18003bad2  mov     eax, [rbp+1F0h+var_258]
0x18003bad5  mov     dword ptr [rbp+1F0h+var_260], edi
0x18003bad8  test    al, 10h
0x18003bada  jz      short loc_18003BAEB
0x18003badc  mov     r8d, 1
0x18003bae2  lea     rcx, [rbp+1F0h+var_260]
0x18003bae6  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003baeb  mov     r8, rdi; Size
0x18003baee  mov     rdi, [rsp+2F0h+Src]
0x18003baf3  mov     rdx, rdi; Src
0x18003baf6  mov     rcx, [rbp+1F0h+lpMem]; void *
0x18003bafa  call    memcpy_0
0x18003baff  mov     ecx, [rbp+1F0h+var_258]
0x18003bb02  mov     eax, ebx
0x18003bb04  and     eax, 7
0x18003bb07  and     ecx, 0FFFFFFF8h
0x18003bb0a  mov     [rbp+1F0h+var_258], ecx
0x18003bb0d  or      ecx, eax
0x18003bb0f  mov     [rbp+1F0h+var_258], ecx
0x18003bb12  btr     ecx, 8
0x18003bb16  mov     [rbp+1F0h+var_258], ecx
0x18003bb19  lea     rdx, [rsp+2F0h+var_2D0]; struct SString *
0x18003bb1e  lea     rcx, [rbp+1F0h+var_260]; this
0x18003bb22  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18003bb27  lea     rdx, [rsp+2F0h+var_2A0]; struct SString *
0x18003bb2c  lea     rcx, [rbp+1F0h+var_260]; this
0x18003bb30  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18003bb35  nop
0x18003bb36  test    r15b, bl
0x18003bb39  jz      short loc_18003BB44
0x18003bb3b  mov     rcx, rdi; lpMem
0x18003bb3e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003bb43  nop
0x18003bb44  test    byte ptr [rsp+2F0h+var_298], r15b
0x18003bb49  jz      short loc_18003BB55
0x18003bb4b  mov     rcx, [rsp+2F0h+var_290]; lpMem
0x18003bb50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003bb55  lea     rcx, [rbp+1F0h+var_260]; this
0x18003bb59  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003bb5e  mov     rdx, r13; lpFindFileData
0x18003bb61  mov     rcx, [rbp+1F0h+lpMem]; lpFileName
0x18003bb65  call    cs:__imp_FindFirstFileW
0x18003bb6b  mov     rbx, rax
0x18003bb6e  cmp     [rsi+8], r12d
0x18003bb72  jz      short loc_18003BB81
0x18003bb74  mov     rcx, [rsi]; hFindFile
0x18003bb77  call    cs:__imp_FindClose
0x18003bb7d  mov     [rsi+8], r12d
0x18003bb81  mov     [rsi], rbx
0x18003bb84  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003bb88  jz      loc_18003BC12
0x18003bb8e  mov     dword ptr [rsi+8], 1
0x18003bb95  mov     [r13+260h], r12d
0x18003bb9c  test    byte ptr [rsp+2F0h+var_2C8], r15b
0x18003bba1  jz      short loc_18003BBAE
0x18003bba3  mov     rcx, [rsp+2F0h+var_2C0]; lpMem
0x18003bba8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003bbad  nop
0x18003bbae  test    byte ptr [rbp+1F0h+var_258], r15b
0x18003bbb2  jz      short loc_18003BBE5
0x18003bbb4  mov     rbx, [rbp+1F0h+lpMem]
0x18003bbb8  test    rbx, rbx
0x18003bbbb  jz      short loc_18003BBE5
0x18003bbbd  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003bbc4  test    rax, rax
0x18003bbc7  jnz     short loc_18003BBD6
0x18003bbc9  call    cs:__imp_GetProcessHeap
0x18003bbcf  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003bbd6  mov     r8, rbx; lpMem
0x18003bbd9  xor     edx, edx; dwFlags
0x18003bbdb  mov     rcx, rax; hHeap
0x18003bbde  call    cs:__imp_HeapFree
0x18003bbe4  nop
0x18003bbe5  mov     rax, r13
0x18003bbe8  mov     rcx, [rbp+1F0h+var_40]
0x18003bbef  xor     rcx, rsp; StackCookie
0x18003bbf2  call    __security_check_cookie
0x18003bbf7  mov     rbx, [rsp+2F0h+arg_10]
0x18003bbff  add     rsp, 2C0h
0x18003bc06  pop     r15
0x18003bc08  pop     r14
0x18003bc0a  pop     r13
0x18003bc0c  pop     r12
0x18003bc0e  pop     rdi
0x18003bc0f  pop     rsi
0x18003bc10  pop     rbp
0x18003bc11  retn
0x18003bc12  call    cs:__imp_GetLastError
0x18003bc18  nop
0x18003bc19  add     eax, 0FFFFFFFEh
0x18003bc1c  test    eax, 0FFFFFFEFh
0x18003bc21  jz      loc_18003BB95
0x18003bc27  call    ?ThrowLastError@@YAXXZ; ThrowLastError(void)
```
