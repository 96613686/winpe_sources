# CCorSvcMgr::CreatePdb2(ushort *,ushort *,int,ushort *)

- ea: `0x180020480`
- end: `0x180020dee`
- name: `?CreatePdb2@CCorSvcMgr@@UEAAJPEAG0H0@Z`
- size: `2414`
- prototype: `DWORD __fastcall(CCorSvcMgr *this, unsigned __int16 *, unsigned __int16 *, int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops`

## callees

- `0x180001f00`
- `0x1800200b0`
- `0x180020480`
- `0x18002142c`
- `0x1800235ec`
- `0x18002372c`
- `0x18002c804`
- `0x18002d624`
- `0x18002dc24`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180032654`
- `0x180032948`
- `0x180032ef4`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x180020a09`
- `KERNEL32!CreateDirectoryW` at `0x180020aa8`
- `KERNEL32!CreateDirectoryW` at `0x180020b48`
- `KERNEL32!CreateDirectoryW` at `0x180020a09`
- `KERNEL32!CreateDirectoryW` at `0x180020aa8`
- `KERNEL32!CreateDirectoryW` at `0x180020b48`
- `KERNEL32!GetLastError` at `0x1800204f9`
- `KERNEL32!GetLastError` at `0x180020642`
- `KERNEL32!GetLastError` at `0x1800206b5`
- `KERNEL32!GetLastError` at `0x180020a13`
- `KERNEL32!GetLastError` at `0x180020ab2`
- `KERNEL32!GetLastError` at `0x180020b56`
- `KERNEL32!GetLastError` at `0x180020bc3`
- `KERNEL32!GetLastError` at `0x1800204f9`
- `KERNEL32!GetLastError` at `0x180020642`
- `KERNEL32!GetLastError` at `0x1800206b5`
- `KERNEL32!GetLastError` at `0x180020a13`
- `KERNEL32!GetLastError` at `0x180020ab2`
- `KERNEL32!GetLastError` at `0x180020b56`
- `KERNEL32!GetLastError` at `0x180020bc3`
- `KERNEL32!GetFullPathNameW` at `0x1800204ef`
- `KERNEL32!GetFullPathNameW` at `0x1800204ef`
- `KERNEL32!GetFileAttributesW` at `0x180020610`
- `KERNEL32!GetFileAttributesW` at `0x1800207c2`
- `KERNEL32!GetFileAttributesW` at `0x180020cb0`
- `KERNEL32!GetFileAttributesW` at `0x180020610`
- `KERNEL32!GetFileAttributesW` at `0x1800207c2`
- `KERNEL32!GetFileAttributesW` at `0x180020cb0`
- `KERNEL32!HeapFree` at `0x1800205fd`
- `KERNEL32!HeapFree` at `0x1800206af`
- `KERNEL32!HeapFree` at `0x180020867`
- `KERNEL32!HeapFree` at `0x180020960`
- `KERNEL32!HeapFree` at `0x1800205fd`
- `KERNEL32!HeapFree` at `0x1800206af`
- `KERNEL32!HeapFree` at `0x180020867`
- `KERNEL32!HeapFree` at `0x180020960`
- `KERNEL32!GetProcessHeap` at `0x1800205e8`
- `KERNEL32!GetProcessHeap` at `0x18002069a`
- `KERNEL32!GetProcessHeap` at `0x180020852`
- `KERNEL32!GetProcessHeap` at `0x18002094b`
- `KERNEL32!GetProcessHeap` at `0x1800205e8`
- `KERNEL32!GetProcessHeap` at `0x18002069a`
- `KERNEL32!GetProcessHeap` at `0x180020852`
- `KERNEL32!GetProcessHeap` at `0x18002094b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002050b`
- `OLEAUT32!__imp_SysAllocString` at `0x180020bee`
- `OLEAUT32!__imp_SysAllocString` at `0x18002050b`
- `OLEAUT32!__imp_SysAllocString` at `0x180020bee`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d54`
- `OLEAUT32!__imp_SysFreeString` at `0x180020db1`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d54`
- `OLEAUT32!__imp_SysFreeString` at `0x180020db1`

## string_xrefs

- `0x18002080a`: `A PDB for the specified native image already exists at %s. Skipping.\n`
- `0x180020900`: `Path for PDB "%s" is too long.\n`
- `0x180020a44`: `Unable to create directory for NGEN PDB.\n`
- `0x180020ae3`: `Unable to create directory for NGEN PDB.\n`
- `0x180020b87`: `Unable to create directory for NGEN PDB.\n`
- `0x180020c6f`: `Unable to create PDB.\n`
- `0x180020d3d`: `PDB generated in directory %s\n`

## pseudocode

```c
DWORD __fastcall CCorSvcMgr::CreatePdb2(
        CCorSvcMgr *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5)
{
  CCorSvcMgr *v8; // rcx
  unsigned __int16 *v9; // r13
  BOOL v10; // r12d
  signed int LogicalImageForRootedNI; // ebx
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  void *v15; // rbx
  HANDLE v16; // rax
  signed int v17; // eax
  unsigned __int16 *v18; // r15
  const unsigned __int16 *v19; // rdx
  struct LogicalImage *v20; // rax
  void *v21; // rbx
  void *v22; // rbx
  HANDLE v23; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  WCHAR *v26; // r14
  signed int v27; // eax
  unsigned __int16 *v28; // rax
  OLECHAR *v29; // r15
  BOOL v30; // r12d
  _DWORD v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpPathName; // [rsp+40h] [rbp-C0h]
  _DWORD v34[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h]
  BOOL v37; // [rsp+60h] [rbp-A0h]
  struct LogicalImage *v38; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v39[2]; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v41; // [rsp+80h] [rbp-80h]
  _DWORD v42[2]; // [rsp+88h] [rbp-78h] BYREF
  int v43; // [rsp+90h] [rbp-70h]
  void *v44; // [rsp+98h] [rbp-68h]
  int v45; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v46; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v47; // [rsp+B0h] [rbp-50h]
  BOOL v48; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v49; // [rsp+C0h] [rbp-40h]
  BOOL v50; // [rsp+C8h] [rbp-38h]
  int v51; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v52; // [rsp+D4h] [rbp-2Ch]
  LPVOID lpMem; // [rsp+E0h] [rbp-20h]
  _WORD v54[260]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Buffer[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v45 = a4;
  v46 = a5;
  if ( !a2 || !a3 )
    return -2147467261;
  if ( !GetFullPathNameW(a2, 0x104u, Buffer, 0) )
    return GetLastError();
  v9 = SysAllocString(Buffer);
  v49 = v9;
  v10 = v9 != 0;
  v37 = v10;
  v50 = v10;
  if ( v9 )
  {
    v38 = 0;
    v39[0] = 2;
    v39[1] = 2;
    v40 = 16;
    v41 = (unsigned __int16 *)&SString::s_EmptyBuffer;
    if ( !CCorSvcMgr::GetNativeImageSignatureFromNativeImagePath(v8, v9, (struct SString *)v39) )
    {
      v52 = 512;
      lpMem = v54;
      v51 = 2;
      v54[0] = 0;
      SString::Printf((SString *)&v51, L"The specified native image is not valid.\n");
      SString::ConvertToUnicode((SString *)&v51);
      Logger::Log((char *)this + 192, lpMem, 2);
      if ( (v52 & 0x800000000LL) != 0 )
      {
        v12 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v12);
        }
      }
      LogicalImageForRootedNI = -2147467259;
LABEL_22:
      v18 = v41;
      goto LABEL_81;
    }
    if ( GetFileAttributesW(v9) == -1 )
    {
      v52 = 512;
      lpMem = v54;
      v51 = 2;
      v54[0] = 0;
      LastError = GetLastError();
      SString::Printf((SString *)&v51, L"Can not find native image '%s'.  Error=%d\n", Buffer, LastError);
      SString::ConvertToUnicode((SString *)&v51);
      Logger::Log((char *)this + 192, lpMem, 2);
      if ( (v52 & 0x800000000LL) != 0 )
      {
        v15 = lpMem;
        if ( lpMem )
        {
          v16 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v16 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v16;
          }
          HeapFree(v16, 0, v15);
        }
      }
      v17 = GetLastError();
      LogicalImageForRootedNI = (unsigned __int16)v17 | 0x80070000;
      if ( v17 <= 0 )
        LogicalImageForRootedNI = v17;
      goto LABEL_22;
    }
    SString::ConvertToUnicode((SString *)v39);
    v18 = v41;
    LogicalImageForRootedNI = CCorSvcMgr::GetLogicalImageForRootedNI((CCorSvcMgr *)((char *)this - 16), v19, v41, &v38);
    if ( LogicalImageForRootedNI < 0 )
    {
LABEL_81:
      if ( (v40 & 8) != 0 )
        operator delete(v18);
      goto LABEL_83;
    }
    v20 = v38;
    if ( LogicalImageForRootedNI == 1 )
      v20 = 0;
    v38 = v20;
    v42[0] = 2;
    v42[1] = 2;
    v43 = 16;
    v44 = (void *)&SString::s_EmptyBuffer;
    if ( !CCorSvcMgr::GetPdbNameFromNativeImagePath(0, v9, (struct SString *)v42) )
    {
      LogicalImageForRootedNI = -2147467259;
LABEL_79:
      if ( (v43 & 8) != 0 )
        operator delete(v44);
      goto LABEL_81;
    }
    v34[0] = 2;
    v34[1] = 2;
    v35 = 16;
    lpFileName = (LPCWSTR)&SString::s_EmptyBuffer;
    SString::Set((SString *)v34, a3);
    SString::ConvertToUnicode((SString *)v42);
    v21 = v44;
    SString::ConvertToUnicode((SString *)v39);
    SString::ConvertToUnicode((SString *)v42);
    v18 = v41;
    SString::AppendPrintf((SString *)v34, L"\\%s\\%s1\\%s", v44, v41, v21);
    SString::ConvertToUnicode((SString *)v34);
    if ( GetFileAttributesW(lpFileName) != -1 )
    {
      v52 = 512;
      lpMem = v54;
      v51 = 2;
      v54[0] = 0;
      SString::ConvertToUnicode((SString *)v34);
      SString::Printf(
        (SString *)&v51,
        L"A PDB for the specified native image already exists at %s. Skipping.\n",
        lpFileName);
      SString::ConvertToUnicode((SString *)&v51);
      Logger::Log((char *)this + 192, lpMem, 2);
      if ( (v52 & 0x800000000LL) != 0 )
      {
        v22 = lpMem;
        if ( lpMem )
        {
          v23 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v23 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v23;
          }
          HeapFree(v23, 0, v22);
        }
      }
      LogicalImageForRootedNI = 0;
LABEL_77:
      if ( (v35 & 8) != 0 )
        operator delete((void *)lpFileName);
      goto LABEL_79;
    }
    if ( (v35 & 2) != 0
      && ((v35 & 7) != 7 || SString::s_IsANSIMultibyte)
      && !(unsigned int)SString::ScanASCII((SString *)v34) )
    {
      SString::ConvertToUnicode((SString *)v34);
    }
    if ( (unsigned int)((v34[0] >> ((v35 & 1) == 0)) - 1) > 0x103 )
    {
      v51 = 2;
      v52 = 512;
      lpMem = v54;
      v54[0] = 0;
      SString::ConvertToUnicode((SString *)v34);
      SString::Printf((SString *)&v51, L"Path for PDB \"%s\" is too long.\n", lpFileName);
      SString::ConvertToUnicode((SString *)&v51);
      Logger::Log((char *)this + 192, lpMem, 2);
      if ( (v52 & 0x800000000LL) != 0 )
      {
        v24 = lpMem;
        if ( lpMem )
        {
          v25 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v25 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v25;
          }
          HeapFree(v25, 0, v24);
        }
      }
      LogicalImageForRootedNI = -2147024785;
      goto LABEL_77;
    }
    v31[0] = 2;
    v31[1] = 2;
    v32 = 16;
    lpPathName = (LPCWSTR)&SString::s_EmptyBuffer;
    SString::Set((SString *)v31, a3);
    SString::GetCount((SString *)v31);
    if ( (unsigned __int16)SString::operator[]((SString *)v31) != 92 )
    {
      SString::GetCount((SString *)v31);
      if ( (unsigned __int16)SString::operator[]((SString *)v31) != 47 )
        SString::AppendPrintf((SString *)v31, L"\\");
    }
    SString::ConvertToUnicode((SString *)v31);
    v26 = (WCHAR *)lpPathName;
    if ( !CreateDirectoryW(lpPathName, 0) && GetLastError() != 183 )
      goto LABEL_57;
    SString::ConvertToUnicode((SString *)v42);
    SString::AppendPrintf((SString *)v31, L"%s\\", v44);
    SString::ConvertToUnicode((SString *)v31);
    v26 = (WCHAR *)lpPathName;
    if ( !CreateDirectoryW(lpPathName, 0) && GetLastError() != 183 )
      goto LABEL_57;
    SString::ConvertToUnicode((SString *)v39);
    SString::AppendPrintf((SString *)v31, L"%s1\\", v41);
    SString::ConvertToUnicode((SString *)v31);
    v26 = (WCHAR *)lpPathName;
    if ( !CreateDirectoryW(lpPathName, 0) && GetLastError() != 183 )
    {
LABEL_57:
      v52 = 512;
      lpMem = v54;
      v51 = 2;
      v54[0] = 0;
      SString::Printf((SString *)&v51, L"Unable to create directory for NGEN PDB.\n");
      SString::ConvertToUnicode((SString *)&v51);
      Logger::Log((char *)this + 192, lpMem, 2);
      if ( (v52 & 0x800000000LL) != 0 )
        operator delete(lpMem);
      v27 = GetLastError();
      LogicalImageForRootedNI = (unsigned __int16)v27 | 0x80070000;
      if ( v27 <= 0 )
        LogicalImageForRootedNI = v27;
LABEL_74:
      if ( (v32 & 8) != 0 )
        operator delete(v26);
      v18 = v41;
      goto LABEL_77;
    }
    SString::ConvertToUnicode((SString *)v31);
    v26 = (WCHAR *)lpPathName;
    v28 = SysAllocString(lpPathName);
    v29 = v28;
    v47 = v28;
    v30 = v28 != 0;
    v48 = v30;
    if ( !v28 )
    {
      LogicalImageForRootedNI = -2147024882;
LABEL_71:
      if ( v30 )
      {
        SysFreeString(v29);
        v48 = 0;
      }
      v10 = v37;
      goto LABEL_74;
    }
    LogicalImageForRootedNI = CCorSvcMgr::CreatePdbForLogicalImage(
                                (CCorSvcMgr *)((char *)this - 16),
                                v38,
                                v9,
                                v28,
                                v45,
                                v46);
    if ( LogicalImageForRootedNI >= 0 )
    {
      SString::ConvertToUnicode((SString *)v34);
      if ( GetFileAttributesW(lpFileName) != -1 )
      {
        SString::ConvertToUnicode((SString *)v31);
        v26 = (WCHAR *)lpPathName;
        Logger::Printf((CCorSvcMgr *)((char *)this + 192), L"PDB generated in directory %s\n", lpPathName);
        goto LABEL_71;
      }
      v52 = 512;
      lpMem = v54;
      v51 = 2;
      v54[0] = 0;
      SString::Printf((SString *)&v51, L"Incorrect PDB generated.");
      SString::ConvertToUnicode((SString *)&v51);
      Logger::Log((char *)this + 192, lpMem, 2);
    }
    else
    {
      v52 = 512;
      lpMem = v54;
      v51 = 2;
      v54[0] = 0;
      SString::Printf((SString *)&v51, L"Unable to create PDB.\n");
      SString::ConvertToUnicode((SString *)&v51);
      Logger::Log((char *)this + 192, lpMem, 2);
    }
    if ( (v52 & 0x800000000LL) != 0 )
      operator delete(lpMem);
    goto LABEL_71;
  }
  LogicalImageForRootedNI = -2147024882;
LABEL_83:
  if ( v10 )
  {
    SysFreeString(v9);
    v50 = 0;
  }
  return LogicalImageForRootedNI;
}

```

## disassembly

```asm
0x180020480  mov     [rsp-8+arg_18], rbx
0x180020485  push    rbp
0x180020486  push    rsi
0x180020487  push    rdi
0x180020488  push    r12
0x18002048a  push    r13
0x18002048c  push    r14
0x18002048e  push    r15
0x180020490  lea     rbp, [rsp-410h]
0x180020498  sub     rsp, 510h
0x18002049f  mov     rax, cs:__security_cookie
0x1800204a6  xor     rax, rsp
0x1800204a9  mov     [rbp+440h+var_40], rax
0x1800204b0  mov     [rbp+440h+var_4A0], r9d
0x1800204b4  mov     r14, r8
0x1800204b7  mov     rax, rdx
0x1800204ba  mov     rsi, rcx
0x1800204bd  mov     rcx, [rbp+440h+arg_20]
0x1800204c4  mov     [rbp+440h+var_498], rcx
0x1800204c8  xor     r15d, r15d
0x1800204cb  test    rdx, rdx
0x1800204ce  jz      loc_180020DBF
0x1800204d4  test    r8, r8
0x1800204d7  jz      loc_180020DBF
0x1800204dd  xor     r9d, r9d; lpFilePart
0x1800204e0  lea     r8, [rbp+440h+Buffer]; lpBuffer
0x1800204e7  mov     edx, 104h; nBufferLength
0x1800204ec  mov     rcx, rax; lpFileName
0x1800204ef  call    cs:__imp_GetFullPathNameW
0x1800204f5  test    eax, eax
0x1800204f7  jnz     short loc_180020504
0x1800204f9  call    cs:__imp_GetLastError
0x1800204ff  jmp     loc_180020DC4
0x180020504  lea     rcx, [rbp+440h+Buffer]; psz
0x18002050b  call    cs:__imp_SysAllocString
0x180020511  mov     r13, rax
0x180020514  mov     [rbp+440h+var_480], rax
0x180020518  mov     [rbp+440h+var_478], r15d
0x18002051c  mov     r12d, r15d
0x18002051f  mov     eax, 1
0x180020524  test    r13, r13
0x180020527  cmovnz  r12d, eax
0x18002052b  mov     [rsp+540h+var_4E0], r12d
0x180020530  mov     [rbp+440h+var_478], r12d
0x180020534  jnz     short loc_180020540
0x180020536  mov     ebx, 8007000Eh
0x18002053b  jmp     loc_180020DA9
0x180020540  mov     [rsp+540h+var_4D8], r15
0x180020545  mov     ebx, 2
0x18002054a  mov     [rsp+540h+var_4D0], ebx
0x18002054e  mov     [rsp+540h+var_4CC], ebx
0x180020552  mov     [rsp+540h+var_4C8], 10h
0x18002055a  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180020561  mov     [rbp+440h+var_4C0], rax
0x180020565  lea     r8, [rsp+540h+var_4D0]; struct SString *
0x18002056a  mov     rdx, r13; unsigned __int16 *
0x18002056d  call    ?GetNativeImageSignatureFromNativeImagePath@CCorSvcMgr@@AEAA_NPEAGPEAVSString@@@Z; CCorSvcMgr::GetNativeImageSignatureFromNativeImagePath(ushort *,SString *)
0x180020572  mov     dil, 8
0x180020575  test    al, al
0x180020577  jnz     loc_18002060D
0x18002057d  mov     [rbp+440h+var_470], r15
0x180020581  mov     [rbp+440h+var_470+4], 200h
0x180020589  mov     [rbp+440h+lpMem], r15
0x18002058d  lea     rax, [rbp+440h+var_458]
0x180020591  mov     [rbp+440h+lpMem], rax
0x180020595  mov     dword ptr [rbp+440h+var_470], ebx
0x180020598  mov     rax, [rbp+440h+lpMem]
0x18002059c  mov     [rax], r15w
0x1800205a0  lea     rdx, aTheSpecifiedNa; "The specified native image is not valid"...
0x1800205a7  lea     rcx, [rbp+440h+var_470]; this
0x1800205ab  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x1800205b0  lea     rcx, [rbp+440h+var_470]; this
0x1800205b4  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800205b9  lea     rcx, [rsi+0C0h]
0x1800205c0  mov     r8d, ebx
0x1800205c3  mov     rdx, [rbp+440h+lpMem]
0x1800205c7  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x1800205cc  nop
0x1800205cd  test    [rbp+440h+var_468], dil
0x1800205d1  jz      short loc_180020603
0x1800205d3  mov     rbx, [rbp+440h+lpMem]
0x1800205d7  test    rbx, rbx
0x1800205da  jz      short loc_180020603
0x1800205dc  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800205e3  test    rax, rax
0x1800205e6  jnz     short loc_1800205F5
0x1800205e8  call    cs:__imp_GetProcessHeap
0x1800205ee  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800205f5  mov     r8, rbx; lpMem
0x1800205f8  xor     edx, edx; dwFlags
0x1800205fa  mov     rcx, rax; hHeap
0x1800205fd  call    cs:__imp_HeapFree
0x180020603  mov     ebx, 80004005h
0x180020608  jmp     loc_1800206C9
0x18002060d  mov     rcx, r13; lpFileName
0x180020610  call    cs:__imp_GetFileAttributesW
0x180020616  cmp     eax, 0FFFFFFFFh
0x180020619  jnz     loc_1800206D2
0x18002061f  mov     [rbp+440h+var_470], r15
0x180020623  mov     [rbp+440h+var_470+4], 200h
0x18002062b  mov     [rbp+440h+lpMem], r15
0x18002062f  lea     rax, [rbp+440h+var_458]
0x180020633  mov     [rbp+440h+lpMem], rax
0x180020637  mov     dword ptr [rbp+440h+var_470], ebx
0x18002063a  mov     rax, [rbp+440h+lpMem]
0x18002063e  mov     [rax], r15w
0x180020642  call    cs:__imp_GetLastError
0x180020648  mov     r9d, eax
0x18002064b  lea     r8, [rbp+440h+Buffer]
0x180020652  lea     rdx, aCanNotFindNati; "Can not find native image '%s'.  Error="...
0x180020659  lea     rcx, [rbp+440h+var_470]; this
0x18002065d  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180020662  lea     rcx, [rbp+440h+var_470]; this
0x180020666  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002066b  lea     rcx, [rsi+0C0h]
0x180020672  mov     r8d, ebx
0x180020675  mov     rdx, [rbp+440h+lpMem]
0x180020679  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x18002067e  nop
0x18002067f  test    [rbp+440h+var_468], dil
0x180020683  jz      short loc_1800206B5
0x180020685  mov     rbx, [rbp+440h+lpMem]
0x180020689  test    rbx, rbx
0x18002068c  jz      short loc_1800206B5
0x18002068e  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180020695  test    rax, rax
0x180020698  jnz     short loc_1800206A7
0x18002069a  call    cs:__imp_GetProcessHeap
0x1800206a0  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800206a7  mov     r8, rbx; lpMem
0x1800206aa  xor     edx, edx; dwFlags
0x1800206ac  mov     rcx, rax; hHeap
0x1800206af  call    cs:__imp_HeapFree
0x1800206b5  call    cs:__imp_GetLastError
0x1800206bb  movzx   ebx, ax
0x1800206be  or      ebx, 80070000h
0x1800206c4  test    eax, eax
0x1800206c6  cmovle  ebx, eax
0x1800206c9  mov     r15, [rbp+440h+var_4C0]
0x1800206cd  jmp     loc_180020D97
0x1800206d2  lea     rcx, [rsp+540h+var_4D0]; this
0x1800206d7  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800206dc  lea     rcx, [rsi-10h]; this
0x1800206e0  lea     r9, [rsp+540h+var_4D8]; struct LogicalImage **
0x1800206e5  mov     r15, [rbp+440h+var_4C0]
0x1800206e9  mov     r8, r15; unsigned __int16 *
0x1800206ec  call    ?GetLogicalImageForRootedNI@CCorSvcMgr@@AEAAJPEBG0PEAPEAVLogicalImage@@@Z; CCorSvcMgr::GetLogicalImageForRootedNI(ushort const *,ushort const *,LogicalImage * *)
0x1800206f1  mov     ebx, eax
0x1800206f3  xor     ecx, ecx; this
0x1800206f5  test    eax, eax
0x1800206f7  js      loc_180020D97
0x1800206fd  mov     rax, [rsp+540h+var_4D8]
0x180020702  lea     edx, [rcx+1]
0x180020705  cmp     ebx, edx
0x180020707  cmovz   rax, rcx
0x18002070b  mov     [rsp+540h+var_4D8], rax
0x180020710  lea     ebx, [rcx+2]
0x180020713  mov     [rbp+440h+var_4B8], ebx
0x180020716  mov     [rbp+440h+var_4B4], ebx
0x180020719  mov     [rbp+440h+var_4B0], 10h
0x180020720  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180020727  mov     [rbp+440h+var_4A8], rax
0x18002072b  lea     r8, [rbp+440h+var_4B8]; struct SString *
0x18002072f  mov     rdx, r13; unsigned __int16 *
0x180020732  call    ?GetPdbNameFromNativeImagePath@CCorSvcMgr@@AEAA_NPEAGPEAVSString@@@Z; CCorSvcMgr::GetPdbNameFromNativeImagePath(ushort *,SString *)
0x180020737  mov     dil, 8
0x18002073a  test    al, al
0x18002073c  jnz     short loc_180020748
0x18002073e  mov     ebx, 80004005h
0x180020743  jmp     loc_180020D87
0x180020748  mov     [rsp+540h+var_4F8], ebx
0x18002074c  mov     [rsp+540h+var_4F4], ebx
0x180020750  mov     [rsp+540h+var_4F0], 10h
0x180020758  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18002075f  mov     [rsp+540h+lpFileName], rax
0x180020764  mov     rdx, r14; unsigned __int16 *
0x180020767  lea     rcx, [rsp+540h+var_4F8]; this
0x18002076c  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180020771  nop
0x180020772  lea     rcx, [rbp+440h+var_4B8]; this
0x180020776  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002077b  mov     rbx, [rbp+440h+var_4A8]
0x18002077f  lea     rcx, [rsp+540h+var_4D0]; this
0x180020784  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180020789  lea     rcx, [rbp+440h+var_4B8]; this
0x18002078d  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180020792  mov     qword ptr [rsp+540h+var_520], rbx
0x180020797  mov     r15, [rbp+440h+var_4C0]
0x18002079b  mov     r9, r15
0x18002079e  mov     r8, [rbp+440h+var_4A8]
0x1800207a2  lea     rdx, aSS1S; "\\%s\\%s1\\%s"
0x1800207a9  lea     rcx, [rsp+540h+var_4F8]; this
0x1800207ae  call    ?AppendPrintf@SString@@QEAAXPEBGZZ; SString::AppendPrintf(ushort const *,...)
0x1800207b3  lea     rcx, [rsp+540h+var_4F8]; this
0x1800207b8  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800207bd  mov     rcx, [rsp+540h+lpFileName]; lpFileName
0x1800207c2  call    cs:__imp_GetFileAttributesW
0x1800207c8  cmp     eax, 0FFFFFFFFh
0x1800207cb  jz      loc_180020875
0x1800207d1  xor     r14d, r14d
0x1800207d4  mov     [rbp+440h+var_470], r14
0x1800207d8  mov     [rbp+440h+var_470+4], 200h
0x1800207e0  mov     [rbp+440h+lpMem], r14
0x1800207e4  lea     rax, [rbp+440h+var_458]
0x1800207e8  mov     [rbp+440h+lpMem], rax
0x1800207ec  lea     ebx, [r14+2]
0x1800207f0  mov     dword ptr [rbp+440h+var_470], ebx
0x1800207f3  mov     rax, [rbp+440h+lpMem]
0x1800207f7  mov     [rax], r14w
0x1800207fb  lea     rcx, [rsp+540h+var_4F8]; this
0x180020800  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180020805  mov     r8, [rsp+540h+lpFileName]
0x18002080a  lea     rdx, aAPdbForTheSpec; "A PDB for the specified native image al"...
0x180020811  lea     rcx, [rbp+440h+var_470]; this
0x180020815  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18002081a  lea     rcx, [rbp+440h+var_470]; this
0x18002081e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180020823  lea     rcx, [rsi+0C0h]
0x18002082a  mov     r8d, ebx
0x18002082d  mov     rdx, [rbp+440h+lpMem]
0x180020831  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x180020836  nop
0x180020837  test    [rbp+440h+var_468], dil
0x18002083b  jz      short loc_18002086D
0x18002083d  mov     rbx, [rbp+440h+lpMem]
0x180020841  test    rbx, rbx
0x180020844  jz      short loc_18002086D
0x180020846  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002084d  test    rax, rax
0x180020850  jnz     short loc_18002085F
0x180020852  call    cs:__imp_GetProcessHeap
0x180020858  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002085f  mov     r8, rbx; lpMem
0x180020862  xor     edx, edx; dwFlags
0x180020864  mov     rcx, rax; hHeap
0x180020867  call    cs:__imp_HeapFree
0x18002086d  mov     ebx, r14d
0x180020870  jmp     loc_180020D75
0x180020875  mov     eax, [rsp+540h+var_4F0]
0x180020879  xor     ebx, ebx
0x18002087b  test    al, 2
0x18002087d  jz      short loc_1800208A6
0x18002087f  and     eax, 7
0x180020882  cmp     al, 7
0x180020884  jnz     short loc_18002088E
0x180020886  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, ebx; int SString::s_IsANSIMultibyte
0x18002088c  jz      short loc_1800208A6
0x18002088e  lea     rcx, [rsp+540h+var_4F8]; this
0x180020893  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x180020898  test    eax, eax
0x18002089a  jnz     short loc_1800208A6
0x18002089c  lea     rcx, [rsp+540h+var_4F8]; this
0x1800208a1  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800208a6  mov     ecx, [rsp+540h+var_4F0]
0x1800208aa  not     ecx
0x1800208ac  mov     r8d, 1
0x1800208b2  and     ecx, r8d
0x1800208b5  mov     edx, [rsp+540h+var_4F8]
0x1800208b9  shr     edx, cl
0x1800208bb  sub     edx, r8d
0x1800208be  cmp     edx, 103h
0x1800208c4  jbe     loc_180020970
0x1800208ca  and     [rbp+440h+var_470], 0
0x1800208cf  mov     [rbp+440h+var_470+4], 200h
0x1800208d7  mov     [rbp+440h+lpMem], rbx
0x1800208db  lea     rax, [rbp+440h+var_458]
0x1800208df  mov     [rbp+440h+lpMem], rax
0x1800208e3  mov     dword ptr [rbp+440h+var_470], 2
0x1800208ea  mov     rax, [rbp+440h+lpMem]
0x1800208ee  mov     [rax], bx
0x1800208f1  lea     rcx, [rsp+540h+var_4F8]; this
0x1800208f6  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800208fb  mov     r8, [rsp+540h+lpFileName]
0x180020900  lea     rdx, aPathForPdbSIsT; "Path for PDB \"%s\" is too long.\n"
0x180020907  lea     rcx, [rbp+440h+var_470]; this
0x18002090b  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180020910  lea     rcx, [rbp+440h+var_470]; this
0x180020914  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180020919  lea     rcx, [rsi+0C0h]
0x180020920  mov     r8d, 2
0x180020926  mov     rdx, [rbp+440h+lpMem]
0x18002092a  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x18002092f  nop
0x180020930  test    [rbp+440h+var_468], dil
0x180020934  jz      short loc_180020966
0x180020936  mov     rbx, [rbp+440h+lpMem]
0x18002093a  test    rbx, rbx
0x18002093d  jz      short loc_180020966
0x18002093f  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180020946  test    rax, rax
0x180020949  jnz     short loc_180020958
0x18002094b  call    cs:__imp_GetProcessHeap
0x180020951  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180020958  mov     r8, rbx; lpMem
0x18002095b  xor     edx, edx; dwFlags
0x18002095d  mov     rcx, rax; hHeap
0x180020960  call    cs:__imp_HeapFree
0x180020966  mov     ebx, 8007006Fh
0x18002096b  jmp     loc_180020D75
0x180020970  mov     r15d, 2
  ... truncated ...
```
