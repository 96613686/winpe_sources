# ComputeLuid

- ea: `0x1800833ec`
- end: `0x18008361a`
- name: `ComputeLuid`
- size: `558`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036f2c`
- `0x180066f50`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800833ec`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180083483`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180083483`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800834a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800834a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800834b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800834b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008346f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008346f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180083525`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180083525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008348d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800834bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008352f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008348d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800834bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008352f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083584`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800835cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800835cb`

## pseudocode

```c
__int64 __fastcall ComputeLuid(_QWORD *a1)
{
  DWORD v2; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD ReturnLength; // [rsp+30h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v12; // [rsp+70h] [rbp+17h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
  }
  ReturnLength = 0;
  v2 = 0;
  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v12 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = 283;
LABEL_13:
            WPP_SF_d(v6[2], v7, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, LastError);
            goto LABEL_33;
          }
          goto LABEL_34;
        }
LABEL_33:
        v6 = WPP_GLOBAL_Control;
        goto LABEL_34;
      }
      v2 = 0;
    }
    else if ( LastError )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 284;
        goto LABEL_13;
      }
      goto LABEL_34;
    }
  }
  if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    if ( ReturnLength <= 0x38 )
    {
      *a1 = *((_QWORD *)&TokenInformation[0] + 1);
      goto LABEL_33;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 286;
        goto LABEL_13;
      }
      goto LABEL_34;
    }
    goto LABEL_33;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( !LastError )
    goto LABEL_33;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 285;
    goto LABEL_13;
  }
LABEL_34:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 287, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x1800833ec  push    rbp
0x1800833ee  push    rbx
0x1800833ef  push    rsi
0x1800833f0  push    rdi
0x1800833f1  push    r14
0x1800833f3  push    r15
0x1800833f5  lea     rbp, [rsp-2Fh]
0x1800833fa  sub     rsp, 88h
0x180083401  mov     rax, cs:__security_cookie
0x180083408  xor     rax, rsp
0x18008340b  mov     [rbp+57h+var_38], rax
0x18008340f  mov     rdi, rcx
0x180083412  mov     rcx, cs:WPP_GLOBAL_Control
0x180083419  lea     r14, WPP_GLOBAL_Control
0x180083420  lea     r15, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180083427  mov     esi, 800h
0x18008342c  cmp     rcx, r14
0x18008342f  jz      short loc_18008344D
0x180083431  test    [rcx+1Ch], esi
0x180083434  jz      short loc_18008344D
0x180083436  cmp     byte ptr [rcx+19h], 6
0x18008343a  jb      short loc_18008344D
0x18008343c  mov     rcx, [rcx+10h]
0x180083440  mov     edx, 11Ah
0x180083445  mov     r8, r15
0x180083448  call    WPP_SF_
0x18008344d  xorps   xmm0, xmm0
0x180083450  mov     [rbp+57h+var_80], 0
0x180083457  xor     eax, eax
0x180083459  xor     ebx, ebx
0x18008345b  mov     [rbp+57h+TokenHandle], rbx
0x18008345f  movups  [rbp+57h+TokenInformation], xmm0
0x180083463  mov     [rbp+57h+var_40], rax
0x180083467  movups  [rbp+57h+var_60], xmm0
0x18008346b  movups  [rbp+57h+var_50], xmm0
0x18008346f  call    cs:__imp_GetCurrentThread
0x180083475  mov     rcx, rax; ThreadHandle
0x180083478  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18008347c  lea     edx, [rbx+8]; DesiredAccess
0x18008347f  lea     r8d, [rbx+1]; OpenAsSelf
0x180083483  call    cs:__imp_OpenThreadToken
0x180083489  test    eax, eax
0x18008348b  jnz     short loc_18008350A
0x18008348d  call    cs:__imp_GetLastError
0x180083493  mov     ebx, eax
0x180083495  cmp     eax, 3F0h
0x18008349a  jnz     loc_180083559
0x1800834a0  call    cs:__imp_GetCurrentProcess
0x1800834a6  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800834aa  mov     edx, 8; DesiredAccess
0x1800834af  mov     rcx, rax; ProcessHandle
0x1800834b2  call    cs:__imp_OpenProcessToken
0x1800834b8  test    eax, eax
0x1800834ba  jnz     short loc_180083508
0x1800834bc  call    cs:__imp_GetLastError
0x1800834c2  mov     ebx, eax
0x1800834c4  test    eax, eax
0x1800834c6  jz      loc_1800835B8
0x1800834cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800834d3  cmp     rcx, r14
0x1800834d6  jz      loc_1800835BF
0x1800834dc  test    [rcx+1Ch], esi
0x1800834df  jz      loc_1800835BF
0x1800834e5  cmp     byte ptr [rcx+19h], 2
0x1800834e9  jb      loc_1800835BF
0x1800834ef  mov     edx, 11Bh
0x1800834f4  mov     rcx, [rcx+10h]
0x1800834f8  mov     r9d, eax
0x1800834fb  mov     r8, r15
0x1800834fe  call    WPP_SF_d
0x180083503  jmp     loc_1800835B8
0x180083508  xor     ebx, ebx
0x18008350a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18008350e  lea     rax, [rbp+57h+var_80]
0x180083512  mov     r9d, 38h ; '8'; TokenInformationLength
0x180083518  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18008351d  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180083521  lea     edx, [r9-2Eh]; TokenInformationClass
0x180083525  call    cs:__imp_GetTokenInformation
0x18008352b  test    eax, eax
0x18008352d  jnz     short loc_18008357E
0x18008352f  call    cs:__imp_GetLastError
0x180083535  mov     ebx, eax
0x180083537  test    eax, eax
0x180083539  jz      short loc_1800835B8
0x18008353b  mov     rcx, cs:WPP_GLOBAL_Control
0x180083542  cmp     rcx, r14
0x180083545  jz      short loc_1800835BF
0x180083547  test    [rcx+1Ch], esi
0x18008354a  jz      short loc_1800835BF
0x18008354c  cmp     byte ptr [rcx+19h], 2
0x180083550  jb      short loc_1800835BF
0x180083552  mov     edx, 11Dh
0x180083557  jmp     short loc_1800834F4
0x180083559  test    eax, eax
0x18008355b  jz      short loc_18008350A
0x18008355d  mov     rcx, cs:WPP_GLOBAL_Control
0x180083564  cmp     rcx, r14
0x180083567  jz      short loc_1800835BF
0x180083569  test    [rcx+1Ch], esi
0x18008356c  jz      short loc_1800835BF
0x18008356e  cmp     byte ptr [rcx+19h], 2
0x180083572  jb      short loc_1800835BF
0x180083574  mov     edx, 11Ch
0x180083579  jmp     loc_1800834F4
0x18008357e  cmp     [rbp+57h+var_80], 38h ; '8'
0x180083582  jbe     short loc_1800835B1
0x180083584  call    cs:__imp_GetLastError
0x18008358a  mov     ebx, eax
0x18008358c  test    eax, eax
0x18008358e  jz      short loc_1800835B8
0x180083590  mov     rcx, cs:WPP_GLOBAL_Control
0x180083597  cmp     rcx, r14
0x18008359a  jz      short loc_1800835BF
0x18008359c  test    [rcx+1Ch], esi
0x18008359f  jz      short loc_1800835BF
0x1800835a1  cmp     byte ptr [rcx+19h], 2
0x1800835a5  jb      short loc_1800835BF
0x1800835a7  mov     edx, 11Eh
0x1800835ac  jmp     loc_1800834F4
0x1800835b1  mov     rax, qword ptr [rbp+57h+TokenInformation+8]
0x1800835b5  mov     [rdi], rax
0x1800835b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800835bf  mov     rax, [rbp+57h+TokenHandle]
0x1800835c3  test    rax, rax
0x1800835c6  jz      short loc_1800835D8
0x1800835c8  mov     rcx, rax; hObject
0x1800835cb  call    cs:__imp_CloseHandle
0x1800835d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800835d8  cmp     rcx, r14
0x1800835db  jz      short loc_1800835FC
0x1800835dd  test    [rcx+1Ch], esi
0x1800835e0  jz      short loc_1800835FC
0x1800835e2  cmp     byte ptr [rcx+19h], 6
0x1800835e6  jb      short loc_1800835FC
0x1800835e8  mov     rcx, [rcx+10h]
0x1800835ec  mov     edx, 11Fh
0x1800835f1  mov     r9d, ebx
0x1800835f4  mov     r8, r15
0x1800835f7  call    WPP_SF_d
0x1800835fc  mov     eax, ebx
0x1800835fe  mov     rcx, [rbp+57h+var_38]
0x180083602  xor     rcx, rsp; StackCookie
0x180083605  call    __security_check_cookie
0x18008360a  add     rsp, 88h
0x180083611  pop     r15
0x180083613  pop     r14
0x180083615  pop     rdi
0x180083616  pop     rsi
0x180083617  pop     rbx
0x180083618  pop     rbp
0x180083619  retn
```
