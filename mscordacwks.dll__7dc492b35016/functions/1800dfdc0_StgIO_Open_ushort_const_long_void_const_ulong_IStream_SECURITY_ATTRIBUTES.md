# StgIO::Open(ushort const *,long,void const *,ulong,IStream *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800dfdc0`
- end: `0x1800e03a0`
- name: `?Open@StgIO@@QEAAJPEBGJPEBXKPEAUIStream@@PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1504`
- prototype: `__int64 __usercall@<rax>(StgIO *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, const void *@<r9>, unsigned int, struct IStream *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b1ab4`
- `0x1800c62d8`
- `0x1800ddd8c`
- `0x1800deea4`
- `0x1800e05e4`

## callees

- `0x18007262c`
- `0x180072f34`
- `0x18007b1bc`
- `0x1800dfdc0`
- `0x1800e03f0`
- `0x1800e09d8`
- `0x1800f0490`
- `0x1800f0d20`
- `0x180106100`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x1800e020b`
- `KERNEL32!UnmapViewOfFile` at `0x1800e0265`
- `KERNEL32!UnmapViewOfFile` at `0x1800e020b`
- `KERNEL32!UnmapViewOfFile` at `0x1800e0265`
- `KERNEL32!MapViewOfFile` at `0x1800e01a5`
- `KERNEL32!MapViewOfFile` at `0x1800e01a5`
- `KERNEL32!CreateFileMappingW` at `0x1800e0148`
- `KERNEL32!CreateFileMappingW` at `0x1800e0148`
- `KERNEL32!SetFilePointer` at `0x1800dffd7`
- `KERNEL32!SetFilePointer` at `0x1800dffd7`
- `KERNEL32!GetLastError` at `0x1800dff38`
- `KERNEL32!GetLastError` at `0x1800e00fc`
- `KERNEL32!GetLastError` at `0x1800e016a`
- `KERNEL32!GetLastError` at `0x1800e0172`
- `KERNEL32!GetLastError` at `0x1800e01c7`
- `KERNEL32!GetLastError` at `0x1800dff38`
- `KERNEL32!GetLastError` at `0x1800e00fc`
- `KERNEL32!GetLastError` at `0x1800e016a`
- `KERNEL32!GetLastError` at `0x1800e0172`
- `KERNEL32!GetLastError` at `0x1800e01c7`
- `KERNEL32!GetModuleHandleW` at `0x1800e001d`
- `KERNEL32!GetModuleHandleW` at `0x1800e001d`
- `KERNEL32!GetProcAddress` at `0x1800e0032`
- `KERNEL32!GetProcAddress` at `0x1800e0061`
- `KERNEL32!GetProcAddress` at `0x1800e00ea`
- `KERNEL32!GetProcAddress` at `0x1800e0032`
- `KERNEL32!GetProcAddress` at `0x1800e0061`
- `KERNEL32!GetProcAddress` at `0x1800e00ea`
- `KERNEL32!CloseHandle` at `0x1800e022a`
- `KERNEL32!CloseHandle` at `0x1800e024b`
- `KERNEL32!CloseHandle` at `0x1800e0277`
- `KERNEL32!CloseHandle` at `0x1800e022a`
- `KERNEL32!CloseHandle` at `0x1800e024b`
- `KERNEL32!CloseHandle` at `0x1800e0277`
- `KERNEL32!LoadLibraryExW` at `0x1800e004c`
- `KERNEL32!LoadLibraryExW` at `0x1800e00d5`
- `KERNEL32!LoadLibraryExW` at `0x1800e004c`
- `KERNEL32!LoadLibraryExW` at `0x1800e00d5`
- `KERNEL32!CreateFileW` at `0x1800dff28`
- `KERNEL32!CreateFileW` at `0x1800dff9b`
- `KERNEL32!CreateFileW` at `0x1800dff28`
- `KERNEL32!CreateFileW` at `0x1800dff9b`

## string_xrefs

- `0x1800e0016`: `kernel32.dll`
- `0x1800e0028`: `AddDllDirectory`
- `0x1800e0045`: `wldp.dll`
- `0x1800e00ce`: `wldp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall StgIO::Open(
        StgIO *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        struct IStream *a6)
{
  unsigned int v6; // edi
  const unsigned __int16 *v7; // r15
  int v9; // r13d
  int v10; // eax
  void *v11; // rax
  __int64 v12; // rcx
  __int64 result; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  HANDLE v16; // rax
  void *v17; // rsi
  unsigned int v18; // r12d
  DWORD v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  int v25; // eax
  FARPROC v26; // rax
  HMODULE v27; // rax
  signed int v28; // eax
  unsigned int v29; // ebx
  HANDLE FileMappingW; // rax
  void *v31; // rsi
  DWORD v32; // eax
  const void *v33; // rax
  const void *v34; // r15
  BOOL v35; // r12d
  signed int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  unsigned int v39; // r9d
  int v40; // edi
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  wchar_t *v42; // [rsp+40h] [rbp-C0h]
  unsigned int v43[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+58h] [rbp-A8h] BYREF
  void *v45; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v46; // [rsp+68h] [rbp-98h]
  unsigned int v47; // [rsp+70h] [rbp-90h]
  const void *v48; // [rsp+78h] [rbp-88h]
  BOOL v49; // [rsp+80h] [rbp-80h]
  HANDLE v50; // [rsp+88h] [rbp-78h]
  int v51; // [rsp+90h] [rbp-70h]
  wchar_t v52[264]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = a3;
  v7 = a2;
  v45 = a2;
  v9 = 0;
  if ( a4 && a5 )
  {
    *((_QWORD *)this + 15) = a4;
    *((_DWORD *)this + 32) = a5;
    if ( (a3 & 8) != 0 )
    {
      *((_QWORD *)this + 14) = a4;
      v10 = 5;
    }
    else
    {
      v10 = 4;
    }
    *((_DWORD *)this + 34) = v10;
    goto LABEL_7;
  }
  if ( a6 )
  {
    if ( (a3 & 0x10) != 0 )
    {
      *((_DWORD *)this + 32) = 0;
    }
    else
    {
      *(_QWORD *)v43 = 0;
      result = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, void **))(*(_QWORD *)a6 + 40LL))(
                 a6,
                 0,
                 2,
                 &v45);
      if ( (int)result < 0 )
        return result;
      *((_DWORD *)this + 32) = (_DWORD)v45;
    }
    *((_QWORD *)this + 10) = a6;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)a6 + 8LL))(a6);
    *((_DWORD *)this + 34) = 3;
    goto LABEL_7;
  }
  if ( !a2 || !*a2 )
  {
    v12 = 2147942487LL;
    return PostError(v12);
  }
  if ( (a3 & 0x10) != 0 )
  {
    FileW = CreateFileW(a2, 0xC0000000, 0, 0, 2 - (unsigned int)((a3 & 0x20) != 0), 0, 0);
    *((_QWORD *)this + 11) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v12 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v12 = (unsigned int)LastError;
      return PostError(v12);
    }
    *((_DWORD *)this + 34) = 1;
LABEL_7:
    if ( (v6 & 2) != 0 )
    {
LABEL_8:
      v11 = operator new(StgIO::m_iCacheSize, (const struct NoThrow *)a2);
      *((_QWORD *)this + 18) = v11;
      if ( !v11 )
      {
        StgIO::Close(this);
        v12 = 2147942414LL;
        return PostError(v12);
      }
      *((_DWORD *)this + 38) = 0;
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  if ( (a3 & 2) != 0 )
    goto LABEL_8;
  a3 = (((a3 >> 2) & 1) == 0) | 4;
  if ( *((_QWORD *)this + 13) )
  {
LABEL_83:
    *((_DWORD *)this + 33) = v6;
    if ( v7 && *v7 )
    {
      SplitPath(v7, a2, a3, a4, dwCreationDisposition, 0, 0, v52, v42);
      if ( (unsigned int)SString::CaseCompareHelper(v52, L".obj", 0, v39, 1, 0) )
      {
        if ( !(unsigned int)SString::CaseCompareHelper(v52, L".tlb", 0, (unsigned int)a4, 1, 0) )
          *(_DWORD *)this = 5;
      }
      else
      {
        *(_DWORD *)this = 4;
      }
    }
    if ( (*((_BYTE *)this + 72) & 4) == 0 )
      return 0;
    if ( ((*((_DWORD *)this + 34) - 1) & 0xFFFFFFFD) != 0 )
      return 0;
    if ( (v6 & 0x10) != 0 )
      return 0;
    v40 = StgIO::MapFileToMem(this, &v45, v43, (struct _SECURITY_ATTRIBUTES *)a4);
    if ( v40 >= 0 )
      return 0;
    StgIO::Close(this);
    return (unsigned int)v40;
  }
  v16 = CreateFileW(a2, 0x80000000, a3, 0, 3u, 0, 0);
  v17 = v16;
  v46 = v16;
  v18 = v16 != (HANDLE)-1LL;
  v43[0] = v18;
  v47 = v18;
  if ( v16 == (HANDLE)-1LL )
    goto LABEL_46;
  v19 = SetFilePointer(v16, 0, 0, 2u);
  *((_DWORD *)this + 32) = v19;
  if ( v19 )
  {
    if ( (v6 & 0x800) == 0 )
    {
LABEL_81:
      v47 = 0;
      *((_QWORD *)this + 11) = v17;
      *((_DWORD *)this + 34) = 1;
      goto LABEL_83;
    }
    v21 = dword_180162180;
    if ( dword_180162180 == -1 )
    {
      ProcAddress = (FARPROC)qword_180168510;
      if ( !qword_180168510 )
      {
        ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
        if ( ModuleHandleW
          && GetProcAddress(ModuleHandleW, "AddDllDirectory")
          && (Library = LoadLibraryExW(L"wldp.dll", 0, 0x800u)) != 0 )
        {
          ProcAddress = GetProcAddress(Library, "WldpIsDynamicCodePolicyEnabled");
          qword_180168510 = (__int64)ProcAddress;
        }
        else
        {
          ProcAddress = (FARPROC)qword_180168510;
        }
        if ( !ProcAddress )
        {
          dword_180162180 = 0;
          goto LABEL_81;
        }
      }
      v44 = 0;
      v25 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v44);
      if ( v25 < 0 )
      {
        v20 = (unsigned int)v25;
        goto LABEL_48;
      }
      v21 = v44 != 0;
      dword_180162180 = v21;
    }
    if ( v21 != 1 )
      goto LABEL_81;
    v26 = (FARPROC)qword_180168508;
    if ( !qword_180168508 )
    {
      v27 = LoadLibraryExW(L"wldp.dll", 0, 0x800u);
      if ( !v27 || (v26 = GetProcAddress(v27, "WldpQueryDynamicCodeTrust"), (qword_180168508 = (__int64)v26) == 0) )
      {
LABEL_46:
        v28 = GetLastError();
        v20 = (unsigned __int16)v28 | 0x80070000;
        if ( v28 <= 0 )
          v20 = (unsigned int)v28;
        goto LABEL_48;
      }
    }
    if ( ((int (__fastcall *)(void *, _QWORD, _QWORD))v26)(v17, 0, 0) >= 0 )
      goto LABEL_81;
    FileMappingW = CreateFileMappingW(v17, 0, 2u, 0, 0, 0);
    v31 = FileMappingW;
    v50 = FileMappingW;
    v51 = 0;
    if ( FileMappingW != (HANDLE)-1LL )
      v9 = 1;
    v51 = v9;
    if ( FileMappingW )
    {
      if ( GetLastError() != 183 )
      {
        v33 = MapViewOfFile(v31, 4u, 0, 0, 0);
        v34 = v33;
        v48 = v33;
        v35 = v33 != 0;
        v49 = v35;
        if ( v33 )
        {
          v38 = ((__int64 (__fastcall *)(_QWORD, const void *, _QWORD))qword_180168508)(
                  0,
                  v33,
                  *((unsigned int *)this + 32));
          if ( v38 >= 0 )
          {
            if ( v35 )
            {
              UnmapViewOfFile(v34);
              v49 = 0;
            }
            if ( v9 )
            {
              CloseHandle(v31);
              v51 = 0;
            }
            v7 = (const unsigned __int16 *)v45;
            v17 = v46;
            goto LABEL_81;
          }
          v37 = (unsigned int)v38;
        }
        else
        {
          v36 = GetLastError();
          v37 = (unsigned __int16)v36 | 0x80070000;
          if ( v36 <= 0 )
            v37 = (unsigned int)v36;
        }
        v29 = PostError(v37);
        if ( v35 )
        {
          UnmapViewOfFile(v34);
          v49 = 0;
        }
        v18 = v43[0];
LABEL_66:
        if ( v9 )
        {
          if ( v31 )
            CloseHandle(v31);
          v51 = 0;
        }
        v17 = v46;
        goto LABEL_71;
      }
      v32 = -2147024713;
    }
    else
    {
      v32 = GetLastError();
    }
    v29 = PostError(v32);
    goto LABEL_66;
  }
  v20 = 2148733195LL;
LABEL_48:
  v29 = PostError(v20);
LABEL_71:
  if ( v18 )
  {
    if ( v17 )
      CloseHandle(v17);
    v47 = 0;
  }
  return v29;
}

```

## disassembly

```asm
0x1800dfdc0  mov     [rsp-8+arg_18], rbx
0x1800dfdc5  push    rbp
0x1800dfdc6  push    rsi
0x1800dfdc7  push    rdi
0x1800dfdc8  push    r12
0x1800dfdca  push    r13
0x1800dfdcc  push    r14
0x1800dfdce  push    r15
0x1800dfdd0  lea     rbp, [rsp-1C0h]
0x1800dfdd8  sub     rsp, 2C0h
0x1800dfddf  mov     rax, cs:__security_cookie
0x1800dfde6  xor     rax, rsp
0x1800dfde9  mov     [rbp+1F0h+var_40], rax
0x1800dfdf0  mov     edi, r8d
0x1800dfdf3  mov     r15, rdx
0x1800dfdf6  mov     [rsp+2F0h+var_290], rdx
0x1800dfdfb  mov     rbx, rcx
0x1800dfdfe  mov     rsi, [rbp+1F0h+arg_28]
0x1800dfe05  mov     r12d, 2
0x1800dfe0b  lea     r14d, [r12-1]
0x1800dfe10  xor     r13d, r13d
0x1800dfe13  test    r9, r9
0x1800dfe16  jz      short loc_1800DFE7F
0x1800dfe18  mov     eax, [rbp+1F0h+arg_20]
0x1800dfe1e  test    eax, eax
0x1800dfe20  jz      short loc_1800DFE7F
0x1800dfe22  mov     [rcx+78h], r9
0x1800dfe26  mov     [rcx+80h], eax
0x1800dfe2c  test    dil, 8
0x1800dfe30  jz      short loc_1800DFE3D
0x1800dfe32  mov     [rcx+70h], r9
0x1800dfe36  lea     eax, [r12+3]
0x1800dfe3b  jmp     short loc_1800DFE42
0x1800dfe3d  mov     eax, 4
0x1800dfe42  mov     [rcx+88h], eax
0x1800dfe48  test    r12b, dil
0x1800dfe4b  jz      loc_1800E02AC
0x1800dfe51  movsxd  rcx, cs:?m_iCacheSize@StgIO@@0HA; dwBytes
0x1800dfe58  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800dfe5d  mov     [rbx+90h], rax
0x1800dfe64  test    rax, rax
0x1800dfe67  jnz     loc_1800E02A5
0x1800dfe6d  mov     rcx, rbx; this
0x1800dfe70  call    ?Close@StgIO@@QEAAXXZ; StgIO::Close(void)
0x1800dfe75  mov     ecx, 8007000Eh
0x1800dfe7a  jmp     loc_1800E0371
0x1800dfe7f  test    rsi, rsi
0x1800dfe82  jz      short loc_1800DFEE8
0x1800dfe84  test    dil, 10h
0x1800dfe88  jnz     short loc_1800DFEBE
0x1800dfe8a  mov     qword ptr [rsp+2F0h+var_2A0], r13
0x1800dfe8f  mov     rax, [rsi]
0x1800dfe92  lea     r9, [rsp+2F0h+var_290]
0x1800dfe97  mov     r8d, r12d
0x1800dfe9a  mov     rdx, r13
0x1800dfe9d  mov     rcx, rsi
0x1800dfea0  mov     rax, [rax+28h]
0x1800dfea4  call    cs:__guard_dispatch_icall_fptr
0x1800dfeaa  test    eax, eax
0x1800dfeac  js      loc_1800E0376
0x1800dfeb2  mov     eax, dword ptr [rsp+2F0h+var_290]
0x1800dfeb6  mov     [rbx+80h], eax
0x1800dfebc  jmp     short loc_1800DFEC5
0x1800dfebe  mov     [rcx+80h], r13d
0x1800dfec5  mov     [rbx+50h], rsi
0x1800dfec9  mov     rax, [rsi]
0x1800dfecc  mov     rcx, rsi
0x1800dfecf  mov     rax, [rax+8]
0x1800dfed3  call    cs:__guard_dispatch_icall_fptr
0x1800dfed9  mov     dword ptr [rbx+88h], 3
0x1800dfee3  jmp     loc_1800DFE48
0x1800dfee8  test    r15, r15
0x1800dfeeb  jz      loc_1800E036C
0x1800dfef1  cmp     [rdx], r13w
0x1800dfef5  jz      loc_1800E036C
0x1800dfefb  test    dil, 10h
0x1800dfeff  jz      short loc_1800DFF5D
0x1800dff01  mov     eax, edi
0x1800dff03  and     al, 20h
0x1800dff05  neg     al
0x1800dff07  sbb     ecx, ecx
0x1800dff09  add     ecx, r12d
0x1800dff0c  mov     [rsp+2F0h+hTemplateFile], r13; hTemplateFile
0x1800dff11  mov     [rsp+2F0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800dff16  mov     [rsp+2F0h+dwCreationDisposition], ecx; dwCreationDisposition
0x1800dff1a  xor     r9d, r9d; lpSecurityAttributes
0x1800dff1d  xor     r8d, r8d; dwShareMode
0x1800dff20  mov     edx, 0C0000000h; dwDesiredAccess
0x1800dff25  mov     rcx, r15; lpFileName
0x1800dff28  call    cs:__imp_CreateFileW
0x1800dff2e  mov     [rbx+58h], rax
0x1800dff32  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800dff36  jnz     short loc_1800DFF51
0x1800dff38  call    cs:__imp_GetLastError
0x1800dff3e  movzx   ecx, ax
0x1800dff41  or      ecx, 80070000h
0x1800dff47  test    eax, eax
0x1800dff49  cmovle  ecx, eax
0x1800dff4c  jmp     loc_1800E0371
0x1800dff51  mov     [rbx+88h], r14d
0x1800dff58  jmp     loc_1800DFE48
0x1800dff5d  test    r12b, dil
0x1800dff60  jnz     loc_1800DFE51
0x1800dff66  shr     r8d, 2
0x1800dff6a  not     r8d
0x1800dff6d  and     r8d, r14d
0x1800dff70  or      r8d, 4; dwShareMode
0x1800dff74  cmp     [rcx+68h], r13
0x1800dff78  jnz     loc_1800E02AC
0x1800dff7e  mov     [rsp+2F0h+hTemplateFile], r13; hTemplateFile
0x1800dff83  mov     [rsp+2F0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800dff88  mov     [rsp+2F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800dff90  xor     r9d, r9d; lpSecurityAttributes
0x1800dff93  mov     edx, 80000000h; dwDesiredAccess
0x1800dff98  mov     rcx, r15; lpFileName
0x1800dff9b  call    cs:__imp_CreateFileW
0x1800dffa1  mov     rsi, rax
0x1800dffa4  mov     [rsp+2F0h+var_288], rax
0x1800dffa9  mov     [rsp+2F0h+var_280], r13d
0x1800dffae  mov     r12d, r13d
0x1800dffb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800dffb5  cmovnz  r12d, r14d
0x1800dffb9  mov     [rsp+2F0h+var_2A0], r12d
0x1800dffbe  mov     [rsp+2F0h+var_280], r12d
0x1800dffc3  jz      loc_1800E00FC
0x1800dffc9  mov     r9d, 2; dwMoveMethod
0x1800dffcf  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800dffd2  xor     edx, edx; lDistanceToMove
0x1800dffd4  mov     rcx, rax; hFile
0x1800dffd7  call    cs:__imp_SetFilePointer
0x1800dffdd  mov     [rbx+80h], eax
0x1800dffe3  test    eax, eax
0x1800dffe5  jnz     short loc_1800DFFF1
0x1800dffe7  mov     ecx, 8013110Bh
0x1800dffec  jmp     loc_1800E0110
0x1800dfff1  bt      edi, 0Bh
0x1800dfff5  jnb     loc_1800E0293
0x1800dfffb  mov     eax, cs:dword_180162180
0x1800e0001  cmp     eax, 0FFFFFFFFh
0x1800e0004  jnz     loc_1800E00B1
0x1800e000a  mov     rax, cs:qword_180168510
0x1800e0011  test    rax, rax
0x1800e0014  jnz     short loc_1800E0088
0x1800e0016  lea     rcx, ModuleName; "kernel32.dll"
0x1800e001d  call    cs:__imp_GetModuleHandleW
0x1800e0023  test    rax, rax
0x1800e0026  jz      short loc_1800E0070
0x1800e0028  lea     rdx, aAdddlldirector; "AddDllDirectory"
0x1800e002f  mov     rcx, rax; hModule
0x1800e0032  call    cs:__imp_GetProcAddress
0x1800e0038  test    rax, rax
0x1800e003b  jz      short loc_1800E0070
0x1800e003d  xor     edx, edx; hFile
0x1800e003f  mov     r8d, 800h; dwFlags
0x1800e0045  lea     rcx, LibFileName; "wldp.dll"
0x1800e004c  call    cs:__imp_LoadLibraryExW
0x1800e0052  test    rax, rax
0x1800e0055  jz      short loc_1800E0070
0x1800e0057  lea     rdx, aWldpisdynamicc; "WldpIsDynamicCodePolicyEnabled"
0x1800e005e  mov     rcx, rax; hModule
0x1800e0061  call    cs:__imp_GetProcAddress
0x1800e0067  mov     cs:qword_180168510, rax
0x1800e006e  jmp     short loc_1800E0077
0x1800e0070  mov     rax, cs:qword_180168510
0x1800e0077  test    rax, rax
0x1800e007a  jnz     short loc_1800E0088
0x1800e007c  mov     cs:dword_180162180, r13d
0x1800e0083  jmp     loc_1800E0293
0x1800e0088  mov     [rsp+2F0h+var_298], r13d
0x1800e008d  lea     rcx, [rsp+2F0h+var_298]
0x1800e0092  call    cs:__guard_dispatch_icall_fptr
0x1800e0098  test    eax, eax
0x1800e009a  jns     short loc_1800E00A0
0x1800e009c  mov     ecx, eax
0x1800e009e  jmp     short loc_1800E0110
0x1800e00a0  mov     eax, r13d
0x1800e00a3  cmp     [rsp+2F0h+var_298], r13d
0x1800e00a8  setnz   al
0x1800e00ab  mov     cs:dword_180162180, eax
0x1800e00b1  cmp     eax, r14d
0x1800e00b4  jnz     loc_1800E0293
0x1800e00ba  mov     rax, cs:qword_180168508
0x1800e00c1  test    rax, rax
0x1800e00c4  jnz     short loc_1800E011C
0x1800e00c6  xor     edx, edx; hFile
0x1800e00c8  mov     r8d, 800h; dwFlags
0x1800e00ce  lea     rcx, LibFileName; "wldp.dll"
0x1800e00d5  call    cs:__imp_LoadLibraryExW
0x1800e00db  test    rax, rax
0x1800e00de  jz      short loc_1800E00FC
0x1800e00e0  lea     rdx, aWldpquerydynam; "WldpQueryDynamicCodeTrust"
0x1800e00e7  mov     rcx, rax; hModule
0x1800e00ea  call    cs:__imp_GetProcAddress
0x1800e00f0  mov     cs:qword_180168508, rax
0x1800e00f7  test    rax, rax
0x1800e00fa  jnz     short loc_1800E011C
0x1800e00fc  call    cs:__imp_GetLastError
0x1800e0102  movzx   ecx, ax
0x1800e0105  or      ecx, 80070000h
0x1800e010b  test    eax, eax
0x1800e010d  cmovle  ecx, eax
0x1800e0110  call    PostError
0x1800e0115  mov     ebx, eax
0x1800e0117  jmp     loc_1800E023E
0x1800e011c  xor     r8d, r8d
0x1800e011f  xor     edx, edx
0x1800e0121  mov     rcx, rsi
0x1800e0124  call    cs:__guard_dispatch_icall_fptr
0x1800e012a  test    eax, eax
0x1800e012c  jns     loc_1800E0293
0x1800e0132  mov     qword ptr [rsp+2F0h+dwFlagsAndAttributes], r13; lpName
0x1800e0137  mov     [rsp+2F0h+dwCreationDisposition], r13d; dwNumberOfBytesToMap
0x1800e013c  xor     r9d, r9d; dwMaximumSizeHigh
0x1800e013f  xor     edx, edx; lpFileMappingAttributes
0x1800e0141  lea     r8d, [r9+2]; flProtect
0x1800e0145  mov     rcx, rsi; hFile
0x1800e0148  call    cs:__imp_CreateFileMappingW
0x1800e014e  mov     rsi, rax
0x1800e0151  mov     [rbp+1F0h+var_268], rax
0x1800e0155  mov     [rbp+1F0h+var_260], r13d
0x1800e0159  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e015d  cmovnz  r13d, r14d
0x1800e0161  mov     [rbp+1F0h+var_260], r13d
0x1800e0165  test    rax, rax
0x1800e0168  jnz     short loc_1800E0172
0x1800e016a  call    cs:__imp_GetLastError
0x1800e0170  jmp     short loc_1800E0184
0x1800e0172  call    cs:__imp_GetLastError
0x1800e0178  cmp     eax, 0B7h
0x1800e017d  jnz     short loc_1800E0192
0x1800e017f  mov     eax, 800700B7h
0x1800e0184  mov     ecx, eax
0x1800e0186  call    PostError
0x1800e018b  mov     ebx, eax
0x1800e018d  jmp     loc_1800E021A
0x1800e0192  and     qword ptr [rsp+2F0h+dwCreationDisposition], 0
0x1800e0198  xor     r9d, r9d; dwFileOffsetLow
0x1800e019b  xor     r8d, r8d; dwFileOffsetHigh
0x1800e019e  lea     edx, [r9+4]; dwDesiredAccess
0x1800e01a2  mov     rcx, rsi; hFileMappingObject
0x1800e01a5  call    cs:__imp_MapViewOfFile
0x1800e01ab  mov     r15, rax
0x1800e01ae  mov     [rsp+2F0h+var_278], rax
0x1800e01b3  and     [rbp+1F0h+var_270], 0
0x1800e01b7  xor     r12d, r12d
0x1800e01ba  test    rax, rax
0x1800e01bd  cmovnz  r12d, r14d
0x1800e01c1  mov     [rbp+1F0h+var_270], r12d
0x1800e01c5  jnz     short loc_1800E01DD
0x1800e01c7  call    cs:__imp_GetLastError
0x1800e01cd  movzx   ecx, ax
0x1800e01d0  or      ecx, 80070000h
0x1800e01d6  test    eax, eax
0x1800e01d8  cmovle  ecx, eax
0x1800e01db  jmp     short loc_1800E01FC
0x1800e01dd  mov     r8d, [rbx+80h]
0x1800e01e4  mov     rdx, r15
0x1800e01e7  xor     ecx, ecx
0x1800e01e9  mov     rax, cs:qword_180168508
0x1800e01f0  call    cs:__guard_dispatch_icall_fptr
0x1800e01f6  test    eax, eax
0x1800e01f8  jns     short loc_1800E025D
0x1800e01fa  mov     ecx, eax
0x1800e01fc  call    PostError
0x1800e0201  mov     ebx, eax
0x1800e0203  test    r12d, r12d
0x1800e0206  jz      short loc_1800E0215
0x1800e0208  mov     rcx, r15; lpBaseAddress
0x1800e020b  call    cs:__imp_UnmapViewOfFile
0x1800e0211  and     [rbp+1F0h+var_270], 0
0x1800e0215  mov     r12d, [rsp+2F0h+var_2A0]
0x1800e021a  test    r13d, r13d
0x1800e021d  jz      short loc_1800E0236
0x1800e021f  xor     r13d, r13d
0x1800e0222  test    rsi, rsi
0x1800e0225  jz      short loc_1800E0230
0x1800e0227  mov     rcx, rsi; hObject
0x1800e022a  call    cs:__imp_CloseHandle
0x1800e0230  mov     [rbp+1F0h+var_260], r13d
0x1800e0234  jmp     short loc_1800E0239
0x1800e0236  xor     r13d, r13d
0x1800e0239  mov     rsi, [rsp+2F0h+var_288]
0x1800e023e  test    r12d, r12d
0x1800e0241  jz      short loc_1800E0256
0x1800e0243  test    rsi, rsi
0x1800e0246  jz      short loc_1800E0251
0x1800e0248  mov     rcx, rsi; hObject
0x1800e024b  call    cs:__imp_CloseHandle
0x1800e0251  mov     [rsp+2F0h+var_280], r13d
0x1800e0256  mov     eax, ebx
0x1800e0258  jmp     loc_1800E0376
0x1800e025d  test    r12d, r12d
0x1800e0260  jz      short loc_1800E026F
0x1800e0262  mov     rcx, r15; lpBaseAddress
0x1800e0265  call    cs:__imp_UnmapViewOfFile
0x1800e026b  and     [rbp+1F0h+var_270], 0
0x1800e026f  test    r13d, r13d
0x1800e0272  jz      short loc_1800E0286
0x1800e0274  mov     rcx, rsi; hObject
0x1800e0277  call    cs:__imp_CloseHandle
  ... truncated ...
```
