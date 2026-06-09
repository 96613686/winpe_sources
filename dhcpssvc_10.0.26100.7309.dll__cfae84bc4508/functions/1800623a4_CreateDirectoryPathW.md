# CreateDirectoryPathW

- ea: `0x1800623a4`
- end: `0x180062586`
- name: `CreateDirectoryPathW`
- size: `482`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800032a4`
- `0x1800038fc`
- `0x1800302a0`
- `0x18004d6f0`
- `0x180062310`
- `0x1800623a4`
- `0x1800670ec`

## callees

- `0x1800057f4`
- `0x1800058cc`
- `0x180005934`
- `0x1800623a4`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800624cd`
- `msvcrt!wcsrchr` at `0x1800624cd`
- `KERNEL32!SetLastError` at `0x18006255c`
- `KERNEL32!SetLastError` at `0x18006255c`
- `KERNEL32!CreateDirectoryW` at `0x180062413`
- `KERNEL32!CreateDirectoryW` at `0x180062505`
- `KERNEL32!CreateDirectoryW` at `0x180062413`
- `KERNEL32!CreateDirectoryW` at `0x180062505`
- `KERNEL32!GetLastError` at `0x180062433`
- `KERNEL32!GetLastError` at `0x18006246d`
- `KERNEL32!GetLastError` at `0x180062527`
- `KERNEL32!GetLastError` at `0x180062433`
- `KERNEL32!GetLastError` at `0x18006246d`
- `KERNEL32!GetLastError` at `0x180062527`

## pseudocode

```c
BOOL __fastcall CreateDirectoryPathW(LPCWSTR lpPathName)
{
  unsigned int DirectoryW; // edi
  DWORD LastError; // eax
  BOOL result; // eax
  DWORD v5; // eax
  DWORD v6; // edi
  wchar_t *v7; // rax
  wchar_t *v8; // rdi
  int DirectoryPathW; // eax
  char v10; // al

  if ( !lpPathName || !*lpPathName )
    goto LABEL_23;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids, lpPathName);
  DirectoryW = CreateDirectoryW(lpPathName, &DhcpGlobalDirSecurityAttr);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_dD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids,
      DirectoryW,
      LastError);
  }
  if ( DirectoryW )
    return DirectoryW;
  v5 = GetLastError();
  v6 = v5;
  if ( v5 == 183 )
    return 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids,
      (_DWORD)lpPathName,
      v5);
  if ( v6 != 3 )
    return 0;
  v7 = wcsrchr(lpPathName, 0x5Cu);
  v8 = v7;
  if ( v7 )
  {
    *v7 = 0;
    DirectoryPathW = CreateDirectoryPathW(lpPathName);
    *v8 = 92;
    if ( DirectoryPathW )
    {
      result = CreateDirectoryW(lpPathName, &DhcpGlobalDirSecurityAttr);
      if ( result )
        return result;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v10 = GetLastError();
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids,
          (_DWORD)lpPathName,
          v10);
      }
    }
  }
  else
  {
LABEL_23:
    SetLastError(0xA1u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800623a4  mov     rax, rsp
0x1800623a7  mov     [rax+8], rbx
0x1800623ab  mov     [rax+10h], rbp
0x1800623af  mov     [rax+18h], rsi
0x1800623b3  mov     [rax+20h], rdi
0x1800623b7  push    r14
0x1800623b9  sub     rsp, 30h
0x1800623bd  xor     esi, esi
0x1800623bf  mov     rbx, rcx
0x1800623c2  test    rcx, rcx
0x1800623c5  jz      loc_180062557
0x1800623cb  cmp     si, [rcx]
0x1800623ce  jz      loc_180062557
0x1800623d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800623db  lea     rbp, WPP_GLOBAL_Control
0x1800623e2  mov     r14d, 8000h
0x1800623e8  cmp     rcx, rbp
0x1800623eb  jz      short loc_180062409
0x1800623ed  test    [rcx+1Ch], r14d
0x1800623f1  jz      short loc_180062409
0x1800623f3  mov     rcx, [rcx+10h]
0x1800623f7  lea     edx, [rsi+14h]
0x1800623fa  mov     r9, rbx
0x1800623fd  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x180062404  call    WPP_SF_S
0x180062409  lea     rdx, DhcpGlobalDirSecurityAttr; lpSecurityAttributes
0x180062410  mov     rcx, rbx; lpPathName
0x180062413  call    cs:__imp_CreateDirectoryW
0x18006241a  nop     dword ptr [rax+rax+00h]
0x18006241f  mov     edi, eax
0x180062421  mov     rax, cs:WPP_GLOBAL_Control
0x180062428  cmp     rax, rbp
0x18006242b  jz      short loc_180062462
0x18006242d  test    [rax+1Ch], r14d
0x180062431  jz      short loc_180062462
0x180062433  call    cs:__imp_GetLastError
0x18006243a  nop     dword ptr [rax+rax+00h]
0x18006243f  mov     rcx, cs:WPP_GLOBAL_Control
0x180062446  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x18006244d  mov     edx, 15h
0x180062452  mov     [rsp+38h+var_18], eax
0x180062456  mov     r9d, edi
0x180062459  mov     rcx, [rcx+10h]
0x18006245d  call    WPP_SF_dD
0x180062462  test    edi, edi
0x180062464  jz      short loc_18006246D
0x180062466  mov     eax, edi
0x180062468  jmp     loc_18006256A
0x18006246d  call    cs:__imp_GetLastError
0x180062474  nop     dword ptr [rax+rax+00h]
0x180062479  mov     edi, eax
0x18006247b  cmp     eax, 0B7h
0x180062480  jnz     short loc_18006248C
0x180062482  mov     eax, 1
0x180062487  jmp     loc_18006256A
0x18006248c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062493  cmp     rcx, rbp
0x180062496  jz      short loc_1800624BA
0x180062498  test    byte ptr [rcx+1Ch], 10h
0x18006249c  jz      short loc_1800624BA
0x18006249e  mov     rcx, [rcx+10h]
0x1800624a2  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x1800624a9  mov     edx, 16h
0x1800624ae  mov     [rsp+38h+var_18], edi
0x1800624b2  mov     r9, rbx
0x1800624b5  call    WPP_SF_SD
0x1800624ba  cmp     edi, 3
0x1800624bd  jnz     loc_180062568
0x1800624c3  lea     r14d, [rdi+59h]
0x1800624c7  mov     rcx, rbx; Str
0x1800624ca  mov     edx, r14d; Ch
0x1800624cd  call    cs:__imp_wcsrchr
0x1800624d4  nop     dword ptr [rax+rax+00h]
0x1800624d9  mov     rdi, rax
0x1800624dc  test    rax, rax
0x1800624df  jz      short loc_180062557
0x1800624e1  lea     rdx, DhcpGlobalDirSecurityAttr
0x1800624e8  mov     [rax], si
0x1800624eb  mov     rcx, rbx; lpPathName
0x1800624ee  call    CreateDirectoryPathW
0x1800624f3  mov     [rdi], r14w
0x1800624f7  test    eax, eax
0x1800624f9  jz      short loc_180062568
0x1800624fb  lea     rdx, DhcpGlobalDirSecurityAttr; lpSecurityAttributes
0x180062502  mov     rcx, rbx; lpPathName
0x180062505  call    cs:__imp_CreateDirectoryW
0x18006250c  nop     dword ptr [rax+rax+00h]
0x180062511  test    eax, eax
0x180062513  jnz     short loc_18006256A
0x180062515  mov     rax, cs:WPP_GLOBAL_Control
0x18006251c  cmp     rax, rbp
0x18006251f  jz      short loc_180062568
0x180062521  test    byte ptr [rax+1Ch], 10h
0x180062525  jz      short loc_180062568
0x180062527  call    cs:__imp_GetLastError
0x18006252e  nop     dword ptr [rax+rax+00h]
0x180062533  mov     rcx, cs:WPP_GLOBAL_Control
0x18006253a  lea     edx, [r14-45h]
0x18006253e  mov     r9, rbx
0x180062541  mov     [rsp+38h+var_18], eax
0x180062545  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x18006254c  mov     rcx, [rcx+10h]
0x180062550  call    WPP_SF_SD
0x180062555  jmp     short loc_180062568
0x180062557  mov     ecx, 0A1h; dwErrCode
0x18006255c  call    cs:__imp_SetLastError
0x180062563  nop     dword ptr [rax+rax+00h]
0x180062568  xor     eax, eax
0x18006256a  mov     rbx, [rsp+38h+arg_0]
0x18006256f  mov     rbp, [rsp+38h+arg_8]
0x180062574  mov     rsi, [rsp+38h+arg_10]
0x180062579  mov     rdi, [rsp+38h+arg_18]
0x18006257e  add     rsp, 30h
0x180062582  pop     r14
0x180062584  retn
```
