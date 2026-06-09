# FwpBackupAndResetLogFile(_tag_FW_PROFILE_INDEX)

- ea: `0x180056edc`
- end: `0x180057160`
- name: `?FwpBackupAndResetLogFile@@YAKW4_tag_FW_PROFILE_INDEX@@@Z`
- size: `644`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180056b40`
- `0x180098a6c`

## callees

- `0x18000a710`
- `0x180032990`
- `0x18003d990`
- `0x180056edc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800570ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800570fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800570ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800570fe`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800570ee`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800570ee`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18005709d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18005709d`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180057036`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180057036`
- `fwbase!FwAlloc` at `0x180056f2e`
- `fwbase!FwAlloc` at `0x180056f2e`
- `fwbase!FwFree` at `0x180057144`
- `fwbase!FwFree` at `0x180057144`

## pseudocode

```c
__int64 __fastcall FwpBackupAndResetLogFile(int a1)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // rdi
  __int64 v4; // rcx
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rsi
  DWORD LastError; // ebx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // eax

  v1 = -1;
  v2 = -1;
  do
    ++v2;
  while ( c_wszBackupFileExtension[v2] );
  v3 = a1;
  v4 = (__int64)*(&g_pSettings)[a1];
  do
    ++v1;
  while ( *(_WORD *)(v4 + 2 * v1) );
  v5 = (unsigned int)(v2 + v1 + 1);
  v6 = (unsigned __int16 *)FwAlloc(2 * v5);
  v7 = v6;
  if ( v6 )
  {
    v9 = StringCchCopyW(v6, v5, (const unsigned __int16 *)*(&g_pSettings)[v3]);
    if ( v9 >= 0 )
    {
      v12 = StringCchCatW(v7, v5, c_wszBackupFileExtension);
      if ( v12 >= 0 )
      {
        if ( CopyFileExW((LPCWSTR)*(&g_pSettings)[v3], v7, 0, 0, 0, 0) )
        {
          if ( SetFilePointerEx((&g_hFile)[*((unsigned int *)&ProfileToFile + v3)], 0, 0, 0) )
          {
            if ( SetEndOfFile((&g_hFile)[*((unsigned int *)&ProfileToFile + v3)]) )
            {
              LastError = 0;
              *((_DWORD *)&g_dwFileOffset + *((unsigned int *)&ProfileToFile + v3)) = 0;
              goto LABEL_31;
            }
            LastError = GetLastError();
            v10 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_31;
            }
            v11 = 17;
          }
          else
          {
            LastError = GetLastError();
            v10 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_31;
            }
            v11 = 16;
          }
        }
        else
        {
          LastError = GetLastError();
          v10 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_31;
          v11 = 15;
        }
      }
      else
      {
        LastError = (unsigned __int16)v12;
        v10 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_31;
        v11 = 14;
      }
    }
    else
    {
      LastError = (unsigned __int16)v9;
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_31;
      v11 = 13;
    }
    WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, LastError);
LABEL_31:
    FwFree(v7);
    return LastError;
  }
  LastError = 14;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, 14);
  return LastError;
}

```

## disassembly

```asm
0x180056edc  push    rbx
0x180056ede  push    rbp
0x180056edf  push    rsi
0x180056ee0  push    rdi
0x180056ee1  push    r14
0x180056ee3  push    r15
0x180056ee5  sub     rsp, 38h
0x180056ee9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180056eed  lea     r15, ?c_wszBackupFileExtension@@3PAGA; ".old"
0x180056ef4  mov     r8, rdx
0x180056ef7  xor     ebp, ebp
0x180056ef9  inc     r8
0x180056efc  cmp     [r15+r8*2], bp
0x180056f01  jnz     short loc_180056EF9
0x180056f03  movsxd  rdi, ecx
0x180056f06  lea     r14, __ImageBase
0x180056f0d  mov     rax, qword ptr rva ?g_pSettings@@3PAPEAUtagHNET_FW_LOGGING_SETTINGS@@A[r14+rdi*8]; tagHNET_FW_LOGGING_SETTINGS * near * g_pSettings ...
0x180056f15  mov     rcx, [rax]
0x180056f18  inc     rdx
0x180056f1b  cmp     [rcx+rdx*2], bp
0x180056f1f  jnz     short loc_180056F18
0x180056f21  lea     rbx, [rdx+1]
0x180056f25  add     rbx, r8
0x180056f28  mov     ebx, ebx
0x180056f2a  lea     rcx, [rbx+rbx]
0x180056f2e  call    cs:__imp_FwAlloc
0x180056f35  nop     dword ptr [rax+rax+00h]
0x180056f3a  mov     rsi, rax
0x180056f3d  test    rax, rax
0x180056f40  jnz     short loc_180056F81
0x180056f42  lea     ebx, [rax+0Eh]
0x180056f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f4c  lea     rax, WPP_GLOBAL_Control
0x180056f53  cmp     rcx, rax
0x180056f56  jz      loc_180057150
0x180056f5c  test    byte ptr [rcx+1Ch], 1
0x180056f60  jz      loc_180057150
0x180056f66  mov     rcx, [rcx+10h]
0x180056f6a  lea     edx, [rsi+0Ch]
0x180056f6d  mov     r9d, ebx
0x180056f70  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x180056f77  call    WPP_SF_d
0x180056f7c  jmp     loc_180057150
0x180056f81  mov     r8, qword ptr rva ?g_pSettings@@3PAPEAUtagHNET_FW_LOGGING_SETTINGS@@A[r14+rdi*8]; tagHNET_FW_LOGGING_SETTINGS * near * g_pSettings ...
0x180056f89  mov     rdx, rbx; unsigned __int64
0x180056f8c  mov     rcx, rsi; unsigned __int16 *
0x180056f8f  mov     r8, [r8]; unsigned __int16 *
0x180056f92  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056f97  test    eax, eax
0x180056f99  jns     short loc_180056FDC
0x180056f9b  movzx   ebx, ax
0x180056f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056fa5  lea     rax, WPP_GLOBAL_Control
0x180056fac  cmp     rcx, rax
0x180056faf  jz      loc_180057141
0x180056fb5  test    byte ptr [rcx+1Ch], 1
0x180056fb9  jz      loc_180057141
0x180056fbf  mov     edx, 0Dh
0x180056fc4  mov     rcx, [rcx+10h]
0x180056fc8  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x180056fcf  mov     r9d, ebx
0x180056fd2  call    WPP_SF_d
0x180056fd7  jmp     loc_180057141
0x180056fdc  mov     r8, r15; unsigned __int16 *
0x180056fdf  mov     rdx, rbx; unsigned __int64
0x180056fe2  mov     rcx, rsi; unsigned __int16 *
0x180056fe5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180056fea  test    eax, eax
0x180056fec  jns     short loc_180057019
0x180056fee  movzx   ebx, ax
0x180056ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ff8  lea     rax, WPP_GLOBAL_Control
0x180056fff  cmp     rcx, rax
0x180057002  jz      loc_180057141
0x180057008  test    byte ptr [rcx+1Ch], 1
0x18005700c  jz      loc_180057141
0x180057012  mov     edx, 0Eh
0x180057017  jmp     short loc_180056FC4
0x180057019  mov     rcx, qword ptr rva ?g_pSettings@@3PAPEAUtagHNET_FW_LOGGING_SETTINGS@@A[r14+rdi*8]; tagHNET_FW_LOGGING_SETTINGS * near * g_pSettings ...
0x180057021  xor     r9d, r9d; lpData
0x180057024  mov     [rsp+68h+dwCopyFlags], ebp; dwCopyFlags
0x180057028  xor     r8d, r8d; lpProgressRoutine
0x18005702b  mov     rdx, rsi; lpNewFileName
0x18005702e  mov     [rsp+68h+pbCancel], rbp; pbCancel
0x180057033  mov     rcx, [rcx]; lpExistingFileName
0x180057036  call    cs:__imp_CopyFileExW
0x18005703d  nop     dword ptr [rax+rax+00h]
0x180057042  test    eax, eax
0x180057044  jnz     short loc_18005707F
0x180057046  call    cs:__imp_GetLastError
0x18005704d  nop     dword ptr [rax+rax+00h]
0x180057052  mov     ebx, eax
0x180057054  mov     rcx, cs:WPP_GLOBAL_Control
0x18005705b  lea     rax, WPP_GLOBAL_Control
0x180057062  cmp     rcx, rax
0x180057065  jz      loc_180057141
0x18005706b  test    byte ptr [rcx+1Ch], 1
0x18005706f  jz      loc_180057141
0x180057075  mov     edx, 0Fh
0x18005707a  jmp     loc_180056FC4
0x18005707f  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[r14+rdi*4]; ulong near * ProfileToFile ...
0x180057087  xor     r9d, r9d; dwMoveMethod
0x18005708a  xor     r8d, r8d; lpNewFilePointer
0x18005708d  mov     [rsp+68h+arg_8], rbp
0x180057092  mov     rdx, rbp; liDistanceToMove
0x180057095  mov     rcx, rva ?g_hFile@@3PAPEAXA[r14+rcx*8]; hFile
0x18005709d  call    cs:__imp_SetFilePointerEx
0x1800570a4  nop     dword ptr [rax+rax+00h]
0x1800570a9  test    eax, eax
0x1800570ab  jnz     short loc_1800570DE
0x1800570ad  call    cs:__imp_GetLastError
0x1800570b4  nop     dword ptr [rax+rax+00h]
0x1800570b9  mov     ebx, eax
0x1800570bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800570c2  lea     rax, WPP_GLOBAL_Control
0x1800570c9  cmp     rcx, rax
0x1800570cc  jz      short loc_180057141
0x1800570ce  test    byte ptr [rcx+1Ch], 1
0x1800570d2  jz      short loc_180057141
0x1800570d4  mov     edx, 10h
0x1800570d9  jmp     loc_180056FC4
0x1800570de  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[r14+rdi*4]; ulong near * ProfileToFile ...
0x1800570e6  mov     rcx, rva ?g_hFile@@3PAPEAXA[r14+rcx*8]; hFile
0x1800570ee  call    cs:__imp_SetEndOfFile
0x1800570f5  nop     dword ptr [rax+rax+00h]
0x1800570fa  test    eax, eax
0x1800570fc  jnz     short loc_18005712F
0x1800570fe  call    cs:__imp_GetLastError
0x180057105  nop     dword ptr [rax+rax+00h]
0x18005710a  mov     ebx, eax
0x18005710c  mov     rcx, cs:WPP_GLOBAL_Control
0x180057113  lea     rax, WPP_GLOBAL_Control
0x18005711a  cmp     rcx, rax
0x18005711d  jz      short loc_180057141
0x18005711f  test    byte ptr [rcx+1Ch], 1
0x180057123  jz      short loc_180057141
0x180057125  mov     edx, 11h
0x18005712a  jmp     loc_180056FC4
0x18005712f  mov     eax, dword ptr rva ?ProfileToFile@@3PAKA[r14+rdi*4]; ulong near * ProfileToFile ...
0x180057137  mov     ebx, ebp
0x180057139  mov     rva ?g_dwFileOffset@@3PAKA[r14+rax*4], ebp; ulong near * g_dwFileOffset ...
0x180057141  mov     rcx, rsi
0x180057144  call    cs:__imp_FwFree
0x18005714b  nop     dword ptr [rax+rax+00h]
0x180057150  mov     eax, ebx
0x180057152  add     rsp, 38h
0x180057156  pop     r15
0x180057158  pop     r14
0x18005715a  pop     rdi
0x18005715b  pop     rsi
0x18005715c  pop     rbp
0x18005715d  pop     rbx
0x18005715e  retn
```
