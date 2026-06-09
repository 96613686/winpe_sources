# HyperVFileIo::Open(ushort const *,HyperVFileOpenFlags,int *)

- ea: `0x180080840`
- end: `0x180080c25`
- name: `?Open@HyperVFileIo@@UEAAHPEBGW4HyperVFileOpenFlags@@PEAH@Z`
- size: `997`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007dbc`
- `0x180007e24`
- `0x1800136d0`
- `0x18001587c`
- `0x180066284`
- `0x1800663a4`
- `0x18007ebe0`
- `0x18007f0f4`
- `0x18007f66c`
- `0x18007f8d4`
- `0x180080840`
- `0x180080c2c`
- `0x180081510`
- `0x180081f2c`
- `0x180082140`
- `0x18008226c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080b11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180080b11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180080b19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180080b19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080966`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800809da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800809da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008096c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008096c`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800809ca`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800809ca`

## string_xrefs

- `0x180080882`: `HyperVFileIo::Open`
- `0x180080c13`: `onecore\vm\common\hypervstorage\hypervfileio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HyperVFileIo::Open(__int64 a1, unsigned __int16 *a2, unsigned int a3, _DWORD *a4)
{
  int v7; // edi
  char v9; // si
  bool v10; // bl
  DWORD LastError; // edi
  __int64 v12; // r8
  const unsigned __int16 *v13; // rdi
  int IsDebugTraceEnabled; // r13d
  _DWORD *v15; // rcx
  char v16; // r15
  const unsigned __int16 *v17; // r8
  RTL_SRWLOCK *v18; // rcx
  struct _FILETIME v19; // [rsp+20h] [rbp-89h]
  _DWORD v20[3]; // [rsp+44h] [rbp-65h] BYREF
  struct _GUID v21; // [rsp+50h] [rbp-59h] BYREF
  HANDLE *p_hFile; // [rsp+60h] [rbp-49h]
  __int64 v23; // [rsp+68h] [rbp-41h]
  unsigned __int16 **v24; // [rsp+70h] [rbp-39h]
  unsigned __int16 **v25; // [rsp+78h] [rbp-31h]
  __int64 v26; // [rsp+80h] [rbp-29h]
  struct _GUID v27; // [rsp+90h] [rbp-19h] BYREF
  HANDLE hFile; // [rsp+A0h] [rbp-9h] BYREF
  unsigned __int16 *v29; // [rsp+A8h] [rbp-1h] BYREF
  unsigned __int16 *v30; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v29 = a2;
  if ( a4 )
    *a4 = 0;
  v30 = L"HyperVFileIo::Open";
  hFile = (HANDLE)-1LL;
  v20[0] = 0;
  v7 = HyperVFileIo::OpenInternal(a2, a3, &hFile, v20);
  v27 = *(struct _GUID *)(a1 + 8);
  HyperVStorageTrace::HyperVFileIo_Open(&v27, v30, v29, a3, hFile, v20[0] != 0, v7);
  if ( v7 < 0 && (a3 & 0x200) == 0 )
  {
    if ( v7 == -2147024894 )
      return 0;
    if ( (unsigned int)HvsIsDebugTraceEnabled(0x8000u) )
    {
      v9 = 1;
      v10 = IsHyperVStorageTraceEnabled();
    }
    else
    {
      v10 = IsHyperVStorageTraceEnabled();
      if ( !v10 )
        goto LABEL_48;
      v9 = 0;
    }
    if ( dword_1800E4838 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 16LL) )
    {
      Init_thread_header(&dword_1800E4838);
      if ( dword_1800E4838 == -1 )
      {
        byte_1800E2464 = v9;
        byte_1800E2465 = v10;
        Init_thread_footer(&dword_1800E4838);
      }
    }
    v19.dwLowDateTime = a3;
    HvsDebugTraceInternal(0x8000u, (const struct HvsDebugTraceParameters *)&off_1800E2450, v29, (unsigned int)v7, v19);
LABEL_48:
    HvsThrowWin32Error(v7);
  }
  *(_QWORD *)&v27.Data1 = a1 + 24;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 24));
  *(_DWORD *)(a1 + 32) = GetCurrentThreadId();
  v26 = 1;
  p_hFile = &hFile;
  v23 = a1;
  v24 = &v30;
  v25 = &v29;
  if ( hFile == (HANDLE)-1LL )
  {
    v21 = *(struct _GUID *)(a1 + 8);
    HyperVStorageTrace::HyperVFileIo_DisconnectedOpen(&v21, v29, v7, a3);
  }
  else
  {
    if ( GetFileTime(hFile, (LPFILETIME)(a1 + 128), 0, (LPFILETIME)(a1 + 136)) )
      LastError = 0;
    else
      LastError = GetLastError();
    v21 = *(struct _GUID *)(a1 + 8);
    HyperVStorageTrace::HyperVFileIo_GetFileTime(&v21, v30, v29, hFile, *(struct _FILETIME *)(a1 + 136), LastError);
    if ( LastError )
      HvsThrowWin32Error(LastError);
  }
  if ( *(_QWORD *)(a1 + 72) != -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32D,
      (unsigned int)"onecore\\vm\\common\\hypervstorage\\hypervfileio.cpp",
      (const char *)0x80070055LL,
      v19.dwLowDateTime);
  *(_QWORD *)(a1 + 72) = hFile;
  LOBYTE(v26) = 0;
  v12 = -1;
  do
    ++v12;
  while ( v29[v12] );
  v13 = (const unsigned __int16 *)(a1 + 40);
  std::wstring::_Assign<unsigned short>(a1 + 40, v29);
  *(_DWORD *)(a1 + 144) = a3;
  IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC000u);
  v15 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
  if ( !v15 || (v16 = 1, !*v15) )
    v16 = 0;
  if ( IsDebugTraceEnabled || v16 )
  {
    if ( dword_1800E4834 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 16LL) )
    {
      Init_thread_header(&dword_1800E4834);
      if ( dword_1800E4834 == -1 )
      {
        byte_1800E247C = IsDebugTraceEnabled != 0;
        byte_1800E247D = v16;
        Init_thread_footer(&dword_1800E4834);
      }
    }
    if ( *(_QWORD *)(a1 + 64) <= 7u )
      v17 = (const unsigned __int16 *)(a1 + 40);
    else
      v17 = *(const unsigned __int16 **)v13;
    HvsDebugTraceInternal(0xC000u, (const struct HvsDebugTraceParameters *)&off_1800E2468, v17);
  }
  if ( a4 )
    *a4 = v20[0];
  v18 = (RTL_SRWLOCK *)(a1 + 24);
  if ( *(_DWORD *)(a1 + 32) )
  {
    *(_DWORD *)(a1 + 32) = 0;
    ReleaseSRWLockExclusive(v18);
  }
  else
  {
    ReleaseSRWLockShared(v18);
  }
  if ( (*(_DWORD *)(a1 + 144) & 0x400) != 0 )
  {
    if ( *(_QWORD *)(a1 + 64) > 7u )
      v13 = *(const unsigned __int16 **)v13;
    v21 = *(struct _GUID *)(a1 + 8);
    HyperVStorageTrace::HyperVFileIo_ClearFileContents(&v21, v13, *(void **)(a1 + 72));
    HyperVFileIo::SetFileSize((HyperVFileIo *)a1, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x180080840  push    rbp
0x180080842  push    rbx
0x180080843  push    rsi
0x180080844  push    rdi
0x180080845  push    r12
0x180080847  push    r13
0x180080849  push    r14
0x18008084b  push    r15
0x18008084d  lea     rbp, [rsp-1Fh]
0x180080852  sub     rsp, 0C8h
0x180080859  mov     rax, cs:__security_cookie
0x180080860  xor     rax, rsp
0x180080863  mov     [rbp+57h+var_48], rax
0x180080867  mov     r12, r9
0x18008086a  mov     r15d, r8d
0x18008086d  mov     rax, rdx
0x180080870  mov     rbx, rcx
0x180080873  mov     [rbp+57h+var_58], rdx
0x180080877  xor     r13d, r13d
0x18008087a  test    r9, r9
0x18008087d  jz      short loc_180080882
0x18008087f  mov     [r9], r13d
0x180080882  lea     rcx, aHypervfileioOp_0; "HyperVFileIo::Open"
0x180080889  mov     [rbp+57h+var_50], rcx
0x18008088d  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x180080895  mov     [rbp+57h+var_BC], r13d
0x180080899  lea     r9, [rbp+57h+var_BC]
0x18008089d  lea     r8, [rbp+57h+hFile]
0x1800808a1  mov     edx, r15d
0x1800808a4  mov     rcx, rax
0x1800808a7  call    ?OpenInternal@HyperVFileIo@@CAJPEBGW4HyperVFileOpenFlags@@PEAPEAXPEAH@Z; HyperVFileIo::OpenInternal(ushort const *,HyperVFileOpenFlags,void * *,int *)
0x1800808ac  mov     edi, eax
0x1800808ae  cmp     [rbp+57h+var_BC], r13d
0x1800808b2  setnz   cl
0x1800808b5  movups  xmm0, xmmword ptr [rbx+8]
0x1800808b9  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x1800808be  mov     [rsp+100h+var_D0], eax; int
0x1800808c2  mov     [rsp+100h+var_D8], cl; bool
0x1800808c6  mov     rcx, [rbp+57h+hFile]
0x1800808ca  mov     qword ptr [rsp+100h+var_E0.dwLowDateTime], rcx; int
0x1800808cf  mov     r9d, r15d; unsigned int
0x1800808d2  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x1800808d6  mov     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x1800808da  lea     rcx, [rbp+57h+var_70]; struct _GUID *
0x1800808de  call    ?HyperVFileIo_Open@HyperVStorageTrace@@SAXU_GUID@@PEBG1KPEAX_NJ@Z; HyperVStorageTrace::HyperVFileIo_Open(_GUID,ushort const *,ushort const *,ulong,void *,bool,long)
0x1800808e3  test    edi, edi
0x1800808e5  jns     short loc_18008095B
0x1800808e7  bt      r15d, 9
0x1800808ec  jb      short loc_18008095B
0x1800808ee  cmp     edi, 80070002h
0x1800808f4  jnz     short loc_1800808FD
0x1800808f6  xor     eax, eax
0x1800808f8  jmp     loc_180080B5A
0x1800808fd  mov     r14d, 8000h
0x180080903  mov     ecx, r14d; unsigned __int16
0x180080906  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x18008090b  test    eax, eax
0x18008090d  jz      short loc_18008091D
0x18008090f  mov     esi, 1
0x180080914  call    ?IsHyperVStorageTraceEnabled@@YA_NXZ; IsHyperVStorageTraceEnabled(void)
0x180080919  mov     bl, al
0x18008091b  jmp     short loc_18008092F
0x18008091d  call    ?IsHyperVStorageTraceEnabled@@YA_NXZ; IsHyperVStorageTraceEnabled(void)
0x180080922  mov     bl, al
0x180080924  test    al, al
0x180080926  jz      loc_180080BFD
0x18008092c  mov     sil, r13b
0x18008092f  mov     edx, cs:_tls_index
0x180080935  mov     rax, gs:58h
0x18008093e  mov     ecx, 10h
0x180080943  mov     rax, [rax+rdx*8]
0x180080947  mov     ecx, [rcx+rax]
0x18008094a  cmp     cs:dword_1800E4838, ecx
0x180080950  jle     loc_180080BE2
0x180080956  jmp     loc_180080BB4
0x18008095b  lea     r14, [rbx+18h]
0x18008095f  mov     qword ptr [rbp+57h+var_70.Data1], r14
0x180080963  mov     rcx, r14; SRWLock
0x180080966  call    cs:__imp_AcquireSRWLockExclusive
0x18008096c  call    cs:__imp_GetCurrentThreadId
0x180080972  mov     [r14+8], eax
0x180080976  xorps   xmm0, xmm0
0x180080979  xor     eax, eax
0x18008097b  movups  [rbp+57h+var_A0], xmm0
0x18008097f  movups  [rbp+57h+var_90], xmm0
0x180080983  mov     [rbp+57h+var_80], rax
0x180080987  lea     rax, [rbp+57h+hFile]
0x18008098b  mov     qword ptr [rbp+57h+var_A0], rax
0x18008098f  mov     qword ptr [rbp+57h+var_A0+8], rbx
0x180080993  lea     rax, [rbp+57h+var_50]
0x180080997  mov     qword ptr [rbp+57h+var_90], rax
0x18008099b  lea     rax, [rbp+57h+var_58]
0x18008099f  mov     qword ptr [rbp+57h+var_90+8], rax
0x1800809a3  mov     esi, 1
0x1800809a8  mov     byte ptr [rbp+57h+var_80], sil
0x1800809ac  mov     rcx, [rbp+57h+hFile]; hFile
0x1800809b0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800809b4  jz      short loc_180080A1A
0x1800809b6  lea     r13, [rbx+88h]
0x1800809bd  lea     rdx, [rbx+80h]; lpCreationTime
0x1800809c4  mov     r9, r13; lpLastWriteTime
0x1800809c7  xor     r8d, r8d; lpLastAccessTime
0x1800809ca  call    cs:__imp_GetFileTime
0x1800809d0  xor     ecx, ecx
0x1800809d2  test    eax, eax
0x1800809d4  jz      short loc_1800809DA
0x1800809d6  mov     edi, ecx
0x1800809d8  jmp     short loc_1800809E2
0x1800809da  call    cs:__imp_GetLastError
0x1800809e0  mov     edi, eax
0x1800809e2  movups  xmm0, xmmword ptr [rbx+8]
0x1800809e6  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x1800809eb  mov     dword ptr [rsp+100h+var_D8], edi; unsigned int
0x1800809ef  mov     rcx, [r13+0]
0x1800809f3  mov     qword ptr [rsp+100h+var_E0.dwLowDateTime], rcx; struct _FILETIME
0x1800809f8  mov     r9, [rbp+57h+hFile]; void *
0x1800809fc  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180080a00  mov     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x180080a04  lea     rcx, [rbp+57h+var_B0]; struct _GUID *
0x180080a08  call    ?HyperVFileIo_GetFileTime@HyperVStorageTrace@@SAXU_GUID@@PEBG1PEAXU_FILETIME@@K@Z; HyperVStorageTrace::HyperVFileIo_GetFileTime(_GUID,ushort const *,ushort const *,void *,_FILETIME,ulong)
0x180080a0d  xor     r13d, r13d
0x180080a10  test    edi, edi
0x180080a12  jnz     loc_180080C05
0x180080a18  jmp     short loc_180080A36
0x180080a1a  movups  xmm0, xmmword ptr [rbx+8]
0x180080a1e  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x180080a23  mov     r9d, r15d; unsigned int
0x180080a26  mov     r8d, edi; int
0x180080a29  mov     rdx, [rbp+57h+var_58]; unsigned __int16 *
0x180080a2d  lea     rcx, [rbp+57h+var_B0]; struct _GUID
0x180080a31  call    ?HyperVFileIo_DisconnectedOpen@HyperVStorageTrace@@SAXU_GUID@@PEBGJK@Z; HyperVStorageTrace::HyperVFileIo_DisconnectedOpen(_GUID,ushort const *,long,ulong)
0x180080a36  mov     rcx, [rbp+5Fh]; this
0x180080a3a  cmp     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x180080a3f  jnz     loc_180080C0D
0x180080a45  mov     rax, [rbp+57h+hFile]
0x180080a49  mov     [rbx+48h], rax
0x180080a4d  mov     byte ptr [rbp+57h+var_80], r13b
0x180080a51  mov     rdx, [rbp+57h+var_58]
0x180080a55  or      r8, 0FFFFFFFFFFFFFFFFh
0x180080a59  inc     r8
0x180080a5c  cmp     [rdx+r8*2], r13w
0x180080a61  jnz     short loc_180080A59
0x180080a63  lea     rdi, [rbx+28h]
0x180080a67  mov     rcx, rdi
0x180080a6a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180080a6f  mov     [rbx+90h], r15d
0x180080a76  mov     ecx, 0C000h; unsigned __int16
0x180080a7b  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x180080a80  mov     r13d, eax
0x180080a83  test    eax, eax
0x180080a85  setnz   [rbp+57h+var_C0]
0x180080a89  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180080a8e  mov     rcx, [rax+8]
0x180080a92  xor     edx, edx
0x180080a94  test    rcx, rcx
0x180080a97  jz      short loc_180080AA2
0x180080a99  mov     ecx, [rcx]
0x180080a9b  test    ecx, ecx
0x180080a9d  mov     r15b, sil
0x180080aa0  jnz     short loc_180080AA5
0x180080aa2  mov     r15b, dl
0x180080aa5  test    r13d, r13d
0x180080aa8  jnz     short loc_180080AAF
0x180080aaa  test    r15b, r15b
0x180080aad  jz      short loc_180080AF8
0x180080aaf  mov     edx, cs:_tls_index
0x180080ab5  mov     rax, gs:58h
0x180080abe  mov     ecx, 10h
0x180080ac3  mov     rax, [rax+rdx*8]
0x180080ac7  mov     ecx, [rcx+rax]
0x180080aca  cmp     cs:dword_1800E4834, ecx
0x180080ad0  jg      loc_180080B7A
0x180080ad6  cmp     qword ptr [rdi+18h], 7
0x180080adb  jbe     short loc_180080AE2
0x180080add  mov     r8, [rdi]
0x180080ae0  jmp     short loc_180080AE5
0x180080ae2  mov     r8, rdi
0x180080ae5  lea     rdx, off_1800E2468; struct HvsDebugTraceParameters *
0x180080aec  mov     ecx, 0C000h; unsigned int
0x180080af1  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x180080af6  xor     edx, edx
0x180080af8  test    r12, r12
0x180080afb  jz      short loc_180080B04
0x180080afd  mov     eax, [rbp+57h+var_BC]
0x180080b00  mov     [r12], eax
0x180080b04  mov     rcx, r14; SRWLock
0x180080b07  cmp     [r14+8], edx
0x180080b0b  jz      short loc_180080B19
0x180080b0d  mov     [r14+8], edx
0x180080b11  call    cs:__imp_ReleaseSRWLockExclusive
0x180080b17  jmp     short loc_180080B1F
0x180080b19  call    cs:__imp_ReleaseSRWLockShared
0x180080b1f  test    dword ptr [rbx+90h], 400h
0x180080b29  jz      short loc_180080B58
0x180080b2b  cmp     qword ptr [rdi+18h], 7
0x180080b30  jbe     short loc_180080B35
0x180080b32  mov     rdi, [rdi]
0x180080b35  movups  xmm0, xmmword ptr [rbx+8]
0x180080b39  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x180080b3e  mov     r8, [rbx+48h]; void *
0x180080b42  mov     rdx, rdi; unsigned __int16 *
0x180080b45  lea     rcx, [rbp+57h+var_B0]; struct _GUID
0x180080b49  call    ?HyperVFileIo_ClearFileContents@HyperVStorageTrace@@SAXU_GUID@@PEBGPEAX@Z; HyperVStorageTrace::HyperVFileIo_ClearFileContents(_GUID,ushort const *,void *)
0x180080b4e  xor     edx, edx; unsigned __int64
0x180080b50  mov     rcx, rbx; this
0x180080b53  call    ?SetFileSize@HyperVFileIo@@UEAAX_K@Z; HyperVFileIo::SetFileSize(unsigned __int64)
0x180080b58  mov     eax, esi
0x180080b5a  mov     rcx, [rbp+57h+var_48]
0x180080b5e  xor     rcx, rsp; StackCookie
0x180080b61  call    __security_check_cookie
0x180080b66  add     rsp, 0C8h
0x180080b6d  pop     r15
0x180080b6f  pop     r14
0x180080b71  pop     r13
0x180080b73  pop     r12
0x180080b75  pop     rdi
0x180080b76  pop     rsi
0x180080b77  pop     rbx
0x180080b78  pop     rbp
0x180080b79  retn
0x180080b7a  lea     rcx, dword_1800E4834
0x180080b81  call    _Init_thread_header
0x180080b86  cmp     cs:dword_1800E4834, 0FFFFFFFFh
0x180080b8d  jnz     loc_180080AD6
0x180080b93  mov     al, [rbp+57h+var_C0]
0x180080b96  mov     cs:byte_1800E247C, al
0x180080b9c  mov     cs:byte_1800E247D, r15b
0x180080ba3  lea     rcx, dword_1800E4834
0x180080baa  call    _Init_thread_footer
0x180080baf  jmp     loc_180080AD6
0x180080bb4  lea     rcx, dword_1800E4838
0x180080bbb  call    _Init_thread_header
0x180080bc0  cmp     cs:dword_1800E4838, 0FFFFFFFFh
0x180080bc7  jnz     short loc_180080BE2
0x180080bc9  mov     cs:byte_1800E2464, sil
0x180080bd0  mov     cs:byte_1800E2465, bl
0x180080bd6  lea     rcx, dword_1800E4838
0x180080bdd  call    _Init_thread_footer
0x180080be2  mov     [rsp+100h+var_E0.dwLowDateTime], r15d
0x180080be7  mov     r9d, edi
0x180080bea  mov     r8, [rbp+57h+var_58]
0x180080bee  lea     rdx, off_1800E2450; struct HvsDebugTraceParameters *
0x180080bf5  mov     ecx, r14d; unsigned int
0x180080bf8  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x180080bfd  mov     ecx, edi; unsigned int
0x180080bff  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
0x180080c05  mov     ecx, edi; unsigned int
0x180080c07  call    ?HvsThrowWin32Error@@YAXK@Z; HvsThrowWin32Error(ulong)
0x180080c0d  mov     r9d, 80070055h; char *
0x180080c13  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\hypervstorage\\hyp"...
0x180080c1a  mov     edx, 32Dh; void *
0x180080c1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
