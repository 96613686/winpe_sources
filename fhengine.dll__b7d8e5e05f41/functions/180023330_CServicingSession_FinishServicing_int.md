# CServicingSession::FinishServicing(int)

- ea: `0x180023330`
- end: `0x1800235d7`
- name: `?FinishServicing@CServicingSession@@UEAAJH@Z`
- size: `679`
- prototype: `__int64 __fastcall(CServicingSession *this, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800077f0`
- `0x180007818`
- `0x18000e078`
- `0x18002204c`
- `0x180023330`
- `0x180031680`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1800233d8`
- `ADVAPI32!SetThreadToken` at `0x180023540`
- `ADVAPI32!SetThreadToken` at `0x1800233d8`
- `ADVAPI32!SetThreadToken` at `0x180023540`
- `KERNEL32!GetLastError` at `0x1800233e2`
- `KERNEL32!GetLastError` at `0x18002355c`
- `KERNEL32!GetLastError` at `0x1800233e2`
- `KERNEL32!GetLastError` at `0x18002355c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002338c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002338c`

## pseudocode

```c
__int64 __fastcall CServicingSession::FinishServicing(CServicingSession *this, int a2, __int64 a3)
{
  int v3; // ebx
  signed int LastError; // eax
  signed int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // esi
  int v12; // ebx
  PVOID *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // r8
  signed int v16; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v19[16]; // [rsp+38h] [rbp-40h] BYREF

  v3 = 0;
  SystemTimeAsFileTime.dwLowDateTime = 0;
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, CatalogFlushStart, a3, 1, v19);
  GetSystemTimeAsFileTime((LPFILETIME)this + 45);
  if ( *((_DWORD *)this + 40) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids);
    v3 = 1;
  }
  if ( !SetThreadToken(0, *((HANDLE *)this + 43)) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 38;
LABEL_14:
      WPP_SF_d(v8[2], v9, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids, (unsigned int)v7);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  v10 = *((_DWORD *)this + 39);
  v11 = 0;
  if ( v10 && !v3 )
  {
    if ( a2 )
    {
      v12 = 1;
      goto LABEL_32;
    }
    goto LABEL_31;
  }
  if ( !a2 )
  {
LABEL_31:
    v12 = 0;
    goto LABEL_32;
  }
  if ( v3 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids);
      v10 = *((_DWORD *)this + 39);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = -2147220479;
  }
  else
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  v12 = 0;
  if ( !v10 )
  {
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      WPP_SF_(v13[2], 40, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids);
    v11 = -2147220478;
  }
LABEL_32:
  v7 = CSessionBaseRW::FlushAndBackupCatalog(
         (CServicingSession *)((char *)this + 8),
         v12,
         0,
         (int *)this + 40,
         (struct _FILETIME)&SystemTimeAsFileTime);
  if ( v7 < 0 )
  {
    if ( !SystemTimeAsFileTime.dwLowDateTime )
      goto LABEL_43;
    if ( !a2 || !*((_DWORD *)this + 99) )
      v7 = 0;
  }
  if ( !SystemTimeAsFileTime.dwLowDateTime )
  {
    if ( v7 >= 0 )
      goto LABEL_46;
LABEL_43:
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 42;
      goto LABEL_14;
    }
    goto LABEL_47;
  }
  if ( v7 >= 0 )
  {
LABEL_46:
    v7 = v11;
    goto LABEL_47;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 41;
    goto LABEL_14;
  }
LABEL_47:
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
      (unsigned int)v16);
  }
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v14, CatalogFlushStop, v15, 1, v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023330  mov     r11, rsp
0x180023333  mov     [r11+10h], rbx
0x180023337  mov     [r11+18h], rbp
0x18002333b  push    rsi
0x18002333c  push    rdi
0x18002333d  push    r12
0x18002333f  push    r13
0x180023341  push    r14
0x180023343  sub     rsp, 50h
0x180023347  mov     rax, cs:__security_cookie
0x18002334e  xor     rax, rsp
0x180023351  mov     [rsp+78h+var_30], rax
0x180023356  xor     ebx, ebx
0x180023358  mov     ebp, edx
0x18002335a  mov     rdi, rcx
0x18002335d  mov     [rsp+78h+var_48.dwLowDateTime], ebx
0x180023361  lea     r12d, [rbx+1]
0x180023365  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, r12b
0x18002336c  jz      short loc_180023385
0x18002336e  lea     rax, [r11-40h]
0x180023372  mov     r9d, r12d
0x180023375  lea     rdx, CatalogFlushStart
0x18002337c  mov     [r11-58h], rax
0x180023380  call    McGenEventWrite_EventWriteTransfer
0x180023385  lea     rcx, [rdi+168h]; lpSystemTimeAsFileTime
0x18002338c  call    cs:__imp_GetSystemTimeAsFileTime
0x180023392  lea     r14, [rdi+0A0h]
0x180023399  lea     r13, WPP_GLOBAL_Control
0x1800233a0  cmp     [r14], ebx
0x1800233a3  jz      short loc_1800233CF
0x1800233a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233ac  cmp     rcx, r13
0x1800233af  jz      short loc_1800233CC
0x1800233b1  test    byte ptr [rcx+1Ch], 8
0x1800233b5  jz      short loc_1800233CC
0x1800233b7  mov     rcx, [rcx+10h]
0x1800233bb  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x1800233c2  mov     edx, 25h ; '%'
0x1800233c7  call    WPP_SF_
0x1800233cc  mov     ebx, r12d
0x1800233cf  mov     rdx, [rdi+158h]; Token
0x1800233d6  xor     ecx, ecx; Thread
0x1800233d8  call    cs:__imp_SetThreadToken
0x1800233de  test    eax, eax
0x1800233e0  jnz     short loc_18002342E
0x1800233e2  call    cs:__imp_GetLastError
0x1800233e8  mov     ebx, eax
0x1800233ea  test    eax, eax
0x1800233ec  jle     short loc_1800233F7
0x1800233ee  movzx   ebx, ax
0x1800233f1  or      ebx, 80070000h
0x1800233f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233fe  cmp     rcx, r13
0x180023401  jz      loc_18002353C
0x180023407  test    [rcx+1Ch], r12b
0x18002340b  jz      loc_18002353C
0x180023411  mov     edx, 26h ; '&'
0x180023416  mov     rcx, [rcx+10h]
0x18002341a  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180023421  mov     r9d, ebx
0x180023424  call    WPP_SF_d
0x180023429  jmp     loc_18002353C
0x18002342e  mov     eax, [rdi+9Ch]
0x180023434  xor     esi, esi
0x180023436  test    eax, eax
0x180023438  jz      short loc_180023447
0x18002343a  test    ebx, ebx
0x18002343c  jnz     short loc_180023447
0x18002343e  test    ebp, ebp
0x180023440  jz      short loc_1800234BC
0x180023442  mov     ebx, r12d
0x180023445  jmp     short loc_1800234BE
0x180023447  test    ebp, ebp
0x180023449  jz      short loc_1800234BC
0x18002344b  test    ebx, ebx
0x18002344d  jz      short loc_18002348A
0x18002344f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023456  cmp     rcx, r13
0x180023459  jz      short loc_180023483
0x18002345b  test    [rcx+1Ch], r12b
0x18002345f  jz      short loc_180023483
0x180023461  mov     rcx, [rcx+10h]
0x180023465  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x18002346c  mov     edx, 27h ; '''
0x180023471  call    WPP_SF_
0x180023476  mov     eax, [rdi+9Ch]
0x18002347c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023483  mov     esi, 80040401h
0x180023488  jmp     short loc_180023491
0x18002348a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023491  xor     ebx, ebx
0x180023493  test    eax, eax
0x180023495  jnz     short loc_1800234BE
0x180023497  cmp     rcx, r13
0x18002349a  jz      short loc_1800234B5
0x18002349c  test    [rcx+1Ch], r12b
0x1800234a0  jz      short loc_1800234B5
0x1800234a2  mov     rcx, [rcx+10h]
0x1800234a6  lea     edx, [rbx+28h]
0x1800234a9  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x1800234b0  call    WPP_SF_
0x1800234b5  mov     esi, 80040402h
0x1800234ba  jmp     short loc_1800234BE
0x1800234bc  xor     ebx, ebx
0x1800234be  lea     rax, [rsp+78h+var_48]
0x1800234c3  mov     r9, r14; int *
0x1800234c6  lea     rcx, [rdi+8]; this
0x1800234ca  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], rax; SystemTimeAsFileTime
0x1800234cf  xor     r8d, r8d; enum _PRIORITY_HINT *
0x1800234d2  mov     edx, ebx; int
0x1800234d4  call    ?FlushAndBackupCatalog@CSessionBaseRW@@IEAAJHPEBW4_PRIORITY_HINT@@PEAH1@Z; CSessionBaseRW::FlushAndBackupCatalog(int,_PRIORITY_HINT const *,int *,int *)
0x1800234d9  mov     ebx, eax
0x1800234db  mov     eax, [rsp+78h+var_48.dwLowDateTime]
0x1800234df  test    ebx, ebx
0x1800234e1  jns     short loc_1800234F6
0x1800234e3  test    eax, eax
0x1800234e5  jz      short loc_18002351E
0x1800234e7  test    ebp, ebp
0x1800234e9  jz      short loc_1800234F4
0x1800234eb  cmp     dword ptr [rdi+18Ch], 0
0x1800234f2  jnz     short loc_1800234F6
0x1800234f4  xor     ebx, ebx
0x1800234f6  test    eax, eax
0x1800234f8  jz      short loc_18002351A
0x1800234fa  test    ebx, ebx
0x1800234fc  jns     short loc_18002353A
0x1800234fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180023505  cmp     rcx, r13
0x180023508  jz      short loc_18002353C
0x18002350a  test    [rcx+1Ch], r12b
0x18002350e  jz      short loc_18002353C
0x180023510  mov     edx, 29h ; ')'
0x180023515  jmp     loc_180023416
0x18002351a  test    ebx, ebx
0x18002351c  jns     short loc_18002353A
0x18002351e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023525  cmp     rcx, r13
0x180023528  jz      short loc_18002353C
0x18002352a  test    [rcx+1Ch], r12b
0x18002352e  jz      short loc_18002353C
0x180023530  mov     edx, 2Ah ; '*'
0x180023535  jmp     loc_180023416
0x18002353a  mov     ebx, esi
0x18002353c  xor     edx, edx; Token
0x18002353e  xor     ecx, ecx; Thread
0x180023540  call    cs:__imp_SetThreadToken
0x180023546  test    eax, eax
0x180023548  jnz     short loc_18002358D
0x18002354a  mov     rax, cs:WPP_GLOBAL_Control
0x180023551  cmp     rax, r13
0x180023554  jz      short loc_18002358D
0x180023556  test    [rax+1Ch], r12b
0x18002355a  jz      short loc_18002358D
0x18002355c  call    cs:__imp_GetLastError
0x180023562  test    eax, eax
0x180023564  jle     short loc_18002356E
0x180023566  movzx   eax, ax
0x180023569  or      eax, 80070000h
0x18002356e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023575  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x18002357c  mov     edx, 2Bh ; '+'
0x180023581  mov     r9d, eax
0x180023584  mov     rcx, [rcx+10h]
0x180023588  call    WPP_SF_d
0x18002358d  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, r12b
0x180023594  jz      short loc_1800235AF
0x180023596  lea     rax, [rsp+78h+var_40]
0x18002359b  mov     r9d, r12d
0x18002359e  lea     rdx, CatalogFlushStop
0x1800235a5  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800235aa  call    McGenEventWrite_EventWriteTransfer
0x1800235af  mov     eax, ebx
0x1800235b1  mov     rcx, [rsp+78h+var_30]
0x1800235b6  xor     rcx, rsp; StackCookie
0x1800235b9  call    __security_check_cookie
0x1800235be  lea     r11, [rsp+78h+var_28]
0x1800235c3  mov     rbx, [r11+38h]
0x1800235c7  mov     rbp, [r11+40h]
0x1800235cb  mov     rsp, r11
0x1800235ce  pop     r14
0x1800235d0  pop     r13
0x1800235d2  pop     r12
0x1800235d4  pop     rdi
0x1800235d5  pop     rsi
0x1800235d6  retn
```
