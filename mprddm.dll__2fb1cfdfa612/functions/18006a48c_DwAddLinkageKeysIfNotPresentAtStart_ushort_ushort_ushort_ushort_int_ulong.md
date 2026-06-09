# DwAddLinkageKeysIfNotPresentAtStart(ushort *,ushort *,ushort *,ushort *,int *,ulong)

- ea: `0x18006a48c`
- end: `0x18006a779`
- name: `?DwAddLinkageKeysIfNotPresentAtStart@@YAKPEAG000PEAHK@Z`
- size: `749`
- prototype: `unsigned int __fastcall(unsigned __int16 *, LPCWSTR lpSubKey, LPCWSTR lpValueName, STRSAFE_LPCWSTR pszSrc, int *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18006a97c`
- `0x18006ae10`

## callees

- `0x180002ba6`
- `0x180025e2c`
- `0x180025ef0`
- `0x18006a48c`
- `0x18006b384`
- `0x18006b82c`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006a6c7`
- `KERNEL32!LocalFree` at `0x18006a6f5`
- `KERNEL32!LocalFree` at `0x18006a6c7`
- `KERNEL32!LocalFree` at `0x18006a6f5`
- `KERNEL32!GetLastError` at `0x18006a6cf`
- `KERNEL32!GetLastError` at `0x18006a6cf`
- `KERNEL32!LocalAlloc` at `0x18006a5f8`
- `KERNEL32!LocalAlloc` at `0x18006a5f8`
- `ADVAPI32!RegSetValueExW` at `0x18006a6bc`
- `ADVAPI32!RegSetValueExW` at `0x18006a6bc`
- `ADVAPI32!RegOpenKeyExW` at `0x18006a51d`
- `ADVAPI32!RegOpenKeyExW` at `0x18006a51d`
- `ADVAPI32!RegCloseKey` at `0x18006a6e7`
- `ADVAPI32!RegCloseKey` at `0x18006a6e7`

## string_xrefs

- `0x18006a702`: `DwAddLinkageKeysAtStart: Function failed with error %d`
- `0x18006a71c`: `DwAddLinkageKeysAtStart: Function failed with error %d`

## pseudocode

```c
__int64 __fastcall DwAddLinkageKeysIfNotPresentAtStart(
        unsigned __int16 *a1,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        STRSAFE_LPCWSTR pszSrc,
        int *a5,
        unsigned int a6)
{
  void *v9; // r14
  unsigned int v11; // edi
  DWORD LastError; // ebx
  unsigned int v13; // r8d
  unsigned int ValueWithAllocW; // eax
  __int64 v15; // rdi
  int v16; // r15d
  _WORD *v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // r10
  char *v21; // rdx
  unsigned __int16 *v22; // rcx
  signed __int64 v23; // rdx
  int v24; // r8d
  int v25; // r9d
  wchar_t *v26; // rax
  unsigned __int16 *v27; // rsi
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned __int16 *v32; // rax
  bool v33; // zf
  _WORD *v34; // rcx
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpValueNamea; // [rsp+58h] [rbp-A8h]
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v41[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  lpValueNamea = lpValueName;
  Src = 0;
  hKey = 0;
  uBytes = 0;
  v40 = 0;
  v9 = 0;
  memset_0(v41, 0, sizeof(v41));
  *a5 = 0;
  v11 = a6;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Bu, &hKey);
  if ( !LastError )
  {
    ValueWithAllocW = RegQueryValueWithAllocW(
                        hKey,
                        lpValueName,
                        v13,
                        (unsigned __int8 **)&Src,
                        (unsigned int *)&uBytes,
                        (unsigned int *)&uBytes + 1,
                        a6);
    v9 = Src;
    LastError = ValueWithAllocW;
    if ( !ValueWithAllocW )
    {
      v15 = -1;
      v16 = 2;
      v17 = Src;
      if ( *(_WORD *)Src )
      {
        while ( 1 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v17[v18] );
          v19 = -1;
          do
            ++v19;
          while ( pszSrc[v19] );
          v20 = (unsigned int)v18;
          if ( (unsigned int)v18 >= v19 )
          {
            v21 = (char *)&v17[v19];
            if ( *(_WORD *)v21 == 123 )
            {
              v22 = a1;
              v23 = v21 - (char *)a1;
              do
              {
                v24 = *(unsigned __int16 *)((char *)v22 + v23);
                v25 = *v22 - v24;
                if ( v25 )
                  break;
                ++v22;
              }
              while ( v24 );
              if ( !v25 )
                break;
            }
          }
          v17 += v20 + 1;
          if ( !*v17 )
            goto LABEL_17;
        }
        *a5 = 1;
      }
LABEL_17:
      if ( !*a5 )
      {
        v26 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)uBytes);
        v27 = v26;
        if ( v26 )
        {
          v28 = -1;
          do
            ++v28;
          while ( pszSrc[v28] );
          StringCchCopyW(v26, v28 + 1, pszSrc);
          v29 = -1;
          do
            ++v29;
          while ( a1[v29] );
          v30 = -1;
          do
            ++v30;
          while ( pszSrc[v30] );
          StringCchCatW(v27, v30 + v29 + 1, a1);
          v31 = -1;
          do
            ++v31;
          while ( a1[v31] );
          do
            ++v15;
          while ( pszSrc[v15] );
          memcpy_0(&v27[v15 + 1 + v31], v9, HIDWORD(uBytes));
          v32 = v27;
          while ( 1 )
          {
            v33 = *v32 == 0;
            v34 = ++v32;
            if ( v33 && !*v34 )
              break;
            ++v16;
          }
          LastError = RegSetValueExW(hKey, lpValueNamea, 0, 7u, (const BYTE *)v27, 2 * v16);
          LocalFree(v27);
        }
        else
        {
          LastError = GetLastError();
        }
      }
      v11 = a6;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    LocalFree(v9);
  if ( LastError )
  {
    TraceIt(v11, "DwAddLinkageKeysAtStart: Function failed with error %d", LastError);
    if ( (_QWORD)xmmword_1800CA020 )
    {
      LOWORD(v40) = 0;
      FormatRRASErrorString(&v40, L"DwAddLinkageKeysAtStart: Function failed with error %d", LastError);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, xmmword_1800CA020, &v40);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18006a48c  push    rbp
0x18006a48e  push    rbx
0x18006a48f  push    rsi
0x18006a490  push    rdi
0x18006a491  push    r12
0x18006a493  push    r13
0x18006a495  push    r14
0x18006a497  push    r15
0x18006a499  lea     rbp, [rsp-778h]
0x18006a4a1  sub     rsp, 878h
0x18006a4a8  mov     rax, cs:__security_cookie
0x18006a4af  xor     rax, rsp
0x18006a4b2  mov     [rbp+7B0h+var_50], rax
0x18006a4b9  mov     rsi, [rbp+7B0h+arg_20]
0x18006a4c0  xor     edi, edi
0x18006a4c2  mov     r15, r8
0x18006a4c5  mov     [rsp+8B0h+lpValueName], r8
0x18006a4ca  mov     rbx, rdx
0x18006a4cd  mov     [rsp+8B0h+Src], rdi
0x18006a4d2  mov     r13, rcx
0x18006a4d5  mov     [rsp+8B0h+hKey], rdi
0x18006a4da  xor     edx, edx; Val
0x18006a4dc  mov     dword ptr [rsp+8B0h+uBytes+4], edi
0x18006a4e0  mov     r8d, 7FCh; Size
0x18006a4e6  mov     dword ptr [rsp+8B0h+uBytes], edi
0x18006a4ea  lea     rcx, [rsp+8B0h+var_84C]; void *
0x18006a4ef  mov     [rsp+8B0h+var_850], edi
0x18006a4f3  mov     r14d, edi
0x18006a4f6  mov     r12, r9
0x18006a4f9  call    memset_0
0x18006a4fe  lea     rax, [rsp+8B0h+hKey]
0x18006a503  mov     [rsi], edi
0x18006a505  mov     r9d, 2001Bh; samDesired
0x18006a50b  mov     [rsp+8B0h+phkResult], rax; phkResult
0x18006a510  xor     r8d, r8d; ulOptions
0x18006a513  mov     rdx, rbx; lpSubKey
0x18006a516  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006a51d  call    cs:__imp_RegOpenKeyExW
0x18006a523  mov     edi, [rbp+7B0h+arg_28]
0x18006a529  mov     ebx, eax
0x18006a52b  test    eax, eax
0x18006a52d  jnz     loc_18006A6DD
0x18006a533  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18006a538  lea     rax, [rsp+8B0h+uBytes+4]
0x18006a53d  mov     [rsp+8B0h+var_880], edi; unsigned int
0x18006a541  lea     r9, [rsp+8B0h+Src]; unsigned __int8 **
0x18006a546  mov     qword ptr [rsp+8B0h+cbData], rax; unsigned int *
0x18006a54b  mov     rdx, r15; lpValueName
0x18006a54e  lea     rax, [rsp+8B0h+uBytes]
0x18006a553  mov     [rsp+8B0h+phkResult], rax; unsigned int *
0x18006a558  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x18006a55d  mov     r14, [rsp+8B0h+Src]
0x18006a562  xor     r11d, r11d
0x18006a565  mov     ebx, eax
0x18006a567  test    eax, eax
0x18006a569  jnz     loc_18006A6DD
0x18006a56f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006a573  lea     r15d, [rbx+2]
0x18006a577  mov     rax, r14
0x18006a57a  cmp     [r14], r11w
0x18006a57e  jz      short loc_18006A5E6
0x18006a580  mov     rdx, rdi
0x18006a583  inc     rdx
0x18006a586  cmp     [rax+rdx*2], r11w
0x18006a58b  jnz     short loc_18006A583
0x18006a58d  mov     rcx, rdi
0x18006a590  inc     rcx
0x18006a593  cmp     [r12+rcx*2], r11w
0x18006a598  jnz     short loc_18006A590
0x18006a59a  mov     r10d, edx
0x18006a59d  cmp     r10, rcx
0x18006a5a0  jb      short loc_18006A5D1
0x18006a5a2  lea     rdx, [rax+rcx*2]
0x18006a5a6  mov     ecx, 7Bh ; '{'
0x18006a5ab  cmp     cx, [rdx]
0x18006a5ae  jnz     short loc_18006A5D1
0x18006a5b0  mov     rcx, r13
0x18006a5b3  sub     rdx, r13
0x18006a5b6  movzx   r9d, word ptr [rcx]
0x18006a5ba  movzx   r8d, word ptr [rcx+rdx]
0x18006a5bf  sub     r9d, r8d
0x18006a5c2  jnz     short loc_18006A5CC
0x18006a5c4  add     rcx, r15
0x18006a5c7  test    r8d, r8d
0x18006a5ca  jnz     short loc_18006A5B6
0x18006a5cc  test    r9d, r9d
0x18006a5cf  jz      short loc_18006A5E0
0x18006a5d1  lea     rax, [rax+r10*2]
0x18006a5d5  add     rax, r15
0x18006a5d8  cmp     [rax], r11w
0x18006a5dc  jnz     short loc_18006A580
0x18006a5de  jmp     short loc_18006A5E6
0x18006a5e0  mov     dword ptr [rsi], 1
0x18006a5e6  cmp     [rsi], r11d
0x18006a5e9  jnz     loc_18006A6D7
0x18006a5ef  mov     edx, dword ptr [rsp+8B0h+uBytes]; uBytes
0x18006a5f3  mov     ecx, 40h ; '@'; uFlags
0x18006a5f8  call    cs:__imp_LocalAlloc
0x18006a5fe  xor     ebx, ebx
0x18006a600  mov     rsi, rax
0x18006a603  test    rax, rax
0x18006a606  jz      loc_18006A6CF
0x18006a60c  mov     rdx, rdi
0x18006a60f  inc     rdx
0x18006a612  cmp     [r12+rdx*2], bx
0x18006a617  jnz     short loc_18006A60F
0x18006a619  inc     rdx; cchDest
0x18006a61c  mov     r8, r12; pszSrc
0x18006a61f  mov     rcx, rsi; pszDest
0x18006a622  call    StringCchCopyW
0x18006a627  mov     rcx, rdi
0x18006a62a  inc     rcx
0x18006a62d  cmp     [r13+rcx*2+0], bx
0x18006a633  jnz     short loc_18006A62A
0x18006a635  mov     rax, rdi
0x18006a638  inc     rax
0x18006a63b  cmp     [r12+rax*2], bx
0x18006a640  jnz     short loc_18006A638
0x18006a642  lea     rdx, [rcx+1]
0x18006a646  mov     r8, r13; unsigned __int16 *
0x18006a649  add     rdx, rax; unsigned __int64
0x18006a64c  mov     rcx, rsi; unsigned __int16 *
0x18006a64f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006a654  mov     rax, rdi
0x18006a657  inc     rax
0x18006a65a  cmp     [r13+rax*2+0], bx
0x18006a660  jnz     short loc_18006A657
0x18006a662  inc     rdi
0x18006a665  cmp     [r12+rdi*2], bx
0x18006a66a  jnz     short loc_18006A662
0x18006a66c  mov     r8d, dword ptr [rsp+8B0h+uBytes+4]; Size
0x18006a671  inc     rax
0x18006a674  add     rax, rdi
0x18006a677  mov     rdx, r14; Src
0x18006a67a  lea     rcx, [rsi+rax*2]; void *
0x18006a67e  call    memcpy_0
0x18006a683  mov     rax, rsi
0x18006a686  cmp     [rax], bx
0x18006a689  lea     rcx, [rax+2]
0x18006a68d  mov     rax, rcx
0x18006a690  jnz     short loc_18006A697
0x18006a692  cmp     [rcx], bx
0x18006a695  jz      short loc_18006A69C
0x18006a697  inc     r15d
0x18006a69a  jmp     short loc_18006A686
0x18006a69c  mov     rdx, [rsp+8B0h+lpValueName]; lpValueName
0x18006a6a1  lea     eax, [r15+r15]
0x18006a6a5  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18006a6aa  mov     r9d, 7; dwType
0x18006a6b0  mov     [rsp+8B0h+cbData], eax; cbData
0x18006a6b4  xor     r8d, r8d; Reserved
0x18006a6b7  mov     [rsp+8B0h+phkResult], rsi; lpData
0x18006a6bc  call    cs:__imp_RegSetValueExW
0x18006a6c2  mov     rcx, rsi; hMem
0x18006a6c5  mov     ebx, eax
0x18006a6c7  call    cs:__imp_LocalFree
0x18006a6cd  jmp     short loc_18006A6D7
0x18006a6cf  call    cs:__imp_GetLastError
0x18006a6d5  mov     ebx, eax
0x18006a6d7  mov     edi, [rbp+7B0h+arg_28]
0x18006a6dd  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18006a6e2  test    rcx, rcx
0x18006a6e5  jz      short loc_18006A6ED
0x18006a6e7  call    cs:__imp_RegCloseKey
0x18006a6ed  test    r14, r14
0x18006a6f0  jz      short loc_18006A6FB
0x18006a6f2  mov     rcx, r14; hMem
0x18006a6f5  call    cs:__imp_LocalFree
0x18006a6fb  test    ebx, ebx
0x18006a6fd  jz      short loc_18006A754
0x18006a6ff  mov     r8d, ebx
0x18006a702  lea     rdx, aDwaddlinkageke; "DwAddLinkageKeysAtStart: Function faile"...
0x18006a709  mov     ecx, edi; unsigned int
0x18006a70b  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006a710  cmp     qword ptr cs:xmmword_1800CA020, 0
0x18006a718  jz      short loc_18006A754
0x18006a71a  xor     eax, eax
0x18006a71c  lea     rdx, aDwaddlinkageke_0; "DwAddLinkageKeysAtStart: Function faile"...
0x18006a723  mov     r8d, ebx
0x18006a726  mov     word ptr [rsp+8B0h+var_850], ax
0x18006a72b  lea     rcx, [rsp+8B0h+var_850]
0x18006a730  call    FormatRRASErrorString
0x18006a735  mov     rdx, qword ptr cs:xmmword_1800CA020
0x18006a73c  lea     r8, [rsp+8B0h+var_850]
0x18006a741  mov     rcx, cs:gRegHelpEtwContext
0x18006a748  mov     rax, cs:gRegHelpTemplateFunc
0x18006a74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a754  mov     eax, ebx
0x18006a756  mov     rcx, [rbp+7B0h+var_50]
0x18006a75d  xor     rcx, rsp; StackCookie
0x18006a760  call    __security_check_cookie
0x18006a765  add     rsp, 878h
0x18006a76c  pop     r15
0x18006a76e  pop     r14
0x18006a770  pop     r13
0x18006a772  pop     r12
0x18006a774  pop     rdi
0x18006a775  pop     rsi
0x18006a776  pop     rbx
0x18006a777  pop     rbp
0x18006a778  retn
```
