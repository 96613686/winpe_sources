# FwpBackupAndResetLogFile(_tag_FW_PROFILE_INDEX)

- ea: `0x180052a3c`
- end: `0x180052c8f`
- name: `?FwpBackupAndResetLogFile@@YAKW4_tag_FW_PROFILE_INDEX@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800526d0`
- `0x180093c9c`

## callees

- `0x18000af3c`
- `0x18002f120`
- `0x18003d5b0`
- `0x180052a3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c3a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180052c30`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180052c30`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180052beb`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180052beb`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180052b90`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180052b90`
- `fwbase!FwAlloc` at `0x180052a8e`
- `fwbase!FwAlloc` at `0x180052a8e`
- `fwbase!FwFree` at `0x180052c7a`
- `fwbase!FwFree` at `0x180052c7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180052a3c  push    rbx
0x180052a3e  push    rbp
0x180052a3f  push    rsi
0x180052a40  push    rdi
0x180052a41  push    r14
0x180052a43  push    r15
0x180052a45  sub     rsp, 38h
0x180052a49  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180052a4d  lea     r15, ?c_wszBackupFileExtension@@3PAGA; ".old"
0x180052a54  mov     r8, rdx
0x180052a57  xor     ebp, ebp
0x180052a59  inc     r8
0x180052a5c  cmp     [r15+r8*2], bp
0x180052a61  jnz     short loc_180052A59
0x180052a63  movsxd  rdi, ecx
0x180052a66  lea     r14, __ImageBase
0x180052a6d  mov     rax, qword ptr rva ?g_pSettings@@3PAPEAUtagHNET_FW_LOGGING_SETTINGS@@A[r14+rdi*8]; tagHNET_FW_LOGGING_SETTINGS * near * g_pSettings ...
0x180052a75  mov     rcx, [rax]
0x180052a78  inc     rdx
0x180052a7b  cmp     [rcx+rdx*2], bp
0x180052a7f  jnz     short loc_180052A78
0x180052a81  lea     rbx, [rdx+1]
0x180052a85  add     rbx, r8
0x180052a88  mov     ebx, ebx
0x180052a8a  lea     rcx, [rbx+rbx]
0x180052a8e  call    cs:__imp_FwAlloc
0x180052a94  mov     rsi, rax
0x180052a97  test    rax, rax
0x180052a9a  jnz     short loc_180052ADB
0x180052a9c  lea     ebx, [rax+0Eh]
0x180052a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052aa6  lea     rax, WPP_GLOBAL_Control
0x180052aad  cmp     rcx, rax
0x180052ab0  jz      loc_180052C80
0x180052ab6  test    byte ptr [rcx+1Ch], 1
0x180052aba  jz      loc_180052C80
0x180052ac0  mov     rcx, [rcx+10h]
0x180052ac4  lea     edx, [rsi+0Ch]
0x180052ac7  mov     r9d, ebx
0x180052aca  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x180052ad1  call    WPP_SF_d
0x180052ad6  jmp     loc_180052C80
0x180052adb  mov     r8, qword ptr rva ?g_pSettings@@3PAPEAUtagHNET_FW_LOGGING_SETTINGS@@A[r14+rdi*8]; tagHNET_FW_LOGGING_SETTINGS * near * g_pSettings ...
0x180052ae3  mov     rdx, rbx; unsigned __int64
0x180052ae6  mov     rcx, rsi; unsigned __int16 *
0x180052ae9  mov     r8, [r8]; unsigned __int16 *
0x180052aec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052af1  test    eax, eax
0x180052af3  jns     short loc_180052B36
0x180052af5  movzx   ebx, ax
0x180052af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180052aff  lea     rax, WPP_GLOBAL_Control
0x180052b06  cmp     rcx, rax
0x180052b09  jz      loc_180052C77
0x180052b0f  test    byte ptr [rcx+1Ch], 1
0x180052b13  jz      loc_180052C77
0x180052b19  mov     edx, 0Dh
0x180052b1e  mov     rcx, [rcx+10h]
0x180052b22  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x180052b29  mov     r9d, ebx
0x180052b2c  call    WPP_SF_d
0x180052b31  jmp     loc_180052C77
0x180052b36  mov     r8, r15; unsigned __int16 *
0x180052b39  mov     rdx, rbx; unsigned __int64
0x180052b3c  mov     rcx, rsi; unsigned __int16 *
0x180052b3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180052b44  test    eax, eax
0x180052b46  jns     short loc_180052B73
0x180052b48  movzx   ebx, ax
0x180052b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b52  lea     rax, WPP_GLOBAL_Control
0x180052b59  cmp     rcx, rax
0x180052b5c  jz      loc_180052C77
0x180052b62  test    byte ptr [rcx+1Ch], 1
0x180052b66  jz      loc_180052C77
0x180052b6c  mov     edx, 0Eh
0x180052b71  jmp     short loc_180052B1E
0x180052b73  mov     rcx, qword ptr rva ?g_pSettings@@3PAPEAUtagHNET_FW_LOGGING_SETTINGS@@A[r14+rdi*8]; tagHNET_FW_LOGGING_SETTINGS * near * g_pSettings ...
0x180052b7b  xor     r9d, r9d; lpData
0x180052b7e  mov     [rsp+68h+dwCopyFlags], ebp; dwCopyFlags
0x180052b82  xor     r8d, r8d; lpProgressRoutine
0x180052b85  mov     rdx, rsi; lpNewFileName
0x180052b88  mov     [rsp+68h+pbCancel], rbp; pbCancel
0x180052b8d  mov     rcx, [rcx]; lpExistingFileName
0x180052b90  call    cs:__imp_CopyFileExW
0x180052b96  test    eax, eax
0x180052b98  jnz     short loc_180052BCD
0x180052b9a  call    cs:__imp_GetLastError
0x180052ba0  mov     ebx, eax
0x180052ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ba9  lea     rax, WPP_GLOBAL_Control
0x180052bb0  cmp     rcx, rax
0x180052bb3  jz      loc_180052C77
0x180052bb9  test    byte ptr [rcx+1Ch], 1
0x180052bbd  jz      loc_180052C77
0x180052bc3  mov     edx, 0Fh
0x180052bc8  jmp     loc_180052B1E
0x180052bcd  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[r14+rdi*4]; ulong near * ProfileToFile ...
0x180052bd5  xor     r9d, r9d; dwMoveMethod
0x180052bd8  xor     r8d, r8d; lpNewFilePointer
0x180052bdb  mov     [rsp+68h+arg_8], rbp
0x180052be0  mov     rdx, rbp; liDistanceToMove
0x180052be3  mov     rcx, rva ?g_hFile@@3PAPEAXA[r14+rcx*8]; hFile
0x180052beb  call    cs:__imp_SetFilePointerEx
0x180052bf1  test    eax, eax
0x180052bf3  jnz     short loc_180052C20
0x180052bf5  call    cs:__imp_GetLastError
0x180052bfb  mov     ebx, eax
0x180052bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c04  lea     rax, WPP_GLOBAL_Control
0x180052c0b  cmp     rcx, rax
0x180052c0e  jz      short loc_180052C77
0x180052c10  test    byte ptr [rcx+1Ch], 1
0x180052c14  jz      short loc_180052C77
0x180052c16  mov     edx, 10h
0x180052c1b  jmp     loc_180052B1E
0x180052c20  mov     ecx, dword ptr rva ?ProfileToFile@@3PAKA[r14+rdi*4]; ulong near * ProfileToFile ...
0x180052c28  mov     rcx, rva ?g_hFile@@3PAPEAXA[r14+rcx*8]; hFile
0x180052c30  call    cs:__imp_SetEndOfFile
0x180052c36  test    eax, eax
0x180052c38  jnz     short loc_180052C65
0x180052c3a  call    cs:__imp_GetLastError
0x180052c40  mov     ebx, eax
0x180052c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c49  lea     rax, WPP_GLOBAL_Control
0x180052c50  cmp     rcx, rax
0x180052c53  jz      short loc_180052C77
0x180052c55  test    byte ptr [rcx+1Ch], 1
0x180052c59  jz      short loc_180052C77
0x180052c5b  mov     edx, 11h
0x180052c60  jmp     loc_180052B1E
0x180052c65  mov     eax, dword ptr rva ?ProfileToFile@@3PAKA[r14+rdi*4]; ulong near * ProfileToFile ...
0x180052c6d  mov     ebx, ebp
0x180052c6f  mov     rva ?g_dwFileOffset@@3PAKA[r14+rax*4], ebp; ulong near * g_dwFileOffset ...
0x180052c77  mov     rcx, rsi
0x180052c7a  call    cs:__imp_FwFree
0x180052c80  mov     eax, ebx
0x180052c82  add     rsp, 38h
0x180052c86  pop     r15
0x180052c88  pop     r14
0x180052c8a  pop     rdi
0x180052c8b  pop     rsi
0x180052c8c  pop     rbp
0x180052c8d  pop     rbx
0x180052c8e  retn
```
