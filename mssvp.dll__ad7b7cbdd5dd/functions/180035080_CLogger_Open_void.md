# CLogger::Open(void)

- ea: `0x180035080`
- end: `0x1800351db`
- name: `?Open@CLogger@@QEAAHXZ`
- size: `347`
- prototype: `_BOOL8 __fastcall(LPCWSTR *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180034e4c`
- `0x18003533c`

## callees

- `0x1800031c0`
- `0x1800048c0`
- `0x180004d40`
- `0x1800059ec`
- `0x180018758`
- `0x180019084`
- `0x180034954`
- `0x180034aa4`
- `0x180035080`
- `0x1800351e4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800351b5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800351b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800351a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800351a0`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800350fd`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800350fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CLogger::Open(LPCWSTR *this)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  int LogLevel; // ebx
  LPCWSTR *v6; // r14
  LPCWSTR v7; // rdx
  int *v8; // rdi
  __int64 v9; // rbx
  WCHAR *FileW; // rax
  int v11; // [rsp+70h] [rbp+8h] BYREF
  char v12; // [rsp+78h] [rbp+10h] BYREF
  char v13; // [rsp+80h] [rbp+18h] BYREF
  __int64 v14; // [rsp+88h] [rbp+20h]

  v2 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
         &v12,
         this + 1);
  v14 = v2;
  v11 = 0;
  v3 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
         &v13,
         v2);
  LogLevel = CLogger::GetLogLevel(v3, &v11);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v2);
  if ( LogLevel )
  {
    CLogger::m_fLoggingEnabled = 0;
    return 0;
  }
  else
  {
    CLogger::PurgeOld((CLogger *)this);
    SHCreateDirectoryExW(0, this[3], 0);
    v6 = this + 4;
    v7 = this[3];
    v8 = (int *)(this[4] - 12);
    if ( v7 - 12 != (LPCWSTR)v8 )
    {
      if ( v8[4] >= 0 && *((_QWORD *)v7 - 3) == *(_QWORD *)v8 )
      {
        v9 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
        ATL::CStringData::Release((ATL::CStringData *)v8);
        *v6 = (LPCWSTR)(v9 + 24);
      }
      else
      {
        ATL::CSimpleStringT<wchar_t,0>::SetString(this + 4, v7, *((unsigned int *)v7 - 4));
      }
    }
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(this + 4, "\\");
    ATL::CSimpleStringT<wchar_t,0>::Append(this + 4, this[1], *((unsigned int *)this[1] - 4));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(this + 4, ".txt");
    FileW = (WCHAR *)CreateFileW(*v6, 4u, 3u, 0, 4u, 0x80u, 0);
    this[6] = FileW;
    if ( FileW != (WCHAR *)-1LL )
    {
      *((_DWORD *)this + 15) = GetFileSize(FileW, 0);
      *((_DWORD *)this + 16) = 0;
    }
    return (LPCWSTR)((char *)this[6] + 1) != 0;
  }
}

```

## disassembly

```asm
0x180035080  push    rbx
0x180035082  push    rsi
0x180035083  push    rdi
0x180035084  push    r14
0x180035086  push    r15
0x180035088  sub     rsp, 40h
0x18003508c  mov     rsi, rcx
0x18003508f  lea     rdx, [rcx+8]
0x180035093  lea     rcx, [rsp+68h+arg_8]
0x180035098  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18003509d  mov     rdi, rax
0x1800350a0  mov     [rsp+68h+arg_18], rax
0x1800350a8  mov     [rsp+68h+arg_0], 0
0x1800350b0  mov     rdx, rax
0x1800350b3  lea     rcx, [rsp+68h+arg_10]
0x1800350bb  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800350c0  lea     rdx, [rsp+68h+arg_0]
0x1800350c5  mov     rcx, rax
0x1800350c8  call    ?GetLogLevel@CLogger@@CAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAW4LogLevel@@@Z; CLogger::GetLogLevel(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,LogLevel *)
0x1800350cd  mov     ebx, eax
0x1800350cf  mov     rcx, rdi
0x1800350d2  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x1800350d7  test    ebx, ebx
0x1800350d9  jz      short loc_1800350EC
0x1800350db  mov     cs:?m_fLoggingEnabled@CLogger@@0HA, 0; int CLogger::m_fLoggingEnabled
0x1800350e5  xor     eax, eax
0x1800350e7  jmp     loc_1800351CF
0x1800350ec  mov     rcx, rsi; this
0x1800350ef  call    ?PurgeOld@CLogger@@QEAAXXZ; CLogger::PurgeOld(void)
0x1800350f4  xor     r8d, r8d; psa
0x1800350f7  mov     rdx, [rsi+18h]; pszPath
0x1800350fb  xor     ecx, ecx; hwnd
0x1800350fd  call    cs:__imp_SHCreateDirectoryExW
0x180035103  lea     r14, [rsi+20h]
0x180035107  mov     rdx, [rsi+18h]
0x18003510b  lea     rcx, [rdx-18h]
0x18003510f  mov     rdi, [r14]
0x180035112  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180035116  cmp     rcx, rdi
0x180035119  jz      short loc_18003514E
0x18003511b  cmp     dword ptr [rdi+10h], 0
0x18003511f  jl      short loc_180035142
0x180035121  mov     rax, [rdi]
0x180035124  cmp     [rcx], rax
0x180035127  jnz     short loc_180035142
0x180035129  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x18003512e  mov     rbx, rax
0x180035131  mov     rcx, rdi; this
0x180035134  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180035139  lea     rax, [rbx+18h]
0x18003513d  mov     [r14], rax
0x180035140  jmp     short loc_18003514E
0x180035142  mov     r8d, [rdx-10h]
0x180035146  mov     rcx, r14
0x180035149  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18003514e  lea     rdx, asc_180047FEC; "\\"
0x180035155  mov     rcx, r14
0x180035158  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x18003515d  mov     rdx, [rsi+8]
0x180035161  mov     r8d, [rdx-10h]
0x180035165  mov     rcx, r14
0x180035168  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x18003516d  lea     rdx, aTxt_1; ".txt"
0x180035174  mov     rcx, r14
0x180035177  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x18003517c  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180035185  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003518d  mov     edx, 4; dwDesiredAccess
0x180035192  mov     [rsp+68h+dwCreationDisposition], edx; dwCreationDisposition
0x180035196  xor     r9d, r9d; lpSecurityAttributes
0x180035199  lea     r8d, [rdx-1]; dwShareMode
0x18003519d  mov     rcx, [r14]; lpFileName
0x1800351a0  call    cs:__imp_CreateFileW
0x1800351a6  mov     [rsi+30h], rax
0x1800351aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800351ae  jz      short loc_1800351C5
0x1800351b0  xor     edx, edx; lpFileSizeHigh
0x1800351b2  mov     rcx, rax; hFile
0x1800351b5  call    cs:__imp_GetFileSize
0x1800351bb  mov     [rsi+3Ch], eax
0x1800351be  mov     dword ptr [rsi+40h], 0
0x1800351c5  xor     eax, eax
0x1800351c7  cmp     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x1800351cc  setnz   al
0x1800351cf  add     rsp, 40h
0x1800351d3  pop     r15
0x1800351d5  pop     r14
0x1800351d7  pop     rdi
0x1800351d8  pop     rsi
0x1800351d9  pop     rbx
0x1800351da  retn
```
