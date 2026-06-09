# FvePersistentRequest::CreateSVIRequestFolder(ushort const *,_FVE_REQUEST_TYPE)

- ea: `0x1800ee320`
- end: `0x1800ee666`
- name: `?CreateSVIRequestFolder@FvePersistentRequest@@SAJPEBGW4_FVE_REQUEST_TYPE@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1800ee734`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180019128`
- `0x1800c8db0`
- `0x1800ee320`
- `0x1800ef0d0`
- `0x1800ef7f0`
- `0x1800f030c`
- `0x1800f05d4`
- `0x1800f0a00`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee5e2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ee44b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ee44b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800ee526`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800ee5c0`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800ee526`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800ee5c0`

## pseudocode

```c
__int64 __fastcall FvePersistentRequest::CreateSVIRequestFolder(const unsigned __int16 *a1, unsigned int a2)
{
  unsigned int FolderName; // eax
  unsigned int v5; // r9d
  signed int v6; // ebx
  PVOID *v7; // rcx
  unsigned int SystemVolumeInformationPath; // eax
  signed int v9; // eax
  int v10; // eax
  signed int LastError; // eax
  signed int v12; // eax
  bool v14; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR PathName[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v16[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(PathName, 0, 0x208u);
  memset_0(v16, 0, 0x208u);
  v14 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids);
  FolderName = FvePersistentRequest::GetFolderName(a2, v16);
  v6 = FolderName;
  if ( FolderName )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, FolderName);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 < 0 )
      goto LABEL_46;
  }
  SystemVolumeInformationPath = MakeSystemVolumeInformationPath(a1, v16, PathName, v5);
  v6 = SystemVolumeInformationPath;
  if ( SystemVolumeInformationPath )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        SystemVolumeInformationPath);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 < 0 )
      goto LABEL_46;
  }
  if ( CreateDirectoryW(PathName, 0) )
  {
    v6 = IsTerminalFolderRedirection(PathName, &v14);
    if ( v6 >= 0 && !v14 )
    {
      if ( a2 == 1 )
      {
        v10 = GrantAccessToSpecifiedUsers(PathName);
        v6 = v10;
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56,
              (unsigned int)&WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
              (unsigned int)PathName,
              v10);
          if ( !RemoveDirectoryW(PathName) )
          {
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return (unsigned int)v6;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_46;
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              57,
              &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
              (unsigned int)LastError);
          }
        }
      }
      goto LABEL_34;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_DlS(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, (__int64)PathName);
    if ( !RemoveDirectoryW(PathName) )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_45;
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)v12);
    }
LABEL_44:
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_45:
    v6 = 0;
    goto LABEL_46;
  }
  v9 = GetLastError();
  v6 = v9;
  if ( v9 == 183 )
    goto LABEL_44;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    {
LABEL_46:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
        WPP_SF_d(v7[2], 58, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, (unsigned int)v6);
      return (unsigned int)v6;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
      (unsigned int)v6);
LABEL_34:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ee320  mov     [rsp-8+arg_10], rbx
0x1800ee325  push    rbp
0x1800ee326  push    rsi
0x1800ee327  push    rdi
0x1800ee328  push    r14
0x1800ee32a  push    r15
0x1800ee32c  lea     rbp, [rsp-370h]
0x1800ee334  sub     rsp, 470h
0x1800ee33b  mov     rax, cs:__security_cookie
0x1800ee342  xor     rax, rsp
0x1800ee345  mov     [rbp+390h+var_30], rax
0x1800ee34c  mov     edi, edx
0x1800ee34e  mov     rsi, rcx
0x1800ee351  mov     ebx, 208h
0x1800ee356  lea     rcx, [rsp+490h+PathName]; void *
0x1800ee35b  mov     r8d, ebx; Size
0x1800ee35e  xor     edx, edx; Val
0x1800ee360  call    memset_0
0x1800ee365  mov     r8d, ebx; Size
0x1800ee368  lea     rcx, [rbp+390h+var_240]; void *
0x1800ee36f  xor     edx, edx; Val
0x1800ee371  call    memset_0
0x1800ee376  mov     [rsp+490h+var_460], 1
0x1800ee37b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee382  lea     r14, WPP_GLOBAL_Control
0x1800ee389  lea     r15, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ee390  cmp     rcx, r14
0x1800ee393  jz      short loc_1800EE3AC
0x1800ee395  test    byte ptr [rcx+1Ch], 20h
0x1800ee399  jz      short loc_1800EE3AC
0x1800ee39b  mov     rcx, [rcx+10h]
0x1800ee39f  mov     edx, 32h ; '2'
0x1800ee3a4  mov     r8, r15
0x1800ee3a7  call    WPP_SF_
0x1800ee3ac  lea     rdx, [rbp+390h+var_240]
0x1800ee3b3  mov     ecx, edi
0x1800ee3b5  call    ?GetFolderName@FvePersistentRequest@@SAJW4_FVE_REQUEST_TYPE@@PEAGK@Z; FvePersistentRequest::GetFolderName(_FVE_REQUEST_TYPE,ushort *,ulong)
0x1800ee3ba  mov     ebx, eax
0x1800ee3bc  test    eax, eax
0x1800ee3be  jz      short loc_1800EE3F5
0x1800ee3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee3c7  cmp     rcx, r14
0x1800ee3ca  jz      short loc_1800EE3ED
0x1800ee3cc  test    byte ptr [rcx+1Ch], 40h
0x1800ee3d0  jz      short loc_1800EE3ED
0x1800ee3d2  mov     rcx, [rcx+10h]
0x1800ee3d6  mov     edx, 33h ; '3'
0x1800ee3db  mov     r9d, eax
0x1800ee3de  mov     r8, r15
0x1800ee3e1  call    WPP_SF_d
0x1800ee3e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee3ed  test    ebx, ebx
0x1800ee3ef  js      loc_1800EE61E
0x1800ee3f5  lea     r8, [rsp+490h+PathName]; unsigned __int16 *
0x1800ee3fa  mov     rcx, rsi; unsigned __int16 *
0x1800ee3fd  lea     rdx, [rbp+390h+var_240]; unsigned __int16 *
0x1800ee404  call    ?MakeSystemVolumeInformationPath@@YAJPEBG0PEAGK@Z; MakeSystemVolumeInformationPath(ushort const *,ushort const *,ushort *,ulong)
0x1800ee409  mov     ebx, eax
0x1800ee40b  test    eax, eax
0x1800ee40d  jz      short loc_1800EE444
0x1800ee40f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee416  cmp     rcx, r14
0x1800ee419  jz      short loc_1800EE43C
0x1800ee41b  test    byte ptr [rcx+1Ch], 40h
0x1800ee41f  jz      short loc_1800EE43C
0x1800ee421  mov     rcx, [rcx+10h]
0x1800ee425  mov     edx, 34h ; '4'
0x1800ee42a  mov     r9d, eax
0x1800ee42d  mov     r8, r15
0x1800ee430  call    WPP_SF_d
0x1800ee435  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee43c  test    ebx, ebx
0x1800ee43e  js      loc_1800EE61E
0x1800ee444  xor     edx, edx; lpSecurityAttributes
0x1800ee446  lea     rcx, [rsp+490h+PathName]; lpPathName
0x1800ee44b  call    cs:__imp_CreateDirectoryW
0x1800ee452  nop     dword ptr [rax+rax+00h]
0x1800ee457  test    eax, eax
0x1800ee459  jnz     short loc_1800EE4B4
0x1800ee45b  call    cs:__imp_GetLastError
0x1800ee462  nop     dword ptr [rax+rax+00h]
0x1800ee467  mov     ebx, eax
0x1800ee469  cmp     eax, 0B7h
0x1800ee46e  jz      loc_1800EE615
0x1800ee474  test    eax, eax
0x1800ee476  jle     short loc_1800EE481
0x1800ee478  movzx   ebx, ax
0x1800ee47b  or      ebx, 80070000h
0x1800ee481  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee488  cmp     rcx, r14
0x1800ee48b  jz      loc_1800EE63D
0x1800ee491  test    byte ptr [rcx+1Ch], 40h
0x1800ee495  jz      loc_1800EE61E
0x1800ee49b  mov     rcx, [rcx+10h]
0x1800ee49f  mov     edx, 35h ; '5'
0x1800ee4a4  mov     r9d, ebx
0x1800ee4a7  mov     r8, r15
0x1800ee4aa  call    WPP_SF_d
0x1800ee4af  jmp     loc_1800EE583
0x1800ee4b4  lea     rdx, [rsp+490h+var_460]; bool *
0x1800ee4b9  lea     rcx, [rsp+490h+PathName]; unsigned __int16 *
0x1800ee4be  call    ?IsTerminalFolderRedirection@@YAJPEAGPEA_N@Z; IsTerminalFolderRedirection(ushort *,bool *)
0x1800ee4c3  mov     ebx, eax
0x1800ee4c5  movzx   eax, [rsp+490h+var_460]
0x1800ee4ca  test    ebx, ebx
0x1800ee4cc  js      loc_1800EE58F
0x1800ee4d2  test    al, al
0x1800ee4d4  jnz     loc_1800EE58F
0x1800ee4da  cmp     edi, 1
0x1800ee4dd  jnz     loc_1800EE583
0x1800ee4e3  lea     rcx, [rsp+490h+PathName]
0x1800ee4e8  call    ?GrantAccessToSpecifiedUsers@@YAJPEBGW4_TypeFolderAccessNeeded@@@Z; GrantAccessToSpecifiedUsers(ushort const *,_TypeFolderAccessNeeded)
0x1800ee4ed  mov     ebx, eax
0x1800ee4ef  test    eax, eax
0x1800ee4f1  jns     loc_1800EE583
0x1800ee4f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee4fe  cmp     rcx, r14
0x1800ee501  jz      short loc_1800EE521
0x1800ee503  test    byte ptr [rcx+1Ch], 2
0x1800ee507  jz      short loc_1800EE521
0x1800ee509  mov     rcx, [rcx+10h]
0x1800ee50d  lea     edx, [rdi+37h]
0x1800ee510  lea     r9, [rsp+490h+PathName]
0x1800ee515  mov     dword ptr [rsp+490h+var_470], eax
0x1800ee519  mov     r8, r15
0x1800ee51c  call    WPP_SF_SD
0x1800ee521  lea     rcx, [rsp+490h+PathName]; lpPathName
0x1800ee526  call    cs:__imp_RemoveDirectoryW
0x1800ee52d  nop     dword ptr [rax+rax+00h]
0x1800ee532  test    eax, eax
0x1800ee534  jnz     short loc_1800EE583
0x1800ee536  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee53d  cmp     rcx, r14
0x1800ee540  jz      loc_1800EE63D
0x1800ee546  test    byte ptr [rcx+1Ch], 2
0x1800ee54a  jz      loc_1800EE61E
0x1800ee550  call    cs:__imp_GetLastError
0x1800ee557  nop     dword ptr [rax+rax+00h]
0x1800ee55c  test    eax, eax
0x1800ee55e  jle     short loc_1800EE568
0x1800ee560  movzx   eax, ax
0x1800ee563  or      eax, 80070000h
0x1800ee568  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee56f  mov     edx, 39h ; '9'
0x1800ee574  mov     r9d, eax
0x1800ee577  mov     r8, r15
0x1800ee57a  mov     rcx, [rcx+10h]
0x1800ee57e  call    WPP_SF_D
0x1800ee583  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee58a  jmp     loc_1800EE61E
0x1800ee58f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee596  cmp     rcx, r14
0x1800ee599  jz      short loc_1800EE5BB
0x1800ee59b  test    byte ptr [rcx+1Ch], 8
0x1800ee59f  jz      short loc_1800EE5BB
0x1800ee5a1  mov     rcx, [rcx+10h]; LoggerHandle
0x1800ee5a5  lea     rdx, [rsp+490h+PathName]
0x1800ee5aa  mov     [rsp+490h+var_468], rdx; __int64
0x1800ee5af  mov     r9d, ebx
0x1800ee5b2  mov     dword ptr [rsp+490h+var_470], eax; char
0x1800ee5b6  call    WPP_SF_DlS
0x1800ee5bb  lea     rcx, [rsp+490h+PathName]; lpPathName
0x1800ee5c0  call    cs:__imp_RemoveDirectoryW
0x1800ee5c7  nop     dword ptr [rax+rax+00h]
0x1800ee5cc  test    eax, eax
0x1800ee5ce  jnz     short loc_1800EE615
0x1800ee5d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee5d7  cmp     rcx, r14
0x1800ee5da  jz      short loc_1800EE61C
0x1800ee5dc  test    byte ptr [rcx+1Ch], 2
0x1800ee5e0  jz      short loc_1800EE61C
0x1800ee5e2  call    cs:__imp_GetLastError
0x1800ee5e9  nop     dword ptr [rax+rax+00h]
0x1800ee5ee  test    eax, eax
0x1800ee5f0  jle     short loc_1800EE5FA
0x1800ee5f2  movzx   eax, ax
0x1800ee5f5  or      eax, 80070000h
0x1800ee5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee601  mov     edx, 37h ; '7'
0x1800ee606  mov     r9d, eax
0x1800ee609  mov     r8, r15
0x1800ee60c  mov     rcx, [rcx+10h]
0x1800ee610  call    WPP_SF_D
0x1800ee615  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee61c  xor     ebx, ebx
0x1800ee61e  cmp     rcx, r14
0x1800ee621  jz      short loc_1800EE63D
0x1800ee623  test    byte ptr [rcx+1Ch], 20h
0x1800ee627  jz      short loc_1800EE63D
0x1800ee629  mov     rcx, [rcx+10h]
0x1800ee62d  mov     edx, 3Ah ; ':'
0x1800ee632  mov     r9d, ebx
0x1800ee635  mov     r8, r15
0x1800ee638  call    WPP_SF_d
0x1800ee63d  mov     eax, ebx
0x1800ee63f  mov     rcx, [rbp+390h+var_30]
0x1800ee646  xor     rcx, rsp; StackCookie
0x1800ee649  call    __security_check_cookie
0x1800ee64e  mov     rbx, [rsp+490h+arg_10]
0x1800ee656  add     rsp, 470h
0x1800ee65d  pop     r15
0x1800ee65f  pop     r14
0x1800ee661  pop     rdi
0x1800ee662  pop     rsi
0x1800ee663  pop     rbp
0x1800ee664  retn
```
