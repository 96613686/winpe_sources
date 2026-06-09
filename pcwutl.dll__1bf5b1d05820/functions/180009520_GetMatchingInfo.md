# GetMatchingInfo

- ea: `0x180009520`
- end: `0x180009642`
- name: `GetMatchingInfo`
- size: `290`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, LPWSTR lpTempFileName)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180009520`
- `0x180009650`
- `0x18000e240`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180009591`
- `msvcrt!_wcsdup` at `0x180009591`
- `msvcrt!free` at `0x1800095b7`
- `msvcrt!free` at `0x1800095b7`
- `apphelp!SdbGrabMatchingInfoEx` at `0x180009622`
- `apphelp!SdbGrabMatchingInfoEx` at `0x180009622`
- `KERNEL32!GetDriveTypeW` at `0x1800095c0`
- `KERNEL32!GetDriveTypeW` at `0x1800095c0`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800095a2`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800095a2`
- `SHLWAPI!PathIsRootW` at `0x1800095ab`
- `SHLWAPI!PathIsRootW` at `0x1800095ab`
- `SHLWAPI!PathGetDriveNumberW` at `0x1800095d8`
- `SHLWAPI!PathGetDriveNumberW` at `0x1800095d8`

## string_xrefs

- `0x180009538`: `ExePath: %ws`

## pseudocode

```c
__int64 __fastcall GetMatchingInfo(LPCWSTR pszPath, LPWSTR lpTempFileName)
{
  unsigned int v4; // ebp
  __int64 v5; // rbx
  BOOL IsRootW; // r14d
  WCHAR *v7; // rax
  WCHAR *v8; // rsi
  UINT DriveTypeW; // eax
  _DWORD v11[4]; // [rsp+30h] [rbp-68h]
  LPCWSTR v12; // [rsp+40h] [rbp-58h]
  __int128 v13; // [rsp+48h] [rbp-50h]

  v4 = 0;
  v13 = 0;
  AslLogCallPrintf(3, "GetMatchingInfo", 379, "ExePath: %ws", pszPath);
  if ( lpTempFileName && (unsigned int)GetTempFile(L"ACG", lpTempFileName) )
  {
    LODWORD(v5) = 1;
    v12 = pszPath;
    v11[0] = 1;
    IsRootW = 0;
    v7 = _wcsdup(pszPath);
    v8 = v7;
    if ( v7 )
    {
      PathRemoveFileSpecW(v7);
      IsRootW = PathIsRootW(v8);
      free(v8);
    }
    DriveTypeW = GetDriveTypeW(pszPath);
    if ( IsRootW || DriveTypeW == 4 )
    {
      v11[0] = 1073741825;
    }
    else if ( DriveTypeW == 5 && PathGetDriveNumberW(pszPath) >= 0 )
    {
      v11[0] = 805306369;
      *(_QWORD *)&v13 = L"Z:\\";
      LODWORD(v5) = 2;
      v11[1] = -1610612736;
    }
    while ( 1 )
    {
      v5 = (unsigned int)(v5 - 1);
      if ( !(unsigned int)SdbGrabMatchingInfoEx((&v12)[v5], (unsigned int)v11[v5], lpTempFileName, 0, 0) )
        break;
      if ( !(_DWORD)v5 )
        return 1;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180009520  push    rbx
0x180009522  push    rbp
0x180009523  push    rsi
0x180009524  push    rdi
0x180009525  push    r14
0x180009527  push    r15
0x180009529  sub     rsp, 68h
0x18000952d  mov     r15, rdx
0x180009530  mov     [rsp+98h+var_78], rcx
0x180009535  mov     rdi, rcx
0x180009538  lea     r9, aExepathWs; "ExePath: %ws"
0x18000953f  xorps   xmm0, xmm0
0x180009542  lea     rdx, aGetmatchinginf_0; "GetMatchingInfo"
0x180009549  xor     ebp, ebp
0x18000954b  mov     r8d, 17Bh
0x180009551  movdqu  [rsp+98h+var_50], xmm0
0x180009557  lea     ecx, [rbp+3]
0x18000955a  call    AslLogCallPrintf
0x18000955f  test    r15, r15
0x180009562  jz      loc_180009633
0x180009568  mov     rdx, r15; lpTempFileName
0x18000956b  lea     rcx, PrefixString; "ACG"
0x180009572  call    GetTempFile
0x180009577  test    eax, eax
0x180009579  jz      loc_180009633
0x18000957f  lea     ebx, [rbp+1]
0x180009582  mov     [rsp+98h+var_58], rdi
0x180009587  mov     rcx, rdi; String
0x18000958a  mov     [rsp+98h+var_68], ebx
0x18000958e  xor     r14d, r14d
0x180009591  call    cs:__imp__wcsdup
0x180009597  mov     rsi, rax
0x18000959a  test    rax, rax
0x18000959d  jz      short loc_1800095BD
0x18000959f  mov     rcx, rax; pszPath
0x1800095a2  call    cs:__imp_PathRemoveFileSpecW
0x1800095a8  mov     rcx, rsi; pszPath
0x1800095ab  call    cs:__imp_PathIsRootW
0x1800095b1  mov     rcx, rsi; Block
0x1800095b4  mov     r14d, eax
0x1800095b7  call    cs:__imp_free
0x1800095bd  mov     rcx, rdi; lpRootPathName
0x1800095c0  call    cs:__imp_GetDriveTypeW
0x1800095c6  test    r14d, r14d
0x1800095c9  jnz     short loc_180009604
0x1800095cb  cmp     eax, 4
0x1800095ce  jz      short loc_180009604
0x1800095d0  cmp     eax, 5
0x1800095d3  jnz     short loc_18000960C
0x1800095d5  mov     rcx, rdi; pszPath
0x1800095d8  call    cs:__imp_PathGetDriveNumberW
0x1800095de  test    eax, eax
0x1800095e0  js      short loc_18000960C
0x1800095e2  lea     rax, aZ; "Z:\\"
0x1800095e9  mov     [rsp+98h+var_68], 30000001h
0x1800095f1  mov     qword ptr [rsp+98h+var_50], rax
0x1800095f6  lea     ebx, [r14+2]
0x1800095fa  mov     [rsp+98h+var_64], 0A0000000h
0x180009602  jmp     short loc_18000960C
0x180009604  mov     [rsp+98h+var_68], 40000001h
0x18000960c  dec     ebx
0x18000960e  mov     [rsp+98h+var_78], rbp
0x180009613  xor     r9d, r9d
0x180009616  mov     r8, r15
0x180009619  mov     edx, [rsp+rbx*4+98h+var_68]
0x18000961d  mov     rcx, [rsp+rbx*8+98h+var_58]
0x180009622  call    cs:__imp_SdbGrabMatchingInfoEx
0x180009628  test    eax, eax
0x18000962a  jz      short loc_180009633
0x18000962c  test    ebx, ebx
0x18000962e  jnz     short loc_18000960C
0x180009630  lea     ebp, [rbx+1]
0x180009633  mov     eax, ebp
0x180009635  add     rsp, 68h
0x180009639  pop     r15
0x18000963b  pop     r14
0x18000963d  pop     rdi
0x18000963e  pop     rsi
0x18000963f  pop     rbp
0x180009640  pop     rbx
0x180009641  retn
```
