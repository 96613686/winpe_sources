# MarkPerBootKeyForDeletion

- ea: `0x180046eb0`
- end: `0x18004711b`
- name: `MarkPerBootKeyForDeletion`
- size: `619`
- prototype: `__int64 __fastcall(__int64, _WORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180029004`

## callees

- `0x180004c04`
- `0x18000af80`
- `0x18000d3d0`
- `0x180018360`
- `0x180028114`
- `0x180046eb0`
- `0x180051d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004709d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004709d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180046f2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180046f2f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180046f43`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004708d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180046f43`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004708d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046f12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046f98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800470ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046f98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800470ec`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180046fec`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180046fec`

## string_xrefs

- `0x180047026`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall MarkPerBootKeyForDeletion(__int64 a1, _WORD *a2)
{
  _WORD *v3; // rdx
  int v5; // ebp
  int KeyFileFullPath; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  const char *v9; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v12; // eax
  signed int v13; // ebx
  DWORD v14; // eax
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+60h] [rbp+18h] BYREF

  lpExistingFileName = 0;
  v3 = *(_WORD **)(a1 + 16);
  TokenHandle = 0;
  v5 = 0;
  KeyFileFullPath = GetKeyFileFullPath(a2, v3, &lpExistingFileName);
  v7 = KeyFileFullPath;
  if ( KeyFileFullPath < 0 )
  {
    v8 = 1604;
    v9 = "Status";
LABEL_19:
    DebugTraceError((unsigned int)KeyFileFullPath, v9, "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v8);
    goto LABEL_20;
  }
  if ( *(_DWORD *)(a1 + 528) )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( SetThreadToken(0, 0) )
      {
        v5 = 1;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_aa991306b93132f591cbba2128657ece_Traceguids, LastError);
        CloseHandle(TokenHandle);
        TokenHandle = 0;
      }
    }
    else
    {
      v12 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_aa991306b93132f591cbba2128657ece_Traceguids, v12);
    }
  }
  if ( !MoveFileExW(lpExistingFileName, 0, 4u) )
  {
    KeyFileFullPath = GetLastError();
    if ( KeyFileFullPath > 0 )
      v7 = (unsigned __int16)KeyFileFullPath | 0x80070000;
    else
      v7 = KeyFileFullPath;
    v8 = 1647;
    v9 = "dwErr";
    goto LABEL_19;
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_aa991306b93132f591cbba2128657ece_Traceguids,
      (_DWORD)lpExistingFileName,
      v7);
  EtwLogNCryptPerbootKeyMarkedForDeletion(
    *(_QWORD *)(a1 + 56),
    *(_QWORD *)(a1 + 8),
    *(_QWORD *)(a1 + 16),
    *(_DWORD *)(a1 + 564),
    v7);
  v13 = 0;
  if ( v5 && !SetThreadToken(0, TokenHandle) )
  {
    v14 = GetLastError();
    v13 = v14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_aa991306b93132f591cbba2128657ece_Traceguids, v14);
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( lpExistingFileName )
    MSCryptFree(lpExistingFileName);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180046eb0  mov     r11, rsp
0x180046eb3  mov     [r11+10h], rbx
0x180046eb7  push    rbp
0x180046eb8  push    rdi
0x180046eb9  push    r12
0x180046ebb  sub     rsp, 30h
0x180046ebf  mov     rax, rdx
0x180046ec2  mov     qword ptr [r11+18h], 0
0x180046eca  mov     rdx, [rcx+10h]; void *
0x180046ece  lea     r8, [r11+18h]
0x180046ed2  mov     rdi, rcx
0x180046ed5  mov     qword ptr [r11+8], 0
0x180046edd  mov     rcx, rax; Src
0x180046ee0  xor     ebp, ebp
0x180046ee2  call    GetKeyFileFullPath
0x180046ee7  lea     r12, WPP_GLOBAL_Control
0x180046eee  mov     ebx, eax
0x180046ef0  test    eax, eax
0x180046ef2  jns     short loc_180046F06
0x180046ef4  mov     r9d, 644h
0x180046efa  lea     rdx, aStatus; "Status"
0x180046f01  jmp     loc_180047026
0x180046f06  cmp     [rdi+210h], ebp
0x180046f0c  jz      loc_180046FE1
0x180046f12  call    cs:__imp_GetCurrentThread
0x180046f19  nop     dword ptr [rax+rax+00h]
0x180046f1e  mov     edx, 4; DesiredAccess
0x180046f23  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180046f28  mov     rcx, rax; ThreadHandle
0x180046f2b  lea     r8d, [rdx-3]; OpenAsSelf
0x180046f2f  call    cs:__imp_OpenThreadToken
0x180046f36  nop     dword ptr [rax+rax+00h]
0x180046f3b  test    eax, eax
0x180046f3d  jz      short loc_180046FAB
0x180046f3f  xor     edx, edx; Token
0x180046f41  xor     ecx, ecx; Thread
0x180046f43  call    cs:__imp_SetThreadToken
0x180046f4a  nop     dword ptr [rax+rax+00h]
0x180046f4f  test    eax, eax
0x180046f51  jz      short loc_180046F5D
0x180046f53  mov     ebp, 1
0x180046f58  jmp     loc_180046FE1
0x180046f5d  call    cs:__imp_GetLastError
0x180046f64  nop     dword ptr [rax+rax+00h]
0x180046f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f70  cmp     rcx, r12
0x180046f73  jz      short loc_180046F93
0x180046f75  test    byte ptr [rcx+1Ch], 1
0x180046f79  jz      short loc_180046F93
0x180046f7b  mov     rcx, [rcx+10h]
0x180046f7f  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x180046f86  mov     edx, 0Dh
0x180046f8b  mov     r9d, eax
0x180046f8e  call    WPP_SF_D
0x180046f93  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180046f98  call    cs:__imp_CloseHandle
0x180046f9f  nop     dword ptr [rax+rax+00h]
0x180046fa4  mov     [rsp+48h+TokenHandle], rbp
0x180046fa9  jmp     short loc_180046FE1
0x180046fab  call    cs:__imp_GetLastError
0x180046fb2  nop     dword ptr [rax+rax+00h]
0x180046fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180046fbe  cmp     rcx, r12
0x180046fc1  jz      short loc_180046FE1
0x180046fc3  test    byte ptr [rcx+1Ch], 1
0x180046fc7  jz      short loc_180046FE1
0x180046fc9  mov     rcx, [rcx+10h]
0x180046fcd  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x180046fd4  mov     edx, 0Eh
0x180046fd9  mov     r9d, eax
0x180046fdc  call    WPP_SF_D
0x180046fe1  mov     rcx, [rsp+48h+lpExistingFileName]; lpExistingFileName
0x180046fe6  xor     edx, edx; lpNewFileName
0x180046fe8  lea     r8d, [rdx+4]; dwFlags
0x180046fec  call    cs:__imp_MoveFileExW
0x180046ff3  nop     dword ptr [rax+rax+00h]
0x180046ff8  test    eax, eax
0x180046ffa  jnz     short loc_180047034
0x180046ffc  call    cs:__imp_GetLastError
0x180047003  nop     dword ptr [rax+rax+00h]
0x180047008  test    eax, eax
0x18004700a  jg      short loc_180047010
0x18004700c  mov     ebx, eax
0x18004700e  jmp     short loc_180047019
0x180047010  movzx   ebx, ax
0x180047013  or      ebx, 80070000h
0x180047019  mov     r9d, 66Fh
0x18004701f  lea     rdx, aDwerr; "dwErr"
0x180047026  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004702d  mov     ecx, eax
0x18004702f  call    DebugTraceError
0x180047034  mov     rcx, cs:WPP_GLOBAL_Control
0x18004703b  cmp     rcx, r12
0x18004703e  jz      short loc_180047064
0x180047040  test    byte ptr [rcx+1Ch], 8
0x180047044  jz      short loc_180047064
0x180047046  mov     r9, [rsp+48h+lpExistingFileName]
0x18004704b  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x180047052  mov     rcx, [rcx+10h]
0x180047056  mov     edx, 0Fh
0x18004705b  mov     [rsp+48h+var_28], ebx
0x18004705f  call    WPP_SF_SD
0x180047064  mov     r9d, [rdi+234h]
0x18004706b  mov     r8, [rdi+10h]
0x18004706f  mov     rdx, [rdi+8]
0x180047073  mov     rcx, [rdi+38h]
0x180047077  mov     [rsp+48h+var_28], ebx
0x18004707b  call    EtwLogNCryptPerbootKeyMarkedForDeletion
0x180047080  xor     ebx, ebx
0x180047082  test    ebp, ebp
0x180047084  jz      short loc_1800470E2
0x180047086  mov     rdx, [rsp+48h+TokenHandle]; Token
0x18004708b  xor     ecx, ecx; Thread
0x18004708d  call    cs:__imp_SetThreadToken
0x180047094  nop     dword ptr [rax+rax+00h]
0x180047099  test    eax, eax
0x18004709b  jnz     short loc_1800470E2
0x18004709d  call    cs:__imp_GetLastError
0x1800470a4  nop     dword ptr [rax+rax+00h]
0x1800470a9  mov     ebx, eax
0x1800470ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800470b2  cmp     rcx, r12
0x1800470b5  jz      short loc_1800470D5
0x1800470b7  test    byte ptr [rcx+1Ch], 1
0x1800470bb  jz      short loc_1800470D5
0x1800470bd  mov     rcx, [rcx+10h]
0x1800470c1  lea     r8, WPP_aa991306b93132f591cbba2128657ece_Traceguids
0x1800470c8  mov     edx, 10h
0x1800470cd  mov     r9d, eax
0x1800470d0  call    WPP_SF_D
0x1800470d5  test    ebx, ebx
0x1800470d7  jle     short loc_1800470E2
0x1800470d9  movzx   ebx, bx
0x1800470dc  or      ebx, 80070000h
0x1800470e2  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800470e7  test    rcx, rcx
0x1800470ea  jz      short loc_1800470F8
0x1800470ec  call    cs:__imp_CloseHandle
0x1800470f3  nop     dword ptr [rax+rax+00h]
0x1800470f8  cmp     [rsp+48h+lpExistingFileName], 0
0x1800470fe  jz      short loc_18004710A
0x180047100  mov     rcx, [rsp+48h+lpExistingFileName]
0x180047105  call    MSCryptFree
0x18004710a  mov     eax, ebx
0x18004710c  mov     rbx, [rsp+48h+arg_8]
0x180047111  add     rsp, 30h
0x180047115  pop     r12
0x180047117  pop     rdi
0x180047118  pop     rbp
0x180047119  retn
```
