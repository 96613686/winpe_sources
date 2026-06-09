# SxCheckTrimSupportForVolume(ushort const *,int *)

- ea: `0x18001c17c`
- end: `0x18001c35a`
- name: `?SxCheckTrimSupportForVolume@@YAJPEBGPEAH@Z`
- size: `478`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001c07c`
- `0x18002d220`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180017e34`
- `0x1800192b4`
- `0x180019ae4`
- `0x18001a630`
- `0x18001b590`
- `0x18001c17c`
- `0x180067af2`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c2c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c2c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c335`

## pseudocode

```c
__int64 __fastcall SxCheckTrimSupportForVolume(const unsigned __int16 *Src, int *a2)
{
  int *v2; // rdi
  WCHAR *v4; // r14
  __int64 FileW; // rbx
  __int16 v6; // ax
  int LastFailureAsHRESULT; // esi
  __int64 v8; // r15
  int v9; // eax
  int v10; // r13d
  WCHAR *v11; // rdi
  int v12; // r13d
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  LPCWSTR lpFileName; // [rsp+40h] [rbp-39h] BYREF
  __int64 v20; // [rsp+48h] [rbp-31h]
  int v21; // [rsp+50h] [rbp-29h] BYREF
  __int16 v22; // [rsp+54h] [rbp-25h]
  __int16 v23; // [rsp+56h] [rbp-23h]

  v2 = a2;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "SxCheckTrimSupportForVolume", 2347, 1);
  v4 = (WCHAR *)&qword_18006F470;
  FileW = -1;
  lpFileName = &qword_18006F470;
  v20 = 0;
  v6 = 2351;
  if ( !Src || (v22 = 2351, v6 = 2352, !v2) )
  {
    LastFailureAsHRESULT = -2147024809;
    v21 = -2147024809;
    goto LABEL_3;
  }
  v21 = 0;
  v22 = 2352;
  *v2 = 0;
  v8 = -1;
  do
    ++v8;
  while ( Src[v8] );
  LastFailureAsHRESULT = 0;
  if ( !(_DWORD)v8
    || (v9 = CBsString::ExtendBuffer((const void **)&lpFileName, (int)v8 + 1),
        v4 = (WCHAR *)lpFileName,
        LastFailureAsHRESULT = v9,
        v9 < 0) )
  {
    v21 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v12 = v20;
      goto LABEL_13;
    }
    v6 = 2355;
LABEL_3:
    v23 = v6;
    goto LABEL_20;
  }
  v10 = v20;
  v11 = (WCHAR *)&lpFileName[(unsigned int)v20];
  memcpy_0(v11, Src, 2LL * (unsigned int)v8);
  v11[(unsigned int)v8] = 0;
  v12 = v8 + v10;
  v2 = a2;
  LODWORD(v20) = v12;
  v21 = LastFailureAsHRESULT;
LABEL_13:
  v22 = 2355;
  if ( v12 )
  {
    v13 = (unsigned int)(v12 - 1);
    if ( v4[v13] == 92 )
    {
      CBsString::SetLength((CBsString *)&lpFileName, v13);
      v4 = (WCHAR *)lpFileName;
    }
  }
  FileW = (__int64)CreateFileW(v4, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15, v14, v16, v17);
    v21 = LastFailureAsHRESULT;
    v6 = 2367;
    goto LABEL_3;
  }
  v21 = 0;
  v22 = 2367;
  LastFailureAsHRESULT = SxCheckTrimSupport((HANDLE)FileW, v2);
  v21 = LastFailureAsHRESULT;
  v6 = 2369;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v22 = 2369;
LABEL_20:
  CBsString::_FreeData(v4);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001c17c  mov     [rsp-8+arg_8], rdx
0x18001c181  push    rbp
0x18001c182  push    rbx
0x18001c183  push    rsi
0x18001c184  push    rdi
0x18001c185  push    r12
0x18001c187  push    r13
0x18001c189  push    r14
0x18001c18b  push    r15
0x18001c18d  lea     rbp, [rsp-1Fh]
0x18001c192  sub     rsp, 98h
0x18001c199  mov     rdi, rdx
0x18001c19c  mov     r12, rcx
0x18001c19f  lea     rdx, aSxchecktrimsup_0; "SxCheckTrimSupportForVolume"
0x18001c1a6  mov     r9d, 1; unsigned __int16
0x18001c1ac  lea     rcx, [rbp+57h+var_80]; this
0x18001c1b0  mov     r8d, 92Bh; unsigned __int16
0x18001c1b6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001c1bb  xor     r13d, r13d
0x18001c1be  lea     r14, qword_18006F470
0x18001c1c5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c1c9  mov     [rbp+57h+lpFileName], r14
0x18001c1cd  mov     [rbp+57h+var_88], r13
0x18001c1d1  mov     eax, 92Fh
0x18001c1d6  test    r12, r12
0x18001c1d9  jnz     short loc_18001C1EC
0x18001c1db  mov     esi, 80070057h
0x18001c1e0  mov     [rbp+57h+var_80], esi
0x18001c1e3  mov     [rbp+57h+var_7A], ax
0x18001c1e7  jmp     loc_18001C320
0x18001c1ec  mov     [rbp+57h+var_7C], ax
0x18001c1f0  mov     eax, 930h
0x18001c1f5  test    rdi, rdi
0x18001c1f8  jz      short loc_18001C1DB
0x18001c1fa  mov     [rbp+57h+var_80], r13d
0x18001c1fe  mov     [rbp+57h+var_7C], ax
0x18001c202  mov     [rdi], r13d
0x18001c205  mov     r15, rbx
0x18001c208  inc     r15
0x18001c20b  cmp     [r12+r15*2], r13w
0x18001c210  jnz     short loc_18001C208
0x18001c212  mov     esi, r13d
0x18001c215  test    r15d, r15d
0x18001c218  jz      short loc_18001C264
0x18001c21a  lea     edx, [r15+1]; unsigned int
0x18001c21e  lea     rcx, [rbp+57h+lpFileName]; this
0x18001c222  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18001c227  mov     r14, [rbp+57h+lpFileName]
0x18001c22b  mov     esi, eax
0x18001c22d  test    eax, eax
0x18001c22f  js      short loc_18001C264
0x18001c231  mov     r13d, dword ptr [rbp+57h+var_88]
0x18001c235  mov     rdx, r12; Src
0x18001c238  mov     eax, r15d
0x18001c23b  lea     rdi, [r14+r13*2]
0x18001c23f  lea     rbx, [rax+rax]
0x18001c243  mov     rcx, rdi; void *
0x18001c246  mov     r8, rbx; Size
0x18001c249  call    memcpy_0
0x18001c24e  xor     eax, eax
0x18001c250  mov     [rbx+rdi], ax
0x18001c254  add     r13d, r15d
0x18001c257  mov     rdi, [rbp+57h+arg_8]
0x18001c25b  mov     dword ptr [rbp+57h+var_88], r13d
0x18001c25f  mov     [rbp+57h+var_80], esi
0x18001c262  jmp     short loc_18001C279
0x18001c264  mov     [rbp+57h+var_80], esi
0x18001c267  test    esi, esi
0x18001c269  jns     short loc_18001C275
0x18001c26b  mov     eax, 933h
0x18001c270  jmp     loc_18001C1E3
0x18001c275  mov     r13d, dword ptr [rbp+57h+var_88]
0x18001c279  mov     eax, 933h
0x18001c27e  mov     [rbp+57h+var_7C], ax
0x18001c282  test    r13d, r13d
0x18001c285  jz      short loc_18001C2A0
0x18001c287  lea     edx, [r13-1]; unsigned int
0x18001c28b  cmp     word ptr [r14+rdx*2], 5Ch ; '\'
0x18001c291  jnz     short loc_18001C2A0
0x18001c293  lea     rcx, [rbp+57h+lpFileName]; this
0x18001c297  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x18001c29c  mov     r14, [rbp+57h+lpFileName]
0x18001c2a0  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18001c2a9  mov     r8d, 3; dwShareMode
0x18001c2af  mov     [rsp+0D0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18001c2b7  xor     r9d, r9d; lpSecurityAttributes
0x18001c2ba  mov     edx, 0C0000000h; dwDesiredAccess
0x18001c2bf  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001c2c4  mov     rcx, r14; lpFileName
0x18001c2c7  call    cs:__imp_CreateFileW
0x18001c2cd  mov     rbx, rax
0x18001c2d0  inc     rax
0x18001c2d3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001c2d9  jnz     short loc_18001C2EF
0x18001c2db  call    GetLastFailureAsHRESULT
0x18001c2e0  mov     esi, eax
0x18001c2e2  mov     [rbp+57h+var_80], eax
0x18001c2e5  mov     eax, 93Fh
0x18001c2ea  jmp     loc_18001C1E3
0x18001c2ef  mov     eax, 93Fh
0x18001c2f4  mov     [rbp+57h+var_80], 0
0x18001c2fb  mov     rdx, rdi; int *
0x18001c2fe  mov     [rbp+57h+var_7C], ax
0x18001c302  mov     rcx, rbx; hDevice
0x18001c305  call    ?SxCheckTrimSupport@@YAJPEAXPEAH@Z; SxCheckTrimSupport(void *,int *)
0x18001c30a  mov     esi, eax
0x18001c30c  mov     [rbp+57h+var_80], eax
0x18001c30f  test    eax, eax
0x18001c311  mov     eax, 941h
0x18001c316  js      loc_18001C1E3
0x18001c31c  mov     [rbp+57h+var_7C], ax
0x18001c320  mov     rcx, r14; unsigned __int16 *
0x18001c323  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x18001c328  lea     rcx, [rbx-1]
0x18001c32c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001c330  ja      short loc_18001C33B
0x18001c332  mov     rcx, rbx; hObject
0x18001c335  call    cs:__imp_CloseHandle
0x18001c33b  lea     rcx, [rbp+57h+var_80]; this
0x18001c33f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001c344  mov     eax, esi
0x18001c346  add     rsp, 98h
0x18001c34d  pop     r15
0x18001c34f  pop     r14
0x18001c351  pop     r13
0x18001c353  pop     r12
0x18001c355  pop     rdi
0x18001c356  pop     rsi
0x18001c357  pop     rbx
0x18001c358  pop     rbp
0x18001c359  retn
```
