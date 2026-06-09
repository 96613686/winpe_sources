# DwAddLinkageKeysIfNotPresentAtStart(ushort *,ushort *,ushort *,ushort *,int *,ulong)

- ea: `0x18006cf0c`
- end: `0x18006d230`
- name: `?DwAddLinkageKeysIfNotPresentAtStart@@YAKPEAG000PEAHK@Z`
- size: `804`
- prototype: `unsigned int __fastcall(unsigned __int16 *, LPCWSTR lpSubKey, LPCWSTR lpValueName, STRSAFE_LPCWSTR pszSrc, int *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18006d42c`
- `0x18006d8c8`

## callees

- `0x180002be6`
- `0x180028058`
- `0x18002812c`
- `0x18006cf0c`
- `0x18006de6c`
- `0x18006e34c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006d166`
- `KERNEL32!LocalFree` at `0x18006d1a6`
- `KERNEL32!LocalFree` at `0x18006d166`
- `KERNEL32!LocalFree` at `0x18006d1a6`
- `KERNEL32!GetLastError` at `0x18006d174`
- `KERNEL32!GetLastError` at `0x18006d174`
- `KERNEL32!LocalAlloc` at `0x18006d08b`
- `KERNEL32!LocalAlloc` at `0x18006d08b`
- `ADVAPI32!RegSetValueExW` at `0x18006d155`
- `ADVAPI32!RegSetValueExW` at `0x18006d155`
- `ADVAPI32!RegOpenKeyExW` at `0x18006cf9d`
- `ADVAPI32!RegOpenKeyExW` at `0x18006cf9d`
- `ADVAPI32!RegCloseKey` at `0x18006d192`
- `ADVAPI32!RegCloseKey` at `0x18006d192`

## string_xrefs

- `0x18006d1b9`: `DwAddLinkageKeysAtStart: Function failed with error %d`
- `0x18006d1da`: `DwAddLinkageKeysAtStart: Function failed with error %d`

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
  int v16; // r12d
  _WORD *v17; // rdx
  __int64 v18; // rax
  unsigned __int64 v19; // r10
  unsigned __int64 v20; // rax
  __int64 v21; // rax
  char *v22; // rcx
  unsigned __int16 *v23; // rax
  signed __int64 v24; // rcx
  int v25; // r9d
  int v26; // r8d
  wchar_t *v27; // rax
  unsigned __int16 *v28; // rsi
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned __int16 *v33; // rax
  bool v34; // zf
  _WORD *v35; // rcx
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpValueNamea; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v42[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  lpValueNamea = lpValueName;
  Src = 0;
  hKey = 0;
  uBytes = 0;
  v41 = 0;
  v9 = 0;
  memset_0(v42, 0, sizeof(v42));
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
          v19 = (unsigned int)v18;
          v20 = -1;
          do
            ++v20;
          while ( pszSrc[v20] );
          if ( v19 >= v20 )
          {
            v21 = -1;
            do
              ++v21;
            while ( pszSrc[v21] );
            v22 = (char *)&v17[v21];
            if ( *(_WORD *)v22 == 123 )
            {
              v23 = a1;
              v24 = v22 - (char *)a1;
              do
              {
                v25 = *(unsigned __int16 *)((char *)v23 + v24);
                v26 = *v23 - v25;
                if ( v26 )
                  break;
                ++v23;
              }
              while ( v25 );
              if ( !v26 )
                break;
            }
          }
          v17 += v19 + 1;
          if ( !*v17 )
            goto LABEL_19;
        }
        *a5 = 1;
      }
LABEL_19:
      if ( !*a5 )
      {
        v27 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)uBytes);
        v28 = v27;
        if ( v27 )
        {
          v29 = -1;
          do
            ++v29;
          while ( pszSrc[v29] );
          StringCchCopyW(v27, v29 + 1, pszSrc);
          v30 = -1;
          do
            ++v30;
          while ( pszSrc[v30] );
          v31 = -1;
          do
            ++v31;
          while ( a1[v31] );
          StringCchCatW(v28, v30 + v31 + 1, a1);
          v32 = -1;
          do
            ++v32;
          while ( pszSrc[v32] );
          do
            ++v15;
          while ( a1[v15] );
          memcpy_0(&v28[v15 + 1 + v32], v9, HIDWORD(uBytes));
          v33 = v28;
          while ( 1 )
          {
            v34 = *v33 == 0;
            v35 = ++v33;
            if ( v34 && !*v35 )
              break;
            ++v16;
          }
          LastError = RegSetValueExW(hKey, lpValueNamea, 0, 7u, (const BYTE *)v28, 2 * v16);
          LocalFree(v28);
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
    if ( (_QWORD)xmmword_1800D1020 )
    {
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, L"DwAddLinkageKeysAtStart: Function failed with error %d", LastError);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, xmmword_1800D1020, &v41);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18006cf0c  push    rbp
0x18006cf0e  push    rbx
0x18006cf0f  push    rsi
0x18006cf10  push    rdi
0x18006cf11  push    r12
0x18006cf13  push    r13
0x18006cf15  push    r14
0x18006cf17  push    r15
0x18006cf19  lea     rbp, [rsp-778h]
0x18006cf21  sub     rsp, 878h
0x18006cf28  mov     rax, cs:__security_cookie
0x18006cf2f  xor     rax, rsp
0x18006cf32  mov     [rbp+7B0h+var_50], rax
0x18006cf39  mov     rsi, [rbp+7B0h+arg_20]
0x18006cf40  xor     edi, edi
0x18006cf42  mov     r12, r8
0x18006cf45  mov     [rsp+8B0h+lpValueName], r8
0x18006cf4a  mov     rbx, rdx
0x18006cf4d  mov     [rsp+8B0h+Src], rdi
0x18006cf52  mov     r13, rcx
0x18006cf55  mov     [rsp+8B0h+hKey], rdi
0x18006cf5a  xor     edx, edx; Val
0x18006cf5c  mov     dword ptr [rsp+8B0h+uBytes+4], edi
0x18006cf60  mov     r8d, 7FCh; Size
0x18006cf66  mov     dword ptr [rsp+8B0h+uBytes], edi
0x18006cf6a  lea     rcx, [rsp+8B0h+var_84C]; void *
0x18006cf6f  mov     [rsp+8B0h+var_850], edi
0x18006cf73  mov     r14d, edi
0x18006cf76  mov     r15, r9
0x18006cf79  call    memset_0
0x18006cf7e  lea     rax, [rsp+8B0h+hKey]
0x18006cf83  mov     [rsi], edi
0x18006cf85  mov     r9d, 2001Bh; samDesired
0x18006cf8b  mov     [rsp+8B0h+phkResult], rax; phkResult
0x18006cf90  xor     r8d, r8d; ulOptions
0x18006cf93  mov     rdx, rbx; lpSubKey
0x18006cf96  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006cf9d  call    cs:__imp_RegOpenKeyExW
0x18006cfa4  nop     dword ptr [rax+rax+00h]
0x18006cfa9  mov     edi, [rbp+7B0h+arg_28]
0x18006cfaf  mov     ebx, eax
0x18006cfb1  test    eax, eax
0x18006cfb3  jnz     loc_18006D188
0x18006cfb9  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18006cfbe  lea     rax, [rsp+8B0h+uBytes+4]
0x18006cfc3  mov     [rsp+8B0h+var_880], edi; unsigned int
0x18006cfc7  lea     r9, [rsp+8B0h+Src]; unsigned __int8 **
0x18006cfcc  mov     qword ptr [rsp+8B0h+cbData], rax; unsigned int *
0x18006cfd1  mov     rdx, r12; lpValueName
0x18006cfd4  lea     rax, [rsp+8B0h+uBytes]
0x18006cfd9  mov     [rsp+8B0h+phkResult], rax; unsigned int *
0x18006cfde  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x18006cfe3  mov     r14, [rsp+8B0h+Src]
0x18006cfe8  xor     r11d, r11d
0x18006cfeb  mov     ebx, eax
0x18006cfed  test    eax, eax
0x18006cfef  jnz     loc_18006D188
0x18006cff5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006cff9  lea     r12d, [rax+2]
0x18006cffd  mov     rdx, r14
0x18006d000  cmp     [r14], r11w
0x18006d004  jz      short loc_18006D079
0x18006d006  mov     rax, rdi
0x18006d009  inc     rax
0x18006d00c  cmp     [rdx+rax*2], r11w
0x18006d011  jnz     short loc_18006D009
0x18006d013  mov     r10d, eax
0x18006d016  mov     rax, rdi
0x18006d019  inc     rax
0x18006d01c  cmp     [r15+rax*2], r11w
0x18006d021  jnz     short loc_18006D019
0x18006d023  cmp     r10, rax
0x18006d026  jb      short loc_18006D064
0x18006d028  mov     rax, rdi
0x18006d02b  inc     rax
0x18006d02e  cmp     [r15+rax*2], r11w
0x18006d033  jnz     short loc_18006D02B
0x18006d035  lea     rcx, [rdx+rax*2]
0x18006d039  mov     eax, 7Bh ; '{'
0x18006d03e  cmp     ax, [rcx]
0x18006d041  jnz     short loc_18006D064
0x18006d043  mov     rax, r13
0x18006d046  sub     rcx, r13
0x18006d049  movzx   r8d, word ptr [rax]
0x18006d04d  movzx   r9d, word ptr [rax+rcx]
0x18006d052  sub     r8d, r9d
0x18006d055  jnz     short loc_18006D05F
0x18006d057  add     rax, r12
0x18006d05a  test    r9d, r9d
0x18006d05d  jnz     short loc_18006D049
0x18006d05f  test    r8d, r8d
0x18006d062  jz      short loc_18006D073
0x18006d064  lea     rdx, [rdx+r10*2]
0x18006d068  add     rdx, r12
0x18006d06b  cmp     [rdx], r11w
0x18006d06f  jnz     short loc_18006D006
0x18006d071  jmp     short loc_18006D079
0x18006d073  mov     dword ptr [rsi], 1
0x18006d079  cmp     [rsi], r11d
0x18006d07c  jnz     loc_18006D182
0x18006d082  mov     edx, dword ptr [rsp+8B0h+uBytes]; uBytes
0x18006d086  mov     ecx, 40h ; '@'; uFlags
0x18006d08b  call    cs:__imp_LocalAlloc
0x18006d092  nop     dword ptr [rax+rax+00h]
0x18006d097  xor     ebx, ebx
0x18006d099  mov     rsi, rax
0x18006d09c  test    rax, rax
0x18006d09f  jz      loc_18006D174
0x18006d0a5  mov     rdx, rdi
0x18006d0a8  inc     rdx
0x18006d0ab  cmp     [r15+rdx*2], bx
0x18006d0b0  jnz     short loc_18006D0A8
0x18006d0b2  inc     rdx; cchDest
0x18006d0b5  mov     r8, r15; pszSrc
0x18006d0b8  mov     rcx, rsi; pszDest
0x18006d0bb  call    StringCchCopyW
0x18006d0c0  mov     rcx, rdi
0x18006d0c3  inc     rcx
0x18006d0c6  cmp     [r15+rcx*2], bx
0x18006d0cb  jnz     short loc_18006D0C3
0x18006d0cd  mov     rax, rdi
0x18006d0d0  inc     rax
0x18006d0d3  cmp     [r13+rax*2+0], bx
0x18006d0d9  jnz     short loc_18006D0D0
0x18006d0db  lea     rdx, [rax+1]
0x18006d0df  mov     r8, r13; unsigned __int16 *
0x18006d0e2  add     rdx, rcx; unsigned __int64
0x18006d0e5  mov     rcx, rsi; unsigned __int16 *
0x18006d0e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006d0ed  mov     r8d, dword ptr [rsp+8B0h+uBytes+4]; Size
0x18006d0f2  mov     rax, rdi
0x18006d0f5  inc     rax
0x18006d0f8  cmp     [r15+rax*2], bx
0x18006d0fd  jnz     short loc_18006D0F5
0x18006d0ff  inc     rdi
0x18006d102  cmp     [r13+rdi*2+0], bx
0x18006d108  jnz     short loc_18006D0FF
0x18006d10a  inc     rax
0x18006d10d  mov     rdx, r14; Src
0x18006d110  add     rax, rdi
0x18006d113  lea     rcx, [rsi+rax*2]; void *
0x18006d117  call    memcpy_0
0x18006d11c  mov     rax, rsi
0x18006d11f  cmp     [rax], bx
0x18006d122  lea     rcx, [rax+2]
0x18006d126  mov     rax, rcx
0x18006d129  jnz     short loc_18006D130
0x18006d12b  cmp     [rcx], bx
0x18006d12e  jz      short loc_18006D135
0x18006d130  inc     r12d
0x18006d133  jmp     short loc_18006D11F
0x18006d135  mov     rdx, [rsp+8B0h+lpValueName]; lpValueName
0x18006d13a  lea     eax, [r12+r12]
0x18006d13e  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18006d143  mov     r9d, 7; dwType
0x18006d149  mov     [rsp+8B0h+cbData], eax; cbData
0x18006d14d  xor     r8d, r8d; Reserved
0x18006d150  mov     [rsp+8B0h+phkResult], rsi; lpData
0x18006d155  call    cs:__imp_RegSetValueExW
0x18006d15c  nop     dword ptr [rax+rax+00h]
0x18006d161  mov     rcx, rsi; hMem
0x18006d164  mov     ebx, eax
0x18006d166  call    cs:__imp_LocalFree
0x18006d16d  nop     dword ptr [rax+rax+00h]
0x18006d172  jmp     short loc_18006D182
0x18006d174  call    cs:__imp_GetLastError
0x18006d17b  nop     dword ptr [rax+rax+00h]
0x18006d180  mov     ebx, eax
0x18006d182  mov     edi, [rbp+7B0h+arg_28]
0x18006d188  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18006d18d  test    rcx, rcx
0x18006d190  jz      short loc_18006D19E
0x18006d192  call    cs:__imp_RegCloseKey
0x18006d199  nop     dword ptr [rax+rax+00h]
0x18006d19e  test    r14, r14
0x18006d1a1  jz      short loc_18006D1B2
0x18006d1a3  mov     rcx, r14; hMem
0x18006d1a6  call    cs:__imp_LocalFree
0x18006d1ad  nop     dword ptr [rax+rax+00h]
0x18006d1b2  test    ebx, ebx
0x18006d1b4  jz      short loc_18006D20A
0x18006d1b6  mov     r8d, ebx
0x18006d1b9  lea     rdx, aDwaddlinkageke; "DwAddLinkageKeysAtStart: Function faile"...
0x18006d1c0  mov     ecx, edi; unsigned int
0x18006d1c2  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006d1c7  xor     eax, eax
0x18006d1c9  cmp     qword ptr cs:xmmword_1800D1020, rax
0x18006d1d0  jz      short loc_18006D20A
0x18006d1d2  mov     r8d, ebx
0x18006d1d5  mov     word ptr [rsp+8B0h+var_850], ax
0x18006d1da  lea     rdx, aDwaddlinkageke_0; "DwAddLinkageKeysAtStart: Function faile"...
0x18006d1e1  lea     rcx, [rsp+8B0h+var_850]
0x18006d1e6  call    FormatRRASErrorString
0x18006d1eb  mov     rdx, qword ptr cs:xmmword_1800D1020
0x18006d1f2  lea     r8, [rsp+8B0h+var_850]
0x18006d1f7  mov     rcx, cs:gRegHelpEtwContext
0x18006d1fe  mov     rax, cs:gRegHelpTemplateFunc
0x18006d205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d20a  mov     eax, ebx
0x18006d20c  mov     rcx, [rbp+7B0h+var_50]
0x18006d213  xor     rcx, rsp; StackCookie
0x18006d216  call    __security_check_cookie
0x18006d21b  add     rsp, 878h
0x18006d222  pop     r15
0x18006d224  pop     r14
0x18006d226  pop     r13
0x18006d228  pop     r12
0x18006d22a  pop     rdi
0x18006d22b  pop     rsi
0x18006d22c  pop     rbx
0x18006d22d  pop     rbp
0x18006d22e  retn
```
