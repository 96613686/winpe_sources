# CDRMStore::Add(ushort const *,ushort const *,uchar *,ulong)

- ea: `0x180034c24`
- end: `0x180034e3c`
- name: `?Add@CDRMStore@@QEAAJPEBG0PEAEK@Z`
- size: `536`
- prototype: `__int64 __usercall@<rax>(CDRMStore *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int8 *@<r9>, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001e034`
- `0x180037320`
- `0x180037890`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x180017210`
- `0x180034bb0`
- `0x180034c24`
- `0x180034e44`
- `0x1800370d8`
- `0x18003721c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034da8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034de4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034da8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDRMStore::Add(
        CDRMStore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD nNumberOfBytesToWrite)
{
  __int64 v8; // rdi
  unsigned __int16 *v9; // r14
  DWORD v10; // r12d
  int FilePathString; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rdi
  unsigned __int16 *v15; // rax
  signed int LastError; // eax
  unsigned __int16 lpOverlapped; // [rsp+20h] [rbp-30h]
  __int64 v19; // [rsp+30h] [rbp-20h] BYREF
  void *Block[3]; // [rsp+38h] [rbp-18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp+48h] BYREF
  HANDLE hFile; // [rsp+A0h] [rbp+50h] BYREF

  Block[1] = (void *)-2LL;
  v8 = -1;
  hFile = (HANDLE)-1LL;
  Block[0] = 0;
  v9 = 0;
  if ( !a2 || !a4 || (v10 = nNumberOfBytesToWrite) == 0 )
  {
    FilePathString = -2147024809;
LABEL_28:
    if ( v8 != -1 )
      CloseHandle((HANDLE)v8);
    goto LABEL_30;
  }
  if ( !*((_DWORD *)this + 1) )
  {
    FilePathString = -2147024809;
    goto LABEL_30;
  }
  FilePathString = CDRMStore::MakeFilePathString(
                     this,
                     *((const unsigned __int16 **)this + 2),
                     a2,
                     a4,
                     lpOverlapped,
                     (unsigned __int16 **)Block);
  if ( FilePathString >= 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(*((_QWORD *)this + 2) + 2 * v13) );
    v14 = v13 + v12 + 1;
    v15 = (unsigned __int16 *)operator new(saturated_mul(v14, 2u));
    v9 = v15;
    if ( !v15 )
    {
      FilePathString = -2147024882;
      goto LABEL_30;
    }
    FilePathString = StringCchCopyW(v15, v14, *((const unsigned __int16 **)this + 2));
    if ( FilePathString >= 0 )
    {
      FilePathString = StringCchCatW(v9, v14, a2);
      if ( FilePathString >= 0 )
      {
        v19 = 0;
        if ( CDRMCLock::Lock((CDRMCLock *)&v19, v9) < 0 )
        {
          CDRMCLock::~CDRMCLock((CDRMCLock *)&v19);
          goto LABEL_30;
        }
        FilePathString = CDRMStore::CreateFileForReadWrite(this, (unsigned __int16 *)Block[0], 1, &hFile);
        if ( FilePathString >= 0 )
        {
          NumberOfBytesWritten = 0;
          v8 = (__int64)hFile;
          if ( *((_DWORD *)this + 2) == 5
            && (LOWORD(hFile) = -257, !WriteFile((HANDLE)v8, &hFile, 2u, &NumberOfBytesWritten, 0))
            || !WriteFile((HANDLE)v8, a4, v10, &NumberOfBytesWritten, 0)
            || v10 != NumberOfBytesWritten )
          {
            LastError = GetLastError();
            FilePathString = LastError;
            if ( LastError > 0 )
              FilePathString = (unsigned __int16)LastError | 0x80070000;
          }
          CDRMCLock::~CDRMCLock((CDRMCLock *)&v19);
        }
        else
        {
          CDRMCLock::~CDRMCLock((CDRMCLock *)&v19);
          v8 = (__int64)hFile;
        }
        goto LABEL_28;
      }
    }
  }
LABEL_30:
  operator delete(Block[0]);
  operator delete(v9);
  return (unsigned int)FilePathString;
}

```

## disassembly

```asm
0x180034c24  mov     r11, rsp
0x180034c27  mov     [r11+18h], r8
0x180034c2b  push    rbp
0x180034c2c  push    rsi
0x180034c2d  push    rdi
0x180034c2e  push    r12
0x180034c30  push    r13
0x180034c32  push    r14
0x180034c34  push    r15
0x180034c36  mov     rbp, rsp
0x180034c39  sub     rsp, 50h
0x180034c3d  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180034c45  mov     [r11+8], rbx
0x180034c49  mov     r13, r9
0x180034c4c  mov     r15, rdx
0x180034c4f  mov     rsi, rcx
0x180034c52  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180034c56  mov     [rbp+hFile], rdi
0x180034c5a  xor     eax, eax
0x180034c5c  mov     [rbp+Block], rax
0x180034c60  mov     r14d, eax
0x180034c63  test    rdx, rdx
0x180034c66  jz      loc_180034DFD
0x180034c6c  test    r9, r9
0x180034c6f  jz      loc_180034DFD
0x180034c75  mov     r12d, [rbp+nNumberOfBytesToWrite]
0x180034c79  test    r12d, r12d
0x180034c7c  jz      loc_180034DFD
0x180034c82  cmp     [rcx+4], eax
0x180034c85  jz      loc_180034DF6
0x180034c8b  lea     rax, [rbp+Block]
0x180034c8f  mov     [r11-60h], rax
0x180034c93  mov     r8, rdx; unsigned __int16 *
0x180034c96  mov     rdx, [rcx+10h]; unsigned __int16 *
0x180034c9a  call    ?MakeFilePathString@CDRMStore@@AEAAJPEBG00GPEAPEAG@Z; CDRMStore::MakeFilePathString(ushort const *,ushort const *,ushort const *,ushort,ushort * *)
0x180034c9f  mov     ebx, eax
0x180034ca1  xor     r8d, r8d
0x180034ca4  test    eax, eax
0x180034ca6  js      loc_180034E11
0x180034cac  or      r9, rdi
0x180034caf  mov     rax, r9
0x180034cb2  inc     rax
0x180034cb5  cmp     [r15+rax*2], r8w
0x180034cba  jnz     short loc_180034CB2
0x180034cbc  mov     rdx, [rsi+10h]
0x180034cc0  mov     rcx, r9
0x180034cc3  inc     rcx
0x180034cc6  cmp     [rdx+rcx*2], r8w
0x180034ccb  jnz     short loc_180034CC3
0x180034ccd  lea     rdi, [rax+1]
0x180034cd1  add     rdi, rcx
0x180034cd4  mov     eax, 2
0x180034cd9  mul     rdi
0x180034cdc  cmovb   rax, r9
0x180034ce0  mov     rcx, rax; Size
0x180034ce3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034ce8  mov     r14, rax
0x180034ceb  test    rax, rax
0x180034cee  jnz     short loc_180034CFA
0x180034cf0  mov     ebx, 8007000Eh
0x180034cf5  jmp     loc_180034E11
0x180034cfa  mov     r8, [rsi+10h]; unsigned __int16 *
0x180034cfe  mov     rdx, rdi; unsigned __int64
0x180034d01  mov     rcx, r14; unsigned __int16 *
0x180034d04  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034d09  mov     ebx, eax
0x180034d0b  test    eax, eax
0x180034d0d  js      loc_180034E11
0x180034d13  mov     r8, r15; unsigned __int16 *
0x180034d16  mov     rdx, rdi; unsigned __int64
0x180034d19  mov     rcx, r14; unsigned __int16 *
0x180034d1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034d21  mov     ebx, eax
0x180034d23  xor     r15d, r15d
0x180034d26  test    eax, eax
0x180034d28  js      loc_180034E11
0x180034d2e  mov     [rbp+var_20], r15
0x180034d32  mov     rdx, r14; unsigned __int16 *
0x180034d35  lea     rcx, [rbp+var_20]; this
0x180034d39  call    ?Lock@CDRMCLock@@QEAAJPEAG@Z; CDRMCLock::Lock(ushort *)
0x180034d3e  test    eax, eax
0x180034d40  jns     short loc_180034D50
0x180034d42  lea     rcx, [rbp+var_20]; this
0x180034d46  call    ??1CDRMCLock@@QEAA@XZ; CDRMCLock::~CDRMCLock(void)
0x180034d4b  jmp     loc_180034E11
0x180034d50  lea     r9, [rbp+hFile]; void **
0x180034d54  mov     r8d, 1; int
0x180034d5a  mov     rdx, [rbp+Block]; unsigned __int16 *
0x180034d5e  mov     rcx, rsi; this
0x180034d61  call    ?CreateFileForReadWrite@CDRMStore@@AEAAJPEAGHPEAPEAX@Z; CDRMStore::CreateFileForReadWrite(ushort *,int,void * *)
0x180034d66  mov     ebx, eax
0x180034d68  test    eax, eax
0x180034d6a  jns     short loc_180034D7E
0x180034d6c  lea     rcx, [rbp+var_20]; this
0x180034d70  call    ??1CDRMCLock@@QEAA@XZ; CDRMCLock::~CDRMCLock(void)
0x180034d75  mov     rdi, [rbp+hFile]
0x180034d79  jmp     loc_180034E02
0x180034d7e  mov     [rbp+NumberOfBytesWritten], r15d
0x180034d82  mov     rdi, [rbp+hFile]
0x180034d86  cmp     dword ptr [rsi+8], 5
0x180034d8a  jnz     short loc_180034DD2
0x180034d8c  mov     word ptr [rbp+hFile], 0FEFFh
0x180034d92  mov     qword ptr [rsp+50h+lpOverlapped], r15; lpOverlapped
0x180034d97  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180034d9b  mov     r8d, 2; nNumberOfBytesToWrite
0x180034da1  lea     rdx, [rbp+hFile]; lpBuffer
0x180034da5  mov     rcx, rdi; hFile
0x180034da8  call    cs:__imp_WriteFile
0x180034dae  test    eax, eax
0x180034db0  jnz     short loc_180034DD2
0x180034db2  call    cs:__imp_GetLastError
0x180034db8  test    eax, eax
0x180034dba  mov     ebx, eax
0x180034dbc  jle     short loc_180034DC7
0x180034dbe  movzx   ebx, ax
0x180034dc1  or      ebx, 80070000h
0x180034dc7  lea     rcx, [rbp+var_20]; this
0x180034dcb  call    ??1CDRMCLock@@QEAA@XZ; CDRMCLock::~CDRMCLock(void)
0x180034dd0  jmp     short loc_180034E02
0x180034dd2  mov     qword ptr [rsp+50h+lpOverlapped], r15; lpOverlapped
0x180034dd7  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180034ddb  mov     r8d, r12d; nNumberOfBytesToWrite
0x180034dde  mov     rdx, r13; lpBuffer
0x180034de1  mov     rcx, rdi; hFile
0x180034de4  call    cs:__imp_WriteFile
0x180034dea  test    eax, eax
0x180034dec  jz      short loc_180034DB2
0x180034dee  cmp     r12d, [rbp+NumberOfBytesWritten]
0x180034df2  jz      short loc_180034DC7
0x180034df4  jmp     short loc_180034DB2
0x180034df6  mov     ebx, 80070057h
0x180034dfb  jmp     short loc_180034E11
0x180034dfd  mov     ebx, 80070057h
0x180034e02  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180034e06  jz      short loc_180034E11
0x180034e08  mov     rcx, rdi; hObject
0x180034e0b  call    cs:__imp_CloseHandle
0x180034e11  mov     rcx, [rbp+Block]; Block
0x180034e15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034e1a  mov     rcx, r14; Block
0x180034e1d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034e22  mov     eax, ebx
0x180034e24  mov     rbx, [rsp+50h+arg_0]
0x180034e2c  add     rsp, 50h
0x180034e30  pop     r15
0x180034e32  pop     r14
0x180034e34  pop     r13
0x180034e36  pop     r12
0x180034e38  pop     rdi
0x180034e39  pop     rsi
0x180034e3a  pop     rbp
0x180034e3b  retn
```
