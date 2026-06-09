# CFaxSecurity::GetObjectInformation(_SI_OBJECT_INFO *)

- ea: `0x180013ce0`
- end: `0x180013f93`
- name: `?GetObjectInformation@CFaxSecurity@@UEAAJPEAU_SI_OBJECT_INFO@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(CFaxSecurity *__hidden this, struct _SI_OBJECT_INFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000de40`
- `0x18000e3b4`
- `0x18000e7b0`
- `0x180013ce0`

## import_xrefs

- `FXSAPI!FaxAccessCheckEx2` at `0x180013d82`
- `FXSAPI!FaxAccessCheckEx2` at `0x180013dba`
- `FXSAPI!FaxAccessCheckEx2` at `0x180013df2`
- `FXSAPI!FaxAccessCheckEx2` at `0x180013d82`
- `FXSAPI!FaxAccessCheckEx2` at `0x180013dba`
- `FXSAPI!FaxAccessCheckEx2` at `0x180013df2`
- `KERNEL32!GetLastError` at `0x180013d8c`
- `KERNEL32!GetLastError` at `0x180013dc4`
- `KERNEL32!GetLastError` at `0x180013dfc`
- `KERNEL32!GetLastError` at `0x180013e4a`
- `KERNEL32!GetLastError` at `0x180013f28`
- `KERNEL32!GetLastError` at `0x180013d8c`
- `KERNEL32!GetLastError` at `0x180013dc4`
- `KERNEL32!GetLastError` at `0x180013dfc`
- `KERNEL32!GetLastError` at `0x180013e4a`
- `KERNEL32!GetLastError` at `0x180013f28`
- `USER32!LoadStringW` at `0x180013e28`
- `USER32!LoadStringW` at `0x180013e28`

## string_xrefs

- `0x180013d9f`: `SeTakeOwnershipPrivilege`
- `0x180013dd7`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::GetObjectInformation(CFaxSecurity *this, struct _SI_OBJECT_INFO *a2)
{
  _QWORD *v4; // rcx
  int v6; // ebx
  __int64 v7; // r14
  DWORD LastError; // eax
  __int64 v9; // r15
  WCHAR *v10; // rsi
  unsigned int v11; // edx
  unsigned __int16 *v12; // rcx
  unsigned int v13; // r8d
  DWORD v14; // eax
  WCHAR *v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  DWORD v18; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x100) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_(v4[2], 11, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids);
    return 2147500035LL;
  }
  a2->dwFlags = 3603;
  v6 = 0;
  v7 = -1;
  if ( !(unsigned int)FaxAccessCheckEx2(*((_QWORD *)this + 1), 0x40000, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      v16 = WPP_GLOBAL_Control;
      v9 = -1;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v17 = 12;
      goto LABEL_32;
    }
    a2->dwFlags |= 8u;
  }
  v9 = EnablePrivilege(L"SeTakeOwnershipPrivilege");
  if ( !(unsigned int)FaxAccessCheckEx2(*((_QWORD *)this + 1), 0x80000, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v17 = 13;
      goto LABEL_32;
    }
    a2->dwFlags |= 0x40u;
  }
  v7 = EnablePrivilege(L"SeSecurityPrivilege");
  if ( (unsigned int)FaxAccessCheckEx2(*((_QWORD *)this + 1), 0x1000000, 0) )
  {
LABEL_20:
    v10 = &Buffer;
    if ( !LoadStringW(*((HINSTANCE *)this + 2), 0x122Eu, &Buffer, 260) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids, v14);
      }
      v10 = 0;
    }
    a2->pszPageTitle = v10;
    if ( (unsigned int)GetFirstFaxPrinterName(v12, v11, v13) )
    {
      v15 = &qword_18001EE60;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids, v18);
      }
      v15 = 0;
    }
    a2->pszObjectName = v15;
    a2->hInstance = (HINSTANCE)*((_QWORD *)this + 2);
    a2->pszServerName = 0;
    goto LABEL_47;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( !LastError )
  {
    a2->dwFlags &= ~2u;
    goto LABEL_20;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 14;
LABEL_32:
    WPP_SF_d(v16[2], v17, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids, LastError);
  }
LABEL_47:
  ReleasePrivilege((HANDLE)v7);
  ReleasePrivilege((HANDLE)v9);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013ce0  push    rbx
0x180013ce2  push    rbp
0x180013ce3  push    rsi
0x180013ce4  push    rdi
0x180013ce5  push    r12
0x180013ce7  push    r13
0x180013ce9  push    r14
0x180013ceb  push    r15
0x180013ced  sub     rsp, 28h
0x180013cf1  mov     rdi, rdx
0x180013cf4  mov     rbp, rcx
0x180013cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cfe  lea     r13, WPP_GLOBAL_Control
0x180013d05  lea     rsi, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180013d0c  mov     r12d, 100h
0x180013d12  cmp     rcx, r13
0x180013d15  jz      short loc_180013D3B
0x180013d17  test    [rcx+1Ch], r12d
0x180013d1b  jz      short loc_180013D3B
0x180013d1d  cmp     byte ptr [rcx+19h], 5
0x180013d21  jb      short loc_180013D3B
0x180013d23  mov     rcx, [rcx+10h]
0x180013d27  mov     edx, 0Ah
0x180013d2c  mov     r8, rsi
0x180013d2f  call    WPP_SF_
0x180013d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d3b  test    rdi, rdi
0x180013d3e  jnz     short loc_180013D6A
0x180013d40  cmp     rcx, r13
0x180013d43  jz      short loc_180013D60
0x180013d45  test    [rcx+1Ch], r12d
0x180013d49  jz      short loc_180013D60
0x180013d4b  cmp     byte ptr [rcx+19h], 2
0x180013d4f  jb      short loc_180013D60
0x180013d51  mov     rcx, [rcx+10h]
0x180013d55  lea     edx, [rdi+0Bh]
0x180013d58  mov     r8, rsi
0x180013d5b  call    WPP_SF_
0x180013d60  mov     eax, 80004003h
0x180013d65  jmp     loc_180013F82
0x180013d6a  mov     dword ptr [rdi], 0E13h
0x180013d70  xor     r8d, r8d
0x180013d73  mov     rcx, [rbp+8]
0x180013d77  mov     edx, 40000h
0x180013d7c  xor     ebx, ebx
0x180013d7e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180013d82  call    cs:__imp_FaxAccessCheckEx2
0x180013d88  test    eax, eax
0x180013d8a  jnz     short loc_180013D9F
0x180013d8c  call    cs:__imp_GetLastError
0x180013d92  mov     ebx, eax
0x180013d94  test    eax, eax
0x180013d96  jnz     loc_180013E8E
0x180013d9c  or      dword ptr [rdi], 8
0x180013d9f  lea     rcx, Name; "SeTakeOwnershipPrivilege"
0x180013da6  call    EnablePrivilege
0x180013dab  mov     rcx, [rbp+8]
0x180013daf  xor     r8d, r8d
0x180013db2  mov     edx, 80000h
0x180013db7  mov     r15, rax
0x180013dba  call    cs:__imp_FaxAccessCheckEx2
0x180013dc0  test    eax, eax
0x180013dc2  jnz     short loc_180013DD7
0x180013dc4  call    cs:__imp_GetLastError
0x180013dca  mov     ebx, eax
0x180013dcc  test    eax, eax
0x180013dce  jnz     loc_180013ECE
0x180013dd4  or      dword ptr [rdi], 40h
0x180013dd7  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x180013dde  call    EnablePrivilege
0x180013de3  mov     rcx, [rbp+8]
0x180013de7  xor     r8d, r8d
0x180013dea  mov     edx, 1000000h
0x180013def  mov     r14, rax
0x180013df2  call    cs:__imp_FaxAccessCheckEx2
0x180013df8  test    eax, eax
0x180013dfa  jnz     short loc_180013E0F
0x180013dfc  call    cs:__imp_GetLastError
0x180013e02  mov     ebx, eax
0x180013e04  test    eax, eax
0x180013e06  jnz     loc_180013EF1
0x180013e0c  and     dword ptr [rdi], 0FFFFFFFDh
0x180013e0f  mov     rcx, [rbp+10h]; hInstance
0x180013e13  lea     rsi, Buffer
0x180013e1a  mov     r8, rsi; lpBuffer
0x180013e1d  mov     r9d, 104h; cchBufferMax
0x180013e23  mov     edx, 122Eh; uID
0x180013e28  call    cs:__imp_LoadStringW
0x180013e2e  test    eax, eax
0x180013e30  jnz     short loc_180013E71
0x180013e32  mov     rax, cs:WPP_GLOBAL_Control
0x180013e39  cmp     rax, r13
0x180013e3c  jz      short loc_180013E6F
0x180013e3e  test    [rax+1Ch], r12d
0x180013e42  jz      short loc_180013E6F
0x180013e44  cmp     byte ptr [rax+19h], 2
0x180013e48  jb      short loc_180013E6F
0x180013e4a  call    cs:__imp_GetLastError
0x180013e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e57  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180013e5e  mov     edx, 0Fh
0x180013e63  mov     r9d, eax
0x180013e66  mov     rcx, [rcx+10h]
0x180013e6a  call    WPP_SF_d
0x180013e6f  xor     esi, esi
0x180013e71  mov     [rdi+20h], rsi
0x180013e75  call    ?GetFirstFaxPrinterName@@YAHPEAGKK@Z; GetFirstFaxPrinterName(ushort *,ulong,ulong)
0x180013e7a  test    eax, eax
0x180013e7c  jz      loc_180013F10
0x180013e82  lea     rax, qword_18001EE60
0x180013e89  jmp     loc_180013F4F
0x180013e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e95  mov     r15, r14
0x180013e98  cmp     rcx, r13
0x180013e9b  jz      loc_180013F63
0x180013ea1  test    [rcx+1Ch], r12d
0x180013ea5  jz      loc_180013F63
0x180013eab  cmp     byte ptr [rcx+19h], 2
0x180013eaf  jb      loc_180013F63
0x180013eb5  mov     edx, 0Ch
0x180013eba  mov     rcx, [rcx+10h]
0x180013ebe  mov     r9d, eax
0x180013ec1  mov     r8, rsi
0x180013ec4  call    WPP_SF_d
0x180013ec9  jmp     loc_180013F63
0x180013ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ed5  cmp     rcx, r13
0x180013ed8  jz      loc_180013F63
0x180013ede  test    [rcx+1Ch], r12d
0x180013ee2  jz      short loc_180013F63
0x180013ee4  cmp     byte ptr [rcx+19h], 2
0x180013ee8  jb      short loc_180013F63
0x180013eea  mov     edx, 0Dh
0x180013eef  jmp     short loc_180013EBA
0x180013ef1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ef8  cmp     rcx, r13
0x180013efb  jz      short loc_180013F63
0x180013efd  test    [rcx+1Ch], r12d
0x180013f01  jz      short loc_180013F63
0x180013f03  cmp     byte ptr [rcx+19h], 2
0x180013f07  jb      short loc_180013F63
0x180013f09  mov     edx, 0Eh
0x180013f0e  jmp     short loc_180013EBA
0x180013f10  mov     rax, cs:WPP_GLOBAL_Control
0x180013f17  cmp     rax, r13
0x180013f1a  jz      short loc_180013F4D
0x180013f1c  test    [rax+1Ch], r12d
0x180013f20  jz      short loc_180013F4D
0x180013f22  cmp     byte ptr [rax+19h], 2
0x180013f26  jb      short loc_180013F4D
0x180013f28  call    cs:__imp_GetLastError
0x180013f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f35  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180013f3c  mov     edx, 10h
0x180013f41  mov     r9d, eax
0x180013f44  mov     rcx, [rcx+10h]
0x180013f48  call    WPP_SF_d
0x180013f4d  xor     eax, eax
0x180013f4f  mov     [rdi+18h], rax
0x180013f53  mov     rax, [rbp+10h]
0x180013f57  mov     [rdi+8], rax
0x180013f5b  mov     qword ptr [rdi+10h], 0
0x180013f63  mov     rcx, r14; hObject
0x180013f66  call    ReleasePrivilege
0x180013f6b  mov     rcx, r15; hObject
0x180013f6e  call    ReleasePrivilege
0x180013f73  test    ebx, ebx
0x180013f75  jle     short loc_180013F80
0x180013f77  movzx   ebx, bx
0x180013f7a  or      ebx, 80070000h
0x180013f80  mov     eax, ebx
0x180013f82  add     rsp, 28h
0x180013f86  pop     r15
0x180013f88  pop     r14
0x180013f8a  pop     r13
0x180013f8c  pop     r12
0x180013f8e  pop     rdi
0x180013f8f  pop     rsi
0x180013f90  pop     rbp
0x180013f91  pop     rbx
0x180013f92  retn
```
