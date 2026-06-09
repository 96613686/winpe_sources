# CMDCOM::ComMDExportW(ulong,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180017e90`
- end: `0x180018103`
- name: `?ComMDExportW@CMDCOM@@UEAAJKPEBG00K@Z`
- size: `627`
- prototype: `__int64 __fastcall(CMDCOM *this, unsigned int, const unsigned __int16 *, wchar_t *, wchar_t *String1, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800089c8`
- `0x180009bd0`
- `0x180017e90`
- `0x18001f548`
- `0x180024e90`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180017eef`
- `msvcrt!_wcsnicmp` at `0x180017f0b`
- `msvcrt!_wcsnicmp` at `0x180017eef`
- `msvcrt!_wcsnicmp` at `0x180017f0b`
- `ole32!CoTaskMemFree` at `0x18001802f`
- `ole32!CoTaskMemFree` at `0x18001802f`
- `KERNEL32!CreateFileW` at `0x18001805f`
- `KERNEL32!CreateFileW` at `0x18001805f`
- `KERNEL32!SetFileTime` at `0x18001808d`
- `KERNEL32!SetFileTime` at `0x18001808d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180018078`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180018078`
- `KERNEL32!CloseHandle` at `0x180018096`
- `KERNEL32!CloseHandle` at `0x180018096`
- `KERNEL32!WaitForSingleObject` at `0x180017f89`
- `KERNEL32!WaitForSingleObject` at `0x180017f89`
- `KERNEL32!ReleaseSemaphore` at `0x1800180b4`
- `KERNEL32!ReleaseSemaphore` at `0x1800180b4`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180017f5f`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180017f5f`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180017fc7`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180017fc7`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180017f36`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180017f36`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180017f72`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180017f72`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDExportW(
        CMDCOM *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        wchar_t *a4,
        wchar_t *String1,
        unsigned int a6)
{
  int inited; // edi
  const unsigned __int16 *v11; // rdx
  struct IIS_CRYPTO_STORAGE *v12; // rax
  struct IIS_CRYPTO_STORAGE *v13; // rbx
  char *StrA; // rax
  __int64 v15; // r8
  _BYTE *v16; // r14
  HANDLE FileW; // rsi
  unsigned int v18; // edx
  LPVOID pv[2]; // [rsp+50h] [rbp-89h] BYREF
  _BYTE v20[128]; // [rsp+60h] [rbp-79h] BYREF

  pv[0] = 0;
  if ( !a4 || !String1 )
    return 2147942487LL;
  if ( !_wcsnicmp(String1, L"/lm/w3svc", 9u) || !_wcsnicmp(String1, L"lm/w3svc", 8u) )
    return 2147942450LL;
  if ( (a6 & 0xFFFFFFFC) != 0 && a6 )
    return 2147943404LL;
  STRAU::STRAU((STRAU *)v20);
  if ( g_dwInitialized )
  {
    v11 = (const unsigned __int16 *)&qword_18003A6B0;
    if ( a3 )
      v11 = a3;
    if ( STRAU::Copy((STRAU *)v20, v11) )
    {
      WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
      v12 = (struct IIS_CRYPTO_STORAGE *)operator new(0x30u);
      v13 = v12;
      if ( v12 )
      {
        *((_QWORD *)v12 + 1) = 0;
        *((_DWORD *)v12 + 4) = 0;
        *((_QWORD *)v12 + 3) = 0;
        *((_QWORD *)v12 + 4) = 0;
        *((_QWORD *)v12 + 5) = 0;
        *(_QWORD *)v12 = &IIS_CRYPTO_STORAGE2::`vftable';
        StrA = STRAU::QueryStrA((STRAU *)v20);
        inited = InitStorageAndSessionKey2(StrA, v13, (struct _IIS_CRYPTO_BLOB **)pv, 0);
        if ( inited >= 0 )
        {
          v16 = pv[0];
          if ( g_dwInitialized )
            inited = SaveSomeData(a6 & 1, a6 & 2, v15, v13, (struct _IIS_CRYPTO_BLOB *)pv[0], a4, a2, String1);
          else
            inited = -2146646016;
          *v16 = 88;
          CoTaskMemFree(v16);
          if ( inited >= 0 )
          {
            FileW = CreateFileW(a4, 0xC0000000, 0, 0, 3u, 0x80u, 0);
            if ( FileW != (HANDLE)-1LL )
            {
              pv[0] = 0;
              GetSystemTimeAsFileTime((LPFILETIME)pv);
              SetFileTime(FileW, 0, (const FILETIME *)pv, (const FILETIME *)pv);
              CloseHandle(FileW);
            }
          }
        }
      }
      else
      {
        inited = -2147024882;
        v13 = 0;
      }
      ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
      if ( v13 )
        IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v13, v18);
    }
    else
    {
      inited = -2147024882;
    }
  }
  else
  {
    inited = -2146646016;
  }
  STRAU::~STRAU((STRAU *)v20);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180017e90  mov     [rsp-8+arg_0], rbx
0x180017e95  push    rbp
0x180017e96  push    rsi
0x180017e97  push    rdi
0x180017e98  push    r12
0x180017e9a  push    r13
0x180017e9c  push    r14
0x180017e9e  push    r15
0x180017ea0  lea     rbp, [rsp-17h]
0x180017ea5  sub     rsp, 0F0h
0x180017eac  mov     rax, cs:__security_cookie
0x180017eb3  xor     rax, rsp
0x180017eb6  mov     [rbp+47h+var_40], rax
0x180017eba  mov     r15, [rbp+47h+String1]
0x180017ebe  xor     r14d, r14d
0x180017ec1  mov     [rsp+120h+pv], r14
0x180017ec6  mov     r12, r9
0x180017ec9  mov     rbx, r8
0x180017ecc  mov     r13d, edx
0x180017ecf  test    r9, r9
0x180017ed2  jz      loc_1800180D7
0x180017ed8  test    r15, r15
0x180017edb  jz      loc_1800180D7
0x180017ee1  lea     r8d, [r14+9]; MaxCount
0x180017ee5  mov     rcx, r15; String1
0x180017ee8  lea     rdx, aLmW3svc_0; "/lm/w3svc"
0x180017eef  call    cs:__imp__wcsnicmp
0x180017ef5  test    eax, eax
0x180017ef7  jz      loc_1800180D0
0x180017efd  lea     r8d, [r14+8]; MaxCount
0x180017f01  mov     rcx, r15; String1
0x180017f04  lea     rdx, aLmW3svc; "lm/w3svc"
0x180017f0b  call    cs:__imp__wcsnicmp
0x180017f11  test    eax, eax
0x180017f13  jz      loc_1800180D0
0x180017f19  mov     esi, [rbp+47h+arg_28]
0x180017f1c  test    esi, 0FFFFFFFCh
0x180017f22  jz      short loc_180017F32
0x180017f24  test    esi, esi
0x180017f26  jz      short loc_180017F32
0x180017f28  mov     eax, 800703ECh
0x180017f2d  jmp     loc_1800180DC
0x180017f32  lea     rcx, [rbp+47h+var_C0]
0x180017f36  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180017f3c  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180017f42  test    eax, eax
0x180017f44  jnz     short loc_180017F4D
0x180017f46  mov     edi, 800CC800h
0x180017f4b  jmp     short loc_180017F6E
0x180017f4d  test    rbx, rbx
0x180017f50  lea     rdx, qword_18003A6B0
0x180017f57  lea     rcx, [rbp+47h+var_C0]
0x180017f5b  cmovnz  rdx, rbx
0x180017f5f  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x180017f65  test    eax, eax
0x180017f67  jnz     short loc_180017F7F
0x180017f69  mov     edi, 8007000Eh
0x180017f6e  lea     rcx, [rbp+47h+var_C0]
0x180017f72  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180017f78  mov     eax, edi
0x180017f7a  jmp     loc_1800180DC
0x180017f7f  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x180017f86  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017f89  call    cs:__imp_WaitForSingleObject
0x180017f8f  mov     ecx, 30h ; '0'; Size
0x180017f94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017f99  mov     rbx, rax
0x180017f9c  test    rax, rax
0x180017f9f  jz      loc_18001809E
0x180017fa5  mov     [rax+8], r14
0x180017fa9  lea     rcx, [rbp+47h+var_C0]
0x180017fad  mov     [rax+10h], r14d
0x180017fb1  mov     [rax+18h], r14
0x180017fb5  mov     [rax+20h], r14
0x180017fb9  mov     [rax+28h], r14
0x180017fbd  lea     rax, ??_7IIS_CRYPTO_STORAGE2@@6B@; const IIS_CRYPTO_STORAGE2::`vftable'
0x180017fc4  mov     [rbx], rax
0x180017fc7  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x180017fcd  xor     r9d, r9d; int
0x180017fd0  lea     r8, [rsp+120h+pv]; struct _IIS_CRYPTO_BLOB **
0x180017fd5  mov     rcx, rax; char *
0x180017fd8  mov     rdx, rbx; this
0x180017fdb  call    ?InitStorageAndSessionKey2@@YAJPEADPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@H@Z; InitStorageAndSessionKey2(char *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB * *,int)
0x180017fe0  mov     edi, eax
0x180017fe2  test    eax, eax
0x180017fe4  js      loc_1800180A6
0x180017fea  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180017ff0  mov     r14, [rsp+120h+pv]
0x180017ff5  test    eax, eax
0x180017ff7  jnz     short loc_180018000
0x180017ff9  mov     edi, 800CC800h
0x180017ffe  jmp     short loc_180018028
0x180018000  mov     edx, esi
0x180018002  mov     [rsp+120h+var_E8], r15; unsigned __int16 *
0x180018007  and     esi, 1
0x18001800a  mov     dword ptr [rsp+120h+hTemplateFile], r13d; unsigned int
0x18001800f  mov     ecx, esi; int
0x180018011  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], r12; Str
0x180018016  and     edx, 2; int
0x180018019  mov     qword ptr [rsp+120h+dwCreationDisposition], r14; struct _IIS_CRYPTO_BLOB *
0x18001801e  mov     r9, rbx; struct IIS_CRYPTO_STORAGE *
0x180018021  call    ?SaveSomeData@@YAJHHHPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEBGK2H@Z; SaveSomeData(int,int,int,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ushort const *,ulong,ushort const *,int)
0x180018026  mov     edi, eax
0x180018028  mov     rcx, r14; pv
0x18001802b  mov     byte ptr [r14], 58h ; 'X'
0x18001802f  call    cs:__imp_CoTaskMemFree
0x180018035  xor     r14d, r14d
0x180018038  test    edi, edi
0x18001803a  js      short loc_1800180A6
0x18001803c  mov     [rsp+120h+hTemplateFile], r14; hTemplateFile
0x180018041  xor     r9d, r9d; lpSecurityAttributes
0x180018044  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001804c  xor     r8d, r8d; dwShareMode
0x18001804f  mov     edx, 0C0000000h; dwDesiredAccess
0x180018054  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x18001805c  mov     rcx, r12; lpFileName
0x18001805f  call    cs:__imp_CreateFileW
0x180018065  mov     rsi, rax
0x180018068  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001806c  jz      short loc_1800180A6
0x18001806e  lea     rcx, [rsp+120h+pv]; lpSystemTimeAsFileTime
0x180018073  mov     [rsp+120h+pv], r14
0x180018078  call    cs:__imp_GetSystemTimeAsFileTime
0x18001807e  lea     r9, [rsp+120h+pv]; lpLastWriteTime
0x180018083  xor     edx, edx; lpCreationTime
0x180018085  lea     r8, [rsp+120h+pv]; lpLastAccessTime
0x18001808a  mov     rcx, rsi; hFile
0x18001808d  call    cs:__imp_SetFileTime
0x180018093  mov     rcx, rsi; hObject
0x180018096  call    cs:__imp_CloseHandle
0x18001809c  jmp     short loc_1800180A6
0x18001809e  mov     edi, 8007000Eh
0x1800180a3  mov     rbx, r14
0x1800180a6  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x1800180ad  xor     r8d, r8d; lpPreviousCount
0x1800180b0  lea     edx, [r8+1]; lReleaseCount
0x1800180b4  call    cs:__imp_ReleaseSemaphore
0x1800180ba  test    rbx, rbx
0x1800180bd  jz      loc_180017F6E
0x1800180c3  mov     rcx, rbx; this
0x1800180c6  call    ??_GIIS_CRYPTO_STORAGE@@QEAAPEAXI@Z; IIS_CRYPTO_STORAGE::`scalar deleting destructor'(uint)
0x1800180cb  jmp     loc_180017F6E
0x1800180d0  mov     eax, 80070032h
0x1800180d5  jmp     short loc_1800180DC
0x1800180d7  mov     eax, 80070057h
0x1800180dc  mov     rcx, [rbp+47h+var_40]
0x1800180e0  xor     rcx, rsp; StackCookie
0x1800180e3  call    __security_check_cookie
0x1800180e8  mov     rbx, [rsp+120h+arg_0]
0x1800180f0  add     rsp, 0F0h
0x1800180f7  pop     r15
0x1800180f9  pop     r14
0x1800180fb  pop     r13
0x1800180fd  pop     r12
0x1800180ff  pop     rdi
0x180018100  pop     rsi
0x180018101  pop     rbp
0x180018102  retn
```
