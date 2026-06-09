# CServerInstall::SetInfToNTPRINTDir(void)

- ea: `0x180029088`
- end: `0x1800291ce`
- name: `?SetInfToNTPRINTDir@CServerInstall@@AEAAHXZ`
- size: `326`
- prototype: `__int64 __fastcall(CServerInstall *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180028fb0`

## callees

- `0x180002300`
- `0x1800026e0`
- `0x180007944`
- `0x180029088`
- `0x18003806c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002916b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002916b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029194`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800290c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800290c1`

## pseudocode

```c
_BOOL8 __fastcall CServerInstall::SetInfToNTPRINTDir(CServerInstall *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // rcx
  DWORD LastError; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  *(_DWORD *)this = 13;
  if ( GetSystemWindowsDirectoryW(Buffer, 0x105u) - 1 <= 0x103 )
  {
    v2 = -1;
    v3 = -1;
    do
      ++v3;
    while ( Buffer[v3] );
    v4 = (unsigned int)(v3 - 1);
    if ( Buffer[v4] != 92 )
    {
      v5 = (unsigned int)(v4 + 2);
      if ( (unsigned int)v5 >= 0x105 )
        goto LABEL_13;
      Buffer[(unsigned int)v3] = 92;
      if ( (unsigned __int64)(2 * v5) >= 0x20A )
        _report_rangecheckfailure(2 * v5);
      Buffer[v5] = 0;
    }
    v6 = -1;
    do
      ++v6;
    while ( Buffer[v6] );
    do
      ++v2;
    while ( gcszNtprintInfPath[v2] );
    if ( (unsigned int)(v2 + v6 + 1) <= 0x105 )
    {
      StringCchCopyW(&Buffer[(unsigned int)v6], 261LL - (unsigned int)v6, gcszNtprintInfPath);
      *(_DWORD *)this = 0;
    }
  }
LABEL_13:
  if ( *(_DWORD *)this )
  {
    LastError = GetLastError();
    *(_DWORD *)this = LastError;
    if ( !LastError )
      *(_DWORD *)this = 13;
    Buffer[0] = 0;
  }
  if ( !TString::bUpdate((CServerInstall *)((char *)this + 24), Buffer) )
    *(_DWORD *)this = GetLastError();
  return *(_DWORD *)this == 0;
}

```

## disassembly

```asm
0x180029088  mov     [rsp+arg_8], rbx
0x18002908d  mov     [rsp+arg_10], rsi
0x180029092  push    rdi
0x180029093  sub     rsp, 240h
0x18002909a  mov     rax, cs:__security_cookie
0x1800290a1  xor     rax, rsp
0x1800290a4  mov     [rsp+248h+var_18], rax
0x1800290ac  mov     rbx, rcx
0x1800290af  mov     dword ptr [rcx], 0Dh
0x1800290b5  mov     edi, 105h
0x1800290ba  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x1800290bf  mov     edx, edi; uSize
0x1800290c1  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800290c7  dec     eax
0x1800290c9  xor     esi, esi
0x1800290cb  cmp     eax, 103h
0x1800290d0  ja      loc_180029167
0x1800290d6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800290da  lea     rax, [rsp+248h+Buffer]
0x1800290df  mov     rcx, rdx
0x1800290e2  inc     rcx
0x1800290e5  cmp     [rax+rcx*2], si
0x1800290e9  jnz     short loc_1800290E2
0x1800290eb  lea     r8d, [rcx-1]
0x1800290ef  mov     r9d, 5Ch ; '\'
0x1800290f5  cmp     [rsp+r8*2+248h+Buffer], r9w
0x1800290fb  jz      short loc_180029124
0x1800290fd  add     r8d, 2
0x180029101  cmp     r8d, edi
0x180029104  jnb     short loc_180029167
0x180029106  mov     eax, ecx
0x180029108  lea     rcx, [r8+r8]
0x18002910c  mov     [rsp+rax*2+248h+Buffer], r9w
0x180029112  cmp     rcx, 20Ah
0x180029119  jnb     loc_1800291C8
0x18002911f  mov     [rsp+rcx+248h+Buffer], si
0x180029124  lea     rax, [rsp+248h+Buffer]
0x180029129  mov     rcx, rdx
0x18002912c  inc     rcx
0x18002912f  cmp     [rax+rcx*2], si
0x180029133  jnz     short loc_18002912C
0x180029135  lea     r8, gcszNtprintInfPath; "inf\\ntprint.inf"
0x18002913c  inc     rdx
0x18002913f  cmp     [r8+rdx*2], si
0x180029144  jnz     short loc_18002913C
0x180029146  lea     eax, [rcx+1]
0x180029149  add     eax, edx
0x18002914b  cmp     eax, edi
0x18002914d  ja      short loc_180029167
0x18002914f  mov     eax, ecx
0x180029151  lea     rcx, [rsp+248h+Buffer]
0x180029156  sub     rdi, rax
0x180029159  mov     rdx, rdi; unsigned __int64
0x18002915c  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180029160  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029165  mov     [rbx], esi
0x180029167  cmp     [rbx], esi
0x180029169  jz      short loc_180029182
0x18002916b  call    cs:__imp_GetLastError
0x180029171  mov     [rbx], eax
0x180029173  test    eax, eax
0x180029175  jnz     short loc_18002917D
0x180029177  mov     dword ptr [rbx], 0Dh
0x18002917d  mov     [rsp+248h+Buffer], si
0x180029182  lea     rcx, [rbx+18h]; this
0x180029186  lea     rdx, [rsp+248h+Buffer]; unsigned __int16 *
0x18002918b  call    ?bUpdate@TString@@QEAAHPEBG@Z; TString::bUpdate(ushort const *)
0x180029190  test    eax, eax
0x180029192  jnz     short loc_18002919C
0x180029194  call    cs:__imp_GetLastError
0x18002919a  mov     [rbx], eax
0x18002919c  cmp     [rbx], esi
0x18002919e  mov     eax, esi
0x1800291a0  setz    al
0x1800291a3  mov     rcx, [rsp+248h+var_18]
0x1800291ab  xor     rcx, rsp; StackCookie
0x1800291ae  call    __security_check_cookie
0x1800291b3  lea     r11, [rsp+248h+var_8]
0x1800291bb  mov     rbx, [r11+18h]
0x1800291bf  mov     rsi, [r11+20h]
0x1800291c3  mov     rsp, r11
0x1800291c6  pop     rdi
0x1800291c7  retn
0x1800291c8  call    __report_rangecheckfailure
```
