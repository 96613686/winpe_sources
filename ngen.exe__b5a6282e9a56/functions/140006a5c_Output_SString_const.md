# Output(SString const &)

- ea: `0x140006a5c`
- end: `0x140006e3c`
- name: `?Output@@YAXAEBVSString@@@Z`
- size: `992`
- prototype: `void __fastcall(const struct SString *)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x140006e3c`
- `0x140006e90`
- `0x140006ee4`
- `0x1400081b0`

## callees

- `0x140001100`
- `0x140006a5c`
- `0x140009dc4`
- `0x14000a10c`
- `0x14000b010`
- `0x14000b578`
- `0x14000b6e8`
- `0x14000c51c`
- `0x14000e4f4`
- `0x14000e6e0`
- `0x1400102cc`
- `0x140013200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140006d00`
- `KERNEL32!WideCharToMultiByte` at `0x140006d48`
- `KERNEL32!WideCharToMultiByte` at `0x140006d00`
- `KERNEL32!WideCharToMultiByte` at `0x140006d48`
- `KERNEL32!WriteFile` at `0x140006d84`
- `KERNEL32!WriteFile` at `0x140006d84`
- `KERNEL32!GetStdHandle` at `0x140006d66`
- `KERNEL32!GetStdHandle` at `0x140006d66`
- `KERNEL32!GetConsoleOutputCP` at `0x140006cc0`
- `KERNEL32!GetConsoleOutputCP` at `0x140006cc0`
- `KERNEL32!HeapFree` at `0x140006db8`
- `KERNEL32!HeapFree` at `0x140006df5`
- `KERNEL32!HeapFree` at `0x140006db8`
- `KERNEL32!HeapFree` at `0x140006df5`
- `KERNEL32!GetProcessHeap` at `0x140006da3`
- `KERNEL32!GetProcessHeap` at `0x140006de0`
- `KERNEL32!GetProcessHeap` at `0x140006da3`
- `KERNEL32!GetProcessHeap` at `0x140006de0`

## pseudocode

```c
void __fastcall Output(const struct SString *a1)
{
  __int64 v2; // rdx
  __int8 v3; // r8
  int v4; // eax
  __int16 v5; // ax
  const WCHAR *v6; // r14
  char v7; // cl
  int v8; // ebx
  UINT ConsoleOutputCP; // r15d
  int v10; // eax
  __int64 cbMultiByte; // rsi
  CHAR *lpMultiByteStr; // rdi
  DWORD v13; // r14d
  HANDLE StdHandle; // rax
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v17; // rbx
  HANDLE v18; // rax
  __m128i v19; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v20[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+60h] [rbp-A0h]
  void *v22; // [rsp+68h] [rbp-98h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-90h] BYREF
  __m128i v24; // [rsp+78h] [rbp-88h]
  unsigned int v25; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+94h] [rbp-6Ch]
  LPCWCH lpWideCharStr; // [rsp+A0h] [rbp-60h]
  __int16 v28; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID lpMem[68]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v26 = 512;
  lpWideCharStr = (LPCWCH)&v28;
  v25 = 2;
  v28 = 0;
  SBuffer::Set((SBuffer *)&v25, a1);
  HIDWORD(v26) = *((_DWORD *)a1 + 2) & 7 | HIDWORD(v26) & 0xFFFFFEF8;
  if ( (~(HIDWORD(v26) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v25) )
    SString::ConvertToUnicode((SString *)&v25);
  if ( (v26 & 0x1000000000LL) != 0 )
    SBuffer::ReallocateBuffer(&v25, (unsigned int)v26, 1);
  v19.m128i_i64[0] = (__int64)lpWideCharStr;
  for ( v19.m128i_i32[2] = (v26 & 0x100000000LL) == 0;
        (unsigned int)SString::Find((SString *)&v25, (struct SString::CIterator *)&v19, 0xAu);
        v19.m128i_i64[0] = (1 << v3) + v2 )
  {
    if ( (~(HIDWORD(v26) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v25) )
      SString::ConvertToUnicode((SString *)&v25);
    if ( (v26 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer(&v25, (unsigned int)v26, 1);
    v2 = v19.m128i_i64[0];
    if ( (unsigned int)(((__int64)lpWideCharStr - v19.m128i_i64[0]) >> ((v26 & 0x100000000LL) == 0)) )
    {
      v24 = v19;
      v3 = _mm_cvtsi128_si32(_mm_srli_si128(v19, 8));
      v4 = -1 << v3;
      v5 = v19.m128i_i32[2] ? *(_WORD *)(v4 + v19.m128i_i64[0]) : *(char *)(v4 + v19.m128i_i64[0]);
      if ( v5 == 13 )
        continue;
    }
    v20[0] = 6;
    v20[1] = 6;
    v22 = L"\r\n";
    v21 = 276;
    SString::Replace((SString *)&v25, (const struct SString::Iterator *)&v19, 1u, (const struct SString *)v20);
    if ( (v21 & 8) != 0 )
      operator delete(v22);
    v2 = v19.m128i_i64[0];
    v3 = v19.m128i_i8[8];
  }
  SString::ConvertToUnicode((SString *)&v25);
  v6 = lpWideCharStr;
  v7 = BYTE4(v26);
  if ( (v26 & 0x200000000LL) != 0 && ((BYTE4(v26) & 7) != 7 || SString::s_IsANSIMultibyte) )
  {
    if ( !(unsigned int)SString::ScanASCII((SString *)&v25) )
      SString::ConvertToUnicode((SString *)&v25);
    v7 = BYTE4(v26);
  }
  v8 = (v25 >> ((v7 & 1) == 0)) - 1;
  ConsoleOutputCP = GetConsoleOutputCP();
  lpMem[0] = 0;
  lpMem[1] = 0;
  lpMem[2] = (LPVOID)512;
  v10 = WideCharToMultiByte(ConsoleOutputCP, 0, v6, v8, 0, 0, 0, 0);
  cbMultiByte = v10;
  if ( v10 > 536870656 )
    ThrowHR(-2146233066);
  lpMultiByteStr = (CHAR *)CQuickMemoryBase<512,128>::AllocThrows(lpMem, v10 + 1);
  v13 = WideCharToMultiByte(ConsoleOutputCP, 0, v6, v8, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( !v13 && v8 > 0 )
    ThrowWin32(0x459u);
  lpMultiByteStr[cbMultiByte] = 0;
  StdHandle = GetStdHandle(0xFFFFFFF5);
  if ( StdHandle )
    WriteFile(StdHandle, lpMultiByteStr, v13, &NumberOfBytesWritten, 0);
  v15 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
    }
    HeapFree(ProcessHeap, 0, v15);
    lpMem[0] = 0;
  }
  if ( (v26 & 0x800000000LL) != 0 )
  {
    v17 = (WCHAR *)lpWideCharStr;
    if ( lpWideCharStr )
    {
      v18 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v18 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v18;
      }
      HeapFree(v18, 0, v17);
    }
  }
}

```

## disassembly

```asm
0x140006a5c  mov     [rsp-8+arg_8], rbx
0x140006a61  mov     [rsp-8+arg_10], rsi
0x140006a66  push    rbp
0x140006a67  push    rdi
0x140006a68  push    r12
0x140006a6a  push    r14
0x140006a6c  push    r15
0x140006a6e  lea     rbp, [rsp-3E0h]
0x140006a76  sub     rsp, 4E0h
0x140006a7d  mov     rax, cs:__security_cookie
0x140006a84  xor     rax, rsp
0x140006a87  mov     [rbp+400h+var_30], rax
0x140006a8e  mov     rbx, rcx
0x140006a91  xor     r12d, r12d
0x140006a94  mov     [rbp+400h+var_470], r12
0x140006a98  mov     [rbp+400h+var_470+4], 200h
0x140006aa0  mov     [rbp+400h+lpWideCharStr], r12
0x140006aa4  lea     rax, [rbp+400h+var_458]
0x140006aa8  mov     [rbp+400h+lpWideCharStr], rax
0x140006aac  mov     dword ptr [rbp+400h+var_470], 2
0x140006ab3  mov     rax, [rbp+400h+lpWideCharStr]
0x140006ab7  mov     [rax], r12w
0x140006abb  mov     rdx, rcx; struct SBuffer *
0x140006abe  lea     rcx, [rbp+400h+var_470]; this
0x140006ac2  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x140006ac7  mov     eax, [rbx+8]
0x140006aca  and     eax, 7
0x140006acd  mov     ecx, [rbp+400h+var_468]
0x140006ad0  mov     r14d, 0FFFFFFF8h
0x140006ad6  and     ecx, r14d
0x140006ad9  mov     [rbp+400h+var_468], ecx
0x140006adc  or      ecx, eax
0x140006ade  mov     [rbp+400h+var_468], ecx
0x140006ae1  btr     ecx, 8
0x140006ae5  mov     [rbp+400h+var_468], ecx
0x140006ae8  mov     eax, [rbp+400h+var_468]
0x140006aeb  shr     eax, 1
0x140006aed  not     eax
0x140006aef  lea     edi, [r12+1]
0x140006af4  test    dil, al
0x140006af7  jnz     short loc_140006B0F
0x140006af9  lea     rcx, [rbp+400h+var_470]; this
0x140006afd  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140006b02  test    eax, eax
0x140006b04  jnz     short loc_140006B0F
0x140006b06  lea     rcx, [rbp+400h+var_470]; this
0x140006b0a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140006b0f  test    byte ptr [rbp+400h+var_468], 10h
0x140006b13  jz      short loc_140006B24
0x140006b15  mov     r8d, edi
0x140006b18  mov     edx, dword ptr [rbp+400h+var_470+4]
0x140006b1b  lea     rcx, [rbp+400h+var_470]
0x140006b1f  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140006b24  mov     rax, [rbp+400h+lpWideCharStr]
0x140006b28  mov     qword ptr [rsp+500h+var_4C0], rax
0x140006b2d  mov     eax, [rbp+400h+var_468]
0x140006b30  not     eax
0x140006b32  and     eax, edi
0x140006b34  mov     dword ptr [rsp+500h+var_4C0+8], eax
0x140006b38  mov     esi, 0Ah
0x140006b3d  mov     r8d, esi; unsigned __int16
0x140006b40  lea     rdx, [rsp+500h+var_4C0]; struct SString::CIterator *
0x140006b45  lea     rcx, [rbp+400h+var_470]; this
0x140006b49  call    ?Find@SString@@QEBAHAEAVCIterator@1@G@Z; SString::Find(SString::CIterator &,ushort)
0x140006b4e  test    eax, eax
0x140006b50  jz      loc_140006C75
0x140006b56  lea     ebx, [rsi-4]
0x140006b59  mov     eax, [rbp+400h+var_468]
0x140006b5c  shr     eax, 1
0x140006b5e  not     eax
0x140006b60  test    dil, al
0x140006b63  jnz     short loc_140006B7B
0x140006b65  lea     rcx, [rbp+400h+var_470]; this
0x140006b69  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140006b6e  test    eax, eax
0x140006b70  jnz     short loc_140006B7B
0x140006b72  lea     rcx, [rbp+400h+var_470]; this
0x140006b76  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140006b7b  test    byte ptr [rbp+400h+var_468], 10h
0x140006b7f  jz      short loc_140006B90
0x140006b81  mov     r8d, edi
0x140006b84  mov     edx, dword ptr [rbp+400h+var_470+4]
0x140006b87  lea     rcx, [rbp+400h+var_470]
0x140006b8b  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140006b90  mov     rax, [rbp+400h+lpWideCharStr]
0x140006b94  mov     ecx, [rbp+400h+var_468]
0x140006b97  not     ecx
0x140006b99  and     ecx, edi
0x140006b9b  mov     rdx, qword ptr [rsp+500h+var_4C0]
0x140006ba0  sub     rax, rdx
0x140006ba3  sar     rax, cl
0x140006ba6  test    eax, eax
0x140006ba8  jz      short loc_140006BDF
0x140006baa  movups  xmm1, [rsp+500h+var_4C0]
0x140006baf  movups  [rsp+500h+var_488], xmm1
0x140006bb4  psrldq  xmm1, 8
0x140006bb9  movd    r8d, xmm1
0x140006bbe  mov     ecx, r8d
0x140006bc1  or      eax, 0FFFFFFFFh
0x140006bc4  shl     eax, cl
0x140006bc6  movsxd  rcx, eax
0x140006bc9  cmp     dword ptr [rbp+400h+var_488+8], r12d
0x140006bcd  jnz     short loc_140006BD5
0x140006bcf  movsx   eax, byte ptr [rcx+rdx]
0x140006bd3  jmp     short loc_140006BD9
0x140006bd5  movzx   eax, word ptr [rcx+rdx]
0x140006bd9  cmp     ax, 0Dh
0x140006bdd  jz      short loc_140006C4B
0x140006bdf  mov     [rsp+500h+var_4A8], ebx
0x140006be3  mov     [rsp+500h+var_4A4], ebx
0x140006be7  mov     [rsp+500h+var_4A0], 10h
0x140006bef  lea     rax, asc_1400180AC; "\r\n"
0x140006bf6  mov     [rsp+500h+var_498], rax
0x140006bfb  mov     ecx, [rsp+500h+var_4A0]
0x140006bff  and     ecx, r14d
0x140006c02  mov     [rsp+500h+var_4A0], ecx
0x140006c06  mov     eax, ecx
0x140006c08  or      eax, 4
0x140006c0b  mov     [rsp+500h+var_4A0], eax
0x140006c0f  or      ecx, 104h
0x140006c15  mov     [rsp+500h+var_4A0], ecx
0x140006c19  lea     r9, [rsp+500h+var_4A8]; struct SString *
0x140006c1e  mov     r8d, edi; unsigned int
0x140006c21  lea     rdx, [rsp+500h+var_4C0]; struct SString::Iterator *
0x140006c26  lea     rcx, [rbp+400h+var_470]; this
0x140006c2a  call    ?Replace@SString@@QEAAXAEBVIterator@1@IAEBV1@@Z; SString::Replace(SString::Iterator const &,uint,SString const &)
0x140006c2f  nop
0x140006c30  test    byte ptr [rsp+500h+var_4A0], 8
0x140006c35  jz      short loc_140006C41
0x140006c37  mov     rcx, [rsp+500h+var_498]; lpMem
0x140006c3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006c41  mov     rdx, qword ptr [rsp+500h+var_4C0]
0x140006c46  mov     r8d, dword ptr [rsp+500h+var_4C0+8]
0x140006c4b  mov     ecx, r8d
0x140006c4e  mov     eax, edi
0x140006c50  shl     eax, cl
0x140006c52  cdqe
0x140006c54  add     rdx, rax
0x140006c57  mov     qword ptr [rsp+500h+var_4C0], rdx
0x140006c5c  mov     r8d, esi; unsigned __int16
0x140006c5f  lea     rdx, [rsp+500h+var_4C0]; struct SString::CIterator *
0x140006c64  lea     rcx, [rbp+400h+var_470]; this
0x140006c68  call    ?Find@SString@@QEBAHAEAVCIterator@1@G@Z; SString::Find(SString::CIterator &,ushort)
0x140006c6d  test    eax, eax
0x140006c6f  jnz     loc_140006B59
0x140006c75  lea     rcx, [rbp+400h+var_470]; this
0x140006c79  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140006c7e  mov     r14, [rbp+400h+lpWideCharStr]
0x140006c82  mov     ecx, [rbp+400h+var_468]
0x140006c85  test    cl, 2
0x140006c88  jz      short loc_140006CB5
0x140006c8a  mov     eax, ecx
0x140006c8c  and     eax, 7
0x140006c8f  cmp     al, 7
0x140006c91  jnz     short loc_140006C9C
0x140006c93  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, r12d; int SString::s_IsANSIMultibyte
0x140006c9a  jz      short loc_140006CB5
0x140006c9c  lea     rcx, [rbp+400h+var_470]; this
0x140006ca0  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140006ca5  test    eax, eax
0x140006ca7  jnz     short loc_140006CB2
0x140006ca9  lea     rcx, [rbp+400h+var_470]; this
0x140006cad  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140006cb2  mov     ecx, [rbp+400h+var_468]
0x140006cb5  not     ecx
0x140006cb7  and     ecx, edi
0x140006cb9  mov     ebx, dword ptr [rbp+400h+var_470]
0x140006cbc  shr     ebx, cl
0x140006cbe  sub     ebx, edi
0x140006cc0  call    cs:__imp_GetConsoleOutputCP
0x140006cc6  mov     r15d, eax
0x140006cc9  mov     [rbp+400h+lpMem], r12
0x140006cd0  mov     [rbp+400h+var_248], r12
0x140006cd7  mov     [rbp+400h+var_240], 200h
0x140006ce2  mov     [rsp+500h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140006ce7  mov     [rsp+500h+lpDefaultChar], r12; lpDefaultChar
0x140006cec  mov     [rsp+500h+cbMultiByte], r12d; cbMultiByte
0x140006cf1  mov     [rsp+500h+lpMultiByteStr], r12; lpMultiByteStr
0x140006cf6  mov     r9d, ebx; cchWideChar
0x140006cf9  mov     r8, r14; lpWideCharStr
0x140006cfc  xor     edx, edx; dwFlags
0x140006cfe  mov     ecx, eax; CodePage
0x140006d00  call    cs:__imp_WideCharToMultiByte
0x140006d06  movsxd  rsi, eax
0x140006d09  cmp     esi, 1FFFFF00h
0x140006d0f  jg      loc_140006E31
0x140006d15  lea     eax, [rsi+1]
0x140006d18  movsxd  rdx, eax
0x140006d1b  lea     rcx, [rbp+400h+lpMem]
0x140006d22  call    ?AllocThrows@?$CQuickMemoryBase@$0CAA@$0IA@@@QEAAPEAX_K@Z; CQuickMemoryBase<512,128>::AllocThrows(unsigned __int64)
0x140006d27  mov     rdi, rax
0x140006d2a  mov     [rsp+500h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140006d2f  mov     [rsp+500h+lpDefaultChar], r12; lpDefaultChar
0x140006d34  mov     [rsp+500h+cbMultiByte], esi; cbMultiByte
0x140006d38  mov     [rsp+500h+lpMultiByteStr], rax; lpMultiByteStr
0x140006d3d  mov     r9d, ebx; cchWideChar
0x140006d40  mov     r8, r14; lpWideCharStr
0x140006d43  xor     edx, edx; dwFlags
0x140006d45  mov     ecx, r15d; CodePage
0x140006d48  call    cs:__imp_WideCharToMultiByte
0x140006d4e  mov     r14d, eax
0x140006d51  test    eax, eax
0x140006d53  jnz     short loc_140006D5D
0x140006d55  test    ebx, ebx
0x140006d57  jg      loc_140006E26
0x140006d5d  mov     [rsi+rdi], r12b
0x140006d61  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140006d66  call    cs:__imp_GetStdHandle
0x140006d6c  test    rax, rax
0x140006d6f  jz      short loc_140006D8B
0x140006d71  mov     [rsp+500h+lpMultiByteStr], r12; lpOverlapped
0x140006d76  lea     r9, [rsp+500h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140006d7b  mov     r8d, r14d; nNumberOfBytesToWrite
0x140006d7e  mov     rdx, rdi; lpBuffer
0x140006d81  mov     rcx, rax; hFile
0x140006d84  call    cs:__imp_WriteFile
0x140006d8a  nop
0x140006d8b  mov     rbx, [rbp+400h+lpMem]
0x140006d92  test    rbx, rbx
0x140006d95  jz      short loc_140006DC5
0x140006d97  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140006d9e  test    rax, rax
0x140006da1  jnz     short loc_140006DB0
0x140006da3  call    cs:__imp_GetProcessHeap
0x140006da9  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140006db0  mov     r8, rbx; lpMem
0x140006db3  xor     edx, edx; dwFlags
0x140006db5  mov     rcx, rax; hHeap
0x140006db8  call    cs:__imp_HeapFree
0x140006dbe  mov     [rbp+400h+lpMem], r12
0x140006dc5  test    byte ptr [rbp+400h+var_468], 8
0x140006dc9  jz      short loc_140006DFB
0x140006dcb  mov     rbx, [rbp+400h+lpWideCharStr]
0x140006dcf  test    rbx, rbx
0x140006dd2  jz      short loc_140006DFB
0x140006dd4  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140006ddb  test    rax, rax
0x140006dde  jnz     short loc_140006DED
0x140006de0  call    cs:__imp_GetProcessHeap
0x140006de6  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140006ded  mov     r8, rbx; lpMem
0x140006df0  xor     edx, edx; dwFlags
0x140006df2  mov     rcx, rax; hHeap
0x140006df5  call    cs:__imp_HeapFree
0x140006dfb  mov     rcx, [rbp+400h+var_30]
0x140006e02  xor     rcx, rsp; StackCookie
0x140006e05  call    __security_check_cookie
0x140006e0a  lea     r11, [rsp+500h+var_20]
0x140006e12  mov     rbx, [r11+38h]
0x140006e16  mov     rsi, [r11+40h]
0x140006e1a  mov     rsp, r11
0x140006e1d  pop     r15
0x140006e1f  pop     r14
0x140006e21  pop     r12
0x140006e23  pop     rdi
0x140006e24  pop     rbp
0x140006e25  retn
0x140006e26  mov     ecx, 459h; unsigned int
0x140006e2b  call    ?ThrowWin32@@YAXK@Z; ThrowWin32(ulong)
0x140006e31  mov     ecx, 80131516h; int
0x140006e36  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
