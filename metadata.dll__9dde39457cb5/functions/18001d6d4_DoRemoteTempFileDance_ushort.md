# DoRemoteTempFileDance(ushort *)

- ea: `0x18001d6d4`
- end: `0x18001d913`
- name: `?DoRemoteTempFileDance@@YAJPEAG@Z`
- size: `575`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180018f60`

## callees

- `0x18000e9b8`
- `0x18001c508`
- `0x18001d6d4`
- `0x1800204fc`
- `0x180020940`
- `0x1800274d0`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x18001d7ea`
- `KERNEL32!MoveFileExW` at `0x18001d822`
- `KERNEL32!MoveFileExW` at `0x18001d8b3`
- `KERNEL32!MoveFileExW` at `0x18001d7ea`
- `KERNEL32!MoveFileExW` at `0x18001d822`
- `KERNEL32!MoveFileExW` at `0x18001d8b3`
- `KERNEL32!DeleteFileW` at `0x18001d85a`
- `KERNEL32!DeleteFileW` at `0x18001d85a`
- `KERNEL32!GetLastError` at `0x18001d7f4`
- `KERNEL32!GetLastError` at `0x18001d864`
- `KERNEL32!GetLastError` at `0x18001d873`
- `KERNEL32!GetLastError` at `0x18001d7f4`
- `KERNEL32!GetLastError` at `0x18001d864`
- `KERNEL32!GetLastError` at `0x18001d873`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18001d8e3`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18001d8ee`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18001d8e3`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18001d8ee`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001d730`
- `IisRTL!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001d730`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d795`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d7ce`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d7da`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d802`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d810`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d833`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d851`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d893`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d8a1`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d8c0`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d795`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d7ce`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d7da`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d802`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d810`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d833`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d851`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d893`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d8a1`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d8c0`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18001d6ff`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18001d70a`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18001d6ff`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18001d70a`

## pseudocode

```c
__int64 __fastcall DoRemoteTempFileDance(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rbx
  signed int PathFrom; // edi
  unsigned __int16 *Str; // rax
  int v4; // esi
  const WCHAR *v5; // rbx
  const WCHAR *v6; // rax
  const WCHAR *v7; // rbx
  const WCHAR *v8; // rax
  int v9; // ebx
  unsigned __int16 *v10; // rax
  const WCHAR *v11; // rax
  signed int LastError; // eax
  const WCHAR *v13; // rbx
  const WCHAR *v14; // rax
  unsigned __int16 *v15; // rax
  _BYTE v17[56]; // [rsp+20h] [rbp-A8h] BYREF
  _BYTE v18[56]; // [rsp+58h] [rbp-70h] BYREF

  v1 = (unsigned __int16 *)g_wszTempFileName;
  STRU::STRU((STRU *)v18);
  STRU::STRU((STRU *)v17);
  if ( !v1 || !(unsigned int)ShouldDoPublish() || STRU::IsEmpty((STRU *)g_struRemoteRealName) )
  {
    PathFrom = -2147024809;
    goto LABEL_26;
  }
  PathFrom = MakePathFrom(
               (struct STRU *)v18,
               (struct STRU *)g_struChangeNotificationDirectory,
               g_wszRealFileNameWithoutPath,
               L".tmp");
  if ( PathFrom < 0 )
    goto LABEL_26;
  PathFrom = MakePathFrom(
               (struct STRU *)v17,
               (struct STRU *)g_struChangeNotificationDirectory,
               g_wszRealFileNameWithoutPath,
               L".bak");
  if ( PathFrom < 0 )
    goto LABEL_26;
  Str = STRU::QueryStr((STRU *)v18);
  PathFrom = CopyFileWithSecurityDescriptor(v1, Str);
  if ( PathFrom < 0 )
    goto LABEL_26;
  PathFrom = UnlockMetabaseFile(2);
  if ( PathFrom < 0 )
    goto LABEL_26;
  v4 = 1;
  v5 = STRU::QueryStr((STRU *)v17);
  v6 = STRU::QueryStr((STRU *)g_struRemoteRealName);
  if ( MoveFileExW(v6, v5, 9u) || GetLastError() == 2 )
  {
    v7 = STRU::QueryStr((STRU *)g_struRemoteRealName);
    v8 = STRU::QueryStr((STRU *)v18);
    if ( !MoveFileExW(v8, v7, 9u) )
    {
      v9 = 1;
      goto LABEL_17;
    }
    v10 = STRU::QueryStr((STRU *)g_struRemoteRealName);
    PathFrom = LockMetabaseFile(v10, 2);
    if ( PathFrom < 0 )
    {
LABEL_23:
      v15 = STRU::QueryStr((STRU *)g_struRemoteRealName);
      LockMetabaseFile(v15, 2);
      goto LABEL_26;
    }
    v11 = STRU::QueryStr((STRU *)v17);
    if ( DeleteFileW(v11) || GetLastError() == 2 )
    {
      PathFrom = 0;
      goto LABEL_26;
    }
    v4 = 0;
  }
  v9 = 0;
LABEL_17:
  LastError = GetLastError();
  PathFrom = LastError;
  if ( LastError > 0 )
    PathFrom = (unsigned __int16)LastError | 0x80070000;
  if ( PathFrom < 0 )
  {
    if ( v9 )
    {
      v13 = STRU::QueryStr((STRU *)g_struRemoteRealName);
      v14 = STRU::QueryStr((STRU *)v17);
      MoveFileExW(v14, v13, 9u);
    }
    if ( v4 )
      goto LABEL_23;
  }
LABEL_26:
  STRU::~STRU((STRU *)v17);
  STRU::~STRU((STRU *)v18);
  return (unsigned int)PathFrom;
}

```

## disassembly

```asm
0x18001d6d4  push    rbx
0x18001d6d6  push    rsi
0x18001d6d7  push    rdi
0x18001d6d8  push    r14
0x18001d6da  sub     rsp, 0A8h
0x18001d6e1  mov     rax, cs:__security_cookie
0x18001d6e8  xor     rax, rsp
0x18001d6eb  mov     [rsp+0C8h+var_38], rax
0x18001d6f3  mov     rbx, cs:?g_wszTempFileName@@3PEAGEA; ushort * g_wszTempFileName
0x18001d6fa  lea     rcx, [rsp+0C8h+var_70]
0x18001d6ff  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001d705  lea     rcx, [rsp+0C8h+var_A8]
0x18001d70a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001d710  test    rbx, rbx
0x18001d713  jz      loc_18001D8D9
0x18001d719  call    ?ShouldDoPublish@@YAHXZ; ShouldDoPublish(void)
0x18001d71e  test    eax, eax
0x18001d720  jz      loc_18001D8D9
0x18001d726  lea     r14, ?g_struRemoteRealName@@3VSTRU@@A; STRU g_struRemoteRealName
0x18001d72d  mov     rcx, r14
0x18001d730  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18001d736  test    al, al
0x18001d738  jnz     loc_18001D8D9
0x18001d73e  mov     r8, cs:?g_wszRealFileNameWithoutPath@@3PEAGEA; unsigned __int16 *
0x18001d745  lea     r9, aTmp; ".tmp"
0x18001d74c  lea     rdx, ?g_struChangeNotificationDirectory@@3VSTRU@@A; struct STRU *
0x18001d753  lea     rcx, [rsp+0C8h+var_70]; struct STRU *
0x18001d758  call    ?MakePathFrom@@YAJPEAVSTRU@@0PEBG1@Z; MakePathFrom(STRU *,STRU *,ushort const *,ushort const *)
0x18001d75d  mov     edi, eax
0x18001d75f  test    eax, eax
0x18001d761  js      loc_18001D8DE
0x18001d767  mov     r8, cs:?g_wszRealFileNameWithoutPath@@3PEAGEA; unsigned __int16 *
0x18001d76e  lea     r9, aBak_0; ".bak"
0x18001d775  lea     rdx, ?g_struChangeNotificationDirectory@@3VSTRU@@A; struct STRU *
0x18001d77c  lea     rcx, [rsp+0C8h+var_A8]; struct STRU *
0x18001d781  call    ?MakePathFrom@@YAJPEAVSTRU@@0PEBG1@Z; MakePathFrom(STRU *,STRU *,ushort const *,ushort const *)
0x18001d786  mov     edi, eax
0x18001d788  test    eax, eax
0x18001d78a  js      loc_18001D8DE
0x18001d790  lea     rcx, [rsp+0C8h+var_70]
0x18001d795  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d79b  mov     rdx, rax; unsigned __int16 *
0x18001d79e  mov     rcx, rbx; unsigned __int16 *
0x18001d7a1  call    ?CopyFileWithSecurityDescriptor@@YAJPEAG0@Z; CopyFileWithSecurityDescriptor(ushort *,ushort *)
0x18001d7a6  mov     edi, eax
0x18001d7a8  test    eax, eax
0x18001d7aa  js      loc_18001D8DE
0x18001d7b0  mov     ecx, 2
0x18001d7b5  call    ?UnlockMetabaseFile@@YAJW4_eMetabaseFile@@H@Z; UnlockMetabaseFile(_eMetabaseFile,int)
0x18001d7ba  mov     edi, eax
0x18001d7bc  test    eax, eax
0x18001d7be  js      loc_18001D8DE
0x18001d7c4  lea     rcx, [rsp+0C8h+var_A8]
0x18001d7c9  mov     esi, 1
0x18001d7ce  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d7d4  mov     rcx, r14
0x18001d7d7  mov     rbx, rax
0x18001d7da  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d7e0  lea     r8d, [rsi+8]; dwFlags
0x18001d7e4  mov     rdx, rbx; lpNewFileName
0x18001d7e7  mov     rcx, rax; lpExistingFileName
0x18001d7ea  call    cs:__imp_MoveFileExW
0x18001d7f0  test    eax, eax
0x18001d7f2  jnz     short loc_18001D7FF
0x18001d7f4  call    cs:__imp_GetLastError
0x18001d7fa  cmp     eax, 2
0x18001d7fd  jnz     short loc_18001D871
0x18001d7ff  mov     rcx, r14
0x18001d802  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d808  lea     rcx, [rsp+0C8h+var_70]
0x18001d80d  mov     rbx, rax
0x18001d810  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d816  mov     r8d, 9; dwFlags
0x18001d81c  mov     rdx, rbx; lpNewFileName
0x18001d81f  mov     rcx, rax; lpExistingFileName
0x18001d822  call    cs:__imp_MoveFileExW
0x18001d828  test    eax, eax
0x18001d82a  jnz     short loc_18001D830
0x18001d82c  mov     ebx, esi
0x18001d82e  jmp     short loc_18001D873
0x18001d830  mov     rcx, r14
0x18001d833  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d839  mov     rcx, rax
0x18001d83c  mov     edx, 2
0x18001d841  call    ?LockMetabaseFile@@YAJPEBGW4_eMetabaseFile@@H@Z; LockMetabaseFile(ushort const *,_eMetabaseFile,int)
0x18001d846  mov     edi, eax
0x18001d848  test    eax, eax
0x18001d84a  js      short loc_18001D8BD
0x18001d84c  lea     rcx, [rsp+0C8h+var_A8]
0x18001d851  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d857  mov     rcx, rax; lpFileName
0x18001d85a  call    cs:__imp_DeleteFileW
0x18001d860  test    eax, eax
0x18001d862  jnz     short loc_18001D8D5
0x18001d864  call    cs:__imp_GetLastError
0x18001d86a  cmp     eax, 2
0x18001d86d  jz      short loc_18001D8D5
0x18001d86f  xor     esi, esi
0x18001d871  xor     ebx, ebx
0x18001d873  call    cs:__imp_GetLastError
0x18001d879  mov     edi, eax
0x18001d87b  test    eax, eax
0x18001d87d  jle     short loc_18001D888
0x18001d87f  movzx   edi, ax
0x18001d882  or      edi, 80070000h
0x18001d888  test    edi, edi
0x18001d88a  jns     short loc_18001D8DE
0x18001d88c  test    ebx, ebx
0x18001d88e  jz      short loc_18001D8B9
0x18001d890  mov     rcx, r14
0x18001d893  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d899  lea     rcx, [rsp+0C8h+var_A8]
0x18001d89e  mov     rbx, rax
0x18001d8a1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d8a7  mov     r8d, 9; dwFlags
0x18001d8ad  mov     rdx, rbx; lpNewFileName
0x18001d8b0  mov     rcx, rax; lpExistingFileName
0x18001d8b3  call    cs:__imp_MoveFileExW
0x18001d8b9  test    esi, esi
0x18001d8bb  jz      short loc_18001D8DE
0x18001d8bd  mov     rcx, r14
0x18001d8c0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d8c6  mov     rcx, rax
0x18001d8c9  mov     edx, 2
0x18001d8ce  call    ?LockMetabaseFile@@YAJPEBGW4_eMetabaseFile@@H@Z; LockMetabaseFile(ushort const *,_eMetabaseFile,int)
0x18001d8d3  jmp     short loc_18001D8DE
0x18001d8d5  xor     edi, edi
0x18001d8d7  jmp     short loc_18001D8DE
0x18001d8d9  mov     edi, 80070057h
0x18001d8de  lea     rcx, [rsp+0C8h+var_A8]
0x18001d8e3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d8e9  lea     rcx, [rsp+0C8h+var_70]
0x18001d8ee  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d8f4  mov     eax, edi
0x18001d8f6  mov     rcx, [rsp+0C8h+var_38]
0x18001d8fe  xor     rcx, rsp; StackCookie
0x18001d901  call    __security_check_cookie
0x18001d906  add     rsp, 0A8h
0x18001d90d  pop     r14
0x18001d90f  pop     rdi
0x18001d910  pop     rsi
0x18001d911  pop     rbx
0x18001d912  retn
```
