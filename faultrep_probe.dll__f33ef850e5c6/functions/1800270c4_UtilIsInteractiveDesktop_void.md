# UtilIsInteractiveDesktop(void)

- ea: `0x1800270c4`
- end: `0x1800273d2`
- name: `?UtilIsInteractiveDesktop@@YAHXZ`
- size: `782`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180011a38`
- `0x180026ed4`

## callees

- `0x1800028b4`
- `0x180003c50`
- `0x180009ed8`
- `0x180009f00`
- `0x180024bc4`
- `0x1800270c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027385`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027399`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027385`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027118`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002715e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002718c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002729f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002736b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002715e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002718c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002729f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002736b`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x18002710f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x18002710f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180027120`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180027120`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180027154`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18002723e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180027295`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180027349`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180027154`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18002723e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180027295`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180027349`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 UtilIsInteractiveDesktop(void)
{
  void *v0; // rdi
  void *v1; // rsi
  unsigned int v2; // r15d
  const struct std::nothrow_t *v3; // rdx
  HWINSTA ProcessWindowStation; // r14
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HDESK v7; // r12
  DWORD LastError; // eax
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  void **unique_for; // rax
  void **v13; // rax
  DWORD nLengthNeeded; // [rsp+70h] [rbp+40h] BYREF
  void *v16; // [rsp+78h] [rbp+48h]
  void *v17; // [rsp+80h] [rbp+50h] BYREF
  void *v18; // [rsp+88h] [rbp+58h]

  v0 = 0;
  v16 = 0;
  v1 = 0;
  v18 = 0;
  nLengthNeeded = 0;
  v2 = 0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_43;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_43;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    goto LABEL_43;
  ProcessWindowStation = GetProcessWindowStation();
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  v7 = ThreadDesktop;
  if ( !ProcessWindowStation || !ThreadDesktop )
    goto LABEL_43;
  nLengthNeeded = 0;
  if ( !GetUserObjectInformationW(ProcessWindowStation, 2, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v9 = 10;
LABEL_11:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, LastError);
      goto LABEL_43;
    }
    goto LABEL_43;
  }
  if ( nLengthNeeded == -1 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_43;
    v11 = 11;
    goto LABEL_16;
  }
  unique_for = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v17, nLengthNeeded + 1);
  v0 = *unique_for;
  *unique_for = 0;
  v16 = v0;
  if ( v17 )
    operator delete(v17, v3);
  if ( !v0 )
    goto LABEL_43;
  if ( GetUserObjectInformationW(ProcessWindowStation, 2, v0, nLengthNeeded, &nLengthNeeded) )
  {
    nLengthNeeded = 0;
    if ( !GetUserObjectInformationW(v7, 2, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        v9 = 13;
        goto LABEL_11;
      }
      goto LABEL_43;
    }
    if ( nLengthNeeded )
    {
      v13 = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v17, nLengthNeeded + 1);
      v1 = *v13;
      *v13 = 0;
      v18 = v1;
      if ( v17 )
        operator delete(v17, v3);
      if ( v1 )
      {
        if ( GetUserObjectInformationW(v7, 2, v1, nLengthNeeded, &nLengthNeeded) )
        {
          if ( !(unsigned int)_o__wcsicmp(v0, L"WinSta0") && !(unsigned int)_o__wcsicmp(v1, L"default") )
            v2 = 1;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          v9 = 15;
          goto LABEL_11;
        }
      }
      goto LABEL_43;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_43;
    v11 = 14;
LABEL_16:
    WPP_SF_(v10[2], v11, &WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    v9 = 12;
    goto LABEL_11;
  }
LABEL_43:
  if ( v1 )
    operator delete(v1, v3);
  if ( v0 )
    operator delete(v0, v3);
  return v2;
}

```

## disassembly

```asm
0x1800270c4  push    rbp
0x1800270c6  push    rbx
0x1800270c7  push    rsi
0x1800270c8  push    rdi
0x1800270c9  push    r12
0x1800270cb  push    r14
0x1800270cd  push    r15
0x1800270cf  mov     rbp, rsp
0x1800270d2  sub     rsp, 30h
0x1800270d6  xor     edi, edi
0x1800270d8  mov     [rbp+arg_8], rdi
0x1800270dc  xor     esi, esi
0x1800270de  mov     [rbp+arg_18], rsi
0x1800270e2  mov     [rbp+nLengthNeeded], esi
0x1800270e5  xor     r15d, r15d
0x1800270e8  call    IsGetThreadDesktopPresent
0x1800270ed  test    al, al
0x1800270ef  jz      loc_1800273A5
0x1800270f5  call    IsGetThreadDesktopPresent
0x1800270fa  test    al, al
0x1800270fc  jz      loc_1800273A5
0x180027102  call    IsGetThreadDesktopPresent
0x180027107  test    al, al
0x180027109  jz      loc_1800273A5
0x18002710f  call    cs:__imp_GetProcessWindowStation
0x180027115  mov     r14, rax
0x180027118  call    cs:__imp_GetCurrentThreadId
0x18002711e  mov     ecx, eax; dwThreadId
0x180027120  call    cs:__imp_GetThreadDesktop
0x180027126  mov     r12, rax
0x180027129  test    r14, r14
0x18002712c  jz      loc_1800273A5
0x180027132  test    rax, rax
0x180027135  jz      loc_1800273A5
0x18002713b  mov     [rbp+nLengthNeeded], r15d
0x18002713f  lea     rax, [rbp+nLengthNeeded]
0x180027143  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180027148  xor     r9d, r9d; nLength
0x18002714b  xor     r8d, r8d; pvInfo
0x18002714e  lea     edx, [rdi+2]; nIndex
0x180027151  mov     rcx, r14; hObj
0x180027154  call    cs:__imp_GetUserObjectInformationW
0x18002715a  test    eax, eax
0x18002715c  jnz     short loc_1800271B4
0x18002715e  call    cs:__imp_GetLastError
0x180027164  cmp     eax, 7Ah ; 'z'
0x180027167  jz      short loc_1800271B4
0x180027169  lea     rax, WPP_GLOBAL_Control
0x180027170  mov     rcx, cs:WPP_GLOBAL_Control
0x180027177  cmp     rcx, rax
0x18002717a  jz      loc_1800273A5
0x180027180  lea     ebx, [rdi+1]
0x180027183  test    [rcx+1Ch], bl
0x180027186  jz      loc_1800273A5
0x18002718c  call    cs:__imp_GetLastError
0x180027192  lea     edx, [rdi+0Ah]
0x180027195  mov     r9d, eax
0x180027198  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x18002719f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271a6  mov     rcx, [rcx+10h]
0x1800271aa  call    WPP_SF_d
0x1800271af  jmp     loc_1800273A5
0x1800271b4  mov     eax, [rbp+nLengthNeeded]
0x1800271b7  inc     eax
0x1800271b9  mov     ebx, 1
0x1800271be  cmp     eax, ebx
0x1800271c0  jnb     short loc_1800271FA
0x1800271c2  lea     rax, WPP_GLOBAL_Control
0x1800271c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271d0  cmp     rcx, rax
0x1800271d3  jz      loc_1800273A5
0x1800271d9  test    [rcx+1Ch], bl
0x1800271dc  jz      loc_1800273A5
0x1800271e2  lea     edx, [rbx+0Ah]
0x1800271e5  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x1800271ec  mov     rcx, [rcx+10h]
0x1800271f0  call    WPP_SF_
0x1800271f5  jmp     loc_1800273A5
0x1800271fa  mov     edx, eax
0x1800271fc  lea     rcx, [rbp+arg_10]
0x180027200  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180027205  mov     rdi, [rax]
0x180027208  mov     [rax], r15
0x18002720b  mov     [rbp+arg_8], rdi
0x18002720f  mov     rcx, [rbp+arg_10]; void *
0x180027213  test    rcx, rcx
0x180027216  jz      short loc_18002721D
0x180027218  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002721d  test    rdi, rdi
0x180027220  jz      loc_1800273A5
0x180027226  lea     rax, [rbp+nLengthNeeded]
0x18002722a  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002722f  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180027233  mov     r8, rdi; pvInfo
0x180027236  mov     edx, 2; nIndex
0x18002723b  mov     rcx, r14; hObj
0x18002723e  call    cs:__imp_GetUserObjectInformationW
0x180027244  test    eax, eax
0x180027246  jnz     short loc_180027278
0x180027248  lea     rax, WPP_GLOBAL_Control
0x18002724f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027256  cmp     rcx, rax
0x180027259  jz      loc_1800273A5
0x18002725f  test    [rcx+1Ch], bl
0x180027262  jz      loc_1800273A5
0x180027268  call    cs:__imp_GetLastError
0x18002726e  mov     edx, 0Ch
0x180027273  jmp     loc_180027195
0x180027278  mov     [rbp+nLengthNeeded], r15d
0x18002727c  lea     rax, [rbp+nLengthNeeded]
0x180027280  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180027285  xor     r9d, r9d; nLength
0x180027288  xor     r8d, r8d; pvInfo
0x18002728b  lea     r14d, [r9+2]
0x18002728f  mov     edx, r14d; nIndex
0x180027292  mov     rcx, r12; hObj
0x180027295  call    cs:__imp_GetUserObjectInformationW
0x18002729b  test    eax, eax
0x18002729d  jnz     short loc_1800272D9
0x18002729f  call    cs:__imp_GetLastError
0x1800272a5  cmp     eax, 7Ah ; 'z'
0x1800272a8  jz      short loc_1800272D9
0x1800272aa  lea     rax, WPP_GLOBAL_Control
0x1800272b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272b8  cmp     rcx, rax
0x1800272bb  jz      loc_1800273A5
0x1800272c1  test    [rcx+1Ch], bl
0x1800272c4  jz      loc_1800273A5
0x1800272ca  call    cs:__imp_GetLastError
0x1800272d0  lea     edx, [r14+0Bh]
0x1800272d4  jmp     loc_180027195
0x1800272d9  mov     eax, [rbp+nLengthNeeded]
0x1800272dc  cmp     eax, ebx
0x1800272de  jnb     short loc_18002730A
0x1800272e0  lea     rax, WPP_GLOBAL_Control
0x1800272e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272ee  cmp     rcx, rax
0x1800272f1  jz      loc_1800273A5
0x1800272f7  test    [rcx+1Ch], bl
0x1800272fa  jz      loc_1800273A5
0x180027300  mov     edx, 0Eh
0x180027305  jmp     loc_1800271E5
0x18002730a  lea     edx, [rax+1]
0x18002730d  lea     rcx, [rbp+arg_10]
0x180027311  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180027316  mov     rsi, [rax]
0x180027319  mov     [rax], r15
0x18002731c  mov     [rbp+arg_18], rsi
0x180027320  mov     rcx, [rbp+arg_10]; void *
0x180027324  test    rcx, rcx
0x180027327  jz      short loc_18002732E
0x180027329  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002732e  test    rsi, rsi
0x180027331  jz      short loc_1800273A5
0x180027333  lea     rax, [rbp+nLengthNeeded]
0x180027337  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18002733c  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180027340  mov     r8, rsi; pvInfo
0x180027343  mov     edx, r14d; nIndex
0x180027346  mov     rcx, r12; hObj
0x180027349  call    cs:__imp_GetUserObjectInformationW
0x18002734f  test    eax, eax
0x180027351  jnz     short loc_18002737B
0x180027353  lea     rax, WPP_GLOBAL_Control
0x18002735a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027361  cmp     rcx, rax
0x180027364  jz      short loc_1800273A5
0x180027366  test    [rcx+1Ch], bl
0x180027369  jz      short loc_1800273A5
0x18002736b  call    cs:__imp_GetLastError
0x180027371  mov     edx, 0Fh
0x180027376  jmp     loc_180027195
0x18002737b  lea     rdx, aWinsta0; "WinSta0"
0x180027382  mov     rcx, rdi
0x180027385  call    cs:__imp__o__wcsicmp
0x18002738b  test    eax, eax
0x18002738d  jnz     short loc_1800273A5
0x18002738f  lea     rdx, aDefault; "default"
0x180027396  mov     rcx, rsi
0x180027399  call    cs:__imp__o__wcsicmp
0x18002739f  test    eax, eax
0x1800273a1  cmovz   r15d, ebx
0x1800273a5  test    rsi, rsi
0x1800273a8  jz      short loc_1800273B3
0x1800273aa  mov     rcx, rsi; void *
0x1800273ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800273b2  nop
0x1800273b3  test    rdi, rdi
0x1800273b6  jz      short loc_1800273C0
0x1800273b8  mov     rcx, rdi; void *
0x1800273bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800273c0  mov     eax, r15d
0x1800273c3  add     rsp, 30h
0x1800273c7  pop     r15
0x1800273c9  pop     r14
0x1800273cb  pop     r12
0x1800273cd  pop     rdi
0x1800273ce  pop     rsi
0x1800273cf  pop     rbx
0x1800273d0  pop     rbp
0x1800273d1  retn
```
