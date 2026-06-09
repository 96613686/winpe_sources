# CCorSvcMgr::GetRuntimeVersionFromNativeHeader(ushort const *,ushort * *)

- ea: `0x180020df0`
- end: `0x1800213db`
- name: `?GetRuntimeVersionFromNativeHeader@CCorSvcMgr@@AEAAJPEBGPEAPEAG@Z`
- size: `1515`
- prototype: `int(CCorSvcMgr *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002142c`

## callees

- `0x180020df0`
- `0x18002dc24`
- `0x180030568`
- `0x180030d84`
- `0x180032654`
- `0x180039120`
- `0x1800396e4`
- `0x180039d20`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800212e9`
- `KERNEL32!SetLastError` at `0x1800212e9`
- `KERNEL32!GetFileSize` at `0x180020ee4`
- `KERNEL32!GetFileSize` at `0x180020ee4`
- `KERNEL32!CreateFileMappingW` at `0x180020f2e`
- `KERNEL32!CreateFileMappingW` at `0x180020f2e`
- `KERNEL32!MapViewOfFile` at `0x18002101a`
- `KERNEL32!MapViewOfFile` at `0x18002101a`
- `KERNEL32!UnmapViewOfFile` at `0x1800212b5`
- `KERNEL32!UnmapViewOfFile` at `0x1800212b5`
- `KERNEL32!CreateFileW` at `0x180020e53`
- `KERNEL32!CreateFileW` at `0x180020e53`
- `KERNEL32!CloseHandle` at `0x1800212d6`
- `KERNEL32!CloseHandle` at `0x1800213a6`
- `KERNEL32!CloseHandle` at `0x1800212d6`
- `KERNEL32!CloseHandle` at `0x1800213a6`
- `KERNEL32!GetLastError` at `0x180020e9e`
- `KERNEL32!GetLastError` at `0x180020ef3`
- `KERNEL32!GetLastError` at `0x180020f80`
- `KERNEL32!GetLastError` at `0x180020fef`
- `KERNEL32!GetLastError` at `0x18002106b`
- `KERNEL32!GetLastError` at `0x1800210da`
- `KERNEL32!GetLastError` at `0x180021316`
- `KERNEL32!GetLastError` at `0x180021385`
- `KERNEL32!GetLastError` at `0x180020e9e`
- `KERNEL32!GetLastError` at `0x180020ef3`
- `KERNEL32!GetLastError` at `0x180020f80`
- `KERNEL32!GetLastError` at `0x180020fef`
- `KERNEL32!GetLastError` at `0x18002106b`
- `KERNEL32!GetLastError` at `0x1800210da`
- `KERNEL32!GetLastError` at `0x180021316`
- `KERNEL32!GetLastError` at `0x180021385`
- `KERNEL32!HeapFree` at `0x180020fe9`
- `KERNEL32!HeapFree` at `0x1800210d4`
- `KERNEL32!HeapFree` at `0x1800211af`
- `KERNEL32!HeapFree` at `0x18002137f`
- `KERNEL32!HeapFree` at `0x180020fe9`
- `KERNEL32!HeapFree` at `0x1800210d4`
- `KERNEL32!HeapFree` at `0x1800211af`
- `KERNEL32!HeapFree` at `0x18002137f`
- `KERNEL32!GetProcessHeap` at `0x180020fd4`
- `KERNEL32!GetProcessHeap` at `0x1800210bf`
- `KERNEL32!GetProcessHeap` at `0x18002119a`
- `KERNEL32!GetProcessHeap` at `0x18002136a`
- `KERNEL32!GetProcessHeap` at `0x180020fd4`
- `KERNEL32!GetProcessHeap` at `0x1800210bf`
- `KERNEL32!GetProcessHeap` at `0x18002119a`
- `KERNEL32!GetProcessHeap` at `0x18002136a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002128a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002128a`

## string_xrefs

- `0x180020eaa`: `Can not open native image '%s'.  Error=%d\n`
- `0x180020f8c`: `Unable to create mapping of native image '%s'.  Error=%d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=52
__int64 __fastcall CCorSvcMgr::GetRuntimeVersionFromNativeHeader(
        CCorSvcMgr *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  HANDLE FileW; // rax
  void *v6; // r15
  BOOL v7; // r12d
  DWORD LastError; // eax
  DWORD FileSize; // edi
  HANDLE FileMappingW; // rsi
  DWORD v11; // eax
  void *v12; // rbx
  HANDLE v13; // rax
  signed int v14; // eax
  unsigned int v15; // ebx
  const void *v16; // r12
  DWORD v17; // eax
  void *v18; // rbx
  HANDLE v19; // rax
  signed int v20; // eax
  void *v21; // rbx
  HANDLE v22; // rax
  struct CORCOMPILE_HEADER *NativeHeader; // rax
  unsigned __int16 *RvaData; // rcx
  BSTR v25; // rax
  DWORD v26; // eax
  void *v27; // rbx
  HANDLE ProcessHeap; // rax
  signed int v29; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD FileSizeHigh; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v33; // [rsp+44h] [rbp-BCh]
  BOOL v34; // [rsp+48h] [rbp-B8h]
  _DWORD v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+58h] [rbp-A8h]
  OLECHAR *psz; // [rsp+60h] [rbp-A0h]
  unsigned __int16 **v38; // [rsp+68h] [rbp-98h]
  const void *v39; // [rsp+70h] [rbp-90h]
  DWORD v40; // [rsp+78h] [rbp-88h]
  HANDLE v41; // [rsp+80h] [rbp-80h]
  BOOL v42; // [rsp+88h] [rbp-78h]
  HANDLE v43; // [rsp+90h] [rbp-70h]
  BOOL v44; // [rsp+98h] [rbp-68h]
  const void *v45; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v46; // [rsp+A8h] [rbp-58h]
  int v47; // [rsp+ACh] [rbp-54h]
  __int128 v48; // [rsp+B0h] [rbp-50h]
  __int128 v49; // [rsp+C0h] [rbp-40h]
  _BYTE v50[16]; // [rsp+D0h] [rbp-30h] BYREF
  int v51; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v52; // [rsp+E4h] [rbp-1Ch]
  LPVOID lpMem; // [rsp+F0h] [rbp-10h]
  _WORD v54[260]; // [rsp+F8h] [rbp-8h] BYREF

  v38 = a3;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  v43 = FileW;
  v7 = FileW != (HANDLE)-1LL;
  v33 = v7;
  v44 = v7;
  if ( FileW == (HANDLE)-1LL )
  {
    v52 = 512;
    lpMem = v54;
    v51 = 2;
    v54[0] = 0;
    LastError = GetLastError();
    SString::Printf((SString *)&v51, L"Can not open native image '%s'.  Error=%d\n", a2, LastError);
    SString::ConvertToUnicode((SString *)&v51);
    Logger::Log((char *)this + 208, lpMem, 2);
    goto LABEL_46;
  }
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  if ( FileSize == -1 && GetLastError() )
  {
LABEL_45:
    v52 = 512;
    lpMem = v54;
    v51 = 2;
    v54[0] = 0;
    v26 = GetLastError();
    SString::Printf((SString *)&v51, L"Unable to determine size of native image '%s'.  Error=%d\n", a2, v26);
    SString::ConvertToUnicode((SString *)&v51);
    Logger::Log((char *)this + 208, lpMem, 2);
LABEL_46:
    if ( (v52 & 0x800000000LL) != 0 )
    {
      v27 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v27);
      }
    }
    v29 = GetLastError();
    v15 = (unsigned __int16)v29 | 0x80070000;
    if ( v29 <= 0 )
      v15 = v29;
    goto LABEL_53;
  }
  if ( FileSizeHigh || FileSize == -1 )
  {
    SetLastError(8u);
    goto LABEL_45;
  }
  FileMappingW = CreateFileMappingW(v6, 0, 2u, 0, 0, 0);
  v41 = FileMappingW;
  v34 = FileMappingW != (HANDLE)-1LL;
  v42 = v34;
  if ( FileMappingW )
  {
    v16 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v39 = v16;
    FileSizeHigh = v16 != 0;
    v40 = FileSizeHigh;
    if ( v16 )
    {
      v45 = v16;
      v46 = FileSize;
      v47 = 2;
      v48 = 0;
      v49 = 0;
      if ( *(_QWORD *)PEDecoder::CheckNativeHeader(&v45, v50) )
      {
        v52 = 512;
        lpMem = v54;
        v51 = 2;
        v54[0] = 0;
        SString::Printf((SString *)&v51, L"Invalid header found in native image '%s'.\n", a2);
        SString::ConvertToUnicode((SString *)&v51);
        Logger::Log((char *)this + 208, lpMem, 2);
        if ( (v52 & 0x800000000LL) != 0 )
        {
          v21 = lpMem;
          if ( lpMem )
          {
            v22 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              v22 = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = v22;
            }
            HeapFree(v22, 0, v21);
          }
        }
      }
      else
      {
        NativeHeader = PEDecoder::GetNativeHeader((PEDecoder *)&v45);
        RvaData = (unsigned __int16 *)PEDecoder::GetRvaData(&v45, *((unsigned int *)NativeHeader + 10));
        if ( RvaData )
        {
          v35[0] = 2;
          v35[1] = 2;
          v36 = 16;
          psz = (OLECHAR *)&SString::s_EmptyBuffer;
          dwCreationDisposition[0] = RvaData[4];
          SString::Printf((SString *)v35, L"v%d.%d.%d", RvaData[2], RvaData[3], *(_QWORD *)dwCreationDisposition);
          SString::ConvertToUnicode((SString *)v35);
          v25 = SysAllocString(psz);
          *v38 = v25;
          v15 = 0;
          if ( (v36 & 8) != 0 )
            operator delete(psz);
          goto LABEL_37;
        }
        v52 = 512;
        lpMem = v54;
        v51 = 2;
        v54[0] = 0;
        SString::Printf((SString *)&v51, L"Invalid header found in native image '%s'.\n", a2);
        SString::ConvertToUnicode((SString *)&v51);
        Logger::Log((char *)this + 208, lpMem, 2);
        if ( (v52 & 0x800000000LL) != 0 )
          operator delete(lpMem);
      }
      v15 = -2147467259;
    }
    else
    {
      v52 = 512;
      lpMem = v54;
      v51 = 2;
      v54[0] = 0;
      v17 = GetLastError();
      SString::Printf((SString *)&v51, L"Unable to map view of native image '%s'.  Error=%d\n", a2, v17);
      SString::ConvertToUnicode((SString *)&v51);
      Logger::Log((char *)this + 208, lpMem, 2);
      if ( (v52 & 0x800000000LL) != 0 )
      {
        v18 = lpMem;
        if ( lpMem )
        {
          v19 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v19 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v19;
          }
          HeapFree(v19, 0, v18);
        }
      }
      v20 = GetLastError();
      v15 = (unsigned __int16)v20 | 0x80070000;
      if ( v20 <= 0 )
        v15 = v20;
    }
LABEL_37:
    if ( FileSizeHigh )
    {
      UnmapViewOfFile(v16);
      v40 = 0;
    }
    v7 = v33;
    goto LABEL_40;
  }
  v52 = 512;
  lpMem = v54;
  v51 = 2;
  v54[0] = 0;
  v11 = GetLastError();
  SString::Printf((SString *)&v51, L"Unable to create mapping of native image '%s'.  Error=%d\n", a2, v11);
  SString::ConvertToUnicode((SString *)&v51);
  Logger::Log((char *)this + 208, lpMem, 2);
  if ( (v52 & 0x800000000LL) != 0 )
  {
    v12 = lpMem;
    if ( lpMem )
    {
      v13 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v13 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v13;
      }
      HeapFree(v13, 0, v12);
    }
  }
  v14 = GetLastError();
  v15 = (unsigned __int16)v14 | 0x80070000;
  if ( v14 <= 0 )
    v15 = v14;
LABEL_40:
  if ( v34 )
  {
    if ( FileMappingW )
      CloseHandle(FileMappingW);
    v42 = 0;
  }
LABEL_53:
  if ( v7 )
  {
    if ( v6 )
      CloseHandle(v6);
    v44 = 0;
  }
  return v15;
}

```

## disassembly

```asm
0x180020df0  mov     [rsp-8+arg_18], rbx
0x180020df5  push    rbp
0x180020df6  push    rsi
0x180020df7  push    rdi
0x180020df8  push    r12
0x180020dfa  push    r13
0x180020dfc  push    r14
0x180020dfe  push    r15
0x180020e00  lea     rbp, [rsp-210h]
0x180020e08  sub     rsp, 310h
0x180020e0f  mov     rax, cs:__security_cookie
0x180020e16  xor     rax, rsp
0x180020e19  mov     [rbp+240h+var_40], rax
0x180020e20  mov     [rsp+340h+var_2D8], r8
0x180020e25  mov     r14, rdx
0x180020e28  mov     r13, rcx
0x180020e2b  xor     edi, edi
0x180020e2d  mov     [rsp+340h+hTemplateFile], rdi; hTemplateFile
0x180020e32  mov     [rsp+340h+dwFlagsAndAttributes], 80h; lpName
0x180020e3a  mov     [rsp+340h+dwCreationDisposition], 3; dwMaximumSizeLow
0x180020e42  xor     r9d, r9d; lpSecurityAttributes
0x180020e45  lea     ebx, [rdi+1]
0x180020e48  mov     r8d, ebx; dwShareMode
0x180020e4b  mov     edx, 80000000h; dwDesiredAccess
0x180020e50  mov     rcx, r14; lpFileName
0x180020e53  call    cs:__imp_CreateFileW
0x180020e59  mov     r15, rax
0x180020e5c  mov     [rbp+240h+var_2B0], rax
0x180020e60  mov     [rbp+240h+var_2A8], edi
0x180020e63  mov     r12d, edi
0x180020e66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020e6a  cmovnz  r12d, ebx
0x180020e6e  mov     [rsp+340h+var_2FC], r12d
0x180020e73  mov     [rbp+240h+var_2A8], r12d
0x180020e77  jnz     short loc_180020EDC
0x180020e79  mov     [rbp+240h+var_260], rdi
0x180020e7d  mov     [rbp+240h+var_260+4], 200h
0x180020e85  mov     [rbp+240h+lpMem], rdi
0x180020e89  lea     rax, [rbp+240h+var_248]
0x180020e8d  mov     [rbp+240h+lpMem], rax
0x180020e91  lea     ebx, [rdi+2]
0x180020e94  mov     dword ptr [rbp+240h+var_260], ebx
0x180020e97  mov     rax, [rbp+240h+lpMem]
0x180020e9b  mov     [rax], di
0x180020e9e  call    cs:__imp_GetLastError
0x180020ea4  mov     r9d, eax
0x180020ea7  mov     r8, r14
0x180020eaa  lea     rdx, aCanNotOpenNati; "Can not open native image '%s'.  Error="...
0x180020eb1  lea     rcx, [rbp+240h+var_260]; this
0x180020eb5  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180020eba  lea     rcx, [rbp+240h+var_260]; this
0x180020ebe  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180020ec3  lea     rcx, [r13+0D0h]
0x180020eca  mov     r8d, ebx
0x180020ecd  mov     rdx, [rbp+240h+lpMem]
0x180020ed1  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x180020ed6  nop
0x180020ed7  jmp     loc_18002134F
0x180020edc  lea     rdx, [rsp+340h+FileSizeHigh]; lpFileSizeHigh
0x180020ee1  mov     rcx, r15; hFile
0x180020ee4  call    cs:__imp_GetFileSize
0x180020eea  mov     edi, eax
0x180020eec  or      ebx, 0FFFFFFFFh
0x180020eef  cmp     eax, ebx
0x180020ef1  jnz     short loc_180020F01
0x180020ef3  call    cs:__imp_GetLastError
0x180020ef9  test    eax, eax
0x180020efb  jnz     loc_1800212EF
0x180020f01  cmp     [rsp+340h+FileSizeHigh], 0
0x180020f06  jnz     loc_1800212E4
0x180020f0c  cmp     edi, ebx
0x180020f0e  jz      loc_1800212E4
0x180020f14  and     qword ptr [rsp+340h+dwFlagsAndAttributes], 0
0x180020f1a  and     [rsp+340h+dwCreationDisposition], 0
0x180020f1f  xor     r9d, r9d; dwMaximumSizeHigh
0x180020f22  lea     ebx, [r9+2]
0x180020f26  mov     r8d, ebx; flProtect
0x180020f29  xor     edx, edx; lpFileMappingAttributes
0x180020f2b  mov     rcx, r15; hFile
0x180020f2e  call    cs:__imp_CreateFileMappingW
0x180020f34  mov     rsi, rax
0x180020f37  mov     [rbp+240h+var_2C0], rax
0x180020f3b  xor     ecx, ecx
0x180020f3d  mov     [rbp+240h+var_2B8], ecx
0x180020f40  mov     eax, ecx
0x180020f42  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180020f46  lea     edx, [rbx-1]
0x180020f49  cmovnz  eax, edx
0x180020f4c  mov     [rsp+340h+var_2F8], eax
0x180020f50  mov     [rbp+240h+var_2B8], eax
0x180020f53  test    rsi, rsi
0x180020f56  jnz     loc_180021008
0x180020f5c  xor     edi, edi
0x180020f5e  mov     [rbp+240h+var_260], rdi
0x180020f62  mov     [rbp+240h+var_260+4], 200h
0x180020f6a  mov     [rbp+240h+lpMem], rdi
0x180020f6e  lea     rax, [rbp+240h+var_248]
0x180020f72  mov     [rbp+240h+lpMem], rax
0x180020f76  mov     dword ptr [rbp+240h+var_260], ebx
0x180020f79  mov     rax, [rbp+240h+lpMem]
0x180020f7d  mov     [rax], di
0x180020f80  call    cs:__imp_GetLastError
0x180020f86  mov     r9d, eax
0x180020f89  mov     r8, r14
0x180020f8c  lea     rdx, aUnableToCreate_0; "Unable to create mapping of native imag"...
0x180020f93  lea     rcx, [rbp+240h+var_260]; this
0x180020f97  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180020f9c  lea     rcx, [rbp+240h+var_260]; this
0x180020fa0  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180020fa5  lea     rcx, [r13+0D0h]
0x180020fac  mov     r8d, ebx
0x180020faf  mov     rdx, [rbp+240h+lpMem]
0x180020fb3  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x180020fb8  nop
0x180020fb9  test    [rbp+240h+var_258], 8
0x180020fbd  jz      short loc_180020FEF
0x180020fbf  mov     rbx, [rbp+240h+lpMem]
0x180020fc3  test    rbx, rbx
0x180020fc6  jz      short loc_180020FEF
0x180020fc8  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180020fcf  test    rax, rax
0x180020fd2  jnz     short loc_180020FE1
0x180020fd4  call    cs:__imp_GetProcessHeap
0x180020fda  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180020fe1  mov     r8, rbx; lpMem
0x180020fe4  xor     edx, edx; dwFlags
0x180020fe6  mov     rcx, rax; hHeap
0x180020fe9  call    cs:__imp_HeapFree
0x180020fef  call    cs:__imp_GetLastError
0x180020ff5  movzx   ebx, ax
0x180020ff8  or      ebx, 80070000h
0x180020ffe  test    eax, eax
0x180021000  cmovle  ebx, eax
0x180021003  jmp     loc_1800212C4
0x180021008  mov     qword ptr [rsp+340h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x18002100d  xor     r9d, r9d; dwFileOffsetLow
0x180021010  xor     r8d, r8d; dwFileOffsetHigh
0x180021013  lea     edx, [r9+4]; dwDesiredAccess
0x180021017  mov     rcx, rsi; hFileMappingObject
0x18002101a  call    cs:__imp_MapViewOfFile
0x180021020  mov     r12, rax
0x180021023  mov     [rsp+340h+var_2D0], rax
0x180021028  xor     ecx, ecx
0x18002102a  mov     [rsp+340h+var_2C8], ecx
0x18002102e  mov     eax, ecx
0x180021030  test    r12, r12
0x180021033  lea     edx, [rcx+1]
0x180021036  cmovnz  eax, edx
0x180021039  mov     [rsp+340h+FileSizeHigh], eax
0x18002103d  mov     [rsp+340h+var_2C8], eax
0x180021041  jnz     loc_1800210F3
0x180021047  xor     edi, edi
0x180021049  mov     [rbp+240h+var_260], rdi
0x18002104d  mov     [rbp+240h+var_260+4], 200h
0x180021055  mov     [rbp+240h+lpMem], rdi
0x180021059  lea     rax, [rbp+240h+var_248]
0x18002105d  mov     [rbp+240h+lpMem], rax
0x180021061  mov     dword ptr [rbp+240h+var_260], ebx
0x180021064  mov     rax, [rbp+240h+lpMem]
0x180021068  mov     [rax], di
0x18002106b  call    cs:__imp_GetLastError
0x180021071  mov     r9d, eax
0x180021074  mov     r8, r14
0x180021077  lea     rdx, aUnableToMapVie; "Unable to map view of native image '%s'"...
0x18002107e  lea     rcx, [rbp+240h+var_260]; this
0x180021082  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180021087  lea     rcx, [rbp+240h+var_260]; this
0x18002108b  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180021090  lea     rcx, [r13+0D0h]
0x180021097  mov     r8d, ebx
0x18002109a  mov     rdx, [rbp+240h+lpMem]
0x18002109e  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x1800210a3  nop
0x1800210a4  test    [rbp+240h+var_258], 8
0x1800210a8  jz      short loc_1800210DA
0x1800210aa  mov     rbx, [rbp+240h+lpMem]
0x1800210ae  test    rbx, rbx
0x1800210b1  jz      short loc_1800210DA
0x1800210b3  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800210ba  test    rax, rax
0x1800210bd  jnz     short loc_1800210CC
0x1800210bf  call    cs:__imp_GetProcessHeap
0x1800210c5  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800210cc  mov     r8, rbx; lpMem
0x1800210cf  xor     edx, edx; dwFlags
0x1800210d1  mov     rcx, rax; hHeap
0x1800210d4  call    cs:__imp_HeapFree
0x1800210da  call    cs:__imp_GetLastError
0x1800210e0  movzx   ebx, ax
0x1800210e3  or      ebx, 80070000h
0x1800210e9  test    eax, eax
0x1800210eb  cmovle  ebx, eax
0x1800210ee  jmp     loc_1800212AC
0x1800210f3  mov     [rbp+240h+var_2A0], r12
0x1800210f7  mov     [rbp+240h+var_298], edi
0x1800210fa  mov     [rbp+240h+var_294], ebx
0x1800210fd  xorps   xmm0, xmm0
0x180021100  movdqu  [rbp+240h+var_290], xmm0
0x180021105  xorps   xmm1, xmm1
0x180021108  movdqu  [rbp+240h+var_280], xmm1
0x18002110d  lea     rdx, [rbp+240h+var_270]
0x180021111  lea     rcx, [rbp+240h+var_2A0]
0x180021115  call    ?CheckNativeHeader@PEDecoder@@QEBA?AVCHECK@@XZ; PEDecoder::CheckNativeHeader(void)
0x18002111a  xor     edi, edi
0x18002111c  cmp     [rax], rdi
0x18002111f  jz      loc_1800211B7
0x180021125  mov     [rbp+240h+var_260], rdi
0x180021129  mov     [rbp+240h+var_260+4], 200h
0x180021131  mov     [rbp+240h+lpMem], rdi
0x180021135  lea     rax, [rbp+240h+var_248]
0x180021139  mov     [rbp+240h+lpMem], rax
0x18002113d  mov     dword ptr [rbp+240h+var_260], ebx
0x180021140  mov     rax, [rbp+240h+lpMem]
0x180021144  mov     [rax], di
0x180021147  mov     r8, r14
0x18002114a  lea     rdx, aInvalidHeaderF; "Invalid header found in native image '%"...
0x180021151  lea     rcx, [rbp+240h+var_260]; this
0x180021155  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18002115a  lea     rcx, [rbp+240h+var_260]; this
0x18002115e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180021163  lea     rcx, [r13+0D0h]
0x18002116a  mov     r8d, ebx
0x18002116d  mov     rdx, [rbp+240h+lpMem]
0x180021171  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x180021176  nop
0x180021177  test    [rbp+240h+var_258], 8
0x18002117b  jz      loc_180021235
0x180021181  mov     rbx, [rbp+240h+lpMem]
0x180021185  test    rbx, rbx
0x180021188  jz      loc_180021235
0x18002118e  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180021195  test    rax, rax
0x180021198  jnz     short loc_1800211A7
0x18002119a  call    cs:__imp_GetProcessHeap
0x1800211a0  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800211a7  mov     r8, rbx; lpMem
0x1800211aa  xor     edx, edx; dwFlags
0x1800211ac  mov     rcx, rax; hHeap
0x1800211af  call    cs:__imp_HeapFree
0x1800211b5  jmp     short loc_180021235
0x1800211b7  lea     rcx, [rbp+240h+var_2A0]; this
0x1800211bb  call    ?GetNativeHeader@PEDecoder@@QEBAPEAUCORCOMPILE_HEADER@@XZ; PEDecoder::GetNativeHeader(void)
0x1800211c0  mov     edx, [rax+28h]
0x1800211c3  lea     rcx, [rbp+240h+var_2A0]
0x1800211c7  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x1800211cc  mov     rcx, rax
0x1800211cf  test    rax, rax
0x1800211d2  jnz     short loc_18002123C
0x1800211d4  mov     [rbp+240h+var_260], rdi
0x1800211d8  mov     [rbp+240h+var_260+4], 200h
0x1800211e0  mov     [rbp+240h+lpMem], rdi
0x1800211e4  lea     rax, [rbp+240h+var_248]
0x1800211e8  mov     [rbp+240h+lpMem], rax
0x1800211ec  mov     dword ptr [rbp+240h+var_260], ebx
0x1800211ef  mov     rax, [rbp+240h+lpMem]
0x1800211f3  mov     [rax], di
0x1800211f6  mov     r8, r14
0x1800211f9  lea     rdx, aInvalidHeaderF; "Invalid header found in native image '%"...
0x180021200  lea     rcx, [rbp+240h+var_260]; this
0x180021204  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180021209  lea     rcx, [rbp+240h+var_260]; this
0x18002120d  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180021212  lea     rcx, [r13+0D0h]
0x180021219  mov     r8d, ebx
0x18002121c  mov     rdx, [rbp+240h+lpMem]
0x180021220  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x180021225  nop
0x180021226  test    [rbp+240h+var_258], 8
0x18002122a  jz      short loc_180021235
0x18002122c  mov     rcx, [rbp+240h+lpMem]; lpMem
0x180021230  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021235  mov     ebx, 80004005h
0x18002123a  jmp     short loc_1800212AC
0x18002123c  mov     [rsp+340h+var_2F0], ebx
0x180021240  mov     [rsp+340h+var_2EC], ebx
0x180021244  mov     [rsp+340h+var_2E8], 10h
0x18002124c  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180021253  mov     [rsp+340h+psz], rax
0x180021258  movzx   eax, word ptr [rcx+8]
0x18002125c  movzx   r9d, word ptr [rcx+6]
0x180021261  movzx   r8d, word ptr [rcx+4]
0x180021266  mov     [rsp+340h+dwCreationDisposition], eax
0x18002126a  lea     rdx, aVDDD; "v%d.%d.%d"
0x180021271  lea     rcx, [rsp+340h+var_2F0]; this
0x180021276  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18002127b  lea     rcx, [rsp+340h+var_2F0]; this
0x180021280  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180021285  mov     rcx, [rsp+340h+psz]; psz
0x18002128a  call    cs:__imp_SysAllocString
0x180021290  mov     rcx, [rsp+340h+var_2D8]
0x180021295  mov     [rcx], rax
0x180021298  mov     ebx, edi
0x18002129a  test    byte ptr [rsp+340h+var_2E8], 8
0x18002129f  jz      short loc_1800212AC
0x1800212a1  mov     rcx, [rsp+340h+psz]; lpMem
0x1800212a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800212ab  nop
0x1800212ac  cmp     [rsp+340h+FileSizeHigh], edi
0x1800212b0  jz      short loc_1800212BF
0x1800212b2  mov     rcx, r12; lpBaseAddress
  ... truncated ...
```
