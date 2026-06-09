# FrsLogFile::LogMessage(ushort const *,unsigned __int64,ulong)

- ea: `0x1401b8204`
- end: `0x1401b86c4`
- name: `?LogMessage@FrsLogFile@@QEAAXPEBG_KK@Z`
- size: `1216`
- prototype: `void __fastcall(FrsLogFile *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1401b81c4`

## callees

- `0x1400036a0`
- `0x14000e34c`
- `0x140035304`
- `0x140044898`
- `0x1401af7c0`
- `0x1401b7dbc`
- `0x1401b8204`
- `0x1401b8e5c`
- `0x1401b9494`
- `0x1401ba178`
- `0x1401befb8`
- `0x1402135d0`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1401b82d2`
- `KERNEL32!WideCharToMultiByte` at `0x1401b82d2`
- `KERNEL32!WriteFile` at `0x1401b83dd`
- `KERNEL32!WriteFile` at `0x1401b84aa`
- `KERNEL32!WriteFile` at `0x1401b83dd`
- `KERNEL32!WriteFile` at `0x1401b84aa`
- `KERNEL32!QueryPerformanceCounter` at `0x1401b8270`
- `KERNEL32!QueryPerformanceCounter` at `0x1401b8553`
- `KERNEL32!QueryPerformanceCounter` at `0x1401b8270`
- `KERNEL32!QueryPerformanceCounter` at `0x1401b8553`
- `KERNEL32!GetLastError` at `0x1401b82f0`
- `KERNEL32!GetLastError` at `0x1401b83ed`
- `KERNEL32!GetLastError` at `0x1401b84ba`
- `KERNEL32!GetLastError` at `0x1401b82f0`
- `KERNEL32!GetLastError` at `0x1401b83ed`
- `KERNEL32!GetLastError` at `0x1401b84ba`
- `KERNEL32!GetCurrentThreadId` at `0x1401b82fe`
- `KERNEL32!GetCurrentThreadId` at `0x1401b83fb`
- `KERNEL32!GetCurrentThreadId` at `0x1401b84c8`
- `KERNEL32!GetCurrentThreadId` at `0x1401b82fe`
- `KERNEL32!GetCurrentThreadId` at `0x1401b83fb`
- `KERNEL32!GetCurrentThreadId` at `0x1401b84c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FrsLogFile::LogMessage(FrsLogFile *this, const unsigned __int16 *a2, unsigned __int64 a3, int a4)
{
  unsigned int *NewLogFile; // r13
  unsigned int v8; // esi
  unsigned int v9; // edi
  LARGE_INTEGER *v10; // rbx
  unsigned int v11; // r14d
  DWORD v12; // ebx
  DWORD v13; // eax
  __int64 v14; // rcx
  CHAR *v15; // rax
  DWORD LastError; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v18; // rcx
  int v19; // r15d
  DWORD v20; // ebx
  DWORD v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  Dword *v24; // r15
  Dword *v25; // r14
  Dword *v26; // rsi
  __int64 DisplayPath; // rdi
  __int64 v28; // rbx
  Dword *v29; // rax
  Dword *v30; // rdi
  Dword *v31; // rbx
  __int64 v32; // rax
  __int64 v33; // r8
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-C8h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+54h] [rbp-ACh]
  struct FrsStatus *v37; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v40[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v42[48]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v43[48]; // [rsp+100h] [rbp+0h] BYREF
  CHAR MultiByteStr[4112]; // [rsp+130h] [rbp+30h] BYREF

  v36 = a4;
  NewLogFile = 0;
  v37 = 0;
  NumberOfBytesWritten = 0;
  v8 = 0;
  v9 = 0;
  PerformanceCount.QuadPart = 0;
  if ( *((_DWORD *)this + 30) )
  {
    v10 = (LARGE_INTEGER *)((char *)this + 128);
    if ( QueryPerformanceCounter(&PerformanceCount)
      && PerformanceCount.QuadPart - v10->QuadPart <= 5LL * *((_QWORD *)this + 17) )
    {
      return;
    }
    *v10 = PerformanceCount;
  }
  v11 = WideCharToMultiByte(0xFDE9u, 0, a2, a3 >> 1, MultiByteStr, 4097, 0, 0);
  LODWORD(Block) = v11;
  if ( v11
    || (v12 = GetLastError(),
        v13 = GetCurrentThreadId(),
        NewLogFile = (unsigned int *)FrsStatusList::PushNewError(
                                       v14,
                                       v12,
                                       0,
                                       1,
                                       "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                                       "FrsLogFile::LogMessage",
                                       965,
                                       v13,
                                       0),
        (v37 = (struct FrsStatus *)NewLogFile) == 0) )
  {
    if ( *((_QWORD *)this + 3) != -1
      || (NewLogFile = (unsigned int *)FrsLogFile::CreateNewLogFile(this), (v37 = (struct FrsStatus *)NewLogFile) == 0) )
    {
      if ( (unsigned int)(*(_DWORD *)this + v36) >= *((_DWORD *)this + 1) )
      {
        if ( v11 )
        {
          v15 = MultiByteStr;
          do
          {
            if ( *v15 == 10 )
              break;
            ++v9;
            ++v15;
          }
          while ( v9 < v11 );
          if ( v9 < v11 && MultiByteStr[v9] == 10 )
            ++v9;
        }
        do
        {
          if ( v8 >= v9 )
            break;
          if ( WriteFile(*((HANDLE *)this + 3), &MultiByteStr[v8], v9 - v8, &NumberOfBytesWritten, 0) )
          {
            v8 += NumberOfBytesWritten;
            NumberOfBytesWritten = 0;
          }
          else
          {
            LastError = GetLastError();
            CurrentThreadId = GetCurrentThreadId();
            NewLogFile = (unsigned int *)FrsStatusList::PushNewError(
                                           v18,
                                           LastError,
                                           0,
                                           1,
                                           "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                                           "FrsLogFile::LogMessage",
                                           1011,
                                           CurrentThreadId,
                                           0);
          }
        }
        while ( !NewLogFile );
        v37 = (struct FrsStatus *)NewLogFile;
        v11 = (unsigned int)Block;
        v19 = v36;
        if ( NewLogFile )
          goto LABEL_31;
        NewLogFile = (unsigned int *)FrsLogFile::CreateNewLogFile(this);
        v37 = (struct FrsStatus *)NewLogFile;
        if ( NewLogFile )
          goto LABEL_31;
      }
      do
      {
        if ( v8 >= v11 )
          break;
        if ( WriteFile(*((HANDLE *)this + 3), &MultiByteStr[v8], v11 - v8, &NumberOfBytesWritten, 0) )
        {
          v8 += NumberOfBytesWritten;
          NumberOfBytesWritten = 0;
        }
        else
        {
          v20 = GetLastError();
          v21 = GetCurrentThreadId();
          NewLogFile = (unsigned int *)FrsStatusList::PushNewError(
                                         v22,
                                         v20,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                                         "FrsLogFile::LogMessage",
                                         1044,
                                         v21,
                                         0);
        }
      }
      while ( !NewLogFile );
      v37 = (struct FrsStatus *)NewLogFile;
    }
  }
  v19 = v36;
LABEL_31:
  v23 = *((_DWORD *)this + 30);
  if ( NewLogFile )
  {
    if ( !v23 )
    {
      *((_DWORD *)this + 30) = 1;
      if ( !QueryPerformanceCounter((LARGE_INTEGER *)this + 16) )
        *((_QWORD *)this + 16) = 0;
      v24 = Dword::Dword((Dword *)v43, *((_DWORD *)this + 1), 10);
      v25 = Dword::Dword((Dword *)v40, *((_DWORD *)this + 24), 10);
      v26 = Dword::Dword((Dword *)v41, *((_DWORD *)this + 4), 10);
      DisplayPath = FilePath::GetDisplayPath((char *)this + 112);
      v28 = *(_QWORD *)FrsStatusString::FrsStatusString((FrsStatusString *)&Block, (const struct FrsStatus *)NewLogFile);
      v29 = Dword::Dword((Dword *)v42, NewLogFile[1], 10);
      LODWORD(lpUsedDefaultChar) = 1;
      FrsEvent::Log(3221226774LL, v29, v28, DisplayPath, v26, v25, v24, lpUsedDefaultChar);
      operator delete[](Block);
    }
    CLEAR_ERROR(&v37);
  }
  else
  {
    *(_DWORD *)this += v19;
    if ( v23 )
    {
      *((_DWORD *)this + 30) = 0;
      *((_QWORD *)this + 16) = 0;
      v30 = Dword::Dword((Dword *)v42, *((_DWORD *)this + 1), 10);
      v31 = Dword::Dword((Dword *)v41, *((_DWORD *)this + 24), 10);
      Dword::Dword((Dword *)v40, *((_DWORD *)this + 4), 10);
      v32 = FilePath::GetDisplayPath((char *)this + 112);
      FrsEvent::Log(1073743128, v32, v33, v31, v30, 1);
    }
  }
}

```

## disassembly

```asm
0x1401b8204  mov     [rsp-8+arg_18], rbx
0x1401b8209  push    rbp
0x1401b820a  push    rsi
0x1401b820b  push    rdi
0x1401b820c  push    r12
0x1401b820e  push    r13
0x1401b8210  push    r14
0x1401b8212  push    r15
0x1401b8214  lea     rbp, [rsp-1050h]
0x1401b821c  mov     eax, 1150h
0x1401b8221  call    _alloca_probe
0x1401b8226  sub     rsp, rax
0x1401b8229  mov     rax, cs:__security_cookie
0x1401b8230  xor     rax, rsp
0x1401b8233  mov     [rbp+1080h+var_40], rax
0x1401b823a  mov     [rsp+1180h+var_112C], r9d
0x1401b823f  mov     r14, r8
0x1401b8242  mov     r15, rdx
0x1401b8245  mov     r12, rcx
0x1401b8248  xor     ebx, ebx
0x1401b824a  mov     r13d, ebx
0x1401b824d  mov     [rsp+1180h+var_1128], rbx
0x1401b8252  mov     [rsp+1180h+NumberOfBytesWritten], ebx
0x1401b8256  mov     esi, ebx
0x1401b8258  mov     edi, ebx
0x1401b825a  mov     qword ptr [rsp+1180h+PerformanceCount], rbx
0x1401b825f  cmp     [rcx+78h], ebx
0x1401b8262  jz      short loc_1401B82A7
0x1401b8264  lea     rbx, [rcx+80h]
0x1401b826b  lea     rcx, [rsp+1180h+PerformanceCount]; lpPerformanceCount
0x1401b8270  call    cs:__imp_QueryPerformanceCounter
0x1401b8277  nop     dword ptr [rax+rax+00h]
0x1401b827c  mov     ecx, eax
0x1401b827e  mov     rax, qword ptr [rsp+1180h+PerformanceCount]
0x1401b8283  test    ecx, ecx
0x1401b8285  jz      short loc_1401B82A2
0x1401b8287  mov     r8, rax
0x1401b828a  sub     r8, [rbx]
0x1401b828d  mov     rcx, [r12+88h]
0x1401b8295  lea     rdx, [rcx+rcx*4]
0x1401b8299  cmp     r8, rdx
0x1401b829c  jle     loc_1401B8699
0x1401b82a2  mov     [rbx], rax
0x1401b82a5  xor     ebx, ebx
0x1401b82a7  shr     r14, 1
0x1401b82aa  mov     [rsp+1180h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x1401b82af  mov     [rsp+1180h+lpDefaultChar], rbx; lpDefaultChar
0x1401b82b4  mov     [rsp+1180h+cbMultiByte], 1001h; cbMultiByte
0x1401b82bc  lea     rax, [rbp+1080h+MultiByteStr]
0x1401b82c0  mov     [rsp+1180h+lpMultiByteStr], rax; lpMultiByteStr
0x1401b82c5  mov     r9d, r14d; cchWideChar
0x1401b82c8  mov     r8, r15; lpWideCharStr
0x1401b82cb  xor     edx, edx; dwFlags
0x1401b82cd  mov     ecx, 0FDE9h; CodePage
0x1401b82d2  call    cs:__imp_WideCharToMultiByte
0x1401b82d9  nop     dword ptr [rax+rax+00h]
0x1401b82de  mov     r14d, eax
0x1401b82e1  mov     dword ptr [rsp+1180h+Block], eax
0x1401b82e5  lea     r15, aFrslogfileLogm; "FrsLogFile::LogMessage"
0x1401b82ec  test    eax, eax
0x1401b82ee  jnz     short loc_1401B834D
0x1401b82f0  call    cs:__imp_GetLastError
0x1401b82f7  nop     dword ptr [rax+rax+00h]
0x1401b82fc  mov     ebx, eax
0x1401b82fe  call    cs:__imp_GetCurrentThreadId
0x1401b8305  nop     dword ptr [rax+rax+00h]
0x1401b830a  and     [rsp+1180h+var_1140], rsi
0x1401b830f  mov     dword ptr [rsp+1180h+lpUsedDefaultChar], eax
0x1401b8313  mov     dword ptr [rsp+1180h+lpDefaultChar], 3C5h
0x1401b831b  mov     qword ptr [rsp+1180h+cbMultiByte], r15
0x1401b8320  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b8327  mov     [rsp+1180h+lpMultiByteStr], rax
0x1401b832c  lea     r9d, [r14+1]
0x1401b8330  xor     r8d, r8d
0x1401b8333  mov     edx, ebx
0x1401b8335  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b833a  mov     r13, rax
0x1401b833d  mov     [rsp+1180h+var_1128], rax
0x1401b8342  xor     ebx, ebx
0x1401b8344  test    rax, rax
0x1401b8347  jnz     loc_1401B8524
0x1401b834d  cmp     qword ptr [r12+18h], 0FFFFFFFFFFFFFFFFh
0x1401b8353  jnz     short loc_1401B836E
0x1401b8355  mov     rcx, r12; this
0x1401b8358  call    ?CreateNewLogFile@FrsLogFile@@AEAAPEAVFrsStatus@@XZ; FrsLogFile::CreateNewLogFile(void)
0x1401b835d  mov     r13, rax
0x1401b8360  mov     [rsp+1180h+var_1128], rax
0x1401b8365  test    rax, rax
0x1401b8368  jnz     loc_1401B8524
0x1401b836e  mov     ecx, [rsp+1180h+var_112C]
0x1401b8372  add     ecx, [r12]
0x1401b8376  cmp     ecx, [r12+4]
0x1401b837b  jb      loc_1401B847C
0x1401b8381  test    r14d, r14d
0x1401b8384  jz      short loc_1401B83A9
0x1401b8386  lea     rax, [rbp+1080h+MultiByteStr]
0x1401b838a  cmp     byte ptr [rax], 0Ah
0x1401b838d  jz      short loc_1401B8399
0x1401b838f  inc     edi
0x1401b8391  inc     rax
0x1401b8394  cmp     edi, r14d
0x1401b8397  jb      short loc_1401B838A
0x1401b8399  cmp     edi, r14d
0x1401b839c  jnb     short loc_1401B83A9
0x1401b839e  mov     eax, edi
0x1401b83a0  cmp     [rbp+rax+1080h+MultiByteStr], 0Ah
0x1401b83a5  jnz     short loc_1401B83A9
0x1401b83a7  inc     edi
0x1401b83a9  lea     r15, aFrslogfileLogm; "FrsLogFile::LogMessage"
0x1401b83b0  lea     r14, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b83b7  cmp     esi, edi
0x1401b83b9  jnb     loc_1401B844B
0x1401b83bf  mov     r8d, edi
0x1401b83c2  sub     r8d, esi; nNumberOfBytesToWrite
0x1401b83c5  mov     eax, esi
0x1401b83c7  lea     rdx, [rbp+1080h+MultiByteStr]
0x1401b83cb  add     rdx, rax; lpBuffer
0x1401b83ce  mov     [rsp+1180h+lpMultiByteStr], rbx; lpOverlapped
0x1401b83d3  lea     r9, [rsp+1180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1401b83d8  mov     rcx, [r12+18h]; hFile
0x1401b83dd  call    cs:__imp_WriteFile
0x1401b83e4  nop     dword ptr [rax+rax+00h]
0x1401b83e9  test    eax, eax
0x1401b83eb  jnz     short loc_1401B843A
0x1401b83ed  call    cs:__imp_GetLastError
0x1401b83f4  nop     dword ptr [rax+rax+00h]
0x1401b83f9  mov     ebx, eax
0x1401b83fb  call    cs:__imp_GetCurrentThreadId
0x1401b8402  nop     dword ptr [rax+rax+00h]
0x1401b8407  and     [rsp+1180h+var_1140], 0
0x1401b840d  mov     dword ptr [rsp+1180h+lpUsedDefaultChar], eax
0x1401b8411  mov     dword ptr [rsp+1180h+lpDefaultChar], 3F3h
0x1401b8419  mov     qword ptr [rsp+1180h+cbMultiByte], r15
0x1401b841e  mov     [rsp+1180h+lpMultiByteStr], r14
0x1401b8423  mov     r9d, 1
0x1401b8429  xor     r8d, r8d
0x1401b842c  mov     edx, ebx
0x1401b842e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b8433  mov     r13, rax
0x1401b8436  xor     ebx, ebx
0x1401b8438  jmp     short loc_1401B8442
0x1401b843a  add     esi, [rsp+1180h+NumberOfBytesWritten]
0x1401b843e  mov     [rsp+1180h+NumberOfBytesWritten], ebx
0x1401b8442  test    r13, r13
0x1401b8445  jz      loc_1401B83B7
0x1401b844b  mov     [rsp+1180h+var_1128], r13
0x1401b8450  test    r13, r13
0x1401b8453  mov     r14d, dword ptr [rsp+1180h+Block]
0x1401b8458  mov     r15d, [rsp+1180h+var_112C]
0x1401b845d  jnz     loc_1401B8529
0x1401b8463  mov     rcx, r12; this
0x1401b8466  call    ?CreateNewLogFile@FrsLogFile@@AEAAPEAVFrsStatus@@XZ; FrsLogFile::CreateNewLogFile(void)
0x1401b846b  mov     r13, rax
0x1401b846e  mov     [rsp+1180h+var_1128], rax
0x1401b8473  test    rax, rax
0x1401b8476  jnz     loc_1401B8529
0x1401b847c  lea     r15, aFrslogfileLogm; "FrsLogFile::LogMessage"
0x1401b8483  cmp     esi, r14d
0x1401b8486  jnb     loc_1401B851F
0x1401b848c  mov     r8d, r14d
0x1401b848f  sub     r8d, esi; nNumberOfBytesToWrite
0x1401b8492  mov     eax, esi
0x1401b8494  lea     rdx, [rbp+1080h+MultiByteStr]
0x1401b8498  add     rdx, rax; lpBuffer
0x1401b849b  mov     [rsp+1180h+lpMultiByteStr], rbx; lpOverlapped
0x1401b84a0  lea     r9, [rsp+1180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1401b84a5  mov     rcx, [r12+18h]; hFile
0x1401b84aa  call    cs:__imp_WriteFile
0x1401b84b1  nop     dword ptr [rax+rax+00h]
0x1401b84b6  test    eax, eax
0x1401b84b8  jnz     short loc_1401B850E
0x1401b84ba  call    cs:__imp_GetLastError
0x1401b84c1  nop     dword ptr [rax+rax+00h]
0x1401b84c6  mov     ebx, eax
0x1401b84c8  call    cs:__imp_GetCurrentThreadId
0x1401b84cf  nop     dword ptr [rax+rax+00h]
0x1401b84d4  and     [rsp+1180h+var_1140], 0
0x1401b84da  mov     dword ptr [rsp+1180h+lpUsedDefaultChar], eax
0x1401b84de  mov     dword ptr [rsp+1180h+lpDefaultChar], 414h
0x1401b84e6  mov     qword ptr [rsp+1180h+cbMultiByte], r15
0x1401b84eb  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b84f2  mov     [rsp+1180h+lpMultiByteStr], rax
0x1401b84f7  mov     r9d, 1
0x1401b84fd  xor     r8d, r8d
0x1401b8500  mov     edx, ebx
0x1401b8502  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b8507  mov     r13, rax
0x1401b850a  xor     ebx, ebx
0x1401b850c  jmp     short loc_1401B8516
0x1401b850e  add     esi, [rsp+1180h+NumberOfBytesWritten]
0x1401b8512  mov     [rsp+1180h+NumberOfBytesWritten], ebx
0x1401b8516  test    r13, r13
0x1401b8519  jz      loc_1401B8483
0x1401b851f  mov     [rsp+1180h+var_1128], r13
0x1401b8524  mov     r15d, [rsp+1180h+var_112C]
0x1401b8529  mov     eax, [r12+78h]
0x1401b852e  test    r13, r13
0x1401b8531  jz      loc_1401B861B
0x1401b8537  test    eax, eax
0x1401b8539  jnz     loc_1401B860F
0x1401b853f  mov     dword ptr [r12+78h], 1
0x1401b8548  lea     rbx, [r12+80h]
0x1401b8550  mov     rcx, rbx; lpPerformanceCount
0x1401b8553  call    cs:__imp_QueryPerformanceCounter
0x1401b855a  nop     dword ptr [rax+rax+00h]
0x1401b855f  test    eax, eax
0x1401b8561  jnz     short loc_1401B8567
0x1401b8563  and     qword ptr [rbx], 0
0x1401b8567  mov     ebx, 0Ah
0x1401b856c  mov     r8d, ebx; int
0x1401b856f  mov     edx, [r12+4]; unsigned int
0x1401b8574  lea     rcx, [rbp+1080h+var_1080]; this
0x1401b8578  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1401b857d  mov     r15, rax
0x1401b8580  mov     r8d, ebx; int
0x1401b8583  mov     edx, [r12+60h]; unsigned int
0x1401b8588  lea     rcx, [rsp+1180h+var_1110]; this
0x1401b858d  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1401b8592  mov     r14, rax
0x1401b8595  mov     r8d, ebx; int
0x1401b8598  mov     edx, [r12+10h]; unsigned int
0x1401b859d  lea     rcx, [rbp+1080h+var_10E0]; this
0x1401b85a1  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1401b85a6  mov     rsi, rax
0x1401b85a9  lea     rcx, [r12+70h]
0x1401b85ae  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x1401b85b3  mov     rdi, rax
0x1401b85b6  mov     rdx, r13; struct FrsStatus *
0x1401b85b9  lea     rcx, [rsp+1180h+Block]; this
0x1401b85be  call    ??0FrsStatusString@@QEAA@PEBVFrsStatus@@@Z; FrsStatusString::FrsStatusString(FrsStatus const *)
0x1401b85c3  nop
0x1401b85c4  mov     rbx, [rax]
0x1401b85c7  mov     r8d, 0Ah; int
0x1401b85cd  mov     edx, [r13+4]; unsigned int
0x1401b85d1  lea     rcx, [rbp+1080h+var_10B0]; this
0x1401b85d5  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1401b85da  mov     dword ptr [rsp+1180h+lpUsedDefaultChar], 1
0x1401b85e2  mov     [rsp+1180h+lpDefaultChar], r15
0x1401b85e7  mov     qword ptr [rsp+1180h+cbMultiByte], r14
0x1401b85ec  mov     [rsp+1180h+lpMultiByteStr], rsi
0x1401b85f1  mov     r9, rdi
0x1401b85f4  mov     r8, rbx
0x1401b85f7  mov     rdx, rax
0x1401b85fa  mov     ecx, 0C0000516h
0x1401b85ff  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum6@@PEBG11111W4LogUseDebugLog@EventLog@@@Z; FrsEvent::Log(FrsEventsEnum6,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,EventLog::LogUseDebugLog)
0x1401b8604  nop
0x1401b8605  mov     rcx, [rsp+1180h+Block]; Block
0x1401b860a  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401b860f  lea     rcx, [rsp+1180h+var_1128]; struct FrsStatus **
0x1401b8614  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401b8619  jmp     short loc_1401B8699
0x1401b861b  add     [r12], r15d
0x1401b861f  test    eax, eax
0x1401b8621  jz      short loc_1401B8699
0x1401b8623  mov     [r12+78h], ebx
0x1401b8628  mov     [r12+80h], rbx
0x1401b8630  mov     esi, 0Ah
0x1401b8635  mov     r8d, esi; int
0x1401b8638  mov     edx, [r12+4]; unsigned int
0x1401b863d  lea     rcx, [rbp+1080h+var_10B0]; this
0x1401b8641  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1401b8646  mov     rdi, rax
0x1401b8649  mov     r8d, esi; int
0x1401b864c  mov     edx, [r12+60h]; unsigned int
0x1401b8651  lea     rcx, [rbp+1080h+var_10E0]; this
0x1401b8655  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1401b865a  mov     rbx, rax
0x1401b865d  mov     r8d, esi; int
0x1401b8660  mov     edx, [r12+10h]; unsigned int
0x1401b8665  lea     rcx, [rsp+1180h+var_1110]; this
0x1401b866a  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x1401b866f  mov     r8, rax
0x1401b8672  lea     rcx, [r12+70h]
0x1401b8677  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x1401b867c  mov     [rsp+1180h+cbMultiByte], 1
0x1401b8684  mov     [rsp+1180h+lpMultiByteStr], rdi
0x1401b8689  mov     r9, rbx
0x1401b868c  mov     rdx, rax
0x1401b868f  mov     ecx, 40000518h
0x1401b8694  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum4@@PEBG111W4LogUseDebugLog@EventLog@@@Z; FrsEvent::Log(FrsEventsEnum4,ushort const *,ushort const *,ushort const *,ushort const *,EventLog::LogUseDebugLog)
0x1401b8699  mov     rcx, [rbp+1080h+var_40]
0x1401b86a0  xor     rcx, rsp; StackCookie
0x1401b86a3  call    __security_check_cookie
0x1401b86a8  mov     rbx, [rsp+1180h+arg_18]
0x1401b86b0  add     rsp, 1150h
0x1401b86b7  pop     r15
0x1401b86b9  pop     r14
0x1401b86bb  pop     r13
0x1401b86bd  pop     r12
0x1401b86bf  pop     rdi
0x1401b86c0  pop     rsi
0x1401b86c1  pop     rbp
0x1401b86c2  retn
```
