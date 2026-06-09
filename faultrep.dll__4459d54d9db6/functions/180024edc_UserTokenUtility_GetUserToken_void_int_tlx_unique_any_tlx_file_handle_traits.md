# UserTokenUtility::GetUserToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180024edc`
- end: `0x1800250f5`
- name: `?GetUserToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, __int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000e7c0`

## callees

- `0x180003d54`
- `0x180007704`
- `0x180009ed8`
- `0x180009f00`
- `0x180024df8`
- `0x180024edc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024f62`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025013`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002506f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002506f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800250e5`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180025009`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180025009`

## pseudocode

```c
__int64 __fastcall UserTokenUtility::GetUserToken(HANDLE ProcessHandle, __int64 a2, void **a3)
{
  void *v5; // rcx
  unsigned int TokenSessionId; // ebx
  void **v7; // rax
  signed int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  void **v11; // rax
  signed int LastError; // eax
  HANDLE v13; // rax
  void *v14; // rcx
  HANDLE v16; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v17; // [rsp+58h] [rbp+28h] BYREF
  HANDLE v18; // [rsp+68h] [rbp+38h] BYREF

  v18 = 0;
  v16 = 0;
  v17 = 0;
  if ( ProcessHandle && a3 )
  {
    v5 = *a3;
    *a3 = 0;
    if ( (unsigned __int64)v5 + 1 > 1 )
      CloseHandle(v5);
    if ( !(unsigned __int8)IsQueryUserTokenPresent() )
    {
      TokenSessionId = -2147024846;
      goto LABEL_31;
    }
    v7 = tlx::replace<tlx::file_handle_traits>(&v18);
    if ( OpenProcessToken(ProcessHandle, 0x4Fu, v7) )
    {
      TokenSessionId = UserTokenUtility::GetTokenSessionId(v18, &v17);
      if ( (TokenSessionId & 0x80000000) == 0 )
      {
        v11 = tlx::replace<tlx::file_handle_traits>(&v16);
        if ( (unsigned int)QueryUserToken(v17, v11) )
        {
          v13 = v16;
          v16 = 0;
          v14 = *a3;
          *a3 = v13;
          if ( (unsigned __int64)v14 + 1 > 1 )
            CloseHandle(v14);
          TokenSessionId = 0;
        }
        else
        {
          LastError = GetLastError();
          TokenSessionId = LastError;
          if ( LastError > 0 )
            TokenSessionId = (unsigned __int16)LastError | 0x80070000;
          if ( TokenSessionId != -2147024846 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 26;
              goto LABEL_13;
            }
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 25;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v8 = GetLastError();
      TokenSessionId = v8;
      if ( v8 > 0 )
        TokenSessionId = (unsigned __int16)v8 | 0x80070000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 24;
LABEL_13:
        WPP_SF_d(v9[2], v10, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, TokenSessionId);
      }
    }
  }
  else
  {
    TokenSessionId = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids);
  }
LABEL_31:
  if ( (unsigned __int64)v16 + 1 > 1 )
    CloseHandle(v16);
  if ( (unsigned __int64)v18 + 1 > 1 )
    CloseHandle(v18);
  return TokenSessionId;
}

```

## disassembly

```asm
0x180024edc  mov     [rsp-18h+arg_8], edx
0x180024ee0  push    rbp
0x180024ee1  push    rbx
0x180024ee2  push    rdi
0x180024ee3  mov     rbp, rsp
0x180024ee6  sub     rsp, 30h
0x180024eea  mov     rdi, r8
0x180024eed  mov     rbx, rcx
0x180024ef0  mov     [rbp+arg_18], 0
0x180024ef8  mov     [rbp+arg_0], 0
0x180024f00  mov     [rbp+hObject], 0
0x180024f08  mov     [rbp+arg_8], 0
0x180024f0f  test    rcx, rcx
0x180024f12  jz      loc_180025079
0x180024f18  test    r8, r8
0x180024f1b  jz      loc_180025079
0x180024f21  mov     rcx, [r8]; hObject
0x180024f24  mov     qword ptr [r8], 0
0x180024f2b  lea     rax, [rcx+1]
0x180024f2f  cmp     rax, 1
0x180024f33  jbe     short loc_180024F3B
0x180024f35  call    cs:__imp_CloseHandle
0x180024f3b  call    IsQueryUserTokenPresent
0x180024f40  test    al, al
0x180024f42  jnz     short loc_180024F4E
0x180024f44  mov     ebx, 80070032h
0x180024f49  jmp     loc_1800250AD
0x180024f4e  lea     rcx, [rbp+arg_18]
0x180024f52  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180024f57  mov     r8, rax; TokenHandle
0x180024f5a  mov     edx, 4Fh ; 'O'; DesiredAccess
0x180024f5f  mov     rcx, rbx; ProcessHandle
0x180024f62  call    cs:__imp_OpenProcessToken
0x180024f68  test    eax, eax
0x180024f6a  jnz     short loc_180024FBF
0x180024f6c  call    cs:__imp_GetLastError
0x180024f72  mov     ebx, eax
0x180024f74  test    eax, eax
0x180024f76  jle     short loc_180024F81
0x180024f78  movzx   ebx, ax
0x180024f7b  or      ebx, 80070000h
0x180024f81  lea     rax, WPP_GLOBAL_Control
0x180024f88  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f8f  cmp     rcx, rax
0x180024f92  jz      loc_1800250AD
0x180024f98  test    byte ptr [rcx+1Ch], 1
0x180024f9c  jz      loc_1800250AD
0x180024fa2  mov     edx, 18h
0x180024fa7  mov     r9d, ebx
0x180024faa  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180024fb1  mov     rcx, [rcx+10h]
0x180024fb5  call    WPP_SF_d
0x180024fba  jmp     loc_1800250AD
0x180024fbf  lea     rdx, [rbp+arg_8]; unsigned int *
0x180024fc3  mov     rcx, [rbp+arg_18]; void *
0x180024fc7  call    ?GetTokenSessionId@UserTokenUtility@@SAJPEAXPEAK@Z; UserTokenUtility::GetTokenSessionId(void *,ulong *)
0x180024fcc  mov     ebx, eax
0x180024fce  test    eax, eax
0x180024fd0  jns     short loc_180024FFA
0x180024fd2  lea     rax, WPP_GLOBAL_Control
0x180024fd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fe0  cmp     rcx, rax
0x180024fe3  jz      loc_1800250AD
0x180024fe9  test    byte ptr [rcx+1Ch], 1
0x180024fed  jz      loc_1800250AD
0x180024ff3  mov     edx, 19h
0x180024ff8  jmp     short loc_180024FA7
0x180024ffa  lea     rcx, [rbp+arg_0]
0x180024ffe  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180025003  mov     rdx, rax
0x180025006  mov     ecx, [rbp+arg_8]
0x180025009  call    cs:__imp_QueryUserToken
0x18002500f  test    eax, eax
0x180025011  jnz     short loc_180025053
0x180025013  call    cs:__imp_GetLastError
0x180025019  mov     ebx, eax
0x18002501b  test    eax, eax
0x18002501d  jle     short loc_180025028
0x18002501f  movzx   ebx, ax
0x180025022  or      ebx, 80070000h
0x180025028  cmp     ebx, 80070032h
0x18002502e  jz      short loc_1800250AD
0x180025030  lea     rax, WPP_GLOBAL_Control
0x180025037  mov     rcx, cs:WPP_GLOBAL_Control
0x18002503e  cmp     rcx, rax
0x180025041  jz      short loc_1800250AD
0x180025043  test    byte ptr [rcx+1Ch], 1
0x180025047  jz      short loc_1800250AD
0x180025049  mov     edx, 1Ah
0x18002504e  jmp     loc_180024FA7
0x180025053  mov     rax, [rbp+arg_0]
0x180025057  mov     [rbp+arg_0], 0
0x18002505f  mov     rcx, [rdi]; hObject
0x180025062  mov     [rdi], rax
0x180025065  lea     rax, [rcx+1]
0x180025069  cmp     rax, 1
0x18002506d  jbe     short loc_180025075
0x18002506f  call    cs:__imp_CloseHandle
0x180025075  xor     ebx, ebx
0x180025077  jmp     short loc_1800250AD
0x180025079  mov     ebx, 80070057h
0x18002507e  lea     rax, WPP_GLOBAL_Control
0x180025085  mov     rcx, cs:WPP_GLOBAL_Control
0x18002508c  cmp     rcx, rax
0x18002508f  jz      short loc_1800250AD
0x180025091  test    byte ptr [rcx+1Ch], 1
0x180025095  jz      short loc_1800250AD
0x180025097  mov     edx, 17h
0x18002509c  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x1800250a3  mov     rcx, [rcx+10h]
0x1800250a7  call    WPP_SF_
0x1800250ac  nop
0x1800250ad  mov     rcx, [rbp+hObject]; hObject
0x1800250b1  lea     rax, [rcx+1]
0x1800250b5  cmp     rax, 1
0x1800250b9  jbe     short loc_1800250C2
0x1800250bb  call    cs:__imp_CloseHandle
0x1800250c1  nop
0x1800250c2  mov     rcx, [rbp+arg_0]; hObject
0x1800250c6  lea     rax, [rcx+1]
0x1800250ca  cmp     rax, 1
0x1800250ce  jbe     short loc_1800250D7
0x1800250d0  call    cs:__imp_CloseHandle
0x1800250d6  nop
0x1800250d7  mov     rcx, [rbp+arg_18]; hObject
0x1800250db  lea     rax, [rcx+1]
0x1800250df  cmp     rax, 1
0x1800250e3  jbe     short loc_1800250EB
0x1800250e5  call    cs:__imp_CloseHandle
0x1800250eb  mov     eax, ebx
0x1800250ed  add     rsp, 30h
0x1800250f1  pop     rdi
0x1800250f2  pop     rbx
0x1800250f3  pop     rbp
0x1800250f4  retn
```
