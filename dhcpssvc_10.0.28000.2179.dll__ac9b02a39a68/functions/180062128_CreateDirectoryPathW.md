# CreateDirectoryPathW

- ea: `0x180062128`
- end: `0x1800622fe`
- name: `CreateDirectoryPathW`
- size: `470`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003298`
- `0x1800038f0`
- `0x18002f890`
- `0x18004d330`
- `0x180062094`
- `0x180062128`
- `0x180066e90`

## callees

- `0x1800057e0`
- `0x1800058bc`
- `0x180005924`
- `0x180062128`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18006224b`
- `msvcrt!wcsrchr` at `0x18006224b`
- `KERNEL32!SetLastError` at `0x1800622d4`
- `KERNEL32!SetLastError` at `0x1800622d4`
- `KERNEL32!CreateDirectoryW` at `0x180062194`
- `KERNEL32!CreateDirectoryW` at `0x180062282`
- `KERNEL32!CreateDirectoryW` at `0x180062194`
- `KERNEL32!CreateDirectoryW` at `0x180062282`
- `KERNEL32!GetLastError` at `0x1800621bb`
- `KERNEL32!GetLastError` at `0x1800621ed`
- `KERNEL32!GetLastError` at `0x1800622a8`
- `KERNEL32!GetLastError` at `0x1800621bb`
- `KERNEL32!GetLastError` at `0x1800621ed`
- `KERNEL32!GetLastError` at `0x1800622a8`

## pseudocode

```c
BOOL __fastcall CreateDirectoryPathW(LPCWSTR lpPathName)
{
  unsigned int DirectoryW; // esi
  __int64 v3; // rbx
  DWORD LastError; // eax
  BOOL result; // eax
  DWORD v6; // eax
  DWORD v7; // ebx
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  int DirectoryPathW; // eax
  __int64 v11; // rbx
  char v12; // al

  if ( !lpPathName || !*lpPathName )
    goto LABEL_23;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids, lpPathName);
  DirectoryW = CreateDirectoryW(lpPathName, &DhcpGlobalDirSecurityAttr);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    WPP_SF_dD(v3, 21, &WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids, DirectoryW, LastError);
  }
  if ( DirectoryW )
    return DirectoryW;
  v6 = GetLastError();
  v7 = v6;
  if ( v6 == 183 )
    return 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids,
      (_DWORD)lpPathName,
      v6);
  if ( v7 != 3 )
    return 0;
  v8 = wcsrchr(lpPathName, 0x5Cu);
  v9 = v8;
  if ( v8 )
  {
    *v8 = 0;
    DirectoryPathW = CreateDirectoryPathW(lpPathName);
    *v9 = 92;
    if ( DirectoryPathW )
    {
      result = CreateDirectoryW(lpPathName, &DhcpGlobalDirSecurityAttr);
      if ( result )
        return result;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v12 = GetLastError();
        WPP_SF_SD(v11, 23, (unsigned int)&WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids, (_DWORD)lpPathName, v12);
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
0x180062128  mov     rax, rsp
0x18006212b  mov     [rax+8], rbx
0x18006212f  mov     [rax+10h], rbp
0x180062133  mov     [rax+18h], rsi
0x180062137  mov     [rax+20h], rdi
0x18006213b  push    r14
0x18006213d  sub     rsp, 30h
0x180062141  xor     ebp, ebp
0x180062143  mov     rdi, rcx
0x180062146  test    rcx, rcx
0x180062149  jz      loc_1800622CF
0x18006214f  cmp     bp, [rcx]
0x180062152  jz      loc_1800622CF
0x180062158  mov     rcx, cs:WPP_GLOBAL_Control
0x18006215f  lea     r14, WPP_GLOBAL_Control
0x180062166  cmp     rcx, r14
0x180062169  jz      short loc_18006218A
0x18006216b  test    dword ptr [rcx+1Ch], 8000h
0x180062172  jz      short loc_18006218A
0x180062174  mov     rcx, [rcx+10h]
0x180062178  lea     edx, [rbp+14h]
0x18006217b  mov     r9, rdi
0x18006217e  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x180062185  call    WPP_SF_S
0x18006218a  lea     rdx, DhcpGlobalDirSecurityAttr; lpSecurityAttributes
0x180062191  mov     rcx, rdi; lpPathName
0x180062194  call    cs:__imp_CreateDirectoryW
0x18006219b  nop     dword ptr [rax+rax+00h]
0x1800621a0  mov     esi, eax
0x1800621a2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800621a9  cmp     rbx, r14
0x1800621ac  jz      short loc_1800621E2
0x1800621ae  test    dword ptr [rbx+1Ch], 8000h
0x1800621b5  jz      short loc_1800621E2
0x1800621b7  mov     rbx, [rbx+10h]
0x1800621bb  call    cs:__imp_GetLastError
0x1800621c2  nop     dword ptr [rax+rax+00h]
0x1800621c7  mov     edx, 15h
0x1800621cc  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x1800621d3  mov     r9d, esi
0x1800621d6  mov     [rsp+38h+var_18], eax
0x1800621da  mov     rcx, rbx
0x1800621dd  call    WPP_SF_dD
0x1800621e2  test    esi, esi
0x1800621e4  jz      short loc_1800621ED
0x1800621e6  mov     eax, esi
0x1800621e8  jmp     loc_1800622E2
0x1800621ed  call    cs:__imp_GetLastError
0x1800621f4  nop     dword ptr [rax+rax+00h]
0x1800621f9  mov     ebx, eax
0x1800621fb  cmp     eax, 0B7h
0x180062200  jnz     short loc_18006220C
0x180062202  mov     eax, 1
0x180062207  jmp     loc_1800622E2
0x18006220c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062213  cmp     rcx, r14
0x180062216  jz      short loc_18006223A
0x180062218  test    byte ptr [rcx+1Ch], 10h
0x18006221c  jz      short loc_18006223A
0x18006221e  mov     rcx, [rcx+10h]
0x180062222  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x180062229  mov     edx, 16h
0x18006222e  mov     [rsp+38h+var_18], ebx
0x180062232  mov     r9, rdi
0x180062235  call    WPP_SF_SD
0x18006223a  cmp     ebx, 3
0x18006223d  jnz     loc_1800622E0
0x180062243  lea     esi, [rbx+59h]
0x180062246  mov     rcx, rdi; Str
0x180062249  mov     edx, esi; Ch
0x18006224b  call    cs:__imp_wcsrchr
0x180062252  nop     dword ptr [rax+rax+00h]
0x180062257  mov     rbx, rax
0x18006225a  test    rax, rax
0x18006225d  jz      short loc_1800622CF
0x18006225f  lea     rdx, DhcpGlobalDirSecurityAttr
0x180062266  mov     [rax], bp
0x180062269  mov     rcx, rdi; lpPathName
0x18006226c  call    CreateDirectoryPathW
0x180062271  mov     [rbx], si
0x180062274  test    eax, eax
0x180062276  jz      short loc_1800622E0
0x180062278  lea     rdx, DhcpGlobalDirSecurityAttr; lpSecurityAttributes
0x18006227f  mov     rcx, rdi; lpPathName
0x180062282  call    cs:__imp_CreateDirectoryW
0x180062289  nop     dword ptr [rax+rax+00h]
0x18006228e  test    eax, eax
0x180062290  jnz     short loc_1800622E2
0x180062292  mov     rbx, cs:WPP_GLOBAL_Control
0x180062299  cmp     rbx, r14
0x18006229c  jz      short loc_1800622E0
0x18006229e  test    byte ptr [rbx+1Ch], 10h
0x1800622a2  jz      short loc_1800622E0
0x1800622a4  mov     rbx, [rbx+10h]
0x1800622a8  call    cs:__imp_GetLastError
0x1800622af  nop     dword ptr [rax+rax+00h]
0x1800622b4  lea     edx, [rsi-45h]
0x1800622b7  mov     r9, rdi
0x1800622ba  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x1800622c1  mov     [rsp+38h+var_18], eax
0x1800622c5  mov     rcx, rbx
0x1800622c8  call    WPP_SF_SD
0x1800622cd  jmp     short loc_1800622E0
0x1800622cf  mov     ecx, 0A1h; dwErrCode
0x1800622d4  call    cs:__imp_SetLastError
0x1800622db  nop     dword ptr [rax+rax+00h]
0x1800622e0  xor     eax, eax
0x1800622e2  mov     rbx, [rsp+38h+arg_0]
0x1800622e7  mov     rbp, [rsp+38h+arg_8]
0x1800622ec  mov     rsi, [rsp+38h+arg_10]
0x1800622f1  mov     rdi, [rsp+38h+arg_18]
0x1800622f6  add     rsp, 30h
0x1800622fa  pop     r14
0x1800622fc  retn
```
