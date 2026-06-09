# ReadDriversInfo

- ea: `0x180003d88`
- end: `0x180003f90`
- name: `ReadDriversInfo`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002e90`

## callees

- `0x180003d88`
- `0x180004088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003eca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003eca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003dad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003dad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180003f51`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180003f51`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180003edf`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180003edf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003f0a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003f0a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003dc5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003e82`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003dc5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003e82`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003e3b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003ea0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003f20`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003e3b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003ea0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003f20`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e32`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e48`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e97`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003ead`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003f17`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003f2d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e32`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e48`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e97`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003ead`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003f17`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003f2d`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerA` at `0x180003f48`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerA` at `0x180003f48`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003e51`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003eb6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003f36`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003e51`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003eb6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003f36`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003dbc`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003e79`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003dbc`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003e79`

## string_xrefs

- `0x180003e15`: `Installable Compressors`

## pseudocode

```c
__int64 ReadDriversInfo()
{
  unsigned int v0; // ebx
  HGLOBAL v1; // rax
  __int64 v2; // r8
  unsigned int PrivateProfileString; // eax
  __int64 v4; // r8
  unsigned __int64 v5; // r14
  unsigned int v6; // edi
  HGLOBAL v7; // rax
  HGLOBAL v8; // rax
  HGLOBAL v9; // rax
  CHAR *lpMultiByteStr; // rsi
  HGLOBAL v11; // rax
  HGLOBAL v12; // rax
  int cbMultiByte; // ebx
  const WCHAR *v14; // rdi
  UINT ACP; // eax
  HGLOBAL v16; // rax
  HGLOBAL v17; // rax

  if ( !pMem )
  {
    v0 = 250;
    EnterCriticalSection(&ICOpenCritSec);
    while ( 1 )
    {
      v1 = GlobalAlloc(0x2042u, v0);
      pMem = GlobalLock(v1);
      if ( !pMem )
        goto LABEL_10;
      PrivateProfileString = myGetPrivateProfileString(aDrivers32, 0, v2, pMem, v0 >> 1);
      v5 = ((unsigned __int64)v0 >> 1) - 5;
      if ( PrivateProfileString < v5 )
      {
        v6 = myGetPrivateProfileString(
               aInstallableCom,
               0,
               v4,
               (char *)pMem + 2 * PrivateProfileString,
               (v0 >> 1) - PrivateProfileString)
           + PrivateProfileString;
        if ( v6 < v5 )
          break;
      }
      v7 = GlobalHandle(pMem);
      GlobalUnlock(v7);
      v8 = GlobalHandle(pMem);
      GlobalFree(v8);
      pMem = 0;
      if ( v0 >= 0x8000 )
        goto LABEL_10;
      v0 *= 2;
    }
    v9 = GlobalAlloc(0x2042u, v6 + 7);
    lpMultiByteStr = (CHAR *)GlobalLock(v9);
    if ( !lpMultiByteStr )
    {
      v11 = GlobalHandle(pMem);
      GlobalUnlock(v11);
      v12 = GlobalHandle(pMem);
      GlobalFree(v12);
      pMem = 0;
LABEL_10:
      LeaveCriticalSection(&ICOpenCritSec);
      return 0;
    }
    cbMultiByte = v6 + 2;
    v14 = (const WCHAR *)pMem;
    ACP = GetACP();
    WideCharToMultiByte(ACP, 0, v14, cbMultiByte, lpMultiByteStr, cbMultiByte, 0, 0);
    v16 = GlobalHandle(pMem);
    GlobalUnlock(v16);
    v17 = GlobalHandle(pMem);
    GlobalFree(v17);
    pMem = lpMultiByteStr;
    while ( *lpMultiByteStr )
    {
      CharLowerA(lpMultiByteStr);
      lpMultiByteStr += lstrlenA(lpMultiByteStr) + 1;
    }
    LeaveCriticalSection(&ICOpenCritSec);
    if ( !pMem )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180003d88  push    rbx
0x180003d8a  push    rbp
0x180003d8b  push    rsi
0x180003d8c  push    rdi
0x180003d8d  push    r14
0x180003d8f  sub     rsp, 40h
0x180003d93  cmp     cs:pMem, 0
0x180003d9b  jnz     loc_180003F80
0x180003da1  lea     rcx, ICOpenCritSec; lpCriticalSection
0x180003da8  mov     ebx, 0FAh
0x180003dad  call    cs:__imp_EnterCriticalSection
0x180003db3  mov     edx, ebx; dwBytes
0x180003db5  mov     ecx, 2042h; uFlags
0x180003dba  mov     edi, ebx
0x180003dbc  call    cs:__imp_GlobalAlloc
0x180003dc2  mov     rcx, rax; hMem
0x180003dc5  call    cs:__imp_GlobalLock
0x180003dcb  mov     cs:pMem, rax
0x180003dd2  mov     r9, rax
0x180003dd5  test    rax, rax
0x180003dd8  jz      loc_180003EC3
0x180003dde  mov     esi, ebx
0x180003de0  lea     rcx, aDrivers32; "DRIVERS32"
0x180003de7  shr     esi, 1
0x180003de9  xor     edx, edx
0x180003deb  mov     dword ptr [rsp+68h+lpMultiByteStr], esi
0x180003def  call    myGetPrivateProfileString
0x180003df4  shr     rdi, 1
0x180003df7  mov     ebp, eax
0x180003df9  lea     r14, [rdi-5]
0x180003dfd  cmp     rbp, r14
0x180003e00  jnb     short loc_180003E2B
0x180003e02  mov     rcx, cs:pMem
0x180003e09  sub     esi, ebp
0x180003e0b  xor     edx, edx
0x180003e0d  mov     dword ptr [rsp+68h+lpMultiByteStr], esi
0x180003e11  lea     r9, [rcx+rbp*2]
0x180003e15  lea     rcx, aInstallableCom; "Installable Compressors"
0x180003e1c  call    myGetPrivateProfileString
0x180003e21  lea     edi, [rax+rbp]
0x180003e24  mov     eax, edi
0x180003e26  cmp     rax, r14
0x180003e29  jb      short loc_180003E71
0x180003e2b  mov     rcx, cs:pMem; pMem
0x180003e32  call    cs:__imp_GlobalHandle
0x180003e38  mov     rcx, rax; hMem
0x180003e3b  call    cs:__imp_GlobalUnlock
0x180003e41  mov     rcx, cs:pMem; pMem
0x180003e48  call    cs:__imp_GlobalHandle
0x180003e4e  mov     rcx, rax; hMem
0x180003e51  call    cs:__imp_GlobalFree
0x180003e57  mov     cs:pMem, 0
0x180003e62  cmp     ebx, 8000h
0x180003e68  jnb     short loc_180003EC3
0x180003e6a  add     ebx, ebx
0x180003e6c  jmp     loc_180003DB3
0x180003e71  lea     edx, [rdi+7]; dwBytes
0x180003e74  mov     ecx, 2042h; uFlags
0x180003e79  call    cs:__imp_GlobalAlloc
0x180003e7f  mov     rcx, rax; hMem
0x180003e82  call    cs:__imp_GlobalLock
0x180003e88  mov     rsi, rax
0x180003e8b  test    rax, rax
0x180003e8e  jnz     short loc_180003ED5
0x180003e90  mov     rcx, cs:pMem; pMem
0x180003e97  call    cs:__imp_GlobalHandle
0x180003e9d  mov     rcx, rax; hMem
0x180003ea0  call    cs:__imp_GlobalUnlock
0x180003ea6  mov     rcx, cs:pMem; pMem
0x180003ead  call    cs:__imp_GlobalHandle
0x180003eb3  mov     rcx, rax; hMem
0x180003eb6  call    cs:__imp_GlobalFree
0x180003ebc  mov     cs:pMem, rsi
0x180003ec3  lea     rcx, ICOpenCritSec; lpCriticalSection
0x180003eca  call    cs:__imp_LeaveCriticalSection
0x180003ed0  jmp     loc_180003F7C
0x180003ed5  lea     ebx, [rdi+2]
0x180003ed8  mov     rdi, cs:pMem
0x180003edf  call    cs:__imp_GetACP
0x180003ee5  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180003eee  mov     r9d, ebx; cchWideChar
0x180003ef1  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x180003efa  mov     ecx, eax; CodePage
0x180003efc  mov     [rsp+68h+cbMultiByte], ebx; cbMultiByte
0x180003f00  mov     r8, rdi; lpWideCharStr
0x180003f03  xor     edx, edx; dwFlags
0x180003f05  mov     [rsp+68h+lpMultiByteStr], rsi; lpMultiByteStr
0x180003f0a  call    cs:__imp_WideCharToMultiByte
0x180003f10  mov     rcx, cs:pMem; pMem
0x180003f17  call    cs:__imp_GlobalHandle
0x180003f1d  mov     rcx, rax; hMem
0x180003f20  call    cs:__imp_GlobalUnlock
0x180003f26  mov     rcx, cs:pMem; pMem
0x180003f2d  call    cs:__imp_GlobalHandle
0x180003f33  mov     rcx, rax; hMem
0x180003f36  call    cs:__imp_GlobalFree
0x180003f3c  mov     cs:pMem, rsi
0x180003f43  jmp     short loc_180003F60
0x180003f45  mov     rcx, rsi; lpsz
0x180003f48  call    cs:__imp_CharLowerA
0x180003f4e  mov     rcx, rsi; lpString
0x180003f51  call    cs:__imp_lstrlenA
0x180003f57  movsxd  rcx, eax
0x180003f5a  inc     rsi
0x180003f5d  add     rsi, rcx
0x180003f60  cmp     byte ptr [rsi], 0
0x180003f63  jnz     short loc_180003F45
0x180003f65  lea     rcx, ICOpenCritSec; lpCriticalSection
0x180003f6c  call    cs:__imp_LeaveCriticalSection
0x180003f72  cmp     cs:pMem, 0
0x180003f7a  jnz     short loc_180003F80
0x180003f7c  xor     eax, eax
0x180003f7e  jmp     short loc_180003F85
0x180003f80  mov     eax, 1
0x180003f85  add     rsp, 40h
0x180003f89  pop     r14
0x180003f8b  pop     rdi
0x180003f8c  pop     rsi
0x180003f8d  pop     rbp
0x180003f8e  pop     rbx
0x180003f8f  retn
```
