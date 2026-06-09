# CDims::CProvider::Load(ushort const *,char const *,ulong)

- ea: `0x180001c10`
- end: `0x1800020e4`
- name: `?Load@CProvider@CDims@@QEAAXPEBGPEBDK@Z`
- size: `1236`
- prototype: `void __fastcall(CDims::CProvider *this, const unsigned __int16 *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800078e0`

## callees

- `0x180001c10`
- `0x18000a338`
- `0x18000a360`
- `0x18000aac8`
- `0x18000ab3c`
- `0x18000ac82`
- `0x18000ad30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001d3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001d3b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001d15`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002031`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001c7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001cd4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001c7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001cd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001cb9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001cb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001fc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020bb`

## pseudocode

```c
void __fastcall CDims::CProvider::Load(
        CDims::CProvider *this,
        const unsigned __int16 *a2,
        const char *a3,
        unsigned int a4)
{
  unsigned int v4; // ebx
  HMODULE v8; // rcx
  __int64 v9; // r12
  __int64 v10; // rbx
  UINT SystemDirectoryW; // eax
  UINT v12; // esi
  unsigned __int64 v13; // rdx
  WCHAR *v14; // rax
  WCHAR *v15; // r14
  UINT v16; // eax
  __int64 v17; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  signed int v21; // ebx
  DWORD v22; // eax
  signed int v23; // ebx
  DWORD v24; // eax
  signed int v25; // ebx
  signed int v26; // eax
  signed int v27; // eax
  unsigned int pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  signed int v29; // [rsp+24h] [rbp-3Ch] BYREF
  WCHAR *v30; // [rsp+28h] [rbp-38h]
  const unsigned __int16 *v31; // [rsp+30h] [rbp-30h] BYREF
  int v32; // [rsp+38h] [rbp-28h]
  int v33; // [rsp+3Ch] [rbp-24h]
  signed int *v34; // [rsp+40h] [rbp-20h]
  __int64 v35; // [rsp+48h] [rbp-18h]

  v4 = a4;
  pExceptionObject = a4;
  v8 = (HMODULE)*((_QWORD *)this + 1);
  v9 = -1;
  if ( !v8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    if ( (unsigned __int64)(v10 - 1) > 0x103 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids);
      pExceptionObject = -2147024809;
      throw (CExcept *)&pExceptionObject;
    }
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    v12 = SystemDirectoryW;
    if ( !SystemDirectoryW )
    {
      LastError = GetLastError();
      v21 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids, LastError);
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      pExceptionObject = v21;
      throw (CExcept *)&pExceptionObject;
    }
    if ( SystemDirectoryW > 0x104 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids);
      pExceptionObject = -2147024883;
      throw (CExcept *)&pExceptionObject;
    }
    v13 = v10 + SystemDirectoryW + 1LL;
    if ( v13 > 0x7FFFFFFFFFFFFFFFLL )
    {
      pExceptionObject = -2147024882;
      throw (CExcept *)&pExceptionObject;
    }
    v14 = (WCHAR *)LocalAlloc(0, 2 * v13);
    v15 = v14;
    if ( !v14 )
    {
      v22 = GetLastError();
      v23 = v22;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ea7d1c204d33352b702f4b4b9615bef9_Traceguids, v22);
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      pExceptionObject = v23;
      throw (CExcept *)&pExceptionObject;
    }
    v30 = v14;
    v16 = GetSystemDirectoryW(v14, v12);
    if ( !v16 )
    {
      v24 = GetLastError();
      v25 = v24;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids, v24);
      if ( v25 > 0 )
        v25 = (unsigned __int16)v25 | 0x80070000;
      pExceptionObject = v25;
      throw (CExcept *)&pExceptionObject;
    }
    if ( v16 >= v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids);
      pExceptionObject = -2147024883;
      throw (CExcept *)&pExceptionObject;
    }
    v17 = v16;
    if ( v15[v16 - 1] != 92 )
    {
      v15[v16] = 92;
      v17 = v16 + 1LL;
    }
    memcpy_0(&v15[v17], a2, 2 * v10 + 2);
    Library = LoadLibraryExW(v15, 0, 0);
    *((_QWORD *)this + 1) = Library;
    if ( !Library )
    {
      v26 = GetLastError();
      v29 = v26;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids,
          (unsigned int)v26);
        v26 = v29;
      }
      if ( pExceptionObject > 1 )
      {
        v31 = a2;
        do
          ++v9;
        while ( a2[v9] );
        v32 = 2 * v9 + 2;
        v33 = 0;
        v34 = &v29;
        v35 = 4;
        LogReport(DM_LOG_ERROR_PROVIDERLOAD, 2, &v31);
        LocalFree(0);
        v26 = v29;
      }
      if ( v26 > 0 )
        v26 = (unsigned __int16)v26 | 0x80070000;
      pExceptionObject = v26;
      throw (CExcept *)&pExceptionObject;
    }
    LocalFree(v15);
    v8 = (HMODULE)*((_QWORD *)this + 1);
    v4 = pExceptionObject;
  }
  ProcAddress = GetProcAddress(v8, a3);
  *(_QWORD *)this = ProcAddress;
  if ( !ProcAddress )
  {
    v27 = GetLastError();
    v29 = v27;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids,
        (unsigned int)v27);
      v27 = v29;
    }
    if ( v4 > 1 )
    {
      v31 = a2;
      do
        ++v9;
      while ( a2[v9] );
      v32 = 2 * v9 + 2;
      v33 = 0;
      v34 = &v29;
      v35 = 4;
      LogReport(DM_LOG_ERROR_PROVIDERLOAD, 2, &v31);
      LocalFree(0);
      v27 = v29;
    }
    if ( v27 > 0 )
      v27 = (unsigned __int16)v27 | 0x80070000;
    pExceptionObject = v27;
    throw (CExcept *)&pExceptionObject;
  }
  *((_QWORD *)this + 2) = a2;
}

```

## disassembly

```asm
0x180001c10  mov     [rsp-38h+arg_18], rbx
0x180001c15  push    rbp
0x180001c16  push    rsi
0x180001c17  push    rdi
0x180001c18  push    r12
0x180001c1a  push    r13
0x180001c1c  push    r14
0x180001c1e  push    r15
0x180001c20  mov     rbp, rsp
0x180001c23  sub     rsp, 60h
0x180001c27  mov     rax, cs:__security_cookie
0x180001c2e  xor     rax, rsp
0x180001c31  mov     [rbp+var_10], rax
0x180001c35  mov     ebx, r9d
0x180001c38  mov     [rbp+pExceptionObject], ebx
0x180001c3b  mov     r13, r8
0x180001c3e  mov     rdi, rdx
0x180001c41  mov     r15, rcx
0x180001c44  mov     rcx, [rcx+8]
0x180001c48  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180001c4f  test    rcx, rcx
0x180001c52  jnz     loc_180001D38
0x180001c58  mov     rbx, r12
0x180001c5b  nop     dword ptr [rax+rax+00h]
0x180001c60  inc     rbx
0x180001c63  cmp     word ptr [rdx+rbx*2], 0
0x180001c68  jnz     short loc_180001C60
0x180001c6a  lea     rax, [rbx-1]
0x180001c6e  cmp     rax, 103h
0x180001c74  ja      loc_180001FEB
0x180001c7a  xor     edx, edx; uSize
0x180001c7c  xor     ecx, ecx; lpBuffer
0x180001c7e  call    cs:__imp_GetSystemDirectoryW
0x180001c84  mov     esi, eax
0x180001c86  test    eax, eax
0x180001c88  jz      loc_180001D75
0x180001c8e  cmp     esi, 104h
0x180001c94  ja      loc_180001DCF
0x180001c9a  lea     rdx, [rsi+1]
0x180001c9e  add     rdx, rbx
0x180001ca1  mov     rax, 7FFFFFFFFFFFFFFFh
0x180001cab  cmp     rdx, rax
0x180001cae  ja      loc_180001E15
0x180001cb4  add     rdx, rdx; uBytes
0x180001cb7  xor     ecx, ecx; uFlags
0x180001cb9  call    cs:__imp_LocalAlloc
0x180001cbf  mov     r14, rax
0x180001cc2  test    rax, rax
0x180001cc5  jz      loc_180001E2D
0x180001ccb  mov     [rbp+var_38], rax
0x180001ccf  mov     edx, esi; uSize
0x180001cd1  mov     rcx, rax; lpBuffer
0x180001cd4  call    cs:__imp_GetSystemDirectoryW
0x180001cda  test    eax, eax
0x180001cdc  jz      loc_180001E87
0x180001ce2  cmp     eax, esi
0x180001ce4  jnb     loc_180001EE2
0x180001cea  mov     ecx, eax
0x180001cec  cmp     word ptr [r14+rcx*2-2], 5Ch ; '\'
0x180001cf3  jnz     loc_180001F28
0x180001cf9  lea     r8, ds:2[rbx*2]; Size
0x180001d01  lea     rcx, [r14+rcx*2]; void *
0x180001d05  mov     rdx, rdi; Src
0x180001d08  call    memcpy_0
0x180001d0d  xor     r8d, r8d; dwFlags
0x180001d10  xor     edx, edx; hFile
0x180001d12  mov     rcx, r14; lpLibFileName
0x180001d15  call    cs:__imp_LoadLibraryExW
0x180001d1b  mov     [r15+8], rax
0x180001d1f  test    rax, rax
0x180001d22  jz      loc_180001F37
0x180001d28  mov     rcx, r14; hMem
0x180001d2b  call    cs:__imp_LocalFree
0x180001d31  mov     rcx, [r15+8]; hModule
0x180001d35  mov     ebx, [rbp+pExceptionObject]
0x180001d38  mov     rdx, r13; lpProcName
0x180001d3b  call    cs:__imp_GetProcAddress
0x180001d41  mov     [r15], rax
0x180001d44  test    rax, rax
0x180001d47  jz      loc_180002031
0x180001d4d  mov     [r15+10h], rdi
0x180001d51  mov     rcx, [rbp+var_10]
0x180001d55  xor     rcx, rsp; StackCookie
0x180001d58  call    __security_check_cookie
0x180001d5d  mov     rbx, [rsp+60h+arg_18]
0x180001d65  add     rsp, 60h
0x180001d69  pop     r15
0x180001d6b  pop     r14
0x180001d6d  pop     r13
0x180001d6f  pop     r12
0x180001d71  pop     rdi
0x180001d72  pop     rsi
0x180001d73  pop     rbp
0x180001d74  retn
0x180001d75  call    cs:__imp_GetLastError
0x180001d7b  mov     ebx, eax
0x180001d7d  lea     rdx, WPP_GLOBAL_Control
0x180001d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d8b  cmp     rcx, rdx
0x180001d8e  jz      short loc_180001DAE
0x180001d90  test    byte ptr [rcx+1Ch], 2
0x180001d94  jz      short loc_180001DAE
0x180001d96  mov     edx, 1Ch
0x180001d9b  mov     r9d, eax
0x180001d9e  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180001da5  mov     rcx, [rcx+10h]
0x180001da9  call    WPP_SF_D
0x180001dae  test    ebx, ebx
0x180001db0  jle     short loc_180001DBB
0x180001db2  movzx   ebx, bx
0x180001db5  or      ebx, 80070000h
0x180001dbb  mov     [rbp+pExceptionObject], ebx
0x180001dbe  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180001dc5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001dc9  call    _CxxThrowException_0
0x180001dcf  lea     rdx, WPP_GLOBAL_Control
0x180001dd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ddd  cmp     rcx, rdx
0x180001de0  jz      short loc_180001DFD
0x180001de2  test    byte ptr [rcx+1Ch], 2
0x180001de6  jz      short loc_180001DFD
0x180001de8  mov     edx, 1Dh
0x180001ded  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180001df4  mov     rcx, [rcx+10h]
0x180001df8  call    WPP_SF_
0x180001dfd  mov     [rbp+pExceptionObject], 8007000Dh
0x180001e04  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180001e0b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001e0f  call    _CxxThrowException_0
0x180001e15  mov     [rbp+pExceptionObject], 8007000Eh
0x180001e1c  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180001e23  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001e27  call    _CxxThrowException_0
0x180001e2d  call    cs:__imp_GetLastError
0x180001e33  mov     ebx, eax
0x180001e35  lea     rdx, WPP_GLOBAL_Control
0x180001e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e43  cmp     rcx, rdx
0x180001e46  jz      short loc_180001E66
0x180001e48  test    byte ptr [rcx+1Ch], 2
0x180001e4c  jz      short loc_180001E66
0x180001e4e  mov     edx, 0Ah
0x180001e53  mov     r9d, eax
0x180001e56  lea     r8, WPP_ea7d1c204d33352b702f4b4b9615bef9_Traceguids
0x180001e5d  mov     rcx, [rcx+10h]
0x180001e61  call    WPP_SF_D
0x180001e66  test    ebx, ebx
0x180001e68  jle     short loc_180001E73
0x180001e6a  movzx   ebx, bx
0x180001e6d  or      ebx, 80070000h
0x180001e73  mov     [rbp+pExceptionObject], ebx
0x180001e76  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180001e7d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001e81  call    _CxxThrowException_0
0x180001e87  call    cs:__imp_GetLastError
0x180001e8d  nop
0x180001e8e  mov     ebx, eax
0x180001e90  lea     rdx, WPP_GLOBAL_Control
0x180001e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e9e  cmp     rcx, rdx
0x180001ea1  jz      short loc_180001EC1
0x180001ea3  test    byte ptr [rcx+1Ch], 2
0x180001ea7  jz      short loc_180001EC1
0x180001ea9  mov     edx, 1Eh
0x180001eae  mov     r9d, eax
0x180001eb1  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180001eb8  mov     rcx, [rcx+10h]
0x180001ebc  call    WPP_SF_D
0x180001ec1  test    ebx, ebx
0x180001ec3  jle     short loc_180001ECE
0x180001ec5  movzx   ebx, bx
0x180001ec8  or      ebx, 80070000h
0x180001ece  mov     [rbp+pExceptionObject], ebx
0x180001ed1  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180001ed8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001edc  call    _CxxThrowException_0
0x180001ee2  lea     rdx, WPP_GLOBAL_Control
0x180001ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ef0  cmp     rcx, rdx
0x180001ef3  jz      short loc_180001F10
0x180001ef5  test    byte ptr [rcx+1Ch], 2
0x180001ef9  jz      short loc_180001F10
0x180001efb  mov     edx, 1Fh
0x180001f00  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180001f07  mov     rcx, [rcx+10h]
0x180001f0b  call    WPP_SF_
0x180001f10  mov     [rbp+pExceptionObject], 8007000Dh
0x180001f17  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180001f1e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001f22  call    _CxxThrowException_0
0x180001f28  mov     word ptr [r14+rcx*2], 5Ch ; '\'
0x180001f2f  inc     rcx
0x180001f32  jmp     loc_180001CF9
0x180001f37  call    cs:__imp_GetLastError
0x180001f3d  mov     [rbp+var_3C], eax
0x180001f40  lea     rdx, WPP_GLOBAL_Control
0x180001f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f4e  cmp     rcx, rdx
0x180001f51  jz      short loc_180001F74
0x180001f53  test    byte ptr [rcx+1Ch], 2
0x180001f57  jz      short loc_180001F74
0x180001f59  mov     edx, 20h ; ' '
0x180001f5e  mov     r9d, eax
0x180001f61  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180001f68  mov     rcx, [rcx+10h]
0x180001f6c  call    WPP_SF_D
0x180001f71  mov     eax, [rbp+var_3C]
0x180001f74  cmp     [rbp+pExceptionObject], 1
0x180001f78  jbe     short loc_180001FCB
0x180001f7a  mov     [rbp+var_30], rdi
0x180001f7e  lea     r12, [r12+1]
0x180001f83  cmp     word ptr [rdi+r12*2], 0
0x180001f89  jnz     short loc_180001F7E
0x180001f8b  lea     eax, ds:2[r12*2]
0x180001f93  mov     [rbp+var_28], eax
0x180001f96  xor     eax, eax
0x180001f98  mov     [rbp+var_24], eax
0x180001f9b  lea     rcx, [rbp+var_3C]
0x180001f9f  mov     [rbp+var_20], rcx
0x180001fa3  mov     [rbp+var_18], 4
0x180001fab  lea     r8, [rbp+var_30]
0x180001faf  mov     edx, 2
0x180001fb4  lea     rcx, DM_LOG_ERROR_PROVIDERLOAD
0x180001fbb  call    _LogReport
0x180001fc0  xor     ecx, ecx; hMem
0x180001fc2  call    cs:__imp_LocalFree
0x180001fc8  mov     eax, [rbp+var_3C]
0x180001fcb  test    eax, eax
0x180001fcd  jle     short loc_180001FD7
0x180001fcf  movzx   eax, ax
0x180001fd2  or      eax, 80070000h
0x180001fd7  mov     [rbp+pExceptionObject], eax
0x180001fda  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180001fe1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180001fe5  call    _CxxThrowException_0
0x180001feb  lea     rdx, WPP_GLOBAL_Control
0x180001ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ff9  cmp     rcx, rdx
0x180001ffc  jz      short loc_180002019
0x180001ffe  test    byte ptr [rcx+1Ch], 2
0x180002002  jz      short loc_180002019
0x180002004  mov     edx, 1Bh
0x180002009  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180002010  mov     rcx, [rcx+10h]
0x180002014  call    WPP_SF_
0x180002019  mov     [rbp+pExceptionObject], 80070057h
0x180002020  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180002027  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000202b  call    _CxxThrowException_0
0x180002031  call    cs:__imp_GetLastError
0x180002037  mov     [rbp+var_3C], eax
0x18000203a  lea     rdx, WPP_GLOBAL_Control
0x180002041  mov     rcx, cs:WPP_GLOBAL_Control
0x180002048  cmp     rcx, rdx
0x18000204b  jz      short loc_18000206E
0x18000204d  test    byte ptr [rcx+1Ch], 2
0x180002051  jz      short loc_18000206E
0x180002053  mov     edx, 21h ; '!'
0x180002058  mov     r9d, eax
0x18000205b  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180002062  mov     rcx, [rcx+10h]
0x180002066  call    WPP_SF_D
0x18000206b  mov     eax, [rbp+var_3C]
0x18000206e  cmp     ebx, 1
0x180002071  jbe     short loc_1800020C4
0x180002073  mov     [rbp+var_30], rdi
0x180002077  lea     r12, [r12+1]
0x18000207c  cmp     word ptr [rdi+r12*2], 0
0x180002082  jnz     short loc_180002077
0x180002084  lea     eax, ds:2[r12*2]
0x18000208c  mov     [rbp+var_28], eax
0x18000208f  xor     eax, eax
0x180002091  mov     [rbp+var_24], eax
0x180002094  lea     rcx, [rbp+var_3C]
0x180002098  mov     [rbp+var_20], rcx
0x18000209c  mov     [rbp+var_18], 4
0x1800020a4  lea     r8, [rbp+var_30]
0x1800020a8  mov     edx, 2
0x1800020ad  lea     rcx, DM_LOG_ERROR_PROVIDERLOAD
0x1800020b4  call    _LogReport
0x1800020b9  xor     ecx, ecx; hMem
0x1800020bb  call    cs:__imp_LocalFree
0x1800020c1  mov     eax, [rbp+var_3C]
0x1800020c4  test    eax, eax
0x1800020c6  jle     short loc_1800020D0
0x1800020c8  movzx   eax, ax
0x1800020cb  or      eax, 80070000h
0x1800020d0  mov     [rbp+pExceptionObject], eax
0x1800020d3  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x1800020da  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800020de  call    _CxxThrowException_0
```
