# CServerInstall::DriverNotInstalled(void)

- ea: `0x180028c48`
- end: `0x180028f9b`
- name: `?DriverNotInstalled@CServerInstall@@AEAAHXZ`
- size: `851`
- prototype: `__int64 __fastcall(CServerInstall *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028fb0`

## callees

- `0x180002300`
- `0x18000d7e0`
- `0x18001c660`
- `0x180028c48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180028e86`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180028eb8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180028edf`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180028e86`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180028eb8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180028edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f3b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180028f2a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180028f2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028cd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028db5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028e29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028cd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028db5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028e29`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180028f17`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180028f17`
- `SETUPAPI!SetupQueryInfVersionInformationW` at `0x180028e11`
- `SETUPAPI!SetupQueryInfVersionInformationW` at `0x180028e5a`
- `SETUPAPI!SetupQueryInfVersionInformationW` at `0x180028e11`
- `SETUPAPI!SetupQueryInfVersionInformationW` at `0x180028e5a`
- `SETUPAPI!SetupGetInfInformationW` at `0x180028d96`
- `SETUPAPI!SetupGetInfInformationW` at `0x180028de5`
- `SETUPAPI!SetupGetInfInformationW` at `0x180028d96`
- `SETUPAPI!SetupGetInfInformationW` at `0x180028de5`
- `WINSPOOL!EnumPrinterDriversW` at `0x180028cb4`
- `WINSPOOL!EnumPrinterDriversW` at `0x180028d15`
- `WINSPOOL!EnumPrinterDriversW` at `0x180028cb4`
- `WINSPOOL!EnumPrinterDriversW` at `0x180028d15`

## pseudocode

```c
__int64 __fastcall CServerInstall::DriverNotInstalled(CServerInstall *this)
{
  WCHAR *v2; // rdx
  BYTE *v3; // rax
  BYTE *v4; // r13
  unsigned int v5; // ebx
  wchar_t *v6; // rsi
  struct _SP_INF_INFORMATION *v7; // r14
  DWORD v8; // eax
  struct _FILETIME v9; // r12
  unsigned __int16 *v10; // rcx
  __int64 v11; // r10
  int v12; // r8d
  int v13; // r9d
  int v14; // r15d
  wchar_t *v15; // r12
  wchar_t *v16; // r12
  wchar_t *v17; // rcx
  wchar_t *v18; // rax
  WORD v19; // ax
  DWORD RequiredSize; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcReturned; // [rsp+44h] [rbp-34h] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp-30h] BYREF
  wchar_t *v24; // [rsp+50h] [rbp-28h]
  SYSTEMTIME SystemTime; // [rsp+58h] [rbp-20h] BYREF

  RequiredSize = 0;
  pcReturned = 0;
  v2 = (WCHAR *)PlatformEnv[MyPlatform];
  SystemTime = 0;
  if ( !EnumPrinterDriversW(0, v2, 6u, 0, 0, &RequiredSize, &pcReturned) && GetLastError() == 122 )
  {
    v3 = (BYTE *)LocalAlloc(0x40u, RequiredSize);
    v4 = v3;
    if ( v3 && EnumPrinterDriversW(0, (LPWSTR)PlatformEnv[MyPlatform], 6u, v3, RequiredSize, &RequiredSize, &pcReturned) )
    {
      v5 = 1;
      v6 = 0;
      v7 = 0;
      if ( pcReturned )
      {
        v8 = 0;
        v9 = (struct _FILETIME)v4;
        do
        {
          v10 = *(unsigned __int16 **)(*(_QWORD *)&v9 + 8LL);
          v11 = *((_QWORD *)this + 2) - (_QWORD)v10;
          do
          {
            v12 = *(unsigned __int16 *)((char *)v10 + v11);
            v13 = *v10 - v12;
            if ( v13 )
              break;
            ++v10;
          }
          while ( v12 );
          if ( !v13 )
            break;
          ++v8;
          *(_QWORD *)&v9 += 136LL;
        }
        while ( v8 < pcReturned );
        FileTime = v9;
        if ( v8 < pcReturned )
        {
          if ( SetupGetInfInformationW(*((LPCVOID *)this + 4), 2u, 0, 0, &RequiredSize) )
          {
            v7 = (struct _SP_INF_INFORMATION *)LocalAlloc(0x40u, RequiredSize);
            v14 = 87;
            if ( v7
              && SetupGetInfInformationW(*((LPCVOID *)this + 4), 2u, v7, RequiredSize, &RequiredSize)
              && SetupQueryInfVersionInformationW(v7, 0, L"DriverVer", 0, 0, &RequiredSize)
              && (v6 = (wchar_t *)LocalAlloc(0x40u, 2 * RequiredSize)) != 0
              && SetupQueryInfVersionInformationW(v7, 0, L"DriverVer", v6, RequiredSize, &RequiredSize) )
            {
              v15 = wcschr(v6, 0x2Fu);
              if ( v15
                && (*v15 = 0, SystemTime.wMonth = _o__wtoi(v6), v24 = v15 + 1, (v16 = wcschr(v15 + 1, 0x2Fu)) != 0) )
              {
                v17 = v24;
                *v16 = 0;
                SystemTime.wDay = _o__wtoi(v17);
                v18 = wcschr(v16 + 1, 0x2Fu);
                if ( v18 )
                  *v18 = 0;
                v19 = _o__wtoi(v16 + 1);
                v9 = FileTime;
                SystemTime.wYear = v19;
              }
              else
              {
                v9 = FileTime;
                *(_DWORD *)this = 87;
              }
            }
            else
            {
              *(_DWORD *)this = GetLastError();
            }
            if ( SystemTime.wYear )
            {
              v14 = 0;
              FileTime = 0;
              if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
              {
                if ( CompareFileTime(&FileTime, (const FILETIME *)(*(_QWORD *)&v9 + 88LL)) < 1 )
                  v5 = 0;
              }
            }
            *(_DWORD *)this = v14;
          }
          else
          {
            *(_DWORD *)this = GetLastError();
          }
        }
      }
    }
    else
    {
      *(_DWORD *)this = GetLastError();
      v5 = 1;
      if ( !v4 )
        return v5;
      v6 = 0;
      v7 = 0;
    }
    DllFreeSplMem(v4);
    if ( v7 )
      DllFreeSplMem(v7);
    if ( v6 )
      DllFreeSplMem(v6);
    return v5;
  }
  return 1;
}

```

## disassembly

```asm
0x180028c48  push    rbp
0x180028c4a  push    rbx
0x180028c4b  push    rsi
0x180028c4c  push    rdi
0x180028c4d  push    r12
0x180028c4f  push    r13
0x180028c51  push    r14
0x180028c53  push    r15
0x180028c55  mov     rbp, rsp
0x180028c58  sub     rsp, 78h
0x180028c5c  mov     rax, cs:__security_cookie
0x180028c63  xor     rax, rsp
0x180028c66  mov     [rbp+var_10], rax
0x180028c6a  movsxd  rdx, cs:MyPlatform
0x180028c71  lea     rax, [rbp+var_34]
0x180028c75  xor     r15d, r15d
0x180028c78  mov     [rsp+78h+pcReturned], rax; pcReturned
0x180028c7d  lea     rax, [rbp+RequiredSize]
0x180028c81  mov     [rbp+RequiredSize], r15d
0x180028c85  mov     rdi, rcx
0x180028c88  mov     [rsp+78h+pcbNeeded], rax; pcbNeeded
0x180028c8d  xorps   xmm0, xmm0
0x180028c90  mov     [rbp+var_34], r15d
0x180028c94  lea     ebx, [r15+6]
0x180028c98  mov     [rsp+78h+cbBuf], r15d; cbBuf
0x180028c9d  lea     rsi, PlatformEnv
0x180028ca4  mov     r8d, ebx; Level
0x180028ca7  mov     rdx, [rsi+rdx*8]; pEnvironment
0x180028cab  xor     r9d, r9d; pDriverInfo
0x180028cae  xor     ecx, ecx; pName
0x180028cb0  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180028cb4  call    cs:__imp_EnumPrinterDriversW
0x180028cba  test    eax, eax
0x180028cbc  jnz     loc_180028F79
0x180028cc2  call    cs:__imp_GetLastError
0x180028cc8  cmp     eax, 7Ah ; 'z'
0x180028ccb  jnz     loc_180028F79
0x180028cd1  mov     edx, [rbp+RequiredSize]; uBytes
0x180028cd4  lea     ecx, [rbx+3Ah]; uFlags
0x180028cd7  call    cs:__imp_LocalAlloc
0x180028cdd  mov     r13, rax
0x180028ce0  test    rax, rax
0x180028ce3  jz      loc_180028F3B
0x180028ce9  mov     ecx, [rbp+RequiredSize]
0x180028cec  lea     rax, [rbp+var_34]
0x180028cf0  movsxd  rdx, cs:MyPlatform
0x180028cf7  mov     r9, r13; pDriverInfo
0x180028cfa  mov     [rsp+78h+pcReturned], rax; pcReturned
0x180028cff  mov     r8d, ebx; Level
0x180028d02  lea     rax, [rbp+RequiredSize]
0x180028d06  mov     [rsp+78h+pcbNeeded], rax; pcbNeeded
0x180028d0b  mov     rdx, [rsi+rdx*8]; pEnvironment
0x180028d0f  mov     [rsp+78h+cbBuf], ecx; cbBuf
0x180028d13  xor     ecx, ecx; pName
0x180028d15  call    cs:__imp_EnumPrinterDriversW
0x180028d1b  test    eax, eax
0x180028d1d  jz      loc_180028F3B
0x180028d23  mov     edx, [rbp+var_34]
0x180028d26  lea     ebx, [r15+1]
0x180028d2a  mov     esi, r15d
0x180028d2d  mov     r14d, r15d
0x180028d30  test    edx, edx
0x180028d32  jz      loc_180028F53
0x180028d38  mov     eax, r15d
0x180028d3b  mov     r12, r13
0x180028d3e  mov     rcx, [r12+8]
0x180028d43  mov     r10, [rdi+10h]
0x180028d47  sub     r10, rcx
0x180028d4a  movzx   r9d, word ptr [rcx]
0x180028d4e  movzx   r8d, word ptr [rcx+r10]
0x180028d53  sub     r9d, r8d
0x180028d56  jnz     short loc_180028D61
0x180028d58  add     rcx, 2
0x180028d5c  test    r8d, r8d
0x180028d5f  jnz     short loc_180028D4A
0x180028d61  test    r9d, r9d
0x180028d64  jz      short loc_180028D73
0x180028d66  add     eax, ebx
0x180028d68  add     r12, 88h
0x180028d6f  cmp     eax, edx
0x180028d71  jb      short loc_180028D3E
0x180028d73  mov     qword ptr [rbp+FileTime.dwLowDateTime], r12
0x180028d77  cmp     eax, edx
0x180028d79  jnb     loc_180028F53
0x180028d7f  mov     rcx, [rdi+20h]; InfSpec
0x180028d83  lea     rax, [rbp+RequiredSize]
0x180028d87  xor     r9d, r9d; ReturnBufferSize
0x180028d8a  mov     qword ptr [rsp+78h+cbBuf], rax; RequiredSize
0x180028d8f  xor     r8d, r8d; ReturnBuffer
0x180028d92  lea     edx, [r9+2]; SearchControl
0x180028d96  call    cs:__imp_SetupGetInfInformationW
0x180028d9c  test    eax, eax
0x180028d9e  jnz     short loc_180028DAD
0x180028da0  call    cs:__imp_GetLastError
0x180028da6  mov     [rdi], eax
0x180028da8  jmp     loc_180028F53
0x180028dad  mov     edx, [rbp+RequiredSize]; uBytes
0x180028db0  mov     ecx, 40h ; '@'; uFlags
0x180028db5  call    cs:__imp_LocalAlloc
0x180028dbb  mov     r14, rax
0x180028dbe  mov     r15d, 57h ; 'W'
0x180028dc4  test    rax, rax
0x180028dc7  jz      loc_180028EF8
0x180028dcd  mov     r9d, [rbp+RequiredSize]; ReturnBufferSize
0x180028dd1  lea     rax, [rbp+RequiredSize]
0x180028dd5  mov     rcx, [rdi+20h]; InfSpec
0x180028dd9  lea     edx, [r15-55h]; SearchControl
0x180028ddd  mov     r8, r14; ReturnBuffer
0x180028de0  mov     qword ptr [rsp+78h+cbBuf], rax; RequiredSize
0x180028de5  call    cs:__imp_SetupGetInfInformationW
0x180028deb  xor     ecx, ecx
0x180028ded  test    eax, eax
0x180028def  jz      loc_180028EF8
0x180028df5  lea     rax, [rbp+RequiredSize]
0x180028df9  xor     r9d, r9d; ReturnBuffer
0x180028dfc  mov     [rsp+78h+pcbNeeded], rax; RequiredSize
0x180028e01  lea     r8, cszDriverVer; "DriverVer"
0x180028e08  mov     [rsp+78h+cbBuf], ecx; ReturnBufferSize
0x180028e0c  xor     edx, edx; InfIndex
0x180028e0e  mov     rcx, r14; InfInformation
0x180028e11  call    cs:__imp_SetupQueryInfVersionInformationW
0x180028e17  test    eax, eax
0x180028e19  jz      loc_180028EF8
0x180028e1f  mov     eax, [rbp+RequiredSize]
0x180028e22  lea     ecx, [r15-17h]; uFlags
0x180028e26  lea     edx, [rax+rax]; uBytes
0x180028e29  call    cs:__imp_LocalAlloc
0x180028e2f  mov     rsi, rax
0x180028e32  test    rax, rax
0x180028e35  jz      loc_180028EF8
0x180028e3b  mov     ecx, [rbp+RequiredSize]
0x180028e3e  lea     rax, [rbp+RequiredSize]
0x180028e42  mov     [rsp+78h+pcbNeeded], rax; RequiredSize
0x180028e47  lea     r8, cszDriverVer; "DriverVer"
0x180028e4e  mov     [rsp+78h+cbBuf], ecx; ReturnBufferSize
0x180028e52  mov     r9, rsi; ReturnBuffer
0x180028e55  mov     rcx, r14; InfInformation
0x180028e58  xor     edx, edx; InfIndex
0x180028e5a  call    cs:__imp_SetupQueryInfVersionInformationW
0x180028e60  test    eax, eax
0x180028e62  jz      loc_180028EF8
0x180028e68  lea     edx, [r15-28h]; Ch
0x180028e6c  mov     rcx, rsi; Str
0x180028e6f  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180028e74  mov     r12, rax
0x180028e77  xor     eax, eax
0x180028e79  test    r12, r12
0x180028e7c  jz      short loc_180028EEF
0x180028e7e  mov     rcx, rsi
0x180028e81  mov     [r12], ax
0x180028e86  call    cs:__imp__o__wtoi
0x180028e8c  mov     [rbp+SystemTime.wMonth], ax
0x180028e90  lea     edx, [r15-28h]; Ch
0x180028e94  lea     rax, [r12+2]
0x180028e99  mov     rcx, rax; Str
0x180028e9c  mov     [rbp+var_28], rax
0x180028ea0  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180028ea5  mov     r12, rax
0x180028ea8  xor     eax, eax
0x180028eaa  test    r12, r12
0x180028ead  jz      short loc_180028EEF
0x180028eaf  mov     rcx, [rbp+var_28]
0x180028eb3  mov     [r12], ax
0x180028eb8  call    cs:__imp__o__wtoi
0x180028ebe  lea     edx, [r15-28h]; Ch
0x180028ec2  mov     [rbp+SystemTime.wDay], ax
0x180028ec6  lea     rcx, [r12+2]; Str
0x180028ecb  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180028ed0  xor     ecx, ecx
0x180028ed2  test    rax, rax
0x180028ed5  jz      short loc_180028EDA
0x180028ed7  mov     [rax], cx
0x180028eda  lea     rcx, [r12+2]
0x180028edf  call    cs:__imp__o__wtoi
0x180028ee5  mov     r12, qword ptr [rbp+FileTime.dwLowDateTime]
0x180028ee9  mov     [rbp+SystemTime.wYear], ax
0x180028eed  jmp     short loc_180028F00
0x180028eef  mov     r12, qword ptr [rbp+FileTime.dwLowDateTime]
0x180028ef3  mov     [rdi], r15d
0x180028ef6  jmp     short loc_180028F02
0x180028ef8  call    cs:__imp_GetLastError
0x180028efe  mov     [rdi], eax
0x180028f00  xor     eax, eax
0x180028f02  cmp     [rbp+SystemTime.wYear], ax
0x180028f06  jz      short loc_180028F36
0x180028f08  xor     r15d, r15d
0x180028f0b  lea     rdx, [rbp+FileTime]; lpFileTime
0x180028f0f  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180028f13  mov     qword ptr [rbp+FileTime.dwLowDateTime], r15
0x180028f17  call    cs:__imp_SystemTimeToFileTime
0x180028f1d  test    eax, eax
0x180028f1f  jz      short loc_180028F36
0x180028f21  lea     rdx, [r12+58h]; lpFileTime2
0x180028f26  lea     rcx, [rbp+FileTime]; lpFileTime1
0x180028f2a  call    cs:__imp_CompareFileTime
0x180028f30  cmp     eax, ebx
0x180028f32  cmovl   ebx, r15d
0x180028f36  mov     [rdi], r15d
0x180028f39  jmp     short loc_180028F53
0x180028f3b  call    cs:__imp_GetLastError
0x180028f41  mov     [rdi], eax
0x180028f43  mov     ebx, 1
0x180028f48  test    r13, r13
0x180028f4b  jz      short loc_180028F75
0x180028f4d  mov     rsi, r15
0x180028f50  mov     r14, r15
0x180028f53  mov     rcx, r13
0x180028f56  call    DllFreeSplMem
0x180028f5b  test    r14, r14
0x180028f5e  jz      short loc_180028F68
0x180028f60  mov     rcx, r14
0x180028f63  call    DllFreeSplMem
0x180028f68  test    rsi, rsi
0x180028f6b  jz      short loc_180028F75
0x180028f6d  mov     rcx, rsi
0x180028f70  call    DllFreeSplMem
0x180028f75  mov     eax, ebx
0x180028f77  jmp     short loc_180028F7E
0x180028f79  mov     eax, 1
0x180028f7e  mov     rcx, [rbp+var_10]
0x180028f82  xor     rcx, rsp; StackCookie
0x180028f85  call    __security_check_cookie
0x180028f8a  add     rsp, 78h
0x180028f8e  pop     r15
0x180028f90  pop     r14
0x180028f92  pop     r13
0x180028f94  pop     r12
0x180028f96  pop     rdi
0x180028f97  pop     rsi
0x180028f98  pop     rbx
0x180028f99  pop     rbp
0x180028f9a  retn
```
